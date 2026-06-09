# IsInfInDriverStore

- ea: `0x180036080`
- end: `0x180036241`
- name: `IsInfInDriverStore`
- size: `449`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b7ec`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800078f0`
- `0x180036080`
- `0x1800363c8`
- `0x18003a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180036209`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180036209`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036144`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036144`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003621a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003621a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800361d6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800361d6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036184`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036184`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003612c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003612c`

## string_xrefs

- `0x180036125`: `setupapi.dll`

## pseudocode

```c
__int64 __fastcall IsInfInDriverStore(wchar_t *Str)
{
  unsigned int valid; // ebx
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v6; // eax
  UINT SystemDirectoryW; // eax
  __int64 v8; // r8
  unsigned __int16 v10[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+40h] [rbp-C0h]
  _OWORD v12[2]; // [rsp+50h] [rbp-B0h]
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v14[264]; // [rsp+280h] [rbp+180h] BYREF

  memset_0(Buffer, 0, 0x208u);
  memset_0(v14, 0, 0x208u);
  *(_OWORD *)v10 = *(_OWORD *)L"DriverStore\\FileRepository";
  v11 = *(_OWORD *)L"ore\\FileRepository";
  v12[0] = *(_OWORD *)L"Repository";
  *(_QWORD *)((char *)v12 + 14) = *(_QWORD *)L"ory";
  if ( Str )
  {
    valid = IsValidInfPath(Str);
    if ( !valid )
      return valid;
    LibraryW = LoadLibraryW(L"setupapi.dll");
    v4 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SetupGetInfPublishedNameW");
      if ( ProcAddress )
      {
        v6 = ((__int64 (__fastcall *)(wchar_t *, WCHAR *, __int64, _QWORD))ProcAddress)(Str, Buffer, 260, 0);
        Buffer[0] = 0;
        valid = v6;
        if ( !v6 )
        {
LABEL_16:
          FreeLibrary(v4);
          return valid;
        }
        SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
        if ( SystemDirectoryW
          && (Buffer[SystemDirectoryW - 1] == 92 || StringCchCatW(Buffer, 0x104u, L"\\") >= 0)
          && StringCchCatW(Buffer, 0x104u, v10) >= 0
          && GetFullPathNameW(Str, 0x104u, v14, 0) - 1 <= 0x102 )
        {
          v8 = -1;
          do
            ++v8;
          while ( Buffer[v8] );
          valid = _o__wcsnicmp(Buffer, v14) == 0;
          goto LABEL_16;
        }
      }
      valid = 0;
      goto LABEL_16;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180036080  push    rbp
0x180036082  push    rbx
0x180036083  push    rsi
0x180036084  push    rdi
0x180036085  push    r14
0x180036087  push    r15
0x180036089  lea     rbp, [rsp-3A8h]
0x180036091  sub     rsp, 4A8h
0x180036098  mov     rax, cs:__security_cookie
0x18003609f  xor     rax, rsp
0x1800360a2  mov     [rbp+3D0h+var_40], rax
0x1800360a9  mov     rsi, rcx
0x1800360ac  mov     ebx, 208h
0x1800360b1  mov     r8d, ebx; Size
0x1800360b4  lea     rcx, [rsp+4D0h+Buffer]; void *
0x1800360b9  xor     edx, edx; Val
0x1800360bb  call    memset_0
0x1800360c0  mov     r8d, ebx; Size
0x1800360c3  lea     rcx, [rbp+3D0h+var_250]; void *
0x1800360ca  xor     edx, edx; Val
0x1800360cc  call    memset_0
0x1800360d1  movups  xmm0, xmmword ptr cs:aDriverstoreFil; "DriverStore\\FileRepository"
0x1800360d8  xor     r14d, r14d
0x1800360db  movups  xmm1, xmmword ptr cs:aDriverstoreFil+10h; "ore\\FileRepository"
0x1800360e2  movups  xmmword ptr [rsp+4D0h+var_4A0], xmm0
0x1800360e7  movups  xmm0, xmmword ptr cs:aDriverstoreFil+20h; "Repository"
0x1800360ee  movups  [rsp+4D0h+var_490], xmm1
0x1800360f3  movsd   xmm1, qword ptr cs:aDriverstoreFil+2Eh; "ory"
0x1800360fb  movups  xmmword ptr [rsp+4D0h+var_480], xmm0
0x180036100  movsd   qword ptr [rsp+4D0h+var_480+0Eh], xmm1
0x180036106  test    rsi, rsi
0x180036109  jnz     short loc_180036113
0x18003610b  mov     ebx, r14d
0x18003610e  jmp     loc_180036220
0x180036113  mov     rcx, rsi; Str
0x180036116  call    IsValidInfPath
0x18003611b  mov     ebx, eax
0x18003611d  test    eax, eax
0x18003611f  jz      loc_180036220
0x180036125  lea     rcx, aSetupapiDll_0; "setupapi.dll"
0x18003612c  call    cs:__imp_LoadLibraryW
0x180036132  mov     rdi, rax
0x180036135  test    rax, rax
0x180036138  jz      short loc_18003610B
0x18003613a  lea     rdx, aSetupgetinfpub; "SetupGetInfPublishedNameW"
0x180036141  mov     rcx, rax; hModule
0x180036144  call    cs:__imp_GetProcAddress
0x18003614a  test    rax, rax
0x18003614d  jz      loc_1800361E5
0x180036153  mov     r15d, 104h
0x180036159  lea     rdx, [rsp+4D0h+Buffer]
0x18003615e  mov     r8d, r15d
0x180036161  xor     r9d, r9d
0x180036164  mov     rcx, rsi
0x180036167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003616c  mov     [rsp+4D0h+Buffer], r14w
0x180036172  mov     ebx, eax
0x180036174  test    eax, eax
0x180036176  jz      loc_180036217
0x18003617c  mov     edx, r15d; uSize
0x18003617f  lea     rcx, [rsp+4D0h+Buffer]; lpBuffer
0x180036184  call    cs:__imp_GetSystemDirectoryW
0x18003618a  test    eax, eax
0x18003618c  jz      short loc_1800361E5
0x18003618e  dec     eax
0x180036190  cmp     [rsp+rax*2+4D0h+Buffer], 5Ch ; '\'
0x180036196  jz      short loc_1800361B0
0x180036198  lea     r8, SubBlock; "\\"
0x18003619f  mov     edx, r15d; unsigned __int64
0x1800361a2  lea     rcx, [rsp+4D0h+Buffer]; unsigned __int16 *
0x1800361a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800361ac  test    eax, eax
0x1800361ae  js      short loc_1800361E5
0x1800361b0  lea     r8, [rsp+4D0h+var_4A0]; unsigned __int16 *
0x1800361b5  mov     rdx, r15; unsigned __int64
0x1800361b8  lea     rcx, [rsp+4D0h+Buffer]; unsigned __int16 *
0x1800361bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800361c2  test    eax, eax
0x1800361c4  js      short loc_1800361E5
0x1800361c6  xor     r9d, r9d; lpFilePart
0x1800361c9  lea     r8, [rbp+3D0h+var_250]; lpBuffer
0x1800361d0  mov     edx, r15d; nBufferLength
0x1800361d3  mov     rcx, rsi; lpFileName
0x1800361d6  call    cs:__imp_GetFullPathNameW
0x1800361dc  dec     eax
0x1800361de  cmp     eax, 102h
0x1800361e3  jbe     short loc_1800361EA
0x1800361e5  mov     ebx, r14d
0x1800361e8  jmp     short loc_180036217
0x1800361ea  lea     rax, [rsp+4D0h+Buffer]
0x1800361ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800361f3  inc     r8
0x1800361f6  cmp     [rax+r8*2], r14w
0x1800361fb  jnz     short loc_1800361F3
0x1800361fd  lea     rdx, [rbp+3D0h+var_250]
0x180036204  lea     rcx, [rsp+4D0h+Buffer]
0x180036209  call    cs:__imp__o__wcsnicmp
0x18003620f  test    eax, eax
0x180036211  mov     ebx, r14d
0x180036214  setz    bl
0x180036217  mov     rcx, rdi; hLibModule
0x18003621a  call    cs:__imp_FreeLibrary
0x180036220  mov     eax, ebx
0x180036222  mov     rcx, [rbp+3D0h+var_40]
0x180036229  xor     rcx, rsp; StackCookie
0x18003622c  call    __security_check_cookie
0x180036231  add     rsp, 4A8h
0x180036238  pop     r15
0x18003623a  pop     r14
0x18003623c  pop     rdi
0x18003623d  pop     rsi
0x18003623e  pop     rbx
0x18003623f  pop     rbp
0x180036240  retn
```
