# CAMCView::Write2File(void *,ushort const *,int)

- ea: `0x140097984`
- end: `0x140097aec`
- name: `?Write2File@CAMCView@@AEAA_NPEAXPEBGH@Z`
- size: `360`
- prototype: `bool(CAMCView *__hidden this, void *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140094ec0`

## callees

- `0x14000c1d0`
- `0x140097984`
- `0x1400e9e10`
- `0x1400e9ed0`

## import_xrefs

- `MFC42u!__imp_?AfxW2AHelper@@YAPEADPEADPEBGH@Z` at `0x140097a80`
- `MFC42u!__imp_?AfxW2AHelper@@YAPEADPEADPEBGH@Z` at `0x140097a80`
- `msvcrt!_mbsnbcnt` at `0x140097a9d`
- `msvcrt!_mbsnbcnt` at `0x140097a9d`
- `msvcrt!_mbslen` at `0x140097a91`
- `msvcrt!_mbslen` at `0x140097a91`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400979ee`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140097acd`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400979ee`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140097acd`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400979f8`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400979f8`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400979b1`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x1400979b1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400979e3`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1400979e3`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400979c3`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1400979c3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140097ab8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140097ab8`

## string_xrefs

- `0x1400979b8`: `CAMCView::Write2File`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall CAMCView::Write2File(CAMCView *this, void *a2, const unsigned __int16 *a3, int a4)
{
  __int64 v7; // rax
  bool v8; // bl
  __int64 v9; // rax
  DWORD v10; // ebx
  DWORD v11; // r8d
  __int64 v12; // rax
  int v13; // r8d
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  const unsigned __int16 *v18; // rax
  size_t v19; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp+0h] BYREF
  _BYTE v22[24]; // [rsp+38h] [rbp+8h] BYREF
  _BYTE v23[24]; // [rsp+50h] [rbp+20h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v22, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v22, L"CAMCView::Write2File");
  v7 = ScCheckPointers(v23, a3, 2147942487LL);
  mmcerror::SC::operator=(v22, v7);
  mmcerror::SC::~SC((mmcerror::SC *)v23);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v22) )
  {
    NumberOfBytesWritten = 0;
    if ( a4 )
    {
      if ( a3 )
      {
        v9 = -1;
        do
          ++v9;
        while ( a3[v9] );
        v10 = 2 * v9;
        v11 = 2 * v9;
        goto LABEL_15;
      }
    }
    else if ( a3 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = 2 * v12 + 2;
      v14 = v13 + 15LL;
      if ( v14 <= v13 )
        v14 = 0xFFFFFFFFFFFFFF0LL;
      v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
      v16 = alloca(v15);
      v17 = alloca(v15);
      v18 = (const unsigned __int16 *)AfxW2AHelper((char *)&NumberOfBytesWritten, a3, v13);
      a3 = v18;
      if ( v18 )
      {
        v19 = _mbslen((const unsigned __int8 *)v18);
        v10 = _mbsnbcnt((const unsigned __int8 *)a3, v19);
        v11 = v10;
LABEL_15:
        WriteFile(a2, a3, v11, &NumberOfBytesWritten, 0);
LABEL_17:
        v8 = NumberOfBytesWritten == v10;
        goto LABEL_18;
      }
    }
    v10 = 0;
    goto LABEL_17;
  }
  v8 = 0;
LABEL_18:
  mmcerror::SC::~SC((mmcerror::SC *)v22);
  return v8;
}

```

## disassembly

