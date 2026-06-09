# DriverProc

- ea: `0x180005e00`
- end: `0x1800064e0`
- name: `DriverProc`
- size: `1760`
- prototype: `__int64 __usercall@<rax>(LPARAM dwInitParam@<rcx>, HDRVR hDriver@<rdx>, LPARAM)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001400`
- `0x180003458`
- `0x180005e00`
- `0x1800064e8`
- `0x180006760`
- `0x1800067c0`
- `0x18000689c`
- `0x180006b68`
- `0x180006c1c`
- `0x180006d14`
- `0x180006dd8`
- `0x180006e8c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005ebc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005ebc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005eb3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005ec9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005eb3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005ec9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005ed2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005ed2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f58`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005f25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000635b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000637a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000635b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x18000637a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000642b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006445`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000642b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006445`
- `USER32!MessageBoxA` at `0x180006399`
- `USER32!MessageBoxA` at `0x180006399`
- `USER32!DialogBoxParamW` at `0x1800063cb`
- `USER32!DialogBoxParamW` at `0x1800063cb`
- `WINMM!DefDriverProc` at `0x180006011`
- `WINMM!DefDriverProc` at `0x180006011`
- `WINMM!GetDriverModuleHandle` at `0x180005fa1`
- `WINMM!GetDriverModuleHandle` at `0x180005fa1`

## string_xrefs

- `0x1800063c4`: `Configure`

## pseudocode

