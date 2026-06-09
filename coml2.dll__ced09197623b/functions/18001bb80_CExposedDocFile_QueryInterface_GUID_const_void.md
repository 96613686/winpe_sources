# CExposedDocFile::QueryInterface(_GUID const &,void * *)

- ea: `0x18001bb80`
- end: `0x18001bf5f`
- name: `?QueryInterface@CExposedDocFile@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `991`
- prototype: `__int64 __fastcall(CExposedDocFile *__hidden this, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004b810`
- `0x18004b820`
- `0x18004b830`
- `0x18004b840`
- `0x18004b850`
- `0x18004b860`

## callees

- `0x180018680`
- `0x18001bb24`
- `0x18001bb80`
- `0x18001bf68`
- `0x18001bff0`
- `0x18001c01c`
- `0x18003686c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001bed6`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18001bed6`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::QueryInterface(CExposedDocFile *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rdi
  struct CSmAllocator *TlsSmAllocator; // rax
  __int64 v8; // rcx
  struct CSmAllocator *v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  CPubDocFile *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  unsigned __int64 v25; // rdx
  __int64 v26; // rax
  CPubDocFile *v27; // rcx
  __int64 v28; // rax
  __int64 (__fastcall ***v29)(_QWORD, GUID *, LPUNKNOWN *); // rcx
  char *v30; // rax
  HRESULT v31; // eax
  LPUNKNOWN v32; // rcx
  LPUNKNOWN v33; // rcx
  _QWORD v34[2]; // [rsp+20h] [rbp-10h] BYREF
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 22);
  TlsSmAllocator = GetTlsSmAllocator();
  v8 = *(_QWORD *)(v3 + 88);
  v9 = TlsSmAllocator;
  v10 = *(_QWORD *)(v3 + 96);
  v34[0] = TlsSmAllocator;
  v11 = *(_DWORD *)(v3 + 104);
  *((_QWORD *)v9 + 1) = v8;
  *((_QWORD *)v9 + 2) = v10;
  if ( v8 )
    LODWORD(v8) = *(_DWORD *)(v8 + 16) - 24;
  *((_DWORD *)v9 + 9) = v11;
  *((_DWORD *)v9 + 8) = v8;
  *(_QWORD *)NtCurrentTeb()->ReservedForOle = v10;
  v34[1] = *((_QWORD *)v9 + 3);
  *((_QWORD *)v9 + 3) = v3;
  if ( !a3 )
  {
    v12 = -2147287031;
    goto LABEL_12;
  }
  *a3 = 0;
  v12 = CExposedDocFile::Validate(this);
  if ( v12 < 0 )
    goto LABEL_12;
  v16 = (CPubDocFile *)*((_QWORD *)this + 20);
  if ( (*((_BYTE *)v16 + 20) & 0x20) != 0 )
  {
    v12 = -2147286782;
    goto LABEL_12;
  }
  v12 = 0;
  v17 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IStorage.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IStorage.Data1 )
    v17 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IStorage.Data4;
  if ( !v17 )
    goto LABEL_45;
  v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v18 )
  {
LABEL_45:
    *a3 = this;
    goto LABEL_43;
  }
  v19 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMarshal.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMarshal.Data1 )
    v19 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMarshal.Data4;
  if ( v19 )
  {
    v20 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IAgileObject.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAgileObject.Data1 )
      v20 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IAgileObject.Data4;
    if ( v20 )
    {
      v21 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IRootStorage.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IRootStorage.Data1 )
        v21 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IRootStorage.Data4;
      if ( v21 )
      {
        v22 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPropertySetStorage.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPropertySetStorage.Data1 )
          v22 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPropertySetStorage.Data4;
        if ( !v22 )
        {
          v25 = (unsigned __int64)this + 8;
          goto LABEL_42;
        }
        v23 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IConnectionPointContainer.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IConnectionPointContainer.Data1 )
          v23 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IConnectionPointContainer.Data4;
        if ( !v23 && *((_QWORD *)this + 13) )
        {
          v25 = (unsigned __int64)this + 80;
          goto LABEL_42;
        }
        if ( (unsigned int)CPubDocFile::IsRoot(v16) )
        {
          v24 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IDirectWriterLock.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectWriterLock.Data1 )
            v24 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IDirectWriterLock.Data4;
          if ( !v24 && *(_DWORD *)(*((_QWORD *)this + 21) + 120LL) )
          {
            v25 = (unsigned __int64)this + 72;
LABEL_42:
            *a3 = (void *)(v25 & -(__int64)(this != 0));
LABEL_43:
            CExposedDocFile::AddRef(this);
            goto LABEL_12;
          }
        }
        v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_20011801_5de6_11d1_8e38_00c04fb9386d.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_20011801_5de6_11d1_8e38_00c04fb9386d.Data1 )
          v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_20011801_5de6_11d1_8e38_00c04fb9386d.Data4;
        if ( v13 )
        {
          v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPropertyBag.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPropertyBag.Data1 )
            v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPropertyBag.Data4;
          if ( v14 )
            goto LABEL_11;
          v30 = (char *)(((unsigned __int64)this + 200) & -(__int64)((CExposedDocFile *)((char *)this + 192) != 0));
        }
        else
        {
          v30 = (char *)this + 192;
        }
        *a3 = v30;
        goto LABEL_43;
      }
      if ( (unsigned int)CPubDocFile::IsRoot(v16) )
      {
        v25 = (unsigned __int64)this + 48;
        goto LABEL_42;
      }
