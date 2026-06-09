# CFileDialogEx::DoModal(void)

- ea: `0x1400b5c10`
- end: `0x1400b5e55`
- name: `?DoModal@CFileDialogEx@@UEAA_JXZ`
- size: `581`
- prototype: `__int64 __fastcall(CFileDialogEx *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14005af30`
- `0x14008ecfc`

## callees

- `0x140062455`
- `0x14006623c`
- `0x1400b5c10`
- `0x1400b5fec`
- `0x1400b60b8`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x1400b5cc1`
- `USER32!IsWindowEnabled` at `0x1400b5cc1`
- `USER32!SetFocus` at `0x1400b5e2d`
- `USER32!SetFocus` at `0x1400b5e2d`
- `USER32!GetFocus` at `0x1400b5c93`
- `USER32!GetFocus` at `0x1400b5c93`
- `USER32!IsWindow` at `0x1400b5e20`
- `USER32!IsWindow` at `0x1400b5e20`
- `USER32!EnableWindow` at `0x1400b5cd8`
- `USER32!EnableWindow` at `0x1400b5e17`
- `USER32!EnableWindow` at `0x1400b5cd8`
- `USER32!EnableWindow` at `0x1400b5e17`
- `MFC42u!__imp_?AfxGetThreadState@@YAPEAV_AFX_THREAD_STATE@@XZ` at `0x1400b5c20`
- `MFC42u!__imp_?AfxGetThreadState@@YAPEAV_AFX_THREAD_STATE@@XZ` at `0x1400b5c20`
- `MFC42u!__imp_?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z` at `0x1400b5cf3`
- `MFC42u!__imp_?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z` at `0x1400b5cf3`
- `MFC42u!__imp_?AfxUnhookWindowCreate@@YAHXZ` at `0x1400b5caf`
- `MFC42u!__imp_?AfxUnhookWindowCreate@@YAHXZ` at `0x1400b5caf`
- `MFC42u!__imp_?PostModal@CDialog@@IEAAXXZ` at `0x1400b5e36`
- `MFC42u!__imp_?PostModal@CDialog@@IEAAXXZ` at `0x1400b5e36`
- `MFC42u!__imp_?PreModal@CDialog@@IEAAPEAUHWND__@@XZ` at `0x1400b5ca2`
- `MFC42u!__imp_?PreModal@CDialog@@IEAAPEAUHWND__@@XZ` at `0x1400b5ca2`
- `KERNEL32!lstrlenW` at `0x1400b5c6b`
- `KERNEL32!lstrlenW` at `0x1400b5c6b`

## pseudocode

```c
__int64 __fastcall CFileDialogEx::DoModal(CFileDialogEx *this)
{
  struct _AFX_THREAD_STATE *ThreadState; // rbp
  __int64 result; // rax
  int v4; // eax
  int v5; // r15d
  HWND Focus; // r14
  HWND v7; // rcx
  bool v8; // zf
  char *v9; // rcx
  __int64 v10; // rax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  int SaveFileNameW; // eax
  int v19; // esi
  __int64 v20; // rax
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1

  ThreadState = AfxGetThreadState();
  if ( ThreadState )
  {
    v4 = lstrlenW(*((LPCWSTR *)this + 30));
    memset_0(
      (void *)(*((_QWORD *)this + 30) + 2LL * (unsigned int)(v4 + 1)),
      0,
      2LL * (unsigned int)(*((_DWORD *)this + 62) - (v4 + 1)));
    v5 = 0;
    Focus = GetFocus();
    *((_QWORD *)this + 25) = CDialog::PreModal(this);
    AfxUnhookWindowCreate();
    v7 = (HWND)*((_QWORD *)this + 25);
    if ( v7 && IsWindowEnabled(v7) )
    {
      v5 = 1;
      EnableWindow(*((HWND *)this + 25), 0);
    }
    if ( (*((_DWORD *)this + 72) & 0x80000) != 0 )
      *((_QWORD *)ThreadState + 6) = this;
    else
      AfxHookWindowCreate(this);
    *((_OWORD *)this + 71) = 0;
    v8 = *((_DWORD *)this + 82) == 0;
    v9 = (char *)this + 1000;
    v10 = *((_QWORD *)this + 40);
    v11 = *((_OWORD *)this + 13);
    *(_OWORD *)((char *)this + 1000) = *((_OWORD *)this + 12);
    v12 = *((_OWORD *)this + 14);
    *(_OWORD *)((char *)this + 1016) = v11;
    v13 = *((_OWORD *)this + 15);
    *(_OWORD *)((char *)this + 1032) = v12;
    v14 = *((_OWORD *)this + 16);
    *(_OWORD *)((char *)this + 1048) = v13;
    v15 = *((_OWORD *)this + 17);
    *(_OWORD *)((char *)this + 1064) = v14;
    v16 = *((_OWORD *)this + 18);
    *(_OWORD *)((char *)this + 1080) = v15;
    v17 = *((_OWORD *)this + 19);
    *(_OWORD *)((char *)this + 1096) = v16;
    *(_OWORD *)((char *)this + 1112) = v17;
    *((_QWORD *)this + 141) = v10;
    *((_DWORD *)this + 250) = 152;
    if ( v8 )
      SaveFileNameW = IsolationAwareGetSaveFileNameW(v9);
    else
      SaveFileNameW = IsolationAwareGetOpenFileNameW(v9);
    v19 = SaveFileNameW;
    v20 = *((_QWORD *)this + 141);
    v21 = *(_OWORD *)((char *)this + 1016);
    *((_OWORD *)this + 12) = *(_OWORD *)((char *)this + 1000);
    v22 = *(_OWORD *)((char *)this + 1032);
    *((_OWORD *)this + 13) = v21;
    v23 = *(_OWORD *)((char *)this + 1048);
    *((_OWORD *)this + 14) = v22;
    v24 = *(_OWORD *)((char *)this + 1064);
    *((_OWORD *)this + 15) = v23;
    v25 = *(_OWORD *)((char *)this + 1080);
    *((_OWORD *)this + 16) = v24;
    v26 = *(_OWORD *)((char *)this + 1096);
    *((_OWORD *)this + 17) = v25;
    v27 = *(_OWORD *)((char *)this + 1112);
    *((_OWORD *)this + 18) = v26;
    *((_OWORD *)this + 19) = v27;
    *((_QWORD *)this + 40) = v20;
    *((_DWORD *)this + 48) = 136;
    *((_QWORD *)ThreadState + 6) = 0;
    if ( v5 )
      EnableWindow(*((HWND *)this + 126), 1);
    if ( IsWindow(Focus) )
      SetFocus(Focus);
    CDialog::PostModal(this);
    LODWORD(result) = 2;
    if ( v19 )
      LODWORD(result) = v19;
    return (int)result;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_238f820e2cc235250b854f74f40deb59_Traceguids);
    return 2;
  }
}

