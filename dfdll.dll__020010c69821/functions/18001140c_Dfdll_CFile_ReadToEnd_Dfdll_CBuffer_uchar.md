# Dfdll::CFile::ReadToEnd(Dfdll::CBuffer<uchar> &)

- ea: `0x18001140c`
- end: `0x1800116ac`
- name: `?ReadToEnd@CFile@Dfdll@@QEAAJAEAV?$CBuffer@E@2@@Z`
- size: `672`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800116ac`

## callees

- `0x180001fc8`
- `0x18001138c`
- `0x18001140c`
- `0x180012b30`
- `0x1800140a0`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011453`
- `KERNEL32!GetLastError` at `0x1800114a7`
- `KERNEL32!GetLastError` at `0x180011453`
- `KERNEL32!GetLastError` at `0x1800114a7`
- `KERNEL32!GetFileSize` at `0x18001144b`
- `KERNEL32!GetFileSize` at `0x18001144b`
- `KERNEL32!SetFilePointer` at `0x18001149e`
- `KERNEL32!SetFilePointer` at `0x18001149e`

## pseudocode

```c
__int64 __fastcall Dfdll::CFile::ReadToEnd(__int64 a1, _DWORD *a2)
{
  void *v4; // r15
  signed int v5; // edi
  __int64 FileSize; // rbx
  signed int LastError; // eax
  __int64 v8; // rsi
  void *v9; // rbx
  DWORD v10; // eax
  int v11; // ecx
  signed int v12; // eax
  unsigned __int64 v13; // rsi
  const struct std::nothrow_t *v14; // rdx
  unsigned int v15; // ebx
  const void *v16; // r15
  unsigned int v17; // ecx
  const struct std::nothrow_t *v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  void **v21; // [rsp+30h] [rbp-20h] BYREF
  void *v22; // [rsp+38h] [rbp-18h]
  unsigned int v23; // [rsp+40h] [rbp-10h]
  unsigned int v24; // [rsp+90h] [rbp+40h] BYREF
  void *FileSizeHigh; // [rsp+A0h] [rbp+50h] BYREF

  v4 = *(void **)(a1 + 8);
  if ( v4 == (void *)-1LL )
    return (unsigned int)-2147024883;
  LODWORD(FileSizeHigh) = 0;
  FileSize = GetFileSize(v4, (LPDWORD)&FileSizeHigh);
  LastError = GetLastError();
  if ( (_DWORD)FileSize == -1 && LastError )
  {
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return (unsigned int)LastError;
    return (unsigned int)v5;
  }
  v8 = FileSize | (16LL * (unsigned int)FileSizeHigh);
  v9 = 0;
  FileSizeHigh = 0;
  LODWORD(FileSizeHigh) = SetFilePointer(v4, 0, (PLONG)&FileSizeHigh + 1, 1u);
  v10 = GetLastError();
  v11 = v10;
  if ( (_DWORD)FileSizeHigh != -1 || !v10 )
  {
    v9 = FileSizeHigh;
    goto LABEL_17;
  }
  v12 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 <= 0 )
    v12 = v11;
  v5 = 0;
  if ( v12 < 0 )
    v5 = v12;
  if ( v5 >= 0 )
  {
LABEL_17:
    v13 = v8 - (_QWORD)v9;
    if ( v13 > 0xFFFFFFFF )
      return (unsigned int)-2147016584;
    v24 = v13;
    v5 = Dfdll::CFile::Read(a1, a2, &v24);
    if ( v5 < 0 )
      return (unsigned int)v5;
    if ( a2[4] <= v24 )
    {
      v5 = -2147418113;
      if ( a2[4] < v24 )
        return (unsigned int)v5;
    }
    else
    {
      v22 = 0;
      v23 = 0;
      v21 = &Dfdll::CBuffer<unsigned char>::`vftable';
      v5 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)&v21, v24);
      if ( v5 < 0 )
      {
        v21 = &Dfdll::CBuffer<unsigned char>::`vftable';
        if ( v22 )
          operator delete(v22, v14);
        return (unsigned int)v5;
      }
      v15 = v24;
      v16 = (const void *)*((_QWORD *)a2 + 1);
      if ( !v16 )
        goto LABEL_26;
      if ( v24 )
      {
        if ( !v23 || v23 < v24 )
        {
LABEL_26:
          v5 = -2147024809;
          goto LABEL_27;
        }
        FileSizeHigh = 0;
        v5 = ((__int64 (__fastcall *)(void ***, _QWORD, void **))v21[8])(&v21, 0, &FileSizeHigh);
        if ( v5 < 0 )
        {
LABEL_27:
          v21 = &Dfdll::CBuffer<unsigned char>::`vftable';
          if ( v22 )
            operator delete(v22, v14);
          return (unsigned int)v5;
        }
        v17 = ((__int64 (__fastcall *)(void ***))v21[9])(&v21);
        if ( v17 )
        {
          v14 = (const struct std::nothrow_t *)(0xFFFFFFFF % v17);
          if ( v15 > 0xFFFFFFFF / v17 )
          {
            v5 = -2147024362;
            goto LABEL_27;
          }
          v17 *= v15;
        }
        memmove(FileSizeHigh, v16, v17);
      }
      (*(void (__fastcall **)(_DWORD *, _DWORD *, _DWORD *))(*(_QWORD *)a2 + 88LL))(a2, a2 + 2, a2 + 4);
      *((_QWORD *)a2 + 1) = 0;
      a2[4] = 0;
      v5 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)a2, v24);
      if ( v5 < 0 )
      {
        v21 = &Dfdll::CBuffer<unsigned char>::`vftable';
        if ( v22 )
          operator delete(v22, v18);
        return (unsigned int)v5;
      }
      v5 = (*(__int64 (__fastcall **)(_DWORD *, void *, _QWORD, _QWORD))(*(_QWORD *)a2 + 104LL))(a2, v22, 0, v24);
      if ( v5 < 0 )
      {
        v21 = &Dfdll::CBuffer<unsigned char>::`vftable';
        if ( v22 )
          operator delete(v22, v19);
        return (unsigned int)v5;
      }
      v21 = &Dfdll::CBuffer<unsigned char>::`vftable';
      if ( v22 )
        operator delete(v22, v19);
    }
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001140c  mov     [rsp-38h+arg_8], rbx
0x180011411  push    rbp
0x180011412  push    rsi
0x180011413  push    rdi
0x180011414  push    r12
0x180011416  push    r13
0x180011418  push    r14
0x18001141a  push    r15
0x18001141c  mov     rbp, rsp
0x18001141f  sub     rsp, 50h
0x180011423  mov     r14, rdx
0x180011426  mov     r13, rcx
0x180011429  mov     r15, [rcx+8]
0x18001142d  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180011431  jnz     short loc_18001143D
0x180011433  mov     edi, 8007000Dh
0x180011438  jmp     loc_180011692
0x18001143d  xor     r12d, r12d
0x180011440  mov     [rbp+FileSizeHigh], r12d
0x180011444  lea     rdx, [rbp+FileSizeHigh]; lpFileSizeHigh
0x180011448  mov     rcx, r15; hFile
0x18001144b  call    cs:__imp_GetFileSize
0x180011451  mov     ebx, eax
0x180011453  call    cs:__imp_GetLastError
0x180011459  mov     ecx, 0FFFFFFFFh
0x18001145e  cmp     ebx, ecx
0x180011460  jnz     short loc_180011481
0x180011462  test    eax, eax
0x180011464  jz      short loc_180011481
0x180011466  movzx   edi, ax
0x180011469  or      edi, 80070000h
0x18001146f  test    eax, eax
0x180011471  cmovle  edi, eax
0x180011474  mov     esi, r12d
0x180011477  test    edi, edi
0x180011479  js      loc_180011692
0x18001147f  jmp     short loc_18001148B
0x180011481  mov     esi, [rbp+FileSizeHigh]
0x180011484  shl     rsi, 4
0x180011488  or      rsi, rbx
0x18001148b  xor     ebx, ebx
0x18001148d  mov     qword ptr [rbp+FileSizeHigh], r12
0x180011491  lea     r9d, [rbx+1]; dwMoveMethod
0x180011495  lea     r8, [rbp+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180011499  xor     edx, edx; lDistanceToMove
0x18001149b  mov     rcx, r15; hFile
0x18001149e  call    cs:__imp_SetFilePointer
0x1800114a4  mov     [rbp+FileSizeHigh], eax
0x1800114a7  call    cs:__imp_GetLastError
0x1800114ad  mov     ecx, eax
0x1800114af  mov     edx, 0FFFFFFFFh
0x1800114b4  cmp     [rbp+FileSizeHigh], edx
0x1800114b7  jnz     short loc_1800114DC
0x1800114b9  test    eax, eax
0x1800114bb  jz      short loc_1800114DC
0x1800114bd  movzx   eax, cx
0x1800114c0  or      eax, 80070000h
0x1800114c5  test    ecx, ecx
0x1800114c7  cmovle  eax, ecx
0x1800114ca  mov     edi, r12d
0x1800114cd  test    eax, eax
0x1800114cf  cmovs   edi, eax
0x1800114d2  test    edi, edi
0x1800114d4  js      loc_180011692
0x1800114da  jmp     short loc_1800114E0
0x1800114dc  mov     rbx, qword ptr [rbp+FileSizeHigh]
0x1800114e0  sub     rsi, rbx
0x1800114e3  cmp     rsi, rdx
0x1800114e6  jbe     short loc_1800114F2
0x1800114e8  mov     edi, 80072078h
0x1800114ed  jmp     loc_180011692
0x1800114f2  mov     [rbp+arg_0], esi
0x1800114f5  lea     r8, [rbp+arg_0]
0x1800114f9  mov     rdx, r14
0x1800114fc  mov     rcx, r13
0x1800114ff  call    ?Read@CFile@Dfdll@@QEAAJAEAV?$CBuffer@E@2@AEAK@Z; Dfdll::CFile::Read(Dfdll::CBuffer<uchar> &,ulong &)
0x180011504  mov     edi, eax
0x180011506  test    eax, eax
0x180011508  js      loc_180011692
0x18001150e  lea     rsi, [r14+10h]
0x180011512  mov     eax, [rbp+arg_0]
0x180011515  cmp     [rsi], eax
0x180011517  jbe     loc_180011688
0x18001151d  mov     [rbp+var_18], r12
0x180011521  mov     [rbp+var_10], r12d
0x180011525  lea     r13, ??_7?$CBuffer@E@Dfdll@@6B@; const Dfdll::CBuffer<uchar>::`vftable'
0x18001152c  mov     [rbp+var_20], r13
0x180011530  mov     edx, eax; unsigned int
0x180011532  lea     rcx, [rbp+var_20]; this
0x180011536  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x18001153b  mov     edi, eax
0x18001153d  test    eax, eax
0x18001153f  jns     short loc_180011559
0x180011541  mov     [rbp+var_20], r13
0x180011545  mov     rcx, [rbp+var_18]; void *
0x180011549  test    rcx, rcx
0x18001154c  jz      short loc_180011554
0x18001154e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011553  nop
0x180011554  jmp     loc_180011692
0x180011559  mov     ebx, [rbp+arg_0]
0x18001155c  lea     r12, [r14+8]
0x180011560  mov     r15, [r12]
0x180011564  test    r15, r15
0x180011567  jnz     short loc_180011586
0x180011569  mov     edi, 80070057h
0x18001156e  mov     [rbp+var_20], r13
0x180011572  mov     rcx, [rbp+var_18]; void *
0x180011576  test    rcx, rcx
0x180011579  jz      short loc_180011581
0x18001157b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011580  nop
0x180011581  jmp     loc_180011692
0x180011586  test    ebx, ebx
0x180011588  jz      short loc_1800115F6
0x18001158a  mov     eax, [rbp+var_10]
0x18001158d  test    eax, eax
0x18001158f  jz      short loc_180011569
0x180011591  cmp     eax, ebx
0x180011593  jb      short loc_180011569
0x180011595  and     qword ptr [rbp+FileSizeHigh], 0
0x18001159a  mov     rax, [rbp+var_20]
0x18001159e  lea     r8, [rbp+FileSizeHigh]
0x1800115a2  xor     edx, edx
0x1800115a4  lea     rcx, [rbp+var_20]
0x1800115a8  mov     rax, [rax+40h]
0x1800115ac  call    cs:__guard_dispatch_icall_fptr
0x1800115b2  mov     edi, eax
0x1800115b4  test    eax, eax
0x1800115b6  js      short loc_18001156E
0x1800115b8  mov     rax, [rbp+var_20]
0x1800115bc  lea     rcx, [rbp+var_20]
0x1800115c0  mov     rax, [rax+48h]
0x1800115c4  call    cs:__guard_dispatch_icall_fptr
0x1800115ca  mov     ecx, eax
0x1800115cc  test    eax, eax
0x1800115ce  jz      short loc_1800115E7
0x1800115d0  xor     edx, edx
0x1800115d2  mov     eax, 0FFFFFFFFh
0x1800115d7  div     ecx
0x1800115d9  cmp     ebx, eax
0x1800115db  jbe     short loc_1800115E4
0x1800115dd  mov     edi, 80070216h
0x1800115e2  jmp     short loc_18001156E
0x1800115e4  imul    ecx, ebx
0x1800115e7  mov     r8d, ecx; Size
0x1800115ea  mov     rdx, r15; Src
0x1800115ed  mov     rcx, qword ptr [rbp+FileSizeHigh]; void *
0x1800115f1  call    memmove
0x1800115f6  mov     rax, [r14]
0x1800115f9  mov     r8, rsi
0x1800115fc  mov     rdx, r12
0x1800115ff  mov     rcx, r14
0x180011602  mov     rax, [rax+58h]
0x180011606  call    cs:__guard_dispatch_icall_fptr
0x18001160c  and     qword ptr [r12], 0
0x180011611  xor     r12d, r12d
0x180011614  mov     [rsi], r12d
0x180011617  mov     edx, [rbp+arg_0]; unsigned int
0x18001161a  mov     rcx, r14; this
0x18001161d  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180011622  mov     edi, eax
0x180011624  test    eax, eax
0x180011626  jns     short loc_18001163D
0x180011628  mov     [rbp+var_20], r13
0x18001162c  mov     rcx, [rbp+var_18]; void *
0x180011630  test    rcx, rcx
0x180011633  jz      short loc_18001163B
0x180011635  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001163a  nop
0x18001163b  jmp     short loc_180011692
0x18001163d  mov     rax, [r14]
0x180011640  mov     r9d, [rbp+arg_0]
0x180011644  xor     r8d, r8d
0x180011647  mov     rdx, [rbp+var_18]
0x18001164b  mov     rcx, r14
0x18001164e  mov     rax, [rax+68h]
0x180011652  call    cs:__guard_dispatch_icall_fptr
0x180011658  mov     edi, eax
0x18001165a  test    eax, eax
0x18001165c  jns     short loc_180011673
0x18001165e  mov     [rbp+var_20], r13
0x180011662  mov     rcx, [rbp+var_18]; void *
0x180011666  test    rcx, rcx
0x180011669  jz      short loc_180011671
0x18001166b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011670  nop
0x180011671  jmp     short loc_180011692
0x180011673  mov     [rbp+var_20], r13
0x180011677  mov     rcx, [rbp+var_18]; void *
0x18001167b  test    rcx, rcx
0x18001167e  jz      short loc_180011686
0x180011680  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011685  nop
0x180011686  jmp     short loc_18001168F
0x180011688  mov     edi, 8000FFFFh
0x18001168d  jb      short loc_180011692
0x18001168f  mov     edi, r12d
0x180011692  mov     eax, edi
0x180011694  mov     rbx, [rsp+50h+arg_8]
0x18001169c  add     rsp, 50h
0x1800116a0  pop     r15
0x1800116a2  pop     r14
0x1800116a4  pop     r13
0x1800116a6  pop     r12
0x1800116a8  pop     rdi
0x1800116a9  pop     rsi
0x1800116aa  pop     rbp
0x1800116ab  retn
```
