# PrimaryCredInitCritSec(_PKU2U_PRIMARY_CREDENTIAL *)

- ea: `0x18002e6a8`
- end: `0x18002e731`
- name: `?PrimaryCredInitCritSec@@YAJPEAU_PKU2U_PRIMARY_CREDENTIAL@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002dec4`
- `0x18002e0ac`
- `0x18002e234`

## callees

- `0x1800264a4`
- `0x18002e6a8`
- `0x18002e738`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x18002e6ec`
- `ntdll!RtlInitializeCriticalSection` at `0x18002e6ec`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e723`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e723`
- `ntdll!RtlEnterCriticalSection` at `0x18002e6dd`
- `ntdll!RtlEnterCriticalSection` at `0x18002e6dd`

## string_xrefs

- `0x18002e6bb`: `onecore\ds\security\protocols\pku2u\credapi.cxx`
- `0x18002e6fb`: `onecore\ds\security\protocols\pku2u\credapi.cxx`

## pseudocode

```c
__int64 __fastcall PrimaryCredInitCritSec(PRTL_CRITICAL_SECTION CriticalSection)
{
  unsigned int v2; // ebx
  NTSTATUS v3; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( CriticalSection )
  {
    RtlEnterCriticalSection(&Pku2uGlobalPrimaryCredCritSectionInitLock);
    if ( !LODWORD(CriticalSection[1].DebugInfo) )
    {
      v3 = RtlInitializeCriticalSection(CriticalSection);
      if ( v3 < 0 )
      {
        v2 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x41D,
               (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
               (const char *)(unsigned int)v3,
               v5);
LABEL_8:
        RtlLeaveCriticalSection(&Pku2uGlobalPrimaryCredCritSectionInitLock);
        return v2;
      }
      LODWORD(CriticalSection[1].DebugInfo) = 1;
    }
    v2 = 0;
    goto LABEL_8;
  }
  v2 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x414,
    (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\credapi.cxx",
    (const char *)0x80070057LL,
    v5);
  return v2;
}

```

## disassembly

```asm
0x18002e6a8  push    rbx; int
0x18002e6aa  sub     rsp, 20h
0x18002e6ae  mov     rbx, rcx
0x18002e6b1  test    rcx, rcx
0x18002e6b4  jnz     short loc_18002E6D6
0x18002e6b6  mov     rcx, [rsp+28h]; this
0x18002e6bb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e6c2  mov     ebx, 80070057h
0x18002e6c7  mov     edx, 414h; void *
0x18002e6cc  mov     r9d, ebx; char *
0x18002e6cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e6d4  jmp     short loc_18002E729
0x18002e6d6  lea     rcx, ?Pku2uGlobalPrimaryCredCritSectionInitLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002e6dd  call    cs:__imp_RtlEnterCriticalSection
0x18002e6e3  cmp     dword ptr [rbx+28h], 0
0x18002e6e7  jnz     short loc_18002E71A
0x18002e6e9  mov     rcx, rbx; CriticalSection
0x18002e6ec  call    cs:__imp_RtlInitializeCriticalSection
0x18002e6f2  test    eax, eax
0x18002e6f4  jns     short loc_18002E713
0x18002e6f6  mov     rcx, [rsp+28h]; this
0x18002e6fb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002e702  mov     r9d, eax; char *
0x18002e705  mov     edx, 41Dh; void *
0x18002e70a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e70f  mov     ebx, eax
0x18002e711  jmp     short loc_18002E71C
0x18002e713  mov     dword ptr [rbx+28h], 1
0x18002e71a  xor     ebx, ebx
0x18002e71c  lea     rcx, ?Pku2uGlobalPrimaryCredCritSectionInitLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002e723  call    cs:__imp_RtlLeaveCriticalSection
0x18002e729  mov     eax, ebx
0x18002e72b  add     rsp, 20h
0x18002e72f  pop     rbx
0x18002e730  retn
```
