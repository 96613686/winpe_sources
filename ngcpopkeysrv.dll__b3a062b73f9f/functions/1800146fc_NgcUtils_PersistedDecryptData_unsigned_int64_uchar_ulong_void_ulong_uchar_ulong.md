# NgcUtils::PersistedDecryptData(unsigned __int64,uchar *,ulong,void *,ulong,uchar * *,ulong *)

- ea: `0x1800146fc`
- end: `0x180014821`
- name: `?PersistedDecryptData@NgcUtils@@YAJ_KPEAEKPEAXKPEAPEAEPEAK@Z`
- size: `293`
- prototype: `__int64 __fastcall(NCRYPT_KEY_HANDLE hKey, PBYTE pbInput, DWORD cbInput, void *pPaddingInfo, DWORD, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018a60`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x1800146fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800147ee`
- `ncrypt!NCryptDecrypt` at `0x18001473d`
- `ncrypt!NCryptDecrypt` at `0x1800147c1`
- `ncrypt!NCryptDecrypt` at `0x18001473d`
- `ncrypt!NCryptDecrypt` at `0x1800147c1`

## string_xrefs

- `0x180014753`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x1800147d2`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::PersistedDecryptData(
        NCRYPT_KEY_HANDLE hKey,
        PBYTE pbInput,
        DWORD cbInput,
        void *pPaddingInfo,
        DWORD pcbResult,
        PBYTE *a6,
        unsigned __int8 **a7)
{
  SECURITY_STATUS v11; // ebx
  __int64 v12; // rdx
  PBYTE v14; // rbx
  SECURITY_STATUS v15; // eax
  unsigned int v16; // edi
  unsigned __int8 **v17; // rcx
  int pbOutput; // [rsp+20h] [rbp-58h]
  int pbOutputa; // [rsp+20h] [rbp-58h]
  PBYTE v20[7]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  pcbResult = 0;
  v11 = NCryptDecrypt(hKey, pbInput, cbInput, pPaddingInfo, 0, 0, &pcbResult, 4u);
  if ( v11 < 0 )
  {
    v12 = 737;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v11,
      pbOutput);
    return (unsigned int)v11;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(v20, pcbResult);
  v14 = v20[0];
  if ( !v20[0] )
  {
    v11 = -2147024882;
    v12 = 740;
    goto LABEL_3;
  }
  v15 = NCryptDecrypt(hKey, pbInput, cbInput, pPaddingInfo, v20[0], pcbResult, &pcbResult, 4u);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v17 = a7;
    *a6 = v14;
    *(_DWORD *)v17 = pcbResult;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EE,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v15,
      pbOutputa);
    if ( v14 )
      LocalFree(v14);
    return v16;
  }
}

```

## disassembly

```asm
0x1800146fc  mov     rax, rsp
0x1800146ff  push    rbx
0x180014700  push    rbp
0x180014701  push    rsi
0x180014702  push    rdi
0x180014703  push    r14
0x180014705  sub     rsp, 50h
0x180014709  mov     dword ptr [rax-40h], 4
0x180014710  mov     rdi, r9
0x180014713  mov     dword ptr [rax+28h], 0
0x18001471a  lea     rax, [rax+28h]
0x18001471e  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180014723  mov     esi, r8d
0x180014726  mov     [rsp+78h+cbOutput], 0; cbOutput
0x18001472e  mov     rbp, rdx
0x180014731  mov     [rsp+78h+pbOutput], 0; int
0x18001473a  mov     r14, rcx
0x18001473d  call    cs:__imp_NCryptDecrypt
0x180014743  mov     ebx, eax
0x180014745  test    eax, eax
0x180014747  jns     short loc_180014769
0x180014749  mov     edx, 2E1h; void *
0x18001474e  mov     rcx, [rsp+78h]; this
0x180014753  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001475a  mov     r9d, ebx; char *
0x18001475d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014762  mov     eax, ebx
0x180014764  jmp     loc_180014816
0x180014769  mov     edx, [rsp+78h+arg_20]
0x180014770  lea     rcx, [rsp+78h+var_38]
0x180014775  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18001477a  mov     rbx, [rsp+78h+var_38]
0x18001477f  test    rbx, rbx
0x180014782  jnz     short loc_180014790
0x180014784  mov     ebx, 8007000Eh
0x180014789  mov     edx, 2E4h
0x18001478e  jmp     short loc_18001474E
0x180014790  mov     eax, [rsp+78h+arg_20]
0x180014797  lea     rcx, [rsp+78h+arg_20]
0x18001479f  mov     [rsp+78h+dwFlags], 4; dwFlags
0x1800147a7  mov     r9, rdi; pPaddingInfo
0x1800147aa  mov     [rsp+78h+pcbResult], rcx; pcbResult
0x1800147af  mov     r8d, esi; cbInput
0x1800147b2  mov     [rsp+78h+cbOutput], eax; cbOutput
0x1800147b6  mov     rcx, r14; hKey
0x1800147b9  mov     rdx, rbp; pbInput
0x1800147bc  mov     [rsp+78h+pbOutput], rbx; int
0x1800147c1  call    cs:__imp_NCryptDecrypt
0x1800147c7  mov     edi, eax
0x1800147c9  test    eax, eax
0x1800147cb  jns     short loc_1800147F8
0x1800147cd  mov     rcx, [rsp+78h]; this
0x1800147d2  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800147d9  mov     r9d, eax; char *
0x1800147dc  mov     edx, 2EEh; void *
0x1800147e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800147e6  test    rbx, rbx
0x1800147e9  jz      short loc_1800147F4
0x1800147eb  mov     rcx, rbx; hMem
0x1800147ee  call    cs:__imp_LocalFree
0x1800147f4  mov     eax, edi
0x1800147f6  jmp     short loc_180014816
0x1800147f8  mov     rax, [rsp+78h+arg_28]
0x180014800  mov     rcx, [rsp+78h+arg_30]
0x180014808  mov     [rax], rbx
0x18001480b  mov     eax, [rsp+78h+arg_20]
0x180014812  mov     [rcx], eax
0x180014814  xor     eax, eax
0x180014816  add     rsp, 50h
0x18001481a  pop     r14
0x18001481c  pop     rdi
0x18001481d  pop     rsi
0x18001481e  pop     rbp
0x18001481f  pop     rbx
0x180014820  retn
```
