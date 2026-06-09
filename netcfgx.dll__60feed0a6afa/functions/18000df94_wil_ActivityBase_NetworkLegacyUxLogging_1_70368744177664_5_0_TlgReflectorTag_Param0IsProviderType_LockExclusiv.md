# wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x18000df94`
- end: `0x18000e02e`
- name: `?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c4d8`
- `0x18000e4d0`
- `0x18000f814`
- `0x18000f9bc`
- `0x18000fb90`

## callees

- `0x18000df94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfc4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dfff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e015`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dfff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e015`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18000df94  mov     [rsp+arg_10], rbx
0x18000df99  mov     [rsp+arg_18], rsi
0x18000df9e  push    rdi
0x18000df9f  sub     rsp, 20h
0x18000dfa3  mov     dword ptr [rsp+28h+SRWLock], 0
0x18000dfab  mov     rsi, rdx
0x18000dfae  mov     rbx, [rcx+118h]
0x18000dfb5  test    rbx, rbx
0x18000dfb8  jz      short loc_18000DFD6
0x18000dfba  add     rbx, 108h
0x18000dfc1  mov     rcx, rbx; SRWLock
0x18000dfc4  call    cs:__imp_AcquireSRWLockExclusive
0x18000dfca  lea     rax, [rsp+28h+arg_8]
0x18000dfcf  mov     edi, 1
0x18000dfd4  jmp     short loc_18000DFE2
0x18000dfd6  lea     rax, [rsp+28h+SRWLock]
0x18000dfdb  mov     edi, 2
0x18000dfe0  xor     ebx, ebx
0x18000dfe2  mov     [rsi], rbx
0x18000dfe5  mov     qword ptr [rax], 0
0x18000dfec  test    dil, 2
0x18000dff0  jz      short loc_18000E005
0x18000dff2  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18000dff7  and     edi, 0FFFFFFFDh
0x18000dffa  test    rcx, rcx
0x18000dffd  jz      short loc_18000E005
0x18000dfff  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e005  test    dil, 1
0x18000e009  jz      short loc_18000E01B
0x18000e00b  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x18000e010  test    rcx, rcx
0x18000e013  jz      short loc_18000E01B
0x18000e015  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e01b  mov     rbx, [rsp+28h+arg_10]
0x18000e020  mov     rax, rsi
0x18000e023  mov     rsi, [rsp+28h+arg_18]
0x18000e028  add     rsp, 20h
0x18000e02c  pop     rdi
0x18000e02d  retn
```
