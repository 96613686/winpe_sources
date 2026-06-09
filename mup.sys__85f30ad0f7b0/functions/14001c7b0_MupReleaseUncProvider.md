# MupReleaseUncProvider

- ea: `0x14001c7b0`
- end: `0x14001c8af`
- name: `MupReleaseUncProvider`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140001cf8`
- `0x140003140`
- `0x1400122f0`
- `0x140013180`
- `0x1400134f0`
- `0x14001c350`
- `0x14001cbd0`
- `0x14001ce70`
- `0x14001ea60`
- `0x14001f030`

## callees

- `0x140002754`
- `0x14001c7b0`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001c855`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001c855`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c839`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c89e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c839`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c89e`
- `ntoskrnl!KeResetEvent` at `0x14001c87f`
- `ntoskrnl!KeResetEvent` at `0x14001c87f`

## pseudocode

```c
int __fastcall MupReleaseUncProvider(__int64 a1)
{
  int result; // eax
  signed __int32 v3; // ebx
  void *v4; // rcx
  struct _KEVENT *v5; // rcx
  void *v6; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids, a1);
  }
  result = *(unsigned __int16 *)(a1 + 144);
  v3 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 4));
  if ( (unsigned __int16)result < 0x101u )
  {
    if ( v3 != 1 )
      return result;
    goto LABEL_9;
  }
  if ( v3 == 2 )
  {
LABEL_9:
    v4 = (void *)_InterlockedExchange64((volatile __int64 *)(a1 + 160), 0);
    if ( v4 )
      result = ObfDereferenceObject(v4);
  }
  if ( v3 == 1 )
  {
    result = *(_DWORD *)(a1 + 148);
    if ( (result & 4) != 0 )
      result = IoDeleteSymbolicLink((PUNICODE_STRING)(a1 + 24));
    v5 = *(struct _KEVENT **)(a1 + 136);
    v6 = *(void **)(a1 + 168);
    *(_QWORD *)(a1 + 168) = 0;
    if ( v5 )
      result = KeResetEvent(v5);
    *(_DWORD *)(a1 + 68) = 1;
    if ( v6 )
      return ObfDereferenceObject(v6);
  }
  return result;
}

```

## disassembly

```asm
0x14001c7b0  mov     [rsp+arg_0], rbx
0x14001c7b5  push    rdi
0x14001c7b6  sub     rsp, 20h
0x14001c7ba  mov     rdi, rcx
0x14001c7bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c7c4  lea     rax, WPP_GLOBAL_Control
0x14001c7cb  cmp     rcx, rax
0x14001c7ce  jz      short loc_14001C7D9
0x14001c7d0  test    dword ptr [rcx+2Ch], 4000000h
0x14001c7d7  jnz     short loc_14001C80C
0x14001c7d9  movzx   eax, word ptr [rdi+90h]
0x14001c7e0  mov     ebx, 0FFFFFFFFh
0x14001c7e5  lock xadd [rdi+4], ebx
0x14001c7ea  dec     ebx
0x14001c7ec  mov     ecx, 101h
0x14001c7f1  cmp     ax, cx
0x14001c7f4  jb      short loc_14001C826
0x14001c7f6  cmp     ebx, 2
0x14001c7f9  jz      short loc_14001C82B
0x14001c7fb  cmp     ebx, 1
0x14001c7fe  jz      short loc_14001C847
0x14001c800  mov     rbx, [rsp+28h+arg_0]
0x14001c805  add     rsp, 20h
0x14001c809  pop     rdi
0x14001c80a  retn
0x14001c80c  mov     rcx, [rcx+18h]
0x14001c810  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14001c817  mov     edx, 11h
0x14001c81c  mov     r9, rdi
0x14001c81f  call    WPP_SF_q
0x14001c824  jmp     short loc_14001C7D9
0x14001c826  cmp     ebx, 1
0x14001c829  jnz     short loc_14001C800
0x14001c82b  xor     ecx, ecx
0x14001c82d  xchg    rcx, [rdi+0A0h]; Object
0x14001c834  test    rcx, rcx
0x14001c837  jz      short loc_14001C7FB
0x14001c839  call    cs:__imp_ObfDereferenceObject
0x14001c840  nop     dword ptr [rax+rax+00h]
0x14001c845  jmp     short loc_14001C7FB
0x14001c847  mov     eax, [rdi+94h]
0x14001c84d  test    al, 4
0x14001c84f  jz      short loc_14001C861
0x14001c851  lea     rcx, [rdi+18h]; SymbolicLinkName
0x14001c855  call    cs:__imp_IoDeleteSymbolicLink
0x14001c85c  nop     dword ptr [rax+rax+00h]
0x14001c861  mov     rcx, [rdi+88h]; Event
0x14001c868  mov     rbx, [rdi+0A8h]
0x14001c86f  mov     qword ptr [rdi+0A8h], 0
0x14001c87a  test    rcx, rcx
0x14001c87d  jz      short loc_14001C88B
0x14001c87f  call    cs:__imp_KeResetEvent
0x14001c886  nop     dword ptr [rax+rax+00h]
0x14001c88b  mov     dword ptr [rdi+44h], 1
0x14001c892  test    rbx, rbx
0x14001c895  jz      loc_14001C800
0x14001c89b  mov     rcx, rbx; Object
0x14001c89e  call    cs:__imp_ObfDereferenceObject
0x14001c8a5  nop     dword ptr [rax+rax+00h]
0x14001c8aa  jmp     loc_14001C800
```
