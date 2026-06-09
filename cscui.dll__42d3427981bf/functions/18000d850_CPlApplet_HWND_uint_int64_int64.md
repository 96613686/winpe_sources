# CPlApplet(HWND__ *,uint,__int64,__int64)

- ea: `0x18000d850`
- end: `0x18000d992`
- name: `?CPlApplet@@YAJPEAUHWND__@@I_J1@Z`
- size: `322`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180008b40`
- `0x18000c1dc`
- `0x18000c1e8`
- `0x18000d850`
- `0x180010b9c`

## import_xrefs

- `SHLWAPI!StrToIntW` at `0x18000d8bc`
- `SHLWAPI!StrToIntW` at `0x18000d8bc`
- `SHLWAPI!StrToIntA` at `0x18000d8e8`
- `SHLWAPI!StrToIntA` at `0x18000d8e8`
- `USER32!SetPropW` at `0x18000d8cf`
- `USER32!SetPropW` at `0x18000d8cf`
- `USER32!RemovePropW` at `0x18000d91d`
- `USER32!RemovePropW` at `0x18000d91d`
- `USER32!SetProcessDPIAware` at `0x18000d90d`
- `USER32!SetProcessDPIAware` at `0x18000d90d`

## pseudocode

```c
__int64 __fastcall CPlApplet(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // ebx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // eax
  _QWORD *v19; // rax

  v4 = 0;
  v7 = a2 - 1;
  if ( !v7 )
    return 1;
  v8 = v7 - 1;
  if ( !v8 )
    return 1;
  v9 = v8 - 1;
  if ( !v9 )
  {
    *(_OWORD *)a4 = 0;
    v16 = -2147024882;
    *(_DWORD *)(a4 + 16) = 0;
    v19 = operator new(8u);
    if ( v19 )
    {
      *v19 = hWnd;
      v16 = 0;
      *(_DWORD *)a4 = 1200;
      *(_DWORD *)(a4 + 4) = 45;
      *(_DWORD *)(a4 + 8) = 67;
      *(_QWORD *)(a4 + 12) = v19;
    }
    return v16 >> 31;
  }
  v10 = v9 - 2;
  if ( !v10 )
  {
    SetProcessDPIAware();
    v17 = (unsigned int)RemovePropW(hWnd, L"CscCplStartPageNumber");
    if ( a4 )
    {
      if ( hWnd )
        *(_QWORD *)a4 = hWnd;
      CCplApplet::Run((CCplApplet *)a4, v17);
    }
    return 1;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v16 = -2147024882;
    if ( a4 )
    {
      v16 = 0;
      operator delete((void *)a4);
    }
    return v16 >> 31;
  }
  v12 = v11 - 1;
  if ( !v12 )
    return v4;
  v13 = v12 - 1;
  if ( !v13 )
    return 1;
  v14 = v13 - 1;
  if ( v14 )
  {
    if ( v14 != 1 || !a4 )
      return v4;
    v15 = StrToIntW((PCWSTR)a4);
  }
  else
  {
    if ( !a4 )
      return v4;
    v15 = StrToIntA((PCSTR)a4);
  }
  if ( !SetPropW(hWnd, L"CscCplStartPageNumber", (HANDLE)v15) )
    ResultFromLastError();
  return v4;
}

