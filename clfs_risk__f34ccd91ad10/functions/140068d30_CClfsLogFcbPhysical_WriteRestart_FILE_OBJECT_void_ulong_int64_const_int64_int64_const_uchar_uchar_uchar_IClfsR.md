# CClfsLogFcbPhysical::WriteRestart(_FILE_OBJECT *,void *,ulong,__int64 const &,__int64 &,__int64 const &,uchar,uchar,uchar,IClfsRequestAsync *,_CLS_LSN const &,_CLS_LSN const &,_CLS_LSN &,_CLS_LSN &,ulong &,__int64 &)

- ea: `0x140068d30`
- end: `0x140069449`
- name: `?WriteRestart@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@PEAXKAEB_JAEA_J2EEEPEAUIClfsRequestAsync@@AEBT_CLS_LSN@@5AEAT4@6AEAK3@Z`
- size: `1817`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct _FILE_OBJECT *@<rdx>, void *@<r8>, unsigned int@<r9d>, const __int64 *, __int64 *, const __int64 *, char, char, char, struct IClfsRequestAsync *, CLFS_LSN *plsn, const union _CLS_LSN *, union _CLS_LSN *, union _CLS_LSN *, unsigned int *, __int64 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1400035a8`
- `0x140005840`
- `0x140005f00`
- `0x1400075b0`
- `0x140008c40`
- `0x14000a29c`
- `0x14000c018`
- `0x14000c6e8`
- `0x14000ed64`
- `0x140010548`
- `0x140017f20`
- `0x1400664b0`
- `0x140067458`
- `0x140068d30`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140068dc3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140069183`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140069191`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007b0cf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140068dc3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140069183`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140069191`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14007b0cf`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400690c2`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400690c2`

## string_xrefs

