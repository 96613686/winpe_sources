# fc::set_store_id(HKEY__ *,fc::store_type,_GUID const &)

- ea: `0x18001f850`
- end: `0x18001fa10`
- name: `?set_store_id@fc@@YAJPEAUHKEY__@@W4store_type@1@AEBU_GUID@@@Z`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020a74`
- `0x180021098`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180009c28`
- `0x180016698`
- `0x180018ab4`
- `0x18001bac0`
- `0x18001e820`
- `0x18001f850`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f9cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f9cb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f8c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001f8c9`

## pseudocode

```c
__int64 __fastcall fc::set_store_id(HKEY a1, unsigned int a2, unsigned int *a3)
{
  unsigned int Key; // eax
  unsigned int v7; // ebx
  const WCHAR *store_id_reg_value_name; // rbp
  __int64 v9; // rdx
  __int64 v10; // r9
  LSTATUS v11; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E8h]
  __int64 samDesired; // [rsp+28h] [rbp-E0h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D8h]
  PHKEY phkResult; // [rsp+38h] [rbp-D0h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-C8h]
  HKEY hKey[2]; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int16 Data[40]; // [rsp+80h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0,
    a3);
  Key = RegCreateKeyExW(a1, L"SYSTEM\\Software\\Microsoft\\FT", 0, 0, 0, 0x2001Fu, 0, hKey, 0);
  if ( Key )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x219,
           (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_utilities.h",
           (const char *)Key,
           dwOptions[0]);
  }
  else
  {
    store_id_reg_value_name = (const WCHAR *)fc::get_store_id_reg_value_name(a2);
    if ( store_id_reg_value_name )
    {
      LODWORD(lpdwDisposition) = *((unsigned __int8 *)a3 + 10);
      LODWORD(phkResult) = *((unsigned __int8 *)a3 + 9);
      LODWORD(lpSecurityAttributes) = *((unsigned __int8 *)a3 + 8);
      LODWORD(samDesired) = *((unsigned __int16 *)a3 + 3);
      dwOptions[0] = *((unsigned __int16 *)a3 + 2);
      StringCchPrintfW(
        Data,
        0x27u,
        L"{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
        *a3,
        *(_QWORD *)dwOptions,
        samDesired,
        lpSecurityAttributes,
        phkResult,
        lpdwDisposition,
        *((unsigned __int8 *)a3 + 11),
        *((unsigned __int8 *)a3 + 12),
        *((unsigned __int8 *)a3 + 13),
        *((unsigned __int8 *)a3 + 14),
        *((unsigned __int8 *)a3 + 15));
      v11 = RegSetValueExW(hKey[0], store_id_reg_value_name, 0, 1u, (const BYTE *)Data, 0x4Eu);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v7 = 0;
        goto LABEL_9;
      }
      v10 = (unsigned int)v11;
      v9 = 551;
    }
    else
    {
      v7 = -2147024809;
      v9 = 541;
      v10 = 2147942487LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_utilities.h",
      (const char *)v10,
      dwOptions[0]);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return v7;
}

