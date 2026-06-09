# InferSidFromPath

- ea: `0x180085590`
- end: `0x18008593c`
- name: `InferSidFromPath`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008e0f4`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18005fc8c`
- `0x180085590`
- `0x18008c988`
- `0x18008ca30`
- `0x18008df60`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008564b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18008564b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800857bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008587c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800857bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008587c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800857aa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008586b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800857aa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008586b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800857d9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800857d9`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008578a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008578a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800855ec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x1800855ec`

## string_xrefs

- `0x180085757`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall InferSidFromPath(const WCHAR *a1, _QWORD *a2)
{
  const CHAR *v3; // rax
  CHAR *v4; // rdi
  PSTR v5; // rax
  _BYTE *i; // rax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int v10; // esi
  __int64 v11; // rbx
  unsigned int StringValue; // r14d
  _BYTE *v13; // rax
  _BYTE *v14; // rcx
  __int64 v15; // rax
  CHAR *v16; // rdx
  _BYTE *v17; // rax
  DWORD cSubKeys; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  CHAR String1[256]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR SubKey[1552]; // [rsp+140h] [rbp+40h] BYREF

  if ( !a1 || !a2 )
    return 87;
  v3 = (const CHAR *)StrDupAFromTInternal(a1);
  v4 = (CHAR *)v3;
  if ( !v3 )
    return 8;
  v5 = StrStrA(v3, "\\Users\\");
  if ( !v5 )
    return 635;
  for ( i = v5 + 7; *i != 92 && *i; ++i )
    ;
  if ( !*i )
    return 635;
  *i = 0;
  hKey = 0;
  v7 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20219u,
         &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 20, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v7);
    }
    return v8;
  }
  cSubKeys = 0;
  memset_0(SubKey, 0, 0x601u);
  if ( (unsigned int)RegGetNumberOfSubkeys(hKey, &cSubKeys) )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 21, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 1);
    }
    return 1;
  }
  v10 = 0;
  if ( !cSubKeys )
  {
LABEL_28:
    GlobalFree(v4);
    RegCloseKey(hKey);
    return 635;
  }
  v11 = 256;
  while ( 1 )
  {
    if ( !(unsigned int)RegGetIthSectionName(hKey, v10, SubKey) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 22, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids);
      }
      return 635;
    }
    memset_0(String1, 0, sizeof(String1));
    StringValue = RegReadStringValue(hKey, "ProfileImagePath", String1, SubKey, 0x100u);
    if ( StringValue )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 23, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, StringValue);
      }
      return StringValue;
    }
    if ( CompareStringA(0x7Fu, 1u, String1, -1, v4, -1) == 2 )
      break;
    if ( ++v10 >= cSubKeys )
      goto LABEL_28;
  }
  v13 = GlobalAlloc(0x40u, 0x100u);
  *a2 = v13;
  v14 = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 24, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 8);
    }
    return 8;
  }
  v15 = 2147483646;
  v16 = SubKey;
  do
  {
    if ( !v15 )
      break;
    if ( !*v16 )
      break;
    *v14++ = *v16++;
    --v15;
    --v11;
  }
  while ( v11 );
  v17 = v14 - 1;
  if ( v11 )
    v17 = v14;
  *v17 = 0;
  GlobalFree(v4);
  RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180085590  mov     [rsp-8+arg_10], rbx
