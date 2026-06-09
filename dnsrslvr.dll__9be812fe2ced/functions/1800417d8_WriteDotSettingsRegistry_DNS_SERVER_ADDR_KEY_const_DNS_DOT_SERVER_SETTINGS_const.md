# WriteDotSettingsRegistry(_DNS_SERVER_ADDR_KEY const *,_DNS_DOT_SERVER_SETTINGS const *)

- ea: `0x1800417d8`
- end: `0x180041b0f`
- name: `?WriteDotSettingsRegistry@@YAJPEBU_DNS_SERVER_ADDR_KEY@@PEBU_DNS_DOT_SERVER_SETTINGS@@@Z`
- size: `823`
- prototype: `__int64 __fastcall(const struct _DNS_SERVER_ADDR_KEY *, const struct _DNS_DOT_SERVER_SETTINGS *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18004150c`

## callees

- `0x1800417d8`
- `0x18004285c`
- `0x180046ec0`
- `0x180047818`
- `0x18005ef14`
- `0x18007d7fc`
- `0x180085fb8`
- `0x180086384`
- `0x1800868b8`
- `0x180086b1c`
- `0x180086f78`
- `0x18008841c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041aae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ac3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041aae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ac3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004199c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004199c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041957`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800419f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041a26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041957`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800419f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180041a26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800418a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800418a6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800418e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800418e6`

## string_xrefs

- `0x180041898`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\DohWellKnownServers`

## pseudocode

```c
__int64 __fastcall WriteDotSettingsRegistry(
        const struct _DNS_SERVER_ADDR_KEY *a1,
        const struct _DNS_DOT_SERVER_SETTINGS *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  const BYTE *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  const BYTE *v12; // rdi
  __int64 v13; // rcx
  HKEY v15; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[72]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v15 = 0;
  *(_DWORD *)Data = 0;
  memset_0(SubKey, 0, 0x82u);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qq(1035, 48, (unsigned int)WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, (_DWORD)a1, (__int64)a2);
  v4 = DnsConvertServerAddrToString(a1, SubKey);
  v5 = v4;
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_30;
    v10 = 49;
    goto LABEL_29;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_S(1035, 50, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, SubKey);
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters\\DohWellKnownServers",
         0,
         0x3001Fu,
         &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_30;
    v10 = 51;
    goto LABEL_29;
  }
  v6 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &v15, 0);
  v5 = v6;
  if ( v6 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SD(1035, 52, (unsigned int)WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, (unsigned int)SubKey, v6);
    goto LABEL_30;
  }
  v7 = *(const BYTE **)a2;
  if ( !*(_QWORD *)a2 )
  {
    v4 = RegDeleteValueW(v15, L"DotHost");
    v5 = v4;
    if ( (v4 & 0xFFFFFFFD) == 0 )
      goto LABEL_19;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_30;
    v10 = 54;
LABEL_29:
    WPP_SF_d(1035, v10, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v4);
    goto LABEL_30;
  }
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&v7[2 * v8] );
  v5 = RegSetValueExW(v15, L"DotHost", 0, 1u, v7, 2 * v8 + 2);
  if ( v5 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_DS(1035, 53, (unsigned int)WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v5, *(_QWORD *)a2);
    goto LABEL_30;
  }
