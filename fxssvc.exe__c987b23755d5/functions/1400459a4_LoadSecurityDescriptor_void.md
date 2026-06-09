# LoadSecurityDescriptor(void)

- ea: `0x1400459a4`
- end: `0x140045c82`
- name: `?LoadSecurityDescriptor@@YAKXZ`
- size: `734`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400458d0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x1400459a4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140045c18`
- `ADVAPI32!RegCloseKey` at `0x140045c18`
- `ADVAPI32!RegCreateKeyExW` at `0x140045a42`
- `ADVAPI32!RegCreateKeyExW` at `0x140045a42`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140045ba7`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x140045ba7`
- `ADVAPI32!RegQueryValueExW` at `0x140045aab`
- `ADVAPI32!RegQueryValueExW` at `0x140045b72`
- `ADVAPI32!RegQueryValueExW` at `0x140045aab`
- `ADVAPI32!RegQueryValueExW` at `0x140045b72`
- `KERNEL32!HeapAlloc` at `0x140045b0c`
- `KERNEL32!HeapAlloc` at `0x140045b0c`
- `KERNEL32!GetLastError` at `0x140045c53`
- `KERNEL32!GetLastError` at `0x140045c53`
- `KERNEL32!GetProcessHeap` at `0x140045af9`
- `KERNEL32!GetProcessHeap` at `0x140045c23`
- `KERNEL32!GetProcessHeap` at `0x140045af9`
- `KERNEL32!GetProcessHeap` at `0x140045c23`
- `KERNEL32!HeapFree` at `0x140045c31`
- `KERNEL32!HeapFree` at `0x140045c31`

## string_xrefs

- `0x140045a2a`: `Software\Microsoft\Fax\Security`
- `0x140045aa4`: `Descriptor`
- `0x140045b6b`: `Descriptor`

## pseudocode

```c
__int64 LoadSecurityDescriptor(void)
{
  BYTE *v0; // rdi
  unsigned int v1; // eax
  unsigned int v2; // ebx
  CMapDeviceId *v3; // rcx
  __int64 v4; // rdx
  DWORD v5; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v7; // r8
  CMapDeviceId *v8; // rcx
  __int64 v9; // rdx
  HANDLE v10; // rax
  DWORD LastError; // eax
  DWORD cbData; // [rsp+80h] [rbp+30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  cbData = 0;
  v0 = 0;
  hKey = 0;
  dwDisposition = 0;
  Type = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Fax\\Security",
         0,
         (LPWSTR)&Class,
         0,
         0x20019u,
         0,
         &hKey,
         &dwDisposition);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 38;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v1);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  v1 = RegQueryValueExW(hKey, L"Descriptor", 0, &Type, 0, &cbData);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 39;
      goto LABEL_10;
    }
    goto LABEL_40;
  }
  if ( Type != 3 || !cbData )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    v2 = 1009;
    goto LABEL_40;
  }
  v5 = cbData;
  ProcessHeap = GetProcessHeap();
  v7 = v5;
  v2 = 8;
  v0 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7);
  if ( !v0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_40;
    }
    v9 = 41;
LABEL_23:
    WPP_SF_(*((_QWORD *)v8 + 2), v9, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    goto LABEL_40;
  }
  v1 = RegQueryValueExW(hKey, L"Descriptor", 0, &Type, v0, &cbData);
  v2 = v1;
  if ( v1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = 42;
      goto LABEL_10;
    }
    goto LABEL_40;
  }
  if ( IsValidSecurityDescriptor(v0) )
  {
    g_pFaxSD = v0;
    v0 = 0;
    goto LABEL_40;
  }
  v2 = 1338;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 43;
    goto LABEL_23;
  }
