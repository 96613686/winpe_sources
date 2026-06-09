# PrjfSendGetDirectoryEnumerationCommand

- ea: `0x1400346f0`
- end: `0x1400349f3`
- name: `PrjfSendGetDirectoryEnumerationCommand`
- size: `771`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140025734`
- `0x140039de8`

## callees

- `0x14000b1d0`
- `0x14000ba20`
- `0x14000bb80`
- `0x14000be80`
- `0x14000d754`
- `0x140032db4`
- `0x140033bd0`
- `0x1400346f0`
- `0x1400359a0`
- `0x14003a5cc`

## pseudocode

```c
__int64 __fastcall PrjfSendGetDirectoryEnumerationCommand(
        struct _FLT_CALLBACK_DATA *a1,
        void *a2,
        __int64 a3,
        unsigned int a4,
        const void **a5,
        char a6,
        unsigned int a7,
        __int128 *a8,
        __int64 a9,
        unsigned int *a10)
{
  __int64 v12; // r12
  unsigned int *v13; // rsi
  __int128 v14; // xmm6
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // eax
  int v21; // edx
  int v22; // ebx
  int v23; // r8d
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // edx
  int v28; // r8d
  _OWORD v31[34]; // [rsp+88h] [rbp-80h] BYREF

  v12 = a9;
  v13 = a10;
  v14 = *a8;
  memset(v31, 0, sizeof(v31));
  v20 = a7;
  if ( !a7 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v16, v18, v19);
    v20 = a7;
  }
  DWORD1(v31[33]) = v20;
  *v13 = 0;
  LODWORD(v31[1]) = a4;
  BYTE9(v31[33]) = a6 & 1;
  BYTE8(v31[33]) = a6 & 2;
  v31[0] = v14;
  if ( a5 )
    memmove((char *)&v31[1] + 4, a5[1], *(unsigned __int16 *)a5);
  v22 = PrjfPrepareCommandForFileObject((_DWORD)a2, a3, 3, (unsigned int)v31);
  if ( v22 >= 0 )
  {
    v24 = PrjfSendCommand(a1, a2, 0, 0, v12, &a7);
    v22 = v24;
    if ( v24 >= 0 )
    {
      if ( (int)PrjfValidateNamesInEnumeration(a4, v12, a7) >= 0 )
      {
        *v13 = a7;
      }
      else
      {
        if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v27) = BYTE1(xmmword_14001A3D0) & 0x40;
          LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdZ(
            526,
            v27,
            v28,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            2,
            14,
            168,
            (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
            127,
            v22,
            a3 + 88);
        }
        return (unsigned int)-2147483642;
      }
    }
    else if ( v24 != -2147483642
           && ((BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v25) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        526,
        v25,
        v26,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        167,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        108,
        v24,
        a3 + 88);
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v21) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdZ(
      526,
      v21,
      v23,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      166,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      84,
      v22,
      a3 + 88);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1400346f0  mov     rax, rsp
