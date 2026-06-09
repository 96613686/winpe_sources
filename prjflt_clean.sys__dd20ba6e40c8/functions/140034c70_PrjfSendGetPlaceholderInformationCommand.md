# PrjfSendGetPlaceholderInformationCommand

- ea: `0x140034c70`
- end: `0x140034e80`
- name: `PrjfSendGetPlaceholderInformationCommand`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002b0d0`

## callees

- `0x14000d754`
- `0x140032fd8`
- `0x140033bd0`
- `0x140034c70`
- `0x14003a5cc`

## pseudocode

```c
__int64 __fastcall PrjfSendGetPlaceholderInformationCommand(
        struct _FLT_CALLBACK_DATA *a1,
        void *a2,
        __int128 *a3,
        unsigned __int16 *a4,
        _OWORD *a5,
        __int64 a6)
{
  __int128 v6; // xmm0
  int v10; // eax
  int v11; // edx
  __int64 v12; // r8
  __int64 v13; // r9
  _DWORD *v14; // rdi
  unsigned int v15; // ebx
  _OWORD *v16; // rcx
  _OWORD *v17; // rax
  __int64 v18; // rdx
  __int128 v19; // xmm1
  int v20; // edx
  int v22; // [rsp+60h] [rbp-9h] BYREF
  int v23; // [rsp+64h] [rbp-5h] BYREF
  PVOID Entry; // [rsp+68h] [rbp-1h] BYREF
  _OWORD v25[4]; // [rsp+70h] [rbp+7h] BYREF
  unsigned int v26; // [rsp+D0h] [rbp+67h] BYREF

  v6 = *a3;
  Entry = 0;
  v22 = 4;
  v26 = 0;
  v23 = 0;
  v25[0] = v6;
  v10 = PrjfPrepareCommandForFilePath(a4, v25, 4, (const void **)a4, 0, a6, 0, &Entry, &v26);
  v14 = Entry;
  v15 = v10;
  if ( v10 >= 0 )
  {
    v16 = a5;
    v17 = (char *)Entry + 60;
    v18 = 2;
    do
    {
      *v17 = *v16;
      v17[1] = v16[1];
      v17[2] = v16[2];
      v17[3] = v16[3];
      v17[4] = v16[4];
      v17[5] = v16[5];
      v17[6] = v16[6];
      v19 = v16[7];
      v16 += 8;
      v17[7] = v19;
      v17 += 8;
      --v18;
    }
    while ( v18 );
    v15 = PrjfSendCommand(a1, a2, v14, 0, (__int64)&v23, &v22);
    if ( (int)(v15 + 0x80000000) >= 0 && v15 != -1073741772 )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = BYTE1(xmmword_14001A3D0) & 0x40;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          526,
          v20,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          14,
          151,
          (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
          27,
          v15,
          (__int64)a4);
      }
    }
  }
  else
  {
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = BYTE1(xmmword_14001A3D0) & 0x40;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        150,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        0,
        v10,
        (__int64)a4);
    }
  }
  if ( v14 )
    PrjfFreeCommandBuffer(v14, v26, v12, v13);
  return v15;
}

