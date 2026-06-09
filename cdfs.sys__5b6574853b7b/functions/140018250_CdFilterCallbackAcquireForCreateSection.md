# CdFilterCallbackAcquireForCreateSection

- ea: `0x140018250`
- end: `0x1400182af`
- name: `CdFilterCallbackAcquireForCreateSection`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140018272`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140018272`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140018288`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x140018288`

## pseudocode

```c
__int64 __fastcall CdFilterCallbackAcquireForCreateSection(__int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 16);
  ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v1 + 24) + 200LL) + 32LL), 1u);
  ExAcquireSharedStarveExclusive(*(PERESOURCE *)(*(_QWORD *)(v1 + 24) + 8LL), 1u);
  result = 298;
  if ( *(_DWORD *)(a1 + 24) != 1 )
    return 294;
  return result;
}

```

## disassembly

```asm
0x140018250  mov     [rsp+arg_0], rbx
0x140018255  push    rdi
0x140018256  sub     rsp, 20h
0x14001825a  mov     rbx, [rcx+10h]
0x14001825e  mov     rdi, rcx
0x140018261  mov     dl, 1; Wait
0x140018263  mov     rax, [rbx+18h]
0x140018267  mov     rcx, [rax+0C8h]
0x14001826e  add     rcx, 20h ; ' '; Resource
0x140018272  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140018279  nop     dword ptr [rax+rax+00h]
0x14001827e  mov     rcx, [rbx+18h]
0x140018282  mov     dl, 1; Wait
0x140018284  mov     rcx, [rcx+8]; Resource
0x140018288  call    cs:__imp_ExAcquireSharedStarveExclusive
0x14001828f  nop     dword ptr [rax+rax+00h]
0x140018294  cmp     dword ptr [rdi+18h], 1
0x140018298  mov     eax, 12Ah
0x14001829d  mov     rbx, [rsp+28h+arg_0]
0x1400182a2  lea     ecx, [rax-4]
0x1400182a5  cmovnz  eax, ecx
0x1400182a8  add     rsp, 20h
0x1400182ac  pop     rdi
0x1400182ad  retn
```
