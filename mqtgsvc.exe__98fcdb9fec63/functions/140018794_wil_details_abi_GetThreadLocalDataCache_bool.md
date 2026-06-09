# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x140018794`
- end: `0x140018854`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z`
- size: `192`
- prototype: `struct wil::details_abi::ThreadLocalData *__fastcall(wil::details_abi *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140018150`

## callees

- `0x1400176a8`
- `0x140018794`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400187ee`
- `KERNEL32!GetCurrentThreadId` at `0x1400187ee`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__fastcall wil::details_abi::GetThreadLocalDataCache(wil::details_abi *this)
{
  __int64 i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // r9d
  void *v6; // [rsp+38h] [rbp+10h] BYREF

  i = 0;
  v2 = wil::details_abi::g_pProcessLocalData;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_QWORD *)(wil::details_abi::g_pProcessLocalData + 8) )
    {
      v6 = 0;
      if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                  *(_QWORD *)wil::details_abi::g_pProcessLocalData,
                  &v6) >= 0
        && !*(_QWORD *)(v2 + 8) )
      {
        *(_QWORD *)(v2 + 8) = v6;
      }
    }
    v3 = (*(_QWORD *)(v2 + 8) + 32LL) & -(__int64)(*(_QWORD *)(v2 + 8) != 0);
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_QWORD *)(v3 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA) + 8); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          i += 16;
          break;
        }
      }
      if ( i && !*(_QWORD *)(i + 8) )
        *(_QWORD *)(i + 8) = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)i;
}

```

## disassembly

```asm
0x140018794  mov     [rsp+arg_0], rbx
0x140018799  push    rdi
0x14001879a  sub     rsp, 20h
0x14001879e  xor     ebx, ebx
0x1400187a0  mov     rdi, cs:?g_pProcessLocalData@details_abi@wil@@3PEAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@EA; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1400187a7  test    rdi, rdi
0x1400187aa  jz      loc_140018846
0x1400187b0  cmp     [rdi+8], rbx
0x1400187b4  jnz     short loc_1400187DB
0x1400187b6  mov     [rsp+28h+arg_8], rbx
0x1400187bb  lea     rdx, [rsp+28h+arg_8]
0x1400187c0  mov     rcx, [rdi]
0x1400187c3  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1400187c8  test    eax, eax
0x1400187ca  js      short loc_1400187DB
0x1400187cc  cmp     [rdi+8], rbx
0x1400187d0  jnz     short loc_1400187DB
0x1400187d2  mov     rax, [rsp+28h+arg_8]
0x1400187d7  mov     [rdi+8], rax
0x1400187db  mov     rcx, [rdi+8]
0x1400187df  lea     rax, [rcx+20h]
0x1400187e3  neg     rcx
0x1400187e6  sbb     rdi, rdi
0x1400187e9  and     rdi, rax
0x1400187ec  jz      short loc_140018846
0x1400187ee  call    cs:__imp_GetCurrentThreadId
0x1400187f4  mov     r9d, eax
0x1400187f7  mov     r8d, eax
0x1400187fa  shr     r8, 2
0x1400187fe  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140018808  mul     r8
0x14001880b  shr     rdx, 3
0x14001880f  lea     rcx, [rdx+rdx*4]
0x140018813  add     rcx, rcx
0x140018816  sub     r8, rcx
0x140018819  mov     rbx, [rdi+r8*8+8]
0x14001881e  test    rbx, rbx
0x140018821  jz      short loc_140018832
0x140018823  cmp     [rbx], r9d
0x140018826  jz      short loc_14001882E
0x140018828  mov     rbx, [rbx+8]
0x14001882c  jmp     short loc_14001881E
0x14001882e  add     rbx, 10h
0x140018832  test    rbx, rbx
0x140018835  jz      short loc_140018846
0x140018837  cmp     qword ptr [rbx+8], 0
0x14001883c  jnz     short loc_140018846
0x14001883e  lea     rcx, [rdi+4]
0x140018842  mov     [rbx+8], rcx
0x140018846  mov     rax, rbx
0x140018849  mov     rbx, [rsp+28h+arg_0]
0x14001884e  add     rsp, 20h
0x140018852  pop     rdi
0x140018853  retn
```
