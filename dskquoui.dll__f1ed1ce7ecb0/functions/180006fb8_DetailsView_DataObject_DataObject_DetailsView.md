# DetailsView::DataObject::DataObject(DetailsView &)

- ea: `0x180006fb8`
- end: `0x180007295`
- name: `??0DataObject@DetailsView@@QEAA@AEAV1@@Z`
- size: `733`
- prototype: `__int64 __fastcall(DetailsView::DataObject *__hidden this, struct DetailsView *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c224`

## callees

- `0x180006ec0`
- `0x180006fb8`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x180006ff2`
- `USER32!RegisterClipboardFormatW` at `0x18000700f`
- `USER32!RegisterClipboardFormatW` at `0x18000702c`
- `USER32!RegisterClipboardFormatW` at `0x180007049`
- `USER32!RegisterClipboardFormatW` at `0x180007066`
- `USER32!RegisterClipboardFormatW` at `0x180006ff2`
- `USER32!RegisterClipboardFormatW` at `0x18000700f`
- `USER32!RegisterClipboardFormatW` at `0x18000702c`
- `USER32!RegisterClipboardFormatW` at `0x180007049`
- `USER32!RegisterClipboardFormatW` at `0x180007066`

## string_xrefs

- `0x180007042`: `FileGroupDescriptorW`

## pseudocode

```c
DetailsView::DataObject *__fastcall DetailsView::DataObject::DataObject(
        DetailsView::DataObject *this,
        struct DetailsView *a2)
{
  bool v2; // zf
  _DWORD *v4; // rax
  unsigned __int16 v5; // cx
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned __int16 v8; // cx
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int16 v11; // cx
  __int64 v12; // rax
  unsigned __int16 v13; // cx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int16 v16; // cx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax

