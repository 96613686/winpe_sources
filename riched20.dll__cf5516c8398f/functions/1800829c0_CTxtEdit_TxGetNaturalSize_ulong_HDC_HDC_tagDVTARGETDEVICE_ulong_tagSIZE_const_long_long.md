# CTxtEdit::TxGetNaturalSize(ulong,HDC__ *,HDC__ *,tagDVTARGETDEVICE *,ulong,tagSIZE const *,long *,long *)

- ea: `0x1800829c0`
- end: `0x180082c4e`
- name: `?TxGetNaturalSize@CTxtEdit@@UEAAJKPEAUHDC__@@0PEAUtagDVTARGETDEVICE@@KPEBUtagSIZE@@PEAJ3@Z`
- size: `654`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, HDC@<r8>, HDC@<r9>, struct tagDVTARGETDEVICE *, unsigned int, const struct tagSIZE *, int *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18002fb90`
- `0x18002fc30`
- `0x18003a4d0`
- `0x18003d61c`
- `0x180040904`
- `0x1800420a4`
- `0x180056bf0`
- `0x18008209c`
- `0x1800829c0`
- `0x180092010`

## import_xrefs

- `GDI32!LPtoDP` at `0x180082af3`
- `GDI32!LPtoDP` at `0x180082af3`
- `GDI32!GetDeviceCaps` at `0x180082adb`
- `GDI32!GetDeviceCaps` at `0x180082adb`
- `GDI32!DeleteDC` at `0x180082c16`
- `GDI32!DeleteDC` at `0x180082c16`
- `GDI32!RestoreDC` at `0x180082bdd`
- `GDI32!RestoreDC` at `0x180082bdd`
- `GDI32!DPtoLP` at `0x180082bfb`
- `GDI32!DPtoLP` at `0x180082bfb`
- `GDI32!GetMapMode` at `0x180082ac8`
- `GDI32!GetMapMode` at `0x180082ac8`

## pseudocode

```c
__int64 __fastcall CTxtEdit::TxGetNaturalSize(
        CDisplay **this,
        unsigned int a2,
        HDC a3,
        HDC a4,
        struct tagDVTARGETDEVICE *a5,
        unsigned int a6,
        const struct tagSIZE *a7,
        int *a8,
        int *a9)
{
  int v13; // ebx
  HDC v14; // rsi
  HDC IC; // rax
  CDisplay *v17; // rcx
  int v18; // eax
  int v19; // [rsp+40h] [rbp-71h]
  struct tagPOINT pt; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-61h] BYREF
  _QWORD v22[16]; // [rsp+70h] [rbp-41h] BYREF

  CCallMgr::CCallMgr((CCallMgr *)v21, (struct CTxtEdit *)this);
  if ( a2 != 1 && a2 != 8 )
  {
    v13 = -2147221397;
    goto LABEL_15;
  }
  if ( (!a4 || a5) && a6 - 1 <= 1 && a8 && a9 )
  {
    if ( a7->cy )
    {
      v14 = 0;
      if ( !a4 && a5 )
      {
        IC = CW32System::CreateIC(
               (unsigned __int16 *)((char *)a5 + a5->tdDriverNameOffset),
               (unsigned __int16 *)((char *)a5 + a5->tdDeviceNameOffset),
               (unsigned __int16 *)((char *)a5 + a5->tdPortNameOffset),
               (const struct _devicemodeW *)((char *)a5 + a5->tdExtDevmodeOffset));
        v14 = IC;
        if ( !IC )
        {
          v13 = -2147467259;
          goto LABEL_15;
        }
        a4 = IC;
      }
      v19 = 0;
      pt.x = *a8;
      pt.y = *a9;
      if ( GetMapMode(a3) != 1 && GetDeviceCaps(a3, 2) != 5 )
      {
        LPtoDP(a3, &pt, 1);
        v19 = 1;
        ConvertDrawDCMapping(a3);
      }
      *((_DWORD *)this[8] + 19) = a7->cy;
      v17 = this[8];
      if ( a6 == 2 )
      {
        v13 = CDisplay::RoundToLine(v17, a3, pt.x, &pt.y);
      }
      else
      {
        v22[0] = 0;
        v22[3] = 0;
        v22[2] = 0;
        v22[1] = this;
        CDisplay::SetDrawInfo(v17, (struct CDrawInfo *)v22, a2, -1, 0, a5, a4);
        CDevDesc::SetDC((CDisplay *)((char *)this[8] + 16), a3, -1, -1);
        v13 = (*(__int64 (__fastcall **)(CDisplay *, HDC, HDC, _QWORD, struct tagPOINT *, LONG *))(*(_QWORD *)this[8]
                                                                                                 + 368LL))(
                this[8],
                a3,
                a4,
                a6,
                &pt,
                &pt.y);
        CDevDesc::SetDC((CDisplay *)((char *)this[8] + 16), 0, -1, -1);
        CDisplay::ReleaseDrawInfo(this[8]);
      }
      v18 = v19;
      if ( v19 )
      {
        RestoreDC(a3, -1);
        v18 = v19;
      }
      if ( v13 >= 0 )
      {
        if ( v18 )
          DPtoLP(a3, &pt, 1);
        *a8 = pt.x;
        *a9 = pt.y;
      }
      if ( v14 )
        DeleteDC(v14);
      *((_DWORD *)this[8] + 19) = 0;
      goto LABEL_15;
    }
    *a8 = 0;
    v13 = 0;
    *a9 = 0;
LABEL_15:
    CCallMgr::~CCallMgr((CCallMgr *)v21);
    return (unsigned int)v13;
  }
  CCallMgr::~CCallMgr((CCallMgr *)v21);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800829c0  mov     [rsp-8+arg_8], edx