LABEL_19:
  *(_DWORD *)Data = (unsigned __int16)DnsConvertDotPort(*((unsigned __int16 *)a2 + 8), v9);
  v5 = RegSetValueExW(v15, L"DotPort", 0, 4u, Data, 4u);
  if ( v5 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_Dd(v11, 55, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v5, *((unsigned __int16 *)a2 + 8));
  }
  else
  {
    v12 = (const BYTE *)a2 + 8;
    v5 = RegSetValueExW(v15, L"DotFlags", 0, 0xBu, v12, 8u);
    if ( v5 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_Di(v13, 56, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v5, *(_QWORD *)v12);
  }
LABEL_30:
  if ( v15 )
  {
    RegCloseKey(v15);
    v15 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 57, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800417d8  mov     [rsp-8+arg_10], rbx
0x1800417dd  push    rbp
0x1800417de  push    rsi
0x1800417df  push    rdi
0x1800417e0  push    r12
0x1800417e2  push    r15
0x1800417e4  lea     rbp, [rsp-10h]
0x1800417e9  sub     rsp, 110h
0x1800417f0  mov     rax, cs:__security_cookie
0x1800417f7  xor     rax, rsp
0x1800417fa  mov     [rbp+30h+var_30], rax
0x1800417fe  xor     esi, esi
0x180041800  mov     rdi, rdx
0x180041803  mov     rbx, rcx
0x180041806  mov     [rsp+130h+hKey], rsi
0x18004180b  xor     edx, edx; Val
0x18004180d  mov     [rsp+130h+var_E0], rsi
0x180041812  lea     rcx, [rsp+130h+SubKey]; void *
0x180041817  mov     dword ptr [rsp+130h+Data], esi
0x18004181b  mov     r8d, 82h; Size
0x180041821  call    memset_0
0x180041826  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004182d  lea     r15, WPP_4190c4b8c0763a141156073a5fd4862d_Traceguids
0x180041834  mov     r12d, 40Bh
0x18004183a  jz      short loc_180041852
0x18004183c  lea     edx, [rsi+30h]
0x18004183f  mov     [rsp+130h+phkResult], rdi
0x180041844  mov     ecx, r12d
0x180041847  mov     r9, rbx
0x18004184a  mov     r8, r15
0x18004184d  call    WPP_SF_qq
0x180041852  lea     rdx, [rsp+130h+SubKey]
0x180041857  mov     rcx, rbx
0x18004185a  call    DnsConvertServerAddrToString
0x18004185f  mov     ebx, eax
0x180041861  test    eax, eax
0x180041863  jnz     loc_180041A88
0x180041869  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180041870  jz      short loc_180041885
0x180041872  lea     edx, [rax+32h]
0x180041875  mov     ecx, r12d
0x180041878  lea     r9, [rsp+130h+SubKey]
0x18004187d  mov     r8, r15
0x180041880  call    WPP_SF_S
0x180041885  lea     rax, [rsp+130h+hKey]
0x18004188a  mov     r9d, 3001Fh; samDesired
0x180041890  xor     r8d, r8d; ulOptions
0x180041893  mov     [rsp+130h+phkResult], rax; phkResult
0x180041898  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18004189f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800418a6  call    cs:__imp_RegOpenKeyExW
0x1800418ac  mov     ebx, eax
0x1800418ae  test    eax, eax
0x1800418b0  jnz     loc_180041A78
0x1800418b6  mov     rcx, [rsp+130h+hKey]; hKey
0x1800418bb  lea     rax, [rsp+130h+var_E0]
0x1800418c0  mov     [rsp+130h+lpdwDisposition], rsi; lpdwDisposition
0x1800418c5  lea     rdx, [rsp+130h+SubKey]; lpSubKey
0x1800418ca  mov     [rsp+130h+var_F8], rax; phkResult
0x1800418cf  xor     r9d, r9d; lpClass
0x1800418d2  mov     [rsp+130h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800418d7  xor     r8d, r8d; Reserved
0x1800418da  mov     [rsp+130h+samDesired], 20006h; samDesired
0x1800418e2  mov     dword ptr [rsp+130h+phkResult], esi; dwOptions
0x1800418e6  call    cs:__imp_RegCreateKeyExW
0x1800418ec  mov     ebx, eax
0x1800418ee  test    eax, eax
0x1800418f0  jz      short loc_18004191D
0x1800418f2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800418f9  jz      loc_180041AA4
0x1800418ff  mov     edx, 34h ; '4'
0x180041904  mov     dword ptr [rsp+130h+phkResult], eax
0x180041908  mov     ecx, r12d
0x18004190b  lea     r9, [rsp+130h+SubKey]
0x180041910  mov     r8, r15
0x180041913  call    WPP_SF_SD
0x180041918  jmp     loc_180041AA4
0x18004191d  mov     rcx, [rdi]
0x180041920  test    rcx, rcx
0x180041923  jz      short loc_180041990
0x180041925  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041929  inc     rax
0x18004192c  cmp     [rcx+rax*2], si
0x180041930  jnz     short loc_180041929
0x180041932  lea     eax, ds:2[rax*2]
0x180041939  mov     r9d, 1; dwType
0x18004193f  mov     [rsp+130h+samDesired], eax; cbData
0x180041943  lea     rdx, aDothost; "DotHost"
0x18004194a  mov     [rsp+130h+phkResult], rcx; lpData
0x18004194f  xor     r8d, r8d; Reserved
0x180041952  mov     rcx, [rsp+130h+var_E0]; hKey
0x180041957  call    cs:__imp_RegSetValueExW
0x18004195d  mov     ebx, eax
0x18004195f  test    eax, eax
0x180041961  jz      short loc_1800419C2
0x180041963  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004196a  jz      loc_180041AA4
0x180041970  mov     rax, [rdi]
0x180041973  mov     edx, 35h ; '5'
0x180041978  mov     ecx, r12d
0x18004197b  mov     [rsp+130h+phkResult], rax
0x180041980  mov     r9d, ebx
0x180041983  mov     r8, r15
0x180041986  call    WPP_SF_DS
0x18004198b  jmp     loc_180041AA4
0x180041990  mov     rcx, [rsp+130h+var_E0]; hKey
0x180041995  lea     rdx, aDothost; "DotHost"
0x18004199c  call    cs:__imp_RegDeleteValueW
0x1800419a2  mov     ebx, eax
0x1800419a4  test    eax, 0FFFFFFFDh
0x1800419a9  jz      short loc_1800419C2
0x1800419ab  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800419b2  jz      loc_180041AA4
0x1800419b8  mov     edx, 36h ; '6'
0x1800419bd  jmp     loc_180041A96
0x1800419c2  movzx   ecx, word ptr [rdi+10h]
0x1800419c6  call    DnsConvertDotPort
0x1800419cb  mov     rcx, [rsp+130h+var_E0]; hKey
0x1800419d0  lea     rdx, aDotport; "DotPort"
0x1800419d7  movzx   eax, ax
0x1800419da  mov     r9d, 4; dwType
0x1800419e0  mov     dword ptr [rsp+130h+Data], eax
0x1800419e4  xor     r8d, r8d; Reserved
0x1800419e7  lea     rax, [rsp+130h+Data]
0x1800419ec  mov     [rsp+130h+samDesired], r9d; cbData
0x1800419f1  mov     [rsp+130h+phkResult], rax; lpData
0x1800419f6  call    cs:__imp_RegSetValueExW
0x1800419fc  mov     ebx, eax
0x1800419fe  test    eax, eax
0x180041a00  jnz     short loc_180041A55
0x180041a02  mov     rcx, [rsp+130h+var_E0]; hKey
0x180041a07  lea     r9d, [rax+0Bh]; dwType
0x180041a0b  add     rdi, 8
0x180041a0f  mov     [rsp+130h+samDesired], 8; cbData
0x180041a17  xor     r8d, r8d; Reserved
0x180041a1a  mov     [rsp+130h+phkResult], rdi; lpData
0x180041a1f  lea     rdx, aDotflags; "DotFlags"
0x180041a26  call    cs:__imp_RegSetValueExW
0x180041a2c  mov     ebx, eax
0x180041a2e  test    eax, eax
0x180041a30  jz      short loc_180041AA4
0x180041a32  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180041a39  jz      short loc_180041AA4
0x180041a3b  mov     rax, [rdi]
0x180041a3e  mov     edx, 38h ; '8'
0x180041a43  mov     r9d, ebx
0x180041a46  mov     [rsp+130h+phkResult], rax
0x180041a4b  mov     r8, r15
0x180041a4e  call    WPP_SF_Di
0x180041a53  jmp     short loc_180041AA4
0x180041a55  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180041a5c  jz      short loc_180041AA4
0x180041a5e  movzx   eax, word ptr [rdi+10h]
0x180041a62  mov     edx, 37h ; '7'
0x180041a67  mov     r9d, ebx
0x180041a6a  mov     dword ptr [rsp+130h+phkResult], eax
0x180041a6e  mov     r8, r15
0x180041a71  call    WPP_SF_Dd
0x180041a76  jmp     short loc_180041AA4
0x180041a78  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180041a7f  jz      short loc_180041AA4
0x180041a81  mov     edx, 33h ; '3'
0x180041a86  jmp     short loc_180041A96
0x180041a88  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180041a8f  jz      short loc_180041AA4
0x180041a91  mov     edx, 31h ; '1'
0x180041a96  mov     r9d, eax
0x180041a99  mov     r8, r15
0x180041a9c  mov     ecx, r12d
0x180041a9f  call    WPP_SF_d
0x180041aa4  mov     rcx, [rsp+130h+var_E0]; hKey
0x180041aa9  test    rcx, rcx
0x180041aac  jz      short loc_180041AB9
0x180041aae  call    cs:__imp_RegCloseKey
0x180041ab4  mov     [rsp+130h+var_E0], rsi
0x180041ab9  mov     rcx, [rsp+130h+hKey]; hKey
0x180041abe  test    rcx, rcx
0x180041ac1  jz      short loc_180041ACE
0x180041ac3  call    cs:__imp_RegCloseKey
0x180041ac9  mov     [rsp+130h+hKey], rsi
0x180041ace  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180041ad5  jz      short loc_180041AEA
0x180041ad7  mov     edx, 39h ; '9'
0x180041adc  mov     ecx, r12d
0x180041adf  mov     r9d, ebx
0x180041ae2  mov     r8, r15
0x180041ae5  call    WPP_SF_d
0x180041aea  mov     eax, ebx
0x180041aec  mov     rcx, [rbp+30h+var_30]
0x180041af0  xor     rcx, rsp; StackCookie
0x180041af3  call    __security_check_cookie
0x180041af8  mov     rbx, [rsp+130h+arg_10]
0x180041b00  add     rsp, 110h
0x180041b07  pop     r15
0x180041b09  pop     r12
0x180041b0b  pop     rdi
0x180041b0c  pop     rsi
0x180041b0d  pop     rbp
0x180041b0e  retn
```