```

## disassembly

```asm
0x140034c70  push    rbp
0x140034c72  push    rbx
0x140034c73  push    rsi
0x140034c74  push    rdi
0x140034c75  push    r14
0x140034c77  push    r15
0x140034c79  lea     rbp, [rsp-1Fh]
0x140034c7e  sub     rsp, 88h
0x140034c85  movaps  xmm0, xmmword ptr [r8]
0x140034c89  lea     rax, [rbp+47h+arg_10]
0x140034c8d  mov     [rsp+0B0h+var_70], rax
0x140034c92  mov     r15, rcx
0x140034c95  mov     ecx, 4
0x140034c9a  mov     [rbp+47h+Entry], 0
0x140034ca2  lea     rax, [rbp+47h+Entry]
0x140034ca6  mov     [rbp+47h+var_50], ecx
0x140034ca9  mov     [rsp+0B0h+var_78], rax
0x140034cae  mov     r14, rdx
0x140034cb1  mov     rax, [rbp+47h+arg_28]
0x140034cb5  lea     rdx, [rbp+47h+var_40]
0x140034cb9  mov     [rsp+0B0h+var_80], 0
0x140034cc2  mov     r8d, ecx
0x140034cc5  mov     [rsp+0B0h+var_88], rax
0x140034cca  mov     rcx, r9
0x140034ccd  mov     [rsp+0B0h+var_90], 0
0x140034cd6  mov     rsi, r9
0x140034cd9  mov     [rbp+47h+arg_10], 0
0x140034ce0  mov     [rbp+47h+var_4C], 0
0x140034ce7  movdqa  [rbp+47h+var_40], xmm0
0x140034cec  call    PrjfPrepareCommandForFilePath
0x140034cf1  mov     rdi, [rbp+47h+Entry]
0x140034cf5  mov     ebx, eax
0x140034cf7  test    eax, eax
0x140034cf9  jns     short loc_140034D56
0x140034cfb  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034d01  lea     rax, WPP_RECORDER_INITIALIZED
0x140034d08  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034d0f  setnz   r8b
0x140034d13  and     dl, 40h
0x140034d16  jnz     short loc_140034D21
0x140034d18  test    r8b, r8b
0x140034d1b  jz      loc_140034E5D
0x140034d21  mov     [rsp+0B0h+var_58], rsi
0x140034d26  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034d2d  mov     [rsp+0B0h+var_60], ebx
0x140034d31  mov     [rsp+0B0h+var_68], 1100h
0x140034d39  mov     [rsp+0B0h+var_70], rax
0x140034d3e  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034d45  mov     [rsp+0B0h+var_78], rax
0x140034d4a  mov     word ptr [rsp+0B0h+var_80], 96h
0x140034d51  jmp     loc_140034E3B
0x140034d56  mov     rcx, [rbp+47h+arg_20]
0x140034d5a  lea     rax, [rdi+3Ch]
0x140034d5e  mov     edx, 2
0x140034d63  lea     r8d, [rdx+7Eh]
0x140034d67  movups  xmm0, xmmword ptr [rcx]
0x140034d6a  movups  xmmword ptr [rax], xmm0
0x140034d6d  movups  xmm1, xmmword ptr [rcx+10h]
0x140034d71  movups  xmmword ptr [rax+10h], xmm1
0x140034d75  movups  xmm0, xmmword ptr [rcx+20h]
0x140034d79  movups  xmmword ptr [rax+20h], xmm0
0x140034d7d  movups  xmm1, xmmword ptr [rcx+30h]
0x140034d81  movups  xmmword ptr [rax+30h], xmm1
0x140034d85  movups  xmm0, xmmword ptr [rcx+40h]
0x140034d89  movups  xmmword ptr [rax+40h], xmm0
0x140034d8d  movups  xmm1, xmmword ptr [rcx+50h]
0x140034d91  movups  xmmword ptr [rax+50h], xmm1
0x140034d95  movups  xmm0, xmmword ptr [rcx+60h]
0x140034d99  movups  xmmword ptr [rax+60h], xmm0
0x140034d9d  movups  xmm1, xmmword ptr [rcx+70h]
0x140034da1  add     rcx, r8
0x140034da4  movups  xmmword ptr [rax+70h], xmm1
0x140034da8  add     rax, r8
0x140034dab  sub     rdx, 1
0x140034daf  jnz     short loc_140034D67
0x140034db1  lea     rax, [rbp+47h+var_50]
0x140034db5  xor     r9d, r9d
0x140034db8  mov     [rsp+0B0h+var_88], rax
0x140034dbd  mov     r8, rdi
0x140034dc0  lea     rax, [rbp+47h+var_4C]
0x140034dc4  mov     rdx, r14
0x140034dc7  mov     rcx, r15
0x140034dca  mov     [rsp+0B0h+var_90], rax
0x140034dcf  call    PrjfSendCommand
0x140034dd4  mov     ecx, 80000000h
0x140034dd9  mov     ebx, eax
0x140034ddb  add     eax, ecx
0x140034ddd  test    ecx, eax
0x140034ddf  jnz     short loc_140034E5D
0x140034de1  cmp     ebx, 0C0000034h
0x140034de7  jz      short loc_140034E5D
0x140034de9  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034def  lea     rax, WPP_RECORDER_INITIALIZED
0x140034df6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034dfd  setnz   r8b
0x140034e01  and     dl, 40h
0x140034e04  jnz     short loc_140034E0B
0x140034e06  test    r8b, r8b
0x140034e09  jz      short loc_140034E5D
0x140034e0b  mov     [rsp+0B0h+var_58], rsi
0x140034e10  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034e17  mov     [rsp+0B0h+var_60], ebx
0x140034e1b  mov     [rsp+0B0h+var_68], 111Bh
0x140034e23  mov     [rsp+0B0h+var_70], rax
0x140034e28  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034e2f  mov     [rsp+0B0h+var_78], rax
0x140034e34  mov     word ptr [rsp+0B0h+var_80], 97h
0x140034e3b  mov     r9, cs:WPP_GLOBAL_Control
0x140034e42  mov     ecx, 20Eh
0x140034e47  mov     dword ptr [rsp+0B0h+var_88], 0Eh
0x140034e4f  mov     byte ptr [rsp+0B0h+var_90], 2
0x140034e54  mov     r9, [r9+40h]
0x140034e58  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140034e5d  test    rdi, rdi
0x140034e60  jz      short loc_140034E6D
0x140034e62  mov     edx, [rbp+47h+arg_10]
0x140034e65  mov     rcx, rdi; Entry
0x140034e68  call    PrjfFreeCommandBuffer
0x140034e6d  mov     eax, ebx
0x140034e6f  add     rsp, 88h
0x140034e76  pop     r15
0x140034e78  pop     r14
0x140034e7a  pop     rdi
0x140034e7b  pop     rsi
0x140034e7c  pop     rbx
0x140034e7d  pop     rbp
0x140034e7e  retn
```