0x180085595  push    rbp
0x180085596  push    rsi
0x180085597  push    rdi
0x180085598  push    r14
0x18008559a  push    r15
0x18008559c  lea     rbp, [rsp-660h]
0x1800855a4  sub     rsp, 760h
0x1800855ab  mov     rax, cs:__security_cookie
0x1800855b2  xor     rax, rsp
0x1800855b5  mov     [rbp+680h+var_30], rax
0x1800855bc  mov     r15, rdx
0x1800855bf  test    rcx, rcx
0x1800855c2  jz      loc_180085910
0x1800855c8  test    rdx, rdx
0x1800855cb  jz      loc_180085910
0x1800855d1  call    StrDupAFromTInternal
0x1800855d6  mov     rdi, rax
0x1800855d9  test    rax, rax
0x1800855dc  jz      loc_180085828
0x1800855e2  lea     rdx, aUsers; "\\Users\\"
0x1800855e9  mov     rcx, rax; pszFirst
0x1800855ec  call    cs:__imp_StrStrA
0x1800855f3  nop     dword ptr [rax+rax+00h]
0x1800855f8  test    rax, rax
0x1800855fb  jz      loc_1800857C7
0x180085601  add     rax, 7
0x180085605  jmp     short loc_18008560E
0x180085607  test    cl, cl
0x180085609  jz      short loc_180085615
0x18008560b  inc     rax
0x18008560e  mov     cl, [rax]
0x180085610  cmp     cl, 5Ch ; '\'
0x180085613  jnz     short loc_180085607
0x180085615  cmp     byte ptr [rax], 0
0x180085618  jz      loc_1800857C7
0x18008561e  mov     byte ptr [rax], 0
0x180085621  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180085628  lea     rax, [rsp+780h+hKey]
0x18008562d  mov     [rsp+780h+hKey], 0
0x180085636  mov     r9d, 20219h; samDesired
0x18008563c  mov     [rsp+780h+phkResult], rax; phkResult
0x180085641  xor     r8d, r8d; ulOptions
0x180085644  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008564b  call    cs:__imp_RegOpenKeyExA
0x180085652  nop     dword ptr [rax+rax+00h]
0x180085657  mov     ebx, eax
0x180085659  test    eax, eax
0x18008565b  jz      short loc_18008569D
0x18008565d  mov     r10, cs:WPP_GLOBAL_Control
0x180085664  lea     rcx, WPP_GLOBAL_Control
0x18008566b  cmp     r10, rcx
0x18008566e  jz      short loc_180085696
0x180085670  test    byte ptr [r10+1Ch], 80h
0x180085675  jz      short loc_180085696
0x180085677  cmp     byte ptr [r10+19h], 2
0x18008567c  jb      short loc_180085696
0x18008567e  mov     rcx, [r10+10h]
0x180085682  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180085689  mov     edx, 14h
0x18008568e  mov     r9d, eax
0x180085691  call    WPP_SF_d
0x180085696  mov     eax, ebx
0x180085698  jmp     loc_180085915
0x18008569d  xor     edx, edx; Val
0x18008569f  mov     [rsp+780h+cSubKeys], 0
0x1800856a7  mov     r8d, 601h; Size
0x1800856ad  lea     rcx, [rbp+680h+SubKey]; void *
0x1800856b1  call    memset_0
0x1800856b6  mov     rcx, [rsp+780h+hKey]; hKey
0x1800856bb  lea     rdx, [rsp+780h+cSubKeys]; lpcSubKeys
0x1800856c0  call    RegGetNumberOfSubkeys
0x1800856c5  test    eax, eax
0x1800856c7  jz      short loc_18008570D
0x1800856c9  mov     r10, cs:WPP_GLOBAL_Control
0x1800856d0  lea     rcx, WPP_GLOBAL_Control
0x1800856d7  cmp     r10, rcx
0x1800856da  jz      short loc_180085703
0x1800856dc  test    byte ptr [r10+1Ch], 80h
0x1800856e1  jz      short loc_180085703
0x1800856e3  cmp     byte ptr [r10+19h], 2
0x1800856e8  jb      short loc_180085703
0x1800856ea  mov     rcx, [r10+10h]
0x1800856ee  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800856f5  mov     edx, 15h
0x1800856fa  lea     r9d, [rdx-14h]
0x1800856fe  call    WPP_SF_d
0x180085703  mov     eax, 1
0x180085708  jmp     loc_180085915
0x18008570d  xor     esi, esi
0x18008570f  cmp     [rsp+780h+cSubKeys], esi
0x180085713  jbe     loc_1800857A7
0x180085719  mov     ebx, 100h
0x18008571e  mov     rcx, [rsp+780h+hKey]
0x180085723  lea     r8, [rbp+680h+SubKey]
0x180085727  mov     edx, esi
0x180085729  call    RegGetIthSectionName
0x18008572e  test    eax, eax
0x180085730  jz      loc_1800858CB
0x180085736  mov     r8, rbx; Size
0x180085739  lea     rcx, [rsp+780h+String1]; void *
0x18008573e  xor     edx, edx; Val
0x180085740  call    memset_0
0x180085745  mov     rcx, [rsp+780h+hKey]; hkey
0x18008574a  lea     r9, [rbp+680h+SubKey]; lpSubKey
0x18008574e  lea     r8, [rsp+780h+String1]; pvData
0x180085753  mov     dword ptr [rsp+780h+phkResult], ebx; DWORD
0x180085757  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18008575e  call    RegReadStringValue
0x180085763  mov     r14d, eax
0x180085766  test    eax, eax
0x180085768  jnz     loc_18008588F
0x18008576e  or      r14d, 0FFFFFFFFh
0x180085772  lea     r8, [rsp+780h+String1]; lpString1
0x180085777  mov     [rsp+780h+cchCount2], r14d; cchCount2
0x18008577c  lea     edx, [rax+1]; dwCmpFlags
0x18008577f  mov     r9d, r14d; cchCount1
0x180085782  mov     [rsp+780h+phkResult], rdi; lpString2
0x180085787  lea     ecx, [rax+7Fh]; Locale
0x18008578a  call    cs:__imp_CompareStringA
0x180085791  nop     dword ptr [rax+rax+00h]
0x180085796  cmp     eax, 2
0x180085799  jz      short loc_1800857D1
0x18008579b  inc     esi
0x18008579d  cmp     esi, [rsp+780h+cSubKeys]
0x1800857a1  jb      loc_18008571E
0x1800857a7  mov     rcx, rdi; hMem
0x1800857aa  call    cs:__imp_GlobalFree
0x1800857b1  nop     dword ptr [rax+rax+00h]
0x1800857b6  mov     rcx, [rsp+780h+hKey]; hKey
0x1800857bb  call    cs:__imp_RegCloseKey
0x1800857c2  nop     dword ptr [rax+rax+00h]
0x1800857c7  mov     eax, 27Bh
0x1800857cc  jmp     loc_180085915
0x1800857d1  mov     rdx, rbx; dwBytes
0x1800857d4  mov     ecx, 40h ; '@'; uFlags
0x1800857d9  call    cs:__imp_GlobalAlloc
0x1800857e0  nop     dword ptr [rax+rax+00h]
0x1800857e5  mov     [r15], rax
0x1800857e8  mov     rcx, rax
0x1800857eb  test    rax, rax
0x1800857ee  jnz     short loc_180085832
0x1800857f0  mov     rax, cs:WPP_GLOBAL_Control
0x1800857f7  lea     rcx, WPP_GLOBAL_Control
0x1800857fe  cmp     rax, rcx
0x180085801  jz      short loc_180085828
0x180085803  test    byte ptr [rax+1Ch], 80h
0x180085807  jz      short loc_180085828
0x180085809  cmp     byte ptr [rax+19h], 2
0x18008580d  jb      short loc_180085828
0x18008580f  mov     rcx, [rax+10h]
0x180085813  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18008581a  mov     edx, 18h
0x18008581f  lea     r9d, [rdx-10h]
0x180085823  call    WPP_SF_d
0x180085828  mov     eax, 8
0x18008582d  jmp     loc_180085915
0x180085832  mov     eax, 7FFFFFFEh
0x180085837  lea     rdx, [rbp+680h+SubKey]
0x18008583b  test    rax, rax
0x18008583e  jz      short loc_18008585A
0x180085840  mov     r8b, [rdx]
0x180085843  test    r8b, r8b
0x180085846  jz      short loc_18008585A
0x180085848  mov     [rcx], r8b
0x18008584b  inc     rdx
0x18008584e  inc     rcx
0x180085851  dec     rax
0x180085854  sub     rbx, 1
0x180085858  jnz     short loc_18008583B
0x18008585a  lea     rax, [rcx-1]
0x18008585e  test    rbx, rbx
0x180085861  cmovnz  rax, rcx
0x180085865  mov     rcx, rdi; hMem
0x180085868  mov     byte ptr [rax], 0
0x18008586b  call    cs:__imp_GlobalFree
0x180085872  nop     dword ptr [rax+rax+00h]
0x180085877  mov     rcx, [rsp+780h+hKey]; hKey
0x18008587c  call    cs:__imp_RegCloseKey
0x180085883  nop     dword ptr [rax+rax+00h]
0x180085888  xor     eax, eax
0x18008588a  jmp     loc_180085915
0x18008588f  mov     rax, cs:WPP_GLOBAL_Control
0x180085896  lea     rcx, WPP_GLOBAL_Control
0x18008589d  cmp     rax, rcx
0x1800858a0  jz      short loc_1800858C6
0x1800858a2  test    byte ptr [rax+1Ch], 80h
0x1800858a6  jz      short loc_1800858C6
0x1800858a8  cmp     byte ptr [rax+19h], 2
0x1800858ac  jb      short loc_1800858C6
0x1800858ae  mov     rcx, [rax+10h]
0x1800858b2  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800858b9  mov     edx, 17h
0x1800858be  mov     r9d, r14d
0x1800858c1  call    WPP_SF_d
0x1800858c6  mov     eax, r14d
0x1800858c9  jmp     short loc_180085915
0x1800858cb  mov     rax, cs:WPP_GLOBAL_Control
0x1800858d2  lea     rcx, WPP_GLOBAL_Control
0x1800858d9  cmp     rax, rcx
0x1800858dc  jz      loc_1800857C7
0x1800858e2  test    byte ptr [rax+1Ch], 80h
0x1800858e6  jz      loc_1800857C7
0x1800858ec  cmp     byte ptr [rax+19h], 6
0x1800858f0  jb      loc_1800857C7
0x1800858f6  mov     rcx, [rax+10h]
0x1800858fa  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180085901  mov     edx, 16h
0x180085906  call    WPP_SF_
0x18008590b  jmp     loc_1800857C7
0x180085910  mov     eax, 57h ; 'W'
0x180085915  mov     rcx, [rbp+680h+var_30]
0x18008591c  xor     rcx, rsp; StackCookie
0x18008591f  call    __security_check_cookie
0x180085924  mov     rbx, [rsp+780h+arg_10]
0x18008592c  add     rsp, 760h
0x180085933  pop     r15
0x180085935  pop     r14
0x180085937  pop     rdi
0x180085938  pop     rsi
0x180085939  pop     rbp
0x18008593a  retn
```
