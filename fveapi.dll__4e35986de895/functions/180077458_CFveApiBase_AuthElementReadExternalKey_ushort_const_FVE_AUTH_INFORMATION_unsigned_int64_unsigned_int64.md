# CFveApiBase::AuthElementReadExternalKey(ushort const *,_FVE_AUTH_INFORMATION *,unsigned __int64,unsigned __int64 *)

- ea: `0x180077458`
- end: `0x1800778f4`
- name: `?AuthElementReadExternalKey@CFveApiBase@@SAJPEBGPEAU_FVE_AUTH_INFORMATION@@_KPEA_K@Z`
- size: `1180`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _FVE_AUTH_INFORMATION *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1800639f0`

## callees

- `0x180005410`
- `0x180018b10`
- `0x18001b260`
- `0x180037f50`
- `0x18003d000`
- `0x1800476f0`
- `0x18005e158`
- `0x180060196`
- `0x180077458`
- `0x18010ddf0`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800778b2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180122f94`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800778b2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180122f94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007785f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180122f3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007785f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180122f3a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800775d3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800775d3`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180077566`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180077566`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180077538`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180077538`

## pseudocode

```c
__int64 __fastcall CFveApiBase::AuthElementReadExternalKey(
        LPCWSTR lpFileName,
        struct _FVE_AUTH_INFORMATION *a2,
        unsigned __int64 a3,
        unsigned __int64 *a4)
{
  __int64 v7; // r13
  _OWORD *v8; // r14
  void *v9; // r15
  DWORD LowPart; // r12d
  unsigned int LastHresultError; // ebx
  __int64 v12; // rdi
  HANDLE FileW; // rax
  void *v14; // rax
  int v15; // eax
  int v16; // eax
  _DWORD *v17; // rax
  __int16 v18; // ax
  __int64 v19; // rax
  __int64 v20; // r8
  int i; // edx
  size_t v22; // rdx
  unsigned __int64 v23; // r12
  unsigned __int64 v24; // rcx
  __int64 v25; // rax
  char *v26; // rbx
  char *v27; // r12
  int v28; // r15d
  unsigned int *v29; // rbx
  _BYTE *v30; // rax
  _WORD v32[2]; // [rsp+40h] [rbp-108h] BYREF
  DWORD v33; // [rsp+44h] [rbp-104h]
  int v34; // [rsp+48h] [rbp-100h]
  __int64 v35; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v36; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v37; // [rsp+60h] [rbp-E8h] BYREF
  char *v38; // [rsp+68h] [rbp-E0h]
  void *v39; // [rsp+70h] [rbp-D8h]
  __int64 v40; // [rsp+78h] [rbp-D0h]
  _DWORD *v41; // [rsp+80h] [rbp-C8h]
  void *Src[2]; // [rsp+88h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+98h] [rbp-B0h]
  unsigned __int64 *v44; // [rsp+A0h] [rbp-A8h]
  unsigned __int64 v45; // [rsp+A8h] [rbp-A0h]
  void *v46; // [rsp+B0h] [rbp-98h] BYREF
  DWORD NumberOfBytesRead; // [rsp+F0h] [rbp-58h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+F8h] [rbp-50h] BYREF

  v44 = a4;
  v45 = a3;
  memset_0(&v46, 0, 0x40u);
  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  v7 = -1;
  v40 = -1;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  v8 = 0;
  v41 = 0;
  v9 = 0;
  v39 = 0;
  LowPart = 0;
  v33 = 0;
  if ( a3 < 0x38 || !a2 || *(_DWORD *)a2 != 56 || *((_DWORD *)a2 + 1) != 1 )
  {
    LastHresultError = -2147024809;
LABEL_3:
    v12 = 584;
    goto LABEL_41;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v7 = (__int64)FileW;
  v40 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL || !GetFileSizeEx(FileW, &FileSize) )
    goto LABEL_8;
  if ( FileSize.QuadPart > 0x1002FuLL )
  {
    LastHresultError = -2147024883;
    goto LABEL_3;
  }
  LowPart = FileSize.LowPart;
  v33 = FileSize.LowPart;
  v14 = CFveApiBase::ZeroAlloc(FileSize.LowPart);
  v9 = v14;
  v39 = v14;
  if ( !v14 )
  {
    LastHresultError = -2147024882;
    goto LABEL_3;
  }
  if ( !ReadFile((HANDLE)v7, v14, LowPart, &NumberOfBytesRead, 0) || LowPart != NumberOfBytesRead )
  {
LABEL_8:
    LastHresultError = GetLastHresultError();
    goto LABEL_3;
  }
  v15 = FveDatumFromExternalFileData(
          (_DWORD)v9,
          LowPart,
          (unsigned int)Src,
          (unsigned int)&v36,
          (__int64)&v35,
          (__int64)&v37);
  v16 = FromNtStatus(v15);
  LastHresultError = v16;
  v12 = 584;
  if ( v16 >= 0 )
  {
    v17 = operator new(0x248u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v17;
    v41 = v17;
    if ( v17 )
    {
      *v17 = 48;
      v17[1] = 1;
      v17[3] = 4;
      v17[2] = 1;
      v18 = 0;
      if ( *(_WORD *)v35 >= 0xCu )
        v18 = *(_WORD *)v35 - 12;
      if ( v18 == 32 )
      {
        v19 = v35;
        v8[1] = *(_OWORD *)(v35 + 12);
        v8[2] = *(_OWORD *)(v19 + 28);
        v46 = v8;
        Src[0] = 0;
        v32[0] = 0;
        if ( v37 && (int)FveDatumGetDataSegment(v37, Src, v32) < 0 )
          v32[0] = 0;
        v20 = 0;
        v43 = 0;
        for ( i = 0; ; i = 1 )
        {
          v34 = i;
          if ( i )
            break;
          v20 += (*(unsigned int *)v46 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL;
          v43 = v20;
        }
        v22 = v32[0];
        v23 = (v32[0] + 71LL) & 0xFFFFFFFFFFFFFFF0uLL;
        v24 = v20 + v23 + 16;
        *v44 = v24;
        v25 = v36;
        *(_OWORD *)((char *)a2 + 40) = *(_OWORD *)(v36 + 8);
        *((_QWORD *)a2 + 4) = *(_QWORD *)(v25 + 24);
        *((_DWORD *)a2 + 2) = 262145;
        if ( v24 <= v45 )
        {
          v26 = (char *)a2 + 56;
          v38 = (char *)a2 + 56;
          if ( v32[0] < 2u )
          {
            *((_QWORD *)a2 + 3) = 0;
          }
          else
          {
            *((_QWORD *)a2 + 3) = v26;
            memcpy_0((char *)a2 + 56, Src[0], v22);
            *(_WORD *)&v26[v32[0] - 2] = 0;
          }
          *((_DWORD *)a2 + 3) = 1;
          *((_QWORD *)a2 + 2) = (char *)a2 + v23;
          v27 = (char *)a2 + v23 + 16;
          v38 = v27;
          v28 = 0;
          v34 = 0;
          while ( !v28 )
          {
            **((_QWORD **)a2 + 2) = v27;
            v29 = (unsigned int *)v46;
            memcpy_0(v27, v46, *(unsigned int *)v46);
            v27 += (*v29 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL;
            v38 = v27;
            v28 = 1;
            v34 = 1;
          }
          LastHresultError = 0;
          v9 = v39;
        }
        else
        {
          *((_DWORD *)a2 + 3) = 0;
          *((_QWORD *)a2 + 2) = 0;
          *((_QWORD *)a2 + 3) = 0;
          LastHresultError = -2147024774;
        }
        LowPart = v33;
      }
      else
      {
        LastHresultError = -2147024883;
      }
    }
    else
    {
      LastHresultError = -2147024882;
    }
  }
  else if ( v16 == -2147024809 )
  {
    LastHresultError = -2144272332;
  }
LABEL_41:
  if ( v7 != -1 )
    CloseHandle((HANDLE)v7);
  if ( v36 )
    FveDatumFree(v36);
  if ( v35 )
    FveDatumFree(v35);
  if ( v37 )
    FveDatumFree(v37);
  if ( v8 )
  {
    v30 = v8;
    do
    {
      *v30++ = 0;
      --v12;
    }
    while ( v12 );
    operator delete(v8);
  }
  if ( v9 )
    CFveApiBase::ZeroFree(v9, LowPart);
  return LastHresultError;
}

```

## disassembly

```asm
0x180077458  push    rbx
0x18007745a  push    rsi
0x18007745b  push    rdi
0x18007745c  push    r12
0x18007745e  push    r13
0x180077460  push    r14
0x180077462  push    r15
0x180077464  sub     rsp, 110h
0x18007746b  mov     rax, cs:__security_cookie
0x180077472  xor     rax, rsp
0x180077475  mov     [rsp+148h+var_48], rax
0x18007747d  mov     [rsp+148h+var_A8], r9
0x180077485  mov     rdi, r8
0x180077488  mov     [rsp+148h+var_A0], r8
0x180077490  mov     rsi, rdx
0x180077493  mov     rbx, rcx
0x180077496  xor     edx, edx; Val
0x180077498  lea     r8d, [rdx+40h]; Size
0x18007749c  lea     rcx, [rsp+148h+var_98]; void *
0x1800774a4  call    memset_0
0x1800774a9  xor     r9d, r9d
0x1800774ac  mov     qword ptr [rsp+148h+FileSize], r9
0x1800774b4  mov     [rsp+148h+NumberOfBytesRead], r9d
0x1800774bc  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800774c0  mov     [rsp+148h+var_D0], r13
0x1800774c5  mov     [rsp+148h+var_F0], r9
0x1800774ca  mov     [rsp+148h+var_F8], r9
0x1800774cf  mov     [rsp+148h+var_E8], r9
0x1800774d4  mov     r14d, r9d
0x1800774d7  mov     [rsp+148h+var_C8], r9
0x1800774df  mov     r15d, r9d
0x1800774e2  mov     [rsp+148h+var_D8], r9
0x1800774e7  mov     r12d, r9d
0x1800774ea  mov     [rsp+148h+var_104], r9d
0x1800774ef  cmp     rdi, 38h ; '8'
0x1800774f3  jnb     short loc_180077504
0x1800774f5  mov     ebx, 80070057h
0x1800774fa  mov     edi, 248h
0x1800774ff  jmp     loc_180077856
0x180077504  test    rsi, rsi
0x180077507  jz      short loc_1800774F5
0x180077509  cmp     dword ptr [rsi], 38h ; '8'
0x18007750c  jnz     short loc_1800774F5
0x18007750e  cmp     dword ptr [rsi+4], 1
0x180077512  jnz     short loc_1800774F5
0x180077514  mov     [rsp+148h+hTemplateFile], r9; hTemplateFile
0x180077519  mov     [rsp+148h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180077521  mov     [rsp+148h+dwCreationDisposition], 3; dwCreationDisposition
0x180077529  xor     r9d, r9d; lpSecurityAttributes
0x18007752c  mov     edx, 80000000h; dwDesiredAccess
0x180077531  lea     r8d, [r9+1]; dwShareMode
0x180077535  mov     rcx, rbx; lpFileName
0x180077538  call    cs:__imp_CreateFileW
0x18007753f  nop     dword ptr [rax+rax+00h]
0x180077544  mov     r13, rax
0x180077547  mov     [rsp+148h+var_D0], rax
0x18007754c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180077550  jnz     short loc_18007755B
0x180077552  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180077557  mov     ebx, eax
0x180077559  jmp     short loc_1800774FA
0x18007755b  lea     rdx, [rsp+148h+FileSize]; lpFileSize
0x180077563  mov     rcx, r13; hFile
0x180077566  call    cs:__imp_GetFileSizeEx
0x18007756d  nop     dword ptr [rax+rax+00h]
0x180077572  test    eax, eax
0x180077574  jz      short loc_180077552
0x180077576  cmp     qword ptr [rsp+148h+FileSize], 1002Fh
0x180077582  jbe     short loc_18007758E
0x180077584  mov     ebx, 8007000Dh
0x180077589  jmp     loc_1800774FA
0x18007758e  mov     r12d, dword ptr [rsp+148h+FileSize]
0x180077596  mov     [rsp+148h+var_104], r12d
0x18007759b  mov     ecx, r12d; unsigned __int64
0x18007759e  call    ?ZeroAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::ZeroAlloc(unsigned __int64)
0x1800775a3  mov     r15, rax
0x1800775a6  mov     [rsp+148h+var_D8], rax
0x1800775ab  xor     r9d, r9d
0x1800775ae  test    rax, rax
0x1800775b1  jnz     short loc_1800775BD
0x1800775b3  mov     ebx, 8007000Eh
0x1800775b8  jmp     loc_1800774FA
0x1800775bd  mov     qword ptr [rsp+148h+dwCreationDisposition], r9; lpOverlapped
0x1800775c2  lea     r9, [rsp+148h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800775ca  mov     r8d, r12d; nNumberOfBytesToRead
0x1800775cd  mov     rdx, r15; lpBuffer
0x1800775d0  mov     rcx, r13; hFile
0x1800775d3  call    cs:__imp_ReadFile
0x1800775da  nop     dword ptr [rax+rax+00h]
0x1800775df  test    eax, eax
0x1800775e1  jz      loc_180077552
0x1800775e7  cmp     r12d, [rsp+148h+NumberOfBytesRead]
0x1800775ef  jnz     loc_180077552
0x1800775f5  lea     rax, [rsp+148h+var_E8]
0x1800775fa  mov     qword ptr [rsp+148h+dwFlagsAndAttributes], rax
0x1800775ff  lea     rax, [rsp+148h+var_F8]
0x180077604  mov     qword ptr [rsp+148h+dwCreationDisposition], rax
0x180077609  lea     r9, [rsp+148h+var_F0]
0x18007760e  lea     r8, [rsp+148h+Src]
0x180077616  mov     rdx, r12
0x180077619  mov     rcx, r15
0x18007761c  call    FveDatumFromExternalFileData
0x180077621  mov     ecx, eax; int
0x180077623  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180077628  mov     ebx, eax
0x18007762a  mov     edi, 248h
0x18007762f  test    eax, eax
0x180077631  jns     short loc_180077648
0x180077633  cmp     eax, 80070057h
0x180077638  jnz     loc_180077856
0x18007763e  mov     ebx, 80310034h
0x180077643  jmp     loc_180077856
0x180077648  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007764f  mov     rcx, rdi; unsigned __int64
0x180077652  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180077657  mov     r14, rax
0x18007765a  mov     [rsp+148h+var_C8], rax
0x180077662  xor     r9d, r9d
0x180077665  test    rax, rax
0x180077668  jnz     short loc_180077674
0x18007766a  mov     ebx, 8007000Eh
0x18007766f  jmp     loc_180077856
0x180077674  mov     dword ptr [rax], 30h ; '0'
0x18007767a  mov     dword ptr [rax+4], 1
0x180077681  mov     dword ptr [rax+0Ch], 4
0x180077688  mov     dword ptr [rax+8], 1
0x18007768f  mov     rax, [rsp+148h+var_F8]
0x180077694  movzx   edx, word ptr [rax]
0x180077697  lea     ecx, [rdx-0Ch]
0x18007769a  mov     eax, r9d
0x18007769d  cmp     dx, 0Ch
0x1800776a1  cmovnb  ax, cx
0x1800776a5  cmp     ax, 20h ; ' '
0x1800776a9  jz      short loc_1800776B5
0x1800776ab  mov     ebx, 8007000Dh
0x1800776b0  jmp     loc_180077856
0x1800776b5  mov     rax, [rsp+148h+var_F8]
0x1800776ba  movups  xmm0, xmmword ptr [rax+0Ch]
0x1800776be  movups  xmmword ptr [r14+10h], xmm0
0x1800776c3  movups  xmm1, xmmword ptr [rax+1Ch]
0x1800776c7  movups  xmmword ptr [r14+20h], xmm1
0x1800776cc  mov     [rsp+148h+var_98], r14
0x1800776d4  mov     [rsp+148h+Src], r9
0x1800776dc  mov     [rsp+148h+var_108], r9w
0x1800776e2  mov     rcx, [rsp+148h+var_E8]
0x1800776e7  test    rcx, rcx
0x1800776ea  jz      short loc_18007770B
0x1800776ec  lea     r8, [rsp+148h+var_108]
0x1800776f1  lea     rdx, [rsp+148h+Src]
0x1800776f9  call    FveDatumGetDataSegment
0x1800776fe  xor     r9d, r9d
0x180077701  test    eax, eax
0x180077703  jns     short loc_18007770B
0x180077705  mov     [rsp+148h+var_108], r9w
0x18007770b  mov     r8, r9
0x18007770e  mov     [rsp+148h+var_B0], r9
0x180077716  mov     edx, r9d
0x180077719  mov     [rsp+148h+var_100], edx
0x18007771d  cmp     edx, 1
0x180077720  jnb     short loc_180077745
0x180077722  mov     eax, edx
0x180077724  mov     rcx, [rsp+rax*8+148h+var_98]
0x18007772c  mov     eax, [rcx]
0x18007772e  add     rax, 0Fh
0x180077732  and     rax, 0FFFFFFFFFFFFFFF0h
0x180077736  add     r8, rax
0x180077739  mov     [rsp+148h+var_B0], r8
0x180077741  inc     edx
0x180077743  jmp     short loc_180077719
0x180077745  movzx   edx, [rsp+148h+var_108]
0x18007774a  lea     r12, [rdx+47h]
0x18007774e  and     r12, 0FFFFFFFFFFFFFFF0h
0x180077752  lea     rcx, [r12+10h]
0x180077757  add     rcx, r8
0x18007775a  mov     rax, [rsp+148h+var_A8]
0x180077762  mov     [rax], rcx
0x180077765  mov     rax, [rsp+148h+var_F0]
0x18007776a  movups  xmm0, xmmword ptr [rax+8]
0x18007776e  movdqu  xmmword ptr [rsi+28h], xmm0
0x180077773  mov     rax, [rax+18h]
0x180077777  mov     [rsi+20h], rax
0x18007777b  mov     dword ptr [rsi+8], 40001h
0x180077782  cmp     rcx, [rsp+148h+var_A0]
0x18007778a  jbe     short loc_1800777A2
0x18007778c  mov     [rsi+0Ch], r9d
0x180077790  mov     [rsi+10h], r9
0x180077794  mov     [rsi+18h], r9
0x180077798  mov     ebx, 8007007Ah
0x18007779d  jmp     loc_180077851
0x1800777a2  lea     rbx, [rsi+38h]
0x1800777a6  mov     [rsp+148h+var_E0], rbx
0x1800777ab  cmp     [rsp+148h+var_108], 2
0x1800777b1  jb      short loc_1800777DA
0x1800777b3  mov     [rsi+18h], rbx
0x1800777b7  mov     r8, rdx; Size
0x1800777ba  mov     rdx, [rsp+148h+Src]; Src
0x1800777c2  mov     rcx, rbx; void *
0x1800777c5  call    memcpy_0
0x1800777ca  movzx   eax, [rsp+148h+var_108]
0x1800777cf  xor     r9d, r9d
0x1800777d2  mov     [rax+rbx-2], r9w
0x1800777d8  jmp     short loc_1800777DE
0x1800777da  mov     [rsi+18h], r9
0x1800777de  lea     rax, [r12-38h]
0x1800777e3  add     rax, rbx
0x1800777e6  mov     [rsp+148h+var_E0], rax
0x1800777eb  mov     dword ptr [rsi+0Ch], 1
0x1800777f2  mov     [rsi+10h], rax
0x1800777f6  lea     r12, [rax+10h]
0x1800777fa  mov     [rsp+148h+var_E0], r12
0x1800777ff  mov     r15d, r9d
0x180077802  mov     [rsp+148h+var_100], r9d
0x180077807  cmp     r15d, 1
0x18007780b  jnb     short loc_18007784A
0x18007780d  mov     ecx, r15d
0x180077810  mov     rax, [rsi+10h]
0x180077814  mov     [rax+rcx*8], r12
0x180077818  mov     rbx, [rsp+rcx*8+148h+var_98]
0x180077820  mov     r8d, [rbx]; Size
0x180077823  mov     rdx, rbx; Src
0x180077826  mov     rcx, r12; void *
0x180077829  call    memcpy_0
0x18007782e  mov     eax, [rbx]
0x180077830  add     rax, 0Fh
0x180077834  and     rax, 0FFFFFFFFFFFFFFF0h
0x180077838  add     r12, rax
0x18007783b  mov     [rsp+148h+var_E0], r12
0x180077840  inc     r15d
0x180077843  mov     [rsp+148h+var_100], r15d
0x180077848  jmp     short loc_180077807
0x18007784a  xor     ebx, ebx
0x18007784c  mov     r15, [rsp+148h+var_D8]
0x180077851  mov     r12d, [rsp+148h+var_104]
0x180077856  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18007785a  jz      short loc_18007786B
0x18007785c  mov     rcx, r13; hObject
0x18007785f  call    cs:__imp_CloseHandle
0x180077866  nop     dword ptr [rax+rax+00h]
0x18007786b  mov     rax, [rsp+148h+var_F0]
0x180077870  test    rax, rax
0x180077873  jz      short loc_18007787D
0x180077875  mov     rcx, rax
0x180077878  call    FveDatumFree
0x18007787d  mov     rcx, [rsp+148h+var_F8]
0x180077882  test    rcx, rcx
0x180077885  jz      short loc_18007788C
0x180077887  call    FveDatumFree
0x18007788c  mov     rcx, [rsp+148h+var_E8]
0x180077891  test    rcx, rcx
0x180077894  jz      short loc_18007789B
0x180077896  call    FveDatumFree
0x18007789b  test    r14, r14
0x18007789e  jz      short loc_1800778BE
0x1800778a0  mov     rax, r14
0x1800778a3  mov     byte ptr [rax], 0
0x1800778a6  inc     rax
0x1800778a9  sub     rdi, 1
0x1800778ad  jnz     short loc_1800778A3
0x1800778af  mov     rcx, r14
0x1800778b2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800778b9  nop     dword ptr [rax+rax+00h]
0x1800778be  test    r15, r15
0x1800778c1  jz      short loc_1800778CE
0x1800778c3  mov     edx, r12d; unsigned __int64
0x1800778c6  mov     rcx, r15; lpMem
0x1800778c9  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x1800778ce  mov     eax, ebx
0x1800778d0  mov     rcx, [rsp+148h+var_48]
0x1800778d8  xor     rcx, rsp; StackCookie
0x1800778db  call    __security_check_cookie
0x1800778e0  add     rsp, 110h
0x1800778e7  pop     r15
0x1800778e9  pop     r14
0x1800778eb  pop     r13
0x1800778ed  pop     r12
0x1800778ef  pop     rdi
0x1800778f0  pop     rsi
0x1800778f1  pop     rbx
0x1800778f2  retn
0x180122f27  push    rbp
0x180122f29  sub     rsp, 40h
0x180122f2d  mov     rbp, rdx
0x180122f30  mov     rcx, [rbp+78h]; hObject
0x180122f34  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180122f38  jz      short loc_180122F47
0x180122f3a  call    cs:__imp_CloseHandle
0x180122f41  nop     dword ptr [rax+rax+00h]
0x180122f46  nop
0x180122f47  mov     rcx, [rbp+58h]
0x180122f4b  test    rcx, rcx
0x180122f4e  jz      short loc_180122F56
0x180122f50  call    FveDatumFree
0x180122f55  nop
0x180122f56  mov     rcx, [rbp+50h]
0x180122f5a  test    rcx, rcx
0x180122f5d  jz      short loc_180122F65
0x180122f5f  call    FveDatumFree
0x180122f64  nop
0x180122f65  mov     rcx, [rbp+60h]
0x180122f69  test    rcx, rcx
  ... truncated ...
```
