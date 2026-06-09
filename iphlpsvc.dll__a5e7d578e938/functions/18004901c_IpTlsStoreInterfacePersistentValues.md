# IpTlsStoreInterfacePersistentValues

- ea: `0x18004901c`
- end: `0x1800492c6`
- name: `IpTlsStoreInterfacePersistentValues`
- size: `682`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180003cf4`
- `0x1800311e0`
- `0x18003588c`
- `0x180047cfc`
- `0x180048a0c`
- `0x1800492cc`
- `0x18005fabc`
- `0x180061540`
- `0x1800632a0`
- `0x1800678bc`
- `0x180068208`

## callees

- `0x18000d7c0`
- `0x180034744`
- `0x18004901c`
- `0x18004b5f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049296`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180049296`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049160`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800491d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049243`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004927e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049160`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800491d8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180049243`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004927e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800490ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800490ca`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18004911c`
- `IPHLPAPI!ConvertGuidToStringW` at `0x18004911c`

## string_xrefs

- `0x180049073`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\IPHTTPS`
- `0x1800490dd`: `%s:RegCreateKeyEx: Key = %s: Status = %d`
- `0x180049175`: `%s:RegSetValueEx:%s = %s: Status = %d`
- `0x1800491ed`: `%s:RegSetValueEx:%s :Statis = %d`

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
0x18004901c  push    rbp
0x18004901e  push    rbx
0x18004901f  push    rsi
0x180049020  push    rdi
0x180049021  push    r12
0x180049023  push    r14
0x180049025  push    r15
0x180049027  lea     rbp, [rsp-1D0h]
0x18004902f  sub     rsp, 2D0h
0x180049036  mov     rax, cs:__security_cookie
0x18004903d  xor     rax, rsp
0x180049040  mov     [rbp+200h+var_40], rax
0x180049047  lea     r15, [rcx+38h]
0x18004904b  movsxd  r12, edx
0x18004904e  movzx   ebx, r8w
0x180049052  mov     qword ptr [rsp+300h+dwOptions], r15
0x180049057  mov     r14, rcx
0x18004905a  mov     [rsp+300h+hKey], 0
0x180049063  lea     r8, aSS; "%s\\%s"
0x18004906a  mov     edx, 105h; cchDest
0x18004906f  lea     rcx, [rbp+200h+pszDest]; pszDest
0x180049073  lea     r9, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\IP"...
0x18004907a  call    StringCchPrintfW
0x18004907f  test    eax, eax
0x180049081  jns     short loc_18004908D
0x180049083  mov     esi, 7Ah ; 'z'
0x180049088  jmp     loc_18004928C
0x18004908d  mov     [rsp+300h+lpdwDisposition], 0; lpdwDisposition
0x180049096  lea     rax, [rsp+300h+hKey]
0x18004909b  mov     [rsp+300h+phkResult], rax; phkResult
0x1800490a0  lea     rdx, [rbp+200h+pszDest]; lpSubKey
0x1800490a4  mov     [rsp+300h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800490ad  xor     r9d, r9d; lpClass
0x1800490b0  mov     dword ptr [rsp+300h+samDesired], 2; samDesired
0x1800490b8  xor     r8d, r8d; Reserved
0x1800490bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800490c2  mov     [rsp+300h+dwOptions], 0; dwOptions
0x1800490ca  call    cs:__imp_RegCreateKeyExW
0x1800490d1  nop     dword ptr [rax+rax+00h]
0x1800490d6  lea     r9, [rbp+200h+pszDest]
0x1800490da  mov     r8, r15
0x1800490dd  lea     rdx, aSRegcreatekeye; "%s:RegCreateKeyEx: Key = %s: Status = %"...
0x1800490e4  mov     [rsp+300h+dwOptions], eax
0x1800490e8  mov     ecx, 10000000h
0x1800490ed  mov     esi, eax
0x1800490ef  call    EventWrite0
0x1800490f4  test    esi, esi
0x1800490f6  jnz     loc_18004928C
0x1800490fc  lea     rcx, IpTlsConfigSettings
0x180049103  test    bl, 1
0x180049106  jz      loc_1800491AB
0x18004910c  lea     rcx, [r14+410h]
0x180049113  lea     r8d, [rsi+27h]
0x180049117  lea     rdx, [rsp+300h+Data]
0x18004911c  call    cs:__imp_ConvertGuidToStringW
0x180049123  nop     dword ptr [rax+rax+00h]
0x180049128  mov     esi, eax
0x18004912a  test    eax, eax
0x18004912c  jnz     loc_18004928C
0x180049132  mov     rcx, [rsp+300h+hKey]; hKey
0x180049137  lea     rax, [rsp+300h+Data]
0x18004913c  lea     rdi, [r12+r12*8]
0x180049140  mov     dword ptr [rsp+300h+samDesired], 4Eh ; 'N'; cbData
0x180049148  lea     rdx, IpTlsConfigSettings
0x18004914f  mov     qword ptr [rsp+300h+dwOptions], rax; lpData
0x180049154  mov     rdx, [rdx+rdi*8+18h]; lpValueName
0x180049159  lea     r9d, [rsi+1]; dwType
0x18004915d  xor     r8d, r8d; Reserved
0x180049160  call    cs:__imp_RegSetValueExW
0x180049167  nop     dword ptr [rax+rax+00h]
0x18004916c  mov     dword ptr [rsp+300h+samDesired], eax
0x180049170  mov     r8, r15
0x180049173  mov     esi, eax
0x180049175  lea     rdx, aSRegsetvalueex_0; "%s:RegSetValueEx:%s = %s: Status = %d"
0x18004917c  lea     rax, [rsp+300h+Data]
0x180049181  mov     ecx, 10000000h
0x180049186  mov     qword ptr [rsp+300h+dwOptions], rax
0x18004918b  lea     rax, IpTlsConfigSettings
0x180049192  mov     r9, [rax+rdi*8+18h]
0x180049197  call    EventWrite0
0x18004919c  test    esi, esi
0x18004919e  jnz     loc_18004928C
0x1800491a4  lea     rcx, IpTlsConfigSettings
0x1800491ab  test    bl, 2
0x1800491ae  jz      short loc_18004920E
0x1800491b0  lea     rax, [r14+20h]
0x1800491b4  mov     dword ptr [rsp+300h+samDesired], 18h; cbData
0x1800491bc  lea     rdi, [r12+r12*8]
0x1800491c0  mov     qword ptr [rsp+300h+dwOptions], rax; lpData
0x1800491c5  mov     rdx, [rcx+rdi*8+20h]; lpValueName
0x1800491ca  mov     r9d, 3; dwType
0x1800491d0  mov     rcx, [rsp+300h+hKey]; hKey
0x1800491d5  xor     r8d, r8d; Reserved
0x1800491d8  call    cs:__imp_RegSetValueExW
0x1800491df  nop     dword ptr [rax+rax+00h]
0x1800491e4  mov     [rsp+300h+dwOptions], eax
0x1800491e8  mov     r8, r15
0x1800491eb  mov     esi, eax
0x1800491ed  lea     rdx, aSRegsetvalueex; "%s:RegSetValueEx:%s :Statis = %d"
0x1800491f4  lea     rax, IpTlsConfigSettings
0x1800491fb  mov     ecx, 10000000h
0x180049200  mov     r9, [rax+rdi*8+20h]
0x180049205  call    EventWrite0
0x18004920a  test    esi, esi
0x18004920c  jnz     short loc_18004928C
0x18004920e  mov     edi, 4
0x180049213  lea     r15, IpTlsConfigSettings
0x18004921a  test    dil, bl
0x18004921d  jz      short loc_180049255
0x18004921f  lea     rcx, [r14+4A8h]
0x180049226  mov     dword ptr [rsp+300h+samDesired], edi; cbData
0x18004922a  mov     qword ptr [rsp+300h+dwOptions], rcx; lpData
0x18004922f  lea     rdx, [r12+r12*8]
0x180049233  mov     rcx, [rsp+300h+hKey]; hKey
0x180049238  mov     r9d, edi; dwType
0x18004923b  mov     rdx, [r15+rdx*8+28h]; lpValueName
0x180049240  xor     r8d, r8d; Reserved
0x180049243  call    cs:__imp_RegSetValueExW
0x18004924a  nop     dword ptr [rax+rax+00h]
0x18004924f  mov     esi, eax
0x180049251  test    eax, eax
0x180049253  jnz     short loc_18004928C
0x180049255  test    bl, 8
0x180049258  jz      short loc_18004928C
0x18004925a  lea     rcx, [r14+4ACh]
0x180049261  mov     dword ptr [rsp+300h+samDesired], edi; cbData
0x180049265  mov     qword ptr [rsp+300h+dwOptions], rcx; lpData
0x18004926a  lea     rdx, [r12+r12*8]
0x18004926e  mov     rcx, [rsp+300h+hKey]; hKey
0x180049273  mov     r9d, edi; dwType
0x180049276  mov     rdx, [r15+rdx*8+30h]; lpValueName
0x18004927b  xor     r8d, r8d; Reserved
0x18004927e  call    cs:__imp_RegSetValueExW
0x180049285  nop     dword ptr [rax+rax+00h]
0x18004928a  mov     esi, eax
0x18004928c  mov     rcx, [rsp+300h+hKey]; hKey
0x180049291  test    rcx, rcx
0x180049294  jz      short loc_1800492A2
0x180049296  call    cs:__imp_RegCloseKey
0x18004929d  nop     dword ptr [rax+rax+00h]
0x1800492a2  mov     eax, esi
0x1800492a4  mov     rcx, [rbp+200h+var_40]
0x1800492ab  xor     rcx, rsp; StackCookie
0x1800492ae  call    __security_check_cookie
0x1800492b3  add     rsp, 2D0h
0x1800492ba  pop     r15
0x1800492bc  pop     r14
0x1800492be  pop     r12
0x1800492c0  pop     rdi
0x1800492c1  pop     rsi
0x1800492c2  pop     rbx
0x1800492c3  pop     rbp
0x1800492c4  retn
```
