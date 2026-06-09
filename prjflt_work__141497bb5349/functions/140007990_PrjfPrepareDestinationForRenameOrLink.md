# PrjfPrepareDestinationForRenameOrLink

- ea: `0x140007990`
- end: `0x140007ce6`
- name: `PrjfPrepareDestinationForRenameOrLink`
- size: `854`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140007694`

## callees

- `0x140007300`
- `0x140007990`
- `0x14000ba20`
- `0x14000bb00`
- `0x14000be80`
- `0x14000d008`
- `0x14000d128`
- `0x140042658`

## pseudocode

```c
__int64 __fastcall PrjfPrepareDestinationForRenameOrLink(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v9; // rcx
  char v10; // di
  int v11; // eax
  _BYTE *v12; // rax
  char v13; // si
  int v14; // edx
  int v15; // ebx
  int v16; // r8d
  int v17; // edx
  int v18; // r8d
  __int16 v20; // [rsp+30h] [rbp-D0h]
  char v21; // [rsp+48h] [rbp-B8h]
  char v22; // [rsp+50h] [rbp-B0h]
  _BYTE v24[48]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v26[20]; // [rsp+B0h] [rbp-50h] BYREF

  memset(v24, 0, 44);
  v25 = 0;
  memset(v26, 0, 0x48u);
  v9 = *(_QWORD *)(a1 + 16);
  v10 = 1;
  v11 = *(_DWORD *)(v9 + 32);
  if ( v11 != 10 && v11 != 65 || (v12 = *(_BYTE **)(v9 + 56), !*v12) || (v13 = 1, (*(_DWORD *)v12 & 2) == 0) )
    v13 = 0;
  *(_DWORD *)v24 = 48;
  *(_QWORD *)&v24[8] = a3;
  *(_DWORD *)&v24[24] = 512;
  *(_QWORD *)&v24[16] = a4;
  *(_OWORD *)&v24[32] = 0;
  v15 = ((__int64 (__fastcall *)(PFLT_FILTER, struct _FLT_INSTANCE *, _BYTE *, __int128 *, _DWORD *, int, int, _QWORD))PrjfFltQueryInformationByName)(
          Globals,
          a2,
          v24,
          &v25,
          v26,
          72,
          68,
          0);
  if ( v15 == -1073741772 )
    return 0;
  if ( v15 < 0 )
  {
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
    if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v22 = v15;
      v21 = 44;
      v20 = 119;
LABEL_12:
      WPP_RECORDER_AND_TRACE_SF_sDL(
        525,
        v14,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        13,
        v20,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        v21,
        v22);
      return (unsigned int)v15;
    }
    return (unsigned int)v15;
  }
  if ( v26[15] == -1610612702 )
  {
    v15 = PrjfDeleteTombstoneIfExists(a2, *(PFILE_OBJECT *)(a5 + 80), a3, a4);
    if ( v15 < 0 )
    {
      if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = BYTE2(xmmword_14001A3D0) & 8;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          531,
          v17,
          v18,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          19,
          120,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          62,
          v15);
      }
      return (unsigned int)v15;
    }
    return 0;
  }
  if ( !v13 || (v26[14] & 0x10) == 0 || v26[15] != -1879048164 )
    return 0;
  v15 = PrjfOpenAndCheckEmptyPartialDirectory(a1, (__int64)a2, a4, a3);
  if ( v15 >= 0 )
  {
    v15 = -1073741567;
    LOBYTE(v14) = BYTE9(xmmword_14001A3E0) & 0x20;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !*((_WORD *)WPP_GLOBAL_Control + 36) )
      v10 = 0;
    if ( (_BYTE)v14 || v10 )
    {
      LOBYTE(v16) = v10;
      WPP_RECORDER_AND_TRACE_SF_sD(
        1293,
        v14,
        v16,
        PrjfTraceRecorder,
        5,
        13,
        122,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        91);
    }
  }
  else
  {
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x20;
    if ( (BYTE1(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v22 = v15;
      v21 = 84;
      v20 = 121;
      goto LABEL_12;
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140007990  push    rbp
0x140007992  push    rbx
0x140007993  push    rsi
0x140007994  push    rdi
0x140007995  push    r12
0x140007997  push    r13
0x140007999  push    r14
0x14000799b  push    r15
0x14000799d  lea     rbp, [rsp-18h]
0x1400079a2  sub     rsp, 118h
0x1400079a9  mov     rax, cs:__security_cookie
0x1400079b0  xor     rax, rsp
0x1400079b3  mov     [rbp+50h+var_50], rax
0x1400079b7  mov     r13, [rbp+50h+arg_20]
0x1400079be  xorps   xmm0, xmm0
0x1400079c1  xor     eax, eax
0x1400079c3  mov     [rsp+150h+var_E8], rcx
0x1400079c8  mov     r15, r8
0x1400079cb  mov     r14, rdx
0x1400079ce  mov     rbx, rcx
0x1400079d1  xor     edx, edx; Val
0x1400079d3  movups  [rbp+50h+var_D0], xmm0
0x1400079d7  lea     r8d, [rax+48h]; Size
0x1400079db  mov     r12, r9
0x1400079de  lea     rcx, [rbp+50h+var_A0]; void *
0x1400079e2  movups  [rsp+150h+var_E0], xmm0
0x1400079e7  movups  [rbp+50h+var_D0+0Ch], xmm0
0x1400079eb  movups  [rbp+50h+var_B0], xmm0
0x1400079ef  call    memset
0x1400079f4  mov     rcx, [rbx+10h]
0x1400079f8  xor     edx, edx
0x1400079fa  mov     [rsp+150h+var_F0], dl
0x1400079fe  mov     dil, 1
0x140007a01  mov     eax, [rcx+20h]
0x140007a04  cmp     eax, 0Ah
0x140007a07  jz      short loc_140007A0E
0x140007a09  cmp     eax, 41h ; 'A'
0x140007a0c  jnz     short loc_140007A1F
0x140007a0e  mov     rax, [rcx+38h]
0x140007a12  cmp     [rax], dl
0x140007a14  jz      short loc_140007A1F
0x140007a16  mov     eax, [rax]
0x140007a18  mov     sil, dil
0x140007a1b  test    al, 2
0x140007a1d  jnz     short loc_140007A22
0x140007a1f  mov     sil, dl
0x140007a22  mov     rax, cs:PrjfFltQueryInformationByName
0x140007a29  lea     rcx, [rbp+50h+var_A0]
0x140007a2d  mov     [rsp+150h+var_118], rdx
0x140007a32  lea     r9, [rbp+50h+var_B0]
0x140007a36  mov     dword ptr [rsp+150h+var_120], 44h ; 'D'
0x140007a3e  lea     r8, [rsp+150h+var_E0]
0x140007a43  xorps   xmm0, xmm0
0x140007a46  mov     [rsp+150h+var_128], 48h ; 'H'
0x140007a4e  mov     [rsp+150h+var_130], rcx
0x140007a53  mov     rdx, r14
0x140007a56  mov     rcx, cs:Globals
0x140007a5d  mov     dword ptr [rsp+150h+var_E0], 30h ; '0'
0x140007a65  mov     qword ptr [rsp+150h+var_E0+8], r15
0x140007a6a  mov     dword ptr [rbp+50h+var_D0+8], 200h
0x140007a71  mov     qword ptr [rbp+50h+var_D0], r12
0x140007a75  movdqu  [rbp+50h+var_C0], xmm0
0x140007a7a  call    _guard_dispatch_icall
0x140007a7f  mov     ebx, eax
0x140007a81  cmp     eax, 0C0000034h
0x140007a86  jnz     short loc_140007A8F
0x140007a88  xor     ebx, ebx
0x140007a8a  jmp     loc_140007CC3
0x140007a8f  xor     ecx, ecx
0x140007a91  test    ebx, ebx
0x140007a93  jns     short loc_140007B0D
0x140007a95  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140007a9b  lea     rax, WPP_RECORDER_INITIALIZED
0x140007aa2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007aa9  setnz   r8b
0x140007aad  and     dl, 20h
0x140007ab0  jnz     short loc_140007ABB
0x140007ab2  test    r8b, r8b
0x140007ab5  jz      loc_140007CC3
0x140007abb  mov     dword ptr [rsp+150h+var_100], ebx
0x140007abf  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007ac6  mov     dword ptr [rsp+150h+var_108], 152Ch
0x140007ace  mov     [rsp+150h+var_110], rax
0x140007ad3  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007ada  mov     [rsp+150h+var_118], rax
0x140007adf  mov     [rsp+150h+var_120], 77h ; 'w'
0x140007ae6  mov     ecx, 20Dh
0x140007aeb  mov     [rsp+150h+var_128], 0Dh
0x140007af3  mov     r9, cs:WPP_GLOBAL_Control
0x140007afa  mov     byte ptr [rsp+150h+var_130], 2
0x140007aff  mov     r9, [r9+40h]
0x140007b03  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140007b08  jmp     loc_140007CC3
0x140007b0d  cmp     [rbp+50h+var_64], 0A0000022h
0x140007b14  jnz     loc_140007B9B
0x140007b1a  mov     rdx, [r13+50h]; FileObject
0x140007b1e  mov     r9, r12
0x140007b21  mov     r8, r15
0x140007b24  mov     rcx, r14; Instance
0x140007b27  call    PrjfDeleteTombstoneIfExists
0x140007b2c  xor     ecx, ecx
0x140007b2e  mov     ebx, eax
0x140007b30  test    eax, eax
0x140007b32  jns     loc_140007CC1
0x140007b38  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140007b3e  lea     rax, WPP_RECORDER_INITIALIZED
0x140007b45  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007b4c  setnz   r8b
0x140007b50  and     dl, 8
0x140007b53  jnz     short loc_140007B5E
0x140007b55  test    r8b, r8b
0x140007b58  jz      loc_140007CC3
0x140007b5e  mov     dword ptr [rsp+150h+var_100], ebx
0x140007b62  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007b69  mov     dword ptr [rsp+150h+var_108], 153Eh
0x140007b71  mov     ecx, 213h
0x140007b76  mov     [rsp+150h+var_110], rax
0x140007b7b  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007b82  mov     [rsp+150h+var_118], rax
0x140007b87  mov     [rsp+150h+var_120], 78h ; 'x'
0x140007b8e  mov     [rsp+150h+var_128], 13h
0x140007b96  jmp     loc_140007AF3
0x140007b9b  test    sil, sil
0x140007b9e  jz      loc_140007CC1
0x140007ba4  test    [rbp+50h+var_68], 10h
0x140007ba8  jz      loc_140007CC1
0x140007bae  cmp     [rbp+50h+var_64], 9000001Ch
0x140007bb5  jnz     loc_140007CC1
0x140007bbb  mov     rcx, [rsp+150h+var_E8]
0x140007bc0  lea     rax, [rsp+150h+var_F0]
0x140007bc5  mov     r9, r15
0x140007bc8  mov     [rsp+150h+var_130], rax
0x140007bcd  mov     r8, r12
0x140007bd0  mov     rdx, r14
0x140007bd3  call    PrjfOpenAndCheckEmptyPartialDirectory
0x140007bd8  xor     ecx, ecx
0x140007bda  mov     ebx, eax
0x140007bdc  test    eax, eax
0x140007bde  jns     short loc_140007C36
0x140007be0  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140007be6  lea     rax, WPP_RECORDER_INITIALIZED
0x140007bed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007bf4  setnz   r8b
0x140007bf8  and     dl, 20h
0x140007bfb  jnz     short loc_140007C06
0x140007bfd  test    r8b, r8b
0x140007c00  jz      loc_140007CC3
0x140007c06  mov     dword ptr [rsp+150h+var_100], ebx
0x140007c0a  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007c11  mov     dword ptr [rsp+150h+var_108], 1554h
0x140007c19  mov     [rsp+150h+var_110], rax
0x140007c1e  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007c25  mov     [rsp+150h+var_118], rax
0x140007c2a  mov     [rsp+150h+var_120], 79h ; 'y'
0x140007c31  jmp     loc_140007AE6
0x140007c36  cmp     [rsp+150h+var_F0], cl
0x140007c3a  jnz     loc_140007CC1
0x140007c40  mov     ebx, 0C0000101h
0x140007c45  mov     dl, byte ptr cs:xmmword_14001A3E0+9
0x140007c4b  lea     rax, WPP_RECORDER_INITIALIZED
0x140007c52  and     dl, 20h
0x140007c55  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140007c5c  jz      short loc_140007C6B
0x140007c5e  mov     rax, cs:WPP_GLOBAL_Control
0x140007c65  cmp     [rax+48h], cx
0x140007c69  jnz     short loc_140007C6E
0x140007c6b  mov     dil, cl
0x140007c6e  test    dl, dl
0x140007c70  jnz     short loc_140007C77
0x140007c72  test    dil, dil
0x140007c75  jz      short loc_140007CC3
0x140007c77  mov     r9, cs:_PrjfTraceRecorder
0x140007c7e  lea     rax, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140007c85  mov     dword ptr [rsp+150h+var_108], 155Bh
0x140007c8d  mov     ecx, 50Dh
0x140007c92  mov     [rsp+150h+var_110], rax
0x140007c97  mov     r8b, dil
0x140007c9a  lea     rax, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140007ca1  mov     [rsp+150h+var_118], rax
0x140007ca6  mov     [rsp+150h+var_120], 7Ah ; 'z'
0x140007cad  mov     [rsp+150h+var_128], 0Dh
0x140007cb5  mov     byte ptr [rsp+150h+var_130], 5
0x140007cba  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140007cbf  jmp     short loc_140007CC3
0x140007cc1  mov     ebx, ecx
0x140007cc3  mov     eax, ebx
0x140007cc5  mov     rcx, [rbp+50h+var_50]
0x140007cc9  xor     rcx, rsp; StackCookie
0x140007ccc  call    __security_check_cookie
0x140007cd1  add     rsp, 118h
0x140007cd8  pop     r15
0x140007cda  pop     r14
0x140007cdc  pop     r13
0x140007cde  pop     r12
0x140007ce0  pop     rdi
0x140007ce1  pop     rsi
0x140007ce2  pop     rbx
0x140007ce3  pop     rbp
0x140007ce4  retn
```
