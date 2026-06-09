# CFtpSite::_SetDirectory(void *,HWND__ *,_ITEMIDLIST const *,CStatusBar *)

- ea: `0x180020a4c`
- end: `0x180020c32`
- name: `?_SetDirectory@CFtpSite@@IEAAJPEAXPEAUHWND__@@PEFBU_ITEMIDLIST@@PEAVCStatusBar@@@Z`
- size: `486`
- prototype: `__int64 __usercall@<rax>(CFtpSite *__hidden this@<rcx>, void *@<rdx>, HWND@<r8>, const struct _ITEMIDLIST *@<r9>, struct CStatusBar *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fa30`

## callees

- `0x180002240`
- `0x18000cca4`
- `0x18001bd14`
- `0x18001bda4`
- `0x18001d840`
- `0x18001fc24`
- `0x180020a4c`
- `0x180020c38`
- `0x180023340`
- `0x180024134`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x180020aef`
- `SHELL32!__imp_ILClone` at `0x180020aef`
- `SHELL32!__imp_ILCombine` at `0x180020b2c`
- `SHELL32!__imp_ILCombine` at `0x180020b40`
- `SHELL32!__imp_ILCombine` at `0x180020b2c`
- `SHELL32!__imp_ILCombine` at `0x180020b40`
- `SHELL32!__imp_ILFree` at `0x180020b4c`
- `SHELL32!__imp_ILFree` at `0x180020b55`
- `SHELL32!__imp_ILFree` at `0x180020bf2`
- `SHELL32!__imp_ILFree` at `0x180020b4c`
- `SHELL32!__imp_ILFree` at `0x180020b55`
- `SHELL32!__imp_ILFree` at `0x180020bf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ba2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020ba2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020bc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020bc6`
- `WININET!InternetCloseHandle` at `0x180020bb9`
- `WININET!InternetCloseHandle` at `0x180020bb9`

## pseudocode

```c
__int64 __fastcall CFtpSite::_SetDirectory(
        LPCITEMIDLIST *this,
        void *a2,
        HWND a3,
        const struct _ITEMIDLIST *a4,
        struct CStatusBar *a5)
{
  const struct _ITEMIDLIST *v5; // rbx
  HWND v6; // r15
  int AbstractPathFromPidl; // eax
  const unsigned __int16 *v10; // r8
  LPITEMIDLIST v11; // r14
  struct _ITEMIDLIST *v12; // r15
  const ITEMIDLIST *v13; // rdi
  const ITEMIDLIST *v14; // rax
  ITEMIDLIST *v15; // r12
  int v16; // edi
  int v17; // edx
  unsigned int v18; // r9d
  ITEMIDLIST *v19; // rcx
  unsigned int v21; // [rsp+28h] [rbp-290h]
  unsigned int v22; // [rsp+30h] [rbp-288h]
  _BYTE v24[528]; // [rsp+50h] [rbp-268h] BYREF

