# DfdManager::ExistInIgnoreList(ushort *)

- ea: `0x1800064fc`
- end: `0x18000673b`
- name: `?ExistInIgnoreList@DfdManager@@QEAA_NPEAG@Z`
- size: `575`
- prototype: `char __fastcall(DfdManager *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002ed8`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x1800064fc`
- `0x18000833b`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800066e6`
- `msvcrt!_wcsicmp` at `0x1800066e6`
- `KERNEL32!HeapAlloc` at `0x180006662`
- `KERNEL32!HeapAlloc` at `0x180006662`
- `KERNEL32!GetProcessHeap` at `0x18000664e`
- `KERNEL32!GetProcessHeap` at `0x180006710`
- `KERNEL32!GetProcessHeap` at `0x18000664e`
- `KERNEL32!GetProcessHeap` at `0x180006710`
- `KERNEL32!HeapFree` at `0x18000671e`
- `KERNEL32!HeapFree` at `0x18000671e`
- `ADVAPI32!RegOpenKeyExW` at `0x180006542`
- `ADVAPI32!RegOpenKeyExW` at `0x180006542`
- `ADVAPI32!RegEnumValueW` at `0x1800066d6`
- `ADVAPI32!RegEnumValueW` at `0x1800066d6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800065cd`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800065cd`
- `ADVAPI32!RegCloseKey` at `0x180006705`
- `ADVAPI32!RegCloseKey` at `0x180006705`

## pseudocode

```c
char __fastcall DfdManager::ExistInIgnoreList(DfdManager *this, unsigned __int16 *a2)
{
  char v3; // si
  void *v4; // rdi
  unsigned int v5; // eax
  __int64 v6; // r9
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v12; // ebx
  HANDLE v13; // rax
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  DfdManager *cbMaxValueNameLen; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cValues; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cchValueName; // [rsp+B8h] [rbp+48h] BYREF

  cbMaxValueNameLen = this;
  hKey = 0;
  v3 = 0;
  v4 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\DiskDiagnostics\\IgnoreList",
         0,
         1u,
         &hKey);
  v6 = v5;
  if ( v5 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 46;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v6);
    }
  }
  else
  {
    cValues = 0;
    LODWORD(cbMaxValueNameLen) = 0;
    v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, (LPDWORD)&cbMaxValueNameLen, 0, 0, 0);
    v6 = v9;
    if ( v9 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 47;
        goto LABEL_5;
      }
    }
    else if ( cValues )
    {
      LODWORD(cbMaxValueNameLen) = (_DWORD)cbMaxValueNameLen + 1;
      v10 = (unsigned int)cbMaxValueNameLen;
      ProcessHeap = GetProcessHeap();
      v4 = HeapAlloc(ProcessHeap, 8u, 2LL * v10);
      if ( v4 )
      {
        v12 = 0;
        if ( cValues )
        {
          while ( 1 )
          {
            memset_0(v4, 0, 2LL * (unsigned int)cbMaxValueNameLen);
            cchValueName = (unsigned int)cbMaxValueNameLen;
            if ( !RegEnumValueW(hKey, v12, (LPWSTR)v4, &cchValueName, 0, 0, 0, 0) && !_wcsicmp((const wchar_t *)v4, a2) )
              break;
            if ( ++v12 >= cValues )
              goto LABEL_24;
          }
          v3 = 1;
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 49;
          v6 = 14;
          goto LABEL_5;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids);
    }
  }
LABEL_24:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v4);
  }
  return v3;
}

