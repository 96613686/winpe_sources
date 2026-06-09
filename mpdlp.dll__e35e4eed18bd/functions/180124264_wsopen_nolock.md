# _wsopen_nolock

- ea: `0x180124264`
- end: `0x180124677`
- name: `_wsopen_nolock`
- size: `1043`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180123c48`

## callees

- `0x180119540`
- `0x18011958c`
- `0x1801195b0`
- `0x180123d0c`
- `0x180123f8c`
- `0x1801241a0`
- `0x180124264`
- `0x1801247e8`
- `0x18013575c`
- `0x180135844`
- `0x180135984`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180124408`
- `KERNEL32!GetLastError` at `0x18012442a`
- `KERNEL32!GetLastError` at `0x180124607`
- `KERNEL32!GetLastError` at `0x180124408`
- `KERNEL32!GetLastError` at `0x18012442a`
- `KERNEL32!GetLastError` at `0x180124607`
- `KERNEL32!CreateFileW` at `0x18012437a`
- `KERNEL32!CreateFileW` at `0x1801243d8`
- `KERNEL32!CreateFileW` at `0x1801245f8`
- `KERNEL32!CreateFileW` at `0x18012437a`
- `KERNEL32!CreateFileW` at `0x1801243d8`
- `KERNEL32!CreateFileW` at `0x1801245f8`
- `KERNEL32!CloseHandle` at `0x18012445d`
- `KERNEL32!CloseHandle` at `0x1801245c3`
- `KERNEL32!CloseHandle` at `0x18012445d`
- `KERNEL32!CloseHandle` at `0x1801245c3`
- `KERNEL32!GetFileType` at `0x180124420`
- `KERNEL32!GetFileType` at `0x180124420`

## pseudocode

