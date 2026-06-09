# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800064d8`
- end: `0x180006528`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000641c`

## callees

- `0x1800064d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064e1`

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
0x1800064d8  push    rbx
0x1800064da  sub     rsp, 20h
0x1800064de  mov     rbx, rcx
0x1800064e1  call    cs:__imp_GetCurrentThreadId
0x1800064e7  mov     r9d, eax
0x1800064ea  mov     ecx, eax
0x1800064ec  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800064f6  shr     r9, 2
0x1800064fa  mul     r9
0x1800064fd  shr     rdx, 3
0x180006501  lea     r8, [rdx+rdx*4]
0x180006505  add     r8, r8
0x180006508  sub     r9, r8
0x18000650b  mov     rax, [rbx+r9*8]
0x18000650f  test    rax, rax
0x180006512  jz      short loc_180006522
0x180006514  cmp     [rax], ecx
0x180006516  jz      short loc_18000651E
0x180006518  mov     rax, [rax+8]
0x18000651c  jmp     short loc_18000650F
0x18000651e  add     rax, 10h
0x180006522  add     rsp, 20h
0x180006526  pop     rbx
0x180006527  retn
```
