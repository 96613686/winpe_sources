# WxConnectionDeleteProxyInfo(ushort const *,_DNS_CONNECTION_PROXY_TYPE)

- ea: `0x1800c4440`
- end: `0x1800c46d8`
- name: `?WxConnectionDeleteProxyInfo@@YAKPEBGW4_DNS_CONNECTION_PROXY_TYPE@@@Z`
- size: `664`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, enum _DNS_CONNECTION_PROXY_TYPE)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callers

- `0x1800ac790`

## callees

- `0x18003de30`
- `0x1800412f4`
- `0x18004148c`
- `0x1800577b4`
- `0x18005cb48`
- `0x18005cd90`
- `0x18008b5f0`
- `0x1800c4440`
- `0x1800dbadc`
- `0x1800dbfe0`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800c45dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x1800c45dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c461c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c468c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c46a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c461c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c468c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c46a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c4579`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c463a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c4579`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c463a`

## pseudocode

```c
__int64 __fastcall WxConnectionDeleteProxyInfo(unsigned __int16 *a1, unsigned int a2)
{
  signed int v4; // ebx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp+7h] BYREF
  HKEY v10; // [rsp+78h] [rbp+Fh]
  LPCWSTR v11[2]; // [rsp+80h] [rbp+17h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+90h] [rbp+27h] BYREF

  v10 = 0;
  hKey = 0;
  v11[0] = &word_1800F66E0;
  v11[1] = 0;
  lpSubKey[0] = &word_1800F66E0;
  lpSubKey[1] = 0;
  cSubKeys = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_Sd(1054, 25, (unsigned int)WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids, (_DWORD)a1, a2);
  if ( a1 )
  {
    v4 = OpenProxyRegistryKey(0x2001Fu, 1);
    if ( v4 >= 0 )
    {
      v4 = NormalizeConnectionName(a1, (CWxString *)v11);
      if ( v4 >= 0 )
      {
        v4 = WxOpenRegistryKey(v10, v11[0], 0x2001Fu, 0, &hKey);
        if ( v4 >= 0 )
        {
          v4 = CWxString::Format((CWxString *)lpSubKey, L"%d", a2);
          if ( v4 >= 0 )
          {
            v5 = RegDeleteKeyExW(hKey, lpSubKey[0], 0, 0);
            v4 = v5;
            if ( v5 > 0 )
              v4 = (unsigned __int16)v5 | 0x80070000;
            if ( v4 >= 0 && !RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) && !cSubKeys )
            {
              if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
                WPP_SF_S(1054, 26, WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids, v11[0]);
              if ( hKey )
              {
                RegCloseKey(hKey);
                hKey = 0;
              }
              RegDeleteKeyExW(v10, v11[0], 0, 0);
            }
          }
        }
      }
    }
  }
  else
  {
    v4 = -2147024809;
  }
  if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_d(1054, 27, WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids, (unsigned int)v4);
  v6 = WX_WIN32_FROM_HR((unsigned int)v4);
  CWxString::_Release((CWxString *)lpSubKey);
  CWxString::_Release((CWxString *)v11);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v10 )
    RegCloseKey(v10);
  return v6;
}

