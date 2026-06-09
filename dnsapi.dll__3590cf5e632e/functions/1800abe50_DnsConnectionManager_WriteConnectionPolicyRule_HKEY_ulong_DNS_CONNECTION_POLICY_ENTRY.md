# DnsConnectionManager::WriteConnectionPolicyRule(HKEY__ *,ulong,_DNS_CONNECTION_POLICY_ENTRY *)

- ea: `0x1800abe50`
- end: `0x1800ac3f5`
- name: `?WriteConnectionPolicyRule@DnsConnectionManager@@AEAAJPEAUHKEY__@@KPEAU_DNS_CONNECTION_POLICY_ENTRY@@@Z`
- size: `1445`
- prototype: `int(DnsConnectionManager *__hidden this, HKEY, unsigned int, struct _DNS_CONNECTION_POLICY_ENTRY *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ab828`

## callees

- `0x1800407cc`
- `0x18004148c`
- `0x1800417d0`
- `0x18004e1d0`
- `0x18004ec60`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800abe50`
- `0x1800c439c`
- `0x1800cc528`
- `0x1800d63cc`
- `0x1800d6694`
- `0x1800dbfe0`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800abfa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800abfa9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800abf64`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800abf64`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac3bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ac3bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ac321`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ac321`
- `RPCRT4!UuidCreate` at `0x1800ac024`
- `RPCRT4!UuidCreate` at `0x1800ac024`

## string_xrefs

- `0x1800ac290`: `AppSid`

## pseudocode

```c
__int64 __fastcall DnsConnectionManager::WriteConnectionPolicyRule(
        DnsConnectionManager *this,
        HKEY a2,
        int a3,
        struct _DNS_CONNECTION_POLICY_ENTRY *a4)
{
  char v4; // di
  HKEY v5; // r13
  int v6; // esi
  const WCHAR *v7; // r14
  __int64 v8; // rbx
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  DWORD *p_cbAppSid; // rax
  __int64 *p_pbAppSid; // r12
  unsigned int v15; // esi
  int v16; // edi
  BYTE *pwszAppId; // r13
  PCWSTR pwszHost; // rdi
  const unsigned __int16 *v20; // rdx
  PCWSTR *ppwszConnections; // r8
  unsigned int v22; // r14d
  __int64 v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 Heap; // rax
  DWORD v27; // r10d
  __int64 v28; // r12
  int v29; // r10d
  __int64 v30; // rax
  unsigned int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  DWORD *p_dwPolicyEntryFlags; // r15
  const BYTE *v35; // rcx
  LSTATUS v36; // eax
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  PBYTE *v39; // [rsp+70h] [rbp-90h]
  _DWORD *v40; // [rsp+78h] [rbp-88h]
  DWORD *v41; // [rsp+80h] [rbp-80h]
  __int64 v42; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR lpValueName; // [rsp+90h] [rbp-70h] BYREF
  DWORD dwType[2]; // [rsp+98h] [rbp-68h]
  BYTE *lpData; // [rsp+A0h] [rbp-60h]
  DWORD cbData[2]; // [rsp+A8h] [rbp-58h]
  const WCHAR *v47; // [rsp+B0h] [rbp-50h]
  int v48; // [rsp+B8h] [rbp-48h]
  _DWORD *v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+C8h] [rbp-38h]
  const WCHAR *v51; // [rsp+D0h] [rbp-30h]
  int v52; // [rsp+D8h] [rbp-28h]
  __int64 v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+E8h] [rbp-18h]
  const WCHAR *v55; // [rsp+F0h] [rbp-10h]
  int v56; // [rsp+F8h] [rbp-8h]
  DWORD *v57; // [rsp+100h] [rbp+0h]
  int v58; // [rsp+108h] [rbp+8h]
  const WCHAR *v59; // [rsp+110h] [rbp+10h]
  int v60; // [rsp+118h] [rbp+18h]
  int *v61; // [rsp+120h] [rbp+20h]
  int v62; // [rsp+128h] [rbp+28h]
  const WCHAR *v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+138h] [rbp+38h]
  __int64 v65; // [rsp+140h] [rbp+40h]
  DWORD v66; // [rsp+148h] [rbp+48h]
  int v67; // [rsp+150h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+158h] [rbp+58h] BYREF
  UUID Uuid; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v70[88]; // [rsp+170h] [rbp+70h] BYREF
  int v71; // [rsp+290h] [rbp+190h] BYREF

  v71 = a3;
  v4 = a3;
  v5 = a2;
  lpSubKey[1] = 0;
  v6 = (int)this;
  hKey = 0;
  v7 = &word_1800F66E0;
  v42 = 0;
  lpSubKey[0] = &word_1800F66E0;
  v67 = 42;
  v8 = 0;
  memset_0(&lpValueName, 0, 0xC0u);
  Uuid = 0;
  memset_0(v70, 0, 0xA2u);
  p_cbAppSid = &a4->cbAppSid;
  p_pbAppSid = (__int64 *)&a4->pbAppSid;
  v41 = &a4->cbAppSid;
  v39 = &a4->pbAppSid;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_qqDqqD(v11, v10, v12, v6, (__int64)v5, v4, (__int64)a4, *p_pbAppSid, *p_cbAppSid);
    p_cbAppSid = &a4->cbAppSid;
  }
  else
  {
    v39 = &a4->pbAppSid;
    v41 = &a4->cbAppSid;
  }
  v15 = 0;
  if ( *p_pbAppSid )
  {
    if ( !*p_cbAppSid )
    {
LABEL_6:
      v16 = -2147024809;
      goto LABEL_7;
    }
  }
  else if ( *p_cbAppSid )
  {
    goto LABEL_6;
  }
  pwszAppId = (BYTE *)a4->pwszAppId;
  if ( !pwszAppId || !*(_WORD *)pwszAppId )
    pwszAppId = (BYTE *)&v67;
  pwszHost = a4->pwszHost;
  v40 = pwszHost;
  if ( !pwszHost || !*pwszHost )
    v40 = &v67;
  if ( UuidCreate(&Uuid) || !(unsigned int)Dns_GuidToString(&Uuid, v70) )
  {
    v16 = -2147024888;
LABEL_25:
    v5 = a2;
    goto LABEL_7;
  }
  v16 = CWxString::Set((CWxString *)lpSubKey, v20, v70);
  if ( v16 < 0 )
  {
LABEL_28:
    v7 = lpSubKey[0];
    goto LABEL_25;
  }
  v22 = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_S(1054, 24, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, lpSubKey[0]);
  v23 = -1;
  if ( !a4->nConnections )
    goto LABEL_51;
  ppwszConnections = a4->ppwszConnections;
  LODWORD(v24) = 0;
  do
  {
    v25 = -1;
    do
      ++v25;
    while ( ppwszConnections[(unsigned int)v24][v25] );
    v24 = (unsigned int)(v24 + 1);
    v22 += v25 + 1;
  }
  while ( (unsigned int)v24 < a4->nConnections );
  if ( !v22 )
    goto LABEL_51;
  ++v22;
  Heap = WxAllocateHeapEx(v24, 2 * v22);
  if ( !Heap )
  {
    v16 = -2147024882;
    goto LABEL_28;
  }
  v8 = Heap;
  v42 = Heap;
  v27 = 0;
  if ( !a4->nConnections )
  {
    if ( !v22 )
    {
      v16 = -2147024785;
      goto LABEL_28;
    }
LABEL_50:
    v32 = v15;
    v15 = 0;
    *(_WORD *)(v8 + 2 * v32) = 0;
LABEL_51:
    dwType[0] = 1;
    lpValueName = L"AppId";
    v33 = -1;
    lpData = pwszAppId;
    do
      ++v33;
    while ( *(_WORD *)&pwszAppId[2 * v33] );
    cbData[0] = 2 * v33 + 2;
    v47 = L"Host";
    v48 = 1;
    v49 = v40;
    do
      ++v23;
    while ( *((_WORD *)v40 + v23) );
    v52 = 7;
    v53 = v8;
    v50 = 2 * v23 + 2;
    p_dwPolicyEntryFlags = &a4->dwPolicyEntryFlags;
    v56 = 4;
    v51 = L"Connections";
    v54 = 2 * v22;
    v55 = L"RuleFlags";
    v59 = L"PolicyTag";
    v61 = &v71;
    v63 = L"AppSid";
    v65 = *p_pbAppSid;
    v57 = p_dwPolicyEntryFlags;
    v58 = 4;
    v60 = 4;
    v66 = *v41;
    v62 = 4;
    v64 = 3;
    v7 = lpSubKey[0];
    if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_SSSDD(
        (_DWORD)v40,
        4,
        (_DWORD)ppwszConnections,
        lpSubKey[0],
        (__int64)pwszAppId,
        (__int64)v40,
        *p_dwPolicyEntryFlags,
        v71);
    v5 = a2;
    v16 = RegCreateKeyExW(a2, v7, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    if ( v16 >= 0 )
    {
      while ( 1 )
      {
        v35 = *(const BYTE **)&cbData[8 * v15 - 2];
        if ( v35 )
        {
          v36 = RegSetValueExW(hKey, *(LPCWSTR *)&dwType[8 * v15 - 2], 0, dwType[8 * v15], v35, cbData[8 * v15]);
          v16 = v36;
          if ( v36 > 0 )
            v16 = (unsigned __int16)v36 | 0x80070000;
          if ( v16 < 0 )
            break;
        }
        if ( ++v15 >= 6 )
          goto LABEL_9;
      }
    }
    goto LABEL_7;
  }
  while ( v15 < v22 )
  {
    v28 = v27;
    if ( (BYTE3(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_DS(
        1054,
        25,
        (unsigned int)WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids,
        v27,
        (__int64)a4->ppwszConnections[v27]);
    v16 = StringCchCopyW((unsigned __int16 *)(v8 + 2LL * v15), v22 - v15, a4->ppwszConnections[v28]);
    if ( v16 < 0 )
      goto LABEL_62;
    v23 = -1;
    v30 = -1;
    do
      ++v30;
    while ( a4->ppwszConnections[v28][v30] );
    v31 = v15 + v30 + 1;
    if ( v31 < v15 || v31 >= v22 )
      break;
    v27 = v29 + 1;
    v15 = v31;
    if ( v27 >= a4->nConnections )
    {
      p_pbAppSid = (__int64 *)v39;
      goto LABEL_50;
    }
  }
  v16 = -2147024785;
LABEL_62:
  v7 = lpSubKey[0];
  v5 = a2;
LABEL_7:
  if ( hKey )
    RegDeleteKeyExW(v5, v7, 0, 0);
LABEL_9:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 27, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids, (unsigned int)v16);
  if ( v8 )
    WxFreeHeapEx(&v42);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CWxString::_Release((CWxString *)lpSubKey);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800abe50  mov     [rsp-8+arg_10], r8d
0x1800abe55  push    rbp
0x1800abe56  push    rbx
0x1800abe57  push    rsi
0x1800abe58  push    rdi
0x1800abe59  push    r12
0x1800abe5b  push    r13
0x1800abe5d  push    r14
0x1800abe5f  push    r15
0x1800abe61  lea     rbp, [rsp-138h]
0x1800abe69  sub     rsp, 238h
0x1800abe70  mov     rax, cs:__security_cookie
0x1800abe77  xor     rax, rsp
0x1800abe7a  mov     [rbp+170h+var_50], rax
0x1800abe81  xor     eax, eax
0x1800abe83  mov     [rsp+270h+var_218], rdx
0x1800abe88  mov     edi, r8d
0x1800abe8b  mov     [rsp+270h+var_21C], eax
0x1800abe8f  mov     r13, rdx
0x1800abe92  mov     [rsp+270h+var_208], rax
0x1800abe97  mov     rsi, rcx
0x1800abe9a  mov     [rbp+170h+hKey], rax
0x1800abe9e  lea     r14, word_1800F66E0
0x1800abea5  mov     [rbp+170h+var_1E8], rax
0x1800abea9  xor     edx, edx; Val
0x1800abeab  mov     [rsp+270h+lpSubKey], r14
0x1800abeb0  mov     r8d, 0C0h; Size
0x1800abeb6  mov     [rbp+170h+var_120], 2Ah ; '*'
0x1800abebd  lea     rcx, [rbp+170h+lpValueName]; void *
0x1800abec1  mov     ebx, eax
0x1800abec3  mov     r15, r9
0x1800abec6  call    memset_0
0x1800abecb  xorps   xmm0, xmm0
0x1800abece  lea     rcx, [rbp+170h+var_100]; void *
0x1800abed2  xor     edx, edx; Val
0x1800abed4  mov     r8d, 0A2h; Size
0x1800abeda  movups  xmmword ptr [rbp+170h+Uuid.Data1], xmm0
0x1800abede  call    memset_0
0x1800abee3  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800abeea  lea     rax, [r15+10h]
0x1800abeee  lea     r12, [r15+18h]
0x1800abef2  mov     [rbp+170h+var_1F0], rax
0x1800abef6  mov     [rsp+270h+var_200], r12
0x1800abefb  jz      short loc_1800ABF28
0x1800abefd  mov     eax, [rax]
0x1800abeff  mov     r9, rsi
0x1800abf02  mov     dword ptr [rsp+270h+lpdwDisposition], eax
0x1800abf06  mov     rax, [r12]
0x1800abf0a  mov     [rsp+270h+phkResult], rax
0x1800abf0f  mov     [rsp+270h+lpSecurityAttributes], r15
0x1800abf14  mov     [rsp+270h+samDesired], edi
0x1800abf18  mov     qword ptr [rsp+270h+dwOptions], r13
0x1800abf1d  call    WPP_SF_qqDqqD
0x1800abf22  lea     rax, [r15+10h]
0x1800abf26  jmp     short loc_1800ABF31
0x1800abf28  mov     [rsp+270h+var_200], r12
0x1800abf2d  mov     [rbp+170h+var_1F0], rax
0x1800abf31  xor     esi, esi
0x1800abf33  cmp     [r12], rsi
0x1800abf37  jz      loc_1800ABFE9
0x1800abf3d  cmp     [rax], esi
0x1800abf3f  ja      loc_1800ABFF1
0x1800abf45  mov     edi, 80070057h
0x1800abf4a  mov     [rsp+270h+var_21C], 152h
0x1800abf52  cmp     [rbp+170h+hKey], rsi
0x1800abf56  jz      short loc_1800ABF70
0x1800abf58  xor     r9d, r9d; Reserved
0x1800abf5b  xor     r8d, r8d; samDesired
0x1800abf5e  mov     rdx, r14; lpSubKey
0x1800abf61  mov     rcx, r13; hKey
0x1800abf64  call    cs:__imp_RegDeleteKeyExW
0x1800abf6b  nop     dword ptr [rax+rax+00h]
0x1800abf70  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800abf77  jz      short loc_1800ABF92
0x1800abf79  mov     edx, 1Bh
0x1800abf7e  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800abf85  mov     ecx, 40Bh
0x1800abf8a  mov     r9d, edi
0x1800abf8d  call    WPP_SF_d
0x1800abf92  test    rbx, rbx
0x1800abf95  jz      short loc_1800ABFA0
0x1800abf97  lea     rcx, [rbp+170h+var_1E8]
0x1800abf9b  call    WxFreeHeapEx
0x1800abfa0  mov     rcx, [rbp+170h+hKey]; hKey
0x1800abfa4  test    rcx, rcx
0x1800abfa7  jz      short loc_1800ABFB9
0x1800abfa9  call    cs:__imp_RegCloseKey
0x1800abfb0  nop     dword ptr [rax+rax+00h]
0x1800abfb5  mov     [rbp+170h+hKey], rsi
0x1800abfb9  lea     rcx, [rsp+270h+lpSubKey]; this
0x1800abfbe  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800abfc3  mov     eax, edi
0x1800abfc5  mov     rcx, [rbp+170h+var_50]
0x1800abfcc  xor     rcx, rsp; StackCookie
0x1800abfcf  call    __security_check_cookie
0x1800abfd4  add     rsp, 238h
0x1800abfdb  pop     r15
0x1800abfdd  pop     r14
0x1800abfdf  pop     r13
0x1800abfe1  pop     r12
0x1800abfe3  pop     rdi
0x1800abfe4  pop     rsi
0x1800abfe5  pop     rbx
0x1800abfe6  pop     rbp
0x1800abfe7  retn
0x1800abfe9  cmp     [rax], esi
0x1800abfeb  jnz     loc_1800ABF45
0x1800abff1  mov     r13, [r15+8]
0x1800abff5  test    r13, r13
0x1800abff8  jz      short loc_1800AC001
0x1800abffa  cmp     [r13+0], si
0x1800abfff  jnz     short loc_1800AC005
0x1800ac001  lea     r13, [rbp+170h+var_120]
0x1800ac005  mov     rdi, [r15]
0x1800ac008  mov     [rsp+270h+var_1F8], rdi
0x1800ac00d  test    rdi, rdi
0x1800ac010  jz      short loc_1800AC017
0x1800ac012  cmp     [rdi], si
0x1800ac015  jnz     short loc_1800AC020
0x1800ac017  lea     rax, [rbp+170h+var_120]
0x1800ac01b  mov     [rsp+270h+var_1F8], rax
0x1800ac020  lea     rcx, [rbp+170h+Uuid]; Uuid
0x1800ac024  call    cs:__imp_UuidCreate
0x1800ac02b  nop     dword ptr [rax+rax+00h]
0x1800ac030  test    eax, eax
0x1800ac032  jz      short loc_1800AC04B
0x1800ac034  mov     [rsp+270h+var_21C], 168h
0x1800ac03c  mov     edi, 80070008h
0x1800ac041  mov     r13, [rsp+270h+var_218]
0x1800ac046  jmp     loc_1800ABF52
0x1800ac04b  lea     rdx, [rbp+170h+var_100]
0x1800ac04f  lea     rcx, [rbp+170h+Uuid]
0x1800ac053  call    Dns_GuidToString
0x1800ac058  test    eax, eax
0x1800ac05a  jnz     short loc_1800AC066
0x1800ac05c  mov     [rsp+270h+var_21C], 16Dh
0x1800ac064  jmp     short loc_1800AC03C
0x1800ac066  lea     r8, [rbp+170h+var_100]; unsigned __int16 *
0x1800ac06a  lea     rcx, [rsp+270h+lpSubKey]; this
0x1800ac06f  call    ?Set@CWxString@@QEAAJPEBG0@Z; CWxString::Set(ushort const *,ushort const *)
0x1800ac074  mov     edi, eax
0x1800ac076  test    eax, eax
0x1800ac078  jns     short loc_1800AC089
0x1800ac07a  mov     [rsp+270h+var_21C], 171h
0x1800ac082  mov     r14, [rsp+270h+lpSubKey]
0x1800ac087  jmp     short loc_1800AC041
0x1800ac089  mov     r14d, esi
0x1800ac08c  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800ac093  jz      short loc_1800AC0B0
0x1800ac095  mov     r9, [rsp+270h+lpSubKey]
0x1800ac09a  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800ac0a1  mov     edx, 18h
0x1800ac0a6  mov     ecx, 41Eh
0x1800ac0ab  call    WPP_SF_S
0x1800ac0b0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ac0b4  cmp     [r15+20h], esi
0x1800ac0b8  jbe     loc_1800AC1EA
0x1800ac0be  mov     r8, [r15+28h]
0x1800ac0c2  mov     ecx, esi
0x1800ac0c4  mov     eax, ecx
0x1800ac0c6  mov     rdx, [r8+rax*8]
0x1800ac0ca  mov     rax, rdi
0x1800ac0cd  inc     rax
0x1800ac0d0  cmp     [rdx+rax*2], si
0x1800ac0d4  jnz     short loc_1800AC0CD
0x1800ac0d6  inc     r14d
0x1800ac0d9  inc     ecx
0x1800ac0db  add     r14d, eax
0x1800ac0de  cmp     ecx, [r15+20h]
0x1800ac0e2  jb      short loc_1800AC0C4
0x1800ac0e4  test    r14d, r14d
0x1800ac0e7  jz      loc_1800AC1EA
0x1800ac0ed  inc     r14d
0x1800ac0f0  mov     [rsp+270h+var_21C], esi
0x1800ac0f4  lea     edx, [r14+r14]
0x1800ac0f8  call    WxAllocateHeapEx
0x1800ac0fd  test    rax, rax
0x1800ac100  jnz     short loc_1800AC11C
0x1800ac102  mov     [rsp+270h+var_21C], 34h ; '4'
0x1800ac10a  mov     edi, 8007000Eh
0x1800ac10f  mov     [rsp+270h+var_21C], 189h
0x1800ac117  jmp     loc_1800AC082
0x1800ac11c  mov     rbx, rax
0x1800ac11f  mov     [rbp+170h+var_1E8], rax
0x1800ac123  xor     edx, edx
0x1800ac125  mov     r10d, edx
0x1800ac128  mov     [rsp+270h+var_220], edx
0x1800ac12c  cmp     [r15+20h], edx
0x1800ac130  jbe     loc_1800AC372
0x1800ac136  cmp     esi, r14d
0x1800ac139  jnb     loc_1800AC354
0x1800ac13f  mov     edi, r14d
0x1800ac142  sub     edi, esi
0x1800ac144  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800ac14b  mov     r12d, r10d
0x1800ac14e  jz      short loc_1800AC17B
0x1800ac150  mov     rax, [r15+28h]
0x1800ac154  lea     r8, WPP_8d63ef3cf88f3278fb85f81933f2f00e_Traceguids
0x1800ac15b  mov     edx, 19h
0x1800ac160  mov     ecx, 41Eh
0x1800ac165  mov     r9d, r10d
0x1800ac168  mov     rax, [rax+r12*8]
0x1800ac16c  mov     qword ptr [rsp+270h+dwOptions], rax
0x1800ac171  call    WPP_SF_DS
0x1800ac176  mov     r10d, [rsp+270h+var_220]
0x1800ac17b  mov     r8, [r15+28h]
0x1800ac17f  mov     eax, esi
0x1800ac181  mov     edx, edi; unsigned __int64
0x1800ac183  mov     r8, [r8+r12*8]; unsigned __int16 *
0x1800ac187  lea     rcx, [rbx+rax*2]; unsigned __int16 *
0x1800ac18b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ac190  xor     edx, edx
0x1800ac192  mov     edi, eax
0x1800ac194  test    eax, eax
0x1800ac196  js      loc_1800AC34A
0x1800ac19c  mov     rax, [r15+28h]
0x1800ac1a0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ac1a4  mov     rcx, [rax+r12*8]
0x1800ac1a8  mov     rax, rdi
0x1800ac1ab  inc     rax
0x1800ac1ae  cmp     [rcx+rax*2], dx
0x1800ac1b2  jnz     short loc_1800AC1AB
0x1800ac1b4  inc     eax
0x1800ac1b6  add     eax, esi
0x1800ac1b8  cmp     eax, esi
0x1800ac1ba  jb      loc_1800AC340
0x1800ac1c0  cmp     eax, r14d
0x1800ac1c3  jnb     loc_1800AC340
0x1800ac1c9  inc     r10d
0x1800ac1cc  mov     esi, eax
0x1800ac1ce  mov     [rsp+270h+var_220], r10d
0x1800ac1d3  cmp     r10d, [r15+20h]
0x1800ac1d7  jb      loc_1800AC136
0x1800ac1dd  mov     r12, [rsp+270h+var_200]
0x1800ac1e2  mov     ecx, esi
0x1800ac1e4  xor     esi, esi
0x1800ac1e6  mov     [rbx+rcx*2], si
0x1800ac1ea  lea     rax, aAppid; "AppId"
0x1800ac1f1  mov     [rbp+170h+dwType], 1
0x1800ac1f8  mov     [rbp+170h+lpValueName], rax
0x1800ac1fc  mov     rax, rdi
0x1800ac1ff  mov     [rbp+170h+lpData], r13
0x1800ac203  inc     rax
0x1800ac206  cmp     [r13+rax*2+0], si
0x1800ac20c  jnz     short loc_1800AC203
0x1800ac20e  mov     rcx, [rsp+270h+var_1F8]
0x1800ac213  lea     eax, ds:2[rax*2]
0x1800ac21a  mov     [rbp+170h+cbData], eax
0x1800ac21d  lea     rax, aHost; "Host"
0x1800ac224  mov     [rbp+170h+var_1C0], rax
0x1800ac228  mov     [rbp+170h+var_1B8], 1
0x1800ac22f  mov     [rbp+170h+var_1B0], rcx
0x1800ac233  inc     rdi
0x1800ac236  cmp     [rcx+rdi*2], si
0x1800ac23a  jnz     short loc_1800AC233
0x1800ac23c  mov     edx, 4
0x1800ac241  mov     [rbp+170h+var_198], 7
0x1800ac248  lea     eax, ds:2[rdi*2]
0x1800ac24f  mov     [rbp+170h+var_190], rbx
0x1800ac253  mov     [rbp+170h+var_1A8], eax
0x1800ac256  add     r15, 30h ; '0'
0x1800ac25a  lea     rax, aConnections; "Connections"
0x1800ac261  mov     [rbp+170h+var_178], edx
0x1800ac264  mov     [rbp+170h+var_1A0], rax
0x1800ac268  lea     eax, [r14+r14]
0x1800ac26c  mov     [rbp+170h+var_188], eax
0x1800ac26f  lea     rax, aRuleflags; "RuleFlags"
0x1800ac276  mov     [rbp+170h+var_180], rax
0x1800ac27a  lea     rax, aPolicytag; "PolicyTag"
0x1800ac281  mov     [rbp+170h+var_160], rax
0x1800ac285  lea     rax, [rbp+170h+arg_10]
0x1800ac28c  mov     [rbp+170h+var_150], rax
0x1800ac290  lea     rax, aAppsid; "AppSid"
0x1800ac297  mov     [rbp+170h+var_140], rax
0x1800ac29b  mov     rax, [r12]
0x1800ac29f  mov     [rbp+170h+var_130], rax
0x1800ac2a3  mov     rax, [rbp+170h+var_1F0]
0x1800ac2a7  mov     [rbp+170h+var_170], r15
0x1800ac2ab  mov     [rbp+170h+var_168], edx
0x1800ac2ae  mov     [rbp+170h+var_158], edx
0x1800ac2b1  mov     eax, [rax]
0x1800ac2b3  mov     [rbp+170h+var_128], eax
0x1800ac2b6  mov     [rbp+170h+var_148], edx
0x1800ac2b9  mov     [rbp+170h+var_138], 3
0x1800ac2c0  test    byte ptr cs:xmmword_1801119E0+3, 40h
0x1800ac2c7  mov     r14, [rsp+270h+lpSubKey]
0x1800ac2cc  jz      short loc_1800AC2F1
0x1800ac2ce  mov     eax, [rbp+170h+arg_10]
0x1800ac2d4  mov     r9, r14
0x1800ac2d7  mov     dword ptr [rsp+270h+phkResult], eax
0x1800ac2db  mov     eax, [r15]
0x1800ac2de  mov     dword ptr [rsp+270h+lpSecurityAttributes], eax
0x1800ac2e2  mov     qword ptr [rsp+270h+samDesired], rcx
0x1800ac2e7  mov     qword ptr [rsp+270h+dwOptions], r13
0x1800ac2ec  call    WPP_SF_SSSDD
0x1800ac2f1  mov     r13, [rsp+270h+var_218]
0x1800ac2f6  lea     rax, [rbp+170h+hKey]
0x1800ac2fa  mov     [rsp+270h+lpdwDisposition], rsi; lpdwDisposition
0x1800ac2ff  xor     r9d, r9d; lpClass
0x1800ac302  mov     [rsp+270h+phkResult], rax; phkResult
  ... truncated ...
```
