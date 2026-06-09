# NgcUtils::DecryptDataAuthenticated(void *,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180013994`
- end: `0x180013b31`
- name: `?DecryptDataAuthenticated@NgcUtils@@YAJPEAXPEAEK1K1K1KPEAPEAEPEAK@Z`
- size: `413`
- prototype: `int __fastcall(BCRYPT_KEY_HANDLE hKey, PUCHAR pbInput, ULONG cbInput, __int64, ULONG pcbResult, PUCHAR pbOutput, unsigned __int8 *, __int64, unsigned __int8 *, PUCHAR *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ebe0`

## callees

- `0x180005858`
- `0x18000b0fc`
- `0x180013270`
- `0x18001368c`
- `0x180013994`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013b04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013b04`
- `bcrypt!BCryptDecrypt` at `0x180013a3d`
- `bcrypt!BCryptDecrypt` at `0x180013ad8`
- `bcrypt!BCryptDecrypt` at `0x180013a3d`
- `bcrypt!BCryptDecrypt` at `0x180013ad8`

## string_xrefs

- `0x180013a4b`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013a7d`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013ae6`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall NgcUtils::DecryptDataAuthenticated(
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
  v15 = BCryptDecrypt(hKey, pbInput, cbInput, pPaddingInfo, 0, 0, 0, 0, &pcbResult, 0);
  if ( v15 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x3C0,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
             (const char *)(unsigned int)v15,
             pbIV);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&pbOutput, pcbResult);
  v17 = pbOutput;
  if ( pbOutput )
  {
    v18 = BCryptDecrypt(hKey, pbInput, cbInput, pPaddingInfo, 0, 0, pbOutput, pcbResult, &pcbResult, 0);
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
              (void *)0x3CF,
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
      (void *)0x3C3,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)0x8007000ELL,
      pbIV);
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180013994  push    rbp
0x180013996  push    rbx
0x180013997  push    rsi
0x180013998  push    rdi
0x180013999  push    r14
0x18001399b  lea     rbp, [rsp-7]
0x1800139a0  sub     rsp, 0B0h
0x1800139a7  mov     rsi, rdx
0x1800139aa  mov     edi, r8d
0x1800139ad  xor     edx, edx; Val
0x1800139af  mov     r14, rcx
0x1800139b2  lea     rcx, [rbp+27h+pPaddingInfo]; void *
0x1800139b6  mov     rbx, r9
0x1800139b9  lea     r8d, [rdx+58h]; Size
0x1800139bd  call    memset_0
0x1800139c2  mov     eax, [rbp+27h+arg_20]
0x1800139c5  lea     r9, [rbp+27h+pPaddingInfo]; pPaddingInfo
0x1800139c9  mov     [rbp+27h+var_70], eax
0x1800139cc  mov     r8d, edi; cbInput
0x1800139cf  mov     rax, [rbp+27h+arg_28]
0x1800139d3  mov     rdx, rsi; pbInput
0x1800139d6  mov     [rbp+27h+var_68], rax
0x1800139da  mov     rcx, r14; hKey
0x1800139dd  mov     eax, dword ptr [rbp+27h+arg_30]
0x1800139e0  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x1800139e8  mov     [rbp+27h+var_60], eax
0x1800139eb  mov     rax, [rbp+27h+arg_38]
0x1800139ef  mov     [rbp+27h+var_58], rax
0x1800139f3  mov     eax, dword ptr [rbp+27h+arg_40]
0x1800139f6  mov     [rbp+27h+var_50], eax
0x1800139f9  lea     rax, [rbp+27h+arg_20]
0x1800139fd  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180013a02  mov     [rsp+0D0h+cbOutput], 0; cbOutput
0x180013a0a  mov     [rsp+0D0h+pbOutput], 0; pbOutput
0x180013a13  mov     [rsp+0D0h+cbIV], 0; cbIV
0x180013a1b  mov     [rsp+0D0h+pbIV], 0; int
0x180013a24  mov     [rbp+27h+pPaddingInfo], 58h ; 'X'
0x180013a2b  mov     [rbp+27h+var_7C], 1
0x180013a32  mov     [rbp+27h+var_78], rbx
0x180013a36  mov     [rbp+27h+arg_20], 0
0x180013a3d  call    cs:__imp_BCryptDecrypt
0x180013a43  test    eax, eax
0x180013a45  jns     short loc_180013A64
0x180013a47  mov     rcx, [rbp+2Fh]; this
0x180013a4b  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013a52  mov     r9d, eax; char *
0x180013a55  mov     edx, 3C0h; void *
0x180013a5a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013a5f  jmp     loc_180013B23
0x180013a64  mov     edx, [rbp+27h+arg_20]
0x180013a67  lea     rcx, [rbp+27h+arg_28]
0x180013a6b  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180013a70  mov     rbx, [rbp+27h+arg_28]
0x180013a74  test    rbx, rbx
0x180013a77  jnz     short loc_180013A9D
0x180013a79  mov     rcx, [rbp+2Fh]; this
0x180013a7d  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013a84  mov     ebx, 8007000Eh
0x180013a89  mov     edx, 3C3h; void *
0x180013a8e  mov     r9d, ebx; char *
0x180013a91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a96  mov     eax, ebx
0x180013a98  jmp     loc_180013B23
0x180013a9d  mov     eax, [rbp+27h+arg_20]
0x180013aa0  lea     rcx, [rbp+27h+arg_20]
0x180013aa4  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x180013aac  lea     r9, [rbp+27h+pPaddingInfo]; pPaddingInfo
0x180013ab0  mov     [rsp+0D0h+pcbResult], rcx; pcbResult
0x180013ab5  mov     r8d, edi; cbInput
0x180013ab8  mov     [rsp+0D0h+cbOutput], eax; cbOutput
0x180013abc  mov     rdx, rsi; pbInput
0x180013abf  mov     [rsp+0D0h+pbOutput], rbx; pbOutput
0x180013ac4  mov     rcx, r14; hKey
0x180013ac7  mov     [rsp+0D0h+cbIV], 0; cbIV
0x180013acf  mov     [rsp+0D0h+pbIV], 0; int
0x180013ad8  call    cs:__imp_BCryptDecrypt
0x180013ade  test    eax, eax
0x180013ae0  jns     short loc_180013B0E
0x180013ae2  mov     rcx, [rbp+2Fh]; this
0x180013ae6  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013aed  mov     r9d, eax; char *
0x180013af0  mov     edx, 3CFh; void *
0x180013af5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013afa  mov     edi, eax
0x180013afc  test    rbx, rbx
0x180013aff  jz      short loc_180013B0A
0x180013b01  mov     rcx, rbx; hMem
0x180013b04  call    cs:__imp_LocalFree
0x180013b0a  mov     eax, edi
0x180013b0c  jmp     short loc_180013B23
0x180013b0e  mov     rax, [rbp+27h+arg_48]
0x180013b12  mov     rcx, [rbp+27h+arg_50]
0x180013b19  mov     [rax], rbx
0x180013b1c  mov     eax, [rbp+27h+arg_20]
0x180013b1f  mov     [rcx], eax
0x180013b21  xor     eax, eax
0x180013b23  add     rsp, 0B0h
0x180013b2a  pop     r14
0x180013b2c  pop     rdi
0x180013b2d  pop     rsi
0x180013b2e  pop     rbx
0x180013b2f  pop     rbp
0x180013b30  retn
```
