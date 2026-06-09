# CreateMatrixCRD

- ea: `0x1800325cc`
- end: `0x180032dd2`
- name: `CreateMatrixCRD`
- size: `2054`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180036bc0`

## callees

- `0x18000b828`
- `0x18000be44`
- `0x18002b058`
- `0x18002e5f0`
- `0x180030440`
- `0x1800306f0`
- `0x180030ca4`
- `0x1800325cc`
- `0x180033a1c`
- `0x180033a84`
- `0x180036648`
- `0x180037d48`
- `0x180037f80`
- `0x1800387e4`
- `0x180038cf8`
- `0x180038f0c`
- `0x180039a70`
- `0x180039ff8`
- `0x18003a054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800328e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800328e5`

## pseudocode

```c
__int64 __fastcall CreateMatrixCRD(__int64 a1, _QWORD *a2, unsigned __int32 *a3, unsigned int a4, int a5)
{
  unsigned int v5; // ebx
  unsigned int v10; // r14d
  unsigned int v11; // r14d
  const char *v12; // r8
  const char *v13; // r8
  unsigned __int32 v15; // r12d
  unsigned int v16; // r9d
  unsigned int v17; // r10d
  unsigned int v18; // r11d
  DWORD v19; // ecx
  unsigned __int32 v20; // ecx
  void *v21; // r13
  __int64 v22; // rdx
  const char *v23; // r8
  __int64 v24; // r8
  unsigned int i; // r14d
  const char *v26; // r8
  ULONG pulResult; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+44h] [rbp-BCh] BYREF
  int v29; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v37[6]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38[10]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v39[24]; // [rsp+E0h] [rbp-20h] BYREF
  char v40[24]; // [rsp+F8h] [rbp-8h] BYREF
  char v41[32]; // [rsp+110h] [rbp+10h] BYREF

  v5 = 1;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  if ( !(unsigned int)IsSRGBColorProfile(a1) )
  {
    v28 = 0;
    v29 = 0;
    v30 = 0;
    if ( !(unsigned int)GetTag(a1, 0x72545243u, 0xCu, &v34, &v31, &v28, 0)
      || !(unsigned int)GetTag(a1, 0x67545243u, 0xCu, &v35, &v32, &v29, 0)
      || !(unsigned int)GetTag(a1, 0x62545243u, 0xCu, &v36, &v33, &v30, 0) )
    {
      return 0;
    }
    pulResult = 0;
    v15 = 6
        * (_byteswap_ulong(*(_DWORD *)(v34 + 8))
         + _byteswap_ulong(*(_DWORD *)(v36 + 8))
         + _byteswap_ulong(*(_DWORD *)(v35 + 8)))
        + 4096;
    if ( ULongLongToULong(2LL * (v15 / 0xF0 + 1), &pulResult) < 0 )
    {
      v19 = 87;
LABEL_39:
      SetLastError(v19);
      return 0;
    }
    v20 = v15 + pulResult;
    if ( !a2 || !*a2 )
    {
      *a3 = v20;
      return v5;
    }
    if ( *a3 < v20 )
    {
LABEL_44:
      v19 = 122;
      goto LABEL_39;
    }
    if ( v17 > v16 )
      v16 = v17;
    if ( v18 > v16 )
      v16 = v18;
    if ( v16 > 0x3FFFFFFF || (v21 = (void *)MemAlloc(4LL * v16)) == 0 )
    {
      v19 = 8;
      goto LABEL_39;
    }
    v22 = *(_QWORD *)a1;
    v37[0] = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)a1 + 68LL));
    v37[1] = _byteswap_ulong(*(_DWORD *)(v22 + 72));
    v37[2] = _byteswap_ulong(*(_DWORD *)(v22 + 76));
    if ( !(unsigned int)EnableGlobalDict(a2, a3)
      || !(unsigned int)BeginGlobalDict(a2, a3)
      || !(unsigned int)CreateCRDRevArray((_DWORD)a2, (_DWORD)a3, v34, v28, (__int64)v21, 1918128707, a5)
      || !(unsigned int)CreateCRDRevArray((_DWORD)a2, (_DWORD)a3, v35, v29, (__int64)v21, 1733579331, a5)
      || !(unsigned int)CreateCRDRevArray((_DWORD)a2, (_DWORD)a3, v36, v30, (__int64)v21, 1649693251, a5)
      || !(unsigned int)EndGlobalDict(a2, a3)
      || !(unsigned int)WriteNewLineObject(a2, a3, "%** CRD Begin ")
      || !(unsigned int)WriteNewLineObject(a2, a3, "<<")
      || !(unsigned int)WriteObject(a2, a3, "/ColorRenderingType 1 ") )
    {
      v5 = 0;
    }
    switch ( a4 )
    {
      case 0u:
        if ( !v5 )
          goto LABEL_74;
        if ( !(unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
          goto LABEL_73;
        v23 = "/Perceptual";
LABEL_68:
        if ( (unsigned int)WriteObject(a2, a3, v23) )
        {
LABEL_69:
          if ( !(unsigned int)SendCRDBWPoint(a2, a3, v37) )
            goto LABEL_73;
          if ( !(unsigned int)SendCRDPQR(a2, a3, a4, v37) )
            goto LABEL_73;
          CreateColorantArray(a1, v39, 1918392666);
          CreateColorantArray(a1, v40, 1733843290);
          CreateColorantArray(a1, v41, 1649957210);
          InvertColorantArray(v39, v38, v24);
          if ( !(unsigned int)WriteNewLineObject(a2, a3, "/MatrixLMN ") || !(unsigned int)WriteObject(a2, a3, "[") )
            goto LABEL_73;
LABEL_74:
          for ( i = 0; i < 9; ++i )
          {
            if ( !v5 )
              goto LABEL_106;
            if ( !(unsigned int)WriteDouble(a2, a3) )
              goto LABEL_105;
          }
          if ( !v5 )
            goto LABEL_106;
          if ( (unsigned int)WriteObject(a2, a3, "]")
            && (unsigned int)WriteNewLineObject(a2, a3, "/EncodeABC ")
            && (unsigned int)WriteObject(a2, a3, "[")
            && (unsigned int)WriteObject(a2, a3, "\r\n")
            && (unsigned int)SendCRDRevArray(a2, a3, v34, v31, 1918128707, a5)
            && (unsigned int)WriteObject(a2, a3, "\r\n")
            && (unsigned int)SendCRDRevArray(a2, a3, v35, v32, 1733579331, a5)
            && (unsigned int)WriteObject(a2, a3, "\r\n")
            && (unsigned int)SendCRDRevArray(a2, a3, v36, v33, 1649693251, a5)
            && (unsigned int)WriteNewLineObject(a2, a3, "]")
            && (unsigned int)WriteObject(a2, a3, ">>") )
          {
            v5 &= -((unsigned int)WriteNewLineObject(a2, a3, "%** CRD End ") != 0);
            goto LABEL_106;
          }
LABEL_105:
          v5 = 0;
LABEL_106:
          MemFree(v21);
          return v5;
        }
LABEL_73:
        v5 = 0;
        goto LABEL_74;
      case 1u:
        if ( !v5 )
          goto LABEL_74;
        if ( (unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
        {
          v26 = "/RelativeColorimetric";
LABEL_85:
          if ( (unsigned int)WriteObject(a2, a3, v26) )
            goto LABEL_69;
        }
        break;
      case 2u:
        if ( !v5 )
          goto LABEL_74;
        if ( (unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
        {
          v26 = "/Saturation";
          goto LABEL_85;
        }
        break;
      case 3u:
        if ( !v5 )
          goto LABEL_74;
        if ( !(unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
          goto LABEL_73;
        v23 = "/AbsoluteColorimetric";
        goto LABEL_68;
      default:
LABEL_87:
        if ( !v5 )
          goto LABEL_74;
        goto LABEL_69;
    }
    v5 = 0;
    goto LABEL_87;
  }
  if ( !a2 || !*a2 )
  {
    *a3 = 4096;
    return 1;
  }
  if ( *a3 < 0x1000 )
    goto LABEL_44;
  if ( !(unsigned int)WriteNewLineObject(a2, a3, "%** CRD Begin ")
    || !(unsigned int)WriteNewLineObject(a2, a3, "<<")
    || !(unsigned int)WriteObject(a2, a3, "/ColorRenderingType 1 ") )
  {
    v5 = 0;
  }
  if ( !a4 )
  {
    if ( !v5 )
      return v5;
    if ( !(unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
      return 0;
    v12 = "/Perceptual";
    goto LABEL_16;
  }
  v10 = a4 - 1;
  if ( !v10 )
  {
    if ( !v5 )
      return v5;
    if ( (unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
    {
      v13 = "/RelativeColorimetric";
LABEL_26:
      if ( (unsigned int)WriteObject(a2, a3, v13) )
        goto LABEL_17;
    }
LABEL_27:
    v5 = 0;
LABEL_28:
    if ( !v5 )
      return v5;
    goto LABEL_17;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    if ( !v5 )
      return v5;
    if ( (unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
    {
      v13 = "/Saturation";
      goto LABEL_26;
    }
    goto LABEL_27;
  }
  if ( v11 != 1 )
    goto LABEL_28;
  if ( v5 )
  {
    if ( !(unsigned int)WriteNewLineObject(a2, a3, "/RenderingIntent ") )
      return 0;
    v12 = "/AbsoluteColorimetric";
LABEL_16:
    if ( (unsigned int)WriteObject(a2, a3, v12) )
    {
LABEL_17:
      if ( (unsigned int)WriteNewLineObject(
                           a2,
                           a3,
                           "/RangePQR [ -0.5 2 -0.5 2 -0.5 2 ] \r\n"
                           "/MatrixPQR [0.8951 -0.7502  0.0389 0.2664  1.7135 -0.0685 -0.1614  0.0367  1.0296] \r\n"
                           "/TransformPQR [{exch pop exch 3 get mul exch pop exch 3 get div} bind {exch pop exch 4 get mu"
                           "l exch pop exch 4 get div} bind {exch pop exch 5 get mul exch pop exch 5 get div} bind] \r\n"
                           "/MatrixLMN [3.240449 -0.969265  0.055643 -1.537136  1.876011 -0.204026 -0.498531  0.041556  1"
                           ".057229] \r\n"
                           "/EncodeABC [{dup 0.00304 le {12.92321 mul}{1 2.4 div exp 1.055 mul 0.055 sub}ifelse} bind dup"
                           " dup] \r\n"
                           "/WhitePoint[0.9505 1 1.0890] >>")
        && (unsigned int)WriteNewLineObject(a2, a3, "%** CRD End ") )
      {
        return v5;
      }
    }
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800325cc  mov     [rsp-8+arg_18], rbx
0x1800325d1  push    rbp
0x1800325d2  push    rsi
0x1800325d3  push    rdi
0x1800325d4  push    r12
0x1800325d6  push    r13
0x1800325d8  push    r14
0x1800325da  push    r15
0x1800325dc  lea     rbp, [rsp-40h]
0x1800325e1  sub     rsp, 140h
0x1800325e8  mov     rax, cs:__security_cookie
0x1800325ef  xor     rax, rsp
0x1800325f2  mov     [rbp+70h+var_40], rax
0x1800325f6  xor     r13d, r13d
0x1800325f9  mov     r12d, 1
0x1800325ff  mov     ebx, r12d
0x180032602  mov     [rsp+170h+var_120], r13d
0x180032607  mov     [rsp+170h+var_11C], r13d
0x18003260c  mov     r14d, r9d
0x18003260f  mov     [rsp+170h+var_118], r13d
0x180032614  mov     rdi, r8
0x180032617  mov     [rsp+170h+var_110], r13
0x18003261c  mov     rsi, rdx
0x18003261f  mov     [rsp+170h+var_108], r13
0x180032624  mov     r15, rcx
0x180032627  mov     [rsp+170h+var_100], r13
0x18003262c  call    IsSRGBColorProfile
0x180032631  test    eax, eax
0x180032633  jz      loc_1800327D3
0x180032639  test    rsi, rsi
0x18003263c  jz      loc_1800327C5
0x180032642  cmp     [rsi], r13
0x180032645  jz      loc_1800327C5
0x18003264b  cmp     dword ptr [rdi], 1000h
0x180032651  jb      loc_180032931
0x180032657  lea     r8, CRDBegin; "%** CRD Begin "
0x18003265e  mov     rdx, rdi
0x180032661  mov     rcx, rsi
0x180032664  call    WriteNewLineObject
0x180032669  test    eax, eax
0x18003266b  jz      short loc_180032699
0x18003266d  lea     r8, BeginDict; "<<"
0x180032674  mov     rdx, rdi
0x180032677  mov     rcx, rsi
0x18003267a  call    WriteNewLineObject
0x18003267f  test    eax, eax
0x180032681  jz      short loc_180032699
0x180032683  lea     r8, DictType; "/ColorRenderingType 1 "
0x18003268a  mov     rdx, rdi
0x18003268d  mov     rcx, rsi
0x180032690  call    WriteObject
0x180032695  test    eax, eax
0x180032697  jnz     short loc_18003269C
0x180032699  mov     ebx, r13d
0x18003269c  test    r14d, r14d
0x18003269f  jz      loc_180032797
0x1800326a5  sub     r14d, r12d
0x1800326a8  jz      loc_18003274F
0x1800326ae  sub     r14d, r12d
0x1800326b1  jz      short loc_180032728
0x1800326b3  cmp     r14d, r12d
0x1800326b6  jnz     loc_18003278A
0x1800326bc  test    ebx, ebx
0x1800326be  jz      loc_180032DCB
0x1800326c4  lea     r8, IntentType; "/RenderingIntent "
0x1800326cb  mov     rdx, rdi
0x1800326ce  mov     rcx, rsi
0x1800326d1  call    WriteNewLineObject
0x1800326d6  test    eax, eax
0x1800326d8  jz      short loc_180032720
0x1800326da  lea     r8, IntentACol; "/AbsoluteColorimetric"
0x1800326e1  mov     rdx, rdi
0x1800326e4  mov     rcx, rsi
0x1800326e7  call    WriteObject
0x1800326ec  test    eax, eax
0x1800326ee  jz      short loc_180032720
0x1800326f0  lea     r8, sRGBColorRenderingDictionary; "/RangePQR [ -0.5 2 -0.5 2 -0.5 2 ] \r\n"...
0x1800326f7  mov     rdx, rdi
0x1800326fa  mov     rcx, rsi
0x1800326fd  call    WriteNewLineObject
0x180032702  test    eax, eax
0x180032704  jz      short loc_180032720
0x180032706  lea     r8, CRDEnd; "%** CRD End "
0x18003270d  mov     rdx, rdi
0x180032710  mov     rcx, rsi
0x180032713  call    WriteNewLineObject
0x180032718  test    eax, eax
0x18003271a  jnz     loc_180032DCB
0x180032720  mov     ebx, r13d
0x180032723  jmp     loc_180032DCB
0x180032728  test    ebx, ebx
0x18003272a  jz      loc_180032DCB
0x180032730  lea     r8, IntentType; "/RenderingIntent "
0x180032737  mov     rdx, rdi
0x18003273a  mov     rcx, rsi
0x18003273d  call    WriteNewLineObject
0x180032742  test    eax, eax
0x180032744  jz      short loc_180032787
0x180032746  lea     r8, IntentSat; "/Saturation"
0x18003274d  jmp     short loc_180032774
0x18003274f  test    ebx, ebx
0x180032751  jz      loc_180032DCB
0x180032757  lea     r8, IntentType; "/RenderingIntent "
0x18003275e  mov     rdx, rdi
0x180032761  mov     rcx, rsi
0x180032764  call    WriteNewLineObject
0x180032769  test    eax, eax
0x18003276b  jz      short loc_180032787
0x18003276d  lea     r8, IntentRCol; "/RelativeColorimetric"
0x180032774  mov     rdx, rdi
0x180032777  mov     rcx, rsi
0x18003277a  call    WriteObject
0x18003277f  test    eax, eax
0x180032781  jnz     loc_1800326F0
0x180032787  mov     ebx, r13d
0x18003278a  test    ebx, ebx
0x18003278c  jz      loc_180032DCB
0x180032792  jmp     loc_1800326F0
0x180032797  test    ebx, ebx
0x180032799  jz      loc_180032DCB
0x18003279f  lea     r8, IntentType; "/RenderingIntent "
0x1800327a6  mov     rdx, rdi
0x1800327a9  mov     rcx, rsi
0x1800327ac  call    WriteNewLineObject
0x1800327b1  test    eax, eax
0x1800327b3  jz      loc_180032720
0x1800327b9  lea     r8, IntentPer; "/Perceptual"
0x1800327c0  jmp     loc_1800326E1
0x1800327c5  mov     dword ptr [rdi], 1000h
0x1800327cb  mov     eax, r12d
0x1800327ce  jmp     loc_1800328ED
0x1800327d3  lea     rax, [rsp+170h+var_12C]
0x1800327d8  mov     [rsp+170h+var_140], r13
0x1800327dd  mov     [rsp+170h+var_148], rax
0x1800327e2  lea     r9, [rsp+170h+var_110]
0x1800327e7  lea     rax, [rsp+170h+var_120]
0x1800327ec  mov     [rsp+170h+var_12C], r13d
0x1800327f1  mov     r12d, 0Ch
0x1800327f7  mov     [rsp+170h+var_150], rax
0x1800327fc  mov     r8d, r12d
0x1800327ff  mov     [rsp+170h+var_128], r13d
0x180032804  mov     edx, 72545243h
0x180032809  mov     [rsp+170h+var_124], r13d
0x18003280e  mov     rcx, r15
0x180032811  call    GetTag
0x180032816  test    eax, eax
0x180032818  jz      loc_1800328EB
0x18003281e  lea     rax, [rsp+170h+var_128]
0x180032823  mov     [rsp+170h+var_140], r13
0x180032828  mov     [rsp+170h+var_148], rax
0x18003282d  lea     r9, [rsp+170h+var_108]
0x180032832  lea     rax, [rsp+170h+var_11C]
0x180032837  mov     r8d, r12d
0x18003283a  mov     edx, 67545243h
0x18003283f  mov     [rsp+170h+var_150], rax
0x180032844  mov     rcx, r15
0x180032847  call    GetTag
0x18003284c  test    eax, eax
0x18003284e  jz      loc_1800328EB
0x180032854  lea     rax, [rsp+170h+var_124]
0x180032859  mov     [rsp+170h+var_140], r13
0x18003285e  mov     [rsp+170h+var_148], rax
0x180032863  lea     r9, [rsp+170h+var_100]
0x180032868  lea     rax, [rsp+170h+var_118]
0x18003286d  mov     r8d, r12d
0x180032870  mov     edx, 62545243h
0x180032875  mov     [rsp+170h+var_150], rax
0x18003287a  mov     rcx, r15
0x18003287d  call    GetTag
0x180032882  test    eax, eax
0x180032884  jz      short loc_1800328EB
0x180032886  mov     r9, [rsp+170h+var_108]
0x18003288b  mov     r11, [rsp+170h+var_100]
0x180032890  mov     r10, [rsp+170h+var_110]
0x180032895  mov     [rsp+170h+pulResult], r13d
0x18003289a  mov     r9d, [r9+8]
0x18003289e  mov     r11d, [r11+8]
0x1800328a2  mov     r10d, [r10+8]
0x1800328a6  bswap   r9d
0x1800328a9  bswap   r11d
0x1800328ac  bswap   r10d
0x1800328af  lea     eax, [r11+r9]
0x1800328b3  add     eax, r10d
0x1800328b6  lea     eax, [rax+rax*2]
0x1800328b9  lea     r12d, ds:1000h[rax*2]
0x1800328c1  mov     eax, 88888889h
0x1800328c6  mul     r12d
0x1800328c9  shr     edx, 7
0x1800328cc  lea     ecx, [rdx+1]
0x1800328cf  add     rcx, rcx; ullOperand
0x1800328d2  lea     rdx, [rsp+170h+pulResult]; pulResult
0x1800328d7  call    ULongLongToULong
0x1800328dc  test    eax, eax
0x1800328de  jns     short loc_180032914
0x1800328e0  mov     ecx, 57h ; 'W'; dwErrCode
0x1800328e5  call    cs:__imp_SetLastError
0x1800328eb  xor     eax, eax
0x1800328ed  mov     rcx, [rbp+70h+var_40]
0x1800328f1  xor     rcx, rsp; StackCookie
0x1800328f4  call    __security_check_cookie
0x1800328f9  mov     rbx, [rsp+170h+arg_18]
0x180032901  add     rsp, 140h
0x180032908  pop     r15
0x18003290a  pop     r14
0x18003290c  pop     r13
0x18003290e  pop     r12
0x180032910  pop     rdi
0x180032911  pop     rsi
0x180032912  pop     rbp
0x180032913  retn
0x180032914  mov     ecx, [rsp+170h+pulResult]
0x180032918  add     ecx, r12d
0x18003291b  test    rsi, rsi
0x18003291e  jz      loc_180032DC9
0x180032924  cmp     [rsi], r13
0x180032927  jz      loc_180032DC9
0x18003292d  cmp     [rdi], ecx
0x18003292f  jnb     short loc_180032938
0x180032931  mov     ecx, 7Ah ; 'z'
0x180032936  jmp     short loc_1800328E5
0x180032938  cmp     r10d, r9d
0x18003293b  cmova   r9d, r10d
0x18003293f  cmp     r11d, r9d
0x180032942  cmova   r9d, r11d
0x180032946  cmp     r9d, 3FFFFFFFh
0x18003294d  ja      loc_180032DBF
0x180032953  mov     ecx, r9d
0x180032956  shl     rcx, 2
0x18003295a  call    MemAlloc
0x18003295f  mov     r13, rax
0x180032962  test    rax, rax
0x180032965  jz      loc_180032DBF
0x18003296b  mov     rdx, [r15]
0x18003296e  mov     ecx, [rdx+44h]
0x180032971  bswap   ecx
0x180032973  mov     [rsp+170h+var_F8], ecx
0x180032977  mov     ecx, [rdx+48h]
0x18003297a  bswap   ecx
0x18003297c  mov     [rsp+170h+var_F4], ecx
0x180032980  mov     ecx, [rdx+4Ch]
0x180032983  mov     rdx, rdi
0x180032986  bswap   ecx
0x180032988  mov     [rbp+70h+var_F0], ecx
0x18003298b  mov     rcx, rsi
0x18003298e  call    EnableGlobalDict
0x180032993  mov     r12d, [rbp+70h+arg_20]
0x18003299a  test    eax, eax
0x18003299c  jz      loc_180032A8B
0x1800329a2  mov     rdx, rdi
0x1800329a5  mov     rcx, rsi
0x1800329a8  call    BeginGlobalDict
0x1800329ad  test    eax, eax
0x1800329af  jz      loc_180032A8B
0x1800329b5  mov     r9d, [rsp+170h+var_12C]
0x1800329ba  mov     rdx, rdi
0x1800329bd  mov     r8, [rsp+170h+var_110]
0x1800329c2  mov     rcx, rsi
0x1800329c5  mov     dword ptr [rsp+170h+var_140], r12d
0x1800329ca  mov     dword ptr [rsp+170h+var_148], 72545243h
0x1800329d2  mov     [rsp+170h+var_150], r13
0x1800329d7  call    CreateCRDRevArray
0x1800329dc  test    eax, eax
0x1800329de  jz      loc_180032A8B
0x1800329e4  mov     r9d, [rsp+170h+var_128]
0x1800329e9  mov     rdx, rdi
0x1800329ec  mov     r8, [rsp+170h+var_108]
0x1800329f1  mov     rcx, rsi
0x1800329f4  mov     dword ptr [rsp+170h+var_140], r12d
0x1800329f9  mov     dword ptr [rsp+170h+var_148], 67545243h
0x180032a01  mov     [rsp+170h+var_150], r13
0x180032a06  call    CreateCRDRevArray
0x180032a0b  test    eax, eax
0x180032a0d  jz      short loc_180032A8B
0x180032a0f  mov     r9d, [rsp+170h+var_124]
0x180032a14  mov     rdx, rdi
0x180032a17  mov     r8, [rsp+170h+var_100]
0x180032a1c  mov     rcx, rsi
0x180032a1f  mov     dword ptr [rsp+170h+var_140], r12d
0x180032a24  mov     dword ptr [rsp+170h+var_148], 62545243h
0x180032a2c  mov     [rsp+170h+var_150], r13
0x180032a31  call    CreateCRDRevArray
0x180032a36  test    eax, eax
0x180032a38  jz      short loc_180032A8B
0x180032a3a  mov     rdx, rdi
0x180032a3d  mov     rcx, rsi
0x180032a40  call    EndGlobalDict
0x180032a45  test    eax, eax
0x180032a47  jz      short loc_180032A8B
0x180032a49  lea     r8, CRDBegin; "%** CRD Begin "
0x180032a50  mov     rdx, rdi
0x180032a53  mov     rcx, rsi
0x180032a56  call    WriteNewLineObject
0x180032a5b  test    eax, eax
0x180032a5d  jz      short loc_180032A8B
0x180032a5f  lea     r8, BeginDict; "<<"
0x180032a66  mov     rdx, rdi
0x180032a69  mov     rcx, rsi
0x180032a6c  call    WriteNewLineObject
0x180032a71  test    eax, eax
0x180032a73  jz      short loc_180032A8B
  ... truncated ...
```
