# wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x1400084b8`
- end: `0x140008552`
- name: `?LockExclusive@?$ActivityBase@VLanguagePackDiskCleanupTraceProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140005580`
- `0x140008b70`
- `0x14000b358`
- `0x14000b504`
- `0x14000b8d0`

## callees

- `0x1400084b8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400084e8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400084e8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008523`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008539`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008523`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140008539`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<LanguagePackDiskCleanupTraceProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        __int64 a1,
        RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  PSRWLOCK *p_SRWLock; // rax
  char v6; // di
  PSRWLOCK SRWLock; // [rsp+30h] [rbp+8h] BYREF
  PSRWLOCK v9; // [rsp+38h] [rbp+10h] BYREF

  LODWORD(SRWLock) = 0;
  v3 = *(RTL_SRWLOCK **)(a1 + 280);
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    p_SRWLock = &v9;
    v6 = 1;
  }
  else
  {
    p_SRWLock = &SRWLock;
    v6 = 2;
    v4 = 0;
  }
  *a2 = v4;
  *p_SRWLock = 0;
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
  }
  if ( (v6 & 1) != 0 && v9 )
    ReleaseSRWLockExclusive(v9);
  return a2;
}

```

## disassembly

```asm
0x1400084b8  mov     [rsp+arg_10], rbx
0x1400084bd  mov     [rsp+arg_18], rsi
0x1400084c2  push    rdi
0x1400084c3  sub     rsp, 20h
0x1400084c7  mov     dword ptr [rsp+28h+SRWLock], 0
0x1400084cf  mov     rsi, rdx
0x1400084d2  mov     rbx, [rcx+118h]
0x1400084d9  test    rbx, rbx
0x1400084dc  jz      short loc_1400084FA
0x1400084de  add     rbx, 108h
0x1400084e5  mov     rcx, rbx; SRWLock
0x1400084e8  call    cs:__imp_AcquireSRWLockExclusive
0x1400084ee  lea     rax, [rsp+28h+arg_8]
0x1400084f3  mov     edi, 1
0x1400084f8  jmp     short loc_140008506
0x1400084fa  lea     rax, [rsp+28h+SRWLock]
0x1400084ff  mov     edi, 2
0x140008504  xor     ebx, ebx
0x140008506  mov     [rsi], rbx
0x140008509  mov     qword ptr [rax], 0
0x140008510  test    dil, 2
0x140008514  jz      short loc_140008529
0x140008516  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x14000851b  and     edi, 0FFFFFFFDh
0x14000851e  test    rcx, rcx
0x140008521  jz      short loc_140008529
0x140008523  call    cs:__imp_ReleaseSRWLockExclusive
0x140008529  test    dil, 1
0x14000852d  jz      short loc_14000853F
0x14000852f  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x140008534  test    rcx, rcx
0x140008537  jz      short loc_14000853F
0x140008539  call    cs:__imp_ReleaseSRWLockExclusive
0x14000853f  mov     rbx, [rsp+28h+arg_10]
0x140008544  mov     rax, rsi
0x140008547  mov     rsi, [rsp+28h+arg_18]
0x14000854c  add     rsp, 20h
0x140008550  pop     rdi
0x140008551  retn
```
