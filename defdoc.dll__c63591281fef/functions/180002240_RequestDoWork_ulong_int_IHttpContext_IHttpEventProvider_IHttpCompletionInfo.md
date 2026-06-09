# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002240`
- end: `0x1800024d9`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(int, __int64, struct IHttpContext *, void (__fastcall ***)(_QWORD, __int64), __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001aa0`
- `0x180001c40`

## callees

- `0x180002240`
- `0x180002504`
- `0x180002e18`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall RequestDoWork(
        int a1,
        __int64 a2,
        struct IHttpContext *a3,
        void (__fastcall ***a4)(_QWORD, __int64),
        __int64 a5)
{
  int v5; // r15d
  int v9; // r14d
  int v10; // r12d
  __int64 v11; // rax
  __int64 v12; // rax
  int ParsedMetadata; // esi
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v18; // rax
  void (__fastcall ***v19)(_QWORD); // rsi
  __int64 v20; // rax
  int v21; // r14d
  struct DEFDOC_META_STORED_CONTEXT *v22; // r8
  int v23; // r9d
  __int64 v24; // rcx
  __int64 (__fastcall ***v25)(_QWORD, void *); // rax
  __int64 v26; // rax
  __int64 v27; // [rsp+20h] [rbp-48h]
  __int64 v28; // [rsp+40h] [rbp-28h] BYREF
  struct INativeSectionException *v29; // [rsp+48h] [rbp-20h] BYREF
  struct DEFDOC_META_STORED_CONTEXT *v30; // [rsp+50h] [rbp-18h] BYREF

  v5 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  if ( a5 )
  {
    v9 = 1;
    v5 = (**(__int64 (__fastcall ***)(__int64))a5)(a5);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  if ( a1 != 128 )
    return 0;
  v11 = *(_QWORD *)a3;
  if ( !v9 )
  {
    if ( (*(__int64 (__fastcall **)(struct IHttpContext *))(v11 + 208))(a3) )
    {
      v12 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 208LL))(a3);
      if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 56LL))(v12) & 0x10) != 0 )
      {
        ParsedMetadata = DEFDOC_META_STORED_CONTEXT::GetParsedMetadata(a3, &v30, &v29);
        if ( ParsedMetadata < 0 )
        {
          if ( v29 )
            (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v29)(
              v29,
              &IID_IAppHostConfigException,
              &v28);
          v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
          *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14) + 536) = 0;
          v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
          (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v15 + 24LL))(
            v15,
            500,
            "Internal Server Error",
            19,
            ParsedMetadata,
            v28,
            0);
          if ( v28 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            v28 = 0;
          }
          if ( v29 )
          {
            (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v29 + 16LL))(v29);
            v29 = 0;
          }
          v16 = (unsigned int)ParsedMetadata;
          goto LABEL_16;
        }
        v18 = (_QWORD *)(*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)a3 + 144LL))(a3, 16);
        v19 = (void (__fastcall ***)(_QWORD))v18;
        if ( !v18 )
        {
          v16 = 2147942408LL;
LABEL_16:
          (**a4)(a4, v16);
          return 2;
        }
        v18[1] = 0;
        *v18 = &W3_DEFAULT_DOC_HANDLER::`vftable';
        v20 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
        v21 = (*(__int64 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD), void *))(*(_QWORD *)v20 + 8LL))(
                v20,
                v19,
                g_pDefaultDocModuleContext);
        if ( v21 < 0 )
        {
          (**v19)(v19);
          (**a4)(a4, (unsigned int)v21);
          return 2;
        }
        v22 = v30;
        v23 = 0;
        v24 = (__int64)v19;
        goto LABEL_25;
      }
    }
    return 0;
  }
  v25 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(v11 + 56))(a3);
  v26 = (**v25)(v25, g_pDefaultDocModuleContext);
  v23 = v9;
  v22 = 0;
  v24 = v26;
LABEL_25:
  LODWORD(v27) = v5;
  return W3_DEFAULT_DOC_HANDLER::DoWork(v24, (__int64 *)a3, (__int64)v22, v23, v27, v10);
}

