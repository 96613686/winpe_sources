# Imapi2Utility::GetCurrentDriveSpeed(IDiscRecorder2Ex *,uchar,ulong *)

- ea: `0x180043bb4`
- end: `0x180043f30`
- name: `?GetCurrentDriveSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EPEAK@Z`
- size: `892`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned __int8, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180043f38`
- `0x180047948`

## callees

- `0x1800140f4`
- `0x180016778`
- `0x180043bb4`
- `0x180048108`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180043f00`
- `ole32!CoTaskMemFree` at `0x180043f00`
- `KERNEL32!LocalAlloc` at `0x180043c0a`
- `KERNEL32!LocalAlloc` at `0x180043c0a`
- `KERNEL32!LocalFree` at `0x180043e60`
- `KERNEL32!LocalFree` at `0x180043e60`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::GetCurrentDriveSpeed(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        _DWORD *a3,
        unsigned int *a4)
{
  char v4; // r12
  unsigned __int8 *v7; // rsi
  char v8; // bl
  __int64 v9; // rax
  int v10; // eax
  int v11; // edi
  __int64 v12; // r9
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ecx
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // edx
  unsigned __int8 *v20; // r9
  unsigned int v21; // r10d
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // ecx
  __int64 v25; // rax
  unsigned int v26; // r8d
  void *v27; // rdx
  int v28; // ecx
  int v29; // eax
  int v30; // ecx
  struct _CDVD_CAPABILITIES_PAGE *v32; // [rsp+50h] [rbp-9h] BYREF
  LPVOID pv[2]; // [rsp+58h] [rbp-1h] BYREF
  __int128 v34; // [rsp+68h] [rbp+Fh] BYREF
  __int16 v35; // [rsp+78h] [rbp+1Fh]

  v4 = (char)a2;
  v35 = 0;
  LODWORD(v32) = 0;
  *(_OWORD *)pv = 0;
  v34 = 0;
  v7 = (unsigned __int8 *)LocalAlloc(0x40u, 0xA8u);
  if ( !v7 )
  {
LABEL_36:
    v25 = *(_QWORD *)this;
    pv[0] = 0;
    LODWORD(v32) = 0;
    v11 = (*(__int64 (__fastcall **)(Imapi2Utility *, __int64, _QWORD, LPVOID *, struct _CDVD_CAPABILITIES_PAGE **))(v25 + 104))(
            this,
            42,
            0,
            pv,
            &v32);
    if ( v11 < 0
      || (v11 = Imapi2Utility::ValidateCapabilitiesModePageLength(
                  (Imapi2Utility *)pv[0],
                  (struct _CDVD_CAPABILITIES_PAGE *const)(unsigned int)v32,
                  v26),
          v11 < 0) )
    {
      v27 = pv[0];
      goto LABEL_47;
    }
    v27 = pv[0];
    if ( v4 )
    {
      if ( *((_BYTE *)pv[0] + 1) >= 0x1Cu )
      {
        v30 = *((unsigned __int8 *)pv[0] + 29) | (*((unsigned __int8 *)pv[0] + 28) << 8);
        if ( v30 )
          goto LABEL_45;
      }
      v28 = *((unsigned __int8 *)pv[0] + 20);
      v29 = *((unsigned __int8 *)pv[0] + 21);
    }
    else
    {
      v28 = *((unsigned __int8 *)pv[0] + 14);
      v29 = *((unsigned __int8 *)pv[0] + 15);
    }
    v30 = v29 | (v28 << 8);
LABEL_45:
    *a3 = v30;
LABEL_47:
    CoTaskMemFree(v27);
    return (unsigned int)v11;
  }
  v35 = 0;
  v8 = 0;
  *(_OWORD *)pv = 0;
  v34 = 0;
  memset_0(v7, 0, 0xA8u);
  LOBYTE(pv[0]) = -84;
  *(_WORD *)((char *)&pv[1] + 1) = 10;
  v9 = *(_QWORD *)this;
  BYTE1(pv[0]) = BYTE1(pv[0]) & 0xF3 | (v4 != 0 ? 4 : 0) | 0x10;
  v10 = (*(__int64 (__fastcall **)(Imapi2Utility *, LPVOID *, __int64, __int128 *, int, unsigned __int8 *, int, struct _CDVD_CAPABILITIES_PAGE **))(v9 + 40))(
          this,
          pv,
          12,
          &v34,
          10,
          v7,
          168,
          &v32);
  v11 = v10;
  if ( v10 < 0 )
    goto LABEL_35;
  v12 = (unsigned int)v32;
  if ( !(_DWORD)v32 )
  {
    if ( v10 == 11141632 )
      goto LABEL_35;
LABEL_7:
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v14 = 89;
LABEL_11:
      v15 = v13[2];
LABEL_17:
      WPP_SF_d(v15, v14, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v12);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  if ( (unsigned int)v32 < 8 )
    goto LABEL_7;
  v16 = v7[3] | ((v7[2] | ((v7[1] | (*v7 << 8)) << 8)) << 8);
  if ( v16 >= 4 )
  {
    v17 = v16 - 4;
    if ( ((v7[3] - 4) & 0xF) != 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v14 = 91;
        v12 = v17;
        goto LABEL_11;
      }
    }
    else
    {
      v18 = v17 >> 4;
      if ( v18 )
      {
        v19 = 0;
        v20 = v7 + 8;
        v21 = 0;
        v8 = 1;
        do
        {
          v22 = v20[5];
          v23 = v20[4];
          v20 += 16;
          v24 = *(v20 - 9) | ((*(v20 - 10) | ((v22 | (v23 << 8)) << 8)) << 8);
          if ( v24 <= v19 )
            v24 = v19;
          v19 = *(v20 - 1) | ((*(v20 - 2) | (((*(v20 - 4) << 8) | *(v20 - 3)) << 8)) << 8);
          if ( v19 <= v24 )
            v19 = v24;
          ++v21;
        }
        while ( v21 < v18 );
        *a3 = v19;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v12 = v16;
    v14 = 90;
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    goto LABEL_17;
  }
LABEL_35:
  LocalFree(v7);
  if ( !v8 )
    goto LABEL_36;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180043bb4  mov     [rsp-8+arg_8], rbx
0x180043bb9  mov     [rsp-8+arg_18], rsi
0x180043bbe  push    rbp
0x180043bbf  push    rdi
0x180043bc0  push    r12
0x180043bc2  push    r14
0x180043bc4  push    r15
0x180043bc6  lea     rbp, [rsp-37h]
0x180043bcb  sub     rsp, 90h
0x180043bd2  mov     rax, cs:__security_cookie
0x180043bd9  xor     rax, rsp
0x180043bdc  mov     [rbp+57h+var_30], rax
0x180043be0  xor     eax, eax
0x180043be2  mov     r12b, dl
0x180043be5  mov     r14, rcx
0x180043be8  mov     [rbp+57h+var_38], ax
0x180043bec  xorps   xmm0, xmm0
0x180043bef  mov     dword ptr [rbp+57h+var_60], eax
0x180043bf2  xorps   xmm1, xmm1
0x180043bf5  mov     edi, 0A8h
0x180043bfa  lea     ecx, [rax+40h]; uFlags
0x180043bfd  mov     edx, edi; uBytes
0x180043bff  mov     r15, r8
0x180043c02  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180043c06  movups  [rbp+57h+var_48], xmm1
0x180043c0a  call    cs:__imp_LocalAlloc
0x180043c10  mov     rsi, rax
0x180043c13  test    rax, rax
0x180043c16  jz      loc_180043E6E
0x180043c1c  xorps   xmm0, xmm0
0x180043c1f  xorps   xmm1, xmm1
0x180043c22  xor     eax, eax
0x180043c24  mov     r8d, edi; Size
0x180043c27  xor     edx, edx; Val
0x180043c29  mov     [rbp+57h+var_38], ax
0x180043c2d  mov     rcx, rsi; void *
0x180043c30  xor     bl, bl
0x180043c32  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180043c36  movups  [rbp+57h+var_48], xmm1
0x180043c3a  call    memset_0
0x180043c3f  mov     al, r12b
0x180043c42  mov     byte ptr [rbp+57h+pv], 0ACh
0x180043c46  neg     al
0x180043c48  mov     word ptr [rbp+57h+pv+9], 0Ah
0x180043c4e  mov     al, byte ptr [rbp+57h+pv+1]
0x180043c51  lea     r9, [rbp+57h+var_48]
0x180043c55  sbb     cl, cl
0x180043c57  lea     rdx, [rbp+57h+pv]
0x180043c5b  and     cl, 4
0x180043c5e  and     al, 0F3h
0x180043c60  or      cl, al
0x180043c62  mov     r8d, 0Ch
0x180043c68  mov     rax, [r14]
0x180043c6b  or      cl, 10h
0x180043c6e  mov     byte ptr [rbp+57h+pv+1], cl
0x180043c71  lea     rcx, [rbp+57h+var_60]
0x180043c75  mov     [rsp+0B0h+var_78], rcx
0x180043c7a  mov     rcx, r14
0x180043c7d  mov     [rsp+0B0h+var_80], edi
0x180043c81  mov     rax, [rax+28h]
0x180043c85  mov     [rsp+0B0h+var_88], rsi
0x180043c8a  mov     dword ptr [rsp+0B0h+var_90], 0Ah
0x180043c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c97  mov     edi, eax
0x180043c99  test    eax, eax
0x180043c9b  js      loc_180043E5D
0x180043ca1  mov     r9d, dword ptr [rbp+57h+var_60]
0x180043ca5  test    r9d, r9d
0x180043ca8  jnz     short loc_180043CB6
0x180043caa  cmp     eax, 0AA0200h
0x180043caf  jnz     short loc_180043CBC
0x180043cb1  jmp     loc_180043E5D
0x180043cb6  cmp     r9d, 8
0x180043cba  jnb     short loc_180043CF2
0x180043cbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180043cc3  lea     rax, WPP_GLOBAL_Control
0x180043cca  cmp     rcx, rax
0x180043ccd  jz      loc_180043E5D
0x180043cd3  test    byte ptr [rcx+1Ch], 4
0x180043cd7  jz      loc_180043E5D
0x180043cdd  cmp     byte ptr [rcx+19h], 3
0x180043ce1  jb      loc_180043E5D
0x180043ce7  mov     edx, 59h ; 'Y'
0x180043cec  mov     rcx, [rcx+10h]
0x180043cf0  jmp     short loc_180043D4E
0x180043cf2  movzx   eax, byte ptr [rsi+1]
0x180043cf6  movzx   ecx, byte ptr [rsi]
0x180043cf9  shl     ecx, 8
0x180043cfc  or      ecx, eax
0x180043cfe  movzx   eax, byte ptr [rsi+2]
0x180043d02  shl     ecx, 8
0x180043d05  or      ecx, eax
0x180043d07  movzx   eax, byte ptr [rsi+3]
0x180043d0b  shl     ecx, 8
0x180043d0e  or      ecx, eax
0x180043d10  cmp     ecx, 4
0x180043d13  jnb     short loc_180043D5F
0x180043d15  mov     r10, cs:WPP_GLOBAL_Control
0x180043d1c  lea     rax, WPP_GLOBAL_Control
0x180043d23  cmp     r10, rax
0x180043d26  jz      loc_180043E5D
0x180043d2c  test    byte ptr [r10+1Ch], 4
0x180043d31  jz      loc_180043E5D
0x180043d37  cmp     byte ptr [r10+19h], 3
0x180043d3c  jb      loc_180043E5D
0x180043d42  mov     r9d, ecx
0x180043d45  mov     edx, 5Ah ; 'Z'
0x180043d4a  mov     rcx, [r10+10h]
0x180043d4e  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180043d55  call    WPP_SF_d
0x180043d5a  jmp     loc_180043E5D
0x180043d5f  lea     r8d, [rcx-4]
0x180043d63  test    r8b, 0Fh
0x180043d67  jz      short loc_180043DA1
0x180043d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d70  lea     rax, WPP_GLOBAL_Control
0x180043d77  cmp     rcx, rax
0x180043d7a  jz      loc_180043E5D
0x180043d80  test    byte ptr [rcx+1Ch], 4
0x180043d84  jz      loc_180043E5D
0x180043d8a  cmp     byte ptr [rcx+19h], 3
0x180043d8e  jb      loc_180043E5D
0x180043d94  mov     edx, 5Bh ; '['
0x180043d99  mov     r9d, r8d
0x180043d9c  jmp     loc_180043CEC
0x180043da1  shr     r8d, 4
0x180043da5  test    r8d, r8d
0x180043da8  jnz     short loc_180043DEB
0x180043daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180043db1  lea     rax, WPP_GLOBAL_Control
0x180043db8  cmp     rcx, rax
0x180043dbb  jz      loc_180043E5D
0x180043dc1  test    byte ptr [rcx+1Ch], 4
0x180043dc5  jz      loc_180043E5D
0x180043dcb  cmp     byte ptr [rcx+19h], 3
0x180043dcf  jb      loc_180043E5D
0x180043dd5  mov     rcx, [rcx+10h]
0x180043dd9  lea     edx, [r8+5Ch]
0x180043ddd  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180043de4  call    WPP_SF_
0x180043de9  jmp     short loc_180043E5D
0x180043deb  xor     edx, edx
0x180043ded  lea     r9, [rsi+8]
0x180043df1  xor     r10d, r10d
0x180043df4  mov     ebx, 1
0x180043df9  test    r8d, r8d
0x180043dfc  jz      short loc_180043E5A
0x180043dfe  movzx   eax, byte ptr [r9+5]
0x180043e03  movzx   ecx, byte ptr [r9+4]
0x180043e08  lea     r9, [r9+10h]
0x180043e0c  shl     ecx, 8
0x180043e0f  or      ecx, eax
0x180043e11  movzx   eax, byte ptr [r9-0Ah]
0x180043e16  shl     ecx, 8
0x180043e19  or      ecx, eax
0x180043e1b  movzx   eax, byte ptr [r9-9]
0x180043e20  shl     ecx, 8
0x180043e23  or      ecx, eax
0x180043e25  movzx   eax, byte ptr [r9-4]
0x180043e2a  cmp     ecx, edx
0x180043e2c  cmovbe  ecx, edx
0x180043e2f  movzx   edx, byte ptr [r9-3]
0x180043e34  shl     eax, 8
0x180043e37  or      edx, eax
0x180043e39  movzx   eax, byte ptr [r9-2]
0x180043e3e  shl     edx, 8
0x180043e41  or      edx, eax
0x180043e43  movzx   eax, byte ptr [r9-1]
0x180043e48  shl     edx, 8
0x180043e4b  or      edx, eax
0x180043e4d  cmp     edx, ecx
0x180043e4f  cmovbe  edx, ecx
0x180043e52  add     r10d, ebx
0x180043e55  cmp     r10d, r8d
0x180043e58  jb      short loc_180043DFE
0x180043e5a  mov     [r15], edx
0x180043e5d  mov     rcx, rsi; hMem
0x180043e60  call    cs:__imp_LocalFree
0x180043e66  test    bl, bl
0x180043e68  jnz     loc_180043F06
0x180043e6e  mov     rax, [r14]
0x180043e71  lea     rcx, [rbp+57h+var_60]
0x180043e75  xor     r8d, r8d
0x180043e78  mov     [rsp+0B0h+var_90], rcx
0x180043e7d  lea     r9, [rbp+57h+pv]
0x180043e81  mov     [rbp+57h+pv], 0
0x180043e89  mov     rcx, r14
0x180043e8c  mov     dword ptr [rbp+57h+var_60], 0
0x180043e93  mov     rax, [rax+68h]
0x180043e97  lea     edx, [r8+2Ah]
0x180043e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ea0  mov     edi, eax
0x180043ea2  test    eax, eax
0x180043ea4  js      short loc_180043EF9
0x180043ea6  mov     edx, dword ptr [rbp+57h+var_60]; struct _CDVD_CAPABILITIES_PAGE *
0x180043ea9  mov     rcx, [rbp+57h+pv]; this
0x180043ead  call    ?ValidateCapabilitiesModePageLength@Imapi2Utility@@YAJQEAU_CDVD_CAPABILITIES_PAGE@@K@Z; Imapi2Utility::ValidateCapabilitiesModePageLength(_CDVD_CAPABILITIES_PAGE * const,ulong)
0x180043eb2  mov     edi, eax
0x180043eb4  test    eax, eax
0x180043eb6  js      short loc_180043EF9
0x180043eb8  mov     rdx, [rbp+57h+pv]
0x180043ebc  test    r12b, r12b
0x180043ebf  jz      short loc_180043EE7
0x180043ec1  mov     al, [rdx+1]
0x180043ec4  cmp     al, 18h
0x180043ec6  jnb     short loc_180043ED2
0x180043ec8  movzx   ecx, byte ptr [rdx+14h]
0x180043ecc  movzx   eax, byte ptr [rdx+15h]
0x180043ed0  jmp     short loc_180043EEF
0x180043ed2  cmp     al, 1Ch
0x180043ed4  jb      short loc_180043EC8
0x180043ed6  movzx   ecx, byte ptr [rdx+1Ch]
0x180043eda  movzx   eax, byte ptr [rdx+1Dh]
0x180043ede  shl     ecx, 8
0x180043ee1  or      ecx, eax
0x180043ee3  jnz     short loc_180043EF4
0x180043ee5  jmp     short loc_180043EC8
0x180043ee7  movzx   ecx, byte ptr [rdx+0Eh]
0x180043eeb  movzx   eax, byte ptr [rdx+0Fh]
0x180043eef  shl     ecx, 8
0x180043ef2  or      ecx, eax
0x180043ef4  mov     [r15], ecx
0x180043ef7  jmp     short loc_180043EFD
0x180043ef9  mov     rdx, [rbp+57h+pv]
0x180043efd  mov     rcx, rdx; pv
0x180043f00  call    cs:__imp_CoTaskMemFree
0x180043f06  mov     eax, edi
0x180043f08  mov     rcx, [rbp+57h+var_30]
0x180043f0c  xor     rcx, rsp; StackCookie
0x180043f0f  call    __security_check_cookie
0x180043f14  lea     r11, [rsp+0B0h+var_20]
0x180043f1c  mov     rbx, [r11+38h]
0x180043f20  mov     rsi, [r11+48h]
0x180043f24  mov     rsp, r11
0x180043f27  pop     r15
0x180043f29  pop     r14
0x180043f2b  pop     r12
0x180043f2d  pop     rdi
0x180043f2e  pop     rbp
0x180043f2f  retn
```
