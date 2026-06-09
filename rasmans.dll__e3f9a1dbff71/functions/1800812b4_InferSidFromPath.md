# InferSidFromPath

- ea: `0x1800812b4`
- end: `0x18008162b`
- name: `InferSidFromPath`
- size: `887`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089b70`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18005cc20`
- `0x1800812b4`
- `0x1800884c4`
- `0x180088564`
- `0x1800899ec`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180081369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180081369`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800814c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081572`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800814c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081572`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800814db`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800814db`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800814b8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081567`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800814b8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081567`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800814a2`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800814a2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x180081310`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrA` at `0x180081310`

## string_xrefs

- `0x18008146f`: `ProfileImagePath`

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
0x1800812b4  mov     [rsp-8+arg_10], rbx
0x1800812b9  push    rbp
0x1800812ba  push    rsi
0x1800812bb  push    rdi
0x1800812bc  push    r14
0x1800812be  push    r15
0x1800812c0  lea     rbp, [rsp-660h]
0x1800812c8  sub     rsp, 760h
0x1800812cf  mov     rax, cs:__security_cookie
0x1800812d6  xor     rax, rsp
0x1800812d9  mov     [rbp+680h+var_30], rax
0x1800812e0  mov     r15, rdx
0x1800812e3  test    rcx, rcx
0x1800812e6  jz      loc_180081600
0x1800812ec  test    rdx, rdx
0x1800812ef  jz      loc_180081600
0x1800812f5  call    StrDupAFromTInternal
0x1800812fa  mov     rdi, rax
0x1800812fd  test    rax, rax
0x180081300  jz      loc_180081524
0x180081306  lea     rdx, aUsers; "\\Users\\"
0x18008130d  mov     rcx, rax; pszFirst
0x180081310  call    cs:__imp_StrStrA
0x180081316  test    rax, rax
0x180081319  jz      loc_1800814C9
0x18008131f  add     rax, 7
0x180081323  jmp     short loc_18008132C
0x180081325  test    cl, cl
0x180081327  jz      short loc_180081333
0x180081329  inc     rax
0x18008132c  mov     cl, [rax]
0x18008132e  cmp     cl, 5Ch ; '\'
0x180081331  jnz     short loc_180081325
0x180081333  cmp     byte ptr [rax], 0
0x180081336  jz      loc_1800814C9
0x18008133c  mov     byte ptr [rax], 0
0x18008133f  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180081346  lea     rax, [rsp+780h+hKey]
0x18008134b  mov     [rsp+780h+hKey], 0
0x180081354  mov     r9d, 20219h; samDesired
0x18008135a  mov     [rsp+780h+phkResult], rax; phkResult
0x18008135f  xor     r8d, r8d; ulOptions
0x180081362  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081369  call    cs:__imp_RegOpenKeyExA
0x18008136f  mov     ebx, eax
0x180081371  test    eax, eax
0x180081373  jz      short loc_1800813B5
0x180081375  mov     r10, cs:WPP_GLOBAL_Control
0x18008137c  lea     rcx, WPP_GLOBAL_Control
0x180081383  cmp     r10, rcx
0x180081386  jz      short loc_1800813AE
0x180081388  test    byte ptr [r10+1Ch], 80h
0x18008138d  jz      short loc_1800813AE
0x18008138f  cmp     byte ptr [r10+19h], 2
0x180081394  jb      short loc_1800813AE
0x180081396  mov     rcx, [r10+10h]
0x18008139a  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800813a1  mov     edx, 14h
0x1800813a6  mov     r9d, eax
0x1800813a9  call    WPP_SF_d
0x1800813ae  mov     eax, ebx
0x1800813b0  jmp     loc_180081605
0x1800813b5  xor     edx, edx; Val
0x1800813b7  mov     [rsp+780h+cSubKeys], 0
0x1800813bf  mov     r8d, 601h; Size
0x1800813c5  lea     rcx, [rbp+680h+SubKey]; void *
0x1800813c9  call    memset_0
0x1800813ce  mov     rcx, [rsp+780h+hKey]; hKey
0x1800813d3  lea     rdx, [rsp+780h+cSubKeys]; lpcSubKeys
0x1800813d8  call    RegGetNumberOfSubkeys
0x1800813dd  test    eax, eax
0x1800813df  jz      short loc_180081425
0x1800813e1  mov     r10, cs:WPP_GLOBAL_Control
0x1800813e8  lea     rcx, WPP_GLOBAL_Control
0x1800813ef  cmp     r10, rcx
0x1800813f2  jz      short loc_18008141B
0x1800813f4  test    byte ptr [r10+1Ch], 80h
0x1800813f9  jz      short loc_18008141B
0x1800813fb  cmp     byte ptr [r10+19h], 2
0x180081400  jb      short loc_18008141B
0x180081402  mov     rcx, [r10+10h]
0x180081406  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18008140d  mov     edx, 15h
0x180081412  lea     r9d, [rdx-14h]
0x180081416  call    WPP_SF_d
0x18008141b  mov     eax, 1
0x180081420  jmp     loc_180081605
0x180081425  xor     esi, esi
0x180081427  cmp     [rsp+780h+cSubKeys], esi
0x18008142b  jbe     loc_1800814B5
0x180081431  mov     ebx, 100h
0x180081436  mov     rcx, [rsp+780h+hKey]
0x18008143b  lea     r8, [rbp+680h+SubKey]
0x18008143f  mov     edx, esi
0x180081441  call    RegGetIthSectionName
0x180081446  test    eax, eax
0x180081448  jz      loc_1800815BB
0x18008144e  mov     r8, rbx; Size
0x180081451  lea     rcx, [rsp+780h+String1]; void *
0x180081456  xor     edx, edx; Val
0x180081458  call    memset_0
0x18008145d  mov     rcx, [rsp+780h+hKey]; hkey
0x180081462  lea     r9, [rbp+680h+SubKey]; lpSubKey
0x180081466  lea     r8, [rsp+780h+String1]; pvData
0x18008146b  mov     dword ptr [rsp+780h+phkResult], ebx; DWORD
0x18008146f  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x180081476  call    RegReadStringValue
0x18008147b  mov     r14d, eax
0x18008147e  test    eax, eax
0x180081480  jnz     loc_18008157F
0x180081486  or      r14d, 0FFFFFFFFh
0x18008148a  lea     r8, [rsp+780h+String1]; lpString1
0x18008148f  mov     [rsp+780h+cchCount2], r14d; cchCount2
0x180081494  lea     edx, [rax+1]; dwCmpFlags
0x180081497  mov     r9d, r14d; cchCount1
0x18008149a  mov     [rsp+780h+phkResult], rdi; lpString2
0x18008149f  lea     ecx, [rax+7Fh]; Locale
0x1800814a2  call    cs:__imp_CompareStringA
0x1800814a8  cmp     eax, 2
0x1800814ab  jz      short loc_1800814D3
0x1800814ad  inc     esi
0x1800814af  cmp     esi, [rsp+780h+cSubKeys]
0x1800814b3  jb      short loc_180081436
0x1800814b5  mov     rcx, rdi; hMem
0x1800814b8  call    cs:__imp_GlobalFree
0x1800814be  mov     rcx, [rsp+780h+hKey]; hKey
0x1800814c3  call    cs:__imp_RegCloseKey
0x1800814c9  mov     eax, 27Bh
0x1800814ce  jmp     loc_180081605
0x1800814d3  mov     rdx, rbx; dwBytes
0x1800814d6  mov     ecx, 40h ; '@'; uFlags
0x1800814db  call    cs:__imp_GlobalAlloc
0x1800814e1  mov     [r15], rax
0x1800814e4  mov     rcx, rax
0x1800814e7  test    rax, rax
0x1800814ea  jnz     short loc_18008152E
0x1800814ec  mov     rax, cs:WPP_GLOBAL_Control
0x1800814f3  lea     rcx, WPP_GLOBAL_Control
0x1800814fa  cmp     rax, rcx
0x1800814fd  jz      short loc_180081524
0x1800814ff  test    byte ptr [rax+1Ch], 80h
0x180081503  jz      short loc_180081524
0x180081505  cmp     byte ptr [rax+19h], 2
0x180081509  jb      short loc_180081524
0x18008150b  mov     rcx, [rax+10h]
0x18008150f  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180081516  mov     edx, 18h
0x18008151b  lea     r9d, [rdx-10h]
0x18008151f  call    WPP_SF_d
0x180081524  mov     eax, 8
0x180081529  jmp     loc_180081605
0x18008152e  mov     eax, 7FFFFFFEh
0x180081533  lea     rdx, [rbp+680h+SubKey]
0x180081537  test    rax, rax
0x18008153a  jz      short loc_180081556
0x18008153c  mov     r8b, [rdx]
0x18008153f  test    r8b, r8b
0x180081542  jz      short loc_180081556
0x180081544  mov     [rcx], r8b
0x180081547  inc     rdx
0x18008154a  inc     rcx
0x18008154d  dec     rax
0x180081550  sub     rbx, 1
0x180081554  jnz     short loc_180081537
0x180081556  lea     rax, [rcx-1]
0x18008155a  test    rbx, rbx
0x18008155d  cmovnz  rax, rcx
0x180081561  mov     rcx, rdi; hMem
0x180081564  mov     byte ptr [rax], 0
0x180081567  call    cs:__imp_GlobalFree
0x18008156d  mov     rcx, [rsp+780h+hKey]; hKey
0x180081572  call    cs:__imp_RegCloseKey
0x180081578  xor     eax, eax
0x18008157a  jmp     loc_180081605
0x18008157f  mov     rax, cs:WPP_GLOBAL_Control
0x180081586  lea     rcx, WPP_GLOBAL_Control
0x18008158d  cmp     rax, rcx
0x180081590  jz      short loc_1800815B6
0x180081592  test    byte ptr [rax+1Ch], 80h
0x180081596  jz      short loc_1800815B6
0x180081598  cmp     byte ptr [rax+19h], 2
0x18008159c  jb      short loc_1800815B6
0x18008159e  mov     rcx, [rax+10h]
0x1800815a2  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800815a9  mov     edx, 17h
0x1800815ae  mov     r9d, r14d
0x1800815b1  call    WPP_SF_d
0x1800815b6  mov     eax, r14d
0x1800815b9  jmp     short loc_180081605
0x1800815bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800815c2  lea     rcx, WPP_GLOBAL_Control
0x1800815c9  cmp     rax, rcx
0x1800815cc  jz      loc_1800814C9
0x1800815d2  test    byte ptr [rax+1Ch], 80h
0x1800815d6  jz      loc_1800814C9
0x1800815dc  cmp     byte ptr [rax+19h], 6
0x1800815e0  jb      loc_1800814C9
0x1800815e6  mov     rcx, [rax+10h]
0x1800815ea  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800815f1  mov     edx, 16h
0x1800815f6  call    WPP_SF_
0x1800815fb  jmp     loc_1800814C9
0x180081600  mov     eax, 57h ; 'W'
0x180081605  mov     rcx, [rbp+680h+var_30]
0x18008160c  xor     rcx, rsp; StackCookie
0x18008160f  call    __security_check_cookie
0x180081614  mov     rbx, [rsp+780h+arg_10]
0x18008161c  add     rsp, 760h
0x180081623  pop     r15
0x180081625  pop     r14
0x180081627  pop     rdi
0x180081628  pop     rsi
0x180081629  pop     rbp
0x18008162a  retn
```