```c
__int64 __fastcall wsopen_nolock(
        _DWORD *a1,
        unsigned int *a2,
        const WCHAR *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  __int64 v10; // rax
  __m128i v11; // xmm0
  __int64 v12; // r14
  unsigned int v14; // eax
  __m128i v15; // xmm0
  int v16; // r15^4
  __int64 dwFlagsAndAttributes; // r15
  HANDLE v18; // r13
  int v19; // ebx
  DWORD v20; // ebx
  DWORD LastError; // eax
  DWORD FileType; // eax
  __int64 v23; // rbx
  __int8 v24; // r14
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // r14d
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  HANDLE v32; // rdx
  DWORD v33; // eax
  char v34[4]; // [rsp+48h] [rbp-81h] BYREF
  DWORD dwCreationDisposition; // [rsp+4Ch] [rbp-7Dh]
  __m128i v36; // [rsp+50h] [rbp-79h]
  __int64 v37; // [rsp+60h] [rbp-69h]
  char v38; // [rsp+68h] [rbp-61h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-59h] BYREF
  __int64 v40; // [rsp+88h] [rbp-41h]
  DWORD v41[2]; // [rsp+90h] [rbp-39h]
  DWORD dwShareMode[4]; // [rsp+98h] [rbp-31h]
  __m128i v43; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-11h]
  char v45[32]; // [rsp+C8h] [rbp-1h] BYREF

  v10 = decode_options(v45, a4, a5, a6);
  v11 = *(__m128i *)v10;
  v12 = HIDWORD(*(_QWORD *)(v10 + 8));
  v40 = *(_QWORD *)(v10 + 16);
  v37 = v40;
  *(_QWORD *)dwShareMode = v12;
  v43 = v11;
  v36 = v11;
  if ( (_DWORD)v12 == -1 )
  {
    *_doserrno() = 0;
    *a2 = -1;
    return (unsigned int)*errno();
  }
  v14 = alloc_osfhnd();
  *a2 = v14;
  if ( v14 == -1 )
  {
    *_doserrno() = 0;
    *a2 = -1;
    *errno() = 24;
    return (unsigned int)*errno();
  }
  v15 = v43;
  v16 = HIDWORD(v37);
  *a1 = 1;
  dwFlagsAndAttributes = (unsigned int)v37 | v16;
  SecurityAttributes.bInheritHandle = (a4 & 0x80) == 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(&SecurityAttributes.bInheritHandle + 1) = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)v41 = dwFlagsAndAttributes;
  dwCreationDisposition = _mm_cvtsi128_si32(_mm_srli_si128(v15, 8));
  v18 = CreateFileW(a3, v15.m128i_u32[1], v12, &SecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, 0);
  if ( v18 == (HANDLE)-1LL )
  {
    v19 = _mm_cvtsi128_si32(_mm_srli_si128(v43, 4));
    if ( (v19 & 0xC0000000) != 0xC0000000
      || (a4 & 1) == 0
      || (v20 = v19 & 0x7FFFFFFF,
          v36.m128i_i32[1] = v20,
          v18 = CreateFileW(a3, v20, v12, &SecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, 0),
          v18 == (HANDLE)-1LL) )
    {
      *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) &= ~1u;
      LastError = GetLastError();
      _acrt_errno_map_os_error(LastError);
      return (unsigned int)*errno();
    }
  }
  else
  {
    v20 = v36.m128i_u32[1];
  }
  FileType = GetFileType(v18);
  if ( !FileType )
  {
    v23 = GetLastError();
    _acrt_errno_map_os_error(v23);
    *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) &= ~1u;
    CloseHandle(v18);
    if ( !(_DWORD)v23 )
      *errno() = 13;
    return (unsigned int)*errno();
  }
  v24 = v36.m128i_i8[0];
  if ( FileType == 2 )
  {
    v24 = v36.m128i_i8[0] | 0x40;
  }
  else if ( FileType == 3 )
  {
    v24 = v36.m128i_i8[0] | 8;
  }
  _acrt_lowio_set_os_handle(*a2, v18);
  v25 = (__int64)(int)*a2 >> 6;
  v26 = *a2 & 0x3F;
  v38 = v24 | 1;
  v36.m128i_i8[0] = v24 | 1;
  *(_BYTE *)(_pioinfo[v25] + 72 * v26 + 56) = v24 | 1;
  *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 57) = 0;
  if ( (a4 & 2) != 0 )
  {
    v27 = truncate_ctrl_z_if_present(*a2);
    if ( v27 )
    {
      v28 = *a2;
LABEL_22:
      close_nolock(v28);
      return v27;
    }
  }
  v29 = *a2;
  v43 = v36;
  v34[0] = 0;
  v44 = v40;
  v27 = configure_text_mode(v29, &v43, a4, v34);
  v30 = (int)*a2;
  if ( v27 )
  {
    v28 = (unsigned int)v30;
    goto LABEL_22;
  }
  *(_BYTE *)(_pioinfo[v30 >> 6] + 72 * (v30 & 0x3F) + 57) = v34[0];
  v31 = (int)*a2;
  *(_BYTE *)(_pioinfo[v31 >> 6] + 72 * (v31 & 0x3F) + 61) ^= (*(_BYTE *)(_pioinfo[v31 >> 6] + 72 * (v31 & 0x3F) + 61)
                                                            ^ BYTE2(a4))
                                                           & 1;
  if ( (v38 & 0x48) == 0 && (a4 & 8) != 0 )
    *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) |= 0x20u;
  if ( (v20 & 0xC0000000) == 0xC0000000 && (a4 & 1) != 0 )
  {
    CloseHandle(v18);
    v36.m128i_i32[1] = v20 & 0x7FFFFFFF;
    v32 = CreateFileW(a3, v20 & 0x7FFFFFFF, dwShareMode[0], &SecurityAttributes, dwCreationDisposition, v41[0], 0);
    if ( v32 == (HANDLE)-1LL )
    {
      v33 = GetLastError();
      _acrt_errno_map_os_error(v33);
      *(_BYTE *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 56) &= ~1u;
      free_osfhnd(*a2);
      return (unsigned int)*errno();
    }
    *(_QWORD *)(_pioinfo[(__int64)(int)*a2 >> 6] + 72LL * (*a2 & 0x3F) + 40) = v32;
  }
  return 0;
}

```

