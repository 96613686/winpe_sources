# GetUserDirFromRegistry(ushort * const,ushort *,ulong)

- ea: `0x180021078`
- end: `0x180021534`
- name: `?GetUserDirFromRegistry@@YAKQEAGPEAGK@Z`
- size: `1212`
- prototype: `__int64 __fastcall(unsigned __int16 *const, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006c60`

## callees

- `0x180013f2c`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x180021078`
- `0x1800244b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180021430`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180021430`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800213a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800213a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800211a6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800211a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002126d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002135f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002126d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002135f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002120f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002120f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800214e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800214e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800214fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800214fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800212fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800212fe`

## string_xrefs

- `0x180021156`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall GetUserDirFromRegistry(unsigned __int16 *const a1, unsigned __int16 *a2)
{
  BYTE *v4; // r14
  __int64 v5; // rdi
  __int64 v6; // rax
  unsigned int v7; // eax
  __int64 v8; // r9
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueName[20]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v23[2]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t v24; // [rsp+88h] [rbp-78h]
  WCHAR SubKey[58]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v26[668]; // [rsp+104h] [rbp+4h] BYREF

  wcscpy(SubKey, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\");
  v4 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  memset_0(v26, 0, 0x294u);
  v24 = aAppdataRoaming[16];
  v23[0] = *(_OWORD *)L"\\AppData\\Roaming";
  v23[1] = *(_OWORD *)L"\\Roaming";
  wcscpy(ValueName, L"ProfileImagePath");
  if ( !a1 || !*a1 )
  {
    v12 = WPP_GLOBAL_Control;
    v11 = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      return v11;
    v13 = 17;
    goto LABEL_58;
  }
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v7 = _o_wcsncat_s(SubKey, 776, a1, (int)v6);
  v8 = v7;
  if ( !v7 )
  {
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_59;
      v13 = 19;
    }
    else
    {
      v11 = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
      if ( v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_59;
        v13 = 20;
      }
      else
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)v23 + v14) );
        if ( cbData + (unsigned int)v14 < 0x105 )
        {
          v4 = (BYTE *)LocalAlloc(0, cbData);
          if ( v4 )
          {
            v11 = RegQueryValueExW(hKey, ValueName, 0, &Type, v4, &cbData);
            if ( !v11 )
            {
              v15 = _o_wcscpy_s(a2, 261, v4);
              v8 = v15;
              if ( v15 )
              {
                v9 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
                {
                  goto LABEL_10;
                }
                v10 = 24;
              }
              else
              {
                if ( a2 )
                {
                  v16 = -1;
                  do
                    ++v16;
                  while ( a2[v16] );
                }
                else
                {
                  LODWORD(v16) = 0;
                }
                if ( a2[(int)v16 - 1] == 92 )
                {
                  if ( a2 )
                  {
                    do
                      ++v5;
                    while ( a2[v5] );
                  }
                  else
                  {
                    LODWORD(v5) = 0;
                  }
                  a2[(int)v5 - 1] = 0;
                }
                v17 = _o_wcscat_s(a2, 261, v23);
                v8 = v17;
                if ( !v17 )
                {
                  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
                  {
                    WPP_SF_SS(
                      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                      26,
                      (unsigned int)WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids,
                      (_DWORD)a2,
                      (__int64)a1);
                  }
                  goto LABEL_59;
                }
                v9 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
                {
                  goto LABEL_10;
                }
                v10 = 25;
              }
              goto LABEL_9;
            }
            v12 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
            {
              goto LABEL_59;
            }
            v13 = 23;
          }
          else
          {
            v11 = 14;
            v12 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
            {
              goto LABEL_59;
            }
            v13 = 22;
          }
        }
        else
        {
          v11 = 1462;
          v12 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
            goto LABEL_59;
          v13 = 21;
        }
      }
    }
LABEL_58:
    WPP_SF_(*(_QWORD *)(v12 + 16), v13, WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids);
    goto LABEL_59;
  }
  v9 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
    goto LABEL_10;
  v10 = 18;
LABEL_9:
  WPP_SF_d(*(_QWORD *)(v9 + 16), v10, WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids, v8);
LABEL_10:
  v11 = 31;
LABEL_59:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 )
    LocalFree(v4);
  return v11;
}

```

