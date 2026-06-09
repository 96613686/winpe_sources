# CModulePath::MakeAbsoluteModulePath(CStr const &,CStr &)

- ea: `0x180004240`
- end: `0x18000458f`
- name: `?MakeAbsoluteModulePath@CModulePath@@SAJAEBVCStr@@AEAV2@@Z`
- size: `847`
- prototype: `__int64 __fastcall(const struct CStr *, struct CStr *this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180005dbc`

## callees

- `0x180004240`
- `0x180008bb0`
- `0x180008f5c`
- `0x180009054`
- `0x180009218`
- `0x180009294`
- `0x18000931c`
- `0x180009394`
- `0x18000957c`
- `0x18000a582`
- `0x18000a5b0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004326`
- `msvcrt!wcsrchr` at `0x180004326`
- `msvcrt!wcschr` at `0x18000427f`
- `msvcrt!wcschr` at `0x1800042b0`
- `msvcrt!wcschr` at `0x18000427f`
- `msvcrt!wcschr` at `0x1800042b0`
- `msvcrt!_wcsnicmp` at `0x18000443f`
- `msvcrt!_wcsnicmp` at `0x18000443f`
- `KERNEL32!GetVersionExW` at `0x18000441f`
- `KERNEL32!GetVersionExW` at `0x18000447a`
- `KERNEL32!GetVersionExW` at `0x18000441f`
- `KERNEL32!GetVersionExW` at `0x18000447a`
- `KERNEL32!GetSystemDirectoryW` at `0x1800043e6`
- `KERNEL32!GetSystemDirectoryW` at `0x1800043e6`
- `KERNEL32!GetModuleFileNameW` at `0x180004305`
- `KERNEL32!GetModuleFileNameW` at `0x180004305`

## string_xrefs

- `0x18000448b`: `%SystemRoot%\System32`

## pseudocode

```c
__int64 __fastcall CModulePath::MakeAbsoluteModulePath(const wchar_t **a1, const wchar_t **this)
{
  wchar_t *v4; // rax
  wchar_t *v5; // rax
  int v6; // edx
  int v7; // edx
  int v8; // edi
  WCHAR *Buffer; // rax
  DWORD ModuleFileNameW; // ebx
  int v11; // edx
  wchar_t *v12; // rax
  __int64 v13; // rax
  void ***v14; // rcx
  int v15; // eax
  WCHAR *v16; // rax
  UINT SystemDirectoryW; // ebx
  int v18; // edx
  unsigned int v19; // ebx
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  void **v23; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 near **v24; // [rsp+28h] [rbp-D8h]
  __int64 v25; // [rsp+30h] [rbp-D0h]
  int v26; // [rsp+38h] [rbp-C8h]
  void **v27; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h]
  size_t MaxCount; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+58h] [rbp-A8h]
  _QWORD v31[3]; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+78h] [rbp-88h]
  _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF

  v4 = wcschr(a1[1], 0x5Cu);
  if ( !v4 || (unsigned int)(v4 - a1[1]) == -1 )
  {
    v5 = wcschr(a1[1], 0x2Fu);
    if ( !v5 || (unsigned int)(v5 - a1[1]) == -1 )
    {
      v8 = 0;
      Buffer = CStr::GetBuffer((CStr *)this, v6);
      if ( !Buffer )
        return (unsigned int)v8;
      ModuleFileNameW = GetModuleFileNameW(hModule, Buffer, 0x104u);
      CStr::ReleaseBuffer((CStr *)this, v11);
      if ( !ModuleFileNameW )
        goto LABEL_32;
      v12 = wcsrchr(this[1], 0x5Cu);
      if ( !v12 )
        goto LABEL_32;
      v13 = v12 - this[1];
      if ( (_DWORD)v13 == -1 )
        goto LABEL_32;
      v23 = &CStr::`vftable';
      v24 = &CStr::s_rgwchEmptyStringBuffer;
      v25 = 0;
      v26 = 0;
      v8 = CStr::AssignLeft((CStr *)&v23, (const struct CStr *)this, (int)v13 + 1);
      if ( v8 < 0 || (v8 = CStr::Assign((CStr *)this, (const struct CStr *)&v23), v8 < 0) )
      {
        v23 = &CStr::`vftable';
        v14 = &v23;
      }
      else
      {
        v15 = CStr::Append((CStr *)this, (const struct CStr *)a1);
        v23 = &CStr::`vftable';
        v8 = v15;
        v14 = &v23;
        if ( v15 >= 0 )
        {
          CStr::Empty((CStr *)&v23);
          goto LABEL_17;
        }
      }
