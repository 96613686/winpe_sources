# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18000a3cc`
- end: `0x18000a41c`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a33c`

## callees

- `0x18000a3cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3d5`

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
0x18000a3cc  push    rbx
0x18000a3ce  sub     rsp, 20h
0x18000a3d2  mov     rbx, rcx
0x18000a3d5  call    cs:__imp_GetCurrentThreadId
0x18000a3db  mov     r9d, eax
0x18000a3de  mov     ecx, eax
0x18000a3e0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a3ea  shr     r9, 2
0x18000a3ee  mul     r9
0x18000a3f1  shr     rdx, 3
0x18000a3f5  lea     r8, [rdx+rdx*4]
0x18000a3f9  add     r8, r8
0x18000a3fc  sub     r9, r8
0x18000a3ff  mov     rax, [rbx+r9*8]
0x18000a403  test    rax, rax
0x18000a406  jz      short loc_18000A416
0x18000a408  cmp     [rax], ecx
0x18000a40a  jz      short loc_18000A412
0x18000a40c  mov     rax, [rax+8]
0x18000a410  jmp     short loc_18000A403
0x18000a412  add     rax, 10h
0x18000a416  add     rsp, 20h
0x18000a41a  pop     rbx
0x18000a41b  retn
```
