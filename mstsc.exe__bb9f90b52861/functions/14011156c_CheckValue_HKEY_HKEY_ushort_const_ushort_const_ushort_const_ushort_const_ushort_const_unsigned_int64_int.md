# CheckValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64,int *)

- ea: `0x14011156c`
- end: `0x1401118c7`
- name: `?CheckValue@@YAJPEAUHKEY__@@0PEBG1111_KPEAH@Z`
- size: `859`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, LPCWSTR lpValueName, const unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140111448`

## callees

- `0x140042438`
- `0x14011156c`
- `0x1401118d0`
- `0x140111bb8`
- `0x140111c9c`
- `0x140113390`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x1401117c9`
- `msvcrt!wcsncat_s` at `0x1401117c9`
- `msvcrt!wcsncpy_s` at `0x1401117ab`
- `msvcrt!wcsncpy_s` at `0x1401117ab`
- `ADVAPI32!RegOpenKeyExW` at `0x140111681`
- `ADVAPI32!RegOpenKeyExW` at `0x1401117ed`
- `ADVAPI32!RegOpenKeyExW` at `0x140111681`
- `ADVAPI32!RegOpenKeyExW` at `0x1401117ed`
- `ADVAPI32!RegCloseKey` at `0x14011188c`
- `ADVAPI32!RegCloseKey` at `0x14011189c`
- `ADVAPI32!RegCloseKey` at `0x14011188c`
- `ADVAPI32!RegCloseKey` at `0x14011189c`
- `ADVAPI32!RegQueryValueExW` at `0x140111621`
- `ADVAPI32!RegQueryValueExW` at `0x14011170e`
- `ADVAPI32!RegQueryValueExW` at `0x140111621`
- `ADVAPI32!RegQueryValueExW` at `0x14011170e`

## pseudocode