```

## disassembly

```asm
0x1800064fc  mov     [rsp-28h+arg_8], rbx
0x180006501  mov     [rsp-28h+cbMaxValueNameLen], rcx
0x180006506  push    rbp
0x180006507  push    rsi
0x180006508  push    rdi
0x180006509  push    r14
0x18000650b  push    r15
0x18000650d  mov     rbp, rsp
0x180006510  sub     rsp, 70h
0x180006514  xor     r15d, r15d
0x180006517  lea     rax, [rbp+hKey]
0x18000651b  mov     r14, rdx
0x18000651e  mov     [rbp+hKey], r15
0x180006522  xor     r8d, r8d; ulOptions
0x180006525  mov     [rsp+70h+phkResult], rax; phkResult
0x18000652a  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180006531  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006538  lea     r9d, [r15+1]; samDesired
0x18000653c  mov     sil, r15b
0x18000653f  mov     edi, r15d
0x180006542  call    cs:__imp_RegOpenKeyExW
0x180006548  mov     r9d, eax
0x18000654b  test    eax, eax
0x18000654d  jz      short loc_180006589
0x18000654f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006556  lea     rax, WPP_GLOBAL_Control
0x18000655d  cmp     rcx, rax
0x180006560  jz      loc_1800066FC
0x180006566  test    byte ptr [rcx+1Ch], 1
0x18000656a  jz      loc_1800066FC
0x180006570  lea     edx, [r15+2Eh]
0x180006574  mov     rcx, [rcx+10h]
0x180006578  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x18000657f  call    WPP_SF_d
0x180006584  jmp     loc_1800066FC
0x180006589  mov     rcx, [rbp+hKey]; hKey
0x18000658d  lea     rax, [rbp+cbMaxValueNameLen]
0x180006591  mov     [rsp+70h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006596  xor     r9d, r9d; lpReserved
0x180006599  mov     [rsp+70h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000659e  xor     r8d, r8d; lpcchClass
0x1800065a1  mov     [rsp+70h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800065a6  xor     edx, edx; lpClass
0x1800065a8  mov     [rsp+70h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800065ad  lea     rax, [rbp+cValues]
0x1800065b1  mov     [rsp+70h+lpcValues], rax; lpcValues
0x1800065b6  mov     [rsp+70h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800065bb  mov     [rsp+70h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800065c0  mov     [rsp+70h+phkResult], r15; lpcSubKeys
0x1800065c5  mov     [rbp+cValues], r15d
0x1800065c9  mov     dword ptr [rbp+cbMaxValueNameLen], r15d
0x1800065cd  call    cs:__imp_RegQueryInfoKeyW
0x1800065d3  mov     r9d, eax
0x1800065d6  test    eax, eax
0x1800065d8  jz      short loc_180006605
0x1800065da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065e1  lea     rax, WPP_GLOBAL_Control
0x1800065e8  cmp     rcx, rax
0x1800065eb  jz      loc_1800066FC
0x1800065f1  test    byte ptr [rcx+1Ch], 1
0x1800065f5  jz      loc_1800066FC
0x1800065fb  mov     edx, 2Fh ; '/'
0x180006600  jmp     loc_180006574
0x180006605  cmp     [rbp+cValues], r15d
0x180006609  jnz     short loc_180006646
0x18000660b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006612  lea     rax, WPP_GLOBAL_Control
0x180006619  cmp     rcx, rax
0x18000661c  jz      loc_1800066FC
0x180006622  test    byte ptr [rcx+1Ch], 4
0x180006626  jz      loc_1800066FC
0x18000662c  mov     rcx, [rcx+10h]
0x180006630  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006637  mov     edx, 30h ; '0'
0x18000663c  call    WPP_SF_
0x180006641  jmp     loc_1800066FC
0x180006646  mov     ebx, dword ptr [rbp+cbMaxValueNameLen]
0x180006649  inc     ebx
0x18000664b  mov     dword ptr [rbp+cbMaxValueNameLen], ebx
0x18000664e  call    cs:__imp_GetProcessHeap
0x180006654  mov     r8d, ebx
0x180006657  mov     edx, 8; dwFlags
0x18000665c  add     r8, r8; dwBytes
0x18000665f  mov     rcx, rax; hHeap
0x180006662  call    cs:__imp_HeapAlloc
0x180006668  mov     rdi, rax
0x18000666b  test    rax, rax
0x18000666e  jnz     short loc_180006695
0x180006670  mov     rcx, cs:WPP_GLOBAL_Control
0x180006677  lea     rax, WPP_GLOBAL_Control
0x18000667e  cmp     rcx, rax
0x180006681  jz      short loc_1800066FC
0x180006683  test    byte ptr [rcx+1Ch], 1
0x180006687  jz      short loc_1800066FC
0x180006689  lea     edx, [rdi+31h]
0x18000668c  lea     r9d, [rdi+0Eh]
0x180006690  jmp     loc_180006574
0x180006695  mov     ebx, r15d
0x180006698  cmp     [rbp+cValues], r15d
0x18000669c  jbe     short loc_1800066FC
0x18000669e  mov     r8d, dword ptr [rbp+cbMaxValueNameLen]
0x1800066a2  xor     edx, edx; Val
0x1800066a4  add     r8, r8; Size
0x1800066a7  mov     rcx, rdi; void *
0x1800066aa  call    memset_0
0x1800066af  mov     eax, dword ptr [rbp+cbMaxValueNameLen]
0x1800066b2  lea     r9, [rbp+cchValueName]; lpcchValueName
0x1800066b6  mov     rcx, [rbp+hKey]; hKey
0x1800066ba  mov     r8, rdi; lpValueName
0x1800066bd  mov     [rsp+70h+lpcValues], r15; lpcbData
0x1800066c2  mov     edx, ebx; dwIndex
0x1800066c4  mov     [rsp+70h+lpcbMaxClassLen], r15; lpData
0x1800066c9  mov     [rsp+70h+lpcbMaxSubKeyLen], r15; lpType
0x1800066ce  mov     [rsp+70h+phkResult], r15; lpReserved
0x1800066d3  mov     [rbp+cchValueName], eax
0x1800066d6  call    cs:__imp_RegEnumValueW
0x1800066dc  test    eax, eax
0x1800066de  jnz     short loc_1800066F0
0x1800066e0  mov     rdx, r14; String2
0x1800066e3  mov     rcx, rdi; String1
0x1800066e6  call    cs:__imp__wcsicmp
0x1800066ec  test    eax, eax
0x1800066ee  jz      short loc_1800066F9
0x1800066f0  inc     ebx
0x1800066f2  cmp     ebx, [rbp+cValues]
0x1800066f5  jb      short loc_18000669E
0x1800066f7  jmp     short loc_1800066FC
0x1800066f9  mov     sil, 1
0x1800066fc  mov     rcx, [rbp+hKey]; hKey
0x180006700  test    rcx, rcx
0x180006703  jz      short loc_18000670B
0x180006705  call    cs:__imp_RegCloseKey
0x18000670b  test    rdi, rdi
0x18000670e  jz      short loc_180006724
0x180006710  call    cs:__imp_GetProcessHeap
0x180006716  mov     r8, rdi; lpMem
0x180006719  xor     edx, edx; dwFlags
0x18000671b  mov     rcx, rax; hHeap
0x18000671e  call    cs:__imp_HeapFree
0x180006724  mov     rbx, [rsp+70h+arg_8]
0x18000672c  mov     al, sil
0x18000672f  add     rsp, 70h
0x180006733  pop     r15
0x180006735  pop     r14
0x180006737  pop     rdi
0x180006738  pop     rsi
0x180006739  pop     rbp
0x18000673a  retn
```
