# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800242e8`
- end: `0x18002433a`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024510`

## callees

- `0x1800242e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242f1`

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
0x1800242e8  push    rbx
0x1800242ea  sub     rsp, 20h
0x1800242ee  mov     rbx, rcx
0x1800242f1  call    cs:__imp_GetCurrentThreadId
0x1800242f7  mov     ecx, eax
0x1800242f9  mov     r9d, eax
0x1800242fc  shr     r9, 2
0x180024300  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002430a  mul     r9
0x18002430d  shr     rdx, 3
0x180024311  lea     r8, [rdx+rdx*4]
0x180024315  add     r8, r8
0x180024318  sub     r9, r8
0x18002431b  mov     rax, [rbx+r9*8]
0x18002431f  jmp     short loc_180024329
0x180024321  cmp     [rax], ecx
0x180024323  jz      short loc_180024334
0x180024325  mov     rax, [rax+8]
0x180024329  test    rax, rax
0x18002432c  jnz     short loc_180024321
0x18002432e  add     rsp, 20h
0x180024332  pop     rbx
0x180024333  retn
0x180024334  add     rax, 10h
0x180024338  jmp     short loc_18002432E
```
