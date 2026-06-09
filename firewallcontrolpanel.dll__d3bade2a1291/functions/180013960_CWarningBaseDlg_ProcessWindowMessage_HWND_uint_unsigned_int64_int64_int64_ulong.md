# CWarningBaseDlg::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x180013960`
- end: `0x180013b97`
- name: `?ProcessWindowMessage@CWarningBaseDlg@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `567`
- prototype: `int(CWarningBaseDlg *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180013ba0`

## callees

- `0x180012500`
- `0x180012fc4`
- `0x1800130d0`
- `0x180013574`
- `0x180013960`
- `0x180013d4c`
- `0x18001563c`
- `0x180030e6e`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `USER32!EndDialog` at `0x180013af7`
- `USER32!EndDialog` at `0x180013af7`
- `USER32!BeginPaint` at `0x180013a7d`
- `USER32!BeginPaint` at `0x180013a7d`
- `USER32!EndPaint` at `0x180013aa0`
- `USER32!EndPaint` at `0x180013aa0`
- `GDI32!DeleteObject` at `0x180013a16`
- `GDI32!DeleteObject` at `0x180013a29`
- `GDI32!DeleteObject` at `0x180013a3c`
- `GDI32!DeleteObject` at `0x180013a16`
- `GDI32!DeleteObject` at `0x180013a29`
- `GDI32!DeleteObject` at `0x180013a3c`
- `UxTheme!CloseThemeData` at `0x180013a4f`
- `UxTheme!CloseThemeData` at `0x180013a4f`

## pseudocode

```c
_BOOL8 __fastcall CWarningBaseDlg::ProcessWindowMessage(
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
  struct tagPAINTSTRUCT Paint; // [rsp+40h] [rbp-51h] BYREF

  v8 = a3;
  if ( !a7 )
  {
    if ( (_DWORD)a3 == 272 )
    {
      v21[0] = 1;
      inited = CWarningBaseDlg::OnInitDialog((CWarningBaseDlg *)this, a2, a3, a4, v21);
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
        *a6 = CWarningBaseDlg::OnCtlColor((CWarningBaseDlg *)this, 2u, a4, a5, v20);
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
        inited = CWarningBaseDlg::OnThemeChange((CWarningBaseDlg *)this, 2u, a3, a4, v21);
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
0x180013960  mov     [rsp-8+arg_8], rbx
0x180013965  push    rbp
0x180013966  push    rsi
0x180013967  push    rdi
0x180013968  push    r12
0x18001396a  push    r13
0x18001396c  push    r14
0x18001396e  push    r15
0x180013970  lea     rbp, [rsp-0Fh]
0x180013975  sub     rsp, 0A0h
0x18001397c  mov     rax, cs:__security_cookie
0x180013983  xor     rax, rsp
0x180013986  mov     [rbp+3Fh+var_40], rax
0x18001398a  mov     r15, [rbp+3Fh+arg_20]
0x18001398e  xor     r12d, r12d
0x180013991  mov     r14, r9
0x180013994  mov     rsi, [rbp+3Fh+arg_28]
0x180013998  mov     edi, r8d
0x18001399b  mov     rbx, rcx
0x18001399e  cmp     [rbp+3Fh+arg_30], r12d
0x1800139a2  jnz     loc_180013B6E
0x1800139a8  lea     r13d, [r12+1]
0x1800139ad  cmp     r8d, 110h
0x1800139b4  jnz     short loc_180013A04
0x1800139b6  lea     rax, [rbp+3Fh+var_A0]
0x1800139ba  mov     [rbp+3Fh+var_A0], r13d
0x1800139be  mov     [rsp+0D0h+var_B0], rax; int *
0x1800139c3  call    ?OnInitDialog@CWarningBaseDlg@@QEAA_JI_K_JAEAH@Z; CWarningBaseDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)
0x1800139c8  mov     [rsi], rax
0x1800139cb  cmp     [rbp+3Fh+var_A0], r12d
0x1800139cf  jnz     loc_180013AA9
0x1800139d5  lea     rax, [rbp+3Fh+var_A0]
0x1800139d9  mov     [rbp+3Fh+var_A0], r13d
0x1800139dd  mov     r9, r15
0x1800139e0  mov     [rsp+0D0h+var_B0], rax
0x1800139e5  mov     r8, r14
0x1800139e8  mov     edx, edi
0x1800139ea  mov     rcx, rbx
0x1800139ed  call    ?ReflectNotifications@?$CWindowImplRoot@VCWindow@ATL@@@ATL@@QEAA_JI_K_JAEAH@Z; ATL::CWindowImplRoot<ATL::CWindow>::ReflectNotifications(uint,unsigned __int64,__int64,int &)
0x1800139f2  cmp     [rbp+3Fh+var_A0], r12d
0x1800139f6  mov     [rsi], rax
0x1800139f9  mov     eax, r12d
0x1800139fc  setnz   al
0x1800139ff  jmp     loc_180013B70
0x180013a04  mov     edx, 2; unsigned int
0x180013a09  cmp     edi, edx
0x180013a0b  jnz     short loc_180013A61
0x180013a0d  mov     rcx, [rcx+40h]; ho
0x180013a11  test    rcx, rcx
0x180013a14  jz      short loc_180013A20
0x180013a16  call    cs:__imp_DeleteObject
0x180013a1c  mov     [rbx+40h], r12
0x180013a20  mov     rcx, [rbx+48h]; ho
0x180013a24  test    rcx, rcx
0x180013a27  jz      short loc_180013A33
0x180013a29  call    cs:__imp_DeleteObject
0x180013a2f  mov     [rbx+48h], r12
0x180013a33  mov     rcx, [rbx+50h]; ho
0x180013a37  test    rcx, rcx
0x180013a3a  jz      short loc_180013A46
0x180013a3c  call    cs:__imp_DeleteObject
0x180013a42  mov     [rbx+50h], r12
0x180013a46  mov     rcx, [rbx+60h]; hTheme
0x180013a4a  test    rcx, rcx
0x180013a4d  jz      short loc_180013A59
0x180013a4f  call    cs:__imp_CloseThemeData
0x180013a55  mov     [rbx+60h], r12
0x180013a59  mov     [rsi], r12
0x180013a5c  jmp     loc_1800139D5
0x180013a61  cmp     edi, 0Fh
0x180013a64  jnz     short loc_180013AB1
0x180013a66  xor     edx, edx; Val
0x180013a68  lea     r8d, [rdi+39h]; Size
0x180013a6c  lea     rcx, [rbp+3Fh+Paint]; void *
0x180013a70  call    memset_0
0x180013a75  mov     rcx, [rbx+8]; hWnd
0x180013a79  lea     rdx, [rbp+3Fh+Paint]; lpPaint
0x180013a7d  call    cs:__imp_BeginPaint
0x180013a83  mov     rcx, [rbx]
0x180013a86  mov     rdx, rax
0x180013a89  mov     r8, [rcx+20h]
0x180013a8d  mov     rcx, rbx
0x180013a90  mov     rax, r8
0x180013a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a98  mov     rcx, [rbx+8]; hWnd
0x180013a9c  lea     rdx, [rbp+3Fh+Paint]; lpPaint
0x180013aa0  call    cs:__imp_EndPaint
0x180013aa6  mov     [rsi], r13
0x180013aa9  mov     eax, r13d
0x180013aac  jmp     loc_180013B70
0x180013ab1  cmp     edi, 138h
0x180013ab7  jnz     short loc_180013AC9
0x180013ab9  mov     r9, r15; __int64
0x180013abc  mov     r8, r14; unsigned __int64
0x180013abf  call    ?OnCtlColor@CWarningBaseDlg@@QEAA_JI_K_JAEAH@Z; CWarningBaseDlg::OnCtlColor(uint,unsigned __int64,__int64,int &)
0x180013ac4  mov     [rsi], rax
0x180013ac7  jmp     short loc_180013AA9
0x180013ac9  cmp     edi, 135h
0x180013acf  jz      short loc_180013AB9
0x180013ad1  cmp     edi, 111h
0x180013ad7  jnz     short loc_180013B1F
0x180013ad9  cmp     r13w, r14w
0x180013add  jnz     short loc_180013B02
0x180013adf  mov     rcx, r14
0x180013ae2  shr     rcx, 10h
0x180013ae6  cmp     r12w, cx
0x180013aea  jnz     loc_1800139D5
0x180013af0  mov     rdx, r13; nResult
0x180013af3  mov     rcx, [rbx+8]; hDlg
0x180013af7  call    cs:__imp_EndDialog
0x180013afd  mov     [rsi], r12
0x180013b00  jmp     short loc_180013AA9
0x180013b02  cmp     dx, r14w
0x180013b06  jnz     loc_1800139D5
0x180013b0c  mov     rcx, r14
0x180013b0f  shr     rcx, 10h; this
0x180013b13  cmp     r12w, cx
0x180013b17  jnz     loc_1800139D5
0x180013b1d  jmp     short loc_180013AF3
0x180013b1f  cmp     edi, 15h
0x180013b22  jnz     short loc_180013B2E
0x180013b24  call    ?UpdateBackground@CWarningBaseDlg@@IEAAXXZ; CWarningBaseDlg::UpdateBackground(void)
0x180013b29  jmp     loc_180013A59
0x180013b2e  cmp     edi, 1Ah
0x180013b31  jnz     short loc_180013B4B
0x180013b33  cmp     r14, 43h ; 'C'
0x180013b37  jnz     short loc_180013B43
0x180013b39  xor     ecx, ecx; int *
0x180013b3b  call    ?IsUIHighContrast@@YAHPEAH@Z; IsUIHighContrast(int *)
0x180013b40  mov     [rbx+58h], eax
0x180013b43  mov     [rsi], r13
0x180013b46  jmp     loc_1800139D5
0x180013b4b  cmp     edi, 31Ah
0x180013b51  jnz     loc_1800139D5
0x180013b57  lea     rax, [rbp+3Fh+var_A0]
0x180013b5b  mov     [rbp+3Fh+var_A0], r13d
0x180013b5f  mov     [rsp+0D0h+var_B0], rax; int *
0x180013b64  call    ?OnThemeChange@CWarningBaseDlg@@QEAA_JI_K_JAEAH@Z; CWarningBaseDlg::OnThemeChange(uint,unsigned __int64,__int64,int &)
0x180013b69  jmp     loc_1800139C8
0x180013b6e  xor     eax, eax
0x180013b70  mov     rcx, [rbp+3Fh+var_40]
0x180013b74  xor     rcx, rsp; StackCookie
0x180013b77  call    __security_check_cookie
0x180013b7c  mov     rbx, [rsp+0D0h+arg_8]
0x180013b84  add     rsp, 0A0h
0x180013b8b  pop     r15
0x180013b8d  pop     r14
0x180013b8f  pop     r13
0x180013b91  pop     r12
0x180013b93  pop     rdi
0x180013b94  pop     rsi
0x180013b95  pop     rbp
0x180013b96  retn
```
