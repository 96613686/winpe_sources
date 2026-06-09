# CreateChildTable

- ea: `0x14001e67c`
- end: `0x14001e716`
- name: `CreateChildTable`
- size: `154`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c3d0`

## callees

- `0x14001e67c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001e699`
- `ntoskrnl!ExAllocatePool2` at `0x14001e699`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e6dc`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e6dc`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e6c0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e6c0`

## pseudocode

```c
__int64 __fastcall CreateChildTable(__int64 a1)
{
  __int64 Pool2; // rax
  __int64 v3; // rbx
  _OWORD *v4; // rax

  Pool2 = ExAllocatePool2(256, 32, 1717663052);
  v3 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_DWORD *)Pool2 = 24;
  *(_BYTE *)(Pool2 + 4) = -1;
  FltAcquirePushLockExclusiveEx(&PoolLock, 0);
  dword_14000ECBC += 24;
  FltReleasePushLockEx(&PoolLock, 0);
  v4 = (_OWORD *)(v3 + 8);
  if ( v3 == -8 )
    return 3221225626LL;
  *(_QWORD *)(a1 + 40) = v4;
  *v4 = 0;
  *(_QWORD *)(v3 + 24) = 0;
  return 0;
}

```

## disassembly

```asm
0x14001e67c  mov     [rsp+arg_0], rbx
0x14001e681  push    rdi
0x14001e682  sub     rsp, 20h
0x14001e686  mov     rdi, rcx
0x14001e689  mov     edx, 20h ; ' '
0x14001e68e  mov     ecx, 100h
0x14001e693  mov     r8d, 6661754Ch
0x14001e699  call    cs:__imp_ExAllocatePool2
0x14001e6a0  nop     dword ptr [rax+rax+00h]
0x14001e6a5  mov     rbx, rax
0x14001e6a8  test    rax, rax
0x14001e6ab  jz      short loc_14001E70F
0x14001e6ad  xor     edx, edx
0x14001e6af  mov     dword ptr [rax], 18h
0x14001e6b5  lea     rcx, PoolLock
0x14001e6bc  mov     byte ptr [rax+4], 0FFh
0x14001e6c0  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e6c7  nop     dword ptr [rax+rax+00h]
0x14001e6cc  add     cs:dword_14000ECBC, 18h
0x14001e6d3  lea     rcx, PoolLock
0x14001e6da  xor     edx, edx
0x14001e6dc  call    cs:__imp_FltReleasePushLockEx
0x14001e6e3  nop     dword ptr [rax+rax+00h]
0x14001e6e8  lea     rax, [rbx+8]
0x14001e6ec  test    rax, rax
0x14001e6ef  jz      short loc_14001E70F
0x14001e6f1  mov     [rdi+28h], rax
0x14001e6f5  xor     ecx, ecx
0x14001e6f7  xorps   xmm0, xmm0
0x14001e6fa  movups  xmmword ptr [rax], xmm0
0x14001e6fd  mov     [rax+10h], rcx
0x14001e701  xor     eax, eax
0x14001e703  mov     rbx, [rsp+28h+arg_0]
0x14001e708  add     rsp, 20h
0x14001e70c  pop     rdi
0x14001e70d  retn
0x14001e70f  mov     eax, 0C000009Ah
0x14001e714  jmp     short loc_14001E703
```
