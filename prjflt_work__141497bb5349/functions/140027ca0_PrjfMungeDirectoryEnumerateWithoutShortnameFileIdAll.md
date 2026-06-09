# PrjfMungeDirectoryEnumerateWithoutShortnameFileIdAll

- ea: `0x140027ca0`
- end: `0x140027f5d`
- name: `PrjfMungeDirectoryEnumerateWithoutShortnameFileIdAll`
- size: `701`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, char, unsigned int *, unsigned int, char, unsigned int **, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
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
- `0x140021150`
- `0x140021198`
- `0x140027ca0`

## pseudocode

```c
__int64 __fastcall PrjfMungeDirectoryEnumerateWithoutShortnameFileIdAll(
        __int64 a1,
        __int64 a2,
        _DWORD *a3,
        char a4,
        unsigned int *a5,
        unsigned int a6,
        char a7,
        unsigned int **a8,
        unsigned int *a9)
{
  _DWORD *v10; // r15
  char v11; // r14
  int v12; // esi
  unsigned int v13; // edi
  unsigned int v14; // ebx
  unsigned int v15; // r13d
  __int64 v16; // rdx
  unsigned int *v17; // r14
  unsigned int ULongFromUser; // eax
  unsigned int v19; // eax
  void *v20; // rcx
  void *v21; // rdx
  void *v22; // rcx
  unsigned int v24; // [rsp+B0h] [rbp+8h]

  v10 = a3;
  v11 = a2;
  v12 = a1;
  v13 = 0;
  v14 = 0;
  if ( (_DWORD)a1 != 80 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  if ( v12 == 80 )
  {
    v15 = v10[15];
    v24 = v15 + 96;
    if ( a6 >= v15 + 96 || a6 >= 0x60 && v11 )
    {
      if ( v15 >= a6 - 96 )
        v15 = a6 - 96;
      if ( a7 )
        RtlCopyToUser(a5, v10, 0x60u);
      else
        RtlCopyVolatileMemory(a5, v10, 0x60u);
      if ( v10[17] == -1879048164 )
      {
        v16 = v10[14] & 0xFFFFE9FF;
        if ( (v10[14] & 0xFFFFE9FF) == 0 )
          v16 = 128;
        if ( a7 )
          RtlWriteULongToUser(a5 + 14, v16);
        else
          a5[14] = v16;
        if ( a7 )
          RtlWriteULongToUser(a5 + 17, 0);
        else
          a5[17] = 0;
      }
      if ( a4 )
      {
        v17 = a5 + 14;
        if ( a7 )
          ULongFromUser = RtlReadULongFromUser(a5 + 14);
        else
          ULongFromUser = *v17;
        v19 = ULongFromUser | 0x440000;
        if ( a7 )
          RtlWriteULongToUser(a5 + 14, v19);
        else
          *v17 = v19;
        if ( a7 )
          RtlWriteULong64ToUser(a5 + 12, 0);
        else
          *((_QWORD *)a5 + 6) = 0;
        if ( a7 )
          RtlWriteULong64ToUser(a5 + 18, -1);
        else
          *((_QWORD *)a5 + 9) = -1;
        v20 = a5 + 20;
        if ( a7 )
          RtlSetUserMemory(v20);
        else
          RtlSetVolatileMemory(v20, 255, 0x10u);
      }
      v21 = v10 + 24;
      v22 = a5 + 24;
      if ( a7 )
        RtlCopyToUser(v22, v21, v15);
      else
        RtlCopyVolatileMemory(v22, v21, v15);
      if ( a7 )
        RtlWriteULongToUser(a5, 0);
      else
        *a5 = 0;
      *a8 = a5;
      v14 = v15 + 96;
      if ( v15 + 96 < v24 )
        v13 = -2147483643;
    }
  }
  else
  {
    if ( (BYTE10(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE10(xmmword_14001A3D0) & 4;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        786,
        a2,
        (_DWORD)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        18,
        18,
        (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
        238,
        v12);
    }
    MicrosoftTelemetryAssertTriggeredMsgKM("Unsupported FileInformationClass");
    v13 = -1073741637;
  }
  *a9 = v14;
  return v13;
}

```

## disassembly

