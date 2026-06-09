# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x180006eec`
- end: `0x180006f3e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800071ec`

## callees

- `0x180006eec`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006ef5`
- `KERNEL32!GetCurrentThreadId` at `0x180006ef5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(__int64 a1)
{
  DWORD CurrentThreadId; // ecx
  __int64 result; // rax

  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(a1 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
        result;
        result = *(_QWORD *)(result + 8) )
  {
    if ( *(_DWORD *)result == CurrentThreadId )
    {
      result += 16;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006eec  push    rbx
0x180006eee  sub     rsp, 20h
0x180006ef2  mov     rbx, rcx
0x180006ef5  call    cs:__imp_GetCurrentThreadId
0x180006efb  mov     ecx, eax
0x180006efd  mov     r9d, eax
0x180006f00  shr     r9, 2
0x180006f04  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006f0e  mul     r9
0x180006f11  shr     rdx, 3
0x180006f15  lea     r8, [rdx+rdx*4]
0x180006f19  add     r8, r8
0x180006f1c  sub     r9, r8
0x180006f1f  mov     rax, [rbx+r9*8]
0x180006f23  jmp     short loc_180006F2D
0x180006f25  cmp     [rax], ecx
0x180006f27  jz      short loc_180006F38
0x180006f29  mov     rax, [rax+8]
0x180006f2d  test    rax, rax
0x180006f30  jnz     short loc_180006F25
0x180006f32  add     rsp, 20h
0x180006f36  pop     rbx
0x180006f37  retn
0x180006f38  add     rax, 10h
0x180006f3c  jmp     short loc_180006F32
```
