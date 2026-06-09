# CMsftDiscFormat2TrackAtOnce::UpdateCachedMediaInformation(void)

- ea: `0x180039a4c`
- end: `0x180039f25`
- name: `?UpdateCachedMediaInformation@CMsftDiscFormat2TrackAtOnce@@AEAAJXZ`
- size: `1241`
- prototype: `__int64 __fastcall(CMsftDiscFormat2TrackAtOnce *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800369e0`

## callees

- `0x18000a5f0`
- `0x18000a86c`
- `0x1800140f4`
- `0x180014180`
- `0x180016778`
- `0x180039a4c`
- `0x180049138`
- `0x180049590`
- `0x1800495f8`
- `0x1800496e4`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2TrackAtOnce::UpdateCachedMediaInformation(CMsftDiscFormat2TrackAtOnce *this)
{
  struct IDiscRecorder2Ex *v1; // rdx
  int v3; // esi
  unsigned int LastTrackOfLastSession; // eax
  unsigned int v5; // r14d
  bool v6; // bl
  struct IDiscRecorder2Ex *v7; // rdx
  int v8; // ecx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rbx
  unsigned __int8 *v13; // r12
  unsigned int TrackSize; // eax
  int v15; // r8d
  unsigned int v16; // r11d
  unsigned int v17; // r10d
  unsigned int NextWritableAddress; // eax
  unsigned int v19; // ecx
  unsigned __int8 *v21; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+38h] [rbp-40h]
  _QWORD v23[2]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v25[3]; // [rsp+60h] [rbp-18h] BYREF

  v1 = (struct IDiscRecorder2Ex *)*((_QWORD *)this + 24);
  v24[0] = 0;
  v24[1] = 0;
  v21 = 0;
  v22 = 0;
  v23[0] = 0;
  v23[1] = 0;
  v3 = CMsftDiscInformation::Init((CMsftDiscInformation *)v24, v1);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        125,
        WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
        (unsigned int)v3);
    }
    goto LABEL_50;
  }
  LastTrackOfLastSession = CMsftDiscInformation::get_LastTrackOfLastSession((CMsftDiscInformation *)v24);
  v5 = LastTrackOfLastSession;
  if ( (*(_BYTE *)(v24[0] + 2LL) & 0xC) != 0xC && LastTrackOfLastSession )
    v5 = LastTrackOfLastSession - 1;
  if ( v5 >= 0x62 )
  {
    v7 = (struct IDiscRecorder2Ex *)*((_QWORD *)this + 24);
    v25[0] = 0;
    v25[1] = 0;
    CMsftTrackInformation::Init((CMsftTrackInformation *)v25, v7, 0x63u, 1u, 0);
    v8 = *((_DWORD *)this + 71);
    if ( (*(_BYTE *)(v25[0] + 6LL) & 0x40) != 0 )
    {
      v6 = v8 == 97;
    }
    else
    {
      v6 = 0;
      if ( v8 == 98 )
      {
        v6 = 1;
        v5 = 99;
      }
    }
    CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)v25);
  }
  else
  {
    v6 = v5 > *((_DWORD *)this + 71);
  }
  if ( v6 )
  {
    v3 = CMsftTrackInformation::Init((CMsftTrackInformation *)&v21, *((struct IDiscRecorder2Ex **)this + 24), v5, 1u, 0);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
      {
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          126,
          WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
          v5,
          v5,
          v3);
      }
      goto LABEL_50;
    }
    if ( (unsigned int)v22 >= 0x1C )
    {
      if ( v5 != 99 )
      {
        v3 = CMsftTrackInformation::Init(
               (CMsftTrackInformation *)v23,
               *((struct IDiscRecorder2Ex **)this + 24),
               v5 + 1,
               1u,
               0);
        if ( v3 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 345) >= 3u )
          {
            WPP_SF_ddD(
              *((_QWORD *)WPP_GLOBAL_Control + 42),
              128,
              WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids,
              v5 + 1,
              v5 + 1,
              v3);
          }
          goto LABEL_50;
        }
        if ( (*(_BYTE *)(v23[0] + 7LL) & 1) == 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
          {
            goto LABEL_49;
          }
          v10 = 129;
LABEL_48:
          WPP_SF_(v9[42], v10, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids);
LABEL_49:
          v3 = -2147467259;
          goto LABEL_50;
        }
        if ( (*(_BYTE *)(v23[0] + 6LL) & 0x40) == 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
          {
            goto LABEL_49;
          }
          v10 = 130;
          goto LABEL_48;
        }
      }
      v11 = *((_DWORD *)this + 71);
      v12 = v5 - 1;
      v13 = v21;
      *((_BYTE *)this + 290) = 1;
      *((_BYTE *)this + 291) = v5;
      *((_BYTE *)this + 289) = 8 * v11 + 10;
      *((_BYTE *)this + 288) = (unsigned __int16)(8 * v11 + 10) >> 8;
      *(_QWORD *)((char *)this + 8 * v12 + 292) = 0;
      *(_QWORD *)((char *)this + 8 * v5 + 292) = 0;
      *((_BYTE *)this + 8 * v12 + 293) = 16;
      *((_BYTE *)this + 8 * v12 + 294) = v5;
      *(_WORD *)((char *)this + 8 * v5 + 293) = -22000;
      TrackSize = CMsftTrackInformation::get_TrackSize((CMsftTrackInformation *)&v21);
      *((_BYTE *)this + 8 * v12 + 296) = 0;
      v16 = TrackSize + v15 + 152;
      *((_BYTE *)this + 8 * v12 + 297) = v17 / 0x4B / 0x3C;
      *((_BYTE *)this + 8 * v12 + 298) = v17 / 0x4B % 0x3C;
      *((_BYTE *)this + 8 * v12 + 299) = v17 % 0x4B;
      *((_BYTE *)this + 8 * v5 + 296) = 0;
      *((_BYTE *)this + 8 * v5 + 297) = v16 / 0x4B / 0x3C;
      *((_BYTE *)this + 8 * v5 + 298) = v16 / 0x4B % 0x3C;
      *((_BYTE *)this + 8 * v5 + 299) = v16 % 0x4B;
      if ( v5 < 0x63 )
        NextWritableAddress = CMsftTrackInformation::get_NextWritableAddress((CMsftTrackInformation *)v23);
      else
        NextWritableAddress = (v13[11] | ((v13[10] | ((v13[9] | (v13[8] << 8)) << 8)) << 8))
                            + CMsftTrackInformation::get_TrackSize((CMsftTrackInformation *)&v21)
                            + 152;
      *((_DWORD *)this + 70) = NextWritableAddress;
      v19 = *((_DWORD *)this + 68) - NextWritableAddress;
      *((_DWORD *)this + 71) = v5;
      *((_DWORD *)this + 69) = v19 - 2;
      goto LABEL_50;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 345) < 3u )
    {
      goto LABEL_49;
    }
    v10 = 127;
    goto LABEL_48;
  }
