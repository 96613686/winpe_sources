# HrCreateProfile(wchar_t const *,wchar_t const *,int,ulong,ulong,_GUID *)

- ea: `0x18009ddd4`
- end: `0x18009e041`
- name: `?HrCreateProfile@@YAJPEB_W0HKKPEAU_GUID@@@Z`
- size: `621`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, int, unsigned int, unsigned int, GUID *pguid)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18009dc10`
- `0x1800a6020`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180014d80`
- `0x180019274`
- `0x180055c20`
- `0x18009ddd4`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009de64`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18009de64`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009de48`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18009de48`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18009df3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18009df3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009df27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009df27`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009df16`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009df16`

## pseudocode

```c
__int64 __fastcall HrCreateProfile(const wchar_t *a1, const wchar_t *a2, int a3, int a4, unsigned int a5, GUID *pguid)
{
  unsigned int Guid; // eax
  unsigned int updated; // ebx
  PVOID *v12; // rcx
  LPCWSTR *v13; // r9
  LSTATUS v14; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  __int64 samDesired; // [rsp+28h] [rbp-D8h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[120]; // [rsp+C0h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
  Guid = CoCreateGuid(pguid);
  updated = Guid;
  if ( Guid )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return updated;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, Guid);
    goto LABEL_21;
  }
  if ( StringFromGUID2(pguid, sz, 39) != 39 )
  {
    updated = -2147467259;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return updated;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
    goto LABEL_21;
  }
  v13 = &qword_1801C7140;
  if ( (unsigned __int64)qword_1801C7158 > 7 )
    v13 = (LPCWSTR *)qword_1801C7140;
  StringCchPrintfW(SubKey, 0x78u, L"%s\\%s", v13, sz);
  hKey = 0;
  v14 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  updated = v14;
  if ( !v14 )
  {
    RegCloseKey(hKey);
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    LODWORD(phkResult) = a5;
    LODWORD(samDesired) = a4;
    dwOptions[0] = a3 != 1;
    updated = HrUpdateProfileInfo(sz, 175, a1, a2, *(_QWORD *)dwOptions, samDesired, &SystemTime, phkResult, a1);
    goto LABEL_21;
  }
  if ( v14 > 0 )
    updated = (unsigned __int16)v14 | 0x80070000;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_22:
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
        WPP_SF_d(v12[2], 33, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, updated);
      return updated;
    }
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
      (unsigned int)sz,
      updated);
LABEL_21:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  return updated;
}