```c
__int64 __fastcall CheckValue(
        HKEY hKey,
        HKEY a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        LPCWSTR lpValueName,
        wchar_t *String2,
        unsigned __int64 a8,
        int *a9)
{
  wchar_t *v10; // rbx
  LSTATUS v12; // eax
  signed int v13; // edi
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  HKEY v16; // r13
  rsize_t v17; // rsi
  LSTATUS v18; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v25; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-A8h]
  HKEY hKeya; // [rsp+60h] [rbp-A0h]
  wchar_t Destination[256]; // [rsp+70h] [rbp-90h] BYREF

  v10 = a3;
  v27 = a5;
  hKeya = a2;
  v26 = 0;
  phkResult = 0;
  v25 = 0;
  v23 = 0;
  *a9 = 0;
  if ( !hKey || !a3 )
    goto LABEL_23;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 4;
  v12 = RegQueryValueExW(hKey, a3, 0, &Type, Data, &cbData);
  v13 = v12;
  if ( v12 != 2 )
  {
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v13 < 0 )
      goto LABEL_46;
    if ( Type != 4 )
    {
LABEL_8:
      v13 = -2147024883;
      goto LABEL_46;
    }
    if ( !*(_DWORD *)Data )
      goto LABEL_45;
  }
  v14 = RegOpenKeyExW(hKey, v10, 0, 0x20019u, &phkResult);
  v13 = v14;
  if ( v14 == 2 )
    goto LABEL_23;
  if ( v14 > 0 )
    v13 = (unsigned __int16)v14 | 0x80070000;
  if ( v13 >= 0 )
  {
    v13 = QueryForMatch(phkResult, String2, a8, a9);
    if ( v13 >= 0 && !*a9 && lpValueName )
    {
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      v15 = RegQueryValueExW(hKey, lpValueName, 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData);
      v13 = v15;
      if ( v15 == 2 )
        goto LABEL_23;
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      if ( v13 >= 0 )
      {
        if ( *(_DWORD *)Data != 4 )
          goto LABEL_8;
        if ( Type )
        {
LABEL_23:
          v13 = IsDomainJoinedNetapi32(&v23);
          if ( v13 < 0 )
            goto LABEL_46;
          v16 = hKeya;
          if ( v23 )
            a4 = v27;
          if ( hKeya && v10 )
          {
            if ( v23 )
            {
              v17 = -1;
              do
                ++v17;
              while ( v10[v17] );
              wcsncpy_s(Destination, 0x100u, v10, v17);
              wcsncat_s(Destination, 256 - v17, L"Domain", 6u);
              v10 = Destination;
            }
            v18 = RegOpenKeyExW(v16, v10, 0, 0x20019u, &v25);
            if ( v18 )
            {
              if ( v18 != 2 )
              {
                if ( v18 > 0 )
                  v13 = (unsigned __int16)v18 | 0x80070000;
                else
                  v13 = v18;
                goto LABEL_46;
              }
            }
            else
            {
              v13 = QueryForMatch(v25, String2, a8, a9);
              if ( v13 < 0 || *a9 )
                goto LABEL_46;
            }
          }
          if ( !a4 )
          {
LABEL_45:
            v13 = 0;
            goto LABEL_46;
          }
          if ( !String2 )
          {
            *a9 = 1;
            goto LABEL_46;
          }
          v13 = StringCchLengthW(a4, 0x400u, &v26);
          if ( v13 >= 0 )
          {
            *a9 = CompareValue(String2, a8, a4, v26);
            goto LABEL_45;
          }
        }
      }
    }
  }
LABEL_46:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v25 )
    RegCloseKey(v25);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14011156c  push    rbp
0x14011156e  push    rbx
0x14011156f  push    rsi
0x140111570  push    rdi
0x140111571  push    r12
0x140111573  push    r13
0x140111575  push    r14
0x140111577  push    r15
0x140111579  lea     rbp, [rsp-188h]
0x140111581  sub     rsp, 288h
0x140111588  mov     rax, cs:__security_cookie
0x14011158f  xor     rax, rsp
0x140111592  mov     [rbp+1C0h+var_50], rax
0x140111599  mov     rax, [rbp+1C0h+arg_20]
0x1401115a0  mov     r15, r9
0x1401115a3  mov     r14, [rbp+1C0h+arg_40]
0x1401115aa  mov     rbx, r8
0x1401115ad  mov     r13, [rbp+1C0h+lpValueName]
0x1401115b4  mov     rsi, rcx
0x1401115b7  mov     r12, [rbp+1C0h+String2]
0x1401115be  mov     [rsp+2C0h+var_268], rax
0x1401115c3  xor     eax, eax
0x1401115c5  mov     [rsp+2C0h+hKey], rdx
0x1401115ca  mov     [rsp+2C0h+var_270], rax
0x1401115cf  mov     [rsp+2C0h+phkResult], rax
0x1401115d4  mov     [rsp+2C0h+var_278], rax
0x1401115d9  mov     [rsp+2C0h+var_284], eax
0x1401115dd  mov     [r14], eax
0x1401115e0  test    rcx, rcx
0x1401115e3  jz      loc_14011174F
0x1401115e9  test    rbx, rbx
0x1401115ec  jz      loc_14011174F
0x1401115f2  mov     dword ptr [rsp+2C0h+Data], eax
0x1401115f6  lea     r9, [rsp+2C0h+Type]; lpType
0x1401115fb  mov     [rsp+2C0h+Type], eax
0x1401115ff  xor     r8d, r8d; lpReserved
0x140111602  lea     rax, [rsp+2C0h+cbData]
0x140111607  mov     [rsp+2C0h+cbData], 4
0x14011160f  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x140111614  mov     rdx, rbx; lpValueName
0x140111617  lea     rax, [rsp+2C0h+Data]
0x14011161c  mov     [rsp+2C0h+lpData], rax; lpData
0x140111621  call    cs:__imp_RegQueryValueExW
0x140111627  mov     edi, eax
0x140111629  cmp     eax, 2
0x14011162c  jz      short loc_140111668
0x14011162e  xor     ecx, ecx
0x140111630  test    eax, eax
0x140111632  jle     short loc_14011163D
0x140111634  movzx   edi, ax
0x140111637  or      edi, 80070000h
0x14011163d  test    edi, edi
0x14011163f  js      loc_140111882
0x140111645  cmp     [rsp+2C0h+Type], 4
0x14011164a  jz      short loc_140111656
0x14011164c  mov     edi, 8007000Dh
0x140111651  jmp     loc_140111882
0x140111656  cmp     dword ptr [rsp+2C0h+Data], ecx
0x14011165a  jz      loc_140111880
0x140111660  test    edi, edi
0x140111662  js      loc_140111882
0x140111668  lea     rax, [rsp+2C0h+phkResult]
0x14011166d  mov     r9d, 20019h; samDesired
0x140111673  xor     r8d, r8d; ulOptions
0x140111676  mov     [rsp+2C0h+lpData], rax; phkResult
0x14011167b  mov     rdx, rbx; lpSubKey
0x14011167e  mov     rcx, rsi; hKey
0x140111681  call    cs:__imp_RegOpenKeyExW
0x140111687  mov     edi, eax
0x140111689  cmp     eax, 2
0x14011168c  jz      loc_14011174F
0x140111692  test    eax, eax
0x140111694  jle     short loc_14011169F
0x140111696  movzx   edi, ax
0x140111699  or      edi, 80070000h
0x14011169f  test    edi, edi
0x1401116a1  js      loc_140111882
0x1401116a7  mov     r8, [rbp+1C0h+arg_38]; unsigned __int64
0x1401116ae  mov     r9, r14; int *
0x1401116b1  mov     rcx, [rsp+2C0h+phkResult]; HKEY
0x1401116b6  mov     rdx, r12; String2
0x1401116b9  call    ?QueryForMatch@@YAJPEAUHKEY__@@PEBG_KPEAH@Z; QueryForMatch(HKEY__ *,ushort const *,unsigned __int64,int *)
0x1401116be  xor     ecx, ecx
0x1401116c0  mov     edi, eax
0x1401116c2  test    eax, eax
0x1401116c4  js      loc_140111882
0x1401116ca  cmp     [r14], ecx
0x1401116cd  jnz     loc_140111882
0x1401116d3  test    r13, r13
0x1401116d6  jz      loc_140111882
0x1401116dc  lea     rax, [rsp+2C0h+cbData]
0x1401116e1  mov     [rsp+2C0h+Type], ecx
0x1401116e5  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x1401116ea  lea     r9, [rsp+2C0h+Data]; lpType
0x1401116ef  lea     rax, [rsp+2C0h+Type]
0x1401116f4  mov     dword ptr [rsp+2C0h+Data], ecx
0x1401116f8  xor     r8d, r8d; lpReserved
0x1401116fb  mov     [rsp+2C0h+lpData], rax; lpData
0x140111700  mov     rdx, r13; lpValueName
0x140111703  mov     [rsp+2C0h+cbData], 4
0x14011170b  mov     rcx, rsi; hKey
0x14011170e  call    cs:__imp_RegQueryValueExW
0x140111714  mov     edi, eax
0x140111716  cmp     eax, 2
0x140111719  jz      short loc_14011174F
0x14011171b  xor     ecx, ecx
0x14011171d  test    eax, eax
0x14011171f  jle     short loc_14011172A
0x140111721  movzx   edi, ax
0x140111724  or      edi, 80070000h
0x14011172a  test    edi, edi
0x14011172c  js      loc_140111882
0x140111732  cmp     dword ptr [rsp+2C0h+Data], 4
0x140111737  jnz     loc_14011164C
0x14011173d  cmp     [rsp+2C0h+Type], ecx
0x140111741  jz      loc_140111882
0x140111747  test    edi, edi
0x140111749  js      loc_140111882
0x14011174f  lea     rcx, [rsp+2C0h+var_284]; int *
0x140111754  call    ?IsDomainJoinedNetapi32@@YAJPEAH@Z; IsDomainJoinedNetapi32(int *)
0x140111759  xor     ecx, ecx
0x14011175b  mov     edi, eax
0x14011175d  test    eax, eax
0x14011175f  js      loc_140111882
0x140111765  mov     eax, [rsp+2C0h+var_284]
0x140111769  test    eax, eax
0x14011176b  mov     r13, [rsp+2C0h+hKey]
0x140111770  cmovnz  r15, [rsp+2C0h+var_268]
0x140111776  test    r13, r13
0x140111779  jz      loc_140111839
0x14011177f  test    rbx, rbx
0x140111782  jz      loc_140111839
0x140111788  test    eax, eax
0x14011178a  jz      short loc_1401117D4
0x14011178c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140111790  inc     rsi
0x140111793  cmp     [rbx+rsi*2], cx
0x140111797  jnz     short loc_140111790
0x140111799  mov     r8, rbx; Source
0x14011179c  lea     rcx, [rsp+2C0h+Destination]; Destination
0x1401117a1  mov     ebx, 100h
0x1401117a6  mov     r9, rsi; MaxCount
0x1401117a9  mov     edx, ebx; SizeInWords
0x1401117ab  call    cs:__imp_wcsncpy_s
0x1401117b1  sub     rbx, rsi
0x1401117b4  lea     r8, aDomain; "Domain"
0x1401117bb  mov     rdx, rbx; SizeInWords
0x1401117be  lea     rcx, [rsp+2C0h+Destination]; Destination
0x1401117c3  mov     r9d, 6; MaxCount
0x1401117c9  call    cs:__imp_wcsncat_s
0x1401117cf  lea     rbx, [rsp+2C0h+Destination]
0x1401117d4  lea     rax, [rsp+2C0h+var_278]
0x1401117d9  mov     r9d, 20019h; samDesired
0x1401117df  xor     r8d, r8d; ulOptions
0x1401117e2  mov     [rsp+2C0h+lpData], rax; phkResult
0x1401117e7  mov     rdx, rbx; lpSubKey
0x1401117ea  mov     rcx, r13; hKey
0x1401117ed  call    cs:__imp_RegOpenKeyExW
0x1401117f3  xor     ecx, ecx
0x1401117f5  test    eax, eax
0x1401117f7  jnz     short loc_14011181F
0x1401117f9  mov     r8, [rbp+1C0h+arg_38]; unsigned __int64
0x140111800  mov     r9, r14; int *
0x140111803  mov     rcx, [rsp+2C0h+var_278]; HKEY
0x140111808  mov     rdx, r12; String2
0x14011180b  call    ?QueryForMatch@@YAJPEAUHKEY__@@PEBG_KPEAH@Z; QueryForMatch(HKEY__ *,ushort const *,unsigned __int64,int *)
0x140111810  xor     ecx, ecx
0x140111812  mov     edi, eax
0x140111814  test    eax, eax
0x140111816  js      short loc_140111882
0x140111818  cmp     [r14], ecx
0x14011181b  jnz     short loc_140111882
0x14011181d  jmp     short loc_140111839
0x14011181f  cmp     eax, 2
0x140111822  jz      short loc_140111839
0x140111824  test    eax, eax
0x140111826  jg      short loc_14011182C
0x140111828  mov     edi, eax
0x14011182a  jmp     short loc_140111835
0x14011182c  movzx   edi, ax
0x14011182f  or      edi, 80070000h
0x140111835  test    edi, edi
0x140111837  js      short loc_140111882
0x140111839  test    r15, r15
0x14011183c  jz      short loc_140111880
0x14011183e  test    r12, r12
0x140111841  jnz     short loc_14011184C
0x140111843  mov     dword ptr [r14], 1
0x14011184a  jmp     short loc_140111882
0x14011184c  lea     r8, [rsp+2C0h+var_270]; unsigned __int64 *
0x140111851  mov     edx, 400h; unsigned __int64
0x140111856  mov     rcx, r15; unsigned __int16 *
0x140111859  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14011185e  mov     edi, eax
0x140111860  test    eax, eax
0x140111862  js      short loc_140111882
0x140111864  mov     r9, [rsp+2C0h+var_270]; unsigned __int64
0x140111869  mov     r8, r15; unsigned __int16 *
0x14011186c  mov     rdx, [rbp+1C0h+arg_38]; unsigned __int64
0x140111873  mov     rcx, r12; String2
0x140111876  call    ?CompareValue@@YAHPEBG_K01@Z; CompareValue(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x14011187b  mov     [r14], eax
0x14011187e  xor     ecx, ecx
0x140111880  mov     edi, ecx
0x140111882  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x140111887  test    rcx, rcx
0x14011188a  jz      short loc_140111892
0x14011188c  call    cs:__imp_RegCloseKey
0x140111892  mov     rcx, [rsp+2C0h+var_278]; hKey
0x140111897  test    rcx, rcx
0x14011189a  jz      short loc_1401118A2
0x14011189c  call    cs:__imp_RegCloseKey
0x1401118a2  mov     eax, edi
0x1401118a4  mov     rcx, [rbp+1C0h+var_50]
0x1401118ab  xor     rcx, rsp; StackCookie
0x1401118ae  call    __security_check_cookie
0x1401118b3  add     rsp, 288h
0x1401118ba  pop     r15
0x1401118bc  pop     r14
0x1401118be  pop     r13
0x1401118c0  pop     r12
0x1401118c2  pop     rdi
0x1401118c3  pop     rsi
0x1401118c4  pop     rbx
0x1401118c5  pop     rbp
0x1401118c6  retn
```
