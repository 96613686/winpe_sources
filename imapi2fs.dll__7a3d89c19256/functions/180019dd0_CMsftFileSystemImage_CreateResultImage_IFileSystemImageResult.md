# CMsftFileSystemImage::CreateResultImage(IFileSystemImageResult * *)

- ea: `0x180019dd0`
- end: `0x18001a0ba`
- name: `?CreateResultImage@CMsftFileSystemImage@@UEAAJPEAPEAUIFileSystemImageResult@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(CMsftFileSystemImage *__hidden this, struct IFileSystemImageResult **)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000c8d0`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x180019dd0`
- `0x18001a0c0`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180043c04`
- `0x180043f0c`
- `0x180077f7c`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180019e27`
- `KERNEL32!GetTickCount` at `0x180019eac`
- `KERNEL32!GetTickCount` at `0x180019e27`
- `KERNEL32!GetTickCount` at `0x180019eac`

## string_xrefs

- `0x180019ded`: `CMsftFileSystemImage::CreateResultImage`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMsftFileSystemImage::CreateResultImage(
        CMsftFileSystemImage *this,
        struct IFileSystemImageResult **a2)
{
  unsigned int v4; // edi
  DWORD TickCount; // r12d
  unsigned int v6; // r15d
  __int64 v7; // rbx
  CIMAPISystemException *v8; // rax
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  unsigned int v11; // eax
  unsigned int v12; // edx
  __int64 v13; // rcx
  unsigned int v14; // eax
  int v15; // r8d
  unsigned int v17; // [rsp+30h] [rbp-F8h]
  CIMAPIException **pExceptionObject; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v19[8]; // [rsp+88h] [rbp-A0h] BYREF
  _BYTE v20[152]; // [rsp+90h] [rbp-98h] BYREF
  CIMAPIException **v21; // [rsp+138h] [rbp+10h] BYREF
  CIMAPIException **v22; // [rsp+140h] [rbp+18h] BYREF
  char *v23; // [rsp+148h] [rbp+20h]

  MethodTrace::MethodTrace((MethodTrace *)v19, "CMsftFileSystemImage::CreateResultImage");
  ImapiClearErrorInfo();
  v23 = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
  try
  {
    v4 = 0;
    if ( !a2 )
    {
      v8 = (CIMAPISystemException *)operator new(0x58u);
      v21 = (CIMAPIException **)v8;
      if ( v8 )
        v9 = CIMAPIException::CIMAPIException(v8, -2147467261, L"resultStream");
      else
        v9 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v21, v9);
      v10 = v21;
      if ( v21 && *v21 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v21,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          495);
        pExceptionObject = v10;
        if ( v10 )
          ++*((_DWORD *)v10 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v20,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v20;
    }
    TickCount = GetTickCount();
    *a2 = 0;
    *(_BYTE *)(**((_QWORD **)this + 26) + 393LL) = 1;
    FileSystemImage::BuildResultObject(**((FileSystemImage ***)this + 26));
    v6 = 11186527;
    if ( *(_BYTE *)(**((_QWORD **)this + 26) + 393LL) )
      v6 = 0;
    v21 = v22;
    if ( v22 )
      ++*((_DWORD *)v22 + 2);
    *a2 = (struct IFileSystemImageResult *)CreateReturnObject<IFileSystemImageResult,CFileSystemImageResult>(
                                             this,
                                             (CIMAPISystemException **)&v21);
    v7 = **((_QWORD **)this + 26);
    *(_DWORD *)(v7 + 808) += GetTickCount() - TickCount;
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v22);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_MsftFileSystemImage);
  }
  v11 = FileSystemImage::CalcImageSize(**((FileSystemImage ***)this + 26));
  v12 = v11;
  if ( !*((_BYTE *)this + 220) && v11 >= 0x200 )
  {
    v13 = **((_QWORD **)this + 26);
    v14 = *(unsigned __int8 *)(v13 + 792);
    v15 = *(_DWORD *)(v13 + 720);
    if ( v15 )
    {
      v4 = (int)((double)v15 / (double)(v15 + *(_DWORD *)(v13 + 696)) * 100.0);
      v14 = *(unsigned __int8 *)(v13 + 792);
    }
    Imapi2Utility::SQMLogFSImageSession(
      (Imapi2Utility *)*(unsigned int *)(v13 + 368),
      *(_DWORD *)(v13 + 372),
      *(_DWORD *)(v13 + 376),
      v4,
      *(_DWORD *)(v13 + 380),
      v12,
      v17,
      v14,
      *(_DWORD *)(v13 + 24),
      *(enum FsiFileSystems *)(v13 + 32),
      *(unsigned __int8 *)(v13 + 392),
      v6,
      *((_DWORD *)this + 54),
      *(_DWORD *)(v13 + 812),
      *(_DWORD *)(v13 + 808));
    *((_BYTE *)this + 220) = 1;
  }
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)v19);
  return v6;
}

```

