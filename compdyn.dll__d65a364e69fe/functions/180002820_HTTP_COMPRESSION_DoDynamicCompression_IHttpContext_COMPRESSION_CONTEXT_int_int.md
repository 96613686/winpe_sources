# HTTP_COMPRESSION::DoDynamicCompression(IHttpContext *,COMPRESSION_CONTEXT *,int,int *)

- ea: `0x180002820`
- end: `0x180002d24`
- name: `?DoDynamicCompression@HTTP_COMPRESSION@@CAJPEAVIHttpContext@@PEAVCOMPRESSION_CONTEXT@@HPEAH@Z`
- size: `1284`
- prototype: `static int(struct IHttpContext *, struct COMPRESSION_CONTEXT *, int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001a60`
- `0x1800035b0`

## callees

- `0x180002820`
- `0x180002d30`
- `0x180002ef0`
- `0x1800068b0`
- `0x1800069c4`
- `0x180006af4`
- `0x180008010`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800028d5`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800028d5`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800029ac`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x1800029ac`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::DoDynamicCompression(
        struct IHttpContext *a1,
        struct COMPRESSION_CONTEXT *a2,
        int a3,
        int *a4)
{
  __int64 v6; // rsi
  char *v7; // r15
  _QWORD *v8; // rdx
  __int64 v9; // rax
  ALLOC_CACHE_HANDLER *v10; // rcx
  __int64 result; // rax
  unsigned int v12; // edi
  unsigned int v13; // r14d
  BOOL v14; // r12d
  unsigned int v15; // edi
  _QWORD *v16; // rax
  _QWORD *v17; // rsi
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 (__fastcall *v21)(_QWORD, unsigned __int8 *, _QWORD, _QWORD *, int, unsigned int *, int *, int, int); // r10
  int v22; // edx
  unsigned __int8 *BytePtr; // rax
  int v24; // ecx
  __int64 (__fastcall *v25)(_QWORD, unsigned __int8 *, _QWORD, _QWORD *, int, unsigned int *, int *, int); // r10
  unsigned __int8 *v26; // rax
  int v27; // r13d
  unsigned int v28; // r14d
  _DWORD *v29; // rdi
  unsigned int v30; // r8d
  int v31; // edx
  unsigned int v32; // esi
  __int64 v33; // rcx
  int (__fastcall ***v34)(_QWORD, GUID **); // rax
  int (__fastcall **v35)(_QWORD, GUID **); // rcx
  struct IHttpTraceContext *v36; // rax
  const struct _GUID *v37; // rdx
  int (__fastcall ***v38)(_QWORD, GUID **); // rax
  struct IHttpTraceContext *v39; // rax
  const struct _GUID *v40; // rdx
  unsigned int v41; // [rsp+50h] [rbp-39h] BYREF
  int v42; // [rsp+54h] [rbp-35h] BYREF
  unsigned int v43; // [rsp+58h] [rbp-31h]
  GUID *v44; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v45[20]; // [rsp+68h] [rbp-21h]
  int v46; // [rsp+7Ch] [rbp-Dh]
  int v47; // [rsp+80h] [rbp-9h]
  __int64 v48; // [rsp+88h] [rbp-1h]
  __int64 v49; // [rsp+90h] [rbp+7h]
  unsigned int v51; // [rsp+F8h] [rbp+6Fh]

  v47 = 2 - (*((_DWORD *)a2 + 23) != 0);
  v48 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 8LL))(v48);
  v6 = v49;
  if ( a4 )
    *a4 = 0;
  v7 = (char *)a2 + 144;
  while ( 1 )
  {
    v8 = *(_QWORD **)v7;
    if ( *(char **)v7 == v7 )
      break;
    if ( (char *)v8[1] != v7 )
      goto LABEL_83;
    v9 = *v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_83;
    v10 = (ALLOC_CACHE_HANDLER *)COMPRESSION_BUFFER::allocHandler;
    *(_QWORD *)v7 = v9;
    *(_QWORD *)(v9 + 8) = v7;
    ALLOC_CACHE_HANDLER::Free(v10, v8 - 500);
  }
  if ( *((_DWORD *)a2 + 40) && *((_DWORD *)a2 + 41) )
    return 0;
  result = COMPRESSION_CONTEXT::SetupCurrentULChunk(a2);
  if ( (int)result < 0 )
    return result;
  v12 = 0;
  v51 = 0;
  v13 = 0;
  v14 = 0;
