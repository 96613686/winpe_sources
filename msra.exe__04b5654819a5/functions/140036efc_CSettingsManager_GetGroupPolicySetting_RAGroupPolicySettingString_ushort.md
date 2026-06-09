# CSettingsManager::GetGroupPolicySetting(_RAGroupPolicySettingString,ushort * *)

- ea: `0x140036efc`
- end: `0x14003715f`
- name: `?GetGroupPolicySetting@CSettingsManager@@QEAAJW4_RAGroupPolicySettingString@@PEAPEAG@Z`
- size: `611`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x14002b9d8`
- `0x14002bd4c`

## callees

- `0x1400020f4`
- `0x140002463`
- `0x1400044f8`
- `0x140036efc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400370ff`
- `ADVAPI32!RegCloseKey` at `0x1400370ff`
- `ADVAPI32!RegOpenKeyExW` at `0x140036f90`
- `ADVAPI32!RegOpenKeyExW` at `0x140036f90`
- `ADVAPI32!RegQueryValueExW` at `0x140036fc8`
- `ADVAPI32!RegQueryValueExW` at `0x14003706e`
- `ADVAPI32!RegQueryValueExW` at `0x140036fc8`
- `ADVAPI32!RegQueryValueExW` at `0x14003706e`
- `KERNEL32!ReleaseMutex` at `0x14003711c`
- `KERNEL32!ReleaseMutex` at `0x14003711c`
- `KERNEL32!WaitForSingleObject` at `0x140036f4d`
- `KERNEL32!WaitForSingleObject` at `0x140036f4d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140037086`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400370c6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140037086`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400370c6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400370a5`
- `OLEAUT32!__imp_SysAllocString` at `0x1400370a5`
- `OLEAUT32!__imp_SysFreeString` at `0x140037096`
- `OLEAUT32!__imp_SysFreeString` at `0x14003712c`
- `OLEAUT32!__imp_SysFreeString` at `0x140037096`
- `OLEAUT32!__imp_SysFreeString` at `0x14003712c`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400370d5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400370d5`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400370e6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400370e6`

## string_xrefs

- `0x140036f82`: `Software\policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSettingsManager::GetGroupPolicySetting(HANDLE *a1, int a2, BSTR *a3)
{
  __int64 v4; // rdi
  OLECHAR *v6; // rbx
  HANDLE v7; // rcx
  unsigned int v8; // edi
  int v9; // r14d
  DWORD v10; // eax
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // kr00_8
  void *v13; // rax
  void *v14; // rsi
  UINT v15; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  v4 = a2;
  hKey[0] = 0;
  cbData = 0;
  Type = 1;
  v6 = 0;
  v7 = *a1;
  if ( !v7 )
  {
    v8 = -2147418113;
    goto LABEL_22;
  }
  if ( WaitForSingleObject(v7, 0x64u) == 258 )
  {
    v9 = 0;
  }
  else
  {
    v9 = 1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\policies\\Microsoft\\Windows NT\\Terminal Services",
            0,
            1u,
            hKey) )
    {
      if ( RegQueryValueExW(hKey[0], (LPCWSTR)(&RA_GP_SETTINGS_STRING)[v4], 0, &Type, 0, &cbData) )
      {
        v8 = -2147467263;
        goto LABEL_18;
      }
      v10 = cbData;
      if ( cbData )
      {
        cbData >>= 1;
        v12 = (v10 >> 1) + 1;
        v11 = 2 * v12;
        if ( !is_mul_ok(v12, 2u) )
          v11 = -1;
        v13 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
        v14 = v13;
        if ( v13 )
        {
          memset_0(v13, 0, 2LL * (cbData + 1));
          cbData = 2 * cbData + 2;
          if ( RegQueryValueExW(hKey[0], (LPCWSTR)(&RA_GP_SETTINGS_STRING)[v4], 0, &Type, (LPBYTE)v14, &cbData) )
          {
            v8 = -2147467259;
            operator delete[](v14);
          }
          else
          {
            SysFreeString(0);
            v6 = SysAllocString((const OLECHAR *)v14);
            hKey[1] = (HKEY)v6;
            if ( !v6 )
              ATL::AtlThrowImpl(-2147024882);
            v8 = 0;
            operator delete[](v14);
            v15 = SysStringByteLen(v6);
            *a3 = SysAllocStringByteLen((LPCSTR)v6, v15);
          }
        }
        else
        {
          v8 = -2147024882;
        }
        goto LABEL_18;
      }
    }
  }
  v8 = -2147467259;
