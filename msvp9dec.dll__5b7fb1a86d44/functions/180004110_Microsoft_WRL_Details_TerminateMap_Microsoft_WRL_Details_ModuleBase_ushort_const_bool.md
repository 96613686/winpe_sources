# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180004110`
- end: `0x18000423e`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `302`
- prototype: `bool __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001150`
- `0x1800039a0`

## callees

- `0x180003f50`
- `0x180004110`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800041f2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800041f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800041c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800041e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800041c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800041e0`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::TerminateMap(
        Microsoft::WRL::Details *this,
        RTL_SRWLOCK *a2,
        const unsigned __int16 *a3)
{
  char v3; // bp
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r14
  __int64 v7; // rax
  void **v8; // rcx
  void *v9; // rsi
  PVOID v10; // rax
  PSRWLOCK SRWLock; // [rsp+48h] [rbp+10h] BYREF

  SRWLock = a2;
  v3 = (char)a3;
  v5 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 32LL))(this) + 8;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
  while ( v5 < v6 )
  {
    if ( *(_QWORD *)v5 )
    {
      if ( (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) && !v3 )
        return 0;
      if ( **(_QWORD **)(*(_QWORD *)v5 + 24LL) )
      {
        v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, v7);
        v8 = *(void ***)(*(_QWORD *)v5 + 24LL);
        v9 = *v8;
        if ( *v8 )
        {
          *v8 = 0;
          if ( SRWLock )
          {
            ReleaseSRWLockExclusive(SRWLock);
            SRWLock = 0;
          }
          v10 = DecodePointer(v9);
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v10 + 16LL))(v10);
        }
        else if ( SRWLock )
        {
          ReleaseSRWLockExclusive(SRWLock);
          SRWLock = 0;
        }
      }
    }
    v5 += 8LL;
  }
  return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
}

```

## disassembly

```asm
0x180004110  mov     [rsp+arg_0], rbx
0x180004115  mov     [rsp+arg_10], rbp
0x18000411a  mov     [rsp+SRWLock], rdx
0x18000411f  push    rsi
0x180004120  push    rdi
0x180004121  push    r14
0x180004123  sub     rsp, 20h
0x180004127  mov     rax, [rcx]
0x18000412a  mov     bpl, r8b
0x18000412d  mov     rdi, rcx
0x180004130  mov     rax, [rax+20h]
0x180004134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004139  mov     rdx, [rdi]
0x18000413c  mov     rcx, rdi
0x18000413f  lea     rbx, [rax+8]
0x180004143  mov     rax, [rdx+30h]
0x180004147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414c  mov     r14, rax
0x18000414f  cmp     rbx, r14
0x180004152  jnb     loc_180004217
0x180004158  cmp     qword ptr [rbx], 0
0x18000415c  jz      loc_18000420A
0x180004162  mov     rcx, [rdi]
0x180004165  mov     rax, [rcx+18h]
0x180004169  mov     rcx, rdi
0x18000416c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004171  test    eax, eax
0x180004173  jz      short loc_18000417E
0x180004175  test    bpl, bpl
0x180004178  jz      loc_180004213
0x18000417e  mov     rax, [rbx]
0x180004181  mov     rcx, [rax+18h]
0x180004185  mov     rax, [rcx]
0x180004188  test    rax, rax
0x18000418b  jz      short loc_18000420A
0x18000418d  mov     rax, [rdi]
0x180004190  mov     rcx, rdi
0x180004193  mov     rax, [rax+38h]
0x180004197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000419c  mov     rdx, rax
0x18000419f  lea     rcx, [rsp+38h+SRWLock]
0x1800041a4  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800041a9  mov     rax, [rbx]
0x1800041ac  mov     rcx, [rax+18h]
0x1800041b0  mov     rsi, [rcx]
0x1800041b3  test    rsi, rsi
0x1800041b6  jnz     short loc_1800041CF
0x1800041b8  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800041bd  test    rcx, rcx
0x1800041c0  jz      short loc_18000420A
0x1800041c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800041c8  mov     [rsp+38h+SRWLock], rsi
0x1800041cd  jmp     short loc_18000420A
0x1800041cf  mov     qword ptr [rcx], 0
0x1800041d6  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800041db  test    rcx, rcx
0x1800041de  jz      short loc_1800041EF
0x1800041e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800041e6  mov     [rsp+38h+SRWLock], 0
0x1800041ef  mov     rcx, rsi; Ptr
0x1800041f2  call    cs:__imp_DecodePointer
0x1800041f8  mov     rdx, rax
0x1800041fb  mov     rcx, [rax]
0x1800041fe  mov     rax, [rcx+10h]
0x180004202  mov     rcx, rdx
0x180004205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420a  add     rbx, 8
0x18000420e  jmp     loc_18000414F
0x180004213  xor     al, al
0x180004215  jmp     short loc_18000422B
0x180004217  mov     rax, [rdi]
0x18000421a  mov     rcx, rdi
0x18000421d  mov     rax, [rax+18h]
0x180004221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004226  test    eax, eax
0x180004228  setz    al
0x18000422b  mov     rbx, [rsp+38h+arg_0]
0x180004230  mov     rbp, [rsp+38h+arg_10]
0x180004235  add     rsp, 20h
0x180004239  pop     r14
0x18000423b  pop     rdi
0x18000423c  pop     rsi
0x18000423d  retn
```
