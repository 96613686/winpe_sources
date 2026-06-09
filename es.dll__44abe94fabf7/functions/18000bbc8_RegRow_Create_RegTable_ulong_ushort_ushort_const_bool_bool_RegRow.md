# RegRow::Create(RegTable *,ulong,ushort *,ushort const *,bool,bool,RegRow * &)

- ea: `0x18000bbc8`
- end: `0x18000bec8`
- name: `?Create@RegRow@@CAJPEAVRegTable@@KPEAGPEBG_N3AEAPEAV1@@Z`
- size: `768`
- prototype: `__int64 __fastcall(struct RegTable *, unsigned int, unsigned __int16 *, const unsigned __int16 *, bool, bool, struct RegRow **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b028`
- `0x18000c784`

## callees

- `0x18000bbc8`
- `0x180017528`
- `0x180017aa0`
- `0x18002c234`
- `0x18003a3e4`
- `0x18003a48c`
- `0x18003c0c4`
- `0x1800434c6`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bcc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bcc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bd66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bda3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bd45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000be9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bea8`

## pseudocode

```c
__int64 __fastcall RegRow::Create(
        struct RegTable *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        bool a6,
        struct RegRow **a7)
{
  unsigned __int16 *v9; // rax
  unsigned __int64 v10; // rdi
  unsigned __int16 *v11; // r12
  struct tagPROPVARIANT *v12; // rax
  struct tagPROPVARIANT *v13; // rbp
  int v14; // ebx
  int v15; // edx
  struct RegRow **v16; // rsi
  void *v17; // rdi
  unsigned __int16 *v18; // r15
  LPVOID v19; // rax
  struct RegRow *v20; // rax
  int *v21; // rax
  int *v22; // r15
  unsigned __int16 *v23; // rdi
  RegistryRegRow *v24; // rax
  struct RegRow *v25; // rax
  InMemoryRegRow *v26; // rax
  bool v27; // r9
  struct RegRow *v28; // rax
  unsigned int v30; // [rsp+28h] [rbp-80h]
  LPVOID pv[9]; // [rsp+60h] [rbp-48h] BYREF

  v9 = WStringCopy(a4);
  v10 = *((unsigned int *)a1 + 136);
  v11 = v9;
  v12 = (struct tagPROPVARIANT *)CoTaskMemAlloc(saturated_mul(v10, 0x18u));
  v13 = v12;
  if ( !v11 || !v12 )
  {
    v14 = -2147024882;
    goto LABEL_38;
  }
  v14 = 0;
  memset_0(v12, 0, 24 * v10);
  if ( (_DWORD)v10 )
  {
    LOBYTE(v15) = 0;
    memset_0(v13, v15, 24 * v10);
  }
  if ( a6 )
  {
    v26 = (InMemoryRegRow *)CoTaskMemAlloc(0x78u);
    if ( v26 )
    {
      v28 = InMemoryRegRow::InMemoryRegRow(v26, a1, v11, v27, v13, v30);
      v16 = a7;
      *a7 = v28;
      if ( v28 )
        goto LABEL_32;
    }
    else
    {
      *a7 = 0;
    }
    goto LABEL_25;
  }
  v16 = a7;
  if ( !a3 )
  {
    v14 = -2147024809;
    goto LABEL_28;
  }
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl'::`2'::impl) )
  {
    v21 = (int *)CoTaskMemAlloc(saturated_mul(v10, 4u));
    v22 = v21;
    if ( !v21 )
    {
      v14 = -2147024882;
      goto LABEL_28;
    }
    memset_0(v21, 0, 4 * v10);
    v23 = WStringCopy(*((const unsigned __int16 **)a1 + 70));
    if ( v23 )
    {
      v24 = (RegistryRegRow *)CoTaskMemAlloc(0x90u);
      if ( v24 )
      {
        v25 = RegistryRegRow::RegistryRegRow(
                v24,
                a1,
                *((HKEY *)a1 + 1),
                v23,
                a2,
                a3,
                v11,
                *((_BYTE *)a1 + 16),
                a5,
                v13,
                v22);
        *a7 = v25;
        if ( v25 )
          goto LABEL_32;
      }
      else
      {
        *a7 = 0;
      }
      CoTaskMemFree(v22);
      CoTaskMemFree(v23);
    }
LABEL_25:
    v14 = -2147024882;
LABEL_39:
    CoTaskMemFree(v11);
LABEL_40:
    if ( v13 )
      CoTaskMemFree(v13);
    return (unsigned int)v14;
  }
  make_unique_atomic_bool_array(pv, (unsigned int)v10);
  v17 = pv[0];
  if ( pv[0] )
  {
    v18 = WStringCopy(*((const unsigned __int16 **)a1 + 70));
    if ( v18 )
    {
      v19 = CoTaskMemAlloc(0x90u);
      if ( v19 )
      {
        v20 = (struct RegRow *)RegistryRegRow::RegistryRegRow(
                                 (__int64)v19,
                                 a1,
                                 *((_QWORD *)a1 + 1),
                                 (__int64)v18,
                                 a2,
                                 (__int64)a3,
                                 v11,
                                 *((_BYTE *)a1 + 16),
                                 a5,
                                 (__int64)v13,
                                 pv);
        v17 = pv[0];
        *a7 = v20;
        if ( v20 )
          goto LABEL_16;
      }
      else
      {
        *a7 = 0;
      }
      CoTaskMemFree(v18);
    }
  }
  v14 = -2147024882;
