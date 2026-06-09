# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x1800111c8`
- end: `0x18001121a`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800113fc`

## callees

- `0x1800111c8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800111d1`
- `KERNEL32!GetCurrentThreadId` at `0x1800111d1`

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
0x1800111c8  push    rbx
0x1800111ca  sub     rsp, 20h
0x1800111ce  mov     rbx, rcx
0x1800111d1  call    cs:__imp_GetCurrentThreadId
0x1800111d7  mov     r9d, eax
0x1800111da  mov     ecx, eax
0x1800111dc  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800111e6  shr     r9, 2
0x1800111ea  mul     r9
0x1800111ed  shr     rdx, 3
0x1800111f1  lea     r8, [rdx+rdx*4]
0x1800111f5  add     r8, r8
0x1800111f8  sub     r9, r8
0x1800111fb  mov     rax, [rbx+r9*8]
0x1800111ff  jmp     short loc_180011209
0x180011201  cmp     [rax], ecx
0x180011203  jz      short loc_180011214
0x180011205  mov     rax, [rax+8]
0x180011209  test    rax, rax
0x18001120c  jnz     short loc_180011201
0x18001120e  add     rsp, 20h
0x180011212  pop     rbx
0x180011213  retn
0x180011214  add     rax, 10h
0x180011218  jmp     short loc_18001120E
```
