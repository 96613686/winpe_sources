# CWbemClass::WritePropertyAsMethodParam(WString &,int,long,CWbemClass *,int)

- ea: `0x18006cab0`
- end: `0x18006cdca`
- name: `?WritePropertyAsMethodParam@CWbemClass@@QEAAJAEAVWString@@HJPEAV1@H@Z`
- size: `794`
- prototype: `__int64 __usercall@<rax>(CWbemClass *__hidden this@<rcx>, struct WString *@<rdx>, int@<r8d>, int@<r9d>, struct CWbemClass *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180032100`

## callees

- `0x180021820`
- `0x180024390`
- `0x18002d8b0`
- `0x180030ce0`
- `0x180037120`
- `0x18006cab0`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18006cc46`
- `wbemcomn!GetMemLogObject` at `0x18006ccc5`
- `wbemcomn!GetMemLogObject` at `0x18006cc46`
- `wbemcomn!GetMemLogObject` at `0x18006ccc5`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18006ccba`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18006ccba`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x18006cb24`
- `wbemcomn!??0WString2@@QEAA@XZ` at `0x18006cb24`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cb60`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cbd4`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cca8`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cd27`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cd71`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cd8c`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cb60`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cbd4`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cca8`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cd27`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cd71`
- `wbemcomn!??1WString2@@QEAA@XZ` at `0x18006cd8c`
- `wbemcomn!?EqualNoCase@WString2@@QEBAHPEBG@Z` at `0x18006cb51`
- `wbemcomn!?EqualNoCase@WString2@@QEBAHPEBG@Z` at `0x18006cb51`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18006cb96`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18006cc10`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18006cb96`
- `wbemcomn!??BWString2@@QEAAPEAGXZ` at `0x18006cc10`
- `wbemcomn!?GetLong@CVar@@QEAAJXZ` at `0x18006cd36`
- `wbemcomn!?GetLong@CVar@@QEAAJXZ` at `0x18006cd36`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006cb80`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006cbfa`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006cb80`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18006cbfa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006cc56`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ccd5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006cc56`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18006ccd5`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cbc8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cbef`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cc9c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cd1b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cd65`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cd80`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cbc8`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cbef`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cc9c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cd1b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cd65`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18006cd80`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWbemClass::WritePropertyAsMethodParam(
        CWbemClass *this,
        struct WString *a2,
        int a3,
        int a4,
        struct CWbemClass *a5,
        int a6)
{
  int v6; // edi
  _DWORD *v9; // rdx
  _DWORD *v10; // r12
  CCompressedString *v11; // rax
  int v12; // edi
  int (__fastcall *v13)(struct CWbemClass *, __int64, _BYTE *); // rbx
  __int64 v14; // rax
  int (__fastcall *v15)(CWbemClass *, __int64, const unsigned __int16 *, _BYTE *, _QWORD, _QWORD); // rbx
  __int64 v16; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  CMemoryLog *v19; // rax
  unsigned int v20; // ebx
  int i; // esi
  CMemoryLog *v22; // rax
  _BYTE v23[40]; // [rsp+48h] [rbp-A0h] BYREF
  struct CPropertyInformation *v24; // [rsp+70h] [rbp-78h]
  _BYTE v25[32]; // [rsp+78h] [rbp-70h] BYREF
  _BYTE v26[40]; // [rsp+98h] [rbp-50h] BYREF

  v6 = a4;
  try
  {
    for ( i = 0; ; ++i )
    {
      v9 = (_DWORD *)*((_QWORD *)this + 84);
      if ( i >= *v9 )
        return 2147749890LL;
      v10 = &v9[2 * i];
      v24 = (struct CPropertyInformation *)CFastHeap::ResolveHeapPointer((CWbemClass *)((char *)this + 720), v10[2]);
      WString2::WString2((WString2 *)v23);
      v11 = CFastHeap::ResolveString((CWbemClass *)((char *)this + 720), v10[1]);
      CCompressedString::CreateWStringCopy(v11, (struct WString2 *)v23);
      if ( WString2::EqualNoCase((WString2 *)v23, L"ReturnValue") )
      {
        WString2::~WString2((WString2 *)v23);
        continue;
      }
      v12 = v6 | 0x2000;
      if ( !a5 )
        break;
      CVar::CVar((CVar *)v26);
      v13 = *(int (__fastcall **)(struct CWbemClass *, __int64, _BYTE *))(*(_QWORD *)a5 + 776LL);
      v14 = WString2::operator unsigned short *(v23);
      if ( v13(a5, v14, v26) < 0 )
        goto LABEL_10;
      if ( !a6 )
      {
        v12 |= 0x1000u;
LABEL_10:
        CVar::~CVar((CVar *)v26);
        break;
      }
      CVar::~CVar((CVar *)v26);
      WString2::~WString2((WString2 *)v23);
LABEL_26:
      v6 = a4;
    }
    CVar::CVar((CVar *)v25);
    v15 = *(int (__fastcall **)(CWbemClass *, __int64, const unsigned __int16 *, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)this + 920LL);
    v16 = WString2::operator unsigned short *(v23);
    if ( v15(this, v16, L"id", v25, 0, 0) < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217354);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids,
          2147749942LL);
      }
      CVar::~CVar((CVar *)v25);
      WString2::~WString2((WString2 *)v23);
      return 2147749942LL;
    }
    if ( CVar::GetType((CVar *)v25) == 3 )
    {
      if ( CVar::GetLong((CVar *)v25) == a3 )
      {
        v20 = CWbemClass::AddPropertyText(this, a2, (struct CPropertyLookup *)(v10 + 1), v24, v12);
        CVar::~CVar((CVar *)v25);
        WString2::~WString2((WString2 *)v23);
        return v20;
      }
      CVar::~CVar((CVar *)v25);
      WString2::~WString2((WString2 *)v23);
      goto LABEL_26;
    }
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217353);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749943LL);
    }
    CVar::~CVar((CVar *)v25);
    WString2::~WString2((WString2 *)v23);
    result = 2147749943LL;
  }
  catch ( CX_MemoryException )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  return result;
}

```