LABEL_16:
  if ( v17 )
    CoTaskMemFree(v17);
LABEL_28:
  if ( v14 < 0 )
    goto LABEL_39;
LABEL_32:
  if ( a5 )
    v14 = (*(__int64 (__fastcall **)(struct RegRow *))(*(_QWORD *)*v16 + 80LL))(*v16);
  if ( v14 < 0 )
  {
LABEL_38:
    if ( !v11 )
      goto LABEL_40;
    goto LABEL_39;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000bbc8  mov     [rsp+arg_0], rbx
0x18000bbcd  mov     [rsp+arg_10], r8
0x18000bbd2  mov     [rsp+arg_8], edx
0x18000bbd6  push    rbp
0x18000bbd7  push    rsi
0x18000bbd8  push    rdi
0x18000bbd9  push    r12
0x18000bbdb  push    r13
0x18000bbdd  push    r14
0x18000bbdf  push    r15
0x18000bbe1  sub     rsp, 70h
0x18000bbe5  mov     r14, rcx
0x18000bbe8  mov     r15, r8
0x18000bbeb  mov     rcx, r9; Src
0x18000bbee  call    ?WStringCopy@@YAPEAGPEBG@Z; WStringCopy(ushort const *)
0x18000bbf3  mov     edi, [r14+220h]
0x18000bbfa  mov     r12, rax
0x18000bbfd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bc04  mov     eax, 18h
0x18000bc09  mul     rdi
0x18000bc0c  cmovb   rax, rcx
0x18000bc10  mov     rcx, rax; cb
0x18000bc13  call    cs:__imp_CoTaskMemAlloc
0x18000bc19  mov     rbp, rax
0x18000bc1c  test    r12, r12
0x18000bc1f  jz      loc_18000BE8D
0x18000bc25  test    rax, rax
0x18000bc28  jz      loc_18000BE8D
0x18000bc2e  lea     rsi, [rdi+rdi*2]
0x18000bc32  xor     edx, edx; Val
0x18000bc34  shl     rsi, 3
0x18000bc38  mov     rcx, rax; void *
0x18000bc3b  mov     r8, rsi; Size
0x18000bc3e  xor     ebx, ebx
0x18000bc40  call    memset_0
0x18000bc45  test    edi, edi
0x18000bc47  jz      short loc_18000BC56
0x18000bc49  mov     r8, rsi; Size
0x18000bc4c  xor     dl, dl; Val
0x18000bc4e  mov     rcx, rbp; void *
0x18000bc51  call    memset_0
0x18000bc56  mov     r13b, [rsp+0A8h+arg_20]
0x18000bc5e  cmp     [rsp+0A8h+arg_28], bl
0x18000bc65  jnz     loc_18000BE2C
0x18000bc6b  mov     rsi, [rsp+0A8h+arg_30]
0x18000bc73  test    r15, r15
0x18000bc76  jz      loc_18000BE21
0x18000bc7c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl(void)'::`2'::impl
0x18000bc83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(void)
0x18000bc88  test    al, al
0x18000bc8a  jz      loc_18000BD50
0x18000bc90  mov     edx, edi
0x18000bc92  lea     rcx, [rsp+0A8h+pv]
0x18000bc97  call    ?make_unique_atomic_bool_array@@YA?AV?$unique_any_array_ptr@U?$atomic@_N@std@@U?$default_delete@$$BY0A@U?$atomic@_N@std@@@wistd@@Uempty_deleter@wil@@_K@wil@@K@Z; make_unique_atomic_bool_array(ulong)
0x18000bc9c  mov     rdi, [rsp+0A8h+pv]
0x18000bca1  test    rdi, rdi
0x18000bca4  jz      loc_18000BD34
0x18000bcaa  mov     rcx, [r14+230h]; Src
0x18000bcb1  call    ?WStringCopy@@YAPEAGPEBG@Z; WStringCopy(ushort const *)
0x18000bcb6  mov     r15, rax
0x18000bcb9  test    rax, rax
0x18000bcbc  jz      short loc_18000BD34
0x18000bcbe  mov     ecx, 90h; cb
0x18000bcc3  call    cs:__imp_CoTaskMemAlloc
0x18000bcc9  test    rax, rax
0x18000bccc  jz      short loc_18000BD28
0x18000bcce  mov     r8, [r14+8]; int
0x18000bcd2  lea     rcx, [rsp+0A8h+pv]
0x18000bcd7  mov     [rsp+0A8h+var_58], rcx; __int64
0x18000bcdc  mov     r9, r15; int
0x18000bcdf  mov     cl, [r14+10h]
0x18000bce3  mov     rdx, r14; int
0x18000bce6  mov     [rsp+0A8h+var_60], rbp; __int64
0x18000bceb  mov     [rsp+0A8h+var_68], r13b; bool
0x18000bcf0  mov     [rsp+0A8h+var_70], cl; char
0x18000bcf4  mov     rcx, [rsp+0A8h+arg_10]
0x18000bcfc  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x18000bd01  mov     [rsp+0A8h+var_80], rcx; __int64
0x18000bd06  mov     ecx, [rsp+0A8h+arg_8]
0x18000bd0d  mov     dword ptr [rsp+0A8h+var_88], ecx; int
0x18000bd11  mov     rcx, rax; int
0x18000bd14  call    ??0RegistryRegRow@@QEAA@PEAVRegTable@@PEAUHKEY__@@PEAGK2PEBG_N4PEAUtagPROPVARIANT@@$$QEAV?$unique_any_array_ptr@U?$atomic@_N@std@@U?$default_delete@$$BY0A@U?$atomic@_N@std@@@wistd@@Uempty_deleter@wil@@_K@wil@@@Z; RegistryRegRow::RegistryRegRow(RegTable *,HKEY__ *,ushort *,ulong,ushort *,ushort const *,bool,bool,tagPROPVARIANT *,wil::unique_any_array_ptr<std::atomic<bool>,wistd::default_delete<std::atomic<bool> [0]>,wil::empty_deleter,unsigned __int64> &&)
0x18000bd19  mov     rdi, [rsp+0A8h+pv]
0x18000bd1e  mov     [rsi], rax
0x18000bd21  test    rax, rax
0x18000bd24  jnz     short loc_18000BD39
0x18000bd26  jmp     short loc_18000BD2B
0x18000bd28  mov     [rsi], rbx
0x18000bd2b  mov     rcx, r15; pv
0x18000bd2e  call    cs:__imp_CoTaskMemFree
0x18000bd34  mov     ebx, 8007000Eh
0x18000bd39  test    rdi, rdi
0x18000bd3c  jz      loc_18000BE26
0x18000bd42  mov     rcx, rdi; pv
0x18000bd45  call    cs:__imp_CoTaskMemFree
0x18000bd4b  jmp     loc_18000BE26
0x18000bd50  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000bd57  mov     eax, 4
0x18000bd5c  mul     rdi
0x18000bd5f  cmovb   rax, rcx
0x18000bd63  mov     rcx, rax; cb
0x18000bd66  call    cs:__imp_CoTaskMemAlloc
0x18000bd6c  mov     r15, rax
0x18000bd6f  test    rax, rax
0x18000bd72  jz      loc_18000BE1A
0x18000bd78  lea     r8, ds:0[rdi*4]; Size
0x18000bd80  xor     edx, edx; Val
0x18000bd82  mov     rcx, rax; void *
0x18000bd85  call    memset_0
0x18000bd8a  mov     rcx, [r14+230h]; Src
0x18000bd91  call    ?WStringCopy@@YAPEAGPEBG@Z; WStringCopy(ushort const *)
0x18000bd96  mov     rdi, rax
0x18000bd99  test    rax, rax
0x18000bd9c  jz      short loc_18000BE13
0x18000bd9e  mov     ecx, 90h; cb
0x18000bda3  call    cs:__imp_CoTaskMemAlloc
0x18000bda9  test    rax, rax
0x18000bdac  jz      short loc_18000BDFE
0x18000bdae  mov     cl, [r14+10h]
0x18000bdb2  mov     r9, rdi; unsigned __int16 *
0x18000bdb5  mov     r8, [r14+8]; HKEY
0x18000bdb9  mov     rdx, r14; struct RegTable *
0x18000bdbc  mov     [rsp+0A8h+var_58], r15; int *
0x18000bdc1  mov     [rsp+0A8h+var_60], rbp; struct tagPROPVARIANT *
0x18000bdc6  mov     [rsp+0A8h+var_68], r13b; bool
0x18000bdcb  mov     [rsp+0A8h+var_70], cl; bool
0x18000bdcf  mov     rcx, [rsp+0A8h+arg_10]
0x18000bdd7  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x18000bddc  mov     [rsp+0A8h+var_80], rcx; unsigned __int16 *
0x18000bde1  mov     ecx, [rsp+0A8h+arg_8]
0x18000bde8  mov     dword ptr [rsp+0A8h+var_88], ecx; unsigned int
0x18000bdec  mov     rcx, rax; this
0x18000bdef  call    ??0RegistryRegRow@@QEAA@PEAVRegTable@@PEAUHKEY__@@PEAGK2PEBG_N4PEAUtagPROPVARIANT@@PEAH@Z; RegistryRegRow::RegistryRegRow(RegTable *,HKEY__ *,ushort *,ulong,ushort *,ushort const *,bool,bool,tagPROPVARIANT *,int *)
0x18000bdf4  mov     [rsi], rax
0x18000bdf7  test    rax, rax
0x18000bdfa  jz      short loc_18000BE01
0x18000bdfc  jmp     short loc_18000BE5F
0x18000bdfe  mov     [rsi], rbx
0x18000be01  mov     rcx, r15; pv
0x18000be04  call    cs:__imp_CoTaskMemFree
0x18000be0a  mov     rcx, rdi; pv
0x18000be0d  call    cs:__imp_CoTaskMemFree
0x18000be13  mov     ebx, 8007000Eh
0x18000be18  jmp     short loc_18000BE97
0x18000be1a  mov     ebx, 8007000Eh
0x18000be1f  jmp     short loc_18000BE26
0x18000be21  mov     ebx, 80070057h
0x18000be26  test    ebx, ebx
0x18000be28  jns     short loc_18000BE5F
0x18000be2a  jmp     short loc_18000BE97
0x18000be2c  mov     ecx, 78h ; 'x'; cb
0x18000be31  call    cs:__imp_CoTaskMemAlloc
0x18000be37  test    rax, rax
0x18000be3a  jz      short loc_18000BE80
0x18000be3c  mov     r8, r12; unsigned __int16 *
0x18000be3f  mov     [rsp+0A8h+var_88], rbp; struct tagPROPVARIANT *
0x18000be44  mov     rdx, r14; struct RegTable *
0x18000be47  mov     rcx, rax; this
0x18000be4a  call    ??0InMemoryRegRow@@QEAA@PEAVRegTable@@PEBG_NPEAUtagPROPVARIANT@@K@Z; InMemoryRegRow::InMemoryRegRow(RegTable *,ushort const *,bool,tagPROPVARIANT *,ulong)
0x18000be4f  mov     rsi, [rsp+0A8h+arg_30]
0x18000be57  mov     [rsi], rax
0x18000be5a  test    rax, rax
0x18000be5d  jz      short loc_18000BE13
0x18000be5f  mov     edx, 1
0x18000be64  cmp     r13b, dl
0x18000be67  jnz     short loc_18000BE7A
0x18000be69  mov     rcx, [rsi]
0x18000be6c  mov     rax, [rcx]
0x18000be6f  mov     rax, [rax+50h]
0x18000be73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be78  mov     ebx, eax
0x18000be7a  test    ebx, ebx
0x18000be7c  js      short loc_18000BE92
0x18000be7e  jmp     short loc_18000BEAE
0x18000be80  mov     rax, [rsp+0A8h+arg_30]
0x18000be88  mov     [rax], rbx
0x18000be8b  jmp     short loc_18000BE13
0x18000be8d  mov     ebx, 8007000Eh
0x18000be92  test    r12, r12
0x18000be95  jz      short loc_18000BEA0
0x18000be97  mov     rcx, r12; pv
0x18000be9a  call    cs:__imp_CoTaskMemFree
0x18000bea0  test    rbp, rbp
0x18000bea3  jz      short loc_18000BEAE
0x18000bea5  mov     rcx, rbp; pv
0x18000bea8  call    cs:__imp_CoTaskMemFree
0x18000beae  mov     eax, ebx
0x18000beb0  mov     rbx, [rsp+0A8h+arg_0]
0x18000beb8  add     rsp, 70h
0x18000bebc  pop     r15
0x18000bebe  pop     r14
0x18000bec0  pop     r13
0x18000bec2  pop     r12
0x18000bec4  pop     rdi
0x18000bec5  pop     rsi
0x18000bec6  pop     rbp
0x18000bec7  retn
```
