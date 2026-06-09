# CClfsLogFcbPhysical::PurgeCacheSection(_CLS_LSN const &,_CLS_LSN const &,uchar)

- ea: `0x140067458`
- end: `0x140067601`
- name: `?PurgeCacheSection@CClfsLogFcbPhysical@@AEAAEAEBT_CLS_LSN@@0E@Z`
- size: `425`
- prototype: `unsigned __int8 __fastcall(CClfsLogFcbPhysical *__hidden this, CLFS_LSN *plsn, CLFS_LSN *, unsigned __int8)`
- caller_count: `12`
- callee_count: `7`
- tags: ``

## callers

- `0x1400035a8`
- `0x140005f1c`
- `0x140009420`
- `0x1400477a0`
- `0x140048318`
- `0x1400496d4`
- `0x140067060`
- `0x140067340`
- `0x140067854`
- `0x1400683b8`
- `0x140068d30`
- `0x140077820`

## callees

- `0x140005840`
- `0x140005f00`
- `0x1400075b0`
- `0x14000a420`
- `0x14000a8e0`
- `0x140066e00`
- `0x140067458`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140067518`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140067518`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400675d8`
- `ntoskrnl!CcPurgeCacheSection` at `0x1400675d8`

## pseudocode

```c
BOOLEAN __fastcall CClfsLogFcbPhysical::PurgeCacheSection(
        CClfsLogFcbPhysical *this,
        CLFS_LSN *plsn,
        CLFS_LSN *a3,
        BOOLEAN a4)
{
  ULONGLONG ullOffset; // rbx
  ULONGLONG v8; // rdi
  BOOLEAN v10; // r15
  ULONG v11; // eax
  CLFS_LSN v12; // rax
  ULONG v13; // eax
  CLFS_LSN v14; // rax
  LARGE_INTEGER *p_FileOffset; // rdx
  _DWORD *v16; // r14
  CLFS_CONTAINER_ID v17; // eax
  char v18; // al
  signed __int64 v19; // rax
  unsigned int v20; // eax
  char v21; // al
  LARGE_INTEGER FileOffset; // [rsp+20h] [rbp-48h] BYREF
  union _CLS_LSN v23; // [rsp+78h] [rbp+10h] BYREF
  ULONGLONG v24; // [rsp+80h] [rbp+18h]
  BOOLEAN v25; // [rsp+88h] [rbp+20h]

  v25 = a4;
  FileOffset.QuadPart = 0;
  ullOffset = plsn->ullOffset;
  v23 = *plsn;
  v8 = a3->ullOffset;
  v24 = a3->ullOffset;
  if ( ClfsLsnGreater(plsn, a3) )
    return 1;
  v10 = 0;
  if ( ClfsLsnRecordSequence(plsn) )
  {
    v11 = ClfsLsnBlockOffset(plsn);
    v12 = ClfsLsnCreate(plsn->offset.cidContainer, v11, 0);
    LODWORD(ullOffset) = v12.offset.idxRecord;
    v23 = v12;
  }
  if ( ClfsLsnRecordSequence(a3) )
  {
    v13 = ClfsLsnBlockOffset(a3);
    v14 = ClfsLsnCreate(a3->offset.cidContainer, v13, 0);
    LODWORD(v8) = v14.offset.idxRecord;
    v24 = v14.ullOffset;
  }
  v25 = ExAcquireResourceExclusiveLite((PERESOURCE)((char *)this + 200), 1u);
  if ( CLFS_LSN_NULL.ullOffset == plsn->ullOffset && CLFS_LSN_NULL.ullOffset == a3->ullOffset )
  {
    p_FileOffset = 0;
LABEL_28:
    v10 = CcPurgeCacheSection((PSECTION_OBJECT_POINTERS)this + 27, p_FileOffset, 0, 0);
    goto LABEL_29;
  }
  v16 = (_DWORD *)((char *)this + 1368);
  if ( this == (CClfsLogFcbPhysical *)-1368LL )
  {
    v18 = 0;
  }
  else
  {
    v17 = *((_DWORD *)this + 343);
    if ( v23.offset.cidContainer < v17 || v23.offset.cidContainer == v17 && (unsigned int)ullOffset <= *v16 )
    {
LABEL_19:
      if ( this == (CClfsLogFcbPhysical *)-1368LL )
      {
        v21 = 0;
      }
      else
      {
        v20 = *((_DWORD *)this + 343);
        if ( HIDWORD(v24) > v20 || HIDWORD(v24) == v20 && (unsigned int)v8 >= *v16 )
          goto LABEL_27;
        v21 = 1;
      }
      if ( v21 )
      {
        v10 = 1;
        goto LABEL_29;
      }
LABEL_27:
      v23.ullOffset = 0;
      p_FileOffset = &FileOffset;
      goto LABEL_28;
    }
    v18 = 1;
  }
  if ( !v18 )
    goto LABEL_19;
  v19 = CClfsLogFcbPhysical::LsnToCacheOffset(this, &v23);
  if ( v19 >= 0 )
  {
    FileOffset.QuadPart = (v19 / 4096) << 12;
    goto LABEL_19;
  }
LABEL_29:
  if ( v25 )
    ClfsReleaseResourceLite((char *)this + 200);
  return v10;
}

