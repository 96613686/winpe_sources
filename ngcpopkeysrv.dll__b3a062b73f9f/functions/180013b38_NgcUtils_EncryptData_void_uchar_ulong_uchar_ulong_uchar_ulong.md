# NgcUtils::EncryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180013b38`
- end: `0x180013c90`
- name: `?EncryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z`
- size: `344`
- prototype: `int __fastcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, UCHAR *, ULONG cbIV, PUCHAR *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ed50`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x18001368c`
- `0x180013b38`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013c5e`
- `bcrypt!BCryptEncrypt` at `0x180013b8e`
- `bcrypt!BCryptEncrypt` at `0x180013c2e`
- `bcrypt!BCryptEncrypt` at `0x180013b8e`
- `bcrypt!BCryptEncrypt` at `0x180013c2e`

## string_xrefs

- `0x180013ba0`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013bd9`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013c40`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
int __fastcall NgcUtils::EncryptData(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        UCHAR *a4,
        ULONG cbIV,
        PUCHAR *a6,
        unsigned __int8 **a7)
{
  NTSTATUS v11; // eax
  PUCHAR v13; // rbx
  NTSTATUS v14; // eax
  int v15; // edi
  int pbIV; // [rsp+20h] [rbp-78h]
  int pbIVa; // [rsp+20h] [rbp-78h]
  ULONG pcbResult; // [rsp+50h] [rbp-48h] BYREF
  PUCHAR pbOutput[8]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  pcbResult = 0;
  v11 = BCryptEncrypt(hKey, pbInput, cbInput, 0, a4, cbIV, 0, 0, &pcbResult, 1u);
  if ( v11 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x2B6,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v11,
             pbIV);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(pbOutput, pcbResult);
  v13 = pbOutput[0];
  if ( pbOutput[0] )
  {
    v14 = BCryptEncrypt(hKey, pbInput, cbInput, 0, a4, cbIV, pbOutput[0], pcbResult, &pcbResult, 1u);
    if ( v14 >= 0 )
    {
      *a6 = v13;
      *(_DWORD *)a7 = pcbResult;
      return 0;
    }
    else
    {
      v15 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x2C5,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
              (const char *)(unsigned int)v14,
              pbIVa);
      if ( v13 )
        LocalFree(v13);
      return v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      pbIV);
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180013b38  mov     r11, rsp
0x180013b3b  push    rbx
0x180013b3c  push    rbp
0x180013b3d  push    rsi
0x180013b3e  push    rdi
0x180013b3f  push    r14
0x180013b41  push    r15
0x180013b43  sub     rsp, 68h
0x180013b47  mov     r15d, [rsp+98h+arg_20]
0x180013b4f  lea     rax, [r11-48h]
0x180013b53  mov     [rsp+98h+dwFlags], 1; dwFlags
0x180013b5b  mov     rdi, r9
0x180013b5e  mov     [r11-58h], rax
0x180013b62  mov     esi, r8d
0x180013b65  mov     [rsp+98h+cbOutput], 0; cbOutput
0x180013b6d  mov     rbp, rdx
0x180013b70  mov     qword ptr [r11-68h], 0
0x180013b78  mov     r14, rcx
0x180013b7b  mov     [r11-70h], r15d
0x180013b7f  mov     [r11-78h], r9
0x180013b83  xor     r9d, r9d; pPaddingInfo
0x180013b86  mov     [rsp+98h+var_48], 0
0x180013b8e  call    cs:__imp_BCryptEncrypt
0x180013b94  test    eax, eax
0x180013b96  jns     short loc_180013BB9
0x180013b98  mov     rcx, [rsp+98h]; this
0x180013ba0  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013ba7  mov     r9d, eax; char *
0x180013baa  mov     edx, 2B6h; void *
0x180013baf  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013bb4  jmp     loc_180013C83
0x180013bb9  mov     edx, [rsp+98h+var_48]
0x180013bbd  lea     rcx, [rsp+98h+var_40]
0x180013bc2  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180013bc7  mov     rbx, [rsp+98h+var_40]
0x180013bcc  test    rbx, rbx
0x180013bcf  jnz     short loc_180013BF9
0x180013bd1  mov     rcx, [rsp+98h]; this
0x180013bd9  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013be0  mov     ebx, 8007000Eh
0x180013be5  mov     edx, 2B9h; void *
0x180013bea  mov     r9d, ebx; char *
0x180013bed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013bf2  mov     eax, ebx
0x180013bf4  jmp     loc_180013C83
0x180013bf9  mov     eax, [rsp+98h+var_48]
0x180013bfd  lea     rcx, [rsp+98h+var_48]
0x180013c02  mov     [rsp+98h+dwFlags], 1; dwFlags
0x180013c0a  xor     r9d, r9d; pPaddingInfo
0x180013c0d  mov     [rsp+98h+pcbResult], rcx; pcbResult
0x180013c12  mov     r8d, esi; cbInput
0x180013c15  mov     [rsp+98h+cbOutput], eax; cbOutput
0x180013c19  mov     rdx, rbp; pbInput
0x180013c1c  mov     [rsp+98h+pbOutput], rbx; pbOutput
0x180013c21  mov     rcx, r14; hKey
0x180013c24  mov     [rsp+98h+cbIV], r15d; cbIV
0x180013c29  mov     [rsp+98h+pbIV], rdi; int
0x180013c2e  call    cs:__imp_BCryptEncrypt
0x180013c34  test    eax, eax
0x180013c36  jns     short loc_180013C68
0x180013c38  mov     rcx, [rsp+98h]; this
0x180013c40  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013c47  mov     r9d, eax; char *
0x180013c4a  mov     edx, 2C5h; void *
0x180013c4f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013c54  mov     edi, eax
0x180013c56  test    rbx, rbx
0x180013c59  jz      short loc_180013C64
0x180013c5b  mov     rcx, rbx; hMem
0x180013c5e  call    cs:__imp_LocalFree
0x180013c64  mov     eax, edi
0x180013c66  jmp     short loc_180013C83
0x180013c68  mov     rax, [rsp+98h+arg_28]
0x180013c70  mov     rcx, [rsp+98h+arg_30]
0x180013c78  mov     [rax], rbx
0x180013c7b  mov     eax, [rsp+98h+var_48]
0x180013c7f  mov     [rcx], eax
0x180013c81  xor     eax, eax
0x180013c83  add     rsp, 68h
0x180013c87  pop     r15
0x180013c89  pop     r14
0x180013c8b  pop     rdi
0x180013c8c  pop     rsi
0x180013c8d  pop     rbp
0x180013c8e  pop     rbx
0x180013c8f  retn
```
