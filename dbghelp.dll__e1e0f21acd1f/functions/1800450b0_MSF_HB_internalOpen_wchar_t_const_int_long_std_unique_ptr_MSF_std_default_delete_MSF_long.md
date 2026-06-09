# MSF_HB::internalOpen(wchar_t const *,int,long *,std::unique_ptr<MSF,std::default_delete<MSF>> &,long)

- ea: `0x1800450b0`
- end: `0x18004533e`
- name: `?internalOpen@MSF_HB@@AEAAHPEB_WHPEAJAEAV?$unique_ptr@UMSF@@U?$default_delete@UMSF@@@std@@@std@@J@Z`
- size: `654`
- prototype: `__int64 __usercall@<rax>(MSF_HB *this@<rcx>, LPCWSTR lpFileName@<rdx>, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180041310`

## callees

- `0x1800269d4`
- `0x180041430`
- `0x180043650`
- `0x180043a40`
- `0x1800450b0`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180045178`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180045178`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800452b6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800452b6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045126`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045160`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045126`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180045160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800451d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800451d1`

## pseudocode

```c
__int64 __fastcall MSF_HB::internalOpen(
        MSF_HB *this,
        LPCWSTR lpFileName,
        int a3,
        int *a4,
        __int64 *a5,
        unsigned int a6)
{
  int v10; // r12d
  DWORD v11; // edx
  DWORD v12; // r8d
  HANDLE FileW; // rbp
  msfz::reader *v14; // rax
  msfz::reader *v15; // rbx
  msfz::reader **v16; // r15
  __int64 v17; // rcx
  __int64 result; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 *v21; // r9
  __int64 *v22; // rax
  unsigned int v23; // ebx
  __int64 v24; // rcx

  *a4 = 0;
  v10 = 0;
  if ( (a3 == 1 || (v11 = 0x80000000, a3 < 0)) && (v11 = -1073741824, a3 == 1) )
    v12 = 0;
  else
    v12 = (a3 | 0xBFFFFFFF) >> 29;
  FileW = CreateFileW(lpFileName, v11, v12, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    if ( !a3 )
      goto LABEL_14;
    FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_14;
    v10 = 1;
  }
  if ( GetFileType(FileW) == 1 )
  {
    v14 = (msfz::reader *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v14;
    if ( v14 )
    {
      *((_DWORD *)v14 + 2) = a3;
      *((_DWORD *)v14 + 6) = 0;
      *(_QWORD *)v14 = &IStreamFileWinAPI::`vftable'{for `IStreamInternal'};
      *((_QWORD *)v14 + 2) = &IStreamFileWinAPI::`vftable'{for `SymBase'};
      *((_QWORD *)v14 + 4) = FileW;
      CDiaInputAssemblyFile::AddRef(v14);
      goto LABEL_15;
    }
  }
  CloseHandle(FileW);
LABEL_14:
  v15 = 0;
LABEL_15:
  v16 = (msfz::reader **)((char *)this + 33056);
  v17 = *((_QWORD *)this + 4132);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  *v16 = v15;
  if ( !v15 )
  {
    *a4 = 4 - (a3 != 0);
    return 0;
  }
  v19 = 0;
  if ( v10 )
  {
    v20 = a6;
    v21 = qword_18022D5B0;
    *((_BYTE *)this + 33040) = 1;
    while ( 1 )
    {
      v22 = &qword_18022D5B0[5 * v19];
      if ( a6 == *(_DWORD *)v22 )
        break;
      v19 = (unsigned int)(v19 + 1);
      if ( (int)v19 >= 7 )
      {
        *a4 = 5;
        v23 = 0;
        goto LABEL_25;
      }
    }
    *((_OWORD *)this + 2060) = *(_OWORD *)v22;
    *((_OWORD *)this + 2061) = *((_OWORD *)v22 + 1);
    *((_QWORD *)this + 4124) = v22[4];
    v23 = MSF_HB::afterCreate(this, a4, a6);
    if ( v23 )
      return v23;
LABEL_25:
    if ( *v16 )
      (*(void (__fastcall **)(msfz::reader *, __int64, __int64, __int64 *))(*(_QWORD *)*v16 + 16LL))(
        *v16,
        v19,
        v20,
        v21);
    *v16 = 0;
    DeleteFileW(lpFileName);
    return v23;
  }
  if ( (int)msfz::reader::MsfzReader::Open(v15) < 0 )
    return (unsigned int)MSF_HB::afterOpen(this, a4);
  v24 = *a5;
  if ( !*a5 )
    return (unsigned int)MSF_HB::afterOpen(this, a4);
  if ( !a3 )
    return 1;
  *a5 = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 240LL))(v24, 1);
  result = 0;
  *a4 = 5;
  return result;
}

