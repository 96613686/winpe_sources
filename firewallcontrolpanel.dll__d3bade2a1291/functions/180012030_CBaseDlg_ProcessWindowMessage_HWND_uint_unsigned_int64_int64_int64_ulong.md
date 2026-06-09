# CBaseDlg::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x180012030`
- end: `0x180012267`
- name: `?ProcessWindowMessage@CBaseDlg@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `567`
- prototype: `int(CBaseDlg *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180012270`

## callees

- `0x180012030`
- `0x180012500`
- `0x180013d4c`
- `0x18001563c`
- `0x1800160d0`
- `0x180016214`
- `0x1800163b4`
- `0x180030e6e`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `USER32!EndDialog` at `0x1800121c7`
- `USER32!EndDialog` at `0x1800121c7`
- `USER32!BeginPaint` at `0x18001214d`
- `USER32!BeginPaint` at `0x18001214d`
- `USER32!EndPaint` at `0x180012170`
- `USER32!EndPaint` at `0x180012170`
- `GDI32!DeleteObject` at `0x1800120e6`
- `GDI32!DeleteObject` at `0x1800120f9`
- `GDI32!DeleteObject` at `0x18001210c`
- `GDI32!DeleteObject` at `0x1800120e6`
- `GDI32!DeleteObject` at `0x1800120f9`
- `GDI32!DeleteObject` at `0x18001210c`
- `UxTheme!CloseThemeData` at `0x18001211f`
- `UxTheme!CloseThemeData` at `0x18001211f`

## pseudocode

```c
_BOOL8 __fastcall CBaseDlg::ProcessWindowMessage(
        HWND *this,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        __int64 *a6,
        unsigned int a7)
{
  unsigned int v8; // edi
  __int64 inited; // rax
  __int64 v11; // rax
  bool v12; // zf
  INT_PTR v14; // rdx
  HWND v15; // rcx
  HWND v16; // rcx
  HWND v17; // rcx
  HWND v18; // rcx
  HDC v19; // rax
  int *v20; // [rsp+20h] [rbp-71h]
  int v21[4]; // [rsp+30h] [rbp-61h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-51h] BYREF

  v8 = a3;
  if ( !a7 )
  {
    if ( (_DWORD)a3 == 272 )
    {
      v21[0] = 1;
      inited = CBaseDlg::OnInitDialog((CBaseDlg *)this, a2, a3, a4, v21);
LABEL_4:
      *a6 = inited;
      if ( !v21[0] )
        goto LABEL_5;
      return 1;
    }
    v14 = 2;
    switch ( (_DWORD)a3 )
    {
      case 2:
        v15 = this[8];
        if ( v15 )
        {
          DeleteObject(v15);
          this[8] = 0;
        }
        v16 = this[9];
        if ( v16 )
        {
          DeleteObject(v16);
          this[9] = 0;
        }
        v17 = this[10];
        if ( v17 )
        {
          DeleteObject(v17);
          this[10] = 0;
        }
        v18 = this[12];
        if ( v18 )
        {
          CloseThemeData(v18);
          this[12] = 0;
        }
        goto LABEL_15;
      case 0xF:
        memset_0(&Paint, 0, sizeof(Paint));
        v19 = BeginPaint(this[1], &Paint);
        (*((void (__fastcall **)(HWND *, HDC))*this + 4))(this, v19);
        EndPaint(this[1], &Paint);
        *a6 = 1;
        break;
      case 0x138:
      case 0x135:
        *a6 = CBaseDlg::OnCtlColor((CBaseDlg *)this, 2u, a4, a5, v20);
        break;
      case 0x111:
        if ( (_WORD)a4 == 1 )
        {
          if ( WORD1(a4) )
            goto LABEL_5;
          v14 = 1;
        }
        else if ( (_DWORD)a4 != 2 )
        {
          goto LABEL_5;
        }
        EndDialog(this[1], v14);
        *a6 = 0;
        break;
      case 0x15:
        CWarningBaseDlg::UpdateBackground((CWarningBaseDlg *)this);
LABEL_15:
        *a6 = 0;
        goto LABEL_5;
      case 0x1A:
        if ( a4 == 67 )
          *((_DWORD *)this + 22) = IsUIHighContrast(0);
        *a6 = 1;
        goto LABEL_5;
      case 0x31A:
        v21[0] = 1;
        inited = CBaseDlg::OnThemeChange((CBaseDlg *)this, 2u, a3, a4, v21);
        goto LABEL_4;
      default:
LABEL_5:
        v21[0] = 1;
        v11 = ATL::CWindowImplRoot<ATL::CWindow>::ReflectNotifications(this, v8, a4, a5, v21);
        v12 = v21[0] == 0;
        *a6 = v11;
        return !v12;
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180012030  mov     [rsp-8+arg_8], rbx
0x180012035  push    rbp
0x180012036  push    rsi
0x180012037  push    rdi
0x180012038  push    r12
0x18001203a  push    r13
0x18001203c  push    r14
0x18001203e  push    r15
0x180012040  lea     rbp, [rsp-0Fh]
0x180012045  sub     rsp, 0A0h
0x18001204c  mov     rax, cs:__security_cookie
0x180012053  xor     rax, rsp
0x180012056  mov     [rbp+3Fh+var_40], rax
0x18001205a  mov     r15, [rbp+3Fh+arg_20]
0x18001205e  xor     r12d, r12d
0x180012061  mov     r14, r9
0x180012064  mov     rsi, [rbp+3Fh+arg_28]
0x180012068  mov     edi, r8d
0x18001206b  mov     rbx, rcx
0x18001206e  cmp     [rbp+3Fh+arg_30], r12d
0x180012072  jnz     loc_18001223E
0x180012078  lea     r13d, [r12+1]
0x18001207d  cmp     r8d, 110h
0x180012084  jnz     short loc_1800120D4
0x180012086  lea     rax, [rbp+3Fh+var_A0]
0x18001208a  mov     [rbp+3Fh+var_A0], r13d
0x18001208e  mov     [rsp+0D0h+var_B0], rax; int *
0x180012093  call    ?OnInitDialog@CBaseDlg@@QEAA_JI_K_JAEAH@Z; CBaseDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)
0x180012098  mov     [rsi], rax
0x18001209b  cmp     [rbp+3Fh+var_A0], r12d
0x18001209f  jnz     loc_180012179
0x1800120a5  lea     rax, [rbp+3Fh+var_A0]
0x1800120a9  mov     [rbp+3Fh+var_A0], r13d
0x1800120ad  mov     r9, r15
0x1800120b0  mov     [rsp+0D0h+var_B0], rax
0x1800120b5  mov     r8, r14
0x1800120b8  mov     edx, edi
0x1800120ba  mov     rcx, rbx
0x1800120bd  call    ?ReflectNotifications@?$CWindowImplRoot@VCWindow@ATL@@@ATL@@QEAA_JI_K_JAEAH@Z; ATL::CWindowImplRoot<ATL::CWindow>::ReflectNotifications(uint,unsigned __int64,__int64,int &)
0x1800120c2  cmp     [rbp+3Fh+var_A0], r12d
0x1800120c6  mov     [rsi], rax
0x1800120c9  mov     eax, r12d
0x1800120cc  setnz   al
0x1800120cf  jmp     loc_180012240
0x1800120d4  mov     edx, 2; unsigned int
0x1800120d9  cmp     edi, edx
0x1800120db  jnz     short loc_180012131
0x1800120dd  mov     rcx, [rcx+40h]; ho
0x1800120e1  test    rcx, rcx
0x1800120e4  jz      short loc_1800120F0
0x1800120e6  call    cs:__imp_DeleteObject
0x1800120ec  mov     [rbx+40h], r12
0x1800120f0  mov     rcx, [rbx+48h]; ho
0x1800120f4  test    rcx, rcx
0x1800120f7  jz      short loc_180012103
0x1800120f9  call    cs:__imp_DeleteObject
0x1800120ff  mov     [rbx+48h], r12
0x180012103  mov     rcx, [rbx+50h]; ho
0x180012107  test    rcx, rcx
0x18001210a  jz      short loc_180012116
0x18001210c  call    cs:__imp_DeleteObject
0x180012112  mov     [rbx+50h], r12
0x180012116  mov     rcx, [rbx+60h]; hTheme
0x18001211a  test    rcx, rcx
0x18001211d  jz      short loc_180012129
0x18001211f  call    cs:__imp_CloseThemeData
0x180012125  mov     [rbx+60h], r12
0x180012129  mov     [rsi], r12
0x18001212c  jmp     loc_1800120A5
0x180012131  cmp     edi, 0Fh
0x180012134  jnz     short loc_180012181
0x180012136  xor     edx, edx; Val
0x180012138  lea     r8d, [rdi+39h]; Size
0x18001213c  lea     rcx, [rbp+3Fh+Paint]; void *
0x180012140  call    memset_0
0x180012145  mov     rcx, [rbx+8]; hWnd
0x180012149  lea     rdx, [rbp+3Fh+Paint]; lpPaint
0x18001214d  call    cs:__imp_BeginPaint
0x180012153  mov     rcx, [rbx]
0x180012156  mov     rdx, rax
0x180012159  mov     r8, [rcx+20h]
0x18001215d  mov     rcx, rbx
0x180012160  mov     rax, r8
0x180012163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012168  mov     rcx, [rbx+8]; hWnd
0x18001216c  lea     rdx, [rbp+3Fh+Paint]; lpPaint
0x180012170  call    cs:__imp_EndPaint
0x180012176  mov     [rsi], r13
0x180012179  mov     eax, r13d
0x18001217c  jmp     loc_180012240
0x180012181  cmp     edi, 138h
0x180012187  jnz     short loc_180012199
0x180012189  mov     r9, r15; __int64
0x18001218c  mov     r8, r14; unsigned __int64
0x18001218f  call    ?OnCtlColor@CBaseDlg@@QEAA_JI_K_JAEAH@Z; CBaseDlg::OnCtlColor(uint,unsigned __int64,__int64,int &)
0x180012194  mov     [rsi], rax
0x180012197  jmp     short loc_180012179
0x180012199  cmp     edi, 135h
0x18001219f  jz      short loc_180012189
0x1800121a1  cmp     edi, 111h
0x1800121a7  jnz     short loc_1800121EF
0x1800121a9  cmp     r13w, r14w
0x1800121ad  jnz     short loc_1800121D2
0x1800121af  mov     rcx, r14
0x1800121b2  shr     rcx, 10h
0x1800121b6  cmp     r12w, cx
0x1800121ba  jnz     loc_1800120A5
0x1800121c0  mov     rdx, r13; nResult
0x1800121c3  mov     rcx, [rbx+8]; hDlg
0x1800121c7  call    cs:__imp_EndDialog
0x1800121cd  mov     [rsi], r12
0x1800121d0  jmp     short loc_180012179
0x1800121d2  cmp     dx, r14w
0x1800121d6  jnz     loc_1800120A5
0x1800121dc  mov     rcx, r14
0x1800121df  shr     rcx, 10h; this
0x1800121e3  cmp     r12w, cx
0x1800121e7  jnz     loc_1800120A5
0x1800121ed  jmp     short loc_1800121C3
0x1800121ef  cmp     edi, 15h
0x1800121f2  jnz     short loc_1800121FE
0x1800121f4  call    ?UpdateBackground@CWarningBaseDlg@@IEAAXXZ; CWarningBaseDlg::UpdateBackground(void)
0x1800121f9  jmp     loc_180012129
0x1800121fe  cmp     edi, 1Ah
0x180012201  jnz     short loc_18001221B
0x180012203  cmp     r14, 43h ; 'C'
0x180012207  jnz     short loc_180012213
0x180012209  xor     ecx, ecx; int *
0x18001220b  call    ?IsUIHighContrast@@YAHPEAH@Z; IsUIHighContrast(int *)
0x180012210  mov     [rbx+58h], eax
0x180012213  mov     [rsi], r13
0x180012216  jmp     loc_1800120A5
0x18001221b  cmp     edi, 31Ah
0x180012221  jnz     loc_1800120A5
0x180012227  lea     rax, [rbp+3Fh+var_A0]
0x18001222b  mov     [rbp+3Fh+var_A0], r13d
0x18001222f  mov     [rsp+0D0h+var_B0], rax; int *
0x180012234  call    ?OnThemeChange@CBaseDlg@@QEAA_JI_K_JAEAH@Z; CBaseDlg::OnThemeChange(uint,unsigned __int64,__int64,int &)
0x180012239  jmp     loc_180012098
0x18001223e  xor     eax, eax
0x180012240  mov     rcx, [rbp+3Fh+var_40]
0x180012244  xor     rcx, rsp; StackCookie
0x180012247  call    __security_check_cookie
0x18001224c  mov     rbx, [rsp+0D0h+arg_8]
0x180012254  add     rsp, 0A0h
0x18001225b  pop     r15
0x18001225d  pop     r14
0x18001225f  pop     r13
0x180012261  pop     r12
0x180012263  pop     rdi
0x180012264  pop     rsi
0x180012265  pop     rbp
0x180012266  retn
```
