# FileSystemImage::SetIMultisessions(tagSAFEARRAY *)

- ea: `0x18004868c`
- end: `0x18004888c`
- name: `?SetIMultisessions@FileSystemImage@@QEAAXPEAUtagSAFEARRAY@@@Z`
- size: `512`
- prototype: `void(FileSystemImage *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18005a8d0`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x1800063b8`
- `0x18000726c`
- `0x18000960c`
- `0x18000c8d0`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x180047f7c`
- `0x1800481fc`
- `0x18004868c`
- `0x180050d34`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x180048753`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180048753`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall FileSystemImage::SetIMultisessions(SAFEARRAY **this, struct tagSAFEARRAY *a2)
{
  CIMAPIException ***p_pExceptionObject; // rax
  struct tagSAFEARRAY **v5; // rdx
  char v6; // bl
  CIMAPIException **v7; // rdi
  HRESULT v8; // ebx
  CIMAPIException *v9; // rax
  CIMAPIException **v10; // rbx
  _BYTE v11[144]; // [rsp+20h] [rbp-39h] BYREF
  CIMAPIException **v12; // [rsp+C0h] [rbp+67h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+C8h] [rbp+6Fh] BYREF
  char v14; // [rsp+D0h] [rbp+77h] BYREF
  CIMAPIException **v15; // [rsp+D8h] [rbp+7Fh] BYREF

  LODWORD(v12) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  if ( a2 )
  {
    p_pExceptionObject = (CIMAPIException ***)WrapMultisession(&v14, a2);
    v6 = 1;
  }
  else
  {
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&pExceptionObject, 0);
    p_pExceptionObject = &pExceptionObject;
    v6 = 2;
  }
  v7 = *p_pExceptionObject;
  v15 = v7;
  if ( v7 )
    ++*((_DWORD *)v7 + 2);
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&pExceptionObject);
  }
  if ( (v6 & 1) != 0 )
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v14);
  Imapi2Utility::SafeArrayDestroyAndNull((Imapi2Utility *)(this + 97), v5);
  v8 = SafeArrayCopy(a2, this + 97);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
    }
    v9 = (CIMAPIException *)operator new(0x58u);
    v12 = (CIMAPIException **)v9;
    if ( v9 )
      v9 = CIMAPIException::CIMAPIException(v9, v8);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v12, v9);
    v10 = v12;
    if ( v12 && *v12 )
    {
      CIMAPIException::SetCodeRefInfo(*v12, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 649);
      pExceptionObject = v10;
      if ( v10 )
        ++*((_DWORD *)v10 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v11, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v11;
  }
  v12 = v7;
  if ( v7 )
    ++*((_DWORD *)v7 + 2);
  FileSystemImage::SetDiscReader(this, &pExceptionObject, &v12);
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&pExceptionObject);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v15);
}

