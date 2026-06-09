# CDDPDEV::ReleaseClientThread(_WORKERTHREAD_COMMAND,uchar *)

- ea: `0x1400225ac`
- end: `0x14002262e`
- name: `?ReleaseClientThread@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@PEAE@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140030bd0`

## callees

- `0x1400225ac`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400225ca`
- `ntoskrnl!KeReadStateEvent` at `0x1400225ca`
- `ntoskrnl!KeSetEvent` at `0x140022607`
- `ntoskrnl!KeSetEvent` at `0x140022607`

## pseudocode

```c
LONG __fastcall CDDPDEV::ReleaseClientThread(__int64 a1, int a2, _BYTE *a3)
{
  LONG result; // eax
  __int64 v7; // rax

  result = KeReadStateEvent(*(PRKEVENT *)(a1 + 2608));
  if ( result || *a3 && (a2 & 0xFFFFFFEF) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 7264);
    *(_DWORD *)(a1 + 3608) = -1073741130;
    *(_BYTE *)(v7 + 2) = 0;
    result = KeSetEvent(*(PRKEVENT *)(a1 + 2632), 0, 0);
    *(_BYTE *)(a1 + 2754) = 1;
  }
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x1400225ac  mov     [rsp+arg_0], rbx
0x1400225b1  mov     [rsp+arg_8], rsi
0x1400225b6  push    rdi
0x1400225b7  sub     rsp, 20h
0x1400225bb  mov     rbx, rcx
0x1400225be  mov     rdi, r8
0x1400225c1  mov     rcx, [rcx+0A30h]; Event
0x1400225c8  mov     esi, edx
0x1400225ca  call    cs:__imp_KeReadStateEvent
0x1400225d1  nop     dword ptr [rax+rax+00h]
0x1400225d6  test    eax, eax
0x1400225d8  jnz     short loc_1400225E6
0x1400225da  cmp     [rdi], al
0x1400225dc  jz      short loc_14002261A
0x1400225de  test    esi, 0FFFFFFEFh
0x1400225e4  jz      short loc_14002261A
0x1400225e6  mov     rax, [rbx+1C60h]
0x1400225ed  xor     r8d, r8d; Wait
0x1400225f0  mov     dword ptr [rbx+0E18h], 0C00002B6h
0x1400225fa  xor     edx, edx; Increment
0x1400225fc  mov     byte ptr [rax+2], 0
0x140022600  mov     rcx, [rbx+0A48h]; Event
0x140022607  call    cs:__imp_KeSetEvent
0x14002260e  nop     dword ptr [rax+rax+00h]
0x140022613  mov     byte ptr [rbx+0AC2h], 1
0x14002261a  mov     rbx, [rsp+28h+arg_0]
0x14002261f  mov     rsi, [rsp+28h+arg_8]
0x140022624  mov     byte ptr [rdi], 0
0x140022627  add     rsp, 20h
0x14002262b  pop     rdi
0x14002262c  retn
```
