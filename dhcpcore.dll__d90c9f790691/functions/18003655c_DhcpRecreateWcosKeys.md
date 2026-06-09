# DhcpRecreateWcosKeys

- ea: `0x18003655c`
- end: `0x18003667d`
- name: `DhcpRecreateWcosKeys`
- size: `289`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003619c`

## callees

- `0x18003655c`
- `0x18004d200`
- `0x18004d310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036656`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036656`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800365c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800365c9`

## pseudocode

```c
LSTATUS DhcpRecreateWcosKeys()
{
  __int64 v0; // rdi
  __int64 v1; // rbx
  LSTATUS result; // eax
  HKEY v3; // rcx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v0 = 0;
  dwDisposition = 0;
  v1 = 0;
  hKey = 0;
  do
  {
    result = RegCreateKeyExW(
               HKEY_LOCAL_MACHINE,
               (&off_180052A70)[v1],
               0,
               0,
               *((_DWORD *)&off_180052A70 + 2 * v1 + 2) != 0,
               0xF003Fu,
               0,
               &hKey,
               &dwDisposition);
    if ( result && (xmmword_1800616A0 & 2) != 0 )
      result = WPP_SF_SD(
                 1025,
                 15,
                 (unsigned int)WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids,
                 (unsigned int)(&off_180052A70)[v1],
                 result);
    if ( dwDisposition == 2 && (xmmword_1800616A0 & 0x10) != 0 )
      result = WPP_SF_S(1028, 16, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, (&off_180052A70)[v1]);
    v3 = hKey;
    if ( hKey )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        WPP_SF_S(1028, 17, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, (&off_180052A70)[v1]);
        v3 = hKey;
      }
      result = RegCloseKey(v3);
    }
    ++v0;
    v1 += 2;
  }
  while ( v0 != 7 );
  return result;
}

```

## disassembly

```asm
0x18003655c  mov     rax, rsp
0x18003655f  mov     [rax+18h], rbx
0x180036563  mov     [rax+20h], rbp
0x180036567  push    rdi
0x180036568  sub     rsp, 50h
0x18003656c  xor     edi, edi
0x18003656e  mov     dword ptr [rax+8], 0
0x180036575  xor     ebx, ebx
0x180036577  mov     qword ptr [rax+10h], 0
0x18003657f  lea     rbp, off_180052A70; "System\\CurrentControlSet\\Services\\Tc"...
0x180036586  mov     rdx, [rbx+rbp]; lpSubKey
0x18003658a  lea     rcx, [rsp+58h+dwDisposition]
0x18003658f  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180036594  xor     eax, eax
0x180036596  cmp     [rbx+rbp+8], eax
0x18003659a  lea     rcx, [rsp+58h+hKey]
0x18003659f  mov     [rsp+58h+phkResult], rcx; phkResult
0x1800365a4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800365ab  setnz   al
0x1800365ae  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800365b7  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800365bf  xor     r9d, r9d; lpClass
0x1800365c2  xor     r8d, r8d; Reserved
0x1800365c5  mov     [rsp+58h+dwOptions], eax; dwOptions
0x1800365c9  call    cs:__imp_RegCreateKeyExW
0x1800365cf  test    eax, eax
0x1800365d1  jz      short loc_1800365FA
0x1800365d3  test    byte ptr cs:xmmword_1800616A0, 2
0x1800365da  jz      short loc_1800365FA
0x1800365dc  mov     r9, [rbx+rbp]
0x1800365e0  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800365e7  mov     edx, 0Fh
0x1800365ec  mov     [rsp+58h+dwOptions], eax
0x1800365f0  mov     ecx, 401h
0x1800365f5  call    WPP_SF_SD
0x1800365fa  cmp     [rsp+58h+dwDisposition], 2
0x1800365ff  jnz     short loc_180036624
0x180036601  test    byte ptr cs:xmmword_1800616A0, 10h
0x180036608  jz      short loc_180036624
0x18003660a  mov     r9, [rbx+rbp]
0x18003660e  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180036615  mov     edx, 10h
0x18003661a  mov     ecx, 404h
0x18003661f  call    WPP_SF_S
0x180036624  mov     rcx, [rsp+58h+hKey]
0x180036629  test    rcx, rcx
0x18003662c  jz      short loc_18003665C
0x18003662e  test    byte ptr cs:xmmword_1800616A0, 10h
0x180036635  jz      short loc_180036656
0x180036637  mov     r9, [rbx+rbp]
0x18003663b  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180036642  mov     edx, 11h
0x180036647  mov     ecx, 404h
0x18003664c  call    WPP_SF_S
0x180036651  mov     rcx, [rsp+58h+hKey]; hKey
0x180036656  call    cs:__imp_RegCloseKey
0x18003665c  inc     rdi
0x18003665f  add     rbx, 10h
0x180036663  cmp     rdi, 7
0x180036667  jnz     loc_180036586
0x18003666d  mov     rbx, [rsp+58h+arg_10]
0x180036672  mov     rbp, [rsp+58h+arg_18]
0x180036677  add     rsp, 50h
0x18003667b  pop     rdi
0x18003667c  retn
```
