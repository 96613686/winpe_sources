# CClfsLogFcbPhysical::AddArchiveRef(_FILE_OBJECT *,_UNICODE_STRING &,_CLS_LSN const &,_CLS_LSN const &,ulong &,ulong &,_CLFS_ARCHIVE_SNAPSHOT &)

- ea: `0x140043a80`
- end: `0x140043f4f`
- name: `?AddArchiveRef@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@AEAU_UNICODE_STRING@@AEBT_CLS_LSN@@2AEAK3AEAU_CLFS_ARCHIVE_SNAPSHOT@@@Z`
- size: `1231`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct _FILE_OBJECT *@<rdx>, struct _UNICODE_STRING *@<r8>, const union _CLS_LSN *@<r9>, CLFS_LSN *plsn2, unsigned int *, unsigned int *, struct _CLFS_ARCHIVE_SNAPSHOT *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400152a0`

## callees

- `0x140005840`
- `0x1400075b0`
- `0x140008330`
- `0x140008c40`
- `0x14000a420`
- `0x14000c018`
- `0x140017f20`
- `0x140037d88`
- `0x140043a80`
- `0x1400664b0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140043b68`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140043b68`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140043bb0`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140043bb0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140043c1a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140043c1a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043b8a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043b8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043de9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043f1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f564`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043de9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043f1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007f564`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043d3f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140043d3f`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::AddArchiveRef(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        struct _UNICODE_STRING *a3,
        const union _CLS_LSN *a4,
        CLFS_LSN *plsn2,
        unsigned int *a6,
        unsigned int *a7,
        struct _CLFS_ARCHIVE_SNAPSHOT *a8)
{
  int Snapshot; // edi
  char v14; // r15
  ULONGLONG v15; // rax
  ULONGLONG *v16; // rdx
  char v17; // cl
  char v18; // al
  struct _FILE_OBJECT *v19; // rbx
  ULONGLONG ullOffset; // rbx
  unsigned int v21; // edi
  unsigned int v22; // eax
  unsigned int v23; // [rsp+88h] [rbp-90h] BYREF
  int v24; // [rsp+8Ch] [rbp-8Ch] BYREF
  UNICODE_STRING String2; // [rsp+90h] [rbp-88h] BYREF
  int v26; // [rsp+A0h] [rbp-78h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-70h] BYREF
  PVOID P[3]; // [rsp+B8h] [rbp-60h] BYREF
  CLFS_LSN v29; // [rsp+D0h] [rbp-48h] BYREF
  ULONGLONG v30; // [rsp+D8h] [rbp-40h]
  ULONGLONG v31; // [rsp+E0h] [rbp-38h]
  BOOLEAN v33; // [rsp+148h] [rbp+30h]

