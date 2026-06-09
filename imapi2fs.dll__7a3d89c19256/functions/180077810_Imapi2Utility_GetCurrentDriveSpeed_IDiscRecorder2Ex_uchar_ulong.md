# Imapi2Utility::GetCurrentDriveSpeed(IDiscRecorder2Ex *,uchar,ulong *)

- ea: `0x180077810`
- end: `0x180077b8c`
- name: `?GetCurrentDriveSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EPEAK@Z`
- size: `892`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned __int8, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000aeb0`

## callees

- `0x1800063b8`
- `0x180028568`
- `0x180077810`
- `0x1800785e0`
- `0x18008170e`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180077b5c`
- `ole32!CoTaskMemFree` at `0x180077b5c`
- `KERNEL32!LocalAlloc` at `0x180077866`
- `KERNEL32!LocalAlloc` at `0x180077866`
- `KERNEL32!LocalFree` at `0x180077abc`
- `KERNEL32!LocalFree` at `0x180077abc`

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
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // ecx
  unsigned int v16; // r8d
  unsigned int v17; // edx
  unsigned __int8 *v18; // r9
  unsigned int v19; // r10d
  int v20; // eax
  int v21; // ecx
  unsigned int v22; // ecx
  __int64 v23; // rax
  unsigned int v24; // r8d
  void *v25; // rdx
  int v26; // ecx
  int v27; // eax
  int v28; // ecx
  struct _CDVD_CAPABILITIES_PAGE *v30; // [rsp+50h] [rbp-9h] BYREF
  LPVOID pv[2]; // [rsp+58h] [rbp-1h] BYREF
  __int128 v32; // [rsp+68h] [rbp+Fh] BYREF
  __int16 v33; // [rsp+78h] [rbp+1Fh]

  v4 = (char)a2;
  v33 = 0;
  LODWORD(v30) = 0;
  *(_OWORD *)pv = 0;
  v32 = 0;
  v7 = (unsigned __int8 *)LocalAlloc(0x40u, 0xA8u);
  if ( !v7 )
  {
LABEL_36:
    v23 = *(_QWORD *)this;
    pv[0] = 0;
    LODWORD(v30) = 0;
    v11 = (*(__int64 (__fastcall **)(Imapi2Utility *, __int64, _QWORD, LPVOID *, struct _CDVD_CAPABILITIES_PAGE **))(v23 + 104))(
            this,
            42,
            0,
            pv,
            &v30);
    if ( v11 < 0
      || (v11 = Imapi2Utility::ValidateCapabilitiesModePageLength(
                  (Imapi2Utility *)pv[0],
                  (struct _CDVD_CAPABILITIES_PAGE *const)(unsigned int)v30,
                  v24),
          v11 < 0) )
    {
      v25 = pv[0];
      goto LABEL_47;
    }
    v25 = pv[0];
    if ( v4 )
    {
      if ( *((_BYTE *)pv[0] + 1) >= 0x1Cu )
      {
        v28 = *((unsigned __int8 *)pv[0] + 29) | (*((unsigned __int8 *)pv[0] + 28) << 8);
        if ( v28 )
          goto LABEL_45;
      }
      v26 = *((unsigned __int8 *)pv[0] + 20);
      v27 = *((unsigned __int8 *)pv[0] + 21);
    }
    else
    {
      v26 = *((unsigned __int8 *)pv[0] + 14);
      v27 = *((unsigned __int8 *)pv[0] + 15);
    }
    v28 = v27 | (v26 << 8);
LABEL_45:
    *a3 = v28;
LABEL_47:
    CoTaskMemFree(v25);
    return (unsigned int)v11;
  }
  v33 = 0;
  v8 = 0;
  *(_OWORD *)pv = 0;
  v32 = 0;
  memset_0(v7, 0, 0xA8u);
  LOBYTE(pv[0]) = -84;
  *(_WORD *)((char *)&pv[1] + 1) = 10;
  v9 = *(_QWORD *)this;
  BYTE1(pv[0]) = BYTE1(pv[0]) & 0xF3 | (v4 != 0 ? 4 : 0) | 0x10;
  v10 = (*(__int64 (__fastcall **)(Imapi2Utility *, LPVOID *, __int64, __int128 *, int, unsigned __int8 *, int, struct _CDVD_CAPABILITIES_PAGE **))(v9 + 40))(
          this,
          pv,
          12,
          &v32,
          10,
          v7,
          168,
          &v30);
  v11 = v10;
  if ( v10 < 0 )
    goto LABEL_35;
  if ( !(_DWORD)v30 )
  {
    if ( v10 == 11141632 )
      goto LABEL_35;
LABEL_7:
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v13 = 89;
LABEL_11:
      v14 = v12[2];
LABEL_17:
      WPP_SF_d(v14, v13, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  if ( (unsigned int)v30 < 8 )
    goto LABEL_7;
  v15 = v7[3] | ((v7[2] | ((v7[1] | (*v7 << 8)) << 8)) << 8);
  if ( v15 >= 4 )
  {
    if ( ((v7[3] - 4) & 0xF) != 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v13 = 91;
        goto LABEL_11;
      }
    }
    else
    {
      v16 = (v15 - 4) >> 4;
      if ( v16 )
      {
        v17 = 0;
        v18 = v7 + 8;
        v19 = 0;
        v8 = 1;
        do
        {
          v20 = v18[5];
          v21 = v18[4];
          v18 += 16;
          v22 = *(v18 - 9) | ((*(v18 - 10) | ((v20 | (v21 << 8)) << 8)) << 8);
          if ( v22 <= v17 )
            v22 = v17;
          v17 = *(v18 - 1) | ((*(v18 - 2) | (((*(v18 - 4) << 8) | *(v18 - 3)) << 8)) << 8);
          if ( v17 <= v22 )
            v17 = v22;
          ++v19;
        }
        while ( v19 < v16 );
        *a3 = v17;
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
    v13 = 90;
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
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
0x180077810  mov     [rsp-8+arg_8], rbx
0x180077815  mov     [rsp-8+arg_18], rsi
0x18007781a  push    rbp
0x18007781b  push    rdi
0x18007781c  push    r12
0x18007781e  push    r14
0x180077820  push    r15
0x180077822  lea     rbp, [rsp-37h]
0x180077827  sub     rsp, 90h
0x18007782e  mov     rax, cs:__security_cookie
0x180077835  xor     rax, rsp
0x180077838  mov     [rbp+57h+var_30], rax
0x18007783c  xor     eax, eax
0x18007783e  mov     r12b, dl
0x180077841  mov     r14, rcx
0x180077844  mov     [rbp+57h+var_38], ax
0x180077848  xorps   xmm0, xmm0
0x18007784b  mov     dword ptr [rbp+57h+var_60], eax
0x18007784e  xorps   xmm1, xmm1
0x180077851  mov     edi, 0A8h
0x180077856  lea     ecx, [rax+40h]; uFlags
0x180077859  mov     edx, edi; uBytes
0x18007785b  mov     r15, r8
0x18007785e  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180077862  movups  [rbp+57h+var_48], xmm1
0x180077866  call    cs:__imp_LocalAlloc
0x18007786c  mov     rsi, rax
0x18007786f  test    rax, rax
0x180077872  jz      loc_180077ACA
0x180077878  xorps   xmm0, xmm0
0x18007787b  xorps   xmm1, xmm1
0x18007787e  xor     eax, eax
0x180077880  mov     r8d, edi; Size
0x180077883  xor     edx, edx; Val
0x180077885  mov     [rbp+57h+var_38], ax
0x180077889  mov     rcx, rsi; void *
0x18007788c  xor     bl, bl
0x18007788e  movups  xmmword ptr [rbp+57h+pv], xmm0
0x180077892  movups  [rbp+57h+var_48], xmm1
0x180077896  call    memset_0
0x18007789b  mov     al, r12b
0x18007789e  mov     byte ptr [rbp+57h+pv], 0ACh
0x1800778a2  neg     al
0x1800778a4  mov     word ptr [rbp+57h+pv+9], 0Ah
0x1800778aa  mov     al, byte ptr [rbp+57h+pv+1]
0x1800778ad  lea     r9, [rbp+57h+var_48]
0x1800778b1  sbb     cl, cl
0x1800778b3  lea     rdx, [rbp+57h+pv]
0x1800778b7  and     cl, 4
0x1800778ba  and     al, 0F3h
0x1800778bc  or      cl, al
0x1800778be  mov     r8d, 0Ch
0x1800778c4  mov     rax, [r14]
0x1800778c7  or      cl, 10h
0x1800778ca  mov     byte ptr [rbp+57h+pv+1], cl
0x1800778cd  lea     rcx, [rbp+57h+var_60]
0x1800778d1  mov     [rsp+0B0h+var_78], rcx
0x1800778d6  mov     rcx, r14
0x1800778d9  mov     [rsp+0B0h+var_80], edi
0x1800778dd  mov     rax, [rax+28h]
0x1800778e1  mov     [rsp+0B0h+var_88], rsi
0x1800778e6  mov     dword ptr [rsp+0B0h+var_90], 0Ah
0x1800778ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800778f3  mov     edi, eax
0x1800778f5  test    eax, eax
0x1800778f7  js      loc_180077AB9
0x1800778fd  mov     r9d, dword ptr [rbp+57h+var_60]
0x180077901  test    r9d, r9d
0x180077904  jnz     short loc_180077912
0x180077906  cmp     eax, 0AA0200h
0x18007790b  jnz     short loc_180077918
0x18007790d  jmp     loc_180077AB9
0x180077912  cmp     r9d, 8
0x180077916  jnb     short loc_18007794E
0x180077918  mov     rcx, cs:WPP_GLOBAL_Control
0x18007791f  lea     rax, WPP_GLOBAL_Control
0x180077926  cmp     rcx, rax
0x180077929  jz      loc_180077AB9
0x18007792f  test    byte ptr [rcx+1Ch], 4
0x180077933  jz      loc_180077AB9
0x180077939  cmp     byte ptr [rcx+19h], 3
0x18007793d  jb      loc_180077AB9
0x180077943  mov     edx, 59h ; 'Y'
0x180077948  mov     rcx, [rcx+10h]
0x18007794c  jmp     short loc_1800779AA
0x18007794e  movzx   eax, byte ptr [rsi+1]
0x180077952  movzx   ecx, byte ptr [rsi]
0x180077955  shl     ecx, 8
0x180077958  or      ecx, eax
0x18007795a  movzx   eax, byte ptr [rsi+2]
0x18007795e  shl     ecx, 8
0x180077961  or      ecx, eax
0x180077963  movzx   eax, byte ptr [rsi+3]
0x180077967  shl     ecx, 8
0x18007796a  or      ecx, eax
0x18007796c  cmp     ecx, 4
0x18007796f  jnb     short loc_1800779BB
0x180077971  mov     r10, cs:WPP_GLOBAL_Control
0x180077978  lea     rax, WPP_GLOBAL_Control
0x18007797f  cmp     r10, rax
0x180077982  jz      loc_180077AB9
0x180077988  test    byte ptr [r10+1Ch], 4
0x18007798d  jz      loc_180077AB9
0x180077993  cmp     byte ptr [r10+19h], 3
0x180077998  jb      loc_180077AB9
0x18007799e  mov     r9d, ecx
0x1800779a1  mov     edx, 5Ah ; 'Z'
0x1800779a6  mov     rcx, [r10+10h]
0x1800779aa  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800779b1  call    WPP_SF_d
0x1800779b6  jmp     loc_180077AB9
0x1800779bb  lea     r8d, [rcx-4]
0x1800779bf  test    r8b, 0Fh
0x1800779c3  jz      short loc_1800779FD
0x1800779c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800779cc  lea     rax, WPP_GLOBAL_Control
0x1800779d3  cmp     rcx, rax
0x1800779d6  jz      loc_180077AB9
0x1800779dc  test    byte ptr [rcx+1Ch], 4
0x1800779e0  jz      loc_180077AB9
0x1800779e6  cmp     byte ptr [rcx+19h], 3
0x1800779ea  jb      loc_180077AB9
0x1800779f0  mov     edx, 5Bh ; '['
0x1800779f5  mov     r9d, r8d
0x1800779f8  jmp     loc_180077948
0x1800779fd  shr     r8d, 4
0x180077a01  test    r8d, r8d
0x180077a04  jnz     short loc_180077A47
0x180077a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180077a0d  lea     rax, WPP_GLOBAL_Control
0x180077a14  cmp     rcx, rax
0x180077a17  jz      loc_180077AB9
0x180077a1d  test    byte ptr [rcx+1Ch], 4
0x180077a21  jz      loc_180077AB9
0x180077a27  cmp     byte ptr [rcx+19h], 3
0x180077a2b  jb      loc_180077AB9
0x180077a31  mov     rcx, [rcx+10h]
0x180077a35  lea     edx, [r8+5Ch]
0x180077a39  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180077a40  call    WPP_SF_
0x180077a45  jmp     short loc_180077AB9
0x180077a47  xor     edx, edx
0x180077a49  lea     r9, [rsi+8]
0x180077a4d  xor     r10d, r10d
0x180077a50  mov     ebx, 1
0x180077a55  test    r8d, r8d
0x180077a58  jz      short loc_180077AB6
0x180077a5a  movzx   eax, byte ptr [r9+5]
0x180077a5f  movzx   ecx, byte ptr [r9+4]
0x180077a64  lea     r9, [r9+10h]
0x180077a68  shl     ecx, 8
0x180077a6b  or      ecx, eax
0x180077a6d  movzx   eax, byte ptr [r9-0Ah]
0x180077a72  shl     ecx, 8
0x180077a75  or      ecx, eax
0x180077a77  movzx   eax, byte ptr [r9-9]
0x180077a7c  shl     ecx, 8
0x180077a7f  or      ecx, eax
0x180077a81  movzx   eax, byte ptr [r9-4]
0x180077a86  cmp     ecx, edx
0x180077a88  cmovbe  ecx, edx
0x180077a8b  movzx   edx, byte ptr [r9-3]
0x180077a90  shl     eax, 8
0x180077a93  or      edx, eax
0x180077a95  movzx   eax, byte ptr [r9-2]
0x180077a9a  shl     edx, 8
0x180077a9d  or      edx, eax
0x180077a9f  movzx   eax, byte ptr [r9-1]
0x180077aa4  shl     edx, 8
0x180077aa7  or      edx, eax
0x180077aa9  cmp     edx, ecx
0x180077aab  cmovbe  edx, ecx
0x180077aae  add     r10d, ebx
0x180077ab1  cmp     r10d, r8d
0x180077ab4  jb      short loc_180077A5A
0x180077ab6  mov     [r15], edx
0x180077ab9  mov     rcx, rsi; hMem
0x180077abc  call    cs:__imp_LocalFree
0x180077ac2  test    bl, bl
0x180077ac4  jnz     loc_180077B62
0x180077aca  mov     rax, [r14]
0x180077acd  lea     rcx, [rbp+57h+var_60]
0x180077ad1  xor     r8d, r8d
0x180077ad4  mov     [rsp+0B0h+var_90], rcx
0x180077ad9  lea     r9, [rbp+57h+pv]
0x180077add  mov     [rbp+57h+pv], 0
0x180077ae5  mov     rcx, r14
0x180077ae8  mov     dword ptr [rbp+57h+var_60], 0
0x180077aef  mov     rax, [rax+68h]
0x180077af3  lea     edx, [r8+2Ah]
0x180077af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077afc  mov     edi, eax
0x180077afe  test    eax, eax
0x180077b00  js      short loc_180077B55
0x180077b02  mov     edx, dword ptr [rbp+57h+var_60]; struct _CDVD_CAPABILITIES_PAGE *
0x180077b05  mov     rcx, [rbp+57h+pv]; this
0x180077b09  call    ?ValidateCapabilitiesModePageLength@Imapi2Utility@@YAJQEAU_CDVD_CAPABILITIES_PAGE@@K@Z; Imapi2Utility::ValidateCapabilitiesModePageLength(_CDVD_CAPABILITIES_PAGE * const,ulong)
0x180077b0e  mov     edi, eax
0x180077b10  test    eax, eax
0x180077b12  js      short loc_180077B55
0x180077b14  mov     rdx, [rbp+57h+pv]
0x180077b18  test    r12b, r12b
0x180077b1b  jz      short loc_180077B43
0x180077b1d  mov     al, [rdx+1]
0x180077b20  cmp     al, 18h
0x180077b22  jnb     short loc_180077B2E
0x180077b24  movzx   ecx, byte ptr [rdx+14h]
0x180077b28  movzx   eax, byte ptr [rdx+15h]
0x180077b2c  jmp     short loc_180077B4B
0x180077b2e  cmp     al, 1Ch
0x180077b30  jb      short loc_180077B24
0x180077b32  movzx   ecx, byte ptr [rdx+1Ch]
0x180077b36  movzx   eax, byte ptr [rdx+1Dh]
0x180077b3a  shl     ecx, 8
0x180077b3d  or      ecx, eax
0x180077b3f  jnz     short loc_180077B50
0x180077b41  jmp     short loc_180077B24
0x180077b43  movzx   ecx, byte ptr [rdx+0Eh]
0x180077b47  movzx   eax, byte ptr [rdx+0Fh]
0x180077b4b  shl     ecx, 8
0x180077b4e  or      ecx, eax
0x180077b50  mov     [r15], ecx
0x180077b53  jmp     short loc_180077B59
0x180077b55  mov     rdx, [rbp+57h+pv]
0x180077b59  mov     rcx, rdx; pv
0x180077b5c  call    cs:__imp_CoTaskMemFree
0x180077b62  mov     eax, edi
0x180077b64  mov     rcx, [rbp+57h+var_30]
0x180077b68  xor     rcx, rsp; StackCookie
0x180077b6b  call    __security_check_cookie
0x180077b70  lea     r11, [rsp+0B0h+var_20]
0x180077b78  mov     rbx, [r11+38h]
0x180077b7c  mov     rsi, [r11+48h]
0x180077b80  mov     rsp, r11
0x180077b83  pop     r15
0x180077b85  pop     r14
0x180077b87  pop     r12
0x180077b89  pop     rdi
0x180077b8a  pop     rbp
0x180077b8b  retn
```
