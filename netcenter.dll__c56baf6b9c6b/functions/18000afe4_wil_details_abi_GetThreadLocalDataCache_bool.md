# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x18000afe4`
- end: `0x18000b0a1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a620`

## callees

- `0x1800088d8`
- `0x18000afe4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b03e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b03e`

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
0x18000afe4  mov     [rsp+arg_0], rbx
0x18000afe9  push    rdi
0x18000afea  sub     rsp, 20h
0x18000afee  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x18000aff5  xor     ebx, ebx
0x18000aff7  test    rdi, rdi
0x18000affa  jz      loc_18000B093
0x18000b000  cmp     [rdi+8], rbx
0x18000b004  jnz     short loc_18000B02B
0x18000b006  mov     rcx, [rdi]
0x18000b009  lea     rdx, [rsp+28h+arg_8]
0x18000b00e  mov     [rsp+28h+arg_8], rbx
0x18000b013  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x18000b018  test    eax, eax
0x18000b01a  js      short loc_18000B02B
0x18000b01c  cmp     [rdi+8], rbx
0x18000b020  jnz     short loc_18000B02B
0x18000b022  mov     rax, [rsp+28h+arg_8]
0x18000b027  mov     [rdi+8], rax
0x18000b02b  mov     rax, [rdi+8]
0x18000b02f  lea     rcx, [rax+20h]
0x18000b033  neg     rax
0x18000b036  sbb     rdi, rdi
0x18000b039  and     rdi, rcx
0x18000b03c  jz      short loc_18000B093
0x18000b03e  call    cs:__imp_GetCurrentThreadId
0x18000b044  mov     r8d, eax
0x18000b047  mov     r9d, eax
0x18000b04a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b054  shr     r8, 2
0x18000b058  mul     r8
0x18000b05b  shr     rdx, 3
0x18000b05f  lea     rcx, [rdx+rdx*4]
0x18000b063  add     rcx, rcx
0x18000b066  sub     r8, rcx
0x18000b069  mov     rbx, [rdi+r8*8+8]
0x18000b06e  test    rbx, rbx
0x18000b071  jz      short loc_18000B093
0x18000b073  cmp     [rbx], r9d
0x18000b076  jz      short loc_18000B07E
0x18000b078  mov     rbx, [rbx+8]
0x18000b07c  jmp     short loc_18000B06E
0x18000b07e  add     rbx, 10h
0x18000b082  jz      short loc_18000B093
0x18000b084  cmp     qword ptr [rbx+8], 0
0x18000b089  jnz     short loc_18000B093
0x18000b08b  lea     rax, [rdi+4]
0x18000b08f  mov     [rbx+8], rax
0x18000b093  mov     rax, rbx
0x18000b096  mov     rbx, [rsp+28h+arg_0]
0x18000b09b  add     rsp, 20h
0x18000b09f  pop     rdi
0x18000b0a0  retn
```