  memset(P, 0, sizeof(P));
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  v29 = CLFS_LSN_INVALID;
  v23 = 0;
  v26 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( (*((_BYTE *)this + 376) & 0x20) == 0 )
    return 3222929442LL;
  if ( ClfsLsnGreater(a4, plsn2)
    || a4 && CLFS_LSN_INVALID.ullOffset == a4->ullOffset
    || plsn2 && CLFS_LSN_INVALID.ullOffset == plsn2->ullOffset )
  {
    return 3221225485LL;
  }
  *((_QWORD *)a8 + 2) = 0;
  v33 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
  RtlInitUnicodeString(&DestinationString, L"\\??\\");
  String2 = *(UNICODE_STRING *)((char *)this + 40);
  if ( RtlPrefixUnicodeString(&DestinationString, &String2, 0) )
  {
    String2.Buffer += (unsigned __int64)DestinationString.Length >> 1;
    String2.Length -= DestinationString.Length;
    String2.MaximumLength -= DestinationString.Length;
    *a6 = String2.Length >> 1;
  }
  if ( String2.Length <= a3->MaximumLength )
  {
    RtlCopyUnicodeString(a3, &String2);
    v15 = *((_QWORD *)this + 61);
    v30 = v15;
    v16 = (ULONGLONG *)((char *)this + 496);
    if ( this == (CClfsLogFcbPhysical *)-496LL )
    {
      v17 = 0;
    }
    else
    {
      if ( v15 <= *((_QWORD *)this + 62) )
        goto LABEL_19;
      v17 = 1;
    }
    if ( v17 )
    {
      v15 = *v16;
      v30 = *v16;
    }
LABEL_19:
    if ( a4 )
    {
      if ( a4->ullOffset >= v15 )
      {
LABEL_24:
        if ( !ClfsLsnGreater(plsn2, (const CLFS_LSN *)this + 60) )
        {
          if ( (unsigned __int8)operator!=(a4, (char *)this + 488) )
          {
            v19 = a2;
            Snapshot = CClfsLogFcbPhysical::CacheBlock(this, a2, a4, &v23);
            if ( Snapshot < 0 )
            {
              v14 = 0;
              goto LABEL_42;
            }
          }
          ullOffset = plsn2->ullOffset;
          v31 = plsn2->ullOffset;
          if ( ClfsLsnLess(plsn2, (const CLFS_LSN *)this + 60) )
          {
            Snapshot = CClfsLogFcbPhysical::CacheBlock(this, a2, plsn2, &v23);
            if ( Snapshot < 0 )
              goto LABEL_12;
            v21 = v23;
            P[0] = ExAllocatePoolWithTag(PagedPool, (unsigned __int64)v23 << 9, 0x73666C43u);
            if ( !_CLFS_READ_BUFFER::GetAddress((_CLFS_READ_BUFFER *)P) )
            {
              Snapshot = -1073741670;
              goto LABEL_12;
            }
            Snapshot = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, CLFS_LSN *, __int64, PVOID *, unsigned int, _QWORD, int, CLFS_LSN *, int *))(*(_QWORD *)this + 128LL))(
                         this,
                         a2,
                         plsn2,
                         1,
                         P,
                         v21 << 9,
                         0,
                         16,
                         &v29,
                         &v26);
            if ( Snapshot < 0 )
              goto LABEL_12;
            ExFreePoolWithTag(P[0], 0);
            P[0] = 0;
            if ( ClfsLsnRecordSequence(plsn2) )
              ullOffset = v29.ullOffset;
            v31 = ullOffset;
          }
          v22 = _InterlockedIncrement((volatile signed __int32 *)this + 331);
          *a7 = v22;
          v14 = 1;
          if ( v22 == 1 )
            *((CLFS_LSN *)this + 69) = CLFS_LSN_INVALID;
          (*(void (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 112LL))(this);
          Snapshot = CClfsBaseFile::CreateSnapshot(
                       *((CClfsBaseFile **)this + 89),
                       (struct CClfsBaseFileSnapshot **)a8 + 2);
          if ( Snapshot >= 0 )
          {
            *((_QWORD *)a8 + 3) = *((_QWORD *)this + 60);
            *(union _CLS_LSN *)a8 = *a4;
            *((_QWORD *)a8 + 1) = ullOffset;
            *((_DWORD *)a8 + 8) = *((_DWORD *)this + 355);
            *((_DWORD *)a8 + 9) = *((_DWORD *)this + 354);
          }
          goto LABEL_41;
        }
LABEL_39:
        Snapshot = -1072037883;
        goto LABEL_12;
      }
      v18 = 1;
    }
    else
    {
      v18 = 0;
    }
    if ( v18 )
      goto LABEL_39;
    goto LABEL_24;
  }
  Snapshot = -2147483643;
LABEL_12:
  v14 = 0;
LABEL_41:
  v19 = a2;
LABEL_42:
  if ( Snapshot < 0 && v14 )
  {
    v24 = 0;
    (*(void (__fastcall **)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, __int64, int *, struct _CLFS_ARCHIVE_SNAPSHOT *))(*(_QWORD *)this + 88LL))(
      this,
      v19,
      1,
      &v24,
      a8);
  }
  if ( v33 )
    ClfsReleaseResourceLite((struct _ERESOURCE *)((char *)this + 200));
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0);
  return (unsigned int)Snapshot;
}