## disassembly

```asm
0x18006cab0  mov     rax, rsp
0x18006cab3  mov     [rax+8], rbx
0x18006cab7  mov     [rax+10h], rsi
0x18006cabb  mov     [rax+20h], r9d
0x18006cabf  mov     [rax+18h], r8d
0x18006cac3  push    rdi
0x18006cac4  push    r12
0x18006cac6  push    r13
0x18006cac8  push    r14
0x18006caca  push    r15
0x18006cacc  sub     rsp, 0C0h
0x18006cad3  mov     edi, r9d
0x18006cad6  mov     r13, rdx
0x18006cad9  mov     r14, rcx
0x18006cadc  xor     esi, esi
0x18006cade  mov     r15, [rsp+0E8h+arg_20]
0x18006cae6  mov     [rsp+0E8h+var_A4], esi
0x18006caea  mov     rdx, [r14+2A0h]
0x18006caf1  cmp     esi, [rdx]
0x18006caf3  jge     loc_18006CDA0
0x18006caf9  lea     eax, ds:0[rsi*8]
0x18006cb00  movsxd  r12, eax
0x18006cb03  add     r12, rdx
0x18006cb06  lea     rbx, [r14+2D0h]
0x18006cb0d  mov     edx, [r12+8]; unsigned int
0x18006cb12  mov     rcx, rbx; this
0x18006cb15  call    ?ResolveHeapPointer@CFastHeap@@QEAAPEAEK@Z; CFastHeap::ResolveHeapPointer(ulong)
0x18006cb1a  mov     [rsp+0E8h+var_78], rax
0x18006cb1f  lea     rcx, [rsp+0E8h+var_A0]
0x18006cb24  call    cs:__imp_??0WString2@@QEAA@XZ; WString2::WString2(void)
0x18006cb2a  nop
0x18006cb2b  mov     edx, [r12+4]; unsigned int
0x18006cb30  mov     rcx, rbx; this
0x18006cb33  call    ?ResolveString@CFastHeap@@QEAAPEAVCCompressedString@@K@Z; CFastHeap::ResolveString(ulong)
0x18006cb38  lea     rdx, [rsp+0E8h+var_A0]; struct WString2 *
0x18006cb3d  mov     rcx, rax; this
0x18006cb40  call    ?CreateWStringCopy@CCompressedString@@QEBAXAEAVWString2@@@Z; CCompressedString::CreateWStringCopy(WString2 &)
0x18006cb45  lea     rdx, aReturnvalue; "ReturnValue"
0x18006cb4c  lea     rcx, [rsp+0E8h+var_A0]
0x18006cb51  call    cs:__imp_?EqualNoCase@WString2@@QEBAHPEBG@Z; WString2::EqualNoCase(ushort const *)
0x18006cb57  test    eax, eax
0x18006cb59  jz      short loc_18006CB6B
0x18006cb5b  lea     rcx, [rsp+0E8h+var_A0]
0x18006cb60  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18006cb66  jmp     loc_18006CD99
0x18006cb6b  bts     edi, 0Dh
0x18006cb6f  mov     [rsp+0E8h+var_A8], edi
0x18006cb73  test    r15, r15
0x18006cb76  jz      short loc_18006CBF5
0x18006cb78  lea     rcx, [rsp+0E8h+var_50]
0x18006cb80  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18006cb86  nop
0x18006cb87  mov     rax, [r15]
0x18006cb8a  mov     rbx, [rax+308h]
0x18006cb91  lea     rcx, [rsp+0E8h+var_A0]
0x18006cb96  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x18006cb9c  lea     r8, [rsp+0E8h+var_50]
0x18006cba4  mov     rdx, rax
0x18006cba7  mov     rcx, r15
0x18006cbaa  mov     rax, rbx
0x18006cbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbb2  test    eax, eax
0x18006cbb4  js      short loc_18006CBE7
0x18006cbb6  cmp     [rsp+0E8h+arg_28], 0
0x18006cbbe  jz      short loc_18006CBDF
0x18006cbc0  lea     rcx, [rsp+0E8h+var_50]
0x18006cbc8  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006cbce  nop
0x18006cbcf  lea     rcx, [rsp+0E8h+var_A0]
0x18006cbd4  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18006cbda  jmp     loc_18006CD92
0x18006cbdf  bts     edi, 0Ch
0x18006cbe3  mov     [rsp+0E8h+var_A8], edi
0x18006cbe7  lea     rcx, [rsp+0E8h+var_50]
0x18006cbef  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006cbf5  lea     rcx, [rsp+0E8h+var_70]
0x18006cbfa  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18006cc00  nop
0x18006cc01  mov     rax, [r14]
0x18006cc04  mov     rbx, [rax+398h]
0x18006cc0b  lea     rcx, [rsp+0E8h+var_A0]
0x18006cc10  call    cs:__imp_??BWString2@@QEAAPEAGXZ; WString2::operator ushort *(void)
0x18006cc16  mov     [rsp+0E8h+var_C0], 0
0x18006cc1f  mov     qword ptr [rsp+0E8h+var_C8], 0
0x18006cc28  lea     r9, [rsp+0E8h+var_70]
0x18006cc2d  lea     r8, aId; "id"
0x18006cc34  mov     rdx, rax
0x18006cc37  mov     rcx, r14
0x18006cc3a  mov     rax, rbx
0x18006cc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc42  test    eax, eax
0x18006cc44  jns     short loc_18006CCB5
0x18006cc46  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006cc4c  mov     ebx, 80041036h
0x18006cc51  mov     edx, ebx
0x18006cc53  mov     rcx, rax
0x18006cc56  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006cc5c  lea     rax, WPP_GLOBAL_Control
0x18006cc63  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc6a  cmp     rcx, rax
0x18006cc6d  jz      short loc_18006CC97
0x18006cc6f  test    byte ptr [rcx+1Ch], 1
0x18006cc73  jz      short loc_18006CC97
0x18006cc75  cmp     byte ptr [rcx+19h], 2
0x18006cc79  jb      short loc_18006CC97
0x18006cc7b  mov     edx, 9Dh
0x18006cc80  mov     r9d, 80041036h
0x18006cc86  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18006cc8d  mov     rcx, [rcx+10h]
0x18006cc91  call    WPP_SF_d
0x18006cc96  nop
0x18006cc97  lea     rcx, [rsp+0E8h+var_70]
0x18006cc9c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006cca2  nop
0x18006cca3  lea     rcx, [rsp+0E8h+var_A0]
0x18006cca8  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18006ccae  mov     eax, ebx
0x18006ccb0  jmp     loc_18006CDAC
0x18006ccb5  lea     rcx, [rsp+0E8h+var_70]
0x18006ccba  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x18006ccc0  cmp     eax, 3
0x18006ccc3  jz      short loc_18006CD31
0x18006ccc5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18006cccb  mov     ebx, 80041037h
0x18006ccd0  mov     edx, ebx
0x18006ccd2  mov     rcx, rax
0x18006ccd5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18006ccdb  lea     rax, WPP_GLOBAL_Control
0x18006cce2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cce9  cmp     rcx, rax
0x18006ccec  jz      short loc_18006CD16
0x18006ccee  test    byte ptr [rcx+1Ch], 1
0x18006ccf2  jz      short loc_18006CD16
0x18006ccf4  cmp     byte ptr [rcx+19h], 2
0x18006ccf8  jb      short loc_18006CD16
0x18006ccfa  mov     edx, 9Eh
0x18006ccff  mov     r9d, 80041037h
0x18006cd05  lea     r8, WPP_bd5c8f861b993c26c5bbe29567545420_Traceguids
0x18006cd0c  mov     rcx, [rcx+10h]
0x18006cd10  call    WPP_SF_d
0x18006cd15  nop
0x18006cd16  lea     rcx, [rsp+0E8h+var_70]
0x18006cd1b  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006cd21  nop
0x18006cd22  lea     rcx, [rsp+0E8h+var_A0]
0x18006cd27  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18006cd2d  mov     eax, ebx
0x18006cd2f  jmp     short loc_18006CDAC
0x18006cd31  lea     rcx, [rsp+0E8h+var_70]
0x18006cd36  call    cs:__imp_?GetLong@CVar@@QEAAJXZ; CVar::GetLong(void)
0x18006cd3c  cmp     eax, [rsp+0E8h+arg_10]
0x18006cd43  jnz     short loc_18006CD7B
0x18006cd45  mov     [rsp+0E8h+var_C8], edi; int
0x18006cd49  mov     r9, [rsp+0E8h+var_78]; struct CPropertyInformation *
0x18006cd4e  lea     r8, [r12+4]; struct CPropertyLookup *
0x18006cd53  mov     rdx, r13; struct WString *
0x18006cd56  mov     rcx, r14; this
0x18006cd59  call    ?AddPropertyText@CWbemClass@@QEAAJAEAVWString@@PEAUCPropertyLookup@@PEAVCPropertyInformation@@J@Z; CWbemClass::AddPropertyText(WString &,CPropertyLookup *,CPropertyInformation *,long)
0x18006cd5e  mov     ebx, eax
0x18006cd60  lea     rcx, [rsp+0E8h+var_70]
0x18006cd65  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006cd6b  nop
0x18006cd6c  lea     rcx, [rsp+0E8h+var_A0]
0x18006cd71  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18006cd77  mov     eax, ebx
0x18006cd79  jmp     short loc_18006CDAC
0x18006cd7b  lea     rcx, [rsp+0E8h+var_70]
0x18006cd80  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18006cd86  nop
0x18006cd87  lea     rcx, [rsp+0E8h+var_A0]
0x18006cd8c  call    cs:__imp_??1WString2@@QEAA@XZ; WString2::~WString2(void)
0x18006cd92  mov     edi, [rsp+0E8h+arg_18]
0x18006cd99  inc     esi
0x18006cd9b  jmp     loc_18006CAE6
0x18006cda0  mov     eax, 80041002h
0x18006cda5  jmp     short loc_18006CDAC
0x18006cda7  mov     eax, 80041006h
0x18006cdac  lea     r11, [rsp+0E8h+var_28]
0x18006cdb4  mov     rbx, [r11+30h]
0x18006cdb8  mov     rsi, [r11+38h]
0x18006cdbc  mov     rsp, r11
0x18006cdbf  pop     r15
0x18006cdc1  pop     r14
0x18006cdc3  pop     r13
0x18006cdc5  pop     r12
0x18006cdc7  pop     rdi
0x18006cdc8  retn
```
