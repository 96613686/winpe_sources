# Mso::Telemetry::Configuration::Details::Environment::ConfigServiceReturnedTrueForSetting(Mso::OfficeWebServiceApi::ConfigToken::Token)

- ea: `0x18013bb80`
- end: `0x18013bd58`
- name: `?ConfigServiceReturnedTrueForSetting@Environment@Details@Configuration@Telemetry@Mso@@KA_NW4Token@ConfigToken@OfficeWebServiceApi@5@@Z`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18013b8c0`
- `0x18013b8d0`

## callees

- `0x180008f14`
- `0x18003e690`
- `0x18003f5a0`
- `0x1800409e0`
- `0x18013bb80`
- `0x180146090`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013bcdb`
- `KERNEL32!GetLastError` at `0x18013bcdb`
- `KERNEL32!CompareStringEx` at `0x18013bc86`
- `KERNEL32!CompareStringEx` at `0x18013bcd1`
- `KERNEL32!CompareStringEx` at `0x18013bc86`
- `KERNEL32!CompareStringEx` at `0x18013bcd1`

## pseudocode

```c
char __fastcall Mso::Telemetry::Configuration::Details::Environment::ConfigServiceReturnedTrueForSetting(
        unsigned int a1)
{
  void ***v2; // rcx
  unsigned __int64 v3; // rdi
  int cchCount2; // ebx
  int v5; // eax
  char v6; // si
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  int pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v12; // [rsp+54h] [rbp-ACh]
  DWORD LastError; // [rsp+254h] [rbp+154h]
  __int16 v14; // [rsp+258h] [rbp+158h]
  __int16 v15; // [rsp+358h] [rbp+258h]
  int v16; // [rsp+3D8h] [rbp+2D8h]
  WCHAR String1[2088]; // [rsp+3E0h] [rbp+2E0h] BYREF

  memset(String1, 0, 0x1048u);
  v2 = (void ***)qword_18021D8C0;
  if ( !qword_18021D8C0 )
  {
    v2 = off_180213960;
    qword_18021D8C0 = (__int64)off_180213960;
  }
  if ( ((unsigned int (__fastcall *)(void ***, __int64, _QWORD, WCHAR *, int))(*v2)[7])(
         v2,
         509206978,
         a1,
         String1,
         2084)
    || !String1[0] )
  {
    return 0;
  }
  v3 = -1;
  do
    ++v3;
  while ( String1[v3] );
  cchCount2 = OcfxInt32FromSize_t(4u);
  v5 = OcfxInt32FromSize_t(v3);
  v6 = 1;
  v7 = CompareStringEx(&LocaleName, 1u, String1, v5, L"true", cchCount2, 0, 0, 0);
  if ( !v7 )
  {
    v8 = OcfxInt32FromSize_t(4u);
    v9 = OcfxInt32FromSize_t(v3);
    v7 = CompareStringEx(L"en-US", 1u, String1, v9, L"true", v8, 0, 0, 0);
    if ( !v7 )
    {
      pExceptionObject = 15;
      LastError = GetLastError();
      v16 = 808464432;
      v15 = 0;
      v14 = 0;
      v12 = 0;
      throw (OException *)&pExceptionObject;
    }
  }
  if ( v7 != 2 )
    return 0;
  return v6;
}

```

## disassembly

