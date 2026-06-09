# ReleaseTempWindow

- ea: `0x140069350`
- end: `0x140069395`
- name: `ReleaseTempWindow`
- size: `69`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14005cbd8`
- `0x1400687ac`
- `0x140068cb4`
- `0x140068da0`

## callees

- `0x14004ecfc`
- `0x1400675a0`
- `0x140069350`

## pseudocode

```c
__int64 __fastcall ReleaseTempWindow(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL);
  ReleaseWindow();
  if ( *(int *)(v1 + 256) <= 0 )
    os_raise(0xFFFFFFFFLL, 0);
  v2 = *(int *)(v1 + 256);
  result = (unsigned int)(v2 - 1);
  *(_DWORD *)(v1 + 256) = result;
  *(_QWORD *)(v1 + 8 * v2 + 120) = 0;
  return result;
}

```

## disassembly

```asm
0x140069350  push    rbx
0x140069352  sub     rsp, 20h
0x140069356  mov     rax, [rcx+20h]
0x14006935a  mov     rbx, [rax+20h]
0x14006935e  call    ReleaseWindow
0x140069363  cmp     dword ptr [rbx+100h], 0
0x14006936a  jg      short loc_140069376
0x14006936c  xor     edx, edx
0x14006936e  or      ecx, 0FFFFFFFFh
0x140069371  call    os_raise
0x140069376  movsxd  rcx, dword ptr [rbx+100h]
0x14006937d  lea     eax, [rcx-1]
0x140069380  mov     [rbx+100h], eax
0x140069386  mov     qword ptr [rbx+rcx*8+78h], 0
0x14006938f  add     rsp, 20h
0x140069393  pop     rbx
0x140069394  retn
```