LABEL_18:
  if ( hKey[0] )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
  }
  if ( v9 == 1 )
    ReleaseMutex(*a1);
LABEL_22:
  SysFreeString(v6);
  return v8;
}

```

## disassembly

```asm
0x140036efc  mov     [rsp-28h+arg_8], rbx
0x140036f01  mov     [rsp-28h+arg_10], rsi
0x140036f06  push    rbp
0x140036f07  push    rdi
0x140036f08  push    r12
0x140036f0a  push    r14
0x140036f0c  push    r15
0x140036f0e  mov     rbp, rsp
0x140036f11  sub     rsp, 40h
0x140036f15  mov     r12, r8
0x140036f18  movsxd  rdi, edx
0x140036f1b  mov     r15, rcx
0x140036f1e  mov     [rbp+hKey], 0
0x140036f26  mov     [rbp+cbData], 0
0x140036f2d  mov     [rbp+Type], 1
0x140036f34  xor     ebx, ebx
0x140036f36  mov     rcx, [rcx]; hHandle
0x140036f39  test    rcx, rcx
0x140036f3c  jnz     short loc_140036F48
0x140036f3e  mov     edi, 8000FFFFh
0x140036f43  jmp     loc_140037129
0x140036f48  mov     edx, 64h ; 'd'; dwMilliseconds
0x140036f4d  call    cs:__imp_WaitForSingleObject
0x140036f54  nop     dword ptr [rax+rax+00h]
0x140036f59  cmp     eax, 102h
0x140036f5e  jnz     short loc_140036F6D
0x140036f60  xor     r14d, r14d
0x140036f63  mov     edi, 80004005h
0x140036f68  jmp     loc_1400370F6
0x140036f6d  mov     r14d, 1
0x140036f73  lea     rax, [rbp+hKey]
0x140036f77  mov     [rsp+40h+phkResult], rax; phkResult
0x140036f7c  mov     r9d, r14d; samDesired
0x140036f7f  xor     r8d, r8d; ulOptions
0x140036f82  lea     rdx, aSoftwarePolici; "Software\\policies\\Microsoft\\Windows "...
0x140036f89  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140036f90  call    cs:__imp_RegOpenKeyExW
0x140036f97  nop     dword ptr [rax+rax+00h]
0x140036f9c  test    eax, eax
0x140036f9e  jnz     short loc_140036F63
0x140036fa0  lea     rcx, ?RA_GP_SETTINGS_STRING@@3PAPEBGA; ushort const * near * RA_GP_SETTINGS_STRING
0x140036fa7  lea     rax, [rbp+cbData]
0x140036fab  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140036fb0  mov     [rsp+40h+phkResult], 0; lpData
0x140036fb9  lea     r9, [rbp+Type]; lpType
0x140036fbd  xor     r8d, r8d; lpReserved
0x140036fc0  mov     rdx, [rcx+rdi*8]; lpValueName
0x140036fc4  mov     rcx, [rbp+hKey]; hKey
0x140036fc8  call    cs:__imp_RegQueryValueExW
0x140036fcf  nop     dword ptr [rax+rax+00h]
0x140036fd4  test    eax, eax
0x140036fd6  jz      short loc_140036FE2
0x140036fd8  mov     edi, 80004001h
0x140036fdd  jmp     loc_1400370F6
0x140036fe2  mov     eax, [rbp+cbData]
0x140036fe5  test    eax, eax
0x140036fe7  jz      loc_140036F63
0x140036fed  shr     eax, 1
0x140036fef  mov     [rbp+cbData], eax
0x140036ff2  lea     ecx, [rax+1]
0x140036ff5  mov     eax, 2
0x140036ffa  mul     rcx
0x140036ffd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140037004  cmovb   rax, rcx
0x140037008  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003700f  mov     rcx, rax; unsigned __int64
0x140037012  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140037017  mov     rsi, rax
0x14003701a  test    rax, rax
0x14003701d  jnz     short loc_140037029
0x14003701f  mov     edi, 8007000Eh
0x140037024  jmp     loc_1400370F6
0x140037029  mov     r8d, [rbp+cbData]
0x14003702d  inc     r8d
0x140037030  add     r8, r8; Size
0x140037033  xor     edx, edx; Val
0x140037035  mov     rcx, rsi; void *
0x140037038  call    memset_0
0x14003703d  mov     eax, [rbp+cbData]
0x140037040  lea     eax, ds:2[rax*2]
0x140037047  mov     [rbp+cbData], eax
0x14003704a  lea     rax, [rbp+cbData]
0x14003704e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140037053  mov     [rsp+40h+phkResult], rsi; lpData
0x140037058  lea     r9, [rbp+Type]; lpType
0x14003705c  xor     r8d, r8d; lpReserved
0x14003705f  lea     rdx, ?RA_GP_SETTINGS_STRING@@3PAPEBGA; ushort const * near * RA_GP_SETTINGS_STRING
0x140037066  mov     rdx, [rdx+rdi*8]; lpValueName
0x14003706a  mov     rcx, [rbp+hKey]; hKey
0x14003706e  call    cs:__imp_RegQueryValueExW
0x140037075  nop     dword ptr [rax+rax+00h]
0x14003707a  test    eax, eax
0x14003707c  jz      short loc_140037094
0x14003707e  mov     edi, 80004005h
0x140037083  mov     rcx, rsi
0x140037086  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14003708d  nop     dword ptr [rax+rax+00h]
0x140037092  jmp     short loc_1400370F6
0x140037094  xor     ecx, ecx; bstrString
0x140037096  call    cs:__imp_SysFreeString
0x14003709d  nop     dword ptr [rax+rax+00h]
0x1400370a2  mov     rcx, rsi; psz
0x1400370a5  call    cs:__imp_SysAllocString
0x1400370ac  nop     dword ptr [rax+rax+00h]
0x1400370b1  mov     rbx, rax
0x1400370b4  mov     [rbp+var_8], rax
0x1400370b8  test    rax, rax
0x1400370bb  jz      loc_140037154
0x1400370c1  xor     edi, edi
0x1400370c3  mov     rcx, rsi
0x1400370c6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1400370cd  nop     dword ptr [rax+rax+00h]
0x1400370d2  mov     rcx, rbx; bstr
0x1400370d5  call    cs:__imp_SysStringByteLen
0x1400370dc  nop     dword ptr [rax+rax+00h]
0x1400370e1  mov     edx, eax; len
0x1400370e3  mov     rcx, rbx; psz
0x1400370e6  call    cs:__imp_SysAllocStringByteLen
0x1400370ed  nop     dword ptr [rax+rax+00h]
0x1400370f2  mov     [r12], rax
0x1400370f6  mov     rcx, [rbp+hKey]; hKey
0x1400370fa  test    rcx, rcx
0x1400370fd  jz      short loc_140037113
0x1400370ff  call    cs:__imp_RegCloseKey
0x140037106  nop     dword ptr [rax+rax+00h]
0x14003710b  mov     [rbp+hKey], 0
0x140037113  cmp     r14d, 1
0x140037117  jnz     short loc_140037129
0x140037119  mov     rcx, [r15]; hMutex
0x14003711c  call    cs:__imp_ReleaseMutex
0x140037123  nop     dword ptr [rax+rax+00h]
0x140037128  nop
0x140037129  mov     rcx, rbx; bstrString
0x14003712c  call    cs:__imp_SysFreeString
0x140037133  nop     dword ptr [rax+rax+00h]
0x140037138  mov     eax, edi
0x14003713a  lea     r11, [rsp+40h+var_s0]
0x14003713f  mov     rbx, [r11+38h]
0x140037143  mov     rsi, [r11+40h]
0x140037147  mov     rsp, r11
0x14003714a  pop     r15
0x14003714c  pop     r14
0x14003714e  pop     r12
0x140037150  pop     rdi
0x140037151  pop     rbp
0x140037152  retn
0x140037154  mov     ecx, 8007000Eh; int
0x140037159  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
