# DAS::DevnodeManagment::DevnodeManager::UninstallDevnodes(ushort const *,ushort const *)

- ea: `0x180028a2c`
- end: `0x180028b04`
- name: `?UninstallDevnodes@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEBG0@Z`
- size: `216`
- prototype: `__int64 __fastcall(DAS::DevnodeManagment::DevnodeManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002e494`

## callees

- `0x18001dfe0`
- `0x180028810`
- `0x180028a2c`
- `0x18002a948`
- `0x18003a2b4`
- `0x18004ecc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028a80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028aec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028a80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028aec`

## string_xrefs

- `0x180028a67`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180028ab2`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::UninstallDevnodes(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  DAS::DevnodeManagment::DevnodeManager *v9; // rcx
  int v10; // [rsp+20h] [rbp-18h]
  const char *v11; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+8h] BYREF

  wil::AcquireSRWLockShared(&SRWLock, this + 1);
  if ( !LOBYTE(this[2].Ptr) )
  {
    v6 = -2140930029;
    v7 = 674;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)(unsigned int)v6,
      v10);
LABEL_4:
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return (unsigned int)v6;
  }
  v6 = DAS::DevnodeManagment::DevnodeManager::StopDevnodeManagement(
         (DAS::DevnodeManagment::DevnodeManager *)this,
         a2,
         a3);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2AA,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)(unsigned int)v6,
      (int)"failed to close devnodes",
      v11);
    goto LABEL_4;
  }
  if ( v6 != 1 )
  {
    v6 = DAS::DevnodeManagment::DevnodeManager::UninstallDevnodesCommon(v9, a2, a3);
    if ( v6 < 0 )
    {
      v7 = 689;
      goto LABEL_3;
    }
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x180028a2c  mov     [rsp+arg_8], rbx
0x180028a31  mov     [rsp+arg_10], rsi
0x180028a36  push    rdi
0x180028a37  sub     rsp, 30h
0x180028a3b  mov     rsi, rdx
0x180028a3e  mov     rbx, rcx
0x180028a41  lea     rdx, [rcx+8]
0x180028a45  mov     rdi, r8
0x180028a48  lea     rcx, [rsp+38h+SRWLock]
0x180028a4d  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x180028a52  cmp     byte ptr [rbx+10h], 0
0x180028a56  jnz     short loc_180028A8A
0x180028a58  mov     ebx, 80640013h
0x180028a5d  mov     edx, 2A2h; void *
0x180028a62  mov     rcx, [rsp+38h]; this
0x180028a67  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180028a6e  mov     r9d, ebx; char *
0x180028a71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a76  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180028a7b  test    rcx, rcx
0x180028a7e  jz      short loc_180028A86
0x180028a80  call    cs:__imp_ReleaseSRWLockShared
0x180028a86  mov     eax, ebx
0x180028a88  jmp     short loc_180028AF4
0x180028a8a  mov     r8, rdi; unsigned __int16 *
0x180028a8d  mov     rdx, rsi; unsigned __int16 *
0x180028a90  mov     rcx, rbx; this
0x180028a93  call    ?StopDevnodeManagement@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEBG0@Z; DAS::DevnodeManagment::DevnodeManager::StopDevnodeManagement(ushort const *,ushort const *)
0x180028a98  mov     ebx, eax
0x180028a9a  test    eax, eax
0x180028a9c  jns     short loc_180028AC5
0x180028a9e  mov     rcx, [rsp+38h]; this
0x180028aa3  lea     rax, aFailedToCloseD; "failed to close devnodes"
0x180028aaa  mov     r9d, ebx; char *
0x180028aad  mov     qword ptr [rsp+38h+var_18], rax; int
0x180028ab2  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180028ab9  mov     edx, 2AAh; void *
0x180028abe  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028ac3  jmp     short loc_180028A76
0x180028ac5  cmp     ebx, 1
0x180028ac8  jz      short loc_180028AE2
0x180028aca  mov     r8, rdi; unsigned __int16 *
0x180028acd  mov     rdx, rsi; unsigned __int16 *
0x180028ad0  call    ?UninstallDevnodesCommon@DevnodeManager@DevnodeManagment@DAS@@AEAAJPEBG0@Z; DAS::DevnodeManagment::DevnodeManager::UninstallDevnodesCommon(ushort const *,ushort const *)
0x180028ad5  mov     ebx, eax
0x180028ad7  test    eax, eax
0x180028ad9  jns     short loc_180028AE2
0x180028adb  mov     edx, 2B1h
0x180028ae0  jmp     short loc_180028A62
0x180028ae2  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x180028ae7  test    rcx, rcx
0x180028aea  jz      short loc_180028AF2
0x180028aec  call    cs:__imp_ReleaseSRWLockShared
0x180028af2  xor     eax, eax
0x180028af4  mov     rbx, [rsp+38h+arg_8]
0x180028af9  mov     rsi, [rsp+38h+arg_10]
0x180028afe  add     rsp, 30h
0x180028b02  pop     rdi
0x180028b03  retn
```
