# DhcpV4ActivateNetwork

- ea: `0x18000a8bc`
- end: `0x18000ac6e`
- name: `DhcpV4ActivateNetwork`
- size: `946`
- prototype: `__int64 __fastcall(unsigned __int64, __int64 *, int *, __int64, unsigned int)`
- caller_count: `11`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18000a738`
- `0x180016d60`
- `0x18001c240`
- `0x180030e74`
- `0x180031d48`
- `0x180031e90`
- `0x180033228`
- `0x180033480`
- `0x1800346a8`
- `0x180034fe4`
- `0x18003e890`

## callees

- `0x180009038`
- `0x18000a100`
- `0x18000a8bc`
- `0x180019884`
- `0x18001be1c`
- `0x18001f0d8`
- `0x18001f100`
- `0x18003191c`
- `0x1800456f0`
- `0x180046158`
- `0x180046324`
- `0x1800494dc`
- `0x18004b260`
- `0x18004b420`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a9e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a9e6`

## pseudocode

```c
__int64 __fastcall DhcpV4ActivateNetwork(unsigned __int64 a1, __int64 *a2, int *a3, __int64 a4, unsigned int a5)
{
  int v6; // esi
  __int64 v7; // rbp
  _QWORD *v10; // r13
  unsigned int v11; // r14d
  unsigned int v12; // ebx
  __int64 v13; // rdx
  DWORD v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r8
  DWORD v17; // ebx
  __int64 v18; // r8
  int IsMachineInCs; // eax
  unsigned int v20; // eax
  __int64 v21; // r9
  int v23; // [rsp+80h] [rbp+8h] BYREF
  __int64 v24; // [rsp+88h] [rbp+10h] BYREF

  v6 = 0;
  v24 = 0;
  v7 = 0;
  v23 = 0;
  v10 = (_QWORD *)a1;
  v11 = a5;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_dJlld(a1, a2, a3, a5, *(_QWORD *)(a4 + 24));
  *v10 = 0;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( DhcpGlobalIsShuttingDown && v11 != 8 )
  {
    v12 = 65;
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_50;
    v13 = 59;
    goto LABEL_9;
  }
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v12 = 50;
    if ( (xmmword_1800616A0 & 2) != 0 )
    {
      v13 = 60;
LABEL_9:
      WPP_SF_D(1025, v13, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v12);
    }
  }
  else
  {
    if ( (unsigned int)DhcpIsMachineInCs() && (unsigned int)DhcpStandbyGetNetworkBlocked(a4 + 2016) )
    {
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_(1025, 61, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
      v12 = 21;
      goto LABEL_50;
    }
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 62, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
    v14 = WaitForSingleObject(DhcpGlobalFirewallReadyEvent, 0x1F4u);
    v17 = v14;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 63, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v14);
    if ( v17 && (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v15, FirewallExemptionGrantDelayed, v17);
    a1 = (unsigned int)DhcpGlobalDsFeatureEnabled;
    if ( !DhcpGlobalDsFeatureEnabled && (unsigned int)DhcpIsMachineInDs() )
    {
      v12 = 1236;
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_(1025, (unsigned int)(a1 + 64), WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
      goto LABEL_50;
    }
    if ( !g_PdcActivationDisabled )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_Jq(1028, 65, v16, *(_QWORD *)(a4 + 24), a4);
      v7 = PdcActivateNetwork(a1, v11);
      if ( !v7 )
      {
        v12 = 1168;
        v6 = 5328;
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_Jq(1025, 66, v18, *(_QWORD *)(a4 + 24), a4);
        goto LABEL_50;
      }
      a1 = (unsigned int)DhcpGlobalDsFeatureEnabled;
    }
    v12 = 0;
    if ( !(_DWORD)a1 || DhcpGlobalIsShuttingDown )
      goto LABEL_45;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 67, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
    IsMachineInCs = DhcpIsMachineInCs();
    v20 = DhcpWcmAcquireRef((int)a4 + 32, (int)a4 + 2016, IsMachineInCs, v11, (__int64)&v23, (__int64)&v24);
    v12 = v20;
    if ( v23 )
      DhcpV4TraceWcmError(a4, v20);
    if ( v12 == 316 )
    {
      v6 = 5328;
      goto LABEL_50;
    }
    if ( !v12 )
    {
LABEL_45:
      if ( v7 )
      {
        v21 = (unsigned int)_InterlockedIncrement(&DhcpGlobalPdcCount);
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_d(1028, 68, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v21);
        *a2 = v7;
        v7 = 0;
      }
      *v10 = v24;
      v24 = 0;
    }
  }
LABEL_50:
  if ( v24 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 69, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
    DhcpWcmReleaseRef(&v24);
  }
  if ( v7 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 70, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids);
    PdcDeactivateNetwork(v7, a2, v11);
  }
  if ( a3 )
    *a3 = v6;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_DdJ(a1, 71, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v12, v11, *(_QWORD *)(a4 + 24));
  return v12;
}

```

