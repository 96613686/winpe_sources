# NgcUtils::DecryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180013834`
- end: `0x18001398c`
- name: `?DecryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z`
- size: `344`
- prototype: `int __fastcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, UCHAR *, ULONG cbIV, PUCHAR *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ea50`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x18001368c`
- `0x180013834`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001395a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001395a`
- `bcrypt!BCryptDecrypt` at `0x18001388a`
- `bcrypt!BCryptDecrypt` at `0x18001392a`
- `bcrypt!BCryptDecrypt` at `0x18001388a`
- `bcrypt!BCryptDecrypt` at `0x18001392a`

## string_xrefs

- `0x18001389c`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x1800138d5`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001393c`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
int __fastcall NgcUtils::DecryptData(
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
  v11 = BCryptDecrypt(hKey, pbInput, cbInput, 0, a4, cbIV, 0, 0, &pcbResult, 1u);
  if ( v11 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x30C,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v11,
             pbIV);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(pbOutput, pcbResult);
  v13 = pbOutput[0];
  if ( pbOutput[0] )
  {
    v14 = BCryptDecrypt(hKey, pbInput, cbInput, 0, a4, cbIV, pbOutput[0], pcbResult, &pcbResult, 1u);
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
              (void *)0x31B,
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
      (void *)0x30F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      pbIV);
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180013834  mov     r11, rsp
0x180013837  push    rbx
0x180013838  push    rbp
0x180013839  push    rsi
0x18001383a  push    rdi
0x18001383b  push    r14
0x18001383d  push    r15
0x18001383f  sub     rsp, 68h
0x180013843  mov     r15d, [rsp+98h+arg_20]
0x18001384b  lea     rax, [r11-48h]
0x18001384f  mov     [rsp+98h+dwFlags], 1; dwFlags
0x180013857  mov     rdi, r9
0x18001385a  mov     [r11-58h], rax
0x18001385e  mov     esi, r8d
0x180013861  mov     [rsp+98h+cbOutput], 0; cbOutput
0x180013869  mov     rbp, rdx
0x18001386c  mov     qword ptr [r11-68h], 0
0x180013874  mov     r14, rcx
0x180013877  mov     [r11-70h], r15d
0x18001387b  mov     [r11-78h], r9
0x18001387f  xor     r9d, r9d; pPaddingInfo
0x180013882  mov     [rsp+98h+var_48], 0
0x18001388a  call    cs:__imp_BCryptDecrypt
0x180013890  test    eax, eax
0x180013892  jns     short loc_1800138B5
0x180013894  mov     rcx, [rsp+98h]; this
0x18001389c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800138a3  mov     r9d, eax; char *
0x1800138a6  mov     edx, 30Ch; void *
0x1800138ab  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800138b0  jmp     loc_18001397F
0x1800138b5  mov     edx, [rsp+98h+var_48]
0x1800138b9  lea     rcx, [rsp+98h+var_40]
0x1800138be  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800138c3  mov     rbx, [rsp+98h+var_40]
0x1800138c8  test    rbx, rbx
0x1800138cb  jnz     short loc_1800138F5
0x1800138cd  mov     rcx, [rsp+98h]; this
0x1800138d5  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800138dc  mov     ebx, 8007000Eh
0x1800138e1  mov     edx, 30Fh; void *
0x1800138e6  mov     r9d, ebx; char *
0x1800138e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800138ee  mov     eax, ebx
0x1800138f0  jmp     loc_18001397F
0x1800138f5  mov     eax, [rsp+98h+var_48]
0x1800138f9  lea     rcx, [rsp+98h+var_48]
0x1800138fe  mov     [rsp+98h+dwFlags], 1; dwFlags
0x180013906  xor     r9d, r9d; pPaddingInfo
0x180013909  mov     [rsp+98h+pcbResult], rcx; pcbResult
0x18001390e  mov     r8d, esi; cbInput
0x180013911  mov     [rsp+98h+cbOutput], eax; cbOutput
0x180013915  mov     rdx, rbp; pbInput
0x180013918  mov     [rsp+98h+pbOutput], rbx; pbOutput
0x18001391d  mov     rcx, r14; hKey
0x180013920  mov     [rsp+98h+cbIV], r15d; cbIV
0x180013925  mov     [rsp+98h+pbIV], rdi; int
0x18001392a  call    cs:__imp_BCryptDecrypt
0x180013930  test    eax, eax
0x180013932  jns     short loc_180013964
0x180013934  mov     rcx, [rsp+98h]; this
0x18001393c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013943  mov     r9d, eax; char *
0x180013946  mov     edx, 31Bh; void *
0x18001394b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013950  mov     edi, eax
0x180013952  test    rbx, rbx
0x180013955  jz      short loc_180013960
0x180013957  mov     rcx, rbx; hMem
0x18001395a  call    cs:__imp_LocalFree
0x180013960  mov     eax, edi
0x180013962  jmp     short loc_18001397F
0x180013964  mov     rax, [rsp+98h+arg_28]
0x18001396c  mov     rcx, [rsp+98h+arg_30]
0x180013974  mov     [rax], rbx
0x180013977  mov     eax, [rsp+98h+var_48]
0x18001397b  mov     [rcx], eax
0x18001397d  xor     eax, eax
0x18001397f  add     rsp, 68h
0x180013983  pop     r15
0x180013985  pop     r14
0x180013987  pop     rdi
0x180013988  pop     rsi
0x180013989  pop     rbp
0x18001398a  pop     rbx
0x18001398b  retn
```