```

## disassembly

```asm
0x18009ddd4  mov     [rsp-8+arg_10], rbx
0x18009ddd9  push    rbp
0x18009ddda  push    rsi
0x18009dddb  push    rdi
0x18009dddc  push    r12
0x18009ddde  push    r13
0x18009dde0  push    r14
0x18009dde2  push    r15
0x18009dde4  lea     rbp, [rsp-0C0h]
0x18009ddec  sub     rsp, 1C0h
0x18009ddf3  mov     rax, cs:__security_cookie
0x18009ddfa  xor     rax, rsp
0x18009ddfd  mov     [rbp+0F0h+var_40], rax
0x18009de04  mov     rdi, [rbp+0F0h+pguid]
0x18009de0b  mov     r12d, r9d
0x18009de0e  mov     r14d, r8d
0x18009de11  mov     r15, rdx
0x18009de14  mov     rsi, rcx
0x18009de17  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de1e  lea     r13, WPP_GLOBAL_Control
0x18009de25  cmp     rcx, r13
0x18009de28  jz      short loc_18009DE45
0x18009de2a  test    byte ptr [rcx+1Ch], 8
0x18009de2e  jz      short loc_18009DE45
0x18009de30  mov     rcx, [rcx+10h]
0x18009de34  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009de3b  mov     edx, 1Dh
0x18009de40  call    WPP_SF_
0x18009de45  mov     rcx, rdi; pguid
0x18009de48  call    cs:__imp_CoCreateGuid
0x18009de4e  mov     ebx, eax
0x18009de50  test    eax, eax
0x18009de52  jnz     loc_18009DFC1
0x18009de58  lea     r8d, [rax+27h]; cchMax
0x18009de5c  mov     rcx, rdi; rguid
0x18009de5f  lea     rdx, [rsp+1F0h+sz]; lpsz
0x18009de64  call    cs:__imp_StringFromGUID2
0x18009de6a  cmp     eax, 27h ; '''
0x18009de6d  jz      short loc_18009DEA8
0x18009de6f  mov     ebx, 80004005h
0x18009de74  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de7b  cmp     rcx, r13
0x18009de7e  jz      loc_18009E015
0x18009de84  test    byte ptr [rcx+1Ch], 1
0x18009de88  jz      loc_18009DFF2
0x18009de8e  mov     rcx, [rcx+10h]
0x18009de92  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009de99  mov     edx, 1Fh
0x18009de9e  call    WPP_SF_
0x18009dea3  jmp     loc_18009DFEB
0x18009dea8  cmp     cs:qword_1801C7158, 7
0x18009deb0  lea     rax, [rsp+1F0h+sz]
0x18009deb5  lea     r9, qword_1801C7140
0x18009debc  mov     qword ptr [rsp+1F0h+dwOptions], rax
0x18009dec1  cmova   r9, cs:qword_1801C7140
0x18009dec9  lea     r8, aSS; "%s\\%s"
0x18009ded0  mov     edx, 78h ; 'x'; unsigned __int64
0x18009ded5  lea     rcx, [rbp+0F0h+SubKey]; wchar_t *
0x18009ded9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009dede  xor     edi, edi
0x18009dee0  lea     rax, [rsp+1F0h+hKey]
0x18009dee5  mov     [rsp+1F0h+lpdwDisposition], rdi; lpdwDisposition
0x18009deea  lea     rdx, [rbp+0F0h+SubKey]; lpSubKey
0x18009deee  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18009def3  xor     r9d, r9d; lpClass
0x18009def6  mov     [rsp+1F0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18009defb  xor     r8d, r8d; Reserved
0x18009defe  mov     dword ptr [rsp+1F0h+samDesired], 2001Fh; samDesired
0x18009df06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009df0d  mov     [rsp+1F0h+dwOptions], edi; dwOptions
0x18009df11  mov     [rsp+1F0h+hKey], rdi
0x18009df16  call    cs:__imp_RegCreateKeyExW
0x18009df1c  mov     ebx, eax
0x18009df1e  test    eax, eax
0x18009df20  jnz     short loc_18009DF84
0x18009df22  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18009df27  call    cs:__imp_RegCloseKey
0x18009df2d  xorps   xmm0, xmm0
0x18009df30  lea     rcx, [rsp+1F0h+SystemTime]; lpSystemTime
0x18009df35  movups  xmmword ptr [rsp+1F0h+SystemTime.wYear], xmm0
0x18009df3a  call    cs:__imp_GetLocalTime
0x18009df40  mov     eax, [rbp+0F0h+arg_20]
0x18009df46  mov     ecx, edi
0x18009df48  mov     [rsp+1F0h+lpdwDisposition], rsi
0x18009df4d  cmp     r14d, 1
0x18009df51  mov     dword ptr [rsp+1F0h+phkResult], eax
0x18009df55  mov     r9, r15
0x18009df58  setnz   cl
0x18009df5b  lea     rax, [rsp+1F0h+SystemTime]
0x18009df60  mov     [rsp+1F0h+lpSecurityAttributes], rax
0x18009df65  mov     r8, rsi
0x18009df68  mov     dword ptr [rsp+1F0h+samDesired], r12d
0x18009df6d  mov     edx, 0AFh; unsigned int
0x18009df72  mov     [rsp+1F0h+dwOptions], ecx
0x18009df76  lea     rcx, [rsp+1F0h+sz]; wchar_t *
0x18009df7b  call    ?HrUpdateProfileInfo@@YAJPEB_WKZZ; HrUpdateProfileInfo(wchar_t const *,ulong,...)
0x18009df80  mov     ebx, eax
0x18009df82  jmp     short loc_18009DFEB
0x18009df84  jle     short loc_18009DF8F
0x18009df86  movzx   ebx, ax
0x18009df89  or      ebx, 80070000h
0x18009df8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009df96  cmp     rcx, r13
0x18009df99  jz      short loc_18009E015
0x18009df9b  test    byte ptr [rcx+1Ch], 1
0x18009df9f  jz      short loc_18009DFF2
0x18009dfa1  mov     rcx, [rcx+10h]
0x18009dfa5  lea     r9, [rsp+1F0h+sz]
0x18009dfaa  mov     edx, 1Eh
0x18009dfaf  mov     [rsp+1F0h+dwOptions], ebx
0x18009dfb3  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009dfba  call    WPP_SF_Sd
0x18009dfbf  jmp     short loc_18009DFEB
0x18009dfc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dfc8  cmp     rcx, r13
0x18009dfcb  jz      short loc_18009E015
0x18009dfcd  test    byte ptr [rcx+1Ch], 1
0x18009dfd1  jz      short loc_18009DFF2
0x18009dfd3  mov     rcx, [rcx+10h]
0x18009dfd7  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009dfde  mov     edx, 20h ; ' '
0x18009dfe3  mov     r9d, eax
0x18009dfe6  call    WPP_SF_d
0x18009dfeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dff2  cmp     rcx, r13
0x18009dff5  jz      short loc_18009E015
0x18009dff7  test    byte ptr [rcx+1Ch], 8
0x18009dffb  jz      short loc_18009E015
0x18009dffd  mov     rcx, [rcx+10h]
0x18009e001  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18009e008  mov     edx, 21h ; '!'
0x18009e00d  mov     r9d, ebx
0x18009e010  call    WPP_SF_d
0x18009e015  mov     eax, ebx
0x18009e017  mov     rcx, [rbp+0F0h+var_40]
0x18009e01e  xor     rcx, rsp; StackCookie
0x18009e021  call    __security_check_cookie
0x18009e026  mov     rbx, [rsp+1F0h+arg_10]
0x18009e02e  add     rsp, 1C0h
0x18009e035  pop     r15
0x18009e037  pop     r14
0x18009e039  pop     r13
0x18009e03b  pop     r12
0x18009e03d  pop     rdi
0x18009e03e  pop     rsi
0x18009e03f  pop     rbp
0x18009e040  retn
```
