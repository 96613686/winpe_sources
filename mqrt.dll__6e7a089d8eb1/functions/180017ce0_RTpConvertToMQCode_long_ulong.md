# RTpConvertToMQCode(long,ulong)

- ea: `0x180017ce0`
- end: `0x180017ed4`
- name: `?RTpConvertToMQCode@@YAJJK@Z`
- size: `500`
- prototype: `__int64 __fastcall(int, unsigned int)`
- caller_count: `37`
- callee_count: `3`
- tags: ``

## callers

- `0x1800055e0`
- `0x180008490`
- `0x180008550`
- `0x180009b20`
- `0x18000a120`
- `0x18000a8b8`
- `0x18000ac70`
- `0x18000af00`
- `0x18000dc48`
- `0x18000e200`
- `0x18000e520`
- `0x18000e590`
- `0x18000ec20`
- `0x18000ee60`
- `0x18000f250`
- `0x18000f600`
- `0x18000f6a0`
- `0x18000f7a0`
- `0x18000f990`
- `0x18000fa60`
- `0x18000fb60`
- `0x18000fcf0`
- `0x180010260`
- `0x180010300`
- `0x1800106c0`
- `0x180012000`
- `0x180015a80`
- `0x180015c30`
- `0x180018f4c`
- `0x18001a63c`
- `0x18001ba48`
- `0x18001bb44`
- `0x18001cbb0`
- `0x18001ce18`
- `0x18001d224`
- `0x1800252b6`
- `0x180025305`

## callees

- `0x1800087f8`
- `0x180013c74`
- `0x180017ce0`

## pseudocode

```c
__int64 __fastcall RTpConvertToMQCode(int a1, int a2)
{
  unsigned int v2; // ebx
  __int64 result; // rax

  v2 = a1;
  if ( !a1
    || a1 == 1074660328
    || a1 == -1072824210
    || (unsigned int)(a1 + 1072824320) <= 0xFF
    || (unsigned int)(a1 - 1074659328) <= 0xFF )
  {
    return v2;
  }
  if ( a1 == 1074660652 )
    return 0;
  if ( (a1 & 0x1FFF0000) != 0xE0000 )
  {
    if ( a1 == -529697949 )
    {
      v2 = -1072824281;
      LogMsgHR(-1072824281, (wchar_t *)L"rt/rtutil", 0x28u);
      return v2;
    }
    if ( a1 > -1073741788 )
    {
      switch ( a1 )
      {
        case -1073741757:
          return (unsigned int)-1072824311;
        case -1073741670:
          return (unsigned int)-1072824281;
        case -1073741536:
          return (unsigned int)-1072824312;
      }
      if ( a1 != -1073741259 )
      {
        if ( a1 == 259 )
          return 1074659334;
        goto LABEL_40;
      }
    }
    else if ( a1 != -1073741788 )
    {
      if ( a1 == -2147024891 )
        return (unsigned int)-1072824283;
      if ( a1 == -1073741819 )
        return (unsigned int)-1072824314;
      if ( a1 != -1073741816 )
      {
        if ( a1 != -1073741811 )
        {
          if ( a1 == -1073741808 )
            return (unsigned int)-1072824309;
          if ( a1 == -1073741790 )
            return (unsigned int)-1072824283;
LABEL_40:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, "1", (unsigned int)a1);
          return v2;
        }
        return (unsigned int)-1072824314;
      }
    }
    return (unsigned int)-1072824313;
  }
  switch ( a1 )
  {
    case -1072823025:
    case -1072823022:
      result = 3222142989LL;
      if ( a2 == 1 )
        return 3222142979LL;
      break;
    case -1072823020:
      return 3222143049LL;
    case -1072823018:
      return 3222143050LL;
    default:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, "1", (unsigned int)a1);
      return 3222143043LL;
  }
  return result;
}

```

## disassembly

