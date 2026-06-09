# CreateChildTable

- ea: `0x14001e6cc`
- end: `0x14001e766`
- name: `CreateChildTable`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c420`

## callees

- `0x14001e6cc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001e6e9`
- `ntoskrnl!ExAllocatePool2` at `0x14001e6e9`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e72c`
- `FLTMGR!FltReleasePushLockEx` at `0x14001e72c`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e710`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001e710`

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
  dword_14000F2FC += 24;
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
0x14001e6cc  mov     [rsp+arg_0], rbx
0x14001e6d1  push    rdi
0x14001e6d2  sub     rsp, 20h
0x14001e6d6  mov     rdi, rcx
0x14001e6d9  mov     edx, 20h ; ' '
0x14001e6de  mov     ecx, 100h
0x14001e6e3  mov     r8d, 6661754Ch
0x14001e6e9  call    cs:__imp_ExAllocatePool2
0x14001e6f0  nop     dword ptr [rax+rax+00h]
0x14001e6f5  mov     rbx, rax
0x14001e6f8  test    rax, rax
0x14001e6fb  jz      short loc_14001E75F
0x14001e6fd  xor     edx, edx
0x14001e6ff  mov     dword ptr [rax], 18h
0x14001e705  lea     rcx, PoolLock
0x14001e70c  mov     byte ptr [rax+4], 0FFh
0x14001e710  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001e717  nop     dword ptr [rax+rax+00h]
0x14001e71c  add     cs:dword_14000F2FC, 18h
0x14001e723  lea     rcx, PoolLock
0x14001e72a  xor     edx, edx
0x14001e72c  call    cs:__imp_FltReleasePushLockEx
0x14001e733  nop     dword ptr [rax+rax+00h]
0x14001e738  lea     rax, [rbx+8]
0x14001e73c  test    rax, rax
0x14001e73f  jz      short loc_14001E75F
0x14001e741  mov     [rdi+28h], rax
0x14001e745  xor     ecx, ecx
0x14001e747  xorps   xmm0, xmm0
0x14001e74a  movups  xmmword ptr [rax], xmm0
0x14001e74d  mov     [rax+10h], rcx
0x14001e751  xor     eax, eax
0x14001e753  mov     rbx, [rsp+28h+arg_0]
0x14001e758  add     rsp, 20h
0x14001e75c  pop     rdi
0x14001e75d  retn
0x14001e75f  mov     eax, 0C000009Ah
0x14001e764  jmp     short loc_14001E753
```
