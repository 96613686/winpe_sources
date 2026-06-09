# CCcs::FillWidth(ushort,long &)

- ea: `0x180024d88`
- end: `0x180025196`
- name: `?FillWidth@CCcs@@AEAAHGAEAJ@Z`
- size: `1038`
- prototype: `__int64 __fastcall(CCcs *__hidden this, unsigned __int16, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180024580`

## callees

- `0x180024d88`
- `0x18002e7e4`
- `0x18003c080`
- `0x1800486b0`
- `0x180090024`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180025041`
- `KERNEL32!WideCharToMultiByte` at `0x180025041`
- `GDI32!GetDeviceCaps` at `0x180025097`
- `GDI32!GetDeviceCaps` at `0x180025097`
- `GDI32!DeleteObject` at `0x180024f42`
- `GDI32!DeleteObject` at `0x180024f42`
- `GDI32!GetStockObject` at `0x1800250c4`
- `GDI32!GetStockObject` at `0x1800250c4`
- `GDI32!SelectObject` at `0x180024dc5`
- `GDI32!SelectObject` at `0x180024e80`
- `GDI32!SelectObject` at `0x180024f33`
- `GDI32!SelectObject` at `0x1800250d6`
- `GDI32!SelectObject` at `0x180025130`
- `GDI32!SelectObject` at `0x180024dc5`
- `GDI32!SelectObject` at `0x180024e80`
- `GDI32!SelectObject` at `0x180024f33`
- `GDI32!SelectObject` at `0x1800250d6`
- `GDI32!SelectObject` at `0x180025130`
- `GDI32!GetCharWidthW` at `0x180024f08`
- `GDI32!GetCharWidthW` at `0x180024fdc`
- `GDI32!GetCharWidthW` at `0x180024f08`
- `GDI32!GetCharWidthW` at `0x180024fdc`
- `GDI32!GetCharWidthA` at `0x180024e3e`
- `GDI32!GetCharWidthA` at `0x18002506c`
- `GDI32!GetCharWidthA` at `0x180024e3e`
- `GDI32!GetCharWidthA` at `0x18002506c`

## pseudocode

```c
__int64 __fastcall CCcs::FillWidth(CCcs *this, unsigned __int16 a2, int *a3)
{
  __int64 v3; // r14
  void *v5; // rdx
  HDC v6; // rcx
  __int64 result; // rax
  __int16 v8; // cx
  unsigned int v9; // r12d
  HDC v10; // r15
  __int64 v11; // rsi
  __int64 v12; // rbx
  WCHAR v13; // cx
  __int16 v14; // ax
  HFONT v15; // r13
  __int16 *v16; // rbx
  int v17; // eax
  unsigned __int16 v18; // cx
  HGDIOBJ StockObject; // rax
  HGDIOBJ v20; // r13
  BYTE v21; // cl
  int cbMultiByte; // [rsp+28h] [rbp-A1h]
  WCHAR WideCharStr; // [rsp+40h] [rbp-89h] BYREF
  int Buffer; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 MultiByteStr; // [rsp+4Ch] [rbp-7Dh] BYREF
  __int16 v26; // [rsp+50h] [rbp-79h]
  int v27; // [rsp+54h] [rbp-75h]
  BOOL UsedDefaultChar; // [rsp+58h] [rbp-71h] BYREF
  HGDIOBJ v29; // [rsp+60h] [rbp-69h]
  int *v30; // [rsp+68h] [rbp-61h]
  HGDIOBJ h; // [rsp+70h] [rbp-59h]
  struct tagLOGFONTW v32; // [rsp+80h] [rbp-49h] BYREF

  v3 = a2;
  v5 = (void *)*((_QWORD *)this + 9);
  v6 = (HDC)*((_QWORD *)this + 8);
  v30 = a3;
  result = (__int64)SelectObject(v6, v5);
  h = (HGDIOBJ)result;
  if ( result )
  {
    v8 = *((_WORD *)this + 48);
    v9 = *((unsigned __int16 *)this + 58);
    v10 = (HDC)*((_QWORD *)this + 8);
    v26 = v8;
    if ( (unsigned __int16)v3 >= 0x4E00u
      && ((unsigned int)(v3 - 19968) <= 0x51FF || (unsigned int)(v3 - 63744) <= 0x1FF) )
    {
      v16 = (__int16 *)((char *)this + 36);
      if ( (unsigned int)(v3 - 44032) > 0x2B9F )
        v16 = (__int16 *)((char *)this + 38);
      CW32System::REGetCharWidth(v10, v3, v16, v9, v8, cbMultiByte);
      v14 = *v16;
      goto LABEL_7;
    }
    v11 = *((_QWORD *)this + 6);
    v12 = v3 & *((int *)this + 4);
    Buffer = 0;
    v13 = v3;
    WideCharStr = v3;
    *(_WORD *)(v11 + 4 * v12 + 2) = 0;
    if ( v9 == 42 || (unsigned __int16)v3 <= 0x7Fu )
    {
      if ( GetCharWidthA(v10, v3, v3, &Buffer) )
        goto LABEL_5;
      v13 = WideCharStr;
    }
    v15 = 0;
    v27 = 0;
    v29 = 0;
    if ( v13 == 8364 )
    {
      if ( GetDeviceCaps(v10, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(v10) )
      {
        v27 = 1;
        StockObject = GetStockObject(12);
        v20 = SelectObject(v10, StockObject);
        v29 = v20;
        memset_0(&v32, 0, sizeof(v32));
        CW32System::GetObjectW(v20, 92, &v32);
        v21 = 9;
        if ( CW32System::_dwPlatformId == 1 )
          v21 = 7;
        v32.lfOutPrecision = v21;
        v15 = CW32System::CreateFontIndirect(&v32);
        SelectObject(v10, v15);
      }
      v13 = WideCharStr;
    }
    if ( CW32System::_dwPlatformId != 1
      || CW32System::_dwMajorVersion != 4
      || CW32System::_dwMinorVersion
      || (unsigned int)v13 - 128 <= 0x7F
      || v9 != 950 && v9 != 936 )
    {
      goto LABEL_11;
    }
    GetCharWidthW(v10, 0x4E00u, 0x4E00u, &Buffer);
    *(_WORD *)(v11 + 4 * v12 + 2) = Buffer;
    if ( (unsigned int)WideCharStr - 19968 <= 0x51FF )
    {
LABEL_6:
      *(_WORD *)(v11 + 4 * v12 + 2) -= v26;
      v14 = *(_WORD *)(v11 + 4 * v12 + 2);
      *(_WORD *)(v11 + 4 * v12) = v3;
LABEL_7:
      *v30 = v14;
      SelectObject(*((HDC *)this + 8), h);
      return 1;
    }
    UsedDefaultChar = 0;
    v17 = WideCharToMultiByte(v9, 0, &WideCharStr, 1, (LPSTR)&MultiByteStr, 2, 0, &UsedDefaultChar);
    v18 = (unsigned __int8)MultiByteStr;
    if ( v17 == 2 )
    {
      v18 = _byteswap_ushort(MultiByteStr);
    }
    else if ( v17 <= 0 )
    {
LABEL_29:
      v13 = WideCharStr;
LABEL_11:
      if ( v13 == 0xFFFF )
      {
        v13 = -2;
        WideCharStr = -2;
      }
      if ( GetCharWidthW(v10, v13, v13, &Buffer) )
        *(_WORD *)(v11 + 4 * v12 + 2) = Buffer;
      if ( v27 )
      {
        SelectObject(v10, v29);
        DeleteObject(v15);
      }
      goto LABEL_6;
    }
    if ( !GetCharWidthA(v10, v18, v18, &Buffer) )
      goto LABEL_29;
LABEL_5:
    *(_WORD *)(v11 + 4 * v12 + 2) = Buffer;
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x180024d88  mov     [rsp-8+arg_18], rbx
0x180024d8d  push    rbp
0x180024d8e  push    rsi
0x180024d8f  push    rdi
0x180024d90  push    r12
0x180024d92  push    r13
0x180024d94  push    r14
0x180024d96  push    r15
0x180024d98  lea     rbp, [rsp-27h]
0x180024d9d  sub     rsp, 0F0h
0x180024da4  mov     rax, cs:__security_cookie
0x180024dab  xor     rax, rsp
0x180024dae  mov     [rbp+57h+var_40], rax
0x180024db2  movzx   r14d, dx
0x180024db6  mov     rdi, rcx
0x180024db9  mov     rdx, [rcx+48h]; h
0x180024dbd  mov     rcx, [rcx+40h]; hdc
0x180024dc1  mov     [rbp+57h+var_B8], r8
0x180024dc5  call    cs:__imp_SelectObject
0x180024dcc  nop     dword ptr [rax+rax+00h]
0x180024dd1  mov     [rbp+57h+h], rax
0x180024dd5  test    rax, rax
0x180024dd8  jz      loc_18002508A
0x180024dde  movzx   ecx, word ptr [rdi+60h]
0x180024de2  mov     eax, 4E00h
0x180024de7  movzx   r12d, word ptr [rdi+74h]
0x180024dec  mov     edx, r14d; unsigned __int16
0x180024def  mov     r15, [rdi+40h]
0x180024df3  mov     [rbp+57h+var_D0], cx
0x180024df7  cmp     r14w, ax
0x180024dfb  jnb     loc_180024F5D
0x180024e01  movsxd  rbx, dword ptr [rdi+10h]
0x180024e05  xor     eax, eax
0x180024e07  mov     rsi, [rdi+30h]
0x180024e0b  and     rbx, r14
0x180024e0e  mov     [rsp+120h+Buffer], 0
0x180024e16  movzx   ecx, r14w
0x180024e1a  mov     [rsp+120h+WideCharStr], cx
0x180024e1f  mov     [rsi+rbx*4+2], ax
0x180024e24  mov     eax, 7Fh
0x180024e29  cmp     r12d, 2Ah ; '*'
0x180024e2d  jnz     loc_180024EB9
0x180024e33  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180024e38  mov     r8d, edx; iLast
0x180024e3b  mov     rcx, r15; hdc
0x180024e3e  call    cs:__imp_GetCharWidthA
0x180024e45  nop     dword ptr [rax+rax+00h]
0x180024e4a  test    eax, eax
0x180024e4c  jz      loc_180024F53
0x180024e52  movzx   eax, word ptr [rsp+120h+Buffer]
0x180024e57  mov     [rsi+rbx*4+2], ax
0x180024e5c  movzx   eax, [rbp+57h+var_D0]
0x180024e60  sub     [rsi+rbx*4+2], ax
0x180024e65  movzx   eax, word ptr [rsi+rbx*4+2]
0x180024e6a  mov     [rsi+rbx*4], r14w
0x180024e6f  mov     rdx, [rbp+57h+var_B8]
0x180024e73  movsx   ecx, ax
0x180024e76  mov     [rdx], ecx
0x180024e78  mov     rdx, [rbp+57h+h]; h
0x180024e7c  mov     rcx, [rdi+40h]; hdc
0x180024e80  call    cs:__imp_SelectObject
0x180024e87  nop     dword ptr [rax+rax+00h]
0x180024e8c  mov     eax, 1
0x180024e91  mov     rcx, [rbp+57h+var_40]
0x180024e95  xor     rcx, rsp; StackCookie
0x180024e98  call    __security_check_cookie
0x180024e9d  mov     rbx, [rsp+120h+arg_18]
0x180024ea5  add     rsp, 0F0h
0x180024eac  pop     r15
0x180024eae  pop     r14
0x180024eb0  pop     r13
0x180024eb2  pop     r12
0x180024eb4  pop     rdi
0x180024eb5  pop     rsi
0x180024eb6  pop     rbp
0x180024eb7  retn
0x180024eb9  cmp     r14w, ax
0x180024ebd  jbe     loc_180024E33
0x180024ec3  xor     r13d, r13d
0x180024ec6  mov     [rbp+57h+var_CC], 0
0x180024ecd  mov     eax, 20ACh
0x180024ed2  mov     [rbp+57h+var_C0], r13
0x180024ed6  cmp     cx, ax
0x180024ed9  jz      loc_18002508F
0x180024edf  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180024ee6  jz      loc_180025146
0x180024eec  mov     eax, 0FFFFh
0x180024ef1  cmp     cx, ax
0x180024ef4  jz      loc_180025187
0x180024efa  movzx   edx, cx; iFirst
0x180024efd  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180024f02  mov     r8d, edx; iLast
0x180024f05  mov     rcx, r15; hdc
0x180024f08  call    cs:__imp_GetCharWidthW
0x180024f0f  nop     dword ptr [rax+rax+00h]
0x180024f14  test    eax, eax
0x180024f16  jz      short loc_180024F22
0x180024f18  movzx   eax, word ptr [rsp+120h+Buffer]
0x180024f1d  mov     [rsi+rbx*4+2], ax
0x180024f22  cmp     [rbp+57h+var_CC], 0
0x180024f26  jz      loc_180024E5C
0x180024f2c  mov     rdx, [rbp+57h+var_C0]; h
0x180024f30  mov     rcx, r15; hdc
0x180024f33  call    cs:__imp_SelectObject
0x180024f3a  nop     dword ptr [rax+rax+00h]
0x180024f3f  mov     rcx, r13; ho
0x180024f42  call    cs:__imp_DeleteObject
0x180024f49  nop     dword ptr [rax+rax+00h]
0x180024f4e  jmp     loc_180024E5C
0x180024f53  movzx   ecx, [rsp+120h+WideCharStr]
0x180024f58  jmp     loc_180024EC3
0x180024f5d  lea     eax, [r14-4E00h]
0x180024f64  cmp     eax, 51FFh
0x180024f69  jbe     short loc_180024F7D
0x180024f6b  lea     eax, [r14-0F900h]
0x180024f72  cmp     eax, 1FFh
0x180024f77  ja      loc_180024E01
0x180024f7d  lea     eax, [r14-0AC00h]
0x180024f84  lea     rbx, [rdi+24h]
0x180024f88  cmp     eax, 2B9Fh
0x180024f8d  jbe     short loc_180024F93
0x180024f8f  lea     rbx, [rdi+26h]
0x180024f93  mov     word ptr [rsp+120h+lpMultiByteStr], cx; __int16
0x180024f98  mov     r9d, r12d; unsigned int
0x180024f9b  mov     rcx, r15; hdc
0x180024f9e  mov     r8, rbx; __int16 *
0x180024fa1  call    ?REGetCharWidth@CW32System@@SAXPEAUHDC__@@GPEAFIFH@Z; CW32System::REGetCharWidth(HDC__ *,ushort,short *,uint,short,int)
0x180024fa6  movzx   eax, word ptr [rbx]
0x180024fa9  jmp     loc_180024E6F
0x180024fae  movzx   eax, cx
0x180024fb1  add     eax, 0FFFFFF80h
0x180024fb4  cmp     eax, 7Fh
0x180024fb7  jbe     loc_180024EEC
0x180024fbd  cmp     r12d, 3B6h
0x180024fc4  jnz     loc_180025165
0x180024fca  mov     eax, 4E00h
0x180024fcf  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180024fd4  mov     r8d, eax; iLast
0x180024fd7  mov     edx, eax; iFirst
0x180024fd9  mov     rcx, r15; hdc
0x180024fdc  call    cs:__imp_GetCharWidthW
0x180024fe3  nop     dword ptr [rax+rax+00h]
0x180024fe8  movzx   eax, word ptr [rsp+120h+Buffer]
0x180024fed  mov     [rsi+rbx*4+2], ax
0x180024ff2  movzx   eax, [rsp+120h+WideCharStr]
0x180024ff7  sub     eax, 4E00h
0x180024ffc  cmp     eax, 51FFh
0x180025001  jbe     loc_180024E5C
0x180025007  lea     rax, [rbp+57h+UsedDefaultChar]
0x18002500b  mov     [rbp+57h+UsedDefaultChar], 0
0x180025012  mov     [rsp+120h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180025017  lea     r8, [rsp+120h+WideCharStr]; lpWideCharStr
0x18002501c  mov     [rsp+120h+lpDefaultChar], 0; lpDefaultChar
0x180025025  lea     rax, [rbp+57h+MultiByteStr]
0x180025029  mov     [rsp+120h+cbMultiByte], 2; cbMultiByte
0x180025031  mov     r9d, 1; cchWideChar
0x180025037  xor     edx, edx; dwFlags
0x180025039  mov     [rsp+120h+lpMultiByteStr], rax; lpMultiByteStr
0x18002503e  mov     ecx, r12d; CodePage
0x180025041  call    cs:__imp_WideCharToMultiByte
0x180025048  nop     dword ptr [rax+rax+00h]
0x18002504d  movzx   ecx, byte ptr [rbp+57h+MultiByteStr]
0x180025051  cmp     eax, 2
0x180025054  jz      loc_180025177
0x18002505a  test    eax, eax
0x18002505c  jle     short loc_180025080
0x18002505e  movzx   edx, cx; iFirst
0x180025061  lea     r9, [rsp+120h+Buffer]; lpBuffer
0x180025066  mov     r8d, edx; iLast
0x180025069  mov     rcx, r15; hdc
0x18002506c  call    cs:__imp_GetCharWidthA
0x180025073  nop     dword ptr [rax+rax+00h]
0x180025078  test    eax, eax
0x18002507a  jnz     loc_180024E52
0x180025080  movzx   ecx, [rsp+120h+WideCharStr]
0x180025085  jmp     loc_180024EEC
0x18002508a  jmp     loc_180024E91
0x18002508f  mov     edx, 2; index
0x180025094  mov     rcx, r15; hdc
0x180025097  call    cs:__imp_GetDeviceCaps
0x18002509e  nop     dword ptr [rax+rax+00h]
0x1800250a3  cmp     eax, 1
0x1800250a6  jnz     short loc_1800250B8
0x1800250a8  mov     rcx, r15; hdc
0x1800250ab  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x1800250b0  test    eax, eax
0x1800250b2  jz      loc_18002513C
0x1800250b8  mov     ecx, 0Ch; i
0x1800250bd  mov     [rbp+57h+var_CC], 1
0x1800250c4  call    cs:__imp_GetStockObject
0x1800250cb  nop     dword ptr [rax+rax+00h]
0x1800250d0  mov     rdx, rax; h
0x1800250d3  mov     rcx, r15; hdc
0x1800250d6  call    cs:__imp_SelectObject
0x1800250dd  nop     dword ptr [rax+rax+00h]
0x1800250e2  xor     edx, edx; Val
0x1800250e4  lea     rcx, [rbp+57h+var_A0]; void *
0x1800250e8  mov     r13, rax
0x1800250eb  mov     [rbp+57h+var_C0], rax
0x1800250ef  lea     r8d, [rdx+5Ch]; Size
0x1800250f3  call    memset_0
0x1800250f8  lea     r8, [rbp+57h+var_A0]; void *
0x1800250fc  mov     edx, 5Ch ; '\'; int
0x180025101  mov     rcx, r13; void *
0x180025104  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x180025109  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180025110  mov     ecx, 9
0x180025115  lea     eax, [rcx-2]
0x180025118  cmovz   ecx, eax
0x18002511b  mov     [rbp+57h+var_A0.lfOutPrecision], cl
0x18002511e  lea     rcx, [rbp+57h+var_A0]; struct tagLOGFONTW *
0x180025122  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x180025127  mov     rdx, rax; h
0x18002512a  mov     rcx, r15; hdc
0x18002512d  mov     r13, rax
0x180025130  call    cs:__imp_SelectObject
0x180025137  nop     dword ptr [rax+rax+00h]
0x18002513c  movzx   ecx, [rsp+120h+WideCharStr]
0x180025141  jmp     loc_180024EDF
0x180025146  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x18002514d  jnz     loc_180024EEC
0x180025153  cmp     cs:?_dwMinorVersion@CW32System@@2KA, 0; ulong CW32System::_dwMinorVersion
0x18002515a  jnz     loc_180024EEC
0x180025160  jmp     loc_180024FAE
0x180025165  cmp     r12d, 3A8h
0x18002516c  jnz     loc_180024EEC
0x180025172  jmp     loc_180024FCA
0x180025177  movzx   eax, byte ptr [rbp+57h+MultiByteStr+1]
0x18002517b  shl     cx, 8
0x18002517f  or      cx, ax
0x180025182  jmp     loc_18002505E
0x180025187  mov     ecx, 0FFFEh
0x18002518c  mov     [rsp+120h+WideCharStr], cx
0x180025191  jmp     loc_180024EFA
```