```asm
0x18013bb80  mov     rax, rsp
0x18013bb83  mov     [rax+10h], rbx
0x18013bb87  mov     [rax+18h], rsi
0x18013bb8b  mov     [rax+20h], rdi
0x18013bb8f  push    rbp
0x18013bb90  push    r12
0x18013bb92  push    r14
0x18013bb94  lea     rbp, [rax-1358h]
0x18013bb9b  mov     eax, 1440h
0x18013bba0  call    _alloca_probe
0x18013bba5  sub     rsp, rax
0x18013bba8  mov     rax, cs:__security_cookie
0x18013bbaf  xor     rax, rsp
0x18013bbb2  mov     [rbp+1350h+var_20], rax
0x18013bbb9  mov     ebx, ecx
0x18013bbbb  xor     edx, edx; Val
0x18013bbbd  mov     r8d, 1048h; Size
0x18013bbc3  lea     rcx, [rbp+1350h+String1]; void *
0x18013bbca  call    memset
0x18013bbcf  mov     rcx, cs:qword_18021D8C0
0x18013bbd6  xor     r14d, r14d
0x18013bbd9  test    rcx, rcx
0x18013bbdc  jnz     short loc_18013BBEC
0x18013bbde  lea     rcx, off_180213960
0x18013bbe5  mov     cs:qword_18021D8C0, rcx
0x18013bbec  mov     rax, [rcx]
0x18013bbef  mov     dword ptr [rsp+1450h+lpString2], 824h
0x18013bbf7  lea     r9, [rbp+1350h+String1]
0x18013bbfe  mov     r8d, ebx
0x18013bc01  mov     edx, 1E59E1C2h
0x18013bc06  mov     rax, [rax+38h]
0x18013bc0a  call    cs:__guard_dispatch_icall_fptr
0x18013bc10  test    eax, eax
0x18013bc12  jnz     loc_18013BD26
0x18013bc18  cmp     r14w, [rbp+1350h+String1]
0x18013bc20  jz      loc_18013BD26
0x18013bc26  lea     rax, [rbp+1350h+String1]
0x18013bc2d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18013bc31  inc     rdi
0x18013bc34  cmp     [rax+rdi*2], r14w
0x18013bc39  jnz     short loc_18013BC31
0x18013bc3b  mov     ecx, 4; unsigned __int64
0x18013bc40  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18013bc45  mov     ebx, eax
0x18013bc47  mov     rcx, rdi; unsigned __int64
0x18013bc4a  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18013bc4f  mov     [rsp+1450h+lParam], r14; lParam
0x18013bc54  mov     [rsp+1450h+lpReserved], r14; lpReserved
0x18013bc59  mov     [rsp+1450h+lpVersionInformation], r14; lpVersionInformation
0x18013bc5e  mov     [rsp+1450h+cchCount2], ebx; cchCount2
0x18013bc62  lea     r12, aTrue; "true"
0x18013bc69  mov     [rsp+1450h+lpString2], r12; lpString2
0x18013bc6e  mov     r9d, eax; cchCount1
0x18013bc71  lea     r8, [rbp+1350h+String1]; lpString1
0x18013bc78  mov     esi, 1
0x18013bc7d  mov     edx, esi; dwCmpFlags
0x18013bc7f  lea     rcx, LocaleName; lpLocaleName
0x18013bc86  call    cs:__imp_CompareStringEx
0x18013bc8c  test    eax, eax
0x18013bc8e  jnz     loc_18013BD21
0x18013bc94  lea     ecx, [rsi+3]; unsigned __int64
0x18013bc97  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18013bc9c  mov     ebx, eax
0x18013bc9e  mov     rcx, rdi; unsigned __int64
0x18013bca1  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18013bca6  mov     [rsp+1450h+lParam], r14; lParam
0x18013bcab  mov     [rsp+1450h+lpReserved], r14; lpReserved
0x18013bcb0  mov     [rsp+1450h+lpVersionInformation], r14; lpVersionInformation
0x18013bcb5  mov     [rsp+1450h+cchCount2], ebx; cchCount2
0x18013bcb9  mov     [rsp+1450h+lpString2], r12; lpString2
0x18013bcbe  mov     r9d, eax; cchCount1
0x18013bcc1  lea     r8, [rbp+1350h+String1]; lpString1
0x18013bcc8  mov     edx, esi; dwCmpFlags
0x18013bcca  lea     rcx, aEnUs; "en-US"
0x18013bcd1  call    cs:__imp_CompareStringEx
0x18013bcd7  test    eax, eax
0x18013bcd9  jnz     short loc_18013BD21
0x18013bcdb  call    cs:__imp_GetLastError
0x18013bce1  mov     [rsp+1450h+pExceptionObject], 0Fh
0x18013bce9  mov     [rbp+1350h+var_11FC], eax
0x18013bcef  mov     [rbp+1350h+var_1078], 30303030h
0x18013bcf9  mov     [rbp+1350h+var_10F8], r14w
0x18013bd01  mov     [rbp+1350h+var_11F8], r14w
0x18013bd09  mov     [rsp+1450h+var_13FC], r14w
0x18013bd0f  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18013bd16  lea     rcx, [rsp+1450h+pExceptionObject]; pExceptionObject
0x18013bd1b  call    _CxxThrowException
0x18013bd21  add     eax, 0FFFFFFFEh
0x18013bd24  jz      short loc_18013BD29
0x18013bd26  mov     sil, r14b
0x18013bd29  mov     al, sil
0x18013bd2c  mov     rcx, [rbp+1350h+var_20]
0x18013bd33  xor     rcx, rsp; StackCookie
0x18013bd36  call    __security_check_cookie
0x18013bd3b  lea     r11, [rsp+1450h+var_10]
0x18013bd43  mov     rbx, [r11+28h]
0x18013bd47  mov     rsi, [r11+30h]
0x18013bd4b  mov     rdi, [r11+38h]
0x18013bd4f  mov     rsp, r11
0x18013bd52  pop     r14
0x18013bd54  pop     r12
0x18013bd56  pop     rbp
0x18013bd57  retn
```
