# Log::Verbose(ILogContext const *,ushort const *,...)

- ea: `0x14000c7d8`
- end: `0x14000c8c3`
- name: `?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ`
- size: `235`
- prototype: `void(const struct ILogContext *, const unsigned __int16 *, ...)`
- caller_count: `26`
- callee_count: `6`
- tags: ``

## callers

- `0x140007d8c`
- `0x14000a34c`
- `0x14000a610`
- `0x14000a910`
- `0x14000a970`
- `0x14000b0c0`
- `0x14000b4f4`
- `0x14000b7e0`
- `0x140014ea4`
- `0x14001604c`
- `0x140025ccc`
- `0x140025e48`
- `0x140026800`
- `0x140026c9c`
- `0x14002a4b0`
- `0x14002a520`
- `0x14002a728`
- `0x14002aa18`
- `0x14002b1f4`
- `0x14002b2d0`
- `0x14002b868`
- `0x14002b9d4`
- `0x14002ba9c`
- `0x14002df49`
- `0x14002f884`
- `0x14002f989`

## callees

- `0x1400081d8`
- `0x140008674`
- `0x14000c308`
- `0x14000c564`
- `0x14000c7d8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void Log::Verbose(const struct ILogContext *a1, const unsigned __int16 *a2, ...)
{
  _QWORD *ContextInfo; // rax
  _QWORD *v4; // rdx
  __int64 v5; // rbx
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+28h] [rbp-10h] BYREF
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( Log::targetLevel == 3 )
  {
    v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v7 = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::FormatV(
      &v6,
      a2,
      (__int64 *)va);
    ContextInfo = (_QWORD *)Log::GetContextInfo(&v7, a1);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &v6,
      L"\n%s",
      *ContextInfo);
    v4 = (_QWORD *)(v7 - 24);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 8LL))(*v4);
    v5 = v6;
    Log::NotifyLoggers(&dword_14003353C, v6, 3, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 - 24 + 16), 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v5 - 24) + 8LL))(*(_QWORD *)(v5 - 24));
  }
}

```

## disassembly

```asm
0x14000c7d8  mov     [rsp+arg_8], rdx
0x14000c7dd  mov     [rsp+arg_10], r8
0x14000c7e2  mov     [rsp+arg_18], r9
0x14000c7e7  push    rbx
0x14000c7e8  sub     rsp, 30h
0x14000c7ec  mov     rbx, rcx
0x14000c7ef  cmp     cs:?targetLevel@Log@@0W4LogLevel@@A, 3; LogLevel Log::targetLevel
0x14000c7f6  jnz     loc_14000C8BD
0x14000c7fc  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000c803  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000c80a  mov     rax, [rax+18h]
0x14000c80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c813  add     rax, 18h
0x14000c817  mov     [rsp+38h+var_18], rax
0x14000c81c  mov     [rsp+38h+var_10], 0
0x14000c825  lea     r8, [rsp+38h+arg_10]
0x14000c82a  mov     rdx, [rsp+38h+arg_8]
0x14000c82f  lea     rcx, [rsp+38h+var_18]
0x14000c834  call    ?FormatV@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGPEAD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::FormatV(ushort const *,char *)
0x14000c839  mov     rdx, rbx
0x14000c83c  lea     rcx, [rsp+38h+var_10]
0x14000c841  call    ?GetContextInfo@Log@@CA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBVILogContext@@@Z; Log::GetContextInfo(ILogContext const *)
0x14000c846  nop
0x14000c847  mov     r8, [rax]
0x14000c84a  lea     rdx, aS_1; "\n%s"
0x14000c851  lea     rcx, [rsp+38h+var_18]
0x14000c856  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000c85b  nop
0x14000c85c  mov     rdx, [rsp+38h+var_10]
0x14000c861  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000c865  or      eax, 0FFFFFFFFh
0x14000c868  lock xadd [rdx+10h], eax
0x14000c86d  sub     eax, 1
0x14000c870  jg      short loc_14000C881
0x14000c872  mov     rcx, [rdx]
0x14000c875  mov     rax, [rcx]
0x14000c878  mov     rax, [rax+8]
0x14000c87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c881  xor     r9d, r9d
0x14000c884  lea     r8d, [r9+3]
0x14000c888  mov     rbx, [rsp+38h+var_18]
0x14000c88d  mov     rdx, rbx
0x14000c890  lea     rcx, dword_14003353C
0x14000c897  call    ?NotifyLoggers@Log@@CAXPEBG0W4LogLevel@@K@Z; Log::NotifyLoggers(ushort const *,ushort const *,LogLevel,ulong)
0x14000c89c  nop
0x14000c89d  lea     rdx, [rbx-18h]
0x14000c8a1  or      eax, 0FFFFFFFFh
0x14000c8a4  lock xadd [rdx+10h], eax
0x14000c8a9  sub     eax, 1
0x14000c8ac  jg      short loc_14000C8BD
0x14000c8ae  mov     rcx, [rdx]
0x14000c8b1  mov     rax, [rcx]
0x14000c8b4  mov     rax, [rax+8]
0x14000c8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8bd  add     rsp, 30h
0x14000c8c1  pop     rbx
0x14000c8c2  retn
```
