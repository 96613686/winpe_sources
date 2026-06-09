# Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)

- ea: `0x1800034b4`
- end: `0x1800035c3`
- name: `?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z`
- size: `271`
- prototype: `bool __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, const unsigned __int16 *, bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003310`
- `0x1800035d0`

## callees

- `0x1800034b4`
- `0x18000b010`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x180003579`
- `KERNEL32!DecodePointer` at `0x180003579`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000353c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000353c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180003559`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180003570`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180003559`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180003570`

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
0x1800034b4  push    rbx
0x1800034b6  push    rbp
0x1800034b7  push    rsi
0x1800034b8  push    rdi
0x1800034b9  push    r14
0x1800034bb  push    r15
0x1800034bd  sub     rsp, 28h
0x1800034c1  mov     r15b, r8b
0x1800034c4  mov     rsi, rcx
0x1800034c7  mov     rax, [rcx]
0x1800034ca  mov     rax, [rax+20h]
0x1800034ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d3  lea     rbx, [rax+8]
0x1800034d7  mov     rdx, [rsi]
0x1800034da  mov     rcx, rsi
0x1800034dd  mov     rax, [rdx+30h]
0x1800034e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e6  mov     r14, rax
0x1800034e9  cmp     rbx, rax
0x1800034ec  jnb     loc_18000359E
0x1800034f2  cmp     qword ptr [rbx], 0
0x1800034f6  jz      loc_180003591
0x1800034fc  mov     rcx, [rsi]
0x1800034ff  mov     rax, [rcx+18h]
0x180003503  mov     rcx, rsi
0x180003506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000350b  test    eax, eax
0x18000350d  jz      short loc_180003518
0x18000350f  test    r15b, r15b
0x180003512  jz      loc_1800035BF
0x180003518  mov     rax, [rbx]
0x18000351b  mov     rcx, [rax+18h]
0x18000351f  mov     rax, [rcx]
0x180003522  test    rax, rax
0x180003525  jz      short loc_180003591
0x180003527  mov     rax, [rsi]
0x18000352a  mov     rcx, rsi
0x18000352d  mov     rax, [rax+38h]
0x180003531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003536  mov     rdi, rax
0x180003539  mov     rcx, rax; SRWLock
0x18000353c  call    cs:__imp_AcquireSRWLockExclusive
0x180003542  mov     rcx, [rbx]
0x180003545  mov     rax, [rcx+18h]
0x180003549  mov     rbp, [rax]
0x18000354c  test    rbp, rbp
0x18000354f  jnz     short loc_180003561
0x180003551  test    rdi, rdi
0x180003554  jz      short loc_180003591
0x180003556  mov     rcx, rdi; SRWLock
0x180003559  call    cs:__imp_ReleaseSRWLockExclusive
0x18000355f  jmp     short loc_180003591
0x180003561  mov     qword ptr [rax], 0
0x180003568  test    rdi, rdi
0x18000356b  jz      short loc_180003576
0x18000356d  mov     rcx, rdi; SRWLock
0x180003570  call    cs:__imp_ReleaseSRWLockExclusive
0x180003576  mov     rcx, rbp; Ptr
0x180003579  call    cs:__imp_DecodePointer
0x18000357f  mov     rdx, rax
0x180003582  mov     rcx, [rax]
0x180003585  mov     rax, [rcx+10h]
0x180003589  mov     rcx, rdx
0x18000358c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003591  add     rbx, 8
0x180003595  cmp     rbx, r14
0x180003598  jb      loc_1800034F2
0x18000359e  mov     rax, [rsi]
0x1800035a1  mov     rcx, rsi
0x1800035a4  mov     rax, [rax+18h]
0x1800035a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ad  test    eax, eax
0x1800035af  setz    al
0x1800035b2  add     rsp, 28h
0x1800035b6  pop     r15
0x1800035b8  pop     r14
0x1800035ba  pop     rdi
0x1800035bb  pop     rsi
0x1800035bc  pop     rbp
0x1800035bd  pop     rbx
0x1800035be  retn
0x1800035bf  xor     al, al
0x1800035c1  jmp     short loc_1800035B2
```
