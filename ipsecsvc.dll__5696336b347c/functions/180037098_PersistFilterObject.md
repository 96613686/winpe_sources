# PersistFilterObject

- ea: `0x180037098`
- end: `0x1800374f7`
- name: `PersistFilterObject`
- size: `1119`
- prototype: `__int64 __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180038908`

## callees

- `0x18000e510`
- `0x180037098`
- `0x180038c44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800374db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800374db`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180037230`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180037230`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003717d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800371ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003726c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800372da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037345`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003739f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800373fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037452`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003717d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800371ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003726c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800372da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037345`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003739f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800373fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037452`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800370e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800370e4`

## pseudocode

```c
__int64 __fastcall PersistFilterObject(HKEY a1, __int64 a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  const BYTE *lpData; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  const BYTE *v12; // rcx
  __int64 v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  const BYTE *v16; // rcx
  const BYTE *v17; // rcx
  DWORD v19; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v3 = *(const WCHAR **)a2;
  hKey = 0;
  v19 = 0;
  v4 = RegCreateKeyExW(a1, v3, 0, 0, 0, 0xF003Fu, 0, &hKey, &v19);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 48;
LABEL_59:
      v8 = v4;
LABEL_60:
      WPP_SF_d(v6[2], v7, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v8);
    }
  }
  else
  {
    if ( !hKey )
    {
      v5 = 1359;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v5;
      v7 = 49;
      v8 = 1359;
      goto LABEL_60;
    }
    v4 = RegSetValueExW(hKey, L"className", 0, 1u, L"ipsecFilter", 0x18u);
    v5 = v4;
    if ( !v4 )
    {
      lpData = *(const BYTE **)(a2 + 64);
      v10 = -1;
      if ( lpData )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&lpData[2 * v11] );
        v4 = RegSetValueExW(hKey, L"description", 0, 1u, lpData, 2 * v11 + 2);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v7 = 51;
            goto LABEL_59;
          }
          goto LABEL_61;
        }
      }
      else
      {
        RegDeleteValueW(hKey, L"description");
      }
      v12 = *(const BYTE **)a2;
      if ( !*(_QWORD *)a2 )
        goto LABEL_28;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v12[2 * v13] );
      v4 = RegSetValueExW(hKey, L"name", 0, 1u, v12, 2 * v13 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 52;
          goto LABEL_59;
        }
      }
      else
      {
LABEL_28:
        v14 = *(const BYTE **)(a2 + 8);
        if ( !v14 )
          goto LABEL_35;
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v14[2 * v15] );
        v4 = RegSetValueExW(hKey, L"ipsecName", 0, 1u, v14, 2 * v15 + 2);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v7 = 53;
            goto LABEL_59;
          }
        }
        else
        {
LABEL_35:
          v16 = *(const BYTE **)(a2 + 16);
          if ( !v16 )
            goto LABEL_41;
          do
            ++v10;
          while ( *(_WORD *)&v16[2 * v10] );
          v4 = RegSetValueExW(hKey, L"ipsecID", 0, 1u, v16, 2 * v10 + 2);
          v5 = v4;
          if ( v4 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v7 = 54;
              goto LABEL_59;
            }
          }
          else
          {
LABEL_41:
            v4 = RegSetValueExW(hKey, L"ipsecDataType", 0, 4u, (const BYTE *)(a2 + 24), 4u);
            v5 = v4;
            if ( v4 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v7 = 55;
                goto LABEL_59;
              }
            }
            else
            {
              v17 = *(const BYTE **)(a2 + 32);
              if ( v17 && (v4 = RegSetValueExW(hKey, L"ipsecData", 0, 3u, v17, *(_DWORD *)(a2 + 40)), (v5 = v4) != 0) )
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  v7 = 56;
                  goto LABEL_59;
                }
              }
              else
              {
                v4 = RegSetValueExW(hKey, L"whenChanged", 0, 4u, (const BYTE *)(a2 + 60), 4u);
                v5 = v4;
                if ( v4 )
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v7 = 57;
                    goto LABEL_59;
                  }
                }
                else if ( *(_QWORD *)(a2 + 48) )
                {
                  v4 = RegWriteMultiValuedString(hKey, L"ipsecOwnersReference");
                  v5 = v4;
                  if ( v4 )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v7 = 58;
                      goto LABEL_59;
                    }
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_61;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 50;
      goto LABEL_59;
    }
  }
