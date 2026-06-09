# PrintableAreaToPrintCapabilities(publicdm::CPrintCapsInfo &)

- ea: `0x18001fcc4`
- end: `0x18001ffee`
- name: `?PrintableAreaToPrintCapabilities@@YAJAEAVCPrintCapsInfo@publicdm@@@Z`
- size: `810`
- prototype: `__int64 __fastcall(struct publicdm::CPrintCapsInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f720`

## callees

- `0x180005e70`
- `0x18000b0a0`
- `0x18001fcc4`
- `0x180023010`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18001fd20`
- `GDI32!GetDeviceCaps` at `0x18001fd31`
- `GDI32!GetDeviceCaps` at `0x18001fd42`
- `GDI32!GetDeviceCaps` at `0x18001fd53`
- `GDI32!GetDeviceCaps` at `0x18001fd64`
- `GDI32!GetDeviceCaps` at `0x18001fd75`
- `GDI32!GetDeviceCaps` at `0x18001fd86`
- `GDI32!GetDeviceCaps` at `0x18001fd97`
- `GDI32!GetDeviceCaps` at `0x18001fd20`
- `GDI32!GetDeviceCaps` at `0x18001fd31`
- `GDI32!GetDeviceCaps` at `0x18001fd42`
- `GDI32!GetDeviceCaps` at `0x18001fd53`
- `GDI32!GetDeviceCaps` at `0x18001fd64`
- `GDI32!GetDeviceCaps` at `0x18001fd75`
- `GDI32!GetDeviceCaps` at `0x18001fd86`
- `GDI32!GetDeviceCaps` at `0x18001fd97`
- `GDI32!CreateICW` at `0x18001fced`
- `GDI32!CreateICW` at `0x18001fced`
- `GDI32!DeleteDC` at `0x18001ffce`
- `GDI32!DeleteDC` at `0x18001ffce`
- `KERNEL32!GetLastError` at `0x18001fcfb`
- `KERNEL32!GetLastError` at `0x18001fcfb`

## string_xrefs

- `0x18001fde9`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001fe31`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x18001fe59`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c
__int64 __fastcall PrintableAreaToPrintCapabilities(struct publicdm::CPrintCapsInfo *a1)
{
  signed int Property; // ebx
  HDC ICW; // rsi
  signed int LastError; // eax
  int v5; // r12d
  int v6; // r13d
  int v7; // r15d
  int v8; // eax
  int v9; // r14d
  __int64 v10; // rcx
  struct IXMLDOMElement **v12; // [rsp+30h] [rbp-40h]
  struct IXMLDOMElement **v13; // [rsp+30h] [rbp-40h]
  struct IXMLDOMElement **v14; // [rsp+30h] [rbp-40h]
  struct IXMLDOMElement **v15; // [rsp+30h] [rbp-40h]
  int v16; // [rsp+50h] [rbp-20h]
  struct IXMLDOMElement *v17; // [rsp+58h] [rbp-18h] BYREF
  struct IXMLDOMElement *v18; // [rsp+60h] [rbp-10h] BYREF
  int DeviceCaps; // [rsp+B8h] [rbp+48h]
  int v20; // [rsp+C0h] [rbp+50h]
  int v21; // [rsp+C8h] [rbp+58h]

  Property = 0;
  ICW = CreateICW(0, *((LPCWSTR *)a1 + 3), 0, *((const DEVMODEW **)a1 + 2));
  if ( ICW )
    goto LABEL_5;
  LastError = GetLastError();
  Property = LastError;
  if ( LastError > 0 )
    Property = (unsigned __int16)LastError | 0x80070000;
  if ( Property >= 0 )
  {
LABEL_5:
    DeviceCaps = GetDeviceCaps(ICW, 112);
    v21 = GetDeviceCaps(ICW, 8);
    v20 = GetDeviceCaps(ICW, 113);
    v16 = GetDeviceCaps(ICW, 10);
    v5 = GetDeviceCaps(ICW, 110);
    v6 = GetDeviceCaps(ICW, 111);
    v7 = GetDeviceCaps(ICW, 88);
    v8 = GetDeviceCaps(ICW, 90);
    v9 = v8;
    if ( v7 && v8 )
    {
      v10 = *((_QWORD *)a1 + 14);
      v18 = 0;
      v17 = 0;
      Property = (*(__int64 (__fastcall **)(__int64, _QWORD, const OLECHAR *, const wchar_t *, _QWORD, _DWORD))(*(_QWORD *)v10 + 8LL))(
                   v10,
                   0,
                   L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                   L"PageImageableSize",
                   0,
                   0);
      if ( Property >= 0 )
      {
        Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                     *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                     v18,
                     L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                     L"ImageableSizeWidth",
                     10 * (2540 * v5 / v7),
                     0,
                     0);
        if ( Property >= 0 )
        {
          Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                       *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                       v18,
                       L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                       L"ImageableSizeHeight",
                       10 * (2540 * v6 / v9),
                       0,
                       v12);
          if ( Property >= 0 )
          {
            Property = (*(__int64 (__fastcall **)(_QWORD, struct IXMLDOMElement *, const OLECHAR *, const wchar_t *, _QWORD, _DWORD))(**((_QWORD **)a1 + 14) + 8LL))(
                         *((_QWORD *)a1 + 14),
                         v18,
                         L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                         L"ImageableArea",
                         0,
                         0);
            if ( Property >= 0 )
            {
              Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                           *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                           v17,
                           L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                           L"OriginWidth",
                           10 * (2540 * DeviceCaps / v7),
                           0,
                           0);
              if ( Property >= 0 )
              {
                Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                             *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                             v17,
                             L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                             L"OriginHeight",
                             10 * (2540 * v20 / v9),
                             0,
                             v13);
                if ( Property >= 0 )
                {
                  Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                               *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                               v17,
                               L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                               L"ExtentWidth",
                               10 * (2540 * v21 / v7),
                               0,
                               v14);
                  if ( Property >= 0 )
                    Property = NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(
                                 *((NPrintTicketUtil::CPrintTicketWrapper **)a1 + 14),
                                 v17,
                                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                                 L"ExtentHeight",
                                 10 * (2540 * v16 / v9),
                                 0,
                                 v15);
                }
              }
            }
          }
        }
      }
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v17);
      NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(&v18);
    }
    if ( ICW )
      DeleteDC(ICW);
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001fcc4  mov     [rsp-38h+arg_0], rbx
0x18001fcc9  push    rbp
0x18001fcca  push    rsi
0x18001fccb  push    rdi
0x18001fccc  push    r12
0x18001fcce  push    r13
0x18001fcd0  push    r14
0x18001fcd2  push    r15
0x18001fcd4  mov     rbp, rsp
0x18001fcd7  sub     rsp, 70h
0x18001fcdb  mov     r9, [rcx+10h]; pdm
0x18001fcdf  mov     rdi, rcx
0x18001fce2  mov     rdx, [rcx+18h]; pszDevice
0x18001fce6  xor     r8d, r8d; pszPort
0x18001fce9  xor     ecx, ecx; pszDriver
0x18001fceb  xor     ebx, ebx
0x18001fced  call    cs:__imp_CreateICW
0x18001fcf3  mov     rsi, rax
0x18001fcf6  test    rax, rax
0x18001fcf9  jnz     short loc_18001FD18
0x18001fcfb  call    cs:__imp_GetLastError
0x18001fd01  mov     ebx, eax
0x18001fd03  test    eax, eax
0x18001fd05  jle     short loc_18001FD10
0x18001fd07  movzx   ebx, ax
0x18001fd0a  or      ebx, 80070000h
0x18001fd10  test    ebx, ebx
0x18001fd12  js      loc_18001FFD4
0x18001fd18  mov     edx, 70h ; 'p'; index
0x18001fd1d  mov     rcx, rsi; hdc
0x18001fd20  call    cs:__imp_GetDeviceCaps
0x18001fd26  mov     edx, 8; index
0x18001fd2b  mov     rcx, rsi; hdc
0x18001fd2e  mov     [rbp+arg_8], eax
0x18001fd31  call    cs:__imp_GetDeviceCaps
0x18001fd37  mov     edx, 71h ; 'q'; index
0x18001fd3c  mov     rcx, rsi; hdc
0x18001fd3f  mov     [rbp+arg_18], eax
0x18001fd42  call    cs:__imp_GetDeviceCaps
0x18001fd48  mov     edx, 0Ah; index
0x18001fd4d  mov     rcx, rsi; hdc
0x18001fd50  mov     [rbp+arg_10], eax
0x18001fd53  call    cs:__imp_GetDeviceCaps
0x18001fd59  mov     edx, 6Eh ; 'n'; index
0x18001fd5e  mov     rcx, rsi; hdc
0x18001fd61  mov     [rbp+var_20], eax
0x18001fd64  call    cs:__imp_GetDeviceCaps
0x18001fd6a  mov     edx, 6Fh ; 'o'; index
0x18001fd6f  mov     rcx, rsi; hdc
0x18001fd72  mov     r12d, eax
0x18001fd75  call    cs:__imp_GetDeviceCaps
0x18001fd7b  mov     edx, 58h ; 'X'; index
0x18001fd80  mov     rcx, rsi; hdc
0x18001fd83  mov     r13d, eax
0x18001fd86  call    cs:__imp_GetDeviceCaps
0x18001fd8c  mov     edx, 5Ah ; 'Z'; index
0x18001fd91  mov     rcx, rsi; hdc
0x18001fd94  mov     r15d, eax
0x18001fd97  call    cs:__imp_GetDeviceCaps
0x18001fd9d  xor     r8d, r8d
0x18001fda0  mov     r14d, eax
0x18001fda3  test    r15d, r15d
0x18001fda6  jz      loc_18001FFC6
0x18001fdac  test    eax, eax
0x18001fdae  jz      loc_18001FFC6
0x18001fdb4  mov     rcx, [rdi+70h]
0x18001fdb8  lea     rdx, [rbp+var_10]
0x18001fdbc  mov     [rsp+70h+var_30], rdx
0x18001fdc1  lea     r9, aPageimageables; "PageImageableSize"
0x18001fdc8  mov     [rsp+70h+var_38], r8
0x18001fdcd  xor     edx, edx
0x18001fdcf  mov     [rsp+70h+var_40], r8; struct IXMLDOMElement **
0x18001fdd4  mov     [rbp+var_10], r8
0x18001fdd8  mov     [rbp+var_18], r8
0x18001fddc  mov     rax, [rcx]
0x18001fddf  mov     [rsp+70h+var_48], r8d
0x18001fde4  mov     qword ptr [rsp+70h+var_50], r8
0x18001fde9  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001fdf0  mov     rax, [rax+8]
0x18001fdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdf9  mov     ebx, eax
0x18001fdfb  test    eax, eax
0x18001fdfd  js      loc_18001FFB4
0x18001fe03  mov     rcx, [rdi+70h]; this
0x18001fe07  lea     r9, aImageablesizew; "ImageableSizeWidth"
0x18001fe0e  imul    eax, r12d, 9ECh
0x18001fe15  xor     r12d, r12d
0x18001fe18  mov     [rsp+70h+var_48], r12d; int
0x18001fe1d  cdq
0x18001fe1e  idiv    r15d
0x18001fe21  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x18001fe25  lea     r8d, [rax+rax*4]
0x18001fe29  add     r8d, r8d
0x18001fe2c  mov     [rsp+70h+var_50], r8d; int
0x18001fe31  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001fe38  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001fe3d  mov     ebx, eax
0x18001fe3f  test    eax, eax
0x18001fe41  js      loc_18001FFB4
0x18001fe47  mov     rcx, [rdi+70h]; this
0x18001fe4b  lea     r9, aImageablesizeh; "ImageableSizeHeight"
0x18001fe52  imul    eax, r13d, 9ECh
0x18001fe59  lea     r13, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18001fe60  mov     [rsp+70h+var_48], r12d; int
0x18001fe65  cdq
0x18001fe66  idiv    r14d
0x18001fe69  mov     rdx, [rbp+var_10]; struct IXMLDOMElement *
0x18001fe6d  lea     r8d, [rax+rax*4]
0x18001fe71  add     r8d, r8d
0x18001fe74  mov     [rsp+70h+var_50], r8d; int
0x18001fe79  mov     r8, r13; unsigned __int16 *
0x18001fe7c  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001fe81  mov     ebx, eax
0x18001fe83  test    eax, eax
0x18001fe85  js      loc_18001FFB4
0x18001fe8b  mov     rcx, [rdi+70h]
0x18001fe8f  lea     rdx, [rbp+var_18]
0x18001fe93  mov     [rsp+70h+var_30], rdx
0x18001fe98  lea     r9, aImageablearea; "ImageableArea"
0x18001fe9f  mov     rdx, [rbp+var_10]
0x18001fea3  mov     r8, r13
0x18001fea6  mov     [rsp+70h+var_38], r12
0x18001feab  mov     rax, [rcx]
0x18001feae  mov     [rsp+70h+var_40], r12; struct IXMLDOMElement **
0x18001feb3  mov     [rsp+70h+var_48], r12d
0x18001feb8  mov     qword ptr [rsp+70h+var_50], r12
0x18001febd  mov     rax, [rax+8]
0x18001fec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fec6  mov     ebx, eax
0x18001fec8  test    eax, eax
0x18001feca  js      loc_18001FFB4
0x18001fed0  imul    eax, [rbp+arg_8], 9ECh
0x18001fed7  lea     r9, aOriginwidth; "OriginWidth"
0x18001fede  mov     rcx, [rdi+70h]; this
0x18001fee2  mov     [rsp+70h+var_48], r12d; int
0x18001fee7  cdq
0x18001fee8  idiv    r15d
0x18001feeb  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18001feef  lea     r8d, [rax+rax*4]
0x18001fef3  add     r8d, r8d
0x18001fef6  mov     [rsp+70h+var_50], r8d; int
0x18001fefb  mov     r8, r13; unsigned __int16 *
0x18001fefe  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001ff03  mov     ebx, eax
0x18001ff05  test    eax, eax
0x18001ff07  js      loc_18001FFB4
0x18001ff0d  imul    eax, [rbp+arg_10], 9ECh
0x18001ff14  lea     r9, aOriginheight; "OriginHeight"
0x18001ff1b  mov     rcx, [rdi+70h]; this
0x18001ff1f  mov     [rsp+70h+var_48], r12d; int
0x18001ff24  cdq
0x18001ff25  idiv    r14d
0x18001ff28  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18001ff2c  lea     r8d, [rax+rax*4]
0x18001ff30  add     r8d, r8d
0x18001ff33  mov     [rsp+70h+var_50], r8d; int
0x18001ff38  mov     r8, r13; unsigned __int16 *
0x18001ff3b  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001ff40  mov     ebx, eax
0x18001ff42  test    eax, eax
0x18001ff44  js      short loc_18001FFB4
0x18001ff46  imul    eax, [rbp+arg_18], 9ECh
0x18001ff4d  lea     r9, aExtentwidth; "ExtentWidth"
0x18001ff54  mov     rcx, [rdi+70h]; this
0x18001ff58  mov     [rsp+70h+var_48], r12d; int
0x18001ff5d  cdq
0x18001ff5e  idiv    r15d
0x18001ff61  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18001ff65  lea     r8d, [rax+rax*4]
0x18001ff69  add     r8d, r8d
0x18001ff6c  mov     [rsp+70h+var_50], r8d; int
0x18001ff71  mov     r8, r13; unsigned __int16 *
0x18001ff74  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001ff79  mov     ebx, eax
0x18001ff7b  test    eax, eax
0x18001ff7d  js      short loc_18001FFB4
0x18001ff7f  imul    eax, [rbp+var_20], 9ECh
0x18001ff86  mov     r8, r13; unsigned __int16 *
0x18001ff89  mov     rcx, [rdi+70h]; this
0x18001ff8d  mov     [rsp+70h+var_48], r12d; int
0x18001ff92  cdq
0x18001ff93  idiv    r14d
0x18001ff96  mov     rdx, [rbp+var_18]; struct IXMLDOMElement *
0x18001ff9a  lea     r9d, [rax+rax*4]
0x18001ff9e  add     r9d, r9d
0x18001ffa1  mov     [rsp+70h+var_50], r9d; int
0x18001ffa6  lea     r9, aExtentheight; "ExtentHeight"
0x18001ffad  call    ?CreateProperty@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBG1HHPEAPEAU3@@Z; NPrintTicketUtil::CPrintTicketWrapper::CreateProperty(IXMLDOMElement *,ushort const *,ushort const *,int,int,IXMLDOMElement * *)
0x18001ffb2  mov     ebx, eax
0x18001ffb4  lea     rcx, [rbp+var_18]
0x18001ffb8  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ffbd  lea     rcx, [rbp+var_10]
0x18001ffc1  call    ?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)
0x18001ffc6  test    rsi, rsi
0x18001ffc9  jz      short loc_18001FFD4
0x18001ffcb  mov     rcx, rsi; hdc
0x18001ffce  call    cs:__imp_DeleteDC
0x18001ffd4  mov     eax, ebx
0x18001ffd6  mov     rbx, [rsp+70h+arg_0]
0x18001ffde  add     rsp, 70h
0x18001ffe2  pop     r15
0x18001ffe4  pop     r14
0x18001ffe6  pop     r13
0x18001ffe8  pop     r12
0x18001ffea  pop     rdi
0x18001ffeb  pop     rsi
0x18001ffec  pop     rbp
0x18001ffed  retn
```
