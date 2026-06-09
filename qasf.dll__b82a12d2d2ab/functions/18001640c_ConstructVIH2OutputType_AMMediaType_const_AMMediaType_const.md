# ConstructVIH2OutputType(_AMMediaType const *,_AMMediaType const *)

- ea: `0x18001640c`
- end: `0x1800164f0`
- name: `?ConstructVIH2OutputType@@YAPEAU_AMMediaType@@PEBU1@0@Z`
- size: `228`
- prototype: `struct _AMMediaType *__fastcall(const struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800177cc`

## callees

- `0x18001640c`
- `0x18001e5c5`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180016429`
- `ole32!CoTaskMemAlloc` at `0x180016429`
- `ole32!CoTaskMemFree` at `0x1800164df`
- `ole32!CoTaskMemFree` at `0x1800164df`

## pseudocode

```c
struct _AMMediaType *__fastcall ConstructVIH2OutputType(const struct _AMMediaType *a1, const struct _AMMediaType *a2)
{
  ULONG cbFormat; // eax
  SIZE_T v5; // rcx
  char *v6; // rax
  char *v7; // rbx
  BYTE *pbFormat; // rcx
  _OWORD *v9; // rsi
  BYTE *v10; // rax
  struct _AMMediaType *result; // rax

  cbFormat = a1->cbFormat;
  v5 = cbFormat + 112;
  if ( (unsigned int)v5 >= cbFormat )
  {
    v6 = (char *)CoTaskMemAlloc(v5);
    v7 = v6;
    if ( v6 )
    {
      if ( a2->cbFormat >= 0x48 )
      {
        pbFormat = a2->pbFormat;
        v9 = v6 + 88;
        *(_OWORD *)(v6 + 136) = *((_OWORD *)pbFormat + 3);
        *((_QWORD *)v6 + 19) = *((_QWORD *)pbFormat + 8);
        if ( a1->cbFormat >= 0x30 )
        {
          v10 = a1->pbFormat;
          *v9 = *(_OWORD *)v10;
          v9[1] = *((_OWORD *)v10 + 1);
          v9[2] = *((_OWORD *)v10 + 2);
          memcpy_0((char *)v9 + 72, a1->pbFormat + 48, a1->cbFormat - 48);
          *(GUID *)v7 = a1->majortype;
          *((_OWORD *)v7 + 1) = a1->subtype;
          *((_OWORD *)v7 + 2) = *(_OWORD *)&a1->bFixedSizeSamples;
          *((_OWORD *)v7 + 3) = *(_OWORD *)&a1->formattype.Data2;
          *((_OWORD *)v7 + 4) = *(_OWORD *)&a1->pUnk;
          *((_QWORD *)v7 + 10) = v9;
          *((_DWORD *)v7 + 18) = a1->cbFormat + 24;
          result = (struct _AMMediaType *)v7;
          *(GUID *)(v7 + 44) = FORMAT_VideoInfo2;
          return result;
        }
      }
      CoTaskMemFree(v6);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001640c  push    rbx
0x18001640e  push    rbp
0x18001640f  push    rsi
0x180016410  push    rdi
0x180016411  sub     rsp, 28h
0x180016415  mov     eax, [rcx+48h]
0x180016418  mov     rdi, rcx
0x18001641b  mov     rbp, rdx
0x18001641e  lea     ecx, [rax+70h]; cb
0x180016421  cmp     ecx, eax
0x180016423  jb      loc_1800164E5
0x180016429  call    cs:__imp_CoTaskMemAlloc
0x18001642f  mov     rbx, rax
0x180016432  test    rax, rax
0x180016435  jz      loc_1800164E5
0x18001643b  cmp     dword ptr [rbp+48h], 48h ; 'H'
0x18001643f  jb      loc_1800164DC
0x180016445  mov     rcx, [rbp+50h]
0x180016449  lea     rsi, [rax+58h]
0x18001644d  movups  xmm0, xmmword ptr [rcx+30h]
0x180016451  movups  xmmword ptr [rsi+30h], xmm0
0x180016455  movsd   xmm1, qword ptr [rcx+40h]
0x18001645a  movsd   qword ptr [rsi+40h], xmm1
0x18001645f  cmp     dword ptr [rdi+48h], 30h ; '0'
0x180016463  jb      short loc_1800164DC
0x180016465  mov     rax, [rdi+50h]
0x180016469  lea     rcx, [rsi+48h]; void *
0x18001646d  movups  xmm0, xmmword ptr [rax]
0x180016470  movups  xmmword ptr [rsi], xmm0
0x180016473  movups  xmm1, xmmword ptr [rax+10h]
0x180016477  movups  xmmword ptr [rsi+10h], xmm1
0x18001647b  movups  xmm0, xmmword ptr [rax+20h]
0x18001647f  movups  xmmword ptr [rsi+20h], xmm0
0x180016483  mov     r8d, [rdi+48h]
0x180016487  mov     rdx, [rdi+50h]
0x18001648b  sub     r8d, 30h ; '0'; Size
0x18001648f  add     rdx, 30h ; '0'; Src
0x180016493  call    memcpy_0
0x180016498  movups  xmm0, xmmword ptr [rdi]
0x18001649b  movups  xmmword ptr [rbx], xmm0
0x18001649e  movups  xmm1, xmmword ptr [rdi+10h]
0x1800164a2  movups  xmmword ptr [rbx+10h], xmm1
0x1800164a6  movups  xmm0, xmmword ptr [rdi+20h]
0x1800164aa  movups  xmmword ptr [rbx+20h], xmm0
0x1800164ae  movups  xmm1, xmmword ptr [rdi+30h]
0x1800164b2  movups  xmmword ptr [rbx+30h], xmm1
0x1800164b6  movups  xmm0, xmmword ptr [rdi+40h]
0x1800164ba  movups  xmmword ptr [rbx+40h], xmm0
0x1800164be  mov     [rbx+50h], rsi
0x1800164c2  mov     eax, [rdi+48h]
0x1800164c5  add     eax, 18h
0x1800164c8  mov     [rbx+48h], eax
0x1800164cb  mov     rax, rbx
0x1800164ce  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x1800164d5  movdqu  xmmword ptr [rbx+2Ch], xmm0
0x1800164da  jmp     short loc_1800164E7
0x1800164dc  mov     rcx, rbx; pv
0x1800164df  call    cs:__imp_CoTaskMemFree
0x1800164e5  xor     eax, eax
0x1800164e7  add     rsp, 28h
0x1800164eb  pop     rdi
0x1800164ec  pop     rsi
0x1800164ed  pop     rbp
0x1800164ee  pop     rbx
0x1800164ef  retn
```
