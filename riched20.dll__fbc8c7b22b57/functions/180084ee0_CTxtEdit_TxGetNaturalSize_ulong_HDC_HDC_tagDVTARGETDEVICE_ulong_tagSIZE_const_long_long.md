# CTxtEdit::TxGetNaturalSize(ulong,HDC__ *,HDC__ *,tagDVTARGETDEVICE *,ulong,tagSIZE const *,long *,long *)

- ea: `0x180084ee0`
- end: `0x180085193`
- name: `?TxGetNaturalSize@CTxtEdit@@UEAAJKPEAUHDC__@@0PEAUtagDVTARGETDEVICE@@KPEBUtagSIZE@@PEAJ3@Z`
- size: `691`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, HDC@<r8>, HDC@<r9>, struct tagDVTARGETDEVICE *, unsigned int, const struct tagSIZE *, int *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18002a6f0`
- `0x18002a790`
- `0x18003b500`
- `0x18003e42c`
- `0x1800412c0`
- `0x180042f94`
- `0x180058184`
- `0x18008455c`
- `0x180084ee0`
- `0x180095010`

## import_xrefs

- `GDI32!LPtoDP` at `0x18008501f`
- `GDI32!LPtoDP` at `0x18008501f`
- `GDI32!GetDeviceCaps` at `0x180085001`
- `GDI32!GetDeviceCaps` at `0x180085001`
- `GDI32!DeleteDC` at `0x180085154`
- `GDI32!DeleteDC` at `0x180085154`
- `GDI32!RestoreDC` at `0x18008510f`
- `GDI32!RestoreDC` at `0x18008510f`
- `GDI32!DPtoLP` at `0x180085133`
- `GDI32!DPtoLP` at `0x180085133`
- `GDI32!GetMapMode` at `0x180084fe8`
- `GDI32!GetMapMode` at `0x180084fe8`

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
0x180084ee0  mov     [rsp-8+arg_8], edx
0x180084ee4  push    rbp
0x180084ee5  push    rbx
0x180084ee6  push    rsi
0x180084ee7  push    rdi
0x180084ee8  push    r12
0x180084eea  push    r13
0x180084eec  push    r14
0x180084eee  push    r15
0x180084ef0  lea     rbp, [rsp-7]
0x180084ef5  sub     rsp, 0B8h
0x180084efc  mov     ebx, edx
0x180084efe  mov     r14, rcx
0x180084f01  mov     rdx, rcx; struct CTxtEdit *
0x180084f04  mov     r13, r9
0x180084f07  lea     rcx, [rbp+3Fh+var_A0]; this
0x180084f0b  mov     rdi, r8
0x180084f0e  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x180084f13  cmp     ebx, 1
0x180084f16  jz      short loc_180084F27
0x180084f18  cmp     ebx, 8
0x180084f1b  jz      short loc_180084F27
0x180084f1d  mov     ebx, 8004006Bh
0x180084f22  jmp     loc_180084FC0
0x180084f27  mov     rbx, [rbp+3Fh+arg_20]
0x180084f2b  test    r13, r13
0x180084f2e  jz      short loc_180084F39
0x180084f30  test    rbx, rbx
0x180084f33  jz      loc_180085170
0x180084f39  mov     eax, [rbp+3Fh+arg_28]
0x180084f3c  dec     eax
0x180084f3e  cmp     eax, 1
0x180084f41  ja      loc_180085170
0x180084f47  mov     r15, [rbp+3Fh+arg_38]
0x180084f4e  test    r15, r15
0x180084f51  jz      loc_180085170
0x180084f57  mov     r12, [rbp+3Fh+arg_40]
0x180084f5e  test    r12, r12
0x180084f61  jz      loc_180085170
0x180084f67  mov     rax, [rbp+3Fh+arg_30]
0x180084f6b  cmp     dword ptr [rax+4], 0
0x180084f6f  jnz     short loc_180084F84
0x180084f71  mov     dword ptr [r15], 0
0x180084f78  xor     ebx, ebx
0x180084f7a  mov     dword ptr [r12], 0
0x180084f82  jmp     short loc_180084FC0
0x180084f84  xor     esi, esi
0x180084f86  test    r13, r13
0x180084f89  jnz     short loc_180084FD3
0x180084f8b  test    rbx, rbx
0x180084f8e  jz      short loc_180084FD3
0x180084f90  movzx   r9d, word ptr [rbx+0Ah]
0x180084f95  movzx   r8d, word ptr [rbx+8]
0x180084f9a  add     r9, rbx; struct _devicemodeW *
0x180084f9d  movzx   edx, word ptr [rbx+6]
0x180084fa1  add     r8, rbx; unsigned __int16 *
0x180084fa4  movzx   ecx, word ptr [rbx+4]
0x180084fa8  add     rdx, rbx; unsigned __int16 *
0x180084fab  add     rcx, rbx; unsigned __int16 *
0x180084fae  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x180084fb3  mov     rsi, rax
0x180084fb6  test    rax, rax
0x180084fb9  jnz     short loc_180084FD0
0x180084fbb  mov     ebx, 80004005h
0x180084fc0  lea     rcx, [rbp+3Fh+var_A0]; this
0x180084fc4  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180084fc9  mov     eax, ebx
0x180084fcb  jmp     loc_18008517E
0x180084fd0  mov     r13, rax
0x180084fd3  xor     eax, eax
0x180084fd5  mov     rcx, rdi; hdc
0x180084fd8  mov     [rbp+3Fh+var_B0], eax
0x180084fdb  mov     eax, [r15]
0x180084fde  mov     [rbp+3Fh+pt.x], eax
0x180084fe1  mov     eax, [r12]
0x180084fe5  mov     [rbp+3Fh+pt.y], eax
0x180084fe8  call    cs:__imp_GetMapMode
0x180084fef  nop     dword ptr [rax+rax+00h]
0x180084ff4  cmp     eax, 1
0x180084ff7  jz      short loc_18008503A
0x180084ff9  mov     edx, 2; index
0x180084ffe  mov     rcx, rdi; hdc
0x180085001  call    cs:__imp_GetDeviceCaps
0x180085008  nop     dword ptr [rax+rax+00h]
0x18008500d  cmp     eax, 5
0x180085010  jz      short loc_18008503A
0x180085012  mov     r8d, 1; c
0x180085018  lea     rdx, [rbp+3Fh+pt]; lppt
0x18008501c  mov     rcx, rdi; hdc
0x18008501f  call    cs:__imp_LPtoDP
0x180085026  nop     dword ptr [rax+rax+00h]
0x18008502b  mov     rcx, rdi; hdc
0x18008502e  mov     [rbp+3Fh+var_B0], 1
0x180085035  call    ?ConvertDrawDCMapping@@YAXPEAUHDC__@@@Z; ConvertDrawDCMapping(HDC__ *)
0x18008503a  cmp     [rbp+3Fh+arg_28], 2
0x18008503e  mov     rcx, [r14+40h]
0x180085042  mov     rax, [rbp+3Fh+arg_30]
0x180085046  mov     eax, [rax+4]
0x180085049  mov     [rcx+4Ch], eax
0x18008504c  mov     rcx, [r14+40h]; this
0x180085050  jnz     short loc_180085069
0x180085052  mov     r8d, [rbp+3Fh+pt.x]; int
0x180085056  lea     r9, [rbp+3Fh+pt.y]; int *
0x18008505a  mov     rdx, rdi; HDC
0x18008505d  call    ?RoundToLine@CDisplay@@QEAAJPEAUHDC__@@JPEAJ@Z; CDisplay::RoundToLine(HDC__ *,long,long *)
0x180085062  mov     ebx, eax
0x180085064  jmp     loc_180085102
0x180085069  mov     r8d, [rbp+3Fh+arg_8]; unsigned int
0x18008506d  xor     edx, edx
0x18008506f  mov     [rsp+0F0h+var_C0], r13; HDC
0x180085074  or      r9d, 0FFFFFFFFh; int
0x180085078  mov     [rbp+3Fh+var_80], rdx
0x18008507c  mov     [rbp+3Fh+var_68], rdx
0x180085080  mov     [rbp+3Fh+var_70], rdx
0x180085084  mov     [rsp+0F0h+var_C8], rbx; struct tagDVTARGETDEVICE *
0x180085089  mov     [rsp+0F0h+var_D0], rdx; void *
0x18008508e  lea     rdx, [rbp+3Fh+var_80]; struct CDrawInfo *
0x180085092  mov     [rbp+3Fh+var_78], r14
0x180085096  call    ?SetDrawInfo@CDisplay@@QEAAXPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; CDisplay::SetDrawInfo(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *)
0x18008509b  mov     rcx, [r14+40h]
0x18008509f  or      r8d, 0FFFFFFFFh; int
0x1800850a3  add     rcx, 10h; this
0x1800850a7  mov     r9d, r8d; int
0x1800850aa  mov     rdx, rdi; HDC
0x1800850ad  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x1800850b2  mov     rcx, [r14+40h]
0x1800850b6  lea     rdx, [rbp+3Fh+pt.y]
0x1800850ba  mov     r9d, [rbp+3Fh+arg_28]
0x1800850be  mov     r8, r13
0x1800850c1  mov     [rsp+0F0h+var_C8], rdx
0x1800850c6  lea     rdx, [rbp+3Fh+pt]
0x1800850ca  mov     [rsp+0F0h+var_D0], rdx
0x1800850cf  mov     rdx, rdi
0x1800850d2  mov     rax, [rcx]
0x1800850d5  mov     rax, [rax+170h]
0x1800850dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850e1  mov     rcx, [r14+40h]
0x1800850e5  or      r9d, 0FFFFFFFFh; int
0x1800850e9  add     rcx, 10h; this
0x1800850ed  or      r8d, r9d; int
0x1800850f0  xor     edx, edx; HDC
0x1800850f2  mov     ebx, eax
0x1800850f4  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x1800850f9  mov     rcx, [r14+40h]; this
0x1800850fd  call    ?ReleaseDrawInfo@CDisplay@@QEAAXXZ; CDisplay::ReleaseDrawInfo(void)
0x180085102  mov     eax, [rbp+3Fh+var_B0]
0x180085105  test    eax, eax
0x180085107  jz      short loc_18008511E
0x180085109  or      edx, 0FFFFFFFFh; nSavedDC
0x18008510c  mov     rcx, rdi; hdc
0x18008510f  call    cs:__imp_RestoreDC
0x180085116  nop     dword ptr [rax+rax+00h]
0x18008511b  mov     eax, [rbp+3Fh+var_B0]
0x18008511e  test    ebx, ebx
0x180085120  js      short loc_18008514C
0x180085122  test    eax, eax
0x180085124  jz      short loc_18008513F
0x180085126  mov     r8d, 1; c
0x18008512c  lea     rdx, [rbp+3Fh+pt]; lppt
0x180085130  mov     rcx, rdi; hdc
0x180085133  call    cs:__imp_DPtoLP
0x18008513a  nop     dword ptr [rax+rax+00h]
0x18008513f  mov     eax, [rbp+3Fh+pt.x]
0x180085142  mov     [r15], eax
0x180085145  mov     eax, [rbp+3Fh+pt.y]
0x180085148  mov     [r12], eax
0x18008514c  test    rsi, rsi
0x18008514f  jz      short loc_180085160
0x180085151  mov     rcx, rsi; hdc
0x180085154  call    cs:__imp_DeleteDC
0x18008515b  nop     dword ptr [rax+rax+00h]
0x180085160  mov     rax, [r14+40h]
0x180085164  mov     dword ptr [rax+4Ch], 0
0x18008516b  jmp     loc_180084FC0
0x180085170  lea     rcx, [rbp+3Fh+var_A0]; this
0x180085174  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180085179  mov     eax, 80070057h
0x18008517e  add     rsp, 0B8h
0x180085185  pop     r15
0x180085187  pop     r14
0x180085189  pop     r13
0x18008518b  pop     r12
0x18008518d  pop     rdi
0x18008518e  pop     rsi
0x18008518f  pop     rbx
0x180085190  pop     rbp
0x180085191  retn
```
