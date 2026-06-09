# CDevnodeManagementCallback::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x140018e20`
- end: `0x140018eea`
- name: `?QueryService@CDevnodeManagementCallback@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(CDevnodeManagementCallback *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140018e20`
- `0x1400191ec`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018ebb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140018ebb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018e49`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140018e49`

## pseudocode

```c
__int64 __fastcall CDevnodeManagementCallback::QueryService(
        CDevnodeManagementCallback *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  RTL_SRWLOCK *v4; // r14
  struct CAepStoreAccess *v6; // rdi
  unsigned int v9; // ebx
  int v10; // eax
  struct CAepStoreAccess *v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = (RTL_SRWLOCK *)((char *)this + 40);
  v6 = 0;
  v12 = 0;
  AcquireSRWLockShared((PSRWLOCK)this + 5);
  if ( *((_DWORD *)this + 12) )
  {
    if ( a4 )
    {
      if ( *(_QWORD *)&GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1 == *(_QWORD *)&a3->Data1
        && *(_QWORD *)GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4 == *(_QWORD *)a3->Data4 )
      {
        v10 = CAepStoreAccess::Create(
                *((const unsigned __int16 **)this + 2),
                *((const unsigned __int16 **)this + 3),
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
0x140018e20  mov     [rsp+arg_8], rbx
0x140018e25  mov     [rsp+arg_10], rbp
0x140018e2a  push    rsi
0x140018e2b  push    rdi
0x140018e2c  push    r14
0x140018e2e  sub     rsp, 20h
0x140018e32  lea     r14, [rcx+28h]
0x140018e36  mov     rbx, rcx
0x140018e39  xor     edi, edi
0x140018e3b  mov     rcx, r14; SRWLock
0x140018e3e  mov     rbp, r9
0x140018e41  mov     [rsp+38h+arg_0], rdi
0x140018e46  mov     rsi, r8
0x140018e49  call    cs:__imp_AcquireSRWLockShared
0x140018e4f  cmp     [rbx+30h], edi
0x140018e52  jnz     short loc_140018E5B
0x140018e54  mov     ebx, 80640013h
0x140018e59  jmp     short loc_140018EB8
0x140018e5b  test    rbp, rbp
0x140018e5e  jnz     short loc_140018E67
0x140018e60  mov     ebx, 80004003h
0x140018e65  jmp     short loc_140018EB8
0x140018e67  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1
0x140018e6e  cmp     rax, [rsi]
0x140018e71  jnz     short loc_140018EB3
0x140018e73  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4
0x140018e7a  cmp     rax, [rsi+8]
0x140018e7e  jnz     short loc_140018EB3
0x140018e80  mov     rdx, [rbx+18h]; unsigned __int16 *
0x140018e84  lea     r8, [rsp+38h+arg_0]; struct CAepStoreAccess **
0x140018e89  mov     rcx, [rbx+10h]; Src
0x140018e8d  call    ?Create@CAepStoreAccess@@SAJPEBG0PEAPEAV1@@Z; CAepStoreAccess::Create(ushort const *,ushort const *,CAepStoreAccess * *)
0x140018e92  mov     rdi, [rsp+38h+arg_0]
0x140018e97  mov     ebx, eax
0x140018e99  test    eax, eax
0x140018e9b  js      short loc_140018EB8
0x140018e9d  mov     rcx, [rdi]
0x140018ea0  mov     r8, rbp
0x140018ea3  mov     rdx, rsi
0x140018ea6  mov     rax, [rcx]
0x140018ea9  mov     rcx, rdi
0x140018eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018eb1  jmp     short loc_140018EB8
0x140018eb3  mov     ebx, 80004002h
0x140018eb8  mov     rcx, r14; SRWLock
0x140018ebb  call    cs:__imp_ReleaseSRWLockShared
0x140018ec1  test    rdi, rdi
0x140018ec4  jz      short loc_140018ED5
0x140018ec6  mov     rax, [rdi]
0x140018ec9  mov     rcx, rdi
0x140018ecc  mov     rax, [rax+10h]
0x140018ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018ed5  mov     rbp, [rsp+38h+arg_10]
0x140018eda  mov     eax, ebx
0x140018edc  mov     rbx, [rsp+38h+arg_8]
0x140018ee1  add     rsp, 20h
0x140018ee5  pop     r14
0x140018ee7  pop     rdi
0x140018ee8  pop     rsi
0x140018ee9  retn
```
