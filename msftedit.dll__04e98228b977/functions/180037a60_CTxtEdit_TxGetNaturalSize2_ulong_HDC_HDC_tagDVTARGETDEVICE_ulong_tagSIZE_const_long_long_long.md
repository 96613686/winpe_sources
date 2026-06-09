# CTxtEdit::TxGetNaturalSize2(ulong,HDC__ *,HDC__ *,tagDVTARGETDEVICE *,ulong,tagSIZE const *,long *,long *,long *)

- ea: `0x180037a60`
- end: `0x1800382da`
- name: `?TxGetNaturalSize2@CTxtEdit@@UEAAJKPEAUHDC__@@0PEAUtagDVTARGETDEVICE@@KPEBUtagSIZE@@PEAJ33@Z`
- size: `2170`
- prototype: `int(CTxtEdit *__hidden this, unsigned int, HDC, HDC, struct tagDVTARGETDEVICE *, unsigned int, const struct tagSIZE *, int *, int *, int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update`

## callees

- `0x18003634c`
- `0x1800363e8`
- `0x1800366b0`
- `0x180037a60`
- `0x1800382e0`
- `0x180044ea4`
- `0x18004d594`
- `0x18004d658`
- `0x18004d8f8`
- `0x180098490`
- `0x1800e96a0`
- `0x1800f8714`
- `0x1800fcce8`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800382c9`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800382c9`
- `ext-ms-win-gdi-dc-create-l1-1-1!CreateICW` at `0x18003812b`
- `ext-ms-win-gdi-dc-create-l1-1-1!CreateICW` at `0x18003812b`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180037b5e`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180038034`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003804c`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180038180`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180037b5e`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180038034`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x18003804c`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x180038180`

## pseudocode

