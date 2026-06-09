# PpfhEventLog::CreateFromPpfEventLog(uchar *,uint)

- ea: `0x18002c7b0`
- end: `0x18002cb2f`
- name: `?CreateFromPpfEventLog@PpfhEventLog@@QEAAXPEAEI@Z`
- size: `895`
- prototype: `void __fastcall(PpfhEventLog *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18004b710`

## callees

- `0x18000f0c8`
- `0x18001af7c`
- `0x180028c28`
- `0x180028d5c`
- `0x180028f7c`
- `0x18002904c`
- `0x18002aa70`
- `0x18002aef4`
- `0x18002b204`
- `0x18002b36c`
- `0x18002b684`
- `0x18002b8f4`
- `0x18002c7b0`
- `0x18002d85c`
- `0x180034fd8`
- `0x180034ff8`
- `0x1800570b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ca1e`

## string_xrefs

- `0x18002cb1a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall PpfhEventLog::CreateFromPpfEventLog(PpfhEventLog *this, unsigned __int8 *a2, unsigned int a3)
{
  unsigned int v4; // edi
  int v5; // eax
  unsigned int v6; // r8d
  int Current; // eax
  unsigned int v8; // r8d
  unsigned __int16 i; // bx
  int v10; // eax
  unsigned int v11; // r8d
  int v12; // eax
  unsigned int v13; // r8d
  int v14; // eax
  const char *v15; // r9
  unsigned int v16; // ebx
  const char *v17; // r9
  int v18; // edi
  void *v19; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v21; // r9
  PpfhEventLogDigest *v22; // rdx
  PpfhEventLogDigest *v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  int Next; // eax
  unsigned int v27; // r8d
  int v28; // [rsp+20h] [rbp-A9h]
  int v29; // [rsp+20h] [rbp-A9h]
  int v30; // [rsp+20h] [rbp-A9h]
  int v31; // [rsp+20h] [rbp-A9h]
  bool v32[8]; // [rsp+50h] [rbp-79h] BYREF
  size_t Size; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v34; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v35; // [rsp+64h] [rbp-65h] BYREF
  unsigned int v36; // [rsp+68h] [rbp-61h] BYREF
  unsigned __int8 *v37; // [rsp+70h] [rbp-59h] BYREF
  void *lpMem; // [rsp+78h] [rbp-51h] BYREF
  _DWORD v39[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v40; // [rsp+88h] [rbp-41h] BYREF
  PpfhEventLogDigest *v41; // [rsp+90h] [rbp-39h]
  PpfhEventLogDigest *v42; // [rsp+98h] [rbp-31h]
  __int64 v43; // [rsp+A0h] [rbp-29h]
  int v44; // [rsp+A8h] [rbp-21h]
  __int64 v45; // [rsp+B0h] [rbp-19h] BYREF
  void *Src; // [rsp+B8h] [rbp-11h] BYREF
  _OWORD v47[2]; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v48; // [rsp+E0h] [rbp+17h] BYREF
  struct TREE_VARIABLE_DATA *v49; // [rsp+E8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]
  char v51; // [rsp+148h] [rbp+7Fh] BYREF

  v4 = 0;
  LODWORD(Size) = 0;
  memset(v47, 0, sizeof(v47));
  v48 = 0;
  v51 = 0;
  v5 = PpfEvtLogIteratorInitialize(a2, a3, v47, &v51);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x4C6, v6, (const char *)(unsigned int)v5, v28);
  *(_WORD *)this = v48;
  *((_DWORD *)this + 1) = HIDWORD(v48);
  while ( v51 )
  {
    v36 = 0;
    v35 = 0;
    Size = 0;
    v34 = 0;
    v37 = 0;
    Current = PpfEvtLogIteratorGetCurrent(
                (unsigned int)v47,
                (unsigned int)&v36,
                (unsigned int)&v35,
                (unsigned int)&Size,
                (__int64)&v34,
                (__int64)&v37);
    if ( Current < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x4D3, v8, (const char *)(unsigned int)Current, v29);
    PpfhEventLogEvent::PpfhEventLogEvent((PpfhEventLogEvent *)v39, v36, v35, v37, v34, 0);
    for ( i = 0; i < 0x2Au; ++i )
    {
      if ( (c_PpfAlgorithmIdToBitmapTable[i] & HIDWORD(v48)) != 0 )
      {
        v10 = PpfEvtLogIteratorSetPreferredHashAlgID(v47, i);
        if ( v10 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x4DC, v11, (const char *)(unsigned int)v10, v30);
        v12 = PpfEvtLogIteratorGetCurrent(
                (unsigned int)v47,
                (unsigned int)&v36,
                (unsigned int)&v35,
                (unsigned int)&Size,
                (__int64)&v34,
                (__int64)&v37);
        if ( v12 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x4DD, v13, (const char *)(unsigned int)v12, v30);
        if ( Size )
        {
          if ( v41 == v42 )
          {
            std::vector<PpfhEventLogDigest>::_Emplace_reallocate<unsigned short &,unsigned char * &,unsigned short &>(
              (unsigned int)&v40,
              (_DWORD)v41,
              (unsigned int)&v48,
              (unsigned int)&Size,
              (__int64)&v48 + 2);
          }
          else
          {
            PpfhEventLogDigest::PpfhEventLogDigest(v41, v48, (unsigned __int8 *)Size, WORD1(v48));
            v41 = (PpfhEventLogDigest *)((char *)v41 + 24);
          }
        }
      }
    }
    v32[0] = 0;
    Src = 0;
    LODWORD(Size) = 0;
    v14 = PpfhCheckForAndValidateSBVarEvent(
            v36,
            v35,
            v37,
            v34,
            v32,
            &v49,
            (unsigned __int8 **)&Src,
            (unsigned int *)&Size,
            0,
            0);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4ED,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v14,
        v31);
    if ( v32[0] )
    {
      v16 = Size;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &lpMem,
        0,
        (unsigned int)Size,
        v15);
      v18 = v4 | 2;
      LODWORD(Size) = v18;
      if ( !lpMem )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v17);
      LODWORD(Size) = v18 & 0xFFFFFFFD;
      v4 = v18 & 0xFFFFFFFC | 1;
      memcpy_0(lpMem, Src, v16);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v45,
        &lpMem);
      v19 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v19);
      }
    }
    v21 = *((_QWORD *)this + 2);
    if ( v21 == *((_QWORD *)this + 3) )
    {
      std::vector<PpfhEventLogEvent>::_Emplace_reallocate<PpfhEventLogEvent>(
        (char *)this + 8,
        *((_QWORD *)this + 2),
        v39);
    }
    else
    {
      *(_DWORD *)v21 = v39[0];
      *(_DWORD *)(v21 + 4) = v39[1];
      v22 = v42;
      v42 = 0;
      v23 = v41;
      v41 = 0;
      v24 = v40;
      v40 = 0;
      *(_QWORD *)(v21 + 8) = v24;
      *(_QWORD *)(v21 + 16) = v23;
      *(_QWORD *)(v21 + 24) = v22;
      v25 = v43;
      v43 = 0;
      *(_QWORD *)(v21 + 32) = v25;
      *(_DWORD *)(v21 + 40) = v44;
      *(_QWORD *)(v21 + 48) = v45;
      v45 = 0;
      *((_QWORD *)this + 2) += 56LL;
    }
    Next = PpfEvtLogIteratorTryGetNext(v47, &v51);
    if ( Next < 0 )
      wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x4F8, v27, (const char *)(unsigned int)Next, v31);
    PpfhEventLogEvent::~PpfhEventLogEvent((PpfhEventLogEvent *)v39);
  }
}

```

