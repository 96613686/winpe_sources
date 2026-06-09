# CStrmEncoder::EncodeOneFrame(int,uchar *,tAvcVideoArea *,IRdpBoundsAccumulator *,__int64,__int64,int,uchar * *,int,int *,int,uchar * *)

- ea: `0x1800e8b9c`
- end: `0x1800e9139`
- name: `?EncodeOneFrame@CStrmEncoder@@QEAAJHPEAEPEAUtAvcVideoArea@@PEAVIRdpBoundsAccumulator@@_J3HPEAPEAEHPEAHH4@Z`
- size: `1437`
- prototype: `__int64 __usercall@<rax>(CStrmEncoder *__hidden this@<rcx>, int@<edx>, unsigned __int8 *@<r8>, struct tAvcVideoArea *@<r9>, struct IRdpBoundsAccumulator *, __int64, __int64, int, unsigned __int8 **, int, int *, int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800e7e1c`

## callees

- `0x1800071c0`
- `0x18002e600`
- `0x1800598d0`
- `0x1800e8440`
- `0x1800e8524`
- `0x1800e8970`
- `0x1800e8b9c`
- `0x1800eaab8`
- `0x1800eab44`
- `0x1800eacb4`
- `0x1800f12fc`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e904b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e904b`
- `RDPBASE!RgnlibBA_CreateInstance` at `0x1800e8d74`
- `RDPBASE!RgnlibBA_CreateInstance` at `0x1800e8d74`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8c07`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8dab`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8e08`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8fbc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e9020`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e908d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e90e2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8c07`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8dab`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8e08`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e8fbc`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e9020`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e908d`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800e90e2`

## string_xrefs

- `0x1800e8db6`: `RgnlibBA_CreateInstance failed`

## pseudocode

