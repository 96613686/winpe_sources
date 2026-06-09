# CCcs::Include(ushort,long &)

- ea: `0x180033b90`
- end: `0x180034059`
- name: `?Include@CCcs@@QEAAHGAEAJ@Z`
- size: `1225`
- prototype: `__int64 __fastcall(CCcs *__hidden this, unsigned __int16, int *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d670`
- `0x1800124f0`
- `0x180021160`
- `0x18004b680`

## callees

- `0x180033af0`
- `0x180033b90`
- `0x180034060`
- `0x18003b4e0`
- `0x1800475c4`
- `0x18008d830`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180033eec`
- `KERNEL32!WideCharToMultiByte` at `0x180033eec`
- `GDI32!GetDeviceCaps` at `0x180033fd5`
- `GDI32!GetDeviceCaps` at `0x180033fd5`
- `GDI32!DeleteObject` at `0x180033df3`
- `GDI32!DeleteObject` at `0x180033df3`
- `GDI32!GetStockObject` at `0x180033f35`
- `GDI32!GetStockObject` at `0x180033f35`
- `GDI32!SelectObject` at `0x180033cba`
- `GDI32!SelectObject` at `0x180033d5a`
- `GDI32!SelectObject` at `0x180033de9`
- `GDI32!SelectObject` at `0x180033f41`
- `GDI32!SelectObject` at `0x180033f92`
- `GDI32!SelectObject` at `0x180033cba`
- `GDI32!SelectObject` at `0x180033d5a`
- `GDI32!SelectObject` at `0x180033de9`
- `GDI32!SelectObject` at `0x180033f41`
- `GDI32!SelectObject` at `0x180033f92`
- `GDI32!GetCharWidthW` at `0x180033dc5`
- `GDI32!GetCharWidthW` at `0x180033e93`
- `GDI32!GetCharWidthW` at `0x180033dc5`
- `GDI32!GetCharWidthW` at `0x180033e93`
- `GDI32!GetCharWidthA` at `0x180033d29`
- `GDI32!GetCharWidthA` at `0x180033f11`
- `GDI32!GetCharWidthA` at `0x180033d29`
- `GDI32!GetCharWidthA` at `0x180033f11`

## pseudocode

```c
__int64 __fastcall CCcs::Include(CCcs *this, unsigned __int16 a2, int *a3)
{
  unsigned int v3; // ebx
  __int16 *v4; // rdi
  unsigned int v7; // r14d
  __int64 v8; // r13
  _WORD *v9; // rdx
  int v10; // eax
  BOOL v11; // r12d
  char *v13; // rcx
  int v14; // ecx
  HGDIOBJ v15; // r12
  UINT v16; // r8d
  __int16 v17; // cx
  HDC v18; // r10
  UINT v19; // edx
  __int64 v20; // rax
  __int64 v21; // rcx
  _WORD *v22; // rdi
  WCHAR v23; // cx
  __int16 v24; // ax
  HDC v25; // r13
  __int16 *v26; // rdi
  int v27; // eax
  unsigned __int16 v28; // cx
  HGDIOBJ StockObject; // rax
  int DeviceCaps; // eax
  int cbMultiByte; // [rsp+28h] [rbp-A1h]
  WCHAR WideCharStr; // [rsp+40h] [rbp-89h] BYREF
  UINT iLast; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 MultiByteStr; // [rsp+4Ch] [rbp-7Dh] BYREF
  __int16 v35; // [rsp+50h] [rbp-79h]
  HDC hdc; // [rsp+58h] [rbp-71h] BYREF
  UINT CodePage; // [rsp+60h] [rbp-69h]
  int v38; // [rsp+64h] [rbp-65h]
  HGDIOBJ h; // [rsp+68h] [rbp-61h]
  HGDIOBJ ho; // [rsp+70h] [rbp-59h]
  struct tagLOGFONTW v41; // [rsp+80h] [rbp-49h] BYREF

  v3 = a2;
  v4 = (__int16 *)((char *)this + 16);
  iLast = a2;
  if ( a2 < 0x4E00u || (unsigned int)a2 - 19968 > 0x51FF && (unsigned int)a2 - 63744 > 0x1FF )
  {
    v7 = 0;
    v8 = a2;
    v9 = (_WORD *)(*((_QWORD *)this + 6) + 4 * (a2 & (unsigned __int64)*(int *)v4));
    if ( (_WORD)v3 == *v9 && (v10 = (__int16)v9[1], v9[1]) )
    {
      v11 = 1;
    }
    else
    {
      v11 = 0;
      v10 = 0;
    }
    *a3 = v10;
    if ( !*((_DWORD *)this + 8) )
    {
      ++*((_DWORD *)this + 7);
      if ( v11 )
        return 1;
      if ( v9[1] )
        ++*((_DWORD *)this + 6);
      else
        ++*((_DWORD *)this + 5);
      if ( *((int *)this + 7) >= 64 )
        CWidthCache::CheckPerformance((CWidthCache *)v4);
    }
  }
  else
  {
    if ( (unsigned int)a2 - 44032 <= 0x2BFF )
      v13 = (char *)this + 36;
    else
      v13 = (char *)this + 38;
    v14 = *(__int16 *)v13;
    v7 = 0;
    *a3 = v14;
    iLast = a2;
    v11 = (_WORD)v14 != 0;
    v8 = a2;
  }
  if ( v11 )
    return 1;
  v15 = SelectObject(*((HDC *)this + 8), *((HGDIOBJ *)this + 9));
  if ( v15 )
  {
    v16 = *((unsigned __int16 *)this + 58);
    v17 = *((_WORD *)this + 48);
    v18 = (HDC)*((_QWORD *)this + 8);
    v19 = iLast;
    CodePage = v16;
    v35 = v17;
    hdc = v18;
    if ( (unsigned __int16)v3 >= 0x4E00u && (iLast - 19968 <= 0x51FF || iLast - 63744 <= 0x1FF) )
    {
      if ( iLast - 44032 > 0x2B9F )
        v26 = v4 + 11;
      else
        v26 = v4 + 10;
      CW32System::REGetCharWidth(v18, v3, v26, v16, v17, cbMultiByte);
      v24 = *v26;
      goto LABEL_23;
    }
    v20 = *((_QWORD *)v4 + 4);
    v21 = v8 & *(int *)v4;
    *(_WORD *)(v20 + 4 * v21 + 2) = 0;
    WideCharStr = v3;
    iLast = 0;
    v22 = (_WORD *)(v20 + 4 * v21);
    v23 = v3;
    if ( v16 == 42 || v3 <= 0x7F )
    {
      if ( GetCharWidthA(v18, v19, v19, (LPINT)&iLast) )
        goto LABEL_21;
      v23 = WideCharStr;
      v18 = hdc;
    }
    v38 = 0;
    ho = 0;
    h = 0;
    if ( v23 == 8364 )
    {
      DeviceCaps = GetDeviceCaps(v18, 2);
      v25 = hdc;
      if ( DeviceCaps != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(hdc) )
      {
        v38 = 1;
        StockObject = GetStockObject(12);
        h = SelectObject(v25, StockObject);
        memset_0(&v41, 0, sizeof(v41));
        CW32System::GetObjectW(h, 92, &v41);
        if ( CW32System::_dwPlatformId == 1 )
          v41.lfOutPrecision = 7;
        else
          v41.lfOutPrecision = 9;
        ho = CW32System::CreateFontIndirect(&v41);
        SelectObject(v25, ho);
        v23 = WideCharStr;
      }
      else
      {
        v23 = WideCharStr;
      }
    }
    else
    {
      v25 = hdc;
    }
    if ( CW32System::_dwPlatformId != 1
      || CW32System::_dwMajorVersion != 4
      || CW32System::_dwMinorVersion
      || (unsigned int)v23 - 128 <= 0x7F
      || CodePage != 950 && CodePage != 936 )
    {
      goto LABEL_30;
    }
    GetCharWidthW(v25, 0x4E00u, 0x4E00u, (LPINT)&iLast);
    v22[1] = iLast;
    if ( (unsigned int)WideCharStr - 19968 <= 0x51FF )
    {
LABEL_22:
      v22[1] -= v35;
      v24 = v22[1];
      *v22 = v3;
LABEL_23:
      *a3 = v24;
      SelectObject(*((HDC *)this + 8), v15);
      return 1;
    }
    LODWORD(hdc) = 0;
    v27 = WideCharToMultiByte(CodePage, 0, &WideCharStr, 1, (LPSTR)&MultiByteStr, 2, 0, (LPBOOL)&hdc);
    v28 = (unsigned __int8)MultiByteStr;
    if ( v27 == 2 )
    {
      v28 = _byteswap_ushort(MultiByteStr);
    }
    else if ( v27 <= 0 )
    {
LABEL_51:
      v23 = WideCharStr;
LABEL_30:
      if ( v23 == 0xFFFF )
      {
        v23 = -2;
        WideCharStr = -2;
      }
      if ( GetCharWidthW(v25, v23, v23, (LPINT)&iLast) )
        v22[1] = iLast;
      if ( v38 )
      {
        SelectObject(v25, h);
        DeleteObject(ho);
      }
      goto LABEL_22;
    }
    if ( !GetCharWidthA(v25, v28, v28, (LPINT)&iLast) )
      goto LABEL_51;
LABEL_21:
    v22[1] = iLast;
    goto LABEL_22;
  }
  return v7;
}

