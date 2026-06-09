# ComputeCompoundMac

- ea: `0x1400144c4`
- end: `0x1400148e8`
- name: `ComputeCompoundMac`
- size: `1060`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400161b0`
- `0x1400169a4`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140002fc4`
- `0x140005e10`
- `0x140005f40`
- `0x1400144c4`
- `0x1400159a4`
- `0x1400159f8`

## pseudocode

```c
__int64 __fastcall ComputeCompoundMac(__int64 a1, UCHAR *a2, ULONG a3, UCHAR *a4, __int64 a5)
{
  __int64 v5; // r15
  UCHAR *v6; // r14
  _OWORD *v10; // r10
  unsigned __int64 v11; // rax
  __int64 v12; // rsi
  __int128 v13; // xmm1
  unsigned int v14; // r15d
  const void *v15; // r14
  size_t v16; // r8
  char v17; // al
  unsigned int HmacSha1Hash; // eax
  unsigned int HmacSha256Hash; // ebx
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  __int64 v23; // [rsp+30h] [rbp-81h] BYREF
  UCHAR *v24; // [rsp+38h] [rbp-79h]
  __int64 v25; // [rsp+40h] [rbp-71h]
  _OWORD v26[2]; // [rsp+48h] [rbp-69h] BYREF
  UCHAR pbInput[32]; // [rsp+68h] [rbp-49h] BYREF
  UCHAR pbSecret[16]; // [rsp+88h] [rbp-29h] BYREF
  __int128 v29; // [rsp+98h] [rbp-19h]
  UCHAR v30[16]; // [rsp+A8h] [rbp-9h] BYREF
  __int128 v31; // [rsp+B8h] [rbp+7h]

  v5 = a5;
  v6 = a4;
  v24 = a4;
  strcpy((char *)v26, "SSTP inner method derived CMK");
  v25 = a5;
  memset(pbInput, 0, sizeof(pbInput));
  *(_OWORD *)pbSecret = 0;
  v29 = 0;
  *(_OWORD *)v30 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  v10 = (_OWORD *)((-(__int64)(*(_BYTE *)(a1 + 326) != 0) & 0xFFFFFFFFFFFFFFD9uLL) + a1 + 268);
  v11 = -(__int64)(*(_BYTE *)(a1 + 326) != 0) & 0xFFFFFFFFFFFFFFDCuLL;
  v12 = *(unsigned int *)(v11 + a1 + 300);
  if ( (unsigned int)v12 < 0x20 )
  {
    v14 = *(_DWORD *)((*(_BYTE *)(a1 + 326) != 0 ? 0x24 : 0) + a1 + 264);
    v15 = (const void *)((*(_BYTE *)(a1 + 326) != 0 ? 268LL : 229LL) + a1);
    memmove(
      pbSecret,
      (const void *)((-(__int64)(*(_BYTE *)(a1 + 326) != 0) & 0xFFFFFFFFFFFFFFD9uLL) + a1 + 268),
      *(unsigned int *)(v11 + a1 + 300));
    v16 = v14;
    if ( 32 - (int)v12 <= v14 )
      v16 = (unsigned int)(32 - v12);
    memmove(&pbSecret[v12], v15, v16);
    v5 = v25;
    v6 = v24;
  }
  else
  {
    v13 = v10[1];
    *(_OWORD *)pbSecret = *v10;
    v29 = v13;
  }
  v17 = *(_BYTE *)(a1 + 176);
  if ( v17 == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
    LOWORD(v23) = 20;
    *(_WORD *)&pbInput[29] = 20;
    *(_OWORD *)pbInput = v26[0];
    pbInput[31] = 1;
    *(_OWORD *)&pbInput[13] = *(_OWORD *)((char *)v26 + 13);
    HmacSha1Hash = GenerateHmacSha1Hash(pbSecret, 0x20u, pbInput, 0x20u, v30, (__int64)&v23);
    HmacSha256Hash = HmacSha1Hash;
    if ( HmacSha1Hash )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return HmacSha256Hash;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF__guid_D(
          WPP_GLOBAL_Control->AttachedDevice,
          57,
          WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids,
          a1 + 364,
          HmacSha1Hash);
    }
    else
    {
      HmacSha256Hash = GenerateHmacSha1Hash(v30, (unsigned __int16)v23, a2, a3, v6, v5);
      if ( HmacSha256Hash )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return HmacSha256Hash;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF__guid_D(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids,
            a1 + 364,
            HmacSha256Hash);
      }
    }
  }
  else
  {
    HmacSha256Hash = 0;
    if ( v17 == 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
      }
      LOWORD(v23) = 32;
      strcpy((char *)&pbInput[29], " ");
      *(_OWORD *)pbInput = v26[0];
      pbInput[31] = 1;
      *(_OWORD *)&pbInput[13] = *(_OWORD *)((char *)v26 + 13);
      HmacSha256Hash = GenerateHmacSha256Hash(pbSecret, 0x20u, pbInput, 0x20u, v30, (__int64)&v23);
      if ( HmacSha256Hash )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return HmacSha256Hash;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
          goto LABEL_41;
        v21 = 60;
      }
      else
      {
        HmacSha256Hash = GenerateHmacSha256Hash(v30, (unsigned __int16)v23, a2, a3, v6, v5);
        if ( !HmacSha256Hash )
          goto LABEL_41;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return HmacSha256Hash;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
          goto LABEL_41;
        v21 = 61;
      }
      WPP_SF__guid_D(
        v20->AttachedDevice,
        v21,
        WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids,
        a1 + 364,
        HmacSha256Hash);
    }
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  return HmacSha256Hash;
}

```

