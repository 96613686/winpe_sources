# CExtensionHelperInfo::IsAttributesMatched(std::list<tagHELPER_ATTRIBUTE,std::allocator<tagHELPER_ATTRIBUTE>> *)

- ea: `0x18001f418`
- end: `0x18001f507`
- name: `?IsAttributesMatched@CExtensionHelperInfo@@QEAA_NPEAV?$list@UtagHELPER_ATTRIBUTE@@V?$allocator@UtagHELPER_ATTRIBUTE@@@std@@@std@@@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180020f8c`

## callees

- `0x180006d58`
- `0x180008248`
- `0x18001eb8c`
- `0x18001f418`
- `0x18002c7f6`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18001f4cc`
- `KERNEL32!lstrcmpW` at `0x18001f4cc`

## pseudocode

```c
char __fastcall CExtensionHelperInfo::IsAttributesMatched(__int64 a1, __m128i **a2)
{
  __m128i *v4; // rbx
  __m128i v5; // xmm7
  __m128i v6; // xmm6
  __int64 v7; // rdi
  int v8; // eax
  int v9; // eax
  bool v10; // zf
  __int64 v12; // [rsp+108h] [rbp+10h] BYREF

  v4 = *a2;
  while ( 1 )
  {
    v4 = (__m128i *)v4->m128i_i64[0];
    if ( v4 == *a2 )
      break;
    v5 = v4[1];
    v6 = v4[2];
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v12,
      v4[1].m128i_i64[0]);
    v7 = *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,tagHELPER_ATTRIBUTE *>::operator[](
                      a1 + 72,
                      &v12);
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
    if ( v7 )
    {
      v8 = _mm_cvtsi128_si32(_mm_srli_si128(v5, 8));
      if ( v8 == *(_DWORD *)(v7 + 8) )
      {
        if ( v8 == 7 )
        {
          v10 = v6.m128i_i32[0] == *(_DWORD *)(v7 + 16);
        }
        else
        {
          if ( v8 == 10 )
          {
            v9 = lstrcmpW((LPCWSTR)v6.m128i_i64[0], *(LPCWSTR *)(v7 + 16));
          }
          else
          {
            if ( v8 != 14 )
              return 0;
            v9 = memcmp_0((const void *)_mm_srli_si128(v6, 8).m128i_i64[0], *(const void **)(v7 + 24), v6.m128i_u32[0]);
          }
          v10 = v9 == 0;
        }
        if ( v10 )
          continue;
      }
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001f418  mov     rax, rsp
0x18001f41b  push    rbx
0x18001f41c  push    rbp
0x18001f41d  push    rsi
0x18001f41e  push    rdi
0x18001f41f  sub     rsp, 0D8h
0x18001f426  movaps  xmmword ptr [rax-38h], xmm6
0x18001f42a  movaps  xmmword ptr [rax-48h], xmm7
0x18001f42e  mov     rsi, rdx
0x18001f431  mov     rbp, rcx
0x18001f434  mov     rbx, [rdx]
0x18001f437  mov     rbx, [rbx]
0x18001f43a  cmp     rbx, [rsi]
0x18001f43d  jz      loc_18001F4EB
0x18001f443  movups  xmm7, xmmword ptr [rbx+10h]
0x18001f447  movups  xmm6, xmmword ptr [rbx+20h]
0x18001f44b  movq    rdx, xmm7
0x18001f450  lea     rcx, [rsp+0F8h+arg_8]
0x18001f458  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001f45d  lea     rcx, [rbp+48h]
0x18001f461  lea     rdx, [rsp+0F8h+arg_8]
0x18001f469  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@@5@@std@@QEAAAEAPEAUtagHELPER_ATTRIBUTE@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,tagHELPER_ATTRIBUTE *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x18001f46e  mov     rdi, [rax]
0x18001f471  mov     rcx, [rsp+0F8h+arg_8]
0x18001f479  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001f47d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001f482  test    rdi, rdi
0x18001f485  jz      short loc_18001F4E7
0x18001f487  psrldq  xmm7, 8
0x18001f48c  movd    eax, xmm7
0x18001f490  cmp     eax, [rdi+8]
0x18001f493  jnz     short loc_18001F4E7
0x18001f495  cmp     eax, 7
0x18001f498  jz      short loc_18001F4D4
0x18001f49a  cmp     eax, 0Ah
0x18001f49d  jz      short loc_18001F4C3
0x18001f49f  cmp     eax, 0Eh
0x18001f4a2  jnz     short loc_18001F4E7
0x18001f4a4  movq    r8, xmm6
0x18001f4a9  mov     r8d, r8d; Size
0x18001f4ac  mov     rdx, [rdi+18h]; Buf2
0x18001f4b0  psrldq  xmm6, 8
0x18001f4b5  movq    rcx, xmm6; Buf1
0x18001f4ba  call    memcmp_0
0x18001f4bf  test    eax, eax
0x18001f4c1  jmp     short loc_18001F4DC
0x18001f4c3  mov     rdx, [rdi+10h]; lpString2
0x18001f4c7  movq    rcx, xmm6; lpString1
0x18001f4cc  call    cs:__imp_lstrcmpW
0x18001f4d2  jmp     short loc_18001F4BF
0x18001f4d4  movq    rax, xmm6
0x18001f4d9  cmp     eax, [rdi+10h]
0x18001f4dc  setz    al
0x18001f4df  test    al, al
0x18001f4e1  jnz     loc_18001F437
0x18001f4e7  xor     al, al
0x18001f4e9  jmp     short loc_18001F4ED
0x18001f4eb  mov     al, 1
0x18001f4ed  lea     r11, [rsp+0F8h+var_20]
0x18001f4f5  movaps  xmm6, xmmword ptr [r11-18h]
0x18001f4fa  movaps  xmm7, xmmword ptr [r11-28h]
0x18001f4ff  mov     rsp, r11
0x18001f502  pop     rdi
0x18001f503  pop     rsi
0x18001f504  pop     rbp
0x18001f505  pop     rbx
0x18001f506  retn
```
