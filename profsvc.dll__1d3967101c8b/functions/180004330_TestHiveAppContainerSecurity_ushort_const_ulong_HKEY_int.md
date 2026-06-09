# TestHiveAppContainerSecurity_(ushort const * *,ulong,HKEY__ *,int)

- ea: `0x180004330`
- end: `0x18000451f`
- name: `?TestHiveAppContainerSecurity_@@YAHPEAPEBGKPEAUHKEY__@@H@Z`
- size: `495`
- prototype: `int(const unsigned __int16 **, unsigned int, HKEY, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800350cc`

## callees

- `0x180004330`
- `0x180004530`
- `0x180004690`
- `0x180004ff4`
- `0x18003e8fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004372`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004372`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004448`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004448`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000435b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000443a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000435b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000443a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800043bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800043bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004408`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800043e2`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800044b0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800043e2`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800044b0`

## pseudocode

```c
_BOOL8 __fastcall TestHiveAppContainerSecurity_(const unsigned __int16 **a1, unsigned int a2, HKEY a3, int a4)
{
  HANDLE ProcessHeap; // rax
  DWORD v9; // r12d
  __int64 v10; // rsi
  void *v11; // r14
  LSTATUS v12; // eax
  bool v13; // sf
  LSTATUS KeySecurity; // eax
  signed int v15; // ebx
  HANDLE v17; // rax
  LSTATUS v19; // eax
  DWORD v20; // ecx
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  ProcessHeap = GetProcessHeap();
  v9 = 256;
  v10 = 0;
  v11 = HeapAlloc(ProcessHeap, 8u, 0x100u);
  if ( v11 )
  {
    if ( !a2 )
      goto LABEL_17;
    do
    {
      v12 = RegOpenKeyExW(a3, a1[v10], 0, 0x20000u, &hKey);
      v13 = v12 < 0;
      if ( v12 > 0 )
        v13 = 1;
      if ( v13 )
        break;
      cbSecurityDescriptor = v9;
      KeySecurity = RegGetKeySecurity(hKey, 4u, v11, &cbSecurityDescriptor);
      v15 = KeySecurity;
      if ( KeySecurity > 0 )
        v15 = (unsigned __int16)KeySecurity | 0x80070000;
      if ( v15 == -2147024774 )
      {
        v20 = 2 * cbSecurityDescriptor;
        if ( 2 * cbSecurityDescriptor <= cbSecurityDescriptor )
        {
          v15 = -2147024362;
        }
        else
        {
          cbSecurityDescriptor *= 2;
          pSecurityDescriptor = 0;
          v15 = ResultFromHeapReAlloc(v11, v20, &pSecurityDescriptor);
          if ( v15 >= 0 )
          {
            v11 = pSecurityDescriptor;
            v9 = cbSecurityDescriptor;
            v19 = RegGetKeySecurity(hKey, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
            v15 = v19;
            if ( v19 > 0 )
              v15 = (unsigned __int16)v19 | 0x80070000;
          }
        }
      }
      if ( hKey != a3 )
        RegCloseKey(hKey);
      if ( v15 < 0 )
        break;
      if ( !(a4 ? DaclContainsPackageAndLpacCapabilitySid_(v11) : (unsigned int)DaclContainsPackageSid_(v11)) )
        break;
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < a2 );
    if ( v11 )
    {
LABEL_17:
      v17 = GetProcessHeap();
      if ( !HeapFree(v17, 0, v11) )
        ResultFromKnownLastError();
    }
  }
  return (_DWORD)v10 == a2;
}

```

## disassembly

```asm
0x180004330  mov     [rsp+arg_10], rbp
0x180004335  mov     [rsp+arg_18], rsi
0x18000433a  push    rdi
0x18000433b  push    r12
0x18000433d  push    r13
0x18000433f  push    r14
0x180004341  push    r15
0x180004343  sub     rsp, 40h
0x180004347  mov     edi, r9d
0x18000434a  mov     [rsp+68h+hKey], 0
0x180004353  mov     r15, r8
0x180004356  mov     ebp, edx
0x180004358  mov     r13, rcx
0x18000435b  call    cs:__imp_GetProcessHeap
0x180004361  mov     r12d, 100h
0x180004367  mov     edx, 8; dwFlags
0x18000436c  mov     rcx, rax; hHeap
0x18000436f  mov     r8d, r12d; dwBytes
0x180004372  call    cs:__imp_HeapAlloc
0x180004378  xor     esi, esi
0x18000437a  mov     r14, rax
0x18000437d  test    rax, rax
0x180004380  jz      loc_180004456
0x180004386  test    ebp, ebp
0x180004388  jz      loc_18000443A
0x18000438e  mov     [rsp+68h+arg_0], rbx
0x180004393  nop     dword ptr [rax+00h]
0x180004397  nop     word ptr [rax+rax+00000000h]
0x1800043a0  mov     rdx, [r13+rsi*8+0]; lpSubKey
0x1800043a5  lea     rax, [rsp+68h+hKey]
0x1800043aa  mov     r9d, 20000h; samDesired
0x1800043b0  mov     [rsp+68h+phkResult], rax; phkResult
0x1800043b5  xor     r8d, r8d; ulOptions
0x1800043b8  mov     rcx, r15; hKey
0x1800043bb  call    cs:__imp_RegOpenKeyExW
0x1800043c1  test    eax, eax
0x1800043c3  jg      loc_180004477
0x1800043c9  js      short loc_180004430
0x1800043cb  mov     rcx, [rsp+68h+hKey]; hKey
0x1800043d0  lea     r9, [rsp+68h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800043d5  mov     r8, r14; pSecurityDescriptor
0x1800043d8  mov     [rsp+68h+cbSecurityDescriptor], r12d
0x1800043dd  mov     edx, 4; SecurityInformation
0x1800043e2  call    cs:__imp_RegGetKeySecurity
0x1800043e8  mov     ebx, eax
0x1800043ea  test    eax, eax
0x1800043ec  jg      loc_180004486
0x1800043f2  cmp     ebx, 8007007Ah
0x1800043f8  jz      loc_1800044CE
0x1800043fe  mov     rcx, [rsp+68h+hKey]; hKey
0x180004403  cmp     rcx, r15
0x180004406  jz      short loc_18000440E
0x180004408  call    cs:__imp_RegCloseKey
0x18000440e  test    ebx, ebx
0x180004410  js      short loc_180004430
0x180004412  mov     rcx, r14; void *
0x180004415  test    edi, edi
0x180004417  jnz     loc_18000450B
0x18000441d  call    ?DaclContainsPackageSid_@@YAHPEAX@Z; DaclContainsPackageSid_(void *)
0x180004422  test    eax, eax
0x180004424  jz      short loc_180004430
0x180004426  inc     esi
0x180004428  cmp     esi, ebp
0x18000442a  jb      loc_1800043A0
0x180004430  mov     rbx, [rsp+68h+arg_0]
0x180004435  test    r14, r14
0x180004438  jz      short loc_180004456
0x18000443a  call    cs:__imp_GetProcessHeap
0x180004440  mov     r8, r14; lpMem
0x180004443  xor     edx, edx; dwFlags
0x180004445  mov     rcx, rax; hHeap
0x180004448  call    cs:__imp_HeapFree
0x18000444e  test    eax, eax
0x180004450  jz      loc_180004515
0x180004456  xor     eax, eax
0x180004458  lea     r11, [rsp+68h+var_28]
0x18000445d  cmp     esi, ebp
0x18000445f  mov     rbp, [r11+40h]
0x180004463  mov     rsi, [r11+48h]
0x180004467  setz    al
0x18000446a  mov     rsp, r11
0x18000446d  pop     r15
0x18000446f  pop     r14
0x180004471  pop     r13
0x180004473  pop     r12
0x180004475  pop     rdi
0x180004476  retn
0x180004477  movzx   eax, ax
0x18000447a  or      eax, 80070000h
0x18000447f  test    eax, eax
0x180004481  jmp     loc_1800043C9
0x180004486  movzx   ebx, ax
0x180004489  or      ebx, 80070000h
0x18000448f  jmp     loc_1800043F2
0x180004494  mov     r14, [rsp+68h+pSecurityDescriptor]
0x180004499  lea     r9, [rsp+68h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000449e  mov     rcx, [rsp+68h+hKey]; hKey
0x1800044a3  mov     r8, r14; pSecurityDescriptor
0x1800044a6  mov     r12d, [rsp+68h+cbSecurityDescriptor]
0x1800044ab  mov     edx, 4; SecurityInformation
0x1800044b0  call    cs:__imp_RegGetKeySecurity
0x1800044b6  mov     ebx, eax
0x1800044b8  test    eax, eax
0x1800044ba  jle     loc_1800043FE
0x1800044c0  movzx   ebx, ax
0x1800044c3  or      ebx, 80070000h
0x1800044c9  jmp     loc_1800043FE
0x1800044ce  mov     eax, [rsp+68h+cbSecurityDescriptor]
0x1800044d2  lea     ecx, [rax+rax]
0x1800044d5  cmp     ecx, eax
0x1800044d7  jbe     short loc_180004501
0x1800044d9  mov     [rsp+68h+cbSecurityDescriptor], ecx
0x1800044dd  lea     r8, [rsp+68h+pSecurityDescriptor]; void **
0x1800044e2  mov     edx, ecx; dwBytes
0x1800044e4  mov     rcx, r14; lpMem
0x1800044e7  mov     [rsp+68h+pSecurityDescriptor], 0
0x1800044f0  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x1800044f5  mov     ebx, eax
0x1800044f7  test    eax, eax
0x1800044f9  js      loc_1800043FE
0x1800044ff  jmp     short loc_180004494
0x180004501  mov     ebx, 80070216h
0x180004506  jmp     loc_1800043FE
0x18000450b  call    ?DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z; DaclContainsPackageAndLpacCapabilitySid_(void *)
0x180004510  jmp     loc_180004422
0x180004515  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000451a  jmp     loc_180004456
```
