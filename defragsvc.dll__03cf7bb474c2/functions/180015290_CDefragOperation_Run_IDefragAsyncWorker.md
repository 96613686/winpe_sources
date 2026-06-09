# CDefragOperation::Run(IDefragAsyncWorker *)

- ea: `0x180015290`
- end: `0x1800155d5`
- name: `?Run@CDefragOperation@@UEAAJPEAUIDefragAsyncWorker@@@Z`
- size: `837`
- prototype: `__int64 __fastcall(CDefragOperation *__hidden this, struct IDefragAsyncWorker *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x180015290`
- `0x1800155dc`
- `0x1800157fc`
- `0x180023220`
- `0x1800244ac`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015467`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015475`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDefragOperation::Run(CDefragOperation *this, struct IDefragAsyncWorker *a2)
{
  __int16 v4; // ax
  _QWORD *v5; // rdi
  __int64 v6; // rcx
  __int64 (__fastcall *v7)(struct IDefragAsyncWorker *, char *); // r15
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  unsigned __int16 **v10; // r14
  unsigned __int16 *v11; // r15
  int AllocatedLength; // r12d
  int v13; // eax
  int v14; // ecx
  LPVOID v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v18; // ebx
  unsigned __int16 v20; // dx
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-40h] BYREF
  __int16 v24; // [rsp+24h] [rbp-3Ch]
  __int16 v25; // [rsp+26h] [rbp-3Ah]
  unsigned int v26; // [rsp+A0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int16 *v28; // [rsp+B0h] [rbp+50h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "CDefragOperation::Run", 233, 1);
  v28 = 0;
  pv = 0;
  v4 = 237;
  v5 = (_QWORD *)((char *)this + 40);
  if ( !a2 )
  {
    v23 = -2147024809;
    v8 = (_QWORD *)((char *)this + 48);
    goto LABEL_19;
  }
  v23 = 0;
  v24 = 237;
  (*(void (__fastcall **)(struct IDefragAsyncWorker *))(*(_QWORD *)a2 + 8LL))(a2);
  v6 = *v5;
  if ( *v5 )
  {
    *v5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  *v5 = a2;
  v7 = *(__int64 (__fastcall **)(struct IDefragAsyncWorker *, char *))(*(_QWORD *)a2 + 144LL);
  v8 = (_QWORD *)((char *)this + 48);
  v9 = *((_QWORD *)this + 6);
  if ( v9 )
  {
    *v8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v23 = v7(a2, (char *)this + 48);
  v4 = 245;
  if ( v23 < 0 )
    goto LABEL_19;
  v24 = 245;
  v23 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)*v5 + 128LL))(*v5, &v28);
  v4 = 248;
  if ( v23 < 0 )
    goto LABEL_19;
  v24 = 248;
  v10 = (unsigned __int16 **)((char *)this + 696);
  v26 = 0;
  v11 = v28;
  if ( v28 )
  {
    AllocatedLength = _GetAllocatedLength(v28, &v26);
    if ( AllocatedLength < 0 )
    {
      v4 = 249;
LABEL_18:
      v23 = AllocatedLength;
LABEL_19:
      v25 = v4;
      goto LABEL_20;
    }
    CBsString::_Release((LPVOID *)this + 87);
    *v10 = v11;
    v28 = 0;
    v21 = v26;
    *((_DWORD *)this + 177) = v26;
    CBsString::BoundUpdateLength((CDefragOperation *)((char *)this + 696), v21);
    v23 = AllocatedLength;
  }
  else
  {
    CBsString::Empty((CDefragOperation *)((char *)this + 696));
    v23 = 0;
  }
  v24 = 249;
  v23 = CBsString::Trailing((CDefragOperation *)((char *)this + 696), v20);
  v4 = 250;
  if ( v23 < 0 )
    goto LABEL_19;
  v24 = 250;
  v13 = *((_DWORD *)this + 176);
  v14 = v13 - 1;
  if ( v13 )
  {
    *((_DWORD *)this + 176) = v14;
    (*v10)[v14] = 0;
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*v5 + 224LL))(*v5, &pv);
  v4 = 254;
  if ( v23 < 0 )
    goto LABEL_19;
  v24 = 254;
  v26 = 0;
  v15 = pv;
  if ( pv )
  {
    AllocatedLength = _GetAllocatedLength((const unsigned __int16 *)pv, &v26);
    if ( AllocatedLength < 0 )
    {
      v4 = 255;
      goto LABEL_18;
    }
    CBsString::_Release((LPVOID *)this + 89);
    *((_QWORD *)this + 89) = v15;
    pv = 0;
    v22 = v26;
    *((_DWORD *)this + 181) = v26;
    CBsString::BoundUpdateLength((CDefragOperation *)((char *)this + 712), v22);
    v23 = AllocatedLength;
  }
  else
  {
    CBsString::Empty((CDefragOperation *)((char *)this + 712));
    v23 = 0;
  }
  v24 = 255;
  v23 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v8 + 24LL))(*v8, (char *)this + 56);
  v4 = 259;
  if ( v23 < 0 )
    goto LABEL_19;
  v24 = 259;
  v23 = (*(__int64 (__fastcall **)(CDefragOperation *))(*(_QWORD *)this + 48LL))(this);
  v4 = 262;
  if ( v23 < 0 )
    goto LABEL_19;
  v24 = 262;
  v23 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v8 + 32LL))(*v8, (char *)this + 56);
  v4 = 265;
  if ( v23 < 0 )
    goto LABEL_19;
  v24 = 265;
