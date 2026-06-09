# CQueryCallback::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x140017640`
- end: `0x14001770a`
- name: `?QueryService@CQueryCallback@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(CQueryCallback *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140017640`
- `0x1400191ec`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400176db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400176db`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140017669`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140017669`

## pseudocode

```c
__int64 __fastcall CQueryCallback::QueryService(
        CQueryCallback *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  RTL_SRWLOCK *v4; // r14
  struct CAepStoreAccess *v6; // rdi
  unsigned int v9; // ebx
  int v10; // eax
  struct CAepStoreAccess *v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = (RTL_SRWLOCK *)((char *)this + 64);
  v6 = 0;
  v12 = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 8);
  if ( *((_DWORD *)this + 18) )
  {
    if ( a4 )
    {
      if ( *(_QWORD *)&GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1 == *(_QWORD *)&a3->Data1
        && *(_QWORD *)GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4 == *(_QWORD *)a3->Data4 )
      {
        v10 = CAepStoreAccess::Create(
                *((const unsigned __int16 **)this + 3),
                *((const unsigned __int16 **)this + 4),
                &v12);
        v6 = v12;
        v9 = v10;
        if ( v10 >= 0 )
          (**(void (__fastcall ***)(struct CAepStoreAccess *, const struct _GUID *, void **))v12)(v12, a3, a4);
      }
      else
      {
        v9 = -2147467262;
      }
    }
    else
    {
      v9 = -2147467261;
    }
  }
  else
  {
    v9 = -2140930029;
  }
  ReleaseSRWLockShared(v4);
  if ( v6 )
    (*(void (__fastcall **)(struct CAepStoreAccess *))(*(_QWORD *)v6 + 16LL))(v6);
  return v9;
}

```

## disassembly

```asm
0x140017640  mov     [rsp+arg_8], rbx
0x140017645  mov     [rsp+arg_10], rbp
0x14001764a  push    rsi
0x14001764b  push    rdi
0x14001764c  push    r14
0x14001764e  sub     rsp, 20h
0x140017652  lea     r14, [rcx+40h]
0x140017656  mov     rbx, rcx
0x140017659  xor     edi, edi
0x14001765b  mov     rcx, r14; SRWLock
0x14001765e  mov     rbp, r9
0x140017661  mov     [rsp+38h+arg_0], rdi
0x140017666  mov     rsi, r8
0x140017669  call    cs:__imp_AcquireSRWLockShared
0x14001766f  cmp     [rbx+48h], edi
0x140017672  jnz     short loc_14001767B
0x140017674  mov     ebx, 80640013h
0x140017679  jmp     short loc_1400176D8
0x14001767b  test    rbp, rbp
0x14001767e  jnz     short loc_140017687
0x140017680  mov     ebx, 80004003h
0x140017685  jmp     short loc_1400176D8
0x140017687  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1
0x14001768e  cmp     rax, [rsi]
0x140017691  jnz     short loc_1400176D3
0x140017693  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4
0x14001769a  cmp     rax, [rsi+8]
0x14001769e  jnz     short loc_1400176D3
0x1400176a0  mov     rdx, [rbx+20h]; unsigned __int16 *
0x1400176a4  lea     r8, [rsp+38h+arg_0]; struct CAepStoreAccess **
0x1400176a9  mov     rcx, [rbx+18h]; Src
0x1400176ad  call    ?Create@CAepStoreAccess@@SAJPEBG0PEAPEAV1@@Z; CAepStoreAccess::Create(ushort const *,ushort const *,CAepStoreAccess * *)
0x1400176b2  mov     rdi, [rsp+38h+arg_0]
0x1400176b7  mov     ebx, eax
0x1400176b9  test    eax, eax
0x1400176bb  js      short loc_1400176D8
0x1400176bd  mov     rcx, [rdi]
0x1400176c0  mov     r8, rbp
0x1400176c3  mov     rdx, rsi
0x1400176c6  mov     rax, [rcx]
0x1400176c9  mov     rcx, rdi
0x1400176cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400176d1  jmp     short loc_1400176D8
0x1400176d3  mov     ebx, 80004002h
0x1400176d8  mov     rcx, r14; SRWLock
0x1400176db  call    cs:__imp_ReleaseSRWLockShared
0x1400176e1  test    rdi, rdi
0x1400176e4  jz      short loc_1400176F5
0x1400176e6  mov     rax, [rdi]
0x1400176e9  mov     rcx, rdi
0x1400176ec  mov     rax, [rax+10h]
0x1400176f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400176f5  mov     rbp, [rsp+38h+arg_10]
0x1400176fa  mov     eax, ebx
0x1400176fc  mov     rbx, [rsp+38h+arg_8]
0x140017701  add     rsp, 20h
0x140017705  pop     r14
0x140017707  pop     rdi
0x140017708  pop     rsi
0x140017709  retn
```
