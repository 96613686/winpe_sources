# CEmfPlusEnumState::ExcludeClipRect(void)

- ea: `0x180119664`
- end: `0x180119782`
- name: `?ExcludeClipRect@CEmfPlusEnumState@@QEAAXXZ`
- size: `286`
- prototype: `void __fastcall(CEmfPlusEnumState *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005df70`

## callees

- `0x18005512c`
- `0x1800e9380`
- `0x180119664`
- `0x1801740cc`
- `0x180175010`

## import_xrefs

- `GDI32!CombineRgn` at `0x18011974e`
- `GDI32!CombineRgn` at `0x18011974e`
- `GDI32!DeleteObject` at `0x18011975d`
- `GDI32!DeleteObject` at `0x18011975d`
- `GDI32!CreateRectRgn` at `0x1801196ed`
- `GDI32!CreateRectRgn` at `0x180119727`
- `GDI32!CreateRectRgn` at `0x1801196ed`
- `GDI32!CreateRectRgn` at `0x180119727`

## pseudocode

```c
void __fastcall CEmfPlusEnumState::ExcludeClipRect(HRGN *this)
{
  const struct tagENHMETARECORD *PartialRecord; // rax
  __int64 *v3; // rcx
  __int64 v4; // rdx
  const struct tagENHMETARECORD *v5; // rdi
  size_t v6; // r8
  __m128i v7; // xmm0
  __int64 v8; // rcx
  unsigned __int64 v9; // xmm0_8
  HRGN RectRgn; // rax
  HRGN v11; // rdi
  __int128 v12; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+30h] [rbp-18h]

  PartialRecord = EmfEnumState::GetPartialRecord((EmfEnumState *)this);
  v4 = *v3;
  v5 = PartialRecord;
  v13 = 0;
  v12 = 0;
  v6 = (*(unsigned int (__fastcall **)(__int64 *))(v4 + 48))(v3);
  if ( v6 < 0x18 )
  {
    memcpy_0(&v12, v5, v6);
    v5 = (const struct tagENHMETARECORD *)&v12;
  }
  v7 = *(__m128i *)v5->dParm;
  v8 = *(_QWORD *)v5->dParm;
  if ( this[536] )
  {
    RectRgn = CreateRectRgn(
                v8,
                _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)v5->dParm, 4)),
                _mm_srli_si128(*(__m128i *)v5->dParm, 8).m128i_i32[0],
                _mm_cvtsi128_si32(_mm_srli_si128(v7, 12)));
    v11 = RectRgn;
    if ( RectRgn )
    {
      CombineRgn(this[536], this[536], RectRgn, 2);
      DeleteObject(v11);
    }
  }
  else
  {
    v9 = _mm_srli_si128(v7, 8).m128i_u64[0];
    this[536] = CreateRectRgn(v8, SHIDWORD(v8), v9, SHIDWORD(v9));
  }
}

```

## disassembly

```asm
0x180119664  mov     [rsp+arg_8], rbx
0x180119669  push    rdi
0x18011966a  sub     rsp, 40h
0x18011966e  mov     rax, cs:__security_cookie
0x180119675  xor     rax, rsp
0x180119678  mov     [rsp+48h+var_10], rax
0x18011967d  mov     rbx, rcx
0x180119680  call    ?GetPartialRecord@EmfEnumState@@QEAAPEBUtagENHMETARECORD@@XZ; EmfEnumState::GetPartialRecord(void)
0x180119685  mov     rdx, [rcx]
0x180119688  mov     rdi, rax
0x18011968b  xor     eax, eax
0x18011968d  xorps   xmm0, xmm0
0x180119690  mov     [rsp+48h+var_18], rax
0x180119695  movups  [rsp+48h+var_28], xmm0
0x18011969a  mov     rax, [rdx+30h]
0x18011969e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801196a3  mov     r8d, eax; Size
0x1801196a6  cmp     r8, 18h
0x1801196aa  jnb     short loc_1801196BE
0x1801196ac  mov     rdx, rdi; Src
0x1801196af  lea     rcx, [rsp+48h+var_28]; void *
0x1801196b4  call    memcpy_0
0x1801196b9  lea     rdi, [rsp+48h+var_28]
0x1801196be  cmp     qword ptr [rbx+10C0h], 0
0x1801196c6  movups  xmm2, xmmword ptr [rdi+8]
0x1801196ca  movdqa  xmm0, xmm2
0x1801196ce  movq    rcx, xmm2; x1
0x1801196d3  jnz     short loc_180119702
0x1801196d5  psrldq  xmm0, 8
0x1801196da  mov     rdx, rcx
0x1801196dd  movq    r8, xmm0; x2
0x1801196e2  shr     rdx, 20h; y1
0x1801196e6  mov     r9, r8
0x1801196e9  shr     r9, 20h; y2
0x1801196ed  call    cs:__imp_CreateRectRgn
0x1801196f4  nop     dword ptr [rax+rax+00h]
0x1801196f9  mov     [rbx+10C0h], rax
0x180119700  jmp     short loc_180119769
0x180119702  psrldq  xmm0, 0Ch
0x180119707  movdqa  xmm1, xmm2
0x18011970b  movd    r9d, xmm0; y2
0x180119710  movdqa  xmm0, xmm2
0x180119714  psrldq  xmm0, 4
0x180119719  psrldq  xmm1, 8
0x18011971e  movd    edx, xmm0; y1
0x180119722  movq    r8, xmm1; x2
0x180119727  call    cs:__imp_CreateRectRgn
0x18011972e  nop     dword ptr [rax+rax+00h]
0x180119733  mov     rdi, rax
0x180119736  test    rax, rax
0x180119739  jz      short loc_180119769
0x18011973b  mov     rcx, [rbx+10C0h]; hrgnDst
0x180119742  mov     r9d, 2; iMode
0x180119748  mov     rdx, rcx; hrgnSrc1
0x18011974b  mov     r8, rax; hrgnSrc2
0x18011974e  call    cs:__imp_CombineRgn
0x180119755  nop     dword ptr [rax+rax+00h]
0x18011975a  mov     rcx, rdi; ho
0x18011975d  call    cs:__imp_DeleteObject
0x180119764  nop     dword ptr [rax+rax+00h]
0x180119769  mov     rcx, [rsp+48h+var_10]
0x18011976e  xor     rcx, rsp; StackCookie
0x180119771  call    __security_check_cookie
0x180119776  mov     rbx, [rsp+48h+arg_8]
0x18011977b  add     rsp, 40h
0x18011977f  pop     rdi
0x180119780  retn
```
