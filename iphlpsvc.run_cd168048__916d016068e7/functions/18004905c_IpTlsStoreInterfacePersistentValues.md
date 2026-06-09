# IpTlsStoreInterfacePersistentValues

- ea: `0x18004905c`
- end: `0x180049306`
- name: `IpTlsStoreInterfacePersistentValues`
- size: `682`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180003ce4`
- `0x1800311d0`
- `0x18003587c`
- `0x180047d3c`
- `0x180048a4c`
- `0x18004930c`
- `0x18005fa9c`
- `0x180061520`
- `0x180063280`
- `0x18006789c`
- `0x1800681e8`

## callees

- `0x18000d7b0`
- `0x180034734`
- `0x18004905c`
- `0x18004b630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800492d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800492d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800491a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049218`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049283`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800492be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800491a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049218`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049283`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800492be`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004910a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004910a`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18004915c`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18004915c`

## string_xrefs

- `0x1800490b3`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\IPHTTPS`
- `0x18004911d`: `%s:RegCreateKeyEx: Key = %s: Status = %d`
- `0x1800491b5`: `%s:RegSetValueEx:%s = %s: Status = %d`
- `0x18004922d`: `%s:RegSetValueEx:%s :Statis = %d`

## pseudocode

```c
__int64 __fastcall IpTlsStoreInterfacePersistentValues(const BYTE *a1, int a2, char a3)
{
  const BYTE *v3; // r15
  __int64 v4; // r12
  unsigned int v7; // esi
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  __int64 samDesired; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[80]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[264]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = a1 + 56;
  v4 = a2;
  hKey = 0;
  if ( StringCchPrintfW(
         pszDest,
         0x105u,
         L"%s\\%s",
         L"System\\CurrentControlSet\\Services\\IPHLPSVC\\Parameters\\IPHTTPS",
         a1 + 56) >= 0 )
  {
    dwOptions[0] = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0, 0, 2u, 0, &hKey, 0);
    v7 = dwOptions[0];
    EventWrite0(0x10000000, L"%s:RegCreateKeyEx: Key = %s: Status = %d", v3, pszDest, *(_QWORD *)dwOptions);
    if ( !v7 )
    {
      if ( (a3 & 1) == 0
        || (v7 = ConvertGuidToStringW(a1 + 1040, Data, 39)) == 0
        && (LODWORD(samDesired) = RegSetValueExW(hKey, *(&IpTlsConfigSettings + 9 * v4 + 3), 0, 1u, Data, 0x4Eu),
            v7 = samDesired,
            EventWrite0(
              0x10000000,
              L"%s:RegSetValueEx:%s = %s: Status = %d",
              v3,
              *((_QWORD *)&IpTlsConfigSettings + 9 * v4 + 3),
              Data,
              samDesired),
            !v7) )
      {
        if ( (a3 & 2) == 0
          || (dwOptionsa[0] = RegSetValueExW(hKey, (&IpTlsConfigSettings)[9 * v4 + 2], 0, 3u, a1 + 32, 0x18u),
              v7 = dwOptionsa[0],
              EventWrite0(
                0x10000000,
                L"%s:RegSetValueEx:%s :Statis = %d",
                v3,
                (&IpTlsConfigSettings)[9 * v4 + 2],
                *(_QWORD *)dwOptionsa),
              !v7) )
        {
          if ( ((a3 & 4) == 0
             || (v7 = RegSetValueExW(hKey, *(&IpTlsConfigSettings + 9 * v4 + 5), 0, 4u, a1 + 1192, 4u)) == 0)
            && (a3 & 8) != 0 )
          {
            v7 = RegSetValueExW(hKey, (&IpTlsConfigSettings)[9 * v4 + 3], 0, 4u, a1 + 1196, 4u);
          }
        }
      }
    }
  }
  else
  {
    v7 = 122;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18004905c  push    rbp
0x18004905e  push    rbx
0x18004905f  push    rsi
0x180049060  push    rdi
0x180049061  push    r12
0x180049063  push    r14
0x180049065  push    r15
0x180049067  lea     rbp, [rsp-1D0h]
0x18004906f  sub     rsp, 2D0h
0x180049076  mov     rax, cs:__security_cookie
0x18004907d  xor     rax, rsp
0x180049080  mov     [rbp+200h+var_40], rax
0x180049087  lea     r15, [rcx+38h]
0x18004908b  movsxd  r12, edx
0x18004908e  movzx   ebx, r8w
0x180049092  mov     qword ptr [rsp+300h+dwOptions], r15
0x180049097  mov     r14, rcx
0x18004909a  mov     [rsp+300h+hKey], 0
0x1800490a3  lea     r8, aSS; "%s\\%s"
0x1800490aa  mov     edx, 105h; cchDest
0x1800490af  lea     rcx, [rbp+200h+pszDest]; pszDest
0x1800490b3  lea     r9, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\IP"...
0x1800490ba  call    StringCchPrintfW
0x1800490bf  test    eax, eax
0x1800490c1  jns     short loc_1800490CD
0x1800490c3  mov     esi, 7Ah ; 'z'
0x1800490c8  jmp     loc_1800492CC
0x1800490cd  mov     [rsp+300h+lpdwDisposition], 0; lpdwDisposition
0x1800490d6  lea     rax, [rsp+300h+hKey]
0x1800490db  mov     [rsp+300h+phkResult], rax; phkResult
0x1800490e0  lea     rdx, [rbp+200h+pszDest]; lpSubKey
0x1800490e4  mov     [rsp+300h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800490ed  xor     r9d, r9d; lpClass
0x1800490f0  mov     dword ptr [rsp+300h+samDesired], 2; samDesired
0x1800490f8  xor     r8d, r8d; Reserved
0x1800490fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049102  mov     [rsp+300h+dwOptions], 0; dwOptions
0x18004910a  call    cs:__imp_RegCreateKeyExW
0x180049111  nop     dword ptr [rax+rax+00h]
0x180049116  lea     r9, [rbp+200h+pszDest]
0x18004911a  mov     r8, r15
0x18004911d  lea     rdx, aSRegcreatekeye; "%s:RegCreateKeyEx: Key = %s: Status = %"...
0x180049124  mov     [rsp+300h+dwOptions], eax
0x180049128  mov     ecx, 10000000h
0x18004912d  mov     esi, eax
0x18004912f  call    EventWrite0
0x180049134  test    esi, esi
0x180049136  jnz     loc_1800492CC
0x18004913c  lea     rcx, IpTlsConfigSettings
0x180049143  test    bl, 1
0x180049146  jz      loc_1800491EB
0x18004914c  lea     rcx, [r14+410h]
0x180049153  lea     r8d, [rsi+27h]
0x180049157  lea     rdx, [rsp+300h+Data]
0x18004915c  call    cs:__imp_ConvertGuidToStringW
0x180049163  nop     dword ptr [rax+rax+00h]
0x180049168  mov     esi, eax
0x18004916a  test    eax, eax
0x18004916c  jnz     loc_1800492CC
0x180049172  mov     rcx, [rsp+300h+hKey]; hKey
0x180049177  lea     rax, [rsp+300h+Data]
0x18004917c  lea     rdi, [r12+r12*8]
0x180049180  mov     dword ptr [rsp+300h+samDesired], 4Eh ; 'N'; cbData
0x180049188  lea     rdx, IpTlsConfigSettings
0x18004918f  mov     qword ptr [rsp+300h+dwOptions], rax; lpData
0x180049194  mov     rdx, [rdx+rdi*8+18h]; lpValueName
0x180049199  lea     r9d, [rsi+1]; dwType
0x18004919d  xor     r8d, r8d; Reserved
0x1800491a0  call    cs:__imp_RegSetValueExW
0x1800491a7  nop     dword ptr [rax+rax+00h]
0x1800491ac  mov     dword ptr [rsp+300h+samDesired], eax
0x1800491b0  mov     r8, r15
0x1800491b3  mov     esi, eax
0x1800491b5  lea     rdx, aSRegsetvalueex_0; "%s:RegSetValueEx:%s = %s: Status = %d"
0x1800491bc  lea     rax, [rsp+300h+Data]
0x1800491c1  mov     ecx, 10000000h
0x1800491c6  mov     qword ptr [rsp+300h+dwOptions], rax
0x1800491cb  lea     rax, IpTlsConfigSettings
0x1800491d2  mov     r9, [rax+rdi*8+18h]
0x1800491d7  call    EventWrite0
0x1800491dc  test    esi, esi
0x1800491de  jnz     loc_1800492CC
0x1800491e4  lea     rcx, IpTlsConfigSettings
0x1800491eb  test    bl, 2
0x1800491ee  jz      short loc_18004924E
0x1800491f0  lea     rax, [r14+20h]
0x1800491f4  mov     dword ptr [rsp+300h+samDesired], 18h; cbData
0x1800491fc  lea     rdi, [r12+r12*8]
0x180049200  mov     qword ptr [rsp+300h+dwOptions], rax; lpData
0x180049205  mov     rdx, [rcx+rdi*8+20h]; lpValueName
0x18004920a  mov     r9d, 3; dwType
0x180049210  mov     rcx, [rsp+300h+hKey]; hKey
0x180049215  xor     r8d, r8d; Reserved
0x180049218  call    cs:__imp_RegSetValueExW
0x18004921f  nop     dword ptr [rax+rax+00h]
0x180049224  mov     [rsp+300h+dwOptions], eax
0x180049228  mov     r8, r15
0x18004922b  mov     esi, eax
0x18004922d  lea     rdx, aSRegsetvalueex; "%s:RegSetValueEx:%s :Statis = %d"
0x180049234  lea     rax, IpTlsConfigSettings
0x18004923b  mov     ecx, 10000000h
0x180049240  mov     r9, [rax+rdi*8+20h]
0x180049245  call    EventWrite0
0x18004924a  test    esi, esi
0x18004924c  jnz     short loc_1800492CC
0x18004924e  mov     edi, 4
0x180049253  lea     r15, IpTlsConfigSettings
0x18004925a  test    dil, bl
0x18004925d  jz      short loc_180049295
0x18004925f  lea     rcx, [r14+4A8h]
0x180049266  mov     dword ptr [rsp+300h+samDesired], edi; cbData
0x18004926a  mov     qword ptr [rsp+300h+dwOptions], rcx; lpData
0x18004926f  lea     rdx, [r12+r12*8]
0x180049273  mov     rcx, [rsp+300h+hKey]; hKey
0x180049278  mov     r9d, edi; dwType
0x18004927b  mov     rdx, [r15+rdx*8+28h]; lpValueName
0x180049280  xor     r8d, r8d; Reserved
0x180049283  call    cs:__imp_RegSetValueExW
0x18004928a  nop     dword ptr [rax+rax+00h]
0x18004928f  mov     esi, eax
0x180049291  test    eax, eax
0x180049293  jnz     short loc_1800492CC
0x180049295  test    bl, 8
0x180049298  jz      short loc_1800492CC
0x18004929a  lea     rcx, [r14+4ACh]
0x1800492a1  mov     dword ptr [rsp+300h+samDesired], edi; cbData
0x1800492a5  mov     qword ptr [rsp+300h+dwOptions], rcx; lpData
0x1800492aa  lea     rdx, [r12+r12*8]
0x1800492ae  mov     rcx, [rsp+300h+hKey]; hKey
0x1800492b3  mov     r9d, edi; dwType
0x1800492b6  mov     rdx, [r15+rdx*8+30h]; lpValueName
0x1800492bb  xor     r8d, r8d; Reserved
0x1800492be  call    cs:__imp_RegSetValueExW
0x1800492c5  nop     dword ptr [rax+rax+00h]
0x1800492ca  mov     esi, eax
0x1800492cc  mov     rcx, [rsp+300h+hKey]; hKey
0x1800492d1  test    rcx, rcx
0x1800492d4  jz      short loc_1800492E2
0x1800492d6  call    cs:__imp_RegCloseKey
0x1800492dd  nop     dword ptr [rax+rax+00h]
0x1800492e2  mov     eax, esi
0x1800492e4  mov     rcx, [rbp+200h+var_40]
0x1800492eb  xor     rcx, rsp; StackCookie
0x1800492ee  call    __security_check_cookie
0x1800492f3  add     rsp, 2D0h
0x1800492fa  pop     r15
0x1800492fc  pop     r14
0x1800492fe  pop     r12
0x180049300  pop     rdi
0x180049301  pop     rsi
0x180049302  pop     rbx
0x180049303  pop     rbp
0x180049304  retn
```
