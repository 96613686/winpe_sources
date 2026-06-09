# CEnumDebugStackFrames::Skip(ulong)

- ea: `0x180081a10`
- end: `0x180081a4d`
- name: `?Skip@CEnumDebugStackFrames@@UEAAJK@Z`
- size: `61`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180081a10`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180081a27`
- `KERNEL32!GetCurrentThreadId` at `0x180081a27`

## pseudocode

```c
__int64 __fastcall CEnumDebugStackFrames::Skip(CEnumDebugStackFrames *this, int a2)
{
  int v2; // ebx

  v2 = *((_DWORD *)this + 3);
  if ( GetCurrentThreadId() != v2 )
    return 2147549183LL;
  *((_DWORD *)this + 6) += a2;
  return 0;
}

```

## disassembly

```asm
0x180081a10  mov     [rsp+arg_0], rbx
0x180081a15  mov     [rsp+arg_8], rsi
0x180081a1a  push    rdi
0x180081a1b  sub     rsp, 20h
0x180081a1f  mov     ebx, [rcx+0Ch]
0x180081a22  mov     esi, edx
0x180081a24  mov     rdi, rcx
0x180081a27  call    cs:__imp_GetCurrentThreadId
0x180081a2d  cmp     eax, ebx
0x180081a2f  jz      short loc_180081A38
0x180081a31  mov     eax, 8000FFFFh
0x180081a36  jmp     short loc_180081A3D
0x180081a38  add     [rdi+18h], esi
0x180081a3b  xor     eax, eax
0x180081a3d  mov     rbx, [rsp+28h+arg_0]
0x180081a42  mov     rsi, [rsp+28h+arg_8]
0x180081a47  add     rsp, 20h
0x180081a4b  pop     rdi
0x180081a4c  retn
```
