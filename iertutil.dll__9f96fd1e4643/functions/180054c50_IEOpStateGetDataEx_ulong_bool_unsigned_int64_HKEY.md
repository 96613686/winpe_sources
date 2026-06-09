# IEOpStateGetDataEx(ulong,bool,unsigned __int64 *,HKEY__ * *)

- ea: `0x180054c50`
- end: `0x180054fd0`
- name: `?IEOpStateGetDataEx@@YAJK_NPEA_KPEAPEAUHKEY__@@@Z`
- size: `896`
- prototype: `int(unsigned int, bool, unsigned __int64 *, HKEY *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054600`
- `0x180062000`

## callees

- `0x180018410`
- `0x180031f00`
- `0x180049ed0`
- `0x180054c50`
- `0x180083bc2`
- `0x180083c10`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180054d9a`
- `msvcrt!wcscat_s` at `0x180054db7`
- `msvcrt!wcscat_s` at `0x180054e99`
- `msvcrt!wcscat_s` at `0x180054eb2`
- `msvcrt!wcscat_s` at `0x180054d9a`
- `msvcrt!wcscat_s` at `0x180054db7`
- `msvcrt!wcscat_s` at `0x180054e99`
- `msvcrt!wcscat_s` at `0x180054eb2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180054f42`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180054f42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054fa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054fa1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180054ef4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180054ef4`

## string_xrefs

- `0x180054dfa`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180054da8`: `\LowRegistry`

## pseudocode

```c
__int64 __fastcall IEOpStateGetDataEx(int a1, char a2, unsigned __int64 *a3, HKEY *a4)
{
  HKEY v6; // rcx
  signed int v10; // ebx
  int v11; // eax
  const wchar_t *String; // rax
  LSTATUS v14; // eax
  REGSAM samDesired; // esi
  const wchar_t *v16; // rax
  wchar_t *v17; // rdx
  LSTATUS ValueW; // eax
  __int64 v19; // rcx
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Destination[20]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[216]; // [rsp+88h] [rbp-78h] BYREF

  v6 = 0;
  hkey = 0;
  v10 = -2147467259;
  v11 = a1 - 1;
  if ( !v11 )
  {
    if ( a2 && !a4 && byte_180299E78[0] )
    {
      *a3 = qword_180299E68[0];
      return 0;
    }
    if ( (unsigned __int8)IEConfiguration_GetBool(536870915) )
    {
      v10 = OpenOrCreateAppContainerRegKey(L"Internet Explorer\\Main", 0x2001Fu, &hkey);
      goto LABEL_29;
    }
    if ( (unsigned __int8)IEConfiguration_GetBool(536870916) )
    {
      if ( !(unsigned __int8)IEConfiguration_GetBool(268435519) )
      {
        v14 = RegCreateKeyExW(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
                0,
                0,
                0,
                0x2001Fu,
                0,
                &hkey,
                0);
        goto LABEL_27;
      }
      wcscpy(Destination, L"Software\\Microsoft\\");
      memset_0(v23, 0, sizeof(v23));
      String = (const wchar_t *)IEConfiguration_GetString(268435499);
      if ( !wcscat_s(Destination, 0x80u, String) && !wcscat_s(Destination, 0x80u, L"\\LowRegistry") )
      {
        v14 = RegCreateKeyExW(HKEY_CURRENT_USER, Destination, 0, 0, 0, 0x2001Fu, 0, &hkey, 0);
        goto LABEL_27;
      }
      goto LABEL_29;
    }
LABEL_3:
    if ( a2 && !a4 && byte_180299E79 )
    {
      *a3 = qword_180299E70;
      return 0;
    }
    samDesired = (unsigned __int8)IEConfiguration_GetBool(536870916) != 0 ? 131097 : 131103;
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435519) || !(unsigned __int8)IEConfiguration_GetBool(536870917) )
    {
      v17 = (wchar_t *)L"Software\\Microsoft\\Internet Explorer\\Main";
      goto LABEL_26;
    }
    wcscpy(Destination, L"Software\\Microsoft\\");
    memset_0(v23, 0, sizeof(v23));
    v16 = (const wchar_t *)IEConfiguration_GetString(268435499);
    if ( !wcscat_s(Destination, 0x80u, v16) && !wcscat_s(Destination, 0x80u, L"\\Main") )
    {
      v17 = Destination;
LABEL_26:
      v14 = RegCreateKeyExW(HKEY_CURRENT_USER, v17, 0, 0, 0, samDesired, 0, &hkey, 0);
LABEL_27:
      v10 = v14;
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
    }
