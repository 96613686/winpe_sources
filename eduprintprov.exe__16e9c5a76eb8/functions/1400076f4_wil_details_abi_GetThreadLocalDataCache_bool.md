# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1400076f4`
- end: `0x1400077af`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `187`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006e70`

## callees

- `0x140005738`
- `0x1400076f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000774a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000774a`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 v1; // rdi
  __int64 i; // rbx
  __int64 v3; // rcx
  __int64 v4; // rdi
  DWORD CurrentThreadId; // r9d
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

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
0x1400076f4  mov     [rsp+arg_0], rbx
0x1400076f9  push    rdi
0x1400076fa  sub     rsp, 20h
0x1400076fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x140007705  xor     ebx, ebx
0x140007707  test    rdi, rdi
0x14000770a  jz      short loc_14000778A
0x14000770c  cmp     [rdi+8], rbx
0x140007710  jnz     short loc_140007737
0x140007712  mov     rcx, [rdi]
0x140007715  lea     rdx, [rsp+28h+arg_8]
0x14000771a  mov     [rsp+28h+arg_8], rbx
0x14000771f  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x140007724  test    eax, eax
0x140007726  js      short loc_140007737
0x140007728  cmp     [rdi+8], rbx
0x14000772c  jnz     short loc_140007737
0x14000772e  mov     rax, [rsp+28h+arg_8]
0x140007733  mov     [rdi+8], rax
0x140007737  mov     rax, [rdi+8]
0x14000773b  lea     rcx, [rax+20h]
0x14000773f  neg     rax
0x140007742  sbb     rdi, rdi
0x140007745  and     rdi, rcx
0x140007748  jz      short loc_14000778A
0x14000774a  call    cs:__imp_GetCurrentThreadId
0x140007750  mov     r8d, eax
0x140007753  mov     r9d, eax
0x140007756  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140007760  shr     r8, 2
0x140007764  mul     r8
0x140007767  shr     rdx, 3
0x14000776b  lea     rcx, [rdx+rdx*4]
0x14000776f  add     rcx, rcx
0x140007772  sub     r8, rcx
0x140007775  mov     rbx, [rdi+r8*8+8]
0x14000777a  jmp     short loc_140007785
0x14000777c  cmp     [rbx], r9d
0x14000777f  jz      short loc_140007798
0x140007781  mov     rbx, [rbx+8]
0x140007785  test    rbx, rbx
0x140007788  jnz     short loc_14000777C
0x14000778a  mov     rax, rbx
0x14000778d  mov     rbx, [rsp+28h+arg_0]
0x140007792  add     rsp, 20h
0x140007796  pop     rdi
0x140007797  retn
0x140007798  add     rbx, 10h
0x14000779c  jz      short loc_14000778A
0x14000779e  cmp     qword ptr [rbx+8], 0
0x1400077a3  jnz     short loc_14000778A
0x1400077a5  lea     rax, [rdi+4]
0x1400077a9  mov     [rbx+8], rax
0x1400077ad  jmp     short loc_14000778A
```