LABEL_11:
      v12 = -2147467262;
      goto LABEL_12;
    }
  }
  if ( !IsSharedMemoryModeDisabledForCurrentProcess() )
  {
    v26 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IMarshal.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMarshal.Data1 )
      v26 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IMarshal.Data4;
    if ( !v26 )
    {
      v27 = (CPubDocFile *)*((_QWORD *)this + 20);
      if ( (*((_DWORD *)v27 + 5) & 0x400) == 0 || !(unsigned int)CPubDocFile::IsRoot(v27) )
      {
        v28 = *((_QWORD *)this + 22);
        ppunkMarshal = 0;
        v29 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *))(v28 + 32);
        if ( !v29 )
          v29 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPUNKNOWN *))(v28 + 16);
        v12 = (**v29)(v29, &IID_IDfReserved1, &ppunkMarshal);
        if ( v12 >= 0 )
        {
          ((void (__fastcall *)(LPUNKNOWN))ppunkMarshal->lpVtbl->Release)(ppunkMarshal);
          if ( *(_QWORD *)(*((_QWORD *)this + 22) + 96LL) )
          {
            v25 = (unsigned __int64)this + 56;
            goto LABEL_42;
          }
        }
      }
    }
    goto LABEL_11;
  }
  if ( *((_QWORD *)this + 31) )
  {
LABEL_73:
    v12 = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 31))(
            *((_QWORD *)this + 31),
            a2,
            a3);
    goto LABEL_12;
  }
  ppunkMarshal = 0;
  v31 = CoCreateFreeThreadedMarshaler((LPUNKNOWN)this, &ppunkMarshal);
  v32 = ppunkMarshal;
  v12 = v31;
  if ( v31 >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 31, (signed __int64)ppunkMarshal, 0) )
      v33 = ppunkMarshal;
    else
      v33 = 0;
    if ( v33 )
    {
      ppunkMarshal = 0;
      ((void (__fastcall *)(LPUNKNOWN))v33->lpVtbl->Release)(v33);
    }
    goto LABEL_73;
  }
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v32->lpVtbl->Release)(v32);
  }
LABEL_12:
  CSafeMultiHeap::~CSafeMultiHeap((CSafeMultiHeap *)v34);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001bb80  mov     [rsp-18h+arg_8], rbx
