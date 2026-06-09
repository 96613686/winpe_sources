# PrjfMungeDirectoryEnumerateWithShortnameFileIdAll

- ea: `0x140026d94`
- end: `0x14002713c`
- name: `PrjfMungeDirectoryEnumerateWithShortnameFileIdAll`
- size: `936`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, char, _DWORD *, unsigned int, char, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1400287d4`

## callees

- `0x14000b1a0`
- `0x14000b1d0`
- `0x14000ba50`
- `0x14000ba70`
- `0x14000d128`
- `0x140021008`
- `0x14002106c`
- `0x1400210a8`
- `0x140021108`
- `0x140021150`
- `0x140021198`
- `0x140026d94`

## pseudocode

```c
__int64 __fastcall PrjfMungeDirectoryEnumerateWithShortnameFileIdAll(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        _DWORD *a6,
        unsigned int a7,
        char a8,
        _QWORD *a9,
        unsigned int *a10)
{
  __int64 v11; // r14
  char v12; // r15
  int v13; // edi
  unsigned int v14; // esi
  unsigned int v15; // ebx
  unsigned int v16; // r13d
  __int64 v17; // rdx
  int v18; // r8d
  char v19; // al
  char *v20; // rcx
  size_t v21; // r8
  void *v22; // rdx
  void *v23; // rcx
  _UNKNOWN **v24; // rcx
  __int64 v25; // rdx
  unsigned int *v26; // r15
  unsigned int ULongFromUser; // eax
  unsigned int v28; // eax
  void *v29; // rcx
  void *v30; // rdx
  void *v31; // rcx
  unsigned int v33; // [rsp+B0h] [rbp+8h]

  v11 = a3;
  v12 = a2;
  v13 = a1;
  v14 = 0;
  v15 = 0;
  if ( (_DWORD)a1 != 81 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( v13 != 81 )
  {
    if ( (BYTE10(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE10(xmmword_14001A3D0) & 4;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        786,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        18,
        20,
        (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
        163,
        v13);
    }
    MicrosoftTelemetryAssertTriggeredMsgKM("Invalid FileInformationClass");
    v14 = -1073741637;
    goto LABEL_65;
  }
  v16 = *(_DWORD *)(v11 + 60);
  v33 = v16 + 122;
  if ( a7 < v16 + 122 && (a7 < 0x7A || !v12) )
    goto LABEL_65;
  if ( v16 >= a7 - 122 )
    v16 = a7 - 122;
  if ( a8 )
    RtlCopyToUser(a6, (void *)v11, 0x60u);
  else
    RtlCopyVolatileMemory(a6, (const void *)v11, 0x60u);
  if ( a4 )
  {
    v19 = *(_BYTE *)(v11 + 96);
    if ( (unsigned __int8)v19 <= 0x18u )
    {
      v20 = (char *)(a6 + 24);
      if ( a8 )
      {
        LOBYTE(v17) = *(_BYTE *)(v11 + 96);
        RtlWriteUCharToUser(v20, v17);
      }
      else
      {
        *v20 = v19;
      }
      v21 = *(char *)(v11 + 96);
      v22 = (void *)(v11 + 98);
      v23 = (char *)a6 + 98;
      if ( a8 )
        RtlCopyToUser(v23, v22, v21);
      else
        RtlCopyVolatileMemory(v23, v22, v21);
      goto LABEL_32;
    }
    v24 = &WPP_RECORDER_INITIALIZED;
    LOBYTE(v17) = BYTE2(xmmword_14001A3D0) & 4;
    if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        530,
        v17,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        18,
        19,
        (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
        120,
        v19);
    }
    if ( *(_BYTE *)(v11 + 96) > 0x18u )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v24, v17);
  }
  if ( a8 )
    RtlWriteUCharToUser(a6 + 24, 0);
  else
    *((_BYTE *)a6 + 96) = 0;
LABEL_32:
  if ( *(_DWORD *)(v11 + 68) == -1879048164 )
  {
    v25 = *(_DWORD *)(v11 + 56) & 0xFFFFE9FF;
    if ( (*(_DWORD *)(v11 + 56) & 0xFFFFE9FF) == 0 )
      v25 = 128;
    if ( a8 )
      RtlWriteULongToUser(a6 + 14, v25);
    else
      a6[14] = v25;
    if ( a8 )
      RtlWriteULongToUser(a6 + 17, 0);
    else
      a6[17] = 0;
  }
  if ( a5 )
  {
    v26 = a6 + 14;
    if ( a8 )
      ULongFromUser = RtlReadULongFromUser(a6 + 14);
    else
      ULongFromUser = *v26;
    v28 = ULongFromUser | 0x440000;
    if ( a8 )
      RtlWriteULongToUser(a6 + 14, v28);
    else
      *v26 = v28;
    if ( a8 )
      RtlWriteULong64ToUser(a6 + 12, 0);
    else
      *((_QWORD *)a6 + 6) = 0;
    if ( a8 )
      RtlWriteULong64ToUser(a6 + 18, -1);
    else
      *((_QWORD *)a6 + 9) = -1;
    v29 = a6 + 20;
    if ( a8 )
      RtlSetUserMemory(v29);
    else
      RtlSetVolatileMemory(v29, 255, 0x10u);
  }
  v30 = (void *)(v11 + 122);
  v31 = (char *)a6 + 122;
  if ( a8 )
    RtlCopyToUser(v31, v30, v16);
  else
    RtlCopyVolatileMemory(v31, v30, v16);
  if ( a8 )
    RtlWriteULongToUser(a6, 0);
  else
    *a6 = 0;
  *a9 = a6;
  v15 = v16 + 122;
  if ( v16 + 122 < v33 )
    v14 = -2147483643;
LABEL_65:
  *a10 = v15;
  return v14;
}

```

## disassembly

```asm
0x140026d94  mov     [rsp+arg_8], rbx
0x140026d99  mov     [rsp+arg_10], rsi
0x140026d9e  push    rdi
0x140026d9f  push    r12
0x140026da1  push    r13
0x140026da3  push    r14
0x140026da5  push    r15
0x140026da7  sub     rsp, 80h
0x140026dae  mov     r12b, r9b
0x140026db1  mov     r14, r8
0x140026db4  mov     r15b, dl
0x140026db7  mov     edi, ecx
0x140026db9  mov     [rsp+0A8h+var_48], 0
0x140026dbe  xor     esi, esi
0x140026dc0  xor     ebx, ebx
0x140026dc2  cmp     ecx, 51h ; 'Q'
0x140026dc5  jz      short loc_140026DCD
0x140026dc7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140026dcc  nop
0x140026dcd  cmp     edi, 51h ; 'Q'
0x140026dd0  jz      loc_140026E60
0x140026dd6  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x140026ddc  lea     rcx, WPP_RECORDER_INITIALIZED
0x140026de3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140026dea  setnz   r8b
0x140026dee  and     dl, 4
0x140026df1  jnz     short loc_140026DF8
0x140026df3  test    r8b, r8b
0x140026df6  jz      short loc_140026E4A
0x140026df8  mov     ecx, 312h
0x140026dfd  mov     r9d, 14h
0x140026e03  mov     [rsp+0A8h+var_58], edi
0x140026e07  mov     [rsp+0A8h+var_60], 5A3h
0x140026e0f  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140026e16  mov     [rsp+0A8h+var_68], rax
0x140026e1b  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140026e22  mov     [rsp+0A8h+var_70], rax
0x140026e27  mov     [rsp+0A8h+var_78], r9w
0x140026e2d  mov     [rsp+0A8h+var_80], 12h
0x140026e35  mov     [rsp+0A8h+var_88], 3
0x140026e3a  mov     r9, cs:WPP_GLOBAL_Control
0x140026e41  mov     r9, [r9+40h]
0x140026e45  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140026e4a  lea     rcx, aInvalidFileinf; "Invalid FileInformationClass"
0x140026e51  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140026e56  mov     esi, 0C00000BBh
0x140026e5b  jmp     loc_140027103
0x140026e60  mov     r13d, [r14+3Ch]
0x140026e64  lea     ecx, [r13+7Ah]
0x140026e68  mov     [rsp+0A8h+arg_0], ecx
0x140026e6f  mov     eax, [rsp+0A8h+arg_30]
0x140026e76  cmp     eax, ecx
0x140026e78  jnb     short loc_140026E8C
0x140026e7a  cmp     eax, 7Ah ; 'z'
0x140026e7d  jb      loc_140027107
0x140026e83  test    r15b, r15b
0x140026e86  jz      loc_140027107
0x140026e8c  add     eax, 0FFFFFF86h
0x140026e8f  cmp     r13d, eax
0x140026e92  cmovnb  r13d, eax
0x140026e96  mov     [rsp+0A8h+var_48], 1
0x140026e9b  mov     dil, [rsp+0A8h+arg_38]
0x140026ea3  mov     r8d, 60h ; '`'; Size
0x140026ea9  mov     rdx, r14; Src
0x140026eac  mov     rbx, [rsp+0A8h+arg_28]
0x140026eb4  mov     rcx, rbx; void *
0x140026eb7  test    dil, dil
0x140026eba  jz      short loc_140026EC3
0x140026ebc  call    RtlCopyToUser
0x140026ec1  jmp     short loc_140026EC8
0x140026ec3  call    RtlCopyVolatileMemory
0x140026ec8  test    r12b, r12b
0x140026ecb  jz      loc_140026F9C
0x140026ed1  movsx   eax, byte ptr [r14+60h]
0x140026ed6  cmp     al, 18h
0x140026ed8  ja      short loc_140026F17
0x140026eda  lea     rcx, [rbx+60h]
0x140026ede  xor     r12d, r12d
0x140026ee1  test    dil, dil
0x140026ee4  jz      short loc_140026EEF
0x140026ee6  mov     dl, al
0x140026ee8  call    RtlWriteUCharToUser
0x140026eed  jmp     short loc_140026EF1
0x140026eef  mov     [rcx], al
0x140026ef1  movsx   r8, byte ptr [r14+60h]; Size
0x140026ef6  lea     rdx, [r14+62h]; Src
0x140026efa  lea     rcx, [rbx+62h]; void *
0x140026efe  test    dil, dil
0x140026f01  jz      short loc_140026F0D
0x140026f03  call    RtlCopyToUser
0x140026f08  jmp     loc_140026FB5
0x140026f0d  call    RtlCopyVolatileMemory
0x140026f12  jmp     loc_140026FB5
0x140026f17  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140026f1d  lea     rcx, WPP_RECORDER_INITIALIZED
0x140026f24  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140026f2b  setnz   r8b
0x140026f2f  xor     r12d, r12d
0x140026f32  and     dl, 4
0x140026f35  jnz     short loc_140026F3C
0x140026f37  test    r8b, r8b
0x140026f3a  jz      short loc_140026F8E
0x140026f3c  mov     ecx, 212h
0x140026f41  mov     r9d, 13h
0x140026f47  mov     [rsp+0A8h+var_58], eax
0x140026f4b  mov     [rsp+0A8h+var_60], 578h
0x140026f53  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140026f5a  mov     [rsp+0A8h+var_68], rax
0x140026f5f  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140026f66  mov     [rsp+0A8h+var_70], rax
0x140026f6b  mov     [rsp+0A8h+var_78], r9w
0x140026f71  mov     [rsp+0A8h+var_80], 12h
0x140026f79  mov     [rsp+0A8h+var_88], 2
0x140026f7e  mov     r9, cs:WPP_GLOBAL_Control
0x140026f85  mov     r9, [r9+40h]
0x140026f89  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140026f8e  cmp     byte ptr [r14+60h], 18h
0x140026f93  jbe     short loc_140026F9F
0x140026f95  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140026f9a  jmp     short loc_140026F9F
0x140026f9c  xor     r12d, r12d
0x140026f9f  test    dil, dil
0x140026fa2  jz      short loc_140026FB1
0x140026fa4  xor     edx, edx
0x140026fa6  lea     rcx, [rbx+60h]
0x140026faa  call    RtlWriteUCharToUser
0x140026faf  jmp     short loc_140026FB5
0x140026fb1  mov     [rbx+60h], r12b
0x140026fb5  cmp     dword ptr [r14+44h], 9000001Ch
0x140026fbd  jnz     short loc_14002701B
0x140026fbf  mov     edx, [r14+38h]
0x140026fc3  mov     [rsp+0A8h+var_40], edx
0x140026fc7  mov     eax, edx
0x140026fc9  btr     eax, 0Ah
0x140026fcd  mov     [rsp+0A8h+var_40], eax
0x140026fd1  mov     eax, edx
0x140026fd3  and     eax, 0FFFFEBFFh
0x140026fd8  mov     [rsp+0A8h+var_40], eax
0x140026fdc  and     edx, 0FFFFE9FFh
0x140026fe2  mov     [rsp+0A8h+var_40], edx
0x140026fe6  mov     eax, 80h
0x140026feb  cmovz   edx, eax
0x140026fee  mov     [rsp+0A8h+var_40], edx
0x140026ff2  test    dil, dil
0x140026ff5  jz      short loc_140027002
0x140026ff7  lea     rcx, [rbx+38h]
0x140026ffb  call    RtlWriteULongToUser
0x140027000  jmp     short loc_140027005
0x140027002  mov     [rbx+38h], edx
0x140027005  test    dil, dil
0x140027008  jz      short loc_140027017
0x14002700a  xor     edx, edx
0x14002700c  lea     rcx, [rbx+44h]
0x140027010  call    RtlWriteULongToUser
0x140027015  jmp     short loc_14002701B
0x140027017  mov     [rbx+44h], r12d
0x14002701b  cmp     [rsp+0A8h+arg_20], r12b
0x140027023  jz      loc_1400270AC
0x140027029  lea     r15, [rbx+38h]
0x14002702d  test    dil, dil
0x140027030  jz      short loc_14002703C
0x140027032  mov     rcx, r15
0x140027035  call    RtlReadULongFromUser
0x14002703a  jmp     short loc_14002703F
0x14002703c  mov     eax, [r15]
0x14002703f  or      eax, 440000h
0x140027044  test    dil, dil
0x140027047  jz      short loc_140027055
0x140027049  mov     edx, eax
0x14002704b  mov     rcx, r15
0x14002704e  call    RtlWriteULongToUser
0x140027053  jmp     short loc_140027058
0x140027055  mov     [r15], eax
0x140027058  test    dil, dil
0x14002705b  jz      short loc_14002706A
0x14002705d  xor     edx, edx
0x14002705f  lea     rcx, [rbx+30h]
0x140027063  call    RtlWriteULong64ToUser
0x140027068  jmp     short loc_14002706E
0x14002706a  mov     [rbx+30h], r12
0x14002706e  test    dil, dil
0x140027071  jz      short loc_140027082
0x140027073  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140027077  lea     rcx, [rbx+48h]
0x14002707b  call    RtlWriteULong64ToUser
0x140027080  jmp     short loc_14002708A
0x140027082  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x14002708a  lea     rcx, [rbx+50h]; void *
0x14002708e  mov     r8d, 10h; Size
0x140027094  test    dil, dil
0x140027097  jz      short loc_1400270A2
0x140027099  mov     dl, 0FFh
0x14002709b  call    RtlSetUserMemory
0x1400270a0  jmp     short loc_1400270AC
0x1400270a2  mov     edx, 0FFh; Val
0x1400270a7  call    RtlSetVolatileMemory
0x1400270ac  lea     rdx, [r14+7Ah]; Src
0x1400270b0  lea     rcx, [rbx+7Ah]; void *
0x1400270b4  mov     r8d, r13d; Size
0x1400270b7  test    dil, dil
0x1400270ba  jz      short loc_1400270C3
0x1400270bc  call    RtlCopyToUser
0x1400270c1  jmp     short loc_1400270C8
0x1400270c3  call    RtlCopyVolatileMemory
0x1400270c8  test    dil, dil
0x1400270cb  jz      short loc_1400270D9
0x1400270cd  xor     edx, edx
0x1400270cf  mov     rcx, rbx
0x1400270d2  call    RtlWriteULongToUser
0x1400270d7  jmp     short loc_1400270DC
0x1400270d9  mov     [rbx], r12d
0x1400270dc  mov     rax, [rsp+0A8h+arg_40]
0x1400270e4  mov     [rax], rbx
0x1400270e7  mov     [rsp+0A8h+var_48], r12b
0x1400270ec  lea     ebx, [r13+7Ah]
0x1400270f0  mov     [rsp+0A8h+var_30], ebx
0x1400270f4  mov     eax, 80000005h
0x1400270f9  cmp     ebx, [rsp+0A8h+arg_0]
0x140027100  cmovb   esi, eax
0x140027103  mov     [rsp+0A8h+var_38], esi
0x140027107  mov     rax, [rsp+0A8h+arg_48]
0x14002710f  mov     [rax], ebx
0x140027111  jmp     short loc_14002711C
0x140027113  mov     esi, 0C00000E8h
0x140027118  mov     [rsp+0A8h+var_38], esi
0x14002711c  mov     eax, esi
0x14002711e  lea     r11, [rsp+0A8h+var_28]
0x140027126  mov     rbx, [r11+38h]
0x14002712a  mov     rsi, [r11+40h]
0x14002712e  mov     rsp, r11
0x140027131  pop     r15
0x140027133  pop     r14
0x140027135  pop     r13
0x140027137  pop     r12
0x140027139  pop     rdi
0x14002713a  retn
0x1400471ff  push    rbp
0x140047201  sub     rsp, 60h
0x140047205  mov     rbp, rdx
0x140047208  xor     eax, eax
0x14004720a  cmp     [rbp+60h], al
0x14004720d  jz      short loc_14004721E
0x14004720f  cmp     [rbp+0E8h], al
0x140047215  setnz   al
0x140047218  mov     [rbp+74h], eax
0x14004721b  mov     eax, [rbp+74h]
0x14004721e  add     rsp, 60h
0x140047222  pop     rbp
0x140047223  retn
```
