# CMediaWrapperFilter::OutputGetMediaType(ulong,ulong,_AMMediaType *)

- ea: `0x1800177cc`
- end: `0x180017a50`
- name: `?OutputGetMediaType@CMediaWrapperFilter@@QEAAJKKPEAU_AMMediaType@@@Z`
- size: `644`
- prototype: `__int64 __fastcall(CMediaWrapperFilter *__hidden this, unsigned int, unsigned int, struct _AMMediaType *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180019880`

## callees

- `0x180001460`
- `0x180001cfc`
- `0x180007210`
- `0x180015f58`
- `0x18001640c`
- `0x1800177cc`
- `0x180018ebc`
- `0x18001e5b9`
- `0x18001e5c5`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180017805`
- `KERNEL32!EnterCriticalSection` at `0x180017805`
- `KERNEL32!LeaveCriticalSection` at `0x1800178a3`
- `KERNEL32!LeaveCriticalSection` at `0x180017a26`
- `KERNEL32!LeaveCriticalSection` at `0x1800178a3`
- `KERNEL32!LeaveCriticalSection` at `0x180017a26`
- `ole32!CoTaskMemAlloc` at `0x1800178b9`
- `ole32!CoTaskMemAlloc` at `0x1800178b9`
- `ole32!CoTaskMemFree` at `0x1800178ca`
- `ole32!CoTaskMemFree` at `0x1800178de`
- `ole32!CoTaskMemFree` at `0x180017920`
- `ole32!CoTaskMemFree` at `0x1800178ca`
- `ole32!CoTaskMemFree` at `0x1800178de`
- `ole32!CoTaskMemFree` at `0x180017920`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::OutputGetMediaType(
        CMediaWrapperFilter *this,
        unsigned int a2,
        unsigned int a3,
        struct _AMMediaType *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r12
  int v9; // eax
  int v10; // ebp
  __int64 v11; // rax
  ULONG cbFormat; // r14d
  SIZE_T v13; // r14
  struct _AMMediaType *v14; // rdi
  size_t v16; // r15
  void *v17; // r14
  __int64 v18; // rcx
  int v19[4]; // [rsp+30h] [rbp-B8h] BYREF
  struct _AMMediaType v20; // [rsp+40h] [rbp-A8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _AMMediaType *))(**((_QWORD **)this + 20) + 56LL))(
         *((_QWORD *)this + 20),
         a2,
         a3,
         a4);
  v10 = TranslateDMOError(v9);
  if ( v10 < 0 )
  {
    if ( !a2 && *((_DWORD *)this + 111) )
    {
      memset_0(&v20, 0, sizeof(v20));
      v18 = *((_QWORD *)this + 20);
      v20.lSampleSize = 1;
      v20.bFixedSizeSamples = 1;
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, struct _AMMediaType *))(*(_QWORD *)v18 + 56LL))(
              v18,
              0,
              0,
              &v20)
        && !memcmp_0(&FORMAT_VideoInfo, &v20.formattype, 0x10u) )
      {
        while ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 20) + 56LL))(
                   *((_QWORD *)this + 20),
                   0,
                   a2,
                   0) )
          ++a2;
        if ( a2 && a3 + 1 >= a2 && a3 + 1 < 2 * a2 )
          v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct _AMMediaType *))(**((_QWORD **)this + 20)
                                                                                         + 56LL))(
                  *((_QWORD *)this + 20),
                  0,
                  a3 - a2,
                  a4);
      }
      FreeMediaType(&v20);
    }
  }
  else if ( a4
         && *(_QWORD *)&a4->formattype.Data1 == *(_QWORD *)&FORMAT_VideoInfo.Data1
         && *(_QWORD *)a4->formattype.Data4 == *(_QWORD *)FORMAT_VideoInfo.Data4
         && !a2
         && *((_DWORD *)this + 111) )
  {
    v11 = *((_QWORD *)this + 17);
    cbFormat = a4->cbFormat;
    v19[0] = 0;
    v13 = cbFormat + 24;
    v14 = ConstructVIH2OutputType(a4, (const struct _AMMediaType *)(*(_QWORD *)v11 + 104LL));
    if ( !v14 )
    {
      LeaveCriticalSection(v4);
      return 2147500037LL;
    }
    v16 = v13;
    v17 = CoTaskMemAlloc(v13);
    if ( v17 )
    {
      CoTaskMemFree(a4->pbFormat);
      memcpy_0(v17, v14->pbFormat, v16);
      a4->majortype = v14->majortype;
      a4->subtype = v14->subtype;
      *(_OWORD *)&a4->bFixedSizeSamples = *(_OWORD *)&v14->bFixedSizeSamples;
      *(_OWORD *)&a4->formattype.Data2 = *(_OWORD *)&v14->formattype.Data2;
      *(_OWORD *)&a4->pUnk = *(_OWORD *)&v14->pUnk;
      a4->pbFormat = (BYTE *)v17;
      CoTaskMemFree(v14);
      if ( (int)CMediaWrapperFilter::CheckInterlaced(this, v19) >= 0 )
      {
        if ( v19[0] )
          *((_DWORD *)a4->pbFormat + 12) = 0;
      }
    }
    else
    {
      CoTaskMemFree(v14);
      v10 = -2147467259;
    }
  }
  LeaveCriticalSection(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800177cc  push    rbx
0x1800177ce  push    rbp
0x1800177cf  push    rsi
0x1800177d0  push    rdi
0x1800177d1  push    r12
0x1800177d3  push    r14
0x1800177d5  push    r15
0x1800177d7  sub     rsp, 0B0h
0x1800177de  mov     rax, cs:__security_cookie
0x1800177e5  xor     rax, rsp
0x1800177e8  mov     [rsp+0E8h+var_48], rax
0x1800177f0  lea     r12, [rcx+0E0h]
0x1800177f7  mov     rsi, rcx
0x1800177fa  mov     rcx, r12; lpCriticalSection
0x1800177fd  mov     rbx, r9
0x180017800  mov     r14d, r8d
0x180017803  mov     edi, edx
0x180017805  call    cs:__imp_EnterCriticalSection
0x18001780b  mov     rcx, [rsi+0A0h]
0x180017812  mov     r9, rbx
0x180017815  mov     r8d, r14d
0x180017818  mov     edx, edi
0x18001781a  mov     rax, [rcx]
0x18001781d  mov     rax, [rax+38h]
0x180017821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017826  mov     ecx, eax; int
0x180017828  call    ?TranslateDMOError@@YAJJ@Z; TranslateDMOError(long)
0x18001782d  mov     ebp, eax
0x18001782f  test    eax, eax
0x180017831  js      loc_180017956
0x180017837  test    rbx, rbx
0x18001783a  jz      loc_180017A23
0x180017840  mov     rax, [rbx+2Ch]
0x180017844  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18001784b  jnz     loc_180017A23
0x180017851  mov     rax, [rbx+34h]
0x180017855  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18001785c  jnz     loc_180017A23
0x180017862  test    edi, edi
0x180017864  jnz     loc_180017A23
0x18001786a  cmp     [rsi+1BCh], edi
0x180017870  jz      loc_180017A23
0x180017876  mov     rax, [rsi+88h]
0x18001787d  mov     rcx, rbx; struct _AMMediaType *
0x180017880  mov     r14d, [rbx+48h]
0x180017884  mov     [rsp+0E8h+var_B8], edi
0x180017888  add     r14d, 18h
0x18001788c  mov     rdx, [rax]
0x18001788f  add     rdx, 68h ; 'h'; struct _AMMediaType *
0x180017893  call    ?ConstructVIH2OutputType@@YAPEAU_AMMediaType@@PEBU1@0@Z; ConstructVIH2OutputType(_AMMediaType const *,_AMMediaType const *)
0x180017898  mov     rdi, rax
0x18001789b  test    rax, rax
0x18001789e  jnz     short loc_1800178B3
0x1800178a0  mov     rcx, r12; lpCriticalSection
0x1800178a3  call    cs:__imp_LeaveCriticalSection
0x1800178a9  mov     eax, 80004005h
0x1800178ae  jmp     loc_180017A2E
0x1800178b3  mov     rcx, r14; cb
0x1800178b6  mov     r15, r14
0x1800178b9  call    cs:__imp_CoTaskMemAlloc
0x1800178bf  mov     r14, rax
0x1800178c2  test    rax, rax
0x1800178c5  jnz     short loc_1800178DA
0x1800178c7  mov     rcx, rdi; pv
0x1800178ca  call    cs:__imp_CoTaskMemFree
0x1800178d0  mov     ebp, 80004005h
0x1800178d5  jmp     loc_180017A23
0x1800178da  mov     rcx, [rbx+50h]; pv
0x1800178de  call    cs:__imp_CoTaskMemFree
0x1800178e4  mov     rdx, [rdi+50h]; Src
0x1800178e8  mov     r8, r15; Size
0x1800178eb  mov     rcx, r14; void *
0x1800178ee  call    memcpy_0
0x1800178f3  movups  xmm0, xmmword ptr [rdi]
0x1800178f6  mov     rcx, rdi; pv
0x1800178f9  movups  xmmword ptr [rbx], xmm0
0x1800178fc  movups  xmm1, xmmword ptr [rdi+10h]
0x180017900  movups  xmmword ptr [rbx+10h], xmm1
0x180017904  movups  xmm0, xmmword ptr [rdi+20h]
0x180017908  movups  xmmword ptr [rbx+20h], xmm0
0x18001790c  movups  xmm1, xmmword ptr [rdi+30h]
0x180017910  movups  xmmword ptr [rbx+30h], xmm1
0x180017914  movups  xmm0, xmmword ptr [rdi+40h]
0x180017918  movups  xmmword ptr [rbx+40h], xmm0
0x18001791c  mov     [rbx+50h], r14
0x180017920  call    cs:__imp_CoTaskMemFree
0x180017926  lea     rdx, [rsp+0E8h+var_B8]; int *
0x18001792b  mov     rcx, rsi; this
0x18001792e  call    ?CheckInterlaced@CMediaWrapperFilter@@IEAAJPEAH@Z; CMediaWrapperFilter::CheckInterlaced(int *)
0x180017933  test    eax, eax
0x180017935  js      loc_180017A23
0x18001793b  cmp     [rsp+0E8h+var_B8], 0
0x180017940  jz      loc_180017A23
0x180017946  mov     rax, [rbx+50h]
0x18001794a  mov     dword ptr [rax+30h], 0
0x180017951  jmp     loc_180017A23
0x180017956  test    edi, edi
0x180017958  jnz     loc_180017A23
0x18001795e  cmp     [rsi+1BCh], edi
0x180017964  jz      loc_180017A23
0x18001796a  xor     edx, edx; Val
0x18001796c  lea     r8d, [rdi+58h]; Size
0x180017970  lea     rcx, [rsp+0E8h+var_A8]; void *
0x180017975  call    memset_0
0x18001797a  mov     rcx, [rsi+0A0h]
0x180017981  lea     r15d, [rdi+1]
0x180017985  mov     [rsp+0E8h+var_A8.lSampleSize], r15d
0x18001798a  lea     r9, [rsp+0E8h+var_A8]
0x18001798f  mov     [rsp+0E8h+var_A8.bFixedSizeSamples], r15d
0x180017994  xor     r8d, r8d
0x180017997  xor     edx, edx
0x180017999  mov     rax, [rcx]
0x18001799c  mov     rax, [rax+38h]
0x1800179a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179a5  test    eax, eax
0x1800179a7  jnz     short loc_180017A19
0x1800179a9  lea     r8d, [rdi+10h]; Size
0x1800179ad  lea     rdx, [rsp+0E8h+var_A8.formattype]; Buf2
0x1800179b2  lea     rcx, FORMAT_VideoInfo; Buf1
0x1800179b9  call    memcmp_0
0x1800179be  test    eax, eax
0x1800179c0  jnz     short loc_180017A19
0x1800179c2  mov     rcx, [rsi+0A0h]
0x1800179c9  xor     r9d, r9d
0x1800179cc  mov     r8d, edi
0x1800179cf  xor     edx, edx
0x1800179d1  mov     rax, [rcx]
0x1800179d4  mov     rax, [rax+38h]
0x1800179d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179dd  test    eax, eax
0x1800179df  jnz     short loc_1800179E6
0x1800179e1  add     edi, r15d
0x1800179e4  jmp     short loc_1800179C2
0x1800179e6  test    edi, edi
0x1800179e8  jz      short loc_180017A19
0x1800179ea  lea     ecx, [r14+1]
0x1800179ee  cmp     ecx, edi
0x1800179f0  jb      short loc_180017A19
0x1800179f2  lea     eax, [rdi+rdi]
0x1800179f5  cmp     ecx, eax
0x1800179f7  jnb     short loc_180017A19
0x1800179f9  mov     rcx, [rsi+0A0h]
0x180017a00  sub     r14d, edi
0x180017a03  mov     r9, rbx
0x180017a06  mov     r8d, r14d
0x180017a09  xor     edx, edx
0x180017a0b  mov     rax, [rcx]
0x180017a0e  mov     rax, [rax+38h]
0x180017a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a17  mov     ebp, eax
0x180017a19  lea     rcx, [rsp+0E8h+var_A8]; struct _AMMediaType *
0x180017a1e  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x180017a23  mov     rcx, r12; lpCriticalSection
0x180017a26  call    cs:__imp_LeaveCriticalSection
0x180017a2c  mov     eax, ebp
0x180017a2e  mov     rcx, [rsp+0E8h+var_48]
0x180017a36  xor     rcx, rsp; StackCookie
0x180017a39  call    __security_check_cookie
0x180017a3e  add     rsp, 0B0h
0x180017a45  pop     r15
0x180017a47  pop     r14
0x180017a49  pop     r12
0x180017a4b  pop     rdi
0x180017a4c  pop     rsi
0x180017a4d  pop     rbp
0x180017a4e  pop     rbx
0x180017a4f  retn
```
