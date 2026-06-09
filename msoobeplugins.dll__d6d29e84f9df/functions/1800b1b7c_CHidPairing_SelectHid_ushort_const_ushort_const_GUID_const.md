# CHidPairing::_SelectHid(ushort const *,ushort const *,_GUID const &)

- ea: `0x1800b1b7c`
- end: `0x1800b1c83`
- name: `?_SelectHid@CHidPairing@@AEAAJPEBG0AEBU_GUID@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(CHidPairing *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800b1050`

## callees

- `0x18000ac48`
- `0x18000b358`
- `0x1800b1b7c`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b1c45`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b1c45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1bbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b1bbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1c59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1c0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1bd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b1c0b`

## pseudocode

```c
__int64 __fastcall CHidPairing::_SelectHid(
        CHidPairing *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  int Error; // ebx
  __int64 v9; // rdx
  void *v10; // rcx
  size_t v11; // rsi
  size_t v12; // r9
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  __int64 v16; // [rsp+20h] [rbp-58h]
  __int64 v17; // [rsp+20h] [rbp-58h]

  Error = 0;
  UnattendLogW(0, L"CHidPairing::_SelectHid - Entering: %ws, %ws", a2, a3);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 6);
  if ( !*((_BYTE *)this + 83) )
  {
    v10 = (void *)*((_QWORD *)this + 13);
    if ( v10 )
      CoTaskMemFree(v10);
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( a2[v12] );
    Error = _AllocStringWorker<CTCoAllocPolicy>((unsigned __int64)v10, v9, a2, v12, v16, (void **)this + 13);
    if ( Error >= 0 )
    {
      CoTaskMemFree(*((LPVOID *)this + 14));
      do
        ++v11;
      while ( a3[v11] );
      Error = _AllocStringWorker<CTCoAllocPolicy>(v14, v13, a3, v11, v17, (void **)this + 14);
      if ( Error >= 0 )
        *((struct _GUID *)this + 26) = *a4;
      if ( !SetEvent(*((HANDLE *)this + 38)) )
        Error = ResultFromKnownLastError();
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 6);
  UnattendLogW(0, L"CHidPairing::_SelectHid - Leaving: hr=0x%08X", (unsigned int)Error);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800b1b7c  push    rbx
0x1800b1b7e  push    rbp
0x1800b1b7f  push    rsi
0x1800b1b80  push    rdi
0x1800b1b81  push    r12
0x1800b1b83  push    r13
0x1800b1b85  push    r14
0x1800b1b87  push    r15
0x1800b1b89  sub     rsp, 38h
0x1800b1b8d  mov     r12, r9
0x1800b1b90  mov     r14, r8
0x1800b1b93  mov     r9, r8
0x1800b1b96  mov     rbp, rdx
0x1800b1b99  mov     r8, rdx
0x1800b1b9c  mov     rdi, rcx
0x1800b1b9f  xor     r13d, r13d
0x1800b1ba2  lea     rdx, aChidpairingSel; "CHidPairing::_SelectHid - Entering: %ws"...
0x1800b1ba9  xor     ecx, ecx
0x1800b1bab  mov     ebx, r13d
0x1800b1bae  call    UnattendLogW
0x1800b1bb3  lea     r15, [rdi+0F0h]
0x1800b1bba  mov     rcx, r15; lpCriticalSection
0x1800b1bbd  call    cs:__imp_EnterCriticalSection
0x1800b1bc3  cmp     [rdi+53h], r13b
0x1800b1bc7  jnz     loc_1800B1C56
0x1800b1bcd  lea     rbx, [rdi+68h]
0x1800b1bd1  mov     rcx, [rbx]; pv
0x1800b1bd4  test    rcx, rcx
0x1800b1bd7  jz      short loc_1800B1BDF
0x1800b1bd9  call    cs:__imp_CoTaskMemFree
0x1800b1bdf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b1be3  mov     r9, rsi
0x1800b1be6  inc     r9
0x1800b1be9  cmp     [rbp+r9*2+0], r13w
0x1800b1bef  jnz     short loc_1800B1BE6
0x1800b1bf1  mov     r8, rbp
0x1800b1bf4  mov     [rsp+78h+var_50], rbx
0x1800b1bf9  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800b1bfe  mov     ebx, eax
0x1800b1c00  test    eax, eax
0x1800b1c02  js      short loc_1800B1C56
0x1800b1c04  lea     rbx, [rdi+70h]
0x1800b1c08  mov     rcx, [rbx]; pv
0x1800b1c0b  call    cs:__imp_CoTaskMemFree
0x1800b1c11  inc     rsi
0x1800b1c14  cmp     [r14+rsi*2], r13w
0x1800b1c19  jnz     short loc_1800B1C11
0x1800b1c1b  mov     r9, rsi
0x1800b1c1e  mov     [rsp+78h+var_50], rbx
0x1800b1c23  mov     r8, r14
0x1800b1c26  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800b1c2b  mov     ebx, eax
0x1800b1c2d  test    eax, eax
0x1800b1c2f  js      short loc_1800B1C3E
0x1800b1c31  movups  xmm0, xmmword ptr [r12]
0x1800b1c36  movdqu  xmmword ptr [rdi+1A0h], xmm0
0x1800b1c3e  mov     rcx, [rdi+130h]; hEvent
0x1800b1c45  call    cs:__imp_SetEvent
0x1800b1c4b  test    eax, eax
0x1800b1c4d  jnz     short loc_1800B1C56
0x1800b1c4f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800b1c54  mov     ebx, eax
0x1800b1c56  mov     rcx, r15; lpCriticalSection
0x1800b1c59  call    cs:__imp_LeaveCriticalSection
0x1800b1c5f  mov     r8d, ebx
0x1800b1c62  lea     rdx, aChidpairingSel_0; "CHidPairing::_SelectHid - Leaving: hr=0"...
0x1800b1c69  xor     ecx, ecx
0x1800b1c6b  call    UnattendLogW
0x1800b1c70  mov     eax, ebx
0x1800b1c72  add     rsp, 38h
0x1800b1c76  pop     r15
0x1800b1c78  pop     r14
0x1800b1c7a  pop     r13
0x1800b1c7c  pop     r12
0x1800b1c7e  pop     rdi
0x1800b1c7f  pop     rsi
0x1800b1c80  pop     rbp
0x1800b1c81  pop     rbx
0x1800b1c82  retn
```
