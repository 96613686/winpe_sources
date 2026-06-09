# Js::IntlEngineInterfaceExtensionObject::EntryIntl_CacheNumberFormat(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x18038d600`
- end: `0x18038d968`
- name: `?EntryIntl_CacheNumberFormat@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `872`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800a2a0c`
- `0x180189ef4`
- `0x1801a25bc`
- `0x1801a3b24`
- `0x1801bd8b4`
- `0x18038d600`
- `0x1803bc034`
- `0x1803bc130`
- `0x1803bcf80`
- `0x1803c4080`
- `0x1803d8f24`
- `0x1803f562c`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `icu!unum_setAttribute` at `0x18038d872`
- `icu!unum_setAttribute` at `0x18038d88a`
- `icu!unum_setAttribute` at `0x18038d872`
- `icu!unum_setAttribute` at `0x18038d88a`
- `icu!unum_open` at `0x18038d81c`
- `icu!unum_open` at `0x18038d81c`
- `icu!unum_setTextAttribute` at `0x18038d8d6`
- `icu!unum_setTextAttribute` at `0x18038d8d6`

## pseudocode

```c
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_CacheNumberFormat(
        __int64 a1,
        int a2,
        __int64 a3,
        _QWORD *a4)
{
  ThreadContext **v5; // r8
  _DWORD *v6; // r14
  unsigned int v7; // edi
  __int64 v8; // r13
  int v9; // r15d
  __int64 v10; // rcx
  _DWORD *v11; // r12
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdi
  unsigned __int8 v20; // al
  unsigned int v21; // ebx
  __int64 v22; // rax
  __int64 v24; // [rsp+48h] [rbp-C0h] BYREF
  void *v25; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v26[160]; // [rsp+58h] [rbp-B0h] BYREF

  v5 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v5[110], 0xC00u, (struct Js::ScriptContext *)v5, 0);
  v6 = 0;
  v25 = 0;
  v7 = 2;
  if ( (a2 & 0xFFFFFF) != 2 || !Js::DynamicObject::Is(a4) )
    goto LABEL_30;
  v8 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  LODWORD(v24) = 0;
  v9 = Js::AssertIntegerProperty((int)a4);
  v10 = a4[1];
  v25 = 0;
  Js::JavascriptOperators::GetProperty_Internal<0>(
    (int)a4,
    (int)a4,
    0,
    503,
    (__int64)&v25,
    *(_QWORD *)(*(_QWORD *)(v10 + 8) + 1088LL),
    0);
  v11 = v25;
  if ( !v25 || !Js::JavascriptString::Is(v25) )
  {
    Js::Throw::FatalInternalError(-2147467259);
    __debugbreak();
  }
  memset_0(v26, 0, 0x9Du);
  v12 = v11[6];
  v13 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 752LL))(v11);
  Js::LangtagToLocaleID_157__0(v13, v12, v26);
  if ( v9 )
  {
    if ( v9 == 1 )
    {
      v7 = 3;
    }
    else
    {
      if ( v9 != 2 )
        goto LABEL_30;
      v14 = Js::AssertIntegerProperty((int)a4);
      v15 = v14;
      if ( v14 )
      {
        if ( v14 == 1 )
        {
          v7 = 10;
        }
        else
        {
          v16 = 0;
          if ( v15 == 2 )
            v16 = 11;
          v7 = v16;
        }
      }
      v17 = a4[1];
      v25 = 0;
      Js::JavascriptOperators::GetProperty_Internal<0>(
        (int)a4,
        (int)a4,
        0,
        527,
        (__int64)&v25,
        *(_QWORD *)(*(_QWORD *)(v17 + 8) + 1088LL),
        0);
      v6 = v25;
      if ( !v25 || !Js::JavascriptString::Is(v25) )
      {
        Js::Throw::FatalInternalError(-2147467259);
        __debugbreak();
      }
      if ( !v7 )
        goto LABEL_30;
    }
  }
  else
  {
    v7 = 1;
  }
  v18 = unum_open(v7, 0, 0, v26, 0, &v24);
  v19 = Js::FinalizableICUObject<void * *,&void unum_close(void * *)>::New(*(_QWORD *)(v8 + 1008), v18);
  if ( (_DWORD)v24 == 7 )
    goto LABEL_27;
  if ( (int)v24 > 0 || (_DWORD)v24 == -124 )
  {
LABEL_30:
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x18038D967LL);
  }
  v20 = Js::AssertBooleanProperty((int)a4);
  unum_setAttribute(*(_QWORD *)(v19 + 8), 1, v20);
  unum_setAttribute(*(_QWORD *)(v19 + 8), 11, 6);
  Js::SetUNumberFormatDigitOptions(*(_QWORD *)(v19 + 8), a4);
  if ( !v6 )
    goto LABEL_26;
  v21 = v6[6];
  v22 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 752LL))(v6);
  unum_setTextAttribute(*(_QWORD *)(v19 + 8), 5, v22, v21, &v24);
  if ( (_DWORD)v24 == 7 )
LABEL_27:
    Js::Throw::OutOfMemory();
  if ( (int)v24 > 0 || (_DWORD)v24 == -124 )
    goto LABEL_30;
LABEL_26:
  (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*a4 + 200LL))(a4, 10, v19);
  return *(_QWORD *)(*(_QWORD *)(v8 + 8) + 1000LL);
}

```