```

## disassembly

```asm
0x18000d850  mov     [rsp+arg_0], rbx
0x18000d855  mov     [rsp+arg_8], rsi
0x18000d85a  push    rdi
0x18000d85b  sub     rsp, 20h
0x18000d85f  xor     ebx, ebx
0x18000d861  mov     rdi, r9
0x18000d864  mov     rsi, rcx
0x18000d867  sub     edx, 1
0x18000d86a  jz      loc_18000D93A
0x18000d870  sub     edx, 1
0x18000d873  jz      loc_18000D93A
0x18000d879  sub     edx, 1
0x18000d87c  jz      loc_18000D951
0x18000d882  sub     edx, 2
0x18000d885  jz      loc_18000D90D
0x18000d88b  sub     edx, 1
0x18000d88e  jz      short loc_18000D8F0
0x18000d890  sub     edx, 1
0x18000d893  jz      loc_18000D93F
0x18000d899  sub     edx, 1
0x18000d89c  jz      loc_18000D93A
0x18000d8a2  sub     edx, 1
0x18000d8a5  jz      short loc_18000D8E0
0x18000d8a7  cmp     edx, 1
0x18000d8aa  jnz     loc_18000D93F
0x18000d8b0  test    r9, r9
0x18000d8b3  jz      loc_18000D93F
0x18000d8b9  mov     rcx, r9; pszSrc
0x18000d8bc  call    cs:__imp_StrToIntW
0x18000d8c2  mov     r8d, eax; hData
0x18000d8c5  lea     rdx, String; "CscCplStartPageNumber"
0x18000d8cc  mov     rcx, rsi; hWnd
0x18000d8cf  call    cs:__imp_SetPropW
0x18000d8d5  test    eax, eax
0x18000d8d7  jnz     short loc_18000D93F
0x18000d8d9  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18000d8de  jmp     short loc_18000D93F
0x18000d8e0  test    rdi, rdi
0x18000d8e3  jz      short loc_18000D93F
0x18000d8e5  mov     rcx, rdi; pszSrc
0x18000d8e8  call    cs:__imp_StrToIntA
0x18000d8ee  jmp     short loc_18000D8C2
0x18000d8f0  mov     ebx, 8007000Eh
0x18000d8f5  test    rdi, rdi
0x18000d8f8  jz      loc_18000D98D
0x18000d8fe  xor     ebx, ebx
0x18000d900  mov     rcx, rdi; Block
0x18000d903  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d908  jmp     loc_18000D98D
0x18000d90d  call    cs:__imp_SetProcessDPIAware
0x18000d913  lea     rdx, String; "CscCplStartPageNumber"
0x18000d91a  mov     rcx, rsi; hWnd
0x18000d91d  call    cs:__imp_RemovePropW
0x18000d923  test    rdi, rdi
0x18000d926  jz      short loc_18000D93A
0x18000d928  test    rsi, rsi
0x18000d92b  jz      short loc_18000D930
0x18000d92d  mov     [rdi], rsi
0x18000d930  mov     edx, eax; unsigned int
0x18000d932  mov     rcx, rdi; this
0x18000d935  call    ?Run@CCplApplet@@QEAAJI@Z; CCplApplet::Run(uint)
0x18000d93a  mov     ebx, 1
0x18000d93f  mov     rsi, [rsp+28h+arg_8]
0x18000d944  mov     eax, ebx
0x18000d946  mov     rbx, [rsp+28h+arg_0]
0x18000d94b  add     rsp, 20h
0x18000d94f  pop     rdi
0x18000d950  retn
0x18000d951  xor     eax, eax
0x18000d953  xorps   xmm0, xmm0
0x18000d956  movups  xmmword ptr [r9], xmm0
0x18000d95a  mov     ebx, 8007000Eh
0x18000d95f  mov     [r9+10h], eax
0x18000d963  lea     ecx, [rax+8]; Size
0x18000d966  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d96b  test    rax, rax
0x18000d96e  jz      short loc_18000D98D
0x18000d970  mov     [rax], rsi
0x18000d973  xor     ebx, ebx
0x18000d975  mov     dword ptr [rdi], 4B0h
0x18000d97b  mov     dword ptr [rdi+4], 2Dh ; '-'
0x18000d982  mov     dword ptr [rdi+8], 43h ; 'C'
0x18000d989  mov     [rdi+0Ch], rax
0x18000d98d  shr     ebx, 1Fh
0x18000d990  jmp     short loc_18000D93F
```
