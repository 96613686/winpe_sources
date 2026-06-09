# CSessionManager::GetGlobalSettings(ushort * const,ulong *)

- ea: `0x180061f84`
- end: `0x180062203`
- name: `?GetGlobalSettings@CSessionManager@@AEAAJQEAGPEAK@Z`
- size: `639`
- prototype: `int(CSessionManager *__hidden this, unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005fcc4`

## callees

- `0x1800074c0`
- `0x18001aa50`
- `0x180025890`
- `0x180026e00`
- `0x18004b460`
- `0x180061f84`
- `0x180062560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800620b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800620b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062104`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062104`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800621cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800621cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180062146`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180062146`
- `RPCRT4!UuidToStringW` at `0x180062037`
- `RPCRT4!UuidToStringW` at `0x180062037`
- `RPCRT4!RpcStringFreeW` at `0x1800621dd`
- `RPCRT4!RpcStringFreeW` at `0x1800621dd`
- `RPCRT4!UuidCreate` at `0x180061fe8`
- `RPCRT4!UuidCreate` at `0x180061fe8`

## string_xrefs

- `0x18006200f`: `UuidCreate failed: 0x%x in %s`
- `0x1800620cd`: `RegOpenKeyEx failed: 0x%x in %s`
- `0x18006215c`: `RegSetValueEx failed: 0x%x in %s`
- `0x1800621a1`: `CachedSessionMode value was read`

## pseudocode

```c
__int64 __fastcall CSessionManager::GetGlobalSettings(
        CSessionManager *this,
        unsigned __int16 *const a2,
        unsigned int *a3)
{
  RPC_STATUS v6; // eax
  signed int v7; // ebx
  const char *v8; // rdx
  RPC_STATUS v9; // eax
  int v10; // eax
  int v11; // edi
  LSTATUS v12; // eax
  unsigned int v13; // eax
  HKEY v14; // rcx
  LSTATUS v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  BYTE Data[8]; // [rsp+30h] [rbp-50h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  DWORD Type; // [rsp+58h] [rbp-28h] BYREF
  const char *v26; // [rsp+60h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-18h] BYREF

  StringUuid = 0;
  hKey = 0;
  v23 = 0;
  Uuid = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  v6 = UuidCreate(&Uuid);
  v7 = v6;
  if ( v6 && v6 != 1824 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "UuidCreate failed: 0x%x in %s";
LABEL_7:
      _DbgPrintMessage(8, v8, (unsigned int)v7, "CSessionManager::GetGlobalSettings");
      goto LABEL_32;
    }
  }
  v9 = UuidToStringW(&Uuid, &StringUuid);
  v7 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "UuidToString failed: 0x%x in %s";
      goto LABEL_7;
    }
  }
  v10 = StringCchLengthW(StringUuid, 0x7FFFFFFFu, &v23);
  v7 = v10;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", (unsigned int)v10, "CSessionManager::GetGlobalSettings");
    goto LABEL_32;
  }
  v11 = v23;
  if ( v23 > 0x1F )
  {
    v11 = 31;
    StringUuid[31] = 0;
  }
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20006u, &hKey);
  v7 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "RegOpenKeyEx failed: 0x%x in %s";
      goto LABEL_7;
    }
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"LSMGlobalSetting", 0, &Type, Data, &cbData)
    || (v13 = *(_DWORD *)Data, *(_DWORD *)Data != 4) )
  {
    v13 = 0;
    *(_DWORD *)Data = 0;
  }
  v14 = hKey;
  *a3 = v13;
  v15 = RegSetValueExW(v14, L"InstanceID", 0, 1u, (const BYTE *)StringUuid, 2 * v11 + 2);
  v7 = v15;
  if ( v15 > 0 )
    v7 = (unsigned __int16)v15 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = "RegSetValueEx failed: 0x%x in %s";
    goto LABEL_7;
  }
  v7 = StringCchCopyW(a2, 0x20u, StringUuid);
  *((_DWORD *)this + 424) = CandidateAccountManagerPolicy::IsCachedSessionEnabled();
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    LODWORD(v23) = *((_DWORD *)this + 424);
    v26 = "CachedSessionMode value was read";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)word_1800C22D2,
      v17,
      v18,
      (__int64)&v26,
      (__int64)&v23);
  }
LABEL_32:
  if ( hKey )
    RegCloseKey(hKey);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180061f84  push    rbp
