# W32DrManualPrn::Enumerate(ProcObj *,DrObjectMgr<DrDevice> *)

- ea: `0x18055f290`
- end: `0x18055f671`
- name: `?Enumerate@W32DrManualPrn@@SAKPEAVProcObj@@PEAV?$DrObjectMgr@VDrDevice@@@@@Z`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180561058`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18007b16c`
- `0x1800ebae0`
- `0x18055f290`
- `0x180562fb4`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18055f3f4`
- `ADVAPI32!RegOpenKeyExW` at `0x18055f58e`
- `ADVAPI32!RegOpenKeyExW` at `0x18055f3f4`
- `ADVAPI32!RegOpenKeyExW` at `0x18055f58e`
- `ADVAPI32!RegQueryValueExW` at `0x18055f433`
- `ADVAPI32!RegQueryValueExW` at `0x18055f433`
- `ADVAPI32!RegCloseKey` at `0x18055f45e`
- `ADVAPI32!RegCloseKey` at `0x18055f562`
- `ADVAPI32!RegCloseKey` at `0x18055f5ea`
- `ADVAPI32!RegCloseKey` at `0x18055f45e`
- `ADVAPI32!RegCloseKey` at `0x18055f562`
- `ADVAPI32!RegCloseKey` at `0x18055f5ea`
- `ADVAPI32!RegCreateKeyExW` at `0x18055f379`
- `ADVAPI32!RegCreateKeyExW` at `0x18055f379`
- `ADVAPI32!RegEnumKeyExW` at `0x18055f49d`
- `ADVAPI32!RegEnumKeyExW` at `0x18055f49d`
- `ADVAPI32!RegDeleteKeyW` at `0x18055f557`
- `ADVAPI32!RegDeleteKeyW` at `0x18055f557`

## string_xrefs

- `0x18055f424`: `MaxPrinterCacheLength`

## pseudocode

```c
__int64 __fastcall W32DrManualPrn::Enumerate(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  unsigned int v5; // eax
  unsigned int v7; // r14d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  DWORD i; // edi
  HKEY v11; // rcx
  RefCount *v12; // rax
  HKEY v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = *(_QWORD *)(a1 + 224);
  phkResult = 0;
  cchName = 0;
  hKey = 0;
  Type = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v2 + 112) + 40LL))(*(_QWORD *)(v2 + 112)) )
  {
    v7 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Terminal Server Client\\Default\\AddIns\\RDPDR",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &phkResult,
           0);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_b2b723f64d253ca842d164799ba59190_Traceguids,
          CurrentThreadActivityIdPrefix,
          v7);
      }
      phkResult = 0;
    }
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Terminal Server Client", 0, 0x20019u, &hKey) )
    {
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"MaxPrinterCacheLength", 0, &Type, Data, &cbData) )
      {
        v9 = 500000;
        *(_DWORD *)Data *= 1000;
        if ( *(_DWORD *)Data < 0x7A120u )
          v9 = *(_DWORD *)Data;
        W32DrPRN::_maxCacheDataSize = v9;
      }
      RegCloseKey(hKey);
    }