LABEL_50:
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)v23);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v21);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)v24);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180039a4c  push    rbp
0x180039a4e  push    rbx
0x180039a4f  push    rsi
0x180039a50  push    rdi
0x180039a51  push    r12
0x180039a53  push    r13
0x180039a55  push    r14
0x180039a57  push    r15
0x180039a59  mov     rbp, rsp
0x180039a5c  sub     rsp, 78h
0x180039a60  mov     rdx, [rcx+0C0h]; struct IDiscRecorder2Ex *
0x180039a67  xor     r13d, r13d
0x180039a6a  mov     r15, rcx
0x180039a6d  mov     [rbp+var_28], r13
0x180039a71  lea     rcx, [rbp+var_28]; this
0x180039a75  mov     [rbp+var_20], r13
0x180039a79  mov     [rbp+var_48], r13
0x180039a7d  mov     [rbp+var_40], r13
0x180039a81  mov     [rbp+var_38], r13
0x180039a85  mov     [rbp+var_30], r13
0x180039a89  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x180039a8e  mov     esi, eax
0x180039a90  test    eax, eax
0x180039a92  jns     short loc_180039AE4
0x180039a94  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a9b  lea     rax, WPP_GLOBAL_Control
0x180039aa2  cmp     rcx, rax
0x180039aa5  jz      loc_180039EF7
0x180039aab  test    byte ptr [rcx+15Ch], 4
0x180039ab2  jz      loc_180039EF7
0x180039ab8  cmp     byte ptr [rcx+159h], 3
0x180039abf  jb      loc_180039EF7
0x180039ac5  mov     rcx, [rcx+150h]
0x180039acc  lea     edx, [r13+7Dh]
0x180039ad0  mov     r9d, esi
0x180039ad3  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180039ada  call    WPP_SF_d
0x180039adf  jmp     loc_180039EF7
0x180039ae4  lea     rcx, [rbp+var_28]; this
0x180039ae8  call    ?get_LastTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_LastTrackOfLastSession(void)
0x180039aed  mov     rcx, [rbp+var_28]
0x180039af1  mov     r14d, eax
0x180039af4  mov     dl, [rcx+2]
0x180039af7  and     dl, 0Ch
0x180039afa  cmp     dl, 0Ch
0x180039afd  jz      short loc_180039B06
0x180039aff  test    eax, eax
0x180039b01  jz      short loc_180039B06
0x180039b03  dec     r14d
0x180039b06  mov     edi, 1
0x180039b0b  lea     r12d, [rdi+62h]
0x180039b0f  cmp     r14d, 62h ; 'b'
0x180039b13  jnb     short loc_180039B21
0x180039b15  cmp     r14d, [r15+11Ch]
0x180039b1c  setnbe  bl
0x180039b1f  jmp     short loc_180039B74
0x180039b21  mov     rdx, [r15+0C0h]; struct IDiscRecorder2Ex *
0x180039b28  lea     rcx, [rbp+var_18]; this
0x180039b2c  mov     r9d, edi; enum _IMAPI_READ_TRACK_ADDRESS_TYPE
0x180039b2f  mov     [rbp+var_18], r13
0x180039b33  mov     r8d, r12d; unsigned int
0x180039b36  mov     [rbp+var_10], r13
0x180039b3a  mov     [rsp+78h+var_58], r13b; unsigned __int8
0x180039b3f  call    ?Init@CMsftTrackInformation@@QEAAJPEAUIDiscRecorder2Ex@@KW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@E@Z; CMsftTrackInformation::Init(IDiscRecorder2Ex *,ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar)
0x180039b44  mov     rax, [rbp+var_18]
0x180039b48  mov     ecx, [r15+11Ch]
0x180039b4f  test    byte ptr [rax+6], 40h
0x180039b53  jz      short loc_180039B5D
0x180039b55  cmp     ecx, 61h ; 'a'
0x180039b58  setz    bl
0x180039b5b  jmp     short loc_180039B6B
0x180039b5d  mov     bl, r13b
0x180039b60  cmp     ecx, 62h ; 'b'
0x180039b63  jnz     short loc_180039B6B
0x180039b65  mov     bl, dil
0x180039b68  mov     r14d, r12d
0x180039b6b  lea     rcx, [rbp+var_18]; this
0x180039b6f  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x180039b74  test    bl, bl
0x180039b76  jz      loc_180039EF7
0x180039b7c  mov     rdx, [r15+0C0h]; struct IDiscRecorder2Ex *
0x180039b83  lea     rcx, [rbp+var_48]; this
0x180039b87  mov     r9d, edi; enum _IMAPI_READ_TRACK_ADDRESS_TYPE
0x180039b8a  mov     [rsp+78h+var_58], r13b; unsigned __int8
0x180039b8f  mov     r8d, r14d; unsigned int
0x180039b92  call    ?Init@CMsftTrackInformation@@QEAAJPEAUIDiscRecorder2Ex@@KW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@E@Z; CMsftTrackInformation::Init(IDiscRecorder2Ex *,ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar)
0x180039b97  mov     esi, eax
0x180039b99  test    eax, eax
0x180039b9b  jns     short loc_180039BE1
0x180039b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ba4  lea     rax, WPP_GLOBAL_Control
0x180039bab  cmp     rcx, rax
0x180039bae  jz      loc_180039EF7
0x180039bb4  test    byte ptr [rcx+15Ch], 4
0x180039bbb  jz      loc_180039EF7
0x180039bc1  cmp     byte ptr [rcx+159h], 3
0x180039bc8  jb      loc_180039EF7
0x180039bce  mov     [rsp+78h+var_50], esi
0x180039bd2  mov     edx, 7Eh ; '~'
0x180039bd7  mov     dword ptr [rsp+78h+var_58], r14d
0x180039bdc  mov     r9d, r14d
0x180039bdf  jmp     short loc_180039C5A
0x180039be1  cmp     dword ptr [rbp+var_40], 1Ch
0x180039be5  jb      loc_180039EB5
0x180039beb  cmp     r14d, r12d
0x180039bee  jz      loc_180039CF8
0x180039bf4  mov     rdx, [r15+0C0h]; struct IDiscRecorder2Ex *
0x180039bfb  lea     ebx, [r14+1]
0x180039bff  mov     r8d, ebx; unsigned int
0x180039c02  mov     [rsp+78h+var_58], r13b; unsigned __int8
0x180039c07  mov     r9d, edi; enum _IMAPI_READ_TRACK_ADDRESS_TYPE
0x180039c0a  lea     rcx, [rbp+var_38]; this
0x180039c0e  call    ?Init@CMsftTrackInformation@@QEAAJPEAUIDiscRecorder2Ex@@KW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@E@Z; CMsftTrackInformation::Init(IDiscRecorder2Ex *,ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar)
0x180039c13  mov     esi, eax
0x180039c15  test    eax, eax
0x180039c17  jns     short loc_180039C72
0x180039c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c20  lea     rax, WPP_GLOBAL_Control
0x180039c27  cmp     rcx, rax
0x180039c2a  jz      loc_180039EF7
0x180039c30  test    byte ptr [rcx+15Ch], 4
0x180039c37  jz      loc_180039EF7
0x180039c3d  cmp     byte ptr [rcx+159h], 3
0x180039c44  jb      loc_180039EF7
0x180039c4a  mov     [rsp+78h+var_50], esi
0x180039c4e  mov     edx, 80h
0x180039c53  mov     dword ptr [rsp+78h+var_58], ebx
0x180039c57  mov     r9d, ebx
0x180039c5a  mov     rcx, [rcx+150h]
0x180039c61  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180039c68  call    WPP_SF_ddD
0x180039c6d  jmp     loc_180039EF7
0x180039c72  mov     rax, [rbp+var_38]
0x180039c76  test    [rax+7], dil
0x180039c7a  jnz     short loc_180039CB7
0x180039c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039c83  lea     rax, WPP_GLOBAL_Control
0x180039c8a  cmp     rcx, rax
0x180039c8d  jz      loc_180039EF2
0x180039c93  test    byte ptr [rcx+15Ch], 4
0x180039c9a  jz      loc_180039EF2
0x180039ca0  cmp     byte ptr [rcx+159h], 3
0x180039ca7  jb      loc_180039EF2
0x180039cad  mov     edx, 81h
0x180039cb2  jmp     loc_180039EDF
0x180039cb7  test    byte ptr [rax+6], 40h
0x180039cbb  jnz     short loc_180039CF8
0x180039cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180039cc4  lea     rax, WPP_GLOBAL_Control
0x180039ccb  cmp     rcx, rax
0x180039cce  jz      loc_180039EF2
0x180039cd4  test    byte ptr [rcx+15Ch], 4
0x180039cdb  jz      loc_180039EF2
0x180039ce1  cmp     byte ptr [rcx+159h], 3
0x180039ce8  jb      loc_180039EF2
0x180039cee  mov     edx, 82h
0x180039cf3  jmp     loc_180039EDF
0x180039cf8  mov     eax, [r15+11Ch]
0x180039cff  lea     ebx, [r14-1]
0x180039d03  mov     r12, [rbp+var_48]
0x180039d07  mov     [r15+122h], dil
0x180039d0e  mov     [r15+123h], r14b
0x180039d15  lea     ecx, ds:0Ah[rax*8]
0x180039d1c  mov     edi, r14d
0x180039d1f  mov     [r15+121h], cl
0x180039d26  mov     eax, ecx
0x180039d28  shr     eax, 8
0x180039d2b  lea     rcx, [rbp+var_48]; this
0x180039d2f  mov     [r15+120h], al
0x180039d36  xor     eax, eax
0x180039d38  mov     [r15+rbx*8+124h], rax
0x180039d40  mov     [r15+rdi*8+124h], rax
0x180039d48  mov     byte ptr [r15+rbx*8+125h], 10h
0x180039d51  mov     [r15+rbx*8+126h], r14b
0x180039d59  mov     word ptr [r15+rdi*8+125h], 0AA10h
0x180039d64  movzx   eax, byte ptr [r12+9]
0x180039d6a  movzx   r8d, byte ptr [r12+8]
0x180039d70  shl     r8d, 8
0x180039d74  or      r8d, eax
0x180039d77  movzx   eax, byte ptr [r12+0Ah]
0x180039d7d  shl     r8d, 8
0x180039d81  or      r8d, eax
0x180039d84  movzx   eax, byte ptr [r12+0Bh]
0x180039d8a  shl     r8d, 8
0x180039d8e  or      r8d, eax
0x180039d91  lea     r10d, [r8+96h]
0x180039d98  call    ?get_TrackSize@CMsftTrackInformation@@QEAAKXZ; CMsftTrackInformation::get_TrackSize(void)
0x180039d9d  mov     [r15+rbx*8+128h], r13b
0x180039da5  lea     r11d, [r8+98h]
0x180039dac  add     r11d, eax
0x180039daf  mov     r13d, 88888889h
0x180039db5  mov     eax, 1B4E81B5h
0x180039dba  mul     r10d
0x180039dbd  mov     eax, r13d
0x180039dc0  mov     r9d, edx
0x180039dc3  shr     r9d, 3
0x180039dc7  mul     r9d
0x180039dca  mov     eax, 1B4E81B5h
0x180039dcf  shr     edx, 5
0x180039dd2  mov     [r15+rbx*8+129h], dl
0x180039dda  movzx   ecx, dl
0x180039ddd  imul    r8d, ecx, 3Ch ; '<'
0x180039de1  mov     cl, r9b
0x180039de4  sub     cl, r8b
0x180039de7  mov     [r15+rbx*8+12Ah], cl
0x180039def  movzx   ecx, r9b
0x180039df3  imul    edx, ecx, 4Bh ; 'K'
0x180039df6  sub     r10b, dl
0x180039df9  mul     r11d
0x180039dfc  mov     [r15+rbx*8+12Bh], r10b
0x180039e04  mov     eax, r13d
0x180039e07  mov     r8d, edx
0x180039e0a  mov     byte ptr [r15+rdi*8+128h], 0
0x180039e13  shr     r8d, 3
0x180039e17  mul     r8d
0x180039e1a  shr     edx, 5
0x180039e1d  movzx   eax, dl
0x180039e20  imul    ecx, eax, 3Ch ; '<'
0x180039e23  mov     al, r8b
0x180039e26  mov     [r15+rdi*8+129h], dl
0x180039e2e  sub     al, cl
0x180039e30  mov     [r15+rdi*8+12Ah], al
0x180039e38  movzx   eax, r8b
0x180039e3c  imul    ecx, eax, 4Bh ; 'K'
0x180039e3f  sub     r11b, cl
0x180039e42  mov     [r15+rdi*8+12Bh], r11b
0x180039e4a  cmp     r14d, 63h ; 'c'
0x180039e4e  jb      short loc_180039E89
0x180039e50  lea     rcx, [rbp+var_48]; this
0x180039e54  call    ?get_TrackSize@CMsftTrackInformation@@QEAAKXZ; CMsftTrackInformation::get_TrackSize(void)
0x180039e59  movzx   ecx, byte ptr [r12+9]
0x180039e5f  add     eax, 98h
0x180039e64  movzx   edx, byte ptr [r12+8]
0x180039e6a  shl     edx, 8
0x180039e6d  or      edx, ecx
0x180039e6f  movzx   ecx, byte ptr [r12+0Ah]
0x180039e75  shl     edx, 8
0x180039e78  or      edx, ecx
0x180039e7a  movzx   ecx, byte ptr [r12+0Bh]
0x180039e80  shl     edx, 8
0x180039e83  or      edx, ecx
0x180039e85  add     eax, edx
0x180039e87  jmp     short loc_180039E92
0x180039e89  lea     rcx, [rbp+var_38]; this
0x180039e8d  call    ?get_NextWritableAddress@CMsftTrackInformation@@QEAAKXZ; CMsftTrackInformation::get_NextWritableAddress(void)
0x180039e92  mov     [r15+118h], eax
0x180039e99  mov     ecx, [r15+110h]
0x180039ea0  sub     ecx, eax
0x180039ea2  mov     [r15+11Ch], r14d
0x180039ea9  sub     ecx, 2
0x180039eac  mov     [r15+114h], ecx
0x180039eb3  jmp     short loc_180039EF7
0x180039eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ebc  lea     rax, WPP_GLOBAL_Control
0x180039ec3  cmp     rcx, rax
0x180039ec6  jz      short loc_180039EF2
0x180039ec8  test    byte ptr [rcx+15Ch], 4
0x180039ecf  jz      short loc_180039EF2
0x180039ed1  cmp     byte ptr [rcx+159h], 3
0x180039ed8  jb      short loc_180039EF2
0x180039eda  mov     edx, 7Fh
0x180039edf  mov     rcx, [rcx+150h]
0x180039ee6  lea     r8, WPP_a247c3a310f734f08a509ab732cfbc0a_Traceguids
0x180039eed  call    WPP_SF_
0x180039ef2  mov     esi, 80004005h
0x180039ef7  lea     rcx, [rbp+var_38]; this
0x180039efb  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x180039f00  lea     rcx, [rbp+var_48]; this
0x180039f04  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x180039f09  lea     rcx, [rbp+var_28]; this
0x180039f0d  call    ??1CMsftDiscInformation@@QEAA@XZ; CMsftDiscInformation::~CMsftDiscInformation(void)
0x180039f12  mov     eax, esi
0x180039f14  add     rsp, 78h
0x180039f18  pop     r15
0x180039f1a  pop     r14
0x180039f1c  pop     r13
0x180039f1e  pop     r12
0x180039f20  pop     rdi
0x180039f21  pop     rsi
0x180039f22  pop     rbx
0x180039f23  pop     rbp
0x180039f24  retn
```
