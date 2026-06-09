# MupReleaseUncProvider

- ea: `0x14001c760`
- end: `0x14001c85f`
- name: `MupReleaseUncProvider`
- size: `255`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140001cf8`
- `0x140003140`
- `0x1400122a0`
- `0x140013130`
- `0x1400134a0`
- `0x14001c300`
- `0x14001cb80`
- `0x14001ce20`
- `0x14001ea10`
- `0x14001efe0`

## callees

- `0x140002754`
- `0x14001c760`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001c805`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001c805`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c7e9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c84e`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c7e9`
- `ntoskrnl!ObfDereferenceObject` at `0x14001c84e`
- `ntoskrnl!KeResetEvent` at `0x14001c82f`
- `ntoskrnl!KeResetEvent` at `0x14001c82f`

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
0x14001c760  mov     [rsp+arg_0], rbx
0x14001c765  push    rdi
0x14001c766  sub     rsp, 20h
0x14001c76a  mov     rdi, rcx
0x14001c76d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c774  lea     rax, WPP_GLOBAL_Control
0x14001c77b  cmp     rcx, rax
0x14001c77e  jz      short loc_14001C789
0x14001c780  test    dword ptr [rcx+2Ch], 4000000h
0x14001c787  jnz     short loc_14001C7BC
0x14001c789  movzx   eax, word ptr [rdi+90h]
0x14001c790  mov     ebx, 0FFFFFFFFh
0x14001c795  lock xadd [rdi+4], ebx
0x14001c79a  dec     ebx
0x14001c79c  mov     ecx, 101h
0x14001c7a1  cmp     ax, cx
0x14001c7a4  jb      short loc_14001C7D6
0x14001c7a6  cmp     ebx, 2
0x14001c7a9  jz      short loc_14001C7DB
0x14001c7ab  cmp     ebx, 1
0x14001c7ae  jz      short loc_14001C7F7
0x14001c7b0  mov     rbx, [rsp+28h+arg_0]
0x14001c7b5  add     rsp, 20h
0x14001c7b9  pop     rdi
0x14001c7ba  retn
0x14001c7bc  mov     rcx, [rcx+18h]
0x14001c7c0  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14001c7c7  mov     edx, 11h
0x14001c7cc  mov     r9, rdi
0x14001c7cf  call    WPP_SF_q
0x14001c7d4  jmp     short loc_14001C789
0x14001c7d6  cmp     ebx, 1
0x14001c7d9  jnz     short loc_14001C7B0
0x14001c7db  xor     ecx, ecx
0x14001c7dd  xchg    rcx, [rdi+0A0h]; Object
0x14001c7e4  test    rcx, rcx
0x14001c7e7  jz      short loc_14001C7AB
0x14001c7e9  call    cs:__imp_ObfDereferenceObject
0x14001c7f0  nop     dword ptr [rax+rax+00h]
0x14001c7f5  jmp     short loc_14001C7AB
0x14001c7f7  mov     eax, [rdi+94h]
0x14001c7fd  test    al, 4
0x14001c7ff  jz      short loc_14001C811
0x14001c801  lea     rcx, [rdi+18h]; SymbolicLinkName
0x14001c805  call    cs:__imp_IoDeleteSymbolicLink
0x14001c80c  nop     dword ptr [rax+rax+00h]
0x14001c811  mov     rcx, [rdi+88h]; Event
0x14001c818  mov     rbx, [rdi+0A8h]
0x14001c81f  mov     qword ptr [rdi+0A8h], 0
0x14001c82a  test    rcx, rcx
0x14001c82d  jz      short loc_14001C83B
0x14001c82f  call    cs:__imp_KeResetEvent
0x14001c836  nop     dword ptr [rax+rax+00h]
0x14001c83b  mov     dword ptr [rdi+44h], 1
0x14001c842  test    rbx, rbx
0x14001c845  jz      loc_14001C7B0
0x14001c84b  mov     rcx, rbx; Object
0x14001c84e  call    cs:__imp_ObfDereferenceObject
0x14001c855  nop     dword ptr [rax+rax+00h]
0x14001c85a  jmp     loc_14001C7B0
```