```asm
0x140027ca0  mov     [rsp+arg_8], rbx
0x140027ca5  mov     [rsp+arg_10], rsi
0x140027caa  push    rdi
0x140027cab  push    r12
0x140027cad  push    r13
0x140027caf  push    r14
0x140027cb1  push    r15
0x140027cb3  sub     rsp, 80h
0x140027cba  mov     r12b, r9b
0x140027cbd  mov     r15, r8
0x140027cc0  mov     r14b, dl
0x140027cc3  mov     esi, ecx
0x140027cc5  mov     [rsp+0A8h+var_48], 0
0x140027cca  xor     edi, edi
0x140027ccc  xor     ebx, ebx
0x140027cce  cmp     ecx, 50h ; 'P'
0x140027cd1  jz      short loc_140027CD9
0x140027cd3  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140027cd8  nop
0x140027cd9  cmp     esi, 50h ; 'P'
0x140027cdc  jz      loc_140027D69
0x140027ce2  mov     dl, byte ptr cs:xmmword_14001A3D0+0Ah
0x140027ce8  lea     rcx, WPP_RECORDER_INITIALIZED
0x140027cef  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140027cf6  setnz   r8b
0x140027cfa  and     dl, 4
0x140027cfd  jnz     short loc_140027D04
0x140027cff  test    r8b, r8b
0x140027d02  jz      short loc_140027D53
0x140027d04  mov     ecx, 312h
0x140027d09  mov     r9d, 12h
0x140027d0f  mov     [rsp+0A8h+var_58], esi
0x140027d13  mov     [rsp+0A8h+var_60], 4EEh
0x140027d1b  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140027d22  mov     [rsp+0A8h+var_68], rax
0x140027d27  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140027d2e  mov     [rsp+0A8h+var_70], rax
0x140027d33  mov     [rsp+0A8h+var_78], r9w
0x140027d39  mov     [rsp+0A8h+var_80], r9d
0x140027d3e  mov     [rsp+0A8h+var_88], 3
0x140027d43  mov     r9, cs:WPP_GLOBAL_Control
0x140027d4a  mov     r9, [r9+40h]
0x140027d4e  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140027d53  lea     rcx, aUnsupportedFil; "Unsupported FileInformationClass"
0x140027d5a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140027d5f  mov     edi, 0C00000BBh
0x140027d64  jmp     loc_140027F24
0x140027d69  mov     r13d, [r15+3Ch]
0x140027d6d  lea     ecx, [r13+60h]
0x140027d71  mov     [rsp+0A8h+arg_0], ecx
0x140027d78  mov     eax, [rsp+0A8h+arg_28]
0x140027d7f  cmp     eax, ecx
0x140027d81  jnb     short loc_140027D95
0x140027d83  cmp     eax, 60h ; '`'
0x140027d86  jb      loc_140027F28
0x140027d8c  test    r14b, r14b
0x140027d8f  jz      loc_140027F28
0x140027d95  add     eax, 0FFFFFFA0h
0x140027d98  cmp     r13d, eax
0x140027d9b  cmovnb  r13d, eax
0x140027d9f  mov     [rsp+0A8h+var_48], 1
0x140027da4  mov     sil, [rsp+0A8h+arg_30]
0x140027dac  mov     r8d, 60h ; '`'; Size
0x140027db2  mov     rdx, r15; Src
0x140027db5  mov     rbx, [rsp+0A8h+arg_20]
0x140027dbd  mov     rcx, rbx; void *
0x140027dc0  test    sil, sil
0x140027dc3  jz      short loc_140027DCC
0x140027dc5  call    RtlCopyToUser
0x140027dca  jmp     short loc_140027DD1
0x140027dcc  call    RtlCopyVolatileMemory
0x140027dd1  cmp     dword ptr [r15+44h], 9000001Ch
0x140027dd9  jnz     short loc_140027E3A
0x140027ddb  mov     edx, [r15+38h]
0x140027ddf  mov     [rsp+0A8h+var_40], edx
0x140027de3  mov     eax, edx
0x140027de5  btr     eax, 0Ah
0x140027de9  mov     [rsp+0A8h+var_40], eax
0x140027ded  mov     eax, edx
0x140027def  and     eax, 0FFFFEBFFh
0x140027df4  mov     [rsp+0A8h+var_40], eax
0x140027df8  and     edx, 0FFFFE9FFh
0x140027dfe  mov     [rsp+0A8h+var_40], edx
0x140027e02  mov     eax, 80h
0x140027e07  cmovz   edx, eax
0x140027e0a  mov     [rsp+0A8h+var_40], edx
0x140027e0e  test    sil, sil
0x140027e11  jz      short loc_140027E1E
0x140027e13  lea     rcx, [rbx+38h]
0x140027e17  call    RtlWriteULongToUser
0x140027e1c  jmp     short loc_140027E21
0x140027e1e  mov     [rbx+38h], edx
0x140027e21  test    sil, sil
0x140027e24  jz      short loc_140027E33
0x140027e26  xor     edx, edx
0x140027e28  lea     rcx, [rbx+44h]
0x140027e2c  call    RtlWriteULongToUser
0x140027e31  jmp     short loc_140027E3A
0x140027e33  mov     dword ptr [rbx+44h], 0
0x140027e3a  test    r12b, r12b
0x140027e3d  jz      loc_140027ECA
0x140027e43  lea     r14, [rbx+38h]
0x140027e47  test    sil, sil
0x140027e4a  jz      short loc_140027E56
0x140027e4c  mov     rcx, r14
0x140027e4f  call    RtlReadULongFromUser
0x140027e54  jmp     short loc_140027E59
0x140027e56  mov     eax, [r14]
0x140027e59  or      eax, 440000h
0x140027e5e  test    sil, sil
0x140027e61  jz      short loc_140027E6F
0x140027e63  mov     edx, eax
0x140027e65  mov     rcx, r14
0x140027e68  call    RtlWriteULongToUser
0x140027e6d  jmp     short loc_140027E72
0x140027e6f  mov     [r14], eax
0x140027e72  test    sil, sil
0x140027e75  jz      short loc_140027E84
0x140027e77  xor     edx, edx
0x140027e79  lea     rcx, [rbx+30h]
0x140027e7d  call    RtlWriteULong64ToUser
0x140027e82  jmp     short loc_140027E8C
0x140027e84  mov     qword ptr [rbx+30h], 0
0x140027e8c  test    sil, sil
0x140027e8f  jz      short loc_140027EA0
0x140027e91  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140027e95  lea     rcx, [rbx+48h]
0x140027e99  call    RtlWriteULong64ToUser
0x140027e9e  jmp     short loc_140027EA8
0x140027ea0  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x140027ea8  lea     rcx, [rbx+50h]; void *
0x140027eac  mov     r8d, 10h; Size
0x140027eb2  test    sil, sil
0x140027eb5  jz      short loc_140027EC0
0x140027eb7  mov     dl, 0FFh
0x140027eb9  call    RtlSetUserMemory
0x140027ebe  jmp     short loc_140027ECA
0x140027ec0  mov     edx, 0FFh; Val
0x140027ec5  call    RtlSetVolatileMemory
0x140027eca  lea     rdx, [r15+60h]; Src
0x140027ece  lea     rcx, [rbx+60h]; void *
0x140027ed2  mov     r8d, r13d; Size
0x140027ed5  test    sil, sil
0x140027ed8  jz      short loc_140027EE1
0x140027eda  call    RtlCopyToUser
0x140027edf  jmp     short loc_140027EE6
0x140027ee1  call    RtlCopyVolatileMemory
0x140027ee6  test    sil, sil
0x140027ee9  jz      short loc_140027EF7
0x140027eeb  xor     edx, edx
0x140027eed  mov     rcx, rbx
0x140027ef0  call    RtlWriteULongToUser
0x140027ef5  jmp     short loc_140027EFD
0x140027ef7  mov     dword ptr [rbx], 0
0x140027efd  mov     rax, [rsp+0A8h+arg_38]
0x140027f05  mov     [rax], rbx
0x140027f08  mov     [rsp+0A8h+var_48], 0
0x140027f0d  lea     ebx, [r13+60h]
0x140027f11  mov     [rsp+0A8h+var_34], ebx
0x140027f15  mov     eax, 80000005h
0x140027f1a  cmp     ebx, [rsp+0A8h+arg_0]
0x140027f21  cmovb   edi, eax
0x140027f24  mov     [rsp+0A8h+var_38], edi
0x140027f28  mov     rax, [rsp+0A8h+arg_40]
0x140027f30  mov     [rax], ebx
0x140027f32  jmp     short loc_140027F3D
0x140027f34  mov     edi, 0C00000E8h
0x140027f39  mov     [rsp+0A8h+var_38], edi
0x140027f3d  mov     eax, edi
0x140027f3f  lea     r11, [rsp+0A8h+var_28]
0x140027f47  mov     rbx, [r11+38h]
0x140027f4b  mov     rsi, [r11+40h]
0x140027f4f  mov     rsp, r11
0x140027f52  pop     r15
0x140027f54  pop     r14
0x140027f56  pop     r13
0x140027f58  pop     r12
0x140027f5a  pop     rdi
0x140027f5b  retn
0x14004728f  push    rbp
0x140047291  sub     rsp, 60h
0x140047295  mov     rbp, rdx
0x140047298  xor     eax, eax
0x14004729a  cmp     [rbp+60h], al
0x14004729d  setnz   al
0x1400472a0  add     rsp, 60h
0x1400472a4  pop     rbp
0x1400472a5  retn
```
