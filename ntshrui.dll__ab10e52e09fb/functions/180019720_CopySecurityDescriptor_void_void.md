# CopySecurityDescriptor(void *,void * *)

- ea: `0x180019720`
- end: `0x180019835`
- name: `?CopySecurityDescriptor@@YAJPEAXPEAPEAX@Z`
- size: `277`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180033cd0`
- `0x18005e600`

## callees

- `0x180019720`
- `0x1800238d8`
- `0x18002637c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197d0`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180019749`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180019749`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180019772`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180019772`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001977f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001977f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180019815`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180019815`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019790`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180019790`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001982d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001982d`

## pseudocode

```c
__int64 __fastcall CopySecurityDescriptor(void *Src, void **a2)
{
  unsigned int Error; // esi
  HLOCAL v5; // rbp
  signed int LastError; // eax
  WORD pControl; // [rsp+48h] [rbp+10h] BYREF
  size_t Size; // [rsp+50h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+58h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147500035LL;
  Error = 0;
  *a2 = 0;
  if ( !Src )
    return 0;
  if ( !IsValidSecurityDescriptor(Src) )
    return 2147942487LL;
  pControl = 0;
  dwRevision = 0;
  if ( !GetSecurityDescriptorControl(Src, &pControl, &dwRevision) )
  {
    LastError = GetLastError();
    Error = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return Error;
  }
  LODWORD(Size) = GetSecurityDescriptorLength(Src);
  v5 = LocalAlloc(0x40u, (unsigned int)Size);
  if ( v5 )
  {
    if ( (pControl & 0x8000u) == 0 )
    {
      if ( !MakeSelfRelativeSD(Src, v5, (LPDWORD)&Size) )
      {
        Error = ResultFromLastError();
        if ( (Error & 0x80000000) != 0 )
        {
          LocalFree(v5);
          return Error;
        }
      }
    }
    else
    {
      memcpy_0(v5, Src, (unsigned int)Size);
    }
    *a2 = v5;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return Error;
}

```

## disassembly

```asm
0x180019720  push    rbx
0x180019722  push    rdi
0x180019723  sub     rsp, 28h
0x180019727  mov     rdi, rdx
0x18001972a  mov     rbx, rcx
0x18001972d  test    rdx, rdx
0x180019730  jz      loc_1800197FF
0x180019736  mov     [rsp+38h+var_18], rsi
0x18001973b  xor     esi, esi
0x18001973d  mov     [rdx], rsi
0x180019740  test    rcx, rcx
0x180019743  jz      loc_180019806
0x180019749  call    cs:__imp_IsValidSecurityDescriptor
0x18001974f  test    eax, eax
0x180019751  jz      loc_1800197EE
0x180019757  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x18001975c  mov     [rsp+38h+arg_0], rbp
0x180019761  lea     rdx, [rsp+38h+pControl]; pControl
0x180019766  mov     [rsp+38h+pControl], si
0x18001976b  mov     rcx, rbx; pSecurityDescriptor
0x18001976e  mov     [rsp+38h+dwRevision], esi
0x180019772  call    cs:__imp_GetSecurityDescriptorControl
0x180019778  test    eax, eax
0x18001977a  jz      short loc_1800197D0
0x18001977c  mov     rcx, rbx; pSecurityDescriptor
0x18001977f  call    cs:__imp_GetSecurityDescriptorLength
0x180019785  mov     edx, eax; uBytes
0x180019787  mov     ecx, 40h ; '@'; uFlags
0x18001978c  mov     dword ptr [rsp+38h+Size], edx
0x180019790  call    cs:__imp_LocalAlloc
0x180019796  mov     rbp, rax
0x180019799  test    rax, rax
0x18001979c  jz      short loc_1800197E7
0x18001979e  mov     eax, 8000h
0x1800197a3  test    [rsp+38h+pControl], ax
0x1800197a8  jz      short loc_18001980A
0x1800197aa  mov     r8d, dword ptr [rsp+38h+Size]; Size
0x1800197af  mov     rdx, rbx; Src
0x1800197b2  mov     rcx, rbp; void *
0x1800197b5  call    memcpy_0
0x1800197ba  mov     [rdi], rbp
0x1800197bd  mov     rbp, [rsp+38h+arg_0]
0x1800197c2  mov     eax, esi
0x1800197c4  mov     rsi, [rsp+38h+var_18]
0x1800197c9  add     rsp, 28h
0x1800197cd  pop     rdi
0x1800197ce  pop     rbx
0x1800197cf  retn
0x1800197d0  call    cs:__imp_GetLastError
0x1800197d6  mov     esi, eax
0x1800197d8  test    eax, eax
0x1800197da  jle     short loc_1800197BD
0x1800197dc  movzx   esi, ax
0x1800197df  or      esi, 80070000h
0x1800197e5  jmp     short loc_1800197BD
0x1800197e7  mov     esi, 8007000Eh
0x1800197ec  jmp     short loc_1800197BD
0x1800197ee  mov     rsi, [rsp+38h+var_18]
0x1800197f3  mov     eax, 80070057h
0x1800197f8  add     rsp, 28h
0x1800197fc  pop     rdi
0x1800197fd  pop     rbx
0x1800197fe  retn
0x1800197ff  mov     eax, 80004003h
0x180019804  jmp     short loc_1800197C9
0x180019806  xor     eax, eax
0x180019808  jmp     short loc_1800197C4
0x18001980a  lea     r8, [rsp+38h+Size]; lpdwBufferLength
0x18001980f  mov     rdx, rbp; pSelfRelativeSecurityDescriptor
0x180019812  mov     rcx, rbx; pAbsoluteSecurityDescriptor
0x180019815  call    cs:__imp_MakeSelfRelativeSD
0x18001981b  test    eax, eax
0x18001981d  jnz     short loc_1800197BA
0x18001981f  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180019824  mov     esi, eax
0x180019826  test    eax, eax
0x180019828  jns     short loc_1800197BA
0x18001982a  mov     rcx, rbp; hMem
0x18001982d  call    cs:__imp_LocalFree
0x180019833  jmp     short loc_1800197BD
```