## disassembly

```asm
0x1400144c4  mov     [rsp-8+arg_10], rbx
0x1400144c9  push    rbp
0x1400144ca  push    rsi
0x1400144cb  push    rdi
0x1400144cc  push    r12
0x1400144ce  push    r13
0x1400144d0  push    r14
0x1400144d2  push    r15
0x1400144d4  lea     rbp, [rsp-1Fh]
0x1400144d9  sub     rsp, 0D0h
0x1400144e0  mov     rax, cs:__security_cookie
0x1400144e7  xor     rax, rsp
0x1400144ea  mov     [rbp+4Fh+var_38], rax
0x1400144ee  movups  xmm0, xmmword ptr cs:aSstpInnerMetho; "SSTP inner method derived CMK"
0x1400144f5  mov     r15, [rbp+4Fh+arg_20]
0x1400144f9  mov     r14, r9
0x1400144fc  movups  xmm1, xmmword ptr cs:aSstpInnerMetho+0Eh; "hod derived CMK"
0x140014503  mov     [rbp+4Fh+var_C8], r9
0x140014507  mov     r12d, r8d
0x14001450a  movups  xmmword ptr [rbp+4Fh+var_B8], xmm0
0x14001450e  mov     [rbp+4Fh+var_C0], r15
0x140014512  mov     r13, rdx
0x140014515  xorps   xmm0, xmm0
0x140014518  mov     rdi, rcx
0x14001451b  movups  xmmword ptr [rbp+4Fh+var_B8+0Eh], xmm1
0x14001451f  xorps   xmm1, xmm1
0x140014522  movups  xmmword ptr [rbp+4Fh+pbInput], xmm1
0x140014526  movups  [rbp+4Fh+var_88], xmm1
0x14001452a  movups  xmmword ptr [rbp+4Fh+pbSecret], xmm0
0x14001452e  movups  [rbp+4Fh+var_68], xmm0
0x140014532  movups  xmmword ptr [rbp+4Fh+var_58], xmm0
0x140014536  movups  [rbp+4Fh+var_48], xmm0
0x14001453a  mov     rcx, cs:WPP_GLOBAL_Control
0x140014541  lea     rbx, WPP_GLOBAL_Control
0x140014548  cmp     rcx, rbx
0x14001454b  jz      short loc_14001456E
0x14001454d  mov     eax, [rcx+2Ch]
0x140014550  and     eax, 84h
0x140014555  cmp     al, 84h
0x140014557  jnz     short loc_14001456E
0x140014559  mov     rcx, [rcx+18h]
0x14001455d  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140014564  mov     edx, 37h ; '7'
0x140014569  call    WPP_SF_
0x14001456e  mov     dl, [rdi+146h]
0x140014574  lea     r10, [rdi+10Ch]
0x14001457b  mov     al, dl
0x14001457d  neg     al
0x14001457f  mov     al, dl
0x140014581  sbb     r8, r8
0x140014584  and     r8d, 24h
0x140014588  neg     al
0x14001458a  mov     al, dl
0x14001458c  sbb     r9, r9
0x14001458f  and     r9d, 27h
0x140014593  add     r9, 0E5h
0x14001459a  neg     al
0x14001459c  sbb     rcx, rcx
0x14001459f  and     rcx, 0FFFFFFFFFFFFFFD9h
0x1400145a3  add     r10, rcx
0x1400145a6  neg     dl
0x1400145a8  sbb     rax, rax
0x1400145ab  and     rax, 0FFFFFFFFFFFFFFDCh
0x1400145af  mov     esi, [rax+rdi+12Ch]
0x1400145b6  cmp     esi, 20h ; ' '
0x1400145b9  jb      short loc_1400145CE
0x1400145bb  movups  xmm0, xmmword ptr [r10]
0x1400145bf  movups  xmm1, xmmword ptr [r10+10h]
0x1400145c4  movups  xmmword ptr [rbp+4Fh+pbSecret], xmm0
0x1400145c8  movups  [rbp+4Fh+var_68], xmm1
0x1400145cc  jmp     short loc_140014619
0x1400145ce  mov     r15d, [r8+rdi+108h]
0x1400145d6  lea     rcx, [rbp+4Fh+pbSecret]; void *
0x1400145da  mov     r8, rsi; Size
0x1400145dd  lea     r14, [r9+rdi]
0x1400145e1  mov     rdx, r10; Src
0x1400145e4  call    memmove
0x1400145e9  mov     eax, 20h ; ' '
0x1400145ee  lea     rcx, [rbp+4Fh+pbSecret]
0x1400145f2  sub     eax, esi
0x1400145f4  add     rcx, rsi; void *
0x1400145f7  mov     rdx, r14; Src
0x1400145fa  mov     r8d, r15d
0x1400145fd  cmp     eax, r15d
0x140014600  ja      short loc_140014605
0x140014602  mov     r8d, eax; Size
0x140014605  call    memmove
0x14001460a  mov     r15, [rbp+4Fh+var_C0]
0x14001460e  lea     rbx, WPP_GLOBAL_Control
0x140014615  mov     r14, [rbp+4Fh+var_C8]
0x140014619  mov     al, [rdi+0B0h]
0x14001461f  cmp     al, 1
0x140014621  jnz     loc_140014764
0x140014627  mov     rcx, cs:WPP_GLOBAL_Control
0x14001462e  mov     sil, 4
0x140014631  cmp     rcx, rbx
0x140014634  jz      short loc_140014660
0x140014636  mov     eax, [rcx+2Ch]
0x140014639  test    sil, al
0x14001463c  jz      short loc_140014660
0x14001463e  cmp     byte ptr [rcx+29h], 2
0x140014642  jb      short loc_140014660
0x140014644  mov     rcx, [rcx+18h]
0x140014648  lea     r9, [rdi+16Ch]
0x14001464f  mov     edx, 38h ; '8'
0x140014654  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14001465b  call    WPP_SF__guid_
0x140014660  movups  xmm0, xmmword ptr [rbp+4Fh+var_B8]
0x140014664  mov     eax, 14h
0x140014669  lea     r8, [rbp+4Fh+pbInput]; pbInput
0x14001466d  movups  xmm1, xmmword ptr [rbp+4Fh+var_B8+0Dh]
0x140014671  mov     word ptr [rsp+100h+var_D0], ax
0x140014676  lea     rcx, [rbp+4Fh+pbSecret]; pbSecret
0x14001467a  mov     word ptr [rbp+4Fh+var_88+0Dh], ax
0x14001467e  lea     rax, [rsp+100h+var_D0]
0x140014683  mov     [rsp+100h+var_D8], rax; __int64
0x140014688  lea     rax, [rbp+4Fh+var_58]
0x14001468c  mov     [rsp+100h+var_E0], rax; PUCHAR
0x140014691  mov     eax, 20h ; ' '
0x140014696  movups  xmmword ptr [rbp+4Fh+pbInput], xmm0
0x14001469a  mov     r9d, eax; cbInput
0x14001469d  mov     byte ptr [rbp+4Fh+var_88+0Fh], 1
0x1400146a1  mov     edx, eax; cbSecret
0x1400146a3  movups  xmmword ptr [rbp+4Fh+pbInput+0Dh], xmm1
0x1400146a7  call    GenerateHmacSha1Hash
0x1400146ac  mov     ebx, eax
0x1400146ae  test    eax, eax
0x1400146b0  jz      short loc_140014704
0x1400146b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400146b9  lea     r14, WPP_GLOBAL_Control
0x1400146c0  cmp     rcx, r14
0x1400146c3  jz      loc_1400148BE
0x1400146c9  mov     edx, [rcx+2Ch]
0x1400146cc  test    sil, dl
0x1400146cf  jz      loc_140014891
0x1400146d5  cmp     byte ptr [rcx+29h], 1
0x1400146d9  jb      loc_140014891
0x1400146df  mov     edx, 39h ; '9'
0x1400146e4  mov     dword ptr [rsp+100h+var_E0], eax
0x1400146e8  mov     rcx, [rcx+18h]
0x1400146ec  lea     r9, [rdi+16Ch]
0x1400146f3  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400146fa  call    WPP_SF__guid_D
0x1400146ff  jmp     loc_140014891
0x140014704  movzx   edx, word ptr [rsp+100h+var_D0]; cbSecret
0x140014709  lea     rcx, [rbp+4Fh+var_58]; pbSecret
0x14001470d  mov     [rsp+100h+var_D8], r15; __int64
0x140014712  mov     r9d, r12d; cbInput
0x140014715  mov     r8, r13; pbInput
0x140014718  mov     [rsp+100h+var_E0], r14; PUCHAR
0x14001471d  call    GenerateHmacSha1Hash
0x140014722  mov     ebx, eax
0x140014724  test    eax, eax
0x140014726  jz      loc_14001488A
0x14001472c  mov     rcx, cs:WPP_GLOBAL_Control
0x140014733  lea     r14, WPP_GLOBAL_Control
0x14001473a  cmp     rcx, r14
0x14001473d  jz      loc_1400148BE
0x140014743  mov     eax, [rcx+2Ch]
0x140014746  test    sil, al
0x140014749  jz      loc_140014891
0x14001474f  cmp     byte ptr [rcx+29h], 1
0x140014753  jb      loc_140014891
0x140014759  mov     edx, 3Ah ; ':'
0x14001475e  mov     dword ptr [rsp+100h+var_E0], ebx
0x140014762  jmp     short loc_1400146E8
0x140014764  xor     ebx, ebx
0x140014766  cmp     al, 2
0x140014768  jnz     loc_14001488A
0x14001476e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014775  lea     rax, WPP_GLOBAL_Control
0x14001477c  mov     sil, 4
0x14001477f  cmp     rcx, rax
0x140014782  jz      short loc_1400147AC
0x140014784  mov     eax, [rcx+2Ch]
0x140014787  test    sil, al
0x14001478a  jz      short loc_1400147AC
0x14001478c  cmp     byte ptr [rcx+29h], 2
0x140014790  jb      short loc_1400147AC
0x140014792  mov     rcx, [rcx+18h]
0x140014796  lea     r9, [rdi+16Ch]
0x14001479d  lea     edx, [rbx+3Bh]
0x1400147a0  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400147a7  call    WPP_SF__guid_
0x1400147ac  movups  xmm0, xmmword ptr [rbp+4Fh+var_B8]
0x1400147b0  mov     ecx, 20h ; ' '
0x1400147b5  lea     rax, [rsp+100h+var_D0]
0x1400147ba  movups  xmm1, xmmword ptr [rbp+4Fh+var_B8+0Dh]
0x1400147be  mov     [rsp+100h+var_D8], rax; __int64
0x1400147c3  lea     r8, [rbp+4Fh+pbInput]; pbInput
0x1400147c7  lea     rax, [rbp+4Fh+var_58]
0x1400147cb  mov     word ptr [rsp+100h+var_D0], cx
0x1400147d0  mov     word ptr [rbp+4Fh+var_88+0Dh], cx
0x1400147d4  mov     r9d, ecx; cbInput
0x1400147d7  mov     edx, ecx; cbSecret
0x1400147d9  mov     [rsp+100h+var_E0], rax; PUCHAR
0x1400147de  movups  xmmword ptr [rbp+4Fh+pbInput], xmm0
0x1400147e2  lea     rcx, [rbp+4Fh+pbSecret]; pbSecret
0x1400147e6  mov     byte ptr [rbp+4Fh+var_88+0Fh], 1
0x1400147ea  movups  xmmword ptr [rbp+4Fh+pbInput+0Dh], xmm1
0x1400147ee  call    GenerateHmacSha256Hash
0x1400147f3  mov     ebx, eax
0x1400147f5  test    eax, eax
0x1400147f7  jz      short loc_140014825
0x1400147f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140014800  lea     rax, WPP_GLOBAL_Control
0x140014807  cmp     rcx, rax
0x14001480a  jz      loc_1400148BE
0x140014810  mov     eax, [rcx+2Ch]
0x140014813  test    sil, al
0x140014816  jz      short loc_14001488A
0x140014818  cmp     byte ptr [rcx+29h], 1
0x14001481c  jb      short loc_14001488A
0x14001481e  mov     edx, 3Ch ; '<'
0x140014823  jmp     short loc_14001486F
0x140014825  movzx   edx, word ptr [rsp+100h+var_D0]; cbSecret
0x14001482a  lea     rcx, [rbp+4Fh+var_58]; pbSecret
0x14001482e  mov     [rsp+100h+var_D8], r15; __int64
0x140014833  mov     r9d, r12d; cbInput
0x140014836  mov     r8, r13; pbInput
0x140014839  mov     [rsp+100h+var_E0], r14; PUCHAR
0x14001483e  call    GenerateHmacSha256Hash
0x140014843  mov     ebx, eax
0x140014845  test    eax, eax
0x140014847  jz      short loc_14001488A
0x140014849  mov     rcx, cs:WPP_GLOBAL_Control
0x140014850  lea     rax, WPP_GLOBAL_Control
0x140014857  cmp     rcx, rax
0x14001485a  jz      short loc_1400148BE
0x14001485c  mov     eax, [rcx+2Ch]
0x14001485f  test    sil, al
0x140014862  jz      short loc_14001488A
0x140014864  cmp     byte ptr [rcx+29h], 1
0x140014868  jb      short loc_14001488A
0x14001486a  mov     edx, 3Dh ; '='
0x14001486f  mov     rcx, [rcx+18h]
0x140014873  lea     r9, [rdi+16Ch]
0x14001487a  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140014881  mov     dword ptr [rsp+100h+var_E0], ebx
0x140014885  call    WPP_SF__guid_D
0x14001488a  lea     r14, WPP_GLOBAL_Control
0x140014891  mov     rcx, cs:WPP_GLOBAL_Control
0x140014898  cmp     rcx, r14
0x14001489b  jz      short loc_1400148BE
0x14001489d  mov     eax, [rcx+2Ch]
0x1400148a0  and     eax, 84h
0x1400148a5  cmp     al, 84h
0x1400148a7  jnz     short loc_1400148BE
0x1400148a9  mov     rcx, [rcx+18h]
0x1400148ad  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400148b4  mov     edx, 3Eh ; '>'
0x1400148b9  call    WPP_SF_
0x1400148be  mov     eax, ebx
0x1400148c0  mov     rcx, [rbp+4Fh+var_38]
0x1400148c4  xor     rcx, rsp; StackCookie
0x1400148c7  call    __security_check_cookie
0x1400148cc  mov     rbx, [rsp+100h+arg_10]
0x1400148d4  add     rsp, 0D0h
0x1400148db  pop     r15
0x1400148dd  pop     r14
0x1400148df  pop     r13
0x1400148e1  pop     r12
0x1400148e3  pop     rdi
0x1400148e4  pop     rsi
0x1400148e5  pop     rbp
0x1400148e6  retn
```
