# CWbemClass::GetClassSubset(ulong,ushort const * *,_IWmiObject * *)

- ea: `0x1800018e0`
- end: `0x180001b8a`
- name: `?GetClassSubset@CWbemClass@@UEAAJKPEAPEBGPEAPEAU_IWmiObject@@@Z`
- size: `682`
- prototype: `__int64 __fastcall(CWbemClass *__hidden this, unsigned int, const unsigned __int16 **, struct _IWmiObject **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800010f0`
- `0x1800015a0`
- `0x1800018e0`
- `0x180001d80`
- `0x180001e10`
- `0x180001e70`
- `0x180037120`
- `0x180060580`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180001989`
- `wbemcomn!GetMemLogObject` at `0x180001a65`
- `wbemcomn!GetMemLogObject` at `0x180001b29`
- `wbemcomn!GetMemLogObject` at `0x180001989`
- `wbemcomn!GetMemLogObject` at `0x180001a65`
- `wbemcomn!GetMemLogObject` at `0x180001b29`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180001ad3`
- `wbemcomn!?Add@CWStringArray@@QEAAHPEBG@Z` at `0x180001ad3`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18000195d`
- `wbemcomn!??0CWStringArray@@QEAA@HH@Z` at `0x18000195d`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180001a40`
- `wbemcomn!??1CWStringArray@@QEAA@XZ` at `0x180001a40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001994`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001a75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b39`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001994`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001a75`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180001b39`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001928`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180001928`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemClass::GetClassSubset(
        CWbemClass *this,
        unsigned int a2,
        const unsigned __int16 **a3,
        struct _IWmiObject **a4)
{
  struct CWbemClass *v7; // rax
  CLimitationMapping *v8; // rdi
  int LimitedVersion; // ebx
  unsigned int v10; // edx
  __int64 v11; // r14
  CMemoryLog *v12; // rax
  struct CWbemClass *v13; // rcx
  __int64 result; // rax
  CMemoryLog *v15; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v17; // rax
  struct CWbemClass *v18; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v19[96]; // [rsp+30h] [rbp-88h] BYREF