## disassembly

```asm
0x180019dd0  mov     [rsp+arg_0], rcx
0x180019dd5  push    rbx
0x180019dd6  push    rsi
0x180019dd7  push    rdi
0x180019dd8  push    r12
0x180019dda  push    r13
0x180019ddc  push    r14
0x180019dde  push    r15
0x180019de0  sub     rsp, 0F0h
0x180019de7  mov     rbx, rdx
0x180019dea  mov     rsi, rcx
0x180019ded  lea     rdx, aCmsftfilesyste_39; "CMsftFileSystemImage::CreateResultImage"
0x180019df4  lea     rcx, [rsp+128h+var_A0]; this
0x180019dfc  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180019e01  nop
0x180019e02  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180019e07  nop
0x180019e08  lea     r14, [rsi+50h]
0x180019e0c  mov     [rsp+128h+arg_18], r14
0x180019e14  mov     rcx, r14; this
0x180019e17  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180019e1c  xor     edi, edi
0x180019e1e  test    rbx, rbx
0x180019e21  jz      loc_180019ECE
0x180019e27  call    cs:__imp_GetTickCount
0x180019e2d  mov     r12d, eax
0x180019e30  mov     [rbx], rdi
0x180019e33  mov     rcx, [rsi+0D0h]
0x180019e3a  mov     rdx, [rcx]
0x180019e3d  mov     byte ptr [rdx+189h], 1
0x180019e44  mov     rcx, [rsi+0D0h]
0x180019e4b  lea     rdx, [rsp+128h+arg_10]
0x180019e53  mov     rcx, [rcx]; this
0x180019e56  call    ?BuildResultObject@FileSystemImage@@QEAA?AV?$SmartClassPtr@VFileSystemImageResult@@VImapiImplementation@@@@XZ; FileSystemImage::BuildResultObject(void)
0x180019e5b  nop
0x180019e5c  mov     rax, [rsi+0D0h]
0x180019e63  mov     rcx, [rax]
0x180019e66  mov     r15d, 0AAB15Fh
0x180019e6c  cmp     [rcx+189h], dil
0x180019e73  cmovnz  r15d, edi
0x180019e77  mov     rax, [rsp+128h+arg_10]
0x180019e7f  mov     [rsp+128h+arg_8], rax
0x180019e87  test    rax, rax
0x180019e8a  jz      short loc_180019E8F
0x180019e8c  inc     dword ptr [rax+8]
0x180019e8f  lea     rdx, [rsp+128h+arg_8]
0x180019e97  mov     rcx, rsi
0x180019e9a  call    ??$CreateReturnObject@UIFileSystemImageResult@@VCFileSystemImageResult@@@@YAPEAUIFileSystemImageResult@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; CreateReturnObject<IFileSystemImageResult,CFileSystemImageResult>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x180019e9f  mov     [rbx], rax
0x180019ea2  mov     rax, [rsi+0D0h]
0x180019ea9  mov     rbx, [rax]
0x180019eac  call    cs:__imp_GetTickCount
0x180019eb2  sub     eax, r12d
0x180019eb5  add     [rbx+328h], eax
0x180019ebb  lea     rcx, [rsp+128h+arg_10]; void *
0x180019ec3  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180019ec8  nop
0x180019ec9  jmp     loc_180019F9D
0x180019ece  mov     ecx, 58h ; 'X'; unsigned __int64
0x180019ed3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019ed8  mov     [rsp+128h+arg_8], rax
0x180019ee0  test    rax, rax
0x180019ee3  jz      short loc_180019EFB
0x180019ee5  lea     r8, aResultstream; "resultStream"
0x180019eec  mov     edx, 80004003h; int
0x180019ef1  mov     rcx, rax; this
0x180019ef4  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180019ef9  jmp     short loc_180019EFE
0x180019efb  mov     rax, rdi
0x180019efe  mov     rdx, rax
0x180019f01  lea     rcx, [rsp+128h+arg_8]
0x180019f09  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180019f0e  nop
0x180019f0f  mov     rbx, [rsp+128h+arg_8]
0x180019f17  test    rbx, rbx
0x180019f1a  jz      short loc_180019F5A
0x180019f1c  cmp     [rbx], rdi
0x180019f1f  jz      short loc_180019F5A
0x180019f21  mov     r8d, 1EFh; int
0x180019f27  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180019f2e  mov     rcx, [rbx]; this
0x180019f31  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180019f36  mov     [rsp+128h+pExceptionObject], rbx
0x180019f3e  test    rbx, rbx
0x180019f41  jz      short loc_180019F46
0x180019f43  inc     dword ptr [rbx+8]
0x180019f46  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180019f4d  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180019f55  call    _CxxThrowException_0
0x180019f5a  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180019f61  lea     rcx, [rsp+128h+var_98]; this
0x180019f69  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180019f6e  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180019f75  lea     rcx, [rsp+128h+var_98]; pExceptionObject
0x180019f7d  call    _CxxThrowException_0
0x180019f83  mov     rsi, [rsp+128h+arg_0]
0x180019f8b  xor     edi, edi
0x180019f8d  mov     r15d, dword ptr [rsp+128h+arg_8]
0x180019f95  mov     r14, [rsp+128h+arg_18]
0x180019f9d  mov     rcx, [rsi+0D0h]
0x180019fa4  mov     rcx, [rcx]; this
0x180019fa7  call    ?CalcImageSize@FileSystemImage@@QEAAKXZ; FileSystemImage::CalcImageSize(void)
0x180019fac  mov     edx, eax
0x180019fae  cmp     [rsi+0DCh], dil
0x180019fb5  jnz     loc_18001A08E
0x180019fbb  cmp     eax, 200h
0x180019fc0  jb      loc_18001A08E
0x180019fc6  mov     rcx, [rsi+0D0h]
0x180019fcd  mov     rcx, [rcx]
0x180019fd0  mov     r9d, [rcx+328h]
0x180019fd7  mov     r10d, [rcx+32Ch]
0x180019fde  mov     r11d, [rsi+0D8h]
0x180019fe5  movzx   ebx, byte ptr [rcx+188h]
0x180019fec  mov     r12d, [rcx+20h]
0x180019ff0  mov     r13d, [rcx+18h]
0x180019ff4  movzx   eax, byte ptr [rcx+318h]
0x180019ffb  mov     r8d, [rcx+2D0h]
0x18001a002  test    r8d, r8d
0x18001a005  jz      short loc_18001A038
0x18001a007  xorps   xmm1, xmm1
0x18001a00a  cvtsi2sd xmm1, r8
0x18001a00f  mov     eax, [rcx+2B8h]
0x18001a015  add     eax, r8d
0x18001a018  xorps   xmm0, xmm0
0x18001a01b  cvtsi2sd xmm0, rax
0x18001a020  divsd   xmm1, xmm0
0x18001a024  mulsd   xmm1, cs:__real@4059000000000000
0x18001a02c  cvttsd2si rdi, xmm1
0x18001a031  movzx   eax, byte ptr [rcx+318h]
0x18001a038  mov     [rsp+128h+var_B8], r9d; unsigned int
0x18001a03d  mov     [rsp+128h+var_C0], r10d; int
0x18001a042  mov     [rsp+128h+var_C8], r11d; unsigned int
0x18001a047  mov     [rsp+128h+var_D0], r15d; unsigned int
0x18001a04c  mov     [rsp+128h+var_D8], ebx; unsigned int
0x18001a050  mov     [rsp+128h+var_E0], r12d; enum FsiFileSystems
0x18001a055  mov     [rsp+128h+var_E8], r13d; unsigned int
0x18001a05a  mov     [rsp+128h+var_F0], eax; unsigned int
0x18001a05e  mov     [rsp+128h+var_100], edx; unsigned int
0x18001a062  mov     eax, [rcx+17Ch]
0x18001a068  mov     [rsp+128h+var_108], eax; unsigned int
0x18001a06c  mov     r9d, edi; unsigned int
0x18001a06f  mov     r8d, [rcx+178h]; unsigned int
0x18001a076  mov     edx, [rcx+174h]; unsigned int
0x18001a07c  mov     ecx, [rcx+170h]; this
0x18001a082  call    ?SQMLogFSImageSession@Imapi2Utility@@YAJKKKKKKKHW4FsiFileSystems@@KHJJKK@Z; Imapi2Utility::SQMLogFSImageSession(ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,FsiFileSystems,ulong,int,long,long,ulong,ulong)
0x18001a087  mov     byte ptr [rsi+0DCh], 1
0x18001a08e  mov     rcx, r14; this
0x18001a091  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18001a096  nop
0x18001a097  lea     rcx, [rsp+128h+var_A0]; this
0x18001a09f  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18001a0a4  mov     eax, r15d
0x18001a0a7  add     rsp, 0F0h
0x18001a0ae  pop     r15
0x18001a0b0  pop     r14
0x18001a0b2  pop     r13
0x18001a0b4  pop     r12
0x18001a0b6  pop     rdi
0x18001a0b7  pop     rsi
0x18001a0b8  pop     rbx
0x18001a0b9  retn
```
