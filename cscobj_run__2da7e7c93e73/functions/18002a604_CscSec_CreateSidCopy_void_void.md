# CscSec_CreateSidCopy(void *,void * *)

- ea: `0x18002a604`
- end: `0x18002a679`
- name: `?CscSec_CreateSidCopy@@YAJPEAXPEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a5a8`

## callees

- `0x180002d80`
- `0x1800084e0`
- `0x180009864`
- `0x18002a604`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a64e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002a64e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a62e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a62e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a61a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002a61a`

## pseudocode

```c
__int64 __fastcall CscSec_CreateSidCopy(PSID pSourceSid, void **a2)
{
  int Error; // ebx
  DWORD LengthSid; // ebp
  __int64 v6; // rdx
  void **v7; // r9
  UstVarLib *v8; // rcx
  void *v9; // rdx

  *a2 = 0;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    Error = UstVarLib::CscUtil_HeapAlloc(LengthSid, v6, a2, v7);
    if ( Error >= 0 && !CopySid(LengthSid, *a2, pSourceSid) )
    {
      Error = UstVarLib::ResultFromLastError(v8);
      CscUtil_HeapFree(*a2, v9);
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
0x18002a604  push    rbx
0x18002a606  push    rbp
0x18002a607  push    rsi
0x18002a608  push    rdi
0x18002a609  sub     rsp, 28h
0x18002a60d  mov     rdi, rdx
0x18002a610  mov     qword ptr [rdx], 0
0x18002a617  mov     rsi, rcx
0x18002a61a  call    cs:__imp_IsValidSid
0x18002a620  test    eax, eax
0x18002a622  jnz     short loc_18002A62B
0x18002a624  mov     ebx, 80070539h
0x18002a629  jmp     short loc_18002A66E
0x18002a62b  mov     rcx, rsi; pSid
0x18002a62e  call    cs:__imp_GetLengthSid
0x18002a634  mov     ecx, eax; dwBytes
0x18002a636  mov     r8, rdi; int
0x18002a639  mov     ebp, eax
0x18002a63b  call    ?CscUtil_HeapAlloc@UstVarLib@@YAJ_KHPEAPEAXPEAX@Z; UstVarLib::CscUtil_HeapAlloc(unsigned __int64,int,void * *,void *)
0x18002a640  mov     ebx, eax
0x18002a642  test    eax, eax
0x18002a644  js      short loc_18002A66E
0x18002a646  mov     rdx, [rdi]; pDestinationSid
0x18002a649  mov     r8, rsi; pSourceSid
0x18002a64c  mov     ecx, ebp; nDestinationSidLength
0x18002a64e  call    cs:__imp_CopySid
0x18002a654  test    eax, eax
0x18002a656  jnz     short loc_18002A66E
0x18002a658  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18002a65d  mov     rcx, [rdi]; lpMem
0x18002a660  mov     ebx, eax
0x18002a662  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18002a667  mov     qword ptr [rdi], 0
0x18002a66e  mov     eax, ebx
0x18002a670  add     rsp, 28h
0x18002a674  pop     rdi
0x18002a675  pop     rsi
0x18002a676  pop     rbp
0x18002a677  pop     rbx
0x18002a678  retn
```