LABEL_19:
    for ( i = 0; ; ++i )
    {
      v11 = phkResult;
      if ( v7 )
        break;
      cchName = 260;
      v7 = RegEnumKeyExW(phkResult, i, Name, &cchName, 0, 0, 0, 0);
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b2b723f64d253ca842d164799ba59190_Traceguids, v17, v7);
        }
      }
      else
      {
        v12 = (RefCount *)W32DrPRN::ResolveCachedPrinter(a1, a2, phkResult, Name);
        if ( !v12 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
          {
            if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v7 + 13,
                WPP_b2b723f64d253ca842d164799ba59190_Traceguids,
                v14);
              v13 = WPP_GLOBAL_Control;
            }
            if ( v13 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v13[7] & 1) != 0 && *((_BYTE *)v13 + 25) >= 3u )
            {
              v15 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                (unsigned int)WPP_b2b723f64d253ca842d164799ba59190_Traceguids,
                v15,
                (__int64)Name);
            }
          }
          RegDeleteKeyW(phkResult, Name);
          RegCloseKey(phkResult);
          phkResult = 0;
          if ( RegOpenKeyExW(
                 HKEY_CURRENT_USER,
                 L"Software\\Microsoft\\Terminal Server Client\\Default\\AddIns\\RDPDR",
                 0,
                 0x20019u,
                 &phkResult) )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                WPP_b2b723f64d253ca842d164799ba59190_Traceguids,
                v16,
                0);
            }
            v11 = 0;
            phkResult = 0;
            break;
          }
          goto LABEL_19;
        }
        RefCount::Release(v12);
      }
    }
    if ( v11 )
      RegCloseKey(v11);
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b2b723f64d253ca842d164799ba59190_Traceguids, v5);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18055f290  mov     [rsp-8+arg_10], rbx
0x18055f295  mov     [rsp-8+arg_18], rdi
0x18055f29a  push    rbp
0x18055f29b  push    r12
0x18055f29d  push    r13
0x18055f29f  push    r14
0x18055f2a1  push    r15
0x18055f2a3  lea     rbp, [rsp-190h]
0x18055f2ab  sub     rsp, 290h
0x18055f2b2  mov     rax, cs:__security_cookie
0x18055f2b9  xor     rax, rsp
0x18055f2bc  mov     [rbp+1B0h+var_30], rax
0x18055f2c3  mov     rax, [rcx+0E0h]
0x18055f2ca  xor     r13d, r13d
0x18055f2cd  mov     [rsp+2B0h+var_260], r13
0x18055f2d2  mov     r15, rcx
0x18055f2d5  mov     [rsp+2B0h+cchName], r13d
0x18055f2da  mov     r12, rdx
0x18055f2dd  mov     [rsp+2B0h+hKey], r13
0x18055f2e2  mov     [rsp+2B0h+Type], r13d
0x18055f2e7  mov     rcx, [rax+70h]
0x18055f2eb  mov     rax, [rcx]
0x18055f2ee  mov     rax, [rax+28h]
0x18055f2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18055f2f7  test    eax, eax
0x18055f2f9  jnz     short loc_18055F344
0x18055f2fb  mov     rax, cs:WPP_GLOBAL_Control
0x18055f302  lea     rbx, WPP_GLOBAL_Control
0x18055f309  cmp     rax, rbx
0x18055f30c  jz      short loc_18055F33D
0x18055f30e  test    byte ptr [rax+1Ch], 1
0x18055f312  jz      short loc_18055F33D
0x18055f314  cmp     byte ptr [rax+19h], 5
0x18055f318  jb      short loc_18055F33D
0x18055f31a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055f31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18055f326  lea     edx, [r13+0Bh]
0x18055f32a  mov     r9d, eax
0x18055f32d  lea     r8, WPP_b2b723f64d253ca842d164799ba59190_Traceguids
0x18055f334  mov     rcx, [rcx+10h]
0x18055f338  call    WPP_SF_d
0x18055f33d  xor     eax, eax
0x18055f33f  jmp     loc_18055F5F3
0x18055f344  mov     [rsp+2B0h+lpdwDisposition], r13; lpdwDisposition
0x18055f349  lea     rax, [rsp+2B0h+var_260]
0x18055f34e  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18055f353  lea     rdx, SubKey; "Software\\Microsoft\\Terminal Server Cl"...
0x18055f35a  mov     [rsp+2B0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18055f35f  xor     r9d, r9d; lpClass
0x18055f362  mov     [rsp+2B0h+samDesired], 0F003Fh; samDesired
0x18055f36a  xor     r8d, r8d; Reserved
0x18055f36d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18055f374  mov     [rsp+2B0h+dwOptions], r13d; dwOptions
0x18055f379  call    cs:__imp_RegCreateKeyExW
0x18055f37f  lea     rbx, WPP_GLOBAL_Control
0x18055f386  mov     r14d, eax
0x18055f389  test    eax, eax
0x18055f38b  jz      short loc_18055F3D3
0x18055f38d  mov     rcx, cs:WPP_GLOBAL_Control
0x18055f394  cmp     rcx, rbx
0x18055f397  jz      short loc_18055F3CE
0x18055f399  test    byte ptr [rcx+1Ch], 1
0x18055f39d  jz      short loc_18055F3CE
0x18055f39f  cmp     byte ptr [rcx+19h], 2
0x18055f3a3  jb      short loc_18055F3CE
0x18055f3a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055f3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18055f3b1  lea     r8, WPP_b2b723f64d253ca842d164799ba59190_Traceguids
0x18055f3b8  mov     edx, 0Ch
0x18055f3bd  mov     [rsp+2B0h+dwOptions], r14d
0x18055f3c2  mov     r9d, eax
0x18055f3c5  mov     rcx, [rcx+10h]
0x18055f3c9  call    WPP_SF_Dd
0x18055f3ce  mov     [rsp+2B0h+var_260], r13
0x18055f3d3  lea     rax, [rsp+2B0h+hKey]
0x18055f3d8  mov     r9d, 20019h; samDesired
0x18055f3de  xor     r8d, r8d; ulOptions
0x18055f3e1  mov     qword ptr [rsp+2B0h+dwOptions], rax; phkResult
0x18055f3e6  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Terminal Server Cl"...
0x18055f3ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18055f3f4  call    cs:__imp_RegOpenKeyExW
0x18055f3fa  test    eax, eax
0x18055f3fc  jnz     short loc_18055F464
0x18055f3fe  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18055f403  lea     rax, [rsp+2B0h+cbData]
0x18055f408  mov     qword ptr [rsp+2B0h+samDesired], rax; lpcbData
0x18055f40d  lea     r9, [rsp+2B0h+Type]; lpType
0x18055f412  lea     rax, [rsp+2B0h+Data]
0x18055f417  mov     dword ptr [rsp+2B0h+Data], r13d
0x18055f41c  xor     r8d, r8d; lpReserved
0x18055f41f  mov     qword ptr [rsp+2B0h+dwOptions], rax; lpData
0x18055f424  lea     rdx, aMaxprintercach; "MaxPrinterCacheLength"
0x18055f42b  mov     [rsp+2B0h+cbData], 4
0x18055f433  call    cs:__imp_RegQueryValueExW
0x18055f439  test    eax, eax
0x18055f43b  jnz     short loc_18055F459
0x18055f43d  imul    ecx, dword ptr [rsp+2B0h+Data], 3E8h
0x18055f445  mov     eax, 7A120h
0x18055f44a  cmp     ecx, eax
0x18055f44c  mov     dword ptr [rsp+2B0h+Data], ecx
0x18055f450  cmovb   eax, ecx
0x18055f453  mov     cs:?_maxCacheDataSize@W32DrPRN@@1KA, eax; ulong W32DrPRN::_maxCacheDataSize
0x18055f459  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18055f45e  call    cs:__imp_RegCloseKey
0x18055f464  mov     edi, r13d
0x18055f467  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18055f46c  test    r14d, r14d
0x18055f46f  jnz     loc_18055F5E5
0x18055f475  mov     [rsp+2B0h+phkResult], r13; lpftLastWriteTime
0x18055f47a  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18055f47f  mov     [rsp+2B0h+lpSecurityAttributes], r13; lpcchClass
0x18055f484  lea     r8, [rsp+2B0h+Name]; lpName
0x18055f489  mov     qword ptr [rsp+2B0h+samDesired], r13; lpClass
0x18055f48e  mov     edx, edi; dwIndex
0x18055f490  mov     qword ptr [rsp+2B0h+dwOptions], r13; lpReserved
0x18055f495  mov     [rsp+2B0h+cchName], 104h
0x18055f49d  call    cs:__imp_RegEnumKeyExW
0x18055f4a3  mov     r14d, eax
0x18055f4a6  test    eax, eax
0x18055f4a8  jnz     loc_18055F629
0x18055f4ae  mov     r8, [rsp+2B0h+var_260]
0x18055f4b3  lea     r9, [rsp+2B0h+Name]
0x18055f4b8  mov     rdx, r12
0x18055f4bb  mov     rcx, r15
0x18055f4be  call    ?ResolveCachedPrinter@W32DrPRN@@KAPEAV1@PEAVProcObj@@PEAV?$DrObjectMgr@VDrDevice@@@@PEAUHKEY__@@PEAG@Z; W32DrPRN::ResolveCachedPrinter(ProcObj *,DrObjectMgr<DrDevice> *,HKEY__ *,ushort *)
0x18055f4c3  test    rax, rax
0x18055f4c6  jnz     loc_18055F61F
0x18055f4cc  mov     rax, cs:WPP_GLOBAL_Control
0x18055f4d3  cmp     rax, rbx
0x18055f4d6  jz      short loc_18055F54D
0x18055f4d8  test    byte ptr [rax+1Ch], 1
0x18055f4dc  jz      short loc_18055F50E
0x18055f4de  cmp     byte ptr [rax+19h], 2
0x18055f4e2  jb      short loc_18055F50E
0x18055f4e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055f4e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18055f4f0  lea     edx, [r14+0Dh]
0x18055f4f4  mov     r9d, eax
0x18055f4f7  lea     r8, WPP_b2b723f64d253ca842d164799ba59190_Traceguids
0x18055f4fe  mov     rcx, [rcx+10h]
0x18055f502  call    WPP_SF_d
0x18055f507  mov     rax, cs:WPP_GLOBAL_Control
0x18055f50e  cmp     rax, rbx
0x18055f511  jz      short loc_18055F54D
0x18055f513  test    byte ptr [rax+1Ch], 1
0x18055f517  jz      short loc_18055F54D
0x18055f519  cmp     byte ptr [rax+19h], 3
0x18055f51d  jb      short loc_18055F54D
0x18055f51f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055f524  lea     rcx, [rsp+2B0h+Name]
0x18055f529  mov     edx, 0Eh
0x18055f52e  mov     qword ptr [rsp+2B0h+dwOptions], rcx
0x18055f533  lea     r8, WPP_b2b723f64d253ca842d164799ba59190_Traceguids
0x18055f53a  mov     rcx, cs:WPP_GLOBAL_Control
0x18055f541  mov     r9d, eax
0x18055f544  mov     rcx, [rcx+10h]
0x18055f548  call    WPP_SF_DS
0x18055f54d  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18055f552  lea     rdx, [rsp+2B0h+Name]; lpSubKey
0x18055f557  call    cs:__imp_RegDeleteKeyW
0x18055f55d  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18055f562  call    cs:__imp_RegCloseKey
0x18055f568  lea     rax, [rsp+2B0h+var_260]
0x18055f56d  mov     [rsp+2B0h+var_260], r13
0x18055f572  mov     r9d, 20019h; samDesired
0x18055f578  mov     qword ptr [rsp+2B0h+dwOptions], rax; phkResult
0x18055f57d  xor     r8d, r8d; ulOptions
0x18055f580  lea     rdx, SubKey; "Software\\Microsoft\\Terminal Server Cl"...
0x18055f587  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18055f58e  call    cs:__imp_RegOpenKeyExW
0x18055f594  test    eax, eax
0x18055f596  jz      loc_18055F464
0x18055f59c  mov     rax, cs:WPP_GLOBAL_Control
0x18055f5a3  cmp     rax, rbx
0x18055f5a6  jz      short loc_18055F5DD
0x18055f5a8  test    byte ptr [rax+1Ch], 1
0x18055f5ac  jz      short loc_18055F5DD
0x18055f5ae  cmp     byte ptr [rax+19h], 2
0x18055f5b2  jb      short loc_18055F5DD
0x18055f5b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055f5b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18055f5c0  lea     r8, WPP_b2b723f64d253ca842d164799ba59190_Traceguids
0x18055f5c7  mov     edx, 0Fh
0x18055f5cc  mov     [rsp+2B0h+dwOptions], r13d
0x18055f5d1  mov     r9d, eax
0x18055f5d4  mov     rcx, [rcx+10h]
0x18055f5d8  call    WPP_SF_Dd
0x18055f5dd  mov     rcx, r13; hKey
0x18055f5e0  mov     [rsp+2B0h+var_260], rcx
0x18055f5e5  test    rcx, rcx
0x18055f5e8  jz      short loc_18055F5F0
0x18055f5ea  call    cs:__imp_RegCloseKey
0x18055f5f0  mov     eax, r14d
0x18055f5f3  mov     rcx, [rbp+1B0h+var_30]
0x18055f5fa  xor     rcx, rsp; StackCookie
0x18055f5fd  call    __security_check_cookie
0x18055f602  lea     r11, [rsp+2B0h+var_20]
0x18055f60a  mov     rbx, [r11+40h]
0x18055f60e  mov     rdi, [r11+48h]
0x18055f612  mov     rsp, r11
0x18055f615  pop     r15
0x18055f617  pop     r14
0x18055f619  pop     r13
0x18055f61b  pop     r12
0x18055f61d  pop     rbp
0x18055f61e  retn
0x18055f61f  mov     rcx, rax; this
0x18055f622  call    ?Release@RefCount@@QEAAKXZ; RefCount::Release(void)
0x18055f627  jmp     short loc_18055F66A
0x18055f629  mov     rax, cs:WPP_GLOBAL_Control
0x18055f630  cmp     rax, rbx
0x18055f633  jz      short loc_18055F66A
0x18055f635  test    byte ptr [rax+1Ch], 1
0x18055f639  jz      short loc_18055F66A
0x18055f63b  cmp     byte ptr [rax+19h], 4
0x18055f63f  jb      short loc_18055F66A
0x18055f641  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18055f646  mov     rcx, cs:WPP_GLOBAL_Control
0x18055f64d  lea     r8, WPP_b2b723f64d253ca842d164799ba59190_Traceguids
0x18055f654  mov     edx, 10h
0x18055f659  mov     [rsp+2B0h+dwOptions], r14d
0x18055f65e  mov     r9d, eax
0x18055f661  mov     rcx, [rcx+10h]
0x18055f665  call    WPP_SF_Dd
0x18055f66a  inc     edi
0x18055f66c  jmp     loc_18055F467
```