```

## disassembly

```asm
0x1800c4440  mov     [rsp-8+arg_10], rbx
0x1800c4445  mov     [rsp-8+arg_18], rsi
0x1800c444a  push    rbp
0x1800c444b  push    rdi
0x1800c444c  push    r14
0x1800c444e  lea     rbp, [rsp-47h]
0x1800c4453  sub     rsp, 0B0h
0x1800c445a  mov     rax, cs:__security_cookie
0x1800c4461  xor     rax, rsp
0x1800c4464  mov     [rbp+57h+var_20], rax
0x1800c4468  xor     r14d, r14d
0x1800c446b  lea     rax, word_1800F66E0
0x1800c4472  mov     [rbp+57h+var_5C], r14d
0x1800c4476  mov     esi, edx
0x1800c4478  mov     [rbp+57h+var_48], r14
0x1800c447c  mov     rdi, rcx
0x1800c447f  mov     [rbp+57h+hKey], r14
0x1800c4483  mov     [rbp+57h+var_40], rax
0x1800c4487  mov     [rbp+57h+var_38], r14
0x1800c448b  mov     [rbp+57h+lpSubKey], rax
0x1800c448f  mov     [rbp+57h+var_28], r14
0x1800c4493  mov     [rbp+57h+cSubKeys], r14d
0x1800c4497  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800c449e  jz      short loc_1800C44BC
0x1800c44a0  lea     edx, [r14+19h]
0x1800c44a4  mov     dword ptr [rsp+0C0h+lpcSubKeys], esi
0x1800c44a8  mov     ecx, 41Eh
0x1800c44ad  lea     r8, WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids
0x1800c44b4  mov     r9, rdi
0x1800c44b7  call    WPP_SF_Sd
0x1800c44bc  test    rdi, rdi
0x1800c44bf  jnz     short loc_1800C44D2
0x1800c44c1  mov     ebx, 80070057h
0x1800c44c6  mov     [rbp+57h+var_5C], 286h
0x1800c44cd  jmp     loc_1800C4646
0x1800c44d2  lea     r8, [rbp+57h+var_48]
0x1800c44d6  mov     edx, 1; int
0x1800c44db  mov     ecx, 2001Fh; samDesired
0x1800c44e0  call    _OpenProxyRegistryKey
0x1800c44e5  mov     ebx, eax
0x1800c44e7  test    eax, eax
0x1800c44e9  jns     short loc_1800C44F7
0x1800c44eb  mov     [rbp+57h+var_5C], 288h
0x1800c44f2  jmp     loc_1800C4646
0x1800c44f7  lea     rdx, [rbp+57h+var_40]; this
0x1800c44fb  mov     rcx, rdi; unsigned __int16 *
0x1800c44fe  call    _NormalizeConnectionName
0x1800c4503  mov     ebx, eax
0x1800c4505  test    eax, eax
0x1800c4507  jns     short loc_1800C4515
0x1800c4509  mov     [rbp+57h+var_5C], 28Ah
0x1800c4510  jmp     loc_1800C4646
0x1800c4515  mov     rdx, [rbp+57h+var_40]; lpSubKey
0x1800c4519  lea     rax, [rbp+57h+hKey]
0x1800c451d  mov     rcx, [rbp+57h+var_48]; hKey
0x1800c4521  xor     r9d, r9d; int
0x1800c4524  mov     r8d, 2001Fh; samDesired
0x1800c452a  mov     [rsp+0C0h+lpcSubKeys], rax; HKEY *
0x1800c452f  call    ?WxOpenRegistryKey@@YAJPEAUHKEY__@@PEBGKHPEAPEAU1@@Z; WxOpenRegistryKey(HKEY__ *,ushort const *,ulong,int,HKEY__ * *)
0x1800c4534  mov     ebx, eax
0x1800c4536  test    eax, eax
0x1800c4538  jns     short loc_1800C4546
0x1800c453a  mov     [rbp+57h+var_5C], 28Bh
0x1800c4541  jmp     loc_1800C4646
0x1800c4546  mov     r8d, esi
0x1800c4549  lea     rdx, aD; "%d"
0x1800c4550  lea     rcx, [rbp+57h+lpSubKey]; this
0x1800c4554  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1800c4559  mov     ebx, eax
0x1800c455b  test    eax, eax
0x1800c455d  jns     short loc_1800C456B
0x1800c455f  mov     [rbp+57h+var_5C], 28Dh
0x1800c4566  jmp     loc_1800C4646
0x1800c456b  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800c456f  xor     r9d, r9d; Reserved
0x1800c4572  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c4576  xor     r8d, r8d; samDesired
0x1800c4579  call    cs:__imp_RegDeleteKeyExW
0x1800c4580  nop     dword ptr [rax+rax+00h]
0x1800c4585  mov     ebx, eax
0x1800c4587  test    eax, eax
0x1800c4589  jle     short loc_1800C4594
0x1800c458b  movzx   ebx, ax
0x1800c458e  or      ebx, 80070000h
0x1800c4594  test    ebx, ebx
0x1800c4596  jns     short loc_1800C45A4
0x1800c4598  mov     [rbp+57h+var_5C], 28Eh
0x1800c459f  jmp     loc_1800C4646
0x1800c45a4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c45a8  lea     rax, [rbp+57h+cSubKeys]
0x1800c45ac  mov     [rsp+0C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800c45b1  xor     r9d, r9d; lpReserved
0x1800c45b4  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800c45b9  xor     r8d, r8d; lpcchClass
0x1800c45bc  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800c45c1  xor     edx, edx; lpClass
0x1800c45c3  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800c45c8  mov     [rsp+0C0h+lpcValues], r14; lpcValues
0x1800c45cd  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800c45d2  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800c45d7  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x1800c45dc  call    cs:__imp_RegQueryInfoKeyA
0x1800c45e3  nop     dword ptr [rax+rax+00h]
0x1800c45e8  test    eax, eax
0x1800c45ea  jnz     short loc_1800C4646
0x1800c45ec  cmp     [rbp+57h+cSubKeys], r14d
0x1800c45f0  jnz     short loc_1800C4646
0x1800c45f2  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800c45f9  jz      short loc_1800C4613
0x1800c45fb  mov     r9, [rbp+57h+var_40]
0x1800c45ff  lea     edx, [rax+1Ah]
0x1800c4602  mov     ecx, 41Eh
0x1800c4607  lea     r8, WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids
0x1800c460e  call    WPP_SF_S
0x1800c4613  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c4617  test    rcx, rcx
0x1800c461a  jz      short loc_1800C462C
0x1800c461c  call    cs:__imp_RegCloseKey
0x1800c4623  nop     dword ptr [rax+rax+00h]
0x1800c4628  mov     [rbp+57h+hKey], r14
0x1800c462c  mov     rdx, [rbp+57h+var_40]; lpSubKey
0x1800c4630  xor     r9d, r9d; Reserved
0x1800c4633  mov     rcx, [rbp+57h+var_48]; hKey
0x1800c4637  xor     r8d, r8d; samDesired
0x1800c463a  call    cs:__imp_RegDeleteKeyExW
0x1800c4641  nop     dword ptr [rax+rax+00h]
0x1800c4646  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800c464d  jz      short loc_1800C4668
0x1800c464f  mov     edx, 1Bh
0x1800c4654  lea     r8, WPP_b095a06bc94d354f8b761c9bf32c4f2a_Traceguids
0x1800c465b  mov     ecx, 41Eh
0x1800c4660  mov     r9d, ebx
0x1800c4663  call    WPP_SF_d
0x1800c4668  mov     ecx, ebx
0x1800c466a  call    WX_WIN32_FROM_HR
0x1800c466f  lea     rcx, [rbp+57h+lpSubKey]; this
0x1800c4673  mov     ebx, eax
0x1800c4675  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800c467a  lea     rcx, [rbp+57h+var_40]; this
0x1800c467e  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800c4683  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c4687  test    rcx, rcx
0x1800c468a  jz      short loc_1800C469C
0x1800c468c  call    cs:__imp_RegCloseKey
0x1800c4693  nop     dword ptr [rax+rax+00h]
0x1800c4698  mov     [rbp+57h+hKey], r14
0x1800c469c  mov     rcx, [rbp+57h+var_48]; hKey
0x1800c46a0  test    rcx, rcx
0x1800c46a3  jz      short loc_1800C46B1
0x1800c46a5  call    cs:__imp_RegCloseKey
0x1800c46ac  nop     dword ptr [rax+rax+00h]
0x1800c46b1  mov     eax, ebx
0x1800c46b3  mov     rcx, [rbp+57h+var_20]
0x1800c46b7  xor     rcx, rsp; StackCookie
0x1800c46ba  call    __security_check_cookie
0x1800c46bf  lea     r11, [rsp+0C0h+var_10]
0x1800c46c7  mov     rbx, [r11+30h]
0x1800c46cb  mov     rsi, [r11+38h]
0x1800c46cf  mov     rsp, r11
0x1800c46d2  pop     r14
0x1800c46d4  pop     rdi
0x1800c46d5  pop     rbp
0x1800c46d6  retn
```
