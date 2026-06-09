# CRTFObject::InitWrite(_reobject &,COleObject *)

- ea: `0x18015a674`
- end: `0x18015aa30`
- name: `?InitWrite@CRTFObject@@AEAAHAEAU_reobject@@PEAVCOleObject@@@Z`
- size: `956`
- prototype: `__int64 __fastcall(CRTFObject *__hidden this, struct _reobject *, struct COleObject *)`
- caller_count: `3`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18015b7ac`
- `0x1801814b0`
- `0x1801a1ce0`

## callees

- `0x18000f430`
- `0x18008a47c`
- `0x18008a518`
- `0x18009abd0`
- `0x180129838`
- `0x18013dce6`
- `0x180148f24`
- `0x18014d65c`
- `0x180151664`
- `0x180151ce8`
- `0x180159cd4`
- `0x180159ee8`
- `0x18015a674`
- `0x1801a8de4`
- `0x1801a8ec4`
- `0x1801aa110`
- `0x1801aa444`
- `0x1801aa4a0`
- `0x1801ab7d0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015a9e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015a9e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015a9bd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015a9bd`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x18015a9d7`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x18015a9d7`

## pseudocode

```c
__int64 __fastcall CRTFObject::InitWrite(CRTFObject *this, struct _reobject *a2, CTxtEdit **a3)
{
  BOOL v6; // ebx
  DWORD v7; // edx
  __int64 v8; // rax
  _WORD *v9; // rsi
  BOOL v10; // r13d
  int IsSimplePersistBlob; // ebx
  CTextMarkContainer *v12; // rcx
  struct CImage *Image; // rax
  bool v14; // zf
  unsigned int EnhMetafilePict; // r15d
  CTextMarkContainer *v16; // rcx
  void *MetafilePictFromBlob; // rbx
  struct ITextBlob::BLOB_PROPERTIES *BlobProperties; // rax
  struct ITextBlob::BLOB_PROPERTIES *v19; // rsi
  CTextMarkContainer *v20; // rcx
  __int16 v21; // ax
  int v22; // ecx
  int v23; // r11d
  int v24; // ecx
  int v25; // eax
  LONG cy; // ecx
  unsigned int v27; // r11d
  LPVOID v29; // rax
  HMETAFILE v30; // rcx
  struct tagPOINT **v31; // [rsp+20h] [rbp-40h]
  struct tagSIZE sizel; // [rsp+30h] [rbp-30h] BYREF
  struct tagPOINT *v33; // [rsp+38h] [rbp-28h] BYREF
  int v34[4]; // [rsp+40h] [rbp-20h] BYREF
  int v35; // [rsp+50h] [rbp-10h]
  int v36; // [rsp+A0h] [rbp+40h]
  CTextBlobSurrogate *v37; // [rsp+A8h] [rbp+48h] BYREF
  DWORD v38; // [rsp+B8h] [rbp+58h]

  memset_0(a2, 0, sizeof(struct _reobject));
  a2->cbStruct = 72;
  COleObject::GetObjectData((COleObject *)a3, a2, 7u);
  memset_0(this, 0, 0x78u);
  v6 = a2->pstg != 0;
  v7 = a2->dwFlags & 0x40000000;
  v8 = *(_QWORD *)&a2->clsid.Data1 - *(_QWORD *)&CLSID_Picture_EnhMetafile.Data1;
  v36 = 1;
  v38 = v7;
  if ( !v8 )
    v8 = *(_QWORD *)a2->clsid.Data4 - *(_QWORD *)CLSID_Picture_EnhMetafile.Data4;
  v9 = (_WORD *)a3 + 77;
  v10 = v8 == 0;
  *(_WORD *)this = 8 * v10 + 1;
  if ( !v7 )
  {
    sizel = 0;
    if ( (*v9 & 0x1000) != 0 )
    {
      *(_WORD *)this = 8;
      if ( CTxtEdit::GetTextMarkContainer(a3[6]) )
      {
        CTextBlobSurrogatePointer::CTextBlobSurrogatePointer(
          (CTextBlobSurrogatePointer *)&v37,
          (const struct COleObject *)a3);
        IsSimplePersistBlob = CTextBlobSurrogate::IsSimplePersistBlob(v37);
        CTextBlobSurrogatePointer::~CTextBlobSurrogatePointer((CTextBlobSurrogatePointer *)&v37);
        if ( IsSimplePersistBlob )
        {
          Image = CTextMarkContainer::GetImage(v12, (const struct COleObject *)a3);
          v37 = Image;
          if ( Image )
          {
            *(_OWORD *)((char *)this + 52) = *((_OWORD *)Image + 11);
            *((_BYTE *)this + 10) = *((_BYTE *)Image + 200) & 3;
            *((_BYTE *)this + 12) = (*((_BYTE *)Image + 200) & 4) != 0;
            *((_BYTE *)this + 13) = (*((_BYTE *)Image + 200) & 8) != 0;
            *((_DWORD *)this + 4) = *((_DWORD *)Image + 51);
          }
          *(_WORD *)this = 12;
          Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v37);
        }
      }
      v6 = 1;
    }
    else if ( !(unsigned int)CW32System::ProgIDFromCLSID(&a2->clsid, (unsigned __int16 **)&sizel) )
    {
      *((struct tagSIZE *)this + 9) = sizel;
      *(_WORD *)this = 5;
      v36 = 0;
      goto LABEL_13;
    }
    if ( (*v9 & 0x1000) == 0 )
      *(_WORD *)this = 1;
  }