## disassembly

```asm
0x18002c7b0  push    rbp
0x18002c7b2  push    rbx
0x18002c7b3  push    rsi
0x18002c7b4  push    rdi
0x18002c7b5  push    r14
0x18002c7b7  push    r15
0x18002c7b9  lea     rbp, [rsp-2Fh]
0x18002c7be  sub     rsp, 0F8h
0x18002c7c5  mov     eax, r8d
0x18002c7c8  mov     r10, rdx
0x18002c7cb  mov     rsi, rcx
0x18002c7ce  xor     r14d, r14d
0x18002c7d1  mov     edi, r14d
0x18002c7d4  mov     dword ptr [rbp+57h+Size], r14d
0x18002c7d8  xorps   xmm0, xmm0
0x18002c7db  xor     ecx, ecx
0x18002c7dd  movups  [rbp+57h+var_60], xmm0
0x18002c7e1  movups  [rbp+57h+var_50], xmm0
0x18002c7e5  mov     [rbp+57h+var_40], rcx
0x18002c7e9  mov     [rbp+57h+arg_18], r14b
0x18002c7ed  lea     r9, [rbp+57h+arg_18]
0x18002c7f1  lea     r8, [rbp+57h+var_60]
0x18002c7f5  mov     edx, eax
0x18002c7f7  mov     rcx, r10
0x18002c7fa  call    PpfEvtLogIteratorInitialize
0x18002c7ff  mov     rcx, [rbp+5Fh]; this
0x18002c803  test    eax, eax
0x18002c805  js      loc_18002CAF0
0x18002c80b  movzx   eax, word ptr [rbp+57h+var_40]
0x18002c80f  mov     [rsi], ax
0x18002c812  mov     eax, dword ptr [rbp+57h+var_40+4]
0x18002c815  mov     [rsi+4], eax
0x18002c818  cmp     [rbp+57h+arg_18], r14b
0x18002c81c  jz      loc_18002CAC3
0x18002c822  lea     r15d, [r14+1]
0x18002c826  mov     [rbp+57h+var_B8], r14d
0x18002c82a  mov     [rbp+57h+var_BC], r14d
0x18002c82e  mov     [rbp+57h+Size], r14
0x18002c832  mov     [rbp+57h+var_C0], r14d
0x18002c836  mov     [rbp+57h+var_B0], r14
0x18002c83a  lea     rax, [rbp+57h+var_B0]
0x18002c83e  mov     [rsp+120h+var_F8], rax
0x18002c843  lea     rax, [rbp+57h+var_C0]
0x18002c847  mov     [rsp+120h+var_100], rax; int
0x18002c84c  lea     r9, [rbp+57h+Size]
0x18002c850  lea     r8, [rbp+57h+var_BC]
0x18002c854  lea     rdx, [rbp+57h+var_B8]
0x18002c858  lea     rcx, [rbp+57h+var_60]
0x18002c85c  call    PpfEvtLogIteratorGetCurrent
0x18002c861  mov     rcx, [rbp+5Fh]; this
0x18002c865  test    eax, eax
0x18002c867  js      loc_18002CAE2
0x18002c86d  mov     [rsp+120h+var_F8], r14; unsigned __int16 *
0x18002c872  mov     eax, [rbp+57h+var_C0]
0x18002c875  mov     dword ptr [rsp+120h+var_100], eax; int
0x18002c879  mov     r9, [rbp+57h+var_B0]; unsigned __int8 *
0x18002c87d  mov     r8d, [rbp+57h+var_BC]; unsigned int
0x18002c881  mov     edx, [rbp+57h+var_B8]; unsigned int
0x18002c884  lea     rcx, [rbp+57h+var_A0]; this
0x18002c888  call    ??0PpfhEventLogEvent@@QEAA@IIPEAEIPEBG@Z; PpfhEventLogEvent::PpfhEventLogEvent(uint,uint,uchar *,uint,ushort const *)
0x18002c88d  nop
0x18002c88e  mov     ebx, r14d
0x18002c891  movzx   eax, bx
0x18002c894  lea     rcx, c_PpfAlgorithmIdToBitmapTable
0x18002c89b  mov     eax, [rcx+rax*4]
0x18002c89e  test    dword ptr [rbp+57h+var_40+4], eax
0x18002c8a1  jz      loc_18002C93A
0x18002c8a7  movzx   edx, bx
0x18002c8aa  lea     rcx, [rbp+57h+var_60]
0x18002c8ae  call    PpfEvtLogIteratorSetPreferredHashAlgID
0x18002c8b3  mov     rcx, [rbp+5Fh]; this
0x18002c8b7  test    eax, eax
0x18002c8b9  js      loc_18002CB0C
0x18002c8bf  lea     rax, [rbp+57h+var_B0]
0x18002c8c3  mov     [rsp+120h+var_F8], rax
0x18002c8c8  lea     rax, [rbp+57h+var_C0]
0x18002c8cc  mov     [rsp+120h+var_100], rax; int
0x18002c8d1  lea     r9, [rbp+57h+Size]
0x18002c8d5  lea     r8, [rbp+57h+var_BC]
0x18002c8d9  lea     rdx, [rbp+57h+var_B8]
0x18002c8dd  lea     rcx, [rbp+57h+var_60]
0x18002c8e1  call    PpfEvtLogIteratorGetCurrent
0x18002c8e6  mov     rcx, [rbp+5Fh]; this
0x18002c8ea  test    eax, eax
0x18002c8ec  js      loc_18002CAFE
0x18002c8f2  mov     r8, [rbp+57h+Size]; unsigned __int8 *
0x18002c8f6  test    r8, r8
0x18002c8f9  jz      short loc_18002C93A
0x18002c8fb  mov     rax, [rbp+57h+var_90]
0x18002c8ff  cmp     rax, [rbp+57h+var_88]
0x18002c903  jz      short loc_18002C91D
0x18002c905  movzx   r9d, word ptr [rbp+57h+var_40+2]; unsigned __int16
0x18002c90a  movzx   edx, word ptr [rbp+57h+var_40]; unsigned __int16
0x18002c90e  mov     rcx, rax; this
0x18002c911  call    ??0PpfhEventLogDigest@@QEAA@GPEAEG@Z; PpfhEventLogDigest::PpfhEventLogDigest(ushort,uchar *,ushort)
0x18002c916  add     [rbp+57h+var_90], 18h
0x18002c91b  jmp     short loc_18002C93A
0x18002c91d  lea     rcx, [rbp+57h+var_40+2]
0x18002c921  mov     [rsp+120h+var_100], rcx
0x18002c926  lea     r9, [rbp+57h+Size]
0x18002c92a  lea     r8, [rbp+57h+var_40]
0x18002c92e  mov     rdx, rax
0x18002c931  lea     rcx, [rbp+57h+var_98]
0x18002c935  call    ??$_Emplace_reallocate@AEAGAEAPEAEAEAG@?$vector@VPpfhEventLogDigest@@V?$allocator@VPpfhEventLogDigest@@@std@@@std@@AEAAPEAVPpfhEventLogDigest@@QEAV2@AEAGAEAPEAE1@Z; std::vector<PpfhEventLogDigest>::_Emplace_reallocate<ushort &,uchar * &,ushort &>(PpfhEventLogDigest * const,ushort &,uchar * &,ushort &)
0x18002c93a  add     bx, r15w
0x18002c93e  cmp     bx, 2Ah ; '*'
0x18002c942  jb      loc_18002C891
0x18002c948  mov     [rbp+57h+var_D0], r14b
0x18002c94c  mov     [rbp+57h+Src], r14
0x18002c950  mov     dword ptr [rbp+57h+Size], r14d
0x18002c954  mov     [rsp+120h+var_D8], r14; unsigned int *
0x18002c959  mov     [rsp+120h+var_E0], r14; unsigned __int8 **
0x18002c95e  lea     rax, [rbp+57h+Size]
0x18002c962  mov     [rsp+120h+var_E8], rax; unsigned int *
0x18002c967  lea     rax, [rbp+57h+Src]
0x18002c96b  mov     [rsp+120h+var_F0], rax; unsigned __int8 **
0x18002c970  lea     rax, [rbp+57h+var_38]
0x18002c974  mov     [rsp+120h+var_F8], rax; struct TREE_VARIABLE_DATA **
0x18002c979  lea     rax, [rbp+57h+var_D0]
0x18002c97d  mov     [rsp+120h+var_100], rax; int
0x18002c982  mov     r9d, [rbp+57h+var_C0]; unsigned int
0x18002c986  mov     r8, [rbp+57h+var_B0]; unsigned __int8 *
0x18002c98a  mov     edx, [rbp+57h+var_BC]; unsigned int
0x18002c98d  mov     ecx, [rbp+57h+var_B8]; unsigned int
0x18002c990  call    ?PpfhCheckForAndValidateSBVarEvent@@YAJIIPEAEIPEA_NPEAPEAUTREE_VARIABLE_DATA@@PEAPEAEPEAI34@Z; PpfhCheckForAndValidateSBVarEvent(uint,uint,uchar *,uint,bool *,TREE_VARIABLE_DATA * *,uchar * *,uint *,uchar * *,uint *)
0x18002c995  mov     rcx, [rbp+5Fh]; this
0x18002c999  test    eax, eax
0x18002c99b  jns     short loc_18002C9B1
0x18002c99d  mov     r9d, eax; char *
0x18002c9a0  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002c9a7  mov     edx, 4EDh; void *
0x18002c9ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c9b1  cmp     [rbp+57h+var_D0], r14b
0x18002c9b5  jz      short loc_18002CA2A
0x18002c9b7  mov     ebx, dword ptr [rbp+57h+Size]
0x18002c9ba  mov     r8d, ebx
0x18002c9bd  xor     edx, edx
0x18002c9bf  lea     rcx, [rbp+57h+lpMem]
0x18002c9c3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002c9c8  or      edi, 2
0x18002c9cb  mov     dword ptr [rbp+57h+Size], edi
0x18002c9ce  mov     rax, [rbp+5Fh]
0x18002c9d2  mov     rcx, [rbp+57h+lpMem]; void *
0x18002c9d6  test    rcx, rcx
0x18002c9d9  jz      loc_18002CB1A
0x18002c9df  and     edi, 0FFFFFFFDh
0x18002c9e2  mov     dword ptr [rbp+57h+Size], edi
0x18002c9e5  or      edi, r15d
0x18002c9e8  mov     r8d, ebx; Size
0x18002c9eb  mov     rdx, [rbp+57h+Src]; Src
0x18002c9ef  call    memcpy_0
0x18002c9f4  lea     rdx, [rbp+57h+lpMem]
0x18002c9f8  lea     rcx, [rbp+57h+var_70]
0x18002c9fc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002ca01  mov     rbx, [rbp+57h+lpMem]
0x18002ca05  test    rbx, rbx
0x18002ca08  jz      short loc_18002CA2A
0x18002ca0a  call    cs:__imp_GetProcessHeap
0x18002ca11  nop     dword ptr [rax+rax+00h]
0x18002ca16  mov     rcx, rax; hHeap
0x18002ca19  mov     r8, rbx; lpMem
0x18002ca1c  xor     edx, edx; dwFlags
0x18002ca1e  call    cs:__imp_HeapFree
0x18002ca25  nop     dword ptr [rax+rax+00h]
0x18002ca2a  mov     r9, [rsi+10h]
0x18002ca2e  cmp     r9, [rsi+18h]
0x18002ca32  jz      short loc_18002CA8B
0x18002ca34  mov     eax, [rbp+57h+var_A0]
0x18002ca37  mov     [r9], eax
0x18002ca3a  mov     eax, [rbp+57h+var_9C]
0x18002ca3d  mov     [r9+4], eax
0x18002ca41  mov     rdx, [rbp+57h+var_88]
0x18002ca45  mov     [rbp+57h+var_88], r14
0x18002ca49  mov     rcx, [rbp+57h+var_90]
0x18002ca4d  mov     [rbp+57h+var_90], r14
0x18002ca51  mov     rax, [rbp+57h+var_98]
0x18002ca55  mov     [rbp+57h+var_98], r14
0x18002ca59  mov     [r9+8], rax
0x18002ca5d  mov     [r9+10h], rcx
0x18002ca61  mov     [r9+18h], rdx
0x18002ca65  mov     rax, [rbp+57h+var_80]
0x18002ca69  mov     [rbp+57h+var_80], r14
0x18002ca6d  mov     [r9+20h], rax
0x18002ca71  mov     eax, [rbp+57h+var_78]
0x18002ca74  mov     [r9+28h], eax
0x18002ca78  mov     rax, [rbp+57h+var_70]
0x18002ca7c  mov     [r9+30h], rax
0x18002ca80  mov     [rbp+57h+var_70], r14
0x18002ca84  add     qword ptr [rsi+10h], 38h ; '8'
0x18002ca89  jmp     short loc_18002CA9B
0x18002ca8b  lea     r8, [rbp+57h+var_A0]
0x18002ca8f  mov     rdx, r9
0x18002ca92  lea     rcx, [rsi+8]
0x18002ca96  call    ??$_Emplace_reallocate@VPpfhEventLogEvent@@@?$vector@VPpfhEventLogEvent@@V?$allocator@VPpfhEventLogEvent@@@std@@@std@@AEAAPEAVPpfhEventLogEvent@@QEAV2@$$QEAV2@@Z; std::vector<PpfhEventLogEvent>::_Emplace_reallocate<PpfhEventLogEvent>(PpfhEventLogEvent * const,PpfhEventLogEvent &&)
0x18002ca9b  lea     rdx, [rbp+57h+arg_18]
0x18002ca9f  lea     rcx, [rbp+57h+var_60]
0x18002caa3  call    PpfEvtLogIteratorTryGetNext
0x18002caa8  mov     rcx, [rbp+5Fh]; this
0x18002caac  test    eax, eax
0x18002caae  js      short loc_18002CAD4
0x18002cab0  lea     rcx, [rbp+57h+var_A0]; this
0x18002cab4  call    ??1PpfhEventLogEvent@@QEAA@XZ; PpfhEventLogEvent::~PpfhEventLogEvent(void)
0x18002cab9  cmp     [rbp+57h+arg_18], r14b
0x18002cabd  jnz     loc_18002C826
0x18002cac3  add     rsp, 0F8h
0x18002caca  pop     r15
0x18002cacc  pop     r14
0x18002cace  pop     rdi
0x18002cacf  pop     rsi
0x18002cad0  pop     rbx
0x18002cad1  pop     rbp
0x18002cad2  retn
0x18002cad4  mov     r9d, eax; char *
0x18002cad7  mov     edx, 4F8h; void *
0x18002cadc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cae2  mov     r9d, eax; char *
0x18002cae5  mov     edx, 4D3h; void *
0x18002caea  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002caf0  mov     r9d, eax; char *
0x18002caf3  mov     edx, 4C6h; void *
0x18002caf8  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cafe  mov     r9d, eax; char *
0x18002cb01  mov     edx, 4DDh; void *
0x18002cb06  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cb0c  mov     r9d, eax; char *
0x18002cb0f  mov     edx, 4DCh; void *
0x18002cb14  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18002cb1a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cb21  mov     edx, 0FF8h; void *
0x18002cb26  mov     rcx, rax; this
0x18002cb29  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
