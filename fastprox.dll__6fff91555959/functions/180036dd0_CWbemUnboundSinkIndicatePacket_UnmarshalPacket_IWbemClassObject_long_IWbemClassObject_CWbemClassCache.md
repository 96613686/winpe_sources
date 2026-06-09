# CWbemUnboundSinkIndicatePacket::UnmarshalPacket(IWbemClassObject * &,long &,IWbemClassObject * * &,CWbemClassCache &)

- ea: `0x180036dd0`
- end: `0x18003704e`
- name: `?UnmarshalPacket@CWbemUnboundSinkIndicatePacket@@QEAAJAEAPEAUIWbemClassObject@@AEAJAEAPEAPEAU2@AEAVCWbemClassCache@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(CWbemUnboundSinkIndicatePacket *this, struct IWbemClassObject **, int *, struct IWbemClassObject ***, struct CWbemClassCache *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180035b64`

## callees

- `0x1800158e0`
- `0x180018ab0`
- `0x180018b20`
- `0x180036a90`
- `0x180036dd0`
- `0x180037120`
- `0x18005d5f0`
- `0x18006fa66`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180036dfd`
- `wbemcomn!GetMemLogObject` at `0x180036e59`
- `wbemcomn!GetMemLogObject` at `0x180036ea7`
- `wbemcomn!GetMemLogObject` at `0x180036ee9`
- `wbemcomn!GetMemLogObject` at `0x180036ff3`
- `wbemcomn!GetMemLogObject` at `0x180036dfd`
- `wbemcomn!GetMemLogObject` at `0x180036e59`
- `wbemcomn!GetMemLogObject` at `0x180036ea7`
- `wbemcomn!GetMemLogObject` at `0x180036ee9`
- `wbemcomn!GetMemLogObject` at `0x180036ff3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036e0d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036e64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036eb5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ef7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ffe`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036e0d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036e64`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036eb5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ef7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036ffe`

## pseudocode

```c
__int64 __fastcall CWbemUnboundSinkIndicatePacket::UnmarshalPacket(
        CWbemUnboundSinkIndicatePacket *this,
        struct IWbemClassObject **a2,
        int *a3,
        struct IWbemClassObject ***a4,
        struct CWbemClassCache *a5)
{
  __int64 v5; // rbp
  CMemoryLog *v10; // rax
  int IsValid; // ebx
  CWbemRefreshingSvc *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  CMemoryLog *MemLogObject; // rax
  unsigned int v16; // eax
  CMemoryLog *v17; // rax
  CWbemRefreshingSvc *v18; // rcx
  __int64 v19; // rdx
  CMemoryLog *v20; // rax
  const void *v22; // r12
  unsigned int v23; // esi
  unsigned int v24; // ecx
  unsigned __int8 *v25; // rax
  unsigned __int8 *v26; // rbp
  struct IWbemClassObject *v27; // rax
  __int64 v28; // rcx
  CMemoryLog *v29; // rax
  _BYTE v30[88]; // [rsp+20h] [rbp-58h] BYREF

  v5 = *((_QWORD *)this + 2);
  *a4 = 0;
  if ( v5 )
  {
    IsValid = CWbemDataPacket::IsValid(this, 0);
    if ( IsValid < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, IsValid);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)IsValid;
      }
      v13 = 13;
      goto LABEL_39;
    }
    v16 = *((_DWORD *)this + 2);
    if ( v16 < 0x1A )
    {
      v17 = GetMemLogObject();
      CMemoryLog::Write(v17, -2147217348);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749948LL;
      }
      v19 = 14;
LABEL_21:
      WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_8c4af607cb753a8cd86772b28617c5a0_Traceguids, 2147749948LL);
      return 2147749948LL;
    }
    if ( v16 - 26 < 0xC )
    {
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -2147217348);
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749948LL;
      }
      v19 = 15;
      goto LABEL_21;
    }
    v22 = (const void *)(v5 + 12);
    v23 = v16 - 38;
    v24 = *(_DWORD *)(*((_QWORD *)this + 2) + 8LL);
    if ( v24 )
    {
      if ( v24 > v23 )
        return 2147942413LL;
      v25 = CBasicBlobControl::sAllocate(v24);
      v26 = v25;
      if ( !v25
        || (memcpy_0(v25, v22, *(unsigned int *)(*((_QWORD *)this + 2) + 8LL)),
            v27 = (struct IWbemClassObject *)CWbemObject::CreateFromMemory(
                                               v26,
                                               *(_DWORD *)(*((_QWORD *)this + 2) + 8LL),
                                               1,
                                               (struct CBlobControl *)g_CBasicBlobControl),
            (*a2 = v27) == 0) )
      {
        IsValid = -2147217402;
      }
      if ( IsValid < 0 )
        goto LABEL_34;
    }
    else
    {
      *a2 = 0;
    }
    v28 = *(unsigned int *)(*((_QWORD *)this + 2) + 8LL);
    if ( (unsigned int)v28 > v23 )
      return 2147942413LL;
    CWbemObjectArrayPacket::SetData((CWbemObjectArrayPacket *)v30, (unsigned __int8 *)v22 + v28, v23 - v28, 1);
    IsValid = CWbemObjectArrayPacket::UnmarshalPacket((CWbemObjectArrayPacket *)v30, a3, a4, a5);
    if ( IsValid >= 0 )
    {
LABEL_35:
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)IsValid;
      }
      v13 = 16;