```

## disassembly

```asm
0x140067458  mov     rax, rsp
0x14006745b  mov     [rax+20h], r9b
0x14006745f  mov     [rax+8], rcx
0x140067463  push    rbx
0x140067464  push    rsi
0x140067465  push    rdi
0x140067466  push    r12
0x140067468  push    r13
0x14006746a  push    r14
0x14006746c  push    r15
0x14006746e  sub     rsp, 30h
0x140067472  mov     r14, r8
0x140067475  mov     rsi, rdx
0x140067478  mov     r13, rcx
0x14006747b  mov     qword ptr [rax-48h], 0
0x140067483  mov     rbx, [rdx]
0x140067486  mov     [rax+10h], rbx
0x14006748a  mov     rdi, [r8]
0x14006748d  mov     [rax+18h], rdi
0x140067491  mov     rdx, r8; plsn2
0x140067494  mov     rcx, rsi; plsn1
0x140067497  call    ClfsLsnGreater
0x14006749c  test    al, al
0x14006749e  jz      short loc_1400674B3
0x1400674a0  mov     al, 1
0x1400674a2  add     rsp, 30h
0x1400674a6  pop     r15
0x1400674a8  pop     r14
0x1400674aa  pop     r13
0x1400674ac  pop     r12
0x1400674ae  pop     rdi
0x1400674af  pop     rsi
0x1400674b0  pop     rbx
0x1400674b1  retn
0x1400674b3  xor     r15b, r15b
0x1400674b6  mov     rcx, rsi; plsn
0x1400674b9  call    ClfsLsnRecordSequence
0x1400674be  test    eax, eax
0x1400674c0  jz      short loc_1400674DF
0x1400674c2  mov     rcx, rsi; plsn
0x1400674c5  call    ClfsLsnBlockOffset
0x1400674ca  xor     r8d, r8d; cRecord
0x1400674cd  mov     edx, eax; offBlock
0x1400674cf  mov     ecx, [rsi+4]; cidContainer
0x1400674d2  call    ClfsLsnCreate
0x1400674d7  mov     rbx, rax
0x1400674da  mov     qword ptr [rsp+68h+arg_8], rax
0x1400674df  mov     rcx, r14; plsn
0x1400674e2  call    ClfsLsnRecordSequence
0x1400674e7  test    eax, eax
0x1400674e9  jz      short loc_14006750C
0x1400674eb  mov     rcx, r14; plsn
0x1400674ee  call    ClfsLsnBlockOffset
0x1400674f3  xor     r8d, r8d; cRecord
0x1400674f6  mov     edx, eax; offBlock
0x1400674f8  mov     ecx, [r14+4]; cidContainer
0x1400674fc  call    ClfsLsnCreate
0x140067501  mov     rdi, rax
0x140067504  mov     [rsp+68h+arg_10], rax
0x14006750c  lea     r12, [r13+0C8h]
0x140067513  mov     dl, 1; Wait
0x140067515  mov     rcx, r12; Resource
0x140067518  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14006751f  nop     dword ptr [rax+rax+00h]
0x140067524  mov     [rsp+68h+arg_18], al
0x14006752b  mov     rcx, qword ptr cs:CLFS_LSN_NULL
0x140067532  cmp     rcx, [rsi]
0x140067535  jnz     short loc_140067543
0x140067537  cmp     rcx, [r14]
0x14006753a  jnz     short loc_140067543
0x14006753c  xor     edx, edx
0x14006753e  jmp     loc_1400675CB
0x140067543  lea     r14, [r13+558h]
0x14006754a  test    r14, r14
0x14006754d  jz      short loc_140067564
0x14006754f  mov     eax, [r14+4]
0x140067553  cmp     dword ptr [rsp+68h+arg_8+4], eax
0x140067557  jb      short loc_140067595
0x140067559  jnz     short loc_140067560
0x14006755b  cmp     ebx, [r14]
0x14006755e  jbe     short loc_140067595
0x140067560  mov     al, 1
0x140067562  jmp     short loc_140067566
0x140067564  xor     al, al
0x140067566  test    al, al
0x140067568  jz      short loc_140067595
0x14006756a  lea     rdx, [rsp+68h+arg_8]; union _CLS_LSN *
0x14006756f  mov     rcx, r13; this
0x140067572  call    ?LsnToCacheOffset@CClfsLogFcbPhysical@@AEAA_KAEBT_CLS_LSN@@@Z; CClfsLogFcbPhysical::LsnToCacheOffset(_CLS_LSN const &)
0x140067577  mov     rcx, rax
0x14006757a  shr     rcx, 20h
0x14006757e  test    ecx, ecx
0x140067580  js      short loc_1400675E7
0x140067582  cqo
0x140067584  mov     ecx, 1000h
0x140067589  idiv    rcx
0x14006758c  shl     rax, 0Ch
0x140067590  mov     qword ptr [rsp+68h+FileOffset], rax
0x140067595  test    r14, r14
0x140067598  jz      short loc_1400675B2
0x14006759a  mov     eax, [r14+4]
0x14006759e  cmp     dword ptr [rsp+68h+arg_10+4], eax
0x1400675a5  ja      short loc_1400675BD
0x1400675a7  jnz     short loc_1400675AE
0x1400675a9  cmp     edi, [r14]
0x1400675ac  jnb     short loc_1400675BD
0x1400675ae  mov     al, 1
0x1400675b0  jmp     short loc_1400675B4
0x1400675b2  xor     al, al
0x1400675b4  test    al, al
0x1400675b6  jz      short loc_1400675BD
0x1400675b8  mov     r15b, 1
0x1400675bb  jmp     short loc_1400675E7
0x1400675bd  mov     qword ptr [rsp+68h+arg_8], 0
0x1400675c6  lea     rdx, [rsp+68h+FileOffset]; FileOffset
0x1400675cb  xor     r9d, r9d; Flags
0x1400675ce  xor     r8d, r8d; Length
0x1400675d1  lea     rcx, [r13+288h]; SectionObjectPointer
0x1400675d8  call    cs:__imp_CcPurgeCacheSection
0x1400675df  nop     dword ptr [rax+rax+00h]
0x1400675e4  mov     r15b, al
0x1400675e7  cmp     [rsp+68h+arg_18], 0
0x1400675ef  jz      short loc_1400675F9
0x1400675f1  mov     rcx, r12
0x1400675f4  call    ClfsReleaseResourceLite
0x1400675f9  mov     al, r15b
0x1400675fc  jmp     loc_1400674A2
0x14007ae77  push    rbp
0x14007ae79  sub     rsp, 20h
0x14007ae7d  mov     rbp, rdx
0x14007ae80  cmp     byte ptr [rbp+88h], 0
0x14007ae87  jz      short loc_14007AE9A
0x14007ae89  mov     rcx, [rbp+70h]
0x14007ae8d  add     rcx, 0C8h
0x14007ae94  call    ClfsReleaseResourceLite
0x14007ae99  nop
0x14007ae9a  add     rsp, 20h
0x14007ae9e  pop     rbp
0x14007ae9f  retn
```
