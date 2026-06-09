# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1800335f4`
- end: `0x1800336b1`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `189`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180032ef0`

## callees

- `0x1800325fc`
- `0x1800335f4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003364e`
- `KERNEL32!GetCurrentThreadId` at `0x18003364e`

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
0x1800335f4  mov     [rsp+arg_0], rbx
0x1800335f9  push    rdi
0x1800335fa  sub     rsp, 20h
0x1800335fe  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x180033605  xor     ebx, ebx
0x180033607  test    rdi, rdi
0x18003360a  jz      loc_1800336A3
0x180033610  cmp     [rdi+8], rbx
0x180033614  jnz     short loc_18003363B
0x180033616  mov     rcx, [rdi]
0x180033619  lea     rdx, [rsp+28h+arg_8]
0x18003361e  mov     [rsp+28h+arg_8], rbx
0x180033623  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x180033628  test    eax, eax
0x18003362a  js      short loc_18003363B
0x18003362c  cmp     [rdi+8], rbx
0x180033630  jnz     short loc_18003363B
0x180033632  mov     rax, [rsp+28h+arg_8]
0x180033637  mov     [rdi+8], rax
0x18003363b  mov     rax, [rdi+8]
0x18003363f  lea     rcx, [rax+20h]
0x180033643  neg     rax
0x180033646  sbb     rdi, rdi
0x180033649  and     rdi, rcx
0x18003364c  jz      short loc_1800336A3
0x18003364e  call    cs:__imp_GetCurrentThreadId
0x180033654  mov     r8d, eax
0x180033657  mov     r9d, eax
0x18003365a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180033664  shr     r8, 2
0x180033668  mul     r8
0x18003366b  shr     rdx, 3
0x18003366f  lea     rcx, [rdx+rdx*4]
0x180033673  add     rcx, rcx
0x180033676  sub     r8, rcx
0x180033679  mov     rbx, [rdi+r8*8+8]
0x18003367e  test    rbx, rbx
0x180033681  jz      short loc_1800336A3
0x180033683  cmp     [rbx], r9d
0x180033686  jz      short loc_18003368E
0x180033688  mov     rbx, [rbx+8]
0x18003368c  jmp     short loc_18003367E
0x18003368e  add     rbx, 10h
0x180033692  jz      short loc_1800336A3
0x180033694  cmp     qword ptr [rbx+8], 0
0x180033699  jnz     short loc_1800336A3
0x18003369b  lea     rax, [rdi+4]
0x18003369f  mov     [rbx+8], rax
0x1800336a3  mov     rax, rbx
0x1800336a6  mov     rbx, [rsp+28h+arg_0]
0x1800336ab  add     rsp, 20h
0x1800336af  pop     rdi
0x1800336b0  retn
```
