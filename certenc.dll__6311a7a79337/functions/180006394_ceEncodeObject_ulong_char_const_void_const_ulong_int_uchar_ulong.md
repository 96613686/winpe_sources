# ceEncodeObject(ulong,char const *,void const *,ulong,int,uchar * *,ulong *)

- ea: `0x180006394`
- end: `0x180006462`
- name: `?ceEncodeObject@@YAHKPEBDPEBXKHPEAPEAEPEAK@Z`
- size: `206`
- prototype: `int(unsigned int, const char *, const void *, unsigned int, int, unsigned __int8 **, unsigned int *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d20`
- `0x180002580`
- `0x180002d00`
- `0x180003a30`
- `0x180004e20`
- `0x1800067b4`
- `0x180007c60`

## callees

- `0x180006394`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000640c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000640c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000643e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000643e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006423`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000644d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006423`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000644d`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800063eb`
- `CRYPT32!CryptEncodeObjectEx` at `0x1800063eb`

## pseudocode

```c
__int64 __fastcall ceEncodeObject(
        __int64 a1,
        const char *a2,
        const void *a3,
        DWORD a4,
        int a5,
        unsigned __int8 **a6,
        unsigned int *pcbEncoded)
{
  unsigned int v10; // esi
  void *v11; // rax
  unsigned __int8 *v12; // rax
  DWORD LastError; // ebx

  *a6 = 0;
  *pcbEncoded = 0;
  while ( 1 )
  {
    v10 = CryptEncodeObjectEx(1u, a2, a3, a4, 0, *a6, pcbEncoded);
    if ( v10 )
    {
      if ( !*pcbEncoded )
        break;
    }
    v11 = *a6;
    if ( !v10 )
      goto LABEL_9;
    if ( v11 )
      return v10;
    v12 = (unsigned __int8 *)LocalAlloc(0, *pcbEncoded);
    *a6 = v12;
    if ( !v12 )
      return 0;
  }
  SetLastError(0x8007000D);
  v11 = *a6;
  v10 = 0;
LABEL_9:
  if ( v11 )
  {
    LastError = GetLastError();
    LocalFree(*a6);
    *a6 = 0;
    SetLastError(LastError);
  }
  return v10;
}

```

## disassembly

```asm
0x180006394  push    rbx
0x180006396  push    rbp
0x180006397  push    rsi
0x180006398  push    rdi
0x180006399  push    r14
0x18000639b  push    r15
0x18000639d  sub     rsp, 48h
0x1800063a1  mov     rdi, [rsp+78h+arg_28]
0x1800063a9  mov     ebp, r9d
0x1800063ac  mov     rbx, [rsp+78h+arg_30]
0x1800063b4  mov     r14, r8
0x1800063b7  mov     r15, rdx
0x1800063ba  mov     qword ptr [rdi], 0
0x1800063c1  mov     dword ptr [rbx], 0
0x1800063c7  mov     rax, [rdi]
0x1800063ca  mov     r9d, ebp; dwFlags
0x1800063cd  mov     [rsp+78h+pcbEncoded], rbx; pcbEncoded
0x1800063d2  mov     r8, r14; pvStructInfo
0x1800063d5  mov     [rsp+78h+pvEncoded], rax; pvEncoded
0x1800063da  mov     rdx, r15; lpszStructType
0x1800063dd  mov     ecx, 1; dwCertEncodingType
0x1800063e2  mov     [rsp+78h+pEncodePara], 0; pEncodePara
0x1800063eb  call    cs:__imp_CryptEncodeObjectEx
0x1800063f1  mov     esi, eax
0x1800063f3  test    eax, eax
0x1800063f5  jz      short loc_1800063FC
0x1800063f7  cmp     dword ptr [rbx], 0
0x1800063fa  jz      short loc_18000641E
0x1800063fc  mov     rax, [rdi]
0x1800063ff  test    esi, esi
0x180006401  jz      short loc_18000642E
0x180006403  test    rax, rax
0x180006406  jnz     short loc_180006453
0x180006408  mov     edx, [rbx]; uBytes
0x18000640a  xor     ecx, ecx; uFlags
0x18000640c  call    cs:__imp_LocalAlloc
0x180006412  mov     [rdi], rax
0x180006415  test    rax, rax
0x180006418  jnz     short loc_1800063C7
0x18000641a  xor     esi, esi
0x18000641c  jmp     short loc_180006453
0x18000641e  mov     ecx, 8007000Dh; dwErrCode
0x180006423  call    cs:__imp_SetLastError
0x180006429  mov     rax, [rdi]
0x18000642c  xor     esi, esi
0x18000642e  test    rax, rax
0x180006431  jz      short loc_180006453
0x180006433  call    cs:__imp_GetLastError
0x180006439  mov     rcx, [rdi]; hMem
0x18000643c  mov     ebx, eax
0x18000643e  call    cs:__imp_LocalFree
0x180006444  mov     ecx, ebx; dwErrCode
0x180006446  mov     qword ptr [rdi], 0
0x18000644d  call    cs:__imp_SetLastError
0x180006453  mov     eax, esi
0x180006455  add     rsp, 48h
0x180006459  pop     r15
0x18000645b  pop     r14
0x18000645d  pop     rdi
0x18000645e  pop     rsi
0x18000645f  pop     rbp
0x180006460  pop     rbx
0x180006461  retn
```
