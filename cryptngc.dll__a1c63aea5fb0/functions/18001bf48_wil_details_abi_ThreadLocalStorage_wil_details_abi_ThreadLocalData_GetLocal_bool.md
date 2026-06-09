# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18001bf48`
- end: `0x18001bf98`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016450`

## callees

- `0x18001bf48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf51`

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
0x18001bf48  push    rbx
0x18001bf4a  sub     rsp, 20h
0x18001bf4e  mov     rbx, rcx
0x18001bf51  call    cs:__imp_GetCurrentThreadId
0x18001bf57  mov     r9d, eax
0x18001bf5a  mov     ecx, eax
0x18001bf5c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001bf66  shr     r9, 2
0x18001bf6a  mul     r9
0x18001bf6d  shr     rdx, 3
0x18001bf71  lea     r8, [rdx+rdx*4]
0x18001bf75  add     r8, r8
0x18001bf78  sub     r9, r8
0x18001bf7b  mov     rax, [rbx+r9*8]
0x18001bf7f  test    rax, rax
0x18001bf82  jz      short loc_18001BF92
0x18001bf84  cmp     [rax], ecx
0x18001bf86  jz      short loc_18001BF8E
0x18001bf88  mov     rax, [rax+8]
0x18001bf8c  jmp     short loc_18001BF7F
0x18001bf8e  add     rax, 10h
0x18001bf92  add     rsp, 20h
0x18001bf96  pop     rbx
0x18001bf97  retn
```