```asm
0x180017ce0  push    rbx
0x180017ce2  sub     rsp, 20h
0x180017ce6  mov     ebx, ecx
0x180017ce8  test    ecx, ecx
0x180017cea  jz      loc_180017ECC
0x180017cf0  cmp     ecx, 400E03E8h
0x180017cf6  jz      loc_180017ECC
0x180017cfc  cmp     ecx, 0C00E006Eh
0x180017d02  jz      loc_180017ECC
0x180017d08  lea     eax, [rcx+3FF20000h]
0x180017d0e  mov     ecx, 0FFh
0x180017d13  cmp     eax, ecx
0x180017d15  jbe     loc_180017ECC
0x180017d1b  lea     eax, [rbx-400E0000h]
0x180017d21  cmp     eax, ecx
0x180017d23  jbe     loc_180017ECC
0x180017d29  cmp     ebx, 400E052Ch
0x180017d2f  jnz     short loc_180017D38
0x180017d31  xor     eax, eax
0x180017d33  jmp     loc_180017ECE
0x180017d38  mov     eax, ebx
0x180017d3a  and     eax, 1FFF0000h
0x180017d3f  cmp     eax, 0E0000h
0x180017d44  jnz     loc_180017DCC
0x180017d4a  cmp     ebx, 0C00E050Fh
0x180017d50  jz      short loc_180017DB9
0x180017d52  cmp     ebx, 0C00E0512h
0x180017d58  jz      short loc_180017DB9
0x180017d5a  cmp     ebx, 0C00E0514h
0x180017d60  jz      short loc_180017DAF
0x180017d62  cmp     ebx, 0C00E0516h
0x180017d68  jz      short loc_180017DA5
0x180017d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d71  lea     rax, WPP_GLOBAL_Control
0x180017d78  cmp     rcx, rax
0x180017d7b  jz      short loc_180017D9B
0x180017d7d  test    byte ptr [rcx+1Ch], 2
0x180017d81  jz      short loc_180017D9B
0x180017d83  mov     rcx, [rcx+10h]
0x180017d87  lea     r8, WPP_47570031a8ac3272128e71323b334376_Traceguids; "1"
0x180017d8e  mov     edx, 0Ah
0x180017d93  mov     r9d, ebx
0x180017d96  call    WPP_SF_d
0x180017d9b  mov     eax, 0C00E0043h
0x180017da0  jmp     loc_180017ECE
0x180017da5  mov     eax, 0C00E004Ah
0x180017daa  jmp     loc_180017ECE
0x180017daf  mov     eax, 0C00E0049h
0x180017db4  jmp     loc_180017ECE
0x180017db9  mov     eax, 0C00E000Dh
0x180017dbe  cmp     edx, 1
0x180017dc1  lea     ecx, [rax-0Ah]
0x180017dc4  cmovz   eax, ecx
0x180017dc7  jmp     loc_180017ECE
0x180017dcc  cmp     ebx, 0E06D7363h
0x180017dd2  jnz     short loc_180017DF2
0x180017dd4  mov     ebx, 0C00E0027h
0x180017dd9  lea     rdx, aRtRtutil; "rt/rtutil"
0x180017de0  mov     ecx, ebx; int
0x180017de2  mov     r8d, 28h ; '('; unsigned __int16
0x180017de8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180017ded  jmp     loc_180017ECC
0x180017df2  mov     eax, 0C0000024h
0x180017df7  cmp     ebx, eax
0x180017df9  jg      short loc_180017E50
0x180017dfb  jz      loc_180017EB2
0x180017e01  cmp     ebx, 80070005h
0x180017e07  jz      short loc_180017E35
0x180017e09  cmp     ebx, 0C0000005h
0x180017e0f  jz      short loc_180017E49
0x180017e11  cmp     ebx, 0C0000008h
0x180017e17  jz      loc_180017EB2
0x180017e1d  cmp     ebx, 0C000000Dh
0x180017e23  jz      short loc_180017E49
0x180017e25  cmp     ebx, 0C0000010h
0x180017e2b  jz      short loc_180017E3F
0x180017e2d  cmp     ebx, 0C0000022h
0x180017e33  jnz     short loc_180017E78
0x180017e35  mov     ebx, 0C00E0025h
0x180017e3a  jmp     loc_180017ECC
0x180017e3f  mov     ebx, 0C00E000Bh
0x180017e44  jmp     loc_180017ECC
0x180017e49  mov     ebx, 0C00E0006h
0x180017e4e  jmp     short loc_180017ECC
0x180017e50  cmp     ebx, 0C0000043h
0x180017e56  jz      short loc_180017EC7
0x180017e58  cmp     ebx, 0C000009Ah
0x180017e5e  jz      short loc_180017EC0
0x180017e60  cmp     ebx, 0C0000120h
0x180017e66  jz      short loc_180017EB9
0x180017e68  cmp     ebx, 0C0000235h
0x180017e6e  jz      short loc_180017EB2
0x180017e70  cmp     ebx, 103h
0x180017e76  jz      short loc_180017EAB
0x180017e78  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e7f  lea     rax, WPP_GLOBAL_Control
0x180017e86  cmp     rcx, rax
0x180017e89  jz      short loc_180017ECC
0x180017e8b  test    byte ptr [rcx+1Ch], 2
0x180017e8f  jz      short loc_180017ECC
0x180017e91  mov     rcx, [rcx+10h]
0x180017e95  lea     r8, WPP_47570031a8ac3272128e71323b334376_Traceguids; "1"
0x180017e9c  mov     edx, 0Bh
0x180017ea1  mov     r9d, ebx
0x180017ea4  call    WPP_SF_d
0x180017ea9  jmp     short loc_180017ECC
0x180017eab  mov     ebx, 400E0006h
0x180017eb0  jmp     short loc_180017ECC
0x180017eb2  mov     ebx, 0C00E0007h
0x180017eb7  jmp     short loc_180017ECC
0x180017eb9  mov     ebx, 0C00E0008h
0x180017ebe  jmp     short loc_180017ECC
0x180017ec0  mov     ebx, 0C00E0027h
0x180017ec5  jmp     short loc_180017ECC
0x180017ec7  mov     ebx, 0C00E0009h
0x180017ecc  mov     eax, ebx
0x180017ece  add     rsp, 20h
0x180017ed2  pop     rbx
0x180017ed3  retn
```
