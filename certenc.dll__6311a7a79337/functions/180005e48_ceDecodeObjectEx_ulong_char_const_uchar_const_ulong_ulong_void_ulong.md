# ceDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,void * *,ulong *)

- ea: `0x180005e48`
- end: `0x180005f27`
- name: `?ceDecodeObjectEx@@YAHKPEBDPEBEKKPEAPEAXPEAK@Z`
- size: `223`
- prototype: `int(unsigned int, const char *, const unsigned __int8 *, unsigned int, unsigned int, void **, unsigned int *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a70`
- `0x1800022f0`
- `0x180002b10`
- `0x180003790`
- `0x180004c20`
- `0x1800067b4`
- `0x180007a70`

## callees

- `0x180005e48`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ecf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005ecf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ee6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005ee6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005f10`
- `CRYPT32!CryptDecodeObjectEx` at `0x180005eae`
- `CRYPT32!CryptDecodeObjectEx` at `0x180005eae`

## pseudocode

```c
__int64 __fastcall ceDecodeObjectEx(
        __int64 a1,
        const char *a2,
        const unsigned __int8 *a3,
        DWORD a4,
        DWORD dwFlags,
        void **a6,
        unsigned int *pcbStructInfo)
{
  unsigned int v10; // esi
  void *v11; // rax
  HLOCAL v12; // rax
  DWORD LastError; // ebx

  *a6 = 0;
  *pcbStructInfo = 0;
  while ( 1 )
  {
    v10 = CryptDecodeObjectEx(1u, a2, a3, a4, dwFlags, 0, *a6, pcbStructInfo);
    if ( v10 )
    {
      if ( !*pcbStructInfo )
        break;
    }
    v11 = *a6;
    if ( !v10 )
      goto LABEL_9;
    if ( v11 )
      return v10;
    v12 = LocalAlloc(0, *pcbStructInfo);
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
0x180005e48  push    rbx
0x180005e4a  push    rbp
0x180005e4b  push    rsi
0x180005e4c  push    rdi
0x180005e4d  push    r12
0x180005e4f  push    r14
0x180005e51  push    r15
0x180005e53  sub     rsp, 40h
0x180005e57  mov     rdi, [rsp+78h+arg_28]
0x180005e5f  mov     ebp, r9d
0x180005e62  mov     rbx, [rsp+78h+arg_30]
0x180005e6a  mov     r14, r8
0x180005e6d  mov     r12d, [rsp+78h+arg_20]
0x180005e75  mov     r15, rdx
0x180005e78  mov     qword ptr [rdi], 0
0x180005e7f  mov     dword ptr [rbx], 0
0x180005e85  mov     rax, [rdi]
0x180005e88  mov     r9d, ebp; cbEncoded
0x180005e8b  mov     [rsp+78h+pcbStructInfo], rbx; pcbStructInfo
0x180005e90  mov     r8, r14; pbEncoded
0x180005e93  mov     [rsp+78h+pvStructInfo], rax; pvStructInfo
0x180005e98  mov     rdx, r15; lpszStructType
0x180005e9b  mov     [rsp+78h+pDecodePara], 0; pDecodePara
0x180005ea4  mov     ecx, 1; dwCertEncodingType
0x180005ea9  mov     [rsp+78h+dwFlags], r12d; dwFlags
0x180005eae  call    cs:__imp_CryptDecodeObjectEx
0x180005eb4  mov     esi, eax
0x180005eb6  test    eax, eax
0x180005eb8  jz      short loc_180005EBF
0x180005eba  cmp     dword ptr [rbx], 0
0x180005ebd  jz      short loc_180005EE1
0x180005ebf  mov     rax, [rdi]
0x180005ec2  test    esi, esi
0x180005ec4  jz      short loc_180005EF1
0x180005ec6  test    rax, rax
0x180005ec9  jnz     short loc_180005F16
0x180005ecb  mov     edx, [rbx]; uBytes
0x180005ecd  xor     ecx, ecx; uFlags
0x180005ecf  call    cs:__imp_LocalAlloc
0x180005ed5  mov     [rdi], rax
0x180005ed8  test    rax, rax
0x180005edb  jnz     short loc_180005E85
0x180005edd  xor     esi, esi
0x180005edf  jmp     short loc_180005F16
0x180005ee1  mov     ecx, 8007000Dh; dwErrCode
0x180005ee6  call    cs:__imp_SetLastError
0x180005eec  mov     rax, [rdi]
0x180005eef  xor     esi, esi
0x180005ef1  test    rax, rax
0x180005ef4  jz      short loc_180005F16
0x180005ef6  call    cs:__imp_GetLastError
0x180005efc  mov     rcx, [rdi]; hMem
0x180005eff  mov     ebx, eax
0x180005f01  call    cs:__imp_LocalFree
0x180005f07  mov     ecx, ebx; dwErrCode
0x180005f09  mov     qword ptr [rdi], 0
0x180005f10  call    cs:__imp_SetLastError
0x180005f16  mov     eax, esi
0x180005f18  add     rsp, 40h
0x180005f1c  pop     r15
0x180005f1e  pop     r14
0x180005f20  pop     r12
0x180005f22  pop     rdi
0x180005f23  pop     rsi
0x180005f24  pop     rbp
0x180005f25  pop     rbx
0x180005f26  retn
```
