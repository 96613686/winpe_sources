# bLoadTTF(unsigned __int64,void *,ulong,_TABLE_POINTERS *,ulong,ushort,unsigned __int64 *,_TTF_CACHE *,ulong,NamedInstanceBuilder const *,uint)

- ea: `0x140007f98`
- end: `0x14000864e`
- name: `?bLoadTTF@@YAH_KPEAXKPEAU_TABLE_POINTERS@@KGPEA_KPEAU_TTF_CACHE@@KPEBVNamedInstanceBuilder@@I@Z`
- size: `1718`
- prototype: `__int64 __usercall@<rax>(unsigned __int64@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, struct _TABLE_POINTERS *@<r9>, unsigned int, unsigned __int16, unsigned __int64 *, struct _TTF_CACHE *, unsigned int, const struct NamedInstanceBuilder *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x140007dcc`

## callees

- `0x140002a68`
- `0x140007f98`
- `0x1400086b4`
- `0x1400089e8`
- `0x14000978c`
- `0x14000a018`
- `0x14000a538`
- `0x14000b7fc`
- `0x14004736c`
- `0x14005af90`
- `0x1400612d0`
- `0x140075de0`
- `0x14007680c`
- `0x140076eea`

## import_xrefs

- `KERNEL32!GetACP` at `0x1400085b2`
- `KERNEL32!GetACP` at `0x1400085b2`
- `KERNEL32!GetOEMCP` at `0x1400085ba`
- `KERNEL32!GetOEMCP` at `0x1400085ba`
- `KERNEL32!GlobalFree` at `0x1400084bf`
- `KERNEL32!GlobalFree` at `0x14000850e`
- `KERNEL32!GlobalFree` at `0x140008517`
- `KERNEL32!GlobalFree` at `0x1400085e4`
- `KERNEL32!GlobalFree` at `0x140008609`
- `KERNEL32!GlobalFree` at `0x140008617`
- `KERNEL32!GlobalFree` at `0x140008625`
- `KERNEL32!GlobalFree` at `0x140008633`
- `KERNEL32!GlobalFree` at `0x140008643`
- `KERNEL32!GlobalFree` at `0x1400084bf`
- `KERNEL32!GlobalFree` at `0x14000850e`
- `KERNEL32!GlobalFree` at `0x140008517`
- `KERNEL32!GlobalFree` at `0x1400085e4`
- `KERNEL32!GlobalFree` at `0x140008609`
- `KERNEL32!GlobalFree` at `0x140008617`
- `KERNEL32!GlobalFree` at `0x140008625`
- `KERNEL32!GlobalFree` at `0x140008633`
- `KERNEL32!GlobalFree` at `0x140008643`
- `KERNEL32!GlobalAlloc` at `0x140008103`
- `KERNEL32!GlobalAlloc` at `0x140008340`
- `KERNEL32!GlobalAlloc` at `0x140008548`
- `KERNEL32!GlobalAlloc` at `0x140008558`
- `KERNEL32!GlobalAlloc` at `0x140008103`
- `KERNEL32!GlobalAlloc` at `0x140008340`
- `KERNEL32!GlobalAlloc` at `0x140008548`
- `KERNEL32!GlobalAlloc` at `0x140008558`

## pseudocode

