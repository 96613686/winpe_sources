# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x180022010`
- end: `0x1800220cd`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021940`

## callees

- `0x18002104c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002206a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002206a`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  void *v7; // [rsp+38h] [rbp+10h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  i = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v3 = *(_QWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v3, &v7) >= 0
        && !*(_QWORD *)(v1 + 8) )
      {
        *(_QWORD *)(v1 + 8) = v7;
      }
    }
    v4 = (*(_QWORD *)(v1 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v1 + 8) != 0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v4 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          if ( i && !*(_QWORD *)(i + 8) )
            *(_QWORD *)(i + 8) = v4 + 4;
          return (struct wil::details_abi::ThreadLocalData *)i;
        }
      }
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x180022010  mov     [rsp+arg_0], rbx
0x180022015  push    rdi
0x180022016  sub     rsp, 20h
0x18002201a  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180022021  xor     ebx, ebx
0x180022023  test    rdi, rdi
0x180022026  jz      loc_1800220BF
0x18002202c  cmp     [rdi+8], rbx
0x180022030  jnz     short loc_180022057
0x180022032  mov     rcx, [rdi]
0x180022035  lea     rdx, [rsp+28h+arg_8]
0x18002203a  mov     [rsp+28h+arg_8], rbx
0x18002203f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180022044  test    eax, eax
0x180022046  js      short loc_180022057
0x180022048  cmp     [rdi+8], rbx
0x18002204c  jnz     short loc_180022057
0x18002204e  mov     rax, [rsp+28h+arg_8]
0x180022053  mov     [rdi+8], rax
0x180022057  mov     rax, [rdi+8]
0x18002205b  lea     rcx, [rax+20h]
0x18002205f  neg     rax
0x180022062  sbb     rdi, rdi
0x180022065  and     rdi, rcx
0x180022068  jz      short loc_1800220BF
0x18002206a  call    cs:__imp_GetCurrentThreadId
0x180022070  mov     r8d, eax
0x180022073  mov     r9d, eax
0x180022076  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180022080  shr     r8, 2
0x180022084  mul     r8
0x180022087  shr     rdx, 3
0x18002208b  lea     rcx, [rdx+rdx*4]
0x18002208f  add     rcx, rcx
0x180022092  sub     r8, rcx
0x180022095  mov     rbx, [rdi+r8*8+8]
0x18002209a  test    rbx, rbx
0x18002209d  jz      short loc_1800220BF
0x18002209f  cmp     [rbx], r9d
0x1800220a2  jz      short loc_1800220AA
0x1800220a4  mov     rbx, [rbx+8]
0x1800220a8  jmp     short loc_18002209A
0x1800220aa  add     rbx, 10h
0x1800220ae  jz      short loc_1800220BF
0x1800220b0  cmp     qword ptr [rbx+8], 0
0x1800220b5  jnz     short loc_1800220BF
0x1800220b7  lea     rax, [rdi+4]
0x1800220bb  mov     [rbx+8], rax
0x1800220bf  mov     rax, rbx
0x1800220c2  mov     rbx, [rsp+28h+arg_0]
0x1800220c7  add     rsp, 20h
0x1800220cb  pop     rdi
0x1800220cc  retn
```
