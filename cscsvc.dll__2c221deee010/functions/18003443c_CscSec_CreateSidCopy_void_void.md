# CscSec_CreateSidCopy(void *,void * *)

- ea: `0x18003443c`
- end: `0x1800344b6`
- name: `?CscSec_CreateSidCopy@@YAJPEAXPEAPEAX@Z`
- size: `122`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003598c`
- `0x180040fd0`
- `0x18004a9c0`
- `0x18005d944`
- `0x1800808d8`

## callees

- `0x18000d640`
- `0x18001be00`
- `0x18002f10c`
- `0x18003443c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180034452`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180034452`
- `ADVAPI32!GetLengthSid` at `0x180034466`
- `ADVAPI32!GetLengthSid` at `0x180034466`
- `ADVAPI32!CopySid` at `0x18003448b`
- `ADVAPI32!CopySid` at `0x18003448b`

## pseudocode

```c
__int64 __fastcall CscSec_CreateSidCopy(PSID pSourceSid, void **a2)
{
  int Error; // ebx
  DWORD LengthSid; // ebp
  void *v6; // r9
  void *v7; // rdx

  *a2 = 0;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    Error = CscUtil_HeapAlloc(LengthSid, 1, a2, v6);
    if ( Error >= 0 && !CopySid(LengthSid, *a2, pSourceSid) )
    {
      Error = ResultFromLastError();
      CscUtil_HeapFree(*a2, v7);
      *a2 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147023559;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003443c  push    rbx
0x18003443e  push    rbp
0x18003443f  push    rsi
0x180034440  push    rdi
0x180034441  sub     rsp, 28h
0x180034445  mov     rdi, rdx
0x180034448  mov     qword ptr [rdx], 0
0x18003444f  mov     rsi, rcx
0x180034452  call    cs:__imp_IsValidSid
0x180034458  test    eax, eax
0x18003445a  jnz     short loc_180034463
0x18003445c  mov     ebx, 80070539h
0x180034461  jmp     short loc_1800344AB
0x180034463  mov     rcx, rsi; pSid
0x180034466  call    cs:__imp_GetLengthSid
0x18003446c  mov     ecx, eax; dwBytes
0x18003446e  mov     r8, rdi; void **
0x180034471  mov     edx, 1; int
0x180034476  mov     ebp, eax
0x180034478  call    ?CscUtil_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z; CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18003447d  mov     ebx, eax
0x18003447f  test    eax, eax
0x180034481  js      short loc_1800344AB
0x180034483  mov     rdx, [rdi]; pDestinationSid
0x180034486  mov     r8, rsi; pSourceSid
0x180034489  mov     ecx, ebp; nDestinationSidLength
0x18003448b  call    cs:__imp_CopySid
0x180034491  test    eax, eax
0x180034493  jnz     short loc_1800344AB
0x180034495  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18003449a  mov     rcx, [rdi]; lpMem
0x18003449d  mov     ebx, eax
0x18003449f  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800344a4  mov     qword ptr [rdi], 0
0x1800344ab  mov     eax, ebx
0x1800344ad  add     rsp, 28h
0x1800344b1  pop     rdi
0x1800344b2  pop     rsi
0x1800344b3  pop     rbp
0x1800344b4  pop     rbx
0x1800344b5  retn
```
