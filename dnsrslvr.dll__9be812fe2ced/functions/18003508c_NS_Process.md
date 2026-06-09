# NS_Process

- ea: `0x18003508c`
- end: `0x1800352a2`
- name: `NS_Process`
- size: `534`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180039350`
- `0x18003e1d4`
- `0x18004b858`

## callees

- `0x180012338`
- `0x180026adc`
- `0x180026b7c`
- `0x180030e34`
- `0x1800343f8`
- `0x18003508c`
- `0x18003e1d4`
- `0x180046ec0`
- `0x18004b858`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!Coalesce_UpdateNetVersion` at `0x1800351cc`
- `DNSAPI!Coalesce_UpdateNetVersion` at `0x1800351cc`
- `DNSAPI!NetInfo_Free` at `0x180035265`
- `DNSAPI!NetInfo_Free` at `0x180035265`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003511e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003511e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003522c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003522c`

## pseudocode

```c
__int64 NS_Process()
{
  unsigned int v0; // eax
  unsigned int v1; // edi
  __int64 v2; // rdx
  unsigned int v3; // ebp
  int v4; // r14d
  unsigned int v5; // eax
  unsigned int v6; // esi
  char v7; // dl
  __int64 result; // rax
  __int64 v9; // [rsp+20h] [rbp-48h] BYREF

  v9 = 0;
  if ( g_fVelocityNetinfoCleanup )
  {
    v0 = GrabNetworkInfo(3, &v9, 0);
    v1 = v0;
    if ( v0 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_34;
      v2 = 20;
LABEL_33:
      WPP_SF_d(1035, v2, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids, v0);
      goto LABEL_34;
    }
  }
  else
  {
    v0 = GrabNetworkInfoOld(1, 0, &v9, 0);
    v1 = v0;
    if ( v0 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_34;
      v2 = 21;
      goto LABEL_33;
    }
  }
  v3 = 0;
  v4 = 0;
  AcquireSRWLockExclusive(&SRWLock);
  v5 = NS_GetStateChange(v9);
  v6 = v5;
  v7 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_d(1035, 22, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids, v5);
    v7 = BYTE1(xmmword_1800AB5A0);
  }
  switch ( v6 )
  {
    case 1u:
      if ( (unsigned int)NS_RestoreNetworkVersion(&v9) )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 26, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids);
        NS_UpdateCachedNetworkInfo(&v9, 0);
      }
      break;
    case 2u:
      goto LABEL_14;
    case 3u:
    case 4u:
      if ( (v7 & 8) != 0 )
        WPP_SF_(1035, 24, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids);
      NS_UpdateCurrentNetworkVersion(v6);
      goto LABEL_20;
    case 5u:
      if ( (v7 & 8) != 0 )
        WPP_SF_(1035, 25, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids);
      NS_UpdateCachedNetworkInfo(&v9, 0);
      v4 = 1;
      goto LABEL_20;
    case 6u:
LABEL_14:
      if ( (v7 & 8) != 0 )
        WPP_SF_(1035, 23, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids);
      NS_UpdateCachedNetworkInfo(&v9, 1);
      v3 = 1;
LABEL_20:
      Coalesce_UpdateNetVersion();
      break;
  }
  ReleaseSRWLockExclusive(&SRWLock);
  if ( v3 || v4 )
    Cache_Flush(v3);
LABEL_34:
  result = NetInfo_Free(v9);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    return WPP_SF_d(1035, 27, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids, v1);
  return result;
}

