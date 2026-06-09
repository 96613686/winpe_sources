# CFileByteStreamSimple::InternalWriteAt(std::scoped_lock<Mso::optional_mutex<std::recursive_mutex>> const &,unsigned __int64,uchar const *,ulong,ulong *,IMetroProgress *)

- ea: `0x1800ff730`
- end: `0x1800ff99b`
- name: `?InternalWriteAt@CFileByteStreamSimple@@IEAAJAEBV?$scoped_lock@U?$optional_mutex@Vrecursive_mutex@std@@@Mso@@@std@@_KPEBEKPEAKPEAUIMetroProgress@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, struct IMetroProgress *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800ffdb0`
- `0x1800fffb8`

## callees

- `0x1800ff354`
- `0x1800ff730`
- `0x1800fffb8`
- `0x180103bf4`
- `0x18010546c`
- `0x180105534`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ff899`
- `KERNEL32!GetLastError` at `0x1800ff8be`
- `KERNEL32!GetLastError` at `0x1800ff899`
- `KERNEL32!GetLastError` at `0x1800ff8be`
- `KERNEL32!WriteFile` at `0x1800ff889`
- `KERNEL32!WriteFile` at `0x1800ff889`

## pseudocode

```c
__int64 __fastcall CFileByteStreamSimple::InternalWriteAt(
        _QWORD *a1,
        __int64 a2,
        char *a3,
        char *a4,
        unsigned int a5,
        _DWORD *a6,
        struct IMetroProgress *a7)
{
  unsigned __int64 Size; // rsi
  __int64 result; // rax
  unsigned int v12; // r15d
  DWORD v13; // r12d
  __int64 v14; // rax
  signed int v15; // ebx
  bool v16; // r13
  BOOL OverlappedResult; // eax
  unsigned int *v18; // r9
  signed int LastError; // eax
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  char *v22; // rax
  __int64 v23; // rcx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-61h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-59h]
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-51h] BYREF
  void **v27; // [rsp+60h] [rbp-31h] BYREF
  __int64 v28; // [rsp+68h] [rbp-29h]
  _DWORD *v29; // [rsp+88h] [rbp-9h]
  __int64 v30; // [rsp+90h] [rbp-1h]
  int v31; // [rsp+98h] [rbp+7h]

  NumberOfBytesWritten = 0;
  Size = CFileByteStreamSimple::InternalGetSize(a1);
  if ( *((_BYTE *)a1 + 160) )
  {
    if ( a1[21] < (unsigned __int64)a3 )
    {
      result = CFileByteStreamSimple::WriteZerosToGap(a1, a2, a3, a7);
      if ( (int)result < 0 )
      {
        _mm_lfence();
        return result;
      }
    }
  }
  CProgressHelper::CProgressHelper((CProgressHelper *)&v27, a7);
  v27 = &CProgressCalc::`vftable';
  v12 = a5;
  v13 = a5;
  if ( a5 >= 0x10000 )
    v13 = 0x10000;
  v29 = a6;
  v31 = 0;
  v14 = a5;
  if ( !a5 )
    v14 = 1;
  v30 = v14;
  v25 = (unsigned __int64)&a3[a5];
  if ( v25 > Size + 0x10000 )
  {
    v15 = CProgressHelper::HrContinue((CProgressHelper *)&v27);
    if ( v15 >= 0 )
    {
      _mm_lfence();
      v16 = (*(int (__fastcall **)(_QWORD *, unsigned __int64, struct IMetroProgress *))(*a1 + 48LL))(a1, v25, a7) >= 0;
      goto LABEL_13;
    }
    goto LABEL_34;
  }
  v16 = 0;
LABEL_13:
  while ( 1 )
  {
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.Pointer = a3;
    Overlapped.hEvent = 0;
    v15 = CProgressHelper::HrContinue((CProgressHelper *)&v27);
    if ( v15 < 0 )
      break;
    OverlappedResult = WriteFile((HANDLE)a1[5], a4, v13, &NumberOfBytesWritten, &Overlapped);
    if ( !*((_DWORD *)a1 + 13) )
      goto LABEL_18;
    if ( OverlappedResult )
      goto LABEL_22;
    if ( GetLastError() == 997 )
    {
      OverlappedResult = Mso::StreamPlatform::Details::TryGetOverlappedResult(
                           (Mso::StreamPlatform::Details *)a1[5],
                           &Overlapped,
                           (struct _OVERLAPPED *)&NumberOfBytesWritten,
                           v18);
LABEL_18:
      if ( OverlappedResult )
        goto LABEL_22;
    }
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( v15 )
      break;
LABEL_22:
    v20 = NumberOfBytesWritten;
    v12 -= NumberOfBytesWritten;
    *a6 += NumberOfBytesWritten;
    a4 += v20;
    a3 += v20;
    v21 = (unsigned __int64)a3;
    if ( Size > (unsigned __int64)a3 )
      v21 = Size;
    Size = v21;
    v22 = (char *)a1[21];
    if ( v22 <= a3 )
      v22 = a3;
    a1[21] = v22;
    if ( v13 != (_DWORD)v20 )
    {
      v15 = -2147467259;
      break;
    }
    v15 = 0;
    if ( !v12 )
      goto LABEL_34;
    v13 = 0x10000;
    if ( v12 < 0x10000 )
      v13 = v12;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(_QWORD *, unsigned __int64, _QWORD))(*a1 + 48LL))(a1, Size, 0);
    goto LABEL_35;
  }
LABEL_34:
  a1[19] = Size;
LABEL_35:
  v27 = &CProgressHelper::`vftable';
  v23 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800ff730  mov     [rsp-8+arg_8], rbx
