# CMainFrame::PreCreateWindow(tagCREATESTRUCTW &)

- ea: `0x1400bd3a0`
- end: `0x1400bd4be`
- name: `?PreCreateWindow@CMainFrame@@UEAAHAEAUtagCREATESTRUCTW@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(CMainFrame *__hidden this, struct tagCREATESTRUCTW *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14001de00`
- `0x140062455`
- `0x1400bbd3c`
- `0x1400bd3a0`

## import_xrefs

- `USER32!GetClassInfoW` at `0x1400bd451`
- `USER32!GetClassInfoW` at `0x1400bd469`
- `USER32!GetClassInfoW` at `0x1400bd451`
- `USER32!GetClassInfoW` at `0x1400bd469`
- `MFC42u!__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x1400bd43c`
- `MFC42u!__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ` at `0x1400bd43c`
- `MFC42u!__imp_?AfxRegisterClass@@YAHPEAUtagWNDCLASSW@@@Z` at `0x1400bd48a`
- `MFC42u!__imp_?AfxRegisterClass@@YAHPEAUtagWNDCLASSW@@@Z` at `0x1400bd48a`
- `MFC42u!__imp_?PreCreateWindow@CMDIFrameWnd@@UEAAHAEAUtagCREATESTRUCTW@@@Z` at `0x1400bd3d8`
- `MFC42u!__imp_?PreCreateWindow@CMDIFrameWnd@@UEAAHAEAUtagCREATESTRUCTW@@@Z` at `0x1400bd3d8`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400bd4aa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400bd4aa`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400bd41c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400bd41c`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400bd3b9`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400bd3b9`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400bd411`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1400bd411`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400bd3cc`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400bd3cc`

## string_xrefs

- `0x1400bd3c0`: `CMainFrame::PreCreateWindow`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMainFrame::PreCreateWindow(CMainFrame *this, struct tagCREATESTRUCTW *a2)
{
  unsigned int v4; // eax
  HINSTANCE v5; // rsi
  unsigned int ClassInfoW; // ebx
  CMainFrame *v7; // rcx
  _BYTE v9[32]; // [rsp+20h] [rbp-98h] BYREF
  struct tagWNDCLASSW WndClass; // [rsp+40h] [rbp-78h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v9, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v9, L"CMainFrame::PreCreateWindow");
  if ( !CMDIFrameWnd::PreCreateWindow(this, a2) )
    goto LABEL_9;
  if ( byte_140160444 )
  {
    v4 = StringCchCopyW(&ClassName, 0xDu, L"MMCMainFrame");
    mmcerror::SC::operator=(v9, v4);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(v9) )
    {
      byte_140160444 = 0;
      goto LABEL_5;
    }
LABEL_9:
    ClassInfoW = 0;
    goto LABEL_10;
  }
LABEL_5:
  memset_0(&WndClass, 0, sizeof(WndClass));
  v5 = (HINSTANCE)*((_QWORD *)AfxGetModuleState() + 2);
  ClassInfoW = GetClassInfoW(v5, &ClassName, &WndClass);
  if ( ClassInfoW
    || GetClassInfoW(v5, a2->lpszClass, &WndClass)
    && (WndClass.lpszClassName = &ClassName,
        WndClass.hIcon = CMainFrame::GetDefaultIcon(v7),
        (ClassInfoW = AfxRegisterClass(&WndClass)) != 0) )
  {
    a2->lpszClass = &ClassName;
    a2->style &= 0xFFFF3FFF;
  }
LABEL_10:
  mmcerror::SC::~SC((mmcerror::SC *)v9);
  return ClassInfoW;
}