LABEL_13:
  *((_DWORD *)this + 12) = a2->dwFlags;
  if ( !v6 )
    return 0;
  v14 = a2->poleobj == 0;
  EnhMetafilePict = 1;
  sizel = a2->sizel;
  if ( v14 )
    goto LABEL_30;
  if ( (*v9 & 0x1000) != 0 )
  {
    if ( !CTxtEdit::GetTextMarkContainer(a3[6]) )
      goto LABEL_30;
    MetafilePictFromBlob = 0;
    BlobProperties = CTextMarkContainer::GetBlobProperties(v16, (const struct COleObject *)a3);
    v19 = BlobProperties;
    if ( BlobProperties )
    {
      if ( (*((_DWORD *)BlobProperties + 7) & 0x18) == 8 )
        MetafilePictFromBlob = GetMetafilePictFromBlob(a3, &sizel);
      if ( *((_DWORD *)v19 + 8) )
        *((_DWORD *)this + 7) = *((_DWORD *)v19 + 2) - *((_DWORD *)v19 + 8);
    }
    if ( (unsigned int)COleObject::FWrapTextAround((COleObject *)a3) )
    {
      LODWORD(v37) = 0;
      v35 = 0;
      v33 = 0;
      *(_OWORD *)v34 = 0;
      CTextMarkContainer::GetMultiLineBlobInfo(
        v20,
        (const struct COleObject *)a3,
        (unsigned int *)&v37,
        (struct ITextMarkContainer::MLBLOB_CREATE_DATA *)v34,
        (const struct tagPOINT **)&v33);
      v21 = CW32System::MulDivFunc(v34[3], 72, 127);
      v22 = v35;
      *((_WORD *)this + 22) = v21;
      *((_WORD *)this + 23) = CW32System::MulDivFunc(v22, v23 - 55, v23);
    }
  }
  else
  {
    v24 = *((_DWORD *)a3 + 24);
    *((_WORD *)this + 22) = *((_WORD *)a3 + 46);
    *((_WORD *)this + 23) = v24;
    MetafilePictFromBlob = OleStdGetMetafilePictFromOleObject(
                             a2->poleobj,
                             v10,
                             a2->dvaspect,
                             &sizel,
                             (struct tagDVTARGETDEVICE *)v31,
                             0);
  }
  if ( MetafilePictFromBlob )
  {
    if ( v10 )
    {
      EnhMetafilePict = CRTFObject::GetEnhMetafilePict(this, MetafilePictFromBlob, &sizel, 0, 0);
      goto LABEL_30;
    }
    EnhMetafilePict = CRTFObject::GetMetafilePict(this, MetafilePictFromBlob, &sizel);
    v29 = GlobalLock(MetafilePictFromBlob);
    if ( v29 )
    {
      v30 = (HMETAFILE)*((_QWORD *)v29 + 2);
      if ( v30 )
        DeleteMetaFile(v30);
      GlobalUnlock(MetafilePictFromBlob);
    }
    CW32System::GlobalFree(MetafilePictFromBlob);
    if ( EnhMetafilePict || !v36 )
      goto LABEL_30;
    return 0;
  }
