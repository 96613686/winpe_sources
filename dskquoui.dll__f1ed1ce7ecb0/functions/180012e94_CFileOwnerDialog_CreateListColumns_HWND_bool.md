# CFileOwnerDialog::CreateListColumns(HWND__ *,bool)

- ea: `0x180012e94`
- end: `0x1800130a6`
- name: `?CreateListColumns@CFileOwnerDialog@@AEAAXPEAUHWND__@@_N@Z`
- size: `530`
- prototype: `void(CFileOwnerDialog *__hidden this, HWND, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180013d44`
- `0x180014604`

## callees

- `0x180001510`
- `0x180012e94`
- `0x180019d24`
- `0x180019ee0`
- `0x18001a15c`

## import_xrefs

- `USER32!GetClientRect` at `0x180012f70`
- `USER32!GetClientRect` at `0x180012f70`
- `USER32!SendMessageW` at `0x180012ed4`
- `USER32!SendMessageW` at `0x180012ee8`
- `USER32!SendMessageW` at `0x180012f06`
- `USER32!SendMessageW` at `0x180012f1a`
- `USER32!SendMessageW` at `0x180013056`
- `USER32!SendMessageW` at `0x180012ed4`
- `USER32!SendMessageW` at `0x180012ee8`
- `USER32!SendMessageW` at `0x180012f06`
- `USER32!SendMessageW` at `0x180012f1a`
- `USER32!SendMessageW` at `0x180013056`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFileOwnerDialog::CreateListColumns(HINSTANCE *this, HWND a2, unsigned __int8 a3)
{
  int v3; // r14d
  HWND v6; // rbx
  int v7; // ebx
  int v8; // ebx
  _BYTE v9[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-D8h]
  _BYTE v11[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v12; // [rsp+38h] [rbp-C8h]
  _BYTE v13[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v14; // [rsp+48h] [rbp-B8h]
  struct tagRECT Rect; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  __int64 v19; // [rsp+78h] [rbp-88h]
  __int128 v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+90h] [rbp-70h]
  __int64 v22; // [rsp+98h] [rbp-68h]
  int v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+A8h] [rbp-58h]
  int v25; // [rsp+B0h] [rbp-50h]
  int v26; // [rsp+B4h] [rbp-4Ch]
  __int128 v27; // [rsp+B8h] [rbp-48h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  __int64 v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  __int64 v31; // [rsp+E0h] [rbp-20h]
  int v32; // [rsp+E8h] [rbp-18h]
  int v33; // [rsp+ECh] [rbp-14h]
  __int128 v34; // [rsp+F0h] [rbp-10h]
  __int64 v35; // [rsp+100h] [rbp+0h]

  v3 = a3;
  SendMessageW(a2, 0x1009u, 0, 0);
  v6 = (HWND)SendMessageW(a2, 0x101Fu, 0, 0);
  if ( v6 )
  {
    while ( (int)SendMessageW(v6, 0x1200u, 0, 0) > 0 )
      SendMessageW(a2, 0x101Cu, 0, 0);
  }
  CString::CString((CString *)v13, *this, 40618);
  CString::CString((CString *)v11, *this, 40619);
  CString::CString((CString *)v9, *this, 40620);
  Rect = 0;
  GetClientRect(a2, &Rect);
  v7 = (Rect.right - Rect.left) / (v3 + 2);
  v16 = 15;
  v17 = v7;
  CString::CopyOnWrite((CString *)v13);
  v18 = *v14;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 15;
  v23 = v7;
  CString::CopyOnWrite((CString *)v11);
  v24 = *v12;
  v25 = 0;
  v26 = 1;
  v27 = 0;
  v28 = 0;
  v29 = 15;
  v30 = v7;
  CString::CopyOnWrite((CString *)v9);
  v31 = *v10;
  v32 = 0;
  v33 = 2;
  v34 = 0;
  v35 = 0;
  v8 = 0;
  do
  {
    SendMessageW(a2, 0x1061u, v8, (LPARAM)(&v16 + 7 * v8));
    ++v8;
  }
  while ( v8 < v3 + 2 );
  CString::~CString((CString *)v9);
  CString::~CString((CString *)v11);
  CString::~CString((CString *)v13);
}

