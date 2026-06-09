# CWrapperOutputPin::CheckMediaType(CMediaType const *)

- ea: `0x1800190b0`
- end: `0x18001916b`
- name: `?CheckMediaType@CWrapperOutputPin@@UEAAJPEBVCMediaType@@@Z`
- size: `187`
- prototype: `int(CWrapperOutputPin *__hidden this, const struct CMediaType *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180016314`
- `0x180018ebc`
- `0x1800190b0`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001912e`
- `ole32!CoTaskMemFree` at `0x18001912e`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::CheckMediaType(CWrapperOutputPin *this, const struct CMediaType *a2)
{
  __int64 v2; // rbx
  unsigned int v3; // r10d
  struct _AMMediaType *v4; // rax
  struct _AMMediaType *v5; // rdi
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax

  v2 = *((_QWORD *)this + 10);
  v3 = *((_DWORD *)this + 64);
  if ( *(_OWORD *)((char *)a2 + 44) == *(_OWORD *)&FORMAT_VideoInfo2 && !v3 && *(_DWORD *)(v2 + 444) )
  {
    v4 = ConstructVIH1Type((const struct _AMMediaType *)a2);
    v5 = v4;
    if ( v4 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _AMMediaType *, __int64))(**(_QWORD **)(v2 + 160) + 72LL))(
             *(_QWORD *)(v2 + 160),
             0,
             v4,
             1);
      v6 = TranslateDMOError(v7);
      CoTaskMemFree(v5);
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct CMediaType *, __int64))(**(_QWORD **)(v2 + 160) + 72LL))(
           *(_QWORD *)(v2 + 160),
           v3,
           a2,
           1);
    return (unsigned int)TranslateDMOError(v8);
  }
  return v6;
}

```

## disassembly

```asm
0x1800190b0  mov     [rsp+arg_0], rbx
0x1800190b5  push    rdi
0x1800190b6  sub     rsp, 30h
0x1800190ba  mov     rax, [rdx+2Ch]
0x1800190be  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800190c5  mov     rbx, [rcx+50h]
0x1800190c9  mov     r10d, [rcx+100h]
0x1800190d0  jnz     short loc_180019136
0x1800190d2  mov     rax, [rdx+34h]
0x1800190d6  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800190dd  jnz     short loc_180019136
0x1800190df  test    r10d, r10d
0x1800190e2  jnz     short loc_180019136
0x1800190e4  cmp     [rbx+1BCh], r10d
0x1800190eb  jz      short loc_180019136
0x1800190ed  mov     rcx, rdx; struct _AMMediaType *
0x1800190f0  call    ?ConstructVIH1Type@@YAPEAU_AMMediaType@@PEBU1@@Z; ConstructVIH1Type(_AMMediaType const *)
0x1800190f5  mov     rdi, rax
0x1800190f8  test    rax, rax
0x1800190fb  jnz     short loc_180019104
0x1800190fd  mov     ebx, 80004005h
0x180019102  jmp     short loc_18001915E
0x180019104  mov     rcx, [rbx+0A0h]
0x18001910b  mov     r9d, 1
0x180019111  mov     r8, rdi
0x180019114  xor     edx, edx
0x180019116  mov     rax, [rcx]
0x180019119  mov     rax, [rax+48h]
0x18001911d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019122  mov     ecx, eax; int
0x180019124  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x180019129  mov     rcx, rdi; pv
0x18001912c  mov     ebx, eax
0x18001912e  call    cs:__imp_CoTaskMemFree
0x180019134  jmp     short loc_18001915E
0x180019136  mov     rcx, [rbx+0A0h]
0x18001913d  mov     r8, rdx
0x180019140  mov     r9d, 1
0x180019146  mov     edx, r10d
0x180019149  mov     rax, [rcx]
0x18001914c  mov     rax, [rax+48h]
0x180019150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019155  mov     ecx, eax; int
0x180019157  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x18001915c  mov     ebx, eax
0x18001915e  mov     eax, ebx
0x180019160  mov     rbx, [rsp+38h+arg_0]
0x180019165  add     rsp, 30h
0x180019169  pop     rdi
0x18001916a  retn
```
