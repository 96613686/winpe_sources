# CExposedDocFile::OpenEntry(CDfName const *,ulong,ulong,void * *)

- ea: `0x180017d40`
- end: `0x18001866d`
- name: `?OpenEntry@CExposedDocFile@@AEAAJPEBVCDfName@@KKPEAPEAX@Z`
- size: `2349`
- prototype: `int(CExposedDocFile *__hidden this, const struct CDfName *, unsigned int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015420`
- `0x1800162a0`

## callees

- `0x180017204`
- `0x180017d40`
- `0x180018680`
- `0x18001871c`
- `0x180018f40`
- `0x180019670`
- `0x180019e20`
- `0x18001a620`
- `0x18001a880`
- `0x18001ad54`
- `0x18001faf0`
- `0x18002e73c`
- `0x18002e778`
- `0x18002e7e0`
- `0x18002ea90`
- `0x1800367e8`
- `0x18003dc44`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001845e`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180018471`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180018480`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001845e`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180018471`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180018480`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800184e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018530`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018599`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800184e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018530`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018599`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001811a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001811a`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::OpenEntry(
        CExposedDocFile *this,
        const struct CDfName *a2,
        int a3,
        unsigned int a4,
        void **a5)
{
  char *v8; // r13
  __int64 v9; // rsi
  int v10; // edx
  int v11; // edx
  int v12; // ecx
  unsigned int v13; // r14d
  int v14; // ecx
  __int64 v15; // rdx
  __int64 i; // rdi
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  PDocFile *v19; // rcx
  int inited; // r12d
  struct PSStream *v21; // rdi
  int v22; // r12d
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rsi
  unsigned __int16 v26; // r14
  __int64 v27; // rdx
  __int64 v28; // r8
  char *v29; // rdi
  struct PSStream *v30; // rax
  __int64 v31; // rax
  __int64 v32; // r12
  GUID *v33; // rdi
  char *v34; // rax
  __int64 v35; // r14
  __int64 v36; // rsi
  struct CSmAllocator *TlsSmAllocator; // rax
  __int64 v38; // rax
  unsigned int v39; // edx
  struct CAsyncConnection *v40; // r8
  unsigned int v42; // eax
  struct CSmAllocator *v43; // rax
  __int64 v44; // rax
  __int64 v45; // r14
  _QWORD *v46; // r15
  __int64 v47; // rdi
  struct PSStream *v48; // rbx
  unsigned int v49; // eax
  __int64 v50; // r10
  CAsyncConnection *v51; // rcx
  struct IConnectionPointContainer *v52; // rdx
  CSmAllocator *v53; // rax
  CSmAllocator *v54; // rax
  CSmAllocator *v55; // rax
  CSmAllocator *v56; // rax
  CSmAllocator *v57; // rax
  CSmAllocator *v58; // rax
  int v59; // ebx
  _QWORD *ReservedForOle; // [rsp+20h] [rbp-10h] BYREF
  struct PSStream *v61; // [rsp+28h] [rbp-8h] BYREF

  v61 = 0;
  if ( (a4 & 0x70) != 0x10 )
    return (unsigned int)-2147287039;
  v8 = (char *)this + 176;
  if ( (a4 & 0x10000) != 0 )
  {
    inited = CFileStream::InitScratch(*(CFileStream **)(*(_QWORD *)v8 + 24LL));
    if ( inited < 0 )
      return (unsigned int)inited;
  }
  v9 = *((_QWORD *)this + 20);
  if ( a3 == 2 )
  {
    v10 = (a4 & 0x10000) != 0 ? 2 : 0;
    if ( (a4 & 3) != 0 )
    {
      if ( (a4 & 3) == 1 )
      {
        v10 |= 0x80u;
      }
      else if ( (a4 & 3) == 2 )
      {
        v10 |= 0xC0u;
      }
    }
    else
    {
      v10 |= 0x40u;
    }
    v11 = v10 | 0x300;
    v61 = 0;
    v12 = v11 | 0x400;
    if ( (a4 & 0x40000) == 0 )
      v12 = v11;
    if ( (a4 & 0x200000) != 0 )
      v12 |= 0x40000u;
    v13 = v12 | 0x4000;
    if ( (a4 & 0x100000) == 0 )
      v13 = v12;
    v14 = *(_DWORD *)(v9 + 20);
    if ( (v14 & 0x20) != 0 )
      return (unsigned int)-2147286782;
    if ( (v14 & 0x40) == 0 )
      return (unsigned int)-2147287035;
    if ( (~(_BYTE)v14 & (~((_BYTE)v14 << 6) & 0x80 | 0x40) & (unsigned __int8)v13) != 0 )
      return (unsigned int)-2147286785;
    v15 = *(_QWORD *)(v9 + 128);
    if ( v15 )
      goto LABEL_23;
LABEL_19:
    for ( i = 0; i; i = v15 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
    {
      v17 = *(unsigned __int16 *)(i + 88);
      if ( (_WORD)v17 == *((_WORD *)a2 + 32)
        && !(unsigned int)dfwcsnicmp((const unsigned __int16 *)(i + 24), (const unsigned __int16 *)a2, v17 >> 1)
        && ((*(_BYTE *)(i + 20) | v13 & (unsigned __int8)(*(_DWORD *)(i + 20) >> 2)) & 0xC0) != 0 )
      {
        return (unsigned int)-2147287035;
      }
      v15 = *(_QWORD *)(i + 96);
      if ( !v15 )
        goto LABEL_19;
LABEL_23:
      ;
    }
    v18 = *(_QWORD *)(v9 + 120);
    if ( v18 )
      v19 = (PDocFile *)(v18 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v19 = 0;
    inited = PDocFile::GetStream(v19, a2, v13, &v61);
    if ( inited < 0 )
      return (unsigned int)inited;
    v21 = v61;
    v22 = *((_DWORD *)v61 + 2);
    GetTlsSmAllocator();
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( !ReservedForOle )
      InternalTlsAllocData(&ReservedForOle);
    if ( ReservedForOle[1] )
      goto LABEL_30;
    v57 = (CSmAllocator *)HeapAlloc(g_hHeap, 0, 0x30u);
    if ( v57 )
    {
      v58 = CSmAllocator::CSmAllocator(v57);
      ReservedForOle[1] = v58;
      if ( v58 )
      {
LABEL_30:
        v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)ReservedForOle[1] + 24LL))(ReservedForOle[1], 168);
        v24 = v23;
        if ( v23 )
        {
          *(GUID *)v23 = GUID_NULL;
          *(_WORD *)(v23 + 88) = 0;
          *(_QWORD *)(v23 + 96) = 0;
          *(_QWORD *)(v23 + 104) = 0;
          *(_QWORD *)(v23 + 112) = 0;
          *(_QWORD *)(v23 + 128) = 0;
          *(_QWORD *)(v23 + 144) = 0;
          *(_QWORD *)(v23 + 136) = 0;
          *(_QWORD *)(v23 + 152) = 0;
          *(_BYTE *)(v23 + 160) = 0;
          *(_QWORD *)(v23 + 128) = v23 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          *(_QWORD *)(v23 + 144) = 0;
          *(_QWORD *)(v23 + 104) = 0;
          *(_DWORD *)(v23 + 20) = v13;
          if ( v9 )
            v25 = v9 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v25 = 0;
          *(_QWORD *)(v23 + 112) = v25;
          *(_DWORD *)(v23 + 124) = 1;
          v26 = *((_WORD *)a2 + 32);
          if ( v26 > 0x40u )
            v26 = 64;
          memcpy_0((void *)(v23 + 24), a2, v26);
          *(_WORD *)(v24 + 88) = v26;
          v27 = *(_QWORD *)(v24 + 112);
          if ( v27 )
            v28 = v27 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v28 = 0;
          *(_QWORD *)(v24 + 96) = *(_QWORD *)(v28 + 128);
          *(_QWORD *)(v28 + 128) = v24 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          *(_DWORD *)(v24 + 120) = 0;
          *(GUID *)v24 = GUID_ab8fc07c_9ca5_4cb4_80f9_f0811ff49894;
          if ( v21 )
            v29 = (char *)v21 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v29 = 0;
          *(_QWORD *)(v24 + 104) = v29;
          *(_DWORD *)(v24 + 16) = v22;
          v30 = (struct PSStream *)NtCurrentTeb()->ReservedForOle;
          v61 = v30;
          if ( !v30 )
          {
            InternalTlsAllocData(&v61);
            v30 = v61;
          }
          if ( !*((_QWORD *)v30 + 1) )
          {
            v53 = (CSmAllocator *)HeapAlloc(g_hHeap, 0, 0x30u);
            if ( v53 )
            {
              v54 = CSmAllocator::CSmAllocator(v53);
              *((_QWORD *)v61 + 1) = v54;
              if ( v54 )
                goto LABEL_42;
            }
            else
            {
              *((_QWORD *)v61 + 1) = 0;
            }
            *((_QWORD *)v61 + 1) = &g_ErrorSmAllocator;
          }
LABEL_42:
          ReservedForOle = NtCurrentTeb()->ReservedForOle;
          if ( !ReservedForOle )
            InternalTlsAllocData(&ReservedForOle);
          if ( !ReservedForOle[1] )
          {
            v55 = (CSmAllocator *)HeapAlloc(g_hHeap, 0, 0x30u);
            if ( v55 )
            {
              v56 = CSmAllocator::CSmAllocator(v55);
              ReservedForOle[1] = v56;
              if ( v56 )
                goto LABEL_45;
            }
            else
            {
              ReservedForOle[1] = 0;
            }
            ReservedForOle[1] = &g_ErrorSmAllocator;
          }
LABEL_45:
          v31 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)ReservedForOle[1] + 24LL))(
                  ReservedForOle[1],
                  152);
          v32 = v31;
          if ( v31 )
          {
            v33 = (GUID *)(v31 + 64);
            *(_QWORD *)(v31 + 16) = &IMappedStream::`vftable';
            *(GUID *)(v31 + 64) = GUID_NULL;
            *(_QWORD *)(v31 + 80) = 0;
            if ( v31 == -64 )
              v34 = 0;
            else
              v34 = (char *)v33 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            *(_QWORD *)(v32 + 80) = v34;
            *(_DWORD *)(v32 + 96) = GetCurrentProcessId();
            *(_QWORD *)(v32 + 88) = *(_QWORD *)NtCurrentTeb()->ReservedForOle;
            CAsyncConnectionContainer::CAsyncConnectionContainer((CAsyncConnectionContainer *)(v32 + 24));
            *(_QWORD *)(v32 + 8) = &CExposedStream::`vftable'{for `IMarshal'};
            *(_QWORD *)v32 = &CExposedStream::`vftable'{for `IStream'};
            *(_QWORD *)(v32 + 16) = &CExposedStream::`vftable'{for `IMappedStream'};
            *(_QWORD *)(v32 + 24) = &CExposedStream::`vftable'{for `CAsyncConnectionContainer'};
            *(_QWORD *)(v32 + 144) = 0;
            *(_QWORD *)(v32 + 112) = 0;
            *(_QWORD *)(v32 + 120) = 0;
            *v33 = GUID_04a45d68_dba8_467d_9aed_e762432212f9;
            *(_DWORD *)(v32 + 128) = 0;
            *(_QWORD *)(v32 + 136) = 0;
            *(_QWORD *)(v32 + 104) = 0;
            v35 = *((_QWORD *)this + 22);
            v36 = *((_QWORD *)this + 21);
            GetTlsSmAllocator();
            TlsSmAllocator = GetTlsSmAllocator();
            v38 = (*(__int64 (__fastcall **)(struct CSmAllocator *, __int64))(*(_QWORD *)TlsSmAllocator + 24LL))(
                    TlsSmAllocator,
                    32);
            if ( v38 )
            {
              *(_DWORD *)(v38 + 24) = 1;
              *(_QWORD *)(v38 + 16) = 0;
              *(GUID *)v38 = GUID_56401fd1_cf16_4404_9dd0_d642080d23eb;
              *(_QWORD *)(v32 + 136) = v38;
              *(_QWORD *)(v32 + 120) = v35;
              *(_QWORD *)(v32 + 104) = v24;
              *(_QWORD *)(v32 + 112) = v36;
              _InterlockedIncrement((volatile signed __int32 *)(v36 + 60));
              *(_DWORD *)(v32 + 128) = 1;
              _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 22) + 56LL));
              v40 = (CExposedDocFile *)((char *)this + 88);
              if ( !*((_QWORD *)this + 13) )
              {
LABEL_50:
                *a5 = (void *)v32;
                return 0;
              }
              v51 = (CAsyncConnection *)(v32 + 32);
              v52 = (struct IConnectionPointContainer *)(v32 + 24);
              goto LABEL_81;
            }
            CExposedStream::`scalar deleting destructor'((CExposedStream *)v32, v39);
          }
          CPubStream::vRelease((CPubStream *)v24);
          return 2147680264LL;
        }
        inited = -2147287032;
        PBasicEntry::Release(v21);
        return (unsigned int)inited;
      }
    }
    else
    {
      ReservedForOle[1] = 0;
    }
    ReservedForOle[1] = &g_ErrorSmAllocator;
    goto LABEL_30;
  }
  v42 = ModeToDFlags(a4);
  inited = CPubDocFile::GetDocFile((CPubDocFile *)v9, a2, v42, &v61);
  if ( inited < 0 )
    return (unsigned int)inited;
  GetTlsSmAllocator();
  v43 = GetTlsSmAllocator();
  v44 = (*(__int64 (__fastcall **)(struct CSmAllocator *, __int64))(*(_QWORD *)v43 + 24LL))(v43, 256);
  v32 = v44;
  if ( !v44 )
  {
    inited = -2147287032;
    CPubDocFile::vRelease(v61);
    return (unsigned int)inited;
  }
  v45 = *((_QWORD *)this + 21);
  v46 = (_QWORD *)(v44 + 8);
  v47 = *(_QWORD *)v8;
  v48 = v61;
  CPropertySetStorage::CPropertySetStorage(v44 + 8, 1);
  CMarshalList::CMarshalList((CMarshalList *)(v32 + 120));
  CAsyncConnectionContainer::CAsyncConnectionContainer((CAsyncConnectionContainer *)(v32 + 80));
  *v46 = &CExposedDocFile::`vftable'{for `CPropertySetStorage'};
  *(_QWORD *)v32 = &CExposedDocFile::`vftable'{for `IStorage'};
  *(_QWORD *)(v32 + 48) = &CExposedDocFile::`vftable'{for `IRootStorage'};
  *(_QWORD *)(v32 + 56) = &CExposedDocFile::`vftable'{for `IMarshal'};
  *(_QWORD *)(v32 + 64) = &CExposedDocFile::`vftable'{for `IBlockingLock'};
  *(_QWORD *)(v32 + 72) = &CExposedDocFile::`vftable'{for `IDirectWriterLock'};
  *(_QWORD *)(v32 + 80) = &CExposedDocFile::`vftable'{for `CAsyncConnectionContainer'};
  v49 = DFlagsToMode(*((_DWORD *)v48 + 5));
  *(_QWORD *)(v32 + 192) = &CPropertyBagEx::`vftable'{for `IPropertyBagEx'};
  *(_QWORD *)(v32 + 200) = &CPropertyBagEx::`vftable'{for `IPropertyBag'};
  *(_DWORD *)(v32 + 208) &= ~1u;
  *(_DWORD *)(v32 + 212) = 0;
  *(_QWORD *)(v32 + 224) = 0;
  *(_QWORD *)(v32 + 216) = 0;
  *(_QWORD *)(v32 + 232) = 0;
  *(_DWORD *)(v32 + 244) = 0;
  *(_DWORD *)(v32 + 240) = v49 & 0xFFFEFFFF;
  *(_QWORD *)(v32 + 248) = 0;
  *(_QWORD *)(v32 + 176) = v47;
  *(_QWORD *)(v32 + 160) = v48;
  *(_QWORD *)(v32 + 168) = v45;
  _InterlockedIncrement((volatile signed __int32 *)(v45 + 60));
  *(_DWORD *)(v32 + 188) = 1;
  *(GUID *)(v32 + 120) = GUID_efe6e9cd_1af4_49c2_89fd_e27936f6b823;
  *(_QWORD *)(v32 + 16) = v32;
  *(_QWORD *)(v32 + 24) = v50;
  *(_QWORD *)(v32 + 216) = v46;
  *(_QWORD *)(v32 + 232) = v50;
  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)v8 + 56LL));
  v40 = (CExposedDocFile *)((char *)this + 88);
  if ( !*((_QWORD *)this + 13) )
    goto LABEL_50;
  v51 = (CAsyncConnection *)(v32 + 88);
  v52 = (struct IConnectionPointContainer *)(v32 + 80);
