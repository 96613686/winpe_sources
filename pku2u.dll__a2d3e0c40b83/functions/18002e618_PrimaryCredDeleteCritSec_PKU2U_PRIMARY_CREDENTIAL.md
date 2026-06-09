# PrimaryCredDeleteCritSec(_PKU2U_PRIMARY_CREDENTIAL *)

- ea: `0x18002e618`
- end: `0x18002e6a1`
- name: `?PrimaryCredDeleteCritSec@@YAJPEAU_PKU2U_PRIMARY_CREDENTIAL@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002dbdc`
- `0x18002e0ac`

## callees

- `0x1800264a4`
- `0x18002e618`
- `0x18002e738`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18002e65c`
- `ntdll!RtlDeleteCriticalSection` at `0x18002e65c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e693`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e693`
- `ntdll!RtlEnterCriticalSection` at `0x18002e64d`
- `ntdll!RtlEnterCriticalSection` at `0x18002e64d`

## string_xrefs

- `0x18002e62b`: `onecore\ds\security\protocols\pku2u\credapi.cxx`
- `0x18002e66b`: `onecore\ds\security\protocols\pku2u\credapi.cxx`

## pseudocode

```c
__int64 __fastcall PrimaryCredDeleteCritSec(PRTL_CRITICAL_SECTION CriticalSection)
{
  unsigned int v2; // ebx
  NTSTATUS v3; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( CriticalSection )
  {
    RtlEnterCriticalSection(&Pku2uGlobalPrimaryCredCritSectionInitLock);
    if ( LODWORD(CriticalSection[1].DebugInfo) )
    {
      v3 = RtlDeleteCriticalSection(CriticalSection);
      if ( v3 < 0 )
      {
        v2 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x42E,
               (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
               (const char *)(unsigned int)v3,
               v5);
LABEL_8:
        RtlLeaveCriticalSection(&Pku2uGlobalPrimaryCredCritSectionInitLock);
        return v2;
      }
      LODWORD(CriticalSection[1].DebugInfo) = 0;
    }
    v2 = 0;
    goto LABEL_8;
  }
  v2 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x425,
    (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
    (const char *)0x80070057LL,
    v5);
  return v2;
}

```

## disassembly

```asm
0x18002e618  push    rbx; int
0x18002e61a  sub     rsp, 20h
0x18002e61e  mov     rbx, rcx
0x18002e621  test    rcx, rcx
0x18002e624  jnz     short loc_18002E646
0x18002e626  mov     rcx, [rsp+28h]; this
0x18002e62b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e632  mov     ebx, 80070057h
0x18002e637  mov     edx, 425h; void *
0x18002e63c  mov     r9d, ebx; char *
0x18002e63f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e644  jmp     short loc_18002E699
0x18002e646  lea     rcx, ?Pku2uGlobalPrimaryCredCritSectionInitLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002e64d  call    cs:__imp_RtlEnterCriticalSection
0x18002e653  cmp     dword ptr [rbx+28h], 0
0x18002e657  jz      short loc_18002E68A
0x18002e659  mov     rcx, rbx; CriticalSection
0x18002e65c  call    cs:__imp_RtlDeleteCriticalSection
0x18002e662  test    eax, eax
0x18002e664  jns     short loc_18002E683
0x18002e666  mov     rcx, [rsp+28h]; this
0x18002e66b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e672  mov     r9d, eax; char *
0x18002e675  mov     edx, 42Eh; void *
0x18002e67a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e67f  mov     ebx, eax
0x18002e681  jmp     short loc_18002E68C
0x18002e683  mov     dword ptr [rbx+28h], 0
0x18002e68a  xor     ebx, ebx
0x18002e68c  lea     rcx, ?Pku2uGlobalPrimaryCredCritSectionInitLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002e693  call    cs:__imp_RtlLeaveCriticalSection
0x18002e699  mov     eax, ebx
0x18002e69b  add     rsp, 20h
0x18002e69f  pop     rbx
0x18002e6a0  retn
```