LABEL_30:
  if ( !v38 )
  {
    v25 = CW32System::MulDivFunc(sizel.cx, 72, 127);
    cy = sizel.cy;
    *((_DWORD *)this + 5) = v25;
    *((_DWORD *)this + 6) = CW32System::MulDivFunc(cy, 72, 127);
    EnhMetafilePict = v27;
  }
  *((_BYTE *)this + 14) = 0;
  return EnhMetafilePict;
}

```

## disassembly

```asm
0x18015a674  mov     [rsp-38h+arg_10], rbx
0x18015a679  push    rbp
0x18015a67a  push    rsi
0x18015a67b  push    rdi
0x18015a67c  push    r12
0x18015a67e  push    r13
0x18015a680  push    r14
0x18015a682  push    r15
0x18015a684  mov     rbp, rsp
0x18015a687  sub     rsp, 60h
0x18015a68b  mov     r12, rdx
0x18015a68e  mov     r14, r8
0x18015a691  mov     rdi, rcx
0x18015a694  mov     ebx, 48h ; 'H'
0x18015a699  mov     r8d, ebx; Size
0x18015a69c  mov     rcx, r12; void *
0x18015a69f  xor     edx, edx; Val
0x18015a6a1  call    memset_0
0x18015a6a6  lea     r8d, [rbx-41h]; unsigned int
0x18015a6aa  mov     [r12], ebx
0x18015a6ae  mov     rdx, r12; struct _reobject *
0x18015a6b1  mov     rcx, r14; this
0x18015a6b4  call    ?GetObjectData@COleObject@@QEAAJPEAU_reobject@@K@Z; COleObject::GetObjectData(_reobject *,ulong)
0x18015a6b9  xor     edx, edx; Val
0x18015a6bb  lea     r8d, [rbx+30h]; Size
0x18015a6bf  mov     rcx, rdi; void *
0x18015a6c2  call    memset_0
0x18015a6c7  mov     edx, [r12+3Ch]
0x18015a6cc  lea     rcx, [r12+8]; struct _GUID *
0x18015a6d1  mov     rax, [rcx]
0x18015a6d4  xor     r15d, r15d
0x18015a6d7  cmp     [r12+20h], r15
0x18015a6dc  mov     ebx, r15d
0x18015a6df  setnz   bl
0x18015a6e2  and     edx, 40000000h
0x18015a6e8  sub     rax, qword ptr cs:CLSID_Picture_EnhMetafile.Data1
0x18015a6ef  lea     r11d, [r15+1]
0x18015a6f3  mov     [rbp+arg_0], r11d
0x18015a6f7  mov     [rbp+arg_18], edx
0x18015a6fa  jnz     short loc_18015A707
0x18015a6fc  mov     rax, [rcx+8]
0x18015a700  sub     rax, qword ptr cs:CLSID_Picture_EnhMetafile.Data4
0x18015a707  test    rax, rax
0x18015a70a  lea     rsi, [r14+9Ah]
0x18015a711  mov     r13d, r15d
0x18015a714  mov     r8d, 1000h
0x18015a71a  setz    r13b
0x18015a71e  movzx   eax, r13w
0x18015a722  shl     ax, 3
0x18015a726  add     ax, r11w
0x18015a72a  mov     [rdi], ax
0x18015a72d  test    edx, edx
0x18015a72f  jnz     loc_18015A7F7
0x18015a735  mov     qword ptr [rbp+var_30.cx], r15
0x18015a739  test    [rsi], r8w
0x18015a73d  jz      loc_18015A8E5
0x18015a743  mov     word ptr [rdi], 8
0x18015a748  mov     rcx, [r14+30h]; this
0x18015a74c  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x18015a751  test    rax, rax
0x18015a754  jz      loc_18015A7DE
0x18015a75a  mov     rdx, r14; struct COleObject *
0x18015a75d  lea     rcx, [rbp+arg_8]; this
0x18015a761  call    ??0CTextBlobSurrogatePointer@@QEAA@AEBVCOleObject@@@Z; CTextBlobSurrogatePointer::CTextBlobSurrogatePointer(COleObject const &)
0x18015a766  mov     rcx, [rbp+arg_8]; this
0x18015a76a  call    ?IsSimplePersistBlob@CTextBlobSurrogate@@QEBAHXZ; CTextBlobSurrogate::IsSimplePersistBlob(void)
0x18015a76f  lea     rcx, [rbp+arg_8]; this
0x18015a773  mov     ebx, eax
0x18015a775  call    ??1CTextBlobSurrogatePointer@@QEAA@XZ; CTextBlobSurrogatePointer::~CTextBlobSurrogatePointer(void)
0x18015a77a  test    ebx, ebx
0x18015a77c  jz      short loc_18015A7DE
0x18015a77e  mov     rdx, r14; struct COleObject *
0x18015a781  call    ?GetImage@CTextMarkContainer@@QEAAPEAVCImage@@AEBVCOleObject@@@Z; CTextMarkContainer::GetImage(COleObject const &)
0x18015a786  mov     [rbp+arg_8], rax
0x18015a78a  mov     rdx, rax
0x18015a78d  test    rax, rax
0x18015a790  jz      short loc_18015A7D0
0x18015a792  movups  xmm0, xmmword ptr [rax+0B0h]
0x18015a799  movdqu  xmmword ptr [rdi+34h], xmm0
0x18015a79e  mov     cl, [rax+0C8h]
0x18015a7a4  and     cl, 3
0x18015a7a7  mov     [rdi+0Ah], cl
0x18015a7aa  mov     cl, [rax+0C8h]
0x18015a7b0  shr     cl, 2
0x18015a7b3  and     cl, 1
0x18015a7b6  mov     [rdi+0Ch], cl
0x18015a7b9  mov     al, [rax+0C8h]
0x18015a7bf  shr     al, 3
0x18015a7c2  and     al, 1
0x18015a7c4  mov     [rdi+0Dh], al
0x18015a7c7  mov     eax, [rdx+0CCh]
0x18015a7cd  mov     [rdi+10h], eax
0x18015a7d0  lea     rcx, [rbp+arg_8]; void *
0x18015a7d4  mov     word ptr [rdi], 0Ch
0x18015a7d9  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x18015a7de  mov     r11d, 1
0x18015a7e4  mov     ebx, r11d
0x18015a7e7  mov     r8d, 1000h
0x18015a7ed  test    [rsi], r8w
0x18015a7f1  jnz     short loc_18015A7F7
0x18015a7f3  mov     [rdi], r11w
0x18015a7f7  mov     eax, [r12+3Ch]
0x18015a7fc  mov     [rdi+30h], eax
0x18015a7ff  test    ebx, ebx
0x18015a801  jz      loc_18015AA0D
0x18015a807  cmp     qword ptr [r12+18h], 0
0x18015a80d  mov     r15d, r11d
0x18015a810  mov     rax, [r12+30h]
0x18015a815  mov     qword ptr [rbp+var_30.cx], rax
0x18015a819  jz      loc_18015AA28
0x18015a81f  test    [rsi], r8w
0x18015a823  jz      loc_18015A918
0x18015a829  mov     rcx, [r14+30h]; this
0x18015a82d  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x18015a832  xor     r12d, r12d
0x18015a835  test    rax, rax
0x18015a838  jz      loc_18015A972
0x18015a83e  mov     rdx, r14; struct COleObject *
0x18015a841  mov     ebx, r12d
0x18015a844  call    ?GetBlobProperties@CTextMarkContainer@@QEAAPEAUBLOB_PROPERTIES@ITextBlob@@AEBVCOleObject@@@Z; CTextMarkContainer::GetBlobProperties(COleObject const &)
0x18015a849  mov     rsi, rax
0x18015a84c  test    rax, rax
0x18015a84f  jz      short loc_18015A87A
0x18015a851  mov     ecx, [rax+1Ch]
0x18015a854  and     cl, 18h
0x18015a857  cmp     cl, 8
0x18015a85a  jnz     short loc_18015A86B
0x18015a85c  lea     rdx, [rbp+var_30]; struct tagSIZE *
0x18015a860  mov     rcx, r14; struct COleObject *
0x18015a863  call    ?GetMetafilePictFromBlob@@YAPEAXPEAVCOleObject@@PEAUtagSIZE@@@Z; GetMetafilePictFromBlob(COleObject *,tagSIZE *)
0x18015a868  mov     rbx, rax
0x18015a86b  cmp     [rsi+20h], r12d
0x18015a86f  jz      short loc_18015A87A
0x18015a871  mov     ecx, [rsi+8]
0x18015a874  sub     ecx, [rsi+20h]
0x18015a877  mov     [rdi+1Ch], ecx
0x18015a87a  mov     rcx, r14; this
0x18015a87d  call    ?FWrapTextAround@COleObject@@QEBAHXZ; COleObject::FWrapTextAround(void)
0x18015a882  test    eax, eax
0x18015a884  jz      loc_18015A94E
0x18015a88a  xor     eax, eax
0x18015a88c  mov     dword ptr [rbp+arg_8], r12d
0x18015a890  mov     [rbp+var_10], eax
0x18015a893  lea     r9, [rbp+var_20]; struct ITextMarkContainer::MLBLOB_CREATE_DATA *
0x18015a897  lea     rax, [rbp+var_28]
0x18015a89b  mov     [rbp+var_28], r12
0x18015a89f  xorps   xmm0, xmm0
0x18015a8a2  mov     [rsp+60h+var_40], rax; struct tagPOINT **
0x18015a8a7  lea     r8, [rbp+arg_8]; unsigned int *
0x18015a8ab  mov     rdx, r14; struct COleObject *
0x18015a8ae  movups  xmmword ptr [rbp+var_20], xmm0
0x18015a8b2  call    ?GetMultiLineBlobInfo@CTextMarkContainer@@QEAAHAEBVCOleObject@@AEAKAEAUMLBLOB_CREATE_DATA@ITextMarkContainer@@AEAPEBUtagPOINT@@@Z; CTextMarkContainer::GetMultiLineBlobInfo(COleObject const &,ulong &,ITextMarkContainer::MLBLOB_CREATE_DATA &,tagPOINT const * &)
0x18015a8b7  mov     ecx, [rbp+var_20+0Ch]; int
0x18015a8ba  mov     r11d, 7Fh
0x18015a8c0  mov     r8d, r11d; int
0x18015a8c3  lea     edx, [r11-37h]; int
0x18015a8c7  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a8cc  mov     ecx, [rbp+var_10]; int
0x18015a8cf  lea     edx, [r11-37h]; int
0x18015a8d3  mov     r8d, r11d; int
0x18015a8d6  mov     [rdi+2Ch], ax
0x18015a8da  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a8df  mov     [rdi+2Eh], ax
0x18015a8e3  jmp     short loc_18015A94E
0x18015a8e5  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18015a8e9  call    ?ProgIDFromCLSID@CW32System@@SAJAEBU_GUID@@PEAPEAG@Z; CW32System::ProgIDFromCLSID(_GUID const &,ushort * *)
0x18015a8ee  mov     r11d, 1
0x18015a8f4  test    eax, eax
0x18015a8f6  jnz     loc_18015A7E7
0x18015a8fc  mov     rax, qword ptr [rbp+var_30.cx]
0x18015a900  mov     r8d, 1000h
0x18015a906  mov     [rdi+48h], rax
0x18015a90a  mov     word ptr [rdi], 5
0x18015a90f  mov     [rbp+arg_0], r15d
0x18015a913  jmp     loc_18015A7F7
0x18015a918  mov     ecx, [r14+60h]
0x18015a91c  lea     r9, [rbp+var_30]; struct tagSIZE *
0x18015a920  movzx   eax, word ptr [r14+5Ch]
0x18015a925  mov     edx, r13d; int
0x18015a928  mov     [rdi+2Ch], ax
0x18015a92c  mov     [rdi+2Eh], cx
0x18015a930  mov     r8d, [r12+38h]; unsigned int
0x18015a935  mov     rcx, [r12+18h]; struct IOleObject *
0x18015a93a  mov     [rsp+60h+hdcRef], 0; hdcRef
0x18015a943  call    ?OleStdGetMetafilePictFromOleObject@@YAPEAXPEAUIOleObject@@HKPEAUtagSIZE@@PEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; OleStdGetMetafilePictFromOleObject(IOleObject *,int,ulong,tagSIZE *,tagDVTARGETDEVICE *,HDC__ *)
0x18015a948  mov     rbx, rax
0x18015a94b  xor     r12d, r12d
0x18015a94e  test    rbx, rbx
0x18015a951  jz      short loc_18015A972
0x18015a953  lea     r8, [rbp+var_30]; struct tagSIZE *
0x18015a957  mov     rdx, rbx; void *
0x18015a95a  mov     rcx, rdi; this
0x18015a95d  test    r13d, r13d
0x18015a960  jz      short loc_18015A9B2
0x18015a962  xor     r9d, r9d; int
0x18015a965  mov     [rsp+60h+var_40], r12; struct CTxtEdit *
0x18015a96a  call    ?GetEnhMetafilePict@CRTFObject@@AEAAHPEAXAEBUtagSIZE@@HPEAVCTxtEdit@@@Z; CRTFObject::GetEnhMetafilePict(void *,tagSIZE const &,int,CTxtEdit *)
0x18015a96f  mov     r15d, eax
0x18015a972  mov     r11d, 1
0x18015a978  cmp     [rbp+arg_18], r12d
0x18015a97c  jnz     short loc_18015A9A9
0x18015a97e  mov     ecx, [rbp+var_30.cx]; int
0x18015a981  mov     edx, 48h ; 'H'; int
0x18015a986  lea     r8d, [rdx+37h]; int
0x18015a98a  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a98f  mov     ecx, [rbp+var_30.cy]; int
0x18015a992  mov     edx, 48h ; 'H'; int
0x18015a997  mov     [rdi+14h], eax
0x18015a99a  lea     r8d, [rdx+37h]; int
0x18015a99e  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a9a3  mov     [rdi+18h], eax
0x18015a9a6  mov     r15d, r11d
0x18015a9a9  mov     [rdi+0Eh], r12b
0x18015a9ad  mov     eax, r15d
0x18015a9b0  jmp     short loc_18015AA0F
0x18015a9b2  call    ?GetMetafilePict@CRTFObject@@AEAAHPEAXAEBUtagSIZE@@@Z; CRTFObject::GetMetafilePict(void *,tagSIZE const &)
0x18015a9b7  mov     rcx, rbx; hMem
0x18015a9ba  mov     r15d, eax
0x18015a9bd  call    cs:__imp_GlobalLock
0x18015a9c4  nop     dword ptr [rax+rax+00h]
0x18015a9c9  test    rax, rax
0x18015a9cc  jz      short loc_18015A9F2
0x18015a9ce  mov     rcx, [rax+10h]; hmf
0x18015a9d2  test    rcx, rcx
0x18015a9d5  jz      short loc_18015A9E3
0x18015a9d7  call    cs:__imp_DeleteMetaFile
0x18015a9de  nop     dword ptr [rax+rax+00h]
0x18015a9e3  mov     rcx, rbx; hMem
0x18015a9e6  call    cs:__imp_GlobalUnlock
0x18015a9ed  nop     dword ptr [rax+rax+00h]
0x18015a9f2  mov     rcx, rbx; void *
0x18015a9f5  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18015a9fa  test    r15d, r15d
0x18015a9fd  jnz     loc_18015A972
0x18015aa03  cmp     [rbp+arg_0], r12d
0x18015aa07  jz      loc_18015A972
0x18015aa0d  xor     eax, eax
0x18015aa0f  mov     rbx, [rsp+60h+arg_10]
0x18015aa17  add     rsp, 60h
0x18015aa1b  pop     r15
0x18015aa1d  pop     r14
0x18015aa1f  pop     r13
0x18015aa21  pop     r12
0x18015aa23  pop     rdi
0x18015aa24  pop     rsi
0x18015aa25  pop     rbp
0x18015aa26  retn
0x18015aa28  xor     r12d, r12d
0x18015aa2b  jmp     loc_18015A978
```
