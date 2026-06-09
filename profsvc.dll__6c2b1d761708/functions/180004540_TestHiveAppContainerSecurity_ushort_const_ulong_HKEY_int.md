# TestHiveAppContainerSecurity_(ushort const * *,ulong,HKEY__ *,int)

- ea: `0x180004540`
- end: `0x180004725`
- name: `?TestHiveAppContainerSecurity_@@YAHPEAPEBGKPEAUHKEY__@@H@Z`
- size: `485`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 **, unsigned int, HKEY, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800358a0`

## callees

- `0x180003754`
- `0x180003850`
- `0x180004540`
- `0x180005370`
- `0x18003fff4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004588`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000456b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000456b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800045cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004624`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004624`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800045f8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800046ba`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800045f8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800046ba`

## pseudocode

```c
_BOOL8 __fastcall TestHiveAppContainerSecurity_(const unsigned __int16 **a1, unsigned int a2, HKEY a3, int a4)
{
  HANDLE ProcessHeap; // rax
  DWORD v9; // r12d
  __int64 v10; // rdi
  void *v11; // r14
  LSTATUS v12; // eax
  bool v13; // sf
  LSTATUS KeySecurity; // eax
  signed int v15; // ebx
  LSTATUS v18; // eax
  DWORD v19; // ecx
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
    if ( a2 )
    {
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
          v19 = 2 * cbSecurityDescriptor;
          if ( 2 * cbSecurityDescriptor <= cbSecurityDescriptor )
          {
            v15 = -2147024362;
          }
          else
          {
            cbSecurityDescriptor *= 2;
            pSecurityDescriptor = 0;
            v15 = ResultFromHeapReAlloc(v11, v19, &pSecurityDescriptor);
            if ( v15 >= 0 )
            {
              v11 = pSecurityDescriptor;
              v9 = cbSecurityDescriptor;
              v18 = RegGetKeySecurity(hKey, 4u, pSecurityDescriptor, &cbSecurityDescriptor);
              v15 = v18;
              if ( v18 > 0 )
                v15 = (unsigned __int16)v18 | 0x80070000;
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
    }
    ResultFromHeapFree(v11);
  }
  return (_DWORD)v10 == a2;
}

```

## disassembly

```asm
0x180004540  mov     [rsp+arg_10], rbp
0x180004545  mov     [rsp+arg_18], rsi
0x18000454a  push    rdi
0x18000454b  push    r12
0x18000454d  push    r13
0x18000454f  push    r14
0x180004551  push    r15
0x180004553  sub     rsp, 40h
0x180004557  mov     esi, r9d
0x18000455a  mov     [rsp+68h+hKey], 0
0x180004563  mov     r15, r8
0x180004566  mov     ebp, edx
0x180004568  mov     r13, rcx
0x18000456b  call    cs:__imp_GetProcessHeap
0x180004572  nop     dword ptr [rax+rax+00h]
0x180004577  mov     r12d, 100h
0x18000457d  mov     edx, 8; dwFlags
0x180004582  mov     rcx, rax; hHeap
0x180004585  mov     r8d, r12d; dwBytes
0x180004588  call    cs:__imp_HeapAlloc
0x18000458f  nop     dword ptr [rax+rax+00h]
0x180004594  xor     edi, edi
0x180004596  mov     r14, rax
0x180004599  test    rax, rax
0x18000459c  jz      loc_18000465F
0x1800045a2  test    ebp, ebp
0x1800045a4  jz      loc_180004657
0x1800045aa  mov     [rsp+68h+arg_0], rbx
0x1800045af  nop
0x1800045b0  mov     rdx, [r13+rdi*8+0]; lpSubKey
0x1800045b5  lea     rax, [rsp+68h+hKey]
0x1800045ba  mov     r9d, 20000h; samDesired
0x1800045c0  mov     [rsp+68h+phkResult], rax; phkResult
0x1800045c5  xor     r8d, r8d; ulOptions
0x1800045c8  mov     rcx, r15; hKey
0x1800045cb  call    cs:__imp_RegOpenKeyExW
0x1800045d2  nop     dword ptr [rax+rax+00h]
0x1800045d7  test    eax, eax
0x1800045d9  jg      loc_180004681
0x1800045df  js      short loc_180004652
0x1800045e1  mov     rcx, [rsp+68h+hKey]; hKey
0x1800045e6  lea     r9, [rsp+68h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800045eb  mov     r8, r14; pSecurityDescriptor
0x1800045ee  mov     [rsp+68h+cbSecurityDescriptor], r12d
0x1800045f3  mov     edx, 4; SecurityInformation
0x1800045f8  call    cs:__imp_RegGetKeySecurity
0x1800045ff  nop     dword ptr [rax+rax+00h]
0x180004604  mov     ebx, eax
0x180004606  test    eax, eax
0x180004608  jg      loc_180004690
0x18000460e  cmp     ebx, 8007007Ah
0x180004614  jz      loc_1800046DE
0x18000461a  mov     rcx, [rsp+68h+hKey]; hKey
0x18000461f  cmp     rcx, r15
0x180004622  jz      short loc_180004630
0x180004624  call    cs:__imp_RegCloseKey
0x18000462b  nop     dword ptr [rax+rax+00h]
0x180004630  test    ebx, ebx
0x180004632  js      short loc_180004652
0x180004634  mov     rcx, r14; void *
0x180004637  test    esi, esi
0x180004639  jnz     loc_18000471B
0x18000463f  call    ?DaclContainsPackageSid_@@YAHPEAX@Z; DaclContainsPackageSid_(void *)
0x180004644  test    eax, eax
0x180004646  jz      short loc_180004652
0x180004648  inc     edi
0x18000464a  cmp     edi, ebp
0x18000464c  jb      loc_1800045B0
0x180004652  mov     rbx, [rsp+68h+arg_0]
0x180004657  mov     rcx, r14; lpMem
0x18000465a  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x18000465f  xor     eax, eax
0x180004661  lea     r11, [rsp+68h+var_28]
0x180004666  mov     rsi, [r11+48h]
0x18000466a  cmp     edi, ebp
0x18000466c  mov     rbp, [r11+40h]
0x180004670  setz    al
0x180004673  mov     rsp, r11
0x180004676  pop     r15
0x180004678  pop     r14
0x18000467a  pop     r13
0x18000467c  pop     r12
0x18000467e  pop     rdi
0x18000467f  retn
0x180004681  movzx   eax, ax
0x180004684  or      eax, 80070000h
0x180004689  test    eax, eax
0x18000468b  jmp     loc_1800045DF
0x180004690  movzx   ebx, ax
0x180004693  or      ebx, 80070000h
0x180004699  jmp     loc_18000460E
0x18000469e  mov     r14, [rsp+68h+pSecurityDescriptor]
0x1800046a3  lea     r9, [rsp+68h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800046a8  mov     rcx, [rsp+68h+hKey]; hKey
0x1800046ad  mov     r8, r14; pSecurityDescriptor
0x1800046b0  mov     r12d, [rsp+68h+cbSecurityDescriptor]
0x1800046b5  mov     edx, 4; SecurityInformation
0x1800046ba  call    cs:__imp_RegGetKeySecurity
0x1800046c1  nop     dword ptr [rax+rax+00h]
0x1800046c6  mov     ebx, eax
0x1800046c8  test    eax, eax
0x1800046ca  jle     loc_18000461A
0x1800046d0  movzx   ebx, ax
0x1800046d3  or      ebx, 80070000h
0x1800046d9  jmp     loc_18000461A
0x1800046de  mov     eax, [rsp+68h+cbSecurityDescriptor]
0x1800046e2  lea     ecx, [rax+rax]
0x1800046e5  cmp     ecx, eax
0x1800046e7  jbe     short loc_180004711
0x1800046e9  mov     [rsp+68h+cbSecurityDescriptor], ecx
0x1800046ed  lea     r8, [rsp+68h+pSecurityDescriptor]; void **
0x1800046f2  mov     edx, ecx; dwBytes
0x1800046f4  mov     rcx, r14; lpMem
0x1800046f7  mov     [rsp+68h+pSecurityDescriptor], 0
0x180004700  call    ?ResultFromHeapReAlloc@@YAJPEAX_KPEAPEAX@Z; ResultFromHeapReAlloc(void *,unsigned __int64,void * *)
0x180004705  mov     ebx, eax
0x180004707  test    eax, eax
0x180004709  js      loc_18000461A
0x18000470f  jmp     short loc_18000469E
0x180004711  mov     ebx, 80070216h
0x180004716  jmp     loc_18000461A
0x18000471b  call    ?DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z; DaclContainsPackageAndLpacCapabilitySid_(void *)
0x180004720  jmp     loc_180004644
```