## disassembly

```asm
0x18038d600  mov     rax, rsp
0x18038d603  mov     [rax+10h], rdx
0x18038d607  mov     [rax+8], rcx
0x18038d60b  mov     [rax+18h], r8
0x18038d60f  mov     [rax+20h], r9
0x18038d613  push    rbp
0x18038d614  push    rbx
0x18038d615  push    rsi
0x18038d616  push    rdi
0x18038d617  push    r12
0x18038d619  push    r13
0x18038d61b  push    r14
0x18038d61d  push    r15
0x18038d61f  lea     rbp, [rax-48h]
0x18038d623  sub     rsp, 108h
0x18038d62a  mov     rax, cs:__security_cookie
0x18038d631  xor     rax, rsp
0x18038d634  mov     [rbp+40h+var_50], rax
0x18038d638  mov     rbx, [rbp+40h+arg_0]
0x18038d63c  xor     r9d, r9d; void *
0x18038d63f  mov     edx, 0C00h; unsigned __int64
0x18038d644  mov     rax, [rbx+8]
0x18038d648  mov     rcx, [rax+8]
0x18038d64c  mov     rcx, [rcx+440h]
0x18038d653  mov     r8, rcx; struct Js::ScriptContext *
0x18038d656  mov     rcx, [rcx+370h]; this
0x18038d65d  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x18038d662  mov     eax, [rbp+40h+arg_8]
0x18038d665  lea     rsi, [rbp+40h+arg_10]
0x18038d669  xor     r14d, r14d
0x18038d66c  and     eax, 0FFFFFFh
0x18038d671  mov     [rsp+140h+var_F8], r14
0x18038d676  lea     edi, [r14+2]
0x18038d67a  cmp     eax, edi
0x18038d67c  jnz     loc_18038D95D
0x18038d682  mov     rsi, [rsi+8]
0x18038d686  mov     rcx, rsi; void *
0x18038d689  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x18038d68e  test    al, al
0x18038d690  jz      loc_18038D95D
0x18038d696  mov     rax, [rbx+8]
0x18038d69a  mov     edx, 212h
0x18038d69f  mov     rcx, [rax+8]
0x18038d6a3  mov     r13, [rcx+440h]
0x18038d6aa  mov     rcx, rsi; int
0x18038d6ad  call    Js__AssertIntegerProperty
0x18038d6b2  mov     dword ptr [rsp+140h+var_100], r14d
0x18038d6b7  mov     r15d, eax
0x18038d6ba  mov     rcx, [rsi+8]
0x18038d6be  lea     rax, [rsp+140h+var_F8]
0x18038d6c3  mov     [rsp+140h+var_F8], r14
0x18038d6c8  mov     r9d, 1F7h; int
0x18038d6ce  mov     [rsp+30h], r14; struct Js::PropertyValueInfo *
0x18038d6d3  xor     r8d, r8d; int
0x18038d6d6  mov     rdx, rsi; int
0x18038d6d9  mov     rcx, [rcx+8]
0x18038d6dd  mov     rcx, [rcx+440h]
0x18038d6e4  mov     [rsp+140h+var_118], rcx; __int64
0x18038d6e9  mov     rcx, rsi; int
0x18038d6ec  mov     [rsp+140h+var_120], rax; __int64
0x18038d6f1  call    ??$GetProperty_Internal@$0A@@JavascriptOperators@Js@@CAHPEAXPEAVRecyclableObject@1@_NHPEAPEAXPEAVScriptContext@1@PEAVPropertyValueInfo@1@@Z; Js::JavascriptOperators::GetProperty_Internal<0>(void *,Js::RecyclableObject *,bool,int,void * *,Js::ScriptContext *,Js::PropertyValueInfo *)
0x18038d6f6  mov     r12, [rsp+140h+var_F8]
0x18038d6fb  test    r12, r12
0x18038d6fe  jz      loc_18038D952
0x18038d704  mov     rcx, r12; void *
0x18038d707  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x18038d70c  test    al, al
0x18038d70e  jz      loc_18038D952
0x18038d714  xor     edx, edx; Val
0x18038d716  lea     rcx, [rsp+140h+var_F0]; void *
0x18038d71b  mov     r8d, 9Dh; Size
0x18038d721  call    memset_0
0x18038d726  mov     rax, [r12]
0x18038d72a  mov     rcx, r12
0x18038d72d  mov     ebx, [r12+18h]
0x18038d732  mov     rax, [rax+2F0h]
0x18038d739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038d73e  lea     r8, [rsp+140h+var_F0]
0x18038d743  mov     edx, ebx
0x18038d745  mov     rcx, rax
0x18038d748  call    Js__LangtagToLocaleID_157__0
0x18038d74d  xor     r12d, r12d
0x18038d750  lea     ebx, [rdi+9]
0x18038d753  test    r15d, r15d
0x18038d756  jnz     short loc_18038D760
0x18038d758  lea     edi, [rbx-0Ah]
0x18038d75b  jmp     loc_18038D801
0x18038d760  cmp     r15d, 1
0x18038d764  jnz     short loc_18038D76F
0x18038d766  lea     edi, [r15+2]
0x18038d76a  jmp     loc_18038D801
0x18038d76f  cmp     r15d, edi
0x18038d772  jnz     loc_18038D95D
0x18038d778  mov     edx, 211h
0x18038d77d  mov     rcx, rsi; int
0x18038d780  call    Js__AssertIntegerProperty
0x18038d785  mov     ecx, eax
0x18038d787  test    eax, eax
0x18038d789  jz      short loc_18038D79F
0x18038d78b  cmp     eax, 1
0x18038d78e  jnz     short loc_18038D795
0x18038d790  lea     edi, [rax+9]
0x18038d793  jmp     short loc_18038D79F
0x18038d795  cmp     ecx, edi
0x18038d797  mov     eax, r12d
0x18038d79a  cmovz   eax, ebx
0x18038d79d  mov     edi, eax
0x18038d79f  mov     rax, [rsi+8]
0x18038d7a3  mov     r9d, 20Fh; int
0x18038d7a9  mov     [rsp+140h+var_F8], r12
0x18038d7ae  xor     r8d, r8d; int
0x18038d7b1  mov     [rsp+30h], r12; struct Js::PropertyValueInfo *
0x18038d7b6  mov     rdx, rsi; int
0x18038d7b9  mov     rcx, rsi; int
0x18038d7bc  mov     rax, [rax+8]
0x18038d7c0  mov     rax, [rax+440h]
0x18038d7c7  mov     [rsp+140h+var_118], rax; __int64
0x18038d7cc  lea     rax, [rsp+140h+var_F8]
0x18038d7d1  mov     [rsp+140h+var_120], rax; __int64
0x18038d7d6  call    ??$GetProperty_Internal@$0A@@JavascriptOperators@Js@@CAHPEAXPEAVRecyclableObject@1@_NHPEAPEAXPEAVScriptContext@1@PEAVPropertyValueInfo@1@@Z; Js::JavascriptOperators::GetProperty_Internal<0>(void *,Js::RecyclableObject *,bool,int,void * *,Js::ScriptContext *,Js::PropertyValueInfo *)
0x18038d7db  mov     r14, [rsp+140h+var_F8]
0x18038d7e0  test    r14, r14
0x18038d7e3  jz      loc_18038D947
0x18038d7e9  mov     rcx, r14; void *
0x18038d7ec  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x18038d7f1  test    al, al
0x18038d7f3  jz      loc_18038D947
0x18038d7f9  test    edi, edi
0x18038d7fb  jz      loc_18038D95D
0x18038d801  lea     rax, [rsp+140h+var_100]
0x18038d806  xor     r8d, r8d
0x18038d809  mov     [rsp+140h+var_118], rax
0x18038d80e  lea     r9, [rsp+140h+var_F0]
0x18038d813  xor     edx, edx
0x18038d815  mov     [rsp+140h+var_120], r12
0x18038d81a  mov     ecx, edi
0x18038d81c  call    cs:__imp_unum_open
0x18038d823  nop     dword ptr [rax+rax+00h]
0x18038d828  mov     rcx, [r13+3F0h]
0x18038d82f  mov     rdx, rax
0x18038d832  call    ?New@?$FinalizableICUObject@PEAPEAX$1?unum_close@@YAXPEAPEAX@Z@Js@@SAPEAV12@PEAVRecycler@Memory@@PEAPEAX@Z; Js::FinalizableICUObject<void * *,&unum_close(void * *)>::New(Memory::Recycler *,void * *)
0x18038d837  mov     ecx, dword ptr [rsp+140h+var_100]
0x18038d83b  mov     rdi, rax
0x18038d83e  cmp     ecx, 7
0x18038d841  jz      loc_18038D941
0x18038d847  test    ecx, ecx
0x18038d849  jg      loc_18038D95D
0x18038d84f  cmp     ecx, 0FFFFFF84h
0x18038d852  jz      loc_18038D95D
0x18038d858  mov     edx, 219h
0x18038d85d  mov     rcx, rsi; int
0x18038d860  call    Js__AssertBooleanProperty
0x18038d865  mov     rcx, [rdi+8]
0x18038d869  mov     edx, 1
0x18038d86e  movzx   r8d, al
0x18038d872  call    cs:__imp_unum_setAttribute
0x18038d879  nop     dword ptr [rax+rax+00h]
0x18038d87e  mov     rcx, [rdi+8]
0x18038d882  mov     r8d, 6
0x18038d888  mov     edx, ebx
0x18038d88a  call    cs:__imp_unum_setAttribute
0x18038d891  nop     dword ptr [rax+rax+00h]
0x18038d896  mov     rcx, [rdi+8]
0x18038d89a  mov     rdx, rsi
0x18038d89d  call    Js__SetUNumberFormatDigitOptions
0x18038d8a2  test    r14, r14
0x18038d8a5  jz      short loc_18038D8F4
0x18038d8a7  mov     rax, [r14]
0x18038d8aa  mov     rcx, r14
0x18038d8ad  mov     ebx, [r14+18h]
0x18038d8b1  mov     rax, [rax+2F0h]
0x18038d8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038d8bd  lea     rcx, [rsp+140h+var_100]
0x18038d8c2  mov     r9d, ebx
0x18038d8c5  mov     [rsp+140h+var_120], rcx
0x18038d8ca  mov     r8, rax
0x18038d8cd  mov     rcx, [rdi+8]
0x18038d8d1  mov     edx, 5
0x18038d8d6  call    cs:__imp_unum_setTextAttribute
0x18038d8dd  nop     dword ptr [rax+rax+00h]
0x18038d8e2  mov     eax, dword ptr [rsp+140h+var_100]
0x18038d8e6  cmp     eax, 7
0x18038d8e9  jz      short loc_18038D941
0x18038d8eb  test    eax, eax
0x18038d8ed  jg      short loc_18038D95D
0x18038d8ef  cmp     eax, 0FFFFFF84h
0x18038d8f2  jz      short loc_18038D95D
0x18038d8f4  mov     rax, [rsi]
0x18038d8f7  xor     r9d, r9d
0x18038d8fa  mov     r8, rdi
0x18038d8fd  mov     [rsp+140h+var_120], r12
0x18038d902  mov     rcx, rsi
0x18038d905  mov     rax, [rax+0C8h]
0x18038d90c  lea     edx, [r9+0Ah]
0x18038d910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18038d915  mov     rax, [r13+8]
0x18038d919  mov     rax, [rax+3E8h]
0x18038d920  mov     rcx, [rbp+40h+var_50]
0x18038d924  xor     rcx, rsp; StackCookie
0x18038d927  call    __security_check_cookie
0x18038d92c  add     rsp, 108h
0x18038d933  pop     r15
0x18038d935  pop     r14
0x18038d937  pop     r13
0x18038d939  pop     r12
0x18038d93b  pop     rdi
0x18038d93c  pop     rsi
0x18038d93d  pop     rbx
0x18038d93e  pop     rbp
0x18038d93f  retn
0x18038d941  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x18038d947  mov     ecx, 80004005h; int
0x18038d94c  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x18038d951  int     3; Trap to Debugger
0x18038d952  mov     ecx, 80004005h; int
0x18038d957  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x18038d95c  int     3; Trap to Debugger
0x18038d95d  mov     ecx, 80004005h; int
0x18038d962  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
```
