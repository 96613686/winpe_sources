# InstallHookHelper

- ea: `0x1400293b8`
- end: `0x1400294a3`
- name: `InstallHookHelper`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400293a0`

## callees

- `0x140001020`
- `0x140003f60`
- `0x1400293b8`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400293e0`
- `KERNEL32!LoadLibraryW` at `0x1400293e0`
- `KERNEL32!GetProcAddress` at `0x1400293f5`
- `KERNEL32!GetProcAddress` at `0x1400293f5`
- `KERNEL32!GetLastError` at `0x140029426`
- `KERNEL32!GetLastError` at `0x140029426`

## string_xrefs

- `0x1400293d9`: `mscoree.dll`
- `0x1400293eb`: `CLRCreateInstance`
- `0x140029410`: `Could not locate appropriate CLR version. Try rebooting, reinstalling.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 InstallHookHelper()
{
  FARPROC ProcAddress; // rax
  HMODULE LibraryW; // rax
  const unsigned __int16 *v2; // r9
  signed int LastError; // ecx
  __int64 result; // rax
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  ProcAddress = (FARPROC)qword_14009DBB8;
  if ( qword_14009DBB8
    || ((LibraryW = LoadLibraryW(L"mscoree.dll")) == 0
      ? (ProcAddress = (FARPROC)qword_14009DBB8)
      : (FARPROC)(ProcAddress = GetProcAddress(LibraryW, "CLRCreateInstance"), qword_14009DBB8 = (__int64)ProcAddress),
        ProcAddress) )
  {
    v7 = 0;
    v5 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
           &CLSID_CLRMetaHost,
           &GUID_d332db9e_b9b3_4125_8207_a14884f53216,
           &v7);
    v6 = v7;
    if ( v5 >= 0 )
    {
      if ( v7 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, void (__fastcall *)(struct ICLRRuntimeInfo *, int (*)(void), int (*)(void))))(*(_QWORD *)v7 + 56LL))(
               v7,
               CLockClr::RuntimeLoadedCallback);
        v6 = v7;
      }
      else
      {
        v5 = -2147418113;
      }
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return (unsigned int)v5;
  }
  else
  {
    ActivityLog::LogEntry(
      (ActivityLog *)1,
      (int)L"VisualStudio",
      L"Could not locate appropriate CLR version. Try rebooting, reinstalling.",
      v2);
    LastError = GetLastError();
    result = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return (unsigned int)LastError;
  }
  return result;
}

```

## disassembly

```asm
0x1400293b8  push    rbx
0x1400293ba  sub     rsp, 30h
0x1400293be  mov     rax, cs:__security_cookie
0x1400293c5  xor     rax, rsp
0x1400293c8  mov     [rsp+38h+var_10], rax
0x1400293cd  mov     rax, cs:qword_14009DBB8
0x1400293d4  test    rax, rax
0x1400293d7  jnz     short loc_14002943D
0x1400293d9  lea     rcx, aMscoreeDll_0; "mscoree.dll"
0x1400293e0  call    cs:__imp_LoadLibraryW
0x1400293e6  test    rax, rax
0x1400293e9  jz      short loc_140029404
0x1400293eb  lea     rdx, aClrcreateinsta; "CLRCreateInstance"
0x1400293f2  mov     rcx, rax; hModule
0x1400293f5  call    cs:__imp_GetProcAddress
0x1400293fb  mov     cs:qword_14009DBB8, rax
0x140029402  jmp     short loc_14002940B
0x140029404  mov     rax, cs:qword_14009DBB8
0x14002940b  test    rax, rax
0x14002940e  jnz     short loc_14002943D
0x140029410  lea     r8, aCouldNotLocate_2; "Could not locate appropriate CLR versio"...
0x140029417  lea     rdx, aVisualstudio; "VisualStudio"
0x14002941e  lea     ecx, [rax+1]; this
0x140029421  call    ?LogEntry@ActivityLog@@YAJHPEBG0@Z; ActivityLog::LogEntry(int,ushort const *,ushort const *)
0x140029426  call    cs:__imp_GetLastError
0x14002942c  mov     ecx, eax
0x14002942e  movzx   eax, ax
0x140029431  or      eax, 80070000h
0x140029436  test    ecx, ecx
0x140029438  cmovle  eax, ecx
0x14002943b  jmp     short loc_140029490
0x14002943d  and     [rsp+38h+var_18], 0
0x140029443  lea     r8, [rsp+38h+var_18]
0x140029448  lea     rdx, _GUID_d332db9e_b9b3_4125_8207_a14884f53216
0x14002944f  lea     rcx, CLSID_CLRMetaHost
0x140029456  call    rax ; qword_14009DBB8
0x140029458  mov     ebx, eax
0x14002945a  mov     rcx, [rsp+38h+var_18]
0x14002945f  test    eax, eax
0x140029461  js      short loc_140029483
0x140029463  test    rcx, rcx
0x140029466  jz      short loc_14002947E
0x140029468  mov     rax, [rcx]
0x14002946b  lea     rdx, ?RuntimeLoadedCallback@CLockClr@@CAXPEAUICLRRuntimeInfo@@P6AJXZ1@Z; CLockClr::RuntimeLoadedCallback(ICLRRuntimeInfo *,long (*)(void),long (*)(void))
0x140029472  call    qword ptr [rax+38h]
0x140029475  mov     ebx, eax
0x140029477  mov     rcx, [rsp+38h+var_18]
0x14002947c  jmp     short loc_140029483
0x14002947e  mov     ebx, 8000FFFFh
0x140029483  test    rcx, rcx
0x140029486  jz      short loc_14002948E
0x140029488  mov     rax, [rcx]
0x14002948b  call    qword ptr [rax+10h]
0x14002948e  mov     eax, ebx
0x140029490  mov     rcx, [rsp+38h+var_10]
0x140029495  xor     rcx, rsp; StackCookie
0x140029498  call    __security_check_cookie
0x14002949d  add     rsp, 30h
0x1400294a1  pop     rbx
0x1400294a2  retn
```
