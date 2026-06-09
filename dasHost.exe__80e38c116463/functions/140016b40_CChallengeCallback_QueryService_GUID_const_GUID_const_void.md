# CChallengeCallback::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x140016b40`
- end: `0x140016c0b`
- name: `?QueryService@CChallengeCallback@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `203`
- prototype: `__int64 __fastcall(CChallengeCallback *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140016b40`
- `0x1400191ec`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016bdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016bdc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016b69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016b69`

## pseudocode

```c
__int64 __fastcall CChallengeCallback::QueryService(
        CChallengeCallback *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  struct CAepStoreAccess *v6; // rdi
  unsigned int v9; // ebx
  int v10; // eax
  struct CAepStoreAccess *v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  v6 = 0;
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( *((_QWORD *)this + 4) )
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
  LeaveCriticalSection(v4);
  if ( v6 )
    (*(void (__fastcall **)(struct CAepStoreAccess *))(*(_QWORD *)v6 + 16LL))(v6);
  return v9;
}

```

## disassembly

```asm
0x140016b40  mov     [rsp+arg_8], rbx
0x140016b45  mov     [rsp+arg_10], rbp
0x140016b4a  push    rsi
0x140016b4b  push    rdi
0x140016b4c  push    r14
0x140016b4e  sub     rsp, 20h
0x140016b52  lea     r14, [rcx+28h]
0x140016b56  mov     rbx, rcx
0x140016b59  xor     edi, edi
0x140016b5b  mov     rcx, r14; lpCriticalSection
0x140016b5e  mov     rbp, r9
0x140016b61  mov     [rsp+38h+arg_0], rdi
0x140016b66  mov     rsi, r8
0x140016b69  call    cs:__imp_EnterCriticalSection
0x140016b6f  cmp     [rbx+20h], rdi
0x140016b73  jnz     short loc_140016B7C
0x140016b75  mov     ebx, 80640013h
0x140016b7a  jmp     short loc_140016BD9
0x140016b7c  test    rbp, rbp
0x140016b7f  jnz     short loc_140016B88
0x140016b81  mov     ebx, 80004003h
0x140016b86  jmp     short loc_140016BD9
0x140016b88  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1
0x140016b8f  cmp     rax, [rsi]
0x140016b92  jnz     short loc_140016BD4
0x140016b94  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4
0x140016b9b  cmp     rax, [rsi+8]
0x140016b9f  jnz     short loc_140016BD4
0x140016ba1  mov     rdx, [rbx+18h]; unsigned __int16 *
0x140016ba5  lea     r8, [rsp+38h+arg_0]; struct CAepStoreAccess **
0x140016baa  mov     rcx, [rbx+10h]; Src
0x140016bae  call    ?Create@CAepStoreAccess@@SAJPEBG0PEAPEAV1@@Z; CAepStoreAccess::Create(ushort const *,ushort const *,CAepStoreAccess * *)
0x140016bb3  mov     rdi, [rsp+38h+arg_0]
0x140016bb8  mov     ebx, eax
0x140016bba  test    eax, eax
0x140016bbc  js      short loc_140016BD9
0x140016bbe  mov     rcx, [rdi]
0x140016bc1  mov     r8, rbp
0x140016bc4  mov     rdx, rsi
0x140016bc7  mov     rax, [rcx]
0x140016bca  mov     rcx, rdi
0x140016bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016bd2  jmp     short loc_140016BD9
0x140016bd4  mov     ebx, 80004002h
0x140016bd9  mov     rcx, r14; lpCriticalSection
0x140016bdc  call    cs:__imp_LeaveCriticalSection
0x140016be2  test    rdi, rdi
0x140016be5  jz      short loc_140016BF6
0x140016be7  mov     rax, [rdi]
0x140016bea  mov     rcx, rdi
0x140016bed  mov     rax, [rax+10h]
0x140016bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016bf6  mov     rbp, [rsp+38h+arg_10]
0x140016bfb  mov     eax, ebx
0x140016bfd  mov     rbx, [rsp+38h+arg_8]
0x140016c02  add     rsp, 20h
0x140016c06  pop     r14
0x140016c08  pop     rdi
0x140016c09  pop     rsi
0x140016c0a  retn
```
