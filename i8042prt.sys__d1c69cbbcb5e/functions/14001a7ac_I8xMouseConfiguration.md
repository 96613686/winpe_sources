# I8xMouseConfiguration

- ea: `0x14001a7ac`
- end: `0x14001aa90`
- name: `I8xMouseConfiguration`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x14001c068`

## callees

- `0x1400014e0`
- `0x140004530`
- `0x140007b10`
- `0x14000aaac`
- `0x14001a7ac`

## pseudocode

```c
__int64 __fastcall I8xMouseConfiguration(__int64 a1, _DWORD *a2)
{
  unsigned __int8 *v4; // rbp
  unsigned int v5; // r15d
  unsigned int v6; // r13d
  _DWORD *v7; // r14
  int v8; // r12d
  __int64 v9; // rax
  __int64 v10; // rcx
  char v11; // al
  char v12; // al
  const char *v13; // rdx
  const char *v14; // rcx
  __int64 v15; // [rsp+28h] [rbp-60h]

  if ( !a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        17,
        66,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    return 3221225626LL;
  }
  if ( a2 == (_DWORD *)-4LL )
    return 3221225626LL;
  v4 = (unsigned __int8 *)(a2 + 5);
  v5 = 0;
  **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 2u;
  v6 = a2[4];
  v7 = *(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  *(_BYTE *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 80LL) = 0;
  v7[5] = a2[2];
  v8 = a2[1];
  v7[4] = v8;
  if ( v6 )
  {
    while ( 1 )
    {
      LODWORD(a2) = *v4;
      if ( (_DWORD)a2 == 1 )
        goto LABEL_13;
      if ( *v4 == 2 )
      {
        *(_OWORD *)(a1 + 536) = *(_OWORD *)v4;
        *(_DWORD *)(a1 + 552) = *((_DWORD *)v4 + 4);
        v11 = 3;
        if ( v8 != 3 )
          v11 = 1;
        *(_BYTE *)(a1 + 537) = v11;
        goto LABEL_22;
      }
      if ( *v4 == 3 )
        break;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v15) = *v4;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          1,
          69,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
          v15);
      }
LABEL_22:
      ++v5;
      v4 += 20;
      if ( v5 >= v6 )
        goto LABEL_23;
    }
    BYTE4(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
LABEL_13:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v15) = *((unsigned __int16 *)v4 + 1);
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        14,
        67,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v15);
    }
    v9 = (unsigned int)v7[16];
    if ( (unsigned int)v9 >= 2 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)a2,
          17,
          68,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
          v7[16]);
    }
    else
    {
      v10 = 5 * v9;
      *(_OWORD *)&v7[v10 + 6] = *(_OWORD *)v4;
      v7[v10 + 10] = *((_DWORD *)v4 + 4);
      BYTE1(v7[5 * v7[16]++ + 6]) = 2;
    }
    goto LABEL_22;
  }
LABEL_23:
  *(_WORD *)(a1 + 584) = 2;
  if ( (*(_BYTE *)(a1 + 536) & 2) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        17,
        70,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    v12 = 3;
    *(_BYTE *)(a1 + 536) = 2;
    if ( v8 != 3 )
      v12 = 1;
    *(_BYTE *)(a1 + 537) = v12;
    *(_WORD *)(a1 + 538) = v8 != 3;
    *(_DWORD *)(a1 + 540) = 12;
    *(_DWORD *)(a1 + 544) = 12;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = "Latched";
    if ( *(_WORD *)(a1 + 538) != 1 )
      v13 = "Level Sensitive";
    v14 = "Sharable";
    if ( *(_BYTE *)(a1 + 537) != 3 )
      v14 = "NonSharable";
    WPP_RECORDER_SF_ssD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v13,
      (unsigned int)"NonSharable",
      71,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      (__int64)v14,
      (__int64)v13,
      *(_DWORD *)(a1 + 544));
  }
  **(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels |= 0x200u;
  return 0;
}

