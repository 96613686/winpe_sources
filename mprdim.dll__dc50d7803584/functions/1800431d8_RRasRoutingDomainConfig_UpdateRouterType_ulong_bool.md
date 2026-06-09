# RRasRoutingDomainConfig::UpdateRouterType(ulong,bool *)

- ea: `0x1800431d8`
- end: `0x180043459`
- name: `?UpdateRouterType@RRasRoutingDomainConfig@@AEAAKKPEA_N@Z`
- size: `641`
- prototype: `unsigned int __fastcall(RRasRoutingDomainConfig *__hidden this, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800416fc`
- `0x180042398`

## callees

- `0x18003a4d8`
- `0x18003b090`
- `0x18003b26c`
- `0x1800431d8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## string_xrefs

- `0x1800432fc`: `RRasRoutingDomainConfig::UpdateRouterType`
- `0x1800433d5`: `RRasRoutingDomainConfig::UpdateRouterType`
- `0x18004330a`: `%s: CreateDialInInterfaceForRoutingDomain returned error %d`
- `0x1800432a4`: `%s: DeleteDialInInterfaceForRoutingDomain failed: %d.`
- `0x1800433bb`: `%s: DeleteInterfaceEntry failed: %d.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::UpdateRouterType(RRasRoutingDomainConfig *this, int a2, bool *a3)
{
  int v3; // r15d
  unsigned int DialInInterface; // ebx
  char v8; // al
  int v9; // edi
  int v10; // eax
  BOOL v11; // ecx
  unsigned int v12; // eax
  const wchar_t *v13; // rdx
  __int64 v14; // r9
  const struct _GUID *v15; // r9
  const struct _GUID *v16; // r9
  GUID v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+54h] [rbp-ACh]
  __int128 v21; // [rsp+64h] [rbp-9Ch]
  int v22; // [rsp+74h] [rbp-8Ch]
  int v23; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v3 = *((_DWORD *)this + 134);
  v23 = 0;
  DialInInterface = 0;
  memset_0(v24, 0, sizeof(v24));
  *((_DWORD *)this + 134) = a2;
  v19 = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  if ( a3 )
  {
    *a3 = 0;
    a2 = *((_DWORD *)this + 134);
  }
  v8 = a2;
  v9 = a2 & 8;
  v10 = v8 & 1;
  v11 = v10 || v9;
  if ( ((v3 & 9) != 0) != v11 )
  {
    if ( v10 || v9 )
    {
      DialInInterface = RRasRoutingDomainConfig::CreateDialInInterface(this);
      if ( DialInInterface )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          LOWORD(v23) = 0;
          LOWORD(v19) = 0;
          v18 = GUID_NULL;
          FormatRRASErrorString(
            &v23,
            L"%s: CreateDialInInterfaceForRoutingDomain returned error %d",
            L"RRasRoutingDomainConfig::UpdateRouterType",
            DialInInterface);
          v15 = &v18;
          if ( this != (RRasRoutingDomainConfig *)-516LL )
            v15 = (const struct _GUID *)((char *)this + 516);
          gCfgStoreParamTemplateFunc(
            gCfgStoreEtwContext,
            (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
            (const unsigned __int16 *)&v23,
            v15,
            0,
            (const unsigned __int16 *)&v19);
        }
        return DialInInterface;
      }
      *((_DWORD *)this + 156) = 100;
    }
    else
    {
      v12 = RRasRoutingDomainConfig::DeleteDialInInterface(this);
      DialInInterface = v12;
      if ( v12 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v13 = L"%s: DeleteDialInInterfaceForRoutingDomain failed: %d.";
          LOWORD(v23) = 0;
          v14 = v12;
          LOWORD(v19) = 0;
LABEL_27:
          v18 = GUID_NULL;
          FormatRRASErrorString(&v23, v13, L"RRasRoutingDomainConfig::UpdateRouterType", v14);
          v16 = &v18;
          if ( this != (RRasRoutingDomainConfig *)-516LL )
            v16 = (const struct _GUID *)((char *)this + 516);
          gCfgStoreParamTemplateFunc(
            gCfgStoreEtwContext,
            (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
            (const unsigned __int16 *)&v23,
            v16,
            0,
            (const unsigned __int16 *)&v19);
          return 0;
        }
        return 0;
      }
      memset_0((char *)this + 624, 0, 0x68u);
    }
    if ( a3 )
      *a3 = 1;
  }
  if ( (v3 & 0x24) != 0 && (*((_BYTE *)this + 536) & 0x24) == 0 )
  {
    DialInInterface = RRasRoutingDomainConfig::DeleteInterfaceEntry(this, 0, 1);
    if ( DialInInterface )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        v13 = L"%s: DeleteInterfaceEntry failed: %d.";
        LOWORD(v23) = 0;
        v14 = DialInInterface;
        LOWORD(v19) = 0;
        goto LABEL_27;
      }
      return 0;
    }
  }
  return DialInInterface;
}

