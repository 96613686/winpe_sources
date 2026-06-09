# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x18003907c`
- end: `0x1800390ce`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180038eac`

## callees

- `0x18003907c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039085`

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
0x18003907c  push    rbx
0x18003907e  sub     rsp, 20h
0x180039082  mov     rbx, rcx
0x180039085  call    cs:__imp_GetCurrentThreadId
0x18003908b  mov     r9d, eax
0x18003908e  mov     ecx, eax
0x180039090  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18003909a  shr     r9, 2
0x18003909e  mul     r9
0x1800390a1  shr     rdx, 3
0x1800390a5  lea     r8, [rdx+rdx*4]
0x1800390a9  add     r8, r8
0x1800390ac  sub     r9, r8
0x1800390af  mov     rax, [rbx+r9*8]
0x1800390b3  test    rax, rax
0x1800390b6  jz      short loc_1800390C6
0x1800390b8  cmp     [rax], ecx
0x1800390ba  jz      short loc_1800390C2
0x1800390bc  mov     rax, [rax+8]
0x1800390c0  jmp     short loc_1800390B3
0x1800390c2  add     rax, 10h
0x1800390c6  add     rsp, 20h
0x1800390ca  pop     rbx
0x1800390cb  retn
0x1800390cc  jmp     short loc_1800390C6
```
