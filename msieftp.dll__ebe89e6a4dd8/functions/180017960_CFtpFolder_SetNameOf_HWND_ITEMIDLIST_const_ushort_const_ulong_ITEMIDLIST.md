# CFtpFolder::SetNameOf(HWND__ *,_ITEMIDLIST const *,ushort const *,ulong,_ITEMIDLIST * *)

- ea: `0x180017960`
- end: `0x180017b84`
- name: `?SetNameOf@CFtpFolder@@UEAAJPEAUHWND__@@PEFBU_ITEMIDLIST@@PEBGKPEAPEFAU3@@Z`
- size: `548`
- prototype: `__int64 __usercall@<rax>(CFtpFolder *__hidden this@<rcx>, HWND@<rdx>, const struct _ITEMIDLIST *@<r8>, const unsigned __int16 *@<r9>, unsigned int, struct _ITEMIDLIST **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180002240`
- `0x180011534`
- `0x180016b4c`
- `0x180017960`
- `0x180018d28`
- `0x18001ca1c`
- `0x18001ce78`
- `0x180024134`
- `0x180025830`
- `0x180028010`

## import_xrefs

- `SHLWAPI!PathFindExtensionW` at `0x180017a2b`
- `SHLWAPI!PathFindExtensionW` at `0x180017a2b`
- `SHLWAPI!PathRemoveBlanksW` at `0x180017a20`
- `SHLWAPI!PathRemoveBlanksW` at `0x180017a20`
- `SHLWAPI!PathFindExtensionA` at `0x180017a61`
- `SHLWAPI!PathFindExtensionA` at `0x180017a61`
- `SHLWAPI!__imp_IUnknown_EnableModeless` at `0x180017a84`
- `SHLWAPI!__imp_IUnknown_EnableModeless` at `0x180017aee`
- `SHLWAPI!__imp_IUnknown_EnableModeless` at `0x180017a84`
- `SHLWAPI!__imp_IUnknown_EnableModeless` at `0x180017aee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017aa4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017ac4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017aa4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017ac4`

## pseudocode

```c
__int64 __fastcall CFtpFolder::SetNameOf(
        CFtpFolder *this,
        HWND a2,
        const struct _ITEMIDLIST *a3,
        WCHAR *a4,
        unsigned int a5,
        struct _ITEMIDLIST **a6)
{
  CFtpDir *FtpDir; // r14
  __int64 v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  const CHAR *LastItemWireName; // rax
  unsigned int v17; // edi
  int v18; // ebx
  int v19; // eax
  int v20; // edx
  unsigned int v21; // r9d
  unsigned int v22; // [rsp+28h] [rbp-CA0h]
  unsigned int v23; // [rsp+28h] [rbp-CA0h]
  unsigned int v24; // [rsp+30h] [rbp-C98h]
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C88h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp-A78h] BYREF
  WCHAR v27[1040]; // [rsp+460h] [rbp-868h] BYREF

  if ( a6 )
    *a6 = 0;
  if ( !CFtpFolder::_IsValidPidlParameter(this, a3) )
    return 2147942487LL;
  FtpDir = CFtpFolder::GetFtpDir(this);
  if ( !FtpDir )
    return 2147942414LL;
  v12 = 2147483646;
  v13 = pszPath;
  v14 = 260;
  do
  {
    if ( !v12 )
      break;
    if ( !*a4 )
      break;
    *v13++ = *a4++;
    --v12;
    --v14;
  }
  while ( v14 );
  v15 = v13 - 1;
  if ( v14 )
    v15 = v13;
  *v15 = 0;
  PathRemoveBlanksW(pszPath);
  if ( *PathFindExtensionW(pszPath)
    || (unsigned int)FtpPidl_IsDirectory(a3, 0)
    || (LastItemWireName = FtpPidl_GetLastItemWireName(a3)) == 0
    || !*PathFindExtensionA(LastItemWireName)
    || !a2
    || (v17 = 1,
        IUnknown_EnableModeless(*((_QWORD *)this + 4), 0),
        LoadStringW(g_hinst, 0x1A5u, Buffer, 260),
        LoadStringW(g_hinst, 0x1A4u, v27, 1040),
        v18 = _SHFusionMessageBox(a2, v27, Buffer, 0x34u),
        IUnknown_EnableModeless(*((_QWORD *)this + 4), 1),
        v18 != 7) )
  {
    v19 = CFtpDir::SetNameOf(FtpDir, this, a2, a3, pszPath, v22, a6);
    v17 = v19;
    if ( v19 < 0 )
    {
      if ( v19 != -2147023673 )
      {
        if ( a2 )
          DisplayWininetError(a2, v20, v19, v21, 0x197u, v23, v24, 0);
      }
      v17 = 1;
    }
  }
  (*(void (__fastcall **)(CFtpDir *))(*(_QWORD *)FtpDir + 16LL))(FtpDir);
  return v17;
}

```