```asm
0x140097984  push    rbp
0x140097986  push    rbx
0x140097987  push    rsi
0x140097988  push    rdi
0x140097989  push    r14
0x14009798b  sub     rsp, 70h
0x14009798f  lea     rbp, [rsp+30h]
0x140097994  mov     rax, cs:__security_cookie
0x14009799b  xor     rax, rbp
0x14009799e  mov     [rbp+60h+var_28], rax
0x1400979a2  mov     ebx, r9d
0x1400979a5  mov     rdi, r8
0x1400979a8  mov     rsi, rdx
0x1400979ab  xor     edx, edx
0x1400979ad  lea     rcx, [rbp+60h+var_58]
0x1400979b1  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x1400979b7  nop
0x1400979b8  lea     rdx, aCamcviewWrite2; "CAMCView::Write2File"
0x1400979bf  lea     rcx, [rbp+60h+var_58]
0x1400979c3  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x1400979c9  mov     r8d, 80070057h
0x1400979cf  mov     rdx, rdi
0x1400979d2  lea     rcx, [rbp+60h+var_40]
0x1400979d6  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x1400979db  nop
0x1400979dc  mov     rdx, rax
0x1400979df  lea     rcx, [rbp+60h+var_58]
0x1400979e3  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400979e9  nop
0x1400979ea  lea     rcx, [rbp+60h+var_40]
0x1400979ee  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400979f4  lea     rcx, [rbp+60h+var_58]
0x1400979f8  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400979fe  xor     r14d, r14d
0x140097a01  test    al, al
0x140097a03  jz      short loc_140097A0D
0x140097a05  mov     bl, r14b
0x140097a08  jmp     loc_140097AC9
0x140097a0d  mov     [rbp+60h+NumberOfBytesWritten], r14d
0x140097a11  test    ebx, ebx
0x140097a13  jz      short loc_140097A34
0x140097a15  test    rdi, rdi
0x140097a18  jz      loc_140097AC0
0x140097a1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140097a22  inc     rax
0x140097a25  cmp     [rdi+rax*2], r14w
0x140097a2a  jnz     short loc_140097A22
0x140097a2c  lea     ebx, [rax+rax]
0x140097a2f  mov     r8d, ebx
0x140097a32  jmp     short loc_140097AA9
0x140097a34  test    rdi, rdi
0x140097a37  jz      loc_140097AC0
0x140097a3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140097a41  inc     rax
0x140097a44  cmp     [rdi+rax*2], r14w
0x140097a49  jnz     short loc_140097A41
0x140097a4b  lea     r8d, ds:2[rax*2]
0x140097a53  movsxd  rax, r8d
0x140097a56  lea     rcx, [rax+0Fh]
0x140097a5a  cmp     rcx, rax
0x140097a5d  ja      short loc_140097A69
0x140097a5f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140097a69  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140097a6d  mov     rax, rcx
0x140097a70  call    _alloca_probe
0x140097a75  sub     rsp, rcx
0x140097a78  lea     rcx, [rsp+90h+NumberOfBytesWritten]
0x140097a7d  mov     rdx, rdi
0x140097a80  call    cs:__imp_?AfxW2AHelper@@YAPEADPEADPEBGH@Z; AfxW2AHelper(char *,ushort const *,int)
0x140097a86  mov     rdi, rax
0x140097a89  test    rax, rax
0x140097a8c  jz      short loc_140097AC0
0x140097a8e  mov     rcx, rax; String
0x140097a91  call    cs:__imp__mbslen
0x140097a97  mov     rdx, rax; MaxCount
0x140097a9a  mov     rcx, rdi; String
0x140097a9d  call    cs:__imp__mbsnbcnt
0x140097aa3  mov     rbx, rax
0x140097aa6  mov     r8d, eax; nNumberOfBytesToWrite
0x140097aa9  mov     [rsp+90h+lpOverlapped], r14; lpOverlapped
0x140097aae  lea     r9, [rbp+60h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140097ab2  mov     rdx, rdi; lpBuffer
0x140097ab5  mov     rcx, rsi; hFile
0x140097ab8  call    cs:__imp_WriteFile
0x140097abe  jmp     short loc_140097AC3
0x140097ac0  mov     ebx, r14d
0x140097ac3  cmp     [rbp+60h+NumberOfBytesWritten], ebx
0x140097ac6  setz    bl
0x140097ac9  lea     rcx, [rbp+60h+var_58]
0x140097acd  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140097ad3  mov     al, bl
0x140097ad5  mov     rcx, [rbp+60h+var_28]
0x140097ad9  xor     rcx, rbp; StackCookie
0x140097adc  call    __security_check_cookie
0x140097ae1  lea     rsp, [rbp+40h]
0x140097ae5  pop     r14
0x140097ae7  pop     rdi
0x140097ae8  pop     rsi
0x140097ae9  pop     rbx
0x140097aea  pop     rbp
0x140097aeb  retn
```