```

## disassembly

```asm
0x18004868c  push    rbp
0x18004868e  push    rbx
0x18004868f  push    rsi
0x180048690  push    rdi
0x180048691  push    r13
0x180048693  push    r14
0x180048695  lea     rbp, [rsp-2Fh]
0x18004869a  sub     rsp, 88h
0x1800486a1  mov     rsi, rdx
0x1800486a4  mov     r14, rcx
0x1800486a7  mov     dword ptr [rbp+57h+arg_0], 0
0x1800486ae  lea     r13, WPP_GLOBAL_Control
0x1800486b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486bc  cmp     rcx, r13
0x1800486bf  jz      short loc_1800486E2
0x1800486c1  test    byte ptr [rcx+44h], 8
0x1800486c5  jz      short loc_1800486E2
0x1800486c7  cmp     byte ptr [rcx+41h], 5
0x1800486cb  jb      short loc_1800486E2
0x1800486cd  mov     edx, 16h
0x1800486d2  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x1800486d9  mov     rcx, [rcx+38h]
0x1800486dd  call    WPP_SF_
0x1800486e2  test    rsi, rsi
0x1800486e5  jz      short loc_1800486FB
0x1800486e7  mov     rdx, rsi
0x1800486ea  lea     rcx, [rbp+57h+arg_10]
0x1800486ee  call    ?WrapMultisession@@YA?AV?$SmartClassPtr@VCDiscImporter@@VCDiscReader@@@@PEAUtagSAFEARRAY@@@Z; WrapMultisession(tagSAFEARRAY *)
0x1800486f3  nop
0x1800486f4  mov     ebx, 1
0x1800486f9  jmp     short loc_18004870F
0x1800486fb  xor     edx, edx
0x1800486fd  lea     rcx, [rbp+57h+pExceptionObject]
0x180048701  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x180048706  lea     rax, [rbp+57h+pExceptionObject]
0x18004870a  mov     ebx, 2
0x18004870f  mov     rdi, [rax]
0x180048712  mov     [rbp+57h+arg_18], rdi
0x180048716  test    rdi, rdi
0x180048719  jz      short loc_18004871E
0x18004871b  inc     dword ptr [rdi+8]
0x18004871e  test    bl, 2
0x180048721  jz      short loc_180048730
0x180048723  and     ebx, 0FFFFFFFDh
0x180048726  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x18004872a  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18004872f  nop
0x180048730  test    bl, 1
0x180048733  jz      short loc_18004873E
0x180048735  lea     rcx, [rbp+57h+arg_10]; void *
0x180048739  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18004873e  lea     rbx, [r14+308h]
0x180048745  mov     rcx, rbx; this
0x180048748  call    ?SafeArrayDestroyAndNull@Imapi2Utility@@YAXAEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::SafeArrayDestroyAndNull(tagSAFEARRAY * &)
0x18004874d  mov     rdx, rbx; ppsaOut
0x180048750  mov     rcx, rsi; psa
0x180048753  call    cs:__imp_SafeArrayCopy
0x180048759  mov     ebx, eax
0x18004875b  test    eax, eax
0x18004875d  jns     loc_180048820
0x180048763  mov     rcx, cs:WPP_GLOBAL_Control
0x18004876a  cmp     rcx, r13
0x18004876d  jz      short loc_180048793
0x18004876f  test    byte ptr [rcx+44h], 4
0x180048773  jz      short loc_180048793
0x180048775  cmp     byte ptr [rcx+41h], 2
0x180048779  jb      short loc_180048793
0x18004877b  mov     edx, 17h
0x180048780  mov     r9d, eax
0x180048783  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x18004878a  mov     rcx, [rcx+38h]
0x18004878e  call    WPP_SF_d
0x180048793  mov     ecx, 58h ; 'X'; unsigned __int64
0x180048798  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004879d  mov     [rbp+57h+arg_0], rax
0x1800487a1  test    rax, rax
0x1800487a4  jz      short loc_1800487B1
0x1800487a6  mov     edx, ebx; int
0x1800487a8  mov     rcx, rax; this
0x1800487ab  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800487b0  nop
0x1800487b1  mov     rdx, rax
0x1800487b4  lea     rcx, [rbp+57h+arg_0]
0x1800487b8  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800487bd  nop
0x1800487be  mov     rbx, [rbp+57h+arg_0]
0x1800487c2  test    rbx, rbx
0x1800487c5  jz      short loc_1800487FF
0x1800487c7  cmp     qword ptr [rbx], 0
0x1800487cb  jz      short loc_1800487FF
0x1800487cd  mov     r8d, 289h; int
0x1800487d3  lea     rdx, aDriversStorage_12; "drivers\\storage\\imapi2\\filesystemima"...
0x1800487da  mov     rcx, [rbx]; this
0x1800487dd  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800487e2  mov     [rbp+57h+pExceptionObject], rbx
0x1800487e6  test    rbx, rbx
0x1800487e9  jz      short loc_1800487EE
0x1800487eb  inc     dword ptr [rbx+8]
0x1800487ee  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800487f5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800487f9  call    _CxxThrowException_0
0x1800487ff  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180048806  lea     rcx, [rbp+57h+var_90]; this
0x18004880a  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18004880f  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180048816  lea     rcx, [rbp+57h+var_90]; pExceptionObject
0x18004881a  call    _CxxThrowException_0
0x180048820  mov     [rbp+57h+arg_0], rdi
0x180048824  test    rdi, rdi
0x180048827  jz      short loc_18004882C
0x180048829  inc     dword ptr [rdi+8]
0x18004882c  lea     r8, [rbp+57h+arg_0]
0x180048830  lea     rdx, [rbp+57h+pExceptionObject]
0x180048834  mov     rcx, r14
0x180048837  call    ?SetDiscReader@FileSystemImage@@QEAA?AV?$SmartClassPtr@VCDiscReader@@V1@@@V2@@Z; FileSystemImage::SetDiscReader(SmartClassPtr<CDiscReader,CDiscReader>)
0x18004883c  lea     rcx, [rbp+57h+pExceptionObject]; void *
0x180048840  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180048845  mov     rcx, cs:WPP_GLOBAL_Control
0x18004884c  cmp     rcx, r13
0x18004884f  jz      short loc_180048873
0x180048851  test    byte ptr [rcx+44h], 8
0x180048855  jz      short loc_180048873
0x180048857  cmp     byte ptr [rcx+41h], 5
0x18004885b  jb      short loc_180048873
0x18004885d  mov     edx, 18h
0x180048862  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x180048869  mov     rcx, [rcx+38h]
0x18004886d  call    WPP_SF_
0x180048872  nop
0x180048873  lea     rcx, [rbp+57h+arg_18]; void *
0x180048877  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18004887c  add     rsp, 88h
0x180048883  pop     r14
0x180048885  pop     r13
0x180048887  pop     rdi
0x180048888  pop     rsi
0x180048889  pop     rbx
0x18004888a  pop     rbp
0x18004888b  retn
```