```c
LRESULT __fastcall DriverProc(DWORD_PTR dwInitParam, HDRVR hDriver, UINT a3, HWND a4, LPARAM a5)
{
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax
  __int64 v9; // rbx
  LRESULT result; // rax
  __int64 v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // eax
  UINT v14; // r8d
  UINT v15; // r8d
  UINT v16; // r8d
  UINT v17; // r8d
  UINT v18; // r8d
  UINT v19; // r8d
  UINT v20; // r8d
  UINT v21; // r8d
  UINT v22; // r8d
  UINT v23; // r8d
  UINT v24; // r8d
  UINT v25; // r8d
  UINT v26; // r8d
  UINT v27; // r8d
  __int64 v28; // rsi
  HINSTANCE v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  LONG lParam2; // [rsp+20h] [rbp-158h]
  LONG *v33; // [rsp+28h] [rbp-150h]
  LONG *v34; // [rsp+30h] [rbp-148h]
  INT v35; // [rsp+38h] [rbp-140h]
  CHAR Caption[64]; // [rsp+80h] [rbp-F8h] BYREF
  CHAR Buffer[128]; // [rsp+C0h] [rbp-B8h] BYREF

  if ( a3 > 0x400C )
  {
    if ( a3 <= 0x403E )
    {
      if ( a3 == 16446 )
      {
        LODWORD(result) = Decompress(
                            dwInitParam,
                            (_DWORD)hDriver,
                            *((_QWORD *)a4 + 1),
                            *((_QWORD *)a4 + 2),
                            *((_DWORD *)a4 + 14),
                            *((_DWORD *)a4 + 15),
                            *((_DWORD *)a4 + 16),
                            *((_DWORD *)a4 + 17),
                            *((_QWORD *)a4 + 3),
                            *((_QWORD *)a4 + 4),
                            *((_DWORD *)a4 + 10),
                            *((_DWORD *)a4 + 11),
                            *((_DWORD *)a4 + 12),
                            *((_DWORD *)a4 + 13));
        return (int)result;
      }
      v14 = a3 - 16397;
      if ( !v14 )
      {
        LODWORD(result) = Decompress(
                            dwInitParam,
                            (_DWORD)hDriver,
                            *((_QWORD *)a4 + 1),
                            *((_QWORD *)a4 + 2),
                            0,
                            0,
                            -1,
                            -1,
                            *((_QWORD *)a4 + 3),
                            *((_QWORD *)a4 + 4),
                            0,
                            0,
                            -1,
                            -1);
        return (int)result;
      }
      v15 = v14 - 1;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 6;
          if ( v17 )
          {
            v18 = v17 - 9;
            if ( !v18 )
            {
              LODWORD(result) = DecompressGetPalette(dwInitParam, a4, a5);
              return (int)result;
            }
            v19 = v18 - 3;
            if ( v19 )
            {
              v20 = v19 - 27;
              if ( !v20 )
              {
                LODWORD(result) = DecompressBegin(
                                    dwInitParam,
                                    (_DWORD)hDriver,
                                    *((_QWORD *)a4 + 1),
                                    (_DWORD)a4,
                                    *((_DWORD *)a4 + 14),
                                    *((_DWORD *)a4 + 15),
                                    *((_DWORD *)a4 + 16),
                                    *((_DWORD *)a4 + 17),
                                    *((_QWORD *)a4 + 3));
                return (int)result;
              }
              if ( v20 == 1 )
              {
                LODWORD(result) = DecompressQuery(
                                    dwInitParam,
                                    (_DWORD)hDriver,
                                    *((_QWORD *)a4 + 1),
                                    (_DWORD)a4,
                                    *((_DWORD *)a4 + 14),
                                    *((_DWORD *)a4 + 15),
                                    *((_DWORD *)a4 + 16),
                                    *((_DWORD *)a4 + 17),
                                    *((_QWORD *)a4 + 3));
                return (int)result;
              }
            }
          }
        }
        return -1;
      }
LABEL_112:
      v9 = 0;
      if ( !*(_DWORD *)(dwInitParam + 32) )
        return -100;
      *(_DWORD *)(dwInitParam + 32) = 0;
      return v9;
    }
    v21 = a3 - 16447;
    if ( !v21 )
      goto LABEL_112;
    v22 = v21 - 9;
    if ( !v22 )
    {
      *(_QWORD *)(dwInitParam + 40) = *((_QWORD *)a4 + 2);
      *(_QWORD *)(dwInitParam + 48) = *((_QWORD *)a4 + 1);
      return 0;
    }
    v23 = v22 - 4024;
    if ( !v23 )
    {
      v9 = 0;
      if ( !a4 || !(_DWORD)a5 )
        return 4;
      v11 = 4;
      if ( (unsigned int)a5 < 4 )
        return v9;
      *(_DWORD *)a4 = *(_DWORD *)(HWND)(dwInitParam + 24);
      return v11;
    }
    v24 = v23 - 1;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( !v25 )
      {
        v28 = 568;
        if ( a4 )
        {
          if ( (unsigned int)a5 >= 0x238 )
          {
            v29 = ghModule;
            *(_DWORD *)a4 = 568;
            *((_DWORD *)a4 + 1) = 1667524982;
            *((_DWORD *)a4 + 2) = 1129730893;
            *((_DWORD *)a4 + 3) = 5;
            *((_DWORD *)a4 + 4) = 0x10000;
            *((_DWORD *)a4 + 5) = 260;
            LoadStringW(v29, 0x2Au, (LPWSTR)a4 + 28, 128);
            LoadStringW(ghModule, 0x2Bu, (LPWSTR)a4 + 12, 16);
          }
          else
          {
            return 0;
          }
        }
        return v28;
      }
      v26 = v25 - 8;
      if ( v26 )
      {
        v27 = v26 - 1;
        if ( v27 )
        {
          if ( v27 != 19 || !a4 )
            return -1;
          *(_DWORD *)a4 = 7500;
        }
        else if ( a4 != HWND_MESSAGE|0x2LL )
        {
          LoadStringA(ghModule, 0x2Au, Buffer, 128);
          LoadStringA(ghModule, 0x2Cu, Caption, 64);
          MessageBoxA(a4, Buffer, Caption, 0x40u);
        }
      }
      else if ( a4 != HWND_MESSAGE|0x2LL )
      {
        LODWORD(result) = DialogBoxParamW(ghModule, L"Configure", a4, ConfigureDlgProc, dwInitParam);
        return (int)result;
      }
      return 0;
    }
    v30 = 4;
    if ( a4 )
    {
      if ( (_DWORD)a5 != 4 )
        return 0;
      v31 = *(_DWORD *)a4;
    }
    else
    {
      v31 = 75;
    }
    *(_DWORD *)(dwInitParam + 24) = v31;
    return v30;
  }
  if ( a3 == 16396 )
  {
    LODWORD(result) = DecompressBegin(dwInitParam, (_DWORD)hDriver, (_DWORD)a4, (_DWORD)a4, 0, 0, -1, -1, a5);
    return (int)result;
  }
  if ( a3 <= 0xA )
  {
    switch ( a3 )
    {
      case 0xAu:
        return 1;
      case 1u:
        if ( !ghModule )
          ghModule = GetDriverModuleHandle(hDriver);
        ++LoadCount;
        return 1;
      case 2u:
        return 1;
    }
    if ( a3 != 3 )
    {
      if ( a3 == 4 )
      {
        if ( dwInitParam != 4294901760 )
        {
          while ( *(int *)(dwInitParam + 28) > 0 )
            CompressEnd(dwInitParam, hDriver);
          if ( *(int *)(dwInitParam + 32) > 0 )
            *(_DWORD *)(dwInitParam + 32) = 0;
          LocalFree((HLOCAL)dwInitParam);
        }
        return 1;
      }
      if ( a3 != 5 )
      {
        if ( a3 == 6 )
        {
          if ( lpDitherTable )
          {
            v7 = GlobalHandle(lpDitherTable);
            GlobalUnlock(v7);
            v8 = GlobalHandle(lpDitherTable);
            GlobalFree(v8);
            lpDitherTable = 0;
          }
          if ( !--LoadCount )
            ghModule = 0;
          return 1;
        }
        if ( a3 != 7 )
        {
          if ( a3 != 8 )
          {
            if ( a3 != 9 )
              return DefDriverProc(dwInitParam, hDriver, a3, (LPARAM)a4, a5);
            return 1;
          }
          return 0;
        }
      }
      return 1;
    }
    v9 = 0;
    if ( !a5 )
      return 4294901760LL;
    if ( *(_DWORD *)(a5 + 4) != 1667524982 )
      return v9;
    v11 = (__int64)LocalAlloc(0x40u, 0x440u);
    if ( !v11 )
    {
      *(_QWORD *)(a5 + 24) = 4294967293LL;
      return v9;
    }
    *(_DWORD *)v11 = *(_DWORD *)(a5 + 16);
    *(_QWORD *)(v11 + 28) = 0;
    *(_DWORD *)(v11 + 36) = 0;
    *(_DWORD *)(v11 + 24) = 75;
    *(_QWORD *)(a5 + 24) = 0;
    return v11;
  }
  if ( a3 == 16388 )
  {
    LODWORD(result) = CompressGetFormat(dwInitParam, a4, a5);
    return (int)result;
  }
  if ( a3 != 16389 )
  {
    switch ( a3 )
    {
      case 0x4006u:
        LODWORD(result) = CompressQuery(dwInitParam, a4, a5);
        break;
      case 0x4007u:
        LODWORD(result) = CompressQuery(dwInitParam, a4, a5);
        if ( !(_DWORD)result )
        {
          *(_DWORD *)(dwInitParam + 28) = 1;
          LODWORD(result) = CompressFrameBegin(a4, a5, dwInitParam + 56, dwInitParam + 64);
        }
        break;
      case 0x4008u:
        LODWORD(result) = Compress((PVOID)dwInitParam, (const BYTE *)a4, 16392, (PBYTE)a4, lParam2, v33, v34, v35);
        break;
      case 0x4009u:
        LODWORD(result) = CompressEnd(dwInitParam, hDriver);
        break;
      case 0x400Au:
        LODWORD(result) = DecompressGetFormat(dwInitParam, a4, a5);
        break;
      case 0x400Bu:
        LODWORD(result) = DecompressQuery(dwInitParam, (_DWORD)hDriver, (_DWORD)a4, (_DWORD)a4, 0, 0, -1, -1, a5);
        break;
      default:
        if ( a3 < 0x4000 )
          return DefDriverProc(dwInitParam, hDriver, a3, (LPARAM)a4, a5);
        return -1;
    }
    return (int)result;
  }
  v12 = 10 * *((_DWORD *)a4 + 1) * *((_DWORD *)a4 + 2);
  if ( *(_WORD *)(a5 + 14) == 8 )
    v13 = v12 >> 4;
  else
    v13 = v12 >> 3;
  return v13 + 2;
}

```

