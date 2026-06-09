# wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x140006c34`
- end: `0x140006cce`
- name: `?LockExclusive@?$ActivityBase@VIsoBurnLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003954`
- `0x140007170`
- `0x1400086e4`
- `0x1400089a0`
- `0x140008b80`

## callees

- `0x140006c34`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140006c64`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140006c64`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006c9f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006cb5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006c9f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140006cb5`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x140006c34  mov     [rsp+arg_10], rbx
0x140006c39  mov     [rsp+arg_18], rsi
0x140006c3e  push    rdi
0x140006c3f  sub     rsp, 20h
0x140006c43  mov     dword ptr [rsp+28h+SRWLock], 0
0x140006c4b  mov     rsi, rdx
0x140006c4e  mov     rbx, [rcx+118h]
0x140006c55  test    rbx, rbx
0x140006c58  jz      short loc_140006C76
0x140006c5a  add     rbx, 108h
0x140006c61  mov     rcx, rbx; SRWLock
0x140006c64  call    cs:__imp_AcquireSRWLockExclusive
0x140006c6a  lea     rax, [rsp+28h+arg_8]
0x140006c6f  mov     edi, 1
0x140006c74  jmp     short loc_140006C82
0x140006c76  lea     rax, [rsp+28h+SRWLock]
0x140006c7b  mov     edi, 2
0x140006c80  xor     ebx, ebx
0x140006c82  mov     [rsi], rbx
0x140006c85  mov     qword ptr [rax], 0
0x140006c8c  test    dil, 2
0x140006c90  jz      short loc_140006CA5
0x140006c92  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x140006c97  and     edi, 0FFFFFFFDh
0x140006c9a  test    rcx, rcx
0x140006c9d  jz      short loc_140006CA5
0x140006c9f  call    cs:__imp_ReleaseSRWLockExclusive
0x140006ca5  test    dil, 1
0x140006ca9  jz      short loc_140006CBB
0x140006cab  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x140006cb0  test    rcx, rcx
0x140006cb3  jz      short loc_140006CBB
0x140006cb5  call    cs:__imp_ReleaseSRWLockExclusive
0x140006cbb  mov     rbx, [rsp+28h+arg_10]
0x140006cc0  mov     rax, rsi
0x140006cc3  mov     rsi, [rsp+28h+arg_18]
0x140006cc8  add     rsp, 20h
0x140006ccc  pop     rdi
0x140006ccd  retn
```
