# CThumbnailRequest::_CreateHBITMAPFromBitmapSource(IWICBitmapSource *,HBITMAP__ * *)

- ea: `0x180021118`
- end: `0x1800212b2`
- name: `?_CreateHBITMAPFromBitmapSource@CThumbnailRequest@@AEAAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(CThumbnailRequest *__hidden this, struct IWICBitmapSource *, HBITMAP *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180021770`

## callees

- `0x18000aea4`
- `0x180011930`
- `0x180021118`
- `0x180035010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1800211ce`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x1800211ce`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180021286`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180021286`

## pseudocode

```c
__int64 __fastcall CThumbnailRequest::_CreateHBITMAPFromBitmapSource(
        CThumbnailRequest *this,
        struct IWICBitmapSource *a2,
        HBITMAP *a3)
{
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetSize)(IWICBitmapSource *, UINT *, UINT *); // rax
  int v7; // ebx
  HBITMAP v8; // rdi
  __int64 v9; // r9
  unsigned int v11; // [rsp+30h] [rbp-19h] BYREF
  unsigned int v12; // [rsp+34h] [rbp-15h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-11h] BYREF
  unsigned int v14; // [rsp+3Ch] [rbp-Dh] BYREF
  void *ppvBits; // [rsp+40h] [rbp-9h] BYREF
  __int128 v16; // [rsp+48h] [rbp-1h] BYREF
  BITMAPINFO pbmi; // [rsp+58h] [rbp+Fh] BYREF

  lpVtbl = a2->lpVtbl;
  v11 = 0;
  v12 = 0;
  GetSize = lpVtbl->GetSize;
  v16 = 0;
  memset(&pbmi, 0, sizeof(pbmi));
  v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))GetSize)(a2, &v11, &v12);
  if ( v7 >= 0 )
  {
    pbmi.bmiHeader.biWidth = v11;
    pbmi.bmiHeader.biHeight = -v12;
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    ppvBits = 0;
    v8 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
    if ( !v8 )
      return (unsigned int)-2147024882;
    if ( v11 > 0x7FFFFFFF )
    {
      DWORD2(v16) = -1;
    }
    else
    {
      DWORD2(v16) = v11;
      if ( v12 <= 0x7FFFFFFF )
      {
        HIDWORD(v16) = v12;
        v13 = 0;
        v7 = ULongLongToUInt(4LL * v11, &v13);
        if ( v7 >= 0 )
        {
          v14 = 0;
          v7 = ULongLongToUInt(v9 * v13, &v14);
          if ( v7 >= 0 )
          {
            v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *, _QWORD, _QWORD, void *))a2->lpVtbl->CopyPixels)(
                   a2,
                   &v16,
                   v13,
                   v14,
                   ppvBits);
            if ( v7 >= 0 )
            {
              *a3 = v8;
              return (unsigned int)v7;
            }
          }
        }
LABEL_13:
        DeleteObject(v8);
        return (unsigned int)v7;
      }
      HIDWORD(v16) = -1;
    }
    v7 = -2147024362;
    goto LABEL_13;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021118  mov     [rsp-8+arg_0], rbx