```

## disassembly

```asm
0x18003508c  push    rbp
0x18003508e  push    rsi
0x18003508f  push    rdi
0x180035090  push    r12
0x180035092  push    r14
0x180035094  push    r15
0x180035096  sub     rsp, 38h
0x18003509a  mov     rax, cs:__security_cookie
0x1800350a1  xor     rax, rsp
0x1800350a4  mov     [rsp+68h+var_40], rax
0x1800350a9  cmp     cs:g_fVelocityNetinfoCleanup, 0
0x1800350b0  lea     r12, WPP_a4f9470467a43f00a153ef08c812372a_Traceguids
0x1800350b7  mov     [rsp+68h+var_48], 0
0x1800350c0  mov     r15d, 40Bh
0x1800350c6  jz      short loc_1800350F6
0x1800350c8  xor     r8d, r8d
0x1800350cb  lea     rdx, [rsp+68h+var_48]
0x1800350d0  lea     ecx, [r8+3]
0x1800350d4  call    GrabNetworkInfo
0x1800350d9  mov     edi, eax
0x1800350db  test    eax, eax
0x1800350dd  jz      short loc_180035112
0x1800350df  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800350e6  jz      loc_180035260
0x1800350ec  mov     edx, 14h
0x1800350f1  jmp     loc_180035252
0x1800350f6  xor     edx, edx
0x1800350f8  lea     r8, [rsp+68h+var_48]
0x1800350fd  xor     r9d, r9d
0x180035100  lea     ecx, [rdx+1]
0x180035103  call    GrabNetworkInfoOld
0x180035108  mov     edi, eax
0x18003510a  test    eax, eax
0x18003510c  jnz     loc_180035244
0x180035112  lea     rcx, SRWLock; SRWLock
0x180035119  xor     ebp, ebp
0x18003511b  xor     r14d, r14d
0x18003511e  call    cs:__imp_AcquireSRWLockExclusive
0x180035124  mov     rcx, [rsp+68h+var_48]
0x180035129  call    NS_GetStateChange
0x18003512e  mov     esi, eax
0x180035130  mov     dl, byte ptr cs:xmmword_1800AB5A0+1
0x180035136  test    dl, 8
0x180035139  jz      short loc_180035152
0x18003513b  lea     edx, [rbp+16h]
0x18003513e  mov     ecx, r15d
0x180035141  mov     r9d, eax
0x180035144  mov     r8, r12
0x180035147  call    WPP_SF_d
0x18003514c  mov     dl, byte ptr cs:xmmword_1800AB5A0+1
0x180035152  mov     ecx, esi
0x180035154  sub     ecx, 1
0x180035157  jz      loc_1800351F2
0x18003515d  sub     ecx, 1
0x180035160  jz      short loc_18003517A
0x180035162  sub     ecx, 1
0x180035165  jz      short loc_1800351D4
0x180035167  sub     ecx, 1
0x18003516a  jz      short loc_1800351D4
0x18003516c  sub     ecx, 1
0x18003516f  jz      short loc_1800351A5
0x180035171  cmp     ecx, 1
0x180035174  jnz     loc_180035225
0x18003517a  test    dl, 8
0x18003517d  jz      short loc_18003518F
0x18003517f  mov     edx, 17h
0x180035184  mov     ecx, r15d
0x180035187  mov     r8, r12
0x18003518a  call    WPP_SF_
0x18003518f  mov     edx, 1
0x180035194  lea     rcx, [rsp+68h+var_48]
0x180035199  call    NS_UpdateCachedNetworkInfo
0x18003519e  mov     ebp, 1
0x1800351a3  jmp     short loc_1800351CC
0x1800351a5  test    dl, 8
0x1800351a8  jz      short loc_1800351BA
0x1800351aa  mov     edx, 19h
0x1800351af  mov     ecx, r15d
0x1800351b2  mov     r8, r12
0x1800351b5  call    WPP_SF_
0x1800351ba  xor     edx, edx
0x1800351bc  lea     rcx, [rsp+68h+var_48]
0x1800351c1  call    NS_UpdateCachedNetworkInfo
0x1800351c6  mov     r14d, 1
0x1800351cc  call    cs:__imp_Coalesce_UpdateNetVersion
0x1800351d2  jmp     short loc_180035225
0x1800351d4  test    dl, 8
0x1800351d7  jz      short loc_1800351E9
0x1800351d9  mov     edx, 18h
0x1800351de  mov     ecx, r15d
0x1800351e1  mov     r8, r12
0x1800351e4  call    WPP_SF_
0x1800351e9  mov     ecx, esi
0x1800351eb  call    NS_UpdateCurrentNetworkVersion
0x1800351f0  jmp     short loc_1800351CC
0x1800351f2  lea     rcx, [rsp+68h+var_48]
0x1800351f7  call    NS_RestoreNetworkVersion
0x1800351fc  test    eax, eax
0x1800351fe  jz      short loc_180035225
0x180035200  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180035207  jz      short loc_180035219
0x180035209  mov     edx, 1Ah
0x18003520e  mov     ecx, r15d
0x180035211  mov     r8, r12
0x180035214  call    WPP_SF_
0x180035219  xor     edx, edx
0x18003521b  lea     rcx, [rsp+68h+var_48]
0x180035220  call    NS_UpdateCachedNetworkInfo
0x180035225  lea     rcx, SRWLock; SRWLock
0x18003522c  call    cs:__imp_ReleaseSRWLockExclusive
0x180035232  test    ebp, ebp
0x180035234  jnz     short loc_18003523B
0x180035236  test    r14d, r14d
0x180035239  jz      short loc_180035260
0x18003523b  mov     ecx, ebp
0x18003523d  call    Cache_Flush
0x180035242  jmp     short loc_180035260
0x180035244  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003524b  jz      short loc_180035260
0x18003524d  mov     edx, 15h
0x180035252  mov     r9d, eax
0x180035255  mov     r8, r12
0x180035258  mov     ecx, r15d
0x18003525b  call    WPP_SF_d
0x180035260  mov     rcx, [rsp+68h+var_48]
0x180035265  call    cs:__imp_NetInfo_Free
0x18003526b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180035272  jz      short loc_180035287
0x180035274  mov     edx, 1Bh
0x180035279  mov     ecx, r15d
0x18003527c  mov     r9d, edi
0x18003527f  mov     r8, r12
0x180035282  call    WPP_SF_d
0x180035287  mov     rcx, [rsp+68h+var_40]
0x18003528c  xor     rcx, rsp; StackCookie
0x18003528f  call    __security_check_cookie
0x180035294  add     rsp, 38h
0x180035298  pop     r15
0x18003529a  pop     r14
0x18003529c  pop     r12
0x18003529e  pop     rdi
0x18003529f  pop     rsi
0x1800352a0  pop     rbp
0x1800352a1  retn
```