## disassembly

```asm
0x180005e00  push    rbx
0x180005e02  push    rbp
0x180005e03  push    rsi
0x180005e04  push    rdi
0x180005e05  sub     rsp, 158h
0x180005e0c  mov     rax, cs:__security_cookie
0x180005e13  xor     rax, rsp
0x180005e16  mov     [rsp+178h+var_38], rax
0x180005e1e  mov     rbp, [rsp+178h+arg_20]
0x180005e26  mov     eax, 400Ch
0x180005e2b  mov     rdi, r9
0x180005e2e  mov     rsi, rcx
0x180005e31  cmp     r8d, eax
0x180005e34  ja      loc_180006136
0x180005e3a  jz      loc_1800060FA
0x180005e40  cmp     r8d, 0Ah
0x180005e44  ja      loc_180005FBE
0x180005e4a  jz      loc_180005FB4
0x180005e50  mov     eax, r8d
0x180005e53  sub     eax, 1
0x180005e56  jz      loc_180005F93
0x180005e5c  sub     eax, 1
0x180005e5f  jz      loc_180005FB4
0x180005e65  sub     eax, 1
0x180005e68  jz      loc_180005F30
0x180005e6e  sub     eax, 1
0x180005e71  jz      loc_180005EF8
0x180005e77  sub     eax, 1
0x180005e7a  jz      loc_180005FB4
0x180005e80  sub     eax, 1
0x180005e83  jz      short loc_180005EA5
0x180005e85  sub     eax, 1
0x180005e88  jz      loc_180005FB4
0x180005e8e  sub     eax, 1
0x180005e91  jz      loc_1800063A7
0x180005e97  cmp     eax, 1
0x180005e9a  jz      loc_180005FB4
0x180005ea0  jmp     loc_18000600C
0x180005ea5  mov     rcx, cs:lpDitherTable; pMem
0x180005eac  xor     ebx, ebx
0x180005eae  test    rcx, rcx
0x180005eb1  jz      short loc_180005EDF
0x180005eb3  call    cs:__imp_GlobalHandle
0x180005eb9  mov     rcx, rax; hMem
0x180005ebc  call    cs:__imp_GlobalUnlock
0x180005ec2  mov     rcx, cs:lpDitherTable; pMem
0x180005ec9  call    cs:__imp_GlobalHandle
0x180005ecf  mov     rcx, rax; hMem
0x180005ed2  call    cs:__imp_GlobalFree
0x180005ed8  mov     cs:lpDitherTable, rbx
0x180005edf  add     cs:LoadCount, 0FFFFFFFFh
0x180005ee6  jnz     loc_180005FB4
0x180005eec  mov     cs:ghModule, rbx
0x180005ef3  jmp     loc_180005FB4
0x180005ef8  mov     eax, 0FFFF0000h
0x180005efd  cmp     rsi, rax
0x180005f00  jz      loc_180005FB4
0x180005f06  xor     ebx, ebx
0x180005f08  cmp     [rcx+1Ch], ebx
0x180005f0b  jle     short loc_180005F1A
0x180005f0d  mov     rcx, rsi
0x180005f10  call    CompressEnd
0x180005f15  cmp     [rsi+1Ch], ebx
0x180005f18  jg      short loc_180005F0D
0x180005f1a  cmp     [rsi+20h], ebx
0x180005f1d  jle     short loc_180005F22
0x180005f1f  mov     [rsi+20h], ebx
0x180005f22  mov     rcx, rsi; hMem
0x180005f25  call    cs:__imp_LocalFree
0x180005f2b  jmp     loc_180005FB4
0x180005f30  xor     ebx, ebx
0x180005f32  test    rbp, rbp
0x180005f35  jnz     short loc_180005F41
0x180005f37  mov     eax, 0FFFF0000h
0x180005f3c  jmp     loc_1800064C4
0x180005f41  cmp     dword ptr [rbp+4], 63646976h
0x180005f48  jnz     loc_1800064C1
0x180005f4e  mov     edx, 440h; uBytes
0x180005f53  mov     ecx, 40h ; '@'; uFlags
0x180005f58  call    cs:__imp_LocalAlloc
0x180005f5e  mov     rcx, rax
0x180005f61  test    rax, rax
0x180005f64  jnz     short loc_180005F74
0x180005f66  mov     eax, 0FFFFFFFDh
0x180005f6b  mov     [rbp+18h], rax
0x180005f6f  jmp     loc_1800064C1
0x180005f74  mov     eax, [rbp+10h]
0x180005f77  mov     [rcx], eax
0x180005f79  mov     [rcx+1Ch], rbx
0x180005f7d  mov     [rcx+24h], ebx
0x180005f80  mov     dword ptr [rcx+18h], 4Bh ; 'K'
0x180005f87  mov     [rbp+18h], rbx
0x180005f8b  mov     rbx, rcx
0x180005f8e  jmp     loc_1800064C1
0x180005f93  xor     ebx, ebx
0x180005f95  cmp     cs:ghModule, rbx
0x180005f9c  jnz     short loc_180005FAE
0x180005f9e  mov     rcx, rdx; hDriver
0x180005fa1  call    cs:__imp_GetDriverModuleHandle
0x180005fa7  mov     cs:ghModule, rax
0x180005fae  inc     cs:LoadCount
0x180005fb4  mov     eax, 1
0x180005fb9  jmp     loc_1800064C4
0x180005fbe  mov     eax, r8d
0x180005fc1  sub     eax, 4004h
0x180005fc6  jz      loc_1800060EA
0x180005fcc  sub     eax, 1
0x180005fcf  jz      loc_1800060C1
0x180005fd5  sub     eax, 1
0x180005fd8  jz      loc_1800060B1
0x180005fde  sub     eax, 1
0x180005fe1  jz      loc_18000607F
0x180005fe7  sub     eax, 1
0x180005fea  jz      loc_180006072
0x180005ff0  sub     eax, 1
0x180005ff3  jz      short loc_180006068
0x180005ff5  sub     eax, 1
0x180005ff8  jz      short loc_180006058
0x180005ffa  cmp     eax, 1
0x180005ffd  jz      short loc_18000601C
0x180005fff  cmp     r8d, 4000h
0x180006006  jnb     loc_180006333
0x18000600c  mov     [rsp+178h+lParam2], rbp; lParam2
0x180006011  call    cs:__imp_DefDriverProc
0x180006017  jmp     loc_1800064C4
0x18000601c  mov     [rsp+178h+var_110], 0FFFFFFFFh
0x180006024  xor     ebx, ebx
0x180006026  mov     [rsp+178h+var_118], 0FFFFFFFFh
0x18000602e  mov     r8, rdi
0x180006031  mov     [rsp+178h+var_138], rbp
0x180006036  mov     [rsp+178h+var_140], 0FFFFFFFFh
0x18000603e  mov     dword ptr [rsp+178h+var_148], 0FFFFFFFFh
0x180006046  mov     dword ptr [rsp+178h+var_150], ebx
0x18000604a  mov     dword ptr [rsp+178h+lParam2], ebx
0x18000604e  call    DecompressQuery
0x180006053  jmp     loc_1800063D1
0x180006058  mov     r8, rbp
0x18000605b  mov     rdx, rdi
0x18000605e  call    DecompressGetFormat
0x180006063  jmp     loc_1800063D1
0x180006068  call    CompressEnd
0x18000606d  jmp     loc_1800063D1
0x180006072  mov     rdx, rdi; input_buffer
0x180006075  call    Compress
0x18000607a  jmp     loc_1800063D1
0x18000607f  mov     r8, rbp
0x180006082  mov     rdx, rdi
0x180006085  call    CompressQuery
0x18000608a  test    eax, eax
0x18000608c  jnz     loc_1800063D1
0x180006092  lea     r9, [rsi+40h]
0x180006096  mov     dword ptr [rsi+1Ch], 1
0x18000609d  lea     r8, [rsi+38h]
0x1800060a1  mov     rdx, rbp
0x1800060a4  mov     rcx, rdi
0x1800060a7  call    CompressFrameBegin
0x1800060ac  jmp     loc_1800063D1
0x1800060b1  mov     r8, rbp
0x1800060b4  mov     rdx, rdi
0x1800060b7  call    CompressQuery
0x1800060bc  jmp     loc_1800063D1
0x1800060c1  mov     eax, [r9+8]
0x1800060c5  mov     ecx, 8
0x1800060ca  imul    eax, [r9+4]
0x1800060cf  lea     eax, [rax+rax*4]
0x1800060d2  add     eax, eax
0x1800060d4  cmp     [rbp+0Eh], cx
0x1800060d8  jnz     short loc_1800060DF
0x1800060da  shr     eax, 4
0x1800060dd  jmp     short loc_1800060E2
0x1800060df  shr     eax, 3
0x1800060e2  add     eax, 2
0x1800060e5  jmp     loc_1800064C4
0x1800060ea  mov     r8, rbp
0x1800060ed  mov     rdx, rdi
0x1800060f0  call    CompressGetFormat
0x1800060f5  jmp     loc_1800063D1
0x1800060fa  mov     [rsp+178h+var_110], 0FFFFFFFFh
0x180006102  xor     ebx, ebx
0x180006104  mov     [rsp+178h+var_118], 0FFFFFFFFh
0x18000610c  mov     r8, rdi
0x18000610f  mov     [rsp+178h+var_138], rbp
0x180006114  mov     [rsp+178h+var_140], 0FFFFFFFFh
0x18000611c  mov     dword ptr [rsp+178h+var_148], 0FFFFFFFFh
0x180006124  mov     dword ptr [rsp+178h+var_150], ebx
0x180006128  mov     dword ptr [rsp+178h+lParam2], ebx
0x18000612c  call    DecompressBegin
0x180006131  jmp     loc_1800063D1
0x180006136  mov     eax, 403Eh
0x18000613b  cmp     r8d, eax
0x18000613e  ja      loc_1800062D7
0x180006144  jz      loc_180006283
0x18000614a  sub     r8d, 400Dh
0x180006151  jz      loc_18000622D
0x180006157  sub     r8d, 1
0x18000615b  jz      loc_1800064AE
0x180006161  sub     r8d, 1
0x180006165  jz      loc_180006333
0x18000616b  sub     r8d, 6
0x18000616f  jz      loc_180006333
0x180006175  sub     r8d, 9
0x180006179  jz      loc_18000621D
0x18000617f  sub     r8d, 3
0x180006183  jz      loc_180006333
0x180006189  sub     r8d, 1Bh
0x18000618d  jz      short loc_1800061DB
0x18000618f  cmp     r8d, 1
0x180006193  jnz     loc_180006333
0x180006199  mov     eax, [r9+34h]
0x18000619d  mov     r8, [r9+8]
0x1800061a1  mov     [rsp+178h+var_110], eax
0x1800061a5  mov     eax, [r9+30h]
0x1800061a9  mov     [rsp+178h+var_118], eax
0x1800061ad  mov     rax, [r9+18h]
0x1800061b1  mov     [rsp+178h+var_138], rax
0x1800061b6  mov     eax, [r9+44h]
0x1800061ba  mov     [rsp+178h+var_140], eax
0x1800061be  mov     eax, [r9+40h]
0x1800061c2  mov     dword ptr [rsp+178h+var_148], eax
0x1800061c6  mov     eax, [r9+3Ch]
0x1800061ca  mov     dword ptr [rsp+178h+var_150], eax
0x1800061ce  mov     eax, [r9+38h]
0x1800061d2  mov     dword ptr [rsp+178h+lParam2], eax
0x1800061d6  jmp     loc_18000604E
0x1800061db  mov     eax, [r9+34h]
0x1800061df  mov     r8, [r9+8]
0x1800061e3  mov     [rsp+178h+var_110], eax
0x1800061e7  mov     eax, [r9+30h]
0x1800061eb  mov     [rsp+178h+var_118], eax
0x1800061ef  mov     rax, [r9+18h]
0x1800061f3  mov     [rsp+178h+var_138], rax
0x1800061f8  mov     eax, [r9+44h]
0x1800061fc  mov     [rsp+178h+var_140], eax
0x180006200  mov     eax, [r9+40h]
0x180006204  mov     dword ptr [rsp+178h+var_148], eax
0x180006208  mov     eax, [r9+3Ch]
0x18000620c  mov     dword ptr [rsp+178h+var_150], eax
0x180006210  mov     eax, [r9+38h]
0x180006214  mov     dword ptr [rsp+178h+lParam2], eax
0x180006218  jmp     loc_18000612C
0x18000621d  mov     r8, rbp
0x180006220  mov     rdx, rdi
0x180006223  call    DecompressGetPalette
0x180006228  jmp     loc_1800063D1
0x18000622d  mov     rax, [r9+20h]
0x180006231  xor     ebx, ebx
0x180006233  mov     [rsp+178h+var_110], 0FFFFFFFFh
0x18000623b  mov     [rsp+178h+var_118], 0FFFFFFFFh
0x180006243  mov     [rsp+178h+var_120], ebx
0x180006247  mov     [rsp+178h+var_128], ebx
0x18000624b  mov     [rsp+178h+var_130], rax
0x180006250  mov     rax, [r9+18h]
0x180006254  mov     [rsp+178h+var_138], rax
0x180006259  mov     [rsp+178h+var_140], 0FFFFFFFFh
0x180006261  mov     dword ptr [rsp+178h+var_148], 0FFFFFFFFh
0x180006269  mov     dword ptr [rsp+178h+var_150], ebx
0x18000626d  mov     dword ptr [rsp+178h+lParam2], ebx
0x180006271  mov     r9, [r9+10h]
0x180006275  mov     r8, [rdi+8]
0x180006279  call    Decompress
0x18000627e  jmp     loc_1800063D1
0x180006283  mov     eax, [r9+34h]
0x180006287  mov     [rsp+178h+var_110], eax
0x18000628b  mov     eax, [r9+30h]
0x18000628f  mov     [rsp+178h+var_118], eax
0x180006293  mov     eax, [r9+2Ch]
0x180006297  mov     [rsp+178h+var_120], eax
0x18000629b  mov     eax, [r9+28h]
0x18000629f  mov     [rsp+178h+var_128], eax
0x1800062a3  mov     rax, [r9+20h]
0x1800062a7  mov     [rsp+178h+var_130], rax
0x1800062ac  mov     rax, [r9+18h]
0x1800062b0  mov     [rsp+178h+var_138], rax
0x1800062b5  mov     eax, [r9+44h]
0x1800062b9  mov     [rsp+178h+var_140], eax
0x1800062bd  mov     eax, [r9+40h]
0x1800062c1  mov     dword ptr [rsp+178h+var_148], eax
0x1800062c5  mov     eax, [r9+3Ch]
0x1800062c9  mov     dword ptr [rsp+178h+var_150], eax
0x1800062cd  mov     eax, [r9+38h]
0x1800062d1  mov     dword ptr [rsp+178h+lParam2], eax
0x1800062d5  jmp     short loc_180006271
0x1800062d7  sub     r8d, 403Fh
0x1800062de  jz      loc_1800064AE
0x1800062e4  sub     r8d, 9
0x1800062e8  jz      loc_180006499
0x1800062ee  sub     r8d, 0FB8h
0x1800062f5  jz      loc_180006475
0x1800062fb  sub     r8d, 1
0x1800062ff  jz      loc_180006450
0x180006305  sub     r8d, 1
0x180006309  jz      loc_1800063D8
0x18000630f  sub     r8d, 8
0x180006313  jz      loc_1800063A1
0x180006319  sub     r8d, 1
0x18000631d  jz      short loc_18000633C
0x18000631f  cmp     r8d, 13h
0x180006323  jnz     short loc_180006333
0x180006325  test    rdi, rdi
0x180006328  jz      short loc_180006333
  ... truncated ...
```