LABEL_61:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180037098  mov     r11, rsp
0x18003709b  mov     [r11+8], rbx
0x18003709f  push    rbp
0x1800370a0  push    rsi
0x1800370a1  push    rdi
0x1800370a2  push    r14
0x1800370a4  push    r15
0x1800370a6  mov     rbp, rsp
0x1800370a9  sub     rsp, 50h
0x1800370ad  xor     r14d, r14d
0x1800370b0  lea     rax, [rbp+arg_8]
0x1800370b4  mov     [r11-38h], rax
0x1800370b8  mov     rdi, rdx
0x1800370bb  mov     rdx, [rdx]; lpSubKey
0x1800370be  lea     rax, [rbp+hKey]
0x1800370c2  mov     [r11-40h], rax
0x1800370c6  xor     r9d, r9d; lpClass
0x1800370c9  mov     [r11-48h], r14
0x1800370cd  xor     r8d, r8d; Reserved
0x1800370d0  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x1800370d8  mov     [r11-58h], r14d
0x1800370dc  mov     [rbp+hKey], r14
0x1800370e0  mov     [rbp+arg_8], r14d
0x1800370e4  call    cs:__imp_RegCreateKeyExW
0x1800370ea  mov     ebx, eax
0x1800370ec  test    eax, eax
0x1800370ee  jz      short loc_18003711A
0x1800370f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370f7  lea     rdx, WPP_GLOBAL_Control
0x1800370fe  cmp     rcx, rdx
0x180037101  jz      loc_1800374D2
0x180037107  test    byte ptr [rcx+1Ch], 10h
0x18003710b  jz      loc_1800374D2
0x180037111  lea     edx, [r14+30h]
0x180037115  jmp     loc_1800374BF
0x18003711a  mov     rcx, [rbp+hKey]; hKey
0x18003711e  test    rcx, rcx
0x180037121  jnz     short loc_180037156
0x180037123  mov     ebx, 54Fh
0x180037128  mov     rcx, cs:WPP_GLOBAL_Control
0x18003712f  lea     rdx, WPP_GLOBAL_Control
0x180037136  cmp     rcx, rdx
0x180037139  jz      loc_1800374E1
0x18003713f  test    byte ptr [rcx+1Ch], 10h
0x180037143  jz      loc_1800374E1
0x180037149  mov     edx, 31h ; '1'
0x18003714e  mov     r9d, ebx
0x180037151  jmp     loc_1800374C2
0x180037156  lea     rax, Data; "ipsecFilter"
0x18003715d  mov     [rsp+50h+samDesired], 18h; cbData
0x180037165  mov     r15d, 1
0x18003716b  mov     [rsp+50h+lpData], rax; lpData
0x180037170  mov     r9d, r15d; dwType
0x180037173  lea     rdx, aClassname; "className"
0x18003717a  xor     r8d, r8d; Reserved
0x18003717d  call    cs:__imp_RegSetValueExW
0x180037183  mov     ebx, eax
0x180037185  test    eax, eax
0x180037187  jz      short loc_1800371B3
0x180037189  mov     rcx, cs:WPP_GLOBAL_Control
0x180037190  lea     rdx, WPP_GLOBAL_Control
0x180037197  cmp     rcx, rdx
0x18003719a  jz      loc_1800374D2
0x1800371a0  test    byte ptr [rcx+1Ch], 10h
0x1800371a4  jz      loc_1800374D2
0x1800371aa  lea     edx, [r15+31h]
0x1800371ae  jmp     loc_1800374BF
0x1800371b3  mov     rcx, [rdi+40h]
0x1800371b7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800371bb  test    rcx, rcx
0x1800371be  jz      short loc_180037225
0x1800371c0  mov     rax, rsi
0x1800371c3  inc     rax
0x1800371c6  cmp     [rcx+rax*2], r14w
0x1800371cb  jnz     short loc_1800371C3
0x1800371cd  lea     eax, ds:2[rax*2]
0x1800371d4  mov     r9d, r15d; dwType
0x1800371d7  mov     [rsp+50h+samDesired], eax; cbData
0x1800371db  lea     rdx, aDescription_0; "description"
0x1800371e2  mov     [rsp+50h+lpData], rcx; lpData
0x1800371e7  xor     r8d, r8d; Reserved
0x1800371ea  mov     rcx, [rbp+hKey]; hKey
0x1800371ee  call    cs:__imp_RegSetValueExW
0x1800371f4  mov     ebx, eax
0x1800371f6  test    eax, eax
0x1800371f8  jz      short loc_180037236
0x1800371fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180037201  lea     rdx, WPP_GLOBAL_Control
0x180037208  cmp     rcx, rdx
0x18003720b  jz      loc_1800374D2
0x180037211  test    byte ptr [rcx+1Ch], 10h
0x180037215  jz      loc_1800374D2
0x18003721b  mov     edx, 33h ; '3'
0x180037220  jmp     loc_1800374BF
0x180037225  mov     rcx, [rbp+hKey]; hKey
0x180037229  lea     rdx, aDescription_0; "description"
0x180037230  call    cs:__imp_RegDeleteValueW
0x180037236  mov     rcx, [rdi]
0x180037239  test    rcx, rcx
0x18003723c  jz      short loc_1800372A3
0x18003723e  mov     rax, rsi
0x180037241  inc     rax
0x180037244  cmp     [rcx+rax*2], r14w
0x180037249  jnz     short loc_180037241
0x18003724b  lea     eax, ds:2[rax*2]
0x180037252  mov     r9d, r15d; dwType
0x180037255  mov     [rsp+50h+samDesired], eax; cbData
0x180037259  lea     rdx, aName; "name"
0x180037260  mov     [rsp+50h+lpData], rcx; lpData
0x180037265  xor     r8d, r8d; Reserved
0x180037268  mov     rcx, [rbp+hKey]; hKey
0x18003726c  call    cs:__imp_RegSetValueExW
0x180037272  mov     ebx, eax
0x180037274  test    eax, eax
0x180037276  jz      short loc_1800372A3
0x180037278  mov     rcx, cs:WPP_GLOBAL_Control
0x18003727f  lea     rdx, WPP_GLOBAL_Control
0x180037286  cmp     rcx, rdx
0x180037289  jz      loc_1800374D2
0x18003728f  test    byte ptr [rcx+1Ch], 10h
0x180037293  jz      loc_1800374D2
0x180037299  mov     edx, 34h ; '4'
0x18003729e  jmp     loc_1800374BF
0x1800372a3  mov     rcx, [rdi+8]
0x1800372a7  test    rcx, rcx
0x1800372aa  jz      short loc_180037311
0x1800372ac  mov     rax, rsi
0x1800372af  inc     rax
0x1800372b2  cmp     [rcx+rax*2], r14w
0x1800372b7  jnz     short loc_1800372AF
0x1800372b9  lea     eax, ds:2[rax*2]
0x1800372c0  mov     r9d, r15d; dwType
0x1800372c3  mov     [rsp+50h+samDesired], eax; cbData
0x1800372c7  lea     rdx, aIpsecname_0; "ipsecName"
0x1800372ce  mov     [rsp+50h+lpData], rcx; lpData
0x1800372d3  xor     r8d, r8d; Reserved
0x1800372d6  mov     rcx, [rbp+hKey]; hKey
0x1800372da  call    cs:__imp_RegSetValueExW
0x1800372e0  mov     ebx, eax
0x1800372e2  test    eax, eax
0x1800372e4  jz      short loc_180037311
0x1800372e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372ed  lea     rdx, WPP_GLOBAL_Control
0x1800372f4  cmp     rcx, rdx
0x1800372f7  jz      loc_1800374D2
0x1800372fd  test    byte ptr [rcx+1Ch], 10h
0x180037301  jz      loc_1800374D2
0x180037307  mov     edx, 35h ; '5'
0x18003730c  jmp     loc_1800374BF
0x180037311  mov     rcx, [rdi+10h]
0x180037315  test    rcx, rcx
0x180037318  jz      short loc_18003737C
0x18003731a  inc     rsi
0x18003731d  cmp     [rcx+rsi*2], r14w
0x180037322  jnz     short loc_18003731A
0x180037324  lea     eax, ds:2[rsi*2]
0x18003732b  mov     r9d, r15d; dwType
0x18003732e  mov     [rsp+50h+samDesired], eax; cbData
0x180037332  lea     rdx, aIpsecid_0; "ipsecID"
0x180037339  mov     [rsp+50h+lpData], rcx; lpData
0x18003733e  xor     r8d, r8d; Reserved
0x180037341  mov     rcx, [rbp+hKey]; hKey
0x180037345  call    cs:__imp_RegSetValueExW
0x18003734b  mov     ebx, eax
0x18003734d  test    eax, eax
0x18003734f  jz      short loc_18003737C
0x180037351  mov     rcx, cs:WPP_GLOBAL_Control
0x180037358  lea     rdx, WPP_GLOBAL_Control
0x18003735f  cmp     rcx, rdx
0x180037362  jz      loc_1800374D2
0x180037368  test    byte ptr [rcx+1Ch], 10h
0x18003736c  jz      loc_1800374D2
0x180037372  mov     edx, 36h ; '6'
0x180037377  jmp     loc_1800374BF
0x18003737c  mov     rcx, [rbp+hKey]; hKey
0x180037380  lea     rax, [rdi+18h]
0x180037384  mov     esi, 4
0x180037389  lea     rdx, aIpsecdatatype_0; "ipsecDataType"
0x180037390  mov     [rsp+50h+samDesired], esi; cbData
0x180037394  mov     r9d, esi; dwType
0x180037397  xor     r8d, r8d; Reserved
0x18003739a  mov     [rsp+50h+lpData], rax; lpData
0x18003739f  call    cs:__imp_RegSetValueExW
0x1800373a5  mov     ebx, eax
0x1800373a7  test    eax, eax
0x1800373a9  jz      short loc_1800373D4
0x1800373ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373b2  lea     rdx, WPP_GLOBAL_Control
0x1800373b9  cmp     rcx, rdx
0x1800373bc  jz      loc_1800374D2
0x1800373c2  test    byte ptr [rcx+1Ch], 10h
0x1800373c6  jz      loc_1800374D2
0x1800373cc  lea     edx, [rsi+33h]
0x1800373cf  jmp     loc_1800374BF
0x1800373d4  mov     rcx, [rdi+20h]
0x1800373d8  test    rcx, rcx
0x1800373db  jz      short loc_180037434
0x1800373dd  mov     eax, [rdi+28h]
0x1800373e0  lea     rdx, aIpsecdata_0; "ipsecData"
0x1800373e7  mov     [rsp+50h+samDesired], eax; cbData
0x1800373eb  mov     r9d, 3; dwType
0x1800373f1  mov     [rsp+50h+lpData], rcx; lpData
0x1800373f6  xor     r8d, r8d; Reserved
0x1800373f9  mov     rcx, [rbp+hKey]; hKey
0x1800373fd  call    cs:__imp_RegSetValueExW
0x180037403  mov     ebx, eax
0x180037405  test    eax, eax
0x180037407  jz      short loc_180037434
0x180037409  mov     rcx, cs:WPP_GLOBAL_Control
0x180037410  lea     rdx, WPP_GLOBAL_Control
0x180037417  cmp     rcx, rdx
0x18003741a  jz      loc_1800374D2
0x180037420  test    byte ptr [rcx+1Ch], 10h
0x180037424  jz      loc_1800374D2
0x18003742a  mov     edx, 38h ; '8'
0x18003742f  jmp     loc_1800374BF
0x180037434  mov     rcx, [rbp+hKey]; hKey
0x180037438  lea     rax, [rdi+3Ch]
0x18003743c  mov     [rsp+50h+samDesired], esi; cbData
0x180037440  lea     rdx, aWhenchanged_1; "whenChanged"
0x180037447  mov     r9d, esi; dwType
0x18003744a  mov     [rsp+50h+lpData], rax; lpData
0x18003744f  xor     r8d, r8d; Reserved
0x180037452  call    cs:__imp_RegSetValueExW
0x180037458  mov     ebx, eax
0x18003745a  test    eax, eax
0x18003745c  jz      short loc_18003747E
0x18003745e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037465  lea     rdx, WPP_GLOBAL_Control
0x18003746c  cmp     rcx, rdx
0x18003746f  jz      short loc_1800374D2
0x180037471  test    byte ptr [rcx+1Ch], 10h
0x180037475  jz      short loc_1800374D2
0x180037477  mov     edx, 39h ; '9'
0x18003747c  jmp     short loc_1800374BF
0x18003747e  mov     r8, [rdi+30h]
0x180037482  test    r8, r8
0x180037485  jz      short loc_1800374D2
0x180037487  mov     r9d, [rdi+38h]
0x18003748b  lea     rdx, aIpsecownersref_0; "ipsecOwnersReference"
0x180037492  mov     rcx, [rbp+hKey]; hKey
0x180037496  call    RegWriteMultiValuedString
0x18003749b  mov     ebx, eax
0x18003749d  test    eax, eax
0x18003749f  jz      short loc_1800374D2
0x1800374a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800374a8  lea     rdx, WPP_GLOBAL_Control
0x1800374af  cmp     rcx, rdx
0x1800374b2  jz      short loc_1800374D2
0x1800374b4  test    byte ptr [rcx+1Ch], 10h
0x1800374b8  jz      short loc_1800374D2
0x1800374ba  mov     edx, 3Ah ; ':'
0x1800374bf  mov     r9d, eax
0x1800374c2  mov     rcx, [rcx+10h]
0x1800374c6  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x1800374cd  call    WPP_SF_d
0x1800374d2  mov     rcx, [rbp+hKey]; hKey
0x1800374d6  test    rcx, rcx
0x1800374d9  jz      short loc_1800374E1
0x1800374db  call    cs:__imp_RegCloseKey
0x1800374e1  mov     eax, ebx
0x1800374e3  mov     rbx, [rsp+50h+arg_0]
0x1800374eb  add     rsp, 50h
0x1800374ef  pop     r15
0x1800374f1  pop     r14
0x1800374f3  pop     rdi
0x1800374f4  pop     rsi
0x1800374f5  pop     rbp
0x1800374f6  retn
```