LABEL_13:
      CStr::Empty((CStr *)v14);
      goto LABEL_32;
    }
  }
  v8 = CStr::Assign((CStr *)this, (const struct CStr *)a1);
  if ( v8 < 0 )
  {
LABEL_32:
    CStr::Empty((CStr *)this);
    return (unsigned int)v8;
  }
LABEL_17:
  v27 = &CStr::`vftable';
  String1 = (wchar_t *)&CStr::s_rgwchEmptyStringBuffer;
  MaxCount = 0;
  v30 = 0;
  v16 = CStr::GetBuffer((CStr *)&v27, v7);
  if ( v16 )
  {
    SystemDirectoryW = GetSystemDirectoryW(v16, 0x104u);
    CStr::ReleaseBuffer((CStr *)&v27, v18);
    if ( SystemDirectoryW )
    {
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
      VersionInformation.dwOSVersionInfoSize = 276;
      GetVersionExW(&VersionInformation);
      if ( VersionInformation.dwPlatformId == 2 )
      {
        v19 = MaxCount;
        if ( !_wcsnicmp(String1, this[1], (unsigned int)MaxCount) )
        {
          v23 = &CStr::`vftable';
          v24 = &CStr::s_rgwchEmptyStringBuffer;
          v25 = 0;
          v26 = 0;
          memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
          VersionInformation.dwOSVersionInfoSize = 276;
          GetVersionExW(&VersionInformation);
          v20 = L"%SystemRoot%\\System32";
          if ( VersionInformation.dwPlatformId != 2 )
            v20 = L"%WinDir%\\System";
          v8 = CStr::Assign((CStr *)&v23, v20);
          if ( v8 < 0 )
            goto LABEL_24;
          v31[0] = &CStr::`vftable';
          v31[1] = &CStr::s_rgwchEmptyStringBuffer;
          v31[2] = 0;
          v32 = 0;
          v8 = CStr::AssignMid((CStr *)v31, (const struct CStr *)this, v19);
          if ( v8 < 0 || (v8 = CStr::Assign((CStr *)this, (const struct CStr *)&v23), v8 < 0) )
          {
            v31[0] = &CStr::`vftable';
          }
          else
          {
            v21 = CStr::Append((CStr *)this, (const struct CStr *)v31);
            v31[0] = &CStr::`vftable';
            v8 = v21;
            if ( v21 >= 0 )
            {
              CStr::Empty((CStr *)v31);
              v23 = &CStr::`vftable';
              CStr::Empty((CStr *)&v23);
              goto LABEL_31;
            }
          }
          CStr::Empty((CStr *)v31);
LABEL_24:
          v23 = &CStr::`vftable';
          CStr::Empty((CStr *)&v23);
          v14 = &v27;
          v27 = &CStr::`vftable';
          goto LABEL_13;
        }
      }
    }
  }