  *((_DWORD *)this + 2) = 14;
  v2 = DetailsView::DataObject::m_CF_Csv == 0;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = a2;
  if ( v2 )
    DetailsView::DataObject::m_CF_Csv = RegisterClipboardFormatW(L"Csv");
  if ( !DetailsView::DataObject::m_CF_RichText )
    DetailsView::DataObject::m_CF_RichText = RegisterClipboardFormatW(L"Rich Text Format");
  if ( !DetailsView::DataObject::m_CF_NtDiskQuotaExport )
    DetailsView::DataObject::m_CF_NtDiskQuotaExport = RegisterClipboardFormatW(L"NT DISKQUTOA IMPORTEXPORT");
  if ( !DetailsView::DataObject::m_CF_FileGroupDescriptor )
    DetailsView::DataObject::m_CF_FileGroupDescriptor = RegisterClipboardFormatW(L"FileGroupDescriptorW");
  if ( !DetailsView::DataObject::m_CF_FileContents )
    DetailsView::DataObject::m_CF_FileContents = RegisterClipboardFormatW(L"FileContents");
  v4 = operator new(saturated_mul(*((unsigned int *)this + 2), 0x20u));
  *(_QWORD *)this = v4;
  v5 = DetailsView::DataObject::m_CF_FileGroupDescriptor;
  *(_WORD *)v4 = DetailsView::DataObject::m_CF_FileGroupDescriptor;
  v4[4] = 1;
  *((_QWORD *)v4 + 1) = 0;
  v4[6] = 4;
  v4[5] = -1;
  v6 = *(_QWORD *)this;
  *(_WORD *)(v6 + 32) = v5;
  *(_DWORD *)(v6 + 48) = 1;
  *(_QWORD *)(v6 + 40) = 0;
  *(_DWORD *)(v6 + 56) = 1;
  *(_DWORD *)(v6 + 52) = -1;
  v7 = *(_QWORD *)this;
  v8 = DetailsView::DataObject::m_CF_FileContents;
  *(_WORD *)(v7 + 64) = DetailsView::DataObject::m_CF_FileContents;
  *(_DWORD *)(v7 + 80) = 1;
  *(_QWORD *)(v7 + 72) = 0;
  *(_DWORD *)(v7 + 88) = 4;
  *(_DWORD *)(v7 + 84) = -1;
  v9 = *(_QWORD *)this;
  *(_WORD *)(v9 + 96) = v8;
  *(_DWORD *)(v9 + 112) = 1;
  *(_QWORD *)(v9 + 104) = 0;
  *(_DWORD *)(v9 + 120) = 1;
  *(_DWORD *)(v9 + 116) = -1;
  v10 = *(_QWORD *)this;
  v11 = DetailsView::DataObject::m_CF_NtDiskQuotaExport;
  *(_WORD *)(v10 + 128) = DetailsView::DataObject::m_CF_NtDiskQuotaExport;
  *(_DWORD *)(v10 + 144) = 1;
  *(_QWORD *)(v10 + 136) = 0;
  *(_DWORD *)(v10 + 152) = 4;
  *(_DWORD *)(v10 + 148) = -1;
  v12 = *(_QWORD *)this;
  *(_WORD *)(v12 + 160) = v11;
  v13 = DetailsView::DataObject::m_CF_RichText;
  *(_DWORD *)(v12 + 176) = 1;
  *(_QWORD *)(v12 + 168) = 0;
  *(_DWORD *)(v12 + 184) = 1;
  *(_DWORD *)(v12 + 180) = -1;
  v14 = *(_QWORD *)this;
  *(_WORD *)(v14 + 192) = v13;
  *(_DWORD *)(v14 + 208) = 1;
  *(_QWORD *)(v14 + 200) = 0;
  *(_DWORD *)(v14 + 216) = 4;
  *(_DWORD *)(v14 + 212) = -1;
  v15 = *(_QWORD *)this;
  *(_WORD *)(v15 + 224) = v13;
  v16 = DetailsView::DataObject::m_CF_Csv;
  *(_DWORD *)(v15 + 240) = 1;
  *(_QWORD *)(v15 + 232) = 0;
  *(_DWORD *)(v15 + 248) = 1;
  *(_DWORD *)(v15 + 244) = -1;
  v17 = *(_QWORD *)this;
  *(_WORD *)(v17 + 256) = v16;
  *(_DWORD *)(v17 + 272) = 1;
  *(_QWORD *)(v17 + 264) = 0;
  *(_DWORD *)(v17 + 280) = 4;
  *(_DWORD *)(v17 + 276) = -1;
  v18 = *(_QWORD *)this;
  *(_WORD *)(v18 + 288) = v16;
  *(_DWORD *)(v18 + 304) = 1;
  *(_QWORD *)(v18 + 296) = 0;
  *(_DWORD *)(v18 + 312) = 1;
  *(_DWORD *)(v18 + 308) = -1;
  v19 = *(_QWORD *)this;
  *(_WORD *)(v19 + 320) = 13;
  *(_DWORD *)(v19 + 336) = 1;
  *(_QWORD *)(v19 + 328) = 0;
  *(_DWORD *)(v19 + 344) = 4;
  *(_DWORD *)(v19 + 340) = -1;
  v20 = *(_QWORD *)this;
  *(_QWORD *)(v20 + 360) = 0;
  *(_WORD *)(v20 + 352) = 13;
  *(_DWORD *)(v20 + 368) = 1;
  *(_DWORD *)(v20 + 376) = 1;
  *(_DWORD *)(v20 + 372) = -1;
  v21 = *(_QWORD *)this;
  *(_QWORD *)(v21 + 392) = 0;
  *(_WORD *)(v21 + 384) = 1;
  *(_DWORD *)(v21 + 400) = 1;
  *(_DWORD *)(v21 + 408) = 4;
  *(_DWORD *)(v21 + 404) = -1;
  v22 = *(_QWORD *)this;
  *(_QWORD *)(v22 + 424) = 0;
  *(_WORD *)(v22 + 416) = 1;
  *(_DWORD *)(v22 + 432) = 1;
  *(_DWORD *)(v22 + 440) = 1;
  *(_DWORD *)(v22 + 436) = -1;
  return this;
}