LABEL_20:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v28);
  v28 = 0;
  v16 = *v5;
  if ( *v5 )
  {
    *v5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = *v8;
  if ( *v8 )
  {
    *v8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v23;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23);
  return v18;
}

```

## disassembly

```asm
0x180015290  mov     [rsp-38h+arg_18], rbx
0x180015295  push    rbp
0x180015296  push    rsi
0x180015297  push    rdi
0x180015298  push    r12
0x18001529a  push    r13
0x18001529c  push    r14
0x18001529e  push    r15
0x1800152a0  mov     rbp, rsp
0x1800152a3  sub     rsp, 60h
0x1800152a7  mov     r14, rdx
0x1800152aa  mov     rsi, rcx
0x1800152ad  mov     r9d, 1; unsigned __int16
0x1800152b3  mov     r8d, 0E9h; unsigned __int16
0x1800152b9  lea     rdx, aCdefragoperati_7; "CDefragOperation::Run"
0x1800152c0  lea     rcx, [rbp+var_40]; this
0x1800152c4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800152c9  nop
0x1800152ca  xor     r13d, r13d
0x1800152cd  mov     [rbp+arg_10], r13
0x1800152d1  mov     [rbp+pv], r13
0x1800152d5  mov     eax, 0EDh
0x1800152da  lea     rdi, [rsi+28h]
0x1800152de  test    r14, r14
0x1800152e1  jz      loc_1800154D5
0x1800152e7  mov     [rbp+var_40], r13d
0x1800152eb  mov     [rbp+var_3C], ax
0x1800152ef  mov     rax, [r14]
0x1800152f2  mov     rcx, r14
0x1800152f5  mov     rax, [rax+8]
0x1800152f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152fe  nop
0x1800152ff  mov     rcx, [rdi]
0x180015302  test    rcx, rcx
0x180015305  jz      short loc_180015317
0x180015307  mov     [rdi], r13
0x18001530a  mov     rax, [rcx]
0x18001530d  mov     rax, [rax+10h]
0x180015311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015316  nop
0x180015317  mov     [rdi], r14
0x18001531a  mov     rax, [r14]
0x18001531d  mov     r15, [rax+90h]
0x180015324  lea     rbx, [rsi+30h]
0x180015328  mov     rcx, [rbx]
0x18001532b  test    rcx, rcx
0x18001532e  jz      short loc_180015340
0x180015330  mov     [rbx], r13
0x180015333  mov     rdx, [rcx]
0x180015336  mov     rax, [rdx+10h]
0x18001533a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001533f  nop
0x180015340  mov     rdx, rbx
0x180015343  mov     rcx, r14
0x180015346  mov     rax, r15
0x180015349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001534e  mov     [rbp+var_40], eax
0x180015351  test    eax, eax
0x180015353  mov     eax, 0F5h
0x180015358  js      loc_18001545F
0x18001535e  mov     [rbp+var_3C], ax
0x180015362  mov     rcx, [rdi]
0x180015365  mov     rax, [rcx]
0x180015368  lea     rdx, [rbp+arg_10]
0x18001536c  mov     rax, [rax+80h]
0x180015373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015378  mov     [rbp+var_40], eax
0x18001537b  test    eax, eax
0x18001537d  mov     eax, 0F8h
0x180015382  js      loc_18001545F
0x180015388  mov     [rbp+var_3C], ax
0x18001538c  lea     r14, [rsi+2B8h]
0x180015393  mov     [rbp+arg_0], r13d
0x180015397  mov     r15, [rbp+arg_10]
0x18001539b  test    r15, r15
0x18001539e  jz      loc_180015564
0x1800153a4  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800153a8  mov     rcx, r15; unsigned __int16 *
0x1800153ab  call    ?_GetAllocatedLength@@YAJPEBGPEAK@Z; _GetAllocatedLength(ushort const *,ulong *)
0x1800153b0  mov     r12d, eax
0x1800153b3  test    eax, eax
0x1800153b5  jns     loc_180015575
0x1800153bb  mov     eax, 0F9h
0x1800153c0  jmp     loc_18001545B
0x1800153c5  mov     eax, 0F9h
0x1800153ca  mov     [rbp+var_3C], ax
0x1800153ce  mov     rcx, r14; this
0x1800153d1  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x1800153d6  mov     [rbp+var_40], eax
0x1800153d9  test    eax, eax
0x1800153db  mov     eax, 0FAh
0x1800153e0  js      short loc_18001545F
0x1800153e2  mov     [rbp+var_3C], ax
0x1800153e6  mov     eax, [rsi+2C0h]
0x1800153ec  lea     ecx, [rax-1]
0x1800153ef  cmp     ecx, eax
0x1800153f1  jnb     short loc_180015401
0x1800153f3  mov     [r14+8], ecx
0x1800153f7  mov     edx, ecx
0x1800153f9  mov     rcx, [r14]
0x1800153fc  mov     [rcx+rdx*2], r13w
0x180015401  mov     rcx, [rdi]
0x180015404  mov     rax, [rcx]
0x180015407  lea     rdx, [rbp+pv]
0x18001540b  mov     rax, [rax+0E0h]
0x180015412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015417  mov     [rbp+var_40], eax
0x18001541a  test    eax, eax
0x18001541c  mov     eax, 0FEh
0x180015421  js      short loc_18001545F
0x180015423  mov     [rbp+var_3C], ax
0x180015427  mov     [rbp+arg_0], r13d
0x18001542b  lea     r14, [rsi+2C8h]
0x180015432  mov     r15, [rbp+pv]
0x180015436  test    r15, r15
0x180015439  jz      loc_18001559C
0x18001543f  lea     rdx, [rbp+arg_0]; unsigned int *
0x180015443  mov     rcx, r15; unsigned __int16 *
0x180015446  call    ?_GetAllocatedLength@@YAJPEBGPEAK@Z; _GetAllocatedLength(ushort const *,ulong *)
0x18001544b  mov     r12d, eax
0x18001544e  test    eax, eax
0x180015450  jns     loc_1800155AD
0x180015456  mov     eax, 0FFh
0x18001545b  mov     [rbp+var_40], r12d
0x18001545f  mov     [rbp+var_3A], ax
0x180015463  mov     rcx, [rbp+pv]; pv
0x180015467  call    cs:__imp_CoTaskMemFree
0x18001546d  mov     [rbp+pv], r13
0x180015471  mov     rcx, [rbp+arg_10]; pv
0x180015475  call    cs:__imp_CoTaskMemFree
0x18001547b  mov     [rbp+arg_10], r13
0x18001547f  mov     rcx, [rdi]
0x180015482  test    rcx, rcx
0x180015485  jz      short loc_180015497
0x180015487  mov     [rdi], r13
0x18001548a  mov     rax, [rcx]
0x18001548d  mov     rax, [rax+10h]
0x180015491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015496  nop
0x180015497  mov     rcx, [rbx]
0x18001549a  test    rcx, rcx
0x18001549d  jz      short loc_1800154AF
0x18001549f  mov     [rbx], r13
0x1800154a2  mov     rax, [rcx]
0x1800154a5  mov     rax, [rax+10h]
0x1800154a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ae  nop
0x1800154af  mov     ebx, [rbp+var_40]
0x1800154b2  lea     rcx, [rbp+var_40]; this
0x1800154b6  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800154bb  mov     eax, ebx
0x1800154bd  mov     rbx, [rsp+60h+arg_18]
0x1800154c5  add     rsp, 60h
0x1800154c9  pop     r15
0x1800154cb  pop     r14
0x1800154cd  pop     r13
0x1800154cf  pop     r12
0x1800154d1  pop     rdi
0x1800154d2  pop     rsi
0x1800154d3  pop     rbp
0x1800154d4  retn
0x1800154d5  mov     [rbp+var_40], 80070057h
0x1800154dc  lea     rbx, [rsi+30h]
0x1800154e0  jmp     loc_18001545F
0x1800154e5  mov     eax, 0FFh
0x1800154ea  mov     [rbp+var_3C], ax
0x1800154ee  mov     rcx, [rbx]
0x1800154f1  mov     rax, [rcx]
0x1800154f4  lea     rdx, [rsi+38h]
0x1800154f8  mov     rax, [rax+18h]
0x1800154fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015501  mov     [rbp+var_40], eax
0x180015504  test    eax, eax
0x180015506  mov     eax, 103h
0x18001550b  js      loc_18001545F
0x180015511  mov     [rbp+var_3C], ax
0x180015515  mov     rax, [rsi]
0x180015518  mov     rcx, rsi
0x18001551b  mov     rax, [rax+30h]
0x18001551f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015524  mov     [rbp+var_40], eax
0x180015527  test    eax, eax
0x180015529  mov     eax, 106h
0x18001552e  js      loc_18001545F
0x180015534  mov     [rbp+var_3C], ax
0x180015538  mov     rcx, [rbx]
0x18001553b  mov     rax, [rcx]
0x18001553e  lea     rdx, [rsi+38h]
0x180015542  mov     rax, [rax+20h]
0x180015546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001554b  mov     [rbp+var_40], eax
0x18001554e  test    eax, eax
0x180015550  mov     eax, 109h
0x180015555  js      loc_18001545F
0x18001555b  mov     [rbp+var_3C], ax
0x18001555f  jmp     loc_180015463
0x180015564  mov     rcx, r14; this
0x180015567  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18001556c  mov     [rbp+var_40], r13d
0x180015570  jmp     loc_1800153C5
0x180015575  mov     rcx, r14; this
0x180015578  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001557d  mov     [r14], r15
0x180015580  mov     [rbp+arg_10], r13
0x180015584  mov     edx, [rbp+arg_0]; unsigned int
0x180015587  mov     [r14+0Ch], edx
0x18001558b  mov     rcx, r14; this
0x18001558e  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180015593  mov     [rbp+var_40], r12d
0x180015597  jmp     loc_1800153C5
0x18001559c  mov     rcx, r14; this
0x18001559f  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x1800155a4  mov     [rbp+var_40], r13d
0x1800155a8  jmp     loc_1800154E5
0x1800155ad  mov     rcx, r14; this
0x1800155b0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800155b5  mov     [r14], r15
0x1800155b8  mov     [rbp+pv], r13
0x1800155bc  mov     edx, [rbp+arg_0]; unsigned int
0x1800155bf  mov     [r14+0Ch], edx
0x1800155c3  mov     rcx, r14; this
0x1800155c6  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800155cb  mov     [rbp+var_40], r12d
0x1800155cf  jmp     loc_1800154E5
```