```

## disassembly

```asm
0x180012e94  mov     [rsp-8+arg_10], rbx
0x180012e99  mov     [rsp-8+arg_18], rsi
0x180012e9e  push    rbp
0x180012e9f  push    rdi
0x180012ea0  push    r14
0x180012ea2  lea     rbp, [rsp-20h]
0x180012ea7  sub     rsp, 120h
0x180012eae  mov     rax, cs:__security_cookie
0x180012eb5  xor     rax, rsp
0x180012eb8  mov     [rbp+30h+var_20], rax
0x180012ebc  movzx   r14d, r8b
0x180012ec0  mov     rdi, rdx
0x180012ec3  mov     rsi, rcx
0x180012ec6  xor     r9d, r9d; lParam
0x180012ec9  xor     r8d, r8d; wParam
0x180012ecc  mov     edx, 1009h; Msg
0x180012ed1  mov     rcx, rdi; hWnd
0x180012ed4  call    cs:__imp_SendMessageW
0x180012eda  xor     r9d, r9d; lParam
0x180012edd  xor     r8d, r8d; wParam
0x180012ee0  mov     edx, 101Fh; Msg
0x180012ee5  mov     rcx, rdi; hWnd
0x180012ee8  call    cs:__imp_SendMessageW
0x180012eee  mov     rbx, rax
0x180012ef1  test    rax, rax
0x180012ef4  jz      short loc_180012F24
0x180012ef6  jmp     short loc_180012F0C
0x180012ef8  xor     r9d, r9d; lParam
0x180012efb  xor     r8d, r8d; wParam
0x180012efe  mov     edx, 101Ch; Msg
0x180012f03  mov     rcx, rdi; hWnd
0x180012f06  call    cs:__imp_SendMessageW
0x180012f0c  xor     r9d, r9d; lParam
0x180012f0f  xor     r8d, r8d; wParam
0x180012f12  mov     edx, 1200h; Msg
0x180012f17  mov     rcx, rbx; hWnd
0x180012f1a  call    cs:__imp_SendMessageW
0x180012f20  test    eax, eax
0x180012f22  jg      short loc_180012EF8
0x180012f24  mov     r8d, 9EAAh; int
0x180012f2a  mov     rdx, [rsi]; HINSTANCE
0x180012f2d  lea     rcx, [rsp+130h+var_F0]; this
0x180012f32  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x180012f37  nop
0x180012f38  mov     r8d, 9EABh; int
0x180012f3e  mov     rdx, [rsi]; HINSTANCE
0x180012f41  lea     rcx, [rsp+130h+var_100]; this
0x180012f46  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x180012f4b  nop
0x180012f4c  mov     r8d, 9EACh; int
0x180012f52  mov     rdx, [rsi]; HINSTANCE
0x180012f55  lea     rcx, [rsp+130h+var_110]; this
0x180012f5a  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x180012f5f  nop
0x180012f60  xorps   xmm0, xmm0
0x180012f63  movups  xmmword ptr [rsp+130h+Rect.left], xmm0
0x180012f68  lea     rdx, [rsp+130h+Rect]; lpRect
0x180012f6d  mov     rcx, rdi; hWnd
0x180012f70  call    cs:__imp_GetClientRect
0x180012f76  mov     eax, [rsp+130h+Rect.right]
0x180012f7a  sub     eax, [rsp+130h+Rect.left]
0x180012f7e  lea     ecx, [r14+2]
0x180012f82  cdq
0x180012f83  idiv    ecx
0x180012f85  mov     ebx, eax
0x180012f87  mov     [rsp+130h+var_D0], 0Fh
0x180012f90  mov     [rsp+130h+var_C8], eax
0x180012f94  lea     rcx, [rsp+130h+var_F0]; this
0x180012f99  call    ?CopyOnWrite@CString@@AEAAXXZ; CString::CopyOnWrite(void)
0x180012f9e  mov     rcx, [rsp+130h+var_E8]
0x180012fa3  mov     rdx, [rcx]
0x180012fa6  mov     [rsp+130h+var_C0], rdx
0x180012fab  mov     [rsp+130h+var_B8], 0
0x180012fb4  xorps   xmm0, xmm0
0x180012fb7  xor     eax, eax
0x180012fb9  movups  [rbp+30h+var_B0], xmm0
0x180012fbd  mov     [rbp+30h+var_A0], rax
0x180012fc1  mov     [rbp+30h+var_98], 0Fh
0x180012fc9  mov     [rbp+30h+var_90], ebx
0x180012fcc  lea     rcx, [rsp+130h+var_100]; this
0x180012fd1  call    ?CopyOnWrite@CString@@AEAAXXZ; CString::CopyOnWrite(void)
0x180012fd6  mov     rax, [rsp+130h+var_F8]
0x180012fdb  mov     rcx, [rax]
0x180012fde  mov     [rbp+30h+var_88], rcx
0x180012fe2  mov     [rbp+30h+var_80], 0
0x180012fe9  mov     [rbp+30h+var_7C], 1
0x180012ff0  xorps   xmm0, xmm0
0x180012ff3  xor     eax, eax
0x180012ff5  movups  [rbp+30h+var_78], xmm0
0x180012ff9  mov     [rbp+30h+var_68], rax
0x180012ffd  mov     [rbp+30h+var_60], 0Fh
0x180013005  mov     [rbp+30h+var_58], ebx
0x180013008  lea     rcx, [rsp+130h+var_110]; this
0x18001300d  call    ?CopyOnWrite@CString@@AEAAXXZ; CString::CopyOnWrite(void)
0x180013012  mov     rax, [rsp+130h+var_108]
0x180013017  mov     rcx, [rax]
0x18001301a  mov     [rbp+30h+var_50], rcx
0x18001301e  mov     [rbp+30h+var_48], 0
0x180013025  mov     [rbp+30h+var_44], 2
0x18001302c  xorps   xmm0, xmm0
0x18001302f  xor     eax, eax
0x180013031  movups  [rbp+30h+var_40], xmm0
0x180013035  mov     [rbp+30h+var_30], rax
0x180013039  lea     esi, [r14+2]
0x18001303d  xor     ebx, ebx
0x18001303f  movsxd  r8, ebx; wParam
0x180013042  imul    rax, r8, 38h ; '8'
0x180013046  lea     r9, [rsp+130h+var_D0]
0x18001304b  add     r9, rax; lParam
0x18001304e  mov     edx, 1061h; Msg
0x180013053  mov     rcx, rdi; hWnd
0x180013056  call    cs:__imp_SendMessageW
0x18001305c  inc     ebx
0x18001305e  cmp     ebx, esi
0x180013060  jl      short loc_18001303F
0x180013062  lea     rcx, [rsp+130h+var_110]; this
0x180013067  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001306c  nop
0x18001306d  lea     rcx, [rsp+130h+var_100]; this
0x180013072  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013077  nop
0x180013078  lea     rcx, [rsp+130h+var_F0]; this
0x18001307d  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013082  mov     rcx, [rbp+30h+var_20]
0x180013086  xor     rcx, rsp; StackCookie
0x180013089  call    __security_check_cookie
0x18001308e  lea     r11, [rsp+130h+var_10]
0x180013096  mov     rbx, [r11+30h]
0x18001309a  mov     rsi, [r11+38h]
0x18001309e  mov     rsp, r11
0x1800130a1  pop     r14
0x1800130a3  pop     rdi
0x1800130a4  pop     rbp
0x1800130a5  retn
```
