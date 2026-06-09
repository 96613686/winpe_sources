# CreateCLSIDRegKey

- ea: `0x18000eef0`
- end: `0x18000f063`
- name: `CreateCLSIDRegKey`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e960`

## callees

- `0x18000ab30`
- `0x18000eca8`
- `0x18000ecf8`
- `0x18000ed40`
- `0x18000eef0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000ef27`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18000ef27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000f00d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18000f00d`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18000ef84`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18000efda`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18000ef84`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18000efda`

## string_xrefs

- `0x18000eff8`: `ThreadingModel`

## pseudocode

```c
int CreateCLSIDRegKey()
{
  const struct _GUID *v0; // rcx
  int result; // eax
  int v2; // ebx
  __int64 cbData; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v5; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v6[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v7[8]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v8[80]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Filename[272]; // [rsp+F0h] [rbp-10h] BYREF

  GetModuleFileNameA(g_hInst, Filename, 0x104u);
  result = MakeCLSIDRegPath(v0, v8);
  v2 = 0;
  if ( result >= 0 )
  {
    hKey = 0;
    CAutoHKey::CAutoHKey((CAutoHKey *)v6, HKEY_CLASSES_ROOT, v8, &hKey);
    if ( !hKey || RegSetValueA(hKey, 0, 1u, "Color Converter DMO", 0x13u) )
    {
      CAutoHKey::~CAutoHKey((CAutoHKey *)v6);
      return -2147467259;
    }
    else
    {
      v5 = 0;
      CAutoHKey::CAutoHKey((CAutoHKey *)v7, hKey, L"InprocServer32", &v5);
      if ( !v5 )
        goto LABEL_9;
      cbData = -1;
      do
        ++cbData;
      while ( Filename[cbData] );
      if ( RegSetValueA(v5, 0, 1u, Filename, cbData) || RegSetValueExA(v5, "ThreadingModel", 0, 1u, "Both", 5u) )
LABEL_9:
        v2 = -2147467259;
      CAutoHKey::~CAutoHKey((CAutoHKey *)v7);
      CAutoHKey::~CAutoHKey((CAutoHKey *)v6);
      return v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000eef0  mov     [rsp-8+arg_0], rbx
0x18000eef5  push    rbp
0x18000eef6  lea     rbp, [rsp-110h]
0x18000eefe  sub     rsp, 210h
0x18000ef05  mov     rax, cs:__security_cookie
0x18000ef0c  xor     rax, rsp
0x18000ef0f  mov     [rbp+110h+var_10], rax
0x18000ef16  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18000ef1d  lea     rdx, [rbp+110h+Filename]; lpFilename
0x18000ef21  mov     r8d, 104h; nSize
0x18000ef27  call    cs:__imp_GetModuleFileNameA
0x18000ef2d  lea     rdx, [rsp+210h+var_1C0]; unsigned __int16 *
0x18000ef32  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18000ef37  xor     ebx, ebx
0x18000ef39  test    eax, eax
0x18000ef3b  js      loc_18000F043
0x18000ef41  lea     r9, [rsp+210h+hKey]; HKEY *
0x18000ef46  mov     [rsp+210h+hKey], rbx
0x18000ef4b  lea     r8, [rsp+210h+var_1C0]; unsigned __int16 *
0x18000ef50  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x18000ef57  lea     rcx, [rsp+210h+var_1D0]; this
0x18000ef5c  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18000ef61  mov     rcx, [rsp+210h+hKey]; hKey
0x18000ef66  test    rcx, rcx
0x18000ef69  jz      loc_18000F034
0x18000ef6f  lea     r9, Data; "Color Converter DMO"
0x18000ef76  mov     [rsp+210h+cbData], 13h; cbData
0x18000ef7e  xor     edx, edx; lpSubKey
0x18000ef80  lea     r8d, [rbx+1]; dwType
0x18000ef84  call    cs:__imp_RegSetValueA
0x18000ef8a  test    eax, eax
0x18000ef8c  jnz     loc_18000F034
0x18000ef92  mov     rdx, [rsp+210h+hKey]; HKEY
0x18000ef97  lea     r9, [rsp+210h+var_1D8]; HKEY *
0x18000ef9c  lea     r8, aInprocserver32; "InprocServer32"
0x18000efa3  mov     [rsp+210h+var_1D8], rbx
0x18000efa8  lea     rcx, [rsp+210h+var_1C8]; this
0x18000efad  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18000efb2  mov     rcx, [rsp+210h+var_1D8]; hKey
0x18000efb7  test    rcx, rcx
0x18000efba  jz      short loc_18000F017
0x18000efbc  lea     rdx, [rbp+110h+Filename]
0x18000efc0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000efc4  inc     rax
0x18000efc7  cmp     [rdx+rax], bl
0x18000efca  jnz     short loc_18000EFC4
0x18000efcc  xor     edx, edx; lpSubKey
0x18000efce  mov     [rsp+210h+cbData], eax; cbData
0x18000efd2  lea     r9, [rbp+110h+Filename]; lpData
0x18000efd6  lea     r8d, [rdx+1]; dwType
0x18000efda  call    cs:__imp_RegSetValueA
0x18000efe0  test    eax, eax
0x18000efe2  jnz     short loc_18000F017
0x18000efe4  mov     rcx, [rsp+210h+var_1D8]; hKey
0x18000efe9  lea     rax, aBoth; "Both"
0x18000eff0  mov     [rsp+210h+var_1E8], 5; cbData
0x18000eff8  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18000efff  mov     r9d, 1; dwType
0x18000f005  mov     qword ptr [rsp+210h+cbData], rax; lpData
0x18000f00a  xor     r8d, r8d; Reserved
0x18000f00d  call    cs:__imp_RegSetValueExA
0x18000f013  test    eax, eax
0x18000f015  jz      short loc_18000F01C
0x18000f017  mov     ebx, 80004005h
0x18000f01c  lea     rcx, [rsp+210h+var_1C8]; this
0x18000f021  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18000f026  lea     rcx, [rsp+210h+var_1D0]; this
0x18000f02b  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18000f030  mov     eax, ebx
0x18000f032  jmp     short loc_18000F043
0x18000f034  lea     rcx, [rsp+210h+var_1D0]; this
0x18000f039  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18000f03e  mov     eax, 80004005h
0x18000f043  mov     rcx, [rbp+110h+var_10]
0x18000f04a  xor     rcx, rsp; StackCookie
0x18000f04d  call    __security_check_cookie
0x18000f052  mov     rbx, [rsp+210h+arg_0]
0x18000f05a  add     rsp, 210h
0x18000f061  pop     rbp
0x18000f062  retn
```
