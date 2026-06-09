# CWbemSmartEnumNextPacket::UnmarshalPacket(long &,IWbemClassObject * * &,CWbemClassCache &)

- ea: `0x180036230`
- end: `0x180036477`
- name: `?UnmarshalPacket@CWbemSmartEnumNextPacket@@QEAAJAEAJAEAPEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(CWbemSmartEnumNextPacket *this, int *, struct IWbemClassObject ***, struct CWbemClassCache *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180035e90`

## callees

- `0x1800158e0`
- `0x180035b08`
- `0x180036230`
- `0x180036a90`
- `0x180037120`
- `0x18006fa4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800362dd`
- `wbemcomn!GetMemLogObject` at `0x180036346`
- `wbemcomn!GetMemLogObject` at `0x180036371`
- `wbemcomn!GetMemLogObject` at `0x1800363db`
- `wbemcomn!GetMemLogObject` at `0x180036415`
- `wbemcomn!GetMemLogObject` at `0x1800362dd`
- `wbemcomn!GetMemLogObject` at `0x180036346`
- `wbemcomn!GetMemLogObject` at `0x180036371`
- `wbemcomn!GetMemLogObject` at `0x1800363db`
- `wbemcomn!GetMemLogObject` at `0x180036415`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800362eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036351`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036381`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800363e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036423`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800362eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036351`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036381`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800363e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036423`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemSmartEnumNextPacket::UnmarshalPacket(
        CWbemSmartEnumNextPacket *this,
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
  unsigned int v23; // [rsp+20h] [rbp-58h]
  int pExceptionObject; // [rsp+24h] [rbp-54h] BYREF
  __int64 v25; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v26; // [rsp+30h] [rbp-48h]

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
    v17 = 13;
    v18 = 2147749898LL;
    goto LABEL_22;
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
    v17 = 14;
    v18 = IsValid;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v15 + 2), v17, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids, v18);
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
    v21 = 15;
    goto LABEL_34;
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
    v21 = 16;
LABEL_34:
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids, 2147749948LL);
    return 2147749948LL;
  }
  v11 = v10 - 34;
  v25 = v8 + 8;
  v26 = v10 - 34;
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
  try
  {
    v23 = CWbemObjectArrayPacket::UnmarshalPacket((CWbemObjectArrayPacket *)&v25, a2, a3, a4);
  }
  catch ( CX_MemoryException )
  {
    return (unsigned int)-2147217402;
  }
  catch ( CX_Exception )
  {
    return (unsigned int)-2147217400;
  }
  v23 = CWbemObjectArrayPacket::UnmarshalPacket((CWbemObjectArrayPacket *)&v25, a2, a3, a4);
}

