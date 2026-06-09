# DeviceEncryptionResourceManager::CheckForTpmReadyNoLock(bool *)

- ea: `0x1800148d4`
- end: `0x180014aa3`
- name: `?CheckForTpmReadyNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z`
- size: `463`
- prototype: `__int64 __fastcall(DeviceEncryptionResourceManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014564`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x18000e354`
- `0x1800105f8`
- `0x1800113f4`
- `0x1800116f4`
- `0x1800148d4`

## import_xrefs

- `FVEAPI!FveCheckTpmCapability` at `0x180014976`
- `FVEAPI!FveCheckTpmCapability` at `0x180014976`

## string_xrefs

- `0x18001491a`: `SimulateDETpmNotReady`

## pseudocode

```c
__int64 __fastcall DeviceEncryptionResourceManager::CheckForTpmReadyNoLock(
        DeviceEncryptionResourceManager *this,
        bool *a2)
{
  int v4; // ebx
  unsigned int v5; // eax
  PVOID *v6; // rcx
  bool v8; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v9[2]; // [rsp+28h] [rbp-58h] BYREF
  _QWORD v10[2]; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v11[3]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h] BYREF

  v12 = 0;
  v8 = 0;
  v4 = 0;
  if ( *((_BYTE *)this + 88) )
  {
LABEL_21:
    *a2 = *((_BYTE *)this + 88);
    if ( !*((_BYTE *)this + 88) )
    {
      v9[0] = 0;
      memset(v11, 0, sizeof(v11));
      v10[1] = v10;
      v10[0] = v10;
      v9[1] = FVE_DE_TPM_NOT_READY_FOR_BITLOCKER;
      FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v11, (struct _FVEAPI_EVENT_DATA_COLLECTION *)v9);
      FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v11);
    }
    return (unsigned int)v4;
  }
  NgscbGet_TEST_BooleanOverride(L"SimulateDETpmNotReady", &v8);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
    goto LABEL_21;
  }
  *(_QWORD *)&v12 = 0x100000010LL;
  v5 = FveCheckTpmCapability(&v12);
  v4 = v5;
  if ( !v5 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_13:
    if ( DWORD2(v12) )
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_d(v6[2], 50, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, DWORD2(v12));
    }
    else
    {
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        WPP_SF_(v6[2], 51, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
      *((_BYTE *)this + 88) = 1;
    }
    goto LABEL_21;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v5);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 >= 0 )
    goto LABEL_13;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800148d4  mov     [rsp-18h+arg_10], rbx
