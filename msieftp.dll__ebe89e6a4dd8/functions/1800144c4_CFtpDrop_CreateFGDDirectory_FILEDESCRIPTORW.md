# CFtpDrop::_CreateFGDDirectory(_FILEDESCRIPTORW *)

- ea: `0x1800144c4`
- end: `0x180014654`
- name: `?_CreateFGDDirectory@CFtpDrop@@AEAAJPEAU_FILEDESCRIPTORW@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(CFtpDrop *__hidden this, struct _FILEDESCRIPTORW *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001262c`

## callees

- `0x180002240`
- `0x1800113ac`
- `0x18001168c`
- `0x1800144c4`
- `0x1800170bc`
- `0x18001b3ec`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800145dc`
- `SHELL32!__imp_ILFree` at `0x1800145dc`
- `SHLWAPI!StrChrW` at `0x180014578`
- `SHLWAPI!StrChrW` at `0x180014578`
- `SHLWAPI!PathFindFileNameW` at `0x1800144ef`
- `SHLWAPI!PathFindFileNameW` at `0x1800144ef`

## pseudocode

```c
__int64 __fastcall CFtpDrop::_CreateFGDDirectory(CFtpDrop *this, struct _FILEDESCRIPTORW *a2)
{
  WCHAR *cFileName; // rbx
  LPWSTR FileNameW; // rax
  _WORD *v5; // rdx
  CFtpDir *SubFtpDir; // rdi
  __int64 v7; // rcx
  LPWSTR v8; // r9
  __int64 v9; // r8
  _WORD *v10; // rcx
  const WCHAR *i; // rcx
  PWSTR v12; // rax
  unsigned int WireEncoding; // eax
  int v14; // ebx
  LPITEMIDLIST pidl; // [rsp+40h] [rbp-258h] BYREF
  _QWORD v17[3]; // [rsp+48h] [rbp-250h] BYREF
  _BYTE v18[528]; // [rsp+60h] [rbp-238h] BYREF

  cFileName = a2->cFileName;
  FileNameW = PathFindFileNameW(a2->cFileName);
  v5 = v18;
  SubFtpDir = (CFtpDir *)*((_QWORD *)this + 3);
  v17[1] = *((_QWORD *)this + 2);
  v17[0] = v18;
  v7 = 2147483646;
  v8 = FileNameW;
  v9 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*v8 )
      break;
    *v5++ = *v8++;
    --v7;
    --v9;
  }
  while ( v9 );
  v10 = v5 - 1;
  if ( v9 )
    v10 = v5;
  *v10 = 0;
  *FileNameW = 0;
  if ( !*cFileName )
    goto LABEL_15;
  pidl = 0;
  for ( i = cFileName; ; i = v12 )
  {
    v12 = StrChrW(i, 0x5Cu);
    if ( !v12 )
      break;
    *v12 = 47;
  }
  WireEncoding = CFtpFolder::GetWireEncoding(*((_QWORD *)this + 2));
  v14 = CreateFtpPidlFromDisplayPath(cFileName, WireEncoding, 0, &pidl, 1, 1);
  if ( v14 >= 0 )
  {
    SubFtpDir = CFtpDir::GetSubFtpDir(*((CFtpDir **)this + 3), *((struct CFtpFolder **)this + 2), pidl, 0);
    if ( !SubFtpDir )
      v14 = -2147024882;
    ILFree(pidl);
    if ( v14 >= 0 )
LABEL_15:
      v14 = CFtpDir::WithHint(
              SubFtpDir,
              0,
              *((HWND *)this + 4),
              (int (*)(void *, struct HINTPROCINFO *, void *, int *))CreateNewFolderCB,
              v17,
              0,
              *((struct CFtpFolder **)this + 2));
  }
  if ( *((CFtpDir **)this + 3) != SubFtpDir && SubFtpDir )
    (*(void (__fastcall **)(CFtpDir *))(*(_QWORD *)SubFtpDir + 16LL))(SubFtpDir);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800144c4  mov     [rsp+arg_10], rbx
