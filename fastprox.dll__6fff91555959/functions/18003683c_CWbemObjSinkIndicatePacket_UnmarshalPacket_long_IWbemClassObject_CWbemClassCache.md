# CWbemObjSinkIndicatePacket::UnmarshalPacket(long &,IWbemClassObject * * &,CWbemClassCache &)

- ea: `0x18003683c`
- end: `0x180036a83`
- name: `?UnmarshalPacket@CWbemObjSinkIndicatePacket@@QEAAJAEAJAEAPEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(CWbemObjSinkIndicatePacket *this, int *, struct IWbemClassObject ***, struct CWbemClassCache *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800364cc`

## callees

- `0x1800158e0`
- `0x180035b08`
- `0x18003683c`
- `0x180036a90`
- `0x180037120`
- `0x18006fa4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800368e9`
- `wbemcomn!GetMemLogObject` at `0x180036952`
- `wbemcomn!GetMemLogObject` at `0x18003697d`
- `wbemcomn!GetMemLogObject` at `0x1800369e7`
- `wbemcomn!GetMemLogObject` at `0x180036a21`
- `wbemcomn!GetMemLogObject` at `0x1800368e9`
- `wbemcomn!GetMemLogObject` at `0x180036952`
- `wbemcomn!GetMemLogObject` at `0x18003697d`
- `wbemcomn!GetMemLogObject` at `0x1800369e7`
- `wbemcomn!GetMemLogObject` at `0x180036a21`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800368f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003695d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003698d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036a2f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800368f7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003695d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003698d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800369f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036a2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemObjSinkIndicatePacket::UnmarshalPacket(
        CWbemObjSinkIndicatePacket *this,
        int *a2,
        struct IWbemClassObject ***a3,
        struct CWbemClassCache *a4)
{
  __int64 v8; // rsi
  unsigned int IsValid; // ebx
  unsigned int v10; // eax
  unsigned int v11; // edx
  CMemoryLog *v13; // rax
  CMemoryLog *v14; // rax
  CWbemRefreshingSvc *v15; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v17; // rdx
  __int64 v18; // r9
  CMemoryLog *v19; // rax
  CWbemRefreshingSvc *v20; // rcx
  __int64 v21; // rdx
  CMemoryLog *v22; // rax
  int pExceptionObject; // [rsp+24h] [rbp-54h] BYREF
  __int64 v24; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v25; // [rsp+30h] [rbp-48h]

  v8 = *((_QWORD *)this + 2);
  *a3 = 0;
  if ( !v8 )
  {
    MemLogObject = GetMemLogObject();
    IsValid = -2147217398;
    CMemoryLog::Write(MemLogObject, -2147217398);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return IsValid;
    }
    v17 = 12;
    v18 = 2147749898LL;
    goto LABEL_21;
  }
  IsValid = CWbemDataPacket::IsValid(this, 0);
  if ( (IsValid & 0x80000000) != 0 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, IsValid);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return IsValid;
    }
    v17 = 13;
    v18 = IsValid;
LABEL_21:
    WPP_SF_d(*((_QWORD *)v15 + 2), v17, WPP_7c35078de6b730c8b6b4841e12630b85_Traceguids, v18);
    return IsValid;
  }
  v10 = *((_DWORD *)this + 2);
  if ( v10 < 0x1A )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217348);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749948LL;
    }
    v21 = 14;
    goto LABEL_33;
  }
  if ( v10 - 26 < 8 )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217348);
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749948LL;
    }
    v21 = 15;
LABEL_33:
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_7c35078de6b730c8b6b4841e12630b85_Traceguids, 2147749948LL);
    return 2147749948LL;
  }
  v11 = v10 - 34;
  v24 = v8 + 8;
  v25 = v10 - 34;
  if ( v8 != -8 && (v11 < 0xC || *(_DWORD *)(v8 + 8) != 12 || *(unsigned int *)(v8 + 12) > (unsigned __int64)v11 - 12) )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids,
        "SafeIntException(ERROR_INVALID_PARAMETER)");
    }
    pExceptionObject = 87;
    throw (SafeIntException *)&pExceptionObject;
  }
  return (unsigned int)CWbemObjectArrayPacket::UnmarshalPacket((CWbemObjectArrayPacket *)&v24, a2, a3, a4);
}

