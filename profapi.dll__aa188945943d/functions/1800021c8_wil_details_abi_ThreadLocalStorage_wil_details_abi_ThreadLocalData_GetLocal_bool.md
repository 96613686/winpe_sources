# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800021c8`
- end: `0x18000221a`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000210c`

## callees

- `0x1800021c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021d1`

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
0x1800021c8  push    rbx
0x1800021ca  sub     rsp, 20h
0x1800021ce  mov     rbx, rcx
0x1800021d1  call    cs:__imp_GetCurrentThreadId
0x1800021d7  mov     r9d, eax
0x1800021da  mov     ecx, eax
0x1800021dc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800021e6  shr     r9, 2
0x1800021ea  mul     r9
0x1800021ed  shr     rdx, 3
0x1800021f1  lea     r8, [rdx+rdx*4]
0x1800021f5  add     r8, r8
0x1800021f8  sub     r9, r8
0x1800021fb  mov     rax, [rbx+r9*8]
0x1800021ff  test    rax, rax
0x180002202  jz      short loc_180002212
0x180002204  cmp     [rax], ecx
0x180002206  jz      short loc_18000220E
0x180002208  mov     rax, [rax+8]
0x18000220c  jmp     short loc_1800021FF
0x18000220e  add     rax, 10h
0x180002212  add     rsp, 20h
0x180002216  pop     rbx
0x180002217  retn
0x180002218  jmp     short loc_180002212
```