0x1800148d9  mov     [rsp-18h+arg_18], rsi
0x1800148de  push    rbp
0x1800148df  push    rdi
0x1800148e0  push    r14
0x1800148e2  mov     rbp, rsp
0x1800148e5  sub     rsp, 80h
0x1800148ec  mov     rax, cs:__security_cookie
0x1800148f3  xor     rax, rsp
0x1800148f6  mov     [rbp+var_10], rax
0x1800148fa  mov     r14, rdx
0x1800148fd  mov     rsi, rcx
0x180014900  xorps   xmm0, xmm0
0x180014903  movups  [rbp+var_20], xmm0
0x180014907  mov     [rbp+var_60], 0
0x18001490b  xor     ebx, ebx
0x18001490d  cmp     [rcx+58h], bl
0x180014910  jnz     loc_180014A1E
0x180014916  lea     rdx, [rbp+var_60]; bool *
0x18001491a  lea     rcx, aSimulatedetpmn; "SimulateDETpmNotReady"
0x180014921  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x180014926  cmp     [rbp+var_60], bl
0x180014929  jz      short loc_180014964
0x18001492b  lea     rdi, WPP_GLOBAL_Control
0x180014932  mov     rcx, cs:WPP_GLOBAL_Control
0x180014939  cmp     rcx, rdi
0x18001493c  jz      loc_180014A1E
0x180014942  test    byte ptr [rcx+1Ch], 8
0x180014946  jz      loc_180014A1E
0x18001494c  lea     edx, [rbx+30h]
0x18001494f  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x180014956  mov     rcx, [rcx+10h]
0x18001495a  call    WPP_SF_
0x18001495f  jmp     loc_180014A1E
0x180014964  mov     dword ptr [rbp+var_20], 10h
0x18001496b  mov     dword ptr [rbp+var_20+4], 1
0x180014972  lea     rcx, [rbp+var_20]
0x180014976  call    cs:__imp_FveCheckTpmCapability
0x18001497c  mov     ebx, eax
0x18001497e  lea     rdi, WPP_GLOBAL_Control
0x180014985  test    eax, eax
0x180014987  jz      short loc_1800149C4
0x180014989  mov     rcx, cs:WPP_GLOBAL_Control
0x180014990  cmp     rcx, rdi
0x180014993  jz      short loc_1800149BA
0x180014995  test    byte ptr [rcx+1Ch], 40h
0x180014999  jz      short loc_1800149BA
0x18001499b  mov     edx, 31h ; '1'
0x1800149a0  mov     r9d, eax
0x1800149a3  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x1800149aa  mov     rcx, [rcx+10h]
0x1800149ae  call    WPP_SF_d
0x1800149b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149ba  test    ebx, ebx
0x1800149bc  js      loc_180014A7D
0x1800149c2  jmp     short loc_1800149CB
0x1800149c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149cb  mov     r9d, dword ptr [rbp+var_20+8]
0x1800149cf  test    r9d, r9d
0x1800149d2  jz      short loc_1800149F6
0x1800149d4  cmp     rcx, rdi
0x1800149d7  jz      short loc_180014A1A
0x1800149d9  test    byte ptr [rcx+1Ch], 8
0x1800149dd  jz      short loc_180014A1A
0x1800149df  mov     edx, 32h ; '2'
0x1800149e4  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x1800149eb  mov     rcx, [rcx+10h]
0x1800149ef  call    WPP_SF_d
0x1800149f4  jmp     short loc_180014A1A
0x1800149f6  cmp     rcx, rdi
0x1800149f9  jz      short loc_180014A16
0x1800149fb  test    byte ptr [rcx+1Ch], 8
0x1800149ff  jz      short loc_180014A16
0x180014a01  mov     edx, 33h ; '3'
0x180014a06  lea     r8, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x180014a0d  mov     rcx, [rcx+10h]
0x180014a11  call    WPP_SF_
0x180014a16  mov     byte ptr [rsi+58h], 1
0x180014a1a  test    ebx, ebx
0x180014a1c  js      short loc_180014A7D
0x180014a1e  mov     al, [rsi+58h]
0x180014a21  mov     [r14], al
0x180014a24  cmp     byte ptr [rsi+58h], 0
0x180014a28  jnz     short loc_180014A7D
0x180014a2a  mov     [rbp+var_58], 0
0x180014a32  mov     [rbp+var_38], 0
0x180014a3a  mov     [rbp+var_30], 0
0x180014a42  mov     [rbp+var_28], 0
0x180014a4a  lea     rax, [rbp+var_48]
0x180014a4e  mov     [rbp+var_40], rax
0x180014a52  lea     rax, [rbp+var_48]
0x180014a56  mov     [rbp+var_48], rax
0x180014a5a  lea     rax, FVE_DE_TPM_NOT_READY_FOR_BITLOCKER
0x180014a61  mov     [rbp+var_50], rax
0x180014a65  lea     rdx, [rbp+var_58]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180014a69  lea     rcx, [rbp+var_38]; this
0x180014a6d  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180014a72  nop
0x180014a73  lea     rcx, [rbp+var_38]; this
0x180014a77  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180014a7c  nop
0x180014a7d  mov     eax, ebx
0x180014a7f  mov     rcx, [rbp+var_10]
0x180014a83  xor     rcx, rsp; StackCookie
0x180014a86  call    __security_check_cookie
0x180014a8b  lea     r11, [rsp+80h+var_s0]
0x180014a93  mov     rbx, [r11+30h]
0x180014a97  mov     rsi, [r11+38h]
0x180014a9b  mov     rsp, r11
0x180014a9e  pop     r14
0x180014aa0  pop     rdi
0x180014aa1  pop     rbp
0x180014aa2  retn
```