```c
__int64 __fastcall CStrmEncoder::EncodeOneFrame(
        CStrmEncoder *this,
        __int64 a2,
        unsigned __int8 *a3,
        struct tAvcVideoArea *a4,
        struct IRdpBoundsAccumulator *a5,
        __int64 a6,
        __int64 a7,
        int a8,
        unsigned __int8 **a9,
        int a10,
        int *a11,
        int a12,
        unsigned __int8 **a13)
{
  int v13; // r10d
  __int64 v15; // r14
  int v16; // eax
  int Bitstream; // esi
  unsigned __int8 **v18; // r15
  __int64 v19; // rdx
  __int64 v20; // r11
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r10
  __int64 v24; // rcx
  CStrmEncoder *v25; // rcx
  int ActivityIdPrefix; // eax
  int v27; // edx
  const char *v28; // rcx
  unsigned __int8 *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rsi
  struct IRdpBoundsAccumulator *v35; // rdi
  __int64 v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  int v39; // r9d
  int v41; // [rsp+20h] [rbp-10h]
  unsigned __int8 **v42; // [rsp+28h] [rbp-8h]
  struct IRdpBoundsAccumulator *v43; // [rsp+60h] [rbp+30h] BYREF
  struct tAvcVideoArea *v44; // [rsp+78h] [rbp+48h] BYREF

  v44 = a4;
  v13 = a2;
  v43 = 0;
  if ( *((_DWORD *)this + 171) )
    *((_DWORD *)this + 171) = 0;
  v15 = *((_QWORD *)this + 14) + 304LL * *((int *)this + 2);
  if ( v15 )
  {
    v18 = a13;
    if ( *((_DWORD *)this + 32) == 4 )
    {
      v19 = *((_QWORD *)this + 91);
      v20 = *((_QWORD *)this + 93);
      v21 = *((_QWORD *)this + 92);
      *(_QWORD *)(v15 + 128) = a3;
      v22 = *(int *)(v15 + 72);
      *(_DWORD *)(v15 + 120) = v13;
      a12 = 0;
      LODWORD(v44) = 0;
      *(_QWORD *)(v15 + 136) = v19;
      *(_QWORD *)(v15 + 144) = v19 + v22;
      v23 = *(int *)(v15 + 76);
      *(_QWORD *)(v15 + 152) = v23 + v19 + v22;
      if ( *(_DWORD *)(v15 + 116) )
      {
        *(_QWORD *)(v15 + 160) = v21;
        *(_QWORD *)(v15 + 168) = v21 + v22;
        *(_QWORD *)(v15 + 176) = v23 + v21 + v22;
        *(_QWORD *)(v15 + 208) = v20;
      }
      v24 = 0;
      if ( *(_DWORD *)(v15 + 100) )
      {
        *(_QWORD *)(v15 + 184) = *(_QWORD *)(v15 + 160);
        do
        {
          *(_QWORD *)(v15 + 8 * v24 + 192) = *(_QWORD *)(v15 + 8 * v24 + 168);
          ++v24;
        }
        while ( v24 != 2 );
      }
      else
      {
        *(_QWORD *)(v15 + 184) = v19;
        do
        {
          *(_QWORD *)(v15 + 8 * v24 + 192) = *(_QWORD *)(v15 + 8 * v24 + 144);
          ++v24;
        }
        while ( v24 != 2 );
      }
      CEncoder::ConvertRgbaToYuv(
        *((CEncoder **)this + 13),
        (struct CPictureSrc *)(v15 + 48),
        v22,
        *v18,
        &a12,
        (unsigned int *)&v44);
      if ( a12 )
      {
        Bitstream = 0;
        *a9 = 0;
        *a11 = 0;
        goto LABEL_74;
      }
      if ( !*(_DWORD *)(v15 + 100) )
      {
        Bitstream = RgnlibBA_CreateInstance(&v43);
        if ( Bitstream < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_74;
          }
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v27 = 61;
          v28 = "RgnlibBA_CreateInstance failed";
          goto LABEL_73;
        }
        Bitstream = CStrmEncoder::BuildBAFromDirtyCellMap(v25, (struct CPictureSrc *)(v15 + 48), v43, (unsigned int)v44);
        if ( Bitstream < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_74;
          }
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v27 = 62;
          v28 = "BuildBAFromDirtyCellMap failed";
          goto LABEL_73;
        }
LABEL_38:
        v34 = *((_QWORD *)this + 13);
        v35 = v43;
        v36 = *(_QWORD *)(v34 + 1904);
        if ( v36 )
          TCntPtr<IRdpBoundsAccumulator>::operator=(v36 + 8280, v43);
        v37 = *(_QWORD *)(v34 + 1928);
        if ( v37 && v35 )
          *(_QWORD *)(v37 + 64) = v35;
        *(_DWORD *)v15 = *((_DWORD *)this + 11);
        *(_QWORD *)(v15 + 16) = a6;
        *(_QWORD *)(v15 + 24) = 0;
        *(_QWORD *)(v15 + 216) = 0;
        *(_DWORD *)(v15 + 8) = 0;
        *(_DWORD *)(v15 + 252) = 0;
        *(_DWORD *)(v15 + 244) = 0;
        *(_DWORD *)(v15 + 248) = *((_DWORD *)this + 168);
        *(_DWORD *)(v15 + 264) = *((_DWORD *)this + 130);
        if ( !*((_DWORD *)this + 22) || *((_DWORD *)this + 138) == 1 && (*((_BYTE *)this + 56) & 3) != 0 )
        {
          *(_DWORD *)(v15 + 240) = 0;
        }
        else
        {
          *(_DWORD *)(v15 + 240) = 1;
          *((_DWORD *)this + 22) = 0;
        }
        if ( ++*((_DWORD *)this + 2) >= *((_DWORD *)this + 5) )
          *((_DWORD *)this + 2) = 0;
        ++*((_DWORD *)this + 4);
        ++*((_DWORD *)this + 11);
        v38 = CStrmEncoder::QueueFrames(this);
        Bitstream = v38;
        if ( v38 >= 0 )
        {
          if ( *((_DWORD *)this + 192) )
            QueryPerformanceCounter((LARGE_INTEGER *)(*((_QWORD *)this + 97) + 80LL));
          Bitstream = CStrmEncoder::EncodeFrame(this, a8);
          if ( Bitstream >= 0 )
          {
            Bitstream = CStrmEncoder::RetrieveBitstream(this, a9, a10, a11, v41, v18);
            if ( Bitstream >= 0
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_74;
            }
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
            v27 = 66;
            v28 = "FAILED RetrieveBitstream";
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_74;
            }
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
            v27 = 65;
            v28 = "FAILED EncodeFrame";
          }
        }
        else if ( v38 == -2147024774 )
        {
          Bitstream = CStrmEncoder::ResetBitstream(this, a9, a11, v39, v18);
          if ( Bitstream >= 0
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_74;
          }
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v27 = 64;
          v28 = "FAILED ResetBitstream";
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_74;
          }
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
          v27 = 63;
          v28 = "FAILED QueueFrames";
        }
LABEL_73:
        LODWORD(v42) = Bitstream;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v27,
          (unsigned int)WPP_de0e01d431563605e25f5df122a30d40_Traceguids,
          ActivityIdPrefix,
          (__int64)v28,
          v42);
        goto LABEL_74;
      }
    }
    else
    {
      v29 = &a3[*(int *)(v15 + 72)];
      if ( *(_DWORD *)(v15 + 100) )
      {
        v32 = *(int *)(v15 + 76);
        *(_QWORD *)(v15 + 168) = v29;
        *(_QWORD *)(v15 + 176) = &v29[v32];
        v33 = 0;
        *(_QWORD *)(v15 + 160) = a3;
        *(_QWORD *)(v15 + 184) = a3;
        do
        {
          *(_QWORD *)(v15 + 8 * v33 + 192) = *(_QWORD *)(v15 + 8 * v33 + 168);
          ++v33;
        }
        while ( v33 != 2 );
      }
      else
      {
        *(_QWORD *)(v15 + 144) = v29;
        v30 = *(int *)(v15 + 76);
        *(_QWORD *)(v15 + 136) = a3;
        *(_QWORD *)(v15 + 152) = &v29[v30];
        v31 = 0;
        *(_QWORD *)(v15 + 184) = a3;
        do
        {
          *(_QWORD *)(v15 + 8 * v31 + 192) = *(_QWORD *)(v15 + 8 * v31 + 144);
          ++v31;
        }
        while ( v31 != 2 );
      }
    }
    TCntPtr<IRdpBoundsAccumulator>::operator=(&v43, a5);
    goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      60,
      (unsigned int)WPP_de0e01d431563605e25f5df122a30d40_Traceguids,
      v16,
      (__int64)"pNewFrame");
  }
  Bitstream = -2147467261;
LABEL_74:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v43, a2, a3);
  return (unsigned int)Bitstream;
}

```

