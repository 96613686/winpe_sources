# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800797fc`
- end: `0x180079855`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180079b98`

## callees

- `0x1800797fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180079805`
- `KERNEL32!GetCurrentThreadId` at `0x180079805`

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
0x1800797fc  push    rbx
0x1800797fe  sub     rsp, 20h
0x180079802  mov     rbx, rcx
0x180079805  call    cs:__imp_GetCurrentThreadId
0x18007980c  nop     dword ptr [rax+rax+00h]
0x180079811  mov     r9d, eax
0x180079814  mov     ecx, eax
0x180079816  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180079820  shr     r9, 2
0x180079824  mul     r9
0x180079827  shr     rdx, 3
0x18007982b  lea     r8, [rdx+rdx*4]
0x18007982f  add     r8, r8
0x180079832  sub     r9, r8
0x180079835  mov     rax, [rbx+r9*8]
0x180079839  jmp     short loc_180079843
0x18007983b  cmp     [rax], ecx
0x18007983d  jz      short loc_18007984F
0x18007983f  mov     rax, [rax+8]
0x180079843  test    rax, rax
0x180079846  jnz     short loc_18007983B
0x180079848  add     rsp, 20h
0x18007984c  pop     rbx
0x18007984d  retn
0x18007984f  add     rax, 10h
0x180079853  jmp     short loc_180079848
```