0x1800144c9  push    rbp
0x1800144ca  push    rsi
0x1800144cb  push    rdi
0x1800144cc  sub     rsp, 280h
0x1800144d3  mov     rax, cs:__security_cookie
0x1800144da  xor     rax, rsp
0x1800144dd  mov     [rsp+298h+var_28], rax
0x1800144e5  lea     rbx, [rdx+48h]
0x1800144e9  mov     rsi, rcx
0x1800144ec  mov     rcx, rbx; pszPath
0x1800144ef  call    cs:__imp_PathFindFileNameW
0x1800144f5  mov     rcx, [rsi+10h]
0x1800144f9  lea     rdx, [rsp+298h+var_238]
0x1800144fe  mov     rdi, [rsi+18h]
0x180014502  mov     r10, rax
0x180014505  lea     rax, [rsp+298h+var_238]
0x18001450a  mov     [rsp+298h+var_248], rcx
0x18001450f  mov     [rsp+298h+var_250], rax
0x180014514  mov     ecx, 7FFFFFFEh
0x180014519  mov     r9, r10
0x18001451c  mov     r8d, 104h
0x180014522  xor     ebp, ebp
0x180014524  test    rcx, rcx
0x180014527  jz      short loc_180014546
0x180014529  movzx   eax, word ptr [r9]
0x18001452d  test    ax, ax
0x180014530  jz      short loc_180014546
0x180014532  mov     [rdx], ax
0x180014535  add     r9, 2
0x180014539  add     rdx, 2
0x18001453d  dec     rcx
0x180014540  sub     r8, 1
0x180014544  jnz     short loc_180014524
0x180014546  test    r8, r8
0x180014549  lea     rcx, [rdx-2]
0x18001454d  cmovnz  rcx, rdx
0x180014551  mov     [rcx], bp
0x180014554  mov     [r10], bp
0x180014558  cmp     [rbx], bp
0x18001455b  jz      loc_1800145E6
0x180014561  mov     [rsp+298h+pidl], rbp
0x180014566  mov     rcx, rbx
0x180014569  jmp     short loc_180014573
0x18001456b  mov     word ptr [rax], 2Fh ; '/'
0x180014570  mov     rcx, rax; pszStart
0x180014573  mov     edx, 5Ch ; '\'; wMatch
0x180014578  call    cs:__imp_StrChrW
0x18001457e  test    rax, rax
0x180014581  jnz     short loc_18001456B
0x180014583  mov     rcx, [rsi+10h]
0x180014587  call    ?GetWireEncoding@CFtpFolder@@QEAA?AW4WIREENC@@XZ; CFtpFolder::GetWireEncoding(void)
0x18001458c  mov     edx, eax
0x18001458e  mov     dword ptr [rsp+298h+var_270], 1
0x180014596  lea     r9, [rsp+298h+pidl]
0x18001459b  mov     dword ptr [rsp+298h+var_278], 1
0x1800145a3  xor     r8d, r8d
0x1800145a6  mov     rcx, rbx
0x1800145a9  call    ?CreateFtpPidlFromDisplayPath@@YAJPEBGW4WIREENC@@PEAKPEAPEFAU_ITEMIDLIST@@HH@Z; CreateFtpPidlFromDisplayPath(ushort const *,WIREENC,ulong *,_ITEMIDLIST * *,int,int)
0x1800145ae  mov     ebx, eax
0x1800145b0  test    eax, eax
0x1800145b2  js      short loc_180014615
0x1800145b4  mov     r8, [rsp+298h+pidl]; struct _ITEMIDLIST *
0x1800145b9  xor     r9d, r9d; int
0x1800145bc  mov     rdx, [rsi+10h]; struct CFtpFolder *
0x1800145c0  mov     rcx, [rsi+18h]; this
0x1800145c4  call    ?GetSubFtpDir@CFtpDir@@QEAAPEAV1@PEAVCFtpFolder@@PEFBU_ITEMIDLIST@@H@Z; CFtpDir::GetSubFtpDir(CFtpFolder *,_ITEMIDLIST const *,int)
0x1800145c9  mov     rcx, [rsp+298h+pidl]; pidl
0x1800145ce  mov     rdi, rax
0x1800145d1  mov     eax, 8007000Eh
0x1800145d6  test    rdi, rdi
0x1800145d9  cmovz   ebx, eax
0x1800145dc  call    cs:__imp_ILFree
0x1800145e2  test    ebx, ebx
0x1800145e4  js      short loc_180014615
0x1800145e6  mov     rcx, [rsi+10h]
0x1800145ea  lea     rax, [rsp+298h+var_250]
0x1800145ef  mov     r8, [rsi+20h]; HWND
0x1800145f3  lea     r9, ?CreateNewFolderCB@@YAJPEAXPEAUHINTPROCINFO@@0PEAH@Z; int (*)(void *, struct HINTPROCINFO *, void *, int *)
0x1800145fa  mov     [rsp+298h+var_268], rcx; struct CFtpFolder *
0x1800145ff  xor     edx, edx; struct CStatusBar *
0x180014601  mov     [rsp+298h+var_270], rbp; struct IUnknown *
0x180014606  mov     rcx, rdi; this
0x180014609  mov     [rsp+298h+var_278], rax; void *
0x18001460e  call    ?WithHint@CFtpDir@@QEAAJPEAVCStatusBar@@PEAUHWND__@@P6AJPEAXPEAUHINTPROCINFO@@2PEAH@ZPEBXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpDir::WithHint(CStatusBar *,HWND__ *,long (*)(void *,HINTPROCINFO *,void *,int *),void const *,IUnknown *,CFtpFolder *)
0x180014613  mov     ebx, eax
0x180014615  cmp     [rsi+18h], rdi
0x180014619  jz      short loc_18001462F
0x18001461b  test    rdi, rdi
0x18001461e  jz      short loc_18001462F
0x180014620  mov     rax, [rdi]
0x180014623  mov     rcx, rdi
0x180014626  mov     rax, [rax+10h]
0x18001462a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001462f  mov     eax, ebx
0x180014631  mov     rcx, [rsp+298h+var_28]
0x180014639  xor     rcx, rsp; StackCookie
0x18001463c  call    __security_check_cookie
0x180014641  mov     rbx, [rsp+298h+arg_10]
0x180014649  add     rsp, 280h
0x180014650  pop     rdi
0x180014651  pop     rsi
0x180014652  pop     rbp
0x180014653  retn
```
