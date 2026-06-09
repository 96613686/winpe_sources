# CscSec_ConvertStringSidToSid(ushort const *,void * *)

- ea: `0x18002a5a8`
- end: `0x18002a5fb`
- name: `?CscSec_ConvertStringSidToSid@@YAJPEBGPEAPEAX@Z`
- size: `83`
- prototype: `int(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014f50`

## callees

- `0x180009864`
- `0x18002a5a8`
- `0x18002a604`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002a5c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002a5c6`

## pseudocode

```c
__int64 __fastcall CscSec_ConvertStringSidToSid(const unsigned __int16 *a1, void **a2)
{
  UstVarLib *v3; // rcx
  unsigned int SidCopy; // ebx
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    SidCopy = CscSec_CreateSidCopy(Sid, a2);
    LocalFree(Sid);
  }
  else
  {
    return (unsigned int)UstVarLib::ResultFromLastError(v3);
  }
  return SidCopy;
}

```

## disassembly

```asm
0x18002a5a8  push    rbx
0x18002a5aa  sub     rsp, 20h
0x18002a5ae  mov     rbx, rdx
0x18002a5b1  mov     qword ptr [rdx], 0
0x18002a5b8  lea     rdx, [rsp+28h+Sid]; Sid
0x18002a5bd  mov     [rsp+28h+Sid], 0
0x18002a5c6  call    cs:__imp_ConvertStringSidToSidW
0x18002a5cc  test    eax, eax
0x18002a5ce  jnz     short loc_18002A5D9
0x18002a5d0  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18002a5d5  mov     ebx, eax
0x18002a5d7  jmp     short loc_18002A5F3
0x18002a5d9  mov     rcx, [rsp+28h+Sid]; pSourceSid
0x18002a5de  mov     rdx, rbx; void **
0x18002a5e1  call    ?CscSec_CreateSidCopy@@YAJPEAXPEAPEAX@Z; CscSec_CreateSidCopy(void *,void * *)
0x18002a5e6  mov     rcx, [rsp+28h+Sid]; hMem
0x18002a5eb  mov     ebx, eax
0x18002a5ed  call    cs:__imp_LocalFree
0x18002a5f3  mov     eax, ebx
0x18002a5f5  add     rsp, 20h
0x18002a5f9  pop     rbx
0x18002a5fa  retn
```