0x180061f86  push    rbx
0x180061f87  push    rsi
0x180061f88  push    rdi
0x180061f89  push    r13
0x180061f8b  push    r14
0x180061f8d  push    r15
0x180061f8f  mov     rbp, rsp
0x180061f92  sub     rsp, 80h
0x180061f99  mov     rax, cs:__security_cookie
0x180061fa0  xor     rax, rsp
0x180061fa3  mov     [rbp+var_8], rax
0x180061fa7  mov     rsi, rcx
0x180061faa  mov     [rbp+StringUuid], 0
0x180061fb2  xorps   xmm0, xmm0
0x180061fb5  mov     [rbp+hKey], 0
0x180061fbd  lea     rcx, [rbp+Uuid]; Uuid
0x180061fc1  mov     [rbp+var_38], 0
0x180061fc9  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180061fcd  mov     r14, r8
0x180061fd0  mov     dword ptr [rbp+Data], 0
0x180061fd7  mov     r15, rdx
0x180061fda  mov     [rbp+cbData], 0
0x180061fe1  mov     [rbp+Type], 0
0x180061fe8  call    cs:__imp_UuidCreate
0x180061fee  mov     ebx, eax
0x180061ff0  mov     r13d, 80070000h
0x180061ff6  test    eax, eax
0x180061ff8  jz      short loc_18006202F
0x180061ffa  cmp     eax, 720h
0x180061fff  jz      short loc_18006202F
0x180062001  test    eax, eax
0x180062003  jle     short loc_18006200B
0x180062005  movzx   ebx, ax
0x180062008  or      ebx, r13d
0x18006200b  test    ebx, ebx
0x18006200d  jns     short loc_18006202F
0x18006200f  lea     rdx, aUuidcreateFail; "UuidCreate failed: 0x%x in %s"
0x180062016  mov     r8d, ebx
0x180062019  lea     r9, aCsessionmanage; "CSessionManager::GetGlobalSettings"
0x180062020  mov     ecx, 8; int
0x180062025  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006202a  jmp     loc_1800621C3
0x18006202f  lea     rdx, [rbp+StringUuid]; StringUuid
0x180062033  lea     rcx, [rbp+Uuid]; Uuid
0x180062037  call    cs:__imp_UuidToStringW
0x18006203d  mov     ebx, eax
0x18006203f  test    eax, eax
0x180062041  jz      short loc_180062058
0x180062043  jle     short loc_18006204B
0x180062045  movzx   ebx, ax
0x180062048  or      ebx, r13d
0x18006204b  test    ebx, ebx
0x18006204d  jns     short loc_180062058
0x18006204f  lea     rdx, aUuidtostringFa; "UuidToString failed: 0x%x in %s"
0x180062056  jmp     short loc_180062016
0x180062058  mov     rcx, [rbp+StringUuid]; unsigned __int16 *
0x18006205c  lea     r8, [rbp+var_38]; unsigned __int64 *
0x180062060  mov     edx, 7FFFFFFFh; unsigned __int64
0x180062065  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006206a  mov     ebx, eax
0x18006206c  test    eax, eax
0x18006206e  jns     short loc_18006207C
0x180062070  mov     r8d, eax
0x180062073  lea     rdx, aStringcchlengt; "StringCchLength failed: 0x%x in %s"
0x18006207a  jmp     short loc_180062019
0x18006207c  mov     rdi, [rbp+var_38]
0x180062080  cmp     rdi, 1Fh
0x180062084  jbe     short loc_180062095
0x180062086  mov     rax, [rbp+StringUuid]
0x18006208a  xor     ecx, ecx
0x18006208c  mov     edi, 1Fh
0x180062091  mov     [rax+3Eh], cx
0x180062095  lea     rax, [rbp+hKey]
0x180062099  mov     r9d, 20006h; samDesired
0x18006209f  xor     r8d, r8d; ulOptions
0x1800620a2  mov     [rsp+80h+phkResult], rax; phkResult
0x1800620a7  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800620ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800620b5  call    cs:__imp_RegOpenKeyExW
0x1800620bb  mov     ebx, eax
0x1800620bd  test    eax, eax
0x1800620bf  jz      short loc_1800620D9
0x1800620c1  jle     short loc_1800620C9
0x1800620c3  movzx   ebx, ax
0x1800620c6  or      ebx, r13d
0x1800620c9  test    ebx, ebx
0x1800620cb  jns     short loc_1800620D9
0x1800620cd  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed: 0x%x in %s"
0x1800620d4  jmp     loc_180062016
0x1800620d9  mov     rcx, [rbp+hKey]; hKey
0x1800620dd  lea     rax, [rbp+cbData]
0x1800620e1  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1800620e6  lea     r9, [rbp+Type]; lpType
0x1800620ea  lea     rax, [rbp+Data]
0x1800620ee  mov     [rbp+cbData], 4
0x1800620f5  xor     r8d, r8d; lpReserved
0x1800620f8  mov     [rsp+80h+phkResult], rax; lpData
0x1800620fd  lea     rdx, aLsmglobalsetti; "LSMGlobalSetting"
0x180062104  call    cs:__imp_RegQueryValueExW
0x18006210a  test    eax, eax
0x18006210c  jnz     short loc_180062116
0x18006210e  mov     eax, dword ptr [rbp+Data]
0x180062111  cmp     eax, 4
0x180062114  jz      short loc_18006211B
0x180062116  xor     eax, eax
0x180062118  mov     dword ptr [rbp+Data], eax
0x18006211b  mov     rcx, [rbp+hKey]; hKey
0x18006211f  lea     rdx, aInstanceid_0; "InstanceID"
0x180062126  mov     [r14], eax
0x180062129  mov     r9d, 1; dwType
0x18006212f  lea     eax, ds:2[rdi*2]
0x180062136  xor     r8d, r8d; Reserved
0x180062139  mov     dword ptr [rsp+80h+lpcbData], eax; cbData
0x18006213d  mov     rax, [rbp+StringUuid]
0x180062141  mov     [rsp+80h+phkResult], rax; lpData
0x180062146  call    cs:__imp_RegSetValueExW
0x18006214c  mov     ebx, eax
0x18006214e  test    eax, eax
0x180062150  jle     short loc_180062158
0x180062152  movzx   ebx, ax
0x180062155  or      ebx, r13d
0x180062158  test    ebx, ebx
0x18006215a  jns     short loc_180062168
0x18006215c  lea     rdx, aRegsetvalueexF; "RegSetValueEx failed: 0x%x in %s"
0x180062163  jmp     loc_180062016
0x180062168  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x18006216c  mov     edx, 20h ; ' '; unsigned __int64
0x180062171  mov     rcx, r15; unsigned __int16 *
0x180062174  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062179  mov     ebx, eax
0x18006217b  call    ?IsCachedSessionEnabled@CandidateAccountManagerPolicy@@SAHXZ; CandidateAccountManagerPolicy::IsCachedSessionEnabled(void)
0x180062180  mov     [rsi+6A0h], eax
0x180062186  mov     eax, cs:dword_1800DA020
0x18006218c  cmp     eax, 4
0x18006218f  jbe     short loc_1800621C3
0x180062191  mov     eax, [rsi+6A0h]
0x180062197  lea     rdx, word_1800C22D2
0x18006219e  mov     dword ptr [rbp+var_38], eax
0x1800621a1  lea     rax, aCachedsessionm; "CachedSessionMode value was read"
0x1800621a8  mov     [rbp+var_20], rax
0x1800621ac  lea     rax, [rbp+var_38]
0x1800621b0  mov     [rsp+80h+lpcbData], rax
0x1800621b5  lea     rax, [rbp+var_20]
0x1800621b9  mov     [rsp+80h+phkResult], rax
0x1800621be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800621c3  mov     rcx, [rbp+hKey]; hKey
0x1800621c7  test    rcx, rcx
0x1800621ca  jz      short loc_1800621D2
0x1800621cc  call    cs:__imp_RegCloseKey
0x1800621d2  cmp     [rbp+StringUuid], 0
0x1800621d7  jz      short loc_1800621E3
0x1800621d9  lea     rcx, [rbp+StringUuid]; String
0x1800621dd  call    cs:__imp_RpcStringFreeW
0x1800621e3  mov     eax, ebx
0x1800621e5  mov     rcx, [rbp+var_8]
0x1800621e9  xor     rcx, rsp; StackCookie
0x1800621ec  call    __security_check_cookie
0x1800621f1  add     rsp, 80h
0x1800621f8  pop     r15
0x1800621fa  pop     r14
0x1800621fc  pop     r13
0x1800621fe  pop     rdi
0x1800621ff  pop     rsi
0x180062200  pop     rbx
0x180062201  pop     rbp
0x180062202  retn
```
