# CValueChunk::Add(wchar_t const *,ulong)

- ea: `0x180005824`
- end: `0x180005977`
- name: `?Add@CValueChunk@@QEAAXPEB_WK@Z`
- size: `339`
- prototype: `void __fastcall(CValueChunk *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005654`

## callees

- `0x180005824`
- `0x180005980`
- `0x180005a1c`
- `0x180013500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000587d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000587d`

## pseudocode

```c
void __fastcall CValueChunk::Add(CValueChunk *this, const wchar_t *a2, unsigned int a3)
{
  __int64 v4; // rbx
  __int64 v6; // rbp
  __int64 v7; // rdi
  _WORD *v8; // rax
  _WORD *v9; // rsi
  __int64 v10; // rcx
  _WORD *v11; // rcx
  int v12; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a3 == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.hxx",
      (const char *)0x80070216LL,
      v12);
  v6 = a3 + 1;
  if ( (unsigned int)v6 < a3 || (v7 = (unsigned int)v6, (unsigned __int64)(2 * v6) > 0xFFFFFFFF) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.hxx",
      (const char *)0x80070216LL,
      v12);
  v8 = CoTaskMemAlloc((unsigned int)(2 * v6));
  v9 = v8;
  if ( !v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.hxx",
      (const char *)0x8007000ELL,
      v12);
  if ( (unsigned int)v4 > 0x7FFFFFFE )
  {
    if ( (_DWORD)v4 != -1 )
      *v8 = 0;
LABEL_19:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.hxx",
      (const char *)0x80004005LL,
      v12);
  }
  v10 = v4;
  do
  {
    if ( !v10 )
      break;
    if ( !*a2 )
      break;
    *v8++ = *a2++;
    --v10;
    --v7;
  }
  while ( v7 );
  v11 = v8 - 1;
  if ( v7 )
    v11 = v8;
  *v11 = 0;
  if ( !v7 )
    goto LABEL_19;
  v9[v4] = 0;
  FixPrivateChars(v9, (unsigned int)v4);
  CVarArray<wchar_t *,5>::Grow((char *)this + 32);
  *(_QWORD *)(*((_QWORD *)this + 5) + 8LL * (unsigned int)(*((_DWORD *)this + 9))++) = v9;
}

```

## disassembly

```asm
0x180005824  push    rbx
0x180005826  push    rbp
0x180005827  push    rsi
0x180005828  push    rdi
0x180005829  push    r14
0x18000582b  push    r15
0x18000582d  sub     rsp, 28h
0x180005831  mov     r15, rcx
0x180005834  mov     ebx, r8d
0x180005837  mov     ecx, 0FFFFFFFFh
0x18000583c  mov     r14, rdx
0x18000583f  cmp     r8d, ecx
0x180005842  jz      loc_180005918
0x180005848  lea     ebp, [rbx+1]
0x18000584b  cmp     ebp, ebx
0x18000584d  jnb     short loc_18000586C
0x18000584f  mov     rcx, [rsp+58h]; this
0x180005854  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000585b  mov     r9d, 80070216h; char *
0x180005861  mov     edx, 85h; void *
0x180005866  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000586c  lea     rax, ds:0[rbp*2]
0x180005874  mov     edi, ebp
0x180005876  cmp     rax, rcx
0x180005879  ja      short loc_18000584F
0x18000587b  mov     ecx, eax; cb
0x18000587d  call    cs:__imp_CoTaskMemAlloc
0x180005883  xor     r9d, r9d
0x180005886  mov     rsi, rax
0x180005889  test    rax, rax
0x18000588c  jz      loc_180005935
0x180005892  lea     eax, [rbp-1]
0x180005895  mov     ecx, 7FFFFFFEh
0x18000589a  cmp     eax, ecx
0x18000589c  ja      loc_180005952
0x1800058a2  cmp     ebx, ecx
0x1800058a4  ja      loc_180005956
0x1800058aa  mov     rcx, rbx
0x1800058ad  mov     rax, rsi
0x1800058b0  test    rcx, rcx
0x1800058b3  jz      short loc_1800058D2
0x1800058b5  movzx   edx, word ptr [r14]
0x1800058b9  test    dx, dx
0x1800058bc  jz      short loc_1800058D2
0x1800058be  mov     [rax], dx
0x1800058c1  add     r14, 2
0x1800058c5  add     rax, 2
0x1800058c9  dec     rcx
0x1800058cc  sub     rdi, 1
0x1800058d0  jnz     short loc_1800058B0
0x1800058d2  test    rdi, rdi
0x1800058d5  lea     rcx, [rax-2]
0x1800058d9  cmovnz  rcx, rax
0x1800058dd  mov     [rcx], r9w
0x1800058e1  jz      short loc_18000595A
0x1800058e3  mov     edx, ebx
0x1800058e5  mov     [rsi+rbx*2], r9w
0x1800058ea  mov     rcx, rsi
0x1800058ed  call    FixPrivateChars
0x1800058f2  lea     rcx, [r15+20h]
0x1800058f6  call    ?Grow@?$CVarArray@PEA_W$04@@AEAAXXZ; CVarArray<wchar_t *,5>::Grow(void)
0x1800058fb  mov     ecx, [r15+24h]
0x1800058ff  mov     rax, [r15+28h]
0x180005903  mov     [rax+rcx*8], rsi
0x180005907  inc     dword ptr [r15+24h]
0x18000590b  add     rsp, 28h
0x18000590f  pop     r15
0x180005911  pop     r14
0x180005913  pop     rdi
0x180005914  pop     rsi
0x180005915  pop     rbp
0x180005916  pop     rbx
0x180005917  retn
0x180005918  mov     rcx, [rsp+58h]; this
0x18000591d  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180005924  mov     r9d, 80070216h; char *
0x18000592a  mov     edx, 7Eh ; '~'; void *
0x18000592f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005935  mov     rcx, [rsp+58h]; this
0x18000593a  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180005941  mov     r9d, 8007000Eh; char *
0x180005947  mov     edx, 89h; void *
0x18000594c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005952  test    ebp, ebp
0x180005954  jz      short loc_18000595A
0x180005956  mov     [rsi], r9w
0x18000595a  mov     rcx, [rsp+58h]; this
0x18000595f  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180005966  mov     r9d, 80004005h; char *
0x18000596c  mov     edx, 8Eh; void *
0x180005971  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
