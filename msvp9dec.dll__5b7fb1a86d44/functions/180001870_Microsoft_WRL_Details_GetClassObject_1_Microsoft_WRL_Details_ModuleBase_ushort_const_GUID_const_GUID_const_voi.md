# Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)

- ea: `0x180001870`
- end: `0x180001a84`
- name: `??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z`
- size: `532`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID Ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002160`

## callees

- `0x180001870`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000193f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180001a1c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000193f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180001a1c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180001a0d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180001a0d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800019f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800019f0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000192d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000192d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000196e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800019c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000196e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800019c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001a3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001a3c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetClassObject<1>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *Ptr)
{
  _QWORD *v5; // rsi
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  _QWORD *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rbx
  RTL_SRWLOCK *v14; // rbp
  void *v15; // rcx
  int v16; // edi
  RTL_SRWLOCK *v18; // rbp
  void *v19; // rcx
  PVOID v20; // rdi
  __int64 v21; // [rsp+68h] [rbp+10h] BYREF

  v21 = a2;
  v5 = Ptr;
  *Ptr = 0;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1) + 8;
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  while ( v9 < v10 )
  {
    if ( *(_QWORD *)v9 )
    {
      v11 = *(_QWORD **)(*(_QWORD *)v9 + 8LL);
      v12 = *v11 - *a3;
      if ( *v11 == *a3 )
        v12 = v11[1] - a3[1];
      if ( !v12 )
      {
        _mm_lfence();
        v13 = *(_QWORD *)v9;
        LODWORD(v21) = 1;
        *v5 = 0;
        Ptr = 0;
        if ( **(_QWORD **)(v13 + 24) )
        {
          v14 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
          AcquireSRWLockShared(v14);
          v15 = **(void ***)(v13 + 24);
          if ( v15 )
          {
            Ptr = DecodePointer(v15);
            v16 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*Ptr)(Ptr, a4, v5);
            if ( v14 )
              ReleaseSRWLockShared(v14);
            return (unsigned int)v16;
          }
          if ( v14 )
            ReleaseSRWLockShared(v14);
        }
        v16 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD **))v13)(&v21, v13, a4, &Ptr);
        if ( v16 >= 0 )
        {
          if ( (v21 & 4) != 0 )
            goto LABEL_25;
          v18 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1);
          AcquireSRWLockExclusive(v18);
          v19 = **(void ***)(v13 + 24);
          if ( v19 )
          {
            v20 = DecodePointer(v19);
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v20 + 8LL))(v20);
          }
          else
          {
            v20 = 0;
            **(_QWORD **)(v13 + 24) = EncodePointer(Ptr);
          }
          if ( v18 )
            ReleaseSRWLockExclusive(v18);
          if ( !v20 )
          {
LABEL_25:
            v20 = Ptr;
          }
          else
          {
            (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
            (*(void (__fastcall **)(_QWORD *))(*Ptr + 16LL))(Ptr);
          }
          *v5 = v20;
          return 0;
        }
        return (unsigned int)v16;
      }
    }
    v9 += 8LL;
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x180001870  mov     [rsp+arg_10], rbx
0x180001875  mov     [rsp+arg_8], rdx
0x18000187a  push    rsi
0x18000187b  push    rdi
0x18000187c  push    r12
0x18000187e  push    r14
0x180001880  push    r15
0x180001882  sub     rsp, 30h
0x180001886  mov     rsi, [rsp+58h+Ptr]
0x18000188e  xor     r12d, r12d
0x180001891  mov     r15, r9
0x180001894  mov     rdi, r8
0x180001897  mov     r14, rcx
0x18000189a  mov     [rsi], r12
0x18000189d  mov     rax, [rcx]
0x1800018a0  mov     rax, [rax+20h]
0x1800018a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018a9  mov     rdx, [r14]
0x1800018ac  mov     rcx, r14
0x1800018af  lea     rbx, [rax+8]
0x1800018b3  mov     rax, [rdx+28h]
0x1800018b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018bc  cmp     rbx, rax
0x1800018bf  jnb     loc_1800019C9
0x1800018c5  mov     rcx, [rbx]
0x1800018c8  test    rcx, rcx
0x1800018cb  jz      loc_1800019B0
0x1800018d1  mov     rdx, [rcx+8]
0x1800018d5  mov     rcx, [rdx]
0x1800018d8  sub     rcx, [rdi]
0x1800018db  jnz     short loc_1800018E5
0x1800018dd  mov     rcx, [rdx+8]
0x1800018e1  sub     rcx, [rdi+8]
0x1800018e5  test    rcx, rcx
0x1800018e8  jnz     loc_1800019B0
0x1800018ee  mov     [rsp+58h+arg_0], rbp
0x1800018f3  lfence
0x1800018f6  mov     rbx, [rbx]
0x1800018f9  mov     dword ptr [rsp+58h+arg_8], 1
0x180001901  mov     [rsi], r12
0x180001904  mov     [rsp+58h+Ptr], r12
0x18000190c  mov     rax, [rbx+18h]
0x180001910  mov     rcx, [rax]
0x180001913  test    rcx, rcx
0x180001916  jz      short loc_180001976
0x180001918  mov     rax, [r14]
0x18000191b  mov     rcx, r14
0x18000191e  mov     rax, [rax+38h]
0x180001922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001927  mov     rcx, rax; SRWLock
0x18000192a  mov     rbp, rax
0x18000192d  call    cs:__imp_AcquireSRWLockShared
0x180001933  mov     rcx, [rbx+18h]
0x180001937  mov     rcx, [rcx]; Ptr
0x18000193a  test    rcx, rcx
0x18000193d  jz      short loc_1800019B9
0x18000193f  call    cs:__imp_DecodePointer
0x180001945  mov     [rsp+58h+Ptr], rax
0x18000194d  mov     r8, rsi
0x180001950  mov     r9, rax
0x180001953  mov     rdx, r15
0x180001956  mov     rcx, [rax]
0x180001959  mov     rax, [rcx]
0x18000195c  mov     rcx, r9
0x18000195f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001964  mov     edi, eax
0x180001966  test    rbp, rbp
0x180001969  jz      short loc_180001997
0x18000196b  mov     rcx, rbp; SRWLock
0x18000196e  call    cs:__imp_ReleaseSRWLockShared
0x180001974  jmp     short loc_180001997
0x180001976  mov     rax, [rbx]
0x180001979  lea     r9, [rsp+58h+Ptr]
0x180001981  mov     r8, r15
0x180001984  lea     rcx, [rsp+58h+arg_8]
0x180001989  mov     rdx, rbx
0x18000198c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001991  mov     edi, eax
0x180001993  test    eax, eax
0x180001995  jns     short loc_1800019D0
0x180001997  mov     rbp, [rsp+58h+arg_0]
0x18000199c  mov     eax, edi
0x18000199e  mov     rbx, [rsp+58h+arg_10]
0x1800019a3  add     rsp, 30h
0x1800019a7  pop     r15
0x1800019a9  pop     r14
0x1800019ab  pop     r12
0x1800019ad  pop     rdi
0x1800019ae  pop     rsi
0x1800019af  retn
0x1800019b0  add     rbx, 8
0x1800019b4  jmp     loc_1800018BC
0x1800019b9  test    rbp, rbp
0x1800019bc  jz      short loc_180001976
0x1800019be  mov     rcx, rbp; SRWLock
0x1800019c1  call    cs:__imp_ReleaseSRWLockShared
0x1800019c7  jmp     short loc_180001976
0x1800019c9  mov     eax, 80040111h
0x1800019ce  jmp     short loc_18000199E
0x1800019d0  test    byte ptr [rsp+58h+arg_8], 4
0x1800019d5  jnz     loc_180001A71
0x1800019db  mov     rax, [r14]
0x1800019de  mov     rcx, r14
0x1800019e1  mov     rax, [rax+38h]
0x1800019e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019ea  mov     rcx, rax; SRWLock
0x1800019ed  mov     rbp, rax
0x1800019f0  call    cs:__imp_AcquireSRWLockExclusive
0x1800019f6  mov     rcx, [rbx+18h]
0x1800019fa  mov     rcx, [rcx]; Ptr
0x1800019fd  test    rcx, rcx
0x180001a00  jnz     short loc_180001A1C
0x180001a02  mov     rcx, [rsp+58h+Ptr]; Ptr
0x180001a0a  mov     rdi, r12
0x180001a0d  call    cs:__imp_EncodePointer
0x180001a13  mov     rcx, [rbx+18h]
0x180001a17  mov     [rcx], rax
0x180001a1a  jmp     short loc_180001A34
0x180001a1c  call    cs:__imp_DecodePointer
0x180001a22  mov     rdi, rax
0x180001a25  mov     rcx, [rax]
0x180001a28  mov     rax, [rcx+8]
0x180001a2c  mov     rcx, rdi
0x180001a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a34  test    rbp, rbp
0x180001a37  jz      short loc_180001A42
0x180001a39  mov     rcx, rbp; SRWLock
0x180001a3c  call    cs:__imp_ReleaseSRWLockExclusive
0x180001a42  test    rdi, rdi
0x180001a45  jz      short loc_180001A71
0x180001a47  mov     rcx, [rsp+58h+Ptr]
0x180001a4f  mov     rax, [rcx]
0x180001a52  mov     rax, [rax+10h]
0x180001a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a5b  mov     rcx, [rsp+58h+Ptr]
0x180001a63  mov     rax, [rcx]
0x180001a66  mov     rax, [rax+10h]
0x180001a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a6f  jmp     short loc_180001A79
0x180001a71  mov     rdi, [rsp+58h+Ptr]
0x180001a79  mov     [rsi], rdi
0x180001a7c  mov     edi, r12d
0x180001a7f  jmp     loc_180001997
```
