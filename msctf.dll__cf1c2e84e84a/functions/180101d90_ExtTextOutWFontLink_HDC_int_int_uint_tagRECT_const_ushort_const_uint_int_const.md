# _ExtTextOutWFontLink(HDC__ *,int,int,uint,tagRECT const *,ushort const *,uint,int const *)

- ea: `0x180101d90`
- end: `0x180102082`
- name: `?_ExtTextOutWFontLink@@YAHPEAUHDC__@@HHIPEBUtagRECT@@PEBGIPEBH@Z`
- size: `754`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, RECT *, const unsigned __int16 *, unsigned int, const int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180101a1c`

## callees

- `0x180101b1c`
- `0x180101bb8`
- `0x180101d60`
- `0x180101d90`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180101e2f`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180101e2f`
- `GDI32!MoveToEx` at `0x180101f9c`
- `GDI32!MoveToEx` at `0x180102064`
- `GDI32!MoveToEx` at `0x180101f9c`
- `GDI32!MoveToEx` at `0x180102064`
- `GDI32!SelectObject` at `0x180101f53`
- `GDI32!SelectObject` at `0x18010202a`
- `GDI32!SelectObject` at `0x180101f53`
- `GDI32!SelectObject` at `0x18010202a`
- `GDI32!ExtTextOutW` at `0x180101ff4`
- `GDI32!ExtTextOutW` at `0x180101ff4`
- `GDI32!GetTextAlign` at `0x180101f81`
- `GDI32!GetTextAlign` at `0x180101f81`
- `GDI32!SetTextAlign` at `0x180101fbb`
- `GDI32!SetTextAlign` at `0x180102010`
- `GDI32!SetTextAlign` at `0x180101fbb`
- `GDI32!SetTextAlign` at `0x180102010`
- `GDI32!GetCurrentObject` at `0x180101e00`
- `GDI32!GetCurrentObject` at `0x180101e00`

## pseudocode

```c
__int64 __fastcall _ExtTextOutWFontLink(
        HDC a1,
        int a2,
        int a3,
        UINT a4,
        RECT *lprect,
        const unsigned __int16 *a6,
        unsigned int a7,
        const int *c)
{
  HRESULT (__stdcall *CodePageToCodePages)(IMLangFontLink *, UINT, DWORD *); // rbx
  UINT ACP; // eax
  unsigned int v12; // ecx
  unsigned int v14; // r13d
  UINT TextAlign; // r12d
  int v16; // r14d
  unsigned int v17; // ebx
  struct IMLangFontLink *v18; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+4Ch] [rbp-34h] BYREF
  int v21; // [rsp+50h] [rbp-30h] BYREF
  int v22; // [rsp+54h] [rbp-2Ch] BYREF
  HGDIOBJ h; // [rsp+58h] [rbp-28h] BYREF
  HGDIOBJ v24; // [rsp+60h] [rbp-20h]
  struct tagPOINT pt; // [rsp+68h] [rbp-18h] BYREF
  HFONT CurrentObject; // [rsp+70h] [rbp-10h]
  LPCWSTR lpString; // [rsp+78h] [rbp-8h]
  unsigned int v31; // [rsp+F0h] [rbp+70h]

  h = 0;
  pt = 0;
  v20 = 0;
  v21 = 0;
  v19 = 0;
  LODWORD(c) = 0;
  v18 = 0;
  v22 = 0;
  if ( !a7 || !(unsigned int)LoadMLFontLink(&v18) )
    return 0;
  CurrentObject = (HFONT)GetCurrentObject(a1, 6u);
  ((void (__fastcall *)(struct IMLangFontLink *, HDC, HFONT, int *))v18->lpVtbl->GetFontCodePages)(
    v18,
    a1,
    CurrentObject,
    &v21);
  CodePageToCodePages = v18->lpVtbl->CodePageToCodePages;
  ACP = GetACP();
  ((void (__fastcall *)(struct IMLangFontLink *, _QWORD, unsigned int *))CodePageToCodePages)(v18, ACP, &v20);
  if ( ((int (__fastcall *)(struct IMLangFontLink *, const unsigned __int16 *, _QWORD, _QWORD, unsigned int *, const int **))v18->lpVtbl->GetStrCodePages)(
         v18,
         a6,
         a7,
         v20,
         &v19,
         &c) >= 0 )
  {
    v12 = (unsigned int)c;
  }
  else
  {
    v12 = a7;
    LODWORD(c) = a7;
  }
  if ( (v19 & v21) != 0 && a7 == v12 )
  {
    ((void (__fastcall *)(struct IMLangFontLink *))v18->lpVtbl->Release)(v18);
    return 0;
  }
  v24 = 0;
  v14 = 0;
  v31 = 1;
  TextAlign = 0;
  v16 = 0;
  v17 = 0;
  if ( a7 )
  {
    do
    {
      lpString = &a6[v17];
      if ( ((int (__fastcall *)(struct IMLangFontLink *, LPCWSTR, _QWORD, _QWORD, unsigned int *, const int **))v18->lpVtbl->GetStrCodePages)(
             v18,
             lpString,
             a7 - v17,
             v20,
             &v19,
             &c) < 0 )
        LODWORD(c) = a7 - v17;
      if ( (v19 & v21) == 0 )
      {
        MapFont(v18, a1, v19, CurrentObject, (HFONT *)&h, &v22);
        v24 = SelectObject(a1, h);
      }
      if ( (int)c > 0 )
      {
        if ( (unsigned int)c + v17 > a7 )
          LODWORD(c) = a7 - v17;
        if ( (_DWORD)c != a7 && v31 )
        {
          TextAlign = GetTextAlign(a1);
          if ( (TextAlign & 1) == 0 )
          {
            MoveToEx(a1, a2, a3, &pt);
            v16 = 1;
          }
          v31 = 0;
        }
        if ( v16 )
          SetTextAlign(a1, TextAlign | 1);
        v14 = ExtTextOutW(a1, a2, a3, a4, lprect, lpString, (UINT)c, 0);
        a4 &= ~2u;
        if ( v16 )
          SetTextAlign(a1, TextAlign);
        if ( !v14 )
          break;
      }
      if ( v24 )
      {
        SelectObject(a1, v24);
        ReleaseFont(v18, (HFONT)h, v22);
        v24 = 0;
      }
      v17 += (unsigned int)c;
    }
    while ( v17 < a7 );
    if ( v16 )
      MoveToEx(a1, pt.x, pt.y, 0);
  }
  ((void (__fastcall *)(struct IMLangFontLink *))v18->lpVtbl->Release)(v18);
  return v14;
}

