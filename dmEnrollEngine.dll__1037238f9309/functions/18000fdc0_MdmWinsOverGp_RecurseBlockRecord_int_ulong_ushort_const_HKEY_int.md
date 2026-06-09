# MdmWinsOverGp_RecurseBlockRecord(int,ulong,ushort const *,HKEY__ *,int *)

- ea: `0x18000fdc0`
- end: `0x1800103d8`
- name: `?MdmWinsOverGp_RecurseBlockRecord@@YAJHKPEBGPEAUHKEY__@@PEAH@Z`
- size: `1560`
- prototype: `int(int, unsigned int, const unsigned __int16 *, HKEY, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fdc0`
- `0x1800760a0`

## callees

- `0x1800071c0`
- `0x18000fdc0`
- `0x1800103e0`
- `0x180010dd4`
- `0x180010fcc`
- `0x1800118f8`
- `0x180011938`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18004e07c`
- `0x180059920`
- `0x180075f90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001010f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001010f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fe53`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fe53`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fea7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fea7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ff99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ffe5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001001d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001005d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800100ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010152`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001037b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ff99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ffe5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001001d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001005d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800100ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010152`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001037b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800102d9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000fef9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001024f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000fef9`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001024f`

## string_xrefs

- `0x18000ffd8`: `Delete`
- `0x18001036d`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmWinsOverGp_RecurseBlockRecord(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        HKEY a4,
        int *a5)
{
  DWORD v8; // edi
  int v9; // r15d
  int *v10; // r12
  LSTATUS v11; // eax
  DWORD v12; // r12d
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  LSTATUS v16; // eax
  int v17; // edx
  LSTATUS v18; // ebx
  unsigned int v19; // ecx
  WCHAR *p_Name; // rbx
  unsigned int ValueW; // eax
  int v22; // ecx
  int v23; // edi
  LSTATUS v24; // eax
  HLOCAL v25; // rbx
  unsigned int v26; // eax
  unsigned int v27; // edx
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  LSTATUS v32; // eax
  int v33; // edx
  int v34; // ecx
  __int64 v36; // rdx
  unsigned int lpReserved; // [rsp+20h] [rbp-E0h]
  int lpReserveda; // [rsp+20h] [rbp-E0h]
  WCHAR *lpReservedb; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v42; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwType; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v44; // [rsp+58h] [rbp-A8h] BYREF
  int *v45; // [rsp+60h] [rbp-A0h]
  int v46; // [rsp+68h] [rbp-98h] BYREF
  int pvData; // [rsp+6Ch] [rbp-94h] BYREF
  int v48; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+74h] [rbp-8Ch] BYREF
  HLOCAL v50; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v52[3]; // [rsp+84h] [rbp-7Ch] BYREF
  WCHAR Name; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v54[526]; // [rsp+92h] [rbp-6Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v45 = a5;
  memset_0(v54, 0, 0x206u);
  v8 = 0;
  v9 = 1;
  *a5 = 0;
  v10 = a5;
  while ( 1 )
  {
    do
    {
      while ( 1 )
      {
        cchName = 260;
        Name = 0;
        v46 = 0;
        v11 = RegEnumKeyExW(a4, v8, &Name, &cchName, 0, 0, 0, 0);
        if ( v11 )
        {
          if ( v11 == 259 && a2 == 3 )
          {
            if ( v9 )
            {
              LODWORD(hKey) = 4;
              v44 = 0;
              RegGetValueW(a4, &Name, L"Delete", 0x10u, 0, &v44, (LPDWORD)&hKey);
              *v10 = 1;
              if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
                McTemplateU0zz_EventWriteTransfer(
                  MDM_ENTERPRISE_DIAGNOSTICS_Context,
                  FoundBlockingRecordMarkedForDeletion,
                  a3,
                  &Name);
            }
          }
          return 0;
        }
        v44 = v8;
        v12 = v8++;
        LODWORD(hKey) = v8;
        if ( a2 >= 3 )
          break;
        hKey = 0;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v13 = RegOpenKeyExW(a4, &Name, 0, 0x2001Fu, &hKey);
        if ( v13 )
        {
          v15 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x36B,
                  (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
                  (const char *)v13,
                  lpReserved);
LABEL_54:
          if ( hKey )
            RegCloseKey(hKey);
          return v15;
        }
        v14 = MdmWinsOverGp_RecurseBlockRecord(1, a2 + 1, &Name, hKey, &v46);
        v15 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x36D,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
            (const char *)(unsigned int)v14,
            lpReserveda);
          goto LABEL_54;
        }
        if ( v46 )
        {
          *v45 = 1;
          v16 = RegDeleteKeyW(a4, &Name);
          v18 = v16;
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
          {
            if ( v16 > 0 )
              v19 = (unsigned __int16)v16 | 0x80070000;
            else
              v19 = v16;
            McTemplateU0zdd_EventWriteTransfer(v19, v17, (unsigned int)&Name, a2, v19);
          }
          if ( !v18 )
            v8 = v12;
        }
        v10 = v45;
        if ( hKey )
          RegCloseKey(hKey);
      }
      v10 = v45;
    }
    while ( a2 != 3 );
    pcbData = 4;
    pvData = 0;
    RegGetValueW(a4, 0, L"IsList", 0x10u, 0, &pvData, &pcbData);
    p_Name = &Name;
    if ( pvData )
      p_Name = 0;
    pcbData = 4;
    v52[0] = 0;
    RegGetValueW(a4, p_Name, L"Delete", 0x10u, 0, v52, &pcbData);
    pcbData = 4;
    v49 = 0;
    ValueW = RegGetValueW(a4, p_Name, L"StorageType", 0x10u, 0, &v49, &pcbData);
    if ( ValueW )
      break;
    pcbData = 4;
    v48 = 0;
    ValueW = RegGetValueW(a4, p_Name, L"Scope", 0x10u, 0, &v48, &pcbData);
    if ( ValueW )
    {
      v36 = 956;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v36,
               (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
               (const char *)ValueW,
               (unsigned int)lpReservedb);
    }
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        MDM_ENTERPRISE_DIAGNOSTICS_Context,
        FoundBlockingRecordMarkedForDeletion,
        a3,
        p_Name);
    v10 = v45;
    *v45 = 1;
    if ( a4 && a3 )
    {
      v23 = v49;
      pdwType = 0;
      v42 = 0;
      v24 = RegGetValueW(a4, &Name, L"Value", 0xFFFFu, &pdwType, 0, &v42);
      LODWORD(v25) = v24;
      if ( v24 > 0 )
        LODWORD(v25) = (unsigned __int16)v24 | 0x80070000;
      if ( (int)v25 >= 0 )
      {
        v25 = LocalAlloc(0, v42);
        v50 = v25;
        if ( v25 )
        {
          v26 = RegGetValueW(a4, &Name, L"Value", 0xFFFFu, 0, v25, &v42);
          if ( v26 )
          {
            LOBYTE(v25) = wil::details::in1diag3::Return_Win32(
                            retaddr,
                            (void *)0x11C,
                            (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
                            (const char *)v26,
                            (unsigned int)lpReservedb);
LABEL_40:
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
            goto LABEL_42;
          }
          if ( ((v23 - 1) & 0xFFFFFFFD) != 0 )
          {
            if ( v23 != 2
              || (v28 = MdmWinsOverGp_RestoreGPValueToDb((OLECHAR *)v25, v27, pdwType, a3, &Name),
                  LOBYTE(v25) = v28,
                  v28 >= 0) )
            {
LABEL_37:
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v50);
              LOBYTE(v25) = 0;
              goto LABEL_42;
            }
            v29 = (unsigned int)v28;
            v30 = 292;
          }
          else
          {
            lpReservedb = &Name;
            v31 = MdmWinsOverGp_RestoreGPValueToRegistry(v25, v42, pdwType, a3);
            LOBYTE(v25) = v31;
            if ( v31 >= 0 )
              goto LABEL_37;
            v29 = (unsigned int)v31;
            v30 = 288;
          }
        }
        else
        {
          LOBYTE(v25) = 14;
          v29 = 2147942414LL;
          v30 = 274;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
          (const char *)v29,
          (int)lpReservedb);
        goto LABEL_40;
      }
    }
    else
    {
      LOBYTE(v25) = 87;
    }
