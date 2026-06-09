# ProtoCloseAdapterComplete

- ea: `0x140037b70`
- end: `0x140037c34`
- name: `ProtoCloseAdapterComplete`
- size: `196`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005dd0`

## callees

- `0x140004ab8`
- `0x14000a290`
- `0x14000a648`
- `0x140037b70`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140037bdf`
- `ntoskrnl!KeSetEvent` at `0x140037bdf`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x140037ba0`
- `NDIS!NdisCompleteUnbindAdapterEx` at `0x140037ba0`

## pseudocode

```c
LONG __fastcall ProtoCloseAdapterComplete(char *P)
{
  void *v2; // rcx
  LONG result; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, P);
  }
  v2 = (void *)*((_QWORD *)P + 14);
  if ( v2 )
    NdisCompleteUnbindAdapterEx(v2);
  if ( (*((_DWORD *)P + 5) & 0x10) != 0 )
    result = KeSetEvent((PRKEVENT)(P + 136), 0, 0);
  else
    result = NdisWanFreeOpenCB(P);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x140037b70  mov     [rsp+arg_0], rbx
0x140037b75  push    rdi
0x140037b76  sub     rsp, 20h
0x140037b7a  mov     rbx, rcx
0x140037b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b84  lea     rdi, WPP_GLOBAL_Control
0x140037b8b  cmp     rcx, rdi
0x140037b8e  jz      short loc_140037B97
0x140037b90  mov     eax, [rcx+2Ch]
0x140037b93  test    al, 4
0x140037b95  jnz     short loc_140037C11
0x140037b97  mov     rcx, [rbx+70h]; UnbindContext
0x140037b9b  test    rcx, rcx
0x140037b9e  jz      short loc_140037BAC
0x140037ba0  call    cs:__imp_NdisCompleteUnbindAdapterEx
0x140037ba7  nop     dword ptr [rax+rax+00h]
0x140037bac  mov     eax, [rbx+14h]
0x140037baf  test    al, 10h
0x140037bb1  jnz     short loc_140037BD3
0x140037bb3  mov     rcx, rbx; P
0x140037bb6  call    NdisWanFreeOpenCB
0x140037bbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140037bc2  cmp     rcx, rdi
0x140037bc5  jnz     short loc_140037BED
0x140037bc7  mov     rbx, [rsp+28h+arg_0]
0x140037bcc  add     rsp, 20h
0x140037bd0  pop     rdi
0x140037bd1  retn
0x140037bd3  lea     rcx, [rbx+88h]; Event
0x140037bda  xor     r8d, r8d; Wait
0x140037bdd  xor     edx, edx; Increment
0x140037bdf  call    cs:__imp_KeSetEvent
0x140037be6  nop     dword ptr [rax+rax+00h]
0x140037beb  jmp     short loc_140037BBB
0x140037bed  mov     eax, [rcx+2Ch]
0x140037bf0  test    al, 4
0x140037bf2  jz      short loc_140037BC7
0x140037bf4  cmp     byte ptr [rcx+29h], 5
0x140037bf8  jb      short loc_140037BC7
0x140037bfa  mov     rcx, [rcx+18h]
0x140037bfe  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140037c05  mov     edx, 11h
0x140037c0a  call    WPP_SF_
0x140037c0f  jmp     short loc_140037BC7
0x140037c11  cmp     byte ptr [rcx+29h], 5
0x140037c15  jb      short loc_140037B97
0x140037c17  mov     rcx, [rcx+18h]
0x140037c1b  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140037c22  mov     edx, 10h
0x140037c27  mov     r9, rbx
0x140037c2a  call    WPP_SF_q
0x140037c2f  jmp     loc_140037B97
```
