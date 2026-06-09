# Microsoft::FoundationServices::Common::Registry::Read<ushort>(ushort const *,ushort *,ulong *,ulong)

- ea: `0x180052a30`
- end: `0x180052d4f`
- name: `??$Read@G@Registry@Common@FoundationServices@Microsoft@@QEAAXPEBGPEAGPEAKK@Z`
- size: `799`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180053d94`

## callees

- `0x180001284`
- `0x18000343a`
- `0x180015438`
- `0x1800516b8`
- `0x180052a30`
- `0x180053c68`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052be4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052b06`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180052b06`

## string_xrefs

- `0x180052a74`: `CLSID`
- `0x180052cf0`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\str_t.h`
- `0x180052c02`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\registry.h`
- `0x180052c42`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\registry.h`
- `0x180052c80`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\registry.h`
- `0x180052cb8`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\registry.h`
- `0x180052d2c`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\utils\registry.h`
- `0x180052bf5`: `nTypeRead == nType && *pcchOut > 0 && *pcchOut % sizeof (T) == 0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::FoundationServices::Common::Registry::Read<unsigned short>(
        HKEY *a1,
        __int64 a2,
        BYTE *lpData,
        unsigned int *lpcbData)
{
  __int64 v7; // rdx
  const WCHAR *v8; // rax
  unsigned int v9; // r14d
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  LSTATUS Value; // edi
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  __int64 v15; // r8
  __int64 result; // rax
  unsigned int v17; // r9d
  DWORD LastError; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  DWORD Type[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C8h]
  const WCHAR *v24; // [rsp+48h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B8h]
  _BYTE pExceptionObject[1216]; // [rsp+58h] [rbp-B0h] BYREF

  v23 = -2;
  v7 = 0x3FFF;
  v8 = L"CLSID";
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  if ( !v7 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\registry.h",
      0x89u,
      L"0 == pszValueName || SUCCEEDED(StringCchLength(pszValueName, CCH_MAX_REG_VALUE_NAME, 0))",
      -2147024809);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  if ( !lpcbData )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\registry.h",
      0x8Bu,
      L"pcchOut",
      -2147024809);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  Type[0] = 0;
  v9 = *lpcbData;
  if ( !is_mul_ok(2u, *lpcbData) )
    goto LABEL_33;
  *lpcbData *= 2;
  v24 = L"CLSID";
  v25 = 0;
  v10 = 0x7FFFFFFF;
  v11 = L"CLSID";
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( !v10 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\str_t.h",
      0x4Eu,
      L"!m_pwsz || SUCCEEDED(StringCchLength(m_pwsz, cchMaxLength, 0))",
      -2147024809);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  Value = RegQueryValueExW(*a1, L"CLSID", 0, Type, lpData, lpcbData);
  operator delete(0);
  if ( !Value || Value == 234 )
  {
    if ( Type[0] != 1 || (v13 = *lpcbData) == 0 || (v13 & 1) != 0 )
    {
      LastError = GetLastError();
      v19 = HR_FROM_WIN32(LastError);
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\registry.h",
        0x9Cu,
        L"nTypeRead == nType && *pcchOut > 0 && *pcchOut % sizeof (T) == 0",
        v19);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
    v14 = v13 >> 1;
    *lpcbData = v14;
    if ( Value == 234 )
    {
      *lpcbData = v14 + 1;
LABEL_32:
      v20 = HR_FROM_WIN32(Value);
      Microsoft::FoundationServices::Common::FsException::FsException(
        (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
        L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\registry.h",
        0xA7u,
        L"lr",
        v20);
      throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
    }
  }
  if ( Value )
    goto LABEL_32;
  v15 = *lpcbData;
  if ( !lpData )
  {
    result = v15 + 1;
    if ( (unsigned __int64)(v15 + 1) <= 0xFFFFFFFF )
    {
      *lpcbData = result;
      return result;
    }
    goto LABEL_33;
  }
  if ( (_DWORD)v15 )
  {
    result = (unsigned int)(v15 - 1);
    if ( !*(_WORD *)&lpData[2 * result] )
      return result;
  }
  v17 = v15 + 1;
  if ( (int)v15 + 1 < (unsigned int)v15 )
LABEL_33:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  *lpcbData = v17;
  if ( v17 > v9 )
  {
    v21 = HR_FROM_WIN32(0xEAu);
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\utils\\registry.h",
      0xEDu,
      &Src,
      v21);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  for ( result = 1; (unsigned int)result <= 1; result = (unsigned int)(result + 1) )
  {
    if ( (unsigned int)result > v17 )
      goto LABEL_33;
    *(_WORD *)&lpData[2 * (v17 - (unsigned int)result)] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180052a30  mov     rax, rsp
0x180052a33  push    rbp
0x180052a34  push    rsi
0x180052a35  push    rdi
0x180052a36  push    r14
0x180052a38  push    r15
0x180052a3a  lea     rbp, [rax-448h]
0x180052a41  sub     rsp, 520h
0x180052a48  mov     [rsp+540h+var_508], 0FFFFFFFFFFFFFFFEh
0x180052a51  mov     [rax+10h], rbx
0x180052a55  mov     rax, cs:__security_cookie
0x180052a5c  xor     rax, rsp
0x180052a5f  mov     [rbp+440h+var_30], rax
0x180052a66  mov     rbx, r9
0x180052a69  mov     rsi, r8
0x180052a6c  mov     r10, rcx
0x180052a6f  mov     edx, 3FFFh
0x180052a74  lea     r11, aClsid; "CLSID"
0x180052a7b  mov     rax, r11
0x180052a7e  xor     r15d, r15d
0x180052a81  cmp     [rax], r15w
0x180052a85  jz      short loc_180052A91
0x180052a87  add     rax, 2
0x180052a8b  sub     rdx, 1
0x180052a8f  jnz     short loc_180052A81
0x180052a91  test    rdx, rdx
0x180052a94  jz      loc_180052C6B
0x180052a9a  test    rbx, rbx
0x180052a9d  jz      loc_180052CA3
0x180052aa3  mov     [rsp+540h+Type], r15d
0x180052aa8  mov     r14d, [r9]
0x180052aab  mov     ecx, r14d
0x180052aae  add     rcx, rcx
0x180052ab1  mov     rax, rcx
0x180052ab4  shr     rax, 20h
0x180052ab8  test    eax, eax
0x180052aba  jnz     loc_180052C65
0x180052ac0  mov     [r9], ecx
0x180052ac3  mov     [rsp+540h+var_500], r11
0x180052ac8  mov     [rsp+540h+var_4F8], r15
0x180052acd  mov     eax, 7FFFFFFFh
0x180052ad2  mov     rcx, r11
0x180052ad5  cmp     [rcx], r15w
0x180052ad9  jz      short loc_180052AE5
0x180052adb  add     rcx, 2
0x180052adf  sub     rax, 1
0x180052ae3  jnz     short loc_180052AD5
0x180052ae5  test    rax, rax
0x180052ae8  jz      loc_180052CDB
0x180052aee  mov     [rsp+540h+lpcbData], rbx; lpcbData
0x180052af3  mov     [rsp+540h+lpData], rsi; lpData
0x180052af8  lea     r9, [rsp+540h+Type]; lpType
0x180052afd  xor     r8d, r8d; lpReserved
0x180052b00  mov     rdx, r11; lpValueName
0x180052b03  mov     rcx, [r10]; hKey
0x180052b06  call    cs:__imp_RegQueryValueExW
0x180052b0c  mov     edi, eax
0x180052b0e  xor     ecx, ecx; Block
0x180052b10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180052b15  mov     r10d, 0EAh
0x180052b1b  test    edi, edi
0x180052b1d  jz      short loc_180052B24
0x180052b1f  cmp     edi, r10d
0x180052b22  jnz     short loc_180052B4F
0x180052b24  cmp     [rsp+540h+Type], 1
0x180052b29  jnz     loc_180052BE4
0x180052b2f  mov     ecx, [rbx]
0x180052b31  test    ecx, ecx
0x180052b33  jz      loc_180052BE4
0x180052b39  test    cl, 1
0x180052b3c  jnz     loc_180052BE4
0x180052b42  shr     ecx, 1
0x180052b44  mov     [rbx], ecx
0x180052b46  cmp     edi, r10d
0x180052b49  jz      loc_180052C25
0x180052b4f  test    edi, edi
0x180052b51  jnz     loc_180052C2A
0x180052b57  mov     r8d, [rbx]
0x180052b5a  test    rsi, rsi
0x180052b5d  jz      short loc_180052BAA
0x180052b5f  cmp     r8d, 1
0x180052b63  jb      short loc_180052B70
0x180052b65  lea     eax, [r8-1]
0x180052b69  cmp     r15w, [rsi+rax*2]
0x180052b6e  jz      short loc_180052BBE
0x180052b70  lea     r9d, [r8+1]
0x180052b74  cmp     r9d, r8d
0x180052b77  jb      loc_180052C65
0x180052b7d  mov     [rbx], r9d
0x180052b80  cmp     r9d, r14d
0x180052b83  ja      loc_180052D13
0x180052b89  mov     eax, 1
0x180052b8e  cmp     eax, 1
0x180052b91  ja      short loc_180052BBE
0x180052b93  cmp     eax, r9d
0x180052b96  ja      loc_180052C65
0x180052b9c  mov     ecx, r9d
0x180052b9f  sub     ecx, eax
0x180052ba1  mov     [rsi+rcx*2], r15w
0x180052ba6  inc     eax
0x180052ba8  jmp     short loc_180052B8E
0x180052baa  lea     rax, [r8+1]
0x180052bae  mov     ecx, 0FFFFFFFFh
0x180052bb3  cmp     rax, rcx
0x180052bb6  ja      loc_180052C65
0x180052bbc  mov     [rbx], eax
0x180052bbe  mov     rcx, [rbp+440h+var_30]
0x180052bc5  xor     rcx, rsp; StackCookie
0x180052bc8  call    __security_check_cookie
0x180052bcd  mov     rbx, [rsp+540h+arg_8]
0x180052bd5  add     rsp, 520h
0x180052bdc  pop     r15
0x180052bde  pop     r14
0x180052be0  pop     rdi
0x180052be1  pop     rsi
0x180052be2  pop     rbp
0x180052be3  retn
0x180052be4  call    cs:__imp_GetLastError
0x180052bea  mov     ecx, eax; unsigned int
0x180052bec  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180052bf1  mov     dword ptr [rsp+540h+lpData], eax; int
0x180052bf5  lea     r9, aNtypereadNtype; "nTypeRead == nType && *pcchOut > 0 && *"...
0x180052bfc  mov     r8d, 9Ch; unsigned int
0x180052c02  lea     rdx, aDsSecurityRmSr_2; "ds\\security\\rm\\src\\client\\promethi"...
0x180052c09  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180052c0e  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052c13  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052c1a  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x180052c1f  call    _CxxThrowException_0
0x180052c25  lea     eax, [rcx+1]
0x180052c28  mov     [rbx], eax
0x180052c2a  mov     ecx, edi; unsigned int
0x180052c2c  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180052c31  mov     dword ptr [rsp+540h+lpData], eax; int
0x180052c35  lea     r9, aLr; "lr"
0x180052c3c  mov     r8d, 0A7h; unsigned int
0x180052c42  lea     rdx, aDsSecurityRmSr_2; "ds\\security\\rm\\src\\client\\promethi"...
0x180052c49  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180052c4e  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052c53  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052c5a  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x180052c5f  call    _CxxThrowException_0
0x180052c65  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180052c6b  mov     dword ptr [rsp+540h+lpData], 80070057h; int
0x180052c73  lea     r9, a0PszvaluenameS; "0 == pszValueName || SUCCEEDED(StringCc"...
0x180052c7a  mov     r8d, 89h; unsigned int
0x180052c80  lea     rdx, aDsSecurityRmSr_2; "ds\\security\\rm\\src\\client\\promethi"...
0x180052c87  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180052c8c  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052c91  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052c98  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x180052c9d  call    _CxxThrowException_0
0x180052ca3  mov     dword ptr [rsp+540h+lpData], 80070057h; int
0x180052cab  lea     r9, aPcchout; "pcchOut"
0x180052cb2  mov     r8d, 8Bh; unsigned int
0x180052cb8  lea     rdx, aDsSecurityRmSr_2; "ds\\security\\rm\\src\\client\\promethi"...
0x180052cbf  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180052cc4  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052cc9  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052cd0  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x180052cd5  call    _CxxThrowException_0
0x180052cdb  mov     dword ptr [rsp+540h+lpData], 80070057h; int
0x180052ce3  lea     r9, aMPwszSucceeded; "!m_pwsz || SUCCEEDED(StringCchLength(m_"...
0x180052cea  mov     r8d, 4Eh ; 'N'; unsigned int
0x180052cf0  lea     rdx, aDsSecurityRmSr_8; "ds\\security\\rm\\src\\client\\promethi"...
0x180052cf7  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180052cfc  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052d01  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052d08  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x180052d0d  call    _CxxThrowException_0
0x180052d13  mov     ecx, r10d; unsigned int
0x180052d16  call    ?HR_FROM_WIN32@@YAJK@Z; HR_FROM_WIN32(ulong)
0x180052d1b  mov     dword ptr [rsp+540h+lpData], eax; int
0x180052d1f  lea     r9, Src; unsigned __int16 *
0x180052d26  mov     r8d, 0EDh; unsigned int
0x180052d2c  lea     rdx, aDsSecurityRmSr_2; "ds\\security\\rm\\src\\client\\promethi"...
0x180052d33  lea     rcx, [rsp+540h+pExceptionObject]; this
0x180052d38  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180052d3d  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180052d44  lea     rcx, [rsp+540h+pExceptionObject]; pExceptionObject
0x180052d49  call    _CxxThrowException_0
```
