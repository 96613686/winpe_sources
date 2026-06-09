# CFtpStm_Create(CFtpDir *,_ITEMIDLIST const *,ulong,IStream * *,_ULARGE_INTEGER,_ULARGE_INTEGER,IProgressDialog *,int)

- ea: `0x180020efc`
- end: `0x180021179`
- name: `?CFtpStm_Create@@YAJPEAVCFtpDir@@PEFBU_ITEMIDLIST@@KPEAPEAUIStream@@T_ULARGE_INTEGER@@3PEAUIProgressDialog@@H@Z`
- size: `637`
- prototype: `__int64 __usercall@<rax>(struct CFtpDir *@<rcx>, const struct _ITEMIDLIST *@<rdx>, unsigned int@<r8d>, struct IStream **@<r9>, union _ULARGE_INTEGER, union _ULARGE_INTEGER, struct IProgressDialog *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001237c`
- `0x180017b8c`
- `0x18001b1b8`

## callees

- `0x18000cbfc`
- `0x18000cca4`
- `0x18001ca1c`
- `0x18001cd5c`
- `0x18001fa30`
- `0x180020efc`
- `0x180023adc`
- `0x180024ac8`
- `0x180026ff0`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x180021024`
- `SHELL32!__imp_ILClone` at `0x180021024`
- `SHELL32!__imp_ILFree` at `0x180021110`
- `SHELL32!__imp_ILFree` at `0x18002111b`
- `SHELL32!__imp_ILFree` at `0x180021124`
- `SHELL32!__imp_ILFree` at `0x180021110`
- `SHELL32!__imp_ILFree` at `0x18002111b`
- `SHELL32!__imp_ILFree` at `0x180021124`
- `SHLWAPI!__imp_IUnknown_Set` at `0x180020fb1`
- `SHLWAPI!__imp_IUnknown_Set` at `0x180020fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210f3`
- `WININET!FtpOpenFileA` at `0x1800210e4`
- `WININET!FtpOpenFileA` at `0x1800210e4`

## pseudocode

```c
__int64 __fastcall CFtpStm_Create(
        const struct _ITEMIDLIST **a1,
        const struct _ITEMIDLIST *a2,
        int a3,
        struct IStream **a4,
        union _ULARGE_INTEGER a5,
        union _ULARGE_INTEGER a6,
        IUnknown *punk,
        int a8)
{
  char *v12; // rsi
  signed int CurrentDirectoryPidlWrap; // ebp
  CFtpSite *v14; // rcx
  int Hint; // eax
  const ITEMIDLIST *v16; // rcx
  LPITEMIDLIST v17; // r14
  void *v18; // rcx
  DWORD v19; // edi
  DWORD v20; // ebx
  const CHAR *LastItemWireName; // rax
  HINTERNET v22; // rax
  signed int LastError; // eax
  LPITEMIDLIST v25; // [rsp+40h] [rbp-38h] BYREF
  LPITEMIDLIST pidl; // [rsp+98h] [rbp+20h] BYREF

  v12 = (char *)operator new(0x60u);
  if ( v12 )
  {
    *((_DWORD *)v12 + 2) = 1;
    *(_QWORD *)v12 = &CFtpStm::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
    *((_QWORD *)v12 + 4) = 0;
    *((_QWORD *)v12 + 6) = 0;
    *((_QWORD *)v12 + 7) = 0;
    *((_QWORD *)v12 + 11) = 0;
  }
  else
  {
    v12 = 0;
  }
  *a4 = 0;
  CurrentDirectoryPidlWrap = -2147024882;
  if ( v12 )
  {
    if ( (unsigned int)Pidl_Set(v12 + 48, a2) )
    {
      *((_DWORD *)v12 + 6) = a3;
      IUnknown_Set((struct CFtpDir **)v12 + 4, (struct CFtpDir *)a1);
      IUnknown_Set((IUnknown **)v12 + 7, punk);
      *((union _ULARGE_INTEGER *)v12 + 8) = a5;
      *((union _ULARGE_INTEGER *)v12 + 9) = a6;
      *((_DWORD *)v12 + 20) = a8;
      v14 = (CFtpSite *)a1[2];
      if ( v14 )
      {
        Hint = CFtpSite::GetHint(v14, 0, a1[5], 0, (void **)v12 + 5, 0, 0);
        if ( Hint >= 0 )
        {
          v16 = *(const ITEMIDLIST **)a1[2][34].mkid.abID;
          if ( v16 )
          {
            v17 = ILClone(v16);
            CurrentDirectoryPidlWrap = v17 == 0 ? 0x8007000E : 0;
            if ( !v17 )
              goto LABEL_24;
          }
          else
          {
            v17 = 0;
          }
          v18 = (void *)*((_QWORD *)v12 + 5);
          v25 = 0;
          CurrentDirectoryPidlWrap = FtpGetCurrentDirectoryPidlWrap(v18, &v25);
          if ( CurrentDirectoryPidlWrap >= 0 )
          {
            pidl = 0;
            CurrentDirectoryPidlWrap = FtpPidl_InsertVirtualRoot(v17, a2, &pidl);
            if ( CurrentDirectoryPidlWrap >= 0 )
            {
              CurrentDirectoryPidlWrap = FtpSetCurrentDirectoryPidlWrap(*((void **)v12 + 5), pidl, 1, 1);
              if ( CurrentDirectoryPidlWrap >= 0 )
              {
                v19 = *(_DWORD *)&a1[2][44].mkid.cb;
                Pidl_Set(v12 + 88, v25);
                v20 = *((_DWORD *)v12 + 6);
                LastItemWireName = FtpPidl_GetLastItemWireName(a2);
                CurrentDirectoryPidlWrap = 0;
                v22 = FtpOpenFileA(*((HINTERNET *)v12 + 5), LastItemWireName, v20, v19, 0);
                *((_QWORD *)v12 + 2) = v22;
                if ( !v22 )
                {
                  LastError = GetLastError();
                  CurrentDirectoryPidlWrap = LastError;
                  if ( LastError > 0 )
                    CurrentDirectoryPidlWrap = (unsigned __int16)LastError | 0x80070000;
                }
              }
              ILFree(pidl);
            }
            ILFree(v25);
          }
          ILFree(v17);
          if ( CurrentDirectoryPidlWrap < 0 )
            goto LABEL_24;
          Hint = (**(__int64 (__fastcall ***)(void *, GUID *, struct IStream **))v12)(v12, &IID_IStream, a4);
        }
        CurrentDirectoryPidlWrap = Hint;
      }
      else
      {
        CurrentDirectoryPidlWrap = -2147467259;
      }
    }
LABEL_24:
    (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  return (unsigned int)CurrentDirectoryPidlWrap;
}

```

## disassembly

```asm
0x180020efc  mov     [rsp+arg_0], rbx
0x180020f01  mov     [rsp+arg_8], rbp
0x180020f06  push    rsi
0x180020f07  push    rdi
0x180020f08  push    r12
0x180020f0a  push    r14
0x180020f0c  push    r15
0x180020f0e  sub     rsp, 50h
0x180020f12  mov     rbx, rcx
0x180020f15  mov     r12, r9
0x180020f18  mov     ecx, 60h ; '`'; unsigned __int64
0x180020f1d  mov     edi, r8d
0x180020f20  mov     r15, rdx
0x180020f23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020f28  mov     rsi, rax
0x180020f2b  test    rax, rax
0x180020f2e  jz      short loc_180020F6A
0x180020f30  lea     rax, ??_7CFtpStm@@6B@; const CFtpStm::`vftable'
0x180020f37  mov     dword ptr [rsi+8], 1
0x180020f3e  mov     [rsi], rax
0x180020f41  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180020f48  mov     qword ptr [rsi+20h], 0
0x180020f50  mov     qword ptr [rsi+30h], 0
0x180020f58  mov     qword ptr [rsi+38h], 0
0x180020f60  mov     qword ptr [rsi+58h], 0
0x180020f68  jmp     short loc_180020F6C
0x180020f6a  xor     esi, esi
0x180020f6c  mov     qword ptr [r12], 0
0x180020f74  mov     ebp, 8007000Eh
0x180020f79  test    rsi, rsi
0x180020f7c  jz      loc_18002115E
0x180020f82  lea     rcx, [rsi+30h]
0x180020f86  mov     rdx, r15
0x180020f89  call    Pidl_Set
0x180020f8e  test    eax, eax
0x180020f90  jz      loc_18002114F
0x180020f96  lea     rcx, [rsi+20h]; struct CFtpDir **
0x180020f9a  mov     [rsi+18h], edi
0x180020f9d  mov     rdx, rbx; struct CFtpDir *
0x180020fa0  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x180020fa5  mov     rdx, [rsp+78h+punk]; punk
0x180020fad  lea     rcx, [rsi+38h]; ppunk
0x180020fb1  call    cs:__imp_IUnknown_Set
0x180020fb7  mov     rax, qword ptr [rsp+78h+arg_20]
0x180020fbf  mov     [rsi+40h], rax
0x180020fc3  mov     rax, qword ptr [rsp+78h+arg_28]
0x180020fcb  mov     [rsi+48h], rax
0x180020fcf  mov     eax, [rsp+78h+arg_38]
0x180020fd6  mov     [rsi+50h], eax
0x180020fd9  mov     rcx, [rbx+10h]; this
0x180020fdd  test    rcx, rcx
0x180020fe0  jz      loc_18002114A
0x180020fe6  mov     r8, [rbx+28h]; struct _ITEMIDLIST *
0x180020fea  lea     rax, [rsi+28h]
0x180020fee  mov     [rsp+78h+var_48], 0; struct CFtpFolder *
0x180020ff7  xor     r9d, r9d; struct CStatusBar *
0x180020ffa  mov     [rsp+78h+var_50], 0; struct IUnknown *
0x180021003  xor     edx, edx; HWND
0x180021005  mov     [rsp+78h+dwContext], rax; void **
0x18002100a  call    ?GetHint@CFtpSite@@QEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEAVCStatusBar@@PEAPEAXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpSite::GetHint(HWND__ *,_ITEMIDLIST const *,CStatusBar *,void * *,IUnknown *,CFtpFolder *)
0x18002100f  test    eax, eax
0x180021011  js      loc_180021146
0x180021017  mov     rax, [rbx+10h]
0x18002101b  mov     rcx, [rax+68h]; pidl
0x18002101f  test    rcx, rcx
0x180021022  jz      short loc_180021040
0x180021024  call    cs:__imp_ILClone
0x18002102a  mov     r14, rax
0x18002102d  neg     rax
0x180021030  sbb     ecx, ecx
0x180021032  not     ecx
0x180021034  and     ebp, ecx
0x180021036  test    r14, r14
0x180021039  jnz     short loc_180021043
0x18002103b  jmp     loc_18002114F
0x180021040  xor     r14d, r14d
0x180021043  mov     rcx, [rsi+28h]; void *
0x180021047  lea     rdx, [rsp+78h+var_38]; struct _ITEMIDLIST **
0x18002104c  mov     [rsp+78h+var_38], 0
0x180021055  call    ?FtpGetCurrentDirectoryPidlWrap@@YAJPEAXPEAPEFAU_ITEMIDLIST@@@Z; FtpGetCurrentDirectoryPidlWrap(void *,_ITEMIDLIST * *)
0x18002105a  mov     ebp, eax
0x18002105c  test    eax, eax
0x18002105e  js      loc_180021121
0x180021064  lea     r8, [rsp+78h+pidl]; struct _ITEMIDLIST **
0x18002106c  mov     [rsp+78h+pidl], 0
0x180021078  mov     rdx, r15; struct _ITEMIDLIST *
0x18002107b  mov     rcx, r14; pidl1
0x18002107e  call    ?FtpPidl_InsertVirtualRoot@@YAJPEFBU_ITEMIDLIST@@0PEAPEFAU1@@Z; FtpPidl_InsertVirtualRoot(_ITEMIDLIST const *,_ITEMIDLIST const *,_ITEMIDLIST * *)
0x180021083  mov     ebp, eax
0x180021085  test    eax, eax
0x180021087  js      loc_180021116
0x18002108d  mov     rdx, [rsp+78h+pidl]; struct _ITEMIDLIST *
0x180021095  mov     r8d, 1; int
0x18002109b  mov     rcx, [rsi+28h]; void *
0x18002109f  mov     r9d, r8d; int
0x1800210a2  call    ?FtpSetCurrentDirectoryPidlWrap@@YAJPEAXPEFBU_ITEMIDLIST@@HH@Z; FtpSetCurrentDirectoryPidlWrap(void *,_ITEMIDLIST const *,int,int)
0x1800210a7  mov     ebp, eax
0x1800210a9  test    eax, eax
0x1800210ab  js      short loc_180021108
0x1800210ad  mov     rax, [rbx+10h]
0x1800210b1  lea     rcx, [rsi+58h]
0x1800210b5  mov     rdx, [rsp+78h+var_38]
0x1800210ba  mov     edi, [rax+84h]
0x1800210c0  call    Pidl_Set
0x1800210c5  mov     ebx, [rsi+18h]
0x1800210c8  mov     rcx, r15; struct _ITEMIDLIST *
0x1800210cb  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x1800210d0  mov     rcx, [rsi+28h]; hConnect
0x1800210d4  xor     ebp, ebp
0x1800210d6  mov     r9d, edi; dwFlags
0x1800210d9  mov     [rsp+78h+dwContext], rbp; dwContext
0x1800210de  mov     r8d, ebx; dwAccess
0x1800210e1  mov     rdx, rax; lpszFileName
0x1800210e4  call    cs:__imp_FtpOpenFileA
0x1800210ea  mov     [rsi+10h], rax
0x1800210ee  test    rax, rax
0x1800210f1  jnz     short loc_180021108
0x1800210f3  call    cs:__imp_GetLastError
0x1800210f9  mov     ebp, eax
0x1800210fb  test    eax, eax
0x1800210fd  jle     short loc_180021108
0x1800210ff  movzx   ebp, ax
0x180021102  or      ebp, 80070000h
0x180021108  mov     rcx, [rsp+78h+pidl]; pidl
0x180021110  call    cs:__imp_ILFree
0x180021116  mov     rcx, [rsp+78h+var_38]; pidl
0x18002111b  call    cs:__imp_ILFree
0x180021121  mov     rcx, r14; pidl
0x180021124  call    cs:__imp_ILFree
0x18002112a  test    ebp, ebp
0x18002112c  js      short loc_18002114F
0x18002112e  mov     rax, [rsi]
0x180021131  lea     rdx, IID_IStream
0x180021138  mov     r8, r12
0x18002113b  mov     rcx, rsi
0x18002113e  mov     rax, [rax]
0x180021141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021146  mov     ebp, eax
0x180021148  jmp     short loc_18002114F
0x18002114a  mov     ebp, 80004005h
0x18002114f  mov     rax, [rsi]
0x180021152  mov     rcx, rsi
0x180021155  mov     rax, [rax+10h]
0x180021159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002115e  lea     r11, [rsp+78h+var_28]
0x180021163  mov     eax, ebp
0x180021165  mov     rbx, [r11+30h]
0x180021169  mov     rbp, [r11+38h]
0x18002116d  mov     rsp, r11
0x180021170  pop     r15
0x180021172  pop     r14
0x180021174  pop     r12
0x180021176  pop     rdi
0x180021177  pop     rsi
0x180021178  retn
```