- `0x14006914c`: `CClfsLogFcbPhysical::WriteRestart`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::WriteRestart(
        CLFS_LSN *this,
        struct _FILE_OBJECT *a2,
        unsigned __int64 a3,
        unsigned int a4,
        const __int64 *a5,
        __int64 *a6,
        const __int64 *a7,
        char a8,
        char a9,
        char a10,
        struct IClfsRequestAsync *a11,
        CLFS_LSN *plsn,
        const union _CLS_LSN *a13,
        union _CLS_LSN *a14,
        union _CLS_LSN *a15,
        unsigned int *a16,
        __int64 *a17)
{
  const union _CLS_LSN *v18; // rdi
  struct _ERESOURCE *v19; // r12
  BOOLEAN v20; // bl
  int v21; // edi
  __int64 v22; // rdx
  ULONGLONG ullOffset; // r8
  CLFS_LSN *v24; // rbx
  struct IClfsRequestAsync *v25; // r14
  struct _FILE_OBJECT *v26; // rax
  CLFS_CONTAINER_ID cidContainer; // eax
  CLFS_LSN *v28; // r13
  CLFS_LSN v29; // rcx
  CLFS_LSN *v30; // r15
  __int64 (__fastcall *v31)(CLFS_LSN *, struct _FILE_OBJECT *, unsigned __int64, _QWORD, __int64 *, __int64 *, const __int64 *, _BYTE, struct IClfsRequestAsync *, const CLFS_LSN *, __int64 *, __int64 *, union _CLS_LSN *, CLFS_LSN *, CLFS_LSN *); // r10
  int v32; // ebx
  CLFS_LSN v34; // rbx
  ULONG v35; // eax
  CLFS_LSN v36; // rax
  struct _FILE_OBJECT *v37; // rax
  BOOLEAN v38; // r9
  CLFS_LSN *v39; // rcx
  CLFS_LSN *v40; // rax
  __int64 v42; // [rsp+28h] [rbp-F0h]
  BOOLEAN v43; // [rsp+80h] [rbp-98h]
  CLFS_LSN v44; // [rsp+90h] [rbp-88h] BYREF
  CLFS_LSN v45; // [rsp+98h] [rbp-80h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-70h]
  CLFS_LSN v48; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-60h] BYREF
  CLFS_LSN v50; // [rsp+C0h] [rbp-58h] BYREF
  CLFS_RECORD_INDEX v51; // [rsp+C8h] [rbp-50h]
  CLFS_CONTAINER_ID v52; // [rsp+CCh] [rbp-4Ch]
  CLFS_LSN v53; // [rsp+D0h] [rbp-48h] BYREF
  unsigned __int64 v55; // [rsp+130h] [rbp+18h] BYREF
  unsigned int v56; // [rsp+138h] [rbp+20h]

  v56 = a4;
  v55 = a3;
  v45 = CLFS_LSN_INVALID;
  v48 = CLFS_LSN_INVALID;
  v46 = 0;
  v47 = 0;
  if ( !a3 )
    return 3221225485LL;
  v18 = a13;
  if ( a13 )
  {
    if ( CLFS_LSN_INVALID.ullOffset == a13->ullOffset )
      return 3221225485LL;
  }
  *a16 = 0;
  *a17 = 0;
  v19 = (struct _ERESOURCE *)&this[25];
  v20 = ExAcquireResourceExclusiveLite((PERESOURCE)&this[25], 1u);
  v43 = v20;
  if ( (this[45].offset.cidContainer & 0x1000) == 0 )
  {
    v24 = plsn;
    if ( ClfsLsnBlockOffset(plsn) >= this[87].ullOffset )
    {
      v21 = -1073741811;
      goto LABEL_8;
    }
    if ( a10 )
      goto LABEL_18;
    if ( ClfsLsnLess(v24, this + 61) )
    {
LABEL_11:
      v21 = -1072037860;
      goto LABEL_8;
    }
    if ( !a8 || v24 && CLFS_LSN_INVALID.ullOffset == v24->ullOffset || !ClfsLsnLess(v24, this + 60) )
    {
LABEL_18:
      v25 = a11;
    }
    else
    {
      v25 = a11;
      v26 = (struct _FILE_OBJECT *)(*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a11 + 56LL))(a11);
      if ( (int)CClfsLogFcbPhysical::CacheBlock((CClfsLogFcbPhysical *)this, v26, v24, (unsigned int *)&v44) < 0 )
        goto LABEL_11;
    }
    cidContainer = this[45].offset.cidContainer;
    if ( (cidContainer & 0x100) == 0 && (cidContainer & 0x200) == 0 || !v25 )
    {
      this[45].offset.cidContainer = cidContainer | 0x100;
      v28 = this + 61;
      v29 = this[61];
      this[65] = v29;
      this[66] = this[64];
      if ( v24 && CLFS_LSN_INVALID.ullOffset == v24->ullOffset )
      {
        v30 = this + 67;
        this[67] = v29;
      }
      else
      {
        if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))operator<=)(
                                 &this[61],
                                 v24,
                                 (const CLFS_LSN)CLFS_LSN_INVALID.ullOffset) )
        {
          v21 = -1072037860;
          goto LABEL_56;
        }
        v30 = this + 67;
        this[67] = *v24;
      }
      this[68] = *v18;
      v31 = *(__int64 (__fastcall **)(CLFS_LSN *, struct _FILE_OBJECT *, unsigned __int64, _QWORD, __int64 *, __int64 *, const __int64 *, _BYTE, struct IClfsRequestAsync *, const CLFS_LSN *, __int64 *, __int64 *, union _CLS_LSN *, CLFS_LSN *, CLFS_LSN *))(this->ullOffset + 120);
      v49 = *a5;
      v21 = v31(this, a2, v55, v56, &v49, a6, a7, 0, v25, &CLFS_LSN_NULL, &v46, a17, a15, &v45, &v48);
      if ( v21 >= 0 )
      {
        LODWORD(v55) = 0;
        v32 = 0;
        v50 = CLFS_LSN_NULL;
        ClfsReleaseResourceLite(v19);
        while ( ExIsResourceAcquiredExclusiveLite(v19) )
        {
          ++v32;
          ClfsReleaseResourceLite(v19);
        }
        v21 = (*(__int64 (__fastcall **)(CLFS_LSN *, CLFS_LSN *, _QWORD, _QWORD, unsigned __int64 *))(this->ullOffset + 192))(
                this,
                &v50,
                0,
                0,
                &v55);
        if ( v21 < 0 )
        {
          if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
          {
            LODWORD(v42) = v21;
            WPP_SF_slD(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              59,
              (unsigned int)WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids,
              (unsigned int)"CClfsLogFcbPhysical::WriteRestart",
              238,
              v42);
          }
          v21 = -1072037841;
        }
        while ( v32-- )
          ExAcquireResourceExclusiveLite(v19, 1u);
        v43 = ExAcquireResourceExclusiveLite(v19, 1u);
      }
      *a14 = *a15;
      if ( !v21 )
      {
        *a16 = v47;
        v34 = *(CLFS_LSN *)(*(__int64 (__fastcall **)(CLFS_LSN *, unsigned __int64 *))(this->ullOffset + 352))(
                             this,
                             &v55);
        v44 = v34;
        if ( (unsigned __int8)operator!=(v30, &this[61]) )
          *v28 = *v30;
        v35 = ClfsLsnRecordSequence(this + 68);
        if ( v45.offset.cidContainer == -1 || (v35 & 0xFFFFFE00) != 0 )
        {
          v36 = CLFS_LSN_INVALID;
        }
        else
        {
          v52 = v45.offset.cidContainer;
          v51 = v45.offset.idxRecord & 0xFFFFFE00 | v35;
          v55 = __PAIR64__(v45.offset.cidContainer, v51);
          v36.ullOffset = __PAIR64__(v45.offset.cidContainer, v51);
        }
        this[64] = v36;
        if ( (this[47].offset.idxRecord & 0x20) == 0 )
          this[62] = *v28;
        v21 = (*(__int64 (__fastcall **)(CLFS_LSN *))(this->ullOffset + 112))(this);
        if ( v21 >= 0 )
        {
          v37 = (struct _FILE_OBJECT *)(*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)v25 + 56LL))(v25);
          CClfsLogFcbPhysical::WrapContainers((CClfsLogFcbPhysical *)this, v37);
          CClfsLogFcbCommon::NotifyObservers((CClfsLogFcbCommon *)this, 0xCF00u, v30, 0);
          v53 = *(CLFS_LSN *)(*(__int64 (__fastcall **)(CLFS_LSN *, unsigned __int64 *))(this->ullOffset + 352))(
                               this,
                               &v55);
          if ( __PAIR64__(v44.offset.cidContainer, v34.offset.idxRecord) < v53.ullOffset )
            CClfsLogFcbPhysical::PurgeCacheSection((CClfsLogFcbPhysical *)this, &v44, &v53, v38);
        }
      }
      ullOffset = CLFS_LSN_INVALID.ullOffset;
      goto LABEL_56;
    }
    (**(void (__fastcall ***)(struct IClfsRequestAsync *))v25)(v25);
    (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)v25 + 104LL))(v25);
    v21 = (*(__int64 (__fastcall **)(CLFS_LSN *, struct IClfsRequestAsync *))(this[76].ullOffset + 408))(this + 76, v25);
    if ( v21 )
      (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)v25 + 8LL))(v25);
    else
      v21 = 259;
