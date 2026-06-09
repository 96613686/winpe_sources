# NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)

- ea: `0x180013e3c`
- end: `0x180013f4e`
- name: `?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z`
- size: `274`
- prototype: `__int64 __usercall@<rax>(NCRYPT_KEY_HANDLE hKey@<rcx>, LPCWSTR pszBlobType@<rdx>, DWORD dwFlags@<r8d>, unsigned int@<r9d>, unsigned __int8 **, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015e94`
- `0x180016328`
- `0x180016dc0`
- `0x1800181a0`
- `0x1800192ec`
- `0x18001bc90`

## callees

- `0x18000b0fc`
- `0x180013270`
- `0x180013e3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013f26`
- `ncrypt!NCryptExportKey` at `0x180013e83`
- `ncrypt!NCryptExportKey` at `0x180013ef9`
- `ncrypt!NCryptExportKey` at `0x180013e83`
- `ncrypt!NCryptExportKey` at `0x180013ef9`

## string_xrefs

- `0x180013e99`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180013f0a`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::ExportNCryptKey(
        NCRYPT_KEY_HANDLE hKey,
        LPCWSTR pszBlobType,
        DWORD dwFlags,
        PBYTE *a4,
        unsigned __int8 **a5)
{
  SECURITY_STATUS v9; // ebx
  __int64 v10; // rdx
  PBYTE v12; // rbx
  SECURITY_STATUS v13; // eax
  unsigned int v14; // edi
  DWORD v15; // eax
  int pbOutput; // [rsp+20h] [rbp-58h]
  int pbOutputa; // [rsp+20h] [rbp-58h]
  DWORD pcbResult; // [rsp+40h] [rbp-38h] BYREF
  PBYTE v19[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  pcbResult = 0;
  v9 = NCryptExportKey(hKey, 0, pszBlobType, 0, 0, 0, &pcbResult, dwFlags);
  if ( v9 < 0 )
  {
    v10 = 546;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v9,
      pbOutput);
    return (unsigned int)v9;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(v19, pcbResult);
  v12 = v19[0];
  if ( !v19[0] )
  {
    v9 = -2147024882;
    v10 = 549;
    goto LABEL_3;
  }
  v13 = NCryptExportKey(hKey, 0, pszBlobType, 0, v19[0], pcbResult, &pcbResult, dwFlags);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v15 = pcbResult;
    *a4 = v12;
    *(_DWORD *)a5 = v15;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v13,
      pbOutputa);
    if ( v12 )
      LocalFree(v12);
    return v14;
  }
}

```

## disassembly

```asm
0x180013e3c  push    rbx
0x180013e3e  push    rbp
0x180013e3f  push    rsi
0x180013e40  push    rdi
0x180013e41  push    r14
0x180013e43  sub     rsp, 50h
0x180013e47  mov     [rsp+78h+dwFlags], r8d; dwFlags
0x180013e4c  lea     rax, [rsp+78h+var_38]
0x180013e51  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180013e56  mov     edi, r8d
0x180013e59  mov     rsi, r9
0x180013e5c  mov     [rsp+78h+cbOutput], 0; cbOutput
0x180013e64  mov     rbp, rdx
0x180013e67  mov     [rsp+78h+pbOutput], 0; int
0x180013e70  mov     r8, rdx; pszBlobType
0x180013e73  mov     [rsp+78h+var_38], 0
0x180013e7b  xor     r9d, r9d; pParameterList
0x180013e7e  xor     edx, edx; hExportKey
0x180013e80  mov     r14, rcx
0x180013e83  call    cs:__imp_NCryptExportKey
0x180013e89  mov     ebx, eax
0x180013e8b  test    eax, eax
0x180013e8d  jns     short loc_180013EAF
0x180013e8f  mov     edx, 222h; void *
0x180013e94  mov     rcx, [rsp+78h]; this
0x180013e99  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013ea0  mov     r9d, ebx; char *
0x180013ea3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ea8  mov     eax, ebx
0x180013eaa  jmp     loc_180013F43
0x180013eaf  mov     edx, [rsp+78h+var_38]
0x180013eb3  lea     rcx, [rsp+78h+var_30]
0x180013eb8  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180013ebd  mov     rbx, [rsp+78h+var_30]
0x180013ec2  test    rbx, rbx
0x180013ec5  jnz     short loc_180013ED3
0x180013ec7  mov     ebx, 8007000Eh
0x180013ecc  mov     edx, 225h
0x180013ed1  jmp     short loc_180013E94
0x180013ed3  mov     eax, [rsp+78h+var_38]
0x180013ed7  lea     rcx, [rsp+78h+var_38]
0x180013edc  mov     [rsp+78h+dwFlags], edi; dwFlags
0x180013ee0  xor     r9d, r9d; pParameterList
0x180013ee3  mov     [rsp+78h+pcbResult], rcx; pcbResult
0x180013ee8  mov     r8, rbp; pszBlobType
0x180013eeb  mov     [rsp+78h+cbOutput], eax; cbOutput
0x180013eef  mov     rcx, r14; hKey
0x180013ef2  xor     edx, edx; hExportKey
0x180013ef4  mov     [rsp+78h+pbOutput], rbx; int
0x180013ef9  call    cs:__imp_NCryptExportKey
0x180013eff  mov     edi, eax
0x180013f01  test    eax, eax
0x180013f03  jns     short loc_180013F30
0x180013f05  mov     rcx, [rsp+78h]; this
0x180013f0a  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013f11  mov     r9d, eax; char *
0x180013f14  mov     edx, 22Fh; void *
0x180013f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f1e  test    rbx, rbx
0x180013f21  jz      short loc_180013F2C
0x180013f23  mov     rcx, rbx; hMem
0x180013f26  call    cs:__imp_LocalFree
0x180013f2c  mov     eax, edi
0x180013f2e  jmp     short loc_180013F43
0x180013f30  mov     eax, [rsp+78h+var_38]
0x180013f34  mov     rcx, [rsp+78h+arg_20]
0x180013f3c  mov     [rsi], rbx
0x180013f3f  mov     [rcx], eax
0x180013f41  xor     eax, eax
0x180013f43  add     rsp, 50h
0x180013f47  pop     r14
0x180013f49  pop     rdi
0x180013f4a  pop     rsi
0x180013f4b  pop     rbp
0x180013f4c  pop     rbx
0x180013f4d  retn
```
