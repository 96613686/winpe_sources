# SSI_REQUEST::Initialize(void)

- ea: `0x180003530`
- end: `0x18000366f`
- name: `?Initialize@SSI_REQUEST@@AEAAJXZ`
- size: `319`
- prototype: `int __fastcall(SSI_REQUEST *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000231c`

## callees

- `0x180003530`
- `0x180003c24`
- `0x180006010`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800035fe`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800035fe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000356a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800035cd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000356a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800035cd`

## pseudocode

```c
int __fastcall SSI_REQUEST::Initialize(SSI_REQUEST *this)
{
  __int64 v2; // rcx
  const unsigned __int16 *v3; // rax
  int result; // eax
  _QWORD *v5; // rdi
  __int64 v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rsi
  struct SSI_INCLUDE_FILE *v9; // rax
  struct SSI_INCLUDE_FILE **v10; // rcx
  __int64 v11; // rdx
  struct SSI_INCLUDE_FILE *v12; // [rsp+70h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 1);
  v12 = 0;
  v3 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 176LL))(v2, 0);
  result = STRU::Copy((SSI_REQUEST *)((char *)this + 336), v3);
  if ( result < 0 )
    return result;
  v5 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 184LL))(*((_QWORD *)this + 1), 0);
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)v5 + v6) );
  v7 = 2 * v6;
  v8 = 2;
  if ( v7 < 0x10 )
  {
    if ( v7 < 8 )
    {
LABEL_11:
      v8 = 0;
      goto LABEL_12;
    }
  }
  else if ( *v5 == qword_18000A220 && v5[1] == qword_18000A228 )
  {
    result = STRU::Copy((SSI_REQUEST *)((char *)this + 16), L"\\\\");
    if ( result < 0 )
      return result;
    goto LABEL_12;
  }
  v8 = 1;
  if ( *v5 != qword_18000A210 )
    goto LABEL_11;
LABEL_12:
  result = STRU::Append((SSI_REQUEST *)((char *)this + 16), (const unsigned __int16 *)&v5[v8]);
  if ( result >= 0 )
  {
    result = SSI_INCLUDE_FILE::CreateInstance(
               (SSI_REQUEST *)((char *)this + 16),
               (SSI_REQUEST *)((char *)this + 336),
               this,
               0,
               &v12);
    if ( result >= 0 )
    {
      v9 = v12;
      v10 = (struct SSI_INCLUDE_FILE **)((char *)this + 1104);
      *((_QWORD *)this + 99) = v12;
      v11 = *((_QWORD *)this + 138);
      if ( *(SSI_REQUEST **)(v11 + 8) != (SSI_REQUEST *)((char *)this + 1104) )
        __fastfail(3u);
      *(_QWORD *)v9 = v11;
      *((_QWORD *)v9 + 1) = v10;
      *(_QWORD *)(v11 + 8) = v9;
      *v10 = v9;
      result = 0;
      *((_QWORD *)this + 135) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003530  push    rbx
0x180003532  push    rbp
0x180003533  push    rsi
0x180003534  push    rdi
0x180003535  push    r14
0x180003537  push    r15
0x180003539  sub     rsp, 38h
0x18000353d  mov     rbx, rcx
0x180003540  xor     r15d, r15d
0x180003543  mov     rcx, [rcx+8]
0x180003547  xor     edx, edx
0x180003549  mov     [rsp+68h+arg_0], r15
0x18000354e  lea     r14, [rbx+150h]
0x180003555  mov     rax, [rcx]
0x180003558  mov     rax, [rax+0B0h]
0x18000355f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003564  mov     rdx, rax
0x180003567  mov     rcx, r14
0x18000356a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003570  test    eax, eax
0x180003572  js      loc_180003662
0x180003578  mov     rcx, [rbx+8]
0x18000357c  xor     edx, edx
0x18000357e  mov     rax, [rcx]
0x180003581  mov     rax, [rax+0B8h]
0x180003588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000358d  mov     rdi, rax
0x180003590  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003594  inc     rax
0x180003597  cmp     [rdi+rax*2], r15w
0x18000359c  jnz     short loc_180003594
0x18000359e  add     eax, eax
0x1800035a0  mov     esi, 10h
0x1800035a5  cmp     eax, esi
0x1800035a7  jb      short loc_1800035DD
0x1800035a9  mov     rax, [rdi]
0x1800035ac  cmp     rax, cs:qword_18000A220
0x1800035b3  jnz     short loc_1800035E2
0x1800035b5  mov     rax, [rdi+8]
0x1800035b9  cmp     rax, cs:qword_18000A228
0x1800035c0  jnz     short loc_1800035E2
0x1800035c2  lea     rcx, [rbx+10h]
0x1800035c6  lea     rdx, asc_180007E28; "\\\\"
0x1800035cd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800035d3  test    eax, eax
0x1800035d5  js      loc_180003662
0x1800035db  jmp     short loc_1800035F6
0x1800035dd  cmp     eax, 8
0x1800035e0  jb      short loc_1800035F3
0x1800035e2  mov     rax, [rdi]
0x1800035e5  mov     esi, 8
0x1800035ea  cmp     rax, cs:qword_18000A210
0x1800035f1  jz      short loc_1800035F6
0x1800035f3  mov     rsi, r15
0x1800035f6  lea     rdx, [rsi+rdi]
0x1800035fa  lea     rcx, [rbx+10h]
0x1800035fe  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003604  test    eax, eax
0x180003606  js      short loc_180003662
0x180003608  lea     rax, [rsp+68h+arg_0]
0x18000360d  xor     r9d, r9d; struct SSI_INCLUDE_FILE *
0x180003610  mov     r8, rbx; struct SSI_REQUEST *
0x180003613  mov     [rsp+68h+var_48], rax; struct SSI_INCLUDE_FILE **
0x180003618  mov     rdx, r14; struct STRU *
0x18000361b  lea     rcx, [rbx+10h]; struct STRU *
0x18000361f  call    ?CreateInstance@SSI_INCLUDE_FILE@@SAJAEAVSTRU@@0PEAVSSI_REQUEST@@PEAV1@PEAPEAV1@@Z; SSI_INCLUDE_FILE::CreateInstance(STRU &,STRU &,SSI_REQUEST *,SSI_INCLUDE_FILE *,SSI_INCLUDE_FILE * *)
0x180003624  test    eax, eax
0x180003626  js      short loc_180003662
0x180003628  mov     rax, [rsp+68h+arg_0]
0x18000362d  lea     rcx, [rbx+450h]
0x180003634  mov     [rbx+318h], rax
0x18000363b  mov     rdx, [rcx]
0x18000363e  cmp     [rdx+8], rcx
0x180003642  jz      short loc_18000364B
0x180003644  mov     ecx, 3
0x180003649  int     29h; Win8: RtlFailFast(ecx)
0x18000364b  mov     [rax], rdx
0x18000364e  mov     [rax+8], rcx
0x180003652  mov     [rdx+8], rax
0x180003656  mov     [rcx], rax
0x180003659  xor     eax, eax
0x18000365b  mov     [rbx+438h], r15
0x180003662  add     rsp, 38h
0x180003666  pop     r15
0x180003668  pop     r14
0x18000366a  pop     rdi
0x18000366b  pop     rsi
0x18000366c  pop     rbp
0x18000366d  pop     rbx
0x18000366e  retn
```