```

## disassembly

```asm
0x18001f850  push    rbx
0x18001f852  push    rbp
0x18001f853  push    rsi
0x18001f854  push    rdi
0x18001f855  push    r14
0x18001f857  sub     rsp, 0E0h
0x18001f85e  mov     rax, cs:__security_cookie
0x18001f865  xor     rax, rsp
0x18001f868  mov     [rsp+108h+var_38], rax
0x18001f870  mov     edi, edx
0x18001f872  mov     [rsp+108h+hKey], 0
0x18001f87b  mov     rbx, rcx
0x18001f87e  xor     edx, edx
0x18001f880  lea     rcx, [rsp+108h+hKey]
0x18001f885  mov     r14, r8
0x18001f888  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001f88d  mov     [rsp+108h+lpdwDisposition], 0; lpdwDisposition
0x18001f896  lea     rax, [rsp+108h+hKey]
0x18001f89b  mov     [rsp+108h+phkResult], rax; phkResult
0x18001f8a0  lea     rdx, SubKey; "SYSTEM\\Software\\Microsoft\\FT"
0x18001f8a7  mov     [rsp+108h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001f8b0  xor     r9d, r9d; lpClass
0x18001f8b3  mov     dword ptr [rsp+108h+samDesired], 2001Fh; samDesired
0x18001f8bb  xor     r8d, r8d; Reserved
0x18001f8be  mov     rcx, rbx; hKey
0x18001f8c1  mov     [rsp+108h+dwOptions], 0; int
0x18001f8c9  call    cs:__imp_RegCreateKeyExW
0x18001f8cf  test    eax, eax
0x18001f8d1  jz      short loc_18001F8F6
0x18001f8d3  mov     rcx, [rsp+108h]; this
0x18001f8db  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001f8e2  mov     r9d, eax; char *
0x18001f8e5  mov     edx, 219h; void *
0x18001f8ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f8ef  mov     ebx, eax
0x18001f8f1  jmp     loc_18001F9E6
0x18001f8f6  mov     ecx, edi
0x18001f8f8  call    ?get_store_id_reg_value_name@fc@@YAPEBGW4store_type@1@@Z; fc::get_store_id_reg_value_name(fc::store_type)
0x18001f8fd  mov     rbp, rax
0x18001f900  test    rax, rax
0x18001f903  jnz     short loc_18001F92B
0x18001f905  mov     ebx, 80070057h
0x18001f90a  mov     edx, 21Dh; void *
0x18001f90f  mov     r9d, ebx; char *
0x18001f912  mov     rcx, [rsp+108h]; this
0x18001f91a  lea     r8, aOnecoreInterna_4; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18001f921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f926  jmp     loc_18001F9E6
0x18001f92b  movzx   ecx, byte ptr [r14+0Eh]
0x18001f930  movzx   edx, byte ptr [r14+0Dh]
0x18001f935  movzx   r8d, byte ptr [r14+0Ch]
0x18001f93a  movzx   r9d, byte ptr [r14+0Bh]
0x18001f93f  movzx   eax, byte ptr [r14+0Fh]
0x18001f944  movzx   r10d, byte ptr [r14+0Ah]
0x18001f949  movzx   r11d, byte ptr [r14+9]
0x18001f94e  movzx   ebx, byte ptr [r14+8]
0x18001f953  movzx   edi, word ptr [r14+6]
0x18001f958  movzx   esi, word ptr [r14+4]
0x18001f95d  mov     [rsp+108h+var_A0], eax
0x18001f961  mov     [rsp+108h+var_A8], ecx
0x18001f965  lea     rcx, [rsp+108h+Data]; unsigned __int16 *
0x18001f96d  mov     [rsp+108h+var_B0], edx
0x18001f971  mov     edx, 27h ; '''; unsigned __int64
0x18001f976  mov     [rsp+108h+var_B8], r8d
0x18001f97b  lea     r8, a08lx04x04x02x0; "{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%"...
0x18001f982  mov     [rsp+108h+var_C0], r9d
0x18001f987  mov     r9d, [r14]
0x18001f98a  mov     dword ptr [rsp+108h+lpdwDisposition], r10d
0x18001f98f  mov     dword ptr [rsp+108h+phkResult], r11d
0x18001f994  mov     dword ptr [rsp+108h+lpSecurityAttributes], ebx
0x18001f998  mov     dword ptr [rsp+108h+samDesired], edi
0x18001f99c  mov     [rsp+108h+dwOptions], esi
0x18001f9a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001f9a5  mov     rcx, [rsp+108h+hKey]; hKey
0x18001f9aa  lea     rax, [rsp+108h+Data]
0x18001f9b2  mov     dword ptr [rsp+108h+samDesired], 4Eh ; 'N'; cbData
0x18001f9ba  mov     r9d, 1; dwType
0x18001f9c0  xor     r8d, r8d; Reserved
0x18001f9c3  mov     qword ptr [rsp+108h+dwOptions], rax; lpData
0x18001f9c8  mov     rdx, rbp; lpValueName
0x18001f9cb  call    cs:__imp_RegSetValueExW
0x18001f9d1  mov     ebx, eax
0x18001f9d3  test    eax, eax
0x18001f9d5  jns     short loc_18001F9E4
0x18001f9d7  mov     r9d, eax
0x18001f9da  mov     edx, 227h
0x18001f9df  jmp     loc_18001F912
0x18001f9e4  xor     ebx, ebx
0x18001f9e6  lea     rcx, [rsp+108h+hKey]
0x18001f9eb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f9f0  mov     eax, ebx
0x18001f9f2  mov     rcx, [rsp+108h+var_38]
0x18001f9fa  xor     rcx, rsp; StackCookie
0x18001f9fd  call    __security_check_cookie
0x18001fa02  add     rsp, 0E0h
0x18001fa09  pop     r14
0x18001fa0b  pop     rdi
0x18001fa0c  pop     rsi
0x18001fa0d  pop     rbp
0x18001fa0e  pop     rbx
0x18001fa0f  retn
```