## disassembly

```asm
0x180021078  mov     [rsp-8+arg_10], rbx
0x18002107d  mov     [rsp-8+arg_18], rsi
0x180021082  push    rbp
0x180021083  push    rdi
0x180021084  push    r12
0x180021086  push    r14
0x180021088  push    r15
0x18002108a  lea     rbp, [rsp-2B0h]
0x180021092  sub     rsp, 3B0h
0x180021099  mov     rax, cs:__security_cookie
0x1800210a0  xor     rax, rsp
0x1800210a3  mov     [rbp+2D0h+var_30], rax
0x1800210aa  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800210b1  xor     r12d, r12d
0x1800210b4  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+10h; "\\Microsoft\\Windows NT\\CurrentVersion"...
0x1800210bb  mov     rsi, rdx
0x1800210be  mov     eax, dword ptr cs:aSoftwareMicros_0+70h; "\\"
0x1800210c4  mov     r15, rcx
0x1800210c7  movaps  xmmword ptr [rbp+2D0h+SubKey], xmm0
0x1800210cb  lea     rcx, [rbp+2D0h+var_2CC]; void *
0x1800210cf  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+20h; "ft\\Windows NT\\CurrentVersion\\Profile"...
0x1800210d6  xor     edx, edx; Val
0x1800210d8  movaps  [rbp+2D0h+var_320], xmm0
0x1800210dc  mov     r8d, 294h; Size
0x1800210e2  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+40h; "rrentVersion\\ProfileList\\"
0x1800210e9  mov     r14d, r12d
0x1800210ec  movaps  [rbp+2D0h+var_330], xmm1
0x1800210f0  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+30h; "ws NT\\CurrentVersion\\ProfileList\\"
0x1800210f7  movaps  [rbp+2D0h+var_300], xmm0
0x1800210fb  movaps  xmm0, xmmword ptr cs:aSoftwareMicros_0+60h; "fileList\\"
0x180021102  movaps  [rbp+2D0h+var_310], xmm1
0x180021106  movaps  xmm1, xmmword ptr cs:aSoftwareMicros_0+50h; "sion\\ProfileList\\"
0x18002110d  movaps  [rbp+2D0h+var_2E0], xmm0
0x180021111  mov     [rsp+3D0h+hKey], r12
0x180021116  mov     [rsp+3D0h+cbData], r12d
0x18002111b  mov     [rsp+3D0h+Type], r12d
0x180021120  movaps  [rbp+2D0h+var_2F0], xmm1
0x180021124  mov     [rbp+2D0h+var_2D0], eax
0x180021127  call    memset_0
0x18002112c  movzx   eax, word ptr cs:aAppdataRoaming+20h; ""
0x180021133  mov     [rbp+2D0h+var_348], ax
0x180021137  movzx   eax, word ptr cs:aProfileimagepa+20h; ""
0x18002113e  mov     [rsp+3D0h+var_370], ax
0x180021143  movups  xmm0, xmmword ptr cs:aAppdataRoaming; "\\AppData\\Roaming"
0x18002114a  movups  xmm1, xmmword ptr cs:aAppdataRoaming+10h; "\\Roaming"
0x180021151  movups  [rsp+3D0h+var_368], xmm0
0x180021156  movups  xmm0, xmmword ptr cs:aProfileimagepa; "ProfileImagePath"
0x18002115d  movups  [rsp+3D0h+var_358], xmm1
0x180021162  movups  xmm1, xmmword ptr cs:aProfileimagepa+10h; "magePath"
0x180021169  movups  xmmword ptr [rsp+3D0h+ValueName], xmm0
0x18002116e  movups  [rsp+3D0h+var_380], xmm1
0x180021173  test    r15, r15
0x180021176  jz      loc_1800214A6
0x18002117c  cmp     [r15], r12w
0x180021180  jz      loc_1800214A6
0x180021186  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002118a  mov     rax, rdi
0x18002118d  inc     rax
0x180021190  cmp     [r15+rax*2], r12w
0x180021195  jnz     short loc_18002118D
0x180021197  movsxd  r9, eax
0x18002119a  lea     rcx, [rbp+2D0h+SubKey]
0x18002119e  mov     r8, r15
0x1800211a1  mov     edx, 308h
0x1800211a6  call    cs:__imp__o_wcsncat_s
0x1800211ad  nop     dword ptr [rax+rax+00h]
0x1800211b2  mov     r9d, eax
0x1800211b5  test    eax, eax
0x1800211b7  jz      short loc_1800211F1
0x1800211b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211c0  lea     rax, WPP_GLOBAL_Control
0x1800211c7  cmp     rcx, rax
0x1800211ca  jz      short loc_1800211E7
0x1800211cc  test    byte ptr [rcx+1Ch], 4
0x1800211d0  jz      short loc_1800211E7
0x1800211d2  mov     edx, 12h
0x1800211d7  mov     rcx, [rcx+10h]
0x1800211db  lea     r8, WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids
0x1800211e2  call    WPP_SF_d
0x1800211e7  mov     ebx, 1Fh
0x1800211ec  jmp     loc_1800214D7
0x1800211f1  lea     rax, [rsp+3D0h+hKey]
0x1800211f6  mov     r9d, 20019h; samDesired
0x1800211fc  xor     r8d, r8d; ulOptions
0x1800211ff  mov     [rsp+3D0h+phkResult], rax; phkResult
0x180021204  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180021208  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002120f  call    cs:__imp_RegOpenKeyExW
0x180021216  nop     dword ptr [rax+rax+00h]
0x18002121b  mov     ebx, eax
0x18002121d  test    eax, eax
0x18002121f  jz      short loc_18002124C
0x180021221  mov     rcx, cs:WPP_GLOBAL_Control
0x180021228  lea     rax, WPP_GLOBAL_Control
0x18002122f  cmp     rcx, rax
0x180021232  jz      loc_1800214D7
0x180021238  test    byte ptr [rcx+1Ch], 4
0x18002123c  jz      loc_1800214D7
0x180021242  mov     edx, 13h
0x180021247  jmp     loc_1800214C7
0x18002124c  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180021251  lea     rax, [rsp+3D0h+cbData]
0x180021256  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x18002125b  lea     r9, [rsp+3D0h+Type]; lpType
0x180021260  xor     r8d, r8d; lpReserved
0x180021263  mov     [rsp+3D0h+phkResult], r12; lpData
0x180021268  lea     rdx, [rsp+3D0h+ValueName]; lpValueName
0x18002126d  call    cs:__imp_RegQueryValueExW
0x180021274  nop     dword ptr [rax+rax+00h]
0x180021279  mov     ebx, eax
0x18002127b  test    eax, eax
0x18002127d  jz      short loc_1800212AA
0x18002127f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021286  lea     rax, WPP_GLOBAL_Control
0x18002128d  cmp     rcx, rax
0x180021290  jz      loc_1800214D7
0x180021296  test    byte ptr [rcx+1Ch], 4
0x18002129a  jz      loc_1800214D7
0x1800212a0  mov     edx, 14h
0x1800212a5  jmp     loc_1800214C7
0x1800212aa  lea     rcx, [rsp+3D0h+var_368]
0x1800212af  mov     rax, rdi
0x1800212b2  inc     rax
0x1800212b5  cmp     [rcx+rax*2], r12w
0x1800212ba  jnz     short loc_1800212B2
0x1800212bc  mov     ecx, [rsp+3D0h+cbData]
0x1800212c0  add     eax, ecx
0x1800212c2  cmp     eax, 105h
0x1800212c7  jb      short loc_1800212F9
0x1800212c9  mov     ebx, 5B6h
0x1800212ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212d5  lea     rax, WPP_GLOBAL_Control
0x1800212dc  cmp     rcx, rax
0x1800212df  jz      loc_1800214D7
0x1800212e5  test    byte ptr [rcx+1Ch], 4
0x1800212e9  jz      loc_1800214D7
0x1800212ef  mov     edx, 15h
0x1800212f4  jmp     loc_1800214C7
0x1800212f9  mov     rdx, rcx; uBytes
0x1800212fc  xor     ecx, ecx; uFlags
0x1800212fe  call    cs:__imp_LocalAlloc
0x180021305  nop     dword ptr [rax+rax+00h]
0x18002130a  mov     r14, rax
0x18002130d  test    rax, rax
0x180021310  jnz     short loc_18002133E
0x180021312  lea     ebx, [rax+0Eh]
0x180021315  mov     rcx, cs:WPP_GLOBAL_Control
0x18002131c  lea     rax, WPP_GLOBAL_Control
0x180021323  cmp     rcx, rax
0x180021326  jz      loc_1800214D7
0x18002132c  test    byte ptr [rcx+1Ch], 4
0x180021330  jz      loc_1800214D7
0x180021336  lea     edx, [rbx+8]
0x180021339  jmp     loc_1800214C7
0x18002133e  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180021343  lea     rax, [rsp+3D0h+cbData]
0x180021348  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x18002134d  lea     r9, [rsp+3D0h+Type]; lpType
0x180021352  xor     r8d, r8d; lpReserved
0x180021355  mov     [rsp+3D0h+phkResult], r14; lpData
0x18002135a  lea     rdx, [rsp+3D0h+ValueName]; lpValueName
0x18002135f  call    cs:__imp_RegQueryValueExW
0x180021366  nop     dword ptr [rax+rax+00h]
0x18002136b  mov     ebx, eax
0x18002136d  test    eax, eax
0x18002136f  jz      short loc_18002139C
0x180021371  mov     rcx, cs:WPP_GLOBAL_Control
0x180021378  lea     rax, WPP_GLOBAL_Control
0x18002137f  cmp     rcx, rax
0x180021382  jz      loc_1800214D7
0x180021388  test    byte ptr [rcx+1Ch], 4
0x18002138c  jz      loc_1800214D7
0x180021392  mov     edx, 17h
0x180021397  jmp     loc_1800214C7
0x18002139c  mov     r8, r14
0x18002139f  mov     edx, 105h
0x1800213a4  mov     rcx, rsi
0x1800213a7  call    cs:__imp__o_wcscpy_s
0x1800213ae  nop     dword ptr [rax+rax+00h]
0x1800213b3  mov     r9d, eax
0x1800213b6  test    eax, eax
0x1800213b8  jz      short loc_1800213E5
0x1800213ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213c1  lea     rax, WPP_GLOBAL_Control
0x1800213c8  cmp     rcx, rax
0x1800213cb  jz      loc_1800211E7
0x1800213d1  test    byte ptr [rcx+1Ch], 4
0x1800213d5  jz      loc_1800211E7
0x1800213db  mov     edx, 18h
0x1800213e0  jmp     loc_1800211D7
0x1800213e5  test    rsi, rsi
0x1800213e8  jz      short loc_1800213F9
0x1800213ea  mov     rax, rdi
0x1800213ed  inc     rax
0x1800213f0  cmp     [rsi+rax*2], r12w
0x1800213f5  jnz     short loc_1800213ED
0x1800213f7  jmp     short loc_1800213FC
0x1800213f9  mov     eax, r12d
0x1800213fc  cdqe
0x1800213fe  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x180021404  jnz     short loc_180021423
0x180021406  test    rsi, rsi
0x180021409  jz      short loc_180021417
0x18002140b  inc     rdi
0x18002140e  cmp     [rsi+rdi*2], r12w
0x180021413  jnz     short loc_18002140B
0x180021415  jmp     short loc_18002141A
0x180021417  mov     edi, r12d
0x18002141a  movsxd  rcx, edi
0x18002141d  mov     [rsi+rcx*2-2], r12w
0x180021423  lea     r8, [rsp+3D0h+var_368]
0x180021428  mov     edx, 105h
0x18002142d  mov     rcx, rsi
0x180021430  call    cs:__imp__o_wcscat_s
0x180021437  nop     dword ptr [rax+rax+00h]
0x18002143c  mov     r9d, eax
0x18002143f  test    eax, eax
0x180021441  jz      short loc_18002146E
0x180021443  mov     rcx, cs:WPP_GLOBAL_Control
0x18002144a  lea     rax, WPP_GLOBAL_Control
0x180021451  cmp     rcx, rax
0x180021454  jz      loc_1800211E7
0x18002145a  test    byte ptr [rcx+1Ch], 4
0x18002145e  jz      loc_1800211E7
0x180021464  mov     edx, 19h
0x180021469  jmp     loc_1800211D7
0x18002146e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021475  lea     rax, WPP_GLOBAL_Control
0x18002147c  cmp     rcx, rax
0x18002147f  jz      short loc_1800214D7
0x180021481  test    byte ptr [rcx+1Ch], 4
0x180021485  jz      short loc_1800214D7
0x180021487  mov     rcx, [rcx+10h]
0x18002148b  lea     r8, WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids
0x180021492  mov     edx, 1Ah
0x180021497  mov     [rsp+3D0h+phkResult], r15
0x18002149c  mov     r9, rsi
0x18002149f  call    WPP_SF_SS
0x1800214a4  jmp     short loc_1800214D7
0x1800214a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214ad  lea     rax, WPP_GLOBAL_Control
0x1800214b4  mov     ebx, r12d
0x1800214b7  cmp     rcx, rax
0x1800214ba  jz      short loc_180021506
0x1800214bc  test    byte ptr [rcx+1Ch], 4
0x1800214c0  jz      short loc_180021506
0x1800214c2  mov     edx, 11h
0x1800214c7  mov     rcx, [rcx+10h]
0x1800214cb  lea     r8, WPP_5351e3ad169c3699daa4b130ec8527d7_Traceguids
0x1800214d2  call    WPP_SF_
0x1800214d7  mov     rcx, [rsp+3D0h+hKey]; hKey
0x1800214dc  test    rcx, rcx
0x1800214df  jz      short loc_1800214F2
0x1800214e1  call    cs:__imp_RegCloseKey
0x1800214e8  nop     dword ptr [rax+rax+00h]
0x1800214ed  mov     [rsp+3D0h+hKey], r12
0x1800214f2  test    r14, r14
0x1800214f5  jz      short loc_180021506
0x1800214f7  mov     rcx, r14; hMem
0x1800214fa  call    cs:__imp_LocalFree
0x180021501  nop     dword ptr [rax+rax+00h]
0x180021506  mov     eax, ebx
0x180021508  mov     rcx, [rbp+2D0h+var_30]
0x18002150f  xor     rcx, rsp; StackCookie
0x180021512  call    __security_check_cookie
0x180021517  lea     r11, [rsp+3D0h+var_20]
0x18002151f  mov     rbx, [r11+40h]
0x180021523  mov     rsi, [r11+48h]
0x180021527  mov     rsp, r11
0x18002152a  pop     r15
0x18002152c  pop     r14
0x18002152e  pop     r12
0x180021530  pop     rdi
0x180021531  pop     rbp
0x180021532  retn
```