  try
  {
    if ( *((_QWORD *)this + 107) || (**((_BYTE **)this + 9) & 0x10) != 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217386);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          245,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749910LL);
      }
      result = 2147749910LL;
    }
    else
    {
      v7 = (struct CWbemClass *)CWin32DefaultArena::WbemMemAlloc(0x90u);
      v18 = v7;
      if ( v7 )
        v8 = CLimitationMapping::CLimitationMapping(v7);
      else
        v8 = 0;
      if ( v8 )
      {
        LimitedVersion = 0;
        CWStringArray::CWStringArray((CWStringArray *)v19, 0, 100);
        v11 = 0;
        while ( LimitedVersion >= 0 )
        {
          if ( (unsigned int)v11 >= a2 )
          {
            if ( (unsigned int)CDecorationPart::MapLimitation((struct CWStringArray *)v19, v8)
              && (unsigned int)CClassPart::MapLimitation(
                                 (CWbemClass *)((char *)this + 520),
                                 0,
                                 (struct CWStringArray *)v19,
                                 v8) )
            {
              CLimitationMapping::SetClassObject(v8, this);
              v18 = 0;
              LimitedVersion = CWbemClass::GetLimitedVersion(this, v8, &v18);
              if ( LimitedVersion < 0 )
                break;
              v13 = v18;
              *((_QWORD *)v18 + 107) = v8;
              *a4 = v13;
            }
            else
            {
              LimitedVersion = -2147217407;
            }
            if ( LimitedVersion >= 0 )
              goto LABEL_17;
            break;
          }
          if ( CWStringArray::Add((CWStringArray *)v19, a3[v11]) )
            LimitedVersion = -2147217402;
          v11 = (unsigned int)(v11 + 1);
        }
        CLimitationMapping::`scalar deleting destructor'(v8, v10);
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, LimitedVersion);
LABEL_17:
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            247,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            (unsigned int)LimitedVersion);
        }
        CWStringArray::~CWStringArray((CWStringArray *)v19);
        result = (unsigned int)LimitedVersion;
      }
      else
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, -2147217402);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            246,
            WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
            2147749894LL);
        }
        result = 2147749894LL;
      }
    }
  }
  catch ( CX_MemoryException )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 248, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800018e0  mov     [rsp+arg_0], rbx
0x1800018e5  mov     [rsp+arg_8], rsi
0x1800018ea  mov     [rsp+arg_10], r8
0x1800018ef  push    rdi
0x1800018f0  push    r12
0x1800018f2  push    r13
0x1800018f4  push    r14
0x1800018f6  push    r15
0x1800018f8  sub     rsp, 90h
0x1800018ff  mov     r13, r9
0x180001902  mov     r12d, edx
0x180001905  mov     r15, rcx
0x180001908  cmp     qword ptr [rcx+358h], 0
0x180001910  jnz     loc_180001B29
0x180001916  mov     rax, [rcx+48h]
0x18000191a  test    byte ptr [rax], 10h
0x18000191d  jnz     loc_180001B29
0x180001923  mov     ecx, 90h
0x180001928  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000192e  mov     [rsp+0B8h+var_90], rax
0x180001933  test    rax, rax
0x180001936  jz      short loc_18000199F
0x180001938  mov     rcx, rax; this
0x18000193b  call    ??0CLimitationMapping@@QEAA@XZ; CLimitationMapping::CLimitationMapping(void)
0x180001940  mov     rdi, rax
0x180001943  test    rdi, rdi
0x180001946  jz      loc_180001A65
0x18000194c  xor     ebx, ebx
0x18000194e  mov     [rsp+0B8h+var_98], ebx
0x180001952  xor     edx, edx
0x180001954  lea     r8d, [rbx+64h]
0x180001958  lea     rcx, [rsp+0B8h+var_88]
0x18000195d  call    cs:__imp_??0CWStringArray@@QEAA@HH@Z; CWStringArray::CWStringArray(int,int)
0x180001963  nop
0x180001964  xor     r14d, r14d
0x180001967  mov     esi, 80041006h
0x18000196c  mov     [rsp+0B8h+var_94], r14d
0x180001971  test    ebx, ebx
0x180001973  jns     loc_180001AB9
0x180001979  mov     rcx, rdi; this
0x18000197c  call    ??_GCLimitationMapping@@QEAAPEAXI@Z; CLimitationMapping::`scalar deleting destructor'(uint)
0x180001981  test    ebx, ebx
0x180001983  jns     loc_180001A24
0x180001989  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000198f  mov     edx, ebx
0x180001991  mov     rcx, rax
0x180001994  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000199a  jmp     loc_180001A24
0x18000199f  xor     edi, edi
0x1800019a1  jmp     short loc_180001943
0x1800019a3  test    ebx, ebx
0x1800019a5  js      short loc_180001979
0x1800019a7  mov     rdx, rdi; struct CLimitationMapping *
0x1800019aa  lea     rcx, [rsp+0B8h+var_88]; struct CWStringArray *
0x1800019af  call    ?MapLimitation@CDecorationPart@@SAHPEAVCWStringArray@@PEAVCLimitationMapping@@@Z; CDecorationPart::MapLimitation(CWStringArray *,CLimitationMapping *)
0x1800019b4  test    eax, eax
0x1800019b6  jz      loc_180001AEA
0x1800019bc  lea     rcx, [r15+208h]; this
0x1800019c3  mov     r9, rdi; struct CLimitationMapping *
0x1800019c6  lea     r8, [rsp+0B8h+var_88]; struct CWStringArray *
0x1800019cb  xor     edx, edx; int
0x1800019cd  call    ?MapLimitation@CClassPart@@QEAAHJPEAVCWStringArray@@PEAVCLimitationMapping@@@Z; CClassPart::MapLimitation(long,CWStringArray *,CLimitationMapping *)
0x1800019d2  test    eax, eax
0x1800019d4  jz      loc_180001AEA
0x1800019da  mov     rdx, r15; struct CWbemClass *
0x1800019dd  mov     rcx, rdi; this
0x1800019e0  call    ?SetClassObject@CLimitationMapping@@QEAAXPEAVCWbemClass@@@Z; CLimitationMapping::SetClassObject(CWbemClass *)
0x1800019e5  mov     [rsp+0B8h+var_90], 0
0x1800019ee  lea     r8, [rsp+0B8h+var_90]; struct CWbemClass **
0x1800019f3  mov     rdx, rdi; struct CLimitationMapping *
0x1800019f6  mov     rcx, r15; this
0x1800019f9  call    ?GetLimitedVersion@CWbemClass@@QEAAJPEAVCLimitationMapping@@PEAPEAV1@@Z; CWbemClass::GetLimitedVersion(CLimitationMapping *,CWbemClass * *)
0x1800019fe  mov     ebx, eax
0x180001a00  mov     [rsp+0B8h+var_98], eax
0x180001a04  test    eax, eax
0x180001a06  js      loc_180001979
0x180001a0c  mov     rcx, [rsp+0B8h+var_90]
0x180001a11  mov     [rcx+358h], rdi
0x180001a18  mov     [r13+0], rcx
0x180001a1c  test    ebx, ebx
0x180001a1e  js      loc_180001979
0x180001a24  lea     rax, WPP_GLOBAL_Control
0x180001a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a32  cmp     rcx, rax
0x180001a35  jnz     loc_180001AF8
0x180001a3b  lea     rcx, [rsp+0B8h+var_88]
0x180001a40  call    cs:__imp_??1CWStringArray@@QEAA@XZ; CWStringArray::~CWStringArray(void)
0x180001a46  mov     eax, ebx
0x180001a48  lea     r11, [rsp+0B8h+var_28]
0x180001a50  mov     rbx, [r11+30h]
0x180001a54  mov     rsi, [r11+38h]
0x180001a58  mov     rsp, r11
0x180001a5b  pop     r15
0x180001a5d  pop     r14
0x180001a5f  pop     r13
0x180001a61  pop     r12
0x180001a63  pop     rdi
0x180001a64  retn
0x180001a65  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001a6b  mov     esi, 80041006h
0x180001a70  mov     edx, esi
0x180001a72  mov     rcx, rax
0x180001a75  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001a7b  lea     rax, WPP_GLOBAL_Control
0x180001a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a89  cmp     rcx, rax
0x180001a8c  jz      short loc_180001AB5
0x180001a8e  test    byte ptr [rcx+1Ch], 1
0x180001a92  jz      short loc_180001AB5
0x180001a94  cmp     byte ptr [rcx+19h], 2
0x180001a98  jb      short loc_180001AB5
0x180001a9a  mov     edx, 0F6h
0x180001a9f  mov     r9d, 80041006h
0x180001aa5  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180001aac  mov     rcx, [rcx+10h]
0x180001ab0  call    WPP_SF_d
0x180001ab5  mov     eax, esi
0x180001ab7  jmp     short loc_180001A48
0x180001ab9  cmp     r14d, r12d
0x180001abc  jnb     loc_1800019A3
0x180001ac2  mov     rax, [rsp+0B8h+arg_10]
0x180001aca  mov     rdx, [rax+r14*8]
0x180001ace  lea     rcx, [rsp+0B8h+var_88]
0x180001ad3  call    cs:__imp_?Add@CWStringArray@@QEAAHPEBG@Z; CWStringArray::Add(ushort const *)
0x180001ad9  test    eax, eax
0x180001adb  cmovnz  ebx, esi
0x180001ade  mov     [rsp+0B8h+var_98], ebx
0x180001ae2  inc     r14d
0x180001ae5  jmp     loc_18000196C
0x180001aea  mov     ebx, 80041001h
0x180001aef  mov     [rsp+0B8h+var_98], ebx
0x180001af3  jmp     loc_180001A1C
0x180001af8  test    byte ptr [rcx+1Ch], 1
0x180001afc  jz      loc_180001A3B
0x180001b02  cmp     byte ptr [rcx+19h], 2
0x180001b06  jb      loc_180001A3B
0x180001b0c  mov     edx, 0F7h
0x180001b11  mov     r9d, ebx
0x180001b14  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180001b1b  mov     rcx, [rcx+10h]
0x180001b1f  call    WPP_SF_d
0x180001b24  jmp     loc_180001A3B
0x180001b29  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180001b2f  mov     ebx, 80041016h
0x180001b34  mov     edx, ebx
0x180001b36  mov     rcx, rax
0x180001b39  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180001b3f  lea     rax, WPP_GLOBAL_Control
0x180001b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b4d  cmp     rcx, rax
0x180001b50  jz      short loc_180001B79
0x180001b52  test    byte ptr [rcx+1Ch], 1
0x180001b56  jz      short loc_180001B79
0x180001b58  cmp     byte ptr [rcx+19h], 2
0x180001b5c  jb      short loc_180001B79
0x180001b5e  mov     edx, 0F5h
0x180001b63  mov     r9d, 80041016h
0x180001b69  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x180001b70  mov     rcx, [rcx+10h]
0x180001b74  call    WPP_SF_d
0x180001b79  mov     eax, ebx
0x180001b7b  jmp     loc_180001A48
0x180001b80  mov     eax, 80041006h
0x180001b85  jmp     loc_180001A48
```