```c
int __fastcall bLoadTTF(
        unsigned __int64 a1,
        unsigned __int8 *a2,
        int a3,
        struct _TABLE_POINTERS *a4,
        unsigned int a5,
        unsigned __int16 a6,
        unsigned __int64 *a7,
        struct _TTF_CACHE *a8,
        unsigned int a9,
        const struct NamedInstanceBuilder *a10,
        unsigned int a11)
{
  unsigned int v14; // edx
  SIZE_T v15; // r15
  char v16; // r12
  char *v17; // rax
  char *v18; // rbx
  __int64 v19; // rcx
  unsigned __int16 v20; // dx
  unsigned __int16 v21; // r9
  __int64 v22; // rdx
  bool v23; // cf
  int v24; // r8d
  int v25; // eax
  __int128 v26; // xmm0
  unsigned int v27; // eax
  HGLOBAL v28; // rax
  void *v29; // rsi
  int v30; // edx
  __int16 v31; // ax
  struct sfnt_mappingTable *v32; // rdx
  HGLOBAL *v33; // r15
  int v34; // eax
  struct _IFIMETRICS *v36; // r12
  HGLOBAL v37; // rax
  void *v38; // r14
  unsigned int *v39; // rdx
  struct _FD_GLYPHSET *v40; // rcx
  __int16 ACP; // bx
  unsigned __int16 v42[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v43; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v44; // [rsp+88h] [rbp-78h] BYREF
  int v45; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v46; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v47; // [rsp+94h] [rbp-6Ch] BYREF
  int v48; // [rsp+98h] [rbp-68h]
  struct sfnt_mappingTable *v49; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v51; // [rsp+B8h] [rbp-48h]
  _DWORD v52[36]; // [rsp+C0h] [rbp-40h] BYREF
  char v53[8]; // [rsp+150h] [rbp+50h] BYREF
  HGLOBAL v54; // [rsp+158h] [rbp+58h]
  __int128 v55; // [rsp+160h] [rbp+60h]
  __int128 v56; // [rsp+170h] [rbp+70h]
  __int128 v57; // [rsp+180h] [rbp+80h]
  __int128 v58; // [rsp+190h] [rbp+90h]
  const void *(__fastcall *v59)(void *, int, int, void **); // [rsp+1A0h] [rbp+A0h]
  __int64 (__fastcall *v60)(); // [rsp+1A8h] [rbp+A8h]
  void (*v61)(void *, unsigned __int16, __int16 *, unsigned __int16, int *, int *, unsigned int); // [rsp+1B0h] [rbp+B0h]
  void (*v62)(void *, int *, unsigned int); // [rsp+1B8h] [rbp+B8h]
  void (__fastcall *v63)(void *, unsigned __int16 *, unsigned __int16); // [rsp+1C0h] [rbp+C0h]
  char *v64; // [rsp+1C8h] [rbp+C8h]
  char v65; // [rsp+1D8h] [rbp+D8h]
  __int16 v66; // [rsp+1E0h] [rbp+E0h]
  __int16 v67; // [rsp+1E2h] [rbp+E2h]
  __int16 v68; // [rsp+1E4h] [rbp+E4h]
  int v69; // [rsp+230h] [rbp+130h] BYREF
  __int128 v70; // [rsp+234h] [rbp+134h]
  __int128 v71; // [rsp+244h] [rbp+144h]

  v48 = a3;
  v51 = a1;
  memset_0(v52, 0, sizeof(v52));
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v65 = 0;
  memset_0(&v69, 0, 0x100u);
  v42[0] = 0;
  v43 = 0;
  v49 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  *a7 = 0;
  v50 = 0;
  if ( a8 )
    return bLoadTTF_Cache(a1, a7, a8, a9);
  if ( (unsigned int)bVerifyTTF(
                       a2,
                       v14,
                       a6,
                       a4,
                       (struct _IFISIZE *)v52,
                       v42,
                       &v43,
                       &v49,
                       &v47,
                       &v46,
                       (struct _CMAPINFO *)&v50,
                       &v45,
                       &v44,
                       a10,
                       a11) )
  {
    v15 = (unsigned int)(v52[0] + 440);
    if ( (unsigned int)v15 >= v52[0] )
    {
      v16 = v44;
      if ( v44 )
      {
        ACP = GetACP();
        GetOEMCP();
        if ( ACP == 932 || ACP == 949 )
          LODWORD(v50) = v50 | 4;
      }
      v17 = (char *)GlobalAlloc(0, v15);
      v18 = v17;
      if ( v17 )
      {
        *a7 = (unsigned __int64)v17;
        memset_0(v17, 0, v15);
        v19 = *((unsigned int *)a4 + 4);
        *((_QWORD *)v18 + 7) = v51;
        *((_DWORD *)v18 + 18) = v48;
        *((_QWORD *)v18 + 8) = a2;
        v20 = _byteswap_ushort(*(_WORD *)&a2[v19 + 18]);
        *((_WORD *)v18 + 198) = v20;
        if ( (unsigned __int16)(v20 - 16) <= 0x3FF0u )
        {
          v21 = v42[0];
          *((_WORD *)v18 + 200) = v43;
          *((_WORD *)v18 + 199) = v21;
          v22 = *((unsigned int *)a4 + 6);
          *((_DWORD *)v18 + 103) = -65536;
          *((_WORD *)v18 + 208) = _byteswap_ushort(*(_WORD *)&a2[v22 + 12]);
          v23 = v45 != 0;
          *((_WORD *)v18 + 209) = _byteswap_ushort(*(_WORD *)&a2[v22 + 14]);
          v24 = v23 ? 2 : 0;
          *((_DWORD *)v18 + 97) = v24;
          if ( (v16 & 1) != 0 )
            *((_DWORD *)v18 + 97) = v24 | 0x40;
          *((_QWORD *)v18 + 5) = 0;
          *((_WORD *)v18 + 201) = ui16LangId(v21, a6);
          v25 = (int)v49;
          *((_DWORD *)v18 + 12) = 0;
          *((_DWORD *)v18 + 98) = v25 - (_DWORD)a2;
          *((_OWORD *)v18 + 7) = *(_OWORD *)a4;
          *((_OWORD *)v18 + 8) = *((_OWORD *)a4 + 1);
          *((_OWORD *)v18 + 9) = *((_OWORD *)a4 + 2);
          *((_OWORD *)v18 + 10) = *((_OWORD *)a4 + 3);
          *((_OWORD *)v18 + 11) = *((_OWORD *)a4 + 4);
          *((_OWORD *)v18 + 12) = *((_OWORD *)a4 + 5);
          *((_OWORD *)v18 + 13) = *((_OWORD *)a4 + 6);
          *((_OWORD *)v18 + 14) = *((_OWORD *)a4 + 7);
          *((_OWORD *)v18 + 15) = *((_OWORD *)a4 + 8);
          *((_OWORD *)v18 + 16) = *((_OWORD *)a4 + 9);
          *((_OWORD *)v18 + 17) = *((_OWORD *)a4 + 10);
          *((_OWORD *)v18 + 18) = *((_OWORD *)a4 + 11);
          *((_OWORD *)v18 + 19) = *((_OWORD *)a4 + 12);
          *((_OWORD *)v18 + 20) = *((_OWORD *)a4 + 13);
          *((_OWORD *)v18 + 21) = *((_OWORD *)a4 + 14);
          v26 = v50;
          *((_QWORD *)v18 + 44) = *((_QWORD *)a4 + 30);
          *((_DWORD *)v18 + 90) = a5;
          v27 = v46;
          *(_OWORD *)(v18 + 420) = v26;
          *((_DWORD *)v18 + 102) = v27;
          *((_QWORD *)v18 + 10) = 0;
          v69 = 1196;
          v70 = 0;
          v54 = 0;
          v71 = 0;
          v55 = 0;
          v56 = 0;
          v57 = 0;
          v58 = 0;
          v28 = GlobalAlloc(0, 0x4B0u);
          v29 = v28;
          if ( v28 )
          {
            v54 = v28;
            v55 = 0;
            if ( !(unsigned int)fs_Initialize((struct fs_GlyphInputType *)v53, (struct fs_GlyphInfoType *)&v69) )
            {
              v64 = v18;
              v59 = pvGetPointerCallback;
              v60 = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
              v61 = vApplyOutlineVariationDeltasCallback;
              v62 = vApplyCVTVariationDeltasCallback;
              v63 = vGetVariationAxisCoordinatesCallback;
              LOWORD(v30) = 0;
              v65 = 1;
              if ( a10 )
                v30 = *((_DWORD *)a10 + 10);
              v31 = *((_WORD *)v18 + 199);
              v67 = *((_WORD *)v18 + 200);
              v68 = v30;
              v66 = v31;
              if ( !(unsigned int)fs_NewSfnt((struct fs_GlyphInputType *)v53, (struct fs_GlyphInfoType *)&v69) )
              {
                v32 = v49;
                v33 = (HGLOBAL *)(v18 + 88);
                *((_QWORD *)v18 + 3) = 0;
                *((_QWORD *)v18 + 4) = 0;
                *((_DWORD *)v18 + 95) = (DWORD2(v70) + 7) & 0xFFFFFFF8;
                v34 = HIDWORD(v70) + 7;
                *((_DWORD *)v18 + 93) = 1;
                *((_QWORD *)v18 + 2) = 0;
                *((_DWORD *)v18 + 96) = v34 & 0xFFFFFFF8;
                *((_DWORD *)v18 + 101) = v47;
                *((_QWORD *)v18 + 12) = 0;
                if ( bLoadGlyphSet(
                       (struct _TT_FONTFILE *)v18,
                       v32,
                       (struct fs_GlyphInputType *)v53,
                       (struct _CMAPINFO *)&v50,
                       (struct _FD_GLYPHSET **)v18 + 11) )
                {
                  vFill_IFIMETRICS(
                    (struct _TT_FONTFILE *)v18,
                    (struct _IFIMETRICS *)(v18 + 440),
                    (struct _IFISIZE *)v52,
                    (struct fs_GlyphInputType *)v53,
                    a10,
                    a11);
                  if ( (*((_DWORD *)v18 + 97) & 0x100) == 0
                    || !(unsigned int)bCheckVerticalTable((struct _TT_FONTFILE *)v18) )
                  {
                    goto LABEL_16;
                  }
                  v36 = (struct _IFIMETRICS *)GlobalAlloc(0, (v52[0] + 7) & 0xFFFFFFF8);
                  v37 = GlobalAlloc(0, *(unsigned int *)*v33);
                  v38 = v37;
                  if ( v36 )
                  {
                    if ( v37 )
                    {
                      vCopy_IFIV((struct _IFIMETRICS *)(v18 + 440), v36);
                      v39 = (unsigned int *)*v33;
                      *((_QWORD *)v18 + 2) = v36;
                      *((_DWORD *)v18 + 93) = 2;
                      memcpy_0(v38, v39, *v39);
                      v40 = (struct _FD_GLYPHSET *)*v33;
                      *((_QWORD *)v18 + 12) = v38;
                      vGetVerticalGSet(v40, (struct _TT_FONTFILE *)v18);
LABEL_16:
                      *((_QWORD *)v18 + 13) = 0;
                      GlobalFree(v29);
                      return 1;
                    }
                    GlobalFree(v36);
                  }
                  if ( *v33 )
                    GlobalFree(*v33);
                  if ( v38 )
                    GlobalFree(v38);
                  if ( *a7 )
                  {
                    GlobalFree((HGLOBAL)*a7);
                    *a7 = 0;
                  }
                  GlobalFree(v29);
                  return 0;
                }
              }
            }
            GlobalFree(v29);
          }
        }
        GlobalFree((HGLOBAL)*a7);
        *a7 = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140007f98  mov     [rsp-8+arg_0], rbx
0x140007f9d  push    rbp
0x140007f9e  push    rsi
0x140007f9f  push    rdi
0x140007fa0  push    r12
0x140007fa2  push    r13
0x140007fa4  push    r14
0x140007fa6  push    r15
0x140007fa8  lea     rbp, [rsp-240h]
0x140007fb0  sub     rsp, 340h
0x140007fb7  mov     rax, cs:__security_cookie
0x140007fbe  xor     rax, rsp
0x140007fc1  mov     [rbp+270h+var_40], rax
0x140007fc8  mov     rdi, [rbp+270h+arg_30]
0x140007fcf  mov     rsi, rdx
0x140007fd2  mov     rbx, [rbp+270h+arg_38]
0x140007fd9  mov     r15, rcx
0x140007fdc  mov     r13, [rbp+270h+arg_48]
0x140007fe3  xor     edx, edx; Val
0x140007fe5  mov     [rbp+270h+var_2D8], r8d
0x140007fe9  mov     r14, r9
0x140007fec  mov     [rbp+270h+var_2B8], rcx
0x140007ff0  mov     r8d, 90h; Size
0x140007ff6  lea     rcx, [rbp+270h+var_2B0]; void *
0x140007ffa  call    memset_0
0x140007fff  xor     r12d, r12d
0x140008002  lea     rcx, [rbp+270h+var_140]; void *
0x140008009  xor     edx, edx; Val
0x14000800b  mov     [rbp+270h+var_1C0], r12
0x140008012  mov     r8d, 100h; Size
0x140008018  mov     [rbp+270h+var_1B8], r12
0x14000801f  mov     [rbp+270h+var_1B0], r12
0x140008026  mov     [rbp+270h+var_198], r12b
0x14000802d  call    memset_0
0x140008032  mov     [rbp+270h+var_2F0], r12w
0x140008037  xorps   xmm0, xmm0
0x14000803a  mov     [rbp+270h+var_2EC], r12w
0x14000803f  mov     [rbp+270h+var_2D0], r12
0x140008043  mov     [rbp+270h+var_2DC], r12d
0x140008047  mov     [rbp+270h+var_2E0], r12d
0x14000804b  mov     [rbp+270h+var_2E4], r12d
0x14000804f  mov     [rbp+270h+var_2E8], r12d
0x140008053  mov     [rdi], r12
0x140008056  movups  [rbp+270h+var_2C8], xmm0
0x14000805a  test    rbx, rbx
0x14000805d  jnz     loc_1400084CC
0x140008063  mov     eax, [rbp+270h+arg_50]
0x140008069  mov     r9, r14; struct _TABLE_POINTERS *
0x14000806c  movzx   r8d, [rbp+270h+arg_28]; unsigned __int16
0x140008074  mov     rcx, rsi; unsigned __int8 *
0x140008077  mov     [rsp+370h+var_300], eax; unsigned int
0x14000807b  lea     rax, [rbp+270h+var_2E8]
0x14000807f  mov     [rsp+370h+var_308], r13; struct NamedInstanceBuilder *
0x140008084  mov     [rsp+370h+var_310], rax; unsigned int *
0x140008089  lea     rax, [rbp+270h+var_2E4]
0x14000808d  mov     [rsp+370h+var_318], rax; int *
0x140008092  lea     rax, [rbp+270h+var_2C8]
0x140008096  mov     [rsp+370h+var_320], rax; struct _CMAPINFO *
0x14000809b  lea     rax, [rbp+270h+var_2E0]
0x14000809f  mov     [rsp+370h+var_328], rax; unsigned int *
0x1400080a4  lea     rax, [rbp+270h+var_2DC]
0x1400080a8  mov     [rsp+370h+var_330], rax; unsigned int *
0x1400080ad  lea     rax, [rbp+270h+var_2D0]
0x1400080b1  mov     [rsp+370h+var_338], rax; struct sfnt_mappingTable **
0x1400080b6  lea     rax, [rbp+270h+var_2EC]
0x1400080ba  mov     [rsp+370h+var_340], rax; unsigned __int16 *
0x1400080bf  lea     rax, [rbp+270h+var_2F0]
0x1400080c3  mov     [rsp+370h+var_348], rax; unsigned __int16 *
0x1400080c8  lea     rax, [rbp+270h+var_2B0]
0x1400080cc  mov     [rsp+370h+var_350], rax; struct _IFISIZE *
0x1400080d1  call    ?bVerifyTTF@@YAHPEAXKGPEAU_TABLE_POINTERS@@PEAU_IFISIZE@@PEAG3PEAPEAUsfnt_mappingTable@@PEAK5PEAU_CMAPINFO@@PEAH5PEBVNamedInstanceBuilder@@I@Z; bVerifyTTF(void *,ulong,ushort,_TABLE_POINTERS *,_IFISIZE *,ushort *,ushort *,sfnt_mappingTable * *,ulong *,ulong *,_CMAPINFO *,int *,ulong *,NamedInstanceBuilder const *,uint)
0x1400080d6  test    eax, eax
0x1400080d8  jz      loc_140008520
0x1400080de  mov     eax, [rbp+270h+var_2B0]
0x1400080e1  lea     r15d, [rax+1B8h]
0x1400080e8  cmp     r15d, eax
0x1400080eb  jb      loc_140008520
0x1400080f1  mov     r12d, [rbp+270h+var_2E8]
0x1400080f5  test    r12d, r12d
0x1400080f8  jnz     loc_1400085B2
0x1400080fe  mov     rdx, r15; dwBytes
0x140008101  xor     ecx, ecx; uFlags
0x140008103  call    cs:__imp_GlobalAlloc
0x140008109  mov     rbx, rax
0x14000810c  test    rax, rax
0x14000810f  jz      loc_140008520
0x140008115  mov     r8, r15; Size
0x140008118  mov     [rdi], rax
0x14000811b  xor     edx, edx; Val
0x14000811d  mov     rcx, rax; void *
0x140008120  call    memset_0
0x140008125  mov     ecx, [r14+10h]
0x140008129  mov     rax, [rbp+270h+var_2B8]
0x14000812d  mov     [rbx+38h], rax
0x140008131  mov     eax, [rbp+270h+var_2D8]
0x140008134  mov     [rbx+48h], eax
0x140008137  mov     [rbx+40h], rsi
0x14000813b  movzx   eax, byte ptr [rcx+rsi+13h]
0x140008140  movzx   edx, byte ptr [rcx+rsi+12h]
0x140008145  shl     dx, 8
0x140008149  or      dx, ax
0x14000814c  mov     eax, 3FF0h
0x140008151  mov     [rbx+18Ch], dx
0x140008158  sub     dx, 10h
0x14000815c  cmp     dx, ax
0x14000815f  ja      loc_1400085E1
0x140008165  movzx   eax, [rbp+270h+var_2EC]
0x140008169  movzx   r9d, [rbp+270h+var_2F0]
0x14000816e  mov     [rbx+190h], ax
0x140008175  mov     [rbx+18Eh], r9w
0x14000817d  mov     edx, [r14+18h]
0x140008181  mov     dword ptr [rbx+19Ch], 0FFFF0000h
0x14000818b  movzx   eax, byte ptr [rdx+rsi+0Ch]
0x140008190  movzx   ecx, byte ptr [rdx+rsi+0Dh]
0x140008195  shl     ax, 8
0x140008199  or      cx, ax
0x14000819c  mov     [rbx+1A0h], cx
0x1400081a3  movzx   eax, byte ptr [rdx+rsi+0Eh]
0x1400081a8  movzx   ecx, byte ptr [rdx+rsi+0Fh]
0x1400081ad  shl     ax, 8
0x1400081b1  or      cx, ax
0x1400081b4  mov     eax, [rbp+270h+var_2E4]
0x1400081b7  neg     eax
0x1400081b9  mov     [rbx+1A2h], cx
0x1400081c0  sbb     r8d, r8d
0x1400081c3  and     r8d, 2
0x1400081c7  mov     [rbx+184h], r8d
0x1400081ce  test    r12b, 1
0x1400081d2  jnz     loc_1400085F6
0x1400081d8  movzx   edx, [rbp+270h+arg_28]; unsigned __int16
0x1400081df  xor     r12d, r12d
0x1400081e2  movzx   ecx, r9w; unsigned __int16
0x1400081e6  mov     [rbx+28h], r12
0x1400081ea  call    ?ui16LangId@@YAGGG@Z; ui16LangId(ushort,ushort)
0x1400081ef  mov     [rbx+192h], ax
0x1400081f6  mov     edx, 4B0h; dwBytes
0x1400081fb  mov     eax, dword ptr [rbp+270h+var_2D0]
0x1400081fe  xor     ecx, ecx; uFlags
0x140008200  mov     [rbx+30h], r12d
0x140008204  sub     eax, esi
0x140008206  mov     [rbx+188h], eax
0x14000820c  movups  xmm0, xmmword ptr [r14]
0x140008210  movups  xmmword ptr [rbx+70h], xmm0
0x140008214  movups  xmm1, xmmword ptr [r14+10h]
0x140008219  movups  xmmword ptr [rbx+80h], xmm1
0x140008220  movups  xmm0, xmmword ptr [r14+20h]
0x140008225  movups  xmmword ptr [rbx+90h], xmm0
0x14000822c  movups  xmm1, xmmword ptr [r14+30h]
0x140008231  movups  xmmword ptr [rbx+0A0h], xmm1
0x140008238  movups  xmm0, xmmword ptr [r14+40h]
0x14000823d  movups  xmmword ptr [rbx+0B0h], xmm0
0x140008244  movups  xmm1, xmmword ptr [r14+50h]
0x140008249  movups  xmmword ptr [rbx+0C0h], xmm1
0x140008250  movups  xmm0, xmmword ptr [r14+60h]
0x140008255  movups  xmmword ptr [rbx+0D0h], xmm0
0x14000825c  movups  xmm1, xmmword ptr [r14+70h]
0x140008261  movups  xmmword ptr [rbx+0E0h], xmm1
0x140008268  movups  xmm0, xmmword ptr [r14+80h]
0x140008270  movups  xmmword ptr [rbx+0F0h], xmm0
0x140008277  movups  xmm1, xmmword ptr [r14+90h]
0x14000827f  movups  xmmword ptr [rbx+100h], xmm1
0x140008286  movups  xmm0, xmmword ptr [r14+0A0h]
0x14000828e  movups  xmmword ptr [rbx+110h], xmm0
0x140008295  movups  xmm1, xmmword ptr [r14+0B0h]
0x14000829d  movups  xmmword ptr [rbx+120h], xmm1
0x1400082a4  movups  xmm0, xmmword ptr [r14+0C0h]
0x1400082ac  movups  xmmword ptr [rbx+130h], xmm0
0x1400082b3  movups  xmm1, xmmword ptr [r14+0D0h]
0x1400082bb  movups  xmmword ptr [rbx+140h], xmm1
0x1400082c2  movups  xmm0, xmmword ptr [r14+0E0h]
0x1400082ca  xorps   xmm1, xmm1
0x1400082cd  movups  xmmword ptr [rbx+150h], xmm0
0x1400082d4  mov     rax, [r14+0F0h]
0x1400082db  movups  xmm0, [rbp+270h+var_2C8]
0x1400082df  mov     [rbx+160h], rax
0x1400082e6  mov     eax, [rbp+270h+arg_20]
0x1400082ec  mov     [rbx+168h], eax
0x1400082f2  mov     eax, [rbp+270h+var_2E0]
0x1400082f5  movdqu  xmmword ptr [rbx+1A4h], xmm0
0x1400082fd  mov     [rbx+198h], eax
0x140008303  mov     [rbx+50h], r12
0x140008307  xorps   xmm0, xmm0
0x14000830a  mov     [rbp+270h+var_140], 4ACh
0x140008314  movups  [rbp+270h+var_13C], xmm0
0x14000831b  mov     [rbp+270h+var_218], r12
0x14000831f  movups  [rbp+270h+var_12C], xmm0
0x140008326  movdqa  [rbp+270h+var_210], xmm0
0x14000832b  movdqa  [rbp+270h+var_200], xmm1
0x140008330  movdqa  [rbp+270h+var_1F0], xmm0
0x140008338  movdqa  [rbp+270h+var_1E0], xmm1
0x140008340  call    cs:__imp_GlobalAlloc
0x140008346  mov     rsi, rax
0x140008349  test    rax, rax
0x14000834c  jz      loc_140008514
0x140008352  xorps   xmm0, xmm0
0x140008355  mov     [rbp+270h+var_218], rax
0x140008359  lea     rdx, [rbp+270h+var_140]; struct fs_GlyphInfoType *
0x140008360  lea     rcx, [rbp+270h+var_220]; struct fs_GlyphInputType *
0x140008364  movups  [rbp+270h+var_210], xmm0
0x140008368  call    ?fs_Initialize@@YAHPEAUfs_GlyphInputType@@PEAUfs_GlyphInfoType@@@Z; fs_Initialize(fs_GlyphInputType *,fs_GlyphInfoType *)
0x14000836d  test    eax, eax
0x14000836f  jnz     loc_14000850B
0x140008375  mov     [rbp+270h+var_1A8], rbx
0x14000837c  lea     rax, ?pvGetPointerCallback@@YAPEBXPEAXHHPEAPEAX@Z; pvGetPointerCallback(void *,int,int,void * *)
0x140008383  mov     [rbp+270h+var_1D0], rax
0x14000838a  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x140008391  mov     [rbp+270h+var_1C8], rax
0x140008398  lea     rax, ?vApplyOutlineVariationDeltasCallback@@YAXPEAXGPEAFGPEAH2I@Z; vApplyOutlineVariationDeltasCallback(void *,ushort,short *,ushort,int *,int *,uint)
0x14000839f  mov     [rbp+270h+var_1C0], rax
0x1400083a6  lea     rax, ?vApplyCVTVariationDeltasCallback@@YAXPEAXPEAHI@Z; vApplyCVTVariationDeltasCallback(void *,int *,uint)
0x1400083ad  mov     [rbp+270h+var_1B8], rax
0x1400083b4  lea     rax, ?vGetVariationAxisCoordinatesCallback@@YAXPEAXPEAGG@Z; vGetVariationAxisCoordinatesCallback(void *,ushort *,ushort)
0x1400083bb  mov     [rbp+270h+var_1B0], rax
0x1400083c2  mov     edx, r12d
0x1400083c5  mov     [rbp+270h+var_198], 1
0x1400083cc  test    r13, r13
0x1400083cf  jnz     loc_140008524
0x1400083d5  movzx   ecx, word ptr [rbx+190h]
0x1400083dc  movzx   eax, word ptr [rbx+18Eh]
0x1400083e3  mov     [rbp+270h+var_18E], cx
0x1400083ea  lea     rcx, [rbp+270h+var_220]; struct fs_GlyphInputType *
0x1400083ee  mov     [rbp+270h+var_18C], dx
0x1400083f5  lea     rdx, [rbp+270h+var_140]; struct fs_GlyphInfoType *
0x1400083fc  mov     [rbp+270h+var_190], ax
0x140008403  call    ?fs_NewSfnt@@YAHPEAUfs_GlyphInputType@@PEAUfs_GlyphInfoType@@@Z; fs_NewSfnt(fs_GlyphInputType *,fs_GlyphInfoType *)
0x140008408  test    eax, eax
0x14000840a  jnz     loc_14000850B
0x140008410  mov     rdx, [rbp+270h+var_2D0]; struct sfnt_mappingTable *
0x140008414  lea     r15, [rbx+58h]
0x140008418  mov     [rbx+18h], r12
0x14000841c  lea     r9, [rbp+270h+var_2C8]; struct _CMAPINFO *
0x140008420  mov     [rbx+20h], r12
0x140008424  lea     r8, [rbp+270h+var_220]; struct fs_GlyphInputType *
0x140008428  mov     eax, dword ptr [rbp+270h+var_13C+8]
0x14000842e  mov     r14d, 0FFFFFFF8h
0x140008434  add     eax, 7
0x140008437  mov     [rsp+370h+var_350], r15; struct _FD_GLYPHSET **
0x14000843c  and     eax, r14d
0x14000843f  mov     rcx, rbx; struct _TT_FONTFILE *
0x140008442  mov     [rbx+17Ch], eax
0x140008448  mov     eax, dword ptr [rbp+270h+var_13C+0Ch]
0x14000844e  add     eax, 7
0x140008451  mov     dword ptr [rbx+174h], 1
0x14000845b  and     eax, r14d
0x14000845e  mov     [rbx+10h], r12
0x140008462  mov     [rbx+180h], eax
0x140008468  mov     eax, [rbp+270h+var_2DC]
0x14000846b  mov     [rbx+194h], eax
0x140008471  mov     [rbx+60h], r12
0x140008475  call    ?bLoadGlyphSet@@YAHPEAU_TT_FONTFILE@@PEAUsfnt_mappingTable@@PEAUfs_GlyphInputType@@PEAU_CMAPINFO@@PEAPEAU_FD_GLYPHSET@@@Z; bLoadGlyphSet(_TT_FONTFILE *,sfnt_mappingTable *,fs_GlyphInputType *,_CMAPINFO *,_FD_GLYPHSET * *)
0x14000847a  test    eax, eax
0x14000847c  jz      loc_14000850B
0x140008482  mov     ecx, [rbp+270h+arg_50]
0x140008488  lea     rdx, [rbx+1B8h]; struct _IFIMETRICS *
0x14000848f  mov     dword ptr [rsp+370h+var_348], ecx; unsigned int
0x140008493  lea     r9, [rbp+270h+var_220]; struct fs_GlyphInputType *
0x140008497  mov     rcx, rbx; struct _TT_FONTFILE *
0x14000849a  mov     [rsp+370h+var_350], r13; struct NamedInstanceBuilder *
0x14000849f  lea     r8, [rbp+270h+var_2B0]; struct _IFISIZE *
0x1400084a3  call    ?vFill_IFIMETRICS@@YAXPEAU_TT_FONTFILE@@PEAU_IFIMETRICS@@PEAU_IFISIZE@@PEAUfs_GlyphInputType@@PEBVNamedInstanceBuilder@@I@Z; vFill_IFIMETRICS(_TT_FONTFILE *,_IFIMETRICS *,_IFISIZE *,fs_GlyphInputType *,NamedInstanceBuilder const *,uint)
0x1400084a8  test    dword ptr [rbx+184h], 100h
0x1400084b2  jnz     short loc_14000852D
0x1400084b4  mov     rcx, rsi; hMem
0x1400084b7  mov     qword ptr [rbx+68h], 0
0x1400084bf  call    cs:__imp_GlobalFree
0x1400084c5  mov     eax, 1
0x1400084ca  jmp     short loc_1400084E1
0x1400084cc  mov     r9d, [rbp+270h+arg_40]; unsigned int
0x1400084d3  mov     r8, rbx; struct _TTF_CACHE *
0x1400084d6  mov     rdx, rdi; unsigned __int64 *
0x1400084d9  mov     rcx, r15; unsigned __int64
0x1400084dc  call    ?bLoadTTF_Cache@@YAH_KPEA_KPEAU_TTF_CACHE@@K@Z; bLoadTTF_Cache(unsigned __int64,unsigned __int64 *,_TTF_CACHE *,ulong)
0x1400084e1  mov     rcx, [rbp+270h+var_40]
0x1400084e8  xor     rcx, rsp; StackCookie
0x1400084eb  call    __security_check_cookie
0x1400084f0  mov     rbx, [rsp+370h+arg_0]
0x1400084f8  add     rsp, 340h
0x1400084ff  pop     r15
0x140008501  pop     r14
0x140008503  pop     r13
0x140008505  pop     r12
0x140008507  pop     rdi
0x140008508  pop     rsi
0x140008509  pop     rbp
0x14000850a  retn
0x14000850b  mov     rcx, rsi; hMem
0x14000850e  call    cs:__imp_GlobalFree
0x140008514  mov     rcx, [rdi]; hMem
0x140008517  call    cs:__imp_GlobalFree
0x14000851d  mov     [rdi], r12
0x140008520  xor     eax, eax
0x140008522  jmp     short loc_1400084E1
0x140008524  mov     edx, [r13+28h]
0x140008528  jmp     loc_1400083D5
0x14000852d  mov     rcx, rbx; struct _TT_FONTFILE *
0x140008530  call    ?bCheckVerticalTable@@YAHPEAU_TT_FONTFILE@@@Z; bCheckVerticalTable(_TT_FONTFILE *)
0x140008535  test    eax, eax
0x140008537  jz      loc_1400084B4
0x14000853d  mov     edx, [rbp+270h+var_2B0]
0x140008540  xor     ecx, ecx; uFlags
  ... truncated ...
```
