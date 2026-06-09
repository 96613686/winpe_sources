# SetSecurityOnFile(ushort *,ushort *)

- ea: `0x180025e98`
- end: `0x180025ff5`
- name: `?SetSecurityOnFile@@YAJPEAG0@Z`
- size: `349`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000e104`
- `0x18001c508`

## callees

- `0x180025e98`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x180025f79`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180025f79`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180025ee9`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180025ee9`
- `KERNEL32!LocalFree` at `0x180025fdd`
- `KERNEL32!LocalFree` at `0x180025fdd`
- `IisRTL!PuDbgPrintW` at `0x180025f42`
- `IisRTL!PuDbgPrintW` at `0x180025fc9`
- `IisRTL!PuDbgPrintW` at `0x180025f42`
- `IisRTL!PuDbgPrintW` at `0x180025fc9`

## string_xrefs

- `0x180025f14`: `[SetSecurityOnFile] Unable to set security on %s. GetNamedSecurityInfo on %s failed with hr = 0x%x\n.`
- `0x180025f1f`: `SetSecurityOnFile`
- `0x180025fab`: `SetSecurityOnFile`
- `0x180025fa0`: `[SetSecurityOnFile] Unable to set security on %s. SetNamedSecurityInfo failed with hr = 0x%x\n.`

## pseudocode

```c
__int64 __fastcall SetSecurityOnFile(unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int NamedSecurityInfoW; // eax
  unsigned int v5; // ebx
  signed int v6; // eax
  PACL pSacl; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+38h] [rbp-10h]
  PACL pDacl; // [rsp+60h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  pDacl = 0;
  hMem = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, &pDacl, 0, &hMem);
  v5 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW )
  {
    if ( NamedSecurityInfoW > 0 )
      v5 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v9) = v5;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        13528,
        "SetSecurityOnFile",
        L"[SetSecurityOnFile] Unable to set security on %s. GetNamedSecurityInfo on %s failed with hr = 0x%x\n.",
        a2,
        a1,
        v9);
    }
  }
  else
  {
    v6 = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(pSacl) = v5;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          13548,
          "SetSecurityOnFile",
          L"[SetSecurityOnFile] Unable to set security on %s. SetNamedSecurityInfo failed with hr = 0x%x\n.",
          a2,
          pSacl);
      }
    }
    else
    {
      v5 = 0;
    }
  }
  if ( hMem )
    LocalFree(hMem);
  return v5;
}

```

## disassembly

```asm
0x180025e98  mov     r11, rsp
0x180025e9b  mov     [r11+8], rbx
0x180025e9f  mov     [r11+10h], rsi
0x180025ea3  push    rdi
0x180025ea4  sub     rsp, 40h
0x180025ea8  lea     rax, [r11+20h]
0x180025eac  mov     qword ptr [r11+18h], 0
0x180025eb4  mov     [r11-10h], rax
0x180025eb8  xor     r9d, r9d; ppsidOwner
0x180025ebb  mov     qword ptr [r11-18h], 0
0x180025ec3  lea     rax, [r11+18h]
0x180025ec7  mov     rdi, rdx
0x180025eca  mov     [r11-20h], rax
0x180025ece  mov     qword ptr [r11-28h], 0
0x180025ed6  mov     rsi, rcx
0x180025ed9  lea     edx, [r9+1]; ObjectType
0x180025edd  mov     qword ptr [r11+20h], 0
0x180025ee5  lea     r8d, [r9+4]; SecurityInfo
0x180025ee9  call    cs:__imp_GetNamedSecurityInfoW
0x180025eef  mov     ebx, eax
0x180025ef1  test    eax, eax
0x180025ef3  jz      short loc_180025F4D
0x180025ef5  jle     short loc_180025F00
0x180025ef7  movzx   ebx, ax
0x180025efa  or      ebx, 80070000h
0x180025f00  test    byte ptr cs:g_dwDebugFlags, 3
0x180025f07  jz      loc_180025FD3
0x180025f0d  mov     rcx, cs:g_pDebug
0x180025f14  lea     rax, aSetsecurityonf_0; "[SetSecurityOnFile] Unable to set secur"...
0x180025f1b  mov     [rsp+48h+var_10], ebx
0x180025f1f  lea     r9, aSetsecurityonf_1; "SetSecurityOnFile"
0x180025f26  mov     [rsp+48h+pSacl], rsi
0x180025f2b  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180025f32  mov     [rsp+48h+pDacl], rdi
0x180025f37  mov     r8d, 34D8h
0x180025f3d  mov     [rsp+48h+psidGroup], rax
0x180025f42  call    cs:__imp_PuDbgPrintW
0x180025f48  jmp     loc_180025FD3
0x180025f4d  mov     rax, [rsp+48h+arg_10]
0x180025f52  xor     r9d, r9d; psidOwner
0x180025f55  mov     [rsp+48h+pSacl], 0; pSacl
0x180025f5e  mov     r8d, 80000004h; SecurityInfo
0x180025f64  mov     [rsp+48h+pDacl], rax; pDacl
0x180025f69  mov     rcx, rdi; pObjectName
0x180025f6c  mov     [rsp+48h+psidGroup], 0; psidGroup
0x180025f75  lea     edx, [r9+1]; ObjectType
0x180025f79  call    cs:__imp_SetNamedSecurityInfoW
0x180025f7f  mov     ebx, eax
0x180025f81  test    eax, eax
0x180025f83  jz      short loc_180025FD1
0x180025f85  jle     short loc_180025F90
0x180025f87  movzx   ebx, ax
0x180025f8a  or      ebx, 80070000h
0x180025f90  test    byte ptr cs:g_dwDebugFlags, 3
0x180025f97  jz      short loc_180025FD3
0x180025f99  mov     rcx, cs:g_pDebug
0x180025fa0  lea     rax, aSetsecurityonf; "[SetSecurityOnFile] Unable to set secur"...
0x180025fa7  mov     dword ptr [rsp+48h+pSacl], ebx
0x180025fab  lea     r9, aSetsecurityonf_1; "SetSecurityOnFile"
0x180025fb2  mov     [rsp+48h+pDacl], rdi
0x180025fb7  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x180025fbe  mov     r8d, 34ECh
0x180025fc4  mov     [rsp+48h+psidGroup], rax
0x180025fc9  call    cs:__imp_PuDbgPrintW
0x180025fcf  jmp     short loc_180025FD3
0x180025fd1  xor     ebx, ebx
0x180025fd3  mov     rcx, [rsp+48h+hMem]; hMem
0x180025fd8  test    rcx, rcx
0x180025fdb  jz      short loc_180025FE3
0x180025fdd  call    cs:__imp_LocalFree
0x180025fe3  mov     rsi, [rsp+48h+arg_8]
0x180025fe8  mov     eax, ebx
0x180025fea  mov     rbx, [rsp+48h+arg_0]
0x180025fef  add     rsp, 40h
0x180025ff3  pop     rdi
0x180025ff4  retn
```
