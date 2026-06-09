# ExcelCreateFile(x,x,x,x,x,x)

- ea: `0x100158d0`
- end: `0x10015ec4`
- name: `_ExcelCreateFile@24`
- size: `1524`
- prototype: `int __thiscall(LPCWSTR lpFileName, int, int, __int16, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1001b1e0`

## callees

- `0x10007320`
- `0x10015090`
- `0x100158d0`
- `0x1002580a`
- `0x10025ab7`
- `0x10025cb3`
- `0x10025e72`
- `0x1003298b`
- `0x10032fa0`
- `0x10035510`
- `0x10035b40`
- `0x10035f40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10015afc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10015e3d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10015afc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10015e3d`
- `ole32!StgCreateDocfile` at `0x10015b9b`
- `ole32!StgCreateDocfile` at `0x10015b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10015b17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10015b17`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x10015bf8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x10015bf8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x10015c0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x10015c0d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10015dca`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x10015dca`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10015e14`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10015e14`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10015ad1`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x10015ad1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10015a8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10015a8d`

## pseudocode

```c
int __fastcall ExcelCreateFile(LPCWSTR lpFileName, int a2, int a3, int a4, __int16 a5, int *a6)
{
  int v7; // ebx
  int result; // eax
  int v9; // eax
  int v10; // eax
  _DWORD *v11; // esi
  bool v12; // zf
  unsigned int v13; // eax
  unsigned __int16 *v14; // ecx
  wchar_t *v15; // ebx
  unsigned __int16 v16; // cx
  unsigned __int16 v17; // si
  __int16 v18; // cx
  int v19; // edi
  unsigned __int16 v20; // si
  HANDLE FileW; // edi
  int v22; // eax
  int v23; // esi
  HRESULT Docfile; // eax
  HGLOBAL v25; // eax
  _DWORD *v26; // eax
  _DWORD *v27; // edi
  _DWORD *v28; // eax
  int v29; // edx
  int v30; // ecx
  int v31; // eax
  const wchar_t *v32; // eax
  int v33; // esi
  int v34; // eax
  int v35; // eax
  int v36; // ecx
  int v37; // eax
  _DWORD *v38; // [esp+18h] [ebp-450h]
  int v39; // [esp+1Ch] [ebp-44Ch]
  int v40; // [esp+20h] [ebp-448h]
  unsigned int v42; // [esp+28h] [ebp-440h]
  int v43; // [esp+2Ch] [ebp-43Ch]
  HGLOBAL v44; // [esp+2Ch] [ebp-43Ch]
  int v45; // [esp+30h] [ebp-438h] BYREF
  LPCSTR v46; // [esp+34h] [ebp-434h]
  char v47; // [esp+38h] [ebp-430h] BYREF
  int v48; // [esp+248h] [ebp-220h] BYREF
  LPCSTR lpFileNamea; // [esp+24Ch] [ebp-21Ch]
  char v50; // [esp+250h] [ebp-218h] BYREF

  v7 = MemAllocate(656);
  v43 = v7;
  if ( !v7 )
    return -2;
  *(_DWORD *)v7 = 0;
  *(_DWORD *)(v7 + 76) = -1;
  JetGetFullPathNameW(lpFileName, 0x105u, (LPWSTR)(v7 + 132), 0);
  v9 = v7;
  if ( *(_DWORD *)v7 == 1 )
    v9 = *(_DWORD *)(v7 + 44);
  *(_DWORD *)(v9 + 104) = 0;
  *(_WORD *)(v9 + 96) = 0x4000;
  v10 = MemAllocate(96);
  v11 = (_DWORD *)v10;
  v38 = (_DWORD *)v10;
  if ( !v10 )
    goto LABEL_77;
  if ( a2 >= 5 )
    *(_DWORD *)(v10 + 12) = 1;
  v12 = *(_DWORD *)(v10 + 12) == 0;
  *(_DWORD *)(v10 + 16) = 2;
  if ( v12 )
  {
    v13 = 0;
    v42 = 0;
    while ( 1 )
    {
      v14 = (unsigned __int16 *)(v7 + 132);
      v39 = (unsigned __int8)byte_10038E84[8 * v13];
      v40 = v7 + 132;
      if ( !byte_10038E84[8 * v13] )
        break;
      v15 = (&off_10038E80)[2 * v13];
      do
      {
        ++v15;
        v16 = *v14;
        v17 = v16 + 32;
        if ( (unsigned __int16)(v16 - 65) > 0x19u )
          v17 = v16;
        v18 = *(v15 - 1);
        v19 = v17;
        v20 = v18 + 32;
        if ( (unsigned __int16)(v18 - 65) > 0x19u )
          v20 = *(v15 - 1);
        v14 = (unsigned __int16 *)(v40 + 2);
        v12 = v39-- == 1;
        v40 += 2;
      }
      while ( !v12 && (_WORD)v19 && (_WORD)v19 == v20 );
      v7 = v43;
      v13 = v42;
      if ( v19 == v20 )
        break;
      v13 = v42 + 1;
      v42 = v13;
      if ( v13 >= 0x10 )
        goto LABEL_23;
    }
    if ( !v13 )
      goto LABEL_37;
LABEL_23:
    if ( wrap )
    {
      FileW = CreateFileW((LPCWSTR)(v7 + 132), 0xC0000000, 0, 0, 2u, 0x110080u, 0);
    }
    else
    {
      v48 = 0;
      lpFileNamea = 0;
      CStrIn::Init((CStrIn *)&v48, (LPCWCH)(v7 + 132), -1);
      FileW = CreateFileA(lpFileNamea, 0xC0000000, 0, 0, 2u, 0x110080u, 0);
      if ( lpFileNamea != &v50 && (unsigned int)lpFileNamea >> 16 && v48 != -1 )
        _free((void *)lpFileNamea);
    }
    v11 = v38;
    v38[5] = FileW;
    if ( FileW == (HANDLE)-1 )
    {
      v22 = -(unsigned __int16)GetLastError();
      if ( v22 )
      {
        if ( v22 == -4 )
        {
LABEL_32:
          v23 = -1;
          MemFree(v38);
          goto LABEL_78;
        }
        if ( v22 == -5 )
          goto LABEL_34;
        if ( v22 != -3 )
        {
          v23 = -11;
          MemFree(v38);
          goto LABEL_78;
        }
        goto LABEL_37;
      }
    }
  }
  else
  {
    Docfile = StgCreateDocfile((const WCHAR *)(v7 + 132), 0x11021u, 0, (IStorage **)(v10 + 28));
    if ( Docfile )
    {
      if ( Docfile != -2147287037 )
      {
        if ( Docfile == -2147287036 )
          goto LABEL_32;
        if ( Docfile != -2147287035 )
        {
          v23 = -11;
          if ( Docfile == -2147287007 )
            v23 = -2;
          MemFree(v38);
          goto LABEL_78;
        }
LABEL_34:
        v23 = -2;
        MemFree(v38);
        goto LABEL_78;
      }
LABEL_37:
      v23 = -3;
      MemFree(v38);
      goto LABEL_78;
    }
    v11[3] = 1;
    v11[9] = 1;
  }
  v25 = GlobalAlloc(0x2002u, 0xFDF4u);
  v44 = v25;
  if ( !v25
    || (v26 = GlobalLock(v25), (v27 = v26) == 0)
    || (v26[2] = v44, v26[1] = 65000, memset(v26 + 3, 0, 0xFDE8u), v28 = v27 + 3, *v27 = 1, v27 == (_DWORD *)-12) )
  {
    OSCloseFile(v11);
    MemFree(v11);
LABEL_77:
    v23 = -6;
LABEL_78:
    MemFree((_DWORD *)v7);
    result = dword_10001970[abs32(v23)];
    if ( result == -10 )
      return -10;
    return result;
  }
  v29 = a2;
  v11[1] = v28;
  v11[16] = 65000;
  v11[21] = 0;
  v11[20] = 0;
  *v11 = 0;
  v11[2] = v28;
  *(_DWORD *)(v7 + 20) = v11;
  if ( a2 < 5 )
    goto LABEL_62;
  v30 = v11[7];
  if ( !v30 )
  {
    v31 = -13;
    goto LABEL_58;
  }
  if ( v11[8] )
  {
    v31 = -10;
    goto LABEL_58;
  }
  v32 = L"Workbook";
  if ( a2 < 8 )
    v32 = L"Book";
  if ( !(*(int (__thiscall **)(_DWORD, int, const wchar_t *, int, _DWORD, _DWORD, _DWORD *))(*(_DWORD *)v30 + 12))(
          *(_DWORD *)(*(_DWORD *)v30 + 12),
          v30,
          v32,
          4113,
          0,
          0,
          v11 + 8) )
  {
    v34 = v11[1];
    v29 = a2;
    v11[16] = 65000;
    v11[21] = 0;
    v11[20] = 0;
    *v11 = 0;
    v11[2] = v34;
LABEL_62:
    *(_DWORD *)(v7 + 24) = a4;
    *(_DWORD *)(v7 + 28) = a4;
    *(_DWORD *)(v7 + 4) = v29;
    *(_DWORD *)(v7 + 44) = 1;
    *(_DWORD *)(v7 + 36) = 0;
    *(_WORD *)(v7 + 32) = a5;
    v35 = MemAllocate(2092);
    if ( v35 )
    {
      v36 = *(_DWORD *)(v7 + 4);
      *(_DWORD *)(v7 + 16) = v35;
      *(_DWORD *)(v7 + 8) = ExcelPTGSize(v36);
      *(_DWORD *)(v7 + 12) = dword_10001C90;
      *(_DWORD *)(v7 + 56) = a3;
      if ( (a3 & 0x800) != 0 )
      {
        v37 = MemAllocate(52);
        if ( !v37 )
          return -2;
        *(_DWORD *)(v7 + 40) = v37;
        *(_DWORD *)(v37 + 40) = *(_DWORD *)(v7 + 16);
        *(_DWORD *)(*(_DWORD *)(v7 + 40) + 36) = *(_DWORD *)(v7 + 4);
      }
      v33 = WriteEmptyBook(v7);
      if ( !v33 )
      {
        *a6 = v7;
        return 0;
      }
    }
    else
    {
      *(_DWORD *)(v7 + 16) = 0;
      v33 = -2;
    }
    goto LABEL_68;
  }
  v31 = -11;
LABEL_58:
  v33 = dword_10001970[abs32(v31)];
  if ( v33 == -10 )
    v33 = -10;
LABEL_68:
  BFCloseFile(*(_DWORD *)(v7 + 20));
  if ( wrap )
  {
    DeleteFileW((LPCWSTR)(v7 + 132));
    MemFree((_DWORD *)v7);
    return v33;
  }
  else
  {
    v45 = 0;
    v46 = 0;
    CStrIn::Init((CStrIn *)&v45, (LPCWCH)(v7 + 132), -1);
    DeleteFileA(v46);
    if ( v46 != &v47 && (unsigned int)v46 >> 16 && v45 != -1 )
      _free((void *)v46);
    MemFree((_DWORD *)v7);
    return v33;
  }
}

```

