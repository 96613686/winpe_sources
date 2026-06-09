# DhcpComputeRetrySleepInterval

- ea: `0x18001ef2c`
- end: `0x18001f0cf`
- name: `DhcpComputeRetrySleepInterval`
- size: `419`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f5f0`
- `0x18001f8e0`

## callees

- `0x1800141fc`
- `0x18001ef2c`
- `0x18001f120`
- `0x18001fe18`
- `0x180020734`
- `0x180043e2c`
- `0x18004d1e0`
- `0x18004d958`
- `0x18004d9e8`

## pseudocode

```c
__int64 __fastcall DhcpComputeRetrySleepInterval(__int64 a1, int a2)
{
  unsigned int v2; // edi
  int v5; // edx
  __int64 v6; // rcx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  unsigned int v14; // eax
  unsigned int v16; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  v16 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_qD(1028, 15, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, *(_QWORD *)(a1 + 24), a2);
  switch ( a2 )
  {
    case 3:
      goto LABEL_35;
    case 6:
LABEL_34:
      v2 = -1;
      goto LABEL_37;
    case 9:
LABEL_35:
      v14 = CalculateTimeToSleep(a1);
LABEL_36:
      v2 = v14;
      goto LABEL_37;
    case 12:
    case 15:
      goto LABEL_34;
    case 24:
      goto LABEL_37;
    case 25:
      if ( !g_fUseIpv6OnlyPreferred )
        goto LABEL_37;
      v14 = CalculateSleepDurationForIpv6OnlyConfig(a1);
      goto LABEL_36;
  }
  if ( !(unsigned int)DhcpIsMachineInModernStandby() )
  {
    if ( a2 > 10 )
    {
      v11 = a2 - 14;
      if ( !v11 )
        goto LABEL_37;
      v12 = v11 - v5;
      if ( !v12 )
      {
        v2 = 1;
        goto LABEL_37;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
LABEL_29:
        v2 = 6;
        goto LABEL_37;
      }
      if ( v13 == 1 )
      {
        v2 = 300;
        goto LABEL_37;
      }
LABEL_27:
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_(1028, 17, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids);
      goto LABEL_29;
    }
    if ( a2 != 10 )
    {
      v7 = a2 - 2;
      if ( !v7 )
        goto LABEL_20;
      v8 = v7 - 2;
      if ( !v8 || (v9 = v8 - 1) == 0 )
      {
        DhcpV4ComputeInitRetryInterval(v6, &v16);
        v2 = v16;
        goto LABEL_37;
      }
      v10 = v9 - 2;
      if ( !v10 )
      {
        v2 = 10;
        goto LABEL_37;
      }
      if ( v10 == 1 )
      {
LABEL_20:
        v2 = 120;
        goto LABEL_37;
      }
      goto LABEL_27;
    }
    goto LABEL_35;
  }
  v2 = 300 * DhcpStandbyGetFailureCount(a1 + 2016);
  if ( (xmmword_1800616A0 & 0x10) == 0 )
    return v2;
  WPP_SF_d(1028, 16, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, v2);
LABEL_37:
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 18, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18001ef2c  mov     rax, rsp
0x18001ef2f  mov     [rax+8], rbx
0x18001ef33  mov     [rax+18h], rsi
0x18001ef37  push    rdi
0x18001ef38  sub     rsp, 30h
0x18001ef3c  xor     edi, edi
0x18001ef3e  mov     ebx, edx
0x18001ef40  mov     [rax+10h], edi
0x18001ef43  mov     rsi, rcx
0x18001ef46  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001ef4d  jz      short loc_18001EF6A
0x18001ef4f  mov     r9, [rsi+18h]
0x18001ef53  lea     edx, [rdi+0Fh]
0x18001ef56  mov     ecx, 404h
0x18001ef5b  mov     [rax-18h], ebx
0x18001ef5e  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001ef65  call    WPP_SF_qD
0x18001ef6a  mov     ecx, ebx
0x18001ef6c  mov     edx, 3
0x18001ef71  sub     ecx, edx
0x18001ef73  jz      loc_18001F091
0x18001ef79  sub     ecx, edx
0x18001ef7b  jz      loc_18001F08C
0x18001ef81  sub     ecx, edx
0x18001ef83  jz      loc_18001F091
0x18001ef89  sub     ecx, edx
0x18001ef8b  jz      loc_18001F08C
0x18001ef91  sub     ecx, edx
0x18001ef93  jz      loc_18001F08C
0x18001ef99  sub     ecx, 9
0x18001ef9c  jz      loc_18001F09B
0x18001efa2  cmp     ecx, 1
0x18001efa5  jz      loc_18001F07A
0x18001efab  call    DhcpIsMachineInModernStandby
0x18001efb0  test    eax, eax
0x18001efb2  jz      short loc_18001EFF1
0x18001efb4  lea     rcx, [rsi+7E0h]
0x18001efbb  call    DhcpStandbyGetFailureCount
0x18001efc0  imul    edi, eax, 12Ch
0x18001efc6  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001efcd  jz      loc_18001F0BD
0x18001efd3  mov     edx, 10h
0x18001efd8  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001efdf  mov     ecx, 404h
0x18001efe4  mov     r9d, edi
0x18001efe7  call    WPP_SF_d
0x18001efec  jmp     loc_18001F09B
0x18001eff1  cmp     ebx, 0Ah
0x18001eff4  jg      short loc_18001F033
0x18001eff6  jz      loc_18001F091
0x18001effc  sub     ebx, 2
0x18001efff  jz      short loc_18001F015
0x18001f001  sub     ebx, 2
0x18001f004  jz      short loc_18001F023
0x18001f006  sub     ebx, 1
0x18001f009  jz      short loc_18001F023
0x18001f00b  sub     ebx, 2
0x18001f00e  jz      short loc_18001F01C
0x18001f010  cmp     ebx, 1
0x18001f013  jnz     short loc_18001F046
0x18001f015  mov     edi, 78h ; 'x'
0x18001f01a  jmp     short loc_18001F09B
0x18001f01c  mov     edi, 0Ah
0x18001f021  jmp     short loc_18001F09B
0x18001f023  lea     rdx, [rsp+38h+arg_8]
0x18001f028  call    DhcpV4ComputeInitRetryInterval
0x18001f02d  mov     edi, [rsp+38h+arg_8]
0x18001f031  jmp     short loc_18001F09B
0x18001f033  sub     ebx, 0Eh
0x18001f036  jz      short loc_18001F09B
0x18001f038  sub     ebx, edx
0x18001f03a  jz      short loc_18001F073
0x18001f03c  sub     ebx, 1
0x18001f03f  jz      short loc_18001F065
0x18001f041  cmp     ebx, 1
0x18001f044  jz      short loc_18001F06C
0x18001f046  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001f04d  jz      short loc_18001F065
0x18001f04f  mov     edx, 11h
0x18001f054  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001f05b  mov     ecx, 404h
0x18001f060  call    WPP_SF_
0x18001f065  mov     edi, 6
0x18001f06a  jmp     short loc_18001F09B
0x18001f06c  mov     edi, 12Ch
0x18001f071  jmp     short loc_18001F09B
0x18001f073  mov     edi, 1
0x18001f078  jmp     short loc_18001F09B
0x18001f07a  cmp     cs:g_fUseIpv6OnlyPreferred, edi
0x18001f080  jz      short loc_18001F09B
0x18001f082  mov     rcx, rsi
0x18001f085  call    CalculateSleepDurationForIpv6OnlyConfig
0x18001f08a  jmp     short loc_18001F099
0x18001f08c  or      edi, 0FFFFFFFFh
0x18001f08f  jmp     short loc_18001F09B
0x18001f091  mov     rcx, rsi
0x18001f094  call    CalculateTimeToSleep
0x18001f099  mov     edi, eax
0x18001f09b  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001f0a2  jz      short loc_18001F0BD
0x18001f0a4  mov     edx, 12h
0x18001f0a9  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001f0b0  mov     ecx, 404h
0x18001f0b5  mov     r9d, edi
0x18001f0b8  call    WPP_SF_d
0x18001f0bd  mov     rbx, [rsp+38h+arg_0]
0x18001f0c2  mov     eax, edi
0x18001f0c4  mov     rsi, [rsp+38h+arg_10]
0x18001f0c9  add     rsp, 30h
0x18001f0cd  pop     rdi
0x18001f0ce  retn
```