```

## disassembly

```asm
0x18003683c  push    rbx
0x18003683e  push    rsi
0x18003683f  push    rdi
0x180036840  push    r12
0x180036842  push    r14
0x180036844  push    r15
0x180036846  sub     rsp, 48h
0x18003684a  mov     r15, r9
0x18003684d  mov     r14, r8
0x180036850  mov     r12, rdx
0x180036853  mov     rdi, rcx
0x180036856  mov     rsi, [rcx+10h]
0x18003685a  mov     qword ptr [r8], 0
0x180036861  test    rsi, rsi
0x180036864  jz      loc_18003697D
0x18003686a  xor     edx, edx; int
0x18003686c  call    ?IsValid@CWbemDataPacket@@QEAAJJ@Z; CWbemDataPacket::IsValid(long)
0x180036871  mov     ebx, eax
0x180036873  test    eax, eax
0x180036875  js      loc_180036952
0x18003687b  mov     eax, [rdi+8]
0x18003687e  cmp     eax, 1Ah
0x180036881  jb      loc_1800369E7
0x180036887  lea     edx, [rax-1Ah]
0x18003688a  cmp     edx, 8
0x18003688d  jb      loc_180036A21
0x180036893  add     edx, 0FFFFFFF8h
0x180036896  lea     rax, [rsi+8]
0x18003689a  mov     [rsp+78h+var_50], rax
0x18003689f  mov     [rsp+78h+var_48], edx
0x1800368a3  test    rax, rax
0x1800368a6  jnz     short loc_1800368D1
0x1800368a8  mov     r9, r15; struct CWbemClassCache *
0x1800368ab  mov     r8, r14; struct IWbemClassObject ***
0x1800368ae  mov     rdx, r12; int *
0x1800368b1  lea     rcx, [rsp+78h+var_50]; this
0x1800368b6  call    ?UnmarshalPacket@CWbemObjectArrayPacket@@QEAAJAEAJAEAPEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z; CWbemObjectArrayPacket::UnmarshalPacket(long &,IWbemClassObject * * &,CWbemClassCache &)
0x1800368bb  mov     [rsp+78h+var_58], eax
0x1800368bf  mov     eax, [rsp+78h+var_58]
0x1800368c3  add     rsp, 48h
0x1800368c7  pop     r15
0x1800368c9  pop     r14
0x1800368cb  pop     r12
0x1800368cd  pop     rdi
0x1800368ce  pop     rsi
0x1800368cf  pop     rbx
0x1800368d0  retn
0x1800368d1  cmp     edx, 0Ch
0x1800368d4  jb      short loc_1800368E9
0x1800368d6  cmp     dword ptr [rax], 0Ch
0x1800368d9  jnz     short loc_1800368E9
0x1800368db  mov     ecx, [rax+4]
0x1800368de  mov     eax, edx
0x1800368e0  sub     rax, 0Ch
0x1800368e4  cmp     rcx, rax
0x1800368e7  jbe     short loc_1800368A8
0x1800368e9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800368ef  mov     edx, 0FFFFFFFEh
0x1800368f4  mov     rcx, rax
0x1800368f7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800368fd  lea     rax, WPP_GLOBAL_Control
0x180036904  mov     rcx, cs:WPP_GLOBAL_Control
0x18003690b  cmp     rcx, rax
0x18003690e  jz      short loc_180036938
0x180036910  test    byte ptr [rcx+1Ch], 1
0x180036914  jz      short loc_180036938
0x180036916  cmp     byte ptr [rcx+19h], 2
0x18003691a  jb      short loc_180036938
0x18003691c  mov     edx, 16h
0x180036921  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x180036928  lea     r8, WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids
0x18003692f  mov     rcx, [rcx+10h]
0x180036933  call    WPP_SF_s
0x180036938  mov     [rsp+78h+pExceptionObject], 57h ; 'W'
0x180036940  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x180036947  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18003694c  call    _CxxThrowException_0
0x180036952  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036958  mov     edx, ebx
0x18003695a  mov     rcx, rax
0x18003695d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036963  lea     rax, WPP_GLOBAL_Control
0x18003696a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036971  cmp     rcx, rax
0x180036974  jnz     short loc_1800369D9
0x180036976  mov     eax, ebx
0x180036978  jmp     loc_1800368C3
0x18003697d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036983  mov     ebx, 8004100Ah
0x180036988  mov     edx, ebx
0x18003698a  mov     rcx, rax
0x18003698d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036993  lea     rax, WPP_GLOBAL_Control
0x18003699a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800369a1  cmp     rcx, rax
0x1800369a4  jz      short loc_180036976
0x1800369a6  test    byte ptr [rcx+1Ch], 1
0x1800369aa  jz      short loc_180036976
0x1800369ac  cmp     byte ptr [rcx+19h], 2
0x1800369b0  jb      short loc_180036976
0x1800369b2  mov     edx, 0Ch
0x1800369b7  mov     r9d, 8004100Ah
0x1800369bd  jmp     short loc_1800369C7
0x1800369bf  mov     edx, 0Dh
0x1800369c4  mov     r9d, ebx
0x1800369c7  lea     r8, WPP_7c35078de6b730c8b6b4841e12630b85_Traceguids
0x1800369ce  mov     rcx, [rcx+10h]
0x1800369d2  call    WPP_SF_d
0x1800369d7  jmp     short loc_180036976
0x1800369d9  test    byte ptr [rcx+1Ch], 1
0x1800369dd  jz      short loc_180036976
0x1800369df  cmp     byte ptr [rcx+19h], 2
0x1800369e3  jb      short loc_180036976
0x1800369e5  jmp     short loc_1800369BF
0x1800369e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800369ed  mov     edx, 8004103Ch
0x1800369f2  mov     rcx, rax
0x1800369f5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800369fb  lea     rax, WPP_GLOBAL_Control
0x180036a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a09  cmp     rcx, rax
0x180036a0c  jz      short loc_180036A6F
0x180036a0e  test    byte ptr [rcx+1Ch], 1
0x180036a12  jz      short loc_180036A6F
0x180036a14  cmp     byte ptr [rcx+19h], 2
0x180036a18  jb      short loc_180036A6F
0x180036a1a  mov     edx, 0Eh
0x180036a1f  jmp     short loc_180036A59
0x180036a21  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036a27  mov     edx, 8004103Ch
0x180036a2c  mov     rcx, rax
0x180036a2f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036a35  lea     rax, WPP_GLOBAL_Control
0x180036a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180036a43  cmp     rcx, rax
0x180036a46  jz      short loc_180036A6F
0x180036a48  test    byte ptr [rcx+1Ch], 1
0x180036a4c  jz      short loc_180036A6F
0x180036a4e  cmp     byte ptr [rcx+19h], 2
0x180036a52  jb      short loc_180036A6F
0x180036a54  mov     edx, 0Fh
0x180036a59  mov     r9d, 8004103Ch
0x180036a5f  lea     r8, WPP_7c35078de6b730c8b6b4841e12630b85_Traceguids
0x180036a66  mov     rcx, [rcx+10h]
0x180036a6a  call    WPP_SF_d
0x180036a6f  mov     eax, 8004103Ch
0x180036a74  jmp     loc_1800368C3
0x180036a79  jmp     loc_1800368BF
0x180036a7e  jmp     loc_1800368BF
```
