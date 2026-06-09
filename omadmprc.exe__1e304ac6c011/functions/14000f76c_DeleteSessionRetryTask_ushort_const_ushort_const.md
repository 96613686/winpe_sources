# DeleteSessionRetryTask(ushort const *,ushort const *)

- ea: `0x14000f76c`
- end: `0x14000f95e`
- name: `?DeleteSessionRetryTask@@YAJPEBG0@Z`
- size: `498`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14000fff0`

## callees

- `0x140008504`
- `0x140008ea0`
- `0x14000ed04`
- `0x14000f76c`
- `0x14000fc54`
- `0x140015690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000f87b`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f92d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f87b`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000f92d`
- `DMCmnUtils!DmDeleteTask` at `0x14000f8fc`
- `DMCmnUtils!DmDeleteTask` at `0x14000f8fc`
- `DMCmnUtils!DmIsTaskScheduled` at `0x14000f8d9`
- `DMCmnUtils!DmIsTaskScheduled` at `0x14000f8d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000f7eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000f7eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f914`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f914`

## string_xrefs

- `0x14000f8a1`: `Retry Schedule created for incomplete session %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteSessionRetryTask(const unsigned __int16 *a1, WCHAR *a2)
{
  LSTATUS v4; // eax
  signed int InitiationIDFromKeyPath; // ebx
  __int64 v6; // rax
  __int64 v7; // rdx
  void **v9; // r9
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  int v12[4]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY *p_hKey; // [rsp+48h] [rbp-B8h]
  char v14; // [rsp+50h] [rbp-B0h]
  _BYTE v15[32]; // [rsp+58h] [rbp-A8h] BYREF
  void *v16[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v17; // [rsp+88h] [rbp-78h]
  unsigned __int64 v18; // [rsp+90h] [rbp-70h]
  unsigned __int16 v19[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  hKey = 0;
  v12[0] = 0;
  v18 = 7;
  v17 = 0;
  LOWORD(v16[0]) = 0;
  p_hKey = &hKey;
  v14 = 1;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x2001Fu, &hKey);
  InitiationIDFromKeyPath = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      InitiationIDFromKeyPath = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_19;
  }
  v6 = std::wstring::wstring(v15, a2);
  InitiationIDFromKeyPath = GetInitiationIDFromKeyPath(v6, v16);
  if ( InitiationIDFromKeyPath < 0 )
  {
    v7 = 1987;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)(unsigned int)InitiationIDFromKeyPath,
      phkResult);
LABEL_19:
    if ( hKey )
      RegCloseKey(hKey);
    if ( v18 >= 8 )
      operator delete(v16[0]);
    return (unsigned int)InitiationIDFromKeyPath;
  }
  if ( v17 )
  {
    v9 = v16;
    if ( v18 >= 8 )
      v9 = (void **)v16[0];
    InitiationIDFromKeyPath = StringCchPrintfW(v19, 0x104u, L"Retry Schedule created for incomplete session %s", v9);
    if ( InitiationIDFromKeyPath >= 0 )
    {
      InitiationIDFromKeyPath = DmIsTaskScheduled(L"\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry", a1, v19, v12);
      if ( v12[0] )
        InitiationIDFromKeyPath = DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt\\SessionRetry", a1, v19);
      goto LABEL_19;
    }
    v7 = 2000;
    goto LABEL_6;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v18 >= 8 )
    operator delete(v16[0]);
  return 2147549183LL;
}

```

## disassembly

