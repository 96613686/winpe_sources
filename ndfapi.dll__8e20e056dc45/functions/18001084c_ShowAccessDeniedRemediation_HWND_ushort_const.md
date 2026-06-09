# ShowAccessDeniedRemediation(HWND__ *,ushort const *)

- ea: `0x18001084c`
- end: `0x1800109f9`
- name: `?ShowAccessDeniedRemediation@@YAJPEAUHWND__@@PEBG@Z`
- size: `429`
- prototype: `int(HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010460`

## callees

- `0x18001084c`
- `0x18001f652`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800108fa`
- `ADVAPI32!RegQueryValueExW` at `0x1800108fa`
- `ADVAPI32!RegOpenKeyW` at `0x1800108a2`
- `ADVAPI32!RegOpenKeyW` at `0x1800108a2`
- `ADVAPI32!RegCloseKey` at `0x180010921`
- `ADVAPI32!RegCloseKey` at `0x180010921`
- `ole32!CoCreateInstance` at `0x180010969`
- `ole32!CoCreateInstance` at `0x180010969`
- `ole32!CLSIDFromString` at `0x180010914`
- `ole32!CLSIDFromString` at `0x180010914`
- `OLEAUT32!__imp_SysAllocString` at `0x180010932`
- `OLEAUT32!__imp_SysAllocString` at `0x180010932`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800109cb`

## string_xrefs

- `0x1800108eb`: `AccessDeniedDialog`

## pseudocode