```

## disassembly

```asm
0x180002240  push    rbp
0x180002242  push    rbx
0x180002243  push    rsi
0x180002244  push    rdi
0x180002245  push    r12
0x180002247  push    r13
0x180002249  push    r14
0x18000224b  push    r15
0x18000224d  mov     rbp, rsp
0x180002250  sub     rsp, 68h
0x180002254  mov     rsi, [rbp+arg_20]
0x180002258  xor     r15d, r15d
0x18000225b  mov     [rbp+var_18], r15
0x18000225f  mov     rdi, r9
0x180002262  mov     [rbp+var_20], r15
0x180002266  mov     rbx, r8
0x180002269  mov     [rbp+var_28], r15
0x18000226d  mov     r13d, ecx
0x180002270  test    rsi, rsi
0x180002273  jz      short loc_18000229E
0x180002275  mov     rax, [rsi]
0x180002278  lea     r14d, [r15+1]
0x18000227c  mov     rcx, rsi
0x18000227f  mov     rax, [rax]
0x180002282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002287  mov     rdx, [rsi]
0x18000228a  mov     r15d, eax
0x18000228d  mov     rcx, rsi
0x180002290  mov     rax, [rdx+8]
0x180002294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002299  mov     r12d, eax
0x18000229c  jmp     short loc_1800022A4
0x18000229e  mov     r14d, r15d
0x1800022a1  mov     r12d, r15d
0x1800022a4  cmp     r13d, 80h
0x1800022ab  jnz     loc_180002488
0x1800022b1  mov     rax, [rbx]
0x1800022b4  xor     r13d, r13d
0x1800022b7  mov     rcx, rbx
0x1800022ba  test    r14d, r14d
0x1800022bd  jnz     loc_18000248C
0x1800022c3  mov     rax, [rax+0D0h]
0x1800022ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022cf  test    rax, rax
0x1800022d2  jz      loc_180002488
0x1800022d8  mov     rax, [rbx]
0x1800022db  mov     rcx, rbx
0x1800022de  mov     rax, [rax+0D0h]
0x1800022e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ea  mov     rdx, rax
0x1800022ed  mov     rcx, [rax]
0x1800022f0  mov     rax, [rcx+38h]
0x1800022f4  mov     rcx, rdx
0x1800022f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022fc  test    al, 10h
0x1800022fe  jz      loc_180002488
0x180002304  lea     r8, [rbp+var_20]; struct INativeSectionException **
0x180002308  mov     rcx, rbx; struct IHttpContext *
0x18000230b  lea     rdx, [rbp+var_18]; struct DEFDOC_META_STORED_CONTEXT **
0x18000230f  call    ?GetParsedMetadata@DEFDOC_META_STORED_CONTEXT@@SAJPEAVIHttpContext@@PEAPEAV1@PEAPEAVINativeSectionException@@@Z; DEFDOC_META_STORED_CONTEXT::GetParsedMetadata(IHttpContext *,DEFDOC_META_STORED_CONTEXT * *,INativeSectionException * *)
0x180002314  mov     esi, eax
0x180002316  test    eax, eax
0x180002318  jns     loc_1800023F7
0x18000231e  mov     rcx, [rbp+var_20]
0x180002322  test    rcx, rcx
0x180002325  jz      short loc_18000233D
0x180002327  mov     rdx, [rcx]
0x18000232a  lea     r8, [rbp+var_28]
0x18000232e  mov     rax, [rdx]
0x180002331  lea     rdx, IID_IAppHostConfigException
0x180002338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233d  mov     rax, [rbx]
0x180002340  mov     rcx, rbx
0x180002343  mov     rax, [rax+20h]
0x180002347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000234c  mov     rdx, rax
0x18000234f  mov     rcx, [rax]
0x180002352  mov     rax, [rcx+8]
0x180002356  mov     rcx, rdx
0x180002359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000235e  mov     rcx, rbx
0x180002361  mov     [rax+218h], r13w
0x180002369  mov     rax, [rbx]
0x18000236c  mov     rax, [rax+20h]
0x180002370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002375  mov     r10, rax
0x180002378  mov     [rsp+68h+var_38], r13d
0x18000237d  mov     edx, 1F4h
0x180002382  lea     r8, aInternalServer; "Internal Server Error"
0x180002389  mov     r9d, 13h
0x18000238f  mov     rcx, [rax]
0x180002392  mov     rax, [rcx+18h]
0x180002396  mov     rcx, [rbp+var_28]
0x18000239a  mov     [rsp+68h+var_40], rcx
0x18000239f  mov     rcx, r10
0x1800023a2  mov     dword ptr [rsp+68h+var_48], esi
0x1800023a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ab  mov     rcx, [rbp+var_28]
0x1800023af  test    rcx, rcx
0x1800023b2  jz      short loc_1800023C4
0x1800023b4  mov     rax, [rcx]
0x1800023b7  mov     rax, [rax+10h]
0x1800023bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023c0  mov     [rbp+var_28], r13
0x1800023c4  mov     rcx, [rbp+var_20]
0x1800023c8  test    rcx, rcx
0x1800023cb  jz      short loc_1800023DD
0x1800023cd  mov     rax, [rcx]
0x1800023d0  mov     rax, [rax+10h]
0x1800023d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d9  mov     [rbp+var_20], r13
0x1800023dd  mov     edx, esi
0x1800023df  mov     rax, [rdi]
0x1800023e2  mov     rax, [rax]
0x1800023e5  mov     rcx, rdi
0x1800023e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023ed  mov     eax, 2
0x1800023f2  jmp     loc_1800024C8
0x1800023f7  mov     rax, [rbx]
0x1800023fa  mov     edx, 10h
0x1800023ff  mov     rcx, rbx
0x180002402  mov     rax, [rax+90h]
0x180002409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240e  mov     rsi, rax
0x180002411  test    rax, rax
0x180002414  jz      short loc_18000247E
0x180002416  lea     rax, ??_7W3_DEFAULT_DOC_HANDLER@@6B@; const W3_DEFAULT_DOC_HANDLER::`vftable'
0x18000241d  mov     [rsi+8], r13
0x180002421  mov     [rsi], rax
0x180002424  mov     rcx, [rbx]
0x180002427  mov     rax, [rcx+38h]
0x18000242b  mov     rcx, rbx
0x18000242e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002433  mov     r8, cs:?g_pDefaultDocModuleContext@@3PEAXEA; void * g_pDefaultDocModuleContext
0x18000243a  mov     r9, rax
0x18000243d  mov     rdx, rsi
0x180002440  mov     rcx, [rax]
0x180002443  mov     rax, [rcx+8]
0x180002447  mov     rcx, r9
0x18000244a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000244f  mov     r14d, eax
0x180002452  test    eax, eax
0x180002454  jns     short loc_180002472
0x180002456  mov     rcx, [rsi]
0x180002459  mov     rax, [rcx]
0x18000245c  mov     rcx, rsi
0x18000245f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002464  mov     rcx, [rdi]
0x180002467  mov     edx, r14d
0x18000246a  mov     rax, [rcx]
0x18000246d  jmp     loc_1800023E5
0x180002472  mov     r8, [rbp+var_18]
0x180002476  xor     r9d, r9d
0x180002479  mov     rcx, rsi
0x18000247c  jmp     short loc_1800024B6
0x18000247e  mov     edx, 80070008h
0x180002483  jmp     loc_1800023DF
0x180002488  xor     eax, eax
0x18000248a  jmp     short loc_1800024C8
0x18000248c  mov     rax, [rax+38h]
0x180002490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002495  mov     rdx, cs:?g_pDefaultDocModuleContext@@3PEAXEA; void * g_pDefaultDocModuleContext
0x18000249c  mov     r8, rax
0x18000249f  mov     rcx, [rax]
0x1800024a2  mov     rax, [rcx]
0x1800024a5  mov     rcx, r8
0x1800024a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024ad  mov     r9d, r14d
0x1800024b0  xor     r8d, r8d
0x1800024b3  mov     rcx, rax
0x1800024b6  mov     dword ptr [rsp+68h+var_40], r12d
0x1800024bb  mov     rdx, rbx
0x1800024be  mov     dword ptr [rsp+68h+var_48], r15d
0x1800024c3  call    ?DoWork@W3_DEFAULT_DOC_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVDEFDOC_META_STORED_CONTEXT@@HKJ@Z; W3_DEFAULT_DOC_HANDLER::DoWork(IHttpContext *,DEFDOC_META_STORED_CONTEXT *,int,ulong,long)
0x1800024c8  add     rsp, 68h
0x1800024cc  pop     r15
0x1800024ce  pop     r14
0x1800024d0  pop     r13
0x1800024d2  pop     r12
0x1800024d4  pop     rdi
0x1800024d5  pop     rsi
0x1800024d6  pop     rbx
0x1800024d7  pop     rbp
0x1800024d8  retn
```
