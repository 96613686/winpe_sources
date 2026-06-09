# IMSVidEVRImpl<CMSVidEVR,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidEVR>::Capture(IPictureDisp * *)

- ea: `0x1800eac60`
- end: `0x1800eae2f`
- name: `?Capture@?$IMSVidEVRImpl@VCMSVidEVR@@$1?LIBID_MSVidCtlLib@@3U_GUID@@B$1?_GUID_00000000_0000_0000_0000_000000000000@@3U__s_GUID@@BUIMSVidEVR@@@@UEAAJPEAPEAUIPictureDisp@@@Z`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004640`
- `0x180006b38`
- `0x18001d270`
- `0x1800eac60`
- `0x1800f8010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800eada1`
- `ole32!CoTaskMemFree` at `0x1800eada1`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x1800eadde`
- `OLEAUT32!__imp_OleCreatePictureIndirect` at `0x1800eadde`
- `USER32!ReleaseDC` at `0x1800eadac`
- `USER32!ReleaseDC` at `0x1800eadac`
- `USER32!GetDC` at `0x1800ead69`
- `USER32!GetDC` at `0x1800ead69`
- `GDI32!CreateDIBitmap` at `0x1800ead94`
- `GDI32!CreateDIBitmap` at `0x1800ead94`

## pseudocode