```

## disassembly

```asm
0x180101d90  mov     rax, rsp
0x180101d93  mov     [rax+8], rbx
0x180101d97  mov     [rax+20h], r9d
0x180101d9b  mov     [rax+18h], r8d
0x180101d9f  mov     [rax+10h], edx
0x180101da2  push    rbp
0x180101da3  push    rsi
0x180101da4  push    rdi
0x180101da5  push    r12
0x180101da7  push    r13
0x180101da9  push    r14
0x180101dab  push    r15
0x180101dad  mov     rbp, rsp
0x180101db0  sub     rsp, 80h
0x180101db7  mov     esi, [rbp+arg_30]
0x180101dba  xor     r15d, r15d
0x180101dbd  mov     [rbp+h], r15
0x180101dc1  mov     rdi, rcx
0x180101dc4  mov     qword ptr [rbp+pt.x], r15
0x180101dc8  mov     [rbp+var_34], r15d
0x180101dcc  mov     [rbp+var_30], r15d
0x180101dd0  mov     [rbp+var_38], r15d
0x180101dd4  mov     [rbp+arg_38], r15d
0x180101dd8  mov     [rbp+var_40], r15
0x180101ddc  mov     [rbp+var_2C], r15d
0x180101de0  test    esi, esi
0x180101de2  jz      loc_180101E9E
0x180101de8  lea     rcx, [rbp+var_40]; struct IMLangFontLink **
0x180101dec  call    ?LoadMLFontLink@@YAHPEAPEAUIMLangFontLink@@@Z; LoadMLFontLink(IMLangFontLink * *)
0x180101df1  test    eax, eax
0x180101df3  jz      loc_180101E9E
0x180101df9  lea     edx, [r15+6]; type
0x180101dfd  mov     rcx, rdi; hdc
0x180101e00  call    cs:__imp_GetCurrentObject
0x180101e06  mov     rcx, [rbp+var_40]
0x180101e0a  lea     r9, [rbp+var_30]
0x180101e0e  mov     r8, rax
0x180101e11  mov     [rbp+var_10], rax
0x180101e15  mov     rdx, [rcx]
0x180101e18  mov     rax, [rdx+38h]
0x180101e1c  mov     rdx, rdi
0x180101e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e24  mov     rcx, [rbp+var_40]
0x180101e28  mov     rdx, [rcx]
0x180101e2b  mov     rbx, [rdx+28h]
0x180101e2f  call    cs:__imp_GetACP
0x180101e35  mov     rcx, [rbp+var_40]
0x180101e39  lea     r8, [rbp+var_34]
0x180101e3d  mov     edx, eax
0x180101e3f  mov     rax, rbx
0x180101e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e47  mov     rcx, [rbp+var_40]
0x180101e4b  lea     rdx, [rbp+arg_38]
0x180101e4f  mov     r9d, [rbp+var_34]
0x180101e53  mov     r8d, esi
0x180101e56  mov     [rsp+80h+lpString], rdx
0x180101e5b  lea     rdx, [rbp+var_38]
0x180101e5f  mov     [rsp+80h+lprect], rdx
0x180101e64  mov     rax, [rcx]
0x180101e67  mov     rdx, [rbp+arg_28]
0x180101e6b  mov     rax, [rax+20h]
0x180101e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e74  test    eax, eax
0x180101e76  jns     short loc_180101E7F
0x180101e78  mov     ecx, esi
0x180101e7a  mov     [rbp+arg_38], ecx
0x180101e7d  jmp     short loc_180101E82
0x180101e7f  mov     ecx, [rbp+arg_38]
0x180101e82  mov     eax, [rbp+var_38]
0x180101e85  test    [rbp+var_30], eax
0x180101e88  jz      short loc_180101EBB
0x180101e8a  cmp     esi, ecx
0x180101e8c  jnz     short loc_180101EBB
0x180101e8e  mov     rcx, [rbp+var_40]
0x180101e92  mov     rax, [rcx]
0x180101e95  mov     rax, [rax+10h]
0x180101e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101e9e  xor     eax, eax
0x180101ea0  mov     rbx, [rsp+80h+arg_0]
0x180101ea8  add     rsp, 80h
0x180101eaf  pop     r15
0x180101eb1  pop     r14
0x180101eb3  pop     r13
0x180101eb5  pop     r12
0x180101eb7  pop     rdi
0x180101eb8  pop     rsi
0x180101eb9  pop     rbp
0x180101eba  retn
0x180101ebb  mov     [rbp+var_20], r15
0x180101ebf  mov     r13d, r15d
0x180101ec2  mov     [rbp+arg_30], 1
0x180101ec9  mov     r12d, r15d
0x180101ecc  mov     r14d, r15d
0x180101ecf  mov     ebx, r15d
0x180101ed2  test    esi, esi
0x180101ed4  jz      loc_18010206A
0x180101eda  mov     rcx, [rbp+arg_28]
0x180101ede  lea     r8, [rbp+arg_38]
0x180101ee2  mov     r9d, [rbp+var_34]
0x180101ee6  mov     r15d, esi
0x180101ee9  mov     [rsp+80h+lpString], r8
0x180101eee  sub     r15d, ebx
0x180101ef1  lea     r8, [rbp+var_38]
0x180101ef5  movsxd  rax, ebx
0x180101ef8  mov     [rsp+80h+lprect], r8
0x180101efd  mov     r8d, r15d
0x180101f00  lea     rdx, [rcx+rax*2]
0x180101f04  mov     rcx, [rbp+var_40]
0x180101f08  mov     [rbp+var_8], rdx
0x180101f0c  mov     rax, [rcx]
0x180101f0f  mov     rax, [rax+20h]
0x180101f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180101f18  test    eax, eax
0x180101f1a  jns     short loc_180101F20
0x180101f1c  mov     [rbp+arg_38], r15d
0x180101f20  mov     r8d, [rbp+var_38]; unsigned int
0x180101f24  test    [rbp+var_30], r8d
0x180101f28  jnz     short loc_180101F5D
0x180101f2a  mov     r9, [rbp+var_10]; HFONT
0x180101f2e  lea     rax, [rbp+var_2C]
0x180101f32  mov     rcx, [rbp+var_40]; struct IMLangFontLink *
0x180101f36  mov     rdx, rdi; HDC
0x180101f39  mov     [rsp+80h+lpString], rax; int *
0x180101f3e  lea     rax, [rbp+h]
0x180101f42  mov     [rsp+80h+lprect], rax; HFONT *
0x180101f47  call    ?MapFont@@YAJPEAUIMLangFontLink@@PEAUHDC__@@KPEAUHFONT__@@PEAPEAU3@PEAH@Z; MapFont(IMLangFontLink *,HDC__ *,ulong,HFONT__ *,HFONT__ * *,int *)
0x180101f4c  mov     rdx, [rbp+h]; h
0x180101f50  mov     rcx, rdi; hdc
0x180101f53  call    cs:__imp_SelectObject
0x180101f59  mov     [rbp+var_20], rax
0x180101f5d  mov     eax, [rbp+arg_38]
0x180101f60  test    eax, eax
0x180101f62  jle     loc_18010201B
0x180101f68  lea     ecx, [rax+rbx]
0x180101f6b  cmp     ecx, esi
0x180101f6d  jbe     short loc_180101F73
0x180101f6f  mov     [rbp+arg_38], r15d
0x180101f73  cmp     [rbp+arg_38], esi
0x180101f76  jz      short loc_180101FAD
0x180101f78  cmp     [rbp+arg_30], 0
0x180101f7c  jz      short loc_180101FAD
0x180101f7e  mov     rcx, rdi; hdc
0x180101f81  call    cs:__imp_GetTextAlign
0x180101f87  mov     r12d, eax
0x180101f8a  test    al, 1
0x180101f8c  jnz     short loc_180101FA8
0x180101f8e  mov     r8d, [rbp+y]; y
0x180101f92  lea     r9, [rbp+pt]; lppt
0x180101f96  mov     edx, [rbp+x]; x
0x180101f99  mov     rcx, rdi; hdc
0x180101f9c  call    cs:__imp_MoveToEx
0x180101fa2  mov     r14d, 1
0x180101fa8  xor     eax, eax
0x180101faa  mov     [rbp+arg_30], eax
0x180101fad  test    r14d, r14d
0x180101fb0  jz      short loc_180101FC1
0x180101fb2  mov     edx, r12d
0x180101fb5  mov     rcx, rdi; hdc
0x180101fb8  or      edx, 1; align
0x180101fbb  call    cs:__imp_SetTextAlign
0x180101fc1  mov     eax, [rbp+arg_38]
0x180101fc4  mov     rcx, rdi; hdc
0x180101fc7  mov     r15d, [rbp+options]
0x180101fcb  mov     r9d, r15d; options
0x180101fce  mov     r8d, [rbp+y]; y
0x180101fd2  mov     edx, [rbp+x]; x
0x180101fd5  mov     [rsp+80h+lpDx], 0; lpDx
0x180101fde  mov     [rsp+80h+c], eax; c
0x180101fe2  mov     rax, [rbp+var_8]
0x180101fe6  mov     [rsp+80h+lpString], rax; lpString
0x180101feb  mov     rax, [rbp+arg_20]
0x180101fef  mov     [rsp+80h+lprect], rax; lprect
0x180101ff4  call    cs:__imp_ExtTextOutW
0x180101ffa  and     r15d, 0FFFFFFFDh
0x180101ffe  mov     r13d, eax
0x180102001  mov     [rbp+options], r15d
0x180102005  test    r14d, r14d
0x180102008  jz      short loc_180102016
0x18010200a  mov     edx, r12d; align
0x18010200d  mov     rcx, rdi; hdc
0x180102010  call    cs:__imp_SetTextAlign
0x180102016  test    r13d, r13d
0x180102019  jz      short loc_180102052
0x18010201b  mov     rax, [rbp+var_20]
0x18010201f  test    rax, rax
0x180102022  jz      short loc_180102047
0x180102024  mov     rdx, rax; h
0x180102027  mov     rcx, rdi; hdc
0x18010202a  call    cs:__imp_SelectObject
0x180102030  mov     r8d, [rbp+var_2C]; int
0x180102034  mov     rdx, [rbp+h]; HFONT
0x180102038  mov     rcx, [rbp+var_40]; struct IMLangFontLink *
0x18010203c  call    ?ReleaseFont@@YAJPEAUIMLangFontLink@@PEAUHFONT__@@H@Z; ReleaseFont(IMLangFontLink *,HFONT__ *,int)
0x180102041  xor     eax, eax
0x180102043  mov     [rbp+var_20], rax
0x180102047  add     ebx, [rbp+arg_38]
0x18010204a  cmp     ebx, esi
0x18010204c  jb      loc_180101EDA
0x180102052  test    r14d, r14d
0x180102055  jz      short loc_18010206A
0x180102057  mov     r8d, [rbp+pt.y]; y
0x18010205b  xor     r9d, r9d; lppt
0x18010205e  mov     edx, [rbp+pt.x]; x
0x180102061  mov     rcx, rdi; hdc
0x180102064  call    cs:__imp_MoveToEx
0x18010206a  mov     rcx, [rbp+var_40]
0x18010206e  mov     rax, [rcx]
0x180102071  mov     rax, [rax+10h]
0x180102075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010207a  mov     eax, r13d
0x18010207d  jmp     loc_180101EA0
```