```

## disassembly

```asm
0x14001a7ac  push    rbx
0x14001a7ae  push    rbp
0x14001a7af  push    rsi
0x14001a7b0  push    rdi
0x14001a7b1  push    r12
0x14001a7b3  push    r13
0x14001a7b5  push    r14
0x14001a7b7  push    r15
0x14001a7b9  sub     rsp, 48h
0x14001a7bd  mov     rbx, rcx
0x14001a7c0  test    rdx, rdx
0x14001a7c3  jnz     short loc_14001A7FB
0x14001a7c5  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001a7cc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001a7d3  jz      short loc_14001A804
0x14001a7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a7dc  lea     rsi, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a7e3  lea     r9d, [rdx+42h]
0x14001a7e7  mov     [rsp+88h+var_68], rsi
0x14001a7ec  lea     r8d, [rdx+11h]
0x14001a7f0  mov     rcx, [rcx+40h]
0x14001a7f4  call    WPP_RECORDER_SF_
0x14001a7f9  jmp     short loc_14001A804
0x14001a7fb  lea     rcx, [rdx+4]
0x14001a7ff  test    rcx, rcx
0x14001a802  jnz     short loc_14001A80E
0x14001a804  mov     eax, 0C000009Ah
0x14001a809  jmp     loc_14001AA7E
0x14001a80e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001a815  lea     rbp, [rcx+10h]
0x14001a819  mov     r9d, 2
0x14001a81f  lea     rdi, WPP_RECORDER_INITIALIZED
0x14001a826  xor     r15d, r15d
0x14001a829  lea     rsi, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001a830  or      [rax], r9d
0x14001a833  mov     r13d, [rcx+0Ch]
0x14001a837  lea     r8d, [r9-1]
0x14001a83b  mov     r14, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001a842  mov     byte ptr [r14+50h], 0
0x14001a847  mov     eax, [rcx+4]
0x14001a84a  mov     [r14+14h], eax
0x14001a84e  mov     r12d, [rcx]
0x14001a851  mov     [r14+10h], r12d
0x14001a855  test    r13d, r13d
0x14001a858  jz      loc_14001A989
0x14001a85e  movzx   edx, byte ptr [rbp+0]
0x14001a862  mov     ecx, edx
0x14001a864  sub     ecx, 1
0x14001a867  jz      short loc_14001A8AF
0x14001a869  sub     ecx, 1
0x14001a86c  jz      loc_14001A91B
0x14001a872  cmp     ecx, 1
0x14001a875  jz      short loc_14001A8A8
0x14001a877  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001a87e  jz      loc_14001A979
0x14001a884  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a88b  mov     r9d, 45h ; 'E'
0x14001a891  mov     dword ptr [rsp+88h+var_60], edx
0x14001a895  mov     [rsp+88h+var_68], rsi
0x14001a89a  mov     rcx, [rcx+40h]
0x14001a89e  call    WPP_RECORDER_SF_D
0x14001a8a3  jmp     loc_14001A96F
0x14001a8a8  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, r8b
0x14001a8af  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001a8b6  jz      short loc_14001A8E9
0x14001a8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8bf  mov     r9d, 43h ; 'C'
0x14001a8c5  movzx   eax, word ptr [rbp+2]
0x14001a8c9  mov     dword ptr [rsp+88h+var_60], eax
0x14001a8cd  mov     [rsp+88h+var_68], rsi
0x14001a8d2  mov     rcx, [rcx+40h]
0x14001a8d6  lea     r8d, [r9-35h]
0x14001a8da  call    WPP_RECORDER_SF_D
0x14001a8df  mov     r8d, 1
0x14001a8e5  lea     r9d, [r8+1]
0x14001a8e9  mov     eax, [r14+40h]
0x14001a8ed  cmp     eax, r9d
0x14001a8f0  jnb     short loc_14001A943
0x14001a8f2  movups  xmm0, xmmword ptr [rbp+0]
0x14001a8f6  lea     rcx, [rax+rax*4]
0x14001a8fa  movups  xmmword ptr [r14+rcx*4+18h], xmm0
0x14001a900  mov     eax, [rbp+10h]
0x14001a903  mov     [r14+rcx*4+28h], eax
0x14001a908  mov     eax, [r14+40h]
0x14001a90c  lea     rcx, [rax+rax*4]
0x14001a910  mov     [r14+rcx*4+19h], r9b
0x14001a915  add     [r14+40h], r8d
0x14001a919  jmp     short loc_14001A979
0x14001a91b  movups  xmm0, xmmword ptr [rbp+0]
0x14001a91f  movups  xmmword ptr [rbx+218h], xmm0
0x14001a926  mov     eax, [rbp+10h]
0x14001a929  mov     [rbx+228h], eax
0x14001a92f  mov     eax, 3
0x14001a934  cmp     r12d, eax
0x14001a937  cmovnz  eax, r8d
0x14001a93b  mov     [rbx+219h], al
0x14001a941  jmp     short loc_14001A979
0x14001a943  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001a94a  jz      short loc_14001A979
0x14001a94c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a953  mov     r9d, 44h ; 'D'
0x14001a959  mov     dword ptr [rsp+88h+var_60], eax
0x14001a95d  mov     [rsp+88h+var_68], rsi
0x14001a962  mov     rcx, [rcx+40h]
0x14001a966  lea     r8d, [r9-33h]
0x14001a96a  call    WPP_RECORDER_SF_d
0x14001a96f  mov     r9d, 2
0x14001a975  lea     r8d, [r9-1]
0x14001a979  add     r15d, r8d
0x14001a97c  add     rbp, 14h
0x14001a980  cmp     r15d, r13d
0x14001a983  jb      loc_14001A85E
0x14001a989  mov     [rbx+248h], r9w
0x14001a991  test    [rbx+218h], r9b
0x14001a998  jnz     short loc_14001AA06
0x14001a99a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001a9a1  jz      short loc_14001A9CC
0x14001a9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a9aa  mov     r9d, 46h ; 'F'
0x14001a9b0  mov     [rsp+88h+var_68], rsi
0x14001a9b5  mov     rcx, [rcx+40h]
0x14001a9b9  lea     r8d, [r9-35h]
0x14001a9bd  call    WPP_RECORDER_SF_
0x14001a9c2  mov     r8d, 1
0x14001a9c8  lea     r9d, [r8+1]
0x14001a9cc  mov     eax, 3
0x14001a9d1  mov     [rbx+218h], r9b
0x14001a9d8  cmp     r12d, eax
0x14001a9db  cmovnz  eax, r8d
0x14001a9df  mov     [rbx+219h], al
0x14001a9e5  xor     eax, eax
0x14001a9e7  cmp     r12d, 3
0x14001a9eb  setnz   al
0x14001a9ee  mov     [rbx+21Ah], ax
0x14001a9f5  mov     eax, 0Ch
0x14001a9fa  mov     [rbx+21Ch], eax
0x14001aa00  mov     [rbx+220h], eax
0x14001aa06  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14001aa0d  jz      short loc_14001AA71
0x14001aa0f  cmp     [rbx+21Ah], r8w
0x14001aa17  lea     rcx, aLevelSensitive; "Level Sensitive"
0x14001aa1e  mov     eax, [rbx+220h]
0x14001aa24  lea     r8, aNonsharable; "NonSharable"
0x14001aa2b  mov     [rsp+88h+var_50], eax
0x14001aa2f  lea     rdx, aLatched; "Latched"
0x14001aa36  cmovnz  rdx, rcx
0x14001aa3a  mov     r9d, 47h ; 'G'
0x14001aa40  cmp     byte ptr [rbx+219h], 3
0x14001aa47  lea     rcx, aSharable; "Sharable"
0x14001aa4e  mov     [rsp+88h+var_58], rdx
0x14001aa53  cmovnz  rcx, r8
0x14001aa57  mov     [rsp+88h+var_60], rcx
0x14001aa5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aa63  mov     [rsp+88h+var_68], rsi
0x14001aa68  mov     rcx, [rcx+40h]
0x14001aa6c  call    WPP_RECORDER_SF_ssD
0x14001aa71  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001aa78  bts     dword ptr [rax], 9
0x14001aa7c  xor     eax, eax
0x14001aa7e  add     rsp, 48h
0x14001aa82  pop     r15
0x14001aa84  pop     r14
0x14001aa86  pop     r13
0x14001aa88  pop     r12
0x14001aa8a  pop     rdi
0x14001aa8b  pop     rsi
0x14001aa8c  pop     rbp
0x14001aa8d  pop     rbx
0x14001aa8e  retn
```
