# CSimpleTable4ui::CloneCursor(ISimpleTableRead * *)

- ea: `0x1800394d0`
- end: `0x180039847`
- name: `?CloneCursor@CSimpleTable4ui@@UEAAJPEAPEAUISimpleTableRead@@@Z`
- size: `887`
- prototype: `__int64 __fastcall(CSimpleTable4ui *__hidden this, struct ISimpleTableRead **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002430`
- `0x1800071e0`
- `0x180008a7c`
- `0x180008dc4`
- `0x1800394d0`
- `0x180054a98`
- `0x18005550e`
- `0x18005551a`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003952a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800395db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039695`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800396d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800397c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003952a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800395db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039695`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800396d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039718`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180039783`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800397c8`

## pseudocode

```c
__int64 __fastcall CSimpleTable4ui::CloneCursor(CSimpleTable4ui *this, struct ISimpleTableRead **a2)
{
  int inited; // ebx
  struct IComponentRecords *v5; // rbx
  struct IComponentRecords *v6; // rax
  __int64 v7; // rsi
  _OWORD *v8; // rax
  void *v9; // rax
  void *v10; // rax
  void *v11; // rax
  void *v12; // rax
  __int64 i; // rbx
  void *v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rax
  void *v17; // rax
  struct IComponentRecords *v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = 0;
  if ( *((_DWORD *)this + 25) != 1 )
  {
    v5 = (struct IComponentRecords *)*((_QWORD *)this + 33);
LABEL_5:
    v6 = (struct IComponentRecords *)CoTaskMemAlloc(0x148u);
    v19 = v6;
    if ( v6 )
      v7 = CSimpleTable4ui::CSimpleTable4ui(
             (__int64)v6,
             *((_QWORD *)this + 10),
             *((_DWORD *)this + 22),
             (__int64)v5,
             *((_DWORD *)this + 24),
             *((_DWORD *)this + 25),
             (CSimpleTable4ui *)((char *)this + 292),
             (CSimpleTable4ui *)((char *)this + 276));
    else
      v7 = 0;
    if ( !v7 )
      return (unsigned int)-2147024882;
    inited = CSimpleDataTableCursor::InitCache((CSimpleDataTableCursor *)(v7 + 24));
    if ( inited < 0
      || (inited = CSimpleDataTableCursor::InternalCloneCursor(
                     (CSimpleTable4ui *)((char *)this + 24),
                     (struct CSimpleDataTableCursor *)(v7 + 24)),
          inited < 0) )
    {
LABEL_28:
      CSimpleTable4ui::`scalar deleting destructor'((CSimpleTable4ui *)v7);
      return (unsigned int)inited;
    }
    *(_DWORD *)(v7 + 176) = *((_DWORD *)this + 44);
    if ( *((_DWORD *)this + 44) )
    {
      v8 = CoTaskMemAlloc(0x10u);
      *(_QWORD *)(v7 + 104) = v8;
      if ( !v8 )
        goto LABEL_14;
      *v8 = *(_OWORD *)*((_QWORD *)this + 13);
      v9 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 44), 4u));
      *(_QWORD *)(v7 + 184) = v9;
      if ( !v9 )
        goto LABEL_14;
      memcpy_0(v9, *((const void **)this + 23), 4LL * *((unsigned int *)this + 44));
      v10 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 44), 4u));
      *(_QWORD *)(v7 + 208) = v10;
      if ( !v10 )
        goto LABEL_14;
      memcpy_0(v10, *((const void **)this + 26), 4LL * *((unsigned int *)this + 44));
      v11 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 44), 2u));
      *(_QWORD *)(v7 + 216) = v11;
      if ( !v11 )
        goto LABEL_14;
      memcpy_0(v11, *((const void **)this + 27), 2LL * *((unsigned int *)this + 44));
      v12 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 44), 8u));
      *(_QWORD *)(v7 + 200) = v12;
      if ( !v12 )
        goto LABEL_14;
      memset_0(v12, 0, 8LL * *((unsigned int *)this + 44));
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 44); i = (unsigned int)(i + 1) )
      {
        *(_QWORD *)(*(_QWORD *)(v7 + 200) + 8 * i) = CoTaskMemAlloc(*(unsigned int *)(*((_QWORD *)this + 26) + 4 * i));
        v14 = *(void **)(*(_QWORD *)(v7 + 200) + 8 * i);
        if ( !v14 )
          goto LABEL_14;
        memcpy_0(
          v14,
          *(const void **)(*((_QWORD *)this + 25) + 8 * i),
          *(unsigned int *)(*((_QWORD *)this + 26) + 4 * i));
      }
    }
    *(_DWORD *)(v7 + 224) = *((_DWORD *)this + 56);
    v15 = *((unsigned int *)this + 56);
    if ( !(_DWORD)v15 )
      goto LABEL_27;
    v16 = CoTaskMemAlloc(saturated_mul(v15, 4u));
    *(_QWORD *)(v7 + 232) = v16;
    if ( v16 )
    {
      memcpy_0(v16, *((const void **)this + 29), 4LL * *((unsigned int *)this + 56));
      v17 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 56), 2u));
      *(_QWORD *)(v7 + 240) = v17;
      if ( v17 )
      {
        memcpy_0(v17, *((const void **)this + 30), 2LL * *((unsigned int *)this + 56));
LABEL_27:
        *(_OWORD *)(v7 + 248) = *(_OWORD *)((char *)this + 248);
        inited = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ISimpleTableRead **))v7)(
                   v7,
                   &IID_ISimpleTableRead,
                   a2);
        if ( inited >= 0 )
          return (unsigned int)inited;
        goto LABEL_28;
      }
    }
LABEL_14:
    inited = -2147024882;
    goto LABEL_28;
  }
  inited = GetReadICR((*((_DWORD *)this + 24) >> 4) & 1, &v19);
  if ( inited >= 0 )
  {
    v5 = v19;
    goto LABEL_5;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800394d0  mov     rax, rsp
0x1800394d3  mov     [rax+10h], rbx
0x1800394d7  mov     [rax+18h], rbp
0x1800394db  push    rsi
0x1800394dc  push    rdi
0x1800394dd  push    r12
0x1800394df  push    r14
0x1800394e1  push    r15
0x1800394e3  sub     rsp, 40h
0x1800394e7  mov     r14, rdx
0x1800394ea  mov     rdi, rcx
0x1800394ed  mov     qword ptr [rax+8], 0
0x1800394f5  cmp     dword ptr [rcx+64h], 1
0x1800394f9  jnz     short loc_18003951E
0x1800394fb  mov     ecx, [rcx+60h]
0x1800394fe  shr     ecx, 4
0x180039501  and     ecx, 1; int
0x180039504  lea     rdx, [rax+8]; struct IComponentRecords **
0x180039508  call    ?GetReadICR@@YAJHPEAPEAUIComponentRecords@@@Z; GetReadICR(int,IComponentRecords * *)
0x18003950d  mov     ebx, eax
0x18003950f  test    eax, eax
0x180039511  js      loc_18003982C
0x180039517  mov     rbx, [rsp+68h+arg_0]
0x18003951c  jmp     short loc_180039525
0x18003951e  mov     rbx, [rcx+108h]
0x180039525  mov     ecx, 148h; cb
0x18003952a  call    cs:__imp_CoTaskMemAlloc
0x180039530  mov     [rsp+68h+arg_0], rax
0x180039535  test    rax, rax
0x180039538  jz      short loc_180039578
0x18003953a  lea     rcx, [rdi+114h]
0x180039541  lea     rdx, [rdi+124h]
0x180039548  mov     [rsp+68h+var_30], rcx
0x18003954d  mov     [rsp+68h+var_38], rdx
0x180039552  mov     ecx, [rdi+64h]
0x180039555  mov     [rsp+68h+var_40], ecx
0x180039559  mov     ecx, [rdi+60h]
0x18003955c  mov     [rsp+68h+var_48], ecx
0x180039560  mov     r9, rbx
0x180039563  mov     r8d, [rdi+58h]
0x180039567  mov     rdx, [rdi+50h]
0x18003956b  mov     rcx, rax
0x18003956e  call    ??0CSimpleTable4ui@@QEAA@_JKPEAUIComponentRecords@@KW4ESchemaType@@AEBU_GUID@@3@Z; CSimpleTable4ui::CSimpleTable4ui(__int64,ulong,IComponentRecords *,ulong,ESchemaType,_GUID const &,_GUID const &)
0x180039573  mov     rsi, rax
0x180039576  jmp     short loc_18003957A
0x180039578  xor     esi, esi
0x18003957a  test    rsi, rsi
0x18003957d  jnz     short loc_180039589
0x18003957f  mov     ebx, 8007000Eh
0x180039584  jmp     loc_18003982C
0x180039589  lea     rcx, [rsi+18h]; this
0x18003958d  call    ?InitCache@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InitCache(void)
0x180039592  mov     ebx, eax
0x180039594  test    eax, eax
0x180039596  js      loc_180039824
0x18003959c  lea     rcx, [rdi+18h]; this
0x1800395a0  lea     rdx, [rsi+18h]; struct CSimpleDataTableCursor *
0x1800395a4  call    ?InternalCloneCursor@CSimpleDataTableCursor@@QEAAJPEAV1@@Z; CSimpleDataTableCursor::InternalCloneCursor(CSimpleDataTableCursor *)
0x1800395a9  mov     ebx, eax
0x1800395ab  test    eax, eax
0x1800395ad  js      loc_180039824
0x1800395b3  mov     eax, [rdi+0B0h]
0x1800395b9  mov     [rsi+0B0h], eax
0x1800395bf  mov     r12d, 4
0x1800395c5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800395c9  cmp     dword ptr [rdi+0B0h], 0
0x1800395d0  jz      loc_18003975C
0x1800395d6  lea     ecx, [r12+0Ch]; cb
0x1800395db  call    cs:__imp_CoTaskMemAlloc
0x1800395e1  mov     rcx, rax
0x1800395e4  mov     [rsi+68h], rax
0x1800395e8  test    rax, rax
0x1800395eb  jnz     short loc_1800395F7
0x1800395ed  mov     ebx, 8007000Eh
0x1800395f2  jmp     loc_180039824
0x1800395f7  mov     rax, [rdi+68h]
0x1800395fb  movups  xmm0, xmmword ptr [rax]
0x1800395fe  movdqu  xmmword ptr [rcx], xmm0
0x180039602  mov     ecx, [rdi+0B0h]
0x180039608  mov     rax, r12
0x18003960b  mul     rcx
0x18003960e  cmovb   rax, r15
0x180039612  mov     rcx, rax; cb
0x180039615  call    cs:__imp_CoTaskMemAlloc
0x18003961b  mov     [rsi+0B8h], rax
0x180039622  test    rax, rax
0x180039625  jz      short loc_1800395ED
0x180039627  mov     r8d, [rdi+0B0h]
0x18003962e  shl     r8, 2; Size
0x180039632  mov     rdx, [rdi+0B8h]; Src
0x180039639  mov     rcx, rax; void *
0x18003963c  call    memcpy_0
0x180039641  mov     ecx, [rdi+0B0h]
0x180039647  mov     rax, r12
0x18003964a  mul     rcx
0x18003964d  cmovb   rax, r15
0x180039651  mov     rcx, rax; cb
0x180039654  call    cs:__imp_CoTaskMemAlloc
0x18003965a  mov     [rsi+0D0h], rax
0x180039661  test    rax, rax
0x180039664  jz      short loc_1800395ED
0x180039666  mov     r8d, [rdi+0B0h]
0x18003966d  shl     r8, 2; Size
0x180039671  mov     rdx, [rdi+0D0h]; Src
0x180039678  mov     rcx, rax; void *
0x18003967b  call    memcpy_0
0x180039680  mov     ecx, [rdi+0B0h]
0x180039686  mov     eax, 2
0x18003968b  mul     rcx
0x18003968e  cmovb   rax, r15
0x180039692  mov     rcx, rax; cb
0x180039695  call    cs:__imp_CoTaskMemAlloc
0x18003969b  mov     [rsi+0D8h], rax
0x1800396a2  test    rax, rax
0x1800396a5  jz      loc_1800395ED
0x1800396ab  mov     r8d, [rdi+0B0h]
0x1800396b2  add     r8, r8; Size
0x1800396b5  mov     rdx, [rdi+0D8h]; Src
0x1800396bc  mov     rcx, rax; void *
0x1800396bf  call    memcpy_0
0x1800396c4  mov     ecx, [rdi+0B0h]
0x1800396ca  mov     eax, 8
0x1800396cf  mul     rcx
0x1800396d2  cmovb   rax, r15
0x1800396d6  mov     rcx, rax; cb
0x1800396d9  call    cs:__imp_CoTaskMemAlloc
0x1800396df  mov     [rsi+0C8h], rax
0x1800396e6  test    rax, rax
0x1800396e9  jz      loc_1800395ED
0x1800396ef  mov     r8d, [rdi+0B0h]
0x1800396f6  shl     r8, 3; Size
0x1800396fa  xor     edx, edx; Val
0x1800396fc  mov     rcx, rax; void *
0x1800396ff  call    memset_0
0x180039704  xor     ebx, ebx
0x180039706  cmp     ebx, [rdi+0B0h]
0x18003970c  jnb     short loc_18003975C
0x18003970e  mov     rax, [rdi+0D0h]
0x180039715  mov     ecx, [rax+rbx*4]; cb
0x180039718  call    cs:__imp_CoTaskMemAlloc
0x18003971e  mov     rcx, [rsi+0C8h]
0x180039725  mov     [rcx+rbx*8], rax
0x180039729  mov     rax, [rsi+0C8h]
0x180039730  mov     rcx, [rax+rbx*8]; void *
0x180039734  test    rcx, rcx
0x180039737  jz      loc_1800395ED
0x18003973d  mov     rax, [rdi+0D0h]
0x180039744  mov     r8d, [rax+rbx*4]; Size
0x180039748  mov     rdx, [rdi+0C8h]
0x18003974f  mov     rdx, [rdx+rbx*8]; Src
0x180039753  call    memcpy_0
0x180039758  inc     ebx
0x18003975a  jmp     short loc_180039706
0x18003975c  mov     ecx, [rdi+0E0h]
0x180039762  mov     [rsi+0E0h], ecx
0x180039768  mov     ecx, [rdi+0E0h]
0x18003976e  test    ecx, ecx
0x180039770  jz      loc_1800397F7
0x180039776  mov     rax, r12
0x180039779  mul     rcx
0x18003977c  cmovb   rax, r15
0x180039780  mov     rcx, rax; cb
0x180039783  call    cs:__imp_CoTaskMemAlloc
0x180039789  mov     [rsi+0E8h], rax
0x180039790  test    rax, rax
0x180039793  jz      loc_1800395ED
0x180039799  mov     r8d, [rdi+0E0h]
0x1800397a0  shl     r8, 2; Size
0x1800397a4  mov     rdx, [rdi+0E8h]; Src
0x1800397ab  mov     rcx, rax; void *
0x1800397ae  call    memcpy_0
0x1800397b3  mov     ecx, [rdi+0E0h]
0x1800397b9  mov     eax, 2
0x1800397be  mul     rcx
0x1800397c1  cmovb   rax, r15
0x1800397c5  mov     rcx, rax; cb
0x1800397c8  call    cs:__imp_CoTaskMemAlloc
0x1800397ce  mov     [rsi+0F0h], rax
0x1800397d5  test    rax, rax
0x1800397d8  jz      loc_1800395ED
0x1800397de  mov     r8d, [rdi+0E0h]
0x1800397e5  add     r8, r8; Size
0x1800397e8  mov     rdx, [rdi+0F0h]; Src
0x1800397ef  mov     rcx, rax; void *
0x1800397f2  call    memcpy_0
0x1800397f7  movups  xmm0, xmmword ptr [rdi+0F8h]
0x1800397fe  movdqu  xmmword ptr [rsi+0F8h], xmm0
0x180039806  mov     rax, [rsi]
0x180039809  mov     r8, r14
0x18003980c  lea     rdx, IID_ISimpleTableRead
0x180039813  mov     rcx, rsi
0x180039816  mov     rax, [rax]
0x180039819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003981e  mov     ebx, eax
0x180039820  test    eax, eax
0x180039822  jns     short loc_18003982C
0x180039824  mov     rcx, rsi; this
0x180039827  call    ??_GCSimpleTable4ui@@QEAAPEAXI@Z; CSimpleTable4ui::`scalar deleting destructor'(uint)
0x18003982c  mov     eax, ebx
0x18003982e  lea     r11, [rsp+68h+var_28]
0x180039833  mov     rbx, [r11+38h]
0x180039837  mov     rbp, [r11+40h]
0x18003983b  mov     rsp, r11
0x18003983e  pop     r15
0x180039840  pop     r14
0x180039842  pop     r12
0x180039844  pop     rdi
0x180039845  pop     rsi
0x180039846  retn
```
