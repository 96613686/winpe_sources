# DeviceEncryptionResourceManager::CheckCommonResourceRequirementsNoLock(bool *,bool)

- ea: `0x180014564`
- end: `0x180014723`
- name: `?CheckCommonResourceRequirementsNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N_N@Z`
- size: `447`
- prototype: `__int64 __fastcall(DeviceEncryptionResourceManager *this, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c1a0`
- `0x180015140`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x180014564`
- `0x18001472c`
- `0x1800148d4`
- `0x180014aac`
- `0x18002b894`

## pseudocode

```c
__int64 __fastcall DeviceEncryptionResourceManager::CheckCommonResourceRequirementsNoLock(
        DeviceEncryptionResourceManager *this,
        bool *a2)
{
  unsigned int v4; // eax
  int v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v9; // eax
  bool v11; // [rsp+58h] [rbp+10h] BYREF
  bool v12; // [rsp+60h] [rbp+18h] BYREF
  bool v13; // [rsp+68h] [rbp+20h] BYREF

  *a2 = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  v4 = DeviceEncryptionResourceManager::CheckForTpmReadyNoLock(this, &v12);
  v5 = v4;
  if ( v4 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v4);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 < 0 )
      return (unsigned int)v5;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
    DeleteBitLockerStatusReg(5);
    v8 = DeviceEncryptionResourceManager::CheckForWinREConfiguredNoLock(this, &v11);
    v5 = v8;
    if ( v8 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v8);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v5 < 0 )
        return (unsigned int)v5;
    }
    else
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 )
    {
      DeleteBitLockerStatusReg(3);
      v9 = DeviceEncryptionResourceManager::CheckForNetworkReadyNoLock(this, &v13);
      v5 = v9;
      if ( v9 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids, v9);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v5 < 0 )
          return (unsigned int)v5;
      }
      else
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v13 )
      {
        DeleteBitLockerStatusReg(6);
        *a2 = 1;
        return (unsigned int)v5;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      {
        v7 = 80;
        goto LABEL_12;
      }
    }
    else if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
    {
      v7 = 77;
      goto LABEL_12;
    }
  }
  else if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
  {
    v7 = 74;
LABEL_12:
    WPP_SF_(v6[2], v7, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014564  mov     rax, rsp
0x180014567  mov     [rax+18h], r8b
0x18001456b  push    rbx
0x18001456c  push    rsi
0x18001456d  push    rdi
0x18001456e  push    r14
0x180014570  push    r15
0x180014572  sub     rsp, 20h
0x180014576  mov     rsi, rdx
0x180014579  mov     byte ptr [rdx], 0
0x18001457c  lea     rdx, [rax+18h]; bool *
0x180014580  mov     byte ptr [rax+20h], 0
0x180014584  mov     rdi, rcx
0x180014587  mov     byte ptr [rax+18h], 0
0x18001458b  mov     byte ptr [rax+10h], 0
0x18001458f  call    ?CheckForTpmReadyNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z; DeviceEncryptionResourceManager::CheckForTpmReadyNoLock(bool *)
0x180014594  lea     r14, WPP_GLOBAL_Control
0x18001459b  mov     ebx, eax
0x18001459d  lea     r15, WPP_30da2b3f58bb356d51c5e00b97cb13e4_Traceguids
0x1800145a4  test    eax, eax
0x1800145a6  jz      short loc_1800145DF
0x1800145a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145af  cmp     rcx, r14
0x1800145b2  jz      short loc_1800145D5
0x1800145b4  test    byte ptr [rcx+1Ch], 40h
0x1800145b8  jz      short loc_1800145D5
0x1800145ba  mov     rcx, [rcx+10h]
0x1800145be  mov     edx, 49h ; 'I'
0x1800145c3  mov     r9d, eax
0x1800145c6  mov     r8, r15
0x1800145c9  call    WPP_SF_d
0x1800145ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145d5  test    ebx, ebx
0x1800145d7  js      loc_180014715
0x1800145dd  jmp     short loc_1800145E6
0x1800145df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145e6  cmp     [rsp+48h+arg_10], 0
0x1800145eb  jnz     short loc_180014616
0x1800145ed  cmp     rcx, r14
0x1800145f0  jz      loc_180014715
0x1800145f6  test    byte ptr [rcx+1Ch], 4
0x1800145fa  jz      loc_180014715
0x180014600  mov     edx, 4Ah ; 'J'
0x180014605  mov     rcx, [rcx+10h]
0x180014609  mov     r8, r15
0x18001460c  call    WPP_SF_
0x180014611  jmp     loc_180014715
0x180014616  mov     ecx, 5
0x18001461b  call    ?DeleteBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@@Z; DeleteBitLockerStatusReg(BITLOCKER_CSP_STATUS)
0x180014620  lea     rdx, [rsp+48h+arg_8]; bool *
0x180014625  mov     rcx, rdi; this
0x180014628  call    ?CheckForWinREConfiguredNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z; DeviceEncryptionResourceManager::CheckForWinREConfiguredNoLock(bool *)
0x18001462d  mov     ebx, eax
0x18001462f  test    eax, eax
0x180014631  jz      short loc_18001466A
0x180014633  mov     rcx, cs:WPP_GLOBAL_Control
0x18001463a  cmp     rcx, r14
0x18001463d  jz      short loc_180014660
0x18001463f  test    byte ptr [rcx+1Ch], 40h
0x180014643  jz      short loc_180014660
0x180014645  mov     rcx, [rcx+10h]
0x180014649  mov     edx, 4Ch ; 'L'
0x18001464e  mov     r9d, eax
0x180014651  mov     r8, r15
0x180014654  call    WPP_SF_d
0x180014659  mov     rcx, cs:WPP_GLOBAL_Control
0x180014660  test    ebx, ebx
0x180014662  js      loc_180014715
0x180014668  jmp     short loc_180014671
0x18001466a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014671  cmp     [rsp+48h+arg_8], 0
0x180014676  jnz     short loc_180014695
0x180014678  cmp     rcx, r14
0x18001467b  jz      loc_180014715
0x180014681  test    byte ptr [rcx+1Ch], 4
0x180014685  jz      loc_180014715
0x18001468b  mov     edx, 4Dh ; 'M'
0x180014690  jmp     loc_180014605
0x180014695  mov     ecx, 3
0x18001469a  call    ?DeleteBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@@Z; DeleteBitLockerStatusReg(BITLOCKER_CSP_STATUS)
0x18001469f  lea     rdx, [rsp+48h+arg_18]; bool *
0x1800146a4  mov     rcx, rdi; this
0x1800146a7  call    ?CheckForNetworkReadyNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z; DeviceEncryptionResourceManager::CheckForNetworkReadyNoLock(bool *)
0x1800146ac  mov     ebx, eax
0x1800146ae  test    eax, eax
0x1800146b0  jz      short loc_1800146E5
0x1800146b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146b9  cmp     rcx, r14
0x1800146bc  jz      short loc_1800146DF
0x1800146be  test    byte ptr [rcx+1Ch], 40h
0x1800146c2  jz      short loc_1800146DF
0x1800146c4  mov     rcx, [rcx+10h]
0x1800146c8  mov     edx, 4Fh ; 'O'
0x1800146cd  mov     r9d, eax
0x1800146d0  mov     r8, r15
0x1800146d3  call    WPP_SF_d
0x1800146d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146df  test    ebx, ebx
0x1800146e1  js      short loc_180014715
0x1800146e3  jmp     short loc_1800146EC
0x1800146e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146ec  cmp     [rsp+48h+arg_18], 0
0x1800146f1  jnz     short loc_180014708
0x1800146f3  cmp     rcx, r14
0x1800146f6  jz      short loc_180014715
0x1800146f8  test    byte ptr [rcx+1Ch], 4
0x1800146fc  jz      short loc_180014715
0x1800146fe  mov     edx, 50h ; 'P'
0x180014703  jmp     loc_180014605
0x180014708  mov     ecx, 6
0x18001470d  call    ?DeleteBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@@Z; DeleteBitLockerStatusReg(BITLOCKER_CSP_STATUS)
0x180014712  mov     byte ptr [rsi], 1
0x180014715  mov     eax, ebx
0x180014717  add     rsp, 20h
0x18001471b  pop     r15
0x18001471d  pop     r14
0x18001471f  pop     rdi
0x180014720  pop     rsi
0x180014721  pop     rbx
0x180014722  retn
```