LABEL_42:
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
      McTemplateU0zzd_EventWriteTransfer(v22, (unsigned int)RestoredGpValue, (_DWORD)a3, (unsigned int)&Name, (char)v25);
    v32 = RegDeleteKeyW(a4, &Name);
    v15 = v32;
    if ( v32 > 0 )
      v15 = (unsigned __int16)v32 | 0x80070000;
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
      McTemplateU0zdd_EventWriteTransfer(v34, v33, (unsigned int)&Name, 3, v15);
    v8 = v44;
    if ( v15 )
      v8 = (unsigned int)hKey;
    if ( (v15 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3DC,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
        (const char *)v15,
        (int)lpReservedb);
      return v15;
    }
    v9 = 0;
  }
  v36 = 944;
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v36,
           (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
           (const char *)ValueW,
           (unsigned int)lpReservedb);
}

```

## disassembly

```asm
0x18000fdc0  mov     [rsp-8+arg_0], rbx
0x18000fdc5  push    rbp
0x18000fdc6  push    rsi
0x18000fdc7  push    rdi
0x18000fdc8  push    r12
0x18000fdca  push    r13
0x18000fdcc  push    r14
0x18000fdce  push    r15
0x18000fdd0  lea     rbp, [rsp-1B0h]
0x18000fdd8  sub     rsp, 2B0h
0x18000fddf  mov     rax, cs:__security_cookie
0x18000fde6  xor     rax, rsp
0x18000fde9  mov     [rbp+1E0h+var_40], rax
0x18000fdf0  mov     rsi, r9
0x18000fdf3  mov     r14, r8
0x18000fdf6  mov     r13d, edx
0x18000fdf9  mov     rbx, [rbp+1E0h+arg_20]
0x18000fe00  mov     [rsp+2E0h+var_280], rbx
0x18000fe05  xor     edx, edx; Val
0x18000fe07  mov     r8d, 206h; Size
0x18000fe0d  lea     rcx, [rbp+1E0h+var_24E]; void *
0x18000fe11  call    memset_0
0x18000fe16  xor     edi, edi
0x18000fe18  lea     r15d, [rdi+1]
0x18000fe1c  mov     [rbx], edi
0x18000fe1e  mov     r12, rbx
0x18000fe21  mov     [rbp+1E0h+cchName], 104h
0x18000fe28  xor     eax, eax
0x18000fe2a  mov     [rbp+1E0h+Name], ax
0x18000fe2e  mov     [rsp+2E0h+var_278], eax
0x18000fe32  mov     [rsp+2E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000fe37  mov     [rsp+2E0h+lpcchClass], rax; lpcchClass
0x18000fe3c  mov     [rsp+2E0h+lpClass], rax; lpClass
0x18000fe41  mov     [rsp+2E0h+lpReserved], rax; lpReserved
0x18000fe46  lea     r9, [rbp+1E0h+cchName]; lpcchName
0x18000fe4a  lea     r8, [rbp+1E0h+Name]; lpName
0x18000fe4e  mov     edx, edi; dwIndex
0x18000fe50  mov     rcx, rsi; hKey
0x18000fe53  call    cs:__imp_RegEnumKeyExW
0x18000fe59  test    eax, eax
0x18000fe5b  jnz     loc_18001032A
0x18000fe61  mov     [rsp+2E0h+var_288], edi
0x18000fe65  mov     r12d, edi
0x18000fe68  inc     edi
0x18000fe6a  mov     dword ptr [rsp+2E0h+hKey], edi
0x18000fe6e  cmp     r13d, 3
0x18000fe72  jnb     loc_18000FF4F
0x18000fe78  mov     [rsp+2E0h+hKey], 0
0x18000fe81  xor     edx, edx
0x18000fe83  lea     rcx, [rsp+2E0h+hKey]
0x18000fe88  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000fe8d  lea     rax, [rsp+2E0h+hKey]
0x18000fe92  mov     [rsp+2E0h+lpReserved], rax; unsigned int
0x18000fe97  mov     r9d, 2001Fh; samDesired
0x18000fe9d  xor     r8d, r8d; ulOptions
0x18000fea0  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x18000fea4  mov     rcx, rsi; hKey
0x18000fea7  call    cs:__imp_RegOpenKeyExW
0x18000fead  test    eax, eax
0x18000feaf  jnz     loc_1800102B2
0x18000feb5  lea     edx, [r13+1]; unsigned int
0x18000feb9  lea     rax, [rsp+2E0h+var_278]
0x18000febe  mov     [rsp+2E0h+lpReserved], rax; int
0x18000fec3  mov     r9, [rsp+2E0h+hKey]; HKEY
0x18000fec8  lea     r8, [rbp+1E0h+Name]; unsigned __int16 *
0x18000fecc  mov     ecx, 1; int
0x18000fed1  call    ?MdmWinsOverGp_RecurseBlockRecord@@YAJHKPEBGPEAUHKEY__@@PEAH@Z; MdmWinsOverGp_RecurseBlockRecord(int,ulong,ushort const *,HKEY__ *,int *)
0x18000fed6  mov     ebx, eax
0x18000fed8  test    eax, eax
0x18000feda  js      loc_180010295
0x18000fee0  cmp     [rsp+2E0h+var_278], 0
0x18000fee5  jz      short loc_18000FF31
0x18000fee7  mov     rax, [rsp+2E0h+var_280]
0x18000feec  mov     dword ptr [rax], 1
0x18000fef2  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x18000fef6  mov     rcx, rsi; hKey
0x18000fef9  call    cs:__imp_RegDeleteKeyW
0x18000feff  mov     ebx, eax
0x18000ff01  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18000ff08  jz      short loc_18000FF2B
0x18000ff0a  test    eax, eax
0x18000ff0c  jg      short loc_18000FF12
0x18000ff0e  mov     ecx, eax
0x18000ff10  jmp     short loc_18000FF1B
0x18000ff12  movzx   ecx, bx
0x18000ff15  or      ecx, 80070000h
0x18000ff1b  mov     dword ptr [rsp+2E0h+lpReserved], ecx
0x18000ff1f  mov     r9d, r13d
0x18000ff22  lea     r8, [rbp+1E0h+Name]
0x18000ff26  call    McTemplateU0zdd_EventWriteTransfer
0x18000ff2b  test    ebx, ebx
0x18000ff2d  cmovz   edi, r12d
0x18000ff31  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000ff36  test    rcx, rcx
0x18000ff39  mov     r12, [rsp+2E0h+var_280]
0x18000ff3e  jz      loc_18000FE21
0x18000ff44  call    cs:__imp_RegCloseKey
0x18000ff4a  jmp     loc_18000FE21
0x18000ff4f  mov     r12, [rsp+2E0h+var_280]
0x18000ff54  jnz     loc_18000FE21
0x18000ff5a  mov     [rsp+2E0h+pcbData], 4
0x18000ff62  mov     [rsp+2E0h+pvData], 0
0x18000ff6a  lea     rax, [rsp+2E0h+pcbData]
0x18000ff6f  mov     [rsp+2E0h+lpcchClass], rax; pcbData
0x18000ff74  lea     rax, [rsp+2E0h+pvData]
0x18000ff79  mov     [rsp+2E0h+lpClass], rax; pvData
0x18000ff7e  mov     [rsp+2E0h+lpReserved], 0; pdwType
0x18000ff87  mov     r9d, 10h; dwFlags
0x18000ff8d  lea     r8, aIslist; "IsList"
0x18000ff94  xor     edx, edx; lpSubKey
0x18000ff96  mov     rcx, rsi; hkey
0x18000ff99  call    cs:__imp_RegGetValueW
0x18000ff9f  xor     edi, edi
0x18000ffa1  lea     rbx, [rbp+1E0h+Name]
0x18000ffa5  cmp     [rsp+2E0h+pvData], edi
0x18000ffa9  cmovnz  rbx, rdi
0x18000ffad  lea     r15d, [rdi+4]
0x18000ffb1  mov     [rsp+2E0h+pcbData], r15d
0x18000ffb6  mov     [rbp+1E0h+var_25C], edi
0x18000ffb9  lea     rax, [rsp+2E0h+pcbData]
0x18000ffbe  mov     [rsp+2E0h+lpcchClass], rax; pcbData
0x18000ffc3  lea     rax, [rbp+1E0h+var_25C]
0x18000ffc7  mov     [rsp+2E0h+lpClass], rax; pvData
0x18000ffcc  mov     [rsp+2E0h+lpReserved], rdi; pdwType
0x18000ffd1  lea     r12d, [rdi+10h]
0x18000ffd5  mov     r9d, r12d; dwFlags
0x18000ffd8  lea     r8, aDelete; "Delete"
0x18000ffdf  mov     rdx, rbx; lpSubKey
0x18000ffe2  mov     rcx, rsi; hkey
0x18000ffe5  call    cs:__imp_RegGetValueW
0x18000ffeb  mov     [rsp+2E0h+pcbData], r15d
0x18000fff0  mov     [rsp+2E0h+var_26C], edi
0x18000fff4  lea     rax, [rsp+2E0h+pcbData]
0x18000fff9  mov     [rsp+2E0h+lpcchClass], rax; pcbData
0x18000fffe  lea     rax, [rsp+2E0h+var_26C]
0x180010003  mov     [rsp+2E0h+lpClass], rax; pvData
0x180010008  mov     [rsp+2E0h+lpReserved], rdi; unsigned int
0x18001000d  mov     r9d, r12d; dwFlags
0x180010010  lea     r8, aStoragetype; "StorageType"
0x180010017  mov     rdx, rbx; lpSubKey
0x18001001a  mov     rcx, rsi; hkey
0x18001001d  call    cs:__imp_RegGetValueW
0x180010023  test    eax, eax
0x180010025  jnz     loc_18001030A
0x18001002b  mov     [rsp+2E0h+pcbData], r15d
0x180010030  mov     [rsp+2E0h+var_270], edi
0x180010034  lea     rax, [rsp+2E0h+pcbData]
0x180010039  mov     [rsp+2E0h+lpcchClass], rax; pcbData
0x18001003e  lea     rax, [rsp+2E0h+var_270]
0x180010043  mov     [rsp+2E0h+lpClass], rax; pvData
0x180010048  mov     [rsp+2E0h+lpReserved], rdi; pdwType
0x18001004d  mov     r9d, r12d; dwFlags
0x180010050  lea     r8, aScope; "Scope"
0x180010057  mov     rdx, rbx; lpSubKey
0x18001005a  mov     rcx, rsi; hkey
0x18001005d  call    cs:__imp_RegGetValueW
0x180010063  test    eax, eax
0x180010065  jnz     loc_180010303
0x18001006b  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, r12b
0x180010072  jz      short loc_18001008D
0x180010074  mov     r9, rbx
0x180010077  mov     r8, r14
0x18001007a  lea     rdx, FoundBlockingRecordMarkedForDeletion
0x180010081  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x180010088  call    McTemplateU0zz_EventWriteTransfer
0x18001008d  mov     r12, [rsp+2E0h+var_280]
0x180010092  mov     dword ptr [r12], 1
0x18001009a  test    rsi, rsi
0x18001009d  jz      loc_180010223
0x1800100a3  test    r14, r14
0x1800100a6  jz      loc_180010223
0x1800100ac  mov     r15d, [rsp+2E0h+var_270]
0x1800100b1  mov     edi, [rsp+2E0h+var_26C]
0x1800100b5  xor     ecx, ecx
0x1800100b7  mov     [rsp+2E0h+pdwType], ecx
0x1800100bb  mov     [rsp+2E0h+var_290], ecx
0x1800100bf  lea     rax, [rsp+2E0h+var_290]
0x1800100c4  mov     [rsp+2E0h+lpcchClass], rax; pcbData
0x1800100c9  mov     [rsp+2E0h+lpClass], rcx; pvData
0x1800100ce  lea     rax, [rsp+2E0h+pdwType]
0x1800100d3  mov     [rsp+2E0h+lpReserved], rax; int
0x1800100d8  mov     r9d, 0FFFFh; dwFlags
0x1800100de  lea     r8, aValue_0; "Value"
0x1800100e5  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x1800100e9  mov     rcx, rsi; hkey
0x1800100ec  call    cs:__imp_RegGetValueW
0x1800100f2  mov     ebx, eax
0x1800100f4  test    eax, eax
0x1800100f6  jle     short loc_180010101
0x1800100f8  movzx   ebx, ax
0x1800100fb  or      ebx, 80070000h
0x180010101  test    ebx, ebx
0x180010103  js      loc_180010228
0x180010109  mov     edx, [rsp+2E0h+var_290]; uBytes
0x18001010d  xor     ecx, ecx; uFlags
0x18001010f  call    cs:__imp_LocalAlloc
0x180010115  mov     rbx, rax
0x180010118  mov     [rsp+2E0h+var_268], rax
0x18001011d  test    rax, rax
0x180010120  jz      loc_1800101F6
0x180010126  lea     rax, [rsp+2E0h+var_290]
0x18001012b  mov     [rsp+2E0h+lpcchClass], rax; pcbData
0x180010130  mov     [rsp+2E0h+lpClass], rbx; pvData
0x180010135  mov     [rsp+2E0h+lpReserved], 0; unsigned int
0x18001013e  mov     r9d, 0FFFFh; dwFlags
0x180010144  lea     r8, aValue_0; "Value"
0x18001014b  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x18001014f  mov     rcx, rsi; hkey
0x180010152  call    cs:__imp_RegGetValueW
0x180010158  test    eax, eax
0x18001015a  jz      short loc_18001017E
0x18001015c  mov     rcx, [rbp+1E8h]; this
0x180010163  mov     r9d, eax; char *
0x180010166  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x18001016d  mov     edx, 11Ch; void *
0x180010172  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010177  mov     ebx, eax
0x180010179  jmp     loc_180010217
0x18001017e  lea     eax, [rdi-1]
0x180010181  test    eax, 0FFFFFFFDh
0x180010186  jz      short loc_1800101B6
0x180010188  cmp     edi, 2
0x18001018b  jnz     short loc_1800101E8
0x18001018d  lea     rax, [rbp+1E0h+Name]
0x180010191  mov     [rsp+2E0h+lpReserved], rax; unsigned __int16 *
0x180010196  mov     r9, r14; unsigned __int16 *
0x180010199  mov     r8d, [rsp+2E0h+pdwType]; unsigned int
0x18001019e  mov     rcx, rbx; psz
0x1800101a1  call    ?MdmWinsOverGp_RestoreGPValueToDb@@YAJPEAXKKPEBG1@Z; MdmWinsOverGp_RestoreGPValueToDb(void *,ulong,ulong,ushort const *,ushort const *)
0x1800101a6  mov     ebx, eax
0x1800101a8  test    eax, eax
0x1800101aa  jns     short loc_1800101E8
0x1800101ac  mov     r9d, eax
0x1800101af  mov     edx, 124h
0x1800101b4  jmp     short loc_180010203
0x1800101b6  mov     dword ptr [rsp+2E0h+lpClass], r15d
0x1800101bb  lea     rax, [rbp+1E0h+Name]
0x1800101bf  mov     [rsp+2E0h+lpReserved], rax
0x1800101c4  mov     r9, r14
0x1800101c7  mov     r8d, [rsp+2E0h+pdwType]
0x1800101cc  mov     edx, [rsp+2E0h+var_290]
0x1800101d0  mov     rcx, rbx
0x1800101d3  call    ?MdmWinsOverGp_RestoreGPValueToRegistry@@YAJPEAXKKPEBG1W4PolicyScope@@@Z; MdmWinsOverGp_RestoreGPValueToRegistry(void *,ulong,ulong,ushort const *,ushort const *,PolicyScope)
0x1800101d8  mov     ebx, eax
0x1800101da  test    eax, eax
0x1800101dc  jns     short loc_1800101E8
0x1800101de  mov     r9d, eax
0x1800101e1  mov     edx, 120h
0x1800101e6  jmp     short loc_180010203
0x1800101e8  lea     rcx, [rsp+2E0h+var_268]
0x1800101ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800101f2  xor     ebx, ebx
0x1800101f4  jmp     short loc_180010228
0x1800101f6  mov     ebx, 8007000Eh
0x1800101fb  mov     r9d, ebx; char *
0x1800101fe  mov     edx, 112h; void *
0x180010203  mov     rcx, [rbp+1E8h]; this
0x18001020a  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x180010211  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010216  nop
0x180010217  lea     rcx, [rsp+2E0h+var_268]
0x18001021c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010221  jmp     short loc_180010228
0x180010223  mov     ebx, 80070057h
0x180010228  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18001022f  jz      short loc_180010248
0x180010231  mov     dword ptr [rsp+2E0h+lpReserved], ebx
0x180010235  lea     r9, [rbp+1E0h+Name]
0x180010239  mov     r8, r14
0x18001023c  lea     rdx, RestoredGpValue
0x180010243  call    McTemplateU0zzd_EventWriteTransfer
0x180010248  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x18001024c  mov     rcx, rsi; hKey
0x18001024f  call    cs:__imp_RegDeleteKeyW
0x180010255  mov     ebx, eax
0x180010257  test    eax, eax
0x180010259  jle     short loc_180010264
0x18001025b  movzx   ebx, ax
0x18001025e  or      ebx, 80070000h
0x180010264  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18001026b  jz      short loc_180010280
0x18001026d  mov     dword ptr [rsp+2E0h+lpReserved], ebx; int
0x180010271  mov     r9d, 3
0x180010277  lea     r8, [rbp+1E0h+Name]
0x18001027b  call    McTemplateU0zdd_EventWriteTransfer
0x180010280  mov     edi, [rsp+2E0h+var_288]
0x180010284  test    ebx, ebx
0x180010286  cmovnz  edi, dword ptr [rsp+2E0h+hKey]
0x18001028b  js      short loc_1800102E6
0x18001028d  xor     r15d, r15d
0x180010290  jmp     loc_18000FE21
0x180010295  mov     rcx, [rbp+1E8h]; this
0x18001029c  mov     r9d, ebx; char *
0x18001029f  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x1800102a6  mov     edx, 36Dh; void *
0x1800102ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800102b0  jmp     short loc_1800102CF
0x1800102b2  mov     rcx, [rbp+1E8h]; this
0x1800102b9  mov     r9d, eax; char *
0x1800102bc  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
  ... truncated ...
```
