# LocalDB::GetUserInstanceDllPath(char *,ulong,LocalDBErrorState *)

- ea: `0x18017d980`
- end: `0x18017dd58`
- name: `?GetUserInstanceDllPath@LocalDB@@AEAAJPEADKPEAW4LocalDBErrorState@@@Z`
- size: `984`
- prototype: `__int64 __fastcall(LocalDB *__hidden this, char *, unsigned int, enum LocalDBErrorState *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18017e590`

## callees

- `0x180003d80`
- `0x18000451c`
- `0x18017d800`
- `0x18017d980`
- `0x1801a65e1`
- `0x1801a65f0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyA` at `0x18017da9a`
- `ADVAPI32!RegQueryInfoKeyA` at `0x18017da9a`
- `ADVAPI32!RegEnumKeyExA` at `0x18017daef`
- `ADVAPI32!RegEnumKeyExA` at `0x18017daef`
- `ADVAPI32!RegQueryValueExA` at `0x18017dc3c`
- `ADVAPI32!RegQueryValueExA` at `0x18017dc3c`
- `ADVAPI32!RegOpenKeyExA` at `0x18017da4d`
- `ADVAPI32!RegOpenKeyExA` at `0x18017dbfb`
- `ADVAPI32!RegOpenKeyExA` at `0x18017da4d`
- `ADVAPI32!RegOpenKeyExA` at `0x18017dbfb`
- `ADVAPI32!RegCloseKey` at `0x18017dd0b`
- `ADVAPI32!RegCloseKey` at `0x18017dd20`
- `ADVAPI32!RegCloseKey` at `0x18017dd0b`
- `ADVAPI32!RegCloseKey` at `0x18017dd20`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18017dc9f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18017dcd4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18017dc9f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18017dcd4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18017dce0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18017dce0`

## string_xrefs

- `0x18017d9b8`: `SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\`
- `0x18017dc30`: `InstanceAPIPath`

## pseudocode

```c
__int64 __fastcall LocalDB::GetUserInstanceDllPath(LocalDB *this, char *a2, DWORD a3, enum LocalDBErrorState *a4)
{
  DWORD v4; // edi
  unsigned __int16 v8; // si
  unsigned __int16 v9; // r15
  unsigned int LocalDBVersion; // ebx
  CHAR *v11; // rdx
  CHAR *v12; // rax
  __int64 v13; // rcx
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int64 v22; // rdx
  __int64 v23; // rcx
  DWORD v24; // edi
  size_t v25; // rax
  size_t v26; // r8
  unsigned __int16 v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v29; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Size; // [rsp+68h] [rbp-98h]
  DWORD Size_4; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  DWORD cSubKeys; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchName; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD Type; // [rsp+88h] [rbp-78h] BYREF
  CHAR SubKey[272]; // [rsp+90h] [rbp-70h] BYREF
  CHAR v38[272]; // [rsp+1A0h] [rbp+A0h] BYREF
  CHAR Name[272]; // [rsp+2B0h] [rbp+1B0h] BYREF
  BYTE Data[272]; // [rsp+3C0h] [rbp+2C0h] BYREF

  v4 = 0;
  strcpy(SubKey, "SOFTWARE\\Microsoft\\Microsoft SQL Server Local DB\\Installed Versions\\");
  v8 = 0;
  v9 = 0;
  Size = a3;
  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  Type = 0;
  Size_4 = 260;
  v38[0] = 0;
  v29 = 0;
  v28[0] = 0;
  LocalDBVersion = RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 9u, &hKey);
  if ( LocalDBVersion )
  {
    *(_DWORD *)a4 = 0;
  }
  else
  {
    LocalDBVersion = RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !LocalDBVersion )
    {
      if ( cSubKeys )
      {
        while ( 1 )
        {
          cchName = 260;
          LocalDBVersion = RegEnumKeyExA(hKey, v4, Name, &cchName, 0, 0, 0, 0);
          if ( LocalDBVersion )
            break;
          if ( cchName >= 0x104 )
            goto LABEL_17;
          LocalDBVersion = LocalDB::GetLocalDBVersion(this, Name, &v29, v28);
          if ( LocalDBVersion )
            goto LABEL_18;
          if ( v29 > v8 || v29 == v8 && v28[0] > v9 )
          {
            v8 = v29;
            v11 = v38;
            v9 = v28[0];
            v12 = Name;
            v13 = 2;
            do
            {
              v11 += 128;
              v14 = *(_OWORD *)v12;
              v15 = *((_OWORD *)v12 + 1);
              v12 += 128;
              *((_OWORD *)v11 - 8) = v14;
              v16 = *((_OWORD *)v12 - 6);
              *((_OWORD *)v11 - 7) = v15;
              v17 = *((_OWORD *)v12 - 5);
              *((_OWORD *)v11 - 6) = v16;
              v18 = *((_OWORD *)v12 - 4);
              *((_OWORD *)v11 - 5) = v17;
              v19 = *((_OWORD *)v12 - 3);
              *((_OWORD *)v11 - 4) = v18;
              v20 = *((_OWORD *)v12 - 2);
              *((_OWORD *)v11 - 3) = v19;
              v21 = *((_OWORD *)v12 - 1);
              *((_OWORD *)v11 - 2) = v20;
              *((_OWORD *)v11 - 1) = v21;
              --v13;
            }
            while ( v13 );
            *(_DWORD *)v11 = *(_DWORD *)v12;
          }
          if ( ++v4 >= cSubKeys )
          {
            if ( !v38[0] )
            {
LABEL_17:
              LocalDBVersion = 13;
LABEL_18:
              *(_DWORD *)a4 = 1;
              break;
            }
            LocalDBVersion = RegOpenKeyExA(hKey, v38, 0, 1u, &phkResult);
            if ( LocalDBVersion )
            {
              *(_DWORD *)a4 = 1;
              break;
            }
            LocalDBVersion = RegQueryValueExA(phkResult, "InstanceAPIPath", 0, &Type, Data, &Size_4);
            if ( LocalDBVersion )
            {
              *(_DWORD *)a4 = (LocalDBVersion == 234) + 2;
              break;
            }
            v24 = Size_4;
            if ( Size_4 < 0x104 && (v25 = Size, Size_4 < Size) && Type == 1 )
            {
              v26 = Size_4;
              if ( Size_4 >= 0x104uLL )
                _report_rangecheckfailure(v23, v22, Size_4);
              Data[Size_4] = 0;
              if ( v24 )
              {
                if ( a2 )
                {
                  if ( v25 >= v24 )
                  {
                    memcpy_0(a2, Data, v26);
                    a2[v24] = 0;
                    break;
                  }
                  memset_0(a2, 0, v25);
                  *_errno() = 34;
                }
                else
                {
                  *_errno() = 22;
                }
                _invalid_parameter_noinfo();
                v24 = Size_4;
              }
              a2[v24] = 0;
            }
            else
            {
              LocalDBVersion = 13;
              *(_DWORD *)a4 = 3;
            }
            break;
          }
        }
      }
      else
      {
        LocalDBVersion = 13;
        *(_DWORD *)a4 = 0;
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return LocalDBVersion;
}

```

## disassembly

```asm
0x18017d980  mov     [rsp-8+arg_0], rbx
0x18017d985  push    rbp
0x18017d986  push    rsi
0x18017d987  push    rdi
0x18017d988  push    r12
0x18017d98a  push    r13
0x18017d98c  push    r14
0x18017d98e  push    r15
0x18017d990  lea     rbp, [rsp-3E0h]
0x18017d998  sub     rsp, 4E0h
0x18017d99f  mov     rax, cs:__security_cookie
0x18017d9a6  xor     rax, rsp
0x18017d9a9  mov     [rbp+410h+var_40], rax
0x18017d9b0  mov     eax, dword ptr cs:aSoftwareMicros_1+40h; "ons\\"
0x18017d9b6  xor     edi, edi
0x18017d9b8  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x18017d9bf  mov     r14, r9
0x18017d9c2  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_1+10h; "ft\\Microsoft SQL Server Local DB\\Inst"...
0x18017d9c9  mov     r12, rdx
0x18017d9cc  mov     dword ptr [rbp+410h+var_440], eax
0x18017d9cf  lea     rdx, [rbp+410h+SubKey]; lpSubKey
0x18017d9d3  movzx   eax, byte ptr cs:aSoftwareMicros_1+44h; ""
0x18017d9da  mov     r13, rcx
0x18017d9dd  mov     [rbp+410h+var_440+4], al
0x18017d9e0  mov     r9d, 9; samDesired
0x18017d9e6  movaps  xmmword ptr [rbp+410h+SubKey], xmm0
0x18017d9ea  lea     rax, [rsp+510h+hKey]
0x18017d9ef  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_1+20h; " Server Local DB\\Installed Versions\\"
0x18017d9f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18017d9fd  movaps  [rbp+410h+var_470], xmm1
0x18017da01  movzx   esi, di
0x18017da04  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_1+30h; "\\Installed Versions\\"
0x18017da0b  movzx   r15d, di
0x18017da0f  mov     dword ptr [rsp+510h+Size], r8d
0x18017da14  xor     r8d, r8d; ulOptions
0x18017da17  mov     [rsp+510h+phkResult], rax; phkResult
0x18017da1c  mov     [rsp+510h+hKey], rdi
0x18017da21  mov     [rsp+510h+var_498], rdi
0x18017da26  mov     [rbp+410h+cSubKeys], edi
0x18017da29  mov     [rbp+410h+Type], edi
0x18017da2c  mov     dword ptr [rsp+510h+Size+4], 104h
0x18017da34  mov     [rbp+410h+var_370], dil
0x18017da3b  mov     [rsp+510h+var_4AC], di
0x18017da40  mov     [rsp+510h+var_4B0], di
0x18017da45  movaps  [rbp+410h+var_460], xmm0
0x18017da49  movaps  [rbp+410h+var_450], xmm1
0x18017da4d  call    cs:__imp_RegOpenKeyExA
0x18017da53  mov     ebx, eax
0x18017da55  test    eax, eax
0x18017da57  jz      short loc_18017DA61
0x18017da59  mov     [r14], edi
0x18017da5c  jmp     loc_18017DD01
0x18017da61  mov     rcx, [rsp+510h+hKey]; hKey
0x18017da66  lea     rax, [rbp+410h+cSubKeys]
0x18017da6a  mov     [rsp+510h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18017da6f  xor     r9d, r9d; lpReserved
0x18017da72  mov     [rsp+510h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18017da77  xor     r8d, r8d; lpcchClass
0x18017da7a  mov     [rsp+510h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18017da7f  xor     edx, edx; lpClass
0x18017da81  mov     [rsp+510h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18017da86  mov     [rsp+510h+lpcValues], rdi; lpcValues
0x18017da8b  mov     [rsp+510h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18017da90  mov     [rsp+510h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x18017da95  mov     [rsp+510h+phkResult], rax; lpcSubKeys
0x18017da9a  call    cs:__imp_RegQueryInfoKeyA
0x18017daa0  mov     ebx, eax
0x18017daa2  test    eax, eax
0x18017daa4  jnz     loc_18017DD01
0x18017daaa  mov     eax, [rbp+410h+cSubKeys]
0x18017daad  test    eax, eax
0x18017daaf  jnz     short loc_18017DAC0
0x18017dab1  mov     ebx, 0Dh
0x18017dab6  mov     [r14], edi
0x18017dab9  jmp     loc_18017DD01
0x18017dac0  mov     rcx, [rsp+510h+hKey]; hKey
0x18017dac5  lea     r9, [rbp+410h+cchName]; lpcchName
0x18017dac9  xor     eax, eax
0x18017dacb  mov     [rbp+410h+cchName], 104h
0x18017dad2  mov     [rsp+510h+lpcValues], rax; lpftLastWriteTime
0x18017dad7  lea     r8, [rbp+410h+Name]; lpName
0x18017dade  mov     [rsp+510h+lpcbMaxClassLen], rax; lpcchClass
0x18017dae3  mov     edx, edi; dwIndex
0x18017dae5  mov     [rsp+510h+lpcbMaxSubKeyLen], rax; lpClass
0x18017daea  mov     [rsp+510h+phkResult], rax; lpReserved
0x18017daef  call    cs:__imp_RegEnumKeyExA
0x18017daf5  mov     ebx, eax
0x18017daf7  test    eax, eax
0x18017daf9  jnz     loc_18017DCFF
0x18017daff  cmp     [rbp+410h+cchName], 104h
0x18017db06  jnb     loc_18017DBCB
0x18017db0c  lea     r9, [rsp+510h+var_4B0]; unsigned __int16 *
0x18017db11  mov     rcx, r13; this
0x18017db14  lea     r8, [rsp+510h+var_4AC]; unsigned __int16 *
0x18017db19  lea     rdx, [rbp+410h+Name]; char *
0x18017db20  call    ?GetLocalDBVersion@LocalDB@@AEAAKPEADPEAG1@Z; LocalDB::GetLocalDBVersion(char *,ushort *,ushort *)
0x18017db25  mov     ebx, eax
0x18017db27  test    eax, eax
0x18017db29  jnz     loc_18017DBD0
0x18017db2f  movzx   eax, [rsp+510h+var_4AC]
0x18017db34  movzx   ecx, [rsp+510h+var_4B0]
0x18017db39  cmp     ax, si
0x18017db3c  ja      short loc_18017DB46
0x18017db3e  jnz     short loc_18017DBB7
0x18017db40  cmp     cx, r15w
0x18017db44  jbe     short loc_18017DBB7
0x18017db46  movzx   esi, ax
0x18017db49  lea     rdx, [rbp+410h+var_370]
0x18017db50  movzx   r15d, cx
0x18017db54  lea     rax, [rbp+410h+Name]
0x18017db5b  mov     ecx, 2
0x18017db60  lea     rdx, [rdx+80h]
0x18017db67  movups  xmm0, xmmword ptr [rax]
0x18017db6a  movups  xmm1, xmmword ptr [rax+10h]
0x18017db6e  lea     rax, [rax+80h]
0x18017db75  movups  xmmword ptr [rdx-80h], xmm0
0x18017db79  movups  xmm0, xmmword ptr [rax-60h]
0x18017db7d  movups  xmmword ptr [rdx-70h], xmm1
0x18017db81  movups  xmm1, xmmword ptr [rax-50h]
0x18017db85  movups  xmmword ptr [rdx-60h], xmm0
0x18017db89  movups  xmm0, xmmword ptr [rax-40h]
0x18017db8d  movups  xmmword ptr [rdx-50h], xmm1
0x18017db91  movups  xmm1, xmmword ptr [rax-30h]
0x18017db95  movups  xmmword ptr [rdx-40h], xmm0
0x18017db99  movups  xmm0, xmmword ptr [rax-20h]
0x18017db9d  movups  xmmword ptr [rdx-30h], xmm1
0x18017dba1  movups  xmm1, xmmword ptr [rax-10h]
0x18017dba5  movups  xmmword ptr [rdx-20h], xmm0
0x18017dba9  movups  xmmword ptr [rdx-10h], xmm1
0x18017dbad  sub     rcx, 1
0x18017dbb1  jnz     short loc_18017DB60
0x18017dbb3  mov     ecx, [rax]
0x18017dbb5  mov     [rdx], ecx
0x18017dbb7  inc     edi
0x18017dbb9  cmp     edi, [rbp+410h+cSubKeys]
0x18017dbbc  jb      loc_18017DAC0
0x18017dbc2  cmp     [rbp+410h+var_370], 0
0x18017dbc9  jnz     short loc_18017DBDC
0x18017dbcb  mov     ebx, 0Dh
0x18017dbd0  mov     dword ptr [r14], 1
0x18017dbd7  jmp     loc_18017DCFF
0x18017dbdc  mov     rcx, [rsp+510h+hKey]; hKey
0x18017dbe1  lea     rax, [rsp+510h+var_498]
0x18017dbe6  mov     r9d, 1; samDesired
0x18017dbec  mov     [rsp+510h+phkResult], rax; phkResult
0x18017dbf1  xor     r8d, r8d; ulOptions
0x18017dbf4  lea     rdx, [rbp+410h+var_370]; lpSubKey
0x18017dbfb  call    cs:__imp_RegOpenKeyExA
0x18017dc01  mov     ebx, eax
0x18017dc03  test    eax, eax
0x18017dc05  jz      short loc_18017DC13
0x18017dc07  mov     dword ptr [r14], 1
0x18017dc0e  jmp     loc_18017DCFF
0x18017dc13  mov     rcx, [rsp+510h+var_498]; hKey
0x18017dc18  lea     rax, [rsp+510h+Size+4]
0x18017dc1d  mov     [rsp+510h+lpcbMaxSubKeyLen], rax; lpcbData
0x18017dc22  lea     r9, [rbp+410h+Type]; lpType
0x18017dc26  lea     rax, [rbp+410h+Data]
0x18017dc2d  xor     r8d, r8d; lpReserved
0x18017dc30  lea     rdx, aInstanceapipat; "InstanceAPIPath"
0x18017dc37  mov     [rsp+510h+phkResult], rax; lpData
0x18017dc3c  call    cs:__imp_RegQueryValueExA
0x18017dc42  mov     ebx, eax
0x18017dc44  test    eax, eax
0x18017dc46  jz      short loc_18017DC60
0x18017dc48  xor     edi, edi
0x18017dc4a  cmp     ebx, 0EAh
0x18017dc50  mov     eax, edi
0x18017dc52  setz    al
0x18017dc55  add     eax, 2
0x18017dc58  mov     [r14], eax
0x18017dc5b  jmp     loc_18017DD01
0x18017dc60  mov     edi, dword ptr [rsp+510h+Size+4]
0x18017dc64  cmp     edi, 104h
0x18017dc6a  jnb     loc_18017DCF3
0x18017dc70  mov     eax, dword ptr [rsp+510h+Size]
0x18017dc74  cmp     edi, eax
0x18017dc76  jnb     short loc_18017DCF3
0x18017dc78  cmp     [rbp+410h+Type], 1
0x18017dc7c  jnz     short loc_18017DCF3
0x18017dc7e  mov     r8d, edi; Size
0x18017dc81  cmp     rdi, 104h
0x18017dc88  jnb     loc_18017DD52
0x18017dc8e  mov     [rbp+rdi+410h+Data], 0
0x18017dc96  test    edi, edi
0x18017dc98  jz      short loc_18017DCEA
0x18017dc9a  test    r12, r12
0x18017dc9d  jnz     short loc_18017DCAD
0x18017dc9f  call    cs:__imp__errno
0x18017dca5  mov     dword ptr [rax], 16h
0x18017dcab  jmp     short loc_18017DCE0
0x18017dcad  mov     rcx, r12; void *
0x18017dcb0  cmp     rax, r8
0x18017dcb3  jb      short loc_18017DCCA
0x18017dcb5  lea     rdx, [rbp+410h+Data]; Src
0x18017dcbc  call    memcpy_0
0x18017dcc1  mov     eax, edi
0x18017dcc3  mov     byte ptr [rax+r12], 0
0x18017dcc8  jmp     short loc_18017DCFF
0x18017dcca  mov     r8, rax; Size
0x18017dccd  xor     edx, edx; Val
0x18017dccf  call    memset_0
0x18017dcd4  call    cs:__imp__errno
0x18017dcda  mov     dword ptr [rax], 22h ; '"'
0x18017dce0  call    cs:__imp__invalid_parameter_noinfo
0x18017dce6  mov     edi, dword ptr [rsp+510h+Size+4]
0x18017dcea  mov     eax, edi
0x18017dcec  mov     byte ptr [rax+r12], 0
0x18017dcf1  jmp     short loc_18017DCFF
0x18017dcf3  mov     ebx, 0Dh
0x18017dcf8  mov     dword ptr [r14], 3
0x18017dcff  xor     edi, edi
0x18017dd01  mov     rcx, [rsp+510h+hKey]; hKey
0x18017dd06  test    rcx, rcx
0x18017dd09  jz      short loc_18017DD16
0x18017dd0b  call    cs:__imp_RegCloseKey
0x18017dd11  mov     [rsp+510h+hKey], rdi
0x18017dd16  mov     rcx, [rsp+510h+var_498]; hKey
0x18017dd1b  test    rcx, rcx
0x18017dd1e  jz      short loc_18017DD26
0x18017dd20  call    cs:__imp_RegCloseKey
0x18017dd26  mov     eax, ebx
0x18017dd28  mov     rcx, [rbp+410h+var_40]
0x18017dd2f  xor     rcx, rsp; StackCookie
0x18017dd32  call    __security_check_cookie
0x18017dd37  mov     rbx, [rsp+510h+arg_0]
0x18017dd3f  add     rsp, 4E0h
0x18017dd46  pop     r15
0x18017dd48  pop     r14
0x18017dd4a  pop     r13
0x18017dd4c  pop     r12
0x18017dd4e  pop     rdi
0x18017dd4f  pop     rsi
0x18017dd50  pop     rbp
0x18017dd51  retn
0x18017dd52  call    __report_rangecheckfailure
```