0x18001bb85  mov     [rsp-18h+arg_10], rsi
0x18001bb8a  push    rbp
0x18001bb8b  push    rdi
0x18001bb8c  push    r14
0x18001bb8e  mov     rbp, rsp
0x18001bb91  sub     rsp, 30h
0x18001bb95  mov     rdi, [rcx+0B0h]
0x18001bb9c  mov     r14, r8
0x18001bb9f  mov     rsi, rdx
0x18001bba2  mov     rbx, rcx
0x18001bba5  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001bbaa  mov     rcx, [rdi+58h]
0x18001bbae  mov     rdx, rax
0x18001bbb1  mov     r8, [rdi+60h]
0x18001bbb5  mov     [rbp+var_10], rax
0x18001bbb9  mov     eax, [rdi+68h]
0x18001bbbc  mov     [rdx+8], rcx
0x18001bbc0  mov     [rdx+10h], r8
0x18001bbc4  test    rcx, rcx
0x18001bbc7  jz      short loc_18001BBCF
0x18001bbc9  mov     ecx, [rcx+10h]
0x18001bbcc  sub     ecx, 18h
0x18001bbcf  mov     [rdx+24h], eax
0x18001bbd2  mov     [rdx+20h], ecx
0x18001bbd5  mov     rax, gs:30h
0x18001bbde  mov     rcx, [rax+1758h]
0x18001bbe5  mov     [rcx], r8
0x18001bbe8  mov     rax, [rdx+18h]
0x18001bbec  mov     [rbp+var_8], rax
0x18001bbf0  mov     [rdx+18h], rdi
0x18001bbf4  test    r14, r14
0x18001bbf7  jnz     short loc_18001BC63
0x18001bbf9  mov     edi, 80030009h
0x18001bbfe  jmp     short loc_18001BC45
0x18001bc00  mov     rax, [rsi]
0x18001bc03  sub     rax, qword ptr cs:_GUID_20011801_5de6_11d1_8e38_00c04fb9386d.Data1
0x18001bc0a  jnz     short loc_18001BC17
0x18001bc0c  mov     rax, [rsi+8]
0x18001bc10  sub     rax, qword ptr cs:_GUID_20011801_5de6_11d1_8e38_00c04fb9386d.Data4
0x18001bc17  test    rax, rax
0x18001bc1a  jz      loc_18001BE8D
0x18001bc20  mov     rax, [rsi]
0x18001bc23  sub     rax, qword ptr cs:IID_IPropertyBag.Data1
0x18001bc2a  jnz     short loc_18001BC37
0x18001bc2c  mov     rax, [rsi+8]
0x18001bc30  sub     rax, qword ptr cs:IID_IPropertyBag.Data4
0x18001bc37  test    rax, rax
0x18001bc3a  jz      loc_18001BE96
0x18001bc40  mov     edi, 80004002h
0x18001bc45  lea     rcx, [rbp+var_10]; this
0x18001bc49  call    ??1CSafeMultiHeap@@QEAA@XZ; CSafeMultiHeap::~CSafeMultiHeap(void)
0x18001bc4e  mov     rbx, [rsp+30h+arg_8]
0x18001bc53  mov     eax, edi
0x18001bc55  mov     rsi, [rsp+30h+arg_10]
0x18001bc5a  add     rsp, 30h
0x18001bc5e  pop     r14
0x18001bc60  pop     rdi
0x18001bc61  pop     rbp
0x18001bc62  retn
0x18001bc63  mov     rcx, rbx; this
0x18001bc66  mov     qword ptr [r14], 0
0x18001bc6d  call    ?Validate@CExposedDocFile@@QEBAJXZ; CExposedDocFile::Validate(void)
0x18001bc72  mov     edi, eax
0x18001bc74  test    eax, eax
0x18001bc76  js      short loc_18001BC45
0x18001bc78  mov     rcx, [rbx+0A0h]; this
0x18001bc7f  test    byte ptr [rcx+14h], 20h
0x18001bc83  jnz     loc_18001BF55
0x18001bc89  mov     rax, [rsi]
0x18001bc8c  xor     edi, edi
0x18001bc8e  sub     rax, qword ptr cs:IID_IStorage.Data1
0x18001bc95  jnz     short loc_18001BCA2
0x18001bc97  mov     rax, [rsi+8]
0x18001bc9b  sub     rax, qword ptr cs:IID_IStorage.Data4
0x18001bca2  test    rax, rax
0x18001bca5  jz      loc_18001BDC6
0x18001bcab  mov     rax, [rsi]
0x18001bcae  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18001bcb5  jnz     short loc_18001BCC2
0x18001bcb7  mov     rax, [rsi+8]
0x18001bcbb  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18001bcc2  test    rax, rax
0x18001bcc5  jz      loc_18001BDC6
0x18001bccb  mov     rax, [rsi]
0x18001bcce  sub     rax, qword ptr cs:IID_IMarshal.Data1
0x18001bcd5  jnz     short loc_18001BCE2
0x18001bcd7  mov     rax, [rsi+8]
0x18001bcdb  sub     rax, qword ptr cs:IID_IMarshal.Data4
0x18001bce2  test    rax, rax
0x18001bce5  jz      loc_18001BEB2
0x18001bceb  mov     rax, [rsi]
0x18001bcee  sub     rax, qword ptr cs:IID_IAgileObject.Data1
0x18001bcf5  jnz     short loc_18001BD02
0x18001bcf7  mov     rax, [rsi+8]
0x18001bcfb  sub     rax, qword ptr cs:IID_IAgileObject.Data4
0x18001bd02  test    rax, rax
0x18001bd05  jz      loc_18001BEB2
0x18001bd0b  mov     rax, [rsi]
0x18001bd0e  sub     rax, qword ptr cs:IID_IRootStorage.Data1
0x18001bd15  jnz     short loc_18001BD22
0x18001bd17  mov     rax, [rsi+8]
0x18001bd1b  sub     rax, qword ptr cs:IID_IRootStorage.Data4
0x18001bd22  test    rax, rax
0x18001bd25  jz      loc_18001BE77
0x18001bd2b  mov     rax, [rsi]
0x18001bd2e  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data1
0x18001bd35  jnz     short loc_18001BD42
0x18001bd37  mov     rax, [rsi+8]
0x18001bd3b  sub     rax, qword ptr cs:IID_IPropertySetStorage.Data4
0x18001bd42  test    rax, rax
0x18001bd45  jz      short loc_18001BDC0
0x18001bd47  mov     rax, [rsi]
0x18001bd4a  sub     rax, qword ptr cs:IID_IConnectionPointContainer.Data1
0x18001bd51  jnz     short loc_18001BD5E
0x18001bd53  mov     rax, [rsi+8]
0x18001bd57  sub     rax, qword ptr cs:IID_IConnectionPointContainer.Data4
0x18001bd5e  test    rax, rax
0x18001bd61  jz      short loc_18001BDCB
0x18001bd63  call    ?IsRoot@CPubDocFile@@QEBAHXZ; CPubDocFile::IsRoot(void)
0x18001bd68  test    eax, eax
0x18001bd6a  jz      loc_18001BC00
0x18001bd70  mov     rax, [rsi]
0x18001bd73  sub     rax, qword ptr cs:IID_IDirectWriterLock.Data1
0x18001bd7a  jnz     short loc_18001BD87
0x18001bd7c  mov     rax, [rsi+8]
0x18001bd80  sub     rax, qword ptr cs:IID_IDirectWriterLock.Data4
0x18001bd87  test    rax, rax
0x18001bd8a  jnz     loc_18001BC00
0x18001bd90  mov     rax, [rbx+0A8h]
0x18001bd97  cmp     [rax+78h], edi
0x18001bd9a  jz      loc_18001BC00
0x18001bda0  lea     rdx, [rbx+48h]
0x18001bda4  mov     rax, rbx
0x18001bda7  neg     rax
0x18001bdaa  sbb     rcx, rcx
0x18001bdad  and     rcx, rdx
0x18001bdb0  mov     [r14], rcx
0x18001bdb3  mov     rcx, rbx; this
0x18001bdb6  call    ?AddRef@CExposedDocFile@@UEAAKXZ; CExposedDocFile::AddRef(void)
0x18001bdbb  jmp     loc_18001BC45
0x18001bdc0  lea     rdx, [rbx+8]
0x18001bdc4  jmp     short loc_18001BDA4
0x18001bdc6  mov     [r14], rbx
0x18001bdc9  jmp     short loc_18001BDB3
0x18001bdcb  cmp     [rbx+68h], rdi
0x18001bdcf  jz      short loc_18001BD63
0x18001bdd1  lea     rdx, [rbx+50h]
0x18001bdd5  jmp     short loc_18001BDA4
0x18001bdd7  mov     rax, [rsi]
0x18001bdda  sub     rax, qword ptr cs:IID_IMarshal.Data1
0x18001bde1  jnz     short loc_18001BDEE
0x18001bde3  mov     rax, [rsi+8]
0x18001bde7  sub     rax, qword ptr cs:IID_IMarshal.Data4
0x18001bdee  test    rax, rax
0x18001bdf1  jnz     loc_18001BC40
0x18001bdf7  mov     rcx, [rbx+0A0h]; this
0x18001bdfe  test    dword ptr [rcx+14h], 400h
0x18001be05  jz      short loc_18001BE14
0x18001be07  call    ?IsRoot@CPubDocFile@@QEBAHXZ; CPubDocFile::IsRoot(void)
0x18001be0c  test    eax, eax
0x18001be0e  jnz     loc_18001BC40
0x18001be14  mov     rax, [rbx+0B0h]
0x18001be1b  mov     [rbp+ppunkMarshal], rdi
0x18001be1f  mov     rcx, [rax+20h]
0x18001be23  test    rcx, rcx
0x18001be26  jnz     short loc_18001BE2C
0x18001be28  mov     rcx, [rax+10h]
0x18001be2c  mov     rax, [rcx]
0x18001be2f  lea     r8, [rbp+ppunkMarshal]
0x18001be33  lea     rdx, IID_IDfReserved1
0x18001be3a  mov     rax, [rax]
0x18001be3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be42  mov     edi, eax
0x18001be44  test    eax, eax
0x18001be46  js      loc_18001BC40
0x18001be4c  mov     rcx, [rbp+ppunkMarshal]
0x18001be50  mov     rax, [rcx]
0x18001be53  mov     rax, [rax+10h]
0x18001be57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be5c  mov     rax, [rbx+0B0h]
0x18001be63  cmp     qword ptr [rax+60h], 0
0x18001be68  jz      loc_18001BC40
0x18001be6e  lea     rdx, [rbx+38h]
0x18001be72  jmp     loc_18001BDA4
0x18001be77  call    ?IsRoot@CPubDocFile@@QEBAHXZ; CPubDocFile::IsRoot(void)
0x18001be7c  test    eax, eax
0x18001be7e  jz      loc_18001BC40
0x18001be84  lea     rdx, [rbx+30h]
0x18001be88  jmp     loc_18001BDA4
0x18001be8d  lea     rax, [rbx+0C0h]
0x18001be94  jmp     short loc_18001BEAA
0x18001be96  lea     rax, [rbx+0C0h]
0x18001be9d  lea     rcx, [rax+8]
0x18001bea1  neg     rax
0x18001bea4  sbb     rax, rax
0x18001bea7  and     rax, rcx
0x18001beaa  mov     [r14], rax
0x18001bead  jmp     loc_18001BDB3
0x18001beb2  call    ?IsSharedMemoryModeDisabledForCurrentProcess@@YA_NXZ; IsSharedMemoryModeDisabledForCurrentProcess(void)
0x18001beb7  test    al, al
0x18001beb9  jz      loc_18001BDD7
0x18001bebf  mov     rax, [rbx+0F8h]
0x18001bec6  test    rax, rax
0x18001bec9  jnz     short loc_18001BF36
0x18001becb  lea     rdx, [rbp+ppunkMarshal]; ppunkMarshal
0x18001becf  mov     [rbp+ppunkMarshal], rdi
0x18001bed3  mov     rcx, rbx; punkOuter
0x18001bed6  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001bedc  mov     rcx, [rbp+ppunkMarshal]
0x18001bee0  mov     edi, eax
0x18001bee2  test    eax, eax
0x18001bee4  jns     short loc_18001BF08
0x18001bee6  test    rcx, rcx
0x18001bee9  jz      loc_18001BC45
0x18001beef  mov     [rbp+ppunkMarshal], 0
0x18001bef7  mov     rax, [rcx]
0x18001befa  mov     rax, [rax+10h]
0x18001befe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf03  jmp     loc_18001BC45
0x18001bf08  xor     eax, eax
0x18001bf0a  lock cmpxchg [rbx+0F8h], rcx
0x18001bf13  jnz     short loc_18001BF19
0x18001bf15  xor     ecx, ecx
0x18001bf17  jmp     short loc_18001BF1D
0x18001bf19  mov     rcx, [rbp+ppunkMarshal]
0x18001bf1d  test    rcx, rcx
0x18001bf20  jz      short loc_18001BF36
0x18001bf22  mov     [rbp+ppunkMarshal], 0
0x18001bf2a  mov     rax, [rcx]
0x18001bf2d  mov     rax, [rax+10h]
0x18001bf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf36  mov     rcx, [rbx+0F8h]
0x18001bf3d  mov     r8, r14
0x18001bf40  mov     rdx, rsi
0x18001bf43  mov     rax, [rcx]
0x18001bf46  mov     rax, [rax]
0x18001bf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf4e  mov     edi, eax
0x18001bf50  jmp     loc_18001BC45
0x18001bf55  mov     edi, 80030102h
0x18001bf5a  jmp     loc_18001BC45
```