## disassembly

```asm
0x180124264  mov     rax, rsp
0x180124267  mov     [rax+8], rbx
0x18012426b  mov     [rax+10h], rsi
0x18012426f  mov     [rax+20h], rdi
0x180124273  mov     [rax+18h], r8
0x180124277  push    rbp
0x180124278  push    r12
0x18012427a  push    r13
0x18012427c  push    r14
0x18012427e  push    r15
0x180124280  lea     rbp, [rax-47h]
0x180124284  sub     rsp, 0E0h
0x18012428b  mov     r12d, r9d
0x18012428e  mov     rbx, r8
0x180124291  mov     r9d, [rbp+3Fh+arg_28]
0x180124295  mov     rdi, rdx
0x180124298  mov     r8d, [rbp+3Fh+arg_20]
0x18012429c  mov     rsi, rcx
0x18012429f  mov     edx, r12d
0x1801242a2  lea     rcx, [rbp+3Fh+var_40]
0x1801242a6  call    decode_options
0x1801242ab  movups  xmm0, xmmword ptr [rax]
0x1801242ae  mov     r14, [rax+8]
0x1801242b2  movsd   xmm1, qword ptr [rax+10h]
0x1801242b7  shr     r14, 20h
0x1801242bb  movsd   [rbp+3Fh+var_80], xmm1
0x1801242c0  movsd   [rbp+3Fh+var_A8], xmm1
0x1801242c5  mov     qword ptr [rbp+3Fh+dwShareMode], r14
0x1801242c9  movups  [rbp+3Fh+var_60], xmm0
0x1801242cd  movups  [rbp+3Fh+var_B8], xmm0
0x1801242d1  cmp     r14d, 0FFFFFFFFh
0x1801242d5  jnz     short loc_1801242EF
0x1801242d7  call    __doserrno
0x1801242dc  xor     esi, esi
0x1801242de  mov     [rax], esi
0x1801242e0  or      dword ptr [rdi], 0FFFFFFFFh
0x1801242e3  call    _errno
0x1801242e8  mov     eax, [rax]
0x1801242ea  jmp     loc_180124656
0x1801242ef  call    _alloc_osfhnd
0x1801242f4  mov     [rdi], eax
0x1801242f6  cmp     eax, 0FFFFFFFFh
0x1801242f9  jnz     short loc_180124314
0x1801242fb  call    __doserrno
0x180124300  xor     esi, esi
0x180124302  mov     [rax], esi
0x180124304  or      dword ptr [rdi], 0FFFFFFFFh
0x180124307  call    _errno
0x18012430c  mov     dword ptr [rax], 18h
0x180124312  jmp     short loc_1801242E3
0x180124314  movups  xmm0, [rbp+3Fh+var_60]
0x180124318  mov     r15, [rbp+3Fh+var_A8]
0x18012431c  lea     r9, [rbp+3Fh+SecurityAttributes]; lpSecurityAttributes
0x180124320  mov     eax, r12d
0x180124323  mov     dword ptr [rsi], 1
0x180124329  shr     eax, 7
0x18012432c  xor     esi, esi
0x18012432e  movq    rdx, xmm0
0x180124333  shr     r15, 20h
0x180124337  or      r15d, dword ptr [rbp+3Fh+var_A8]
0x18012433b  not     eax
0x18012433d  psrldq  xmm0, 8
0x180124342  and     eax, 1
0x180124345  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x18012434a  mov     r8d, r14d; dwShareMode
0x18012434d  shr     rdx, 20h; dwDesiredAccess
0x180124351  mov     rcx, rbx; lpFileName
0x180124354  mov     [rsp+100h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180124359  mov     [rbp+3Fh+SecurityAttributes.bInheritHandle], eax
0x18012435c  mov     qword ptr [rbp+3Fh+SecurityAttributes.nLength], 18h
0x180124364  mov     dword ptr [rbp+3Fh+SecurityAttributes+14h], esi
0x180124367  mov     [rbp+3Fh+SecurityAttributes.lpSecurityDescriptor], rsi
0x18012436b  mov     qword ptr [rbp+3Fh+var_78], r15
0x18012436f  movd    [rbp+3Fh+var_BC], xmm0
0x180124374  movd    [rsp+100h+dwCreationDisposition], xmm0; dwCreationDisposition
0x18012437a  call    cs:__imp_CreateFileW
0x180124380  mov     r13, rax
0x180124383  mov     ecx, 0C0000000h
0x180124388  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012438c  jnz     loc_18012441A
0x180124392  movups  xmm0, [rbp+3Fh+var_60]
0x180124396  psrldq  xmm0, 4
0x18012439b  movd    ebx, xmm0
0x18012439f  mov     eax, ebx
0x1801243a1  and     eax, ecx
0x1801243a3  cmp     eax, ecx
0x1801243a5  jnz     short loc_1801243E7
0x1801243a7  test    r12b, 1
0x1801243ab  jz      short loc_1801243E7
0x1801243ad  mov     eax, [rbp+3Fh+var_BC]
0x1801243b0  lea     r9, [rbp+3Fh+SecurityAttributes]; lpSecurityAttributes
0x1801243b4  mov     rcx, [rbp+3Fh+lpFileName]; lpFileName
0x1801243b8  btr     ebx, 1Fh
0x1801243bc  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x1801243c1  mov     r8d, r14d; dwShareMode
0x1801243c4  mov     dword ptr [rbp+3Fh+var_B8+4], ebx
0x1801243c7  mov     rdx, qword ptr [rbp+3Fh+var_B8]
0x1801243cb  shr     rdx, 20h; dwDesiredAccess
0x1801243cf  mov     [rsp+100h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1801243d4  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x1801243d8  call    cs:__imp_CreateFileW
0x1801243de  mov     r13, rax
0x1801243e1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801243e5  jnz     short loc_18012441D
0x1801243e7  movsxd  rcx, dword ptr [rdi]
0x1801243ea  lea     r15, __pioinfo
0x1801243f1  mov     rax, rcx
0x1801243f4  and     ecx, 3Fh
0x1801243f7  sar     rax, 6
0x1801243fb  lea     rcx, [rcx+rcx*8]
0x1801243ff  mov     rax, [r15+rax*8]
0x180124403  and     byte ptr [rax+rcx*8+38h], 0FEh
0x180124408  call    cs:__imp_GetLastError
0x18012440e  mov     ecx, eax
0x180124410  call    __acrt_errno_map_os_error
0x180124415  jmp     loc_1801242E3
0x18012441a  mov     ebx, dword ptr [rbp+3Fh+var_B8+4]
0x18012441d  mov     rcx, r13; hFile
0x180124420  call    cs:__imp_GetFileType
0x180124426  test    eax, eax
0x180124428  jnz     short loc_18012447B
0x18012442a  call    cs:__imp_GetLastError
0x180124430  mov     ecx, eax
0x180124432  mov     ebx, eax
0x180124434  call    __acrt_errno_map_os_error
0x180124439  movsxd  rdx, dword ptr [rdi]
0x18012443c  lea     r15, __pioinfo
0x180124443  mov     rcx, rdx
0x180124446  and     edx, 3Fh
0x180124449  sar     rcx, 6
0x18012444d  lea     rdx, [rdx+rdx*8]
0x180124451  mov     rcx, [r15+rcx*8]
0x180124455  and     byte ptr [rcx+rdx*8+38h], 0FEh
0x18012445a  mov     rcx, r13; hObject
0x18012445d  call    cs:__imp_CloseHandle
0x180124463  test    ebx, ebx
0x180124465  jnz     loc_1801242E3
0x18012446b  call    _errno
0x180124470  mov     dword ptr [rax], 0Dh
0x180124476  jmp     loc_1801242E3
0x18012447b  mov     r14b, byte ptr [rbp+3Fh+var_B8]
0x18012447f  cmp     eax, 2
0x180124482  jnz     short loc_18012448A
0x180124484  or      r14b, 40h
0x180124488  jmp     short loc_180124493
0x18012448a  cmp     eax, 3
0x18012448d  jnz     short loc_180124493
0x18012448f  or      r14b, 8
0x180124493  mov     ecx, [rdi]
0x180124495  mov     rdx, r13
0x180124498  call    __acrt_lowio_set_os_handle
0x18012449d  movsxd  rcx, dword ptr [rdi]
0x1801244a0  lea     r15, __pioinfo
0x1801244a7  mov     rax, rcx
0x1801244aa  or      r14b, 1
0x1801244ae  sar     rax, 6
0x1801244b2  and     ecx, 3Fh
0x1801244b5  mov     [rbp+3Fh+var_A0], r14b
0x1801244b9  mov     byte ptr [rbp+3Fh+var_B8], r14b
0x1801244bd  mov     rax, [r15+rax*8]
0x1801244c1  lea     rcx, [rcx+rcx*8]
0x1801244c5  mov     [rax+rcx*8+38h], r14b
0x1801244ca  movsxd  rcx, dword ptr [rdi]
0x1801244cd  mov     rax, rcx
0x1801244d0  and     ecx, 3Fh
0x1801244d3  sar     rax, 6
0x1801244d7  lea     rcx, [rcx+rcx*8]
0x1801244db  mov     rax, [r15+rax*8]
0x1801244df  mov     [rax+rcx*8+39h], sil
0x1801244e4  test    r12b, 2
0x1801244e8  jz      short loc_180124507
0x1801244ea  mov     ecx, [rdi]
0x1801244ec  call    truncate_ctrl_z_if_present
0x1801244f1  mov     r14d, eax
0x1801244f4  test    eax, eax
0x1801244f6  jz      short loc_180124507
0x1801244f8  mov     ecx, [rdi]
0x1801244fa  call    _close_nolock
0x1801244ff  mov     eax, r14d
0x180124502  jmp     loc_180124656
0x180124507  movups  xmm0, [rbp+3Fh+var_B8]
0x18012450b  lea     r9, [rsp+100h+var_C0]
0x180124510  mov     ecx, [rdi]
0x180124512  movsd   xmm1, [rbp+3Fh+var_80]
0x180124517  lea     rdx, [rbp+3Fh+var_60]
0x18012451b  mov     r8d, r12d
0x18012451e  movaps  [rbp+3Fh+var_60], xmm0
0x180124522  mov     [rsp+100h+var_C0], sil
0x180124527  movsd   [rbp+3Fh+var_50], xmm1
0x18012452c  call    configure_text_mode
0x180124531  mov     r14d, eax
0x180124534  movsxd  rax, dword ptr [rdi]
0x180124537  test    r14d, r14d
0x18012453a  jz      short loc_180124540
0x18012453c  mov     ecx, eax
0x18012453e  jmp     short loc_1801244FA
0x180124540  mov     rcx, rax
0x180124543  and     eax, 3Fh
0x180124546  sar     rcx, 6
0x18012454a  lea     rdx, [rax+rax*8]
0x18012454e  mov     al, [rsp+100h+var_C0]
0x180124552  mov     rcx, [r15+rcx*8]
0x180124556  mov     [rcx+rdx*8+39h], al
0x18012455a  movsxd  rcx, dword ptr [rdi]
0x18012455d  mov     rax, rcx
0x180124560  and     ecx, 3Fh
0x180124563  sar     rax, 6
0x180124567  lea     rdx, [rcx+rcx*8]
0x18012456b  mov     rcx, [r15+rax*8]
0x18012456f  mov     eax, r12d
0x180124572  shr     eax, 10h
0x180124575  xor     al, [rcx+rdx*8+3Dh]
0x180124579  and     al, 1
0x18012457b  xor     [rcx+rdx*8+3Dh], al
0x18012457f  test    [rbp+3Fh+var_A0], 48h
0x180124583  jnz     short loc_1801245A5
0x180124585  test    r12b, 8
0x180124589  jz      short loc_1801245A5
0x18012458b  movsxd  rcx, dword ptr [rdi]
0x18012458e  mov     rax, rcx
0x180124591  and     ecx, 3Fh
0x180124594  sar     rax, 6
0x180124598  lea     rcx, [rcx+rcx*8]
0x18012459c  mov     rax, [r15+rax*8]
0x1801245a0  or      byte ptr [rax+rcx*8+38h], 20h
0x1801245a5  mov     ecx, 0C0000000h
0x1801245aa  mov     eax, ebx
0x1801245ac  and     eax, ecx
0x1801245ae  cmp     eax, ecx
0x1801245b0  jnz     loc_180124654
0x1801245b6  test    r12b, 1
0x1801245ba  jz      loc_180124654
0x1801245c0  mov     rcx, r13; hObject
0x1801245c3  call    cs:__imp_CloseHandle
0x1801245c9  mov     rax, qword ptr [rbp+3Fh+var_78]
0x1801245cd  lea     r9, [rbp+3Fh+SecurityAttributes]; lpSecurityAttributes
0x1801245d1  mov     r8d, [rbp+3Fh+dwShareMode]; dwShareMode
0x1801245d5  btr     ebx, 1Fh
0x1801245d9  mov     rcx, [rbp+3Fh+lpFileName]; lpFileName
0x1801245dd  mov     [rsp+100h+hTemplateFile], rsi; hTemplateFile
0x1801245e2  mov     [rsp+100h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x1801245e6  mov     eax, [rbp+3Fh+var_BC]
0x1801245e9  mov     dword ptr [rbp+3Fh+var_B8+4], ebx
0x1801245ec  mov     rdx, qword ptr [rbp+3Fh+var_B8]
0x1801245f0  shr     rdx, 20h; dwDesiredAccess
0x1801245f4  mov     [rsp+100h+dwCreationDisposition], eax; dwCreationDisposition
0x1801245f8  call    cs:__imp_CreateFileW
0x1801245fe  mov     rdx, rax
0x180124601  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180124605  jnz     short loc_18012463A
0x180124607  call    cs:__imp_GetLastError
0x18012460d  mov     ecx, eax
0x18012460f  call    __acrt_errno_map_os_error
0x180124614  movsxd  rcx, dword ptr [rdi]
0x180124617  mov     rax, rcx
0x18012461a  and     ecx, 3Fh
0x18012461d  sar     rax, 6
0x180124621  lea     rcx, [rcx+rcx*8]
0x180124625  mov     rax, [r15+rax*8]
0x180124629  and     byte ptr [rax+rcx*8+38h], 0FEh
0x18012462e  mov     ecx, [rdi]
0x180124630  call    _free_osfhnd
0x180124635  jmp     loc_1801242E3
0x18012463a  movsxd  rcx, dword ptr [rdi]
0x18012463d  mov     rax, rcx
0x180124640  sar     rax, 6
0x180124644  and     ecx, 3Fh
0x180124647  mov     rax, [r15+rax*8]
0x18012464b  lea     rcx, [rcx+rcx*8]
0x18012464f  mov     [rax+rcx*8+28h], rdx
0x180124654  xor     eax, eax
0x180124656  lea     r11, [rsp+100h+var_20]
0x18012465e  mov     rbx, [r11+30h]
0x180124662  mov     rsi, [r11+38h]
0x180124666  mov     rdi, [r11+48h]
0x18012466a  mov     rsp, r11
0x18012466d  pop     r15
0x18012466f  pop     r14
0x180124671  pop     r13
0x180124673  pop     r12
0x180124675  pop     rbp
0x180124676  retn
```
