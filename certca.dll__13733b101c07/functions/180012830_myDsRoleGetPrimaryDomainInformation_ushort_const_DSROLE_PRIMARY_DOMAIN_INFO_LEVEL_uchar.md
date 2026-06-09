# myDsRoleGetPrimaryDomainInformation(ushort const *,_DSROLE_PRIMARY_DOMAIN_INFO_LEVEL,uchar * *)

- ea: `0x180012830`
- end: `0x180012957`
- name: `?myDsRoleGetPrimaryDomainInformation@@YAKPEBGW4_DSROLE_PRIMARY_DOMAIN_INFO_LEVEL@@PEAPEAE@Z`
- size: `295`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000ac20`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000d9f0`
- `0x180012450`
- `0x180012830`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128c0`

## string_xrefs

- `0x180012886`: `netapi32.dll`
- `0x18001284c`: `dsrole.dll`
- `0x18001286f`: `dsrole.dll`
- `0x1800128ec`: `dsrole.dll`

## pseudocode

```c
__int64 __fastcall myDsRoleGetPrimaryDomainInformation(const unsigned __int16 *a1, void *a2, unsigned __int8 **a3)
{
  HMODULE v3; // rcx
  int v5; // eax
  void *v6; // rdx
  int v7; // eax
  unsigned int v8; // ecx
  FARPROC ProcAddress; // rax
  unsigned int v10; // ebx
  int v11; // edx
  unsigned int v12; // ecx
  int v13; // eax

  v3 = qword_1800C4EB8;
  if ( qword_1800C4EB8
    || (qword_1800C4EB8 = myLoadSystem32LibraryEx(L"dsrole.dll", a2, 0), (v3 = qword_1800C4EB8) != 0)
    || (v5 = myHLastError(),
        CSPrintErrorLineFileData2(L"dsrole.dll", 0x2A01CBu, v5, 0),
        qword_1800C4EB8 = myLoadSystem32LibraryEx(L"netapi32.dll", v6, 0),
        (v3 = qword_1800C4EB8) != 0) )
  {
    ProcAddress = (FARPROC)qword_1800C4EC0;
    if ( qword_1800C4EC0 )
      goto LABEL_11;
    ProcAddress = GetProcAddress(v3, "DsRoleGetPrimaryDomainInformation");
    qword_1800C4EC0 = (__int64)ProcAddress;
    if ( ProcAddress )
      goto LABEL_11;
    v7 = myHLastError();
    v8 = 4129227;
  }
  else
  {
    v7 = myHLastError();
    v8 = 3146187;
  }
  v10 = v7;
  CSPrintErrorLineFile(v8, v7);
  if ( v10 )
  {
    CSPrintErrorLineFileData2(L"dsrole.dll", 0x4801CBu, 1, 0);
    CSPrintErrorLineFileData2(L"DsRoleGetPrimaryDomainInformation", 0x4901CBu, 1, 0);
    v11 = v10;
    v12 = 11076043;
LABEL_13:
    CSPrintErrorLineFile(v12, v11);
    return v10;
  }
  ProcAddress = (FARPROC)qword_1800C4EC0;
LABEL_11:
  v13 = ((__int64 (__fastcall *)(_QWORD, __int64, unsigned __int8 **))ProcAddress)(0, 1, a3);
  v10 = v13;
  if ( v13 )
  {
    v11 = v13;
    v12 = 11469259;
    goto LABEL_13;
  }
  return v10;
}

```

## disassembly

```asm
0x180012830  mov     [rsp+arg_0], rbx
0x180012835  push    rdi
0x180012836  sub     rsp, 20h
0x18001283a  mov     rcx, cs:qword_1800C4EB8; hModule
0x180012841  mov     rdi, r8
0x180012844  test    rcx, rcx
0x180012847  jnz     short loc_1800128AD
0x180012849  xor     r8d, r8d; unsigned int
0x18001284c  lea     rcx, aDsroleDll; "dsrole.dll"
0x180012853  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x180012858  mov     cs:qword_1800C4EB8, rax
0x18001285f  mov     rcx, rax
0x180012862  test    rax, rax
0x180012865  jnz     short loc_1800128AD
0x180012867  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001286c  xor     r9d, r9d; int
0x18001286f  lea     rcx, aDsroleDll; "dsrole.dll"
0x180012876  mov     r8d, eax; int
0x180012879  mov     edx, 2A01CBh; unsigned int
0x18001287e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180012883  xor     r8d, r8d; unsigned int
0x180012886  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18001288d  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x180012892  mov     cs:qword_1800C4EB8, rax
0x180012899  mov     rcx, rax
0x18001289c  test    rax, rax
0x18001289f  jnz     short loc_1800128AD
0x1800128a1  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800128a6  mov     ecx, 3001CBh
0x1800128ab  jmp     short loc_1800128DC
0x1800128ad  mov     rax, cs:qword_1800C4EC0
0x1800128b4  test    rax, rax
0x1800128b7  jnz     short loc_180012929
0x1800128b9  lea     rdx, aDsrolegetprima; "DsRoleGetPrimaryDomainInformation"
0x1800128c0  call    cs:__imp_GetProcAddress
0x1800128c6  mov     cs:qword_1800C4EC0, rax
0x1800128cd  test    rax, rax
0x1800128d0  jnz     short loc_180012929
0x1800128d2  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800128d7  mov     ecx, 3F01CBh; unsigned int
0x1800128dc  mov     edx, eax; int
0x1800128de  mov     ebx, eax
0x1800128e0  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800128e5  test    ebx, ebx
0x1800128e7  jz      short loc_180012922
0x1800128e9  xor     r9d, r9d; int
0x1800128ec  lea     rcx, aDsroleDll; "dsrole.dll"
0x1800128f3  mov     edx, 4801CBh; unsigned int
0x1800128f8  lea     r8d, [r9+1]; int
0x1800128fc  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180012901  xor     r9d, r9d; int
0x180012904  lea     rcx, aDsrolegetprima_0; "DsRoleGetPrimaryDomainInformation"
0x18001290b  mov     edx, 4901CBh; unsigned int
0x180012910  lea     r8d, [r9+1]; int
0x180012914  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180012919  mov     edx, ebx
0x18001291b  mov     ecx, 0A901CBh
0x180012920  jmp     short loc_180012945
0x180012922  mov     rax, cs:qword_1800C4EC0
0x180012929  mov     r8, rdi
0x18001292c  mov     edx, 1
0x180012931  xor     ecx, ecx
0x180012933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012938  mov     ebx, eax
0x18001293a  test    eax, eax
0x18001293c  jz      short loc_18001294A
0x18001293e  mov     edx, eax; int
0x180012940  mov     ecx, 0AF01CBh; unsigned int
0x180012945  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001294a  mov     eax, ebx
0x18001294c  mov     rbx, [rsp+28h+arg_0]
0x180012951  add     rsp, 20h
0x180012955  pop     rdi
0x180012956  retn
```
