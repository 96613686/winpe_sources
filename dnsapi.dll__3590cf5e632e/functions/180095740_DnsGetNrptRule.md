# DnsGetNrptRule

- ea: `0x180095740`
- end: `0x18009595f`
- name: `DnsGetNrptRule`
- size: `543`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task`

## callees

- `0x1800097e0`
- `0x1800180e0`
- `0x18008b5f0`
- `0x18008bf98`
- `0x180095740`
- `0x1800bbe60`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800de650`
- `0x1800dfdc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800958ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800958ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095907`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095825`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095825`

## string_xrefs

- `0x1800957d8`: `Parameters\DnsPolicyConfig`
- `0x1800957ee`: `Dnscache`
- `0x1800957e7`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 __fastcall DnsGetNrptRule(LPCWSTR lpSubKey, _OWORD *a2)
{
  __int64 v4; // r9
  unsigned int NrptRuleFromRegistry; // ebx
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int64 v13; // [rsp+28h] [rbp-61h]
  HKEY phkResult; // [rsp+40h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-41h] BYREF
  _OWORD v16[7]; // [rsp+50h] [rbp-39h] BYREF

  hKey = 0;
  phkResult = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qq(1035, 32, (unsigned int)WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, (_DWORD)lpSubKey, (__int64)a2);
  if ( a2 && (memset_0(a2, 0, 0x70u), lpSubKey) )
  {
    NrptRuleFromRegistry = CreatePersistedRegistryKeyHelper(
                             (__int64)L"Dnscache",
                             (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                             (__int64)L"Parameters\\DnsPolicyConfig",
                             v4,
                             0x20019u,
                             v13,
                             0,
                             &hKey);
    if ( !NrptRuleFromRegistry )
    {
      NrptRuleFromRegistry = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
      if ( !NrptRuleFromRegistry )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          WPP_SF_S(1035, 33, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, lpSubKey);
        NrptRuleFromRegistry = Dns_ReadNrptRuleFromRegistry(phkResult, (int *)v16);
        if ( !NrptRuleFromRegistry )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            WPP_SF_(1035, 34, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids);
          v6 = v16[1];
          *a2 = v16[0];
          v7 = v16[2];
          a2[1] = v6;
          v8 = v16[3];
          a2[2] = v7;
          v9 = v16[4];
          a2[3] = v8;
          v10 = v16[5];
          a2[4] = v9;
          v11 = v16[6];
          a2[5] = v10;
          a2[6] = v11;
          memset_0(v16, 0, sizeof(v16));
        }
      }
    }
  }
  else
  {
    NrptRuleFromRegistry = 87;
  }
  DnsFreeNrptRule(v16);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 35, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids, NrptRuleFromRegistry);
  return NrptRuleFromRegistry;
}

