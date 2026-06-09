# CNtfsStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800588a0`
- end: `0x180058a66`
- name: `?Stat@CNtfsStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `454`
- prototype: `int(CNtfsStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180058a70`

## callees

- `0x18001e2f0`
- `0x180023e70`
- `0x180042800`
- `0x180043100`
- `0x1800588a0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800589b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800589b7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800589ad`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800589ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005896f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005896f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800589d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800589d8`

## pseudocode

```c
__int64 __fastcall CNtfsStream::Stat(CNtfsStream *this, struct tagSTATSTG *a2, int a3)
{
  __int64 v7; // rbx
  signed int v8; // ebx
  unsigned __int16 *v9; // rdi
  SIZE_T v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  void *v13; // rcx
  signed int LastError; // eax
  int v15; // eax
  __int128 v16; // xmm0
  __int128 v17; // [rsp+20h] [rbp-59h] BYREF
  unsigned __int64 v18; // [rsp+30h] [rbp-49h]
  __int64 v19; // [rsp+38h] [rbp-41h]
  __int128 v20; // [rsp+40h] [rbp-39h]
  __int128 v21; // [rsp+50h] [rbp-29h]
  __int128 v22; // [rsp+60h] [rbp-19h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+70h] [rbp-9h] BYREF

  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !(unsigned int)IsValidReadPtrIn(a2, 0x50u) )
    return 2147680265LL;
  if ( (a3 & 0xFFFFFFFE) != 0 )
    return 2147680511LL;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), 0xFFFFFFFFLL);
  v7 = -1;
  if ( *((_QWORD *)this + 12) != -1 )
  {
    memset_0(&v17, 0, 0x50u);
    if ( (a3 & 1) != 0 )
    {
      v9 = 0;
      *(_QWORD *)&v17 = 0;
    }
    else
    {
      do
        ++v7;
      while ( *(_WORD *)(*((_QWORD *)this + 2) + 2 * v7) );
      v10 = (unsigned int)(2 * v7 + 2);
      v11 = v10;
      v12 = (unsigned __int16 *)CoTaskMemAlloc(v10);
      *(_QWORD *)&v17 = v12;
      v9 = v12;
      if ( !v12 )
      {
        v8 = -2147287032;
        goto LABEL_17;
      }
      StringCbCopyW(v12, v11, *((const unsigned __int16 **)this + 2));
    }
    v13 = (void *)*((_QWORD *)this + 12);
    DWORD2(v17) = 2;
    DWORD1(v21) = 6;
    if ( GetFileInformationByHandle(v13, &FileInformation) )
    {
      v8 = 0;
      v18 = __PAIR64__(FileInformation.nFileSizeHigh, FileInformation.nFileSizeLow);
      v15 = *((_DWORD *)this + 22);
      *(_OWORD *)a2 = v17;
      v19 = 0;
      *((_OWORD *)a2 + 1) = v18;
      v20 = 0u;
      *((_OWORD *)a2 + 2) = 0u;
      LODWORD(v21) = v15 & 0xFFFFEFFF;
      v16 = v22;
      *((_OWORD *)a2 + 3) = v21;
      *((_OWORD *)a2 + 4) = v16;
      goto LABEL_20;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      goto LABEL_20;
LABEL_17:
    if ( v9 )
      CoTaskMemFree(v9);
    goto LABEL_20;
  }
  v8 = -2147286782;
LABEL_20:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 32LL))(*((_QWORD *)this + 13));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800588a0  mov     [rsp-8+arg_10], rbx
0x1800588a5  push    rbp
0x1800588a6  push    rsi
0x1800588a7  push    rdi
0x1800588a8  push    r14
0x1800588aa  push    r15
0x1800588ac  lea     rbp, [rsp-37h]
0x1800588b1  sub     rsp, 0B0h
0x1800588b8  mov     rax, cs:__security_cookie
0x1800588bf  xor     rax, rsp
0x1800588c2  mov     [rbp+57h+var_28], rax
0x1800588c6  xor     eax, eax
0x1800588c8  xorps   xmm0, xmm0
0x1800588cb  mov     r14, rdx
0x1800588ce  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800588d1  mov     rsi, rcx
0x1800588d4  mov     edi, r8d
0x1800588d7  mov     rcx, r14; void *
0x1800588da  lea     edx, [rax+50h]; unsigned __int64
0x1800588dd  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800588e1  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800588e5  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800588e9  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x1800588ee  xor     r15d, r15d
0x1800588f1  test    eax, eax
0x1800588f3  jnz     short loc_1800588FF
0x1800588f5  mov     eax, 80030009h
0x1800588fa  jmp     loc_180058A43
0x1800588ff  test    edi, 0FFFFFFFEh
0x180058905  jz      short loc_180058911
0x180058907  mov     eax, 800300FFh
0x18005890c  jmp     loc_180058A43
0x180058911  mov     rcx, [rsi+68h]
0x180058915  or      edx, 0FFFFFFFFh
0x180058918  mov     rax, [rcx]
0x18005891b  mov     rax, [rax+18h]
0x18005891f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058924  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180058928  cmp     [rsi+60h], rbx
0x18005892c  jnz     short loc_180058938
0x18005892e  mov     ebx, 80030102h
0x180058933  jmp     loc_180058A31
0x180058938  xor     edx, edx; Val
0x18005893a  lea     rcx, [rbp+57h+var_B0]; void *
0x18005893e  lea     r8d, [rdx+50h]; Size
0x180058942  call    memset_0
0x180058947  test    dil, 1
0x18005894b  jz      short loc_180058956
0x18005894d  mov     rdi, r15
0x180058950  mov     qword ptr [rbp+57h+var_B0], r15
0x180058954  jmp     short loc_180058997
0x180058956  mov     rax, [rsi+10h]
0x18005895a  inc     rbx
0x18005895d  cmp     [rax+rbx*2], r15w
0x180058962  jnz     short loc_18005895A
0x180058964  lea     eax, ds:2[rbx*2]
0x18005896b  mov     ecx, eax; cb
0x18005896d  mov     ebx, eax
0x18005896f  call    cs:__imp_CoTaskMemAlloc
0x180058975  mov     qword ptr [rbp+57h+var_B0], rax
0x180058979  mov     rdi, rax
0x18005897c  test    rax, rax
0x18005897f  jnz     short loc_180058988
0x180058981  mov     ebx, 80030008h
0x180058986  jmp     short loc_1800589D0
0x180058988  mov     r8, [rsi+10h]; unsigned __int16 *
0x18005898c  mov     rdx, rbx; unsigned __int64
0x18005898f  mov     rcx, rax; unsigned __int16 *
0x180058992  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180058997  mov     rcx, [rsi+60h]; hFile
0x18005899b  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18005899f  mov     dword ptr [rbp+57h+var_B0+8], 2
0x1800589a6  mov     dword ptr [rbp+57h+var_80+4], 6
0x1800589ad  call    cs:__imp_GetFileInformationByHandle
0x1800589b3  test    eax, eax
0x1800589b5  jnz     short loc_1800589E0
0x1800589b7  call    cs:__imp_GetLastError
0x1800589bd  mov     ebx, eax
0x1800589bf  test    eax, eax
0x1800589c1  jle     short loc_1800589CC
0x1800589c3  movzx   ebx, ax
0x1800589c6  or      ebx, 80070000h
0x1800589cc  test    ebx, ebx
0x1800589ce  jns     short loc_180058A31
0x1800589d0  test    rdi, rdi
0x1800589d3  jz      short loc_180058A31
0x1800589d5  mov     rcx, rdi; pv
0x1800589d8  call    cs:__imp_CoTaskMemFree
0x1800589de  jmp     short loc_180058A31
0x1800589e0  mov     eax, [rbp+57h+FileInformation.nFileSizeLow]
0x1800589e3  mov     ebx, r15d
0x1800589e6  movaps  xmm0, [rbp+57h+var_B0]
0x1800589ea  mov     dword ptr [rbp+57h+var_A0], eax
0x1800589ed  mov     eax, [rbp+57h+FileInformation.nFileSizeHigh]
0x1800589f0  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800589f3  mov     eax, [rsi+58h]
0x1800589f6  movups  xmmword ptr [r14], xmm0
0x1800589fa  mov     qword ptr [rbp+57h+var_A0+8], r15
0x1800589fe  btr     eax, 0Ch
0x180058a02  movaps  xmm1, [rbp+57h+var_A0]
0x180058a06  movups  xmmword ptr [r14+10h], xmm1
0x180058a0b  mov     qword ptr [rbp+57h+var_90], r15
0x180058a0f  mov     qword ptr [rbp+57h+var_90+8], r15
0x180058a13  movaps  xmm0, [rbp+57h+var_90]
0x180058a17  movups  xmmword ptr [r14+20h], xmm0
0x180058a1c  mov     dword ptr [rbp+57h+var_80], eax
0x180058a1f  movaps  xmm1, [rbp+57h+var_80]
0x180058a23  movaps  xmm0, [rbp+57h+var_70]
0x180058a27  movups  xmmword ptr [r14+30h], xmm1
0x180058a2c  movups  xmmword ptr [r14+40h], xmm0
0x180058a31  mov     rcx, [rsi+68h]
0x180058a35  mov     rdx, [rcx]
0x180058a38  mov     rax, [rdx+20h]
0x180058a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a41  mov     eax, ebx
0x180058a43  mov     rcx, [rbp+57h+var_28]
0x180058a47  xor     rcx, rsp; StackCookie
0x180058a4a  call    __security_check_cookie
0x180058a4f  mov     rbx, [rsp+0D0h+arg_10]
0x180058a57  add     rsp, 0B0h
0x180058a5e  pop     r15
0x180058a60  pop     r14
0x180058a62  pop     rdi
0x180058a63  pop     rsi
0x180058a64  pop     rbp
0x180058a65  retn
```