```

## disassembly

```asm
0x180036230  push    rbx
0x180036232  push    rsi
0x180036233  push    rdi
0x180036234  push    r12
0x180036236  push    r14
0x180036238  push    r15
0x18003623a  sub     rsp, 48h
0x18003623e  mov     r15, r9
0x180036241  mov     r14, r8
0x180036244  mov     r12, rdx
0x180036247  mov     rdi, rcx
0x18003624a  mov     rsi, [rcx+10h]
0x18003624e  mov     qword ptr [r8], 0
0x180036255  test    rsi, rsi
0x180036258  jz      loc_180036371
0x18003625e  xor     edx, edx; int
0x180036260  call    ?IsValid@CWbemDataPacket@@QEAAJJ@Z; CWbemDataPacket::IsValid(long)
0x180036265  mov     ebx, eax
0x180036267  test    eax, eax
0x180036269  js      loc_180036346
0x18003626f  mov     eax, [rdi+8]
0x180036272  cmp     eax, 1Ah
0x180036275  jb      loc_1800363DB
0x18003627b  lea     edx, [rax-1Ah]
0x18003627e  cmp     edx, 8
0x180036281  jb      loc_180036415
0x180036287  add     edx, 0FFFFFFF8h
0x18003628a  lea     rax, [rsi+8]
0x18003628e  mov     [rsp+78h+var_50], rax
0x180036293  mov     [rsp+78h+var_48], edx
0x180036297  test    rax, rax
0x18003629a  jnz     short loc_1800362C5
0x18003629c  mov     r9, r15; struct CWbemClassCache *
0x18003629f  mov     r8, r14; struct IWbemClassObject ***
0x1800362a2  mov     rdx, r12; int *
0x1800362a5  lea     rcx, [rsp+78h+var_50]; this
0x1800362aa  call    ?UnmarshalPacket@CWbemObjectArrayPacket@@QEAAJAEAJAEAPEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z; CWbemObjectArrayPacket::UnmarshalPacket(long &,IWbemClassObject * * &,CWbemClassCache &)
0x1800362af  mov     [rsp+78h+var_58], eax
0x1800362b3  mov     eax, [rsp+78h+var_58]
0x1800362b7  add     rsp, 48h
0x1800362bb  pop     r15
0x1800362bd  pop     r14
0x1800362bf  pop     r12
0x1800362c1  pop     rdi
0x1800362c2  pop     rsi
0x1800362c3  pop     rbx
0x1800362c4  retn
0x1800362c5  cmp     edx, 0Ch
0x1800362c8  jb      short loc_1800362DD
0x1800362ca  cmp     dword ptr [rax], 0Ch
0x1800362cd  jnz     short loc_1800362DD
0x1800362cf  mov     ecx, [rax+4]
0x1800362d2  mov     eax, edx
0x1800362d4  sub     rax, 0Ch
0x1800362d8  cmp     rcx, rax
0x1800362db  jbe     short loc_18003629C
0x1800362dd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800362e3  mov     edx, 0FFFFFFFEh
0x1800362e8  mov     rcx, rax
0x1800362eb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800362f1  lea     rax, WPP_GLOBAL_Control
0x1800362f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362ff  cmp     rcx, rax
0x180036302  jz      short loc_18003632C
0x180036304  test    byte ptr [rcx+1Ch], 1
0x180036308  jz      short loc_18003632C
0x18003630a  cmp     byte ptr [rcx+19h], 2
0x18003630e  jb      short loc_18003632C
0x180036310  mov     edx, 16h
0x180036315  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18003631c  lea     r8, WPP_6737080c1ee93bb283ad4d220f5cef4f_Traceguids
0x180036323  mov     rcx, [rcx+10h]
0x180036327  call    WPP_SF_s
0x18003632c  mov     [rsp+78h+pExceptionObject], 57h ; 'W'
0x180036334  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18003633b  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180036340  call    _CxxThrowException_0
0x180036346  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003634c  mov     edx, ebx
0x18003634e  mov     rcx, rax
0x180036351  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036357  lea     rax, WPP_GLOBAL_Control
0x18003635e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036365  cmp     rcx, rax
0x180036368  jnz     short loc_1800363CD
0x18003636a  mov     eax, ebx
0x18003636c  jmp     loc_1800362B7
0x180036371  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036377  mov     ebx, 8004100Ah
0x18003637c  mov     edx, ebx
0x18003637e  mov     rcx, rax
0x180036381  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036387  lea     rax, WPP_GLOBAL_Control
0x18003638e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036395  cmp     rcx, rax
0x180036398  jz      short loc_18003636A
0x18003639a  test    byte ptr [rcx+1Ch], 1
0x18003639e  jz      short loc_18003636A
0x1800363a0  cmp     byte ptr [rcx+19h], 2
0x1800363a4  jb      short loc_18003636A
0x1800363a6  mov     edx, 0Dh
0x1800363ab  mov     r9d, 8004100Ah
0x1800363b1  jmp     short loc_1800363BB
0x1800363b3  mov     edx, 0Eh
0x1800363b8  mov     r9d, ebx
0x1800363bb  lea     r8, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids
0x1800363c2  mov     rcx, [rcx+10h]
0x1800363c6  call    WPP_SF_d
0x1800363cb  jmp     short loc_18003636A
0x1800363cd  test    byte ptr [rcx+1Ch], 1
0x1800363d1  jz      short loc_18003636A
0x1800363d3  cmp     byte ptr [rcx+19h], 2
0x1800363d7  jb      short loc_18003636A
0x1800363d9  jmp     short loc_1800363B3
0x1800363db  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800363e1  mov     edx, 8004103Ch
0x1800363e6  mov     rcx, rax
0x1800363e9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800363ef  lea     rax, WPP_GLOBAL_Control
0x1800363f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363fd  cmp     rcx, rax
0x180036400  jz      short loc_180036463
0x180036402  test    byte ptr [rcx+1Ch], 1
0x180036406  jz      short loc_180036463
0x180036408  cmp     byte ptr [rcx+19h], 2
0x18003640c  jb      short loc_180036463
0x18003640e  mov     edx, 0Fh
0x180036413  jmp     short loc_18003644D
0x180036415  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003641b  mov     edx, 8004103Ch
0x180036420  mov     rcx, rax
0x180036423  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036429  lea     rax, WPP_GLOBAL_Control
0x180036430  mov     rcx, cs:WPP_GLOBAL_Control
0x180036437  cmp     rcx, rax
0x18003643a  jz      short loc_180036463
0x18003643c  test    byte ptr [rcx+1Ch], 1
0x180036440  jz      short loc_180036463
0x180036442  cmp     byte ptr [rcx+19h], 2
0x180036446  jb      short loc_180036463
0x180036448  mov     edx, 10h
0x18003644d  mov     r9d, 8004103Ch
0x180036453  lea     r8, WPP_1dc8a53bc0cd3976ab96ac4ecec6522b_Traceguids
0x18003645a  mov     rcx, [rcx+10h]
0x18003645e  call    WPP_SF_d
0x180036463  mov     eax, 8004103Ch
0x180036468  jmp     loc_1800362B7
0x18003646d  jmp     loc_1800362B3
0x180036472  jmp     loc_1800362B3
```