0x1800ff735  mov     [rsp-8+lpBuffer], r9
0x1800ff73a  push    rbp
0x1800ff73b  push    rsi
0x1800ff73c  push    rdi
0x1800ff73d  push    r12
0x1800ff73f  push    r13
0x1800ff741  push    r14
0x1800ff743  push    r15
0x1800ff745  lea     rbp, [rsp-0Fh]
0x1800ff74a  sub     rsp, 0A0h
0x1800ff751  mov     r14, r8
0x1800ff754  mov     rbx, rdx
0x1800ff757  mov     rdi, rcx
0x1800ff75a  xor     r15d, r15d
0x1800ff75d  mov     [rbp+3Fh+NumberOfBytesWritten], r15d
0x1800ff761  call    ?InternalGetSize@CFileByteStreamSimple@@IEBA_KAEBV?$scoped_lock@U?$optional_mutex@Vrecursive_mutex@std@@@Mso@@@std@@@Z; CFileByteStreamSimple::InternalGetSize(std::scoped_lock<Mso::optional_mutex<std::recursive_mutex>> const &)
0x1800ff766  mov     rsi, rax
0x1800ff769  mov     [rbp+3Fh+arg_0], r15b
0x1800ff76d  mov     r13, [rbp+3Fh+arg_30]
0x1800ff771  cmp     [rdi+0A0h], r15b
0x1800ff778  jz      short loc_1800FF7A0
0x1800ff77a  cmp     [rdi+0A8h], r14
0x1800ff781  jnb     short loc_1800FF7A0
0x1800ff783  mov     r9, r13
0x1800ff786  mov     r8, r14
0x1800ff789  mov     rdx, rbx
0x1800ff78c  mov     rcx, rdi
0x1800ff78f  call    ?WriteZerosToGap@CFileByteStreamSimple@@IEAAJAEBV?$scoped_lock@U?$optional_mutex@Vrecursive_mutex@std@@@Mso@@@std@@_KPEAUIMetroProgress@@@Z; CFileByteStreamSimple::WriteZerosToGap(std::scoped_lock<Mso::optional_mutex<std::recursive_mutex>> const &,unsigned __int64,IMetroProgress *)
0x1800ff794  test    eax, eax
0x1800ff796  jns     short loc_1800FF7A0
0x1800ff798  lfence
0x1800ff79b  jmp     loc_1800FF980
0x1800ff7a0  mov     rdx, r13; struct IMetroProgress *
0x1800ff7a3  lea     rcx, [rbp+3Fh+var_70]; this
0x1800ff7a7  call    ??0CProgressHelper@@QEAA@PEAUIMetroProgress@@@Z; CProgressHelper::CProgressHelper(IMetroProgress *)
0x1800ff7ac  lea     rax, ??_7CProgressCalc@@6B@; const CProgressCalc::`vftable'
0x1800ff7b3  mov     [rbp+3Fh+var_70], rax
0x1800ff7b7  mov     r15d, [rbp+3Fh+arg_20]
0x1800ff7bb  mov     r12d, r15d
0x1800ff7be  mov     eax, 10000h
0x1800ff7c3  cmp     r15d, eax
0x1800ff7c6  cmovnb  r12d, eax
0x1800ff7ca  mov     rax, [rbp+3Fh+arg_28]
0x1800ff7ce  mov     [rbp+3Fh+var_48], rax
0x1800ff7d2  mov     [rbp+3Fh+var_38], 0
0x1800ff7d9  mov     eax, r15d
0x1800ff7dc  mov     edx, 1
0x1800ff7e1  test    r15d, r15d
0x1800ff7e4  cmovz   eax, edx
0x1800ff7e7  mov     [rbp+3Fh+var_40], rax
0x1800ff7eb  lea     rcx, [r14+r15]
0x1800ff7ef  mov     [rbp+3Fh+var_98], rcx
0x1800ff7f3  lea     rax, [rsi+10000h]
0x1800ff7fa  cmp     rcx, rax
0x1800ff7fd  jbe     short loc_1800FF834
0x1800ff7ff  lea     rcx, [rbp+3Fh+var_70]; this
0x1800ff803  call    ?HrContinue@CProgressHelper@@QEAAJXZ; CProgressHelper::HrContinue(void)
0x1800ff808  mov     ebx, eax
0x1800ff80a  test    eax, eax
0x1800ff80c  js      loc_1800FF94E
0x1800ff812  lfence
0x1800ff815  mov     rax, [rdi]
0x1800ff818  mov     r8, r13
0x1800ff81b  mov     rdx, [rbp+3Fh+var_98]
0x1800ff81f  mov     rcx, rdi
0x1800ff822  mov     rax, [rax+30h]
0x1800ff826  call    cs:__guard_dispatch_icall_fptr
0x1800ff82c  test    eax, eax
0x1800ff82e  setns   r13b
0x1800ff832  jmp     short loc_1800FF838
0x1800ff834  mov     r13b, [rbp+3Fh+arg_0]
0x1800ff838  mov     [rbp+3Fh+Overlapped.Internal], 0
0x1800ff840  mov     [rbp+3Fh+Overlapped.InternalHigh], 0
0x1800ff848  mov     dword ptr [rbp+3Fh+Overlapped.10h], r14d
0x1800ff84c  mov     rax, r14
0x1800ff84f  shr     rax, 20h
0x1800ff853  mov     dword ptr [rbp+3Fh+Overlapped.10h+4], eax
0x1800ff856  mov     [rbp+3Fh+Overlapped.hEvent], 0
0x1800ff85e  lea     rcx, [rbp+3Fh+var_70]; this
0x1800ff862  call    ?HrContinue@CProgressHelper@@QEAAJXZ; CProgressHelper::HrContinue(void)
0x1800ff867  mov     ebx, eax
0x1800ff869  test    eax, eax
0x1800ff86b  js      loc_1800FF931
0x1800ff871  lea     rax, [rbp+3Fh+Overlapped]
0x1800ff875  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x1800ff87a  lea     r9, [rbp+3Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800ff87e  mov     r8d, r12d; nNumberOfBytesToWrite
0x1800ff881  mov     rdx, [rbp+3Fh+lpBuffer]; lpBuffer
0x1800ff885  mov     rcx, [rdi+28h]; hFile
0x1800ff889  call    cs:__imp_WriteFile
0x1800ff88f  cmp     dword ptr [rdi+34h], 0
0x1800ff893  jz      short loc_1800FF8BA
0x1800ff895  test    eax, eax
0x1800ff897  jnz     short loc_1800FF8D7
0x1800ff899  call    cs:__imp_GetLastError
0x1800ff89f  cmp     eax, 3E5h
0x1800ff8a4  jnz     short loc_1800FF8BE
0x1800ff8a6  lea     r8, [rbp+3Fh+NumberOfBytesWritten]; struct _OVERLAPPED *
0x1800ff8aa  lea     rdx, [rbp+3Fh+Overlapped]; void *
0x1800ff8ae  mov     rcx, [rdi+28h]; this
0x1800ff8b2  call    ?TryGetOverlappedResult@Details@StreamPlatform@Mso@@YA_NPEAXAEAU_OVERLAPPED@@AEAK@Z; Mso::StreamPlatform::Details::TryGetOverlappedResult(void *,_OVERLAPPED &,ulong &)
0x1800ff8b7  movzx   eax, al
0x1800ff8ba  test    eax, eax
0x1800ff8bc  jnz     short loc_1800FF8D7
0x1800ff8be  call    cs:__imp_GetLastError
0x1800ff8c4  mov     ebx, eax
0x1800ff8c6  test    eax, eax
0x1800ff8c8  jle     short loc_1800FF8D3
0x1800ff8ca  movzx   ebx, ax
0x1800ff8cd  or      ebx, 80070000h
0x1800ff8d3  test    ebx, ebx
0x1800ff8d5  jnz     short loc_1800FF931
0x1800ff8d7  mov     ecx, [rbp+3Fh+NumberOfBytesWritten]
0x1800ff8da  sub     r15d, ecx
0x1800ff8dd  mov     rax, [rbp+3Fh+arg_28]
0x1800ff8e1  add     [rax], ecx
0x1800ff8e3  add     [rbp+3Fh+lpBuffer], rcx
0x1800ff8e7  add     r14, rcx
0x1800ff8ea  mov     rax, r14
0x1800ff8ed  cmp     rsi, r14
0x1800ff8f0  cmova   rax, rsi
0x1800ff8f4  mov     rsi, rax
0x1800ff8f7  mov     rax, [rdi+0A8h]
0x1800ff8fe  cmp     rax, r14
0x1800ff901  cmovbe  rax, r14
0x1800ff905  mov     [rdi+0A8h], rax
0x1800ff90c  cmp     r12d, ecx
0x1800ff90f  jnz     short loc_1800FF92C
0x1800ff911  xor     ebx, ebx
0x1800ff913  test    r15d, r15d
0x1800ff916  jz      short loc_1800FF94E
0x1800ff918  mov     eax, 10000h
0x1800ff91d  mov     r12d, eax
0x1800ff920  cmp     r15d, eax
0x1800ff923  cmovb   r12d, r15d
0x1800ff927  jmp     loc_1800FF838
0x1800ff92c  mov     ebx, 80004005h
0x1800ff931  test    r13b, r13b
0x1800ff934  jz      short loc_1800FF94E
0x1800ff936  mov     rax, [rdi]
0x1800ff939  xor     r8d, r8d
0x1800ff93c  mov     rdx, rsi
0x1800ff93f  mov     rcx, rdi
0x1800ff942  mov     rax, [rax+30h]
0x1800ff946  call    cs:__guard_dispatch_icall_fptr
0x1800ff94c  jmp     short loc_1800FF955
0x1800ff94e  mov     [rdi+98h], rsi
0x1800ff955  lea     rax, ??_7CProgressHelper@@6B@; const CProgressHelper::`vftable'
0x1800ff95c  mov     [rbp+3Fh+var_70], rax
0x1800ff960  mov     rcx, [rbp+3Fh+var_68]
0x1800ff964  test    rcx, rcx
0x1800ff967  jz      short loc_1800FF97E
0x1800ff969  mov     [rbp+3Fh+var_68], 0
0x1800ff971  mov     rax, [rcx]
0x1800ff974  mov     rax, [rax+10h]
0x1800ff978  call    cs:__guard_dispatch_icall_fptr
0x1800ff97e  mov     eax, ebx
0x1800ff980  mov     rbx, [rsp+0D0h+arg_8]
0x1800ff988  add     rsp, 0A0h
0x1800ff98f  pop     r15
0x1800ff991  pop     r14
0x1800ff993  pop     r13
0x1800ff995  pop     r12
0x1800ff997  pop     rdi
0x1800ff998  pop     rsi
0x1800ff999  pop     rbp
0x1800ff99a  retn
```