0x18002111d  mov     [rsp-8+arg_18], rsi
0x180021122  push    rbp
0x180021123  push    rdi
0x180021124  push    r14
0x180021126  lea     rbp, [rsp-47h]
0x18002112b  sub     rsp, 90h
0x180021132  mov     rax, cs:__security_cookie
0x180021139  xor     rax, rsp
0x18002113c  mov     [rbp+57h+var_18], rax
0x180021140  mov     rax, [rdx]
0x180021143  xorps   xmm1, xmm1
0x180021146  mov     rsi, rdx
0x180021149  mov     [rbp+57h+var_70], 0
0x180021150  mov     r14, r8
0x180021153  mov     [rbp+57h+var_6C], 0
0x18002115a  xorps   xmm0, xmm0
0x18002115d  lea     r8, [rbp+57h+var_6C]
0x180021161  mov     rax, [rax+18h]
0x180021165  lea     rdx, [rbp+57h+var_70]
0x180021169  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biCompression], xmm1
0x18002116d  mov     rcx, rsi
0x180021170  movups  [rbp+57h+var_58], xmm0
0x180021174  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSize], xmm1
0x180021178  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], xmm1
0x18002117c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021181  mov     ebx, eax
0x180021183  test    eax, eax
0x180021185  js      loc_18002128C
0x18002118b  mov     eax, [rbp+57h+var_70]
0x18002118e  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180021192  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180021195  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180021199  mov     eax, [rbp+57h+var_6C]
0x18002119c  xor     r8d, r8d; usage
0x18002119f  neg     eax
0x1800211a1  mov     [rsp+0A0h+offset], 0; offset
0x1800211a9  xor     ecx, ecx; hdc
0x1800211ab  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1800211ae  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800211b5  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800211bd  mov     [rbp+57h+ppvBits], 0
0x1800211c5  mov     [rsp+0A0h+hSection], 0; hSection
0x1800211ce  call    cs:__imp_CreateDIBSection
0x1800211d4  mov     rdi, rax
0x1800211d7  test    rax, rax
0x1800211da  jnz     short loc_1800211E6
0x1800211dc  mov     ebx, 8007000Eh
0x1800211e1  jmp     loc_18002128C
0x1800211e6  mov     eax, [rbp+57h+var_70]
0x1800211e9  mov     ecx, 7FFFFFFFh
0x1800211ee  cmp     eax, ecx
0x1800211f0  ja      loc_180021277
0x1800211f6  mov     r9d, [rbp+57h+var_6C]
0x1800211fa  mov     dword ptr [rbp+57h+var_58+8], eax
0x1800211fd  cmp     r9d, ecx
0x180021200  ja      short loc_18002126E
0x180021202  mov     ecx, eax
0x180021204  mov     dword ptr [rbp+57h+var_58+0Ch], r9d
0x180021208  shl     rcx, 2; unsigned __int64
0x18002120c  lea     rdx, [rbp+57h+var_68]; unsigned int *
0x180021210  mov     [rbp+57h+var_68], 0
0x180021217  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18002121c  mov     ebx, eax
0x18002121e  test    eax, eax
0x180021220  js      short loc_180021283
0x180021222  mov     ecx, [rbp+57h+var_68]
0x180021225  lea     rdx, [rbp+57h+var_64]; unsigned int *
0x180021229  imul    rcx, r9; unsigned __int64
0x18002122d  mov     [rbp+57h+var_64], 0
0x180021234  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180021239  mov     ebx, eax
0x18002123b  test    eax, eax
0x18002123d  js      short loc_180021283
0x18002123f  mov     rdx, [rbp+57h+ppvBits]
0x180021243  mov     rcx, rsi
0x180021246  mov     rax, [rsi]
0x180021249  mov     r9d, [rbp+57h+var_64]
0x18002124d  mov     r8d, [rbp+57h+var_68]
0x180021251  mov     [rsp+0A0h+hSection], rdx
0x180021256  lea     rdx, [rbp+57h+var_58]
0x18002125a  mov     rax, [rax+38h]
0x18002125e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021263  mov     ebx, eax
0x180021265  test    eax, eax
0x180021267  js      short loc_180021283
0x180021269  mov     [r14], rdi
0x18002126c  jmp     short loc_18002128C
0x18002126e  mov     dword ptr [rbp+57h+var_58+0Ch], 0FFFFFFFFh
0x180021275  jmp     short loc_18002127E
0x180021277  mov     dword ptr [rbp+57h+var_58+8], 0FFFFFFFFh
0x18002127e  mov     ebx, 80070216h
0x180021283  mov     rcx, rdi; ho
0x180021286  call    cs:__imp_DeleteObject
0x18002128c  mov     eax, ebx
0x18002128e  mov     rcx, [rbp+57h+var_18]
0x180021292  xor     rcx, rsp; StackCookie
0x180021295  call    __security_check_cookie
0x18002129a  lea     r11, [rsp+0A0h+var_10]
0x1800212a2  mov     rbx, [r11+20h]
0x1800212a6  mov     rsi, [r11+38h]
0x1800212aa  mov     rsp, r11
0x1800212ad  pop     r14
0x1800212af  pop     rdi
0x1800212b0  pop     rbp
0x1800212b1  retn
```
