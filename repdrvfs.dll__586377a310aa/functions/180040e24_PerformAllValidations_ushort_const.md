# PerformAllValidations(ushort const *)

- ea: `0x180040e24`
- end: `0x1800411b8`
- name: `?PerformAllValidations@@YAJPEBG@Z`
- size: `916`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180041610`
- `0x1800417f8`

## callees

- `0x1800012b8`
- `0x1800288a0`
- `0x180028a74`
- `0x1800292b8`
- `0x1800296d0`
- `0x18002b1b8`
- `0x18002bedc`
- `0x18002bfd0`
- `0x18002d75c`
- `0x18002d980`
- `0x1800403f4`
- `0x1800407e8`
- `0x180040e24`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180041157`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180041157`
- `wbemcomn!GetMemLogObject` at `0x180040e84`
- `wbemcomn!GetMemLogObject` at `0x180040f1a`
- `wbemcomn!GetMemLogObject` at `0x18004106e`
- `wbemcomn!GetMemLogObject` at `0x1800410e6`
- `wbemcomn!GetMemLogObject` at `0x180040e84`
- `wbemcomn!GetMemLogObject` at `0x180040f1a`
- `wbemcomn!GetMemLogObject` at `0x18004106e`
- `wbemcomn!GetMemLogObject` at `0x1800410e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040e8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040f25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041079`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800410f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040e8f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180040f25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041079`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800410f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PerformAllValidations(const unsigned __int16 *a1)
{
  unsigned int v2; // edi
  CMemoryLog *v3; // rax
  unsigned int v4; // edi
  CMemoryLog *MemLogObject; // rax
  CPageSource *v6; // rcx
  CPageSource *v7; // rcx
  CPageSource *v8; // rcx
  CPageSource *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // edi
  CMemoryLog *v12; // rax
  struct PageBlockMap *v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // esi
  CMemoryLog *v16; // rax
  union _LARGE_INTEGER v18; // [rsp+30h] [rbp-D0h] BYREF
  union _LARGE_INTEGER v19; // [rsp+38h] [rbp-C8h] BYREF
  union _LARGE_INTEGER v20; // [rsp+40h] [rbp-C0h] BYREF
  union _LARGE_INTEGER v21; // [rsp+48h] [rbp-B8h] BYREF
  struct PageBlockMap *v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+60h] [rbp-A0h]
  _BYTE v25[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v26; // [rsp+70h] [rbp-90h]
  unsigned int (__fastcall *v27)(CPageSource *__hidden, unsigned int); // [rsp+78h] [rbp-88h]
  int v28; // [rsp+80h] [rbp-80h]
  _BYTE v29[8]; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v30; // [rsp+90h] [rbp-70h]
  __int64 (__fastcall *v31)(CComServer *__hidden); // [rsp+98h] [rbp-68h]
  int v32; // [rsp+A0h] [rbp-60h]
  _BYTE v33[968]; // [rsp+B0h] [rbp-50h] BYREF
  void *v34; // [rsp+478h] [rbp+378h]
  void *v35; // [rsp+480h] [rbp+380h]
  void *v36; // [rsp+490h] [rbp+390h]
  void *v37; // [rsp+498h] [rbp+398h]
  _QWORD v38[4]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned int v39; // [rsp+4D0h] [rbp+3D0h]

  g_bPerformingVerify = 1;
  CPageSource::CPageSource((CPageSource *)v33);
  v2 = CPageSource::Init((CPageSource *)v33, 1, a1);
  if ( !v2 )
  {
    v25[0] = 0;
    v26 = v33;
    v27 = CPageSource::Shutdown;
    v28 = 0;
    v23 = 0;
    v24 = 0;
    v4 = CVarObjHeap::Initialize((CVarObjHeap *)&v23, (struct CPageSource *)v33);
    if ( v4 )
    {
      g_error = 1;
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v4);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v4);
      }
      g_bPerformingVerify = 0;
      goto LABEL_34;
    }
    v29[0] = 0;
    v30 = &v23;
    v31 = CComServer::Register;
    v32 = 0;
    memset_0(v38, 0, 0xA0u);
    v18.QuadPart = 0;
    v19.QuadPart = 0;
    v20.QuadPart = 0;
    v21.QuadPart = 0;
    if ( !CPageSource::GetFileSize(v6, v36, &v18)
      && !CPageSource::GetFileSize(v7, v37, &v19)
      && !CPageSource::GetFileSize(v8, v34, &v20)
      && !CPageSource::GetFileSize(v9, v35, &v21) )
    {
      v38[0] = v18.QuadPart;
      v38[1] = v19.QuadPart;
      v38[2] = v20.QuadPart;
      v38[3] = v21.QuadPart;
    }
    v22 = 0;
    v10 = CVarObjHeap::ValidateAllPages((CVarObjHeap *)&v23, &v22, (struct _RepStats *)v38);
    v11 = v10;
    if ( v10 )
    {
      if ( v10 == 14 )
      {
LABEL_33:
        g_bPerformingVerify = 0;
        ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v29);
LABEL_34:
        ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>::~ObjScopeGuardImpl1<CBTreeFile,unsigned long (CBTreeFile::*)(unsigned long),int>((__int64)v25);
        goto LABEL_35;
      }
      g_error = 1;
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, v11);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v11);
      }
    }
    v13 = v22;
    v14 = ValidateBTreeAgainstObjHeap(
            a1,
            (struct CPageSource *)v33,
            (struct CVarObjHeap *)&v23,
            v22,
            (struct _RepStats *)v38);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 != 14 )
      {
        g_error = 1;
        v16 = GetMemLogObject();
        CMemoryLog::Write(v16, v15);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v15);
        }
      }
    }
    CheckBlockMap(v13, v39);
    if ( v13 )
    {
      `eh vector destructor iterator'(v13, 0x28u, *((_QWORD *)v13 - 1), (void (*)(void *))PageBlockMap::~PageBlockMap);
      CWin32DefaultArena::WbemMemFree((char *)v13 - 8);
    }
    OutputStats((struct _RepStats *)v38);
    goto LABEL_33;
  }
  g_error = 1;
  v3 = GetMemLogObject();
  CMemoryLog::Write(v3, v2);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, v2);
  }
  g_bPerformingVerify = 0;
LABEL_35:
  CPageSource::~CPageSource((CPageSource *)v33);
  return 0;
}

```

## disassembly

```asm
0x180040e24  mov     [rsp-8+arg_8], rbx
0x180040e29  mov     [rsp-8+arg_10], rsi
0x180040e2e  push    rbp
0x180040e2f  push    rdi
0x180040e30  push    r14
0x180040e32  lea     rbp, [rsp-460h]
0x180040e3a  sub     rsp, 560h
0x180040e41  mov     rax, cs:__security_cookie
0x180040e48  xor     rax, rsp
0x180040e4b  mov     [rbp+470h+var_20], rax
0x180040e52  mov     rsi, rcx
0x180040e55  mov     cs:?g_bPerformingVerify@@3_NA, 1; bool g_bPerformingVerify
0x180040e5c  lea     rcx, [rbp+470h+var_4C0]; this
0x180040e60  call    ??0CPageSource@@QEAA@XZ; CPageSource::CPageSource(void)
0x180040e65  nop
0x180040e66  mov     r8, rsi; unsigned __int16 *
0x180040e69  mov     dl, 1; bool
0x180040e6b  lea     rcx, [rbp+470h+var_4C0]; this
0x180040e6f  call    ?Init@CPageSource@@QEAAK_NPEBG@Z; CPageSource::Init(bool,ushort const *)
0x180040e74  mov     edi, eax
0x180040e76  xor     r14d, r14d
0x180040e79  test    eax, eax
0x180040e7b  jz      short loc_180040ED7
0x180040e7d  mov     cs:?g_error@@3_NA, 1; bool g_error
0x180040e84  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180040e8a  mov     edx, edi
0x180040e8c  mov     rcx, rax
0x180040e8f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180040e95  lea     rbx, WPP_GLOBAL_Control
0x180040e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ea3  cmp     rcx, rbx
0x180040ea6  jz      short loc_180040ECB
0x180040ea8  test    byte ptr [rcx+1Ch], 1
0x180040eac  jz      short loc_180040ECB
0x180040eae  cmp     byte ptr [rcx+19h], 2
0x180040eb2  jb      short loc_180040ECB
0x180040eb4  lea     edx, [r14+11h]
0x180040eb8  mov     r9d, edi
0x180040ebb  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x180040ec2  mov     rcx, [rcx+10h]
0x180040ec6  call    WPP_SF_d
0x180040ecb  mov     cs:?g_bPerformingVerify@@3_NA, r14b; bool g_bPerformingVerify
0x180040ed2  jmp     loc_180041186
0x180040ed7  mov     [rsp+570h+var_508], r14b
0x180040edc  lea     rax, [rbp+470h+var_4C0]
0x180040ee0  mov     [rsp+570h+var_500], rax
0x180040ee5  lea     rax, ?Shutdown@CPageSource@@QEAAKK@Z; CPageSource::Shutdown(ulong)
0x180040eec  mov     [rsp+570h+var_4F8], rax
0x180040ef1  mov     [rbp+470h+var_4F0], r14d
0x180040ef5  mov     [rsp+570h+var_518], r14
0x180040efa  mov     [rsp+570h+var_510], r14d
0x180040eff  lea     rdx, [rbp+470h+var_4C0]; struct CPageSource *
0x180040f03  lea     rcx, [rsp+570h+var_518]; this
0x180040f08  call    ?Initialize@CVarObjHeap@@QEAAKPEAVCPageSource@@@Z; CVarObjHeap::Initialize(CPageSource *)
0x180040f0d  mov     edi, eax
0x180040f0f  test    eax, eax
0x180040f11  jz      short loc_180040F6E
0x180040f13  mov     cs:?g_error@@3_NA, 1; bool g_error
0x180040f1a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180040f20  mov     edx, edi
0x180040f22  mov     rcx, rax
0x180040f25  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180040f2b  lea     rbx, WPP_GLOBAL_Control
0x180040f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f39  cmp     rcx, rbx
0x180040f3c  jz      short loc_180040F62
0x180040f3e  test    byte ptr [rcx+1Ch], 1
0x180040f42  jz      short loc_180040F62
0x180040f44  cmp     byte ptr [rcx+19h], 2
0x180040f48  jb      short loc_180040F62
0x180040f4a  mov     edx, 12h
0x180040f4f  mov     r9d, edi
0x180040f52  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x180040f59  mov     rcx, [rcx+10h]
0x180040f5d  call    WPP_SF_d
0x180040f62  mov     cs:?g_bPerformingVerify@@3_NA, r14b; bool g_bPerformingVerify
0x180040f69  jmp     loc_18004117B
0x180040f6e  mov     [rbp+470h+var_4E8], r14b
0x180040f72  lea     rax, [rsp+570h+var_518]
0x180040f77  mov     [rbp+470h+var_4E0], rax
0x180040f7b  lea     rax, ?Register@CComServer@@UEAAJXZ; CComServer::Register(void)
0x180040f82  mov     [rbp+470h+var_4D8], rax
0x180040f86  mov     [rbp+470h+var_4D0], r14d
0x180040f8a  xor     edx, edx; Val
0x180040f8c  mov     r8d, 0A0h; Size
0x180040f92  lea     rcx, [rbp+470h+var_C0]; void *
0x180040f99  call    memset_0
0x180040f9e  mov     qword ptr [rsp+570h+var_540], r14
0x180040fa3  mov     qword ptr [rsp+570h+var_538], r14
0x180040fa8  mov     qword ptr [rsp+570h+var_530], r14
0x180040fad  mov     qword ptr [rsp+570h+var_528], r14
0x180040fb2  lea     r8, [rsp+570h+var_540]; union _LARGE_INTEGER *
0x180040fb7  mov     rdx, [rbp+470h+var_E0]; void *
0x180040fbe  call    ?GetFileSize@CPageSource@@QEAAKPEAXPEAT_LARGE_INTEGER@@@Z; CPageSource::GetFileSize(void *,_LARGE_INTEGER *)
0x180040fc3  test    eax, eax
0x180040fc5  jnz     short loc_180041036
0x180040fc7  lea     r8, [rsp+570h+var_538]; union _LARGE_INTEGER *
0x180040fcc  mov     rdx, [rbp+470h+var_D8]; void *
0x180040fd3  call    ?GetFileSize@CPageSource@@QEAAKPEAXPEAT_LARGE_INTEGER@@@Z; CPageSource::GetFileSize(void *,_LARGE_INTEGER *)
0x180040fd8  test    eax, eax
0x180040fda  jnz     short loc_180041036
0x180040fdc  lea     r8, [rsp+570h+var_530]; union _LARGE_INTEGER *
0x180040fe1  mov     rdx, [rbp+470h+var_F8]; void *
0x180040fe8  call    ?GetFileSize@CPageSource@@QEAAKPEAXPEAT_LARGE_INTEGER@@@Z; CPageSource::GetFileSize(void *,_LARGE_INTEGER *)
0x180040fed  test    eax, eax
0x180040fef  jnz     short loc_180041036
0x180040ff1  lea     r8, [rsp+570h+var_528]; union _LARGE_INTEGER *
0x180040ff6  mov     rdx, [rbp+470h+var_F0]; void *
0x180040ffd  call    ?GetFileSize@CPageSource@@QEAAKPEAXPEAT_LARGE_INTEGER@@@Z; CPageSource::GetFileSize(void *,_LARGE_INTEGER *)
0x180041002  test    eax, eax
0x180041004  jnz     short loc_180041036
0x180041006  mov     rax, qword ptr [rsp+570h+var_540]
0x18004100b  mov     [rbp+470h+var_C0], rax
0x180041012  mov     rax, qword ptr [rsp+570h+var_538]
0x180041017  mov     [rbp+470h+var_B8], rax
0x18004101e  mov     rax, qword ptr [rsp+570h+var_530]
0x180041023  mov     [rbp+470h+var_B0], rax
0x18004102a  mov     rax, qword ptr [rsp+570h+var_528]
0x18004102f  mov     [rbp+470h+var_A8], rax
0x180041036  mov     [rsp+570h+var_520], r14
0x18004103b  lea     r8, [rbp+470h+var_C0]; struct _RepStats *
0x180041042  lea     rdx, [rsp+570h+var_520]; struct PageBlockMap **
0x180041047  lea     rcx, [rsp+570h+var_518]; this
0x18004104c  call    ?ValidateAllPages@CVarObjHeap@@QEAAKPEAPEAVPageBlockMap@@AEAU_RepStats@@@Z; CVarObjHeap::ValidateAllPages(PageBlockMap * *,_RepStats &)
0x180041051  mov     edi, eax
0x180041053  lea     rbx, WPP_GLOBAL_Control
0x18004105a  test    eax, eax
0x18004105c  jz      short loc_1800410AF
0x18004105e  cmp     eax, 0Eh
0x180041061  jz      loc_18004116A
0x180041067  mov     cs:?g_error@@3_NA, 1; bool g_error
0x18004106e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180041074  mov     edx, edi
0x180041076  mov     rcx, rax
0x180041079  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004107f  mov     rcx, cs:WPP_GLOBAL_Control
0x180041086  cmp     rcx, rbx
0x180041089  jz      short loc_1800410AF
0x18004108b  test    byte ptr [rcx+1Ch], 1
0x18004108f  jz      short loc_1800410AF
0x180041091  cmp     byte ptr [rcx+19h], 2
0x180041095  jb      short loc_1800410AF
0x180041097  mov     edx, 13h
0x18004109c  mov     r9d, edi
0x18004109f  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x1800410a6  mov     rcx, [rcx+10h]
0x1800410aa  call    WPP_SF_d
0x1800410af  lea     rax, [rbp+470h+var_C0]
0x1800410b6  mov     [rsp+570h+var_550], rax; struct _RepStats *
0x1800410bb  mov     rdi, [rsp+570h+var_520]
0x1800410c0  mov     r9, rdi; struct PageBlockMap *
0x1800410c3  lea     r8, [rsp+570h+var_518]; struct CVarObjHeap *
0x1800410c8  lea     rdx, [rbp+470h+var_4C0]; struct CPageSource *
0x1800410cc  mov     rcx, rsi; unsigned __int16 *
0x1800410cf  call    ?ValidateBTreeAgainstObjHeap@@YAKPEBGAEAVCPageSource@@AEAVCVarObjHeap@@PEAVPageBlockMap@@AEAU_RepStats@@@Z; ValidateBTreeAgainstObjHeap(ushort const *,CPageSource &,CVarObjHeap &,PageBlockMap *,_RepStats &)
0x1800410d4  mov     esi, eax
0x1800410d6  test    eax, eax
0x1800410d8  jz      short loc_180041127
0x1800410da  cmp     eax, 0Eh
0x1800410dd  jz      short loc_180041127
0x1800410df  mov     cs:?g_error@@3_NA, 1; bool g_error
0x1800410e6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800410ec  mov     edx, esi
0x1800410ee  mov     rcx, rax
0x1800410f1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800410f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800410fe  cmp     rcx, rbx
0x180041101  jz      short loc_180041127
0x180041103  test    byte ptr [rcx+1Ch], 1
0x180041107  jz      short loc_180041127
0x180041109  cmp     byte ptr [rcx+19h], 2
0x18004110d  jb      short loc_180041127
0x18004110f  mov     edx, 14h
0x180041114  mov     r9d, esi
0x180041117  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x18004111e  mov     rcx, [rcx+10h]
0x180041122  call    WPP_SF_d
0x180041127  mov     edx, [rbp+470h+var_A0]; unsigned int
0x18004112d  mov     rcx, rdi; struct PageBlockMap *
0x180041130  call    ?CheckBlockMap@@YAXPEAVPageBlockMap@@K@Z; CheckBlockMap(PageBlockMap *,ulong)
0x180041135  test    rdi, rdi
0x180041138  jz      short loc_18004115E
0x18004113a  lea     r9, ??1PageBlockMap@@QEAA@XZ; void (*)(void *)
0x180041141  mov     r8, [rdi-8]; unsigned __int64
0x180041145  mov     edx, 28h ; '('; unsigned __int64
0x18004114a  mov     rcx, rdi; void *
0x18004114d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180041152  nop
0x180041153  lea     rcx, [rdi-8]
0x180041157  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18004115d  nop
0x18004115e  lea     rcx, [rbp+470h+var_C0]; struct _RepStats *
0x180041165  call    ?OutputStats@@YAXAEAU_RepStats@@@Z; OutputStats(_RepStats &)
0x18004116a  mov     cs:?g_bPerformingVerify@@3_NA, r14b; bool g_bPerformingVerify
0x180041171  lea     rcx, [rbp+470h+var_4E8]
0x180041175  call    ??1?$ObjScopeGuardImpl1@VCBTreeFile@@P81@EAAKK@ZH@@QEAA@XZ; ObjScopeGuardImpl1<CBTreeFile,ulong (CBTreeFile::*)(ulong),int>::~ObjScopeGuardImpl1<CBTreeFile,ulong (CBTreeFile::*)(ulong),int>(void)
0x18004117a  nop
0x18004117b  lea     rcx, [rsp+570h+var_508]
0x180041180  call    ??1?$ObjScopeGuardImpl1@VCBTreeFile@@P81@EAAKK@ZH@@QEAA@XZ; ObjScopeGuardImpl1<CBTreeFile,ulong (CBTreeFile::*)(ulong),int>::~ObjScopeGuardImpl1<CBTreeFile,ulong (CBTreeFile::*)(ulong),int>(void)
0x180041185  nop
0x180041186  lea     rcx, [rbp+470h+var_4C0]; this
0x18004118a  call    ??1CPageSource@@QEAA@XZ; CPageSource::~CPageSource(void)
0x18004118f  xor     eax, eax
0x180041191  mov     rcx, [rbp+470h+var_20]
0x180041198  xor     rcx, rsp; StackCookie
0x18004119b  call    __security_check_cookie
0x1800411a0  lea     r11, [rsp+570h+var_10]
0x1800411a8  mov     rbx, [r11+28h]
0x1800411ac  mov     rsi, [r11+30h]
0x1800411b0  mov     rsp, r11
0x1800411b3  pop     r14
0x1800411b5  pop     rdi
0x1800411b6  pop     rbp
0x1800411b7  retn
```
