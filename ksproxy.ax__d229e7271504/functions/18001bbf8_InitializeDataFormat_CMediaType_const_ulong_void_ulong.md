# InitializeDataFormat(CMediaType const *,ulong,void * *,ulong *)

- ea: `0x18001bbf8`
- end: `0x18001bd74`
- name: `?InitializeDataFormat@@YAJPEBVCMediaType@@KPEAPEAXPEAK@Z`
- size: `380`
- prototype: `__int64 __fastcall(const struct CMediaType *, unsigned int, void **, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001bb40`
- `0x18001ee00`
- `0x180025d60`
- `0x180030890`
- `0x1800315e0`
- `0x180035d90`

## callees

- `0x18001bbf8`
- `0x180044850`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001bcb5`
- `ole32!CoTaskMemAlloc` at `0x18001bcb5`

## pseudocode

```c
__int64 __fastcall InitializeDataFormat(const struct CMediaType *a1, unsigned int a2, void **a3, unsigned int *a4)
{
  __int64 v5; // rsi
  _DWORD *v6; // r9
  IUnknown *pUnk; // rcx
  unsigned int v10; // eax
  unsigned int v11; // ecx
  SIZE_T v12; // rcx
  char *v13; // rax
  char *v15; // rbx
  unsigned int lSampleSize; // eax
  __int64 v17; // [rsp+20h] [rbp-28h] BYREF
  void *Src; // [rsp+50h] [rbp+8h] BYREF

  v5 = a2;
  v6 = 0;
  pUnk = a1->pUnk;
  Src = 0;
  if ( pUnk )
  {
    v17 = 0;
    if ( pUnk->QueryInterface(pUnk, &GUID_d559999a_a4c3_11d2_876a_00a0c9223196, (void **)&v17) >= 0 )
    {
      (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v17 + 24LL))(v17, &Src);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v6 = Src;
  }
  v10 = a1->cbFormat + 64;
  if ( a1->cbFormat >= 0xFFFFFFC0 )
    goto LABEL_19;
  *a4 = v10;
  if ( !v6 )
    goto LABEL_10;
  if ( v10 + 7 < v10 || (v11 = (v10 + 7) & 0xFFFFFFF8, v10 = v11 + *v6, v10 < v11) )
  {
LABEL_19:
    *a4 = -1;
    return 2147942934LL;
  }
  *a4 = v10;
LABEL_10:
  v12 = v10 + (unsigned int)v5;
  if ( (unsigned int)v12 < (unsigned int)v5 )
    return 2147942934LL;
  v13 = (char *)CoTaskMemAlloc(v12);
  *a3 = v13;
  if ( !v13 )
    return 2147942414LL;
  v15 = &v13[v5];
  *(_DWORD *)v15 = a1->cbFormat + 64;
  *((_DWORD *)v15 + 1) = a1->bTemporalCompression != 0;
  if ( a1->bFixedSizeSamples )
    lSampleSize = a1->lSampleSize;
  else
    lSampleSize = 0;
  *((_DWORD *)v15 + 2) = lSampleSize;
  *((_DWORD *)v15 + 3) = 0;
  *((_OWORD *)v15 + 1) = a1->majortype;
  *((_OWORD *)v15 + 2) = a1->subtype;
  *((_OWORD *)v15 + 3) = a1->formattype;
  memcpy_0(v15 + 64, a1->pbFormat, a1->cbFormat);
  if ( Src )
  {
    *((_DWORD *)v15 + 1) |= 2u;
    memcpy_0(&v15[(*(_DWORD *)v15 + 7) & 0xFFFFFFF8], Src, *(unsigned int *)Src);
  }
  return 0;
}

