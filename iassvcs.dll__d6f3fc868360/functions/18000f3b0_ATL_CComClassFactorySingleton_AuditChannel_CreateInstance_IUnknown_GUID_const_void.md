# ATL::CComClassFactorySingleton<AuditChannel>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000f3b0`
- end: `0x18000f4a6`
- name: `?CreateInstance@?$CComClassFactorySingleton@VAuditChannel@@@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `246`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d718`
- `0x18000f3b0`
- `0x18000fbec`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x18000f467`
- `msvcrt!free` at `0x18000f467`
- `KERNEL32!EnterCriticalSection` at `0x18000f407`
- `KERNEL32!EnterCriticalSection` at `0x18000f407`
- `KERNEL32!LeaveCriticalSection` at `0x18000f472`
- `KERNEL32!LeaveCriticalSection` at `0x18000f472`
- `KERNEL32!LeaveCriticalSection` at `0x1800188b8`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactorySingleton<AuditChannel>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  _QWORD *v8; // rsi
  int v9; // eax
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
            v9 = ATL::CComObjectCached<AuditChannel>::CreateInstance(&Block);
            *(_DWORD *)(a1 + 72) = v9;
            if ( v9 >= 0 )
            {
              v10 = Block;
              v11 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))Block)(Block, &IID_IUnknown, v8);
              *(_DWORD *)(a1 + 72) = v11;
              if ( v11 < 0 )
              {
                if ( v10 )
                {
                  ATL::CComObjectCached<AuditChannel>::~CComObjectCached<AuditChannel>((__int64)v10);
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
0x18000f3b0  mov     [rsp+arg_8], rbx
0x18000f3b5  mov     [rsp+arg_0], rcx
0x18000f3ba  push    rsi
0x18000f3bb  push    rdi
0x18000f3bc  push    r12
0x18000f3be  push    r14
0x18000f3c0  push    r15
0x18000f3c2  sub     rsp, 20h
0x18000f3c6  mov     r14, r9
0x18000f3c9  mov     r12, r8
0x18000f3cc  mov     rbx, rcx
0x18000f3cf  mov     eax, 80004003h
0x18000f3d4  test    r9, r9
0x18000f3d7  jz      loc_18000F494
0x18000f3dd  mov     qword ptr [r9], 0
0x18000f3e4  test    rdx, rdx
0x18000f3e7  jz      short loc_18000F3F3
0x18000f3e9  mov     eax, 80040110h
0x18000f3ee  jmp     loc_18000F494
0x18000f3f3  cmp     dword ptr [rcx+48h], 0
0x18000f3f7  jnz     short loc_18000F478
0x18000f3f9  lea     rsi, [rcx+50h]
0x18000f3fd  cmp     qword ptr [rsi], 0
0x18000f401  jnz     short loc_18000F478
0x18000f403  add     rcx, 10h; lpCriticalSection
0x18000f407  call    cs:__imp_EnterCriticalSection
0x18000f40d  cmp     dword ptr [rbx+48h], 0
0x18000f411  jnz     short loc_18000F46E
0x18000f413  cmp     qword ptr [rsi], 0
0x18000f417  jnz     short loc_18000F46E
0x18000f419  mov     [rsp+48h+Block], 0
0x18000f422  lea     rcx, [rsp+48h+Block]
0x18000f427  call    ?CreateInstance@?$CComObjectCached@VAuditChannel@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObjectCached<AuditChannel>::CreateInstance(ATL::CComObjectCached<AuditChannel> * *)
0x18000f42c  mov     [rbx+48h], eax
0x18000f42f  test    eax, eax
0x18000f431  js      short loc_18000F46E
0x18000f433  mov     rdi, [rsp+48h+Block]
0x18000f438  mov     rax, [rdi]
0x18000f43b  mov     r8, rsi
0x18000f43e  lea     rdx, IID_IUnknown
0x18000f445  mov     rcx, rdi
0x18000f448  mov     rax, [rax]
0x18000f44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f450  mov     [rbx+48h], eax
0x18000f453  test    eax, eax
0x18000f455  jns     short loc_18000F46E
0x18000f457  test    rdi, rdi
0x18000f45a  jz      short loc_18000F46E
0x18000f45c  mov     rcx, rdi
0x18000f45f  call    ??1?$CComObjectCached@VAuditChannel@@@ATL@@QEAA@XZ; ATL::CComObjectCached<AuditChannel>::~CComObjectCached<AuditChannel>(void)
0x18000f464  mov     rcx, rdi; Block
0x18000f467  call    cs:__imp_free
0x18000f46d  nop
0x18000f46e  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000f472  call    cs:__imp_LeaveCriticalSection
0x18000f478  mov     eax, [rbx+48h]
0x18000f47b  test    eax, eax
0x18000f47d  jnz     short loc_18000F494
0x18000f47f  mov     rcx, [rbx+50h]
0x18000f483  mov     rax, [rcx]
0x18000f486  mov     r8, r14
0x18000f489  mov     rdx, r12
0x18000f48c  mov     rax, [rax]
0x18000f48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f494  mov     rbx, [rsp+48h+arg_8]
0x18000f499  add     rsp, 20h
0x18000f49d  pop     r15
0x18000f49f  pop     r14
0x18000f4a1  pop     r12
0x18000f4a3  pop     rdi
0x18000f4a4  pop     rsi
0x18000f4a5  retn
0x1800188a2  push    rbp
0x1800188a4  sub     rsp, 20h
0x1800188a8  mov     rbp, rdx
0x1800188ab  mov     rcx, [rbp+50h]
0x1800188af  add     rcx, 10h
0x1800188b3  add     rsp, 20h
0x1800188b7  pop     rbp
0x1800188b8  jmp     cs:__imp_LeaveCriticalSection
```
