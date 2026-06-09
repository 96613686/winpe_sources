# CMediaWrapperFilter::ChangeOutputFormatWhenUsingVideoInfoHeader2HackIfNecessary(ulong)

- ea: `0x180015c64`
- end: `0x180015f51`
- name: `?ChangeOutputFormatWhenUsingVideoInfoHeader2HackIfNecessary@CMediaWrapperFilter@@IEAAJK@Z`
- size: `749`
- prototype: `__int64 __fastcall(CMediaWrapperFilter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180018750`

## callees

- `0x180001460`
- `0x180001cfc`
- `0x180007104`
- `0x1800071e8`
- `0x180007210`
- `0x180015c64`
- `0x180016314`
- `0x180018ebc`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015d38`
- `ole32!CoTaskMemFree` at `0x180015d38`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::ChangeOutputFormatWhenUsingVideoInfoHeader2HackIfNecessary(
        CMediaWrapperFilter *this,
        unsigned int a2)
{
  __int64 v2; // rax
  __int64 v4; // r15
  __int64 v5; // rcx
  int v6; // ebx
  struct _AMMediaType *v7; // rax
  struct _AMMediaType *v8; // rbx
  __int64 result; // rax
  int v10; // esi
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  const struct _AMMediaType *v13; // rsi
  __int64 v14; // rax
  BYTE *pbFormat; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rcx
  struct _AMMediaType *pv; // [rsp+30h] [rbp-49h] BYREF
  struct _AMMediaType v21; // [rsp+40h] [rbp-39h] BYREF

  v2 = *((_QWORD *)this + 18);
  pv = 0;
  v4 = a2;
  v5 = *(_QWORD *)(*(_QWORD *)(v2 + 8LL * a2) + 360LL);
  v6 = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType **))(*(_QWORD *)v5 + 104LL))(v5, &pv);
  if ( v6 )
    goto LABEL_16;
  if ( *(_QWORD *)&pv->formattype.Data1 == *(_QWORD *)&FORMAT_VideoInfo2.Data1
    && *(_QWORD *)pv->formattype.Data4 == *(_QWORD *)FORMAT_VideoInfo2.Data4
    && !(_DWORD)v4
    && *((_DWORD *)this + 111) )
  {
    v7 = ConstructVIH1Type(pv);
    v8 = v7;
    if ( !v7 )
    {
      if ( pv )
        DeleteMediaType(pv);
      return 2147500037LL;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *, _QWORD))(**((_QWORD **)this + 20) + 72LL))(
            *((_QWORD *)this + 20),
            0,
            v7,
            0);
    CoTaskMemFree(v8);
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *, _QWORD))(**((_QWORD **)this + 20) + 72LL))(
            *((_QWORD *)this + 20),
            (unsigned int)v4,
            pv,
            0);
  }
  v6 = TranslateDMOError(v10);
  if ( v6 >= 0 )
  {
LABEL_16:
    if ( pv )
      DeleteMediaType(pv);
    v11 = *(_QWORD *)(*((_QWORD *)this + 18) + 8 * v4);
    if ( *(_BYTE *)(v11 + 420) )
    {
      if ( *(_QWORD *)(v11 + 148) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
        && *(_QWORD *)(v11 + 156) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
      {
        v12 = *(_QWORD **)(*((_QWORD *)this + 17) + 8 * v4);
        if ( *(_QWORD *)((char *)v12 + 148) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
          && *(_QWORD *)((char *)v12 + 156) == *(_QWORD *)FORMAT_VideoInfo2.Data4
          && *(_QWORD *)(v11 + 148) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
          && *(_QWORD *)(v11 + 156) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
        {
          v13 = (const struct _AMMediaType *)(v11 + 104);
          if ( v12[13] == *(_QWORD *)(v11 + 104)
            && v12[14] == *(_QWORD *)(v11 + 112)
            && !(_DWORD)v4
            && *((_DWORD *)this + 111) )
          {
            memset_0(&v21, 0, sizeof(v21));
            v21.lSampleSize = 1;
            v21.bFixedSizeSamples = 1;
            v6 = CopyMediaType(&v21, v13);
            if ( v6 >= 0 )
            {
              v14 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 8 * v4) + 184LL);
              pbFormat = v21.pbFormat;
              *((_OWORD *)v21.pbFormat + 3) = *(_OWORD *)(v14 + 48);
              *((_QWORD *)pbFormat + 8) = *(_QWORD *)(v14 + 64);
              v16 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 18) + 8 * v4) + 48LL);
              if ( v16 )
              {
                v6 = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v16 + 88LL))(v16, &v21);
                if ( v6 >= 0 )
                {
                  v17 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 17) + 8 * v4) + 184LL);
                  v18 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 18) + 8 * v4) + 184LL);
                  *(_OWORD *)(v18 + 48) = *(_OWORD *)(v17 + 48);
                  *(_QWORD *)(v18 + 64) = *(_QWORD *)(v17 + 64);
                  v19 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 18) + 8 * v4) + 360LL);
                  v6 = (*(__int64 (__fastcall **)(__int64, struct _AMMediaType *))(*(_QWORD *)v19 + 112LL))(v19, &v21);
                }
              }
            }
            FreeMediaType(&v21);
          }
        }
      }
      result = 0;
      if ( v6 < 0 )
        return (unsigned int)v6;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( pv )
      DeleteMediaType(pv);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180015c64  mov     [rsp-8+arg_10], rbx
0x180015c69  push    rbp
0x180015c6a  push    rsi
0x180015c6b  push    rdi
0x180015c6c  push    r14
0x180015c6e  push    r15
0x180015c70  lea     rbp, [rsp-37h]
0x180015c75  sub     rsp, 0B0h
0x180015c7c  mov     rax, cs:__security_cookie
0x180015c83  xor     rax, rsp
0x180015c86  mov     [rbp+57h+var_30], rax
0x180015c8a  mov     rax, [rcx+90h]
0x180015c91  mov     rdi, rcx
0x180015c94  mov     [rbp+57h+pv], 0
0x180015c9c  mov     r15d, edx
0x180015c9f  lea     rdx, [rbp+57h+pv]
0x180015ca3  mov     r8, [rax+r15*8]
0x180015ca7  mov     rcx, [r8+168h]
0x180015cae  mov     rax, [rcx]
0x180015cb1  mov     rax, [rax+68h]
0x180015cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cba  mov     ebx, eax
0x180015cbc  test    eax, eax
0x180015cbe  jnz     loc_180015D7D
0x180015cc4  mov     r8, [rbp+57h+pv]
0x180015cc8  mov     rax, [r8+2Ch]
0x180015ccc  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180015cd3  jnz     short loc_180015D40
0x180015cd5  mov     rax, [r8+34h]
0x180015cd9  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180015ce0  jnz     short loc_180015D40
0x180015ce2  test    r15d, r15d
0x180015ce5  jnz     short loc_180015D40
0x180015ce7  cmp     [rdi+1BCh], r15d
0x180015cee  jz      short loc_180015D40
0x180015cf0  mov     rcx, r8; struct _AMMediaType *
0x180015cf3  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x180015cf8  mov     rbx, rax
0x180015cfb  test    rax, rax
0x180015cfe  jnz     short loc_180015D18
0x180015d00  mov     rcx, [rbp+57h+pv]; pv
0x180015d04  test    rcx, rcx
0x180015d07  jz      short loc_180015D0E
0x180015d09  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180015d0e  mov     eax, 80004005h
0x180015d13  jmp     loc_180015F2E
0x180015d18  mov     rcx, [rdi+0A0h]
0x180015d1f  xor     r9d, r9d
0x180015d22  mov     r8, rbx
0x180015d25  xor     edx, edx
0x180015d27  mov     rax, [rcx]
0x180015d2a  mov     rax, [rax+48h]
0x180015d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d33  mov     rcx, rbx; pv
0x180015d36  mov     esi, eax
0x180015d38  call    cs:__imp_CoTaskMemFree
0x180015d3e  jmp     short loc_180015D5B
0x180015d40  mov     rcx, [rdi+0A0h]
0x180015d47  xor     r9d, r9d
0x180015d4a  mov     edx, r15d
0x180015d4d  mov     rax, [rcx]
0x180015d50  mov     rax, [rax+48h]
0x180015d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d59  mov     esi, eax
0x180015d5b  mov     ecx, esi; int
0x180015d5d  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x180015d62  mov     ebx, eax
0x180015d64  test    eax, eax
0x180015d66  jns     short loc_180015D7D
0x180015d68  mov     rcx, [rbp+57h+pv]; pv
0x180015d6c  test    rcx, rcx
0x180015d6f  jz      short loc_180015D76
0x180015d71  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180015d76  mov     eax, ebx
0x180015d78  jmp     loc_180015F2E
0x180015d7d  mov     rcx, [rbp+57h+pv]; pv
0x180015d81  test    rcx, rcx
0x180015d84  jz      short loc_180015D8B
0x180015d86  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180015d8b  mov     rax, [rdi+90h]
0x180015d92  mov     rcx, [rax+r15*8]
0x180015d96  cmp     byte ptr [rcx+1A4h], 0
0x180015d9d  jz      loc_180015F2C
0x180015da3  mov     r9, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180015daa  cmp     [rcx+94h], r9
0x180015db1  jnz     loc_180015F23
0x180015db7  mov     r8, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180015dbe  cmp     [rcx+9Ch], r8
0x180015dc5  jnz     loc_180015F23
0x180015dcb  mov     rax, [rdi+88h]
0x180015dd2  mov     rdx, [rax+r15*8]
0x180015dd6  cmp     [rdx+94h], r9
0x180015ddd  jnz     loc_180015F23
0x180015de3  cmp     [rdx+9Ch], r8
0x180015dea  jnz     loc_180015F23
0x180015df0  cmp     [rcx+94h], r9
0x180015df7  jnz     loc_180015F23
0x180015dfd  cmp     [rcx+9Ch], r8
0x180015e04  jnz     loc_180015F23
0x180015e0a  mov     rax, [rdx+68h]
0x180015e0e  lea     rsi, [rcx+68h]
0x180015e12  cmp     rax, [rsi]
0x180015e15  jnz     loc_180015F23
0x180015e1b  mov     rax, [rdx+70h]
0x180015e1f  cmp     rax, [rsi+8]
0x180015e23  jnz     loc_180015F23
0x180015e29  test    r15d, r15d
0x180015e2c  jnz     loc_180015F23
0x180015e32  cmp     [rdi+1BCh], r15d
0x180015e39  jz      loc_180015F23
0x180015e3f  xor     edx, edx; Val
0x180015e41  lea     r8d, [r15+58h]; Size
0x180015e45  lea     rcx, [rbp+57h+var_90]; void *
0x180015e49  call    memset_0
0x180015e4e  lea     eax, [r15+1]
0x180015e52  mov     rdx, rsi; struct _AMMediaType *
0x180015e55  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180015e59  mov     [rbp+57h+var_90.lSampleSize], eax
0x180015e5c  mov     [rbp+57h+var_90.bFixedSizeSamples], eax
0x180015e5f  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180015e64  mov     ebx, eax
0x180015e66  test    eax, eax
0x180015e68  js      loc_180015F1A
0x180015e6e  mov     rax, [rdi+88h]
0x180015e75  mov     rcx, [rax+r15*8]
0x180015e79  mov     rax, [rcx+0B8h]
0x180015e80  mov     rcx, [rbp+57h+var_90.pbFormat]
0x180015e84  movups  xmm0, xmmword ptr [rax+30h]
0x180015e88  movups  xmmword ptr [rcx+30h], xmm0
0x180015e8c  movsd   xmm1, qword ptr [rax+40h]
0x180015e91  movsd   qword ptr [rcx+40h], xmm1
0x180015e96  mov     rax, [rdi+90h]
0x180015e9d  mov     rcx, [rax+r15*8]
0x180015ea1  mov     rcx, [rcx+30h]
0x180015ea5  test    rcx, rcx
0x180015ea8  jz      short loc_180015F1A
0x180015eaa  mov     rax, [rcx]
0x180015ead  lea     rdx, [rbp+57h+var_90]
0x180015eb1  mov     rax, [rax+58h]
0x180015eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eba  mov     ebx, eax
0x180015ebc  test    eax, eax
0x180015ebe  js      short loc_180015F1A
0x180015ec0  mov     rax, [rdi+88h]
0x180015ec7  mov     rcx, [rax+r15*8]
0x180015ecb  mov     rax, [rdi+90h]
0x180015ed2  mov     rdx, [rcx+0B8h]
0x180015ed9  mov     rcx, [rax+r15*8]
0x180015edd  movups  xmm0, xmmword ptr [rdx+30h]
0x180015ee1  mov     rax, [rcx+0B8h]
0x180015ee8  movups  xmmword ptr [rax+30h], xmm0
0x180015eec  movsd   xmm1, qword ptr [rdx+40h]
0x180015ef1  lea     rdx, [rbp+57h+var_90]
0x180015ef5  movsd   qword ptr [rax+40h], xmm1
0x180015efa  mov     rax, [rdi+90h]
0x180015f01  mov     rcx, [rax+r15*8]
0x180015f05  mov     rcx, [rcx+168h]
0x180015f0c  mov     rax, [rcx]
0x180015f0f  mov     rax, [rax+70h]
0x180015f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f18  mov     ebx, eax
0x180015f1a  lea     rcx, [rbp+57h+var_90]; struct _AMMediaType *
0x180015f1e  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180015f23  xor     eax, eax
0x180015f25  test    ebx, ebx
0x180015f27  cmovs   eax, ebx
0x180015f2a  jmp     short loc_180015F2E
0x180015f2c  xor     eax, eax
0x180015f2e  mov     rcx, [rbp+57h+var_30]
0x180015f32  xor     rcx, rsp; StackCookie
0x180015f35  call    __security_check_cookie
0x180015f3a  mov     rbx, [rsp+0D0h+arg_10]
0x180015f42  add     rsp, 0B0h
0x180015f49  pop     r15
0x180015f4b  pop     r14
0x180015f4d  pop     rdi
0x180015f4e  pop     rsi
0x180015f4f  pop     rbp
0x180015f50  retn
```
