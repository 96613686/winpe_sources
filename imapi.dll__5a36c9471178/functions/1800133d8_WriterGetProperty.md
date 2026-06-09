# WriterGetProperty

- ea: `0x1800133d8`
- end: `0x1800134e1`
- name: `WriterGetProperty`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e958`
- `0x180010170`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x180007d40`
- `0x180007d80`
- `0x1800133d8`

## pseudocode

```c
__int64 __fastcall WriterGetProperty(_DWORD *a1, unsigned int a2, _DWORD *a3)
{
  _BYTE *v6; // rcx
  unsigned int v7; // ebx
  int v8; // eax

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 110, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v7 = 0;
    switch ( a2 )
    {
      case 1u:
        v8 = a1[5];
        break;
      case 2u:
        v8 = a1[6];
        break;
      case 3u:
        v8 = a1[7];
        break;
      case 4u:
        v8 = a1[8];
        break;
      case 5u:
        v8 = a1[9];
        break;
      default:
        if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[68] & 1) == 0 )
          goto LABEL_9;
        WPP_SF_d(*((_QWORD *)v6 + 7), 113, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a2);
        goto LABEL_8;
    }
    *a3 = v8;
    goto LABEL_24;
  }
  if ( v6 == (_BYTE *)&WPP_GLOBAL_Control || (v6[68] & 1) == 0 )
    goto LABEL_9;
  WPP_SF_(*((_QWORD *)v6 + 7), 111, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids);
LABEL_8:
  v6 = WPP_GLOBAL_Control;
LABEL_9:
  v7 = -2147024809;
LABEL_24:
  if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (v6[68] & 1) != 0 )
    WPP_SF_qD(*((_QWORD *)v6 + 7), 114, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, a1, v7);
  return v7;
}

```

## disassembly

```asm
0x1800133d8  push    rbx
0x1800133da  push    rbp
0x1800133db  push    rsi
0x1800133dc  push    rdi
0x1800133dd  push    r15
0x1800133df  sub     rsp, 30h
0x1800133e3  mov     rsi, r8
0x1800133e6  mov     ebp, edx
0x1800133e8  mov     rdi, rcx
0x1800133eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133f2  lea     r15, WPP_GLOBAL_Control
0x1800133f9  cmp     rcx, r15
0x1800133fc  jz      short loc_180013423
0x1800133fe  test    byte ptr [rcx+44h], 1
0x180013402  jz      short loc_180013423
0x180013404  mov     rcx, [rcx+38h]
0x180013408  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001340f  mov     edx, 6Eh ; 'n'
0x180013414  mov     r9, rdi
0x180013417  call    WPP_SF_q
0x18001341c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013423  test    rdi, rdi
0x180013426  jnz     short loc_180013454
0x180013428  cmp     rcx, r15
0x18001342b  jz      short loc_18001344D
0x18001342d  test    byte ptr [rcx+44h], 1
0x180013431  jz      short loc_18001344D
0x180013433  mov     rcx, [rcx+38h]
0x180013437  lea     edx, [rdi+6Fh]
0x18001343a  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013441  call    WPP_SF_
0x180013446  mov     rcx, cs:WPP_GLOBAL_Control
0x18001344d  mov     ebx, 80070057h
0x180013452  jmp     short loc_1800134AD
0x180013454  xor     ebx, ebx
0x180013456  mov     eax, ebp
0x180013458  sub     eax, 1
0x18001345b  jz      short loc_1800134A8
0x18001345d  sub     eax, 1
0x180013460  jz      short loc_1800134A3
0x180013462  sub     eax, 1
0x180013465  jz      short loc_18001349E
0x180013467  sub     eax, 1
0x18001346a  jz      short loc_180013499
0x18001346c  cmp     eax, 1
0x18001346f  jz      short loc_180013494
0x180013471  cmp     rcx, r15
0x180013474  jz      short loc_18001344D
0x180013476  test    byte ptr [rcx+44h], 1
0x18001347a  jz      short loc_18001344D
0x18001347c  mov     rcx, [rcx+38h]
0x180013480  lea     edx, [rbx+71h]
0x180013483  mov     r9d, ebp
0x180013486  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001348d  call    WPP_SF_d
0x180013492  jmp     short loc_180013446
0x180013494  mov     eax, [rdi+24h]
0x180013497  jmp     short loc_1800134AB
0x180013499  mov     eax, [rdi+20h]
0x18001349c  jmp     short loc_1800134AB
0x18001349e  mov     eax, [rdi+1Ch]
0x1800134a1  jmp     short loc_1800134AB
0x1800134a3  mov     eax, [rdi+18h]
0x1800134a6  jmp     short loc_1800134AB
0x1800134a8  mov     eax, [rdi+14h]
0x1800134ab  mov     [rsi], eax
0x1800134ad  cmp     rcx, r15
0x1800134b0  jz      short loc_1800134D4
0x1800134b2  test    byte ptr [rcx+44h], 1
0x1800134b6  jz      short loc_1800134D4
0x1800134b8  mov     rcx, [rcx+38h]
0x1800134bc  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800134c3  mov     edx, 72h ; 'r'
0x1800134c8  mov     [rsp+58h+var_38], ebx
0x1800134cc  mov     r9, rdi
0x1800134cf  call    WPP_SF_qD
0x1800134d4  mov     eax, ebx
0x1800134d6  add     rsp, 30h
0x1800134da  pop     r15
0x1800134dc  pop     rdi
0x1800134dd  pop     rsi
0x1800134de  pop     rbp
0x1800134df  pop     rbx
0x1800134e0  retn
```