LABEL_40:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v0 )
  {
    v10 = GetProcessHeap();
    if ( !HeapFree(v10, 0, v0)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400459a4  push    rbp
0x1400459a6  push    rbx
0x1400459a7  push    rdi
0x1400459a8  push    r13
0x1400459aa  push    r15
0x1400459ac  mov     rbp, rsp
0x1400459af  sub     rsp, 50h
0x1400459b3  mov     [rbp+cbData], 0
0x1400459ba  xor     edi, edi
0x1400459bc  mov     [rbp+hKey], 0
0x1400459c4  mov     [rbp+dwDisposition], 0
0x1400459cb  mov     [rbp+Type], 0
0x1400459d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400459d9  lea     r15, WPP_GLOBAL_Control
0x1400459e0  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400459e7  cmp     rcx, r15
0x1400459ea  jz      short loc_140045A07
0x1400459ec  test    byte ptr [rcx+1Ch], 4
0x1400459f0  jz      short loc_140045A07
0x1400459f2  cmp     byte ptr [rcx+19h], 5
0x1400459f6  jb      short loc_140045A07
0x1400459f8  mov     rcx, [rcx+10h]
0x1400459fc  lea     edx, [rdi+25h]
0x1400459ff  mov     r8, r13
0x140045a02  call    WPP_SF_
0x140045a07  lea     rax, [rbp+dwDisposition]
0x140045a0b  xor     r8d, r8d; Reserved
0x140045a0e  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x140045a13  lea     r9, Class; lpClass
0x140045a1a  lea     rax, [rbp+hKey]
0x140045a1e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140045a25  mov     [rsp+50h+phkResult], rax; phkResult
0x140045a2a  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Fax\\Security"
0x140045a31  mov     [rsp+50h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x140045a36  mov     [rsp+50h+samDesired], 20019h; samDesired
0x140045a3e  mov     [rsp+50h+dwOptions], edi; dwOptions
0x140045a42  call    cs:__imp_RegCreateKeyExW
0x140045a48  mov     ebx, eax
0x140045a4a  test    eax, eax
0x140045a4c  jz      short loc_140045A8B
0x140045a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140045a55  cmp     rcx, r15
0x140045a58  jz      loc_140045C0F
0x140045a5e  test    byte ptr [rcx+1Ch], 4
0x140045a62  jz      loc_140045C0F
0x140045a68  cmp     byte ptr [rcx+19h], 2
0x140045a6c  jb      loc_140045C0F
0x140045a72  mov     edx, 26h ; '&'
0x140045a77  mov     rcx, [rcx+10h]
0x140045a7b  mov     r9d, eax
0x140045a7e  mov     r8, r13
0x140045a81  call    WPP_SF_d
0x140045a86  jmp     loc_140045C0F
0x140045a8b  mov     rcx, [rbp+hKey]; hKey
0x140045a8f  lea     rax, [rbp+cbData]
0x140045a93  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x140045a98  lea     r9, [rbp+Type]; lpType
0x140045a9c  xor     r8d, r8d; lpReserved
0x140045a9f  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x140045aa4  lea     rdx, aDescriptor; "Descriptor"
0x140045aab  call    cs:__imp_RegQueryValueExW
0x140045ab1  mov     ebx, eax
0x140045ab3  test    eax, eax
0x140045ab5  jz      short loc_140045AE2
0x140045ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140045abe  cmp     rcx, r15
0x140045ac1  jz      loc_140045C0F
0x140045ac7  test    byte ptr [rcx+1Ch], 4
0x140045acb  jz      loc_140045C0F
0x140045ad1  cmp     byte ptr [rcx+19h], 2
0x140045ad5  jb      loc_140045C0F
0x140045adb  mov     edx, 27h ; '''
0x140045ae0  jmp     short loc_140045A77
0x140045ae2  cmp     [rbp+Type], 3
0x140045ae6  jnz     loc_140045BE1
0x140045aec  mov     eax, [rbp+cbData]
0x140045aef  test    eax, eax
0x140045af1  jz      loc_140045BE1
0x140045af7  mov     ebx, eax
0x140045af9  call    cs:__imp_GetProcessHeap
0x140045aff  mov     r8d, ebx; dwBytes
0x140045b02  mov     ebx, 8
0x140045b07  mov     edx, ebx; dwFlags
0x140045b09  mov     rcx, rax; hHeap
0x140045b0c  call    cs:__imp_HeapAlloc
0x140045b12  mov     rdi, rax
0x140045b15  test    rax, rax
0x140045b18  jnz     short loc_140045B52
0x140045b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140045b21  cmp     rcx, r15
0x140045b24  jz      loc_140045C0F
0x140045b2a  test    byte ptr [rcx+1Ch], 4
0x140045b2e  jz      loc_140045C0F
0x140045b34  cmp     byte ptr [rcx+19h], 2
0x140045b38  jb      loc_140045C0F
0x140045b3e  lea     edx, [rbx+21h]
0x140045b41  mov     rcx, [rcx+10h]
0x140045b45  mov     r8, r13
0x140045b48  call    WPP_SF_
0x140045b4d  jmp     loc_140045C0F
0x140045b52  mov     rcx, [rbp+hKey]; hKey
0x140045b56  lea     rax, [rbp+cbData]
0x140045b5a  mov     qword ptr [rsp+50h+samDesired], rax; lpcbData
0x140045b5f  lea     r9, [rbp+Type]; lpType
0x140045b63  xor     r8d, r8d; lpReserved
0x140045b66  mov     qword ptr [rsp+50h+dwOptions], rdi; lpData
0x140045b6b  lea     rdx, aDescriptor; "Descriptor"
0x140045b72  call    cs:__imp_RegQueryValueExW
0x140045b78  mov     ebx, eax
0x140045b7a  test    eax, eax
0x140045b7c  jz      short loc_140045BA4
0x140045b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140045b85  cmp     rcx, r15
0x140045b88  jz      loc_140045C0F
0x140045b8e  test    byte ptr [rcx+1Ch], 4
0x140045b92  jz      short loc_140045C0F
0x140045b94  cmp     byte ptr [rcx+19h], 2
0x140045b98  jb      short loc_140045C0F
0x140045b9a  mov     edx, 2Ah ; '*'
0x140045b9f  jmp     loc_140045A77
0x140045ba4  mov     rcx, rdi; pSecurityDescriptor
0x140045ba7  call    cs:__imp_IsValidSecurityDescriptor
0x140045bad  test    eax, eax
0x140045baf  jnz     short loc_140045BD6
0x140045bb1  mov     ebx, 53Ah
0x140045bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x140045bbd  cmp     rcx, r15
0x140045bc0  jz      short loc_140045C0F
0x140045bc2  test    byte ptr [rcx+1Ch], 4
0x140045bc6  jz      short loc_140045C0F
0x140045bc8  cmp     byte ptr [rcx+19h], 2
0x140045bcc  jb      short loc_140045C0F
0x140045bce  lea     edx, [rax+2Bh]
0x140045bd1  jmp     loc_140045B41
0x140045bd6  mov     cs:?g_pFaxSD@@3PEAXEA, rdi; void * g_pFaxSD
0x140045bdd  xor     edi, edi
0x140045bdf  jmp     short loc_140045C0F
0x140045be1  mov     rcx, cs:WPP_GLOBAL_Control
0x140045be8  cmp     rcx, r15
0x140045beb  jz      short loc_140045C0A
0x140045bed  test    byte ptr [rcx+1Ch], 4
0x140045bf1  jz      short loc_140045C0A
0x140045bf3  cmp     byte ptr [rcx+19h], 2
0x140045bf7  jb      short loc_140045C0A
0x140045bf9  mov     rcx, [rcx+10h]
0x140045bfd  mov     edx, 28h ; '('
0x140045c02  mov     r8, r13
0x140045c05  call    WPP_SF_
0x140045c0a  mov     ebx, 3F1h
0x140045c0f  mov     rcx, [rbp+hKey]; hKey
0x140045c13  test    rcx, rcx
0x140045c16  jz      short loc_140045C1E
0x140045c18  call    cs:__imp_RegCloseKey
0x140045c1e  test    rdi, rdi
0x140045c21  jz      short loc_140045C74
0x140045c23  call    cs:__imp_GetProcessHeap
0x140045c29  mov     r8, rdi; lpMem
0x140045c2c  xor     edx, edx; dwFlags
0x140045c2e  mov     rcx, rax; hHeap
0x140045c31  call    cs:__imp_HeapFree
0x140045c37  test    eax, eax
0x140045c39  jnz     short loc_140045C74
0x140045c3b  mov     rax, cs:WPP_GLOBAL_Control
0x140045c42  cmp     rax, r15
0x140045c45  jz      short loc_140045C74
0x140045c47  test    byte ptr [rax+1Ch], 4
0x140045c4b  jz      short loc_140045C74
0x140045c4d  cmp     byte ptr [rax+19h], 2
0x140045c51  jb      short loc_140045C74
0x140045c53  call    cs:__imp_GetLastError
0x140045c59  mov     rcx, cs:WPP_GLOBAL_Control
0x140045c60  mov     edx, 2Ch ; ','
0x140045c65  mov     r9d, eax
0x140045c68  mov     r8, r13
0x140045c6b  mov     rcx, [rcx+10h]
0x140045c6f  call    WPP_SF_d
0x140045c74  mov     eax, ebx
0x140045c76  add     rsp, 50h
0x140045c7a  pop     r15
0x140045c7c  pop     r13
0x140045c7e  pop     rdi
0x140045c7f  pop     rbx
0x140045c80  pop     rbp
0x140045c81  retn
```