0x1400346f3  push    rbp
0x1400346f4  push    rbx
0x1400346f5  push    rsi
0x1400346f6  push    r12
0x1400346f8  push    r13
0x1400346fa  push    r14
0x1400346fc  push    r15
0x1400346fe  lea     rbp, [rax-1F8h]
0x140034705  sub     rsp, 2C0h
0x14003470c  movaps  xmmword ptr [rax-48h], xmm6
0x140034710  mov     rax, cs:__security_cookie
0x140034717  xor     rax, rsp
0x14003471a  mov     [rbp+1F0h+var_50], rax
0x140034721  mov     rax, [rbp+1F0h+arg_38]
0x140034728  mov     r14, r8
0x14003472b  mov     rbx, [rbp+1F0h+arg_20]
0x140034732  mov     r13, rdx
0x140034735  mov     r12, [rbp+1F0h+arg_40]
0x14003473c  xor     edx, edx; Val
0x14003473e  mov     rsi, [rbp+1F0h+arg_48]
0x140034745  mov     r8d, 220h; Size
0x14003474b  movaps  xmm6, xmmword ptr [rax]
0x14003474e  mov     r15d, r9d
0x140034751  mov     [rsp+70h], rcx
0x140034756  lea     rcx, [rbp+1F0h+var_270]; void *
0x14003475a  mov     [rsp+2F0h+Entry], 0
0x140034763  call    memset
0x140034768  mov     eax, [rbp+1F0h+arg_30]
0x14003476e  mov     dword ptr [rsp+2F0h+var_290], 0
0x140034776  test    eax, eax
0x140034778  jnz     short loc_140034785
0x14003477a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14003477f  mov     eax, [rbp+1F0h+arg_30]
0x140034785  mov     cl, [rbp+1F0h+arg_28]
0x14003478b  mov     [rbp+1F0h+var_5C], eax
0x140034791  mov     al, cl
0x140034793  and     al, 1
0x140034795  mov     dword ptr [rsi], 0
0x14003479b  and     cl, 2
0x14003479e  mov     [rbp+1F0h+var_260], r15d
0x1400347a2  mov     [rbp+1F0h+var_57], al
0x1400347a8  mov     [rbp+1F0h+var_58], cl
0x1400347ae  movdqu  [rbp+1F0h+var_270], xmm6
0x1400347b3  test    rbx, rbx
0x1400347b6  jz      short loc_1400347C9
0x1400347b8  movzx   r8d, word ptr [rbx]; Size
0x1400347bc  lea     rcx, [rbp+1F0h+var_25C]; void *
0x1400347c0  mov     rdx, [rbx+8]; Src
0x1400347c4  call    memmove
0x1400347c9  lea     rax, [rsp+2F0h+var_290]
0x1400347ce  mov     r8d, 3
0x1400347d4  mov     [rsp+2F0h+var_2C0], rax
0x1400347d9  lea     r9, [rbp+1F0h+var_270]
0x1400347dd  lea     rax, [rsp+2F0h+Entry]
0x1400347e2  mov     rdx, r14
0x1400347e5  mov     rcx, r13
0x1400347e8  mov     [rsp+2F0h+var_2C8], rax
0x1400347ed  call    PrjfPrepareCommandForFileObject
0x1400347f2  mov     ebx, eax
0x1400347f4  test    eax, eax
0x1400347f6  jns     loc_14003487D
0x1400347fc  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140034802  lea     rax, WPP_RECORDER_INITIALIZED
0x140034809  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140034810  setnz   r8b
0x140034814  and     dl, 40h
0x140034817  jnz     short loc_140034822
0x140034819  test    r8b, r8b
0x14003481c  jz      loc_1400349B0
0x140034822  lea     rax, [r14+58h]
0x140034826  mov     qword ptr [rsp+2F0h+var_298], rax
0x14003482b  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140034832  mov     dword ptr [rsp+2F0h+var_2A0], ebx
0x140034836  mov     [rsp+2F0h+var_2A8], 1354h
0x14003483e  mov     qword ptr [rsp+2F0h+var_2B0], rax
0x140034843  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14003484a  mov     [rsp+2F0h+var_2B8], rax
0x14003484f  mov     word ptr [rsp+2F0h+var_2C0], 0A6h
0x140034856  mov     r9, cs:WPP_GLOBAL_Control
0x14003485d  mov     ecx, 20Eh
0x140034862  mov     dword ptr [rsp+2F0h+var_2C8], 0Eh
0x14003486a  mov     byte ptr [rsp+2F0h+var_2D0], 2
0x14003486f  mov     r9, [r9+40h]
0x140034873  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140034878  jmp     loc_1400349B0
0x14003487d  mov     r8, [rsp+2F0h+Entry]
0x140034882  lea     rax, [rbp+1F0h+arg_30]
0x140034889  mov     rcx, [rsp+70h]
0x14003488e  xor     r9d, r9d
0x140034891  mov     [rsp+2F0h+var_2C8], rax
0x140034896  mov     rdx, r13
0x140034899  mov     [rsp+2F0h+var_2D0], r12
0x14003489e  call    PrjfSendCommand
0x1400348a3  mov     ebx, eax
0x1400348a5  test    eax, eax
0x1400348a7  jns     short loc_140034913
0x1400348a9  cmp     eax, 80000006h
0x1400348ae  jz      loc_1400349B0
0x1400348b4  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400348ba  lea     rax, WPP_RECORDER_INITIALIZED
0x1400348c1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400348c8  setnz   r8b
0x1400348cc  and     dl, 40h
0x1400348cf  jnz     short loc_1400348DA
0x1400348d1  test    r8b, r8b
0x1400348d4  jz      loc_1400349B0
0x1400348da  lea     rax, [r14+58h]
0x1400348de  mov     qword ptr [rsp+2F0h+var_298], rax
0x1400348e3  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400348ea  mov     dword ptr [rsp+2F0h+var_2A0], ebx
0x1400348ee  mov     [rsp+2F0h+var_2A8], 136Ch
0x1400348f6  mov     qword ptr [rsp+2F0h+var_2B0], rax
0x1400348fb  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034902  mov     [rsp+2F0h+var_2B8], rax
0x140034907  mov     word ptr [rsp+2F0h+var_2C0], 0A7h
0x14003490e  jmp     loc_140034856
0x140034913  mov     r8d, [rbp+1F0h+arg_30]
0x14003491a  mov     rdx, r12
0x14003491d  mov     ecx, r15d
0x140034920  call    PrjfValidateNamesInEnumeration
0x140034925  test    eax, eax
0x140034927  jns     short loc_1400349A8
0x140034929  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14003492f  lea     rax, WPP_RECORDER_INITIALIZED
0x140034936  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003493d  setnz   r8b
0x140034941  and     dl, 40h
0x140034944  jnz     short loc_14003494B
0x140034946  test    r8b, r8b
0x140034949  jz      short loc_1400349A1
0x14003494b  mov     r9, cs:WPP_GLOBAL_Control
0x140034952  lea     rax, [r14+58h]
0x140034956  mov     qword ptr [rsp+2F0h+var_298], rax
0x14003495b  mov     ecx, 20Eh
0x140034960  mov     dword ptr [rsp+2F0h+var_2A0], ebx
0x140034964  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14003496b  mov     [rsp+2F0h+var_2A8], 137Fh
0x140034973  mov     r9, [r9+40h]
0x140034977  mov     qword ptr [rsp+2F0h+var_2B0], rax
0x14003497c  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140034983  mov     [rsp+2F0h+var_2B8], rax
0x140034988  mov     word ptr [rsp+2F0h+var_2C0], 0A8h
0x14003498f  mov     dword ptr [rsp+2F0h+var_2C8], 0Eh
0x140034997  mov     byte ptr [rsp+2F0h+var_2D0], 2
0x14003499c  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x1400349a1  mov     ebx, 80000006h
0x1400349a6  jmp     short loc_1400349B0
0x1400349a8  mov     eax, [rbp+1F0h+arg_30]
0x1400349ae  mov     [rsi], eax
0x1400349b0  cmp     [rsp+2F0h+Entry], 0
0x1400349b6  jz      short loc_1400349C6
0x1400349b8  mov     edx, dword ptr [rsp+2F0h+var_290]
0x1400349bc  mov     rcx, [rsp+2F0h+Entry]; Entry
0x1400349c1  call    PrjfFreeCommandBuffer
0x1400349c6  mov     eax, ebx
0x1400349c8  mov     rcx, [rbp+1F0h+var_50]
0x1400349cf  xor     rcx, rsp; StackCookie
0x1400349d2  call    __security_check_cookie
0x1400349d7  movaps  xmm6, [rsp+2F0h+var_48+8]
0x1400349df  add     rsp, 2C0h
0x1400349e6  pop     r15
0x1400349e8  pop     r14
0x1400349ea  pop     r13
0x1400349ec  pop     r12
0x1400349ee  pop     rsi
0x1400349ef  pop     rbx
0x1400349f0  pop     rbp
0x1400349f1  retn
```
