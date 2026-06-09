# DhcpRegistryCreateUniqueKey

- ea: `0x1800042d4`
- end: `0x1800044c5`
- name: `DhcpRegistryCreateUniqueKey`
- size: `497`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH psz, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180009920`

## callees

- `0x180001f90`
- `0x180002160`
- `0x180002c00`
- `0x180003110`
- `0x180003210`
- `0x1800042d4`
- `0x18000d440`
- `0x180011894`
- `0x180012a00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000445f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000445f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004474`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004474`

## string_xrefs

- `0x180004329`: `System\CurrentControlSet\Services\Dhcp\Parameters\Options`
- `0x1800043fb`: `System\CurrentControlSet\Services\Dhcp\Parameters\Options`

## pseudocode

```c
__int64 __fastcall DhcpRegistryCreateUniqueKey(STRSAFE_PCNZWCH psz, PHKEY phkResult, int a3)
{
  int IsWCOSSystem; // eax
  const wchar_t *v6; // r12
  const wchar_t *v7; // rcx
  HRESULT v8; // eax
  int v9; // r15d
  size_t v10; // rdx
  unsigned int v11; // ebx
  HRESULT v12; // eax
  int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // r8
  size_t v16; // rbx
  __int64 v17; // rcx
  wchar_t *v18; // rsi
  unsigned int v19; // eax
  size_t pcbLength; // [rsp+50h] [rbp-10h] BYREF
  __int64 v22; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+48h] BYREF

  dwDisposition = 0;
  v22 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Sq((_DWORD)psz, 95, a3, (char)psz);
  IsWCOSSystem = DhcpIsWCOSSystem(psz);
  pcbLength = 0;
  v6 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  v7 = L"OSDATA\\Networking\\Dhcp\\Client4\\Parameters\\Options";
  if ( !IsWCOSSystem )
    v7 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
  v8 = StringCbLengthW(v7, (size_t)L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options", &pcbLength);
  if ( v8 >= 0 )
  {
    v9 = pcbLength;
  }
  else
  {
    v9 = 0;
    HIDWORD(pcbLength) = 108;
  }
  v11 = WX_WIN32_FROM_HR((unsigned int)v8);
  if ( !v11 )
  {
    pcbLength = 0;
    if ( psz )
    {
      v12 = StringCbLengthW(psz, v10, &pcbLength);
      if ( v12 >= 0 )
      {
        v13 = pcbLength;
LABEL_15:
        v11 = WX_WIN32_FROM_HR((unsigned int)v12);
        if ( !v11 )
        {
          v16 = (unsigned int)(v9 + v13 + 4);
          v22 = DhcpAlloc(v16, v14, v15);
          v18 = (wchar_t *)v22;
          if ( v22 )
          {
            if ( !(unsigned int)DhcpIsWCOSSystem(v17) )
              v6 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\Options";
            v19 = StringCbPrintfW(v18, v16, L"%s\\%s", v6, psz);
            v11 = WX_WIN32_FROM_HR(v19);
            if ( !v11 )
            {
              v11 = RegCreateKeyExW(
                      HKEY_LOCAL_MACHINE,
                      v18,
                      0,
                      (LPWSTR)L"DhcpClientClass",
                      0,
                      0xF003Fu,
                      0,
                      phkResult,
                      &dwDisposition);
              if ( !v11 && dwDisposition == 2 )
              {
                RegCloseKey(*phkResult);
                v11 = 183;
              }
            }
          }
          else
          {
            v11 = 8;
          }
        }
        goto LABEL_24;
      }
      HIDWORD(pcbLength) = 108;
    }
    else
    {
      v12 = -2147024809;
      HIDWORD(pcbLength) = 104;
    }
    v13 = 0;
    goto LABEL_15;
  }
LABEL_24:
  DhcpFree(&v22);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 96, WPP_e15037783097355a5233924022d92169_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800042d4  mov     [rsp-28h+arg_0], rbx
0x1800042d9  mov     [rsp-28h+arg_8], rsi
0x1800042de  push    rbp
0x1800042df  push    rdi
0x1800042e0  push    r12
0x1800042e2  push    r14
0x1800042e4  push    r15
0x1800042e6  mov     rbp, rsp
0x1800042e9  sub     rsp, 60h
0x1800042ed  mov     r14, rdx
0x1800042f0  mov     [rbp+dwDisposition], 0
0x1800042f7  mov     rdi, rcx
0x1800042fa  mov     [rbp+var_8], 0
0x180004302  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180004309  jz      short loc_18000431D
0x18000430b  mov     edx, 5Fh ; '_'
0x180004310  mov     qword ptr [rsp+60h+dwOptions], r14
0x180004315  mov     r9, rcx
0x180004318  call    WPP_SF_Sq
0x18000431d  call    DhcpIsWCOSSystem
0x180004322  mov     dword ptr [rbp+pcbLength+4], 0
0x180004329  lea     rdx, psz; "System\\CurrentControlSet\\Services\\Dh"...
0x180004330  test    eax, eax
0x180004332  mov     [rbp+pcbLength], 0
0x18000433a  lea     r12, aOsdataNetworki_1; "OSDATA\\Networking\\Dhcp\\Client4\\Para"...
0x180004341  mov     [rbp+arg_10], 0
0x180004348  mov     rcx, r12
0x18000434b  lea     r8, [rbp+pcbLength]; pcbLength
0x18000434f  cmovz   rcx, rdx; psz
0x180004353  call    StringCbLengthW
0x180004358  mov     esi, 6Ch ; 'l'
0x18000435d  test    eax, eax
0x18000435f  jns     short loc_18000436A
0x180004361  mov     r15d, [rbp+arg_10]
0x180004365  mov     dword ptr [rbp+pcbLength+4], esi
0x180004368  jmp     short loc_18000436E
0x18000436a  mov     r15d, dword ptr [rbp+pcbLength]
0x18000436e  mov     ecx, eax
0x180004370  call    WX_WIN32_FROM_HR
0x180004375  mov     ebx, eax
0x180004377  test    eax, eax
0x180004379  jnz     loc_18000447F
0x18000437f  mov     dword ptr [rbp+pcbLength+4], eax
0x180004382  mov     [rbp+pcbLength], 0
0x18000438a  mov     [rbp+arg_10], eax
0x18000438d  test    rdi, rdi
0x180004390  jnz     short loc_1800043A3
0x180004392  mov     eax, 80070057h
0x180004397  mov     dword ptr [rbp+pcbLength+4], 68h ; 'h'
0x18000439e  mov     esi, [rbp+arg_10]
0x1800043a1  jmp     short loc_1800043BB
0x1800043a3  lea     r8, [rbp+pcbLength]; pcbLength
0x1800043a7  mov     rcx, rdi; psz
0x1800043aa  call    StringCbLengthW
0x1800043af  test    eax, eax
0x1800043b1  jns     short loc_1800043B8
0x1800043b3  mov     dword ptr [rbp+pcbLength+4], esi
0x1800043b6  jmp     short loc_18000439E
0x1800043b8  mov     esi, dword ptr [rbp+pcbLength]
0x1800043bb  mov     ecx, eax
0x1800043bd  call    WX_WIN32_FROM_HR
0x1800043c2  mov     ebx, eax
0x1800043c4  test    eax, eax
0x1800043c6  jnz     loc_18000447F
0x1800043cc  lea     eax, [rsi+4]
0x1800043cf  add     eax, r15d
0x1800043d2  mov     ecx, eax
0x1800043d4  mov     ebx, eax
0x1800043d6  call    DhcpAlloc
0x1800043db  mov     [rbp+var_8], rax
0x1800043df  mov     rsi, rax
0x1800043e2  test    rax, rax
0x1800043e5  jnz     short loc_1800043EF
0x1800043e7  lea     ebx, [rax+8]
0x1800043ea  jmp     loc_18000447F
0x1800043ef  call    DhcpIsWCOSSystem
0x1800043f4  test    eax, eax
0x1800043f6  mov     qword ptr [rsp+60h+dwOptions], rdi
0x1800043fb  lea     rax, psz; "System\\CurrentControlSet\\Services\\Dh"...
0x180004402  mov     rdx, rbx; cbDest
0x180004405  cmovz   r12, rax
0x180004409  lea     r8, aSS_0; "%s\\%s"
0x180004410  mov     r9, r12
0x180004413  mov     rcx, rsi; pszDest
0x180004416  call    StringCbPrintfW
0x18000441b  mov     ecx, eax
0x18000441d  call    WX_WIN32_FROM_HR
0x180004422  mov     ebx, eax
0x180004424  test    eax, eax
0x180004426  jnz     short loc_18000447F
0x180004428  lea     rax, [rbp+dwDisposition]
0x18000442c  xor     r8d, r8d; Reserved
0x18000442f  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180004434  lea     r9, Class; "DhcpClientClass"
0x18000443b  mov     [rsp+60h+phkResult], r14; phkResult
0x180004440  mov     rdx, rsi; lpSubKey
0x180004443  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000444c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004453  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000445b  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x18000445f  call    cs:__imp_RegCreateKeyExW
0x180004465  mov     ebx, eax
0x180004467  test    eax, eax
0x180004469  jnz     short loc_18000447F
0x18000446b  cmp     [rbp+dwDisposition], 2
0x18000446f  jnz     short loc_18000447F
0x180004471  mov     rcx, [r14]; hKey
0x180004474  call    cs:__imp_RegCloseKey
0x18000447a  mov     ebx, 0B7h
0x18000447f  lea     rcx, [rbp+var_8]
0x180004483  call    DhcpFree
0x180004488  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000448f  jz      short loc_1800044AA
0x180004491  mov     edx, 60h ; '`'
0x180004496  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000449d  mov     ecx, 404h
0x1800044a2  mov     r9d, ebx
0x1800044a5  call    WPP_SF_d
0x1800044aa  lea     r11, [rsp+60h+var_s0]
0x1800044af  mov     eax, ebx
0x1800044b1  mov     rbx, [r11+30h]
0x1800044b5  mov     rsi, [r11+38h]
0x1800044b9  mov     rsp, r11
0x1800044bc  pop     r15
0x1800044be  pop     r14
0x1800044c0  pop     r12
0x1800044c2  pop     rdi
0x1800044c3  pop     rbp
0x1800044c4  retn
```
