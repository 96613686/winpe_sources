# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800091a4`
- end: `0x180009261`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008aa0`

## callees

- `0x1800080dc`
- `0x1800091a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800091fe`

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
0x1800091a4  mov     [rsp+arg_0], rbx
0x1800091a9  push    rdi
0x1800091aa  sub     rsp, 20h
0x1800091ae  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1800091b5  xor     ebx, ebx
0x1800091b7  test    rdi, rdi
0x1800091ba  jz      loc_180009253
0x1800091c0  cmp     [rdi+8], rbx
0x1800091c4  jnz     short loc_1800091EB
0x1800091c6  mov     rcx, [rdi]
0x1800091c9  lea     rdx, [rsp+28h+arg_8]
0x1800091ce  mov     [rsp+28h+arg_8], rbx
0x1800091d3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1800091d8  test    eax, eax
0x1800091da  js      short loc_1800091EB
0x1800091dc  cmp     [rdi+8], rbx
0x1800091e0  jnz     short loc_1800091EB
0x1800091e2  mov     rax, [rsp+28h+arg_8]
0x1800091e7  mov     [rdi+8], rax
0x1800091eb  mov     rax, [rdi+8]
0x1800091ef  lea     rcx, [rax+20h]
0x1800091f3  neg     rax
0x1800091f6  sbb     rdi, rdi
0x1800091f9  and     rdi, rcx
0x1800091fc  jz      short loc_180009253
0x1800091fe  call    cs:__imp_GetCurrentThreadId
0x180009204  mov     r8d, eax
0x180009207  mov     r9d, eax
0x18000920a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009214  shr     r8, 2
0x180009218  mul     r8
0x18000921b  shr     rdx, 3
0x18000921f  lea     rcx, [rdx+rdx*4]
0x180009223  add     rcx, rcx
0x180009226  sub     r8, rcx
0x180009229  mov     rbx, [rdi+r8*8+8]
0x18000922e  test    rbx, rbx
0x180009231  jz      short loc_180009253
0x180009233  cmp     [rbx], r9d
0x180009236  jz      short loc_18000923E
0x180009238  mov     rbx, [rbx+8]
0x18000923c  jmp     short loc_18000922E
0x18000923e  add     rbx, 10h
0x180009242  jz      short loc_180009253
0x180009244  cmp     qword ptr [rbx+8], 0
0x180009249  jnz     short loc_180009253
0x18000924b  lea     rax, [rdi+4]
0x18000924f  mov     [rbx+8], rax
0x180009253  mov     rax, rbx
0x180009256  mov     rbx, [rsp+28h+arg_0]
0x18000925b  add     rsp, 20h
0x18000925f  pop     rdi
0x180009260  retn
```
