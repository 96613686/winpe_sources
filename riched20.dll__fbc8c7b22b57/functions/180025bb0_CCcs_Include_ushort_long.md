# CCcs::Include(ushort,long &)

- ea: `0x180025bb0`
- end: `0x1800260c8`
- name: `?Include@CCcs@@QEAAHGAEAJ@Z`
- size: `1304`
- prototype: `__int64 __fastcall(CCcs *__hidden this, unsigned __int16, int *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18000dad0`
- `0x1800112c0`
- `0x180024580`
- `0x18004c848`

## callees

- `0x180025bb0`
- `0x1800260d0`
- `0x18002e7e4`
- `0x18003c080`
- `0x1800486b0`
- `0x180090024`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180025f37`
- `KERNEL32!WideCharToMultiByte` at `0x180025f37`
- `GDI32!GetDeviceCaps` at `0x18002603e`
- `GDI32!GetDeviceCaps` at `0x18002603e`
- `GDI32!DeleteObject` at `0x180025e32`
- `GDI32!DeleteObject` at `0x180025e32`
- `GDI32!GetStockObject` at `0x180025f8c`
- `GDI32!GetStockObject` at `0x180025f8c`
- `GDI32!SelectObject` at `0x180025cdb`
- `GDI32!SelectObject` at `0x180025d87`
- `GDI32!SelectObject` at `0x180025e22`
- `GDI32!SelectObject` at `0x180025f9e`
- `GDI32!SelectObject` at `0x180025ff5`
- `GDI32!SelectObject` at `0x180025cdb`
- `GDI32!SelectObject` at `0x180025d87`
- `GDI32!SelectObject` at `0x180025e22`
- `GDI32!SelectObject` at `0x180025f9e`
- `GDI32!SelectObject` at `0x180025ff5`
- `GDI32!GetCharWidthW` at `0x180025df8`
- `GDI32!GetCharWidthW` at `0x180025ed8`
- `GDI32!GetCharWidthW` at `0x180025df8`
- `GDI32!GetCharWidthW` at `0x180025ed8`
- `GDI32!GetCharWidthA` at `0x180025d50`
- `GDI32!GetCharWidthA` at `0x180025f62`
- `GDI32!GetCharWidthA` at `0x180025d50`
- `GDI32!GetCharWidthA` at `0x180025f62`

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
0x180025bb0  mov     [rsp-8+arg_18], rbx
0x180025bb5  push    rbp
0x180025bb6  push    rsi
0x180025bb7  push    rdi
0x180025bb8  push    r12
0x180025bba  push    r13
0x180025bbc  push    r14
0x180025bbe  push    r15
0x180025bc0  lea     rbp, [rsp-27h]
0x180025bc5  sub     rsp, 0F0h
0x180025bcc  mov     rax, cs:__security_cookie
0x180025bd3  xor     rax, rsp
0x180025bd6  mov     [rbp+57h+var_40], rax
0x180025bda  movzx   ebx, dx
0x180025bdd  lea     rdi, [rcx+10h]
0x180025be1  mov     eax, 4E00h
0x180025be6  mov     [rsp+120h+iLast], ebx
0x180025bea  mov     r15, r8
0x180025bed  mov     rsi, rcx
0x180025bf0  cmp     bx, ax
0x180025bf3  jnb     loc_180025C8A
0x180025bf9  mov     rax, [rdi+20h]
0x180025bfd  xor     r14d, r14d
0x180025c00  movsxd  rcx, dword ptr [rdi]
0x180025c03  mov     r13, rbx
0x180025c06  and     rcx, rbx
0x180025c09  lea     rdx, [rax+rcx*4]
0x180025c0d  cmp     bx, [rax+rcx*4]
0x180025c11  jnz     loc_180025DA1
0x180025c17  movsx   eax, word ptr [rdx+2]
0x180025c1b  test    ax, ax
0x180025c1e  jz      loc_180025DA1
0x180025c24  mov     r12d, 1
0x180025c2a  mov     [r8], eax
0x180025c2d  cmp     [rdi+10h], r14d
0x180025c31  jnz     loc_180025CCA
0x180025c37  inc     dword ptr [rdi+0Ch]
0x180025c3a  test    r12d, r12d
0x180025c3d  jz      short loc_180025C6C
0x180025c3f  mov     eax, 1
0x180025c44  mov     rcx, [rbp+57h+var_40]
0x180025c48  xor     rcx, rsp; StackCookie
0x180025c4b  call    __security_check_cookie
0x180025c50  mov     rbx, [rsp+120h+arg_18]
0x180025c58  add     rsp, 0F0h
0x180025c5f  pop     r15
0x180025c61  pop     r14
0x180025c63  pop     r13
0x180025c65  pop     r12
0x180025c67  pop     rdi
0x180025c68  pop     rsi
0x180025c69  pop     rbp
0x180025c6a  retn
0x180025c6c  cmp     r14w, [rdx+2]
0x180025c71  jz      loc_180025E8E
0x180025c77  inc     dword ptr [rdi+8]
0x180025c7a  cmp     dword ptr [rdi+0Ch], 40h ; '@'
0x180025c7e  jl      short loc_180025CCA
0x180025c80  mov     rcx, rdi; this
0x180025c83  call    ?CheckPerformance@CWidthCache@@AEAAXXZ; CWidthCache::CheckPerformance(void)
0x180025c88  jmp     short loc_180025CCA
0x180025c8a  lea     eax, [rbx-4E00h]
0x180025c90  cmp     eax, 51FFh
0x180025c95  ja      loc_180025E78
0x180025c9b  lea     eax, [rbx-0AC00h]
0x180025ca1  cmp     eax, 2BFFh
0x180025ca6  jbe     loc_18002600B
0x180025cac  lea     rcx, [rdi+16h]
0x180025cb0  movsx   ecx, word ptr [rcx]
0x180025cb3  xor     r14d, r14d
0x180025cb6  test    cx, cx
0x180025cb9  mov     [r8], ecx
0x180025cbc  mov     r12d, r14d
0x180025cbf  mov     [rsp+120h+iLast], ebx
0x180025cc3  setnz   r12b
0x180025cc7  mov     r13, rbx
0x180025cca  test    r12d, r12d
0x180025ccd  jnz     loc_180025C3F
0x180025cd3  mov     rdx, [rsi+48h]; h
0x180025cd7  mov     rcx, [rsi+40h]; hdc
0x180025cdb  call    cs:__imp_SelectObject
0x180025ce2  nop     dword ptr [rax+rax+00h]
0x180025ce7  mov     r12, rax
0x180025cea  test    rax, rax
0x180025ced  jz      loc_180025D99
0x180025cf3  movzx   r8d, word ptr [rsi+74h]
0x180025cf8  mov     edx, 4E00h
0x180025cfd  movzx   ecx, word ptr [rsi+60h]
0x180025d01  cmp     bx, dx
0x180025d04  mov     r10, [rsi+40h]
0x180025d08  mov     edx, [rsp+120h+iLast]; iFirst
0x180025d0c  mov     [rbp+57h+CodePage], r8d
0x180025d10  mov     [rbp+57h+var_D0], cx
0x180025d14  mov     [rbp+57h+hdc], r10
0x180025d18  jnb     loc_180025E51
0x180025d1e  movsxd  rcx, dword ptr [rdi]
0x180025d21  mov     rax, [rdi+20h]
0x180025d25  and     rcx, r13
0x180025d28  mov     [rax+rcx*4+2], r14w
0x180025d2e  mov     [rsp+120h+WideCharStr], bx
0x180025d33  mov     [rsp+120h+iLast], r14d
0x180025d38  lea     rdi, [rax+rcx*4]
0x180025d3c  movzx   ecx, bx
0x180025d3f  cmp     r8d, 2Ah ; '*'
0x180025d43  jnz     short loc_180025DAC
0x180025d45  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180025d4a  mov     r8d, edx; iLast
0x180025d4d  mov     rcx, r10; hdc
0x180025d50  call    cs:__imp_GetCharWidthA
0x180025d57  nop     dword ptr [rax+rax+00h]
0x180025d5c  test    eax, eax
0x180025d5e  jz      loc_180025E43
0x180025d64  movzx   eax, word ptr [rsp+120h+iLast]
0x180025d69  mov     [rdi+2], ax
0x180025d6d  movzx   eax, [rbp+57h+var_D0]
0x180025d71  sub     [rdi+2], ax
0x180025d75  movzx   eax, word ptr [rdi+2]
0x180025d79  mov     [rdi], bx
0x180025d7c  cwde
0x180025d7d  mov     rdx, r12; h
0x180025d80  mov     [r15], eax
0x180025d83  mov     rcx, [rsi+40h]; hdc
0x180025d87  call    cs:__imp_SelectObject
0x180025d8e  nop     dword ptr [rax+rax+00h]
0x180025d93  mov     r14d, 1
0x180025d99  mov     eax, r14d
0x180025d9c  jmp     loc_180025C44
0x180025da1  mov     r12d, r14d
0x180025da4  mov     eax, r14d
0x180025da7  jmp     loc_180025C2A
0x180025dac  cmp     ebx, 7Fh
0x180025daf  jbe     short loc_180025D45
0x180025db1  mov     eax, 20ACh
0x180025db6  mov     [rbp+57h+var_BC], r14d
0x180025dba  mov     [rbp+57h+ho], r14
0x180025dbe  mov     [rbp+57h+h], r14
0x180025dc2  cmp     cx, ax
0x180025dc5  jz      loc_180026036
0x180025dcb  mov     r13, [rbp+57h+hdc]
0x180025dcf  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180025dd6  jz      loc_18002607A
0x180025ddc  mov     eax, 0FFFFh
0x180025de1  cmp     cx, ax
0x180025de4  jz      loc_1800260B9
0x180025dea  movzx   edx, cx; iFirst
0x180025ded  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180025df2  mov     r8d, edx; iLast
0x180025df5  mov     rcx, r13; hdc
0x180025df8  call    cs:__imp_GetCharWidthW
0x180025dff  nop     dword ptr [rax+rax+00h]
0x180025e04  test    eax, eax
0x180025e06  jz      short loc_180025E11
0x180025e08  movzx   eax, word ptr [rsp+120h+iLast]
0x180025e0d  mov     [rdi+2], ax
0x180025e11  cmp     [rbp+57h+var_BC], 0
0x180025e15  jz      loc_180025D6D
0x180025e1b  mov     rdx, [rbp+57h+h]; h
0x180025e1f  mov     rcx, r13; hdc
0x180025e22  call    cs:__imp_SelectObject
0x180025e29  nop     dword ptr [rax+rax+00h]
0x180025e2e  mov     rcx, [rbp+57h+ho]; ho
0x180025e32  call    cs:__imp_DeleteObject
0x180025e39  nop     dword ptr [rax+rax+00h]
0x180025e3e  jmp     loc_180025D6D
0x180025e43  movzx   ecx, [rsp+120h+WideCharStr]
0x180025e48  mov     r10, [rbp+57h+hdc]
0x180025e4c  jmp     loc_180025DB1
0x180025e51  lea     eax, [rdx-4E00h]
0x180025e57  cmp     eax, 51FFh
0x180025e5c  ja      short loc_180025E96
0x180025e5e  lea     eax, [rdx-0AC00h]
0x180025e64  cmp     eax, 2B9Fh
0x180025e69  ja      loc_180026014
0x180025e6f  add     rdi, 14h
0x180025e73  jmp     loc_180026018
0x180025e78  lea     eax, [rbx-0F900h]
0x180025e7e  cmp     eax, 1FFh
0x180025e83  ja      loc_180025BF9
0x180025e89  jmp     loc_180025C9B
0x180025e8e  inc     dword ptr [rdi+4]
0x180025e91  jmp     loc_180025C7A
0x180025e96  lea     eax, [rdx-0F900h]
0x180025e9c  cmp     eax, 1FFh
0x180025ea1  ja      loc_180025D1E
0x180025ea7  jmp     short loc_180025E5E
0x180025ea9  movzx   eax, cx
0x180025eac  add     eax, 0FFFFFF80h
0x180025eaf  cmp     eax, 7Fh
0x180025eb2  jbe     loc_180025DDC
0x180025eb8  mov     eax, [rbp+57h+CodePage]
0x180025ebb  cmp     eax, 3B6h
0x180025ec0  jnz     loc_180026099
0x180025ec6  mov     eax, 4E00h
0x180025ecb  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180025ed0  mov     r8d, eax; iLast
0x180025ed3  mov     edx, eax; iFirst
0x180025ed5  mov     rcx, r13; hdc
0x180025ed8  call    cs:__imp_GetCharWidthW
0x180025edf  nop     dword ptr [rax+rax+00h]
0x180025ee4  movzx   eax, word ptr [rsp+120h+iLast]
0x180025ee9  mov     edx, 4E00h
0x180025eee  mov     [rdi+2], ax
0x180025ef2  movzx   eax, [rsp+120h+WideCharStr]
0x180025ef7  sub     eax, edx
0x180025ef9  cmp     eax, 51FFh
0x180025efe  jbe     loc_180025D6D
0x180025f04  mov     ecx, [rbp+57h+CodePage]; CodePage
0x180025f07  lea     rax, [rbp+57h+hdc]
0x180025f0b  mov     [rsp+120h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180025f10  lea     r8, [rsp+120h+WideCharStr]; lpWideCharStr
0x180025f15  mov     [rsp+120h+lpDefaultChar], r14; lpDefaultChar
0x180025f1a  lea     rax, [rbp+57h+MultiByteStr]
0x180025f1e  mov     [rsp+120h+cbMultiByte], 2; cbMultiByte
0x180025f26  mov     r9d, 1; cchWideChar
0x180025f2c  xor     edx, edx; dwFlags
0x180025f2e  mov     [rsp+120h+lpMultiByteStr], rax; lpMultiByteStr
0x180025f33  mov     dword ptr [rbp+57h+hdc], r14d
0x180025f37  call    cs:__imp_WideCharToMultiByte
0x180025f3e  nop     dword ptr [rax+rax+00h]
0x180025f43  movzx   ecx, byte ptr [rbp+57h+MultiByteStr]
0x180025f47  cmp     eax, 2
0x180025f4a  jz      loc_1800260A9
0x180025f50  test    eax, eax
0x180025f52  jle     short loc_180025F76
0x180025f54  movzx   edx, cx; iFirst
0x180025f57  lea     r9, [rsp+120h+iLast]; lpBuffer
0x180025f5c  mov     r8d, edx; iLast
0x180025f5f  mov     rcx, r13; hdc
0x180025f62  call    cs:__imp_GetCharWidthA
0x180025f69  nop     dword ptr [rax+rax+00h]
0x180025f6e  test    eax, eax
0x180025f70  jnz     loc_180025D64
0x180025f76  movzx   ecx, [rsp+120h+WideCharStr]
0x180025f7b  jmp     loc_180025DDC
0x180025f80  mov     ecx, 0Ch; i
0x180025f85  mov     [rbp+57h+var_BC], 1
0x180025f8c  call    cs:__imp_GetStockObject
0x180025f93  nop     dword ptr [rax+rax+00h]
0x180025f98  mov     rdx, rax; h
0x180025f9b  mov     rcx, r13; hdc
0x180025f9e  call    cs:__imp_SelectObject
0x180025fa5  nop     dword ptr [rax+rax+00h]
0x180025faa  xor     edx, edx; Val
0x180025fac  lea     rcx, [rbp+57h+var_A0]; void *
0x180025fb0  mov     r8d, 5Ch ; '\'; Size
0x180025fb6  mov     [rbp+57h+h], rax
0x180025fba  call    memset_0
0x180025fbf  mov     rcx, [rbp+57h+h]; void *
0x180025fc3  lea     r8, [rbp+57h+var_A0]; void *
0x180025fc7  mov     edx, 5Ch ; '\'; int
0x180025fcc  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x180025fd1  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180025fd8  jz      loc_180026071
0x180025fde  mov     [rbp+57h+var_A0.lfOutPrecision], 9
0x180025fe2  lea     rcx, [rbp+57h+var_A0]; struct tagLOGFONTW *
0x180025fe6  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x180025feb  mov     rdx, rax; h
0x180025fee  mov     [rbp+57h+ho], rax
0x180025ff2  mov     rcx, r13; hdc
0x180025ff5  call    cs:__imp_SelectObject
0x180025ffc  nop     dword ptr [rax+rax+00h]
0x180026001  movzx   ecx, [rsp+120h+WideCharStr]
0x180026006  jmp     loc_180025DCF
0x18002600b  lea     rcx, [rdi+14h]
0x18002600f  jmp     loc_180025CB0
0x180026014  add     rdi, 16h
0x180026018  mov     word ptr [rsp+120h+lpMultiByteStr], cx; __int16
0x18002601d  mov     r9d, r8d; unsigned int
0x180026020  mov     r8, rdi; __int16 *
0x180026023  mov     rcx, r10; hdc
0x180026026  movzx   edx, bx; unsigned __int16
0x180026029  call    ?REGetCharWidth@CW32System@@SAXPEAUHDC__@@GPEAFIFH@Z; CW32System::REGetCharWidth(HDC__ *,ushort,short *,uint,short,int)
0x18002602e  movzx   eax, word ptr [rdi]
0x180026031  jmp     loc_180025D7C
0x180026036  mov     edx, 2; index
0x18002603b  mov     rcx, r10; hdc
0x18002603e  call    cs:__imp_GetDeviceCaps
0x180026045  nop     dword ptr [rax+rax+00h]
0x18002604a  mov     r13, [rbp+57h+hdc]
0x18002604e  cmp     eax, 1
0x180026051  jnz     loc_180025F80
0x180026057  mov     rcx, r13; hdc
0x18002605a  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x18002605f  test    eax, eax
0x180026061  jnz     loc_180025F80
0x180026067  movzx   ecx, [rsp+120h+WideCharStr]
0x18002606c  jmp     loc_180025DCF
0x180026071  mov     [rbp+57h+var_A0.lfOutPrecision], 7
0x180026075  jmp     loc_180025FE2
0x18002607a  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x180026081  jnz     loc_180025DDC
0x180026087  cmp     cs:?_dwMinorVersion@CW32System@@2KA, 0; ulong CW32System::_dwMinorVersion
0x18002608e  jnz     loc_180025DDC
0x180026094  jmp     loc_180025EA9
0x180026099  cmp     eax, 3A8h
0x18002609e  jnz     loc_180025DDC
0x1800260a4  jmp     loc_180025EC6
0x1800260a9  movzx   eax, byte ptr [rbp+57h+MultiByteStr+1]
0x1800260ad  shl     cx, 8
0x1800260b1  or      cx, ax
  ... truncated ...
```