LABEL_8:
    ullOffset = CLFS_LSN_INVALID.ullOffset;
LABEL_56:
    v20 = v43;
    goto LABEL_57;
  }
  v21 = -1072037845;
  CClfsLogFcbCommon::SetInvalidLogTag((CClfsLogFcbCommon *)this, 0xCu, -1072037845);
  ullOffset = CLFS_LSN_INVALID.ullOffset;
LABEL_57:
  if ( v21 != 259 )
  {
    v39 = this + 65;
    if ( v21 < 0 )
    {
      if ( this == (CLFS_LSN *)-520LL || ullOffset != v39->ullOffset )
      {
        this[61] = *v39;
        ullOffset = CLFS_LSN_INVALID.ullOffset;
      }
      v40 = this + 66;
      if ( this == (CLFS_LSN *)-528LL || ullOffset != v40->ullOffset )
      {
        this[64] = *v40;
        ullOffset = CLFS_LSN_INVALID.ullOffset;
      }
      a15->ullOffset = ullOffset;
    }
    this[45].offset.cidContainer &= ~0x100u;
    *v39 = CLFS_LSN_INVALID;
    this[66] = CLFS_LSN_INVALID;
    this[67] = CLFS_LSN_INVALID;
    this[68] = CLFS_LSN_INVALID;
    (*(void (__fastcall **)(CLFS_LSN *, _QWORD, ULONGLONG))(this[76].ullOffset + 432))(this + 76, 0, ullOffset);
  }
  if ( v20 )
    ClfsReleaseResourceLite(v19);
  if ( !a9 && v21 >= 0 && v21 != 259 )
    (*(void (__fastcall **)(CLFS_LSN *, __int64, ULONGLONG))(this->ullOffset + 232))(this, v22, ullOffset);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140068d30  mov     r11, rsp