```

## disassembly

```asm
0x18001bbf8  mov     r11, rsp
0x18001bbfb  mov     [r11+10h], rbx
0x18001bbff  mov     [r11+18h], rsi
0x18001bc03  push    rdi
0x18001bc04  push    r14
0x18001bc06  push    r15
0x18001bc08  sub     rsp, 30h
0x18001bc0c  mov     rbx, r9
0x18001bc0f  mov     esi, edx
0x18001bc11  xor     r9d, r9d
0x18001bc14  mov     rdi, rcx
0x18001bc17  mov     rcx, [rcx+40h]
0x18001bc1b  mov     r14, r8
0x18001bc1e  mov     [r11+8], r9
0x18001bc22  test    rcx, rcx
0x18001bc25  jz      short loc_18001BC71
0x18001bc27  mov     [r11-28h], r9
0x18001bc2b  lea     r8, [r11-28h]
0x18001bc2f  mov     rax, [rcx]
0x18001bc32  lea     rdx, _GUID_d559999a_a4c3_11d2_876a_00a0c9223196
0x18001bc39  mov     rax, [rax]
0x18001bc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc41  test    eax, eax
0x18001bc43  js      short loc_18001BC6C
0x18001bc45  mov     rcx, [rsp+48h+var_28]
0x18001bc4a  lea     rdx, [rsp+48h+Src]
0x18001bc4f  mov     rax, [rcx]
0x18001bc52  mov     rax, [rax+18h]
0x18001bc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc5b  mov     rcx, [rsp+48h+var_28]
0x18001bc60  mov     rax, [rcx]
0x18001bc63  mov     rax, [rax+10h]
0x18001bc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc6c  mov     r9, [rsp+48h+Src]
0x18001bc71  mov     eax, [rdi+48h]
0x18001bc74  add     eax, 40h ; '@'
0x18001bc77  cmp     eax, 40h ; '@'
0x18001bc7a  jb      loc_18001BD54
0x18001bc80  mov     [rbx], eax
0x18001bc82  mov     r15d, 0FFFFFFF8h
0x18001bc88  test    r9, r9
0x18001bc8b  jz      short loc_18001BCAA
0x18001bc8d  lea     ecx, [rax+7]
0x18001bc90  cmp     ecx, eax
0x18001bc92  jb      loc_18001BD54
0x18001bc98  mov     eax, [r9]
0x18001bc9b  and     ecx, r15d
0x18001bc9e  add     eax, ecx
0x18001bca0  cmp     eax, ecx
0x18001bca2  jb      loc_18001BD54
0x18001bca8  mov     [rbx], eax
0x18001bcaa  lea     ecx, [rax+rsi]; cb
0x18001bcad  cmp     ecx, esi
0x18001bcaf  jb      loc_18001BD5A
0x18001bcb5  call    cs:__imp_CoTaskMemAlloc
0x18001bcbc  nop     dword ptr [rax+rax+00h]
0x18001bcc1  mov     [r14], rax
0x18001bcc4  test    rax, rax
0x18001bcc7  jnz     short loc_18001BCD3
0x18001bcc9  mov     eax, 8007000Eh
0x18001bcce  jmp     loc_18001BD5F
0x18001bcd3  lea     rbx, [rax+rsi]
0x18001bcd7  mov     eax, [rdi+48h]
0x18001bcda  add     eax, 40h ; '@'
0x18001bcdd  mov     [rbx], eax
0x18001bcdf  xor     eax, eax
0x18001bce1  cmp     [rdi+24h], eax
0x18001bce4  setnz   al
0x18001bce7  mov     [rbx+4], eax
0x18001bcea  cmp     dword ptr [rdi+20h], 0
0x18001bcee  jz      short loc_18001BCF5
0x18001bcf0  mov     eax, [rdi+28h]
0x18001bcf3  jmp     short loc_18001BCF7
0x18001bcf5  xor     eax, eax
0x18001bcf7  mov     [rbx+8], eax
0x18001bcfa  lea     rcx, [rbx+40h]; void *
0x18001bcfe  mov     dword ptr [rbx+0Ch], 0
0x18001bd05  movups  xmm0, xmmword ptr [rdi]
0x18001bd08  movdqu  xmmword ptr [rbx+10h], xmm0
0x18001bd0d  movups  xmm1, xmmword ptr [rdi+10h]
0x18001bd11  movdqu  xmmword ptr [rbx+20h], xmm1
0x18001bd16  movups  xmm0, xmmword ptr [rdi+2Ch]
0x18001bd1a  movdqu  xmmword ptr [rbx+30h], xmm0
0x18001bd1f  mov     r8d, [rdi+48h]; Size
0x18001bd23  mov     rdx, [rdi+50h]; Src
0x18001bd27  call    memcpy_0
0x18001bd2c  cmp     [rsp+48h+Src], 0
0x18001bd32  jz      short loc_18001BD50
0x18001bd34  or      dword ptr [rbx+4], 2
0x18001bd38  mov     ecx, [rbx]
0x18001bd3a  mov     rdx, [rsp+48h+Src]; Src
0x18001bd3f  add     ecx, 7
0x18001bd42  and     rcx, r15
0x18001bd45  add     rcx, rbx; void *
0x18001bd48  mov     r8d, [rdx]; Size
0x18001bd4b  call    memcpy_0
0x18001bd50  xor     eax, eax
0x18001bd52  jmp     short loc_18001BD5F
0x18001bd54  mov     dword ptr [rbx], 0FFFFFFFFh
0x18001bd5a  mov     eax, 80070216h
0x18001bd5f  mov     rbx, [rsp+48h+arg_8]
0x18001bd64  mov     rsi, [rsp+48h+arg_10]
0x18001bd69  add     rsp, 30h
0x18001bd6d  pop     r15
0x18001bd6f  pop     r14
0x18001bd71  pop     rdi
0x18001bd72  retn
```