```c
__int64 __fastcall IMSVidEVRImpl<CMSVidEVR,&_GUID const LIBID_MSVidCtlLib,&__s_GUID const _GUID_00000000_0000_0000_0000_000000000000,IMSVidEVR>::Capture(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  HRESULT v5; // ebx
  __int64 v6; // rcx
  HRESULT v7; // eax
  HDC DC; // rdi
  HBITMAP v9; // rbx
  char **v11; // [rsp+38h] [rbp-61h]
  void *pjBits; // [rsp+40h] [rbp-59h] BYREF
  int v13; // [rsp+48h] [rbp-51h] BYREF
  LPVOID lpvObj; // [rsp+50h] [rbp-49h] BYREF
  struct tagPICTDESC PictDesc; // [rsp+58h] [rbp-41h] BYREF
  __int64 v16; // [rsp+70h] [rbp-29h] BYREF
  BITMAPINFOHEADER pbmih; // [rsp+78h] [rbp-21h] BYREF
  BITMAPINFO pbmi; // [rsp+A0h] [rbp+7h] BYREF

  lpvObj = 0;
  memset(&PictDesc, 0, sizeof(PictDesc));
  if ( a2 )
  {
    v6 = *(_QWORD *)(a1 + 208);
    if ( v6 )
    {
      memset(&pbmih, 0, sizeof(pbmih));
      pjBits = 0;
      v16 = 0;
      v13 = 0;
      pbmih.biSize = 40;
      v5 = (*(__int64 (__fastcall **)(__int64, BITMAPINFOHEADER *, void **, int *, __int64 *))(*(_QWORD *)v6 + 96LL))(
             v6,
             &pbmih,
             &pjBits,
             &v13,
             &v16);
      if ( v5 < 0 )
        goto LABEL_11;
      if ( !pjBits )
      {
        v5 = -2147418113;
        goto LABEL_11;
      }
      pbmi.bmiColors[0] = 0;
      pbmi.bmiHeader = pbmih;
      DC = GetDC(0);
      v9 = CreateDIBitmap(DC, &pbmih, 4u, pjBits, &pbmi, 0);
      CoTaskMemFree(pjBits);
      ReleaseDC(0, DC);
      PictDesc.8 = (union tagPICTDESC::$43BF5684F0E8BAFC8B650B528FAB349D)(unsigned __int64)v9;
      PictDesc.picType = 1;
      PictDesc.cbSizeofstruct = 24;
      v5 = OleCreatePictureIndirect(&PictDesc, &IID_IPicture, 1, &lpvObj);
      if ( v5 < 0 )
        goto LABEL_11;
      v7 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64))lpvObj)(
             lpvObj,
             &GUID_7bf80981_bf32_101a_8bbb_00aa00300cab,
             a2);
    }
    else
    {
      v7 = ATL::AtlSetErrorInfo2(
             &GUID_c45268a2_fa81_4e19_b1e3_72edbd60aeda,
             0xC0040590,
             a3,
             a4,
             &GUID_37b03540_a4c8_11d2_b634_00c04f79498e,
             -2147467259,
             hInstance,
             v11);
    }
    v5 = v7;
    goto LABEL_11;
  }
  v5 = -2147467261;
LABEL_11:
  ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&lpvObj);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800eac60  mov     [rsp-8+arg_10], rbx
0x1800eac65  push    rbp
0x1800eac66  push    rsi
0x1800eac67  push    rdi
0x1800eac68  lea     rbp, [rsp-47h]
0x1800eac6d  sub     rsp, 0E0h
0x1800eac74  mov     rax, cs:__security_cookie
0x1800eac7b  xor     rax, rsp
0x1800eac7e  mov     [rbp+57h+var_20], rax
0x1800eac82  xor     eax, eax
0x1800eac84  mov     [rbp+57h+lpvObj], 0
0x1800eac8c  mov     qword ptr [rbp+57h+PictDesc.8+8], rax
0x1800eac90  xorps   xmm0, xmm0
0x1800eac93  mov     rsi, rdx
0x1800eac96  movups  xmmword ptr [rbp+57h+PictDesc.cbSizeofstruct], xmm0
0x1800eac9a  test    rdx, rdx
0x1800eac9d  jnz     short loc_1800EACA9
0x1800eac9f  mov     ebx, 80004003h
0x1800eaca4  jmp     loc_1800EAE05
0x1800eaca9  mov     rcx, [rcx+0D0h]
0x1800eacb0  test    rcx, rcx
0x1800eacb3  jnz     short loc_1800EACEB
0x1800eacb5  mov     rax, cs:hInstance
0x1800eacbc  lea     rcx, _GUID_c45268a2_fa81_4e19_b1e3_72edbd60aeda; clsid
0x1800eacc3  mov     [rsp+0F0h+var_C0], rax; HINSTANCE
0x1800eacc8  mov     edx, 0C0040590h; dwMessageId
0x1800eaccd  lea     rax, _GUID_37b03540_a4c8_11d2_b634_00c04f79498e
0x1800eacd4  mov     [rsp+0F0h+iUsage], 80004005h; int
0x1800eacdc  mov     [rsp+0F0h+pbmi], rax; struct _GUID *
0x1800eace1  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x1800eace6  jmp     loc_1800EAE03
0x1800eaceb  movups  xmmword ptr [rbp+57h+pbmih.biSize], xmm0
0x1800eacef  mov     qword ptr [rbp+57h+pbmih.biClrUsed], rax
0x1800eacf3  lea     rdx, [rbp+57h+var_80]
0x1800eacf7  mov     [rbp+57h+pjBits], rax
0x1800eacfb  lea     r9, [rbp+57h+var_A8]
0x1800eacff  mov     [rbp+57h+var_80], rax
0x1800ead03  lea     r8, [rbp+57h+pjBits]
0x1800ead07  mov     [rbp+57h+var_A8], eax
0x1800ead0a  mov     [rbp+57h+pbmih.biSize], 28h ; '('
0x1800ead11  movups  xmmword ptr [rbp+57h+pbmih.biCompression], xmm0
0x1800ead15  mov     rax, [rcx]
0x1800ead18  mov     [rsp+0F0h+pbmi], rdx
0x1800ead1d  lea     rdx, [rbp+57h+pbmih]
0x1800ead21  mov     rax, [rax+60h]
0x1800ead25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ead2a  mov     ebx, eax
0x1800ead2c  test    eax, eax
0x1800ead2e  js      loc_1800EAE05
0x1800ead34  cmp     [rbp+57h+pjBits], 0
0x1800ead39  jnz     short loc_1800EAD45
0x1800ead3b  mov     ebx, 8000FFFFh
0x1800ead40  jmp     loc_1800EAE05
0x1800ead45  movups  xmm0, xmmword ptr [rbp+57h+pbmih.biWidth]
0x1800ead49  xor     eax, eax
0x1800ead4b  xor     ecx, ecx; hWnd
0x1800ead4d  movups  xmm1, xmmword ptr [rbp+57h+pbmih.biSizeImage]
0x1800ead51  mov     qword ptr [rbp+57h+var_50.bmiHeader.biClrImportant], rax
0x1800ead55  mov     eax, [rbp+57h+pbmih.biSize]
0x1800ead58  mov     [rbp+57h+var_50.bmiHeader.biSize], eax
0x1800ead5b  mov     eax, [rbp+57h+pbmih.biClrImportant]
0x1800ead5e  mov     [rbp+57h+var_50.bmiHeader.biClrImportant], eax
0x1800ead61  movups  xmmword ptr [rbp+57h+var_50.bmiHeader.biWidth], xmm0
0x1800ead65  movups  xmmword ptr [rbp+57h+var_50.bmiHeader.biSizeImage], xmm1
0x1800ead69  call    cs:__imp_GetDC
0x1800ead6f  mov     r9, [rbp+57h+pjBits]; pjBits
0x1800ead73  lea     rdx, [rbp+57h+pbmih]; pbmih
0x1800ead77  mov     rdi, rax
0x1800ead7a  mov     [rsp+0F0h+iUsage], 0; iUsage
0x1800ead82  lea     rax, [rbp+57h+var_50]
0x1800ead86  mov     rcx, rdi; hdc
0x1800ead89  mov     r8d, 4; flInit
0x1800ead8f  mov     [rsp+0F0h+pbmi], rax; pbmi
0x1800ead94  call    cs:__imp_CreateDIBitmap
0x1800ead9a  mov     rcx, [rbp+57h+pjBits]; pv
0x1800ead9e  mov     rbx, rax
0x1800eada1  call    cs:__imp_CoTaskMemFree
0x1800eada7  mov     rdx, rdi; hDC
0x1800eadaa  xor     ecx, ecx; hWnd
0x1800eadac  call    cs:__imp_ReleaseDC
0x1800eadb2  mov     r8d, 1; fOwn
0x1800eadb8  mov     qword ptr [rbp+57h+PictDesc.8], rbx
0x1800eadbc  lea     r9, [rbp+57h+lpvObj]; lplpvObj
0x1800eadc0  mov     [rbp+57h+PictDesc.picType], r8d
0x1800eadc4  lea     rdx, IID_IPicture; riid
0x1800eadcb  mov     qword ptr [rbp+57h+PictDesc.8+8], 0
0x1800eadd3  lea     rcx, [rbp+57h+PictDesc]; lpPictDesc
0x1800eadd7  mov     [rbp+57h+PictDesc.cbSizeofstruct], 18h
0x1800eadde  call    cs:__imp_OleCreatePictureIndirect
0x1800eade4  mov     ebx, eax
0x1800eade6  test    eax, eax
0x1800eade8  js      short loc_1800EAE05
0x1800eadea  mov     rcx, [rbp+57h+lpvObj]
0x1800eadee  lea     rdx, _GUID_7bf80981_bf32_101a_8bbb_00aa00300cab
0x1800eadf5  mov     r8, rsi
0x1800eadf8  mov     rax, [rcx]
0x1800eadfb  mov     rax, [rax]
0x1800eadfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eae03  mov     ebx, eax
0x1800eae05  lea     rcx, [rbp+57h+lpvObj]
0x1800eae09  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800eae0e  mov     eax, ebx
0x1800eae10  mov     rcx, [rbp+57h+var_20]
0x1800eae14  xor     rcx, rsp; StackCookie
0x1800eae17  call    __security_check_cookie
0x1800eae1c  mov     rbx, [rsp+0F0h+arg_10]
0x1800eae24  add     rsp, 0E0h
0x1800eae2b  pop     rdi
0x1800eae2c  pop     rsi
0x1800eae2d  pop     rbp
0x1800eae2e  retn
```
