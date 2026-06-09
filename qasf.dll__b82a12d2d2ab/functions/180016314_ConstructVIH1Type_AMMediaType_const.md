# ConstructVIH1Type(_AMMediaType const *)

- ea: `0x180016314`
- end: `0x180016406`
- name: `?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z`
- size: `242`
- prototype: `struct _AMMediaType *__fastcall(const struct _AMMediaType *)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008980`
- `0x180009020`
- `0x180009d70`
- `0x18000ce10`
- `0x180015c64`
- `0x180016dd4`
- `0x180016e8c`
- `0x1800190b0`
- `0x18001a900`

## callees

- `0x180016314`
- `0x18001e5c5`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001636b`
- `ole32!CoTaskMemAlloc` at `0x18001636b`

## pseudocode

```c
struct _AMMediaType *__fastcall ConstructVIH1Type(const struct _AMMediaType *a1)
{
  ULONG cbFormat; // eax
  char *v3; // rax
  char *v4; // rsi
  BYTE *pbFormat; // rcx
  char *v6; // rbx
  struct _AMMediaType *result; // rax

  if ( *(_QWORD *)&FORMAT_VideoInfo2.Data1 != *(_QWORD *)&a1->formattype.Data1 )
    return 0;
  if ( *(_QWORD *)FORMAT_VideoInfo2.Data4 != *(_QWORD *)a1->formattype.Data4 )
    return 0;
  cbFormat = a1->cbFormat;
  if ( cbFormat < 0x70 )
    return 0;
  if ( cbFormat + 88 < cbFormat )
    return 0;
  if ( cbFormat + 88 < 0x18 )
    return 0;
  v3 = (char *)CoTaskMemAlloc(cbFormat + 64);
  v4 = v3;
  if ( !v3 )
    return 0;
  pbFormat = a1->pbFormat;
  v6 = v3 + 88;
  *(_OWORD *)(v3 + 88) = *(_OWORD *)pbFormat;
  *(_OWORD *)(v3 + 104) = *((_OWORD *)pbFormat + 1);
  *(_OWORD *)(v3 + 120) = *((_OWORD *)pbFormat + 2);
  memcpy_0(v3 + 136, a1->pbFormat + 72, a1->cbFormat - 72);
  *(GUID *)v4 = a1->majortype;
  *((_OWORD *)v4 + 1) = a1->subtype;
  *((_OWORD *)v4 + 2) = *(_OWORD *)&a1->bFixedSizeSamples;
  *((_OWORD *)v4 + 3) = *(_OWORD *)&a1->formattype.Data2;
  *((_OWORD *)v4 + 4) = *(_OWORD *)&a1->pUnk;
  *((_QWORD *)v4 + 10) = v6;
  *((_DWORD *)v4 + 18) = a1->cbFormat - 24;
  result = (struct _AMMediaType *)v4;
  *(GUID *)(v4 + 44) = FORMAT_VideoInfo;
  return result;
}

```

## disassembly

```asm
0x180016314  mov     [rsp+arg_0], rbx
0x180016319  mov     [rsp+arg_8], rsi
0x18001631e  push    rdi
0x18001631f  sub     rsp, 20h
0x180016323  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18001632a  mov     rdi, rcx
0x18001632d  cmp     rax, [rcx+2Ch]
0x180016331  jnz     loc_1800163F4
0x180016337  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18001633e  cmp     rax, [rcx+34h]
0x180016342  jnz     loc_1800163F4
0x180016348  mov     eax, [rcx+48h]
0x18001634b  cmp     eax, 70h ; 'p'
0x18001634e  jb      loc_1800163F4
0x180016354  lea     ecx, [rax+58h]
0x180016357  cmp     ecx, eax
0x180016359  jb      loc_1800163F4
0x18001635f  cmp     ecx, 18h
0x180016362  jb      loc_1800163F4
0x180016368  add     ecx, 0FFFFFFE8h; cb
0x18001636b  call    cs:__imp_CoTaskMemAlloc
0x180016371  mov     rsi, rax
0x180016374  test    rax, rax
0x180016377  jz      short loc_1800163F4
0x180016379  mov     rcx, [rdi+50h]
0x18001637d  lea     rbx, [rax+58h]
0x180016381  movups  xmm0, xmmword ptr [rcx]
0x180016384  movups  xmmword ptr [rbx], xmm0
0x180016387  movups  xmm1, xmmword ptr [rcx+10h]
0x18001638b  movups  xmmword ptr [rbx+10h], xmm1
0x18001638f  movups  xmm0, xmmword ptr [rcx+20h]
0x180016393  lea     rcx, [rbx+30h]; void *
0x180016397  movups  xmmword ptr [rbx+20h], xmm0
0x18001639b  mov     r8d, [rdi+48h]
0x18001639f  mov     rdx, [rdi+50h]
0x1800163a3  sub     r8d, 48h ; 'H'; Size
0x1800163a7  add     rdx, 48h ; 'H'; Src
0x1800163ab  call    memcpy_0
0x1800163b0  movups  xmm0, xmmword ptr [rdi]
0x1800163b3  movups  xmmword ptr [rsi], xmm0
0x1800163b6  movups  xmm1, xmmword ptr [rdi+10h]
0x1800163ba  movups  xmmword ptr [rsi+10h], xmm1
0x1800163be  movups  xmm0, xmmword ptr [rdi+20h]
0x1800163c2  movups  xmmword ptr [rsi+20h], xmm0
0x1800163c6  movups  xmm1, xmmword ptr [rdi+30h]
0x1800163ca  movups  xmmword ptr [rsi+30h], xmm1
0x1800163ce  movups  xmm0, xmmword ptr [rdi+40h]
0x1800163d2  movups  xmmword ptr [rsi+40h], xmm0
0x1800163d6  mov     [rsi+50h], rbx
0x1800163da  mov     eax, [rdi+48h]
0x1800163dd  sub     eax, 18h
0x1800163e0  mov     [rsi+48h], eax
0x1800163e3  mov     rax, rsi
0x1800163e6  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x1800163ed  movdqu  xmmword ptr [rsi+2Ch], xmm0
0x1800163f2  jmp     short loc_1800163F6
0x1800163f4  xor     eax, eax
0x1800163f6  mov     rbx, [rsp+28h+arg_0]
0x1800163fb  mov     rsi, [rsp+28h+arg_8]
0x180016400  add     rsp, 20h
0x180016404  pop     rdi
0x180016405  retn
```