LABEL_12:
  if ( a3 && (v13 > HTTP_COMPRESSION::sm_dwDynamicCompressionBufferLimit || *(_WORD *)(v6 + 536) >= 0xFFFCu) )
  {
LABEL_65:
    v34 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
    v44 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v35 = *v34;
    *(_OWORD *)v45 = 0;
    if ( (*v35)(v34, &v44) >= 0
      && *(_DWORD *)&v45[8]
      && *(_DWORD *)&v45[4] >= 5u
      && (*(_DWORD *)v45 == 64 || (v45[0] & 0x40) != 0) )
    {
      v36 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      IISCompressionEvents::DYNAMIC_COMPRESSION_DO::RaiseEvent(v36, v37, v12, v13);
    }
    if ( v14 )
    {
      result = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 144LL))(
                 v48,
                 1,
                 1,
                 0,
                 0);
      if ( (int)result >= 0 )
      {
        *a4 = 1;
        return 0;
      }
      return result;
    }
    if ( !*((_DWORD *)a2 + 23) )
    {
      v38 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
      v44 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      *(_OWORD *)v45 = 0;
      if ( (**v38)(v38, &v44) >= 0
        && *(_DWORD *)&v45[8]
        && *(_DWORD *)&v45[4] >= 4u
        && (*(_DWORD *)v45 == 64 || (v45[0] & 0x40) != 0) )
      {
        v39 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
        IISCompressionEvents::DYNAMIC_COMPRESSION_END::RaiseEvent(v39, v40);
      }
    }
    return 0;
  }
  if ( !*((_DWORD *)a2 + 4) || (result = COMPRESSION_CONTEXT::ProcessEncodedChunkHeader(a2), (int)result >= 0) )
  {
    v15 = 0;
    if ( *((_DWORD *)a2 + 24) < *((_DWORD *)a2 + 22) )
    {
      v15 = *((_DWORD *)a2 + 28)
          ? *(_DWORD *)(*((_QWORD *)a2 + 13) + 16LL)
          : *((_DWORD *)a2 + 35) - *((_DWORD *)a2 + 34);
      if ( *((_DWORD *)a2 + 4) && v15 >= *((_DWORD *)a2 + 5) )
        v15 = *((_DWORD *)a2 + 5);
    }
    if ( *((_DWORD *)a2 + 23) )
    {
      if ( !v15 )
      {
        v14 = 0;
        if ( !*(_QWORD *)(*((_QWORD *)a2 + 1) + 208LL) )
        {
          v12 = v51;
          goto LABEL_65;
        }
      }
    }
    v41 = 0;
    v42 = 0;
    v16 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)COMPRESSION_BUFFER::allocHandler);
    v17 = v16;
    if ( v16 )
    {
      v18 = v16 + 500;
      v16[501] = v16 + 500;
      v16[500] = v16 + 500;
      v19 = *(_QWORD **)v7;
      if ( *(char **)(*(_QWORD *)v7 + 8LL) != v7 )
LABEL_83:
        __fastfail(3u);
      *v18 = v19;
      v16[501] = v7;
      v19[1] = v18;
      *(_QWORD *)v7 = v18;
      v20 = *((_QWORD *)a2 + 1);
      v21 = *(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD *, int, unsigned int *, int *, int, int))(v20 + 208);
      v22 = *(_DWORD *)(v20 + 224);
      if ( v21 )
      {
        if ( v15 )
        {
          BytePtr = COMPRESSION_CONTEXT::QueryBytePtr(a2);
          v24 = 0;
        }
        else
        {
          v24 = v47;
          BytePtr = 0;
        }
        LODWORD(result) = v21(*((_QWORD *)a2 + 4), BytePtr, v15, v17, 4000, &v41, &v42, v22, v24);
      }
      else
      {
        v25 = *(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, _QWORD *, int, unsigned int *, int *, int))(v20 + 200);
        if ( v15 )
          v26 = COMPRESSION_CONTEXT::QueryBytePtr(a2);
        else
          v26 = 0;
        LODWORD(result) = v25(*((_QWORD *)a2 + 4), v26, v15, v17, 4000, &v41, &v42, v22);
      }
      v27 = result;
      if ( (int)result < 0 )
      {
        return (unsigned int)result;
      }
      else
      {
        v12 = v41 + v51;
        v51 += v41;
        v43 = v42 + v13;
        v14 = result == 0;
        if ( !v42
          || (*(_DWORD *)&v45[8] = v42,
              v44 = 0,
              *(_QWORD *)&v45[12] = 0,
              v46 = 0,
              *(_QWORD *)v45 = v17,
              result = (*(__int64 (__fastcall **)(__int64, GUID **, __int64))(*(_QWORD *)v48 + 160LL))(
                         v48,
                         &v44,
                         0xFFFFFFFFLL),
              (int)result >= 0) )
        {
          v28 = v41;
          if ( !v41 )
            goto LABEL_59;
          v29 = (_DWORD *)((char *)a2 + 136);
          while ( 1 )
          {
            v30 = *((_DWORD *)a2 + 24);
            if ( v30 >= *((_DWORD *)a2 + 22) )
            {
LABEL_58:
              v12 = v51;
LABEL_59:
              if ( *((_DWORD *)a2 + 4) )
                *((_DWORD *)a2 + 5) -= v41;
              v13 = v43;
              if ( !v27 )
              {
                v6 = v49;
                goto LABEL_12;
              }
              goto LABEL_65;
            }
            v31 = *((_DWORD *)a2 + 28);
            if ( v31 )
              v32 = *(_DWORD *)(*((_QWORD *)a2 + 13) + 16LL);
            else
              v32 = *((_DWORD *)a2 + 35) - *v29;
            if ( v32 > v28 )
            {
              if ( v31 )
              {
                *(_QWORD *)(*((_QWORD *)a2 + 13) + 8LL) += v28;
                *(_DWORD *)(*((_QWORD *)a2 + 13) + 16LL) -= v28;
              }
              else
              {
                *v29 += v28;
              }
              goto LABEL_58;
            }
            v33 = *((_QWORD *)a2 + 13);
            if ( v31 )
              break;
            *v29 += v32;
            if ( !*(_QWORD *)(v33 + 16) )
              goto LABEL_51;
LABEL_52:
            result = COMPRESSION_CONTEXT::SetupCurrentULChunk(a2);
            if ( (int)result < 0 )
              return result;
            v28 -= v32;
            if ( !v28 )
              goto LABEL_58;
          }
          v29 = (_DWORD *)((char *)a2 + 136);
LABEL_51:
          *((_DWORD *)a2 + 24) = v30 + 1;
          *((_QWORD *)a2 + 13) = v33 + 32;
          goto LABEL_52;
        }
      }
    }
    else
    {
      return 2147942408LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002820  mov     [rsp-8+arg_18], r9
0x180002825  mov     [rsp-8+arg_10], r8d
0x18000282a  mov     [rsp-8+arg_0], rcx
0x18000282f  push    rbp
0x180002830  push    rbx
0x180002831  push    rsi
0x180002832  push    rdi
0x180002833  push    r13
0x180002835  push    r15
0x180002837  lea     rbp, [rsp-2Fh]
0x18000283c  sub     rsp, 0B8h
0x180002843  mov     eax, [rdx+5Ch]
0x180002846  mov     rdi, r9
0x180002849  neg     eax
0x18000284b  mov     rbx, rdx
0x18000284e  sbb     eax, eax
0x180002850  add     eax, 2
0x180002853  mov     [rbp+57h+var_60], eax
0x180002856  mov     rax, [rcx]
0x180002859  mov     rax, [rax+20h]
0x18000285d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002862  mov     r13, rax
0x180002865  mov     [rbp+57h+var_58], rax
0x180002869  mov     rcx, [rax]
0x18000286c  mov     rax, [rcx+8]
0x180002870  mov     rcx, r13
0x180002873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002878  xor     r13d, r13d
0x18000287b  mov     [rbp+57h+var_50], rax
0x18000287f  mov     rsi, rax
0x180002882  test    rdi, rdi
0x180002885  jz      short loc_18000288A
0x180002887  mov     [rdi], r13d
0x18000288a  mov     [rsp+0E0h+var_30], r12
0x180002892  lea     r15, [rbx+90h]
0x180002899  mov     [rsp+0E0h+var_38], r14
0x1800028a1  mov     rdx, [r15]
0x1800028a4  cmp     rdx, r15
0x1800028a7  jz      short loc_1800028DD
0x1800028a9  cmp     [rdx+8], r15
0x1800028ad  jnz     loc_180002CF8
0x1800028b3  mov     rax, [rdx]
0x1800028b6  cmp     [rax+8], rdx
0x1800028ba  jnz     loc_180002CF8
0x1800028c0  mov     rcx, cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * COMPRESSION_BUFFER::allocHandler
0x1800028c7  add     rdx, 0FFFFFFFFFFFFF060h
0x1800028ce  mov     [r15], rax
0x1800028d1  mov     [rax+8], r15
0x1800028d5  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800028db  jmp     short loc_1800028A1
0x1800028dd  cmp     [rbx+0A0h], r13d
0x1800028e4  jz      short loc_1800028F3
0x1800028e6  cmp     [rbx+0A4h], r13d
0x1800028ed  jnz     loc_180002CEF
0x1800028f3  mov     rcx, rbx; this
0x1800028f6  call    ?SetupCurrentULChunk@COMPRESSION_CONTEXT@@QEAAJXZ; COMPRESSION_CONTEXT::SetupCurrentULChunk(void)
0x1800028fb  test    eax, eax
0x1800028fd  js      loc_180002D04
0x180002903  mov     edi, r13d
0x180002906  mov     [rbp+57h+arg_8], r13d
0x18000290a  mov     r14d, r13d
0x18000290d  mov     r12d, r13d
0x180002910  cmp     [rbp+57h+arg_10], 0
0x180002914  mov     eax, 0FFFCh
0x180002919  jz      short loc_180002935
0x18000291b  cmp     r14d, cs:?sm_dwDynamicCompressionBufferLimit@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwDynamicCompressionBufferLimit
0x180002922  ja      loc_180002BC3
0x180002928  cmp     [rsi+218h], ax
0x18000292f  jnb     loc_180002BC3
0x180002935  cmp     dword ptr [rbx+10h], 0
0x180002939  jz      short loc_18000294B
0x18000293b  mov     rcx, rbx; this
0x18000293e  call    ?ProcessEncodedChunkHeader@COMPRESSION_CONTEXT@@QEAAJXZ; COMPRESSION_CONTEXT::ProcessEncodedChunkHeader(void)
0x180002943  test    eax, eax
0x180002945  js      loc_180002D04
0x18000294b  mov     eax, [rbx+58h]
0x18000294e  mov     edi, r13d
0x180002951  cmp     [rbx+60h], eax
0x180002954  jnb     short loc_18000297E
0x180002956  cmp     dword ptr [rbx+70h], 0
0x18000295a  jz      short loc_180002965
0x18000295c  mov     rax, [rbx+68h]
0x180002960  mov     edi, [rax+10h]
0x180002963  jmp     short loc_180002971
0x180002965  mov     edi, [rbx+8Ch]
0x18000296b  sub     edi, [rbx+88h]
0x180002971  cmp     dword ptr [rbx+10h], 0
0x180002975  jz      short loc_18000297E
0x180002977  cmp     edi, [rbx+14h]
0x18000297a  cmovnb  edi, [rbx+14h]
0x18000297e  cmp     dword ptr [rbx+5Ch], 0
0x180002982  jz      short loc_18000299D
0x180002984  test    edi, edi
0x180002986  jnz     short loc_18000299D
0x180002988  mov     rax, [rbx+8]
0x18000298c  mov     r12d, r13d
0x18000298f  cmp     qword ptr [rax+0D0h], 0
0x180002997  jz      loc_180002BC0
0x18000299d  mov     rcx, cs:?allocHandler@COMPRESSION_BUFFER@@2PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * COMPRESSION_BUFFER::allocHandler
0x1800029a4  mov     [rbp+57h+var_90], r13d
0x1800029a8  mov     [rbp+57h+var_8C], r13d
0x1800029ac  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x1800029b2  mov     rsi, rax
0x1800029b5  test    rax, rax
0x1800029b8  jz      loc_180002CFF
0x1800029be  lea     rcx, [rax+0FA0h]
0x1800029c5  mov     [rax+0FA8h], rcx
0x1800029cc  mov     [rcx], rcx
0x1800029cf  mov     rdx, [r15]
0x1800029d2  cmp     [rdx+8], r15
0x1800029d6  jnz     loc_180002CF8
0x1800029dc  mov     [rcx], rdx
0x1800029df  mov     [rcx+8], r15
0x1800029e3  mov     [rdx+8], rcx
0x1800029e7  mov     [r15], rcx
0x1800029ea  mov     rax, [rbx+8]
0x1800029ee  mov     r10, [rax+0D0h]
0x1800029f5  mov     edx, [rax+0E0h]
0x1800029fb  test    r10, r10
0x1800029fe  jz      short loc_180002A50
0x180002a00  test    edi, edi
0x180002a02  jz      short loc_180002A11
0x180002a04  mov     rcx, rbx; this
0x180002a07  call    ?QueryBytePtr@COMPRESSION_CONTEXT@@QEAAPEAEXZ; COMPRESSION_CONTEXT::QueryBytePtr(void)
0x180002a0c  mov     ecx, r13d
0x180002a0f  jmp     short loc_180002A17
0x180002a11  mov     ecx, [rbp+57h+var_60]
0x180002a14  mov     rax, r13
0x180002a17  mov     [rsp+0E0h+var_A0], ecx
0x180002a1b  mov     r9, rsi
0x180002a1e  mov     [rsp+0E0h+var_A8], edx
0x180002a22  lea     rcx, [rbp+57h+var_8C]
0x180002a26  mov     [rsp+0E0h+var_B0], rcx
0x180002a2b  mov     rdx, rax
0x180002a2e  lea     rcx, [rbp+57h+var_90]
0x180002a32  mov     r8d, edi
0x180002a35  mov     [rsp+0E0h+var_B8], rcx
0x180002a3a  mov     rax, r10
0x180002a3d  mov     rcx, [rbx+20h]
0x180002a41  mov     dword ptr [rsp+0E0h+var_C0], 0FA0h
0x180002a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4e  jmp     short loc_180002A9B
0x180002a50  mov     r10, [rax+0C8h]
0x180002a57  test    edi, edi
0x180002a59  jz      short loc_180002A65
0x180002a5b  mov     rcx, rbx; this
0x180002a5e  call    ?QueryBytePtr@COMPRESSION_CONTEXT@@QEAAPEAEXZ; COMPRESSION_CONTEXT::QueryBytePtr(void)
0x180002a63  jmp     short loc_180002A68
0x180002a65  mov     rax, r13
0x180002a68  mov     [rsp+0E0h+var_A8], edx
0x180002a6c  lea     rcx, [rbp+57h+var_8C]
0x180002a70  mov     [rsp+0E0h+var_B0], rcx
0x180002a75  mov     rdx, rax
0x180002a78  lea     rcx, [rbp+57h+var_90]
0x180002a7c  mov     r9, rsi
0x180002a7f  mov     [rsp+0E0h+var_B8], rcx
0x180002a84  mov     r8d, edi
0x180002a87  mov     rcx, [rbx+20h]
0x180002a8b  mov     rax, r10
0x180002a8e  mov     dword ptr [rsp+0E0h+var_C0], 0FA0h
0x180002a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a9b  mov     r13d, eax
0x180002a9e  test    eax, eax
0x180002aa0  js      loc_180002CF3
0x180002aa6  mov     edi, [rbp+57h+arg_8]
0x180002aa9  xor     ecx, ecx
0x180002aab  add     edi, [rbp+57h+var_90]
0x180002aae  mov     r12d, ecx
0x180002ab1  mov     eax, [rbp+57h+var_8C]
0x180002ab4  add     r14d, eax
0x180002ab7  test    r13d, r13d
0x180002aba  mov     [rbp+57h+arg_8], edi
0x180002abd  mov     [rbp+57h+var_88], r14d
0x180002ac1  setz    r12b
0x180002ac5  test    eax, eax
0x180002ac7  jz      short loc_180002B00
0x180002ac9  mov     dword ptr [rbp+57h+var_78+8], eax
0x180002acc  lea     rdx, [rbp+57h+var_80]
0x180002ad0  mov     [rbp+57h+var_80], rcx
0x180002ad4  mov     r8d, 0FFFFFFFFh
0x180002ada  mov     qword ptr [rbp+57h+var_78+0Ch], rcx
0x180002ade  mov     [rbp+57h+var_64], ecx
0x180002ae1  mov     rcx, [rbp+57h+var_58]
0x180002ae5  mov     qword ptr [rbp+57h+var_78], rsi
0x180002ae9  mov     rax, [rcx]
0x180002aec  mov     rax, [rax+0A0h]
0x180002af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af8  test    eax, eax
0x180002afa  js      loc_180002D04
0x180002b00  mov     r14d, [rbp+57h+var_90]
0x180002b04  test    r14d, r14d
0x180002b07  jz      loc_180002B9A
0x180002b0d  lea     rdi, [rbx+88h]
0x180002b14  mov     r8d, [rbx+60h]
0x180002b18  cmp     r8d, [rbx+58h]
0x180002b1c  jnb     short loc_180002B97
0x180002b1e  mov     edx, [rbx+70h]
0x180002b21  test    edx, edx
0x180002b23  jz      short loc_180002B2E
0x180002b25  mov     rax, [rbx+68h]
0x180002b29  mov     esi, [rax+10h]
0x180002b2c  jmp     short loc_180002B36
0x180002b2e  mov     esi, [rbx+8Ch]
0x180002b34  sub     esi, [rdi]
0x180002b36  cmp     esi, r14d
0x180002b39  ja      short loc_180002B7B
0x180002b3b  mov     rcx, [rbx+68h]
0x180002b3f  test    edx, edx
0x180002b41  jz      short loc_180002B4C
0x180002b43  lea     rdi, [rbx+88h]
0x180002b4a  jmp     short loc_180002B55
0x180002b4c  add     [rdi], esi
0x180002b4e  cmp     qword ptr [rcx+10h], 0
0x180002b53  jnz     short loc_180002B64
0x180002b55  lea     eax, [r8+1]
0x180002b59  mov     [rbx+60h], eax
0x180002b5c  lea     rax, [rcx+20h]
0x180002b60  mov     [rbx+68h], rax
0x180002b64  mov     rcx, rbx; this
0x180002b67  call    ?SetupCurrentULChunk@COMPRESSION_CONTEXT@@QEAAJXZ; COMPRESSION_CONTEXT::SetupCurrentULChunk(void)
0x180002b6c  test    eax, eax
0x180002b6e  js      loc_180002D04
0x180002b74  sub     r14d, esi
0x180002b77  jnz     short loc_180002B14
0x180002b79  jmp     short loc_180002B97
0x180002b7b  test    edx, edx
0x180002b7d  jz      short loc_180002B94
0x180002b7f  mov     rcx, [rbx+68h]
0x180002b83  mov     eax, r14d
0x180002b86  add     [rcx+8], rax
0x180002b8a  mov     rax, [rbx+68h]
0x180002b8e  sub     [rax+10h], r14d
0x180002b92  jmp     short loc_180002B97
0x180002b94  add     [rdi], r14d
0x180002b97  mov     edi, [rbp+57h+arg_8]
0x180002b9a  cmp     dword ptr [rbx+10h], 0
0x180002b9e  jz      short loc_180002BA6
0x180002ba0  mov     eax, [rbp+57h+var_90]
0x180002ba3  sub     [rbx+14h], eax
0x180002ba6  mov     r14d, [rbp+57h+var_88]
0x180002baa  test    r13d, r13d
0x180002bad  jnz     short loc_180002BBB
0x180002baf  mov     rsi, [rbp+57h+var_50]
0x180002bb3  xor     r13d, r13d
0x180002bb6  jmp     loc_180002910
0x180002bbb  xor     r13d, r13d
0x180002bbe  jmp     short loc_180002BC3
0x180002bc0  mov     edi, [rbp+57h+arg_8]
0x180002bc3  mov     rsi, [rbp+57h+arg_0]
0x180002bc7  mov     rcx, rsi
0x180002bca  mov     rax, [rsi]
0x180002bcd  mov     rax, [rax+110h]
0x180002bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd9  mov     r8, rax
0x180002bdc  lea     r15, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002be3  xorps   xmm0, xmm0
0x180002be6  mov     [rbp+57h+var_80], r15
0x180002bea  lea     rdx, [rbp+57h+var_80]
0x180002bee  mov     rcx, [rax]
0x180002bf1  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180002bf6  mov     rax, [rcx]
0x180002bf9  mov     rcx, r8
0x180002bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c01  test    eax, eax
0x180002c03  js      short loc_180002C3E
0x180002c05  cmp     dword ptr [rbp+57h+var_78+8], 0
0x180002c09  jz      short loc_180002C3E
0x180002c0b  cmp     dword ptr [rbp+57h+var_78+4], 5
0x180002c0f  jb      short loc_180002C3E
0x180002c11  mov     rax, qword ptr [rbp+57h+var_78]
0x180002c15  cmp     eax, 40h ; '@'
0x180002c18  jz      short loc_180002C1E
0x180002c1a  test    al, 40h
0x180002c1c  jz      short loc_180002C3E
0x180002c1e  mov     rax, [rsi]
0x180002c21  mov     rcx, rsi
0x180002c24  mov     rax, [rax+110h]
0x180002c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c30  mov     rcx, rax; struct IHttpTraceContext *
0x180002c33  mov     r9d, r14d; unsigned int
0x180002c36  mov     r8d, edi; unsigned int
0x180002c39  call    ?RaiseEvent@DYNAMIC_COMPRESSION_DO@IISCompressionEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z; IISCompressionEvents::DYNAMIC_COMPRESSION_DO::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)
0x180002c3e  test    r12d, r12d
0x180002c41  jz      short loc_180002C7F
0x180002c43  mov     rcx, [rbp+57h+var_58]
0x180002c47  mov     edx, 1
0x180002c4c  xor     r9d, r9d
0x180002c4f  mov     [rsp+0E0h+var_C0], r13
0x180002c54  mov     r8d, edx
0x180002c57  mov     rax, [rcx]
0x180002c5a  mov     rax, [rax+90h]
0x180002c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c66  test    eax, eax
0x180002c68  js      loc_180002D04
0x180002c6e  mov     rax, [rbp+57h+arg_18]
0x180002c72  mov     dword ptr [rax], 1
0x180002c78  xor     eax, eax
0x180002c7a  jmp     loc_180002D04
0x180002c7f  cmp     dword ptr [rbx+5Ch], 0
0x180002c83  jnz     short loc_180002CEF
  ... truncated ...
```
