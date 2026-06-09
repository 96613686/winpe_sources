# NgcUtils::EncryptDataAuthenticated(void *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180013c98`
- end: `0x180013e35`
- name: `?EncryptDataAuthenticated@NgcUtils@@YAJPEAXPEAEK1K1K1KPEAPEAEPEAK@Z`
- size: `413`
- prototype: `int __fastcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, __int64, ULONG pcbResult, PUCHAR pbOutput, unsigned __int8 *, __int64, unsigned __int8 *, PUCHAR *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001eee0`

## callees

- `0x180005858`
- `0x18000b0fc`
- `0x180013270`
- `0x18001368c`
- `0x180013c98`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013e08`
- `bcrypt!BCryptEncrypt` at `0x180013d41`
- `bcrypt!BCryptEncrypt` at `0x180013ddc`
- `bcrypt!BCryptEncrypt` at `0x180013d41`
- `bcrypt!BCryptEncrypt` at `0x180013ddc`

## string_xrefs

- `0x180013d4f`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013d81`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013dea`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall NgcUtils::EncryptDataAuthenticated(
        BCRYPT_KEY_HANDLE hKey,
        PUCHAR pbInput,
        ULONG cbInput,
        __int64 a4,
        ULONG pcbResult,
        PUCHAR pbOutput,
        unsigned __int8 *a7,
        __int64 a8,
        unsigned __int8 *a9,
        PUCHAR *a10,
        unsigned __int8 **a11)
{
  NTSTATUS v15; // eax
  PUCHAR v17; // rbx
  NTSTATUS v18; // eax
  int v19; // edi
  unsigned __int8 **v20; // rcx
  int pbIV; // [rsp+20h] [rbp-89h]
  int pbIVa; // [rsp+20h] [rbp-89h]
  _DWORD pPaddingInfo[2]; // [rsp+50h] [rbp-59h] BYREF
  __int64 v24; // [rsp+58h] [rbp-51h]
  ULONG v25; // [rsp+60h] [rbp-49h]
  PUCHAR v26; // [rsp+68h] [rbp-41h]
  int v27; // [rsp+70h] [rbp-39h]
  __int64 v28; // [rsp+78h] [rbp-31h]
  int v29; // [rsp+80h] [rbp-29h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+2Fh]

  memset_0(pPaddingInfo, 0, 0x58u);
  v25 = pcbResult;
  v26 = pbOutput;
  v27 = (int)a7;
  v28 = a8;
  v29 = (int)a9;
  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v24 = a4;
  pcbResult = 0;
  v15 = BCryptEncrypt(hKey, pbInput, cbInput, pPaddingInfo, 0, 0, 0, 0, &pcbResult, 0);
  if ( v15 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x385,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v15,
             pbIV);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&pbOutput, pcbResult);
  v17 = pbOutput;
  if ( pbOutput )
  {
    v18 = BCryptEncrypt(hKey, pbInput, cbInput, pPaddingInfo, 0, 0, pbOutput, pcbResult, &pcbResult, 0);
    if ( v18 >= 0 )
    {
      v20 = a11;
      *a10 = v17;
      *(_DWORD *)v20 = pcbResult;
      return 0;
    }
    else
    {
      v19 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x394,
              (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
              (const char *)(unsigned int)v18,
              pbIVa);
      if ( v17 )
        LocalFree(v17);
      return v19;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x388,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      pbIV);
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180013c98  push    rbp
0x180013c9a  push    rbx
0x180013c9b  push    rsi
0x180013c9c  push    rdi
0x180013c9d  push    r14
0x180013c9f  lea     rbp, [rsp-7]
0x180013ca4  sub     rsp, 0B0h
0x180013cab  mov     rsi, rdx
0x180013cae  mov     edi, r8d
0x180013cb1  xor     edx, edx; Val
0x180013cb3  mov     r14, rcx
0x180013cb6  lea     rcx, [rbp+27h+pPaddingInfo]; void *
0x180013cba  mov     rbx, r9
0x180013cbd  lea     r8d, [rdx+58h]; Size
0x180013cc1  call    memset_0
0x180013cc6  mov     eax, [rbp+27h+arg_20]
0x180013cc9  lea     r9, [rbp+27h+pPaddingInfo]; pPaddingInfo
0x180013ccd  mov     [rbp+27h+var_70], eax
0x180013cd0  mov     r8d, edi; cbInput
0x180013cd3  mov     rax, [rbp+27h+arg_28]
0x180013cd7  mov     rdx, rsi; pbInput
0x180013cda  mov     [rbp+27h+var_68], rax
0x180013cde  mov     rcx, r14; hKey
0x180013ce1  mov     eax, dword ptr [rbp+27h+arg_30]
0x180013ce4  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x180013cec  mov     [rbp+27h+var_60], eax
0x180013cef  mov     rax, [rbp+27h+arg_38]
0x180013cf3  mov     [rbp+27h+var_58], rax
0x180013cf7  mov     eax, dword ptr [rbp+27h+arg_40]
0x180013cfa  mov     [rbp+27h+var_50], eax
0x180013cfd  lea     rax, [rbp+27h+arg_20]
0x180013d01  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180013d06  mov     [rsp+0D0h+cbOutput], 0; cbOutput
0x180013d0e  mov     [rsp+0D0h+pbOutput], 0; pbOutput
0x180013d17  mov     [rsp+0D0h+cbIV], 0; cbIV
0x180013d1f  mov     [rsp+0D0h+pbIV], 0; int
0x180013d28  mov     [rbp+27h+pPaddingInfo], 58h ; 'X'
0x180013d2f  mov     [rbp+27h+var_7C], 1
0x180013d36  mov     [rbp+27h+var_78], rbx
0x180013d3a  mov     [rbp+27h+arg_20], 0
0x180013d41  call    cs:__imp_BCryptEncrypt
0x180013d47  test    eax, eax
0x180013d49  jns     short loc_180013D68
0x180013d4b  mov     rcx, [rbp+2Fh]; this
0x180013d4f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013d56  mov     r9d, eax; char *
0x180013d59  mov     edx, 385h; void *
0x180013d5e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013d63  jmp     loc_180013E27
0x180013d68  mov     edx, [rbp+27h+arg_20]
0x180013d6b  lea     rcx, [rbp+27h+arg_28]
0x180013d6f  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180013d74  mov     rbx, [rbp+27h+arg_28]
0x180013d78  test    rbx, rbx
0x180013d7b  jnz     short loc_180013DA1
0x180013d7d  mov     rcx, [rbp+2Fh]; this
0x180013d81  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013d88  mov     ebx, 8007000Eh
0x180013d8d  mov     edx, 388h; void *
0x180013d92  mov     r9d, ebx; char *
0x180013d95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013d9a  mov     eax, ebx
0x180013d9c  jmp     loc_180013E27
0x180013da1  mov     eax, [rbp+27h+arg_20]
0x180013da4  lea     rcx, [rbp+27h+arg_20]
0x180013da8  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x180013db0  lea     r9, [rbp+27h+pPaddingInfo]; pPaddingInfo
0x180013db4  mov     [rsp+0D0h+pcbResult], rcx; pcbResult
0x180013db9  mov     r8d, edi; cbInput
0x180013dbc  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x180013dc0  mov     rdx, rsi; pbInput
0x180013dc3  mov     [rsp+0D0h+pbOutput], rbx; pbOutput
0x180013dc8  mov     rcx, r14; hKey
0x180013dcb  mov     [rsp+0D0h+cbIV], 0; cbIV
0x180013dd3  mov     [rsp+0D0h+pbIV], 0; int
0x180013ddc  call    cs:__imp_BCryptEncrypt
0x180013de2  test    eax, eax
0x180013de4  jns     short loc_180013E12
0x180013de6  mov     rcx, [rbp+2Fh]; this
0x180013dea  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013df1  mov     r9d, eax; char *
0x180013df4  mov     edx, 394h; void *
0x180013df9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013dfe  mov     edi, eax
0x180013e00  test    rbx, rbx
0x180013e03  jz      short loc_180013E0E
0x180013e05  mov     rcx, rbx; hMem
0x180013e08  call    cs:__imp_LocalFree
0x180013e0e  mov     eax, edi
0x180013e10  jmp     short loc_180013E27
0x180013e12  mov     rax, [rbp+27h+arg_48]
0x180013e16  mov     rcx, [rbp+27h+arg_50]
0x180013e1d  mov     [rax], rbx
0x180013e20  mov     eax, [rbp+27h+arg_20]
0x180013e23  mov     [rcx], eax
0x180013e25  xor     eax, eax
0x180013e27  add     rsp, 0B0h
0x180013e2e  pop     r14
0x180013e30  pop     rdi
0x180013e31  pop     rsi
0x180013e32  pop     rbx
0x180013e33  pop     rbp
0x180013e34  retn
```
