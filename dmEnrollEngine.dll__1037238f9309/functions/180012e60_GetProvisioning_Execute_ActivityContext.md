# GetProvisioning::Execute(ActivityContext *)

- ea: `0x180012e60`
- end: `0x1800132e4`
- name: `?Execute@GetProvisioning@@UEAAJPEAVActivityContext@@@Z`
- size: `1156`
- prototype: `int(GetProvisioning *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000de50`
- `0x18000e0d0`
- `0x180010600`
- `0x180012e60`
- `0x18001390c`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001e4c4`
- `0x18001f98c`
- `0x18002e1a0`
- `0x18003ebe0`
- `0x180041420`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800130e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180013101`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800130e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180013101`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012f8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012f74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001329b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012f74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012fb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001329b`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180013010`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x1800130c2`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180013287`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180013010`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x1800130c2`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180013287`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180012fcf`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180012fcf`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetProvisioning::Execute(GetProvisioning *this, struct ActivityContext *a2)
{
  int v3; // r12d
  _QWORD *v4; // r15
  _QWORD *v5; // r14
  _QWORD *v6; // rsi
  int KeyAsString; // ebx
  HKEY v8; // rcx
  HKEY v9; // rcx
  LSTATUS v10; // eax
  int v11; // edx
  __int64 v12; // r8
  const unsigned __int16 *CorrelationID; // r9
  __int64 v14; // rcx
  const unsigned __int16 *v15; // r8
  __int64 v16; // r8
  EEDBManager *v17; // rcx
  HKEY phkResult; // [rsp+C0h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp-78h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  unsigned __int16 *v23; // [rsp+D8h] [rbp-68h] BYREF
  unsigned __int16 *v24; // [rsp+E0h] [rbp-60h] BYREF
  int v25; // [rsp+E8h] [rbp-58h]
  int v26; // [rsp+ECh] [rbp-54h]
  struct _GUID v27; // [rsp+F0h] [rbp-50h] BYREF
  struct _GUID v28; // [rsp+100h] [rbp-40h] BYREF
  struct _GUID v29; // [rsp+110h] [rbp-30h] BYREF
  __int64 v30; // [rsp+120h] [rbp-20h] BYREF
  __int64 v31; // [rsp+128h] [rbp-18h] BYREF
  void *v32[2]; // [rsp+130h] [rbp-10h] BYREF
  char v33; // [rsp+140h] [rbp+0h]
  WCHAR SubKey[40]; // [rsp+150h] [rbp+10h] BYREF
  unsigned __int16 v35[264]; // [rsp+1A0h] [rbp+60h] BYREF

  v22 = *((_DWORD *)a2 + 12);
  v30 = *((_QWORD *)a2 + 7);
  v31 = *((_QWORD *)a2 + 8);
  v3 = 0;
  v23 = 0;
  v32[0] = 0;
  v24 = 0;
  phkResult = 0;
  v21 = 0;
  v26 = *((_DWORD *)a2 + 73);
  v25 = *((_DWORD *)a2 + 72);
  if ( *((_QWORD *)a2 + 39) )
  {
    v4 = (_QWORD *)((char *)a2 + 296);
    if ( *((_QWORD *)a2 + 40) > 7u )
      v4 = (_QWORD *)*v4;
  }
  else
  {
    v4 = 0;
  }
  if ( *((_QWORD *)a2 + 43) )
  {
    v5 = (_QWORD *)((char *)a2 + 328);
    if ( *((_QWORD *)a2 + 44) > 7u )
      v5 = (_QWORD *)*v5;
  }
  else
  {
    v5 = 0;
  }
  if ( *((_QWORD *)a2 + 47) )
  {
    v6 = (_QWORD *)((char *)a2 + 360);
    if ( *((_QWORD *)a2 + 48) > 7u )
      v6 = (_QWORD *)*v6;
  }
  else
  {
    v6 = 0;
  }
  KeyAsString = ActivityContext::get_KeyAsString(a2, SubKey);
  if ( KeyAsString < 0 )
    goto LABEL_14;
  hKey = 0;
  KeyAsString = EEDBManager::OpenEnrollmentsHKEY(0x2001Fu, &hKey);
  v9 = hKey;
  if ( KeyAsString < 0 )
  {
    hKey = 0;
LABEL_17:
    if ( v9 )
      RegCloseKey(v9);
    goto LABEL_14;
  }
  v10 = RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, &phkResult);
  KeyAsString = v10;
  if ( v10 > 0 )
    KeyAsString = (unsigned __int16)v10 | 0x80070000;
  v9 = hKey;
  hKey = 0;
  if ( KeyAsString < 0 )
    goto LABEL_17;
  if ( v9 )
    RegCloseKey(v9);
  KeyAsString = OmaDmRegistrySetString(phkResult, 0, L"EnrollmentID", SubKey);
  if ( KeyAsString < 0 )
    goto LABEL_14;
  v32[1] = &phkResult;
  v33 = 1;
  v29 = *(struct _GUID *)((char *)a2 + 8);
  KeyAsString = EEDBManager::GetEnrollmentAuthPolicy(&v29, (enum MDMAuthPolicy *)&v21);
  if ( KeyAsString < 0 )
  {
    OmaDmRegistryDeleteValue(phkResult, 0, L"EnrollmentID");
LABEL_14:
    v8 = phkResult;
    phkResult = 0;
    goto LABEL_42;
  }
  *(_QWORD *)&v29.Data1 = 0;
  v28 = *(struct _GUID *)((char *)a2 + 8);
  EEDBManager::GetEnrollmentString(&v28, L"SID", (unsigned __int16 **)&v29);
  *(_QWORD *)&v28.Data1 = 0;
  v27 = *(struct _GUID *)((char *)a2 + 8);
  EEDBManager::GetEnrollmentEntDmId(&v27, (unsigned __int16 **)&v28);
  if ( (unsigned int)(v21 - 1) <= 1
    || (v27 = *(struct _GUID *)((char *)a2 + 8), EEDBManager::GetEnrollmentString(&v27, L"DomainUsername", &v23) < 0) )
  {
    v27 = *(struct _GUID *)((char *)a2 + 8);
    KeyAsString = EEDBManager::GetEnrollmentString(&v27, L"UPN", &v23);
    if ( KeyAsString < 0 )
    {
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v28);
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v29);
      OmaDmRegistryDeleteValue(phkResult, 0, L"EnrollmentID");
      goto LABEL_14;
    }
  }
  LOBYTE(v3) = (unsigned int)_o__wcsnicmp((char *)a2 + 448) == 0;
  _o__wcsnicmp((char *)a2 + 448);
  CorrelationID = ActivityContext::get_CorrelationID(a2);
  if ( *((_QWORD *)a2 + 32) == v12 )
  {
    v14 = (unsigned int)v12;
  }
  else
  {
    v14 = (__int64)a2 + 240;
    if ( *((_QWORD *)a2 + 33) > 7u )
      v14 = *(_QWORD *)v14;
  }
  v15 = (const unsigned __int16 *)((char *)a2 + 112);
  if ( *((_QWORD *)a2 + 17) > 7u )
    v15 = *(const unsigned __int16 **)v15;
  KeyAsString = GetProvisioning(
                  *(__int64 *)&v29.Data1,
                  (__int64)phkResult,
                  v15,
                  (__int64)v23,
                  *((_QWORD *)a2 + 5),
                  v14,
                  v21,
                  v3,
                  v11,
                  *(__int64 *)&v28.Data1,
                  *((_QWORD *)a2 + 34),
                  *((_DWORD *)a2 + 70),
                  v26,
                  v25,
                  (__int64)v4,
                  (__int64)v5,
                  (__int64)v6,
                  *((_DWORD *)a2 + 18),
                  (__int64)CorrelationID,
                  (__int64)&v22,
                  (__int64)&v30,
                  (__int64)&v31,
                  v35,
                  &v24);
  *((_DWORD *)a2 + 12) = v22;
  *((_QWORD *)a2 + 7) = v30;
  v16 = -1;
  do
    ++v16;
  while ( v35[v16] );
  std::wstring::_Assign<unsigned short>((char *)a2 + 144, v35, v16);
  *((_QWORD *)a2 + 8) = v31;
  if ( v24 )
  {
    v27 = *(struct _GUID *)((char *)a2 + 8);
    EEDBManager::SetErrorContext(v17, &v27, v24);
  }
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v28);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v29);
  OmaDmRegistryDeleteValue(phkResult, 0, L"EnrollmentID");
  v8 = phkResult;
  phkResult = 0;
