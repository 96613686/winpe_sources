# DeleteInstances(ushort const *,IWbemServices *)

- ea: `0x180051410`
- end: `0x1800517a6`
- name: `?DeleteInstances@@YAHPEBGPEAUIWbemServices@@@Z`
- size: `918`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IWbemServices *)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050084`
- `0x1800acb14`
- `0x1800ad024`
- `0x1800ad164`
- `0x1800ad30c`

## callees

- `0x180051410`
- `0x1800585e8`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180051440`
- `OLEAUT32!__imp_SysAllocString` at `0x18005153d`
- `OLEAUT32!__imp_SysAllocString` at `0x180051440`
- `OLEAUT32!__imp_SysAllocString` at `0x18005153d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005149e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005159b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800516cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180051763`
- `OLEAUT32!__imp_SysFreeString` at `0x180051782`
- `OLEAUT32!__imp_SysFreeString` at `0x18005149e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005159b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800516cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180051763`
- `OLEAUT32!__imp_SysFreeString` at `0x180051782`
- `OLEAUT32!__imp_VariantInit` at `0x18005160c`
- `OLEAUT32!__imp_VariantInit` at `0x18005160c`
- `OLEAUT32!__imp_VariantClear` at `0x18005166a`
- `OLEAUT32!__imp_VariantClear` at `0x18005166a`

## string_xrefs

- `0x180051536`: `__PATH`
- `0x180051467`: `DeleteInstances: Failed to allocate memory`
- `0x18005148a`: `DeleteInstances: Failed to allocate memory`
- `0x180051564`: `DeleteInstances: Failed to allocate memory`
- `0x180051587`: `DeleteInstances: Failed to allocate memory`
- `0x1800514f0`: `DeleteInstances: DeleteInstances failed with 0x%x`
- `0x180051514`: `DeleteInstances: DeleteInstances failed with 0x%x`
- `0x180051721`: `DeleteInstances: Get failed with 0x%x`
- `0x18005174a`: `DeleteInstances: Get failed with 0x%x`
- `0x1800516ab`: `DeleteInstances: DeleteInstance failed with 0x%x`
- `0x1800516f9`: `DeleteInstances: DeleteInstance failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DeleteInstances(const unsigned __int16 *a1, struct IWbemServices *a2)
{
  OLECHAR *v3; // rbx
  OLECHAR *v4; // rcx
  unsigned int v6; // r15d
  int v7; // eax
  __int64 v8; // rdi
  OLECHAR *v9; // rsi
  __int64 v10; // r14
  int v11; // eax
  int v12; // r13d
  __int64 v13; // [rsp+40h] [rbp-40h] BYREF
  OLECHAR *v14; // [rsp+48h] [rbp-38h]
  __int64 v15[2]; // [rsp+50h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-20h] BYREF
  int v17; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v18; // [rsp+D0h] [rbp+50h]
  __int64 v19; // [rsp+D8h] [rbp+58h] BYREF

  v18 = 0;
  v3 = 0;
  v14 = 0;
  if ( a1 )
  {
    v3 = SysAllocString(a1);
    v14 = v3;
  }
  if ( !v3 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"DeleteInstances: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"DeleteInstances: Failed to allocate memory");
      }
    }
    v4 = 0;
    goto LABEL_11;
  }
  v6 = 1;
  v7 = ((__int64 (__fastcall *)(struct IWbemServices *, OLECHAR *, __int64))a2->lpVtbl->CreateInstanceEnum)(a2, v3, 1);
  if ( v7 < 0 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"DeleteInstances: DeleteInstances failed with 0x%x", (unsigned int)v7);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"DeleteInstances: DeleteInstances failed with 0x%x", (unsigned int)v7);
      }
    }
LABEL_19:
    v4 = v3;
LABEL_11:
    SysFreeString(v4);
    return 0;
  }
  v8 = v18;
  v13 = v18;
  v9 = SysAllocString(L"__PATH");
  v15[1] = (__int64)v9;
  if ( !v9 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"DeleteInstances: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"DeleteInstances: Failed to allocate memory");
      }
    }
    SysFreeString(0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    goto LABEL_19;
  }
  v19 = 0;
  v17 = 1;
  while ( v17 == 1 )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v18 + 32LL))(
            v18,
            0xFFFFFFFFLL,
            1,
            &v19,
            &v17) )
    {
      if ( v17 != 1 )
        break;
      v10 = v19;
      v15[0] = v19;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v11 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v19 + 32LL))(
              v19,
              v9,
              0,
              &pvarg,
              0,
              0);
      if ( v11 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"DeleteInstances: Get failed with 0x%x", (unsigned int)v11);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"DeleteInstances: Get failed with 0x%x", (unsigned int)v11);
          }
        }
        goto LABEL_40;
      }
      v12 = ((__int64 (__fastcall *)(struct IWbemServices *, LONGLONG, _QWORD, _QWORD, _QWORD))a2->lpVtbl->DeleteInstance)(
              a2,
              pvarg.llVal,
              0,
              0,
              0);
      VariantClear(&pvarg);
      if ( v12 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"DeleteInstances: DeleteInstance failed with 0x%x", (unsigned int)v12);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"DeleteInstances: DeleteInstance failed with 0x%x", (unsigned int)v12);
          }
        }
LABEL_40:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v15);
        SysFreeString(v9);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
        v6 = 0;
        goto LABEL_52;
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  SysFreeString(v9);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
LABEL_52:
  SysFreeString(v3);
  return v6;
}

```

