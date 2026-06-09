# CDropOperation::_CalcUploadProgress(void)

- ea: `0x180013f20`
- end: `0x1800140f8`
- name: `?_CalcUploadProgress@CDropOperation@@IEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CDropOperation *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180014c6c`

## callees

- `0x180002240`
- `0x180002b60`
- `0x18001168c`
- `0x180013f20`
- `0x1800147a4`
- `0x18001bd14`
- `0x18001d840`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800140cd`
- `SHELL32!__imp_ILFree` at `0x1800140cd`
- `SHLWAPI!PathFindFileNameW` at `0x180014005`
- `SHLWAPI!PathFindFileNameW` at `0x180014005`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013f7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013f7f`

## pseudocode

```c
__int64 __fastcall CDropOperation::_CalcUploadProgress(CDropOperation *this)
{
  unsigned __int16 *v1; // rax
  unsigned int v3; // r9d
  int v4; // ebx
  __int64 v5; // rdi
  LPWSTR FileNameW; // rbx
  __int64 v7; // rax
  ITEMIDLIST *v8; // rax
  HWND v9; // r8
  CFtpDir *v10; // rcx
  unsigned int v12; // [rsp+28h] [rbp-D8h]
  struct CFtpFolder *v13; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v16[5]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+78h] [rbp-88h]
  LPITEMIDLIST pidl; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+88h] [rbp-78h]
  __int64 v20; // [rsp+90h] [rbp-70h]
  __int64 v21; // [rsp+98h] [rbp-68h]
  __int64 v22; // [rsp+A0h] [rbp-60h]
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPath[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v25[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v26[528]; // [rsp+6F0h] [rbp+5F0h] BYREF

  v15 = (unsigned __int16 *)*((_QWORD *)this + 10);
  v1 = (unsigned __int16 *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  v14 = v1;
  if ( LoadStringW(g_hinst, 0x120u, Buffer, 260) )
    (*(void (__fastcall **)(_QWORD, __int64, WCHAR *))(**((_QWORD **)this + 9) + 80LL))(
      *((_QWORD *)this + 9),
      2,
      Buffer);
  do
  {
    v4 = _EnumOneHdrop((const unsigned __int16 **)&v15, (const unsigned __int16 **)&v14, v25, v3, pszPath, v12);
    if ( v4 )
      break;
    v5 = *((_QWORD *)this + 9);
    UrlGetAbstractPathFromPidl(*(const struct _ITEMIDLIST **)(*((_QWORD *)this + 3) + 40LL), 0, 0, v26, 0x104u);
    FileNameW = PathFindFileNameW(pszPath);
    memset_0(v16, 0, 0x68u);
    v7 = *((_QWORD *)this + 2);
    v16[1] = v25;
    v16[3] = v26;
    v16[0] = v7;
    v16[2] = FileNameW;
    v16[4] = 5;
    v17 = 1;
    v8 = FtpCloneServerID((LPCITEMIDLIST)(*(_QWORD *)(v7 + 48) + *(int *)(v7 + 64)));
    v9 = (HWND)*((_QWORD *)this + 4);
    v10 = (CFtpDir *)*((_QWORD *)this + 3);
    pidl = v8;
    v21 = *((_QWORD *)this + 7);
    v22 = *((_QWORD *)this + 8);
    v13 = (struct CFtpFolder *)*((_QWORD *)this + 2);
    v20 = v5;
    v19 = 1;
    v4 = CFtpDir::WithHint(
           v10,
           0,
           v9,
           (int (*)(void *, struct HINTPROCINFO *, void *, int *))CDropOperation::CopyCB,
           v16,
           0,
           v13);
    if ( v4 >= 0 )
    {
      *((_QWORD *)this + 7) = v21;
      *((_QWORD *)this + 8) = v22;
    }
    ILFree(pidl);
  }
  while ( !v4 );
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013f20  push    rbp
0x180013f22  push    rbx
0x180013f23  push    rsi
0x180013f24  push    rdi
0x180013f25  lea     rbp, [rsp-818h]
0x180013f2d  sub     rsp, 918h
0x180013f34  mov     rax, cs:__security_cookie
0x180013f3b  xor     rax, rsp
0x180013f3e  mov     [rbp+830h+var_30], rax
0x180013f45  mov     rax, [rcx+50h]
0x180013f49  lea     r8, [rbp+830h+Buffer]; lpBuffer
0x180013f4d  mov     r9d, 104h; cchBufferMax
0x180013f53  mov     [rsp+930h+var_8E8], rax
0x180013f58  mov     rax, [rcx+58h]
0x180013f5c  mov     rsi, rcx
0x180013f5f  mov     qword ptr [rcx+38h], 0
0x180013f67  mov     qword ptr [rcx+40h], 0
0x180013f6f  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180013f76  lea     edx, [r9+1Ch]; uID
0x180013f7a  mov     [rsp+930h+var_8F0], rax
0x180013f7f  call    cs:__imp_LoadStringW
0x180013f85  test    eax, eax
0x180013f87  jz      short loc_180013FAD
0x180013f89  mov     rcx, [rsi+48h]
0x180013f8d  lea     r8, [rbp+830h+Buffer]
0x180013f91  xor     r9d, r9d
0x180013f94  mov     [rsp+930h+var_910], 0
0x180013f9d  mov     rax, [rcx]
0x180013fa0  lea     edx, [r9+2]
0x180013fa4  mov     rax, [rax+50h]
0x180013fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fad  lea     rax, [rbp+830h+pszPath]
0x180013fb4  lea     r8, [rbp+830h+var_450]; unsigned __int16 *
0x180013fbb  mov     [rsp+930h+var_910], rax; unsigned __int16 *
0x180013fc0  lea     rdx, [rsp+930h+var_8F0]; unsigned __int16 **
0x180013fc5  lea     rcx, [rsp+930h+var_8E8]; unsigned __int16 **
0x180013fca  call    ?_EnumOneHdrop@@YAJPEAPEBG0PEAGK1K@Z; _EnumOneHdrop(ushort const * *,ushort const * *,ushort *,ulong,ushort *,ulong)
0x180013fcf  mov     ebx, eax
0x180013fd1  test    eax, eax
0x180013fd3  jnz     loc_1800140DB
0x180013fd9  mov     rcx, [rsi+18h]
0x180013fdd  lea     r9, [rbp+830h+var_240]; void *
0x180013fe4  mov     rdi, [rsi+48h]
0x180013fe8  xor     r8d, r8d; int
0x180013feb  xor     edx, edx; int
0x180013fed  mov     dword ptr [rsp+930h+var_910], 104h; unsigned int
0x180013ff5  mov     rcx, [rcx+28h]; struct _ITEMIDLIST *
0x180013ff9  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x180013ffe  lea     rcx, [rbp+830h+pszPath]; pszPath
0x180014005  call    cs:__imp_PathFindFileNameW
0x18001400b  xor     edx, edx; Val
0x18001400d  lea     rcx, [rsp+930h+var_8E0]; void *
0x180014012  mov     rbx, rax
0x180014015  lea     r8d, [rdx+68h]; Size
0x180014019  call    memset_0
0x18001401e  mov     rax, [rsi+10h]
0x180014022  lea     rcx, [rbp+830h+var_450]
0x180014029  mov     [rsp+930h+var_8D8], rcx
0x18001402e  lea     rcx, [rbp+830h+var_240]
0x180014035  mov     [rsp+930h+var_8C8], rcx
0x18001403a  mov     [rsp+930h+var_8E0], rax
0x18001403f  mov     [rsp+930h+var_8D0], rbx
0x180014044  mov     [rsp+930h+var_8C0], 5
0x18001404d  mov     [rsp+930h+var_8B8], 1
0x180014055  movsxd  rcx, dword ptr [rax+40h]
0x180014059  add     rcx, [rax+30h]; pidl
0x18001405d  call    ?FtpCloneServerID@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z; FtpCloneServerID(_ITEMIDLIST const *)
0x180014062  mov     r8, [rsi+20h]; HWND
0x180014066  lea     r9, ?CopyCB@CDropOperation@@SAJPEAXPEAUHINTPROCINFO@@0PEAH@Z; int (*)(void *, struct HINTPROCINFO *, void *, int *)
0x18001406d  mov     rcx, [rsi+18h]; this
0x180014071  xor     edx, edx; struct CStatusBar *
0x180014073  mov     [rbp+830h+pidl], rax
0x180014077  mov     rax, [rsi+38h]
0x18001407b  mov     [rbp+830h+var_898], rax
0x18001407f  mov     rax, [rsi+40h]
0x180014083  mov     [rbp+830h+var_890], rax
0x180014087  mov     rax, [rsi+10h]
0x18001408b  mov     [rsp+930h+var_900], rax; struct CFtpFolder *
0x180014090  lea     rax, [rsp+930h+var_8E0]
0x180014095  mov     [rsp+930h+var_908], 0; struct IUnknown *
0x18001409e  mov     [rsp+930h+var_910], rax; void *
0x1800140a3  mov     [rbp+830h+var_8A0], rdi
0x1800140a7  mov     [rbp+830h+var_8A8], 1
0x1800140ae  call    ?WithHint@CFtpDir@@QEAAJPEAVCStatusBar@@PEAUHWND__@@P6AJPEAXPEAUHINTPROCINFO@@2PEAH@ZPEBXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpDir::WithHint(CStatusBar *,HWND__ *,long (*)(void *,HINTPROCINFO *,void *,int *),void const *,IUnknown *,CFtpFolder *)
0x1800140b3  mov     ebx, eax
0x1800140b5  test    eax, eax
0x1800140b7  js      short loc_1800140C9
0x1800140b9  mov     rax, [rbp+830h+var_898]
0x1800140bd  mov     [rsi+38h], rax
0x1800140c1  mov     rax, [rbp+830h+var_890]
0x1800140c5  mov     [rsi+40h], rax
0x1800140c9  mov     rcx, [rbp+830h+pidl]; pidl
0x1800140cd  call    cs:__imp_ILFree
0x1800140d3  test    ebx, ebx
0x1800140d5  jz      loc_180013FAD
0x1800140db  mov     eax, ebx
0x1800140dd  mov     rcx, [rbp+830h+var_30]
0x1800140e4  xor     rcx, rsp; StackCookie
0x1800140e7  call    __security_check_cookie
0x1800140ec  add     rsp, 918h
0x1800140f3  pop     rdi
0x1800140f4  pop     rsi
0x1800140f5  pop     rbx
0x1800140f6  pop     rbp
0x1800140f7  retn
```
