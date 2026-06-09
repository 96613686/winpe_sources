# NcaCriticalSectionDestroy

- ea: `0x1800190a0`
- end: `0x1800190fa`
- name: `NcaCriticalSectionDestroy`
- size: `90`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x180004984`
- `0x180007360`
- `0x18000b4f4`
- `0x18000db90`
- `0x18000f430`
- `0x180010270`
- `0x180010600`
- `0x1800109b0`
- `0x180010de0`
- `0x180011bc0`
- `0x180012c20`
- `0x180013990`
- `0x180013dd0`
- `0x180014520`
- `0x180014aa0`
- `0x180014d20`
- `0x180015140`
- `0x180015900`
- `0x180015e80`
- `0x180016890`
- `0x180016c08`
- `0x180018170`

## callees

- `0x180004f04`
- `0x1800190a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800190e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800190e0`

## pseudocode

```c
void __fastcall NcaCriticalSectionDestroy(LPCRITICAL_SECTION lpCriticalSection)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  if ( LODWORD(lpCriticalSection[1].DebugInfo) )
  {
    DeleteCriticalSection(lpCriticalSection);
    LODWORD(lpCriticalSection[1].DebugInfo) = 0;
  }
}

```

## disassembly

```asm
0x1800190a0  push    rbx
0x1800190a2  sub     rsp, 20h
0x1800190a6  mov     rbx, rcx
0x1800190a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800190b0  lea     rax, WPP_GLOBAL_Control
0x1800190b7  cmp     rcx, rax
0x1800190ba  jz      short loc_1800190D7
0x1800190bc  test    byte ptr [rcx+1Ch], 8
0x1800190c0  jz      short loc_1800190D7
0x1800190c2  mov     rcx, [rcx+10h]
0x1800190c6  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x1800190cd  mov     edx, 24h ; '$'
0x1800190d2  call    WPP_SF_
0x1800190d7  cmp     dword ptr [rbx+28h], 0
0x1800190db  jz      short loc_1800190F3
0x1800190dd  mov     rcx, rbx; lpCriticalSection
0x1800190e0  call    cs:__imp_DeleteCriticalSection
0x1800190e7  nop     dword ptr [rax+rax+00h]
0x1800190ec  mov     dword ptr [rbx+28h], 0
0x1800190f3  add     rsp, 20h
0x1800190f7  pop     rbx
0x1800190f8  retn
```