```

## disassembly

```asm
0x180006fb8  mov     [rsp+arg_0], rbx
0x180006fbd  mov     [rsp+arg_8], rsi
0x180006fc2  push    rdi
0x180006fc3  sub     rsp, 20h
0x180006fc7  xor     esi, esi
0x180006fc9  mov     dword ptr [rcx+8], 0Eh
0x180006fd0  cmp     si, cs:?m_CF_Csv@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_Csv
0x180006fd7  mov     rbx, rcx
0x180006fda  mov     [rcx], rsi
0x180006fdd  mov     [rcx+10h], rsi
0x180006fe1  mov     [rcx+18h], rsi
0x180006fe5  mov     [rcx+20h], rdx
0x180006fe9  jnz     short loc_180006FFF
0x180006feb  lea     rcx, szFormat; "Csv"
0x180006ff2  call    cs:__imp_RegisterClipboardFormatW
0x180006ff8  mov     cs:?m_CF_Csv@DataObject@DetailsView@@2GA, ax; ushort DetailsView::DataObject::m_CF_Csv
0x180006fff  cmp     si, cs:?m_CF_RichText@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_RichText
0x180007006  jnz     short loc_18000701C
0x180007008  lea     rcx, aRichTextFormat; "Rich Text Format"
0x18000700f  call    cs:__imp_RegisterClipboardFormatW
0x180007015  mov     cs:?m_CF_RichText@DataObject@DetailsView@@2GA, ax; ushort DetailsView::DataObject::m_CF_RichText
0x18000701c  cmp     si, cs:?m_CF_NtDiskQuotaExport@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_NtDiskQuotaExport
0x180007023  jnz     short loc_180007039
0x180007025  lea     rcx, aNtDiskqutoaImp; "NT DISKQUTOA IMPORTEXPORT"
0x18000702c  call    cs:__imp_RegisterClipboardFormatW
0x180007032  mov     cs:?m_CF_NtDiskQuotaExport@DataObject@DetailsView@@2GA, ax; ushort DetailsView::DataObject::m_CF_NtDiskQuotaExport
0x180007039  cmp     si, cs:?m_CF_FileGroupDescriptor@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_FileGroupDescriptor
0x180007040  jnz     short loc_180007056
0x180007042  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x180007049  call    cs:__imp_RegisterClipboardFormatW
0x18000704f  mov     cs:?m_CF_FileGroupDescriptor@DataObject@DetailsView@@2GA, ax; ushort DetailsView::DataObject::m_CF_FileGroupDescriptor
0x180007056  cmp     si, cs:?m_CF_FileContents@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_FileContents
0x18000705d  jnz     short loc_180007073
0x18000705f  lea     rcx, aFilecontents; "FileContents"
0x180007066  call    cs:__imp_RegisterClipboardFormatW
0x18000706c  mov     cs:?m_CF_FileContents@DataObject@DetailsView@@2GA, ax; ushort DetailsView::DataObject::m_CF_FileContents
0x180007073  mov     ecx, [rbx+8]
0x180007076  mov     eax, 20h ; ' '
0x18000707b  mul     rcx
0x18000707e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180007085  cmovb   rax, rdi
0x180007089  mov     rcx, rax; uBytes
0x18000708c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007091  mov     [rbx], rax
0x180007094  lea     r8d, [rdi+2]
0x180007098  movzx   ecx, cs:?m_CF_FileGroupDescriptor@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_FileGroupDescriptor
0x18000709f  lea     edx, [rdi+5]
0x1800070a2  mov     [rax], cx
0x1800070a5  mov     [rax+10h], r8d
0x1800070a9  mov     [rax+8], rsi
0x1800070ad  mov     [rax+18h], edx
0x1800070b0  mov     [rax+14h], edi
0x1800070b3  mov     rax, [rbx]
0x1800070b6  mov     [rax+20h], cx
0x1800070ba  mov     [rax+30h], r8d
0x1800070be  mov     [rax+28h], rsi
0x1800070c2  mov     [rax+38h], r8d
0x1800070c6  mov     [rax+34h], edi
0x1800070c9  mov     rax, [rbx]
0x1800070cc  movzx   ecx, cs:?m_CF_FileContents@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_FileContents
0x1800070d3  mov     [rax+40h], cx
0x1800070d7  mov     [rax+50h], r8d
0x1800070db  mov     [rax+48h], rsi
0x1800070df  mov     [rax+58h], edx
0x1800070e2  mov     [rax+54h], edi
0x1800070e5  mov     rax, [rbx]
0x1800070e8  mov     [rax+60h], cx
0x1800070ec  mov     [rax+70h], r8d
0x1800070f0  mov     [rax+68h], rsi
0x1800070f4  mov     [rax+78h], r8d
0x1800070f8  mov     [rax+74h], edi
0x1800070fb  mov     rax, [rbx]
0x1800070fe  movzx   ecx, cs:?m_CF_NtDiskQuotaExport@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_NtDiskQuotaExport
0x180007105  mov     [rax+80h], cx
0x18000710c  mov     [rax+90h], r8d
0x180007113  mov     [rax+88h], rsi
0x18000711a  mov     [rax+98h], edx
0x180007120  mov     [rax+94h], edi
0x180007126  mov     rax, [rbx]
0x180007129  mov     [rax+0A0h], cx
0x180007130  movzx   ecx, cs:?m_CF_RichText@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_RichText
0x180007137  mov     [rax+0B0h], r8d
0x18000713e  mov     [rax+0A8h], rsi
0x180007145  mov     [rax+0B8h], r8d
0x18000714c  mov     [rax+0B4h], edi
0x180007152  mov     rax, [rbx]
0x180007155  mov     [rax+0C0h], cx
0x18000715c  mov     [rax+0D0h], r8d
0x180007163  mov     [rax+0C8h], rsi
0x18000716a  mov     [rax+0D8h], edx
0x180007170  mov     [rax+0D4h], edi
0x180007176  mov     rax, [rbx]
0x180007179  mov     [rax+0E0h], cx
0x180007180  movzx   ecx, cs:?m_CF_Csv@DataObject@DetailsView@@2GA; ushort DetailsView::DataObject::m_CF_Csv
0x180007187  mov     [rax+0F0h], r8d
0x18000718e  mov     [rax+0E8h], rsi
0x180007195  mov     [rax+0F8h], r8d
0x18000719c  mov     [rax+0F4h], edi
0x1800071a2  mov     rax, [rbx]
0x1800071a5  mov     [rax+100h], cx
0x1800071ac  mov     [rax+110h], r8d
0x1800071b3  mov     [rax+108h], rsi
0x1800071ba  mov     [rax+118h], edx
0x1800071c0  mov     [rax+114h], edi
0x1800071c6  mov     rax, [rbx]
0x1800071c9  mov     [rax+120h], cx
0x1800071d0  lea     ecx, [rdi+0Eh]
0x1800071d3  mov     [rax+130h], r8d
0x1800071da  mov     [rax+128h], rsi
0x1800071e1  mov     [rax+138h], r8d
0x1800071e8  mov     [rax+134h], edi
0x1800071ee  mov     rax, [rbx]
0x1800071f1  mov     [rax+140h], cx
0x1800071f8  mov     [rax+150h], r8d
0x1800071ff  mov     [rax+148h], rsi
0x180007206  mov     [rax+158h], edx
0x18000720c  mov     [rax+154h], edi
0x180007212  mov     rax, [rbx]
0x180007215  mov     [rax+168h], rsi
0x18000721c  mov     [rax+160h], cx
0x180007223  mov     [rax+170h], r8d
0x18000722a  mov     [rax+178h], r8d
0x180007231  mov     [rax+174h], edi
0x180007237  mov     rax, [rbx]
0x18000723a  mov     [rax+188h], rsi
0x180007241  mov     [rax+180h], r8w
0x180007249  mov     [rax+190h], r8d
0x180007250  mov     [rax+198h], edx
0x180007256  mov     [rax+194h], edi
0x18000725c  mov     rax, [rbx]
0x18000725f  mov     [rax+1A8h], rsi
0x180007266  mov     rsi, [rsp+28h+arg_8]
0x18000726b  mov     [rax+1A0h], r8w
0x180007273  mov     [rax+1B0h], r8d
0x18000727a  mov     [rax+1B8h], r8d
0x180007281  mov     [rax+1B4h], edi
0x180007287  mov     rax, rbx
0x18000728a  mov     rbx, [rsp+28h+arg_0]
0x18000728f  add     rsp, 20h
0x180007293  pop     rdi
0x180007294  retn
```
