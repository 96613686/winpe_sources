# ClearSavedEapUserCredentials

- ea: `0x1800233e8`
- end: `0x18002343b`
- name: `ClearSavedEapUserCredentials`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b9b4`

## callees

- `0x180006a20`
- `0x18000e020`
- `0x1800233e8`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180023430`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180023430`

## pseudocode

```c
unsigned int __fastcall ClearSavedEapUserCredentials(CWorkerThreadState *a1)
{
  unsigned int result; // eax

  result = CWorkerThreadState::WaitForThread(a1);
  if ( byte_180033810 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
    return CredDeleteW(L"*Session", 2u, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800233e8  sub     rsp, 28h
0x1800233ec  call    ?WaitForThread@CWorkerThreadState@@QEAAKXZ; CWorkerThreadState::WaitForThread(void)
0x1800233f1  cmp     cs:byte_180033810, 0
0x1800233f8  jz      short loc_180023436
0x1800233fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180023401  lea     rax, WPP_GLOBAL_Control
0x180023408  cmp     rcx, rax
0x18002340b  jz      short loc_180023422
0x18002340d  mov     rcx, [rcx+10h]
0x180023411  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180023418  mov     edx, 48h ; 'H'
0x18002341d  call    WPP_SF_
0x180023422  xor     r8d, r8d; Flags
0x180023425  lea     rcx, TargetName; "*Session"
0x18002342c  lea     edx, [r8+2]; Type
0x180023430  call    cs:__imp_CredDeleteW
0x180023436  add     rsp, 28h
0x18002343a  retn
```