```c
__int64 __fastcall ShowAccessDeniedRemediation(HWND a1, const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  OLECHAR *v5; // rdi
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  CLSID pclsid; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v12[126]; // [rsp+82h] [rbp-7Eh] BYREF

  phkResult = 0;
  pclsid = GUID_NULL;
  v4 = -2147024846;
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer", &phkResult) )
  {
    *(_WORD *)Data = 0;
    memset_0(v12, 0, sizeof(v12));
    cbData[0] = 128;
    Type = 0;
    if ( !RegQueryValueExW(phkResult, L"AccessDeniedDialog", 0, &Type, Data, cbData) && Type == 1 )
      v4 = CLSIDFromString((LPCOLESTR)Data, &pclsid);
    RegCloseKey(phkResult);
    if ( v4 >= 0 )
    {
      v5 = SysAllocString(a2);
      if ( v5 )
      {
        *(_QWORD *)cbData = 0;
        v4 = CoCreateInstance(&pclsid, 0, 1u, &IID_IFsrmAccessDeniedRemediationClient, (LPVOID *)cbData);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, HWND, OLECHAR *, __int64, int, _QWORD, _QWORD, _QWORD))(**(_QWORD **)cbData + 56LL))(
                 *(_QWORD *)cbData,
                 a1,
                 v5,
                 1,
                 7,
                 0,
                 0,
                 0);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)cbData + 16LL))(*(_QWORD *)cbData);
        }
        SysFreeString(v5);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001084c  mov     [rsp-8+arg_10], rbx
0x180010851  push    rbp
0x180010852  push    rsi
0x180010853  push    rdi
0x180010854  lea     rbp, [rsp-10h]
0x180010859  sub     rsp, 110h
0x180010860  mov     rax, cs:__security_cookie
0x180010867  xor     rax, rsp
0x18001086a  mov     [rbp+20h+var_20], rax
0x18001086e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180010875  mov     rdi, rdx
0x180010878  mov     [rsp+120h+phkResult], 0
0x180010881  mov     rsi, rcx
0x180010884  lea     r8, [rsp+120h+phkResult]; phkResult
0x180010889  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180010890  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010897  movdqu  xmmword ptr [rsp+120h+pclsid.Data1], xmm0
0x18001089d  mov     ebx, 80070032h
0x1800108a2  call    cs:__imp_RegOpenKeyW
0x1800108a8  test    eax, eax
0x1800108aa  jnz     loc_1800109D8
0x1800108b0  xor     edx, edx; Val
0x1800108b2  mov     word ptr [rbp+20h+Data], ax
0x1800108b6  lea     r8d, [rax+7Eh]; Size
0x1800108ba  lea     rcx, [rbp+20h+var_9E]; void *
0x1800108be  call    memset_0
0x1800108c3  mov     rcx, [rsp+120h+phkResult]; hKey
0x1800108c8  lea     rax, [rsp+120h+cbData]
0x1800108cd  mov     [rsp+120h+lpcbData], rax; lpcbData
0x1800108d2  lea     r9, [rsp+120h+Type]; lpType
0x1800108d7  lea     rax, [rbp+20h+Data]
0x1800108db  mov     [rsp+120h+cbData], 80h
0x1800108e3  xor     r8d, r8d; lpReserved
0x1800108e6  mov     [rsp+120h+lpData], rax; lpData
0x1800108eb  lea     rdx, ValueName; "AccessDeniedDialog"
0x1800108f2  mov     [rsp+120h+Type], 0
0x1800108fa  call    cs:__imp_RegQueryValueExW
0x180010900  test    eax, eax
0x180010902  jnz     short loc_18001091C
0x180010904  cmp     [rsp+120h+Type], 1
0x180010909  jnz     short loc_18001091C
0x18001090b  lea     rdx, [rsp+120h+pclsid]; pclsid
0x180010910  lea     rcx, [rbp+20h+Data]; lpsz
0x180010914  call    cs:__imp_CLSIDFromString
0x18001091a  mov     ebx, eax
0x18001091c  mov     rcx, [rsp+120h+phkResult]; hKey
0x180010921  call    cs:__imp_RegCloseKey
0x180010927  test    ebx, ebx
0x180010929  js      loc_1800109D8
0x18001092f  mov     rcx, rdi; psz
0x180010932  call    cs:__imp_SysAllocString
0x180010938  mov     rdi, rax
0x18001093b  test    rax, rax
0x18001093e  jz      loc_1800109D3
0x180010944  xor     edx, edx; pUnkOuter
0x180010946  mov     qword ptr [rsp+120h+cbData], 0
0x18001094f  lea     rax, [rsp+120h+cbData]
0x180010954  lea     r9, IID_IFsrmAccessDeniedRemediationClient; riid
0x18001095b  mov     [rsp+120h+lpData], rax; ppv
0x180010960  lea     rcx, [rsp+120h+pclsid]; rclsid
0x180010965  lea     r8d, [rdx+1]; dwClsContext
0x180010969  call    cs:__imp_CoCreateInstance
0x18001096f  mov     ebx, eax
0x180010971  test    eax, eax
0x180010973  js      short loc_1800109C8
0x180010975  mov     rcx, qword ptr [rsp+120h+cbData]
0x18001097a  mov     r9d, 1
0x180010980  mov     [rsp+120h+var_E8], 0
0x180010989  mov     r8, rdi
0x18001098c  mov     [rsp+120h+var_F0], 0
0x180010995  mov     rdx, rsi
0x180010998  mov     [rsp+120h+lpcbData], 0
0x1800109a1  mov     rax, [rcx]
0x1800109a4  mov     dword ptr [rsp+120h+lpData], 7
0x1800109ac  mov     rax, [rax+38h]
0x1800109b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109b5  mov     rcx, qword ptr [rsp+120h+cbData]
0x1800109ba  mov     ebx, eax
0x1800109bc  mov     rax, [rcx]
0x1800109bf  mov     rax, [rax+10h]
0x1800109c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c8  mov     rcx, rdi; bstrString
0x1800109cb  call    cs:__imp_SysFreeString
0x1800109d1  jmp     short loc_1800109D8
0x1800109d3  mov     ebx, 8007000Eh
0x1800109d8  mov     eax, ebx
0x1800109da  mov     rcx, [rbp+20h+var_20]
0x1800109de  xor     rcx, rsp; StackCookie
0x1800109e1  call    __security_check_cookie
0x1800109e6  mov     rbx, [rsp+120h+arg_10]
0x1800109ee  add     rsp, 110h
0x1800109f5  pop     rdi
0x1800109f6  pop     rsi
0x1800109f7  pop     rbp
0x1800109f8  retn
```
