# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18000457c`
- end: `0x1800045ce`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000488c`

## callees

- `0x18000457c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004585`
- `KERNEL32!GetCurrentThreadId` at `0x180004585`

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
0x18000457c  push    rbx
0x18000457e  sub     rsp, 20h
0x180004582  mov     rbx, rcx
0x180004585  call    cs:__imp_GetCurrentThreadId
0x18000458b  mov     r9d, eax
0x18000458e  mov     ecx, eax
0x180004590  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000459a  shr     r9, 2
0x18000459e  mul     r9
0x1800045a1  shr     rdx, 3
0x1800045a5  lea     r8, [rdx+rdx*4]
0x1800045a9  add     r8, r8
0x1800045ac  sub     r9, r8
0x1800045af  mov     rax, [rbx+r9*8]
0x1800045b3  jmp     short loc_1800045BD
0x1800045b5  cmp     [rax], ecx
0x1800045b7  jz      short loc_1800045C8
0x1800045b9  mov     rax, [rax+8]
0x1800045bd  test    rax, rax
0x1800045c0  jnz     short loc_1800045B5
0x1800045c2  add     rsp, 20h
0x1800045c6  pop     rbx
0x1800045c7  retn
0x1800045c8  add     rax, 10h
0x1800045cc  jmp     short loc_1800045C2
```
