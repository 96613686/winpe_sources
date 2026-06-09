# CMediaType::SetFormat(uchar *,ulong)

- ea: `0x18000f6c0`
- end: `0x18000f75d`
- name: `?SetFormat@CMediaType@@QEAAHPEAEK@Z`
- size: `157`
- prototype: `__int64 __fastcall(CMediaType *this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002f814`

## callees

- `0x18000f6c0`
- `0x180044850`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000f6dd`
- `ole32!CoTaskMemAlloc` at `0x18000f6dd`
- `ole32!CoTaskMemFree` at `0x18000f74f`
- `ole32!CoTaskMemFree` at `0x18000f74f`

## pseudocode

```c
__int64 __fastcall CMediaType::SetFormat(CMediaType *this, unsigned __int8 *a2, unsigned int a3)
{
  size_t v4; // r14
  unsigned __int8 *pbFormat; // rbx
  unsigned int cbFormat; // eax

  v4 = a3;
  if ( this->cbFormat == a3 )
    goto LABEL_14;
  pbFormat = (unsigned __int8 *)CoTaskMemAlloc(a3);
  cbFormat = this->cbFormat;
  if ( pbFormat )
  {
    if ( cbFormat )
      CoTaskMemFree(this->pbFormat);
    this->cbFormat = v4;
    this->pbFormat = pbFormat;
    goto LABEL_6;
  }
  if ( (unsigned int)v4 <= cbFormat )
  {
LABEL_14:
    if ( this->pbFormat )
    {
      pbFormat = this->pbFormat;
LABEL_6:
      memcpy_0(pbFormat, a2, v4);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f6c0  push    rbx
0x18000f6c2  push    rbp
0x18000f6c3  push    rsi
0x18000f6c4  push    rdi
0x18000f6c5  push    r14
0x18000f6c7  sub     rsp, 20h
0x18000f6cb  mov     rbp, rdx
0x18000f6ce  mov     r14d, r8d
0x18000f6d1  mov     rsi, rcx
0x18000f6d4  cmp     [rcx+48h], r8d
0x18000f6d8  jz      short loc_18000F71F
0x18000f6da  mov     ecx, r14d; cb
0x18000f6dd  call    cs:__imp_CoTaskMemAlloc
0x18000f6e4  nop     dword ptr [rax+rax+00h]
0x18000f6e9  mov     rbx, rax
0x18000f6ec  mov     eax, [rsi+48h]
0x18000f6ef  test    rbx, rbx
0x18000f6f2  jz      short loc_18000F744
0x18000f6f4  test    eax, eax
0x18000f6f6  jnz     short loc_18000F74B
0x18000f6f8  mov     [rsi+48h], r14d
0x18000f6fc  mov     [rsi+50h], rbx
0x18000f700  mov     r8, r14; Size
0x18000f703  mov     rdx, rbp; Src
0x18000f706  mov     rcx, rbx; void *
0x18000f709  call    memcpy_0
0x18000f70e  mov     eax, 1
0x18000f713  add     rsp, 20h
0x18000f717  pop     r14
0x18000f719  pop     rdi
0x18000f71a  pop     rsi
0x18000f71b  pop     rbp
0x18000f71c  pop     rbx
0x18000f71d  retn
0x18000f71f  mov     ecx, 50h ; 'P'
0x18000f724  mov     rbx, rsi
0x18000f727  mov     eax, ecx
0x18000f729  cmp     qword ptr [rcx+rsi], 0
0x18000f72e  jz      short loc_18000F736
0x18000f730  mov     rbx, [rcx+rbx]
0x18000f734  jmp     short loc_18000F700
0x18000f736  xor     eax, eax
0x18000f738  add     rsp, 20h
0x18000f73c  pop     r14
0x18000f73e  pop     rdi
0x18000f73f  pop     rsi
0x18000f740  pop     rbp
0x18000f741  pop     rbx
0x18000f742  retn
0x18000f744  cmp     r14d, eax
0x18000f747  ja      short loc_18000F736
0x18000f749  jmp     short loc_18000F71F
0x18000f74b  mov     rcx, [rsi+50h]; pv
0x18000f74f  call    cs:__imp_CoTaskMemFree
0x18000f756  nop     dword ptr [rax+rax+00h]
0x18000f75b  jmp     short loc_18000F6F8
```