LABEL_81:
  v59 = CAsyncConnection::Init(v51, v52, v40);
  if ( v59 >= 0 )
    goto LABEL_50;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  return (unsigned int)v59;
}

```

## disassembly

```asm
0x180017d40  mov     [rsp-38h+arg_8], rbx
0x180017d45  mov     [rsp-38h+arg_10], r8d
0x180017d4a  mov     [rsp-38h+arg_0], rcx
0x180017d4f  push    rbp
0x180017d50  push    rsi
0x180017d51  push    rdi
0x180017d52  push    r12
0x180017d54  push    r13
0x180017d56  push    r14
0x180017d58  push    r15
0x180017d5a  mov     rbp, rsp
0x180017d5d  sub     rsp, 30h
0x180017d61  mov     edi, r9d
0x180017d64  mov     r15, rdx
0x180017d67  xor     r9d, r9d
0x180017d6a  mov     eax, edi
0x180017d6c  and     al, 70h
0x180017d6e  mov     [rbp+var_8], r9
0x180017d72  mov     rbx, rcx
0x180017d75  cmp     al, 10h
0x180017d77  jnz     loc_180018619
0x180017d7d  mov     r14d, edi
0x180017d80  lea     r13, [rcx+0B0h]
0x180017d87  and     r14d, 10000h
0x180017d8e  jnz     loc_180018624
0x180017d94  cmp     [rbp+arg_10], 2
0x180017d98  mov     rsi, [rbx+0A0h]
0x180017d9f  jnz     loc_18001829B
0x180017da5  mov     eax, r14d
0x180017da8  mov     r8d, edi
0x180017dab  neg     eax
0x180017dad  mov     rbx, r9
0x180017db0  mov     eax, edi
0x180017db2  sbb     edx, edx
0x180017db4  and     r8d, 40000h
0x180017dbb  and     edx, 2
0x180017dbe  and     eax, 3
0x180017dc1  jz      short loc_180017DD9
0x180017dc3  sub     eax, 1
0x180017dc6  jz      loc_1800184CE
0x180017dcc  cmp     eax, 1
0x180017dcf  jnz     short loc_180017DDC
0x180017dd1  or      edx, 0C0h
0x180017dd7  jmp     short loc_180017DDC
0x180017dd9  or      edx, 40h
0x180017ddc  or      edx, 300h
0x180017de2  mov     [rbp+var_8], r9
0x180017de6  mov     ecx, edx
0x180017de8  bts     ecx, 0Ah
0x180017dec  test    r8d, r8d
0x180017def  cmovz   ecx, edx
0x180017df2  mov     eax, ecx
0x180017df4  bts     eax, 12h
0x180017df8  bt      edi, 15h
0x180017dfc  cmovb   ecx, eax
0x180017dff  mov     r14d, ecx
0x180017e02  bts     r14d, 0Eh
0x180017e07  bt      edi, 14h
0x180017e0b  cmovnb  r14d, ecx
0x180017e0f  mov     ecx, [rsi+14h]
0x180017e12  test    cl, 20h
0x180017e15  jnz     loc_180018644
0x180017e1b  test    cl, 40h
0x180017e1e  jz      loc_18001860E
0x180017e24  mov     eax, ecx
0x180017e26  not     ecx
0x180017e28  shl     eax, 6
0x180017e2b  not     eax
0x180017e2d  and     eax, 80h
0x180017e32  or      eax, 40h
0x180017e35  and     eax, ecx
0x180017e37  test    r14b, al
0x180017e3a  jnz     loc_18001827E
0x180017e40  mov     rdx, [rsi+80h]
0x180017e47  test    rdx, rdx
0x180017e4a  jnz     short loc_180017E71
0x180017e4c  mov     rdi, r9
0x180017e4f  nop
0x180017e50  test    rdi, rdi
0x180017e53  jz      short loc_180017E89
0x180017e55  movzx   eax, word ptr [rdi+58h]
0x180017e59  lea     rcx, [rdi+18h]; unsigned __int16 *
0x180017e5d  cmp     ax, [r15+40h]
0x180017e62  jz      loc_180018260
0x180017e68  mov     rdx, [rdi+60h]
0x180017e6c  test    rdx, rdx
0x180017e6f  jz      short loc_180017E4C
0x180017e71  mov     rax, gs:30h
0x180017e7a  mov     rcx, [rax+1758h]
0x180017e81  mov     rdi, [rcx]
0x180017e84  add     rdi, rdx
0x180017e87  jmp     short loc_180017E50
0x180017e89  mov     rdx, [rsi+78h]
0x180017e8d  test    rdx, rdx
0x180017e90  jz      loc_180018606
0x180017e96  mov     rax, gs:30h
0x180017e9f  mov     rcx, [rax+1758h]
0x180017ea6  mov     rcx, [rcx]
0x180017ea9  add     rcx, rdx; this
0x180017eac  lea     r9, [rbp+var_8]; struct PSStream **
0x180017eb0  mov     r8d, r14d; unsigned int
0x180017eb3  mov     rdx, r15; struct CDfName *
0x180017eb6  call    ?GetStream@PDocFile@@QEAAJPEBVCDfName@@KPEAPEAVPSStream@@@Z; PDocFile::GetStream(CDfName const *,ulong,PSStream * *)
0x180017ebb  mov     r12d, eax
0x180017ebe  test    eax, eax
0x180017ec0  js      loc_180018284
0x180017ec6  mov     rdi, [rbp+var_8]
0x180017eca  mov     r12d, [rdi+8]
0x180017ece  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x180017ed3  mov     rax, gs:30h
0x180017edc  mov     rcx, [rax+1758h]
0x180017ee3  mov     [rbp+var_10], rcx
0x180017ee7  test    rcx, rcx
0x180017eea  jz      loc_18001847C
0x180017ef0  mov     rax, [rbp+var_10]
0x180017ef4  lea     r13, ?g_ErrorSmAllocator@@3VCErrorSmAllocator@@A; CErrorSmAllocator g_ErrorSmAllocator
0x180017efb  cmp     qword ptr [rax+8], 0
0x180017f00  jz      loc_18001858A
0x180017f06  mov     rax, [rbp+var_10]
0x180017f0a  mov     edx, 0A8h
0x180017f0f  mov     rcx, [rax+8]
0x180017f13  mov     rax, [rcx]
0x180017f16  mov     rax, [rax+18h]
0x180017f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f1f  mov     rbx, rax
0x180017f22  test    rax, rax
0x180017f25  jz      loc_18001856B
0x180017f2b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180017f32  xor     edx, edx
0x180017f34  movups  xmmword ptr [rax], xmm0
0x180017f37  mov     [rax+58h], dx
0x180017f3b  mov     [rax+60h], rdx
0x180017f3f  mov     [rax+68h], rdx
0x180017f43  mov     [rax+70h], rdx
0x180017f47  mov     [rax+80h], rdx
0x180017f4e  mov     [rax+90h], rdx
0x180017f55  mov     [rax+88h], rdx
0x180017f5c  mov     [rax+98h], rdx
0x180017f63  mov     [rax+0A0h], dl
0x180017f69  mov     rax, gs:30h
0x180017f72  mov     rcx, [rax+1758h]
0x180017f79  mov     rax, rbx
0x180017f7c  sub     rax, [rcx]
0x180017f7f  mov     [rbx+80h], rax
0x180017f86  mov     [rbx+90h], rdx
0x180017f8d  mov     [rbx+68h], rdx
0x180017f91  mov     [rbx+14h], r14d
0x180017f95  test    rsi, rsi
0x180017f98  jz      loc_18001848B
0x180017f9e  mov     rax, gs:30h
0x180017fa7  mov     rcx, [rax+1758h]
0x180017fae  sub     rsi, [rcx]
0x180017fb1  mov     [rbx+70h], rsi
0x180017fb5  mov     dword ptr [rbx+7Ch], 1
0x180017fbc  movzx   r14d, word ptr [r15+40h]
0x180017fc1  cmp     r14w, 40h ; '@'
0x180017fc6  ja      loc_180018255
0x180017fcc  movzx   r8d, r14w; Size
0x180017fd0  lea     rcx, [rbx+18h]; void *
0x180017fd4  mov     rdx, r15; Src
0x180017fd7  call    memcpy_0
0x180017fdc  mov     [rbx+58h], r14w
0x180017fe1  mov     rdx, [rbx+70h]
0x180017fe5  test    rdx, rdx
0x180017fe8  jz      loc_1800184C4
0x180017fee  mov     rax, gs:30h
0x180017ff7  mov     rcx, [rax+1758h]
0x180017ffe  mov     r8, [rcx]
0x180018001  add     r8, rdx
0x180018004  xor     esi, esi
0x180018006  mov     rax, [r8+80h]
0x18001800d  mov     [rbx+60h], rax
0x180018011  mov     rax, gs:30h
0x18001801a  mov     rcx, [rax+1758h]
0x180018021  mov     rax, rbx
0x180018024  sub     rax, [rcx]
0x180018027  mov     [r8+80h], rax
0x18001802e  mov     [rbx+78h], esi
0x180018031  movups  xmm0, xmmword ptr cs:_GUID_ab8fc07c_9ca5_4cb4_80f9_f0811ff49894.Data1
0x180018038  movups  xmmword ptr [rbx], xmm0
0x18001803b  test    rdi, rdi
0x18001803e  jz      loc_180018582
0x180018044  mov     rax, gs:30h
0x18001804d  mov     rcx, [rax+1758h]
0x180018054  sub     rdi, [rcx]
0x180018057  mov     [rbx+68h], rdi
0x18001805b  mov     [rbx+10h], r12d
0x18001805f  mov     rax, gs:30h
0x180018068  mov     rax, [rax+1758h]
0x18001806f  mov     [rbp+var_8], rax
0x180018073  test    rax, rax
0x180018076  jz      loc_18001845A
0x18001807c  cmp     qword ptr [rax+8], 0
0x180018081  jz      loc_1800184D7
0x180018087  mov     rax, gs:30h
0x180018090  mov     rcx, [rax+1758h]
0x180018097  mov     [rbp+var_10], rcx
0x18001809b  test    rcx, rcx
0x18001809e  jz      loc_18001846D
0x1800180a4  mov     rax, [rbp+var_10]
0x1800180a8  cmp     qword ptr [rax+8], 0
0x1800180ad  jz      loc_180018521
0x1800180b3  mov     rax, [rbp+var_10]
0x1800180b7  mov     edx, 98h
0x1800180bc  mov     rcx, [rax+8]
0x1800180c0  mov     rax, [rcx]
0x1800180c3  mov     rax, [rax+18h]
0x1800180c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180cc  mov     r12, rax
0x1800180cf  test    rax, rax
0x1800180d2  jz      loc_18001849B
0x1800180d8  lea     rdi, [r12+40h]
0x1800180dd  lea     rax, ??_7IMappedStream@@6B@; const IMappedStream::`vftable'
0x1800180e4  mov     [r12+10h], rax
0x1800180e9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800180f0  movups  xmmword ptr [rdi], xmm0
0x1800180f3  mov     [rdi+10h], rsi
0x1800180f7  test    rdi, rdi
0x1800180fa  jz      loc_180018665
0x180018100  mov     rax, gs:30h
0x180018109  mov     rcx, [rax+1758h]
0x180018110  mov     rax, rdi
0x180018113  sub     rax, [rcx]
0x180018116  mov     [rdi+10h], rax
0x18001811a  call    cs:__imp_GetCurrentProcessId
0x180018120  mov     [rdi+20h], eax
0x180018123  mov     rax, gs:30h
0x18001812c  mov     rcx, [rax+1758h]
0x180018133  mov     rax, [rcx]
0x180018136  lea     rcx, [r12+18h]; this
0x18001813b  mov     [rdi+18h], rax
0x18001813f  call    ??0CAsyncConnectionContainer@@QEAA@XZ; CAsyncConnectionContainer::CAsyncConnectionContainer(void)
0x180018144  lea     rax, ??_7CExposedStream@@6BIMarshal@@@; const CExposedStream::`vftable'{for `IMarshal'}
0x18001814b  mov     [r12+8], rax
0x180018150  lea     r8, ??_7CExposedStream@@6BIStream@@@; const CExposedStream::`vftable'{for `IStream'}
0x180018157  mov     [r12], r8
0x18001815b  lea     rax, ??_7CExposedStream@@6BIMappedStream@@@; const CExposedStream::`vftable'{for `IMappedStream'}
0x180018162  mov     [r12+10h], rax
0x180018167  lea     rax, ??_7CExposedStream@@6BCAsyncConnectionContainer@@@; const CExposedStream::`vftable'{for `CAsyncConnectionContainer'}
0x18001816e  mov     [r12+18h], rax
0x180018173  mov     [r12+90h], rsi
0x18001817b  movups  xmm0, xmmword ptr cs:_GUID_04a45d68_dba8_467d_9aed_e762432212f9.Data1
0x180018182  mov     [r12+70h], rsi
0x180018187  mov     [r12+78h], rsi
0x18001818c  movups  xmmword ptr [rdi], xmm0
0x18001818f  mov     rdi, [rbp+arg_0]
0x180018193  mov     [r12+80h], esi
0x18001819b  mov     [r12+88h], rsi
0x1800181a3  mov     [r12+68h], rsi
0x1800181a8  mov     r14, [rdi+0B0h]
0x1800181af  mov     rsi, [rdi+0A8h]
0x1800181b6  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x1800181bb  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x1800181c0  mov     r8, rax
0x1800181c3  mov     edx, 20h ; ' '
0x1800181c8  mov     rcx, [rax]
0x1800181cb  mov     rax, [rcx+18h]
0x1800181cf  mov     rcx, r8
0x1800181d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181d7  test    rax, rax
0x1800181da  jz      loc_180018493
0x1800181e0  movups  xmm0, xmmword ptr cs:_GUID_56401fd1_cf16_4404_9dd0_d642080d23eb.Data1
0x1800181e7  mov     dword ptr [rax+18h], 1
0x1800181ee  xor     ecx, ecx
0x1800181f0  mov     [rax+10h], rcx
0x1800181f4  movups  xmmword ptr [rax], xmm0
0x1800181f7  mov     [r12+88h], rax
0x1800181ff  mov     [r12+78h], r14
0x180018204  mov     [r12+68h], rbx
0x180018209  mov     [r12+70h], rsi
0x18001820e  lock inc dword ptr [rsi+3Ch]
0x180018212  mov     dword ptr [r12+80h], 1
0x18001821e  mov     rax, [rdi+0B0h]
0x180018225  lock inc dword ptr [rax+38h]
0x180018229  cmp     [rdi+68h], rcx
0x18001822d  lea     r8, [rdi+58h]; struct CAsyncConnection *
0x180018231  jnz     loc_1800185D6
0x180018237  mov     rax, [rbp+arg_20]
0x18001823b  mov     [rax], r12
0x18001823e  xor     eax, eax
0x180018240  mov     rbx, [rsp+30h+arg_8]
0x180018245  add     rsp, 30h
0x180018249  pop     r15
0x18001824b  pop     r14
0x18001824d  pop     r13
0x18001824f  pop     r12
0x180018251  pop     rdi
0x180018252  pop     rsi
0x180018253  pop     rbp
0x180018254  retn
0x180018255  mov     r14d, 40h ; '@'
0x18001825b  jmp     loc_180017FCC
0x180018260  mov     r8, rax
0x180018263  mov     rdx, r15; unsigned __int16 *
0x180018266  shr     r8, 1; unsigned __int64
0x180018269  call    ?dfwcsnicmp@@YAHPEBG0_K@Z; dfwcsnicmp(ushort const *,ushort const *,unsigned __int64)
0x18001826e  test    eax, eax
0x180018270  jz      loc_18001864F
0x180018276  xor     r9d, r9d
0x180018279  jmp     loc_180017E68
  ... truncated ...
```