LABEL_29:
    if ( v10 >= 0 && a3 )
    {
      pcbData = 8;
      ValueW = RegGetValueW(hkey, 0, L"OperationalData", 0x40u, 0, a3, &pcbData);
      v10 = ValueW;
      if ( ValueW > 0 )
        v10 = (unsigned __int16)ValueW | 0x80070000;
      if ( v10 == -2147024894 )
      {
        *a3 = 0;
        v10 = 0;
      }
      else if ( v10 >= 0 )
      {
        v19 = (unsigned int)(a1 - 1);
        qword_180299E68[v19] = *a3;
        byte_180299E78[v19] = 1;
      }
    }
    v6 = hkey;
    goto LABEL_38;
  }
  if ( v11 == 1 )
    goto LABEL_3;
LABEL_38:
  if ( v6 )
  {
    if ( v10 >= 0 && a4 )
      *a4 = v6;
    else
      RegCloseKey(v6);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180054c50  mov     [rsp-8+arg_8], rbx
0x180054c55  push    rbp
0x180054c56  push    rsi
0x180054c57  push    rdi
0x180054c58  push    r12
0x180054c5a  push    r13
0x180054c5c  push    r14
0x180054c5e  push    r15
0x180054c60  lea     rbp, [rsp-70h]
0x180054c65  sub     rsp, 170h
0x180054c6c  mov     rax, cs:__security_cookie
0x180054c73  xor     rax, rsp
0x180054c76  mov     [rbp+0A0h+var_40], rax
0x180054c7a  mov     r13d, ecx
0x180054c7d  xor     r12d, r12d
0x180054c80  mov     eax, r13d
0x180054c83  mov     ecx, r12d
0x180054c86  mov     [rsp+1A0h+hkey], rcx
0x180054c8b  mov     r14, r9
0x180054c8e  mov     rdi, r8
0x180054c91  mov     sil, dl
0x180054c94  mov     ebx, 80004005h
0x180054c99  mov     r15d, 20000004h
0x180054c9f  sub     eax, 1
0x180054ca2  jz      short loc_180054CD8
0x180054ca4  cmp     eax, 1
0x180054ca7  jnz     loc_180054F8E
0x180054cad  test    sil, sil
0x180054cb0  jz      loc_180054E13
0x180054cb6  test    r14, r14
0x180054cb9  jnz     loc_180054E13
0x180054cbf  cmp     cs:byte_180299E79, r12b
0x180054cc6  jz      loc_180054E13
0x180054ccc  mov     rax, cs:qword_180299E70
0x180054cd3  mov     [rdi], rax
0x180054cd6  jmp     short loc_180054CF5
0x180054cd8  test    sil, sil
0x180054cdb  jz      short loc_180054CFC
0x180054cdd  test    r14, r14
0x180054ce0  jnz     short loc_180054CFC
0x180054ce2  cmp     cs:byte_180299E78, r12b
0x180054ce9  jz      short loc_180054CFC
0x180054ceb  mov     rax, cs:qword_180299E68
0x180054cf2  mov     [r8], rax
0x180054cf5  xor     eax, eax
0x180054cf7  jmp     loc_180054FA9
0x180054cfc  mov     ecx, 20000003h
0x180054d01  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180054d06  test    al, al
0x180054d08  jz      short loc_180054D27
0x180054d0a  lea     r8, [rsp+1A0h+hkey]; phkResult
0x180054d0f  mov     edx, 2001Fh; samDesired
0x180054d14  lea     rcx, aInternetExplor; "Internet Explorer\\Main"
0x180054d1b  call    ?OpenOrCreateAppContainerRegKey@@YAJPEBGKPEAPEAUHKEY__@@@Z; OpenOrCreateAppContainerRegKey(ushort const *,ulong,HKEY__ * *)
0x180054d20  mov     ebx, eax
0x180054d22  jmp     loc_180054F09
0x180054d27  mov     ecx, r15d
0x180054d2a  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180054d2f  test    al, al
0x180054d31  jz      loc_180054CAD
0x180054d37  mov     ecx, 1000003Fh
0x180054d3c  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180054d41  test    al, al
0x180054d43  jz      loc_180054DEB
0x180054d49  movups  xmm0, xmmword ptr cs:aSoftwareMicros_19; "Software\\Microsoft\\"
0x180054d50  xor     edx, edx; Val
0x180054d52  mov     r8d, 0D8h; Size
0x180054d58  movups  xmm1, xmmword ptr cs:aSoftwareMicros_19+10h; "\\Microsoft\\"
0x180054d5f  lea     rcx, [rbp+0A0h+var_118]; void *
0x180054d63  movaps  xmmword ptr [rsp+1A0h+Destination], xmm0
0x180054d68  movsd   xmm0, qword ptr cs:aSoftwareMicros_19+20h; "ft\\"
0x180054d70  movsd   [rbp+0A0h+var_120], xmm0
0x180054d75  movaps  [rsp+1A0h+var_130], xmm1
0x180054d7a  call    memset_0
0x180054d7f  mov     ecx, 1000002Bh
0x180054d84  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180054d89  mov     r15d, 80h
0x180054d8f  lea     rcx, [rsp+1A0h+Destination]; Destination
0x180054d94  mov     edx, r15d; SizeInWords
0x180054d97  mov     r8, rax; Source
0x180054d9a  call    cs:__imp_wcscat_s
0x180054da0  test    eax, eax
0x180054da2  jnz     loc_180054F09
0x180054da8  lea     r8, aLowregistry; "\\LowRegistry"
0x180054daf  mov     edx, r15d; SizeInWords
0x180054db2  lea     rcx, [rsp+1A0h+Destination]; Destination
0x180054db7  call    cs:__imp_wcscat_s
0x180054dbd  test    eax, eax
0x180054dbf  jnz     loc_180054F09
0x180054dc5  mov     [rsp+1A0h+lpdwDisposition], r12
0x180054dca  lea     rax, [rsp+1A0h+hkey]
0x180054dcf  mov     [rsp+1A0h+phkResult], rax
0x180054dd4  lea     rdx, [rsp+1A0h+Destination]
0x180054dd9  mov     [rsp+1A0h+lpSecurityAttributes], r12
0x180054dde  mov     [rsp+1A0h+samDesired], 2001Fh
0x180054de6  jmp     loc_180054EE2
0x180054deb  mov     [rsp+1A0h+lpdwDisposition], r12
0x180054df0  lea     rax, [rsp+1A0h+hkey]
0x180054df5  mov     [rsp+1A0h+phkResult], rax
0x180054dfa  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Internet Explorer"...
0x180054e01  mov     [rsp+1A0h+lpSecurityAttributes], r12
0x180054e06  mov     [rsp+1A0h+samDesired], 2001Fh
0x180054e0e  jmp     loc_180054EE2
0x180054e13  mov     ecx, r15d
0x180054e16  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180054e1b  neg     al
0x180054e1d  mov     ecx, 1000003Fh
0x180054e22  sbb     esi, esi
0x180054e24  and     esi, 0FFFFFFFAh
0x180054e27  add     esi, 2001Fh
0x180054e2d  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180054e32  test    al, al
0x180054e34  jz      loc_180054EC3
0x180054e3a  mov     ecx, 20000005h
0x180054e3f  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180054e44  test    al, al
0x180054e46  jz      short loc_180054EC3
0x180054e48  movups  xmm0, xmmword ptr cs:aSoftwareMicros_19; "Software\\Microsoft\\"
0x180054e4f  xor     edx, edx; Val
0x180054e51  mov     r8d, 0D8h; Size
0x180054e57  movups  xmm1, xmmword ptr cs:aSoftwareMicros_19+10h; "\\Microsoft\\"
0x180054e5e  lea     rcx, [rbp+0A0h+var_118]; void *
0x180054e62  movaps  xmmword ptr [rsp+1A0h+Destination], xmm0
0x180054e67  movsd   xmm0, qword ptr cs:aSoftwareMicros_19+20h; "ft\\"
0x180054e6f  movsd   [rbp+0A0h+var_120], xmm0
0x180054e74  movaps  [rsp+1A0h+var_130], xmm1
0x180054e79  call    memset_0
0x180054e7e  mov     ecx, 1000002Bh
0x180054e83  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180054e88  mov     r15d, 80h
0x180054e8e  lea     rcx, [rsp+1A0h+Destination]; Destination
0x180054e93  mov     edx, r15d; SizeInWords
0x180054e96  mov     r8, rax; Source
0x180054e99  call    cs:__imp_wcscat_s
0x180054e9f  test    eax, eax
0x180054ea1  jnz     short loc_180054F09
0x180054ea3  lea     r8, aMain; "\\Main"
0x180054eaa  mov     edx, r15d; SizeInWords
0x180054ead  lea     rcx, [rsp+1A0h+Destination]; Destination
0x180054eb2  call    cs:__imp_wcscat_s
0x180054eb8  test    eax, eax
0x180054eba  jnz     short loc_180054F09
0x180054ebc  lea     rdx, [rsp+1A0h+Destination]
0x180054ec1  jmp     short loc_180054ECA
0x180054ec3  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Internet Explorer"...
0x180054eca  mov     [rsp+1A0h+lpdwDisposition], r12; lpdwDisposition
0x180054ecf  lea     rax, [rsp+1A0h+hkey]
0x180054ed4  mov     [rsp+1A0h+phkResult], rax; phkResult
0x180054ed9  mov     [rsp+1A0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180054ede  mov     [rsp+1A0h+samDesired], esi; samDesired
0x180054ee2  xor     r9d, r9d; lpClass
0x180054ee5  mov     [rsp+1A0h+dwOptions], r12d; dwOptions
0x180054eea  xor     r8d, r8d; Reserved
0x180054eed  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180054ef4  call    cs:__imp_RegCreateKeyExW
0x180054efa  mov     ebx, eax
0x180054efc  test    eax, eax
0x180054efe  jle     short loc_180054F09
0x180054f00  movzx   ebx, ax
0x180054f03  or      ebx, 80070000h
0x180054f09  test    ebx, ebx
0x180054f0b  js      short loc_180054F89
0x180054f0d  test    rdi, rdi
0x180054f10  jz      short loc_180054F89
0x180054f12  mov     rcx, [rsp+1A0h+hkey]; hkey
0x180054f17  lea     rax, [rsp+1A0h+pcbData]
0x180054f1c  mov     [rsp+1A0h+lpSecurityAttributes], rax; pcbData
0x180054f21  lea     r8, ValueName; "OperationalData"
0x180054f28  mov     qword ptr [rsp+1A0h+samDesired], rdi; pvData
0x180054f2d  mov     r9d, 40h ; '@'; dwFlags
0x180054f33  xor     edx, edx; lpSubKey
0x180054f35  mov     qword ptr [rsp+1A0h+dwOptions], r12; pdwType
0x180054f3a  mov     [rsp+1A0h+pcbData], 8
0x180054f42  call    cs:__imp_RegGetValueW
0x180054f48  mov     ebx, eax
0x180054f4a  test    eax, eax
0x180054f4c  jle     short loc_180054F57
0x180054f4e  movzx   ebx, ax
0x180054f51  or      ebx, 80070000h
0x180054f57  cmp     ebx, 80070002h
0x180054f5d  jnz     short loc_180054F67
0x180054f5f  mov     [rdi], r12
0x180054f62  mov     ebx, r12d
0x180054f65  jmp     short loc_180054F89
0x180054f67  test    ebx, ebx
0x180054f69  js      short loc_180054F89
0x180054f6b  mov     rax, [rdi]
0x180054f6e  lea     ecx, [r13-1]
0x180054f72  lea     rdx, __ImageBase
0x180054f79  mov     rva qword_180299E68[rdx+rcx*8], rax
0x180054f81  mov     byte ptr [rcx+rdx+299E78h], 1
0x180054f89  mov     rcx, [rsp+1A0h+hkey]; hKey
0x180054f8e  test    rcx, rcx
0x180054f91  jz      short loc_180054FA7
0x180054f93  test    ebx, ebx
0x180054f95  js      short loc_180054FA1
0x180054f97  test    r14, r14
0x180054f9a  jz      short loc_180054FA1
0x180054f9c  mov     [r14], rcx
0x180054f9f  jmp     short loc_180054FA7
0x180054fa1  call    cs:__imp_RegCloseKey
0x180054fa7  mov     eax, ebx
0x180054fa9  mov     rcx, [rbp+0A0h+var_40]
0x180054fad  xor     rcx, rsp; StackCookie
0x180054fb0  call    __security_check_cookie
0x180054fb5  mov     rbx, [rsp+1A0h+arg_8]
0x180054fbd  add     rsp, 170h
0x180054fc4  pop     r15
0x180054fc6  pop     r14
0x180054fc8  pop     r13
0x180054fca  pop     r12
0x180054fcc  pop     rdi
0x180054fcd  pop     rsi
0x180054fce  pop     rbp
0x180054fcf  retn
```
