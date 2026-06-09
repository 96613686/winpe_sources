# wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)

- ea: `0x140009e44`
- end: `0x140009ede`
- name: `?LockExclusive@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `154`
- prototype: `RTL_SRWLOCK **__fastcall(__int64, RTL_SRWLOCK **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000672c`
- `0x14000a400`
- `0x14000d358`
- `0x14000d500`
- `0x14000d6e0`

## callees

- `0x140009e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009e74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009e74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009eaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009ec5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009eaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009ec5`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x140009e44  mov     [rsp+arg_10], rbx
0x140009e49  mov     [rsp+arg_18], rsi
0x140009e4e  push    rdi
0x140009e4f  sub     rsp, 20h
0x140009e53  mov     dword ptr [rsp+28h+SRWLock], 0
0x140009e5b  mov     rsi, rdx
0x140009e5e  mov     rbx, [rcx+118h]
0x140009e65  test    rbx, rbx
0x140009e68  jz      short loc_140009E86
0x140009e6a  add     rbx, 108h
0x140009e71  mov     rcx, rbx; SRWLock
0x140009e74  call    cs:__imp_AcquireSRWLockExclusive
0x140009e7a  lea     rax, [rsp+28h+arg_8]
0x140009e7f  mov     edi, 1
0x140009e84  jmp     short loc_140009E92
0x140009e86  lea     rax, [rsp+28h+SRWLock]
0x140009e8b  mov     edi, 2
0x140009e90  xor     ebx, ebx
0x140009e92  mov     [rsi], rbx
0x140009e95  mov     qword ptr [rax], 0
0x140009e9c  test    dil, 2
0x140009ea0  jz      short loc_140009EB5
0x140009ea2  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x140009ea7  and     edi, 0FFFFFFFDh
0x140009eaa  test    rcx, rcx
0x140009ead  jz      short loc_140009EB5
0x140009eaf  call    cs:__imp_ReleaseSRWLockExclusive
0x140009eb5  test    dil, 1
0x140009eb9  jz      short loc_140009ECB
0x140009ebb  mov     rcx, [rsp+28h+arg_8]; SRWLock
0x140009ec0  test    rcx, rcx
0x140009ec3  jz      short loc_140009ECB
0x140009ec5  call    cs:__imp_ReleaseSRWLockExclusive
0x140009ecb  mov     rbx, [rsp+28h+arg_10]
0x140009ed0  mov     rax, rsi
0x140009ed3  mov     rsi, [rsp+28h+arg_18]
0x140009ed8  add     rsp, 20h
0x140009edc  pop     rdi
0x140009edd  retn
```
