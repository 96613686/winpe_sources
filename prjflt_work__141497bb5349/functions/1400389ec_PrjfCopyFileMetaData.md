# PrjfCopyFileMetaData

- ea: `0x1400389ec`
- end: `0x140038b71`
- name: `PrjfCopyFileMetaData`
- size: `389`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140037b8c`

## callees

- `0x14000d008`
- `0x14000d128`
- `0x14003875c`
- `0x1400389ec`

## pseudocode

```c
__int64 __fastcall PrjfCopyFileMetaData(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  int v5; // ebx
  int v6; // edx
  int v7; // r8d
  _QWORD v9[4]; // [rsp+60h] [rbp-38h] BYREF
  int v10; // [rsp+80h] [rbp-18h]
  int v11; // [rsp+84h] [rbp-14h]

  if ( a1 && a2 && a3 && a4 )
  {
    v5 = 0;
    if ( (a5 & 0x68) != 0 )
    {
      v11 = 0;
      v9[3] = *(_QWORD *)(a1 + 40);
      v9[0] = *(_QWORD *)(a1 + 16);
      v9[1] = *(_QWORD *)(a1 + 24);
      v9[2] = *(_QWORD *)(a1 + 32);
      v10 = *(_DWORD *)(a1 + 48);
      v5 = PrjfCopyFileBasicInformation(v9, a3, a4);
      if ( v5 < 0
        && (SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v6) = BYTE1(xmmword_14001A3D0) & 0x80;
        LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          527,
          v6,
          v7,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          15,
          34,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          148,
          v5);
      }
    }
  }
  else
  {
    if ( SBYTE1(xmmword_14001A3D0) < 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 0x80;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        527,
        a2,
        a3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        15,
        32,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        102);
    }
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400389ec  mov     rax, rsp
0x1400389ef  push    rbx
0x1400389f0  sub     rsp, 90h
0x1400389f7  mov     r10, r9
0x1400389fa  mov     r11, r8
0x1400389fd  test    rcx, rcx
0x140038a00  jz      loc_140038AF5
0x140038a06  test    rdx, rdx
0x140038a09  jz      loc_140038AF5
0x140038a0f  test    r8, r8
0x140038a12  jz      loc_140038AF5
0x140038a18  test    r9, r9
0x140038a1b  jz      loc_140038AF5
0x140038a21  mov     r9d, [rsp+98h+arg_20]
0x140038a29  xor     ebx, ebx
0x140038a2b  test    r9b, 68h
0x140038a2f  jz      loc_140038B65
0x140038a35  mov     [rax-14h], ebx
0x140038a38  mov     r8, r10
0x140038a3b  mov     rax, [rcx+28h]
0x140038a3f  mov     rdx, r11
0x140038a42  mov     [rsp+98h+var_20], rax
0x140038a47  mov     rax, [rcx+10h]
0x140038a4b  mov     [rsp+98h+var_38], rax
0x140038a50  mov     rax, [rcx+18h]
0x140038a54  mov     [rsp+98h+var_30], rax
0x140038a59  mov     rax, [rcx+20h]
0x140038a5d  mov     [rsp+98h+var_28], rax
0x140038a62  mov     eax, [rcx+30h]
0x140038a65  lea     rcx, [rsp+98h+var_38]
0x140038a6a  mov     [rsp+98h+var_18], eax
0x140038a71  call    PrjfCopyFileBasicInformation
0x140038a76  mov     ebx, eax
0x140038a78  test    eax, eax
0x140038a7a  jns     loc_140038B65
0x140038a80  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140038a86  lea     rax, WPP_RECORDER_INITIALIZED
0x140038a8d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140038a94  setnz   r8b
0x140038a98  and     dl, 80h
0x140038a9b  jnz     short loc_140038AA6
0x140038a9d  test    r8b, r8b
0x140038aa0  jz      loc_140038B65
0x140038aa6  mov     r9, cs:WPP_GLOBAL_Control
0x140038aad  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038ab4  mov     [rsp+98h+var_48], ebx
0x140038ab8  mov     ecx, 20Fh
0x140038abd  mov     [rsp+98h+var_50], 494h
0x140038ac5  mov     [rsp+98h+var_58], rax
0x140038aca  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038ad1  mov     r9, [r9+40h]
0x140038ad5  mov     [rsp+98h+var_60], rax
0x140038ada  mov     [rsp+98h+var_68], 22h ; '"'
0x140038ae1  mov     [rsp+98h+var_70], 0Fh
0x140038ae9  mov     [rsp+98h+var_78], 2
0x140038aee  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140038af3  jmp     short loc_140038B65
0x140038af5  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140038afb  lea     rax, WPP_RECORDER_INITIALIZED
0x140038b02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140038b09  setnz   r8b
0x140038b0d  and     dl, 80h
0x140038b10  jnz     short loc_140038B17
0x140038b12  test    r8b, r8b
0x140038b15  jz      short loc_140038B60
0x140038b17  mov     r9, cs:WPP_GLOBAL_Control
0x140038b1e  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140038b25  mov     [rsp+98h+var_50], 466h
0x140038b2d  mov     ecx, 20Fh
0x140038b32  mov     [rsp+98h+var_58], rax
0x140038b37  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140038b3e  mov     [rsp+98h+var_60], rax
0x140038b43  mov     r9, [r9+40h]
0x140038b47  mov     [rsp+98h+var_68], 20h ; ' '
0x140038b4e  mov     [rsp+98h+var_70], 0Fh
0x140038b56  mov     [rsp+98h+var_78], 2
0x140038b5b  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140038b60  mov     ebx, 0C000000Dh
0x140038b65  mov     eax, ebx
0x140038b67  add     rsp, 90h
0x140038b6e  pop     rbx
0x140038b6f  retn
```
