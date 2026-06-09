# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)

- ea: `0x180006200`
- end: `0x18000625f`
- name: `?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006138`

## callees

- `0x180006200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006209`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(__int64 a1)
{
  DWORD CurrentThreadId; // r9d
  __int64 i; // rcx

  CurrentThreadId = GetCurrentThreadId();
  for ( i = *(_QWORD *)(a1 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
  {
    if ( *(_DWORD *)i == CurrentThreadId )
      return i + 16;
  }
  return 0;
}

```

## disassembly

```asm
0x180006200  push    rbx
0x180006202  sub     rsp, 20h
0x180006206  mov     rbx, rcx
0x180006209  call    cs:__imp_GetCurrentThreadId
0x180006210  nop     dword ptr [rax+rax+00h]
0x180006215  mov     ecx, eax
0x180006217  shr     rcx, 2
0x18000621b  mov     r9d, eax
0x18000621e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006228  mul     rcx
0x18000622b  shr     rdx, 3
0x18000622f  lea     r8, [rdx+rdx*4]
0x180006233  add     r8, r8
0x180006236  sub     rcx, r8
0x180006239  mov     rcx, [rbx+rcx*8]
0x18000623d  nop     dword ptr [rax]
0x180006240  test    rcx, rcx
0x180006243  jz      short loc_18000625B
0x180006245  cmp     [rcx], r9d
0x180006248  jz      short loc_180006250
0x18000624a  mov     rcx, [rcx+8]
0x18000624e  jmp     short loc_180006240
0x180006250  lea     rax, [rcx+10h]
0x180006254  add     rsp, 20h
0x180006258  pop     rbx
0x180006259  retn
0x18000625b  xor     eax, eax
0x18000625d  jmp     short loc_180006254
```
