# PrjfSendQueryFileNameCommand

- ea: `0x140034e88`
- end: `0x140035057`
- name: `PrjfSendQueryFileNameCommand`
- size: `463`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, __int128 *, unsigned __int16 *, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140039de8`

## callees

- `0x14000d754`
- `0x140032fd8`
- `0x140033bd0`
- `0x140034e88`
- `0x14003a5cc`

## pseudocode

```c
__int64 __fastcall PrjfSendQueryFileNameCommand(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        __int128 *a3,
        unsigned __int16 *a4,
        _BYTE *a5)
{
  __int128 v5; // xmm0
  int v9; // edx
  int v10; // ebx
  int v11; // r8d
  int v12; // edx
  int v13; // r8d
  int v15; // [rsp+60h] [rbp-20h] BYREF
  int v16; // [rsp+64h] [rbp-1Ch] BYREF
  PVOID Entry; // [rsp+68h] [rbp-18h] BYREF
  __int128 v18; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+B0h] [rbp+30h] BYREF

  v5 = *a3;
  Entry = 0;
  v19 = 0;
  v16 = 0;
  v15 = 4;
  v18 = v5;
  v10 = PrjfPrepareCommandForFilePath(a4, &v18, 5, 0, 0, 0, 0, &Entry, &v19);
  if ( v10 >= 0 )
  {
    v10 = PrjfSendCommand(a1, a2, Entry, 0, (__int64)&v16, (__int64)&v15);
    if ( v10 == -1073741772 )
    {
      v10 = 0;
      *a5 = 0;
    }
    else if ( v10 >= 0 )
    {
      *a5 = 1;
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
           || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        163,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        120,
        v10,
        (__int64)a4);
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      526,
      v9,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      162,
      (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      98,
      v10,
      (__int64)a4);
  }
  if ( Entry )
    PrjfFreeCommandBuffer(Entry);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140034e88  mov     r11, rsp
0x140034e8b  mov     [r11+8], rbx
0x140034e8f  mov     [r11+10h], rsi
0x140034e93  push    rbp
0x140034e94  push    r14
0x140034e96  push    r15
0x140034e98  mov     rbp, rsp
0x140034e9b  sub     rsp, 80h
0x140034ea2  movaps  xmm0, xmmword ptr [r8]
0x140034ea6  lea     rax, [rbp+arg_10]
0x140034eaa  mov     [r11-58h], rax
0x140034eae  mov     r15, r9
0x140034eb1  xor     r9d, r9d
0x140034eb4  mov     [rbp+Entry], 0
0x140034ebc  lea     rax, [rbp+Entry]
0x140034ec0  mov     [rbp+arg_10], 0
0x140034ec7  mov     [r11-60h], rax
0x140034ecb  mov     rsi, rdx
0x140034ece  mov     qword ptr [r11-68h], 0
0x140034ed6  lea     rdx, [rbp+var_10]
0x140034eda  mov     r14, rcx
0x140034edd  mov     qword ptr [r11-70h], 0
0x140034ee5  lea     r8d, [r9+5]
0x140034ee9  mov     qword ptr [r11-78h], 0
0x140034ef1  mov     rcx, r15
0x140034ef4  mov     [rbp+var_1C], 0
0x140034efb  mov     [rbp+var_20], 4
0x140034f02  movdqa  [rbp+var_10], xmm0
0x140034f07  call    PrjfPrepareCommandForFilePath
0x140034f0c  mov     ebx, eax
0x140034f0e  test    eax, eax
0x140034f10  jns     short loc_140034F8F
0x140034f12  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034f18  lea     rax, WPP_RECORDER_INITIALIZED
0x140034f1f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034f26  setnz   r8b
0x140034f2a  and     dl, 40h
0x140034f2d  jnz     short loc_140034F38
0x140034f2f  test    r8b, r8b
0x140034f32  jz      loc_140035028
0x140034f38  mov     [rsp+80h+var_28], r15
0x140034f3d  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034f44  mov     [rsp+80h+var_30], ebx
0x140034f48  mov     [rsp+80h+var_38], 1262h
0x140034f50  mov     [rsp+80h+var_40], rax
0x140034f55  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034f5c  mov     [rsp+80h+var_48], rax
0x140034f61  mov     [rsp+80h+var_50], 0A2h
0x140034f68  mov     r9, cs:WPP_GLOBAL_Control
0x140034f6f  mov     ecx, 20Eh
0x140034f74  mov     dword ptr [rsp+80h+var_58], 0Eh
0x140034f7c  mov     byte ptr [rsp+80h+var_60], 2
0x140034f81  mov     r9, [r9+40h]
0x140034f85  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140034f8a  jmp     loc_140035028
0x140034f8f  mov     r8, [rbp+Entry]
0x140034f93  lea     rax, [rbp+var_20]
0x140034f97  mov     [rsp+80h+var_58], rax
0x140034f9c  xor     r9d, r9d
0x140034f9f  lea     rax, [rbp+var_1C]
0x140034fa3  mov     rdx, rsi
0x140034fa6  mov     rcx, r14
0x140034fa9  mov     [rsp+80h+var_60], rax
0x140034fae  call    PrjfSendCommand
0x140034fb3  mov     ebx, eax
0x140034fb5  cmp     eax, 0C0000034h
0x140034fba  jnz     short loc_140034FC6
0x140034fbc  mov     rax, [rbp+arg_20]
0x140034fc0  xor     ebx, ebx
0x140034fc2  mov     [rax], bl
0x140034fc4  jmp     short loc_140035028
0x140034fc6  test    ebx, ebx
0x140034fc8  jns     short loc_140035021
0x140034fca  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034fd0  lea     rax, WPP_RECORDER_INITIALIZED
0x140034fd7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034fde  setnz   r8b
0x140034fe2  and     dl, 40h
0x140034fe5  jnz     short loc_140034FEC
0x140034fe7  test    r8b, r8b
0x140034fea  jz      short loc_140035028
0x140034fec  mov     [rsp+80h+var_28], r15
0x140034ff1  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034ff8  mov     [rsp+80h+var_30], ebx
0x140034ffc  mov     [rsp+80h+var_38], 1278h
0x140035004  mov     [rsp+80h+var_40], rax
0x140035009  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140035010  mov     [rsp+80h+var_48], rax
0x140035015  mov     [rsp+80h+var_50], 0A3h
0x14003501c  jmp     loc_140034F68
0x140035021  mov     rax, [rbp+arg_20]
0x140035025  mov     byte ptr [rax], 1
0x140035028  cmp     [rbp+Entry], 0
0x14003502d  jz      short loc_14003503B
0x14003502f  mov     edx, [rbp+arg_10]
0x140035032  mov     rcx, [rbp+Entry]; Entry
0x140035036  call    PrjfFreeCommandBuffer
0x14003503b  lea     r11, [rsp+80h+var_s0]
0x140035043  mov     eax, ebx
0x140035045  mov     rbx, [r11+20h]
0x140035049  mov     rsi, [r11+28h]
0x14003504d  mov     rsp, r11
0x140035050  pop     r15
0x140035052  pop     r14
0x140035054  pop     rbp
0x140035055  retn
```