```

## disassembly

```asm
0x1800450b0  mov     [rsp+arg_0], rbx
0x1800450b5  mov     [rsp+arg_8], rbp
0x1800450ba  mov     [rsp+arg_10], rsi
0x1800450bf  push    rdi
0x1800450c0  push    r12
0x1800450c2  push    r13
0x1800450c4  push    r14
0x1800450c6  push    r15
0x1800450c8  sub     rsp, 40h
0x1800450cc  xor     r15d, r15d
0x1800450cf  mov     r14, r9
0x1800450d2  mov     [r9], r15d
0x1800450d5  mov     edi, r8d
0x1800450d8  mov     r13, rdx
0x1800450db  mov     rsi, rcx
0x1800450de  mov     r12d, r15d
0x1800450e1  cmp     r8d, 1
0x1800450e5  jz      short loc_1800450F1
0x1800450e7  mov     edx, 80000000h; dwDesiredAccess
0x1800450ec  test    r8d, r8d
0x1800450ef  jns     short loc_180045100
0x1800450f1  mov     edx, 0C0000000h
0x1800450f6  cmp     edi, 1
0x1800450f9  jnz     short loc_180045100
0x1800450fb  mov     r8d, r15d
0x1800450fe  jmp     short loc_18004510B
0x180045100  or      r8d, 0BFFFFFFFh
0x180045107  shr     r8d, 1Dh; dwShareMode
0x18004510b  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180045110  xor     r9d, r9d; lpSecurityAttributes
0x180045113  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004511b  mov     rcx, r13; lpFileName
0x18004511e  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180045126  call    cs:__imp_CreateFileW
0x18004512c  mov     rbp, rax
0x18004512f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045133  jnz     short loc_180045175
0x180045135  test    edi, edi
0x180045137  jz      loc_1800451D7
0x18004513d  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180045142  xor     r9d, r9d; lpSecurityAttributes
0x180045145  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004514d  xor     r8d, r8d; dwShareMode
0x180045150  mov     edx, 0C0000000h; dwDesiredAccess
0x180045155  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18004515d  mov     rcx, r13; lpFileName
0x180045160  call    cs:__imp_CreateFileW
0x180045166  mov     rbp, rax
0x180045169  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004516d  jz      short loc_1800451D7
0x18004516f  mov     r12d, 1
0x180045175  mov     rcx, rbp; hFile
0x180045178  call    cs:__imp_GetFileType
0x18004517e  cmp     eax, 1
0x180045181  jnz     short loc_1800451CE
0x180045183  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004518a  mov     ecx, 28h ; '('; unsigned __int64
0x18004518f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180045194  mov     rbx, rax
0x180045197  test    rax, rax
0x18004519a  jz      short loc_1800451CE
0x18004519c  mov     [rax+8], edi
0x18004519f  mov     rcx, rbx
0x1800451a2  mov     [rax+18h], r15d
0x1800451a6  lea     rax, ??_7IStreamFileWinAPI@@6BIStreamInternal@@@; const IStreamFileWinAPI::`vftable'{for `IStreamInternal'}
0x1800451ad  mov     [rbx], rax
0x1800451b0  lea     rax, ??_7IStreamFileWinAPI@@6BSymBase@@@; const IStreamFileWinAPI::`vftable'{for `SymBase'}
0x1800451b7  mov     [rbx+10h], rax
0x1800451bb  mov     [rbx+20h], rbp
0x1800451bf  mov     rax, cs:off_180206B00
0x1800451c6  call    cs:__guard_dispatch_icall_fptr
0x1800451cc  jmp     short loc_1800451DA
0x1800451ce  mov     rcx, rbp; hObject
0x1800451d1  call    cs:__imp_CloseHandle
0x1800451d7  mov     rbx, r15
0x1800451da  mov     rcx, rsi
0x1800451dd  mov     eax, 8120h
0x1800451e2  lea     r15, [rcx+rax]
0x1800451e6  mov     rcx, [rcx+rax]
0x1800451ea  test    rcx, rcx
0x1800451ed  jz      short loc_1800451FC
0x1800451ef  mov     rax, [rcx]
0x1800451f2  mov     rax, [rax+10h]
0x1800451f6  call    cs:__guard_dispatch_icall_fptr
0x1800451fc  mov     [r15], rbx
0x1800451ff  test    rbx, rbx
0x180045202  jnz     short loc_180045215
0x180045204  neg     edi
0x180045206  sbb     eax, eax
0x180045208  add     eax, 4
0x18004520b  mov     [r14], eax
0x18004520e  xor     eax, eax
0x180045210  jmp     loc_18004531E
0x180045215  xor     edx, edx
0x180045217  test    r12d, r12d
0x18004521a  jz      loc_1800452BE
0x180045220  mov     r8d, [rsp+68h+arg_28]; int
0x180045228  lea     r9, qword_18022D5B0
0x18004522f  mov     byte ptr [rsi+8110h], 1
0x180045236  nop     word ptr [rax+rax+00000000h]
0x180045240  lea     rcx, [rdx+rdx*4]
0x180045244  cmp     r8d, [r9+rcx*8]
0x180045248  lea     rax, [r9+rcx*8]
0x18004524c  jz      short loc_180045260
0x18004524e  inc     edx
0x180045250  cmp     edx, 7
0x180045253  jl      short loc_180045240
0x180045255  mov     dword ptr [r14], 5
0x18004525c  xor     ebx, ebx
0x18004525e  jmp     short loc_180045297
0x180045260  movups  xmm0, xmmword ptr [rax]
0x180045263  mov     rdx, r14; int *
0x180045266  mov     rcx, rsi; this
0x180045269  movups  xmmword ptr [rsi+80C0h], xmm0
0x180045270  movups  xmm1, xmmword ptr [rax+10h]
0x180045274  movups  xmmword ptr [rsi+80D0h], xmm1
0x18004527b  movsd   xmm0, qword ptr [rax+20h]
0x180045280  movsd   qword ptr [rsi+80E0h], xmm0
0x180045288  call    ?afterCreate@MSF_HB@@AEAAHPEAJJ@Z; MSF_HB::afterCreate(long *,long)
0x18004528d  mov     ebx, eax
0x18004528f  test    eax, eax
0x180045291  jnz     loc_18004531C
0x180045297  mov     rcx, [r15]
0x18004529a  test    rcx, rcx
0x18004529d  jz      short loc_1800452AC
0x18004529f  mov     rax, [rcx]
0x1800452a2  mov     rax, [rax+10h]
0x1800452a6  call    cs:__guard_dispatch_icall_fptr
0x1800452ac  mov     rcx, r13; lpFileName
0x1800452af  mov     qword ptr [r15], 0
0x1800452b6  call    cs:__imp_DeleteFileW
0x1800452bc  jmp     short loc_18004531C
0x1800452be  mov     r15, [rsp+68h+arg_20]
0x1800452c6  mov     rcx, rbx; this
0x1800452c9  mov     r8, r15
0x1800452cc  call    ?Open@MsfzReader@reader@msfz@@SAJPEAUIStream@@IAEAV?$unique_ptr@UMSF@@U?$default_delete@UMSF@@@std@@@std@@@Z; msfz::reader::MsfzReader::Open(IStream *,uint,std::unique_ptr<MSF> &)
0x1800452d1  test    eax, eax
0x1800452d3  js      short loc_18004530F
0x1800452d5  mov     rcx, [r15]
0x1800452d8  test    rcx, rcx
0x1800452db  jz      short loc_18004530F
0x1800452dd  test    edi, edi
0x1800452df  jz      short loc_180045308
0x1800452e1  mov     qword ptr [r15], 0
0x1800452e8  mov     edx, 1
0x1800452ed  mov     rax, [rcx]
0x1800452f0  mov     rax, [rax+0F0h]
0x1800452f7  call    cs:__guard_dispatch_icall_fptr
0x1800452fd  xor     eax, eax
0x1800452ff  mov     dword ptr [r14], 5
0x180045306  jmp     short loc_18004531E
0x180045308  mov     eax, 1
0x18004530d  jmp     short loc_18004531E
0x18004530f  mov     rdx, r14; int *
0x180045312  mov     rcx, rsi; this
0x180045315  call    ?afterOpen@MSF_HB@@AEAAHPEAJ@Z; MSF_HB::afterOpen(long *)
0x18004531a  mov     ebx, eax
0x18004531c  mov     eax, ebx
0x18004531e  mov     rbx, [rsp+68h+arg_0]
0x180045323  mov     rbp, [rsp+68h+arg_8]
0x180045328  mov     rsi, [rsp+68h+arg_10]
0x180045330  add     rsp, 40h
0x180045334  pop     r15
0x180045336  pop     r14
0x180045338  pop     r13
0x18004533a  pop     r12
0x18004533c  pop     rdi
0x18004533d  retn
```
