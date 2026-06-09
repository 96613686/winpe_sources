# CChildFrame::Create(ushort const *,ushort const *,ulong,tagRECT const &,CMDIFrameWnd *,CCreateContext *)

- ea: `0x1400abe90`
- end: `0x1400ac0fd`
- name: `?Create@CChildFrame@@UEAAHPEBG0KAEBUtagRECT@@PEAVCMDIFrameWnd@@PEAUCCreateContext@@@Z`
- size: `621`
- prototype: `__int64 __fastcall(CChildFrame *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const struct tagRECT *, struct CMDIFrameWnd *, struct CCreateContext *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400347fc`
- `0x140062455`
- `0x1400abe90`
- `0x1400e9dba`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `USER32!BringWindowToTop` at `0x1400ac07a`
- `USER32!BringWindowToTop` at `0x1400ac07a`
- `USER32!GetClientRect` at `0x1400abf3e`
- `USER32!GetClientRect` at `0x1400abf3e`
- `USER32!SendMessageW` at `0x1400ac03a`
- `USER32!SendMessageW` at `0x1400ac0bc`
- `USER32!SendMessageW` at `0x1400ac0d4`
- `USER32!SendMessageW` at `0x1400ac03a`
- `USER32!SendMessageW` at `0x1400ac0bc`
- `USER32!SendMessageW` at `0x1400ac0d4`
- `MFC42u!__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x1400abf8c`
- `MFC42u!__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x1400abf8c`
- `MFC42u!__imp_?AfxGetThread@@YAPEAVCWinThread@@XZ` at `0x1400abed4`
- `MFC42u!__imp_?AfxGetThread@@YAPEAVCWinThread@@XZ` at `0x1400abed4`
- `MFC42u!__imp_?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z` at `0x1400ac021`
- `MFC42u!__imp_?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z` at `0x1400ac021`
- `MFC42u!__imp_?AfxUnhookWindowCreate@@YAHXZ` at `0x1400ac043`
- `MFC42u!__imp_?AfxUnhookWindowCreate@@YAHXZ` at `0x1400ac043`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x1400ac0a3`
- `MFC42u!__imp_?ShowWindow@CWnd@@QEAAHH@Z` at `0x1400ac0a3`

## pseudocode

```c
__int64 __fastcall CChildFrame::Create(
        WPARAM *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        const struct tagRECT *a5,
        struct CMDIFrameWnd *a6,
        struct CCreateContext *a7)
{
  struct CMDIFrameWnd *v7; // rsi
  struct CWinThread *Thread; // rax
  int MinimumAllowedWidth; // eax
  int v14; // ebx
  LONG bottom; // eax
  LONG top; // ecx
  LPARAM v17; // rcx
  WPARAM v18; // rax
  HWND v20; // rbx
  int v21; // edx
  struct CCreateContext *v22; // [rsp+30h] [rbp-A1h] BYREF
  LPARAM v23; // [rsp+38h] [rbp-99h]
  __int64 v24; // [rsp+40h] [rbp-91h]
  __int64 v25; // [rsp+48h] [rbp-89h]
  int v26; // [rsp+50h] [rbp-81h]
  int v27; // [rsp+54h] [rbp-7Dh]
  LONG v28; // [rsp+58h] [rbp-79h]
  LONG left; // [rsp+5Ch] [rbp-75h]
  int v30; // [rsp+60h] [rbp-71h]
  const unsigned __int16 *v31; // [rsp+68h] [rbp-69h]
  const unsigned __int16 *v32; // [rsp+70h] [rbp-61h]
  LPARAM lParam[3]; // [rsp+80h] [rbp-51h] BYREF
  LONG v34; // [rsp+98h] [rbp-39h]
  LONG v35; // [rsp+9Ch] [rbp-35h]
  int v36; // [rsp+A0h] [rbp-31h]
  int v37; // [rsp+A4h] [rbp-2Dh]
  unsigned int v38; // [rsp+A8h] [rbp-29h]
  int v39; // [rsp+ACh] [rbp-25h]
  struct CCreateContext *v40; // [rsp+B0h] [rbp-21h]
  struct tagRECT Rect; // [rsp+B8h] [rbp-19h] BYREF