```

## disassembly

```asm
0x180095740  mov     [rsp-8+arg_10], rbx
0x180095745  push    rbp
0x180095746  push    rsi
0x180095747  push    rdi
0x180095748  lea     rbp, [rsp-47h]
0x18009574d  sub     rsp, 0D0h
0x180095754  mov     rax, cs:__security_cookie
0x18009575b  xor     rax, rsp
0x18009575e  mov     [rbp+57h+var_20], rax
0x180095762  mov     rdi, rdx
0x180095765  mov     [rbp+57h+hKey], 0
0x18009576d  mov     rsi, rcx
0x180095770  mov     [rbp+57h+var_A0], 0
0x180095778  mov     ebx, 70h ; 'p'
0x18009577d  lea     rcx, [rbp+57h+var_90]; void *
0x180095781  mov     r8d, ebx; Size
0x180095784  xor     edx, edx; Val
0x180095786  call    memset_0
0x18009578b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180095792  jz      short loc_1800957B0
0x180095794  lea     edx, [rbx-50h]
0x180095797  mov     [rsp+0E0h+phkResult], rdi
0x18009579c  mov     ecx, 40Bh
0x1800957a1  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x1800957a8  mov     r9, rsi
0x1800957ab  call    WPP_SF_qq
0x1800957b0  test    rdi, rdi
0x1800957b3  jz      loc_1800958D3
0x1800957b9  mov     r8, rbx; Size
0x1800957bc  xor     edx, edx; Val
0x1800957be  mov     rcx, rdi; void *
0x1800957c1  call    memset_0
0x1800957c6  test    rsi, rsi
0x1800957c9  jz      loc_1800958D3
0x1800957cf  lea     rax, [rbp+57h+hKey]
0x1800957d3  mov     [rsp+0E0h+var_A8], rax
0x1800957d8  lea     r8, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x1800957df  mov     [rsp+0E0h+var_B0], 0
0x1800957e7  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800957ee  lea     rcx, aDnscache_1; "Dnscache"
0x1800957f5  mov     dword ptr [rsp+0E0h+phkResult], 20019h
0x1800957fd  call    CreatePersistedRegistryKeyHelper
0x180095802  mov     ebx, eax
0x180095804  test    eax, eax
0x180095806  jnz     loc_1800958D8
0x18009580c  mov     rcx, [rbp+57h+hKey]; hKey
0x180095810  lea     rax, [rbp+57h+var_A0]
0x180095814  mov     r9d, 20019h; samDesired
0x18009581a  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18009581f  xor     r8d, r8d; ulOptions
0x180095822  mov     rdx, rsi; lpSubKey
0x180095825  call    cs:__imp_RegOpenKeyExW
0x18009582c  nop     dword ptr [rax+rax+00h]
0x180095831  mov     ebx, eax
0x180095833  test    eax, eax
0x180095835  jnz     loc_1800958D8
0x18009583b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180095842  jz      short loc_18009585B
0x180095844  lea     edx, [rax+21h]
0x180095847  mov     ecx, 40Bh
0x18009584c  mov     r9, rsi
0x18009584f  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x180095856  call    WPP_SF_S
0x18009585b  mov     rcx, [rbp+57h+var_A0]; hKey
0x18009585f  lea     rdx, [rbp+57h+var_90]; void *
0x180095863  call    Dns_ReadNrptRuleFromRegistry
0x180095868  mov     ebx, eax
0x18009586a  test    eax, eax
0x18009586c  jnz     short loc_1800958D8
0x18009586e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180095875  jz      short loc_18009588B
0x180095877  lea     edx, [rax+22h]
0x18009587a  mov     ecx, 40Bh
0x18009587f  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x180095886  call    WPP_SF_
0x18009588b  movaps  xmm0, [rbp+57h+var_90]
0x18009588f  lea     rcx, [rbp+57h+var_90]; void *
0x180095893  movaps  xmm1, [rbp+57h+var_80]
0x180095897  xor     edx, edx; Val
0x180095899  movups  xmmword ptr [rdi], xmm0
0x18009589c  movaps  xmm0, [rbp+57h+var_70]
0x1800958a0  movups  xmmword ptr [rdi+10h], xmm1
0x1800958a4  lea     r8d, [rdx+70h]; Size
0x1800958a8  movaps  xmm1, [rbp+57h+var_60]
0x1800958ac  movups  xmmword ptr [rdi+20h], xmm0
0x1800958b0  movaps  xmm0, [rbp+57h+var_50]
0x1800958b4  movups  xmmword ptr [rdi+30h], xmm1
0x1800958b8  movaps  xmm1, [rbp+57h+var_40]
0x1800958bc  movups  xmmword ptr [rdi+40h], xmm0
0x1800958c0  movaps  xmm0, [rbp+57h+var_30]
0x1800958c4  movups  xmmword ptr [rdi+50h], xmm1
0x1800958c8  movups  xmmword ptr [rdi+60h], xmm0
0x1800958cc  call    memset_0
0x1800958d1  jmp     short loc_1800958D8
0x1800958d3  mov     ebx, 57h ; 'W'
0x1800958d8  lea     rcx, [rbp+57h+var_90]
0x1800958dc  call    DnsFreeNrptRule
0x1800958e1  mov     rcx, [rbp+57h+var_A0]; hKey
0x1800958e5  test    rcx, rcx
0x1800958e8  jz      short loc_1800958FE
0x1800958ea  call    cs:__imp_RegCloseKey
0x1800958f1  nop     dword ptr [rax+rax+00h]
0x1800958f6  mov     [rbp+57h+var_A0], 0
0x1800958fe  mov     rcx, [rbp+57h+hKey]; hKey
0x180095902  test    rcx, rcx
0x180095905  jz      short loc_18009591B
0x180095907  call    cs:__imp_RegCloseKey
0x18009590e  nop     dword ptr [rax+rax+00h]
0x180095913  mov     [rbp+57h+hKey], 0
0x18009591b  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180095922  jz      short loc_18009593D
0x180095924  mov     edx, 23h ; '#'
0x180095929  lea     r8, WPP_3f446efdbc2a3dd930a3c284624de6ad_Traceguids
0x180095930  mov     ecx, 40Bh
0x180095935  mov     r9d, ebx
0x180095938  call    WPP_SF_d
0x18009593d  mov     eax, ebx
0x18009593f  mov     rcx, [rbp+57h+var_20]
0x180095943  xor     rcx, rsp; StackCookie
0x180095946  call    __security_check_cookie
0x18009594b  mov     rbx, [rsp+0E0h+arg_10]
0x180095953  add     rsp, 0D0h
0x18009595a  pop     rdi
0x18009595b  pop     rsi
0x18009595c  pop     rbp
0x18009595d  retn
```
