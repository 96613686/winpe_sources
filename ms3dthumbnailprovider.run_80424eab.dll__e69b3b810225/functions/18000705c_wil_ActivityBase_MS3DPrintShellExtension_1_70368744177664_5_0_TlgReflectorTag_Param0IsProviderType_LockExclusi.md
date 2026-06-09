# wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18000705c`
- end: `0x1800070f6`
- name: `?LockExclusive@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005624`
- `0x1800075a0`
- `0x180008cf0`
- `0x180008e98`
- `0x180009070`

## callees

- `0x18000705c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000708c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000708c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800070c7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800070dd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800070c7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800070dd`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18000705c  mov     [rsp+arg_10], rbx
0x180007061  mov     [rsp+arg_18], rsi
0x180007066  push    rdi
0x180007067  sub     rsp, 20h
0x18000706b  mov     dword ptr [rsp+28h+SRWLock], 0
0x180007073  mov     rsi, rdx
0x180007076  mov     rbx, [rcx+118h]
0x18000707d  test    rbx, rbx
0x180007080  jz      short loc_18000709E
0x180007082  add     rbx, 108h
0x180007089  mov     rcx, rbx; SRWLock
0x18000708c  call    cs:__imp_AcquireSRWLockExclusive
0x180007092  lea     rax, [rsp+28h+arg_8]
0x180007097  mov     edi, 1
0x18000709c  jmp     short loc_1800070AA
0x18000709e  lea     rax, [rsp+28h+SRWLock]
0x1800070a3  mov     edi, 2
0x1800070a8  xor     ebx, ebx
0x1800070aa  mov     [rsi], rbx
0x1800070ad  mov     qword ptr [rax], 0
0x1800070b4  test    dil, 2
0x1800070b8  jz      short loc_1800070CD
0x1800070ba  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x1800070bf  and     edi, 0FFFFFFFDh
0x1800070c2  test    rcx, rcx
0x1800070c5  jz      short loc_1800070CD
0x1800070c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800070cd  test    dil, 1
0x1800070d1  jz      short loc_1800070E3
0x1800070d3  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x1800070d8  test    rcx, rcx
0x1800070db  jz      short loc_1800070E3
0x1800070dd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800070e3  mov     rbx, [rsp+28h+arg_10]
0x1800070e8  mov     rax, rsi
0x1800070eb  mov     rsi, [rsp+28h+arg_18]
0x1800070f0  add     rsp, 20h
0x1800070f4  pop     rdi
0x1800070f5  retn
```