LABEL_42:
  if ( v8 )
    RegCloseKey(v8);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v24);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(v32);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v23);
  return (unsigned int)KeyAsString;
}

```

## disassembly

```asm
0x180012e60  push    rbp
0x180012e62  push    rbx
0x180012e63  push    rsi
0x180012e64  push    rdi
0x180012e65  push    r12
0x180012e67  push    r13
0x180012e69  push    r14
0x180012e6b  push    r15
0x180012e6d  lea     rbp, [rsp-288h]
0x180012e75  sub     rsp, 3C8h
0x180012e7c  mov     rax, cs:__security_cookie
0x180012e83  xor     rax, rsp
0x180012e86  mov     [rbp+2C0h+var_50], rax
0x180012e8d  mov     rdi, rdx
0x180012e90  mov     eax, [rdx+30h]
0x180012e93  mov     [rbp+2C0h+var_32C], eax
0x180012e96  mov     rax, [rdx+38h]
0x180012e9a  mov     [rbp+2C0h+var_2E0], rax
0x180012e9e  mov     rax, [rdx+40h]
0x180012ea2  mov     [rbp+2C0h+var_2D8], rax
0x180012ea6  xor     r12d, r12d
0x180012ea9  mov     [rbp+2C0h+var_328], r12
0x180012ead  mov     [rbp+2C0h+var_2D0], r12
0x180012eb1  mov     [rbp+2C0h+var_320], r12
0x180012eb5  mov     [rbp+2C0h+var_340], r12
0x180012eb9  mov     [rbp+2C0h+var_330], r12d
0x180012ebd  mov     eax, [rdx+124h]
0x180012ec3  mov     [rbp+2C0h+var_314], eax
0x180012ec6  mov     eax, [rdx+120h]
0x180012ecc  mov     [rbp+2C0h+var_318], eax
0x180012ecf  cmp     [rdx+138h], r12
0x180012ed6  jnz     short loc_180012EDD
0x180012ed8  mov     r15d, r12d
0x180012edb  jmp     short loc_180012EEE
0x180012edd  lea     r15, [rdx+128h]
0x180012ee4  cmp     qword ptr [r15+18h], 7
0x180012ee9  jbe     short loc_180012EEE
0x180012eeb  mov     r15, [r15]
0x180012eee  cmp     [rdx+158h], r12
0x180012ef5  jnz     short loc_180012EFC
0x180012ef7  mov     r14, r12
0x180012efa  jmp     short loc_180012F0D
0x180012efc  lea     r14, [rdx+148h]
0x180012f03  cmp     qword ptr [r14+18h], 7
0x180012f08  jbe     short loc_180012F0D
0x180012f0a  mov     r14, [r14]
0x180012f0d  cmp     [rdx+178h], r12
0x180012f14  jnz     short loc_180012F1B
0x180012f16  mov     rsi, r12
0x180012f19  jmp     short loc_180012F2C
0x180012f1b  lea     rsi, [rdx+168h]
0x180012f22  cmp     qword ptr [rsi+18h], 7
0x180012f27  jbe     short loc_180012F2C
0x180012f29  mov     rsi, [rsi]
0x180012f2c  lea     rdx, [rbp+2C0h+SubKey]; unsigned __int16 *
0x180012f30  mov     rcx, rdi; this
0x180012f33  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x180012f38  mov     ebx, eax
0x180012f3a  test    eax, eax
0x180012f3c  jns     short loc_180012F4B
0x180012f3e  mov     rcx, [rbp+2C0h+var_340]
0x180012f42  mov     [rbp+2C0h+var_340], r12
0x180012f46  jmp     loc_180013296
0x180012f4b  mov     [rbp+2C0h+hKey], r12
0x180012f4f  lea     rdx, [rbp+2C0h+hKey]; HKEY *
0x180012f53  mov     r13d, 2001Fh
0x180012f59  mov     ecx, r13d; unsigned int
0x180012f5c  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x180012f61  mov     ebx, eax
0x180012f63  mov     rcx, [rbp+2C0h+hKey]; hKey
0x180012f67  test    eax, eax
0x180012f69  jns     short loc_180012F7C
0x180012f6b  mov     [rbp+2C0h+hKey], r12
0x180012f6f  test    rcx, rcx
0x180012f72  jz      short loc_180012F3E
0x180012f74  call    cs:__imp_RegCloseKey
0x180012f7a  jmp     short loc_180012F3E
0x180012f7c  lea     rax, [rbp+2C0h+var_340]
0x180012f80  mov     [rsp+400h+phkResult], rax; phkResult
0x180012f85  mov     r9d, r13d; samDesired
0x180012f88  xor     r8d, r8d; ulOptions
0x180012f8b  lea     rdx, [rbp+2C0h+SubKey]; lpSubKey
0x180012f8f  call    cs:__imp_RegOpenKeyExW
0x180012f95  mov     ebx, eax
0x180012f97  test    eax, eax
0x180012f99  jle     short loc_180012FA4
0x180012f9b  movzx   ebx, ax
0x180012f9e  or      ebx, 80070000h
0x180012fa4  mov     rcx, [rbp+2C0h+hKey]; hKey
0x180012fa8  mov     [rbp+2C0h+hKey], r12
0x180012fac  test    ebx, ebx
0x180012fae  js      short loc_180012F6F
0x180012fb0  test    rcx, rcx
0x180012fb3  jz      short loc_180012FBB
0x180012fb5  call    cs:__imp_RegCloseKey
0x180012fbb  lea     r9, [rbp+2C0h+SubKey]
0x180012fbf  lea     r13, aEnrollmentid; "EnrollmentID"
0x180012fc6  mov     r8, r13
0x180012fc9  xor     edx, edx
0x180012fcb  mov     rcx, [rbp+2C0h+var_340]
0x180012fcf  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180012fd5  mov     ebx, eax
0x180012fd7  test    eax, eax
0x180012fd9  js      loc_180012F3E
0x180012fdf  lea     rax, [rbp+2C0h+var_340]
0x180012fe3  mov     [rbp+2C0h+var_2C8], rax
0x180012fe7  mov     [rbp+2C0h+var_2C0], 1
0x180012feb  movups  xmm0, xmmword ptr [rdi+8]
0x180012fef  movdqu  xmmword ptr [rbp+2C0h+var_2F0.Data1], xmm0
0x180012ff4  lea     rdx, [rbp+2C0h+var_330]; enum MDMAuthPolicy *
0x180012ff8  lea     rcx, [rbp+2C0h+var_2F0]; struct _GUID
0x180012ffc  call    ?GetEnrollmentAuthPolicy@EEDBManager@@SAJU_GUID@@PEAW4MDMAuthPolicy@@@Z; EEDBManager::GetEnrollmentAuthPolicy(_GUID,MDMAuthPolicy *)
0x180013001  mov     ebx, eax
0x180013003  test    eax, eax
0x180013005  jns     short loc_18001301C
0x180013007  mov     r8, r13
0x18001300a  xor     edx, edx
0x18001300c  mov     rcx, [rbp+2C0h+var_340]
0x180013010  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180013016  nop
0x180013017  jmp     loc_180012F3E
0x18001301c  mov     qword ptr [rbp+2C0h+var_2F0.Data1], r12
0x180013020  movups  xmm0, xmmword ptr [rdi+8]
0x180013024  movdqu  xmmword ptr [rbp+2C0h+var_300.Data1], xmm0
0x180013029  lea     r8, [rbp+2C0h+var_2F0]; unsigned __int16 **
0x18001302d  lea     rdx, aSid; "SID"
0x180013034  lea     rcx, [rbp+2C0h+var_300]; struct _GUID
0x180013038  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18001303d  mov     qword ptr [rbp+2C0h+var_300.Data1], r12
0x180013041  movups  xmm0, xmmword ptr [rdi+8]
0x180013045  movdqu  xmmword ptr [rbp+2C0h+var_310.Data1], xmm0
0x18001304a  lea     rdx, [rbp+2C0h+var_300]; unsigned __int16 **
0x18001304e  lea     rcx, [rbp+2C0h+var_310]; struct _GUID
0x180013052  call    ?GetEnrollmentEntDmId@EEDBManager@@SAJU_GUID@@PEAPEAG@Z; EEDBManager::GetEnrollmentEntDmId(_GUID,ushort * *)
0x180013057  mov     eax, [rbp+2C0h+var_330]
0x18001305a  dec     eax
0x18001305c  cmp     eax, 1
0x18001305f  jbe     short loc_180013082
0x180013061  movups  xmm0, xmmword ptr [rdi+8]
0x180013065  movdqu  xmmword ptr [rbp+2C0h+var_310.Data1], xmm0
0x18001306a  lea     r8, [rbp+2C0h+var_328]; unsigned __int16 **
0x18001306e  lea     rdx, aDomainusername; "DomainUsername"
0x180013075  lea     rcx, [rbp+2C0h+var_310]; struct _GUID
0x180013079  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18001307e  test    eax, eax
0x180013080  jns     short loc_1800130CE
0x180013082  movups  xmm0, xmmword ptr [rdi+8]
0x180013086  movdqu  xmmword ptr [rbp+2C0h+var_310.Data1], xmm0
0x18001308b  lea     r8, [rbp+2C0h+var_328]; unsigned __int16 **
0x18001308f  lea     rdx, aUpn; "UPN"
0x180013096  lea     rcx, [rbp+2C0h+var_310]; struct _GUID
0x18001309a  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18001309f  mov     ebx, eax
0x1800130a1  test    eax, eax
0x1800130a3  jns     short loc_1800130CE
0x1800130a5  lea     rcx, [rbp+2C0h+var_300]
0x1800130a9  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800130ae  nop
0x1800130af  lea     rcx, [rbp+2C0h+var_2F0]
0x1800130b3  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800130b8  nop
0x1800130b9  mov     r8, r13
0x1800130bc  xor     edx, edx
0x1800130be  mov     rcx, [rbp+2C0h+var_340]
0x1800130c2  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x1800130c8  nop
0x1800130c9  jmp     loc_180012F3E
0x1800130ce  lea     rbx, [rdi+1C0h]
0x1800130d5  mov     r13d, 104h
0x1800130db  mov     r8d, r13d
0x1800130de  mov     rdx, cs:off_1800AF248; "OR_RENEW"
0x1800130e5  mov     rcx, rbx
0x1800130e8  call    cs:__imp__o__wcsnicmp
0x1800130ee  test    eax, eax
0x1800130f0  setz    r12b
0x1800130f4  mov     r8d, r13d
0x1800130f7  mov     rdx, cs:off_1800AF2C8; "OR_MDMRECOVERY"
0x1800130fe  mov     rcx, rbx
0x180013101  call    cs:__imp__o__wcsnicmp
0x180013107  xor     r8d, r8d
0x18001310a  mov     edx, r8d
0x18001310d  test    eax, eax
0x18001310f  setz    dl
0x180013112  mov     rcx, rdi; this
0x180013115  call    ?get_CorrelationID@ActivityContext@@QEBAPEBGXZ; ActivityContext::get_CorrelationID(void)
0x18001311a  mov     r9, rax
0x18001311d  mov     r10d, [rdi+48h]
0x180013121  mov     r11d, [rdi+118h]
0x180013128  mov     rbx, [rdi+110h]
0x18001312f  cmp     [rdi+100h], r8
0x180013136  jnz     short loc_18001313D
0x180013138  mov     ecx, r8d
0x18001313b  jmp     short loc_18001314E
0x18001313d  lea     rcx, [rdi+0F0h]
0x180013144  cmp     qword ptr [rcx+18h], 7
0x180013149  jbe     short loc_18001314E
0x18001314b  mov     rcx, [rcx]
0x18001314e  mov     rax, [rdi+28h]
0x180013152  lea     r8, [rdi+70h]
0x180013156  cmp     qword ptr [r8+18h], 7
0x18001315b  jbe     short loc_180013160
0x18001315d  mov     r8, [r8]
0x180013160  lea     r13, [rbp+2C0h+var_320]
0x180013164  mov     [rsp+400h+var_348], r13
0x18001316c  lea     r13, [rbp+2C0h+var_260]
0x180013170  mov     [rsp+400h+var_350], r13
0x180013178  lea     r13, [rbp+2C0h+var_2D8]
0x18001317c  mov     [rsp+400h+var_358], r13
0x180013184  lea     r13, [rbp+2C0h+var_2E0]
0x180013188  mov     [rsp+400h+var_360], r13
0x180013190  lea     r13, [rbp+2C0h+var_32C]
0x180013194  mov     [rsp+400h+var_368], r13
0x18001319c  mov     [rsp+400h+var_370], r9
0x1800131a4  mov     [rsp+400h+var_378], r10d
0x1800131ac  mov     [rsp+400h+var_380], rsi
0x1800131b4  mov     [rsp+400h+var_388], r14
0x1800131b9  mov     [rsp+400h+var_390], r15
0x1800131be  mov     r9d, [rbp+2C0h+var_318]
0x1800131c2  mov     [rsp+400h+var_398], r9d
0x1800131c7  mov     r9d, [rbp+2C0h+var_314]
0x1800131cb  mov     [rsp+400h+var_3A0], r9d
0x1800131d0  mov     [rsp+400h+var_3A8], r11d
0x1800131d5  mov     [rsp+400h+var_3B0], rbx
0x1800131da  mov     r13, qword ptr [rbp+2C0h+var_300.Data1]
0x1800131de  mov     [rsp+400h+var_3B8], r13
0x1800131e3  mov     [rsp+400h+var_3C0], edx
0x1800131e7  mov     [rsp+400h+var_3C8], r12d
0x1800131ec  mov     edx, [rbp+2C0h+var_330]
0x1800131ef  mov     [rsp+400h+var_3D0], edx
0x1800131f3  mov     [rsp+400h+var_3D8], rcx
0x1800131f8  mov     [rsp+400h+phkResult], rax
0x1800131fd  mov     r9, [rbp+2C0h+var_328]
0x180013201  mov     rdx, [rbp+2C0h+var_340]
0x180013205  mov     rcx, qword ptr [rbp+2C0h+var_2F0.Data1]
0x180013209  call    ?GetProvisioning@@YAJPEBGPEAUHKEY__@@0000W4MDMAuthPolicy@@HH0PEAPEAGKKK000K0PEAK33QEAG3@Z; GetProvisioning(ushort const *,HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,MDMAuthPolicy,int,int,ushort const *,ushort * *,ulong,ulong,ulong,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ulong *,ushort * *,ushort * *,ushort * const,ushort * *)
0x18001320e  mov     ebx, eax
0x180013210  mov     ecx, [rbp+2C0h+var_32C]
0x180013213  mov     [rdi+30h], ecx
0x180013216  mov     rcx, [rbp+2C0h+var_2E0]
0x18001321a  mov     [rdi+38h], rcx
0x18001321e  lea     rax, [rbp+2C0h+var_260]
0x180013222  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013226  xor     esi, esi
0x180013228  inc     r8
0x18001322b  cmp     [rax+r8*2], si
0x180013230  jnz     short loc_180013228
0x180013232  lea     rcx, [rdi+90h]
0x180013239  lea     rdx, [rbp+2C0h+var_260]
0x18001323d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180013242  mov     rax, [rbp+2C0h+var_2D8]
0x180013246  mov     [rdi+40h], rax
0x18001324a  mov     r8, [rbp+2C0h+var_320]; unsigned __int16 *
0x18001324e  test    r8, r8
0x180013251  jz      short loc_180013266
0x180013253  movups  xmm0, xmmword ptr [rdi+8]
0x180013257  movdqu  xmmword ptr [rbp+2C0h+var_310.Data1], xmm0
0x18001325c  lea     rdx, [rbp+2C0h+var_310]; struct _GUID
0x180013260  call    ?SetErrorContext@EEDBManager@@QEAAJU_GUID@@PEBG@Z; EEDBManager::SetErrorContext(_GUID,ushort const *)
0x180013265  nop
0x180013266  lea     rcx, [rbp+2C0h+var_300]
0x18001326a  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18001326f  nop
0x180013270  lea     rcx, [rbp+2C0h+var_2F0]
0x180013274  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180013279  nop
0x18001327a  lea     r8, aEnrollmentid; "EnrollmentID"
0x180013281  xor     edx, edx
0x180013283  mov     rcx, [rbp+2C0h+var_340]
0x180013287  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x18001328d  nop
0x18001328e  mov     rcx, [rbp+2C0h+var_340]; hKey
0x180013292  mov     [rbp+2C0h+var_340], rsi
0x180013296  test    rcx, rcx
0x180013299  jz      short loc_1800132A2
0x18001329b  call    cs:__imp_RegCloseKey
0x1800132a1  nop
0x1800132a2  lea     rcx, [rbp+2C0h+var_320]
0x1800132a6  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800132ab  nop
0x1800132ac  lea     rcx, [rbp+2C0h+var_2D0]
0x1800132b0  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800132b5  nop
0x1800132b6  lea     rcx, [rbp+2C0h+var_328]
0x1800132ba  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x1800132bf  mov     eax, ebx
0x1800132c1  mov     rcx, [rbp+2C0h+var_50]
0x1800132c8  xor     rcx, rsp; StackCookie
0x1800132cb  call    __security_check_cookie
0x1800132d0  add     rsp, 3C8h
0x1800132d7  pop     r15
0x1800132d9  pop     r14
0x1800132db  pop     r13
0x1800132dd  pop     r12
0x1800132df  pop     rdi
0x1800132e0  pop     rsi
0x1800132e1  pop     rbx
0x1800132e2  pop     rbp
0x1800132e3  retn
```
