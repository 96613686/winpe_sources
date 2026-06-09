# wil::details_abi::GetThreadLocalDataCache(bool)

- ea: `0x1000a550`
- end: `0x1000a5e0`
- name: `?GetThreadLocalDataCache@details_abi@wil@@YGPAUThreadLocalData@12@_N@Z`
- size: `144`
- prototype: `struct wil::details_abi::ThreadLocalData *(wil::details_abi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1000a6c0`

## callees

- `0x1000a550`
- `0x1000eef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000a597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1000a597`

## pseudocode

```c
struct wil::details_abi::ThreadLocalData *__usercall wil::details_abi::GetThreadLocalDataCache@<eax>(void *a1@<ebx>)
{
  int v1; // esi
  int v2; // ecx
  int v3; // esi
  DWORD CurrentThreadId; // ecx
  _DWORD *v5; // eax
  int v7; // [esp+4h] [ebp-4h] BYREF

  v1 = wil::details_abi::g_pProcessLocalData;
  if ( !wil::details_abi::g_pProcessLocalData )
    return 0;
  if ( !*(_DWORD *)(wil::details_abi::g_pProcessLocalData + 4) )
  {
    v2 = *(_DWORD *)wil::details_abi::g_pProcessLocalData;
    v7 = 0;
    if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
                (char *)&v7,
                v2,
                a1) >= 0
      && !*(_DWORD *)(v1 + 4) )
    {
      *(_DWORD *)(v1 + 4) = v7;
    }
  }
  v3 = *(_DWORD *)(v1 + 4) != 0 ? *(_DWORD *)(v1 + 4) + 16 : 0;
  if ( !v3 )
    return 0;
  CurrentThreadId = GetCurrentThreadId();
  v5 = *(_DWORD **)(v3 + 4 * ((CurrentThreadId >> 2) % 0xA) + 8);
  if ( !v5 )
    return 0;
  while ( *v5 != CurrentThreadId )
  {
    v5 = (_DWORD *)v5[1];
    if ( !v5 )
      return 0;
  }
  if ( v5 != (_DWORD *)-8 && !v5[4] )
    v5[4] = v3 + 4;
  return (struct wil::details_abi::ThreadLocalData *)(v5 + 2);
}

```

## disassembly

```asm
0x1000a550  mov     edi, edi
0x1000a552  push    ebp
0x1000a553  mov     ebp, esp
0x1000a555  push    ecx
0x1000a556  push    esi
0x1000a557  mov     esi, ?g_pProcessLocalData@details_abi@wil@@3PAV?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@12@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> * wil::details_abi::g_pProcessLocalData
0x1000a55d  test    esi, esi
0x1000a55f  jz      short loc_1000A5BF
0x1000a561  cmp     dword ptr [esi+4], 0
0x1000a565  jnz     short loc_1000A588
0x1000a567  mov     ecx, [esi]
0x1000a569  lea     edx, [ebp+var_4]
0x1000a56c  mov     [ebp+var_4], 0
0x1000a573  call    ?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SGJPBDPAPAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)
0x1000a578  test    eax, eax
0x1000a57a  js      short loc_1000A588
0x1000a57c  cmp     dword ptr [esi+4], 0
0x1000a580  jnz     short loc_1000A588
0x1000a582  mov     eax, [ebp+var_4]
0x1000a585  mov     [esi+4], eax
0x1000a588  mov     esi, [esi+4]
0x1000a58b  lea     eax, [esi+10h]
0x1000a58e  neg     esi
0x1000a590  sbb     esi, esi
0x1000a592  and     esi, eax
0x1000a594  jz      short loc_1000A5BF
0x1000a596  push    edi
0x1000a597  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1000a59d  mov     ecx, eax
0x1000a59f  xor     edx, edx
0x1000a5a1  shr     eax, 2
0x1000a5a4  mov     edi, 0Ah
0x1000a5a9  div     edi
0x1000a5ab  pop     edi
0x1000a5ac  mov     eax, [esi+edx*4+8]
0x1000a5b0  test    eax, eax
0x1000a5b2  jz      short loc_1000A5BF
0x1000a5b4  cmp     [eax], ecx
0x1000a5b6  jz      short loc_1000A5C6
0x1000a5b8  mov     eax, [eax+4]
0x1000a5bb  test    eax, eax
0x1000a5bd  jnz     short loc_1000A5B4
0x1000a5bf  xor     eax, eax
0x1000a5c1  pop     esi
0x1000a5c2  mov     esp, ebp
0x1000a5c4  pop     ebp
0x1000a5c5  retn
0x1000a5c6  lea     ecx, [eax+8]
0x1000a5c9  test    ecx, ecx
0x1000a5cb  jz      short loc_1000A5D9
0x1000a5cd  cmp     dword ptr [ecx+8], 0
0x1000a5d1  jnz     short loc_1000A5D9
0x1000a5d3  lea     eax, [esi+4]
0x1000a5d6  mov     [ecx+8], eax
0x1000a5d9  mov     eax, ecx
0x1000a5db  pop     esi
0x1000a5dc  mov     esp, ebp
0x1000a5de  pop     ebp
0x1000a5df  retn
```
