# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18002a44c`
- end: `0x18002a49e`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a88c`

## callees

- `0x18002a44c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002a455`
- `KERNEL32!GetCurrentThreadId` at `0x18002a455`

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
0x18002a44c  push    rbx
0x18002a44e  sub     rsp, 20h
0x18002a452  mov     rbx, rcx
0x18002a455  call    cs:__imp_GetCurrentThreadId
0x18002a45b  mov     r9d, eax
0x18002a45e  mov     ecx, eax
0x18002a460  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002a46a  shr     r9, 2
0x18002a46e  mul     r9
0x18002a471  shr     rdx, 3
0x18002a475  lea     r8, [rdx+rdx*4]
0x18002a479  add     r8, r8
0x18002a47c  sub     r9, r8
0x18002a47f  mov     rax, [rbx+r9*8]
0x18002a483  jmp     short loc_18002A48D
0x18002a485  cmp     [rax], ecx
0x18002a487  jz      short loc_18002A498
0x18002a489  mov     rax, [rax+8]
0x18002a48d  test    rax, rax
0x18002a490  jnz     short loc_18002A485
0x18002a492  add     rsp, 20h
0x18002a496  pop     rbx
0x18002a497  retn
0x18002a498  add     rax, 10h
0x18002a49c  jmp     short loc_18002A492
```