```

## disassembly

```asm
0x1400b5c10  push    rbx
0x1400b5c12  push    rbp
0x1400b5c13  push    rsi
0x1400b5c14  push    rdi
0x1400b5c15  push    r14
0x1400b5c17  push    r15
0x1400b5c19  sub     rsp, 28h
0x1400b5c1d  mov     rbx, rcx
0x1400b5c20  call    cs:__imp_?AfxGetThreadState@@YAPEAV_AFX_THREAD_STATE@@XZ; AfxGetThreadState(void)
0x1400b5c26  mov     rbp, rax
0x1400b5c29  test    rax, rax
0x1400b5c2c  jnz     short loc_1400B5C64
0x1400b5c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5c35  lea     rax, WPP_GLOBAL_Control
0x1400b5c3c  lea     ebx, [rbp+2]
0x1400b5c3f  cmp     rcx, rax
0x1400b5c42  jz      short loc_1400B5C5C
0x1400b5c44  cmp     [rcx+19h], bl
0x1400b5c47  jb      short loc_1400B5C5C
0x1400b5c49  mov     rcx, [rcx+10h]
0x1400b5c4d  lea     edx, [rbp+0Ah]
0x1400b5c50  lea     r8, WPP_238f820e2cc235250b854f74f40deb59_Traceguids
0x1400b5c57  call    WPP_SF_
0x1400b5c5c  mov     rax, rbx
0x1400b5c5f  jmp     loc_1400B5E48
0x1400b5c64  mov     rcx, [rbx+0F0h]; lpString
0x1400b5c6b  call    cs:__imp_lstrlenW
0x1400b5c71  mov     r8d, [rbx+0F8h]
0x1400b5c78  xor     edx, edx; Val
0x1400b5c7a  lea     ecx, [rax+1]
0x1400b5c7d  mov     rax, [rbx+0F0h]
0x1400b5c84  sub     r8d, ecx
0x1400b5c87  add     r8, r8; Size
0x1400b5c8a  lea     rcx, [rax+rcx*2]; void *
0x1400b5c8e  call    memset_0
0x1400b5c93  call    cs:__imp_GetFocus
0x1400b5c99  mov     rcx, rbx
0x1400b5c9c  xor     r15d, r15d
0x1400b5c9f  mov     r14, rax
0x1400b5ca2  call    cs:__imp_?PreModal@CDialog@@IEAAPEAUHWND__@@XZ; CDialog::PreModal(void)
0x1400b5ca8  mov     [rbx+0C8h], rax
0x1400b5caf  call    cs:__imp_?AfxUnhookWindowCreate@@YAHXZ; AfxUnhookWindowCreate(void)
0x1400b5cb5  mov     rcx, [rbx+0C8h]; hWnd
0x1400b5cbc  test    rcx, rcx
0x1400b5cbf  jz      short loc_1400B5CDE
0x1400b5cc1  call    cs:__imp_IsWindowEnabled
0x1400b5cc7  test    eax, eax
0x1400b5cc9  jz      short loc_1400B5CDE
0x1400b5ccb  mov     rcx, [rbx+0C8h]; hWnd
0x1400b5cd2  xor     edx, edx; bEnable
0x1400b5cd4  lea     r15d, [rdx+1]
0x1400b5cd8  call    cs:__imp_EnableWindow
0x1400b5cde  test    dword ptr [rbx+120h], 80000h
0x1400b5ce8  jz      short loc_1400B5CF0
0x1400b5cea  mov     [rbp+30h], rbx
0x1400b5cee  jmp     short loc_1400B5CF9
0x1400b5cf0  mov     rcx, rbx
0x1400b5cf3  call    cs:__imp_?AfxHookWindowCreate@@YAXPEAVCWnd@@@Z; AfxHookWindowCreate(CWnd *)
0x1400b5cf9  lea     rdi, [rbx+3E8h]
0x1400b5d00  xorps   xmm0, xmm0
0x1400b5d03  movups  xmmword ptr [rbx+470h], xmm0
0x1400b5d0a  cmp     dword ptr [rbx+148h], 0
0x1400b5d11  mov     rcx, rdi
0x1400b5d14  movups  xmm0, xmmword ptr [rbx+0C0h]
0x1400b5d1b  mov     rax, [rbx+140h]
0x1400b5d22  movups  xmm1, xmmword ptr [rbx+0D0h]
0x1400b5d29  movups  xmmword ptr [rdi], xmm0
0x1400b5d2c  movups  xmm0, xmmword ptr [rbx+0E0h]
0x1400b5d33  movups  xmmword ptr [rdi+10h], xmm1
0x1400b5d37  movups  xmm1, xmmword ptr [rbx+0F0h]
0x1400b5d3e  movups  xmmword ptr [rdi+20h], xmm0
0x1400b5d42  movups  xmm0, xmmword ptr [rbx+100h]
0x1400b5d49  movups  xmmword ptr [rdi+30h], xmm1
0x1400b5d4d  movups  xmm1, xmmword ptr [rbx+110h]
0x1400b5d54  movups  xmmword ptr [rdi+40h], xmm0
0x1400b5d58  movups  xmm0, xmmword ptr [rbx+120h]
0x1400b5d5f  movups  xmmword ptr [rdi+50h], xmm1
0x1400b5d63  movups  xmm1, xmmword ptr [rbx+130h]
0x1400b5d6a  movups  xmmword ptr [rdi+60h], xmm0
0x1400b5d6e  movups  xmmword ptr [rdi+70h], xmm1
0x1400b5d72  mov     [rdi+80h], rax
0x1400b5d79  mov     dword ptr [rdi], 98h
0x1400b5d7f  jz      short loc_1400B5D88
0x1400b5d81  call    IsolationAwareGetOpenFileNameW
0x1400b5d86  jmp     short loc_1400B5D8D
0x1400b5d88  call    IsolationAwareGetSaveFileNameW
0x1400b5d8d  mov     esi, eax
0x1400b5d8f  mov     rax, [rdi+80h]
0x1400b5d96  movups  xmm0, xmmword ptr [rdi]
0x1400b5d99  movups  xmm1, xmmword ptr [rdi+10h]
0x1400b5d9d  movups  xmmword ptr [rbx+0C0h], xmm0
0x1400b5da4  movups  xmm0, xmmword ptr [rdi+20h]
0x1400b5da8  movups  xmmword ptr [rbx+0D0h], xmm1
0x1400b5daf  movups  xmm1, xmmword ptr [rdi+30h]
0x1400b5db3  movups  xmmword ptr [rbx+0E0h], xmm0
0x1400b5dba  movups  xmm0, xmmword ptr [rdi+40h]
0x1400b5dbe  movups  xmmword ptr [rbx+0F0h], xmm1
0x1400b5dc5  movups  xmm1, xmmword ptr [rdi+50h]
0x1400b5dc9  movups  xmmword ptr [rbx+100h], xmm0
0x1400b5dd0  movups  xmm0, xmmword ptr [rdi+60h]
0x1400b5dd4  movups  xmmword ptr [rbx+110h], xmm1
0x1400b5ddb  movups  xmm1, xmmword ptr [rdi+70h]
0x1400b5ddf  movups  xmmword ptr [rbx+120h], xmm0
0x1400b5de6  movups  xmmword ptr [rbx+130h], xmm1
0x1400b5ded  mov     [rbx+140h], rax
0x1400b5df4  mov     dword ptr [rbx+0C0h], 88h
0x1400b5dfe  mov     qword ptr [rbp+30h], 0
0x1400b5e06  test    r15d, r15d
0x1400b5e09  jz      short loc_1400B5E1D
0x1400b5e0b  mov     rcx, [rbx+3F0h]; hWnd
0x1400b5e12  mov     edx, 1; bEnable
0x1400b5e17  call    cs:__imp_EnableWindow
0x1400b5e1d  mov     rcx, r14; hWnd
0x1400b5e20  call    cs:__imp_IsWindow
0x1400b5e26  test    eax, eax
0x1400b5e28  jz      short loc_1400B5E33
0x1400b5e2a  mov     rcx, r14; hWnd
0x1400b5e2d  call    cs:__imp_SetFocus
0x1400b5e33  mov     rcx, rbx
0x1400b5e36  call    cs:__imp_?PostModal@CDialog@@IEAAXXZ; CDialog::PostModal(void)
0x1400b5e3c  mov     eax, 2
0x1400b5e41  test    esi, esi
0x1400b5e43  cmovnz  eax, esi
0x1400b5e46  cdqe
0x1400b5e48  add     rsp, 28h
0x1400b5e4c  pop     r15
0x1400b5e4e  pop     r14
0x1400b5e50  pop     rdi
0x1400b5e51  pop     rsi
0x1400b5e52  pop     rbp
0x1400b5e53  pop     rbx
0x1400b5e54  retn
```
