# CDAOStaticGlobals::IsIExplore(void)

- ea: `0x1800ca308`
- end: `0x1800ca3ff`
- name: `?IsIExplore@CDAOStaticGlobals@@QEAA_NXZ`
- size: `247`
- prototype: `bool __fastcall(CDAOStaticGlobals *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180051100`
- `0x180058260`

## callees

- `0x1800ca308`
- `0x1800cdb20`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x1800ca3a6`
- `msvcrt!_wsplitpath_s` at `0x1800ca3a6`
- `msvcrt!_wcsicmp` at `0x1800ca3c2`
- `msvcrt!_wcsicmp` at `0x1800ca3c2`
- `KERNEL32!GetModuleFileNameW` at `0x1800ca351`
- `KERNEL32!GetModuleFileNameW` at `0x1800ca351`

## pseudocode

```c
bool __fastcall CDAOStaticGlobals::IsIExplore(CDAOStaticGlobals *this)
{
  int v1; // edx
  DWORD ModuleFileNameW; // eax
  wchar_t String1[264]; // [rsp+50h] [rbp-438h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp-228h] BYREF

  v1 = *((_DWORD *)this + 24);
  if ( v1 == -1 )
  {
    Filename[0] = 0;
    String1[0] = 0;
    ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x105u);
    if ( !ModuleFileNameW || ModuleFileNameW == 261 || _wsplitpath_s(Filename, 0, 0, 0, 0, String1, 0x101u, 0, 0) )
    {
      v1 = 0;
      *((_DWORD *)this + 24) = 0;
    }
    else
    {
      v1 = _wcsicmp(String1, L"iexplore") == 0;
      *((_DWORD *)this + 24) = v1;
    }
  }
  return v1 == 1;
}

```

## disassembly

```asm
0x1800ca308  push    rbx
0x1800ca30a  sub     rsp, 480h
0x1800ca311  mov     rax, cs:__security_cookie
0x1800ca318  xor     rax, rsp
0x1800ca31b  mov     [rsp+488h+var_18], rax
0x1800ca323  mov     edx, [rcx+60h]
0x1800ca326  mov     rbx, rcx
0x1800ca329  cmp     edx, 0FFFFFFFFh
0x1800ca32c  jnz     loc_1800CA3DF
0x1800ca332  xor     eax, eax
0x1800ca334  lea     rdx, [rsp+488h+Filename]; lpFilename
0x1800ca33c  mov     r8d, 105h; nSize
0x1800ca342  mov     [rsp+488h+Filename], ax
0x1800ca34a  xor     ecx, ecx; hModule
0x1800ca34c  mov     [rsp+488h+String1], ax
0x1800ca351  call    cs:__imp_GetModuleFileNameW
0x1800ca358  nop     dword ptr [rax+rax+00h]
0x1800ca35d  test    eax, eax
0x1800ca35f  jz      short loc_1800CA3DA
0x1800ca361  cmp     eax, 105h
0x1800ca366  jz      short loc_1800CA3DA
0x1800ca368  mov     [rsp+488h+ExtCount], 0; ExtCount
0x1800ca371  lea     rax, [rsp+488h+String1]
0x1800ca376  mov     [rsp+488h+Ext], 0; Ext
0x1800ca37f  lea     rcx, [rsp+488h+Filename]; FullPath
0x1800ca387  mov     [rsp+488h+FilenameCount], 101h; FilenameCount
0x1800ca390  xor     r9d, r9d; Dir
0x1800ca393  mov     [rsp+488h+var_460], rax; Filename
0x1800ca398  xor     r8d, r8d; DriveCount
0x1800ca39b  xor     edx, edx; Drive
0x1800ca39d  mov     [rsp+488h+DirCount], 0; DirCount
0x1800ca3a6  call    cs:__imp__wsplitpath_s
0x1800ca3ad  nop     dword ptr [rax+rax+00h]
0x1800ca3b2  test    eax, eax
0x1800ca3b4  jnz     short loc_1800CA3DA
0x1800ca3b6  lea     rdx, aIexplore; "iexplore"
0x1800ca3bd  lea     rcx, [rsp+488h+String1]; String1
0x1800ca3c2  call    cs:__imp__wcsicmp
0x1800ca3c9  nop     dword ptr [rax+rax+00h]
0x1800ca3ce  xor     edx, edx
0x1800ca3d0  test    eax, eax
0x1800ca3d2  setz    dl
0x1800ca3d5  mov     [rbx+60h], edx
0x1800ca3d8  jmp     short loc_1800CA3DF
0x1800ca3da  xor     edx, edx
0x1800ca3dc  mov     [rbx+60h], edx
0x1800ca3df  cmp     edx, 1
0x1800ca3e2  setz    al
0x1800ca3e5  mov     rcx, [rsp+488h+var_18]
0x1800ca3ed  xor     rcx, rsp; StackCookie
0x1800ca3f0  call    __security_check_cookie
0x1800ca3f5  add     rsp, 480h
0x1800ca3fc  pop     rbx
0x1800ca3fd  retn
```
