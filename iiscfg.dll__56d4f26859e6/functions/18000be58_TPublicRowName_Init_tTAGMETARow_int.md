# TPublicRowName::Init(tTAGMETARow *,int)

- ea: `0x18000be58`
- end: `0x18000bf6e`
- name: `?Init@TPublicRowName@@QEAAJPEAUtTAGMETARow@@H@Z`
- size: `278`
- prototype: `int(TPublicRowName *__hidden this, struct tTAGMETARow *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c4d0`

## callees

- `0x180001d04`
- `0x18000be58`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000bf3c`
- `msvcrt!wcscpy_s` at `0x18000bf3c`
- `ole32!CoTaskMemAlloc` at `0x18000bea0`
- `ole32!CoTaskMemAlloc` at `0x18000bea0`
- `ole32!CoTaskMemRealloc` at `0x18000bf24`
- `ole32!CoTaskMemRealloc` at `0x18000bf24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TPublicRowName::Init(TPublicRowName *this, struct tTAGMETARow *a2, unsigned int a3)
{
  TPublicRowName *v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rax
  bool v8; // cf
  SIZE_T v9; // rax
  _QWORD *v10; // rax
  unsigned int i; // ebp
  const wchar_t *v12; // r14
  __int64 v13; // rax
  rsize_t v14; // r15
  wchar_t *v15; // rax

  *((_DWORD *)this + 10) = a3;
  if ( a3 > 3 )
  {
    v6 = a3;
    v7 = 8LL * a3;
    if ( !is_mul_ok(a3, 8u) )
      v7 = -1;
    v8 = __CFADD__(v7, 8);
    v9 = v7 + 8;
    if ( v8 )
      v9 = -1;
    v10 = CoTaskMemAlloc(v9);
    if ( v10 )
    {
      *v10 = v6;
      v5 = (TPublicRowName *)(v10 + 1);
      `eh vector constructor iterator'(
        v10 + 1,
        8u,
        (unsigned int)v6,
        (void (*)(void *))ATL::CComBSTR::CComBSTR,
        (void (*)(void *))wstring::~wstring);
    }
    else
    {
      v5 = 0;
    }
    *((_QWORD *)this + 3) = v5;
    if ( !v5 )
      return 2147942414LL;
  }
  else
  {
    v5 = this;
  }
  *((_QWORD *)this + 4) = v5;
  for ( i = 0; i < *((_DWORD *)this + 10); ++i )
  {
    v12 = (const wchar_t *)*((_QWORD *)a2 + 6 * i + 3);
    if ( v12 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v14 = v13 + 1;
      v15 = (wchar_t *)CoTaskMemRealloc(*((LPVOID *)v5 + i), 2 * (v13 + 1));
      *((_QWORD *)v5 + i) = v15;
      if ( v15 )
        wcscpy_s(v15, v14, v12);
    }
    v5 = (TPublicRowName *)*((_QWORD *)this + 4);
    if ( !*((_QWORD *)v5 + i) )
      return 2147942414LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18000be58  push    rbx
0x18000be5a  push    rbp
0x18000be5b  push    rsi
0x18000be5c  push    rdi
0x18000be5d  push    r12
0x18000be5f  push    r13
0x18000be61  push    r14
0x18000be63  push    r15
0x18000be65  sub     rsp, 38h
0x18000be69  mov     r12, rdx
0x18000be6c  mov     rdi, rcx
0x18000be6f  mov     [rcx+28h], r8d
0x18000be73  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000be77  xor     r13d, r13d
0x18000be7a  cmp     r8d, 3
0x18000be7e  ja      short loc_18000BE85
0x18000be80  mov     rbx, rdi
0x18000be83  jmp     short loc_18000BEEC
0x18000be85  mov     esi, r8d
0x18000be88  mov     ebp, 8
0x18000be8d  mov     eax, ebp
0x18000be8f  mul     rsi
0x18000be92  cmovb   rax, rcx
0x18000be96  add     rax, rbp
0x18000be99  cmovb   rax, rcx
0x18000be9d  mov     rcx, rax; cb
0x18000bea0  call    cs:__imp_CoTaskMemAlloc
0x18000bea6  mov     [rsp+78h+arg_0], rax
0x18000beae  test    rax, rax
0x18000beb1  jz      short loc_18000BEDC
0x18000beb3  mov     [rax], rsi
0x18000beb6  lea     rbx, [rax+8]
0x18000beba  lea     rax, ??1wstring@@QEAA@XZ; wstring::~wstring(void)
0x18000bec1  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x18000bec6  lea     r9, ??0CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x18000becd  mov     r8d, esi; unsigned __int64
0x18000bed0  mov     edx, ebp; unsigned __int64
0x18000bed2  mov     rcx, rbx; void *
0x18000bed5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000beda  jmp     short loc_18000BEDF
0x18000bedc  mov     rbx, r13
0x18000bedf  mov     [rdi+18h], rbx
0x18000bee3  test    rbx, rbx
0x18000bee6  jz      short loc_18000BF58
0x18000bee8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000beec  mov     [rdi+20h], rbx
0x18000bef0  mov     ebp, r13d
0x18000bef3  cmp     ebp, [rdi+28h]
0x18000bef6  jnb     short loc_18000BF54
0x18000bef8  mov     esi, ebp
0x18000befa  lea     rax, [rsi+rsi*2]
0x18000befe  add     rax, rax
0x18000bf01  mov     r14, [r12+rax*8+18h]
0x18000bf06  test    r14, r14
0x18000bf09  jz      short loc_18000BF42
0x18000bf0b  mov     rax, rcx
0x18000bf0e  inc     rax
0x18000bf11  cmp     [r14+rax*2], r13w
0x18000bf16  jnz     short loc_18000BF0E
0x18000bf18  lea     r15, [rax+1]
0x18000bf1c  lea     rdx, [r15+r15]; cb
0x18000bf20  mov     rcx, [rbx+rsi*8]; pv
0x18000bf24  call    cs:__imp_CoTaskMemRealloc
0x18000bf2a  mov     [rbx+rsi*8], rax
0x18000bf2e  test    rax, rax
0x18000bf31  jz      short loc_18000BF42
0x18000bf33  mov     r8, r14; Source
0x18000bf36  mov     rdx, r15; SizeInWords
0x18000bf39  mov     rcx, rax; Destination
0x18000bf3c  call    cs:__imp_wcscpy_s
0x18000bf42  mov     rbx, [rdi+20h]
0x18000bf46  cmp     [rbx+rsi*8], r13
0x18000bf4a  jz      short loc_18000BF58
0x18000bf4c  inc     ebp
0x18000bf4e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000bf52  jmp     short loc_18000BEF3
0x18000bf54  xor     eax, eax
0x18000bf56  jmp     short loc_18000BF5D
0x18000bf58  mov     eax, 8007000Eh
0x18000bf5d  add     rsp, 38h
0x18000bf61  pop     r15
0x18000bf63  pop     r14
0x18000bf65  pop     r13
0x18000bf67  pop     r12
0x18000bf69  pop     rdi
0x18000bf6a  pop     rsi
0x18000bf6b  pop     rbp
0x18000bf6c  pop     rbx
0x18000bf6d  retn
```