```c
__int64 __fastcall CTxtEdit::TxGetNaturalSize2(
        unsigned __int64 this,
        int a2,
        HDC a3,
        HDC a4,
        struct tagDVTARGETDEVICE *a5,
        unsigned int a6,
        const struct tagSIZE *a7,
        int *a8,
        int *a9,
        int *a10)
{
  bool v14; // al
  HDC v15; // r14
  struct tagDVTARGETDEVICE *v16; // rsi
  int *v17; // rdx
  const struct tagSIZE *v18; // r15
  HDC v19; // r12
  int DeviceCaps; // eax
  BOOL v21; // edx
  int *v22; // r13
  int v23; // eax
  int v24; // ecx
  __int64 v25; // rcx
  __int64 v26; // r15
  int v27; // eax
  const struct IDpiAccessor *v28; // rdx
  bool v29; // cl
  struct IGraphicContext *v30; // rax
  __int64 v31; // r15
  int v32; // eax
  __int64 v33; // rax
  void (__fastcall ****v34)(_QWORD, int *, int *, __int64 *, char *); // r15
  void (__fastcall ***v35)(_QWORD, int *, int *, __int64 *, char *); // r15
  struct IGraphicContext *v36; // rcx
  _QWORD *v37; // r15
  const struct IDpiAccessor *v38; // rbx
  char v39; // al
  __int64 v40; // rdx
  _QWORD *v41; // rbx
  int v42; // eax
  __int64 v43; // rbx
  void (__fastcall ****v44)(_QWORD, int *, int *, __int64 *, char *); // rbx
  void (__fastcall ***v45)(_QWORD, int *, int *, __int64 *, char *); // rbx
  __int64 v46; // rsi
  unsigned int v47; // ebx
  unsigned int v48; // r14d
  int v49; // ebx
  int v50; // eax
  int v51; // r8d
  int *v52; // rcx
  __int64 v53; // rax
  __int64 v55; // rax
  void (__fastcall ****v56)(_QWORD, int *, int *, __int64 *, char *); // rbx
  void (__fastcall ***v57)(_QWORD, int *, int *, __int64 *, char *); // rbx
  CMsgCallBack *v58; // rcx
  int *v59; // rax
  HDC ICW; // rax
  void (__fastcall **v61)(_QWORD, int *, int *, __int64 *, char *); // rax
  void (__fastcall **v62)(_QWORD, int *, int *, __int64 *, char *); // rax
  int v63; // eax
  int v64; // eax
  int v65; // [rsp+30h] [rbp-D0h] BYREF
  int v66; // [rsp+34h] [rbp-CCh] BYREF
  struct IGraphicContext *GraphicContext; // [rsp+38h] [rbp-C8h] BYREF
  char v68; // [rsp+40h] [rbp-C0h]
  __int64 v69; // [rsp+44h] [rbp-BCh] BYREF
  char v70; // [rsp+4Ch] [rbp-B4h]
  int v71; // [rsp+50h] [rbp-B0h] BYREF
  int v72; // [rsp+54h] [rbp-ACh] BYREF
  int v73; // [rsp+58h] [rbp-A8h] BYREF
  void **v74; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v75; // [rsp+68h] [rbp-98h]
  void **v76; // [rsp+70h] [rbp-90h] BYREF
  __int64 v77; // [rsp+78h] [rbp-88h]
  struct IGraphicContext *v78; // [rsp+80h] [rbp-80h] BYREF
  char v79; // [rsp+88h] [rbp-78h]
  __int64 v80; // [rsp+8Ch] [rbp-74h]
  char v81; // [rsp+94h] [rbp-6Ch]
  unsigned __int64 v82; // [rsp+98h] [rbp-68h] BYREF
  struct IGraphicContext *v83; // [rsp+A0h] [rbp-60h] BYREF
  char v84; // [rsp+A8h] [rbp-58h]
  __int64 v85; // [rsp+ACh] [rbp-54h] BYREF
  char v86; // [rsp+B4h] [rbp-4Ch]
  _QWORD v87[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct IGraphicContext *v88; // [rsp+D0h] [rbp-30h] BYREF
  char v89; // [rsp+D8h] [rbp-28h]
  __int64 v90; // [rsp+DCh] [rbp-24h]
  char v91; // [rsp+E4h] [rbp-1Ch]
  __int16 v92; // [rsp+E8h] [rbp-18h]
  __int64 v93; // [rsp+ECh] [rbp-14h]
  int v94; // [rsp+F8h] [rbp-8h]
  __int128 v95; // [rsp+100h] [rbp+0h]
  BOOL v96; // [rsp+150h] [rbp+50h]
  int v97; // [rsp+158h] [rbp+58h] BYREF

  v97 = a2;
  v14 = CCallMgrCenter::EnterContext((CCallMgrCenter *)(this + 48));
  v15 = 0;
  v73 = 0;
  v82 = ((this & -(__int64)v14) + 48) & -(__int64)((this & -(__int64)v14) != 0);
  if ( a2 != 1 && a2 != 8 )
  {
    v49 = -2147221397;
LABEL_56:
    CCallMgr::~CCallMgr((CCallMgr *)&v82);
    return (unsigned int)v49;
  }
  v16 = a5;
  if ( !a4 || a5 )
  {
    if ( a8 )
    {
      v17 = a9;
      if ( a9 )
      {
        if ( (a6 & 0x3FFFFFFF) <= 4 && a6 != -2147483646 )
        {
          v18 = a7;
          if ( !a7->cy )
          {
            v59 = a10;
            *a8 = 0;
            *v17 = 0;
            if ( v59 )
              *v59 = 0;
            v49 = 0;
            goto LABEL_56;
          }
          v19 = 0;
          if ( !a4 && a5 )
          {
            ICW = CreateICW(
                    (LPCWSTR)((char *)a5 + a5->tdDriverNameOffset),
                    (LPCWSTR)((char *)a5 + a5->tdDeviceNameOffset),
                    (LPCWSTR)((char *)a5 + a5->tdPortNameOffset),
                    (const DEVMODEW *)((char *)a5 + a5->tdExtDevmodeOffset));
            v19 = ICW;
            if ( !ICW )
            {
              v49 = -2147467259;
              goto LABEL_56;
            }
            a4 = ICW;
          }
          if ( (*(_BYTE *)(this + 176) & 8) != 0 )
          {
            if ( *(_QWORD *)(this + 304) )
            {
              v58 = *(CMsgCallBack **)(this + 312);
              if ( v58 )
                CMsgCallBack::NotifyEvents(v58, 0x80u);
            }
          }
          if ( (*(_BYTE *)(this + 276) & 0x40) != 0 )
          {
            DeviceCaps = 1;
          }
          else
          {
            v15 = a3;
            DeviceCaps = GetDeviceCaps(a3, 2);
          }
          v21 = (g_dwFlagsCTO & 1) != 0 && DeviceCaps == 1;
          v22 = a8;
          v96 = v21;
          v23 = *a8;
          v24 = *a9;
          v65 = *a8;
          v66 = v24;
          if ( v21 )
          {
            v65 = 8 * v23;
            v66 = 8 * v24;
          }
          v25 = *(_QWORD *)(this + 136);
          *(_DWORD *)(v25 + 140) = v18->cy;
          *(_QWORD *)(v25 + 144) = 0;
          v26 = *(_QWORD *)(this + 568);
          v74 = &COverrideDpi::`vftable';
          v75 = 0;
          if ( v26 )
          {
            LODWORD(v75) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
            v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          else
          {
            LODWORD(v75) = CW32System::_xPerInchScreenDC;
            v27 = CW32System::_yPerInchScreenDC;
          }
          HIDWORD(v75) = v27;
          if ( v15 && ((*(_BYTE *)(this + 280) & 1) == 0 || GetDeviceCaps(v15, 2) == 2) )
          {
            LODWORD(v75) = GetDeviceCaps(v15, 88);
            HIDWORD(v75) = GetDeviceCaps(v15, 90);
          }
          if ( (a6 & 0xBFFFFFFF) == 2 )
          {
            v55 = *(_QWORD *)(this + 256);
            if ( v55 && (v56 = *(void (__fastcall *****)(_QWORD, int *, int *, __int64 *, char *))(v55 + 80)) != 0 )
              v57 = *v56;
            else
              v57 = 0;
            GraphicContext = CreateGraphicContext(
                               (*(_BYTE *)(this + 276) & 0x40) != 0,
                               (const struct IDpiAccessor *)&v74,
                               v15,
                               0);
            v68 = 0;
            v69 = 0;
            v70 = 0;
            if ( v57 )
            {
              v70 = 1;
              v61 = *v57;
              v71 = 0;
              v97 = 0;
              (*v61)(v57, &v71, &v97, &v69, (char *)&v69 + 4);
            }
            v49 = CDisplay::RoundToLine(*(CDisplay **)(this + 136), (const struct CHDC *)&GraphicContext, v65, &v66);
            CHDC::~CHDC((CHDC *)&GraphicContext);
          }
          else
          {
            v28 = *(const struct IDpiAccessor **)(this + 568);
            v29 = (*(_BYTE *)(this + 276) & 0x40) != 0;
            v87[0] = 0;
            v87[1] = this;
            v30 = CreateGraphicContext(v29, v28, 0, 0);
            v89 = 0;
            v90 = 0;
            v91 = 0;
            v92 = 0;
            v93 = 0;
            v94 = 0;
            v31 = *(_QWORD *)(this + 568);
            v88 = v30;
            v76 = &COverrideDpi::`vftable';
            v95 = 0;
            v77 = 0;
            if ( v31 )
            {
              LODWORD(v77) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
              v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            }
            else
            {
              LODWORD(v77) = CW32System::_xPerInchScreenDC;
              v32 = CW32System::_yPerInchScreenDC;
            }
            HIDWORD(v77) = v32;
            if ( a4 )
              COverrideDpi::UpdateDpi((COverrideDpi *)&v76, a4);
            v33 = *(_QWORD *)(this + 256);
            if ( v33 && (v34 = *(void (__fastcall *****)(_QWORD, int *, int *, __int64 *, char *))(v33 + 80)) != 0 )
              v35 = *v34;
            else
              v35 = 0;
            v36 = CreateGraphicContext((*(_BYTE *)(this + 276) & 0x40) != 0, (const struct IDpiAccessor *)&v76, a4, 0);
            GraphicContext = v36;
            v68 = 0;
            v69 = 0;
            v70 = 0;
            if ( v35 )
            {
              v72 = 0;
              v71 = 0;
              v70 = 1;
              (**v35)(v35, &v72, &v71, &v69, (char *)&v69 + 4);
              v36 = GraphicContext;
            }
            v37 = *(_QWORD **)(this + 136);
            v38 = *(const struct IDpiAccessor **)(v37[2] + 568LL);
            v39 = (*(__int64 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v36 + 80LL))(v36);
            v78 = CreateGraphicContext(v39, v38, 0, 0);
            v79 = 0;
            v80 = 0;
            v81 = 0;
            (*(void (__fastcall **)(struct IGraphicContext *, struct IGraphicContext *))(*(_QWORD *)v78 + 8LL))(
              v78,
              GraphicContext);
            v79 = v68;
            v80 = v69;
            v81 = v70;
            if ( !v70 && !(*(unsigned __int8 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v78 + 24LL))(v78) )
            {
              v40 = v37[11];
              if ( v40 )
                CHDC::SetDC((CHDC *)&v78, (const struct CHDC *)(v40 + 8));
            }
            v41 = (_QWORD *)v37[8];
            if ( !v41 )
            {
              v37[8] = v87;
              v41 = v87;
            }
            ++*(_DWORD *)v41;
            ++*((_DWORD *)v41 + 1);
            v42 = v97;
            v41[9] = v16;
            v41[8] = 0;
            *((_DWORD *)v41 + 14) = v42;
            if ( v81 || (*(unsigned __int8 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v78 + 24LL))(v78) )
              CDevDesc::SetDC((CDevDesc *)(v41 + 1), (const struct CHDC *)&v78, -1, -1);
            CHDC::~CHDC((CHDC *)&v78);
            v43 = *(_QWORD *)(this + 256);
            if ( v43 && (v44 = *(void (__fastcall *****)(_QWORD, int *, int *, __int64 *, char *))(v43 + 80)) != 0 )
              v45 = *v44;
            else
              v45 = 0;
            v83 = CreateGraphicContext((*(_BYTE *)(this + 276) & 0x40) != 0, (const struct IDpiAccessor *)&v74, v15, 0);
            v84 = 0;
            v85 = 0;
            v86 = 0;
            if ( v45 )
            {
              v86 = 1;
              v62 = *v45;
              v72 = 0;
              v97 = 0;
              (*v62)(v45, &v72, &v97, &v85, (char *)&v85 + 4);
            }
            v46 = *(_QWORD *)(this + 136);
            v47 = *(_DWORD *)(v46 + 52);
            v48 = *(_DWORD *)(v46 + 56);
            CDevDesc::SetDC((CDevDesc *)(v46 + 16), (const struct CHDC *)&v83, -1, -1);
            CDisplay::SetDispResolution((CDisplay *)v46);
            if ( __PAIR64__(v48, v47) != *(_QWORD *)(v46 + 52) )
              *(_QWORD *)(v46 + 144) = 0;
            v49 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, int *, int *))(**(_QWORD **)(this + 136) + 456LL))(
                    *(_QWORD *)(this + 136),
                    a6,
                    &v65,
                    &v66,
                    &v73);
            CDevDesc::ResetDCW((CDevDesc *)(*(_QWORD *)(this + 136) + 16LL));
            CDisplay::ReleaseDrawInfo(*(CDisplay **)(this + 136));
            CHDC::~CHDC((CHDC *)&v83);
            CHDC::~CHDC((CHDC *)&GraphicContext);
            v76 = &IDpiAccessor::`vftable';
            CHDC::~CHDC((CHDC *)&v88);
          }
          if ( v49 >= 0 )
          {
            if ( v96 )
            {
              v63 = v65 - 4;
              if ( v65 + 4 >= 0 )
                v63 = v65 + 4;
              v51 = v63 / 8;
              v65 = v63 / 8;
              v64 = v66 - 4;
              if ( v66 + 4 >= 0 )
                v64 = v66 + 4;
              v50 = v64 / 8;
              v66 = v50;
            }
            else
            {
              v50 = v66;
              v51 = v65;
            }
            v52 = a9;
            *v22 = v51;
            *v52 = v50;
            if ( a10 )
              *a10 = v73;
          }
          if ( v19 )
            DeleteDC(v19);
          v53 = *(_QWORD *)(this + 136);
          *(_QWORD *)(v53 + 140) = 0;
          *(_DWORD *)(v53 + 148) = 0;
          v74 = &IDpiAccessor::`vftable';
          goto LABEL_56;
        }
      }
    }
  }
  CCallMgr::~CCallMgr((CCallMgr *)&v82);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180037a60  mov     [rsp-8+arg_10], rbx
0x180037a65  mov     [rsp-8+arg_8], edx
0x180037a69  push    rbp
0x180037a6a  push    rsi
0x180037a6b  push    rdi
0x180037a6c  push    r12
0x180037a6e  push    r13
0x180037a70  push    r14
0x180037a72  push    r15
0x180037a74  lea     rbp, [rsp-10h]
0x180037a79  sub     rsp, 110h
0x180037a80  mov     rdi, rcx
0x180037a83  mov     rbx, r9
0x180037a86  add     rcx, 30h ; '0'; this
0x180037a8a  mov     r13, r8
0x180037a8d  mov     esi, edx
0x180037a8f  call    ?EnterContext@CCallMgrCenter@@AEAA_NXZ; CCallMgrCenter::EnterContext(void)
0x180037a94  neg     al
0x180037a96  sbb     r11, r11
0x180037a99  and     r11, rdi
0x180037a9c  lea     r10, [r11+30h]
0x180037aa0  neg     r11
0x180037aa3  sbb     rax, rax
0x180037aa6  xor     r14d, r14d
0x180037aa9  and     rax, r10
0x180037aac  mov     [rsp+140h+var_E8], r14d
0x180037ab1  mov     [rbp+40h+var_A8], rax
0x180037ab5  cmp     esi, 1
0x180037ab8  jnz     loc_1800380D3
0x180037abe  mov     rsi, [rbp+40h+arg_20]
0x180037ac2  test    rbx, rbx
0x180037ac5  jnz     loc_1800380E6
0x180037acb  mov     rcx, [rbp+40h+arg_38]
0x180037ad2  test    rcx, rcx
0x180037ad5  jz      loc_18003806B
0x180037adb  mov     rdx, [rbp+40h+arg_40]
0x180037ae2  test    rdx, rdx
0x180037ae5  jz      loc_18003806B
0x180037aeb  mov     eax, [rbp+40h+arg_28]
0x180037aee  and     eax, 3FFFFFFFh
0x180037af3  cmp     eax, 4
0x180037af6  ja      loc_18003806B
0x180037afc  cmp     [rbp+40h+arg_28], 80000002h
0x180037b03  jz      loc_18003806B
0x180037b09  mov     r15, [rbp+40h+arg_30]
0x180037b10  cmp     [r15+4], r14d
0x180037b14  jz      loc_1800380F0
0x180037b1a  mov     r12, r14
0x180037b1d  test    rbx, rbx
0x180037b20  jnz     short loc_180037B2B
0x180037b22  test    rsi, rsi
0x180037b25  jnz     loc_18003810D
0x180037b2b  test    byte ptr [rdi+0B0h], 8
0x180037b32  jz      short loc_180037B41
0x180037b34  cmp     [rdi+130h], r14
0x180037b3b  jnz     loc_18003807E
0x180037b41  mov     al, [rdi+114h]
0x180037b47  shr     al, 6
0x180037b4a  test    al, 1
0x180037b4c  cmovz   r14, r13
0x180037b50  jnz     loc_180038061
0x180037b56  mov     edx, 2; index
0x180037b5b  mov     rcx, r14; hdc
0x180037b5e  call    cs:__imp_GetDeviceCaps
0x180037b65  nop     dword ptr [rax+rax+00h]
0x180037b6a  test    byte ptr cs:?g_dwFlagsCTO@@3KA, 1; ulong g_dwFlagsCTO
0x180037b71  jnz     loc_180038151
0x180037b77  xor     edx, edx
0x180037b79  mov     r13, [rbp+40h+arg_38]
0x180037b80  mov     rcx, [rbp+40h+arg_40]
0x180037b87  mov     [rbp+40h+arg_0], edx
0x180037b8a  mov     eax, [r13+0]
0x180037b8e  mov     ecx, [rcx]
0x180037b90  mov     [rsp+140h+var_110], eax
0x180037b94  mov     [rsp+140h+var_10C], ecx
0x180037b98  test    edx, edx
0x180037b9a  jnz     loc_180038161
0x180037ba0  mov     eax, [r15+4]
0x180037ba4  mov     rcx, [rdi+88h]
0x180037bab  mov     [rcx+8Ch], eax
0x180037bb1  lea     rax, ??_7COverrideDpi@@6B@; const COverrideDpi::`vftable'
0x180037bb8  mov     qword ptr [rcx+90h], 0
0x180037bc3  mov     r15, [rdi+238h]
0x180037bca  mov     [rsp+140h+var_E0], rax
0x180037bcf  mov     [rsp+140h+var_D8], 0
0x180037bd8  test    r15, r15
0x180037bdb  jz      loc_1800380A9
0x180037be1  mov     rax, [r15]
0x180037be4  mov     rcx, r15
0x180037be7  mov     rax, [rax+8]
0x180037beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037bf0  mov     dword ptr [rsp+140h+var_D8], eax
0x180037bf4  mov     rcx, r15
0x180037bf7  mov     rax, [r15]
0x180037bfa  mov     rax, [rax+10h]
0x180037bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c03  xor     r15d, r15d
0x180037c06  mov     dword ptr [rsp+140h+var_D8+4], eax
0x180037c0a  test    r14, r14
0x180037c0d  jnz     loc_18003801F
0x180037c13  mov     eax, [rbp+40h+arg_28]
0x180037c16  btr     eax, 1Eh
0x180037c1a  cmp     eax, 2
0x180037c1d  jz      loc_180037F97
0x180037c23  mov     cl, [rdi+114h]
0x180037c29  xor     r9d, r9d; struct ITextRenderTarget *
0x180037c2c  mov     rdx, [rdi+238h]; struct IDpiAccessor *
0x180037c33  xor     r8d, r8d; HDC
0x180037c36  shr     cl, 6
0x180037c39  and     cl, 1; bool
0x180037c3c  mov     [rbp+40h+var_80], r15
0x180037c40  mov     [rbp+40h+var_78], rdi
0x180037c44  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x180037c49  mov     [rbp+40h+var_68], r15b
0x180037c4d  xorps   xmm0, xmm0
0x180037c50  mov     [rbp+40h+var_64], r15
0x180037c54  mov     [rbp+40h+var_5C], r15b
0x180037c58  mov     [rbp+40h+var_58], r15w
0x180037c5d  mov     [rbp+40h+var_54], r15
0x180037c61  mov     [rbp+40h+var_48], r15d
0x180037c65  mov     r15, [rdi+238h]
0x180037c6c  mov     [rbp+40h+var_70], rax
0x180037c70  lea     rax, ??_7COverrideDpi@@6B@; const COverrideDpi::`vftable'
0x180037c77  mov     [rsp+140h+var_D0], rax
0x180037c7c  movdqa  [rbp+40h+var_40], xmm0
0x180037c81  mov     [rsp+140h+var_C8], 0
0x180037c8a  test    r15, r15
0x180037c8d  jz      loc_1800380BE
0x180037c93  mov     rax, [r15]
0x180037c96  mov     rcx, r15
0x180037c99  mov     rax, [rax+8]
0x180037c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ca2  mov     dword ptr [rsp+140h+var_C8], eax
0x180037ca6  mov     rcx, r15
0x180037ca9  mov     rax, [r15]
0x180037cac  mov     rax, [rax+10h]
0x180037cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037cb5  mov     dword ptr [rsp+140h+var_C8+4], eax
0x180037cb9  test    rbx, rbx
0x180037cbc  jnz     loc_1800381DB
0x180037cc2  mov     rax, [rdi+100h]
0x180037cc9  test    rax, rax
0x180037ccc  jz      short loc_180037CDB
0x180037cce  mov     r15, [rax+50h]
0x180037cd2  test    r15, r15
0x180037cd5  jnz     loc_1800381ED
0x180037cdb  xor     r15d, r15d
0x180037cde  mov     cl, [rdi+114h]
0x180037ce4  lea     rdx, [rsp+140h+var_D0]; struct IDpiAccessor *
0x180037ce9  shr     cl, 6
0x180037cec  xor     r9d, r9d; struct ITextRenderTarget *
0x180037cef  and     cl, 1; bool
0x180037cf2  mov     r8, rbx; HDC
0x180037cf5  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x180037cfa  mov     rcx, rax
0x180037cfd  mov     [rsp+140h+var_108], rax
0x180037d02  xor     eax, eax
0x180037d04  mov     [rsp+140h+var_100], al
0x180037d08  mov     [rsp+140h+var_FC], rax
0x180037d0d  mov     [rsp+140h+var_F4], al
0x180037d11  test    r15, r15
0x180037d14  jnz     loc_1800381F5
0x180037d1a  mov     r15, [rdi+88h]
0x180037d21  mov     rax, [r15+10h]
0x180037d25  mov     rbx, [rax+238h]
0x180037d2c  mov     rax, [rcx]
0x180037d2f  mov     rax, [rax+50h]
0x180037d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d38  xor     r9d, r9d; struct ITextRenderTarget *
0x180037d3b  xor     r8d, r8d; HDC
0x180037d3e  mov     rdx, rbx; struct IDpiAccessor *
0x180037d41  mov     cl, al; bool
0x180037d43  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x180037d48  mov     rdx, [rsp+140h+var_108]
0x180037d4d  xor     ebx, ebx
0x180037d4f  mov     [rbp+40h+var_C0], rax
0x180037d53  mov     r8, rax
0x180037d56  mov     [rbp+40h+var_B8], bl
0x180037d59  mov     [rbp+40h+var_B4], rbx
0x180037d5d  mov     [rbp+40h+var_AC], bl
0x180037d60  mov     rcx, [rax]
0x180037d63  mov     rax, [rcx+8]
0x180037d67  mov     rcx, r8
0x180037d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d6f  mov     al, [rsp+140h+var_100]
0x180037d73  mov     [rbp+40h+var_B8], al
0x180037d76  mov     eax, dword ptr [rsp+140h+var_FC]
0x180037d7a  mov     dword ptr [rbp+40h+var_B4], eax
0x180037d7d  mov     eax, dword ptr [rsp+140h+var_FC+4]
0x180037d81  mov     dword ptr [rbp+40h+var_B4+4], eax
0x180037d84  mov     al, [rsp+140h+var_F4]
0x180037d88  mov     [rbp+40h+var_AC], al
0x180037d8b  test    al, al
0x180037d8d  jnz     short loc_180037DB0
0x180037d8f  mov     rcx, [rbp+40h+var_C0]
0x180037d93  mov     rax, [rcx]
0x180037d96  mov     rax, [rax+18h]
0x180037d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037d9f  test    al, al
0x180037da1  jnz     short loc_180037DB0
0x180037da3  mov     rdx, [r15+58h]
0x180037da7  test    rdx, rdx
0x180037daa  jnz     loc_180038233
0x180037db0  mov     rbx, [r15+40h]
0x180037db4  test    rbx, rbx
0x180037db7  jnz     short loc_180037DC5
0x180037db9  lea     rax, [rbp+40h+var_80]
0x180037dbd  mov     [r15+40h], rax
0x180037dc1  lea     rbx, [rbp+40h+var_80]
0x180037dc5  inc     dword ptr [rbx]
0x180037dc7  xor     r15d, r15d
0x180037dca  inc     dword ptr [rbx+4]
0x180037dcd  mov     eax, [rbp+40h+arg_8]
0x180037dd0  mov     [rbx+48h], rsi
0x180037dd4  or      esi, 0FFFFFFFFh
0x180037dd7  mov     [rbx+40h], r15
0x180037ddb  mov     [rbx+38h], eax
0x180037dde  cmp     [rbp+40h+var_AC], r15b
0x180037de2  jnz     short loc_180037DF8
0x180037de4  mov     rcx, [rbp+40h+var_C0]
0x180037de8  mov     rax, [rcx]
0x180037deb  mov     rax, [rax+18h]
0x180037def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037df4  test    al, al
0x180037df6  jz      short loc_180037E0B
0x180037df8  lea     rcx, [rbx+8]; this
0x180037dfc  mov     r9d, esi; int
0x180037dff  mov     r8d, esi; int
0x180037e02  lea     rdx, [rbp+40h+var_C0]; struct CHDC *
0x180037e06  call    ?SetDC@CDevDesc@@QEAAHAEBVCHDC@@JJ@Z; CDevDesc::SetDC(CHDC const &,long,long)
0x180037e0b  lea     rcx, [rbp+40h+var_C0]; this
0x180037e0f  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x180037e14  mov     rbx, [rdi+100h]
0x180037e1b  test    rbx, rbx
0x180037e1e  jz      short loc_180037E2D
0x180037e20  mov     rbx, [rbx+50h]
0x180037e24  test    rbx, rbx
0x180037e27  jnz     loc_180038245
0x180037e2d  mov     rbx, r15
0x180037e30  mov     cl, [rdi+114h]
0x180037e36  lea     rdx, [rsp+140h+var_E0]; struct IDpiAccessor *
0x180037e3b  shr     cl, 6
0x180037e3e  xor     r9d, r9d; struct ITextRenderTarget *
0x180037e41  and     cl, 1; bool
0x180037e44  mov     r8, r14; HDC
0x180037e47  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x180037e4c  mov     [rbp+40h+var_A0], rax
0x180037e50  mov     [rbp+40h+var_98], r15b
0x180037e54  mov     [rbp+40h+var_94], r15
0x180037e58  mov     [rbp+40h+var_8C], r15b
0x180037e5c  test    rbx, rbx
0x180037e5f  jnz     loc_18003824D
0x180037e65  mov     rsi, [rdi+88h]
0x180037e6c  lea     rdx, [rbp+40h+var_A0]; struct CHDC *
0x180037e70  or      r8d, 0FFFFFFFFh; int
0x180037e74  mov     r9d, r8d; int
0x180037e77  mov     ebx, [rsi+34h]
0x180037e7a  lea     rcx, [rsi+10h]; this
0x180037e7e  mov     r14d, [rsi+38h]
0x180037e82  call    ?SetDC@CDevDesc@@QEAAHAEBVCHDC@@JJ@Z; CDevDesc::SetDC(CHDC const &,long,long)
0x180037e87  mov     rcx, rsi; this
0x180037e8a  call    ?SetDispResolution@CDisplay@@QEAAXXZ; CDisplay::SetDispResolution(void)
0x180037e8f  cmp     ebx, [rsi+34h]
0x180037e92  jnz     loc_18003809D
0x180037e98  cmp     r14d, [rsi+38h]
0x180037e9c  jnz     loc_18003809D
0x180037ea2  mov     rcx, [rdi+88h]
0x180037ea9  lea     rdx, [rsp+140h+var_E8]
0x180037eae  mov     [rsp+140h+var_120], rdx
0x180037eb3  lea     r9, [rsp+140h+var_10C]
0x180037eb8  mov     edx, [rbp+40h+arg_28]
0x180037ebb  lea     r8, [rsp+140h+var_110]
0x180037ec0  mov     rax, [rcx]
0x180037ec3  mov     rax, [rax+1C8h]
0x180037eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ecf  mov     rcx, [rdi+88h]
0x180037ed6  mov     ebx, eax
0x180037ed8  add     rcx, 10h; this
0x180037edc  call    ?ResetDCW@CDevDesc@@QEAAXXZ; CDevDesc::ResetDCW(void)
0x180037ee1  mov     rcx, [rdi+88h]; this
0x180037ee8  call    ?ReleaseDrawInfo@CDisplay@@QEAAXXZ; CDisplay::ReleaseDrawInfo(void)
0x180037eed  lea     rcx, [rbp+40h+var_A0]; this
0x180037ef1  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x180037ef6  lea     rcx, [rsp+140h+var_108]; this
0x180037efb  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x180037f00  lea     rsi, ??_7IDpiAccessor@@6B@; const IDpiAccessor::`vftable'
0x180037f07  lea     rcx, [rbp+40h+var_70]; this
0x180037f0b  mov     [rsp+140h+var_D0], rsi
0x180037f10  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x180037f15  test    ebx, ebx
0x180037f17  js      short loc_180037F49
0x180037f19  cmp     [rbp+40h+arg_0], r15d
0x180037f1d  jnz     loc_180038283
0x180037f23  mov     eax, [rsp+140h+var_10C]
0x180037f27  mov     r8d, [rsp+140h+var_110]
0x180037f2c  mov     rcx, [rbp+40h+arg_40]
0x180037f33  mov     [r13+0], r8d
0x180037f37  mov     [rcx], eax
0x180037f39  mov     rcx, [rbp+40h+arg_48]
0x180037f40  test    rcx, rcx
  ... truncated ...
```
