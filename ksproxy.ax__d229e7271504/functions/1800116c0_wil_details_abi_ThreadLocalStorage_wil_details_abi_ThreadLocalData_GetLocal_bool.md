# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800116c0`
- end: `0x180011719`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `89`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011608`

## callees

- `0x1800116c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800116c9`
- `KERNEL32!GetCurrentThreadId` at `0x1800116c9`

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
0x1800116c0  push    rbx
0x1800116c2  sub     rsp, 20h
0x1800116c6  mov     rbx, rcx
0x1800116c9  call    cs:__imp_GetCurrentThreadId
0x1800116d0  nop     dword ptr [rax+rax+00h]
0x1800116d5  mov     r9d, eax
0x1800116d8  mov     ecx, eax
0x1800116da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800116e4  shr     r9, 2
0x1800116e8  mul     r9
0x1800116eb  shr     rdx, 3
0x1800116ef  lea     r8, [rdx+rdx*4]
0x1800116f3  add     r8, r8
0x1800116f6  sub     r9, r8
0x1800116f9  mov     rax, [rbx+r9*8]
0x1800116fd  test    rax, rax
0x180011700  jz      short loc_180011710
0x180011702  cmp     [rax], ecx
0x180011704  jz      short loc_18001170C
0x180011706  mov     rax, [rax+8]
0x18001170a  jmp     short loc_1800116FD
0x18001170c  add     rax, 10h
0x180011710  add     rsp, 20h
0x180011714  pop     rbx
0x180011715  retn
0x180011717  jmp     short loc_180011710
```