  v5 = a4;
  v6 = a3;
  if ( a4 && (unsigned int)FtpID_IsServerItemID(a4) )
    v5 = (const struct _ITEMIDLIST *)((char *)v5 + v5->mkid.cb);
  if ( a5 )
  {
    if ( !v5
      || (AbstractPathFromPidl = UrlGetAbstractPathFromPidl(v5, 1, 0, v24, 0x104u),
          v10 = (const unsigned __int16 *)v24,
          AbstractPathFromPidl < 0) )
    {
      v10 = L"\\";
    }
    CStatusBar::SetStatusMessage(a5, 0x42u, v10);
  }
  if ( this[13] )
  {
    v11 = 0;
    v12 = 0;
    v13 = v5;
    if ( v5 && (unsigned int)FtpID_IsServerItemID(v5) )
    {
      v12 = FtpCloneServerID(v5);
      v13 = (const struct _ITEMIDLIST *)((char *)v5 + v5->mkid.cb);
    }
    v14 = ILCombine(v12, this[13]);
    v15 = (ITEMIDLIST *)v14;
    if ( v14 )
    {
      v11 = ILCombine(v14, v13);
      ILFree(v15);
    }
    ILFree(v12);
    v6 = a3;
  }
  else
  {
    v11 = ILClone(v5);
  }
  v16 = FtpSetCurrentDirectoryPidlWrap(a2, v11, 1, 1);
  if ( v16 < 0 )
  {
    CFtpSite::ReleaseHint((CFtpSite *)this, 0, a2);
    if ( v16 == -2147012785 )
    {
      EnterCriticalSection(&g_csDll);
      v19 = (ITEMIDLIST *)this[3];
      this[3] = 0;
      if ( v19 )
        InternetCloseHandle(v19);
      LeaveCriticalSection(&g_csDll);
    }
    else
    {
      DisplayWininetError(v6, v17, v16, v18, 0x198u, v21, v22, 0);
      v16 = -2147023673;
    }
  }
  else
  {
    v16 = CFtpSite::_SetPidl((CFtpSite *)this, v5);
  }
  ILFree(v11);
  if ( a5 )
    CStatusBar::SetStatusMessage(a5, 0x40u, 0);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180020a4c  push    rbx
0x180020a4e  push    rbp
0x180020a4f  push    rsi
0x180020a50  push    rdi
0x180020a51  push    r12
0x180020a53  push    r13
0x180020a55  push    r14
0x180020a57  push    r15
0x180020a59  sub     rsp, 278h
0x180020a60  mov     rax, cs:__security_cookie
0x180020a67  xor     rax, rsp
0x180020a6a  mov     [rsp+2B8h+var_58], rax
0x180020a72  mov     rbp, [rsp+2B8h+arg_20]
0x180020a7a  mov     rbx, r9
0x180020a7d  mov     [rsp+2B8h+var_278], r8
0x180020a82  mov     r15, r8
0x180020a85  mov     r13, rdx
0x180020a88  mov     rsi, rcx
0x180020a8b  test    r9, r9
0x180020a8e  jz      short loc_180020AA2
0x180020a90  mov     rcx, rbx; struct _ITEMIDLIST *
0x180020a93  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x180020a98  test    eax, eax
0x180020a9a  jz      short loc_180020AA2
0x180020a9c  movzx   eax, word ptr [rbx]
0x180020a9f  add     rbx, rax
0x180020aa2  test    rbp, rbp
0x180020aa5  jz      short loc_180020AE5
0x180020aa7  test    rbx, rbx
0x180020aaa  jz      short loc_180020AD1
0x180020aac  xor     r8d, r8d; int
0x180020aaf  mov     [rsp+2B8h+var_298], 104h; unsigned int
0x180020ab7  lea     r9, [rsp+2B8h+var_268]; void *
0x180020abc  mov     rcx, rbx; struct _ITEMIDLIST *
0x180020abf  lea     edx, [r8+1]; int
0x180020ac3  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x180020ac8  lea     r8, [rsp+2B8h+var_268]
0x180020acd  test    eax, eax
0x180020acf  jns     short loc_180020AD8
0x180020ad1  lea     r8, asc_18002AE70; "\\"
0x180020ad8  mov     edx, 42h ; 'B'; unsigned int
0x180020add  mov     rcx, rbp; this
0x180020ae0  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x180020ae5  cmp     qword ptr [rsi+68h], 0
0x180020aea  jnz     short loc_180020AFA
0x180020aec  mov     rcx, rbx; pidl
0x180020aef  call    cs:__imp_ILClone
0x180020af5  mov     r14, rax
0x180020af8  jmp     short loc_180020B60
0x180020afa  xor     r14d, r14d
0x180020afd  xor     r15d, r15d
0x180020b00  mov     rdi, rbx
0x180020b03  test    rbx, rbx
0x180020b06  jz      short loc_180020B25
0x180020b08  mov     rcx, rbx; struct _ITEMIDLIST *
0x180020b0b  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x180020b10  test    eax, eax
0x180020b12  jz      short loc_180020B25
0x180020b14  mov     rcx, rbx; pidl
0x180020b17  call    ?FtpCloneServerID@@YAPEFAU_ITEMIDLIST@@PEFBU1@@Z; FtpCloneServerID(_ITEMIDLIST const *)
0x180020b1c  movzx   edi, word ptr [rbx]
0x180020b1f  mov     r15, rax
0x180020b22  add     rdi, rbx
0x180020b25  mov     rdx, [rsi+68h]; pidl2
0x180020b29  mov     rcx, r15; pidl1
0x180020b2c  call    cs:__imp_ILCombine
0x180020b32  mov     r12, rax
0x180020b35  test    rax, rax
0x180020b38  jz      short loc_180020B52
0x180020b3a  mov     rdx, rdi; pidl2
0x180020b3d  mov     rcx, rax; pidl1
0x180020b40  call    cs:__imp_ILCombine
0x180020b46  mov     rcx, r12; pidl
0x180020b49  mov     r14, rax
0x180020b4c  call    cs:__imp_ILFree
0x180020b52  mov     rcx, r15; pidl
0x180020b55  call    cs:__imp_ILFree
0x180020b5b  mov     r15, [rsp+2B8h+var_278]
0x180020b60  mov     r9d, 1; int
0x180020b66  mov     rdx, r14; struct _ITEMIDLIST *
0x180020b69  mov     r8d, r9d; int
0x180020b6c  mov     rcx, r13; void *
0x180020b6f  call    ?FtpSetCurrentDirectoryPidlWrap@@YAJPEAXPEFBU_ITEMIDLIST@@HH@Z; FtpSetCurrentDirectoryPidlWrap(void *,_ITEMIDLIST const *,int,int)
0x180020b74  mov     edi, eax
0x180020b76  mov     rcx, rsi; this
0x180020b79  test    eax, eax
0x180020b7b  js      short loc_180020B89
0x180020b7d  mov     rdx, rbx; struct _ITEMIDLIST *
0x180020b80  call    ?_SetPidl@CFtpSite@@AEAAJPEFBU_ITEMIDLIST@@@Z; CFtpSite::_SetPidl(_ITEMIDLIST const *)
0x180020b85  mov     edi, eax
0x180020b87  jmp     short loc_180020BEF
0x180020b89  mov     r8, r13; void *
0x180020b8c  xor     edx, edx; struct _ITEMIDLIST *
0x180020b8e  call    ?ReleaseHint@CFtpSite@@QEAAXPEFBU_ITEMIDLIST@@PEAX@Z; CFtpSite::ReleaseHint(_ITEMIDLIST const *,void *)
0x180020b93  cmp     edi, 80072F4Fh
0x180020b99  jnz     short loc_180020BCE
0x180020b9b  lea     rcx, g_csDll; lpCriticalSection
0x180020ba2  call    cs:__imp_EnterCriticalSection
0x180020ba8  mov     rcx, [rsi+18h]; hInternet
0x180020bac  mov     qword ptr [rsi+18h], 0
0x180020bb4  test    rcx, rcx
0x180020bb7  jz      short loc_180020BBF
0x180020bb9  call    cs:__imp_InternetCloseHandle
0x180020bbf  lea     rcx, g_csDll; lpCriticalSection
0x180020bc6  call    cs:__imp_LeaveCriticalSection
0x180020bcc  jmp     short loc_180020BEF
0x180020bce  mov     [rsp+2B8h+var_280], 0; struct IProgressDialog *
0x180020bd7  mov     r8d, edi; int
0x180020bda  mov     rcx, r15; HWND
0x180020bdd  mov     [rsp+2B8h+var_298], 198h; unsigned int
0x180020be5  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x180020bea  mov     edi, 800704C7h
0x180020bef  mov     rcx, r14; pidl
0x180020bf2  call    cs:__imp_ILFree
0x180020bf8  test    rbp, rbp
0x180020bfb  jz      short loc_180020C0C
0x180020bfd  xor     r8d, r8d; unsigned __int16 *
0x180020c00  mov     rcx, rbp; this
0x180020c03  lea     edx, [r8+40h]; unsigned int
0x180020c07  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x180020c0c  mov     eax, edi
0x180020c0e  mov     rcx, [rsp+2B8h+var_58]
0x180020c16  xor     rcx, rsp; StackCookie
0x180020c19  call    __security_check_cookie
0x180020c1e  add     rsp, 278h
0x180020c25  pop     r15
0x180020c27  pop     r14
0x180020c29  pop     r13
0x180020c2b  pop     r12
0x180020c2d  pop     rdi
0x180020c2e  pop     rsi
0x180020c2f  pop     rbp
0x180020c30  pop     rbx
0x180020c31  retn
```