## disassembly

```asm
0x100158d0  mov     edi, edi
0x100158d2  push    ebp
0x100158d3  mov     ebp, esp
0x100158d5  sub     esp, 45Ch
0x100158db  mov     eax, ___security_cookie
0x100158e0  xor     eax, ebp
0x100158e2  mov     [ebp+var_4], eax
0x100158e5  mov     eax, [ebp+arg_C]
0x100158e8  push    ebx
0x100158e9  push    esi
0x100158ea  mov     esi, ecx
0x100158ec  mov     [ebp+var_444], edx
0x100158f2  push    edi
0x100158f3  mov     ecx, 290h
0x100158f8  mov     [ebp+var_458], eax
0x100158fe  call    _MemAllocate@4; MemAllocate(x)
0x10015903  mov     ebx, eax
0x10015905  mov     [ebp+var_43C], ebx
0x1001590b  test    ebx, ebx
0x1001590d  jnz     short loc_10015927
0x1001590f  mov     eax, 0FFFFFFFEh
0x10015914  pop     edi
0x10015915  pop     esi
0x10015916  pop     ebx
0x10015917  mov     ecx, [ebp+var_4]
0x1001591a  xor     ecx, ebp; StackCookie
0x1001591c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10015921  mov     esp, ebp
0x10015923  pop     ebp
0x10015924  retn    10h
0x10015927  push    0; lpFilePart
0x10015929  lea     eax, [ebx+84h]
0x1001592f  mov     dword ptr [ebx], 0
0x10015935  push    eax; lpBuffer
0x10015936  push    105h; nBufferLength
0x1001593b  push    esi; lpFileName
0x1001593c  mov     dword ptr [ebx+4Ch], 0FFFFFFFFh
0x10015943  call    _JetGetFullPathNameW@16; JetGetFullPathNameW(x,x,x,x)
0x10015948  cmp     dword ptr [ebx], 1
0x1001594b  mov     eax, ebx
0x1001594d  jnz     short loc_10015952
0x1001594f  mov     eax, [ebx+2Ch]
0x10015952  mov     ecx, 4000h
0x10015957  mov     dword ptr [eax+68h], 0
0x1001595e  mov     [eax+60h], cx
0x10015962  mov     ecx, 60h ; '`'
0x10015967  call    _MemAllocate@4; MemAllocate(x)
0x1001596c  mov     esi, eax
0x1001596e  mov     [ebp+var_450], esi
0x10015974  test    esi, esi
0x10015976  jz      loc_10015E8D
0x1001597c  cmp     [ebp+var_444], 5
0x10015983  jl      short loc_1001598C
0x10015985  mov     dword ptr [esi+0Ch], 1
0x1001598c  cmp     dword ptr [esi+0Ch], 0
0x10015990  mov     dword ptr [esi+10h], 2
0x10015997  jnz     loc_10015B89
0x1001599d  xor     eax, eax
0x1001599f  mov     [ebp+var_440], eax
0x100159a5  nop     word ptr [eax+eax+00000000h]
0x100159b0  mov     ecx, off_10038E80[eax*8]; "http:"
0x100159b7  movzx   edx, byte_10038E84[eax*8]
0x100159bf  mov     [ebp+var_454], ecx
0x100159c5  lea     ecx, [ebx+84h]
0x100159cb  mov     [ebp+var_44C], edx
0x100159d1  mov     [ebp+var_448], ecx
0x100159d7  test    edx, edx
0x100159d9  jz      loc_10015A63
0x100159df  mov     ebx, [ebp+var_454]
0x100159e5  movzx   eax, word ptr [ecx]
0x100159e8  lea     ebx, [ebx+2]
0x100159eb  mov     ecx, eax
0x100159ed  lea     edx, [eax-41h]
0x100159f0  lea     eax, [ecx+20h]
0x100159f3  cmp     dx, 19h
0x100159f7  movzx   esi, ax
0x100159fa  mov     eax, ecx
0x100159fc  cmova   esi, eax
0x100159ff  movzx   eax, word ptr [ebx-2]
0x10015a03  mov     ecx, eax
0x10015a05  movzx   edi, si
0x10015a08  lea     edx, [eax-41h]
0x10015a0b  lea     eax, [ecx+20h]
0x10015a0e  cmp     dx, 19h
0x10015a12  movzx   esi, ax
0x10015a15  mov     eax, ecx
0x10015a17  mov     ecx, [ebp+var_448]
0x10015a1d  cmova   esi, eax
0x10015a20  add     ecx, 2
0x10015a23  movzx   eax, si
0x10015a26  sub     [ebp+var_44C], 1
0x10015a2d  mov     [ebp+var_448], ecx
0x10015a33  jz      short loc_10015A3F
0x10015a35  test    di, di
0x10015a38  jz      short loc_10015A3F
0x10015a3a  cmp     di, ax
0x10015a3d  jz      short loc_100159E5
0x10015a3f  mov     ebx, [ebp+var_43C]
0x10015a45  mov     ecx, edi
0x10015a47  sub     ecx, eax
0x10015a49  mov     eax, [ebp+var_440]
0x10015a4f  jz      short loc_10015A63
0x10015a51  inc     eax
0x10015a52  mov     [ebp+var_440], eax
0x10015a58  cmp     eax, 10h
0x10015a5b  jb      loc_100159B0
0x10015a61  jmp     short loc_10015A6B
0x10015a63  test    eax, eax
0x10015a65  jz      loc_10015B74
0x10015a6b  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10015a72  lea     eax, [ebx+84h]
0x10015a78  jz      short loc_10015A97
0x10015a7a  push    0; hTemplateFile
0x10015a7c  push    110080h; dwFlagsAndAttributes
0x10015a81  push    2; dwCreationDisposition
0x10015a83  push    0; lpSecurityAttributes
0x10015a85  push    0; dwShareMode
0x10015a87  push    0C0000000h; dwDesiredAccess
0x10015a8c  push    eax; lpFileName
0x10015a8d  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x10015a93  mov     edi, eax
0x10015a95  jmp     short loc_10015B05
0x10015a97  push    0FFFFFFFFh; int
0x10015a99  push    eax; lpWideCharStr
0x10015a9a  lea     ecx, [ebp+var_220]; this
0x10015aa0  mov     [ebp+var_220], 0
0x10015aaa  mov     [ebp+lpFileName], 0
0x10015ab4  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10015ab9  push    0; hTemplateFile
0x10015abb  push    110080h; dwFlagsAndAttributes
0x10015ac0  push    2; dwCreationDisposition
0x10015ac2  push    0; lpSecurityAttributes
0x10015ac4  push    0; dwShareMode
0x10015ac6  push    0C0000000h; dwDesiredAccess
0x10015acb  push    [ebp+lpFileName]; lpFileName
0x10015ad1  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x10015ad7  mov     ecx, [ebp+lpFileName]
0x10015add  mov     edi, eax
0x10015adf  lea     eax, [ebp+var_218]
0x10015ae5  cmp     ecx, eax
0x10015ae7  jz      short loc_10015B05
0x10015ae9  mov     eax, ecx
0x10015aeb  shr     eax, 10h
0x10015aee  test    eax, eax
0x10015af0  jz      short loc_10015B05
0x10015af2  cmp     [ebp+var_220], 0FFFFFFFFh
0x10015af9  jz      short loc_10015B05
0x10015afb  push    ecx; Block
0x10015afc  call    ds:__imp__free
0x10015b02  add     esp, 4
0x10015b05  mov     esi, [ebp+var_450]
0x10015b0b  mov     [esi+14h], edi
0x10015b0e  cmp     edi, 0FFFFFFFFh
0x10015b11  jnz     loc_10015BEE
0x10015b17  call    ds:__imp__GetLastError@0; GetLastError()
0x10015b1d  movzx   eax, ax
0x10015b20  neg     eax
0x10015b22  jz      loc_10015BEE
0x10015b28  cmp     eax, 0FFFFFFFCh
0x10015b2b  jnz     short loc_10015B40
0x10015b2d  mov     ecx, [ebp+var_450]
0x10015b33  or      esi, 0FFFFFFFFh
0x10015b36  call    _MemFree@4; MemFree(x)
0x10015b3b  jmp     loc_10015E92
0x10015b40  cmp     eax, 0FFFFFFFBh
0x10015b43  jnz     short loc_10015B5A
0x10015b45  mov     ecx, [ebp+var_450]
0x10015b4b  mov     esi, 0FFFFFFFEh
0x10015b50  call    _MemFree@4; MemFree(x)
0x10015b55  jmp     loc_10015E92
0x10015b5a  cmp     eax, 0FFFFFFFDh
0x10015b5d  jz      short loc_10015B74
0x10015b5f  mov     ecx, [ebp+var_450]
0x10015b65  mov     esi, 0FFFFFFF5h
0x10015b6a  call    _MemFree@4; MemFree(x)
0x10015b6f  jmp     loc_10015E92
0x10015b74  mov     ecx, [ebp+var_450]
0x10015b7a  mov     esi, 0FFFFFFFDh
0x10015b7f  call    _MemFree@4; MemFree(x)
0x10015b84  jmp     loc_10015E92
0x10015b89  lea     eax, [esi+1Ch]
0x10015b8c  push    eax; ppstgOpen
0x10015b8d  push    0; reserved
0x10015b8f  push    11021h; grfMode
0x10015b94  lea     eax, [ebx+84h]
0x10015b9a  push    eax; pwcsName
0x10015b9b  call    ds:__imp__StgCreateDocfile@16; StgCreateDocfile(x,x,x,x)
0x10015ba1  test    eax, eax
0x10015ba3  jz      short loc_10015BE0
0x10015ba5  cmp     eax, 80030003h
0x10015baa  jz      short loc_10015B74
0x10015bac  cmp     eax, 80030004h
0x10015bb1  jz      loc_10015B2D
0x10015bb7  cmp     eax, 80030005h
0x10015bbc  jz      short loc_10015B45
0x10015bbe  cmp     eax, 80030021h
0x10015bc3  mov     ecx, 0FFFFFFFEh
0x10015bc8  mov     esi, 0FFFFFFF5h
0x10015bcd  cmovz   esi, ecx
0x10015bd0  mov     ecx, [ebp+var_450]
0x10015bd6  call    _MemFree@4; MemFree(x)
0x10015bdb  jmp     loc_10015E92
0x10015be0  mov     dword ptr [esi+0Ch], 1
0x10015be7  mov     dword ptr [esi+24h], 1
0x10015bee  push    0FDF4h; dwBytes
0x10015bf3  push    2002h; uFlags
0x10015bf8  call    ds:__imp__GlobalAlloc@8; GlobalAlloc(x,x)
0x10015bfe  mov     [ebp+var_43C], eax
0x10015c04  test    eax, eax
0x10015c06  jz      loc_10015E7F
0x10015c0c  push    eax; hMem
0x10015c0d  call    ds:__imp__GlobalLock@4; GlobalLock(x)
0x10015c13  mov     edi, eax
0x10015c15  test    edi, edi
0x10015c17  jz      loc_10015E7F
0x10015c1d  mov     eax, [ebp+var_43C]
0x10015c23  push    0FDE8h; Size
0x10015c28  mov     [edi+8], eax
0x10015c2b  lea     eax, [edi+0Ch]
0x10015c2e  push    0; Val
0x10015c30  push    eax; void *
0x10015c31  mov     dword ptr [edi+4], 0FDE8h
0x10015c38  call    _memset
0x10015c3d  lea     eax, [edi+0Ch]
0x10015c40  mov     dword ptr [edi], 1
0x10015c46  add     esp, 0Ch
0x10015c49  test    eax, eax
0x10015c4b  jz      loc_10015E7F
0x10015c51  mov     edx, [ebp+var_444]
0x10015c57  mov     [esi+4], eax
0x10015c5a  mov     dword ptr [esi+40h], 0FDE8h
0x10015c61  mov     dword ptr [esi+54h], 0
0x10015c68  mov     dword ptr [esi+50h], 0
0x10015c6f  mov     dword ptr [esi], 0
0x10015c75  mov     [esi+8], eax
0x10015c78  mov     [ebx+14h], esi
0x10015c7b  cmp     edx, 5
0x10015c7e  jl      loc_10015D21
0x10015c84  mov     edi, esi
0x10015c86  mov     ecx, [edi+1Ch]
0x10015c89  test    ecx, ecx
0x10015c8b  jnz     short loc_10015C92
0x10015c8d  lea     eax, [ecx-0Dh]
0x10015c90  jmp     short loc_10015CDF
0x10015c92  cmp     dword ptr [edi+20h], 0
0x10015c96  lea     eax, [edi+20h]
0x10015c99  jz      short loc_10015CA2
0x10015c9b  mov     eax, 0FFFFFFF6h
0x10015ca0  jmp     short loc_10015CDF
0x10015ca2  mov     esi, [ecx]
0x10015ca4  cmp     edx, 8
0x10015ca7  push    eax
0x10015ca8  push    0
0x10015caa  push    0
0x10015cac  mov     esi, [esi+0Ch]
0x10015caf  mov     eax, offset aWorkbook; "Workbook"
0x10015cb4  push    1011h
0x10015cb9  mov     [ebp+var_43C], offset aBook; "Book"
0x10015cc3  cmovl   eax, [ebp+var_43C]
0x10015cca  push    eax
0x10015ccb  push    ecx
0x10015ccc  mov     ecx, esi
0x10015cce  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10015cd4  call    esi
0x10015cd6  test    eax, eax
0x10015cd8  jz      short loc_10015CFA
0x10015cda  mov     eax, 0FFFFFFF5h
0x10015cdf  cdq
0x10015ce0  xor     eax, edx
0x10015ce2  sub     eax, edx
0x10015ce4  mov     esi, ds:dword_10001970[eax*4]
0x10015ceb  mov     eax, 0FFFFFFF6h
0x10015cf0  cmp     esi, eax
0x10015cf2  cmovz   esi, eax
0x10015cf5  jmp     loc_10015DB2
0x10015cfa  mov     eax, [edi+4]
0x10015cfd  mov     edx, [ebp+var_444]
0x10015d03  mov     dword ptr [edi+40h], 0FDE8h
0x10015d0a  mov     dword ptr [edi+54h], 0
0x10015d11  mov     dword ptr [edi+50h], 0
0x10015d18  mov     dword ptr [edi], 0
0x10015d1e  mov     [edi+8], eax
0x10015d21  mov     eax, [ebp+arg_4]
0x10015d24  mov     ecx, 82Ch
0x10015d29  mov     [ebx+18h], eax
0x10015d2c  mov     [ebx+1Ch], eax
0x10015d2f  mov     ax, [ebp+arg_8]
0x10015d33  mov     [ebx+4], edx
0x10015d36  mov     dword ptr [ebx+2Ch], 1
0x10015d3d  mov     dword ptr [ebx+24h], 0
0x10015d44  mov     [ebx+20h], ax
0x10015d48  call    _MemAllocate@4; MemAllocate(x)
0x10015d4d  test    eax, eax
0x10015d4f  jnz     short loc_10015D59
0x10015d51  mov     [ebx+10h], eax
0x10015d54  lea     esi, [eax-2]
0x10015d57  jmp     short loc_10015DB2
0x10015d59  mov     ecx, [ebx+4]
0x10015d5c  mov     [ebx+10h], eax
0x10015d5f  call    _ExcelPTGSize@4; ExcelPTGSize(x)
  ... truncated ...
```