LABEL_31:
  v27 = &CStr::`vftable';
  CStr::Empty((CStr *)&v27);
  if ( v8 < 0 )
    goto LABEL_32;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004240  mov     [rsp-8+arg_10], rbx
0x180004245  push    rbp
0x180004246  push    rsi
0x180004247  push    rdi
0x180004248  push    r12
0x18000424a  push    r13
0x18000424c  push    r14
0x18000424e  push    r15
0x180004250  lea     rbp, [rsp-0B0h]
0x180004258  sub     rsp, 1B0h
0x18000425f  mov     rax, cs:__security_cookie
0x180004266  xor     rax, rsp
0x180004269  mov     [rbp+0E0h+var_40], rax
0x180004270  mov     rsi, rdx
0x180004273  mov     r14, rcx
0x180004276  mov     rcx, [rcx+8]; Str
0x18000427a  mov     edx, 5Ch ; '\'; Ch
0x18000427f  call    cs:__imp_wcschr
0x180004285  xor     r12d, r12d
0x180004288  lea     r15, ??_7CStr@@6B@; const CStr::`vftable'
0x18000428f  lea     r13, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180004296  test    rax, rax
0x180004299  jz      short loc_1800042A7
0x18000429b  sub     rax, [r14+8]
0x18000429f  sar     rax, 1
0x1800042a2  cmp     eax, 0FFFFFFFFh
0x1800042a5  jnz     short loc_1800042C7
0x1800042a7  mov     rcx, [r14+8]; Str
0x1800042ab  mov     edx, 2Fh ; '/'; Ch
0x1800042b0  call    cs:__imp_wcschr
0x1800042b6  test    rax, rax
0x1800042b9  jz      short loc_1800042E1
0x1800042bb  sub     rax, [r14+8]
0x1800042bf  sar     rax, 1
0x1800042c2  cmp     eax, 0FFFFFFFFh
0x1800042c5  jz      short loc_1800042E1
0x1800042c7  mov     rdx, r14; struct CStr *
0x1800042ca  mov     rcx, rsi; this
0x1800042cd  call    ?Assign@CStr@@QEAAJAEBV1@@Z; CStr::Assign(CStr const &)
0x1800042d2  mov     edi, eax
0x1800042d4  test    eax, eax
0x1800042d6  js      loc_18000455B
0x1800042dc  jmp     loc_1800043B7
0x1800042e1  mov     rcx, rsi; this
0x1800042e4  mov     edi, r12d
0x1800042e7  call    ?GetBuffer@CStr@@QEAAPEAGH@Z; CStr::GetBuffer(int)
0x1800042ec  test    rax, rax
0x1800042ef  jz      loc_180004563
0x1800042f5  mov     rcx, cs:hModule; hModule
0x1800042fc  mov     r8d, 104h; nSize
0x180004302  mov     rdx, rax; lpFilename
0x180004305  call    cs:__imp_GetModuleFileNameW
0x18000430b  mov     rcx, rsi; this
0x18000430e  mov     ebx, eax
0x180004310  call    ?ReleaseBuffer@CStr@@QEAAXH@Z; CStr::ReleaseBuffer(int)
0x180004315  test    ebx, ebx
0x180004317  jz      loc_18000455B
0x18000431d  mov     rcx, [rsi+8]; Str
0x180004321  mov     edx, 5Ch ; '\'; Ch
0x180004326  call    cs:__imp_wcsrchr
0x18000432c  test    rax, rax
0x18000432f  jz      loc_18000455B
0x180004335  sub     rax, [rsi+8]
0x180004339  sar     rax, 1
0x18000433c  cmp     eax, 0FFFFFFFFh
0x18000433f  jz      loc_18000455B
0x180004345  lea     r8d, [rax+1]; unsigned int
0x180004349  mov     [rsp+1E0h+var_1C0], r15
0x18000434e  mov     rdx, rsi; struct CStr *
0x180004351  mov     [rsp+1E0h+var_1B8], r13
0x180004356  lea     rcx, [rsp+1E0h+var_1C0]; this
0x18000435b  mov     [rsp+1E0h+var_1B0], r12
0x180004360  mov     [rsp+1E0h+var_1A8], r12d
0x180004365  call    ?AssignLeft@CStr@@QEAAJAEBV1@I@Z; CStr::AssignLeft(CStr const &,uint)
0x18000436a  mov     edi, eax
0x18000436c  test    eax, eax
0x18000436e  jns     short loc_180004384
0x180004370  mov     [rsp+1E0h+var_1C0], r15
0x180004375  lea     rcx, [rsp+1E0h+var_1C0]; this
0x18000437a  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18000437f  jmp     loc_18000455B
0x180004384  lea     rdx, [rsp+1E0h+var_1C0]; struct CStr *
0x180004389  mov     rcx, rsi; this
0x18000438c  call    ?Assign@CStr@@QEAAJAEBV1@@Z; CStr::Assign(CStr const &)
0x180004391  mov     edi, eax
0x180004393  test    eax, eax
0x180004395  js      short loc_180004370
0x180004397  mov     rdx, r14; struct CStr *
0x18000439a  mov     rcx, rsi; this
0x18000439d  call    ?Append@CStr@@QEAAJAEBV1@@Z; CStr::Append(CStr const &)
0x1800043a2  mov     [rsp+1E0h+var_1C0], r15
0x1800043a7  mov     edi, eax
0x1800043a9  lea     rcx, [rsp+1E0h+var_1C0]; this
0x1800043ae  test    eax, eax
0x1800043b0  js      short loc_18000437A
0x1800043b2  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x1800043b7  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800043bc  mov     [rsp+1E0h+var_1A0], r15
0x1800043c1  mov     [rsp+1E0h+String1], r13
0x1800043c6  mov     [rsp+1E0h+MaxCount], r12
0x1800043cb  mov     [rsp+1E0h+var_188], r12d
0x1800043d0  call    ?GetBuffer@CStr@@QEAAPEAGH@Z; CStr::GetBuffer(int)
0x1800043d5  test    rax, rax
0x1800043d8  jz      loc_180004548
0x1800043de  mov     edx, 104h; uSize
0x1800043e3  mov     rcx, rax; lpBuffer
0x1800043e6  call    cs:__imp_GetSystemDirectoryW
0x1800043ec  lea     rcx, [rsp+1E0h+var_1A0]; this
0x1800043f1  mov     ebx, eax
0x1800043f3  call    ?ReleaseBuffer@CStr@@QEAAXH@Z; CStr::ReleaseBuffer(int)
0x1800043f8  test    ebx, ebx
0x1800043fa  jz      loc_180004548
0x180004400  mov     r14d, 110h
0x180004406  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x18000440a  mov     r8d, r14d; Size
0x18000440d  xor     edx, edx; Val
0x18000440f  call    memset_0
0x180004414  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x180004418  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 114h
0x18000441f  call    cs:__imp_GetVersionExW
0x180004425  cmp     [rbp+0E0h+VersionInformation.dwPlatformId], 2
0x180004429  jnz     loc_180004548
0x18000442f  mov     ebx, dword ptr [rsp+1E0h+MaxCount]
0x180004433  mov     rdx, [rsi+8]; String2
0x180004437  mov     r8d, ebx; MaxCount
0x18000443a  mov     rcx, [rsp+1E0h+String1]; String1
0x18000443f  call    cs:__imp__wcsnicmp
0x180004445  test    eax, eax
0x180004447  jnz     loc_180004548
0x18000444d  mov     r8d, r14d; Size
0x180004450  mov     [rsp+1E0h+var_1C0], r15
0x180004455  xor     edx, edx; Val
0x180004457  mov     [rsp+1E0h+var_1B8], r13
0x18000445c  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x180004460  mov     [rsp+1E0h+var_1B0], r12
0x180004465  mov     [rsp+1E0h+var_1A8], r12d
0x18000446a  call    memset_0
0x18000446f  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x180004473  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 114h
0x18000447a  call    cs:__imp_GetVersionExW
0x180004480  cmp     [rbp+0E0h+VersionInformation.dwPlatformId], 2
0x180004484  lea     rcx, aWindirSystem; "%WinDir%\\System"
0x18000448b  lea     rdx, aSystemrootSyst; "%SystemRoot%\\System32"
0x180004492  setz    al
0x180004495  test    al, al
0x180004497  cmovz   rdx, rcx; unsigned __int16 *
0x18000449b  lea     rcx, [rsp+1E0h+var_1C0]; this
0x1800044a0  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x1800044a5  mov     edi, eax
0x1800044a7  test    eax, eax
0x1800044a9  jns     short loc_1800044C9
0x1800044ab  lea     rcx, [rsp+1E0h+var_1C0]; this
0x1800044b0  mov     [rsp+1E0h+var_1C0], r15
0x1800044b5  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x1800044ba  lea     rcx, [rsp+1E0h+var_1A0]
0x1800044bf  mov     [rsp+1E0h+var_1A0], r15
0x1800044c4  jmp     loc_18000437A
0x1800044c9  mov     r8d, ebx; unsigned int
0x1800044cc  mov     [rsp+1E0h+var_180], r15
0x1800044d1  mov     rdx, rsi; struct CStr *
0x1800044d4  mov     [rsp+1E0h+var_178], r13
0x1800044d9  lea     rcx, [rsp+1E0h+var_180]; this
0x1800044de  mov     [rsp+1E0h+var_170], r12
0x1800044e3  mov     [rsp+1E0h+var_168], r12d
0x1800044e8  call    ?AssignMid@CStr@@QEAAJAEBV1@I@Z; CStr::AssignMid(CStr const &,uint)
0x1800044ed  mov     edi, eax
0x1800044ef  test    eax, eax
0x1800044f1  jns     short loc_180004504
0x1800044f3  mov     [rsp+1E0h+var_180], r15
0x1800044f8  lea     rcx, [rsp+1E0h+var_180]; this
0x1800044fd  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180004502  jmp     short loc_1800044AB
0x180004504  lea     rdx, [rsp+1E0h+var_1C0]; struct CStr *
0x180004509  mov     rcx, rsi; this
0x18000450c  call    ?Assign@CStr@@QEAAJAEBV1@@Z; CStr::Assign(CStr const &)
0x180004511  mov     edi, eax
0x180004513  test    eax, eax
0x180004515  js      short loc_1800044F3
0x180004517  lea     rdx, [rsp+1E0h+var_180]; struct CStr *
0x18000451c  mov     rcx, rsi; this
0x18000451f  call    ?Append@CStr@@QEAAJAEBV1@@Z; CStr::Append(CStr const &)
0x180004524  mov     [rsp+1E0h+var_180], r15
0x180004529  mov     edi, eax
0x18000452b  lea     rcx, [rsp+1E0h+var_180]; this
0x180004530  test    eax, eax
0x180004532  js      short loc_1800044FD
0x180004534  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180004539  lea     rcx, [rsp+1E0h+var_1C0]; this
0x18000453e  mov     [rsp+1E0h+var_1C0], r15
0x180004543  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180004548  lea     rcx, [rsp+1E0h+var_1A0]; this
0x18000454d  mov     [rsp+1E0h+var_1A0], r15
0x180004552  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180004557  test    edi, edi
0x180004559  jns     short loc_180004563
0x18000455b  mov     rcx, rsi; this
0x18000455e  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180004563  mov     eax, edi
0x180004565  mov     rcx, [rbp+0E0h+var_40]
0x18000456c  xor     rcx, rsp; StackCookie
0x18000456f  call    __security_check_cookie
0x180004574  mov     rbx, [rsp+1E0h+arg_10]
0x18000457c  add     rsp, 1B0h
0x180004583  pop     r15
0x180004585  pop     r14
0x180004587  pop     r13
0x180004589  pop     r12
0x18000458b  pop     rdi
0x18000458c  pop     rsi
0x18000458d  pop     rbp
0x18000458e  retn
```
