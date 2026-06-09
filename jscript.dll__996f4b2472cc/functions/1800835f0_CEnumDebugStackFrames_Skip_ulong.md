# CEnumDebugStackFrames::Skip(ulong)

- ea: `0x1800835f0`
- end: `0x180083634`
- name: `?Skip@CEnumDebugStackFrames@@UEAAJK@Z`
- size: `68`
- prototype: `__int64 __fastcall(CEnumDebugStackFrames *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800835f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180083607`
- `KERNEL32!GetCurrentThreadId` at `0x180083607`

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
0x1800835f0  mov     [rsp+arg_0], rbx
0x1800835f5  mov     [rsp+arg_8], rsi
0x1800835fa  push    rdi
0x1800835fb  sub     rsp, 20h
0x1800835ff  mov     ebx, [rcx+0Ch]
0x180083602  mov     esi, edx
0x180083604  mov     rdi, rcx
0x180083607  call    cs:__imp_GetCurrentThreadId
0x18008360e  nop     dword ptr [rax+rax+00h]
0x180083613  cmp     eax, ebx
0x180083615  jz      short loc_18008361E
0x180083617  mov     eax, 8000FFFFh
0x18008361c  jmp     short loc_180083623
0x18008361e  add     [rdi+18h], esi
0x180083621  xor     eax, eax
0x180083623  mov     rbx, [rsp+28h+arg_0]
0x180083628  mov     rsi, [rsp+28h+arg_8]
0x18008362d  add     rsp, 20h
0x180083631  pop     rdi
0x180083632  retn
```