## disassembly

```asm
0x180051410  mov     [rsp-38h+arg_8], rbx
0x180051415  push    rbp
0x180051416  push    rsi
0x180051417  push    rdi
0x180051418  push    r12
0x18005141a  push    r13
0x18005141c  push    r14
0x18005141e  push    r15
0x180051420  mov     rbp, rsp
0x180051423  sub     rsp, 80h
0x18005142a  mov     r12, rdx
0x18005142d  xor     r13d, r13d
0x180051430  mov     [rbp+arg_10], r13
0x180051434  mov     ebx, r13d
0x180051437  mov     [rbp+var_38], rbx
0x18005143b  test    rcx, rcx
0x18005143e  jz      short loc_18005144D
0x180051440  call    cs:__imp_SysAllocString
0x180051446  mov     rbx, rax
0x180051449  mov     [rbp+var_38], rax
0x18005144d  test    rbx, rbx
0x180051450  jnz     short loc_1800514AB
0x180051452  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180051459  jz      short loc_18005149C
0x18005145b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180051462  test    rax, rax
0x180051465  jz      short loc_180051478
0x180051467  lea     rdx, aDeleteinstance_2; "DeleteInstances: Failed to allocate mem"...
0x18005146e  lea     ecx, [rbx+2]
0x180051471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051476  jmp     short loc_18005149C
0x180051478  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18005147f  jz      short loc_18005149C
0x180051481  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180051488  jz      short loc_18005149C
0x18005148a  lea     rdx, aDeleteinstance_2; "DeleteInstances: Failed to allocate mem"...
0x180051491  mov     ecx, 2; unsigned int
0x180051496  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18005149b  nop
0x18005149c  xor     ecx, ecx; bstrString
0x18005149e  call    cs:__imp_SysFreeString
0x1800514a4  xor     eax, eax
0x1800514a6  jmp     loc_18005178B
0x1800514ab  mov     rax, [r12]
0x1800514af  lea     rcx, [rbp+arg_10]
0x1800514b3  mov     [rsp+80h+var_60], rcx
0x1800514b8  xor     r9d, r9d
0x1800514bb  lea     r15d, [r9+1]
0x1800514bf  mov     r8d, r15d
0x1800514c2  mov     rdx, rbx
0x1800514c5  mov     rcx, r12
0x1800514c8  mov     rax, [rax+90h]
0x1800514cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514d4  mov     r8d, eax
0x1800514d7  test    eax, eax
0x1800514d9  jns     short loc_18005152E
0x1800514db  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800514e2  jz      short loc_180051526
0x1800514e4  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800514eb  test    rax, rax
0x1800514ee  jz      short loc_180051502
0x1800514f0  lea     rdx, aDeleteinstance_0; "DeleteInstances: DeleteInstances failed"...
0x1800514f7  lea     ecx, [r15+1]
0x1800514fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051500  jmp     short loc_180051526
0x180051502  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180051509  jz      short loc_180051526
0x18005150b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180051512  jz      short loc_180051526
0x180051514  lea     rdx, aDeleteinstance_0; "DeleteInstances: DeleteInstances failed"...
0x18005151b  mov     ecx, 2; unsigned int
0x180051520  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180051525  nop
0x180051526  mov     rcx, rbx
0x180051529  jmp     loc_18005149E
0x18005152e  mov     rdi, [rbp+arg_10]
0x180051532  mov     [rbp+var_40], rdi
0x180051536  lea     rcx, aPath; "__PATH"
0x18005153d  call    cs:__imp_SysAllocString
0x180051543  mov     rsi, rax
0x180051546  mov     [rbp+var_28], rax
0x18005154a  test    rax, rax
0x18005154d  jnz     short loc_1800515B0
0x18005154f  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180051556  jz      short loc_180051599
0x180051558  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005155f  test    rax, rax
0x180051562  jz      short loc_180051575
0x180051564  lea     rdx, aDeleteinstance_2; "DeleteInstances: Failed to allocate mem"...
0x18005156b  lea     ecx, [rsi+2]
0x18005156e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051573  jmp     short loc_180051599
0x180051575  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18005157c  jz      short loc_180051599
0x18005157e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180051585  jz      short loc_180051599
0x180051587  lea     rdx, aDeleteinstance_2; "DeleteInstances: Failed to allocate mem"...
0x18005158e  mov     ecx, 2; unsigned int
0x180051593  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180051598  nop
0x180051599  xor     ecx, ecx; bstrString
0x18005159b  call    cs:__imp_SysFreeString
0x1800515a1  nop
0x1800515a2  lea     rcx, [rbp+var_40]
0x1800515a6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800515ab  jmp     loc_180051526
0x1800515b0  mov     [rbp+arg_18], r13
0x1800515b4  mov     [rbp+arg_0], r15d
0x1800515b8  cmp     [rbp+arg_0], r15d
0x1800515bc  jnz     loc_180051760
0x1800515c2  mov     rcx, [rbp+arg_10]
0x1800515c6  mov     rax, [rcx]
0x1800515c9  lea     rdx, [rbp+arg_0]
0x1800515cd  mov     [rsp+80h+var_60], rdx
0x1800515d2  lea     r9, [rbp+arg_18]
0x1800515d6  mov     r8d, r15d
0x1800515d9  or      edx, 0FFFFFFFFh
0x1800515dc  mov     rax, [rax+20h]
0x1800515e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515e5  test    eax, eax
0x1800515e7  jnz     short loc_1800515B8
0x1800515e9  cmp     [rbp+arg_0], r15d
0x1800515ed  jnz     loc_180051760
0x1800515f3  mov     r14, [rbp+arg_18]
0x1800515f7  mov     [rbp+var_30], r14
0x1800515fb  xorps   xmm0, xmm0
0x1800515fe  xor     eax, eax
0x180051600  movups  xmmword ptr [rbp+pvarg], xmm0
0x180051604  mov     qword ptr [rbp+pvarg+10h], rax
0x180051608  lea     rcx, [rbp+pvarg]; pvarg
0x18005160c  call    cs:__imp_VariantInit
0x180051612  mov     rcx, [rbp+arg_18]
0x180051616  mov     rax, [rcx]
0x180051619  mov     [rsp+80h+var_58], r13
0x18005161e  mov     [rsp+80h+var_60], r13
0x180051623  lea     r9, [rbp+pvarg]
0x180051627  xor     r8d, r8d
0x18005162a  mov     rdx, rsi
0x18005162d  mov     rax, [rax+20h]
0x180051631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051636  mov     r8d, eax
0x180051639  test    eax, eax
0x18005163b  js      loc_18005170C
0x180051641  mov     rax, [r12]
0x180051645  mov     [rsp+80h+var_60], r13
0x18005164a  xor     r9d, r9d
0x18005164d  xor     r8d, r8d
0x180051650  mov     rdx, qword ptr [rbp+pvarg+8]
0x180051654  mov     rcx, r12
0x180051657  mov     rax, [rax+80h]
0x18005165e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051663  mov     r13d, eax
0x180051666  lea     rcx, [rbp+pvarg]; pvarg
0x18005166a  call    cs:__imp_VariantClear
0x180051670  xor     ecx, ecx
0x180051672  test    r13d, r13d
0x180051675  js      short loc_180051694
0x180051677  xor     r13d, r13d
0x18005167a  test    r14, r14
0x18005167d  jz      short loc_18005168F
0x18005167f  mov     rax, [r14]
0x180051682  mov     rcx, r14
0x180051685  mov     rax, [rax+10h]
0x180051689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005168e  nop
0x18005168f  jmp     loc_1800515B8
0x180051694  cmp     cs:?g_dwDebugLevel@@3KA, ecx; ulong g_dwDebugLevel
0x18005169a  jz      short loc_1800516BC
0x18005169c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800516a3  test    rax, rax
0x1800516a6  jz      short loc_1800516E4
0x1800516a8  mov     r8d, r13d
0x1800516ab  lea     rdx, aDeleteinstance; "DeleteInstances: DeleteInstance failed "...
0x1800516b2  mov     ecx, 2
0x1800516b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516bc  xor     r13d, r13d
0x1800516bf  lea     rcx, [rbp+var_30]
0x1800516c3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800516c8  nop
0x1800516c9  mov     rcx, rsi; bstrString
0x1800516cc  call    cs:__imp_SysFreeString
0x1800516d2  nop
0x1800516d3  lea     rcx, [rbp+var_40]
0x1800516d7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800516dc  mov     r15d, r13d
0x1800516df  jmp     loc_18005177F
0x1800516e4  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, rcx; void * g_lpDebugMsgContextInstance
0x1800516eb  jz      short loc_1800516BC
0x1800516ed  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, rcx; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800516f4  jz      short loc_1800516BC
0x1800516f6  mov     r8d, r13d
0x1800516f9  lea     rdx, aDeleteinstance; "DeleteInstances: DeleteInstance failed "...
0x180051700  mov     ecx, 2; unsigned int
0x180051705  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18005170a  jmp     short loc_1800516BC
0x18005170c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180051713  jz      short loc_1800516BF
0x180051715  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18005171c  test    rax, rax
0x18005171f  jz      short loc_180051734
0x180051721  lea     rdx, aDeleteinstance_1; "DeleteInstances: Get failed with 0x%x"
0x180051728  mov     ecx, 2
0x18005172d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051732  jmp     short loc_1800516BF
0x180051734  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18005173b  jz      short loc_1800516BF
0x18005173d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180051744  jz      loc_1800516BF
0x18005174a  lea     rdx, aDeleteinstance_1; "DeleteInstances: Get failed with 0x%x"
0x180051751  mov     ecx, 2; unsigned int
0x180051756  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18005175b  jmp     loc_1800516BF
0x180051760  mov     rcx, rsi; bstrString
0x180051763  call    cs:__imp_SysFreeString
0x180051769  nop
0x18005176a  test    rdi, rdi
0x18005176d  jz      short loc_18005177F
0x18005176f  mov     rcx, [rdi]
0x180051772  mov     rax, [rcx+10h]
0x180051776  mov     rcx, rdi
0x180051779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005177e  nop
0x18005177f  mov     rcx, rbx; bstrString
0x180051782  call    cs:__imp_SysFreeString
0x180051788  mov     eax, r15d
0x18005178b  mov     rbx, [rsp+80h+arg_8]
0x180051793  add     rsp, 80h
0x18005179a  pop     r15
0x18005179c  pop     r14
0x18005179e  pop     r13
0x1800517a0  pop     r12
0x1800517a2  pop     rdi
0x1800517a3  pop     rsi
0x1800517a4  pop     rbp
0x1800517a5  retn
```
