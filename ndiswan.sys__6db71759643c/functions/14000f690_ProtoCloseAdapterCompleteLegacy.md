# ProtoCloseAdapterCompleteLegacy

- ea: `0x14000f690`
- end: `0x14000f761`
- name: `ProtoCloseAdapterCompleteLegacy`
- size: `209`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f768`

## callees

- `0x140004ab8`
- `0x14000a290`
- `0x14000a648`
- `0x14000f690`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000f70c`
- `ntoskrnl!KeSetEvent` at `0x14000f70c`
- `NDIS!NdisCompleteUnbindAdapter` at `0x14000f6ed`
- `NDIS!NdisCompleteUnbindAdapter` at `0x14000f6ed`

## pseudocode

```c
LONG __fastcall ProtoCloseAdapterCompleteLegacy(char *P, unsigned int a2)
{
  __int64 v4; // rcx
  LONG result; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_714410adb39534c9cec6a41078899c0f_Traceguids, P);
  }
  v4 = *((_QWORD *)P + 14);
  *((_DWORD *)P + 40) = a2;
  if ( v4 )
    NdisCompleteUnbindAdapter(v4, a2);
  if ( (*((_DWORD *)P + 5) & 0x10) != 0 )
    result = KeSetEvent((PRKEVENT)(P + 136), 0, 0);
  else
    result = NdisWanFreeOpenCB(P);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_714410adb39534c9cec6a41078899c0f_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000f690  mov     [rsp+arg_0], rbx
0x14000f695  mov     [rsp+arg_8], rsi
0x14000f69a  push    rdi
0x14000f69b  sub     rsp, 20h
0x14000f69f  mov     edi, edx
0x14000f6a1  mov     rbx, rcx
0x14000f6a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f6ab  lea     rsi, WPP_GLOBAL_Control
0x14000f6b2  cmp     rcx, rsi
0x14000f6b5  jz      short loc_14000F6DC
0x14000f6b7  mov     eax, [rcx+2Ch]
0x14000f6ba  test    al, 4
0x14000f6bc  jz      short loc_14000F6DC
0x14000f6be  cmp     byte ptr [rcx+29h], 5
0x14000f6c2  jb      short loc_14000F6DC
0x14000f6c4  mov     rcx, [rcx+18h]
0x14000f6c8  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000f6cf  mov     edx, 10h
0x14000f6d4  mov     r9, rbx
0x14000f6d7  call    WPP_SF_q
0x14000f6dc  mov     rcx, [rbx+70h]
0x14000f6e0  mov     [rbx+0A0h], edi
0x14000f6e6  test    rcx, rcx
0x14000f6e9  jz      short loc_14000F6F9
0x14000f6eb  mov     edx, edi
0x14000f6ed  call    cs:__imp_NdisCompleteUnbindAdapter
0x14000f6f4  nop     dword ptr [rax+rax+00h]
0x14000f6f9  mov     eax, [rbx+14h]
0x14000f6fc  test    al, 10h
0x14000f6fe  jz      short loc_14000F71A
0x14000f700  lea     rcx, [rbx+88h]; Event
0x14000f707  xor     r8d, r8d; Wait
0x14000f70a  xor     edx, edx; Increment
0x14000f70c  call    cs:__imp_KeSetEvent
0x14000f713  nop     dword ptr [rax+rax+00h]
0x14000f718  jmp     short loc_14000F722
0x14000f71a  mov     rcx, rbx; P
0x14000f71d  call    NdisWanFreeOpenCB
0x14000f722  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f729  cmp     rcx, rsi
0x14000f72c  jz      short loc_14000F750
0x14000f72e  mov     eax, [rcx+2Ch]
0x14000f731  test    al, 4
0x14000f733  jz      short loc_14000F750
0x14000f735  cmp     byte ptr [rcx+29h], 5
0x14000f739  jb      short loc_14000F750
0x14000f73b  mov     rcx, [rcx+18h]
0x14000f73f  lea     r8, WPP_714410adb39534c9cec6a41078899c0f_Traceguids
0x14000f746  mov     edx, 11h
0x14000f74b  call    WPP_SF_
0x14000f750  mov     rbx, [rsp+28h+arg_0]
0x14000f755  mov     rsi, [rsp+28h+arg_8]
0x14000f75a  add     rsp, 20h
0x14000f75e  pop     rdi
0x14000f75f  retn
```