## disassembly

```asm
0x1800e8b9c  mov     [rsp-28h+arg_8], rbx
0x1800e8ba1  mov     [rsp-28h+arg_10], rsi
0x1800e8ba6  mov     [rsp-28h+arg_18], r9
0x1800e8bab  push    rbp
0x1800e8bac  push    rdi
0x1800e8bad  push    r12
0x1800e8baf  push    r14
0x1800e8bb1  push    r15
0x1800e8bb3  mov     rbp, rsp
0x1800e8bb6  sub     rsp, 30h
0x1800e8bba  xor     r12d, r12d
0x1800e8bbd  mov     r10d, edx
0x1800e8bc0  mov     rbx, rcx
0x1800e8bc3  mov     [rbp+arg_0], r12
0x1800e8bc7  cmp     [rcx+2ACh], r12d
0x1800e8bce  jz      short loc_1800E8BD7
0x1800e8bd0  mov     [rcx+2ACh], r12d
0x1800e8bd7  movsxd  rax, dword ptr [rcx+8]
0x1800e8bdb  imul    r14, rax, 130h
0x1800e8be2  add     r14, [rcx+70h]
0x1800e8be6  jnz     short loc_1800E8C41
0x1800e8be8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8bef  lea     rax, WPP_GLOBAL_Control
0x1800e8bf6  cmp     rcx, rax
0x1800e8bf9  jz      short loc_1800E8C37
0x1800e8bfb  test    byte ptr [rcx+1Ch], 8
0x1800e8bff  jz      short loc_1800E8C37
0x1800e8c01  cmp     byte ptr [rcx+19h], 2
0x1800e8c05  jb      short loc_1800E8C37
0x1800e8c07  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e8c0d  lea     rcx, aPnewframe; "pNewFrame"
0x1800e8c14  mov     r9d, eax
0x1800e8c17  mov     [rsp+30h+var_10], rcx
0x1800e8c1c  lea     edx, [r14+3Ch]
0x1800e8c20  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8c27  lea     r8, WPP_de0e01d431563605e25f5df122a30d40_Traceguids
0x1800e8c2e  mov     rcx, [rcx+10h]
0x1800e8c32  call    WPP_SF_Ds
0x1800e8c37  mov     esi, 80004003h
0x1800e8c3c  jmp     loc_1800E9117
0x1800e8c41  cmp     dword ptr [rcx+80h], 4
0x1800e8c48  mov     r15, [rbp+arg_60]
0x1800e8c4f  jnz     loc_1800E8E1F
0x1800e8c55  mov     rdx, [rcx+2D8h]
0x1800e8c5c  mov     r11, [rcx+2E8h]
0x1800e8c63  mov     r9, [rcx+2E0h]
0x1800e8c6a  mov     [r14+80h], r8
0x1800e8c71  movsxd  r8, dword ptr [r14+48h]; int
0x1800e8c75  mov     [r14+78h], r10d
0x1800e8c79  mov     [rbp+arg_58], r12d
0x1800e8c80  mov     dword ptr [rbp+arg_18], r12d
0x1800e8c84  lea     rax, [rdx+r8]
0x1800e8c88  mov     [r14+88h], rdx
0x1800e8c8f  mov     [r14+90h], rax
0x1800e8c96  movsxd  r10, dword ptr [r14+4Ch]
0x1800e8c9a  add     rax, r10
0x1800e8c9d  mov     [r14+98h], rax
0x1800e8ca4  cmp     [r14+74h], r12d
0x1800e8ca8  jz      short loc_1800E8CCD
0x1800e8caa  lea     rax, [r9+r8]
0x1800e8cae  mov     [r14+0A0h], r9
0x1800e8cb5  mov     [r14+0A8h], rax
0x1800e8cbc  add     rax, r10
0x1800e8cbf  mov     [r14+0B0h], rax
0x1800e8cc6  mov     [r14+0D0h], r11
0x1800e8ccd  mov     rcx, r12
0x1800e8cd0  cmp     [r14+64h], r12d
0x1800e8cd4  jnz     short loc_1800E8CF8
0x1800e8cd6  mov     [r14+0B8h], rdx
0x1800e8cdd  mov     rax, [r14+rcx*8+90h]
0x1800e8ce5  mov     [r14+rcx*8+0C0h], rax
0x1800e8ced  inc     rcx
0x1800e8cf0  cmp     rcx, 2
0x1800e8cf4  jnz     short loc_1800E8CDD
0x1800e8cf6  jmp     short loc_1800E8D1F
0x1800e8cf8  mov     rax, [r14+0A0h]
0x1800e8cff  mov     [r14+0B8h], rax
0x1800e8d06  mov     rax, [r14+rcx*8+0A8h]
0x1800e8d0e  mov     [r14+rcx*8+0C0h], rax
0x1800e8d16  inc     rcx
0x1800e8d19  cmp     rcx, 2
0x1800e8d1d  jnz     short loc_1800E8D06
0x1800e8d1f  mov     r9, [r15]; unsigned __int8 *
0x1800e8d22  lea     rax, [rbp+arg_18]
0x1800e8d26  mov     rcx, [rbx+68h]; this
0x1800e8d2a  lea     rdx, [r14+30h]; struct CPictureSrc *
0x1800e8d2e  mov     [rsp+30h+var_8], rax; unsigned int *
0x1800e8d33  lea     rax, [rbp+arg_58]
0x1800e8d3a  mov     [rsp+30h+var_10], rax; int *
0x1800e8d3f  call    ?ConvertRgbaToYuv@CEncoder@@QEAAXPEAVCPictureSrc@@HPEAEPEAHPEAI@Z; CEncoder::ConvertRgbaToYuv(CPictureSrc *,int,uchar *,int *,uint *)
0x1800e8d44  cmp     [rbp+arg_58], r12d
0x1800e8d4b  jz      short loc_1800E8D66
0x1800e8d4d  mov     rax, [rbp+arg_40]
0x1800e8d51  mov     esi, r12d
0x1800e8d54  mov     [rax], r12
0x1800e8d57  mov     rax, [rbp+arg_50]
0x1800e8d5e  mov     [rax], r12d
0x1800e8d61  jmp     loc_1800E9117
0x1800e8d66  lea     rcx, [rbp+arg_0]
0x1800e8d6a  cmp     [r14+64h], r12d
0x1800e8d6e  jnz     loc_1800E8EB0
0x1800e8d74  call    cs:__imp_RgnlibBA_CreateInstance
0x1800e8d7a  mov     esi, eax
0x1800e8d7c  test    eax, eax
0x1800e8d7e  jns     short loc_1800E8DC2
0x1800e8d80  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8d87  lea     rax, WPP_GLOBAL_Control
0x1800e8d8e  cmp     rcx, rax
0x1800e8d91  jz      loc_1800E9117
0x1800e8d97  test    byte ptr [rcx+1Ch], 8
0x1800e8d9b  jz      loc_1800E9117
0x1800e8da1  cmp     byte ptr [rcx+19h], 2
0x1800e8da5  jb      loc_1800E9117
0x1800e8dab  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e8db1  mov     edx, 3Dh ; '='
0x1800e8db6  lea     rcx, aRgnlibbaCreate; "RgnlibBA_CreateInstance failed"
0x1800e8dbd  jmp     loc_1800E90F4
0x1800e8dc2  mov     r9d, dword ptr [rbp+arg_18]; unsigned int
0x1800e8dc6  lea     rdx, [r14+30h]; struct CPictureSrc *
0x1800e8dca  mov     r8, [rbp+arg_0]; struct IRdpBoundsAccumulator *
0x1800e8dce  call    ?BuildBAFromDirtyCellMap@CStrmEncoder@@AEAAJPEAVCPictureSrc@@PEAVIRdpBoundsAccumulator@@I@Z; CStrmEncoder::BuildBAFromDirtyCellMap(CPictureSrc *,IRdpBoundsAccumulator *,uint)
0x1800e8dd3  mov     esi, eax
0x1800e8dd5  test    eax, eax
0x1800e8dd7  jns     loc_1800E8EB9
0x1800e8ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8de4  lea     rax, WPP_GLOBAL_Control
0x1800e8deb  cmp     rcx, rax
0x1800e8dee  jz      loc_1800E9117
0x1800e8df4  test    byte ptr [rcx+1Ch], 8
0x1800e8df8  jz      loc_1800E9117
0x1800e8dfe  cmp     byte ptr [rcx+19h], 2
0x1800e8e02  jb      loc_1800E9117
0x1800e8e08  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e8e0e  mov     edx, 3Eh ; '>'
0x1800e8e13  lea     rcx, aBuildbafromdir; "BuildBAFromDirtyCellMap failed"
0x1800e8e1a  jmp     loc_1800E90F4
0x1800e8e1f  movsxd  rcx, dword ptr [r14+48h]
0x1800e8e23  add     rcx, r8
0x1800e8e26  cmp     [r14+64h], r12d
0x1800e8e2a  jnz     short loc_1800E8E6D
0x1800e8e2c  mov     [r14+90h], rcx
0x1800e8e33  movsxd  rax, dword ptr [r14+4Ch]
0x1800e8e37  add     rax, rcx
0x1800e8e3a  mov     [r14+88h], r8
0x1800e8e41  mov     [r14+98h], rax
0x1800e8e48  mov     rcx, r12
0x1800e8e4b  mov     [r14+0B8h], r8
0x1800e8e52  mov     rax, [r14+rcx*8+90h]
0x1800e8e5a  mov     [r14+rcx*8+0C0h], rax
0x1800e8e62  inc     rcx
0x1800e8e65  cmp     rcx, 2
0x1800e8e69  jnz     short loc_1800E8E52
0x1800e8e6b  jmp     short loc_1800E8EAC
0x1800e8e6d  movsxd  rax, dword ptr [r14+4Ch]
0x1800e8e71  add     rax, rcx
0x1800e8e74  mov     [r14+0A8h], rcx
0x1800e8e7b  mov     [r14+0B0h], rax
0x1800e8e82  mov     rcx, r12
0x1800e8e85  mov     [r14+0A0h], r8
0x1800e8e8c  mov     [r14+0B8h], r8
0x1800e8e93  mov     rax, [r14+rcx*8+0A8h]
0x1800e8e9b  mov     [r14+rcx*8+0C0h], rax
0x1800e8ea3  inc     rcx
0x1800e8ea6  cmp     rcx, 2
0x1800e8eaa  jnz     short loc_1800E8E93
0x1800e8eac  lea     rcx, [rbp+arg_0]
0x1800e8eb0  mov     rdx, [rbp+arg_20]
0x1800e8eb4  call    ??4?$TCntPtr@VIRdpBoundsAccumulator@@@@QEAAPEAVIRdpBoundsAccumulator@@PEAV1@@Z; TCntPtr<IRdpBoundsAccumulator>::operator=(IRdpBoundsAccumulator *)
0x1800e8eb9  mov     rsi, [rbx+68h]
0x1800e8ebd  mov     rdi, [rbp+arg_0]
0x1800e8ec1  mov     rcx, [rsi+770h]
0x1800e8ec8  test    rcx, rcx
0x1800e8ecb  jz      short loc_1800E8EDC
0x1800e8ecd  add     rcx, 2058h
0x1800e8ed4  mov     rdx, rdi
0x1800e8ed7  call    ??4?$TCntPtr@VIRdpBoundsAccumulator@@@@QEAAPEAVIRdpBoundsAccumulator@@PEAV1@@Z; TCntPtr<IRdpBoundsAccumulator>::operator=(IRdpBoundsAccumulator *)
0x1800e8edc  mov     rax, [rsi+788h]
0x1800e8ee3  test    rax, rax
0x1800e8ee6  jz      short loc_1800E8EF1
0x1800e8ee8  test    rdi, rdi
0x1800e8eeb  jz      short loc_1800E8EF1
0x1800e8eed  mov     [rax+40h], rdi
0x1800e8ef1  mov     eax, [rbx+2Ch]
0x1800e8ef4  mov     [r14], eax
0x1800e8ef7  mov     rax, [rbp+arg_28]
0x1800e8efb  mov     [r14+10h], rax
0x1800e8eff  mov     [r14+18h], r12
0x1800e8f03  mov     [r14+0D8h], r12
0x1800e8f0a  mov     [r14+8], r12d
0x1800e8f0e  mov     [r14+0FCh], r12d
0x1800e8f15  mov     [r14+0F4h], r12d
0x1800e8f1c  mov     eax, [rbx+2A0h]
0x1800e8f22  mov     [r14+0F8h], eax
0x1800e8f29  mov     eax, [rbx+208h]
0x1800e8f2f  mov     [r14+108h], eax
0x1800e8f36  cmp     [rbx+58h], r12d
0x1800e8f3a  jz      short loc_1800E8F5C
0x1800e8f3c  cmp     dword ptr [rbx+228h], 1
0x1800e8f43  jnz     short loc_1800E8F4B
0x1800e8f45  test    byte ptr [rbx+38h], 3
0x1800e8f49  jnz     short loc_1800E8F5C
0x1800e8f4b  mov     dword ptr [r14+0F0h], 1
0x1800e8f56  mov     [rbx+58h], r12d
0x1800e8f5a  jmp     short loc_1800E8F63
0x1800e8f5c  mov     [r14+0F0h], r12d
0x1800e8f63  inc     dword ptr [rbx+8]
0x1800e8f66  mov     eax, [rbx+8]
0x1800e8f69  cmp     eax, [rbx+14h]
0x1800e8f6c  jl      short loc_1800E8F72
0x1800e8f6e  mov     [rbx+8], r12d
0x1800e8f72  inc     dword ptr [rbx+10h]
0x1800e8f75  mov     rcx, rbx; this
0x1800e8f78  inc     dword ptr [rbx+2Ch]
0x1800e8f7b  call    ?QueueFrames@CStrmEncoder@@AEAAJXZ; CStrmEncoder::QueueFrames(void)
0x1800e8f80  mov     esi, eax
0x1800e8f82  test    eax, eax
0x1800e8f84  jns     loc_1800E9037
0x1800e8f8a  cmp     eax, 8007007Ah
0x1800e8f8f  jz      short loc_1800E8FD3
0x1800e8f91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8f98  lea     rax, WPP_GLOBAL_Control
0x1800e8f9f  cmp     rcx, rax
0x1800e8fa2  jz      loc_1800E9117
0x1800e8fa8  test    byte ptr [rcx+1Ch], 8
0x1800e8fac  jz      loc_1800E9117
0x1800e8fb2  cmp     byte ptr [rcx+19h], 2
0x1800e8fb6  jb      loc_1800E9117
0x1800e8fbc  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e8fc2  mov     edx, 3Fh ; '?'
0x1800e8fc7  lea     rcx, aFailedQueuefra; "FAILED QueueFrames"
0x1800e8fce  jmp     loc_1800E90F4
0x1800e8fd3  mov     r8, [rbp+arg_50]; int *
0x1800e8fda  mov     rcx, rbx; this
0x1800e8fdd  mov     rdx, [rbp+arg_40]; unsigned __int8 **
0x1800e8fe1  mov     [rsp+30h+var_10], r15; unsigned __int8 **
0x1800e8fe6  call    ?ResetBitstream@CStrmEncoder@@AEAAJPEAPEAEPEAHH0@Z; CStrmEncoder::ResetBitstream(uchar * *,int *,int,uchar * *)
0x1800e8feb  mov     esi, eax
0x1800e8fed  test    eax, eax
0x1800e8fef  jns     loc_1800E9117
0x1800e8ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8ffc  lea     rax, WPP_GLOBAL_Control
0x1800e9003  cmp     rcx, rax
0x1800e9006  jz      loc_1800E9117
0x1800e900c  test    byte ptr [rcx+1Ch], 8
0x1800e9010  jz      loc_1800E9117
0x1800e9016  cmp     byte ptr [rcx+19h], 2
0x1800e901a  jb      loc_1800E9117
0x1800e9020  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e9026  mov     edx, 40h ; '@'
0x1800e902b  lea     rcx, aFailedResetbit; "FAILED ResetBitstream"
0x1800e9032  jmp     loc_1800E90F4
0x1800e9037  cmp     [rbx+300h], r12d
0x1800e903e  jz      short loc_1800E9051
0x1800e9040  mov     rcx, [rbx+308h]
0x1800e9047  add     rcx, 50h ; 'P'; lpPerformanceCount
0x1800e904b  call    cs:__imp_QueryPerformanceCounter
0x1800e9051  mov     edx, [rbp+arg_38]; int
0x1800e9054  mov     rcx, rbx; this
0x1800e9057  call    ?EncodeFrame@CStrmEncoder@@AEAAJH@Z; CStrmEncoder::EncodeFrame(int)
0x1800e905c  mov     esi, eax
0x1800e905e  test    eax, eax
0x1800e9060  jns     short loc_1800E90A1
0x1800e9062  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9069  lea     rax, WPP_GLOBAL_Control
0x1800e9070  cmp     rcx, rax
0x1800e9073  jz      loc_1800E9117
0x1800e9079  test    byte ptr [rcx+1Ch], 8
0x1800e907d  jz      loc_1800E9117
0x1800e9083  cmp     byte ptr [rcx+19h], 2
0x1800e9087  jb      loc_1800E9117
0x1800e908d  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e9093  mov     edx, 41h ; 'A'
0x1800e9098  lea     rcx, aFailedEncodefr; "FAILED EncodeFrame"
0x1800e909f  jmp     short loc_1800E90F4
0x1800e90a1  mov     r9, [rbp+arg_50]; int *
0x1800e90a8  mov     rcx, rbx; this
0x1800e90ab  mov     r8d, [rbp+arg_48]; int
0x1800e90af  mov     rdx, [rbp+arg_40]; unsigned __int8 **
0x1800e90b3  mov     [rsp+30h+var_8], r15; unsigned __int8 **
0x1800e90b8  call    ?RetrieveBitstream@CStrmEncoder@@AEAAJPEAPEAEHPEAHH0@Z; CStrmEncoder::RetrieveBitstream(uchar * *,int,int *,int,uchar * *)
0x1800e90bd  mov     esi, eax
0x1800e90bf  test    eax, eax
0x1800e90c1  jns     short loc_1800E9117
0x1800e90c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e90ca  lea     rax, WPP_GLOBAL_Control
0x1800e90d1  cmp     rcx, rax
0x1800e90d4  jz      short loc_1800E9117
0x1800e90d6  test    byte ptr [rcx+1Ch], 8
0x1800e90da  jz      short loc_1800E9117
0x1800e90dc  cmp     byte ptr [rcx+19h], 2
0x1800e90e0  jb      short loc_1800E9117
0x1800e90e2  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800e90e8  mov     edx, 42h ; 'B'
0x1800e90ed  lea     rcx, aFailedRetrieve; "FAILED RetrieveBitstream"
0x1800e90f4  mov     dword ptr [rsp+30h+var_8], esi
0x1800e90f8  lea     r8, WPP_de0e01d431563605e25f5df122a30d40_Traceguids
0x1800e90ff  mov     [rsp+30h+var_10], rcx
0x1800e9104  mov     r9d, eax
0x1800e9107  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e910e  mov     rcx, [rcx+10h]
  ... truncated ...
```
