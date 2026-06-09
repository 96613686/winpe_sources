# DetailsView::Importer::Import(IDataObject *)

- ea: `0x18000be38`
- end: `0x18000c013`
- name: `?Import@Importer@DetailsView@@QEAAJPEAUIDataObject@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(DetailsView::Importer *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a820`

## callees

- `0x180007614`
- `0x180007ae4`
- `0x18000b52c`
- `0x18000bd88`
- `0x18000be38`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000bf17`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000bf17`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18000bfc4`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18000bfc4`
- `ole32!ReleaseStgMedium` at `0x18000bff3`
- `ole32!ReleaseStgMedium` at `0x18000bff3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DetailsView::Importer::Import(DetailsView::Importer *this, struct IDataObject *a2)
{
  int v4; // edi
  HRESULT HGlobalFromStream; // ebx
  _WORD v7[2]; // [rsp+30h] [rbp-19h] BYREF
  int v8; // [rsp+34h] [rbp-15h]
  unsigned __int16 v9; // [rsp+38h] [rbp-11h]
  int v10; // [rsp+3Ch] [rbp-Dh]
  __int16 v11; // [rsp+40h] [rbp-9h]
  int v12; // [rsp+44h] [rbp-5h]
  __int16 v13; // [rsp+48h] [rbp-1h]
  int v14; // [rsp+4Ch] [rbp+3h]
  STGMEDIUM v15; // [rsp+50h] [rbp+7h] BYREF
  __int16 v16; // [rsp+68h] [rbp+1Fh] BYREF
  int v17; // [rsp+6Ah] [rbp+21h]
  __int16 v18; // [rsp+6Eh] [rbp+25h]
  __int64 v19; // [rsp+70h] [rbp+27h]
  int v20; // [rsp+78h] [rbp+2Fh]
  int v21; // [rsp+7Ch] [rbp+33h]
  int v22; // [rsp+80h] [rbp+37h]
  int v23; // [rsp+84h] [rbp+3Bh]
  LPSTREAM ppstm; // [rsp+C0h] [rbp+77h] BYREF
  HGLOBAL phglobal; // [rsp+C8h] [rbp+7Fh] BYREF

  v17 = 0;
  v18 = 0;
  v23 = 0;
  v15.tymed = 0;
  *(_OWORD *)&v15.hBitmap = 0;
  v7[0] = DetailsView::DataObject::m_CF_NtDiskQuotaExport;
  v8 = 4;
  v9 = DetailsView::DataObject::m_CF_NtDiskQuotaExport;
  v10 = 1;
  v11 = 15;
  v12 = 4;
  v13 = 15;
  v14 = 1;
  v4 = 0;
  while ( 1 )
  {
    v16 = v7[4 * v4];
    v20 = 1;
    v19 = 0;
    v22 = *(&v8 + 2 * v4);
    v21 = -1;
    HGlobalFromStream = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, STGMEDIUM *))a2->lpVtbl->GetData)(
                          a2,
                          &v16,
                          &v15);
    if ( HGlobalFromStream >= 0 )
      break;
    if ( (unsigned int)++v4 >= 4 )
      goto LABEL_17;
  }
  ppstm = 0;
  if ( v15.tymed == 1 )
  {
    HGlobalFromStream = CreateStreamOnHGlobal(v15.hBitmap, 0, &ppstm);
  }
  else
  {
    HGlobalFromStream = -2147467259;
    if ( v15.tymed != 4 )
      goto LABEL_17;
    ppstm = v15.pstm;
    (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)v15.hBitmap + 8LL))(v15.hBitmap);
    HGlobalFromStream = 0;
  }
  if ( ppstm )
  {
    phglobal = 0;
    HGlobalFromStream = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(
                          ppstm,
                          0,
                          0,
                          0);
    if ( HGlobalFromStream >= 0 )
    {
      if ( DetailsView::DataObject::m_CF_NtDiskQuotaExport == v16 )
      {
        DetailsView::Importer::Source::Source((DetailsView::Importer::Source *)v7, ppstm);
        DetailsView::Importer::Import(this, (struct DetailsView::Importer::Source *)v7);
        DetailsView::Importer::Source::~Source((DetailsView::Importer::Source *)v7);
      }
      else if ( v16 == 15 )
      {
        phglobal = 0;
        HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
        if ( HGlobalFromStream >= 0 )
          HGlobalFromStream = DetailsView::Importer::Import(this, (HDROP)phglobal);
      }
    }
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  }
LABEL_17:
  ReleaseStgMedium(&v15);
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x18000be38  mov     [rsp-8+arg_0], rbx
0x18000be3d  mov     [rsp-8+arg_8], rsi
0x18000be42  push    rbp
0x18000be43  push    rdi
0x18000be44  push    r14
0x18000be46  lea     rbp, [rsp-47h]
0x18000be4b  sub     rsp, 90h
0x18000be52  mov     r14, rdx
0x18000be55  mov     rsi, rcx
0x18000be58  mov     [rbp+57h+var_36], 0
0x18000be5f  xor     eax, eax
0x18000be61  mov     [rbp+57h+var_32], ax
0x18000be65  mov     [rbp+57h+var_1C], eax
0x18000be68  mov     [rbp+57h+var_50.tymed], eax
0x18000be6b  xorps   xmm0, xmm0
0x18000be6e  movdqu  xmmword ptr [rbp+57h+var_50.8], xmm0
0x18000be73  movzx   eax, cs:?m_CF_NtDiskQuotaExport@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_NtDiskQuotaExport
0x18000be7a  mov     [rbp+57h+var_70], ax
0x18000be7e  mov     [rbp+57h+var_6C], 4
0x18000be85  mov     [rbp+57h+var_68], ax
0x18000be89  mov     [rbp+57h+var_64], 1
0x18000be90  mov     eax, 0Fh
0x18000be95  mov     [rbp+57h+var_60], ax
0x18000be99  mov     [rbp+57h+var_5C], 4
0x18000bea0  mov     [rbp+57h+var_58], ax
0x18000bea4  mov     [rbp+57h+var_54], 1
0x18000beab  xor     edi, edi
0x18000bead  movsxd  rcx, edi
0x18000beb0  movzx   eax, [rbp+rcx*8+57h+var_70]
0x18000beb5  mov     [rbp+57h+var_38], ax
0x18000beb9  mov     [rbp+57h+var_28], 1
0x18000bec0  mov     [rbp+57h+var_30], 0
0x18000bec8  mov     eax, [rbp+rcx*8+57h+var_6C]
0x18000becc  mov     [rbp+57h+var_20], eax
0x18000becf  mov     [rbp+57h+var_24], 0FFFFFFFFh
0x18000bed6  mov     rax, [r14]
0x18000bed9  lea     r8, [rbp+57h+var_50]
0x18000bedd  lea     rdx, [rbp+57h+var_38]
0x18000bee1  mov     rcx, r14
0x18000bee4  mov     rax, [rax+18h]
0x18000bee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beed  mov     ebx, eax
0x18000beef  test    eax, eax
0x18000bef1  jns     short loc_18000BEFF
0x18000bef3  inc     edi
0x18000bef5  cmp     edi, 4
0x18000bef8  jb      short loc_18000BEAD
0x18000befa  jmp     loc_18000BFEF
0x18000beff  mov     [rbp+57h+ppstm], 0
0x18000bf07  cmp     [rbp+57h+var_50.tymed], 1
0x18000bf0b  jnz     short loc_18000BF21
0x18000bf0d  lea     r8, [rbp+57h+ppstm]; ppstm
0x18000bf11  xor     edx, edx; fDeleteOnRelease
0x18000bf13  mov     rcx, qword ptr [rbp+57h+var_50.8]; hGlobal
0x18000bf17  call    cs:__imp_CreateStreamOnHGlobal
0x18000bf1d  mov     ebx, eax
0x18000bf1f  jmp     short loc_18000BF46
0x18000bf21  mov     ebx, 80004005h
0x18000bf26  cmp     [rbp+57h+var_50.tymed], 4
0x18000bf2a  jnz     loc_18000BFEF
0x18000bf30  mov     rcx, qword ptr [rbp+57h+var_50.8]
0x18000bf34  mov     [rbp+57h+ppstm], rcx
0x18000bf38  mov     rax, [rcx]
0x18000bf3b  mov     rax, [rax+8]
0x18000bf3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf44  xor     ebx, ebx
0x18000bf46  mov     rcx, [rbp+57h+ppstm]
0x18000bf4a  test    rcx, rcx
0x18000bf4d  jz      loc_18000BFEF
0x18000bf53  mov     [rbp+57h+phglobal], 0
0x18000bf5b  mov     rax, [rcx]
0x18000bf5e  xor     r9d, r9d
0x18000bf61  xor     r8d, r8d
0x18000bf64  mov     rdx, [rbp+57h+phglobal]
0x18000bf68  mov     rax, [rax+28h]
0x18000bf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf71  mov     ebx, eax
0x18000bf73  test    eax, eax
0x18000bf75  js      short loc_18000BFDE
0x18000bf77  movzx   eax, [rbp+57h+var_38]
0x18000bf7b  cmp     cs:?m_CF_NtDiskQuotaExport@DataObject@DetailsView@@2GA, ax; ushort DetailsView::DataObject::m_CF_NtDiskQuotaExport
0x18000bf82  jnz     short loc_18000BFAA
0x18000bf84  mov     rdx, [rbp+57h+ppstm]; struct IStream *
0x18000bf88  lea     rcx, [rbp+57h+var_70]; this
0x18000bf8c  call    ??0Source@Importer@DetailsView@@QEAA@PEAUIStream@@@Z; DetailsView::Importer::Source::Source(IStream *)
0x18000bf91  nop
0x18000bf92  lea     rdx, [rbp+57h+var_70]; struct DetailsView::Importer::Source *
0x18000bf96  mov     rcx, rsi; this
0x18000bf99  call    ?Import@Importer@DetailsView@@AEAAJAEAVSource@12@@Z; DetailsView::Importer::Import(DetailsView::Importer::Source &)
0x18000bf9e  nop
0x18000bf9f  lea     rcx, [rbp+57h+var_70]; this
0x18000bfa3  call    ??1Source@Importer@DetailsView@@UEAA@XZ; DetailsView::Importer::Source::~Source(void)
0x18000bfa8  jmp     short loc_18000BFDE
0x18000bfaa  mov     ecx, 0Fh
0x18000bfaf  cmp     cx, ax
0x18000bfb2  jnz     short loc_18000BFDE
0x18000bfb4  mov     [rbp+57h+phglobal], 0
0x18000bfbc  lea     rdx, [rbp+57h+phglobal]; phglobal
0x18000bfc0  mov     rcx, [rbp+57h+ppstm]; pstm
0x18000bfc4  call    cs:__imp_GetHGlobalFromStream
0x18000bfca  mov     ebx, eax
0x18000bfcc  test    eax, eax
0x18000bfce  js      short loc_18000BFDE
0x18000bfd0  mov     rdx, [rbp+57h+phglobal]; HDROP
0x18000bfd4  mov     rcx, rsi; this
0x18000bfd7  call    ?Import@Importer@DetailsView@@QEAAJPEAUHDROP__@@@Z; DetailsView::Importer::Import(HDROP__ *)
0x18000bfdc  mov     ebx, eax
0x18000bfde  mov     rcx, [rbp+57h+ppstm]
0x18000bfe2  mov     rax, [rcx]
0x18000bfe5  mov     rax, [rax+10h]
0x18000bfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfee  nop
0x18000bfef  lea     rcx, [rbp+57h+var_50]; LPSTGMEDIUM
0x18000bff3  call    cs:__imp_ReleaseStgMedium
0x18000bff9  mov     eax, ebx
0x18000bffb  lea     r11, [rsp+0A0h+var_10]
0x18000c003  mov     rbx, [r11+20h]
0x18000c007  mov     rsi, [r11+28h]
0x18000c00b  mov     rsp, r11
0x18000c00e  pop     r14
0x18000c010  pop     rdi
0x18000c011  pop     rbp
0x18000c012  retn
```