0x140068d33  mov     [r11+20h], r9d
0x140068d37  mov     [r11+18h], r8
0x140068d3b  mov     [r11+10h], rdx
0x140068d3f  mov     [r11+8], rcx
0x140068d43  push    rbx
0x140068d44  push    rsi
0x140068d45  push    rdi
0x140068d46  push    r12
0x140068d48  push    r13
0x140068d4a  push    r14
0x140068d4c  push    r15
0x140068d4e  sub     rsp, 0E0h
0x140068d55  mov     rsi, rcx
0x140068d58  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140068d5f  mov     [r11-80h], rax
0x140068d63  mov     [r11-68h], rax
0x140068d67  xor     r15d, r15d
0x140068d6a  mov     [r11-78h], r15
0x140068d6e  mov     [r11-70h], r15
0x140068d72  test    r8, r8
0x140068d75  jz      loc_140069430
0x140068d7b  mov     rdi, [rsp+118h+arg_60]
0x140068d83  test    rdi, rdi
0x140068d86  jz      short loc_140068D91
0x140068d88  cmp     rax, [rdi]
0x140068d8b  jz      loc_140069430
0x140068d91  mov     [rsp+118h+var_94], r15d
0x140068d99  mov     [rsp+118h+var_98], r15b
0x140068da1  mov     rax, [rsp+118h+arg_78]
0x140068da9  mov     [rax], r15d
0x140068dac  mov     rax, [rsp+118h+arg_80]
0x140068db4  mov     [rax], r15
0x140068db7  lea     r12, [rcx+0C8h]
0x140068dbe  mov     dl, 1; Wait
0x140068dc0  mov     rcx, r12; Resource
0x140068dc3  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140068dca  nop     dword ptr [rax+rax+00h]
0x140068dcf  mov     bl, al
0x140068dd1  mov     [rsp+118h+var_98], al
0x140068dd8  test    dword ptr [rsi+16Ch], 1000h
0x140068de2  jz      short loc_140068E0C
0x140068de4  mov     edi, 0C01A002Bh
0x140068de9  mov     [rsp+118h+var_94], edi
0x140068df0  mov     r8d, edi; int
0x140068df3  mov     edx, 0Ch; unsigned int
0x140068df8  mov     rcx, rsi; this
0x140068dfb  call    ?SetInvalidLogTag@CClfsLogFcbCommon@@QEAAXKJ@Z; CClfsLogFcbCommon::SetInvalidLogTag(ulong,long)
0x140068e00  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x140068e07  jmp     loc_140069345
0x140068e0c  mov     rbx, [rsp+118h+plsn]
0x140068e14  mov     rcx, rbx; plsn
0x140068e17  call    ClfsLsnBlockOffset
0x140068e1c  mov     eax, eax
0x140068e1e  cmp     rax, [rsi+2B8h]
0x140068e25  jb      short loc_140068E3F
0x140068e27  mov     edi, 0C000000Dh
0x140068e2c  mov     [rsp+118h+var_94], edi
0x140068e33  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x140068e3a  jmp     loc_14006933E
0x140068e3f  cmp     [rsp+118h+arg_48], r15b
0x140068e47  jnz     loc_140068ECF
0x140068e4d  lea     rdx, [rsi+1E8h]; plsn2
0x140068e54  mov     rcx, rbx; plsn1
0x140068e57  call    ClfsLsnLess
0x140068e5c  test    al, al
0x140068e5e  jz      short loc_140068E67
0x140068e60  mov     edi, 0C01A001Ch
0x140068e65  jmp     short loc_140068E2C
0x140068e67  cmp     [rsp+118h+arg_38], r15b
0x140068e6f  jz      short loc_140068ECF
0x140068e71  test    rbx, rbx
0x140068e74  jz      short loc_140068E82
0x140068e76  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140068e7d  cmp     rax, [rbx]
0x140068e80  jz      short loc_140068ECF
0x140068e82  lea     rdx, [rsi+1E0h]; plsn2
0x140068e89  mov     rcx, rbx; plsn1
0x140068e8c  call    ClfsLsnLess
0x140068e91  test    al, al
0x140068e93  jz      short loc_140068ECF
0x140068e95  mov     r14, [rsp+118h+arg_50]
0x140068e9d  mov     rax, [r14]
0x140068ea0  mov     rax, [rax+38h]
0x140068ea4  mov     rcx, r14
0x140068ea7  call    _guard_dispatch_icall
0x140068eac  mov     rdx, rax; struct _FILE_OBJECT *
0x140068eaf  lea     r9, [rsp+118h+var_88]; unsigned int *
0x140068eb7  mov     r8, rbx; union _CLS_LSN *
0x140068eba  mov     rcx, rsi; this
0x140068ebd  call    ?CacheBlock@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@AEBT_CLS_LSN@@AEAK@Z; CClfsLogFcbPhysical::CacheBlock(_FILE_OBJECT *,_CLS_LSN const &,ulong &)
0x140068ec2  mov     [rsp+118h+var_94], eax
0x140068ec9  test    eax, eax
0x140068ecb  jns     short loc_140068ED7
0x140068ecd  jmp     short loc_140068E60
0x140068ecf  mov     r14, [rsp+118h+arg_50]
0x140068ed7  mov     eax, [rsi+16Ch]
0x140068edd  mov     ecx, 100h
0x140068ee2  test    ecx, eax
0x140068ee4  jnz     short loc_140068EEC
0x140068ee6  bt      eax, 9
0x140068eea  jnb     short loc_140068F52
0x140068eec  test    r14, r14
0x140068eef  jz      short loc_140068F52
0x140068ef1  mov     rax, [r14]
0x140068ef4  mov     rax, [rax]
0x140068ef7  mov     rcx, r14
0x140068efa  call    _guard_dispatch_icall
0x140068eff  mov     rax, [r14]
0x140068f02  mov     rax, [rax+68h]
0x140068f06  mov     rcx, r14
0x140068f09  call    _guard_dispatch_icall
0x140068f0e  lea     rcx, [rsi+260h]
0x140068f15  mov     rax, [rcx]
0x140068f18  mov     rax, [rax+198h]
0x140068f1f  mov     rdx, r14
0x140068f22  call    _guard_dispatch_icall
0x140068f27  mov     edi, eax
0x140068f29  mov     [rsp+118h+var_94], eax
0x140068f30  test    eax, eax
0x140068f32  jnz     short loc_140068F3E
0x140068f34  mov     edi, 103h
0x140068f39  jmp     loc_140068E2C
0x140068f3e  mov     rax, [r14]
0x140068f41  mov     rax, [rax+8]
0x140068f45  mov     rcx, r14
0x140068f48  call    _guard_dispatch_icall
0x140068f4d  jmp     loc_140068E33
0x140068f52  or      eax, ecx
0x140068f54  mov     [rsi+16Ch], eax
0x140068f5a  lea     r13, [rsi+1E8h]
0x140068f61  mov     rcx, [r13+0]
0x140068f65  mov     [rsi+208h], rcx
0x140068f6c  mov     rax, [rsi+200h]
0x140068f73  mov     [rsi+210h], rax
0x140068f7a  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x140068f81  test    rbx, rbx
0x140068f84  jz      short loc_140068F97
0x140068f86  cmp     r8, [rbx]
0x140068f89  jnz     short loc_140068F97
0x140068f8b  lea     r15, [rsi+218h]
0x140068f92  mov     [r15], rcx
0x140068f95  jmp     short loc_140068FB7
0x140068f97  mov     rdx, rbx
0x140068f9a  mov     rcx, r13
0x140068f9d  call    ??N@YAEAEBT_CLS_LSN@@0@Z; operator<=(_CLS_LSN const &,_CLS_LSN const &)
0x140068fa2  test    al, al
0x140068fa4  jz      loc_140069332
0x140068faa  lea     r15, [rsi+218h]
0x140068fb1  mov     rax, [rbx]
0x140068fb4  mov     [r15], rax
0x140068fb7  mov     rax, [rdi]
0x140068fba  mov     [rsi+220h], rax
0x140068fc1  mov     rax, [rsi]
0x140068fc4  mov     r10, [rax+78h]
0x140068fc8  mov     rax, [rsp+118h+arg_20]
0x140068fd0  mov     rcx, [rax]
0x140068fd3  mov     [rsp+118h+var_60], rcx
0x140068fdb  lea     rax, [rsp+118h+var_68]
0x140068fe3  mov     [rsp+118h+var_A8], rax
0x140068fe8  lea     rax, [rsp+118h+var_80]
0x140068ff0  mov     [rsp+118h+var_B0], rax
0x140068ff5  mov     rax, [rsp+118h+arg_70]
0x140068ffd  mov     [rsp+118h+var_B8], rax
0x140069002  mov     rax, [rsp+118h+arg_80]
0x14006900a  mov     [rsp+118h+var_C0], rax
0x14006900f  lea     rax, [rsp+118h+var_78]
0x140069017  mov     [rsp+118h+var_C8], rax
0x14006901c  lea     rax, CLFS_LSN_NULL
0x140069023  mov     [rsp+118h+var_D0], rax
0x140069028  mov     [rsp+118h+var_D8], r14
0x14006902d  mov     [rsp+118h+var_E0], 0
0x140069032  mov     rcx, [rsp+118h+arg_30]
0x14006903a  mov     [rsp+118h+var_E8], rcx
0x14006903f  mov     rcx, [rsp+118h+arg_28]
0x140069047  mov     [rsp+118h+var_F0], rcx
0x14006904c  lea     rax, [rsp+118h+var_60]
0x140069054  mov     [rsp+118h+var_F8], rax
0x140069059  mov     r9d, [rsp+118h+arg_18]
0x140069061  mov     r8, [rsp+118h+arg_10]
0x140069069  mov     rdx, [rsp+118h+arg_8]
0x140069071  mov     rcx, rsi
0x140069074  mov     rax, r10
0x140069077  call    _guard_dispatch_icall
0x14006907c  mov     edi, eax
0x14006907e  mov     [rsp+118h+var_94], eax
0x140069085  test    eax, eax
0x140069087  js      loc_1400691A4
0x14006908d  mov     dword ptr [rsp+118h+arg_10], 0
0x140069098  xor     ebx, ebx
0x14006909a  mov     [rsp+118h+var_90], ebx
0x1400690a1  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1400690a8  mov     [rsp+118h+var_58], rax
0x1400690b0  mov     rcx, r12
0x1400690b3  call    ClfsReleaseResourceLite
0x1400690b8  mov     [rsp+118h+var_98], bl
0x1400690bf  mov     rcx, r12; Resource
0x1400690c2  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400690c9  nop     dword ptr [rax+rax+00h]
0x1400690ce  test    al, al
0x1400690d0  jz      short loc_1400690E5
0x1400690d2  inc     ebx
0x1400690d4  mov     [rsp+118h+var_90], ebx
0x1400690db  mov     rcx, r12
0x1400690de  call    ClfsReleaseResourceLite
0x1400690e3  jmp     short loc_1400690BF
0x1400690e5  mov     rax, [rsi]
0x1400690e8  mov     rax, [rax+0C0h]
0x1400690ef  lea     rcx, [rsp+118h+arg_10]
0x1400690f7  mov     [rsp+118h+var_F8], rcx
0x1400690fc  xor     r9d, r9d
0x1400690ff  xor     r8d, r8d
0x140069102  lea     rdx, [rsp+118h+var_58]
0x14006910a  mov     rcx, rsi
0x14006910d  call    _guard_dispatch_icall
0x140069112  mov     edi, eax
0x140069114  mov     [rsp+118h+var_94], eax
0x14006911b  test    eax, eax
0x14006911d  jns     short loc_14006916F
0x14006911f  lea     rax, WPP_GLOBAL_Control
0x140069126  mov     rcx, cs:WPP_GLOBAL_Control
0x14006912d  cmp     rcx, rax
0x140069130  jz      short loc_140069163
0x140069132  mov     eax, [rcx+2Ch]
0x140069135  bt      eax, 1Bh
0x140069139  jnb     short loc_140069163
0x14006913b  mov     edx, 3Bh ; ';'
0x140069140  mov     dword ptr [rsp+118h+var_F0], edi
0x140069144  mov     dword ptr [rsp+118h+var_F8], 61EEh
0x14006914c  lea     r9, aCclfslogfcbphy_14; "CClfsLogFcbPhysical::WriteRestart"
0x140069153  lea     r8, WPP_dcf16e4e60dd3ad9d97db933bb98632a_Traceguids
0x14006915a  mov     rcx, [rcx+18h]
0x14006915e  call    WPP_SF_slD
0x140069163  mov     edi, 0C01A002Fh
0x140069168  mov     [rsp+118h+var_94], edi
0x14006916f  mov     eax, ebx
0x140069171  dec     ebx
0x140069173  mov     [rsp+118h+var_90], ebx
0x14006917a  mov     dl, 1; Wait
0x14006917c  mov     rcx, r12; Resource
0x14006917f  test    eax, eax
0x140069181  jz      short loc_140069191
0x140069183  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006918a  nop     dword ptr [rax+rax+00h]
0x14006918f  jmp     short loc_14006916F
0x140069191  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140069198  nop     dword ptr [rax+rax+00h]
0x14006919d  mov     [rsp+118h+var_98], al
0x1400691a4  mov     rax, [rsp+118h+arg_70]
0x1400691ac  mov     rcx, [rax]
0x1400691af  mov     rax, [rsp+118h+arg_68]
0x1400691b7  mov     [rax], rcx
0x1400691ba  test    edi, edi
0x1400691bc  jnz     loc_140069326
0x1400691c2  mov     eax, dword ptr [rsp+118h+var_70]
0x1400691c9  mov     rcx, [rsp+118h+arg_78]
0x1400691d1  mov     [rcx], eax
0x1400691d3  mov     rax, [rsi]
0x1400691d6  mov     rax, [rax+160h]
0x1400691dd  lea     rdx, [rsp+118h+arg_10]
0x1400691e5  mov     rcx, rsi
0x1400691e8  call    _guard_dispatch_icall
0x1400691ed  mov     rbx, [rax]
0x1400691f0  mov     qword ptr [rsp+118h+var_88], rbx
0x1400691f8  mov     rdx, r13
0x1400691fb  mov     rcx, r15
0x1400691fe  call    ??9@YAEAEBT_CLS_LSN@@0@Z; operator!=(_CLS_LSN const &,_CLS_LSN const &)
0x140069203  test    al, al
0x140069205  jz      short loc_14006920E
0x140069207  mov     rax, [r15]
0x14006920a  mov     [r13+0], rax
0x14006920e  lea     rcx, [rsi+220h]; plsn
0x140069215  call    ClfsLsnRecordSequence
0x14006921a  mov     edx, dword ptr [rsp+118h+var_80+4]
0x140069221  cmp     edx, 0FFFFFFFFh
0x140069224  jz      short loc_140069264
0x140069226  mov     r8d, 0FFFFFE00h
0x14006922c  test    r8d, eax
0x14006922f  jnz     short loc_140069264
0x140069231  mov     rcx, [rsp+118h+var_80]
0x140069239  and     ecx, r8d
0x14006923c  mov     [rsp+118h+var_4C], edx
0x140069243  or      eax, ecx
0x140069245  mov     [rsp+118h+var_50], eax
0x14006924c  mov     dword ptr [rsp+118h+arg_10], eax
0x140069253  mov     dword ptr [rsp+118h+arg_10+4], edx
0x14006925a  mov     rax, [rsp+118h+arg_10]
0x140069262  jmp     short loc_14006926B
0x140069264  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x14006926b  mov     [rsi+200h], rax
0x140069272  test    byte ptr [rsi+178h], 20h
0x140069279  jnz     short loc_140069286
0x14006927b  mov     rax, [r13+0]
0x14006927f  mov     [rsi+1F0h], rax
0x140069286  mov     rax, [rsi]
0x140069289  mov     rax, [rax+70h]
0x14006928d  mov     rcx, rsi
0x140069290  call    _guard_dispatch_icall
0x140069295  mov     edi, eax
0x140069297  mov     [rsp+118h+var_94], eax
  ... truncated ...
```