0x1800829c4  push    rbp
0x1800829c5  push    rbx
0x1800829c6  push    rsi
0x1800829c7  push    rdi
0x1800829c8  push    r12
0x1800829ca  push    r13
0x1800829cc  push    r14
0x1800829ce  push    r15
0x1800829d0  lea     rbp, [rsp-7]
0x1800829d5  sub     rsp, 0B8h
0x1800829dc  mov     ebx, edx
0x1800829de  mov     r14, rcx
0x1800829e1  mov     rdx, rcx; struct CTxtEdit *
0x1800829e4  mov     r13, r9
0x1800829e7  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800829eb  mov     rdi, r8
0x1800829ee  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x1800829f3  cmp     ebx, 1
0x1800829f6  jz      short loc_180082A07
0x1800829f8  cmp     ebx, 8
0x1800829fb  jz      short loc_180082A07
0x1800829fd  mov     ebx, 8004006Bh
0x180082a02  jmp     loc_180082AA0
0x180082a07  mov     rbx, [rbp+3Fh+arg_20]
0x180082a0b  test    r13, r13
0x180082a0e  jz      short loc_180082A19
0x180082a10  test    rbx, rbx
0x180082a13  jz      loc_180082C2C
0x180082a19  mov     eax, [rbp+3Fh+arg_28]
0x180082a1c  dec     eax
0x180082a1e  cmp     eax, 1
0x180082a21  ja      loc_180082C2C
0x180082a27  mov     r15, [rbp+3Fh+arg_38]
0x180082a2e  test    r15, r15
0x180082a31  jz      loc_180082C2C
0x180082a37  mov     r12, [rbp+3Fh+arg_40]
0x180082a3e  test    r12, r12
0x180082a41  jz      loc_180082C2C
0x180082a47  mov     rax, [rbp+3Fh+arg_30]
0x180082a4b  cmp     dword ptr [rax+4], 0
0x180082a4f  jnz     short loc_180082A64
0x180082a51  mov     dword ptr [r15], 0
0x180082a58  xor     ebx, ebx
0x180082a5a  mov     dword ptr [r12], 0
0x180082a62  jmp     short loc_180082AA0
0x180082a64  xor     esi, esi
0x180082a66  test    r13, r13
0x180082a69  jnz     short loc_180082AB3
0x180082a6b  test    rbx, rbx
0x180082a6e  jz      short loc_180082AB3
0x180082a70  movzx   r9d, word ptr [rbx+0Ah]
0x180082a75  movzx   r8d, word ptr [rbx+8]
0x180082a7a  add     r9, rbx; struct _devicemodeW *
0x180082a7d  movzx   edx, word ptr [rbx+6]
0x180082a81  add     r8, rbx; unsigned __int16 *
0x180082a84  movzx   ecx, word ptr [rbx+4]
0x180082a88  add     rdx, rbx; unsigned __int16 *
0x180082a8b  add     rcx, rbx; unsigned __int16 *
0x180082a8e  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x180082a93  mov     rsi, rax
0x180082a96  test    rax, rax
0x180082a99  jnz     short loc_180082AB0
0x180082a9b  mov     ebx, 80004005h
0x180082aa0  lea     rcx, [rbp+3Fh+var_A0]; this
0x180082aa4  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180082aa9  mov     eax, ebx
0x180082aab  jmp     loc_180082C3A
0x180082ab0  mov     r13, rax
0x180082ab3  xor     eax, eax
0x180082ab5  mov     rcx, rdi; hdc
0x180082ab8  mov     [rbp+3Fh+var_B0], eax
0x180082abb  mov     eax, [r15]
0x180082abe  mov     [rbp+3Fh+pt.x], eax
0x180082ac1  mov     eax, [r12]
0x180082ac5  mov     [rbp+3Fh+pt.y], eax
0x180082ac8  call    cs:__imp_GetMapMode
0x180082ace  cmp     eax, 1
0x180082ad1  jz      short loc_180082B08
0x180082ad3  mov     edx, 2; index
0x180082ad8  mov     rcx, rdi; hdc
0x180082adb  call    cs:__imp_GetDeviceCaps
0x180082ae1  cmp     eax, 5
0x180082ae4  jz      short loc_180082B08
0x180082ae6  mov     r8d, 1; c
0x180082aec  lea     rdx, [rbp+3Fh+pt]; lppt
0x180082af0  mov     rcx, rdi; hdc
0x180082af3  call    cs:__imp_LPtoDP
0x180082af9  mov     rcx, rdi; hdc
0x180082afc  mov     [rbp+3Fh+var_B0], 1
0x180082b03  call    ?ConvertDrawDCMapping@@YAXPEAUHDC__@@@Z; ConvertDrawDCMapping(HDC__ *)
0x180082b08  cmp     [rbp+3Fh+arg_28], 2
0x180082b0c  mov     rcx, [r14+40h]
0x180082b10  mov     rax, [rbp+3Fh+arg_30]
0x180082b14  mov     eax, [rax+4]
0x180082b17  mov     [rcx+4Ch], eax
0x180082b1a  mov     rcx, [r14+40h]; this
0x180082b1e  jnz     short loc_180082B37
0x180082b20  mov     r8d, [rbp+3Fh+pt.x]; int
0x180082b24  lea     r9, [rbp+3Fh+pt.y]; int *
0x180082b28  mov     rdx, rdi; HDC
0x180082b2b  call    ?RoundToLine@CDisplay@@QEAAJPEAUHDC__@@JPEAJ@Z; CDisplay::RoundToLine(HDC__ *,long,long *)
0x180082b30  mov     ebx, eax
0x180082b32  jmp     loc_180082BD0
0x180082b37  mov     r8d, [rbp+3Fh+arg_8]; unsigned int
0x180082b3b  xor     edx, edx
0x180082b3d  mov     [rsp+0F0h+var_C0], r13; HDC
0x180082b42  or      r9d, 0FFFFFFFFh; int
0x180082b46  mov     [rbp+3Fh+var_80], rdx
0x180082b4a  mov     [rbp+3Fh+var_68], rdx
0x180082b4e  mov     [rbp+3Fh+var_70], rdx
0x180082b52  mov     [rsp+0F0h+var_C8], rbx; struct tagDVTARGETDEVICE *
0x180082b57  mov     [rsp+0F0h+var_D0], rdx; void *
0x180082b5c  lea     rdx, [rbp+3Fh+var_80]; struct CDrawInfo *
0x180082b60  mov     [rbp+3Fh+var_78], r14
0x180082b64  call    ?SetDrawInfo@CDisplay@@QEAAXPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; CDisplay::SetDrawInfo(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *)
0x180082b69  mov     rcx, [r14+40h]
0x180082b6d  or      r8d, 0FFFFFFFFh; int
0x180082b71  add     rcx, 10h; this
0x180082b75  mov     r9d, r8d; int
0x180082b78  mov     rdx, rdi; HDC
0x180082b7b  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x180082b80  mov     rcx, [r14+40h]
0x180082b84  lea     rdx, [rbp+3Fh+pt.y]
0x180082b88  mov     r9d, [rbp+3Fh+arg_28]
0x180082b8c  mov     r8, r13
0x180082b8f  mov     [rsp+0F0h+var_C8], rdx
0x180082b94  lea     rdx, [rbp+3Fh+pt]
0x180082b98  mov     [rsp+0F0h+var_D0], rdx
0x180082b9d  mov     rdx, rdi
0x180082ba0  mov     rax, [rcx]
0x180082ba3  mov     rax, [rax+170h]
0x180082baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082baf  mov     rcx, [r14+40h]
0x180082bb3  or      r9d, 0FFFFFFFFh; int
0x180082bb7  add     rcx, 10h; this
0x180082bbb  or      r8d, r9d; int
0x180082bbe  xor     edx, edx; HDC
0x180082bc0  mov     ebx, eax
0x180082bc2  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x180082bc7  mov     rcx, [r14+40h]; this
0x180082bcb  call    ?ReleaseDrawInfo@CDisplay@@QEAAXXZ; CDisplay::ReleaseDrawInfo(void)
0x180082bd0  mov     eax, [rbp+3Fh+var_B0]
0x180082bd3  test    eax, eax
0x180082bd5  jz      short loc_180082BE6
0x180082bd7  or      edx, 0FFFFFFFFh; nSavedDC
0x180082bda  mov     rcx, rdi; hdc
0x180082bdd  call    cs:__imp_RestoreDC
0x180082be3  mov     eax, [rbp+3Fh+var_B0]
0x180082be6  test    ebx, ebx
0x180082be8  js      short loc_180082C0E
0x180082bea  test    eax, eax
0x180082bec  jz      short loc_180082C01
0x180082bee  mov     r8d, 1; c
0x180082bf4  lea     rdx, [rbp+3Fh+pt]; lppt
0x180082bf8  mov     rcx, rdi; hdc
0x180082bfb  call    cs:__imp_DPtoLP
0x180082c01  mov     eax, [rbp+3Fh+pt.x]
0x180082c04  mov     [r15], eax
0x180082c07  mov     eax, [rbp+3Fh+pt.y]
0x180082c0a  mov     [r12], eax
0x180082c0e  test    rsi, rsi
0x180082c11  jz      short loc_180082C1C
0x180082c13  mov     rcx, rsi; hdc
0x180082c16  call    cs:__imp_DeleteDC
0x180082c1c  mov     rax, [r14+40h]
0x180082c20  mov     dword ptr [rax+4Ch], 0
0x180082c27  jmp     loc_180082AA0
0x180082c2c  lea     rcx, [rbp+3Fh+var_A0]; this
0x180082c30  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180082c35  mov     eax, 80070057h
0x180082c3a  add     rsp, 0B8h
0x180082c41  pop     r15
0x180082c43  pop     r14
0x180082c45  pop     r13
0x180082c47  pop     r12
0x180082c49  pop     rdi
0x180082c4a  pop     rsi
0x180082c4b  pop     rbx
0x180082c4c  pop     rbp
0x180082c4d  retn
```
