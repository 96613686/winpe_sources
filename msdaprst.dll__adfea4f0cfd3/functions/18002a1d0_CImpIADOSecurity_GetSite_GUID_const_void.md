# CImpIADOSecurity::GetSite(_GUID const &,void * *)

- ea: `0x18002a1d0`
- end: `0x18002a242`
- name: `?GetSite@CImpIADOSecurity@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `114`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014b00`

## callees

- `0x18002a108`
- `0x18002a1a0`
- `0x18002a1d0`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::GetSite(struct CCriticalSection **this, const struct _GUID *a2, void **a3)
{
  unsigned int v6; // ebx
  struct CCriticalSection *v7; // rcx
  char v9; // [rsp+30h] [rbp+8h] BYREF

  CMPCSAutoBlock::CMPCSAutoBlock((CMPCSAutoBlock *)&v9, this + 5);
  if ( a3 )
  {
    v7 = this[4];
    if ( v7 )
      v6 = (**(__int64 (__fastcall ***)(struct CCriticalSection *, const struct _GUID *, void **))v7)(v7, a2, a3);
    else
      v6 = -2147467259;
  }
  else
  {
    v6 = -2147024809;
  }
  CMPCSAutoBlock::~CMPCSAutoBlock((CMPCSAutoBlock *)&v9);
  return v6;
}

```

## disassembly

```asm
0x18002a1d0  mov     [rsp+arg_8], rbx
0x18002a1d5  mov     [rsp+arg_10], rsi
0x18002a1da  push    rdi
0x18002a1db  sub     rsp, 20h
0x18002a1df  mov     rsi, rdx
0x18002a1e2  mov     rbx, rcx
0x18002a1e5  lea     rdx, [rcx+28h]; struct CCriticalSection **
0x18002a1e9  mov     rdi, r8
0x18002a1ec  lea     rcx, [rsp+28h+arg_0]; this
0x18002a1f1  call    ??0CMPCSAutoBlock@@QEAA@PEAPEAVCCriticalSection@@@Z; CMPCSAutoBlock::CMPCSAutoBlock(CCriticalSection * *)
0x18002a1f6  test    rdi, rdi
0x18002a1f9  jnz     short loc_18002A202
0x18002a1fb  mov     ebx, 80070057h
0x18002a200  jmp     short loc_18002A225
0x18002a202  mov     rcx, [rbx+20h]
0x18002a206  test    rcx, rcx
0x18002a209  jnz     short loc_18002A212
0x18002a20b  mov     ebx, 80004005h
0x18002a210  jmp     short loc_18002A225
0x18002a212  mov     rax, [rcx]
0x18002a215  mov     r8, rdi
0x18002a218  mov     rdx, rsi
0x18002a21b  mov     rax, [rax]
0x18002a21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a223  mov     ebx, eax
0x18002a225  lea     rcx, [rsp+28h+arg_0]; this
0x18002a22a  call    ??1CMPCSAutoBlock@@QEAA@XZ; CMPCSAutoBlock::~CMPCSAutoBlock(void)
0x18002a22f  mov     rsi, [rsp+28h+arg_10]
0x18002a234  mov     eax, ebx
0x18002a236  mov     rbx, [rsp+28h+arg_8]
0x18002a23b  add     rsp, 20h
0x18002a23f  pop     rdi
0x18002a240  retn
```