```

## disassembly

```asm
0x180033b90  mov     [rsp-8+arg_18], rbx
0x180033b95  push    rbp
0x180033b96  push    rsi
0x180033b97  push    rdi
0x180033b98  push    r12
0x180033b9a  push    r13
0x180033b9c  push    r14
0x180033b9e  push    r15
0x180033ba0  lea     rbp, [rsp-27h]
0x180033ba5  sub     rsp, 0F0h
0x180033bac  mov     rax, cs:__security_cookie
0x180033bb3  xor     rax, rsp
0x180033bb6  mov     [rbp+57h+var_40], rax
0x180033bba  movzx   ebx, dx
0x180033bbd  lea     rdi, [rcx+10h]
0x180033bc1  mov     eax, 4E00h
0x180033bc6  mov     [rsp+120h+iLast], ebx
0x180033bca  mov     r15, r8
0x180033bcd  mov     rsi, rcx
0x180033bd0  cmp     bx, ax
0x180033bd3  jnb     loc_180033C69
0x180033bd9  mov     rax, [rdi+20h]
0x180033bdd  xor     r14d, r14d
0x180033be0  movsxd  rcx, dword ptr [rdi]
0x180033be3  mov     r13, rbx
0x180033be6  and     rcx, rbx
0x180033be9  lea     rdx, [rax+rcx*4]
0x180033bed  cmp     bx, [rax+rcx*4]
0x180033bf1  jnz     loc_180033D6E
0x180033bf7  movsx   eax, word ptr [rdx+2]
0x180033bfb  test    ax, ax
0x180033bfe  jz      loc_180033D6E
0x180033c04  mov     r12d, 1
0x180033c0a  mov     [r8], eax
0x180033c0d  cmp     [rdi+10h], r14d
0x180033c11  jnz     loc_180033CA9
0x180033c17  inc     dword ptr [rdi+0Ch]
0x180033c1a  test    r12d, r12d
0x180033c1d  jz      short loc_180033C4B
0x180033c1f  mov     eax, 1
0x180033c24  mov     rcx, [rbp+57h+var_40]
0x180033c28  xor     rcx, rsp; StackCookie
0x180033c2b  call    __security_check_cookie
0x180033c30  mov     rbx, [rsp+120h+arg_18]
0x180033c38  add     rsp, 0F0h
0x180033c3f  pop     r15
0x180033c41  pop     r14
0x180033c43  pop     r13
0x180033c45  pop     r12
0x180033c47  pop     rdi
0x180033c48  pop     rsi
0x180033c49  pop     rbp
0x180033c4a  retn
0x180033c4b  cmp     r14w, [rdx+2]
0x180033c50  jz      loc_180033E49
0x180033c56  inc     dword ptr [rdi+8]
0x180033c59  cmp     dword ptr [rdi+0Ch], 40h ; '@'
0x180033c5d  jl      short loc_180033CA9
0x180033c5f  mov     rcx, rdi; this
0x180033c62  call    ?CheckPerformance@CWidthCache@@AEAAXXZ; CWidthCache::CheckPerformance(void)
0x180033c67  jmp     short loc_180033CA9
0x180033c69  lea     eax, [rbx-4E00h]
0x180033c6f  cmp     eax, 51FFh
0x180033c74  ja      loc_180033E33
0x180033c7a  lea     eax, [rbx-0AC00h]
0x180033c80  cmp     eax, 2BFFh
0x180033c85  jbe     loc_180033FA2
0x180033c8b  lea     rcx, [rdi+16h]
0x180033c8f  movsx   ecx, word ptr [rcx]
0x180033c92  xor     r14d, r14d
0x180033c95  test    cx, cx
0x180033c98  mov     [r8], ecx
0x180033c9b  mov     r12d, r14d
0x180033c9e  mov     [rsp+120h+iLast], ebx
0x180033ca2  setnz   r12b
0x180033ca6  mov     r13, rbx
0x180033ca9  test    r12d, r12d
0x180033cac  jnz     loc_180033C1F
0x180033cb2  mov     rdx, [rsi+48h]; h
0x180033cb6  mov     rcx, [rsi+40h]; hdc
0x180033cba  call    cs:__imp_SelectObject
0x180033cc0  mov     r12, rax
0x180033cc3  test    rax, rax
0x180033cc6  jz      loc_180033D66
0x180033ccc  movzx   r8d, word ptr [rsi+74h]
0x180033cd1  mov     edx, 4E00h
0x180033cd6  movzx   ecx, word ptr [rsi+60h]
0x180033cda  cmp     bx, dx
0x180033cdd  mov     r10, [rsi+40h]
0x180033ce1  mov     edx, [rsp+120h+iLast]; iFirst
0x180033ce5  mov     [rbp+57h+CodePage], r8d
0x180033ce9  mov     [rbp+57h+var_D0], cx
0x180033ced  mov     [rbp+57h+hdc], r10
0x180033cf1  jnb     loc_180033E0C
0x180033cf7  movsxd  rcx, dword ptr [rdi]
0x180033cfa  mov     rax, [rdi+20h]
0x180033cfe  and     rcx, r13
0x180033d01  mov     [rax+rcx*4+2], r14w
0x180033d07  mov     [rsp+120h+WideCharStr], bx
0x180033d0c  mov     [rsp+120h+iLast], r14d
0x180033d11  lea     rdi, [rax+rcx*4]
0x180033d15  movzx   ecx, bx
0x180033d18  cmp     r8d, 2Ah ; '*'
0x180033d1c  jnz     short loc_180033D79
0x180033d1e  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180033d23  mov     r8d, edx; iLast
0x180033d26  mov     rcx, r10; hdc
0x180033d29  call    cs:__imp_GetCharWidthA
0x180033d2f  test    eax, eax
0x180033d31  jz      loc_180033DFE
0x180033d37  movzx   eax, word ptr [rsp+120h+iLast]
0x180033d3c  mov     [rdi+2], ax
0x180033d40  movzx   eax, [rbp+57h+var_D0]
0x180033d44  sub     [rdi+2], ax
0x180033d48  movzx   eax, word ptr [rdi+2]
0x180033d4c  mov     [rdi], bx
0x180033d4f  cwde
0x180033d50  mov     rdx, r12; h
0x180033d53  mov     [r15], eax
0x180033d56  mov     rcx, [rsi+40h]; hdc
0x180033d5a  call    cs:__imp_SelectObject
0x180033d60  mov     r14d, 1
0x180033d66  mov     eax, r14d
0x180033d69  jmp     loc_180033C24
0x180033d6e  mov     r12d, r14d
0x180033d71  mov     eax, r14d
0x180033d74  jmp     loc_180033C0A
0x180033d79  cmp     ebx, 7Fh
0x180033d7c  jbe     short loc_180033D1E
0x180033d7e  mov     eax, 20ACh
0x180033d83  mov     [rbp+57h+var_BC], r14d
0x180033d87  mov     [rbp+57h+ho], r14
0x180033d8b  mov     [rbp+57h+h], r14
0x180033d8f  cmp     cx, ax
0x180033d92  jz      loc_180033FCD
0x180033d98  mov     r13, [rbp+57h+hdc]
0x180033d9c  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180033da3  jz      loc_18003400B
0x180033da9  mov     eax, 0FFFFh
0x180033dae  cmp     cx, ax
0x180033db1  jz      loc_18003404A
0x180033db7  movzx   edx, cx; iFirst
0x180033dba  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180033dbf  mov     r8d, edx; iLast
0x180033dc2  mov     rcx, r13; hdc
0x180033dc5  call    cs:__imp_GetCharWidthW
0x180033dcb  test    eax, eax
0x180033dcd  jz      short loc_180033DD8
0x180033dcf  movzx   eax, word ptr [rsp+120h+iLast]
0x180033dd4  mov     [rdi+2], ax
0x180033dd8  cmp     [rbp+57h+var_BC], 0
0x180033ddc  jz      loc_180033D40
0x180033de2  mov     rdx, [rbp+57h+h]; h
0x180033de6  mov     rcx, r13; hdc
0x180033de9  call    cs:__imp_SelectObject
0x180033def  mov     rcx, [rbp+57h+ho]; ho
0x180033df3  call    cs:__imp_DeleteObject
0x180033df9  jmp     loc_180033D40
0x180033dfe  movzx   ecx, [rsp+120h+WideCharStr]
0x180033e03  mov     r10, [rbp+57h+hdc]
0x180033e07  jmp     loc_180033D7E
0x180033e0c  lea     eax, [rdx-4E00h]
0x180033e12  cmp     eax, 51FFh
0x180033e17  ja      short loc_180033E51
0x180033e19  lea     eax, [rdx-0AC00h]
0x180033e1f  cmp     eax, 2B9Fh
0x180033e24  ja      loc_180033FAB
0x180033e2a  add     rdi, 14h
0x180033e2e  jmp     loc_180033FAF
0x180033e33  lea     eax, [rbx-0F900h]
0x180033e39  cmp     eax, 1FFh
0x180033e3e  ja      loc_180033BD9
0x180033e44  jmp     loc_180033C7A
0x180033e49  inc     dword ptr [rdi+4]
0x180033e4c  jmp     loc_180033C59
0x180033e51  lea     eax, [rdx-0F900h]
0x180033e57  cmp     eax, 1FFh
0x180033e5c  ja      loc_180033CF7
0x180033e62  jmp     short loc_180033E19
0x180033e64  movzx   eax, cx
0x180033e67  add     eax, 0FFFFFF80h
0x180033e6a  cmp     eax, 7Fh
0x180033e6d  jbe     loc_180033DA9
0x180033e73  mov     eax, [rbp+57h+CodePage]
0x180033e76  cmp     eax, 3B6h
0x180033e7b  jnz     loc_18003402A
0x180033e81  mov     eax, 4E00h
0x180033e86  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180033e8b  mov     r8d, eax; iLast
0x180033e8e  mov     edx, eax; iFirst
0x180033e90  mov     rcx, r13; hdc
0x180033e93  call    cs:__imp_GetCharWidthW
0x180033e99  movzx   eax, word ptr [rsp+120h+iLast]
0x180033e9e  mov     edx, 4E00h
0x180033ea3  mov     [rdi+2], ax
0x180033ea7  movzx   eax, [rsp+120h+WideCharStr]
0x180033eac  sub     eax, edx
0x180033eae  cmp     eax, 51FFh
0x180033eb3  jbe     loc_180033D40
0x180033eb9  mov     ecx, [rbp+57h+CodePage]; CodePage
0x180033ebc  lea     rax, [rbp+57h+hdc]
0x180033ec0  mov     [rsp+120h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180033ec5  lea     r8, [rsp+120h+WideCharStr]; lpWideCharStr
0x180033eca  mov     [rsp+120h+lpDefaultChar], r14; lpDefaultChar
0x180033ecf  lea     rax, [rbp+57h+MultiByteStr]
0x180033ed3  mov     [rsp+120h+cbMultiByte], 2; cbMultiByte
0x180033edb  mov     r9d, 1; cchWideChar
0x180033ee1  xor     edx, edx; dwFlags
0x180033ee3  mov     [rsp+120h+lpMultiByteStr], rax; lpMultiByteStr
0x180033ee8  mov     dword ptr [rbp+57h+hdc], r14d
0x180033eec  call    cs:__imp_WideCharToMultiByte
0x180033ef2  movzx   ecx, byte ptr [rbp+57h+MultiByteStr]
0x180033ef6  cmp     eax, 2
0x180033ef9  jz      loc_18003403A
0x180033eff  test    eax, eax
0x180033f01  jle     short loc_180033F1F
0x180033f03  movzx   edx, cx; iFirst
0x180033f06  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180033f0b  mov     r8d, edx; iLast
0x180033f0e  mov     rcx, r13; hdc
0x180033f11  call    cs:__imp_GetCharWidthA
0x180033f17  test    eax, eax
0x180033f19  jnz     loc_180033D37
0x180033f1f  movzx   ecx, [rsp+120h+WideCharStr]
0x180033f24  jmp     loc_180033DA9
0x180033f29  mov     ecx, 0Ch; i
0x180033f2e  mov     [rbp+57h+var_BC], 1
0x180033f35  call    cs:__imp_GetStockObject
0x180033f3b  mov     rdx, rax; h
0x180033f3e  mov     rcx, r13; hdc
0x180033f41  call    cs:__imp_SelectObject
0x180033f47  xor     edx, edx; Val
0x180033f49  lea     rcx, [rbp+57h+var_A0]; void *
0x180033f4d  mov     r8d, 5Ch ; '\'; Size
0x180033f53  mov     [rbp+57h+h], rax
0x180033f57  call    memset_0
0x180033f5c  mov     rcx, [rbp+57h+h]; void *
0x180033f60  lea     r8, [rbp+57h+var_A0]; void *
0x180033f64  mov     edx, 5Ch ; '\'; int
0x180033f69  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x180033f6e  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180033f75  jz      loc_180034002
0x180033f7b  mov     [rbp+57h+var_A0.lfOutPrecision], 9
0x180033f7f  lea     rcx, [rbp+57h+var_A0]; struct tagLOGFONTW *
0x180033f83  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x180033f88  mov     rdx, rax; h
0x180033f8b  mov     [rbp+57h+ho], rax
0x180033f8f  mov     rcx, r13; hdc
0x180033f92  call    cs:__imp_SelectObject
0x180033f98  movzx   ecx, [rsp+120h+WideCharStr]
0x180033f9d  jmp     loc_180033D9C
0x180033fa2  lea     rcx, [rdi+14h]
0x180033fa6  jmp     loc_180033C8F
0x180033fab  add     rdi, 16h
0x180033faf  mov     word ptr [rsp+120h+lpMultiByteStr], cx; __int16
0x180033fb4  mov     r9d, r8d; unsigned int
0x180033fb7  mov     r8, rdi; __int16 *
0x180033fba  mov     rcx, r10; hdc
0x180033fbd  movzx   edx, bx; unsigned __int16
0x180033fc0  call    ?REGetCharWidth@CW32System@@SAXPEAUHDC__@@GPEAFIFH@Z; CW32System::REGetCharWidth(HDC__ *,ushort,short *,uint,short,int)
0x180033fc5  movzx   eax, word ptr [rdi]
0x180033fc8  jmp     loc_180033D4F
0x180033fcd  mov     edx, 2; index
0x180033fd2  mov     rcx, r10; hdc
0x180033fd5  call    cs:__imp_GetDeviceCaps
0x180033fdb  mov     r13, [rbp+57h+hdc]
0x180033fdf  cmp     eax, 1
0x180033fe2  jnz     loc_180033F29
0x180033fe8  mov     rcx, r13; hdc
0x180033feb  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x180033ff0  test    eax, eax
0x180033ff2  jnz     loc_180033F29
0x180033ff8  movzx   ecx, [rsp+120h+WideCharStr]
0x180033ffd  jmp     loc_180033D9C
0x180034002  mov     [rbp+57h+var_A0.lfOutPrecision], 7
0x180034006  jmp     loc_180033F7F
0x18003400b  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180034012  jnz     loc_180033DA9
0x180034018  cmp     cs:?_dwMinorVersion@CW32System@@2KA, 0; ulong CW32System::_dwMinorVersion
0x18003401f  jnz     loc_180033DA9
0x180034025  jmp     loc_180033E64
0x18003402a  cmp     eax, 3A8h
0x18003402f  jnz     loc_180033DA9
0x180034035  jmp     loc_180033E81
0x18003403a  movzx   eax, byte ptr [rbp+57h+MultiByteStr+1]
0x18003403e  shl     cx, 8
0x180034042  or      cx, ax
0x180034045  jmp     loc_180033F03
0x18003404a  mov     ecx, 0FFFEh
0x18003404f  mov     [rsp+120h+WideCharStr], cx
0x180034054  jmp     loc_180033DB7
```
