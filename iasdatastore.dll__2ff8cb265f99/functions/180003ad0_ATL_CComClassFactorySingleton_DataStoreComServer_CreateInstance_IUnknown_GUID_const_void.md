# ATL::CComClassFactorySingleton<DataStoreComServer>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003ad0`
- end: `0x180003bc6`
- name: `?CreateInstance@?$CComClassFactorySingleton@VDataStoreComServer@@@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800021b4`
- `0x180003ad0`
- `0x180003f78`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x180003b87`
- `msvcrt!free` at `0x180003b87`
- `KERNEL32!EnterCriticalSection` at `0x180003b27`
- `KERNEL32!EnterCriticalSection` at `0x180003b27`
- `KERNEL32!LeaveCriticalSection` at `0x180003b92`
- `KERNEL32!LeaveCriticalSection` at `0x180003b92`
- `KERNEL32!LeaveCriticalSection` at `0x18000e1be`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactorySingleton<DataStoreComServer>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  _QWORD *v8; // rsi
  int Instance; // eax
  void *v10; // rdi
  int v11; // eax
  void *Block; // [rsp+68h] [rbp+20h] BYREF

  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return 2147746064LL;
    }
    else
    {
      if ( !*(_DWORD *)(a1 + 72) )
      {
        v8 = (_QWORD *)(a1 + 80);
        if ( !*(_QWORD *)(a1 + 80) )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
          if ( !*(_DWORD *)(a1 + 72) && !*v8 )
          {
            Block = 0;
            Instance = ATL::CComObjectCached<DataStoreComServer>::CreateInstance((DataStoreComServer **)&Block);
            *(_DWORD *)(a1 + 72) = Instance;
            if ( Instance >= 0 )
            {
              v10 = Block;
              v11 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))Block)(Block, &IID_IUnknown, v8);
              *(_DWORD *)(a1 + 72) = v11;
              if ( v11 < 0 )
              {
                if ( v10 )
                {
                  ATL::CComObjectCached<DataStoreComServer>::~CComObjectCached<DataStoreComServer>(v10);
                  free(v10);
                }
              }
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
        }
      }
      result = *(unsigned int *)(a1 + 72);
      if ( !(_DWORD)result )
        return (***(__int64 (__fastcall ****)(_QWORD, __int64, _QWORD *))(a1 + 80))(*(_QWORD *)(a1 + 80), a3, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003ad0  mov     [rsp+arg_8], rbx
0x180003ad5  mov     [rsp+arg_0], rcx
0x180003ada  push    rsi
0x180003adb  push    rdi
0x180003adc  push    r12
0x180003ade  push    r14
0x180003ae0  push    r15
0x180003ae2  sub     rsp, 20h
0x180003ae6  mov     r14, r9
0x180003ae9  mov     r12, r8
0x180003aec  mov     rbx, rcx
0x180003aef  mov     eax, 80004003h
0x180003af4  test    r9, r9
0x180003af7  jz      loc_180003BB4
0x180003afd  mov     qword ptr [r9], 0
0x180003b04  test    rdx, rdx
0x180003b07  jz      short loc_180003B13
0x180003b09  mov     eax, 80040110h
0x180003b0e  jmp     loc_180003BB4
0x180003b13  cmp     dword ptr [rcx+48h], 0
0x180003b17  jnz     short loc_180003B98
0x180003b19  lea     rsi, [rcx+50h]
0x180003b1d  cmp     qword ptr [rsi], 0
0x180003b21  jnz     short loc_180003B98
0x180003b23  add     rcx, 10h; lpCriticalSection
0x180003b27  call    cs:__imp_EnterCriticalSection
0x180003b2d  cmp     dword ptr [rbx+48h], 0
0x180003b31  jnz     short loc_180003B8E
0x180003b33  cmp     qword ptr [rsi], 0
0x180003b37  jnz     short loc_180003B8E
0x180003b39  mov     [rsp+48h+Block], 0
0x180003b42  lea     rcx, [rsp+48h+Block]
0x180003b47  call    ?CreateInstance@?$CComObjectCached@VDataStoreComServer@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObjectCached<DataStoreComServer>::CreateInstance(ATL::CComObjectCached<DataStoreComServer> * *)
0x180003b4c  mov     [rbx+48h], eax
0x180003b4f  test    eax, eax
0x180003b51  js      short loc_180003B8E
0x180003b53  mov     rdi, [rsp+48h+Block]
0x180003b58  mov     rax, [rdi]
0x180003b5b  mov     r8, rsi
0x180003b5e  lea     rdx, IID_IUnknown
0x180003b65  mov     rcx, rdi
0x180003b68  mov     rax, [rax]
0x180003b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b70  mov     [rbx+48h], eax
0x180003b73  test    eax, eax
0x180003b75  jns     short loc_180003B8E
0x180003b77  test    rdi, rdi
0x180003b7a  jz      short loc_180003B8E
0x180003b7c  mov     rcx, rdi
0x180003b7f  call    ??1?$CComObjectCached@VDataStoreComServer@@@ATL@@QEAA@XZ; ATL::CComObjectCached<DataStoreComServer>::~CComObjectCached<DataStoreComServer>(void)
0x180003b84  mov     rcx, rdi; Block
0x180003b87  call    cs:__imp_free
0x180003b8d  nop
0x180003b8e  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003b92  call    cs:__imp_LeaveCriticalSection
0x180003b98  mov     eax, [rbx+48h]
0x180003b9b  test    eax, eax
0x180003b9d  jnz     short loc_180003BB4
0x180003b9f  mov     rcx, [rbx+50h]
0x180003ba3  mov     rax, [rcx]
0x180003ba6  mov     r8, r14
0x180003ba9  mov     rdx, r12
0x180003bac  mov     rax, [rax]
0x180003baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bb4  mov     rbx, [rsp+48h+arg_8]
0x180003bb9  add     rsp, 20h
0x180003bbd  pop     r15
0x180003bbf  pop     r14
0x180003bc1  pop     r12
0x180003bc3  pop     rdi
0x180003bc4  pop     rsi
0x180003bc5  retn
0x18000e1a8  push    rbp
0x18000e1aa  sub     rsp, 20h
0x18000e1ae  mov     rbp, rdx
0x18000e1b1  mov     rcx, [rbp+50h]
0x18000e1b5  add     rcx, 10h
0x18000e1b9  add     rsp, 20h
0x18000e1bd  pop     rbp
0x18000e1be  jmp     cs:__imp_LeaveCriticalSection
```