## disassembly

```asm
0x18000a8bc  mov     rax, rsp
0x18000a8bf  mov     [rax+18h], rbx
0x18000a8c3  push    rbp
0x18000a8c4  push    rsi
0x18000a8c5  push    rdi
0x18000a8c6  push    r12
0x18000a8c8  push    r13
0x18000a8ca  push    r14
0x18000a8cc  push    r15
0x18000a8ce  sub     rsp, 40h
0x18000a8d2  xor     ebx, ebx
0x18000a8d4  mov     rdi, r9
0x18000a8d7  mov     esi, ebx
0x18000a8d9  mov     [rax+10h], rbx
0x18000a8dd  mov     ebp, ebx
0x18000a8df  mov     [rax+8], ebx
0x18000a8e2  mov     r15, r8
0x18000a8e5  mov     r12, rdx
0x18000a8e8  mov     r13, rcx
0x18000a8eb  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000a8f2  mov     r14d, [rsp+78h+arg_20]
0x18000a8fa  jz      short loc_18000A90D
0x18000a8fc  mov     rax, [r9+18h]
0x18000a900  mov     r9d, r14d
0x18000a903  mov     [rsp+78h+var_58], rax
0x18000a908  call    WPP_SF_dJlld
0x18000a90d  mov     [r13+0], rbx
0x18000a911  mov     [r12], rbx
0x18000a915  test    r15, r15
0x18000a918  jz      short loc_18000A91D
0x18000a91a  mov     [r15], ebx
0x18000a91d  cmp     cs:DhcpGlobalIsShuttingDown, ebx
0x18000a923  jz      short loc_18000A959
0x18000a925  cmp     r14d, 8
0x18000a929  jz      short loc_18000A959
0x18000a92b  mov     ebx, 41h ; 'A'
0x18000a930  test    byte ptr cs:xmmword_1800616A0, 2
0x18000a937  jz      loc_18000ABBB
0x18000a93d  lea     edx, [rbx-6]
0x18000a940  mov     ecx, 401h
0x18000a945  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000a94c  mov     r9d, ebx
0x18000a94f  call    WPP_SF_D
0x18000a954  jmp     loc_18000ABBB
0x18000a959  call    DhcpIsFSEGuestSystem
0x18000a95e  test    eax, eax
0x18000a960  jz      short loc_18000A979
0x18000a962  mov     ebx, 32h ; '2'
0x18000a967  test    byte ptr cs:xmmword_1800616A0, 2
0x18000a96e  jz      loc_18000ABBB
0x18000a974  lea     edx, [rbx+0Ah]
0x18000a977  jmp     short loc_18000A940
0x18000a979  call    DhcpIsMachineInCs
0x18000a97e  test    eax, eax
0x18000a980  jz      short loc_18000A9BB
0x18000a982  lea     rcx, [rdi+7E0h]
0x18000a989  call    DhcpStandbyGetNetworkBlocked
0x18000a98e  test    eax, eax
0x18000a990  jz      short loc_18000A9BB
0x18000a992  test    byte ptr cs:xmmword_1800616A0, 2
0x18000a999  jz      short loc_18000A9B1
0x18000a99b  mov     edx, 3Dh ; '='
0x18000a9a0  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000a9a7  mov     ecx, 401h
0x18000a9ac  call    WPP_SF_
0x18000a9b1  mov     ebx, 15h
0x18000a9b6  jmp     loc_18000ABBB
0x18000a9bb  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000a9c2  jz      short loc_18000A9DA
0x18000a9c4  mov     edx, 3Eh ; '>'
0x18000a9c9  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000a9d0  mov     ecx, 404h
0x18000a9d5  call    WPP_SF_
0x18000a9da  mov     rcx, cs:DhcpGlobalFirewallReadyEvent; hHandle
0x18000a9e1  mov     edx, 1F4h; dwMilliseconds
0x18000a9e6  call    cs:__imp_WaitForSingleObject
0x18000a9ec  mov     ebx, eax
0x18000a9ee  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000a9f5  jz      short loc_18000AA10
0x18000a9f7  mov     edx, 3Fh ; '?'
0x18000a9fc  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000aa03  mov     ecx, 404h
0x18000aa08  mov     r9d, eax
0x18000aa0b  call    WPP_SF_D
0x18000aa10  test    ebx, ebx
0x18000aa12  jz      short loc_18000AA2C
0x18000aa14  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18000aa1b  jz      short loc_18000AA2C
0x18000aa1d  mov     r8d, ebx
0x18000aa20  lea     rdx, FirewallExemptionGrantDelayed
0x18000aa27  call    McTemplateU0q_EtwEventWriteTransfer
0x18000aa2c  mov     ecx, cs:DhcpGlobalDsFeatureEnabled
0x18000aa32  test    ecx, ecx
0x18000aa34  jnz     short loc_18000AA6A
0x18000aa36  call    DhcpIsMachineInDs
0x18000aa3b  test    eax, eax
0x18000aa3d  jz      short loc_18000AA6A
0x18000aa3f  mov     ebx, 4D4h
0x18000aa44  test    byte ptr cs:xmmword_1800616A0, 2
0x18000aa4b  jz      loc_18000ABBB
0x18000aa51  lea     edx, [rcx+40h]
0x18000aa54  mov     ecx, 401h
0x18000aa59  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000aa60  call    WPP_SF_
0x18000aa65  jmp     loc_18000ABBB
0x18000aa6a  cmp     cs:g_PdcActivationDisabled, esi
0x18000aa70  jnz     short loc_18000AADB
0x18000aa72  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000aa79  jz      short loc_18000AA93
0x18000aa7b  mov     r9, [rdi+18h]
0x18000aa7f  mov     edx, 41h ; 'A'
0x18000aa84  mov     ecx, 404h
0x18000aa89  mov     [rsp+78h+var_58], rdi
0x18000aa8e  call    WPP_SF_Jq
0x18000aa93  mov     edx, r14d
0x18000aa96  call    PdcActivateNetwork
0x18000aa9b  mov     rbp, rax
0x18000aa9e  test    rax, rax
0x18000aaa1  jnz     short loc_18000AAD5
0x18000aaa3  mov     ebx, 490h
0x18000aaa8  mov     esi, 14D0h
0x18000aaad  test    byte ptr cs:xmmword_1800616A0, 2
0x18000aab4  jz      loc_18000ABBB
0x18000aaba  mov     r9, [rdi+18h]
0x18000aabe  lea     edx, [rax+42h]
0x18000aac1  mov     ecx, 401h
0x18000aac6  mov     [rsp+78h+var_58], rdi
0x18000aacb  call    WPP_SF_Jq
0x18000aad0  jmp     loc_18000ABBB
0x18000aad5  mov     ecx, cs:DhcpGlobalDsFeatureEnabled
0x18000aadb  xor     ebx, ebx
0x18000aadd  test    ecx, ecx
0x18000aadf  jz      loc_18000AB67
0x18000aae5  cmp     cs:DhcpGlobalIsShuttingDown, ebx
0x18000aaeb  jnz     short loc_18000AB67
0x18000aaed  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000aaf4  jz      short loc_18000AB0A
0x18000aaf6  lea     edx, [rbx+43h]
0x18000aaf9  mov     ecx, 404h
0x18000aafe  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000ab05  call    WPP_SF_
0x18000ab0a  call    DhcpIsMachineInCs
0x18000ab0f  mov     r8d, eax
0x18000ab12  lea     rdx, [rdi+7E0h]
0x18000ab19  lea     rax, [rsp+78h+arg_8]
0x18000ab21  mov     r9d, r14d
0x18000ab24  mov     [rsp+78h+var_50], rax
0x18000ab29  lea     rcx, [rdi+20h]
0x18000ab2d  lea     rax, [rsp+78h+arg_0]
0x18000ab35  mov     [rsp+78h+var_58], rax
0x18000ab3a  call    DhcpWcmAcquireRef
0x18000ab3f  mov     ebx, eax
0x18000ab41  cmp     [rsp+78h+arg_0], esi
0x18000ab48  jz      short loc_18000AB54
0x18000ab4a  mov     edx, eax
0x18000ab4c  mov     rcx, rdi
0x18000ab4f  call    DhcpV4TraceWcmError
0x18000ab54  cmp     ebx, 13Ch
0x18000ab5a  jnz     short loc_18000AB63
0x18000ab5c  mov     esi, 14D0h
0x18000ab61  jmp     short loc_18000ABBB
0x18000ab63  test    ebx, ebx
0x18000ab65  jnz     short loc_18000ABBB
0x18000ab67  test    rbp, rbp
0x18000ab6a  jz      short loc_18000ABA3
0x18000ab6c  mov     r9d, 1
0x18000ab72  lock xadd cs:DhcpGlobalPdcCount, r9d
0x18000ab7b  inc     r9d
0x18000ab7e  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000ab85  jz      short loc_18000AB9D
0x18000ab87  mov     edx, 44h ; 'D'
0x18000ab8c  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000ab93  mov     ecx, 404h
0x18000ab98  call    WPP_SF_d
0x18000ab9d  mov     [r12], rbp
0x18000aba1  xor     ebp, ebp
0x18000aba3  mov     rax, [rsp+78h+arg_8]
0x18000abab  mov     [r13+0], rax
0x18000abaf  mov     [rsp+78h+arg_8], 0
0x18000abbb  cmp     [rsp+78h+arg_8], 0
0x18000abc4  jz      short loc_18000ABF2
0x18000abc6  test    byte ptr cs:xmmword_1800616A0, 2
0x18000abcd  jz      short loc_18000ABE5
0x18000abcf  mov     edx, 45h ; 'E'
0x18000abd4  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000abdb  mov     ecx, 401h
0x18000abe0  call    WPP_SF_
0x18000abe5  lea     rcx, [rsp+78h+arg_8]
0x18000abed  call    DhcpWcmReleaseRef
0x18000abf2  test    rbp, rbp
0x18000abf5  jz      short loc_18000AC21
0x18000abf7  test    byte ptr cs:xmmword_1800616A0, 2
0x18000abfe  jz      short loc_18000AC16
0x18000ac00  mov     edx, 46h ; 'F'
0x18000ac05  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000ac0c  mov     ecx, 401h
0x18000ac11  call    WPP_SF_
0x18000ac16  mov     r8d, r14d
0x18000ac19  mov     rcx, rbp
0x18000ac1c  call    PdcDeactivateNetwork
0x18000ac21  test    r15, r15
0x18000ac24  jz      short loc_18000AC29
0x18000ac26  mov     [r15], esi
0x18000ac29  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000ac30  jz      short loc_18000AC54
0x18000ac32  mov     rax, [rdi+18h]
0x18000ac36  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18000ac3d  mov     [rsp+78h+var_50], rax
0x18000ac42  mov     edx, 47h ; 'G'
0x18000ac47  mov     r9d, ebx
0x18000ac4a  mov     dword ptr [rsp+78h+var_58], r14d
0x18000ac4f  call    WPP_SF_DdJ
0x18000ac54  mov     eax, ebx
0x18000ac56  mov     rbx, [rsp+78h+arg_10]
0x18000ac5e  add     rsp, 40h
0x18000ac62  pop     r15
0x18000ac64  pop     r14
0x18000ac66  pop     r13
0x18000ac68  pop     r12
0x18000ac6a  pop     rdi
0x18000ac6b  pop     rsi
0x18000ac6c  pop     rbp
0x18000ac6d  retn
```