  v7 = a6;
  if ( !a6 )
  {
    Thread = AfxGetThread();
    if ( !Thread )
      return 0;
    v7 = (struct CMDIFrameWnd *)_RTDynamicCast_0(
                                  *((_QWORD *)Thread + 8),
                                  0,
                                  &CWnd `RTTI Type Descriptor',
                                  &CMDIFrameWnd `RTTI Type Descriptor',
                                  0);
    if ( !v7 )
      return 0;
  }
  memset_0(&v22, 0, 0x50u);
  v32 = a2;
  v31 = a3;
  v30 = a4;
  MinimumAllowedWidth = CAMCView::GetMinimumAllowedWidth();
  Rect = 0;
  v14 = MinimumAllowedWidth;
  GetClientRect(*((HWND *)v7 + 8), &Rect);
  left = a5->left;
  bottom = a5->bottom;
  top = a5->top;
  v28 = top;
  if ( 5 * (Rect.right - Rect.left) / 6 > v14 )
    v14 = 5 * (Rect.right - Rect.left) / 6;
  v26 = bottom - top;
  v27 = v14;
  v25 = *((_QWORD *)v7 + 8);
  v24 = 0;
  v17 = *((_QWORD *)AfxGetModuleState() + 2);
  v18 = *this;
  v23 = v17;
  v22 = a7;
  if ( !(*(unsigned int (__fastcall **)(WPARAM *, struct CCreateContext **))(v18 + 200))(this, &v22) )
  {
    (*(void (__fastcall **)(WPARAM *))(*this + 344))(this);
    return 0;
  }
  lParam[0] = (LPARAM)v32;
  lParam[1] = (LPARAM)v31;
  lParam[2] = v23;
  v34 = left;
  v35 = v28;
  v36 = v27;
  v37 = v26;
  v39 = 0;
  v38 = v30 & 0xEEFFFFFF;
  v40 = v22;
  AfxHookWindowCreate((struct CWnd *)this);
  v20 = (HWND)SendMessageW(*((HWND *)v7 + 42), 0x220u, 0, (LPARAM)lParam);
  if ( !AfxUnhookWindowCreate() )
    (*(void (__fastcall **)(WPARAM *))(*this + 344))(this);
  if ( !v20 )
    return 0;
  if ( (v30 & 0x10000000) != 0 )
  {
    BringWindowToTop(v20);
    if ( (v30 & 0x20000000) != 0 )
    {
      v21 = 2;
    }
    else
    {
      v21 = 3;
      if ( (v30 & 0x1000000) == 0 )
        v21 = 1;
    }
    CWnd::ShowWindow((CWnd *)this, v21);
    SendMessageW(*((HWND *)v7 + 42), 0x222u, this[8], 0);
    SendMessageW(*((HWND *)v7 + 42), 0x234u, 0, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x1400abe90  push    rbp
0x1400abe92  push    rbx
0x1400abe93  push    rsi
0x1400abe94  push    rdi
0x1400abe95  push    r12
0x1400abe97  push    r13
0x1400abe99  push    r14
0x1400abe9b  push    r15
0x1400abe9d  lea     rbp, [rsp-7]
0x1400abea2  sub     rsp, 0D8h
0x1400abea9  mov     rax, cs:__security_cookie
0x1400abeb0  xor     rax, rsp
0x1400abeb3  mov     [rbp+3Fh+var_48], rax
0x1400abeb7  mov     rsi, [rbp+3Fh+arg_28]
0x1400abebb  mov     r12d, r9d
0x1400abebe  mov     r14, [rbp+3Fh+arg_20]
0x1400abec2  mov     r15, r8
0x1400abec5  mov     r13, [rbp+3Fh+arg_30]
0x1400abec9  mov     rbx, rdx
0x1400abecc  mov     rdi, rcx
0x1400abecf  test    rsi, rsi
0x1400abed2  jnz     short loc_1400ABF0C
0x1400abed4  call    cs:__imp_?AfxGetThread@@YAPEAVCWinThread@@XZ; AfxGetThread(void)
0x1400abeda  test    rax, rax
0x1400abedd  jz      loc_1400ABFCD
0x1400abee3  mov     rcx, [rax+40h]
0x1400abee7  lea     r9, ??_R0?AVCMDIFrameWnd@@@8; CMDIFrameWnd `RTTI Type Descriptor'
0x1400abeee  lea     r8, ??_R0?AVCWnd@@@8; CWnd `RTTI Type Descriptor'
0x1400abef5  mov     [rsp+110h+var_F0], esi
0x1400abef9  xor     edx, edx
0x1400abefb  call    __RTDynamicCast_0
0x1400abf00  mov     rsi, rax
0x1400abf03  test    rax, rax
0x1400abf06  jz      loc_1400ABFCD
0x1400abf0c  xor     edx, edx; Val
0x1400abf0e  lea     rcx, [rsp+110h+var_E0]; void *
0x1400abf13  lea     r8d, [rdx+50h]; Size
0x1400abf17  call    memset_0
0x1400abf1c  mov     [rbp+3Fh+var_A0], rbx
0x1400abf20  mov     [rbp+3Fh+var_A8], r15
0x1400abf24  mov     [rbp+3Fh+var_B0], r12d
0x1400abf28  call    ?GetMinimumAllowedWidth@CAMCView@@SAHXZ; CAMCView::GetMinimumAllowedWidth(void)
0x1400abf2d  xorps   xmm0, xmm0
0x1400abf30  lea     rdx, [rbp+3Fh+Rect]; lpRect
0x1400abf34  movups  xmmword ptr [rbp+3Fh+Rect.left], xmm0
0x1400abf38  mov     rcx, [rsi+40h]; hWnd
0x1400abf3c  mov     ebx, eax
0x1400abf3e  call    cs:__imp_GetClientRect
0x1400abf44  mov     ecx, [rbp+3Fh+Rect.right]
0x1400abf47  mov     eax, 2AAAAAABh
0x1400abf4c  sub     ecx, [rbp+3Fh+Rect.left]
0x1400abf4f  lea     ecx, [rcx+rcx*4]
0x1400abf52  imul    ecx
0x1400abf54  mov     eax, [r14]
0x1400abf57  mov     [rbp+3Fh+var_B4], eax
0x1400abf5a  mov     ecx, edx
0x1400abf5c  mov     eax, [r14+0Ch]
0x1400abf60  shr     ecx, 1Fh
0x1400abf63  add     edx, ecx
0x1400abf65  mov     ecx, [r14+4]
0x1400abf69  cmp     edx, ebx
0x1400abf6b  mov     [rbp+3Fh+var_B8], ecx
0x1400abf6e  cmovg   ebx, edx
0x1400abf71  sub     eax, ecx
0x1400abf73  mov     [rsp+110h+var_C0], eax
0x1400abf77  mov     [rbp+3Fh+var_BC], ebx
0x1400abf7a  mov     rax, [rsi+40h]
0x1400abf7e  mov     [rsp+110h+var_C8], rax
0x1400abf83  mov     [rsp+110h+var_D0], 0
0x1400abf8c  call    cs:__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1400abf92  lea     rdx, [rsp+110h+var_E0]
0x1400abf97  mov     rcx, [rax+10h]
0x1400abf9b  mov     rax, [rdi]
0x1400abf9e  mov     [rsp+110h+var_D8], rcx
0x1400abfa3  mov     rcx, rdi
0x1400abfa6  mov     [rsp+110h+var_E0], r13
0x1400abfab  mov     rax, [rax+0C8h]
0x1400abfb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400abfb7  mov     rcx, rdi
0x1400abfba  test    eax, eax
0x1400abfbc  jnz     short loc_1400ABFD4
0x1400abfbe  mov     rax, [rdi]
0x1400abfc1  mov     rax, [rax+158h]
0x1400abfc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400abfcd  xor     eax, eax
0x1400abfcf  jmp     loc_1400AC0DD
0x1400abfd4  mov     rax, [rbp+3Fh+var_A0]
0x1400abfd8  mov     [rbp+3Fh+lParam], rax
0x1400abfdc  mov     rax, [rbp+3Fh+var_A8]
0x1400abfe0  mov     [rbp+3Fh+var_88], rax
0x1400abfe4  mov     rax, [rsp+110h+var_D8]
0x1400abfe9  mov     [rbp+3Fh+var_80], rax
0x1400abfed  mov     eax, [rbp+3Fh+var_B4]
0x1400abff0  mov     [rbp+3Fh+var_78], eax
0x1400abff3  mov     eax, [rbp+3Fh+var_B8]
0x1400abff6  mov     [rbp+3Fh+var_74], eax
0x1400abff9  mov     eax, [rbp+3Fh+var_BC]
0x1400abffc  mov     [rbp+3Fh+var_70], eax
0x1400abfff  mov     eax, [rsp+110h+var_C0]
0x1400ac003  mov     [rbp+3Fh+var_6C], eax
0x1400ac006  mov     eax, [rbp+3Fh+var_B0]
0x1400ac009  and     eax, 0EEFFFFFFh
0x1400ac00e  mov     [rbp+3Fh+var_64], 0
0x1400ac015  mov     [rbp+3Fh+var_68], eax
0x1400ac018  mov     rax, [rsp+110h+var_E0]
0x1400ac01d  mov     [rbp+3Fh+var_60], rax
0x1400ac021  call    cs:__imp_?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z; AfxHookWindowCreate(CWnd *)
0x1400ac027  mov     rcx, [rsi+150h]; hWnd
0x1400ac02e  lea     r9, [rbp+3Fh+lParam]; lParam
0x1400ac032  xor     r8d, r8d; wParam
0x1400ac035  mov     edx, 220h; Msg
0x1400ac03a  call    cs:__imp_SendMessageW
0x1400ac040  mov     rbx, rax
0x1400ac043  call    cs:__imp_?AfxUnhookWindowCreate@@YAHXZ; AfxUnhookWindowCreate(void)
0x1400ac049  test    eax, eax
0x1400ac04b  jnz     short loc_1400AC05F
0x1400ac04d  mov     rcx, [rdi]
0x1400ac050  mov     rax, [rcx+158h]
0x1400ac057  mov     rcx, rdi
0x1400ac05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ac05f  test    rbx, rbx
0x1400ac062  jz      loc_1400ABFCD
0x1400ac068  test    [rbp+3Fh+var_B0], 10000000h
0x1400ac06f  mov     r14d, 1
0x1400ac075  jz      short loc_1400AC0DA
0x1400ac077  mov     rcx, rbx; hWnd
0x1400ac07a  call    cs:__imp_BringWindowToTop
0x1400ac080  test    [rbp+3Fh+var_B0], 20000000h
0x1400ac087  jz      short loc_1400AC08F
0x1400ac089  lea     edx, [r14+1]
0x1400ac08d  jmp     short loc_1400AC0A0
0x1400ac08f  test    [rbp+3Fh+var_B0], 1000000h
0x1400ac096  mov     edx, 3
0x1400ac09b  jnz     short loc_1400AC0A0
0x1400ac09d  mov     edx, r14d
0x1400ac0a0  mov     rcx, rdi
0x1400ac0a3  call    cs:__imp_?ShowWindow@CWnd@@QEAAHH@Z; CWnd::ShowWindow(int)
0x1400ac0a9  mov     r8, [rdi+40h]; wParam
0x1400ac0ad  xor     r9d, r9d; lParam
0x1400ac0b0  mov     rcx, [rsi+150h]; hWnd
0x1400ac0b7  mov     edx, 222h; Msg
0x1400ac0bc  call    cs:__imp_SendMessageW
0x1400ac0c2  mov     rcx, [rsi+150h]; hWnd
0x1400ac0c9  xor     r9d, r9d; lParam
0x1400ac0cc  xor     r8d, r8d; wParam
0x1400ac0cf  mov     edx, 234h; Msg
0x1400ac0d4  call    cs:__imp_SendMessageW
0x1400ac0da  mov     eax, r14d
0x1400ac0dd  mov     rcx, [rbp+3Fh+var_48]
0x1400ac0e1  xor     rcx, rsp; StackCookie
0x1400ac0e4  call    __security_check_cookie
0x1400ac0e9  add     rsp, 0D8h
0x1400ac0f0  pop     r15
0x1400ac0f2  pop     r14
0x1400ac0f4  pop     r13
0x1400ac0f6  pop     r12
0x1400ac0f8  pop     rdi
0x1400ac0f9  pop     rsi
0x1400ac0fa  pop     rbx
0x1400ac0fb  pop     rbp
0x1400ac0fc  retn
```
