# CW32System::REGetCharWidth(HDC__ *,ushort,short *,uint,short,int)

- ea: `0x18003c080`
- end: `0x18003c37e`
- name: `?REGetCharWidth@CW32System@@SAXPEAUHDC__@@GPEAFIFH@Z`
- size: `766`
- prototype: `void __usercall(HDC hdc@<rcx>, unsigned __int16@<dx>, __int16 *@<r8>, unsigned int@<r9d>, __int16, int)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a1d0`
- `0x1800112c0`
- `0x180024d88`
- `0x180025bb0`

## callees

- `0x18002e7e4`
- `0x18003c080`
- `0x1800486b0`
- `0x180090024`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18003c22f`
- `KERNEL32!WideCharToMultiByte` at `0x18003c22f`
- `GDI32!GetDeviceCaps` at `0x18003c303`
- `GDI32!GetDeviceCaps` at `0x18003c303`
- `GDI32!DeleteObject` at `0x18003c192`
- `GDI32!DeleteObject` at `0x18003c192`
- `GDI32!GetStockObject` at `0x18003c283`
- `GDI32!GetStockObject` at `0x18003c283`
- `GDI32!SelectObject` at `0x18003c183`
- `GDI32!SelectObject` at `0x18003c295`
- `GDI32!SelectObject` at `0x18003c2e5`
- `GDI32!SelectObject` at `0x18003c183`
- `GDI32!SelectObject` at `0x18003c295`
- `GDI32!SelectObject` at `0x18003c2e5`
- `GDI32!GetCharWidthW` at `0x18003c15c`
- `GDI32!GetCharWidthW` at `0x18003c1d4`
- `GDI32!GetCharWidthW` at `0x18003c15c`
- `GDI32!GetCharWidthW` at `0x18003c1d4`
- `GDI32!GetCharWidthA` at `0x18003c0d2`
- `GDI32!GetCharWidthA` at `0x18003c25a`
- `GDI32!GetCharWidthA` at `0x18003c0d2`
- `GDI32!GetCharWidthA` at `0x18003c25a`

## pseudocode

```c
void __fastcall CW32System::REGetCharWidth(HDC hdc, WCHAR a2, __int16 *a3, UINT a4, __int16 a5)
{
  int v8; // r14d
  HFONT v9; // r15
  HGDIOBJ v10; // r12
  int v11; // eax
  unsigned __int16 v12; // cx
  HGDIOBJ StockObject; // rax
  WCHAR WideCharStr; // [rsp+40h] [rbp-89h] BYREF
  int Buffer; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int16 MultiByteStr; // [rsp+4Ch] [rbp-7Dh] BYREF
  BOOL UsedDefaultChar; // [rsp+50h] [rbp-79h] BYREF
  struct tagLOGFONTW v18; // [rsp+60h] [rbp-69h] BYREF

  WideCharStr = a2;
  Buffer = 0;
  *a3 = 0;
  if ( a4 == 42 || a2 <= 0x7Fu )
  {
    if ( GetCharWidthA(hdc, a2, a2, &Buffer) )
      goto LABEL_3;
    a2 = WideCharStr;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a2 == 8364 )
  {
    if ( GetDeviceCaps(hdc, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(hdc) )
    {
      v8 = 1;
      StockObject = GetStockObject(12);
      v10 = SelectObject(hdc, StockObject);
      memset_0(&v18, 0, sizeof(v18));
      CW32System::GetObjectW(v10, 92, &v18);
      if ( CW32System::_dwPlatformId == 1 )
        v18.lfOutPrecision = 7;
      else
        v18.lfOutPrecision = 9;
      v9 = CW32System::CreateFontIndirect(&v18);
      SelectObject(hdc, v9);
    }
    a2 = WideCharStr;
  }
  if ( CW32System::_dwPlatformId != 1
    || CW32System::_dwMajorVersion != 4
    || CW32System::_dwMinorVersion
    || (unsigned int)a2 - 128 <= 0x7F
    || a4 != 950 && a4 != 936 )
  {
    goto LABEL_8;
  }
  GetCharWidthW(hdc, 0x4E00u, 0x4E00u, &Buffer);
  *a3 = Buffer;
  if ( (unsigned int)WideCharStr - 19968 <= 0x51FF )
    goto LABEL_4;
  UsedDefaultChar = 0;
  v11 = WideCharToMultiByte(a4, 0, &WideCharStr, 1, (LPSTR)&MultiByteStr, 2, 0, &UsedDefaultChar);
  v12 = (unsigned __int8)MultiByteStr;
  if ( v11 == 2 )
  {
    v12 = _byteswap_ushort(MultiByteStr);
LABEL_20:
    if ( !GetCharWidthA(hdc, v12, v12, &Buffer) )
      goto LABEL_21;
LABEL_3:
    *a3 = Buffer;
    goto LABEL_4;
  }
  if ( v11 > 0 )
    goto LABEL_20;
LABEL_21:
  a2 = WideCharStr;
LABEL_8:
  if ( a2 == 0xFFFF )
  {
    a2 = -2;
    WideCharStr = -2;
  }
  if ( GetCharWidthW(hdc, a2, a2, &Buffer) )
    *a3 = Buffer;
  if ( v8 )
  {
    SelectObject(hdc, v10);
    DeleteObject(v9);
  }
LABEL_4:
  *a3 -= a5;
}

```

## disassembly

```asm
0x18003c080  push    rbp
0x18003c082  push    rbx
0x18003c083  push    rsi
0x18003c084  push    rdi
0x18003c085  push    r12
0x18003c087  push    r13
0x18003c089  push    r14
0x18003c08b  push    r15
0x18003c08d  lea     rbp, [rsp-0Fh]
0x18003c092  sub     rsp, 0D8h
0x18003c099  mov     rax, cs:__security_cookie
0x18003c0a0  xor     rax, rsp
0x18003c0a3  mov     [rbp+47h+var_50], rax
0x18003c0a7  xor     r13d, r13d
0x18003c0aa  mov     [rsp+110h+WideCharStr], dx
0x18003c0af  mov     [rsp+110h+Buffer], r13d
0x18003c0b4  mov     edi, r9d
0x18003c0b7  mov     [r8], r13w
0x18003c0bb  mov     rbx, r8
0x18003c0be  mov     rsi, rcx
0x18003c0c1  cmp     r9d, 2Ah ; '*'
0x18003c0c5  jnz     short loc_18003C116
0x18003c0c7  movzx   edx, dx; iFirst
0x18003c0ca  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003c0cf  mov     r8d, edx; iLast
0x18003c0d2  call    cs:__imp_GetCharWidthA
0x18003c0d9  nop     dword ptr [rax+rax+00h]
0x18003c0de  test    eax, eax
0x18003c0e0  jz      loc_18003C1A3
0x18003c0e6  movzx   eax, word ptr [rsp+110h+Buffer]
0x18003c0eb  mov     [rbx], ax
0x18003c0ee  movzx   eax, [rbp+47h+arg_20]
0x18003c0f2  sub     [rbx], ax
0x18003c0f5  mov     rcx, [rbp+47h+var_50]
0x18003c0f9  xor     rcx, rsp; StackCookie
0x18003c0fc  call    __security_check_cookie
0x18003c101  add     rsp, 0D8h
0x18003c108  pop     r15
0x18003c10a  pop     r14
0x18003c10c  pop     r13
0x18003c10e  pop     r12
0x18003c110  pop     rdi
0x18003c111  pop     rsi
0x18003c112  pop     rbx
0x18003c113  pop     rbp
0x18003c114  retn
0x18003c116  cmp     dx, 7Fh
0x18003c11a  jbe     short loc_18003C0C7
0x18003c11c  mov     eax, 20ACh
0x18003c121  mov     r14d, r13d
0x18003c124  mov     r15, r13
0x18003c127  mov     r12, r13
0x18003c12a  cmp     dx, ax
0x18003c12d  jz      loc_18003C2FB
0x18003c133  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x18003c13a  jz      loc_18003C32F
0x18003c140  mov     eax, 0FFFFh
0x18003c145  cmp     dx, ax
0x18003c148  jz      loc_18003C36F
0x18003c14e  movzx   edx, dx; iFirst
0x18003c151  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003c156  mov     r8d, edx; iLast
0x18003c159  mov     rcx, rsi; hdc
0x18003c15c  call    cs:__imp_GetCharWidthW
0x18003c163  nop     dword ptr [rax+rax+00h]
0x18003c168  test    eax, eax
0x18003c16a  jz      short loc_18003C174
0x18003c16c  movzx   eax, word ptr [rsp+110h+Buffer]
0x18003c171  mov     [rbx], ax
0x18003c174  test    r14d, r14d
0x18003c177  jz      loc_18003C0EE
0x18003c17d  mov     rdx, r12; h
0x18003c180  mov     rcx, rsi; hdc
0x18003c183  call    cs:__imp_SelectObject
0x18003c18a  nop     dword ptr [rax+rax+00h]
0x18003c18f  mov     rcx, r15; ho
0x18003c192  call    cs:__imp_DeleteObject
0x18003c199  nop     dword ptr [rax+rax+00h]
0x18003c19e  jmp     loc_18003C0EE
0x18003c1a3  movzx   edx, [rsp+110h+WideCharStr]
0x18003c1a8  jmp     loc_18003C11C
0x18003c1ad  movzx   eax, dx
0x18003c1b0  add     eax, 0FFFFFF80h
0x18003c1b3  cmp     eax, 7Fh
0x18003c1b6  jbe     short loc_18003C140
0x18003c1b8  cmp     edi, 3B6h
0x18003c1be  jnz     loc_18003C34E
0x18003c1c4  mov     edx, 4E00h; iFirst
0x18003c1c9  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003c1ce  mov     r8d, edx; iLast
0x18003c1d1  mov     rcx, rsi; hdc
0x18003c1d4  call    cs:__imp_GetCharWidthW
0x18003c1db  nop     dword ptr [rax+rax+00h]
0x18003c1e0  movzx   eax, word ptr [rsp+110h+Buffer]
0x18003c1e5  mov     [rbx], ax
0x18003c1e8  movzx   eax, [rsp+110h+WideCharStr]
0x18003c1ed  sub     eax, 4E00h
0x18003c1f2  cmp     eax, 51FFh
0x18003c1f7  jbe     loc_18003C0EE
0x18003c1fd  lea     rax, [rbp+47h+UsedDefaultChar]
0x18003c201  mov     [rbp+47h+UsedDefaultChar], r13d
0x18003c205  mov     [rsp+110h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18003c20a  lea     r8, [rsp+110h+WideCharStr]; lpWideCharStr
0x18003c20f  mov     [rsp+110h+lpDefaultChar], r13; lpDefaultChar
0x18003c214  lea     rax, [rbp+47h+MultiByteStr]
0x18003c218  mov     [rsp+110h+cbMultiByte], 2; cbMultiByte
0x18003c220  mov     r9d, 1; cchWideChar
0x18003c226  xor     edx, edx; dwFlags
0x18003c228  mov     [rsp+110h+lpMultiByteStr], rax; lpMultiByteStr
0x18003c22d  mov     ecx, edi; CodePage
0x18003c22f  call    cs:__imp_WideCharToMultiByte
0x18003c236  nop     dword ptr [rax+rax+00h]
0x18003c23b  movzx   ecx, byte ptr [rbp+47h+MultiByteStr]
0x18003c23f  cmp     eax, 2
0x18003c242  jz      loc_18003C35F
0x18003c248  test    eax, eax
0x18003c24a  jle     short loc_18003C26E
0x18003c24c  movzx   edx, cx; iFirst
0x18003c24f  lea     r9, [rsp+110h+Buffer]; lpBuffer
0x18003c254  mov     r8d, edx; iLast
0x18003c257  mov     rcx, rsi; hdc
0x18003c25a  call    cs:__imp_GetCharWidthA
0x18003c261  nop     dword ptr [rax+rax+00h]
0x18003c266  test    eax, eax
0x18003c268  jnz     loc_18003C0E6
0x18003c26e  movzx   edx, [rsp+110h+WideCharStr]
0x18003c273  jmp     loc_18003C140
0x18003c278  mov     ecx, 0Ch; i
0x18003c27d  mov     r14d, 1
0x18003c283  call    cs:__imp_GetStockObject
0x18003c28a  nop     dword ptr [rax+rax+00h]
0x18003c28f  mov     rdx, rax; h
0x18003c292  mov     rcx, rsi; hdc
0x18003c295  call    cs:__imp_SelectObject
0x18003c29c  nop     dword ptr [rax+rax+00h]
0x18003c2a1  xor     edx, edx; Val
0x18003c2a3  lea     rcx, [rbp+47h+var_B0]; void *
0x18003c2a7  mov     r8d, 5Ch ; '\'; Size
0x18003c2ad  mov     r12, rax
0x18003c2b0  call    memset_0
0x18003c2b5  lea     r8, [rbp+47h+var_B0]; void *
0x18003c2b9  mov     edx, 5Ch ; '\'; int
0x18003c2be  mov     rcx, r12; void *
0x18003c2c1  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x18003c2c6  cmp     cs:?_dwPlatformId@CW32System@@0KA, r14d; ulong CW32System::_dwPlatformId
0x18003c2cd  jz      short loc_18003C329
0x18003c2cf  mov     [rbp+47h+var_B0.lfOutPrecision], 9
0x18003c2d3  lea     rcx, [rbp+47h+var_B0]; struct tagLOGFONTW *
0x18003c2d7  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x18003c2dc  mov     rdx, rax; h
0x18003c2df  mov     rcx, rsi; hdc
0x18003c2e2  mov     r15, rax
0x18003c2e5  call    cs:__imp_SelectObject
0x18003c2ec  nop     dword ptr [rax+rax+00h]
0x18003c2f1  movzx   edx, [rsp+110h+WideCharStr]
0x18003c2f6  jmp     loc_18003C133
0x18003c2fb  mov     edx, 2; index
0x18003c300  mov     rcx, rsi; hdc
0x18003c303  call    cs:__imp_GetDeviceCaps
0x18003c30a  nop     dword ptr [rax+rax+00h]
0x18003c30f  cmp     eax, 1
0x18003c312  jnz     loc_18003C278
0x18003c318  mov     rcx, rsi; hdc
0x18003c31b  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x18003c320  test    eax, eax
0x18003c322  jz      short loc_18003C2F1
0x18003c324  jmp     loc_18003C278
0x18003c329  mov     [rbp+47h+var_B0.lfOutPrecision], 7
0x18003c32d  jmp     short loc_18003C2D3
0x18003c32f  cmp     cs:?_dwMajorVersion@CW32System@@2KA, 4; ulong CW32System::_dwMajorVersion
0x18003c336  jnz     loc_18003C140
0x18003c33c  cmp     cs:?_dwMinorVersion@CW32System@@2KA, r13d; ulong CW32System::_dwMinorVersion
0x18003c343  jnz     loc_18003C140
0x18003c349  jmp     loc_18003C1AD
0x18003c34e  cmp     edi, 3A8h
0x18003c354  jnz     loc_18003C140
0x18003c35a  jmp     loc_18003C1C4
0x18003c35f  movzx   eax, byte ptr [rbp+47h+MultiByteStr+1]
0x18003c363  shl     cx, 8
0x18003c367  or      cx, ax
0x18003c36a  jmp     loc_18003C24C
0x18003c36f  mov     edx, 0FFFEh
0x18003c374  mov     [rsp+110h+WideCharStr], dx
0x18003c379  jmp     loc_18003C14E
```