```

## disassembly

```asm
0x1800431d8  mov     [rsp-8+arg_8], rbx
0x1800431dd  push    rbp
0x1800431de  push    rsi
0x1800431df  push    rdi
0x1800431e0  push    r14
0x1800431e2  push    r15
0x1800431e4  lea     rbp, [rsp-790h]
0x1800431ec  sub     rsp, 890h
0x1800431f3  mov     rax, cs:__security_cookie
0x1800431fa  xor     rax, rsp
0x1800431fd  mov     [rbp+7B0h+var_30], rax
0x180043204  mov     r15d, [rcx+218h]
0x18004320b  mov     r14, r8
0x18004320e  mov     edi, edx
0x180043210  mov     rsi, rcx
0x180043213  xor     eax, eax
0x180043215  lea     rcx, [rbp+7B0h+var_82C]; void *
0x180043219  xor     edx, edx; Val
0x18004321b  mov     [rbp+7B0h+var_830], eax
0x18004321e  mov     r8d, 7FCh; Size
0x180043224  xor     ebx, ebx
0x180043226  call    memset_0
0x18004322b  xor     eax, eax
0x18004322d  mov     [rsi+218h], edi
0x180043233  mov     [rsp+8B0h+var_860], eax
0x180043237  xorps   xmm0, xmm0
0x18004323a  mov     [rsp+8B0h+var_83C], eax
0x18004323e  movups  [rsp+8B0h+var_85C], xmm0
0x180043243  movups  [rsp+8B0h+var_84C], xmm0
0x180043248  test    r14, r14
0x18004324b  jz      short loc_180043256
0x18004324d  mov     [r14], al
0x180043250  mov     edi, [rsi+218h]
0x180043256  mov     edx, eax
0x180043258  test    r15b, 9
0x18004325c  mov     eax, edi
0x18004325e  setnz   dl
0x180043261  and     edi, 8
0x180043264  and     eax, 1
0x180043267  jnz     short loc_180043271
0x180043269  test    edi, edi
0x18004326b  jnz     short loc_180043271
0x18004326d  xor     ecx, ecx
0x18004326f  jmp     short loc_180043276
0x180043271  mov     ecx, 1
0x180043276  cmp     edx, ecx
0x180043278  jz      loc_180043381
0x18004327e  test    eax, eax
0x180043280  jnz     short loc_1800432D3
0x180043282  test    edi, edi
0x180043284  jnz     short loc_1800432D3
0x180043286  mov     rcx, rsi; this
0x180043289  call    ?DeleteDialInInterface@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::DeleteDialInInterface(void)
0x18004328e  mov     ebx, eax
0x180043290  test    eax, eax
0x180043292  jz      short loc_1800432BC
0x180043294  cmp     qword ptr cs:xmmword_1800710A0, 0
0x18004329c  jz      loc_18004342F
0x1800432a2  xor     ecx, ecx
0x1800432a4  lea     rdx, aSDeletedialini; "%s: DeleteDialInInterfaceForRoutingDoma"...
0x1800432ab  mov     word ptr [rbp+7B0h+var_830], cx
0x1800432af  mov     r9d, eax
0x1800432b2  mov     word ptr [rsp+8B0h+var_860], cx
0x1800432b7  jmp     loc_1800433CE
0x1800432bc  xor     edx, edx; Val
0x1800432be  lea     rcx, [rsi+270h]; void *
0x1800432c5  lea     r8d, [rdx+68h]; Size
0x1800432c9  call    memset_0
0x1800432ce  jmp     loc_180043378
0x1800432d3  mov     rcx, rsi; this
0x1800432d6  call    ?CreateDialInInterface@RRasRoutingDomainConfig@@AEAAKXZ; RRasRoutingDomainConfig::CreateDialInInterface(void)
0x1800432db  mov     ebx, eax
0x1800432dd  test    eax, eax
0x1800432df  jz      loc_18004336E
0x1800432e5  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800432ed  jz      loc_180043431
0x1800432f3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800432fa  xor     eax, eax
0x1800432fc  lea     r8, aRrasroutingdom_4; "RRasRoutingDomainConfig::UpdateRouterTy"...
0x180043303  mov     r9d, ebx
0x180043306  mov     word ptr [rbp+7B0h+var_830], ax
0x18004330a  lea     rdx, aSCreatedialini; "%s: CreateDialInInterfaceForRoutingDoma"...
0x180043311  mov     word ptr [rsp+8B0h+var_860], ax
0x180043316  lea     rcx, [rbp+7B0h+var_830]
0x18004331a  movdqu  [rsp+8B0h+var_870], xmm0
0x180043320  call    FormatRRASErrorString
0x180043325  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18004332c  lea     rcx, [rsi+204h]
0x180043333  test    rcx, rcx
0x180043336  lea     rax, [rsp+8B0h+var_860]
0x18004333b  mov     [rsp+8B0h+var_888], rax
0x180043340  lea     r9, [rsp+8B0h+var_870]
0x180043345  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x18004334c  lea     r8, [rbp+7B0h+var_830]
0x180043350  cmovnz  r9, rcx
0x180043354  mov     [rsp+8B0h+var_890], 0
0x18004335d  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180043364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043369  jmp     loc_180043431
0x18004336e  mov     dword ptr [rsi+270h], 64h ; 'd'
0x180043378  test    r14, r14
0x18004337b  jz      short loc_180043381
0x18004337d  mov     byte ptr [r14], 1
0x180043381  test    r15b, 24h
0x180043385  jz      loc_180043431
0x18004338b  test    byte ptr [rsi+218h], 24h
0x180043392  jnz     loc_180043431
0x180043398  mov     r8b, 1; bool
0x18004339b  xor     edx, edx; String1
0x18004339d  mov     rcx, rsi; this
0x1800433a0  call    ?DeleteInterfaceEntry@RRasRoutingDomainConfig@@AEAAKPEAG_N@Z; RRasRoutingDomainConfig::DeleteInterfaceEntry(ushort *,bool)
0x1800433a5  mov     ebx, eax
0x1800433a7  test    eax, eax
0x1800433a9  jz      loc_180043431
0x1800433af  cmp     qword ptr cs:xmmword_1800710A0, 0
0x1800433b7  jz      short loc_18004342F
0x1800433b9  xor     eax, eax
0x1800433bb  lea     rdx, aSDeleteinterfa; "%s: DeleteInterfaceEntry failed: %d."
0x1800433c2  mov     word ptr [rbp+7B0h+var_830], ax
0x1800433c6  mov     r9d, ebx
0x1800433c9  mov     word ptr [rsp+8B0h+var_860], ax
0x1800433ce  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800433d5  lea     r8, aRrasroutingdom_4; "RRasRoutingDomainConfig::UpdateRouterTy"...
0x1800433dc  lea     rcx, [rbp+7B0h+var_830]
0x1800433e0  movdqu  [rsp+8B0h+var_870], xmm0
0x1800433e6  call    FormatRRASErrorString
0x1800433eb  mov     rdx, qword ptr cs:xmmword_1800710A0
0x1800433f2  lea     rcx, [rsi+204h]
0x1800433f9  test    rcx, rcx
0x1800433fc  lea     rax, [rsp+8B0h+var_860]
0x180043401  mov     [rsp+8B0h+var_888], rax
0x180043406  lea     r9, [rsp+8B0h+var_870]
0x18004340b  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180043412  lea     r8, [rbp+7B0h+var_830]
0x180043416  cmovnz  r9, rcx
0x18004341a  mov     [rsp+8B0h+var_890], 0
0x180043423  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004342a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004342f  xor     ebx, ebx
0x180043431  mov     eax, ebx
0x180043433  mov     rcx, [rbp+7B0h+var_30]
0x18004343a  xor     rcx, rsp; StackCookie
0x18004343d  call    __security_check_cookie
0x180043442  mov     rbx, [rsp+8B0h+arg_8]
0x18004344a  add     rsp, 890h
0x180043451  pop     r15
0x180043453  pop     r14
0x180043455  pop     rdi
0x180043456  pop     rsi
0x180043457  pop     rbp
0x180043458  retn
```