LABEL_39:
      v14 = (unsigned int)IsValid;
      goto LABEL_40;
    }
LABEL_34:
    v29 = GetMemLogObject();
    CMemoryLog::Write(v29, IsValid);
    goto LABEL_35;
  }
  v10 = GetMemLogObject();
  IsValid = -2147217398;
  CMemoryLog::Write(v10, -2147217398);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)IsValid;
  }
  v13 = 12;
  v14 = 2147749898LL;
LABEL_40:
  WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_8c4af607cb753a8cd86772b28617c5a0_Traceguids, v14);
  return (unsigned int)IsValid;
}

```

## disassembly

```asm
0x180036dd0  push    rbx
0x180036dd2  push    rbp
0x180036dd3  push    rsi
0x180036dd4  push    rdi
0x180036dd5  push    r12
0x180036dd7  push    r13
0x180036dd9  push    r14
0x180036ddb  push    r15
0x180036ddd  sub     rsp, 38h
0x180036de1  mov     rbp, [rcx+10h]
0x180036de5  mov     r15, r9
0x180036de8  mov     qword ptr [r9], 0
0x180036def  mov     r13, r8
0x180036df2  mov     r14, rdx
0x180036df5  mov     rdi, rcx
0x180036df8  test    rbp, rbp
0x180036dfb  jnz     short loc_180036E4C
0x180036dfd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036e03  mov     ebx, 8004100Ah
0x180036e08  mov     rcx, rax
0x180036e0b  mov     edx, ebx
0x180036e0d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036e13  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180036e1a  lea     rax, WPP_GLOBAL_Control
0x180036e21  cmp     rcx, rax
0x180036e24  jz      loc_18003703B
0x180036e2a  test    byte ptr [rcx+1Ch], 1
0x180036e2e  jz      loc_18003703B
0x180036e34  cmp     byte ptr [rcx+19h], 2
0x180036e38  jb      loc_18003703B
0x180036e3e  lea     edx, [rbp+0Ch]
0x180036e41  mov     r9d, 8004100Ah
0x180036e47  jmp     loc_18003702B
0x180036e4c  xor     edx, edx; int
0x180036e4e  call    ?IsValid@CWbemDataPacket@@QEAAJJ@Z; CWbemDataPacket::IsValid(long)
0x180036e53  mov     ebx, eax
0x180036e55  test    eax, eax
0x180036e57  jns     short loc_180036E9F
0x180036e59  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036e5f  mov     rcx, rax
0x180036e62  mov     edx, ebx
0x180036e64  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e71  lea     rax, WPP_GLOBAL_Control
0x180036e78  cmp     rcx, rax
0x180036e7b  jz      loc_18003703B
0x180036e81  test    byte ptr [rcx+1Ch], 1
0x180036e85  jz      loc_18003703B
0x180036e8b  cmp     byte ptr [rcx+19h], 2
0x180036e8f  jb      loc_18003703B
0x180036e95  mov     edx, 0Dh
0x180036e9a  jmp     loc_180037028
0x180036e9f  mov     eax, [rdi+8]
0x180036ea2  cmp     eax, 1Ah
0x180036ea5  jnb     short loc_180036EE1
0x180036ea7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036ead  mov     rcx, rax
0x180036eb0  mov     edx, 8004103Ch
0x180036eb5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ec2  lea     rax, WPP_GLOBAL_Control
0x180036ec9  cmp     rcx, rax
0x180036ecc  jz      short loc_180036F37
0x180036ece  test    byte ptr [rcx+1Ch], 1
0x180036ed2  jz      short loc_180036F37
0x180036ed4  cmp     byte ptr [rcx+19h], 2
0x180036ed8  jb      short loc_180036F37
0x180036eda  mov     edx, 0Eh
0x180036edf  jmp     short loc_180036F21
0x180036ee1  lea     esi, [rax-1Ah]
0x180036ee4  cmp     esi, 0Ch
0x180036ee7  jnb     short loc_180036F41
0x180036ee9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036eef  mov     rcx, rax
0x180036ef2  mov     edx, 8004103Ch
0x180036ef7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f04  lea     rax, WPP_GLOBAL_Control
0x180036f0b  cmp     rcx, rax
0x180036f0e  jz      short loc_180036F37
0x180036f10  test    byte ptr [rcx+1Ch], 1
0x180036f14  jz      short loc_180036F37
0x180036f16  cmp     byte ptr [rcx+19h], 2
0x180036f1a  jb      short loc_180036F37
0x180036f1c  mov     edx, 0Fh
0x180036f21  mov     rcx, [rcx+10h]
0x180036f25  lea     r8, WPP_8c4af607cb753a8cd86772b28617c5a0_Traceguids
0x180036f2c  mov     r9d, 8004103Ch
0x180036f32  call    WPP_SF_d
0x180036f37  mov     eax, 8004103Ch
0x180036f3c  jmp     loc_18003703D
0x180036f41  mov     rax, [rdi+10h]
0x180036f45  lea     r12, [rbp+0Ch]
0x180036f49  add     esi, 0FFFFFFF4h
0x180036f4c  mov     ecx, [rax+8]; int
0x180036f4f  test    ecx, ecx
0x180036f51  jz      short loc_180036FA6
0x180036f53  cmp     ecx, esi
0x180036f55  ja      short loc_180036FB8
0x180036f57  call    ?sAllocate@CBasicBlobControl@@SAPEAEH@Z; CBasicBlobControl::sAllocate(int)
0x180036f5c  mov     rbp, rax
0x180036f5f  test    rax, rax
0x180036f62  jz      short loc_180036F9B
0x180036f64  mov     rcx, [rdi+10h]
0x180036f68  mov     rdx, r12; Src
0x180036f6b  mov     r8d, [rcx+8]; Size
0x180036f6f  mov     rcx, rax; void *
0x180036f72  call    memcpy_0
0x180036f77  mov     rdx, [rdi+10h]
0x180036f7b  lea     r9, ?g_CBasicBlobControl@@3VCBasicBlobControl@@A; struct CBlobControl *
0x180036f82  mov     r8d, 1; int
0x180036f88  mov     rcx, rbp; unsigned __int8 *
0x180036f8b  mov     edx, [rdx+8]; int
0x180036f8e  call    ?CreateFromMemory@CWbemObject@@SAPEAV1@PEAEHHAEAVCBlobControl@@@Z; CWbemObject::CreateFromMemory(uchar *,int,int,CBlobControl &)
0x180036f93  mov     [r14], rax
0x180036f96  test    rax, rax
0x180036f99  jnz     short loc_180036FA0
0x180036f9b  mov     ebx, 80041006h
0x180036fa0  test    ebx, ebx
0x180036fa2  js      short loc_180036FF3
0x180036fa4  jmp     short loc_180036FAD
0x180036fa6  mov     qword ptr [r14], 0
0x180036fad  mov     rax, [rdi+10h]
0x180036fb1  mov     ecx, [rax+8]
0x180036fb4  cmp     ecx, esi
0x180036fb6  jbe     short loc_180036FBF
0x180036fb8  mov     eax, 8007000Dh
0x180036fbd  jmp     short loc_18003703D
0x180036fbf  sub     esi, ecx
0x180036fc1  lea     rdx, [r12+rcx]; unsigned __int8 *
0x180036fc5  mov     r8d, esi; unsigned int
0x180036fc8  lea     rcx, [rsp+78h+var_58]; this
0x180036fcd  mov     r9b, 1; bool
0x180036fd0  call    ?SetData@CWbemObjectArrayPacket@@QEAAXPEAEK_N@Z; CWbemObjectArrayPacket::SetData(uchar *,ulong,bool)
0x180036fd5  mov     r9, [rsp+78h+arg_20]; struct CWbemClassCache *
0x180036fdd  lea     rcx, [rsp+78h+var_58]; this
0x180036fe2  mov     r8, r15; struct IWbemClassObject ***
0x180036fe5  mov     rdx, r13; int *
0x180036fe8  call    ?UnmarshalPacket@CWbemObjectArrayPacket@@QEAAJAEAJAEAPEAPEAUIWbemClassObject@@AEAVCWbemClassCache@@@Z; CWbemObjectArrayPacket::UnmarshalPacket(long &,IWbemClassObject * * &,CWbemClassCache &)
0x180036fed  mov     ebx, eax
0x180036fef  test    eax, eax
0x180036ff1  jns     short loc_180037004
0x180036ff3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036ff9  mov     rcx, rax
0x180036ffc  mov     edx, ebx
0x180036ffe  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180037004  mov     rcx, cs:WPP_GLOBAL_Control
0x18003700b  lea     rax, WPP_GLOBAL_Control
0x180037012  cmp     rcx, rax
0x180037015  jz      short loc_18003703B
0x180037017  test    byte ptr [rcx+1Ch], 1
0x18003701b  jz      short loc_18003703B
0x18003701d  cmp     byte ptr [rcx+19h], 2
0x180037021  jb      short loc_18003703B
0x180037023  mov     edx, 10h
0x180037028  mov     r9d, ebx
0x18003702b  mov     rcx, [rcx+10h]
0x18003702f  lea     r8, WPP_8c4af607cb753a8cd86772b28617c5a0_Traceguids
0x180037036  call    WPP_SF_d
0x18003703b  mov     eax, ebx
0x18003703d  add     rsp, 38h
0x180037041  pop     r15
0x180037043  pop     r14
0x180037045  pop     r13
0x180037047  pop     r12
0x180037049  pop     rdi
0x18003704a  pop     rsi
0x18003704b  pop     rbp
0x18003704c  pop     rbx
0x18003704d  retn
```
