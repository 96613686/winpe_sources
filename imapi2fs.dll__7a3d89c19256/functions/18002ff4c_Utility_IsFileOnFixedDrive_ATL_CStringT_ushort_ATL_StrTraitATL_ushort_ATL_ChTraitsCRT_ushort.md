# Utility::IsFileOnFixedDrive(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18002ff4c`
- end: `0x18003008a`
- name: `?IsFileOnFixedDrive@Utility@@SA_NAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005ff0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18001b974`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18002ff4c`
- `0x180081750`

## import_xrefs

- `KERNEL32!GetDriveTypeW` at `0x180030065`
- `KERNEL32!GetDriveTypeW` at `0x180030065`
- `KERNEL32!GetVolumePathNameW` at `0x18002ff7b`
- `KERNEL32!GetVolumePathNameW` at `0x18002ff7b`
- `KERNEL32!GetLastError` at `0x18002ffd7`
- `KERNEL32!GetLastError` at `0x18002ffd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall Utility::IsFileOnFixedDrive(LPCWSTR *a1)
{
  CIMAPISystemException *v2; // rax
  CIMAPISystemException *v3; // rbx
  DWORD LastError; // eax
  CIMAPIException **v5; // rbx
  CIMAPISystemException *pExceptionObject; // [rsp+20h] [rbp-298h] BYREF
  CIMAPIException **v8; // [rsp+28h] [rbp-290h] BYREF
  _BYTE v9[96]; // [rsp+30h] [rbp-288h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+90h] [rbp-228h] BYREF

  if ( !GetVolumePathNameW(*a1, szVolumePathName, 0x104u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_4a1263e1fdae307c29234b23c923e679_Traceguids, *a1);
    }
    v2 = (CIMAPISystemException *)operator new(0x58u);
    v3 = v2;
    pExceptionObject = v2;
    if ( v2 )
    {
      LastError = GetLastError();
      v2 = CIMAPISystemException::CIMAPISystemException(v3, LastError);
    }
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v8, v2);
    v5 = v8;
    if ( v8 && *v8 )
    {
      CIMAPIException::SetCodeRefInfo(*v8, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiutil.cpp", 686);
      pExceptionObject = (CIMAPISystemException *)v5;
      if ( v5 )
        ++*((_DWORD *)v5 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v9, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v9;
  }
  return GetDriveTypeW(szVolumePathName) == 3;
}

```

## disassembly

```asm
0x18002ff4c  push    rbx
0x18002ff4e  sub     rsp, 2B0h
0x18002ff55  mov     rax, cs:__security_cookie
0x18002ff5c  xor     rax, rsp
0x18002ff5f  mov     [rsp+2B8h+var_18], rax
0x18002ff67  mov     rbx, rcx
0x18002ff6a  mov     r8d, 104h; cchBufferLength
0x18002ff70  lea     rdx, [rsp+2B8h+szVolumePathName]; lpszVolumePathName
0x18002ff78  mov     rcx, [rcx]; lpszFileName
0x18002ff7b  call    cs:__imp_GetVolumePathNameW
0x18002ff81  test    eax, eax
0x18002ff83  jnz     loc_18003005D
0x18002ff89  lea     rax, WPP_GLOBAL_Control
0x18002ff90  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff97  cmp     rcx, rax
0x18002ff9a  jz      short loc_18002FFC0
0x18002ff9c  test    byte ptr [rcx+44h], 4
0x18002ffa0  jz      short loc_18002FFC0
0x18002ffa2  cmp     byte ptr [rcx+41h], 2
0x18002ffa6  jb      short loc_18002FFC0
0x18002ffa8  mov     edx, 1Fh
0x18002ffad  mov     r9, [rbx]
0x18002ffb0  lea     r8, WPP_4a1263e1fdae307c29234b23c923e679_Traceguids
0x18002ffb7  mov     rcx, [rcx+38h]
0x18002ffbb  call    WPP_SF_S
0x18002ffc0  mov     ecx, 58h ; 'X'; unsigned __int64
0x18002ffc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ffca  mov     rbx, rax
0x18002ffcd  mov     [rsp+2B8h+pExceptionObject], rax
0x18002ffd2  test    rax, rax
0x18002ffd5  jz      short loc_18002FFE8
0x18002ffd7  call    cs:__imp_GetLastError
0x18002ffdd  mov     edx, eax; int
0x18002ffdf  mov     rcx, rbx; this
0x18002ffe2  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18002ffe7  nop
0x18002ffe8  mov     rdx, rax
0x18002ffeb  lea     rcx, [rsp+2B8h+var_290]
0x18002fff0  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18002fff5  nop
0x18002fff6  mov     rbx, [rsp+2B8h+var_290]
0x18002fffb  test    rbx, rbx
0x18002fffe  jz      short loc_18003003A
0x180030000  cmp     qword ptr [rbx], 0
0x180030004  jz      short loc_18003003A
0x180030006  mov     r8d, 2AEh; int
0x18003000c  lea     rdx, aDriversStorage_2; "drivers\\storage\\imapi2\\filesystemima"...
0x180030013  mov     rcx, [rbx]; this
0x180030016  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003001b  mov     [rsp+2B8h+pExceptionObject], rbx
0x180030020  test    rbx, rbx
0x180030023  jz      short loc_180030028
0x180030025  inc     dword ptr [rbx+8]
0x180030028  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003002f  lea     rcx, [rsp+2B8h+pExceptionObject]; pExceptionObject
0x180030034  call    _CxxThrowException_0
0x18003003a  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180030041  lea     rcx, [rsp+2B8h+var_288]; this
0x180030046  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003004b  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180030052  lea     rcx, [rsp+2B8h+var_288]; pExceptionObject
0x180030057  call    _CxxThrowException_0
0x18003005d  lea     rcx, [rsp+2B8h+szVolumePathName]; lpRootPathName
0x180030065  call    cs:__imp_GetDriveTypeW
0x18003006b  cmp     eax, 3
0x18003006e  setz    al
0x180030071  mov     rcx, [rsp+2B8h+var_18]
0x180030079  xor     rcx, rsp; StackCookie
0x18003007c  call    __security_check_cookie
0x180030081  add     rsp, 2B0h
0x180030088  pop     rbx
0x180030089  retn
```