```

## disassembly

```asm
0x1400bd3a0  push    rbx
0x1400bd3a2  push    rbp
0x1400bd3a3  push    rsi
0x1400bd3a4  push    rdi
0x1400bd3a5  sub     rsp, 98h
0x1400bd3ac  mov     rdi, rdx
0x1400bd3af  mov     rbx, rcx
0x1400bd3b2  xor     edx, edx
0x1400bd3b4  lea     rcx, [rsp+0B8h+var_98]
0x1400bd3b9  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400bd3bf  nop
0x1400bd3c0  lea     rdx, aCmainframePrec; "CMainFrame::PreCreateWindow"
0x1400bd3c7  lea     rcx, [rsp+0B8h+var_98]
0x1400bd3cc  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400bd3d2  mov     rdx, rdi
0x1400bd3d5  mov     rcx, rbx
0x1400bd3d8  call    cs:__imp_?PreCreateWindow@CMDIFrameWnd@@UEAAHAEAUtagCREATESTRUCTW@@@Z; CMDIFrameWnd::PreCreateWindow(tagCREATESTRUCTW &)
0x1400bd3de  test    eax, eax
0x1400bd3e0  jz      loc_1400BD4A3
0x1400bd3e6  lea     rbp, ClassName
0x1400bd3ed  cmp     cs:byte_140160444, 0
0x1400bd3f4  jz      short loc_1400BD42C
0x1400bd3f6  lea     r8, aMmcmainframe; "MMCMainFrame"
0x1400bd3fd  mov     edx, 0Dh; unsigned __int64
0x1400bd402  mov     rcx, rbp; unsigned __int16 *
0x1400bd405  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400bd40a  mov     edx, eax
0x1400bd40c  lea     rcx, [rsp+0B8h+var_98]
0x1400bd411  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1400bd417  lea     rcx, [rsp+0B8h+var_98]
0x1400bd41c  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400bd422  test    al, al
0x1400bd424  jnz     short loc_1400BD4A3
0x1400bd426  mov     cs:byte_140160444, al
0x1400bd42c  xor     edx, edx; Val
0x1400bd42e  lea     r8d, [rdx+48h]; Size
0x1400bd432  lea     rcx, [rsp+0B8h+WndClass]; void *
0x1400bd437  call    memset_0
0x1400bd43c  call    cs:__imp_?AfxGetModuleState@@YAPEAVAFX_MODULE_STATE@@XZ; AfxGetModuleState(void)
0x1400bd442  mov     rsi, [rax+10h]
0x1400bd446  lea     r8, [rsp+0B8h+WndClass]; lpWndClass
0x1400bd44b  mov     rdx, rbp; lpClassName
0x1400bd44e  mov     rcx, rsi; hInstance
0x1400bd451  call    cs:__imp_GetClassInfoW
0x1400bd457  mov     ebx, eax
0x1400bd459  test    eax, eax
0x1400bd45b  jnz     short loc_1400BD496
0x1400bd45d  lea     r8, [rsp+0B8h+WndClass]; lpWndClass
0x1400bd462  mov     rdx, [rdi+40h]; lpClassName
0x1400bd466  mov     rcx, rsi; hInstance
0x1400bd469  call    cs:__imp_GetClassInfoW
0x1400bd46f  test    eax, eax
0x1400bd471  jz      short loc_1400BD4A5
0x1400bd473  mov     [rsp+0B8h+WndClass.lpszClassName], rbp
0x1400bd47b  call    ?GetDefaultIcon@CMainFrame@@IEBAPEAUHICON__@@XZ; CMainFrame::GetDefaultIcon(void)
0x1400bd480  mov     [rsp+0B8h+WndClass.hIcon], rax
0x1400bd485  lea     rcx, [rsp+0B8h+WndClass]
0x1400bd48a  call    cs:__imp_?AfxRegisterClass@@YAHPEAUtagWNDCLASSW@@@Z; AfxRegisterClass(tagWNDCLASSW *)
0x1400bd490  mov     ebx, eax
0x1400bd492  test    eax, eax
0x1400bd494  jz      short loc_1400BD4A5
0x1400bd496  mov     [rdi+40h], rbp
0x1400bd49a  and     dword ptr [rdi+30h], 0FFFF3FFFh
0x1400bd4a1  jmp     short loc_1400BD4A5
0x1400bd4a3  xor     ebx, ebx
0x1400bd4a5  lea     rcx, [rsp+0B8h+var_98]
0x1400bd4aa  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400bd4b0  mov     eax, ebx
0x1400bd4b2  add     rsp, 98h
0x1400bd4b9  pop     rdi
0x1400bd4ba  pop     rsi
0x1400bd4bb  pop     rbp
0x1400bd4bc  pop     rbx
0x1400bd4bd  retn
```