## disassembly

```asm
0x180017960  mov     [rsp+arg_18], rbx
0x180017965  push    rbp
0x180017966  push    rsi
0x180017967  push    rdi
0x180017968  push    r12
0x18001796a  push    r13
0x18001796c  push    r14
0x18001796e  push    r15
0x180017970  sub     rsp, 0C90h
0x180017977  mov     rax, cs:__security_cookie
0x18001797e  xor     rax, rsp
0x180017981  mov     [rsp+0CC8h+var_48], rax
0x180017989  mov     r12, [rsp+0CC8h+arg_28]
0x180017991  xor     r13d, r13d
0x180017994  mov     rbx, r9
0x180017997  mov     rbp, r8
0x18001799a  mov     rsi, rdx
0x18001799d  mov     r15, rcx
0x1800179a0  test    r12, r12
0x1800179a3  jz      short loc_1800179A9
0x1800179a5  mov     [r12], r13
0x1800179a9  mov     rdx, rbp; struct _ITEMIDLIST *
0x1800179ac  call    ?_IsValidPidlParameter@CFtpFolder@@QEAAHPEFBU_ITEMIDLIST@@@Z; CFtpFolder::_IsValidPidlParameter(_ITEMIDLIST const *)
0x1800179b1  test    eax, eax
0x1800179b3  jnz     short loc_1800179BF
0x1800179b5  mov     eax, 80070057h
0x1800179ba  jmp     loc_180017B59
0x1800179bf  mov     rcx, r15; this
0x1800179c2  call    ?GetFtpDir@CFtpFolder@@QEAAPEAVCFtpDir@@XZ; CFtpFolder::GetFtpDir(void)
0x1800179c7  mov     r14, rax
0x1800179ca  test    rax, rax
0x1800179cd  jnz     short loc_1800179D9
0x1800179cf  mov     eax, 8007000Eh
0x1800179d4  jmp     loc_180017B59
0x1800179d9  mov     ecx, 7FFFFFFEh
0x1800179de  lea     rax, [rsp+0CC8h+pszPath]
0x1800179e3  mov     edx, 104h
0x1800179e8  test    rcx, rcx
0x1800179eb  jz      short loc_180017A0C
0x1800179ed  movzx   r8d, word ptr [rbx]
0x1800179f1  test    r8w, r8w
0x1800179f5  jz      short loc_180017A0C
0x1800179f7  mov     [rax], r8w
0x1800179fb  add     rbx, 2
0x1800179ff  add     rax, 2
0x180017a03  dec     rcx
0x180017a06  sub     rdx, 1
0x180017a0a  jnz     short loc_1800179E8
0x180017a0c  test    rdx, rdx
0x180017a0f  lea     rcx, [rax-2]
0x180017a13  cmovnz  rcx, rax
0x180017a17  mov     [rcx], r13w
0x180017a1b  lea     rcx, [rsp+0CC8h+pszPath]; pszPath
0x180017a20  call    cs:__imp_PathRemoveBlanksW
0x180017a26  lea     rcx, [rsp+0CC8h+pszPath]; pszPath
0x180017a2b  call    cs:__imp_PathFindExtensionW
0x180017a31  cmp     r13w, [rax]
0x180017a35  jnz     loc_180017AF9
0x180017a3b  xor     edx, edx; int
0x180017a3d  mov     rcx, rbp; struct _ITEMIDLIST *
0x180017a40  call    ?FtpPidl_IsDirectory@@YAHPEFBU_ITEMIDLIST@@H@Z; FtpPidl_IsDirectory(_ITEMIDLIST const *,int)
0x180017a45  test    eax, eax
0x180017a47  jnz     loc_180017AF9
0x180017a4d  mov     rcx, rbp; struct _ITEMIDLIST *
0x180017a50  call    ?FtpPidl_GetLastItemWireName@@YAPEBDPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetLastItemWireName(_ITEMIDLIST const *)
0x180017a55  test    rax, rax
0x180017a58  jz      loc_180017AF9
0x180017a5e  mov     rcx, rax; pszPath
0x180017a61  call    cs:__imp_PathFindExtensionA
0x180017a67  cmp     [rax], r13b
0x180017a6a  jz      loc_180017AF9
0x180017a70  test    rsi, rsi
0x180017a73  jz      loc_180017AF9
0x180017a79  mov     rcx, [r15+20h]
0x180017a7d  xor     edx, edx
0x180017a7f  mov     edi, 1
0x180017a84  call    cs:__imp_IUnknown_EnableModeless
0x180017a8a  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180017a91  lea     r8, [rsp+0CC8h+Buffer]; lpBuffer
0x180017a99  mov     r9d, 104h; cchBufferMax
0x180017a9f  mov     edx, 1A5h; uID
0x180017aa4  call    cs:__imp_LoadStringW
0x180017aaa  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180017ab1  lea     r8, [rsp+0CC8h+var_868]; lpBuffer
0x180017ab9  mov     r9d, 410h; cchBufferMax
0x180017abf  mov     edx, 1A4h; uID
0x180017ac4  call    cs:__imp_LoadStringW
0x180017aca  lea     r9d, [rdi+33h]; unsigned int
0x180017ace  mov     rcx, rsi; HWND
0x180017ad1  lea     r8, [rsp+0CC8h+Buffer]; unsigned __int16 *
0x180017ad9  lea     rdx, [rsp+0CC8h+var_868]; unsigned __int16 *
0x180017ae1  call    ?_SHFusionMessageBox@@YAHPEAUHWND__@@PEBG1I@Z; _SHFusionMessageBox(HWND__ *,ushort const *,ushort const *,uint)
0x180017ae6  mov     rcx, [r15+20h]
0x180017aea  mov     edx, edi
0x180017aec  mov     ebx, eax
0x180017aee  call    cs:__imp_IUnknown_EnableModeless
0x180017af4  cmp     ebx, 7
0x180017af7  jz      short loc_180017B48
0x180017af9  lea     rax, [rsp+0CC8h+pszPath]
0x180017afe  mov     [rsp+0CC8h+var_C98], r12; unsigned int
0x180017b03  mov     r9, rbp; struct _ITEMIDLIST *
0x180017b06  mov     [rsp+0CC8h+var_CA8], rax; unsigned __int16 *
0x180017b0b  mov     r8, rsi; HWND
0x180017b0e  mov     rdx, r15; struct CFtpFolder *
0x180017b11  mov     rcx, r14; this
0x180017b14  call    ?SetNameOf@CFtpDir@@QEAAJPEAVCFtpFolder@@PEAUHWND__@@PEFBU_ITEMIDLIST@@PEBGKPEAPEFAU4@@Z; CFtpDir::SetNameOf(CFtpFolder *,HWND__ *,_ITEMIDLIST const *,ushort const *,ulong,_ITEMIDLIST * *)
0x180017b19  mov     edi, eax
0x180017b1b  test    eax, eax
0x180017b1d  jns     short loc_180017B48
0x180017b1f  cmp     eax, 800704C7h
0x180017b24  jz      short loc_180017B43
0x180017b26  test    rsi, rsi
0x180017b29  jz      short loc_180017B43
0x180017b2b  mov     [rsp+0CC8h+var_C90], r13; struct IProgressDialog *
0x180017b30  mov     r8d, eax; int
0x180017b33  mov     rcx, rsi; HWND
0x180017b36  mov     dword ptr [rsp+0CC8h+var_CA8], 197h; unsigned int
0x180017b3e  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x180017b43  mov     edi, 1
0x180017b48  mov     rax, [r14]
0x180017b4b  mov     rcx, r14
0x180017b4e  mov     rax, [rax+10h]
0x180017b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b57  mov     eax, edi
0x180017b59  mov     rcx, [rsp+0CC8h+var_48]
0x180017b61  xor     rcx, rsp; StackCookie
0x180017b64  call    __security_check_cookie
0x180017b69  mov     rbx, [rsp+0CC8h+arg_18]
0x180017b71  add     rsp, 0C90h
0x180017b78  pop     r15
0x180017b7a  pop     r14
0x180017b7c  pop     r13
0x180017b7e  pop     r12
0x180017b80  pop     rdi
0x180017b81  pop     rsi
0x180017b82  pop     rbp
0x180017b83  retn
```
