# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000210c`
- end: `0x18000215e`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `82`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001fe0`

## callees

- `0x18000210c`
- `0x180002164`
- `0x1800021c8`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rbx
  __int64 Shared; // rax
  __int64 v3; // rdi
  __int64 Local; // rax

  v1 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    Shared = wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(this);
    v3 = Shared;
    if ( Shared )
    {
      Local = wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(Shared + 8);
      v1 = Local;
      if ( Local )
      {
        if ( !*(_QWORD *)(Local + 8) )
          *(_QWORD *)(Local + 8) = v3 + 4;
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v1;
}

```

## disassembly

```asm
0x18000210c  mov     [rsp+arg_0], rbx
0x180002111  push    rdi
0x180002112  sub     rsp, 20h
0x180002116  xor     ebx, ebx
0x180002118  cmp     cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA, rbx; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000211f  jz      short loc_18000213F
0x180002121  call    ?GetShared@?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUProcessLocalData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData>::GetShared(void)
0x180002126  mov     rdi, rax
0x180002129  test    rax, rax
0x18000212c  jz      short loc_18000213F
0x18000212e  lea     rcx, [rax+8]
0x180002132  call    ?GetLocal@?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAAPEAUThreadLocalData@23@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::GetLocal(bool)
0x180002137  mov     rbx, rax
0x18000213a  test    rax, rax
0x18000213d  jnz     short loc_18000214D
0x18000213f  mov     rax, rbx
0x180002142  mov     rbx, [rsp+28h+arg_0]
0x180002147  add     rsp, 20h
0x18000214b  pop     rdi
0x18000214c  retn
0x18000214d  cmp     qword ptr [rax+8], 0
0x180002152  jnz     short loc_18000213F
0x180002154  lea     rcx, [rdi+4]
0x180002158  mov     [rax+8], rcx
0x18000215c  jmp     short loc_18000213F
```