```asm
0x14000f76c  mov     [rsp-8+arg_10], rbx
0x14000f771  push    rbp
0x14000f772  push    rsi
0x14000f773  push    rdi
0x14000f774  lea     rbp, [rsp-1C0h]
0x14000f77c  sub     rsp, 2C0h
0x14000f783  mov     rax, cs:__security_cookie
0x14000f78a  xor     rax, rsp
0x14000f78d  mov     [rbp+1D0h+var_20], rax
0x14000f794  mov     rsi, rdx
0x14000f797  mov     rdi, rcx
0x14000f79a  mov     [rsp+2D0h+hKey], 0
0x14000f7a3  mov     [rsp+2D0h+var_298], 0
0x14000f7ab  mov     [rbp+1D0h+var_240], 7
0x14000f7b3  mov     [rbp+1D0h+var_248], 0
0x14000f7bb  xor     eax, eax
0x14000f7bd  mov     word ptr [rsp+2D0h+var_258], ax
0x14000f7c2  lea     rax, [rsp+2D0h+hKey]
0x14000f7c7  mov     [rsp+2D0h+var_288], rax
0x14000f7cc  mov     [rsp+2D0h+var_280], 1
0x14000f7d1  lea     rax, [rsp+2D0h+hKey]
0x14000f7d6  mov     qword ptr [rsp+2D0h+phkResult], rax; int
0x14000f7db  mov     r9d, 2001Fh; samDesired
0x14000f7e1  xor     r8d, r8d; ulOptions
0x14000f7e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000f7eb  call    cs:__imp_RegOpenKeyExW
0x14000f7f2  nop     dword ptr [rax+rax+00h]
0x14000f7f7  mov     ebx, eax
0x14000f7f9  test    eax, eax
0x14000f7fb  jz      short loc_14000F811
0x14000f7fd  jle     loc_14000F90A
0x14000f803  movzx   ebx, ax
0x14000f806  or      ebx, 80070000h
0x14000f80c  jmp     loc_14000F90A
0x14000f811  mov     rdx, rsi; Src
0x14000f814  lea     rcx, [rsp+2D0h+var_278]; void *
0x14000f819  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000f81e  lea     rdx, [rsp+2D0h+var_258]
0x14000f823  mov     rcx, rax
0x14000f826  call    ?GetInitiationIDFromKeyPath@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetInitiationIDFromKeyPath(std::wstring,std::wstring &)
0x14000f82b  mov     ebx, eax
0x14000f82d  test    eax, eax
0x14000f82f  jns     short loc_14000F851
0x14000f831  mov     edx, 7C3h; void *
0x14000f836  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14000f83d  mov     r9d, ebx; char *
0x14000f840  mov     rcx, [rbp+1D8h]; this
0x14000f847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000f84c  jmp     loc_14000F90A
0x14000f851  cmp     [rbp+1D0h+var_248], 0
0x14000f856  jnz     short loc_14000F891
0x14000f858  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14000f85d  test    rcx, rcx
0x14000f860  jz      short loc_14000F86F
0x14000f862  call    cs:__imp_RegCloseKey
0x14000f869  nop     dword ptr [rax+rax+00h]
0x14000f86e  nop
0x14000f86f  cmp     [rbp+1D0h+var_240], 8
0x14000f874  jb      short loc_14000F887
0x14000f876  mov     rcx, [rsp+2D0h+var_258]
0x14000f87b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f882  nop     dword ptr [rax+rax+00h]
0x14000f887  mov     eax, 8000FFFFh
0x14000f88c  jmp     loc_14000F93B
0x14000f891  lea     r9, [rsp+2D0h+var_258]
0x14000f896  cmp     [rbp+1D0h+var_240], 8
0x14000f89b  cmovnb  r9, [rsp+2D0h+var_258]
0x14000f8a1  lea     r8, aRetryScheduleC_0; "Retry Schedule created for incomplete s"...
0x14000f8a8  mov     edx, 104h; unsigned __int64
0x14000f8ad  lea     rcx, [rbp+1D0h+var_230]; unsigned __int16 *
0x14000f8b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f8b6  mov     ebx, eax
0x14000f8b8  test    eax, eax
0x14000f8ba  jns     short loc_14000F8C6
0x14000f8bc  mov     edx, 7D0h
0x14000f8c1  jmp     loc_14000F836
0x14000f8c6  lea     r9, [rsp+2D0h+var_298]
0x14000f8cb  lea     r8, [rbp+1D0h+var_230]
0x14000f8cf  mov     rdx, rdi
0x14000f8d2  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt\\S"...
0x14000f8d9  call    cs:__imp_?DmIsTaskScheduled@@YAJPEBG00PEAH@Z; DmIsTaskScheduled(ushort const *,ushort const *,ushort const *,int *)
0x14000f8e0  nop     dword ptr [rax+rax+00h]
0x14000f8e5  mov     ebx, eax
0x14000f8e7  cmp     [rsp+2D0h+var_298], 0
0x14000f8ec  jz      short loc_14000F90A
0x14000f8ee  lea     r8, [rbp+1D0h+var_230]
0x14000f8f2  mov     rdx, rdi
0x14000f8f5  lea     rcx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\EnterpriseMgmt\\S"...
0x14000f8fc  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x14000f903  nop     dword ptr [rax+rax+00h]
0x14000f908  mov     ebx, eax
0x14000f90a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14000f90f  test    rcx, rcx
0x14000f912  jz      short loc_14000F921
0x14000f914  call    cs:__imp_RegCloseKey
0x14000f91b  nop     dword ptr [rax+rax+00h]
0x14000f920  nop
0x14000f921  cmp     [rbp+1D0h+var_240], 8
0x14000f926  jb      short loc_14000F939
0x14000f928  mov     rcx, [rsp+2D0h+var_258]
0x14000f92d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000f934  nop     dword ptr [rax+rax+00h]
0x14000f939  mov     eax, ebx
0x14000f93b  mov     rcx, [rbp+1D0h+var_20]
0x14000f942  xor     rcx, rsp; StackCookie
0x14000f945  call    __security_check_cookie
0x14000f94a  mov     rbx, [rsp+2D0h+arg_10]
0x14000f952  add     rsp, 2C0h
0x14000f959  pop     rdi
0x14000f95a  pop     rsi
0x14000f95b  pop     rbp
0x14000f95c  retn
```