```

## disassembly

```asm
0x140043a80  mov     r11, rsp
0x140043a83  mov     [r11+18h], rbx
0x140043a87  mov     [r11+20h], rsi
0x140043a8b  mov     [r11+10h], rdx
0x140043a8f  mov     [r11+8], rcx
0x140043a93  push    rdi
0x140043a94  push    r12
0x140043a96  push    r13
0x140043a98  push    r14
0x140043a9a  push    r15
0x140043a9c  sub     rsp, 0D0h
0x140043aa3  mov     r14, r9
0x140043aa6  mov     rbx, r8
0x140043aa9  mov     rsi, rcx
0x140043aac  xorps   xmm0, xmm0
0x140043aaf  movdqu  xmmword ptr [r11-60h], xmm0
0x140043ab5  xor     r13d, r13d
0x140043ab8  mov     [r11-50h], r13
0x140043abc  mov     [r11-70h], r13
0x140043ac0  mov     [r11-68h], r13
0x140043ac4  mov     qword ptr [rsp+0F8h+String2.Length], r13
0x140043ac9  mov     [r11-80h], r13
0x140043acd  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140043ad4  mov     [r11-48h], rax
0x140043ad8  mov     [rsp+0F8h+var_90], r13d
0x140043add  mov     [r11-78h], r13d
0x140043ae1  mov     rdi, [rsp+0F8h+arg_28]
0x140043ae9  mov     [rdi], r13d
0x140043aec  mov     rax, [rsp+0F8h+arg_30]
0x140043af4  mov     [rax], r13d
0x140043af7  test    byte ptr [rcx+178h], 20h
0x140043afe  jnz     short loc_140043B0A
0x140043b00  mov     eax, 0C01A0022h
0x140043b05  jmp     loc_140043F31
0x140043b0a  mov     r15, [rsp+0F8h+plsn2]
0x140043b12  mov     rdx, r15; plsn2
0x140043b15  mov     rcx, r14; plsn1
0x140043b18  call    ClfsLsnGreater
0x140043b1d  test    al, al
0x140043b1f  jnz     loc_140043F2C
0x140043b25  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140043b2c  test    r14, r14
0x140043b2f  jz      short loc_140043B3A
0x140043b31  cmp     rax, [r14]
0x140043b34  jz      loc_140043F2C
0x140043b3a  test    r15, r15
0x140043b3d  jz      short loc_140043B48
0x140043b3f  cmp     rax, [r15]
0x140043b42  jz      loc_140043F2C
0x140043b48  mov     [rsp+0F8h+var_94], r13d
0x140043b4d  mov     [rsp+0F8h+var_98], r13b
0x140043b52  mov     r12, [rsp+0F8h+arg_38]
0x140043b5a  mov     [r12+10h], r13
0x140043b5f  lea     rcx, [rsi+0C8h]; Resource
0x140043b66  mov     dl, 1; Wait
0x140043b68  call    cs:__imp_ExAcquireResourceSharedLite
0x140043b6f  nop     dword ptr [rax+rax+00h]
0x140043b74  mov     byte ptr [rsp+0F8h+arg_28], al
0x140043b7b  lea     rdx, asc_14001C860; "\\??\\"
0x140043b82  lea     rcx, [rsp+0F8h+DestinationString]; DestinationString
0x140043b8a  call    cs:__imp_RtlInitUnicodeString
0x140043b91  nop     dword ptr [rax+rax+00h]
0x140043b96  movups  xmm0, xmmword ptr [rsi+28h]
0x140043b9a  movdqu  xmmword ptr [rsp+0F8h+String2.Length], xmm0
0x140043ba0  xor     r8d, r8d; CaseInSensitive
0x140043ba3  lea     rdx, [rsp+0F8h+String2]; String2
0x140043ba8  lea     rcx, [rsp+0F8h+DestinationString]; String1
0x140043bb0  call    cs:__imp_RtlPrefixUnicodeString
0x140043bb7  nop     dword ptr [rax+rax+00h]
0x140043bbc  test    al, al
0x140043bbe  jz      short loc_140043BF4
0x140043bc0  movzx   edx, [rsp+0F8h+DestinationString.Length]
0x140043bc8  mov     ecx, edx
0x140043bca  shr     rcx, 1
0x140043bcd  mov     rax, [rsp+0F8h+String2.Buffer]
0x140043bd2  lea     rcx, [rax+rcx*2]
0x140043bd6  mov     [rsp+0F8h+String2.Buffer], rcx
0x140043bdb  movzx   eax, [rsp+0F8h+String2.Length]
0x140043be0  sub     ax, dx
0x140043be3  mov     [rsp+0F8h+String2.Length], ax
0x140043be8  movzx   ecx, ax
0x140043beb  sub     [rsp+0F8h+String2.MaximumLength], dx
0x140043bf0  shr     ecx, 1
0x140043bf2  mov     [rdi], ecx
0x140043bf4  movzx   eax, word ptr [rbx+2]
0x140043bf8  cmp     [rsp+0F8h+String2.Length], ax
0x140043bfd  jbe     short loc_140043C12
0x140043bff  mov     edi, 80000005h
0x140043c04  mov     [rsp+0F8h+var_94], edi
0x140043c08  mov     r15b, [rsp+0F8h+var_98]
0x140043c0d  jmp     loc_140043EBC
0x140043c12  lea     rdx, [rsp+0F8h+String2]; SourceString
0x140043c17  mov     rcx, rbx; DestinationString
0x140043c1a  call    cs:__imp_RtlCopyUnicodeString
0x140043c21  nop     dword ptr [rax+rax+00h]
0x140043c26  lea     rbx, [rsi+1E8h]
0x140043c2d  mov     rax, [rbx]
0x140043c30  mov     [rsp+0F8h+var_40], rax
0x140043c38  lea     rdx, [rsi+1F0h]
0x140043c3f  test    rdx, rdx
0x140043c42  jz      short loc_140043C5A
0x140043c44  mov     rcx, rax
0x140043c47  shr     rcx, 20h
0x140043c4b  cmp     ecx, [rdx+4]
0x140043c4e  jb      short loc_140043C6C
0x140043c50  jnz     short loc_140043C56
0x140043c52  cmp     eax, [rdx]
0x140043c54  jbe     short loc_140043C6C
0x140043c56  mov     cl, 1
0x140043c58  jmp     short loc_140043C5D
0x140043c5a  mov     cl, r13b
0x140043c5d  test    cl, cl
0x140043c5f  jz      short loc_140043C6C
0x140043c61  mov     rax, [rdx]
0x140043c64  mov     [rsp+0F8h+var_40], rax
0x140043c6c  mov     rcx, rax
0x140043c6f  test    r14, r14
0x140043c72  jz      short loc_140043C89
0x140043c74  shr     rcx, 20h
0x140043c78  cmp     [r14+4], ecx
0x140043c7c  ja      short loc_140043C94
0x140043c7e  jnz     short loc_140043C85
0x140043c80  cmp     [r14], eax
0x140043c83  jnb     short loc_140043C94
0x140043c85  mov     al, 1
0x140043c87  jmp     short loc_140043C8C
0x140043c89  mov     al, r13b
0x140043c8c  test    al, al
0x140043c8e  jnz     loc_140043EAB
0x140043c94  lea     r13, [rsi+1E0h]
0x140043c9b  mov     rdx, r13; plsn2
0x140043c9e  mov     rcx, r15; plsn1
0x140043ca1  call    ClfsLsnGreater
0x140043ca6  test    al, al
0x140043ca8  jnz     loc_140043EAB
0x140043cae  mov     rdx, rbx
0x140043cb1  mov     rcx, r14
0x140043cb4  call    ??9@YAEAEBT_CLS_LSN@@0@Z; operator!=(_CLS_LSN const &,_CLS_LSN const &)
0x140043cb9  test    al, al
0x140043cbb  jz      short loc_140043CE6
0x140043cbd  lea     r9, [rsp+0F8h+var_90]; unsigned int *
0x140043cc2  mov     r8, r14; union _CLS_LSN *
0x140043cc5  mov     rbx, [rsp+0F8h+arg_8]
0x140043ccd  mov     rdx, rbx; struct _FILE_OBJECT *
0x140043cd0  mov     rcx, rsi; this
0x140043cd3  call    ?CacheBlock@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@AEBT_CLS_LSN@@AEAK@Z; CClfsLogFcbPhysical::CacheBlock(_FILE_OBJECT *,_CLS_LSN const &,ulong &)
0x140043cd8  mov     edi, eax
0x140043cda  mov     [rsp+0F8h+var_94], eax
0x140043cde  test    eax, eax
0x140043ce0  js      loc_140043EB5
0x140043ce6  mov     rbx, [r15]
0x140043ce9  mov     [rsp+0F8h+var_38], rbx
0x140043cf1  mov     rdx, r13; plsn2
0x140043cf4  mov     rcx, r15; plsn1
0x140043cf7  call    ClfsLsnLess
0x140043cfc  test    al, al
0x140043cfe  jz      loc_140043E1C
0x140043d04  lea     r9, [rsp+0F8h+var_90]; unsigned int *
0x140043d09  mov     r8, r15; union _CLS_LSN *
0x140043d0c  mov     rdx, [rsp+0F8h+arg_8]; struct _FILE_OBJECT *
0x140043d14  mov     rcx, rsi; this
0x140043d17  call    ?CacheBlock@CClfsLogFcbPhysical@@AEAAJPEAU_FILE_OBJECT@@AEBT_CLS_LSN@@AEAK@Z; CClfsLogFcbPhysical::CacheBlock(_FILE_OBJECT *,_CLS_LSN const &,ulong &)
0x140043d1c  mov     edi, eax
0x140043d1e  mov     [rsp+0F8h+var_94], eax
0x140043d22  test    eax, eax
0x140043d24  js      loc_140043C08
0x140043d2a  mov     edi, [rsp+0F8h+var_90]
0x140043d2e  mov     edx, edi
0x140043d30  shl     rdx, 9; NumberOfBytes
0x140043d34  mov     ecx, 1; PoolType
0x140043d39  mov     r8d, 73666C43h; Tag
0x140043d3f  call    cs:__imp_ExAllocatePoolWithTag
0x140043d46  nop     dword ptr [rax+rax+00h]
0x140043d4b  mov     [rsp+0F8h+P], rax
0x140043d53  lea     rcx, [rsp+0F8h+P]; this
0x140043d5b  call    ?GetAddress@_CLFS_READ_BUFFER@@QEBAPEAEXZ; _CLFS_READ_BUFFER::GetAddress(void)
0x140043d60  test    rax, rax
0x140043d63  jnz     short loc_140043D6F
0x140043d65  mov     edi, 0C000009Ah
0x140043d6a  jmp     loc_140043C04
0x140043d6f  mov     rax, [rsi]
0x140043d72  shl     edi, 9
0x140043d75  mov     rax, [rax+80h]
0x140043d7c  lea     rcx, [rsp+0F8h+var_78]
0x140043d84  mov     [rsp+0F8h+var_B0], rcx
0x140043d89  lea     rcx, [rsp+0F8h+var_48]
0x140043d91  mov     [rsp+0F8h+var_B8], rcx
0x140043d96  mov     [rsp+0F8h+var_C0], 10h
0x140043d9e  mov     [rsp+0F8h+var_C8], 0
0x140043da7  mov     [rsp+0F8h+var_D0], edi
0x140043dab  lea     rcx, [rsp+0F8h+P]
0x140043db3  mov     [rsp+0F8h+var_D8], rcx
0x140043db8  mov     r9d, 1
0x140043dbe  mov     r8, r15
0x140043dc1  mov     rdx, [rsp+0F8h+arg_8]
0x140043dc9  mov     rcx, rsi
0x140043dcc  call    _guard_dispatch_icall
0x140043dd1  mov     edi, eax
0x140043dd3  mov     [rsp+0F8h+var_94], eax
0x140043dd7  test    eax, eax
0x140043dd9  js      loc_140043C08
0x140043ddf  xor     edx, edx; Tag
0x140043de1  mov     rcx, [rsp+0F8h+P]; P
0x140043de9  call    cs:__imp_ExFreePoolWithTag
0x140043df0  nop     dword ptr [rax+rax+00h]
0x140043df5  mov     [rsp+0F8h+P], 0
0x140043e01  mov     rcx, r15; plsn
0x140043e04  call    ClfsLsnRecordSequence
0x140043e09  test    eax, eax
0x140043e0b  cmovnz  rbx, [rsp+0F8h+var_48]
0x140043e14  mov     [rsp+0F8h+var_38], rbx
0x140043e1c  mov     eax, 1
0x140043e21  lock xadd [rsi+52Ch], eax
0x140043e29  inc     eax
0x140043e2b  mov     rcx, [rsp+0F8h+arg_30]
0x140043e33  mov     [rcx], eax
0x140043e35  mov     r15b, 1
0x140043e38  mov     [rsp+0F8h+var_98], r15b
0x140043e3d  cmp     eax, 1
0x140043e40  jnz     short loc_140043E50
0x140043e42  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140043e49  mov     [rsi+228h], rax
0x140043e50  mov     rax, [rsi]
0x140043e53  mov     rax, [rax+70h]
0x140043e57  mov     rcx, rsi
0x140043e5a  call    _guard_dispatch_icall
0x140043e5f  mov     [rsp+0F8h+var_94], eax
0x140043e63  lea     rdx, [r12+10h]; struct CClfsBaseFileSnapshot **
0x140043e68  mov     rcx, [rsi+2C8h]; this
0x140043e6f  call    ?CreateSnapshot@CClfsBaseFile@@QEAAJPEAPEAVCClfsBaseFileSnapshot@@@Z; CClfsBaseFile::CreateSnapshot(CClfsBaseFileSnapshot * *)
0x140043e74  mov     edi, eax
0x140043e76  mov     [rsp+0F8h+var_94], eax
0x140043e7a  test    eax, eax
0x140043e7c  js      short loc_140043EBC
0x140043e7e  mov     rax, [r13+0]
0x140043e82  mov     [r12+18h], rax
0x140043e87  mov     rax, [r14]
0x140043e8a  mov     [r12], rax
0x140043e8e  mov     [r12+8], rbx
0x140043e93  mov     eax, [rsi+58Ch]
0x140043e99  mov     [r12+20h], eax
0x140043e9e  mov     eax, [rsi+588h]
0x140043ea4  mov     [r12+24h], eax
0x140043ea9  jmp     short loc_140043EBC
0x140043eab  mov     edi, 0C01A0005h
0x140043eb0  jmp     loc_140043C04
0x140043eb5  mov     r15b, [rsp+0F8h+var_98]
0x140043eba  jmp     short loc_140043EC4
0x140043ebc  mov     rbx, [rsp+0F8h+arg_8]
0x140043ec4  test    edi, edi
0x140043ec6  jns     short loc_140043EF7
0x140043ec8  test    r15b, r15b
0x140043ecb  jz      short loc_140043EF7
0x140043ecd  mov     [rsp+0F8h+var_8C], 0
0x140043ed5  mov     rax, [rsi]
0x140043ed8  mov     rax, [rax+58h]
0x140043edc  mov     [rsp+0F8h+var_D8], r12
0x140043ee1  lea     r9, [rsp+0F8h+var_8C]
0x140043ee6  mov     r8d, 1
0x140043eec  mov     rdx, rbx
0x140043eef  mov     rcx, rsi
0x140043ef2  call    _guard_dispatch_icall
0x140043ef7  cmp     byte ptr [rsp+0F8h+arg_28], 0
0x140043eff  jz      short loc_140043F0D
0x140043f01  lea     rcx, [rsi+0C8h]
0x140043f08  call    ClfsReleaseResourceLite
0x140043f0d  mov     rcx, [rsp+0F8h+P]; P
0x140043f15  test    rcx, rcx
0x140043f18  jz      short loc_140043F28
0x140043f1a  xor     edx, edx; Tag
0x140043f1c  call    cs:__imp_ExFreePoolWithTag
0x140043f23  nop     dword ptr [rax+rax+00h]
0x140043f28  mov     eax, edi
0x140043f2a  jmp     short loc_140043F31
0x140043f2c  mov     eax, 0C000000Dh
0x140043f31  lea     r11, [rsp+0F8h+var_28]
0x140043f39  mov     rbx, [r11+40h]
0x140043f3d  mov     rsi, [r11+48h]
0x140043f41  mov     rsp, r11
0x140043f44  pop     r15
0x140043f46  pop     r14
0x140043f48  pop     r13
0x140043f4a  pop     r12
0x140043f4c  pop     rdi
0x140043f4d  retn
0x14007f4ec  push    rbp
0x14007f4ee  sub     rsp, 60h
0x14007f4f2  mov     rbp, rdx
0x14007f4f5  cmp     dword ptr [rbp+64h], 0
0x14007f4f9  jge     short loc_14007F539
0x14007f4fb  cmp     byte ptr [rbp+60h], 0
0x14007f4ff  jz      short loc_14007F539
0x14007f501  mov     dword ptr [rbp+6Ch], 0
0x14007f508  mov     rcx, [rbp+100h]
0x14007f50f  mov     rax, [rcx]
0x14007f512  mov     rax, [rax+58h]
0x14007f516  mov     rdx, [rbp+138h]
0x14007f51d  mov     [rsp+68h+var_48], rdx
0x14007f522  lea     r9, [rbp+6Ch]
0x14007f526  mov     r8d, 1
  ... truncated ...
```
