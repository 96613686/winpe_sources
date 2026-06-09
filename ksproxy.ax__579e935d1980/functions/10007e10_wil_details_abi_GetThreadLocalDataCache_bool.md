# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x10007e10`
- end: `0x10007e94`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YGPAUThreadLocalData@12@_N@Z`
- size: `132`
- prototype: `struct wil::details_abi::ThreadLocalData *(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10008050`

## callees

- `0x10007e10`
- `0x1000fa6a`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x10007e56`
- `KERNEL32!GetCurrentThreadId` at `0x10007e56`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *wil::details_abi::GetThreadLocalDataCache()
{
  int v0; // esi
  _DWORD *v1; // edi
  int v2; // ecx
  int v3; // esi
  DWORD CurrentThreadId; // ecx
  _DWORD *i; // edi
  int v7; // [esp+Ch] [ebp-4h] BYREF

  v0 = wil::details_abi::g_pProcessLocalData;
  v1 = 0;
  if ( wil::details_abi::g_pProcessLocalData )
  {
    if ( !*(_DWORD *)(wil::details_abi::g_pProcessLocalData + 4) )
    {
      v2 = *(_DWORD *)wil::details_abi::g_pProcessLocalData;
      v7 = 0;
      if ( wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(v2, &v7) >= 0
        && !*(_DWORD *)(v0 + 4) )
      {
        *(_DWORD *)(v0 + 4) = v7;
      }
    }
    v3 = *(_DWORD *)(v0 + 4) != 0 ? *(_DWORD *)(v0 + 4) + 16 : 0;
    if ( v3 )
    {
      CurrentThreadId = GetCurrentThreadId();
      for ( i = *(_DWORD **)(v3 + 4 * ((CurrentThreadId >> 2) % 0xA) + 8); ; i = (_DWORD *)i[1] )
      {
        if ( !i )
          return 0;
        if ( *i == CurrentThreadId )
          break;
      }
      v1 = i + 2;
      if ( v1 && !v1[2] )
        v1[2] = v3 + 4;
    }
  }
  return (struct wil::details_abi::ThreadLocalData *)v1;
}

```

## disassembly

```asm
0x10007e10  mov     edi, edi
0x10007e12  push    ebp
0x10007e13  mov     ebp, esp
0x10007e15  push    ecx
0x10007e16  push    ebx
0x10007e17  push    esi
0x10007e18  mov     esi, ?g_pProcessLocalData@details_abi@wil@@3PAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x10007e1e  xor     ebx, ebx
0x10007e20  push    edi
0x10007e21  mov     edi, ebx
0x10007e23  test    esi, esi
0x10007e25  jz      short loc_10007E7B
0x10007e27  cmp     [esi+4], ebx
0x10007e2a  jnz     short loc_10007E48
0x10007e2c  mov     ecx, [esi]
0x10007e2e  lea     edx, [ebp+var_4]
0x10007e31  mov     [ebp+var_4], ebx
0x10007e34  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x10007e39  test    eax, eax
0x10007e3b  js      short loc_10007E48
0x10007e3d  cmp     [esi+4], ebx
0x10007e40  jnz     short loc_10007E48
0x10007e42  mov     eax, [ebp+var_4]
0x10007e45  mov     [esi+4], eax
0x10007e48  mov     esi, [esi+4]
0x10007e4b  lea     eax, [esi+10h]
0x10007e4e  neg     esi
0x10007e50  sbb     esi, esi
0x10007e52  and     esi, eax
0x10007e54  jz      short loc_10007E7B
0x10007e56  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10007e5c  mov     ecx, eax
0x10007e5e  xor     edx, edx
0x10007e60  push    0Ah
0x10007e62  pop     edi
0x10007e63  shr     eax, 2
0x10007e66  div     edi
0x10007e68  mov     edi, [esi+edx*4+8]
0x10007e6c  jmp     short loc_10007E75
0x10007e6e  cmp     [edi], ecx
0x10007e70  jz      short loc_10007E82
0x10007e72  mov     edi, [edi+4]
0x10007e75  test    edi, edi
0x10007e77  jnz     short loc_10007E6E
0x10007e79  mov     edi, ebx
0x10007e7b  mov     eax, edi
0x10007e7d  pop     edi
0x10007e7e  pop     esi
0x10007e7f  pop     ebx
0x10007e80  leave
0x10007e81  retn
0x10007e82  add     edi, 8
0x10007e85  jz      short loc_10007E7B
0x10007e87  cmp     [edi+8], ebx
0x10007e8a  jnz     short loc_10007E7B
0x10007e8c  lea     eax, [esi+4]
0x10007e8f  mov     [edi+8], eax
0x10007e92  jmp     short loc_10007E7B
```
