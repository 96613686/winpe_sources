# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x180002d64`
- end: `0x180002e73`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ad0`
- `0x180002e80`

## callees

- `0x180002d64`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002e29`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180002e29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002dec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002e09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002e09`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002e20`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Details::TerminateMap(
        Microsoft::WRL::Details *this,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const unsigned __int16 *a3)
{
  char v3; // r15
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r14
  RTL_SRWLOCK *v7; // rdi
  void **v8; // rax
  void *v9; // rbp
  PVOID v10; // rax

  v3 = (char)a3;
  v5 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *, struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)this + 32LL))(
         this,
         a2)
     + 8;
  v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
  if ( v5 >= v6 )
    return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  while ( !*(_QWORD *)v5 )
  {
LABEL_12:
    v5 += 8LL;
    if ( v5 >= v6 )
      return (*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) == 0;
  }
  if ( !(*(unsigned int (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 24LL))(this) || v3 )
  {
    if ( **(_QWORD **)(*(_QWORD *)v5 + 24LL) )
    {
      v7 = (RTL_SRWLOCK *)(*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 56LL))(this);
      AcquireSRWLockExclusive(v7);
      v8 = *(void ***)(*(_QWORD *)v5 + 24LL);
      v9 = *v8;
      if ( *v8 )
      {
        *v8 = 0;
        if ( v7 )
          ReleaseSRWLockExclusive(v7);
        v10 = DecodePointer(v9);
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v10 + 16LL))(v10);
      }
      else if ( v7 )
      {
        ReleaseSRWLockExclusive(v7);
      }
    }
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180002d64  push    rbx
0x180002d66  push    rbp
0x180002d67  push    rsi
0x180002d68  push    rdi
0x180002d69  push    r14
0x180002d6b  push    r15
0x180002d6d  sub     rsp, 28h
0x180002d71  mov     rax, [rcx]
0x180002d74  mov     r15b, r8b
0x180002d77  mov     rsi, rcx
0x180002d7a  mov     rax, [rax+20h]
0x180002d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d83  mov     rdx, [rsi]
0x180002d86  mov     rcx, rsi
0x180002d89  lea     rbx, [rax+8]
0x180002d8d  mov     rax, [rdx+30h]
0x180002d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d96  mov     r14, rax
0x180002d99  cmp     rbx, rax
0x180002d9c  jnb     loc_180002E4E
0x180002da2  cmp     qword ptr [rbx], 0
0x180002da6  jz      loc_180002E41
0x180002dac  mov     rcx, [rsi]
0x180002daf  mov     rax, [rcx+18h]
0x180002db3  mov     rcx, rsi
0x180002db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbb  test    eax, eax
0x180002dbd  jz      short loc_180002DC8
0x180002dbf  test    r15b, r15b
0x180002dc2  jz      loc_180002E6F
0x180002dc8  mov     rax, [rbx]
0x180002dcb  mov     rcx, [rax+18h]
0x180002dcf  mov     rax, [rcx]
0x180002dd2  test    rax, rax
0x180002dd5  jz      short loc_180002E41
0x180002dd7  mov     rax, [rsi]
0x180002dda  mov     rcx, rsi
0x180002ddd  mov     rax, [rax+38h]
0x180002de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de6  mov     rcx, rax; SRWLock
0x180002de9  mov     rdi, rax
0x180002dec  call    cs:__imp_AcquireSRWLockExclusive
0x180002df2  mov     rcx, [rbx]
0x180002df5  mov     rax, [rcx+18h]
0x180002df9  mov     rbp, [rax]
0x180002dfc  test    rbp, rbp
0x180002dff  jnz     short loc_180002E11
0x180002e01  test    rdi, rdi
0x180002e04  jz      short loc_180002E41
0x180002e06  mov     rcx, rdi; SRWLock
0x180002e09  call    cs:__imp_ReleaseSRWLockExclusive
0x180002e0f  jmp     short loc_180002E41
0x180002e11  mov     qword ptr [rax], 0
0x180002e18  test    rdi, rdi
0x180002e1b  jz      short loc_180002E26
0x180002e1d  mov     rcx, rdi; SRWLock
0x180002e20  call    cs:__imp_ReleaseSRWLockExclusive
0x180002e26  mov     rcx, rbp; Ptr
0x180002e29  call    cs:__imp_DecodePointer
0x180002e2f  mov     rdx, rax
0x180002e32  mov     rcx, [rax]
0x180002e35  mov     rax, [rcx+10h]
0x180002e39  mov     rcx, rdx
0x180002e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e41  add     rbx, 8
0x180002e45  cmp     rbx, r14
0x180002e48  jb      loc_180002DA2
0x180002e4e  mov     rax, [rsi]
0x180002e51  mov     rcx, rsi
0x180002e54  mov     rax, [rax+18h]
0x180002e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5d  test    eax, eax
0x180002e5f  setz    al
0x180002e62  add     rsp, 28h
0x180002e66  pop     r15
0x180002e68  pop     r14
0x180002e6a  pop     rdi
0x180002e6b  pop     rsi
0x180002e6c  pop     rbp
0x180002e6d  pop     rbx
0x180002e6e  retn
0x180002e6f  xor     al, al
0x180002e71  jmp     short loc_180002E62
```
