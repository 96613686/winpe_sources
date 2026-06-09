# NgscbTryWriteEventLog(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180011390`
- end: `0x1800113ec`
- name: `?NgscbTryWriteEventLog@@YAXPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `92`
- prototype: `void __fastcall(PCEVENT_DESCRIPTOR EventDescriptor, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fbc0`

## callees

- `0x1800037a0`
- `0x180011390`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1800113ac`
- `ADVAPI32!EventWrite` at `0x1800113ac`

## pseudocode

```c
void __fastcall NgscbTryWriteEventLog(
        PCEVENT_DESCRIPTOR EventDescriptor,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  ULONG v3; // eax

  if ( g_HstiEventLog )
  {
    v3 = EventWrite(g_HstiEventLog, EventDescriptor, UserDataCount, UserData);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fdbaa957ea32373b347160d97d74c1eb_Traceguids, v3);
    }
  }
}

```

## disassembly

```asm
0x180011390  sub     rsp, 28h
0x180011394  mov     rax, rcx
0x180011397  mov     rcx, cs:?g_HstiEventLog@@3_KA; RegHandle
0x18001139e  test    rcx, rcx
0x1800113a1  jz      short loc_1800113E7
0x1800113a3  mov     r9, r8; UserData
0x1800113a6  mov     r8d, edx; UserDataCount
0x1800113a9  mov     rdx, rax; EventDescriptor
0x1800113ac  call    cs:__imp_EventWrite
0x1800113b2  test    eax, eax
0x1800113b4  jz      short loc_1800113E7
0x1800113b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113bd  lea     rdx, WPP_GLOBAL_Control
0x1800113c4  cmp     rcx, rdx
0x1800113c7  jz      short loc_1800113E7
0x1800113c9  test    byte ptr [rcx+1Ch], 2
0x1800113cd  jz      short loc_1800113E7
0x1800113cf  mov     rcx, [rcx+10h]
0x1800113d3  lea     r8, WPP_fdbaa957ea32373b347160d97d74c1eb_Traceguids
0x1800113da  mov     edx, 0Bh
0x1800113df  mov     r9d, eax
0x1800113e2  call    WPP_SF_d
0x1800113e7  add     rsp, 28h
0x1800113eb  retn
```
