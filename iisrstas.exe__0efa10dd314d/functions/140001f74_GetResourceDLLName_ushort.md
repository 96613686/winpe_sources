# GetResourceDLLName(ushort * *)

- ea: `0x140001f74`
- end: `0x1400020e3`
- name: `?GetResourceDLLName@@YAJPEAPEAG@Z`
- size: `367`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140002a40`

## callees

- `0x140001008`
- `0x140001060`
- `0x140001f74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140001fa1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140001f95`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140001ffa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140001f95`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x140001ffa`

## string_xrefs

- `0x140002067`: `\SYSTEM32\INETSRV\iisres.dll`

## pseudocode

```c
__int64 __fastcall GetResourceDLLName(unsigned __int16 **a1)
{
  UINT v2; // ebx
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  UINT v7; // ecx
  __int64 v8; // r8
  _WORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // r9
  const wchar_t *v14; // rcx
  unsigned __int16 *v15; // rax
  __int64 i; // rdx
  unsigned __int16 *v17; // rcx
  _WORD *v18; // rcx

  *a1 = &g_szResourceDll;
  v2 = 260;
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(&g_szResourceDll, 0x104u);
  if ( !SystemWindowsDirectoryW )
  {
LABEL_2:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  if ( SystemWindowsDirectoryW < 0x104 )
    goto LABEL_10;
  v2 = SystemWindowsDirectoryW + 30;
  v6 = (unsigned __int16 *)operator new[](saturated_mul(SystemWindowsDirectoryW + 30, 2u));
  *a1 = v6;
  if ( !v6 )
  {
    v5 = -2147024888;
    goto LABEL_27;
  }
  v7 = GetSystemWindowsDirectoryW(v6, v2);
  if ( !v7 )
    goto LABEL_2;
  if ( v7 < v2 - 29 )
  {
LABEL_10:
    v8 = 2147483646;
    if ( v2 - 1 > 0x7FFFFFFE )
    {
      v5 = -2147024809;
    }
    else
    {
      v9 = *a1;
      v10 = v2;
      v11 = v2;
      v12 = v2;
      do
      {
        if ( !*v9 )
          break;
        ++v9;
        --v11;
      }
      while ( v11 );
      v5 = v11 == 0 ? 0x80070057 : 0;
      if ( v11 )
        v13 = v12 - v11;
      else
        v13 = 0;
      if ( v11 )
      {
        v14 = L"\\SYSTEM32\\INETSRV\\iisres.dll";
        v15 = &(*a1)[v13];
        for ( i = v10 - v13; i; --i )
        {
          if ( !v8 )
            break;
          if ( !*v14 )
            break;
          *v15++ = *v14++;
          --v8;
        }
        v17 = v15 - 1;
        if ( i )
          v17 = v15;
        v5 = i == 0 ? 0x8007007A : 0;
        *v17 = 0;
      }
    }
LABEL_26:
    if ( (v5 & 0x80000000) == 0 )
      return v5;
    goto LABEL_27;
  }
  v5 = -2147024774;
LABEL_27:
  v18 = *a1;
  if ( *a1 != &g_szResourceDll && v18 )
    operator delete[](v18);
  *a1 = 0;
  return v5;
}

```

## disassembly

```asm
0x140001f74  push    rbx
0x140001f76  push    rsi
0x140001f77  push    rdi
0x140001f78  push    r14
0x140001f7a  sub     rsp, 28h
0x140001f7e  lea     r14, ?g_szResourceDll@@3PAGA; ushort near * g_szResourceDll
0x140001f85  mov     rdi, rcx
0x140001f88  mov     [rcx], r14
0x140001f8b  mov     ebx, 104h
0x140001f90  mov     rcx, r14; lpBuffer
0x140001f93  mov     edx, ebx; uSize
0x140001f95  call    cs:__imp_GetSystemWindowsDirectoryW
0x140001f9b  xor     esi, esi
0x140001f9d  test    eax, eax
0x140001f9f  jnz     short loc_140001FBF
0x140001fa1  call    cs:__imp_GetLastError
0x140001fa7  mov     ebx, eax
0x140001fa9  test    eax, eax
0x140001fab  jle     loc_1400020BE
0x140001fb1  movzx   ebx, ax
0x140001fb4  or      ebx, 80070000h
0x140001fba  jmp     loc_1400020BE
0x140001fbf  cmp     eax, ebx
0x140001fc1  jb      short loc_140002017
0x140001fc3  lea     ebx, [rax+1Eh]
0x140001fc6  mov     eax, 2
0x140001fcb  mov     ecx, ebx
0x140001fcd  mul     rcx
0x140001fd0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140001fd7  cmovb   rax, rcx
0x140001fdb  mov     rcx, rax; unsigned __int64
0x140001fde  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140001fe3  mov     [rdi], rax
0x140001fe6  test    rax, rax
0x140001fe9  jnz     short loc_140001FF5
0x140001feb  mov     ebx, 80070008h
0x140001ff0  jmp     loc_1400020C2
0x140001ff5  mov     edx, ebx; uSize
0x140001ff7  mov     rcx, rax; lpBuffer
0x140001ffa  call    cs:__imp_GetSystemWindowsDirectoryW
0x140002000  mov     ecx, eax
0x140002002  test    eax, eax
0x140002004  jz      short loc_140001FA1
0x140002006  lea     eax, [rbx-1Dh]
0x140002009  cmp     ecx, eax
0x14000200b  jb      short loc_140002017
0x14000200d  mov     ebx, 8007007Ah
0x140002012  jmp     loc_1400020C2
0x140002017  lea     eax, [rbx-1]
0x14000201a  mov     r8d, 7FFFFFFEh
0x140002020  cmp     eax, r8d
0x140002023  ja      loc_1400020B9
0x140002029  mov     r10, [rdi]
0x14000202c  mov     rax, r10
0x14000202f  mov     edx, ebx
0x140002031  mov     ecx, ebx
0x140002033  mov     r9d, ebx
0x140002036  cmp     [rax], si
0x140002039  jz      short loc_140002045
0x14000203b  add     rax, 2
0x14000203f  sub     rcx, 1
0x140002043  jnz     short loc_140002036
0x140002045  mov     rax, rcx
0x140002048  neg     rax
0x14000204b  sbb     ebx, ebx
0x14000204d  not     ebx
0x14000204f  and     ebx, 80070057h
0x140002055  test    rcx, rcx
0x140002058  jz      short loc_14000205F
0x14000205a  sub     r9, rcx
0x14000205d  jmp     short loc_140002062
0x14000205f  mov     r9, rsi
0x140002062  test    rcx, rcx
0x140002065  jz      short loc_1400020BE
0x140002067  lea     rcx, aSystem32Inetsr; "\\SYSTEM32\\INETSRV\\iisres.dll"
0x14000206e  lea     rax, [r10+r9*2]
0x140002072  sub     rdx, r9
0x140002075  jz      short loc_14000209B
0x140002077  test    r8, r8
0x14000207a  jz      short loc_14000209B
0x14000207c  movzx   r9d, word ptr [rcx]
0x140002080  test    r9w, r9w
0x140002084  jz      short loc_14000209B
0x140002086  mov     [rax], r9w
0x14000208a  add     rcx, 2
0x14000208e  add     rax, 2
0x140002092  dec     r8
0x140002095  sub     rdx, 1
0x140002099  jnz     short loc_140002077
0x14000209b  test    rdx, rdx
0x14000209e  lea     rcx, [rax-2]
0x1400020a2  mov     ebx, 8007007Ah
0x1400020a7  cmovnz  rcx, rax
0x1400020ab  neg     rdx
0x1400020ae  sbb     eax, eax
0x1400020b0  not     eax
0x1400020b2  and     ebx, eax
0x1400020b4  mov     [rcx], si
0x1400020b7  jmp     short loc_1400020BE
0x1400020b9  mov     ebx, 80070057h
0x1400020be  test    ebx, ebx
0x1400020c0  jns     short loc_1400020D7
0x1400020c2  mov     rcx, [rdi]; void *
0x1400020c5  cmp     rcx, r14
0x1400020c8  jz      short loc_1400020D4
0x1400020ca  test    rcx, rcx
0x1400020cd  jz      short loc_1400020D4
0x1400020cf  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400020d4  mov     [rdi], rsi
0x1400020d7  mov     eax, ebx
0x1400020d9  add     rsp, 28h
0x1400020dd  pop     r14
0x1400020df  pop     rdi
0x1400020e0  pop     rsi
0x1400020e1  pop     rbx
0x1400020e2  retn
```
