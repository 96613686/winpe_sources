# CCMProviderInfo::CreateProvider(IUnknown *,_GUID const &,void * *)

- ea: `0x180014674`
- end: `0x180014802`
- name: `?CreateProvider@CCMProviderInfo@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `398`
- prototype: `__int64 __fastcall(CCMProviderInfo *__hidden this, LPUNKNOWN pUnkOuter, IID *riid, LPVOID *ppv)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013ff4`
- `0x18001d6d8`
- `0x1800555b8`
- `0x180063e3c`
- `0x18006946c`

## callees

- `0x180014674`
- `0x18001b868`
- `0x180029328`
- `0x180087010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18001479c`
- `ntdll!WinSqmSetDWORD` at `0x18001479c`
- `ole32!CoCreateInstance` at `0x1800147ef`
- `ole32!CoCreateInstance` at `0x1800147ef`

## pseudocode

```c
HRESULT __fastcall CCMProviderInfo::CreateProvider(CCMProviderInfo *this, LPUNKNOWN pUnkOuter, IID *riid, LPVOID *ppv)
{
  const struct _GUID *v4; // rbx
  bool v5; // zf
  __int64 v10; // rdx
  __int64 v11; // rcx
  HRESULT result; // eax
  _DWORD v13[6]; // [rsp+40h] [rbp-18h] BYREF

  v4 = (const struct _GUID *)((char *)this + 32);
  v5 = *((_DWORD *)this + 8) == -2048086068;
  v13[0] = -1890948248;
  v13[1] = 1312575286;
  v13[2] = 2092728766;
  v13[3] = 1556408740;
  if ( v5
    && *((_DWORD *)this + 9) == 1258536409
    && *((_DWORD *)this + 10) == 1710925975
    && *((_DWORD *)this + 11) == -1685724213 )
  {
    if ( !dword_1800BD8CC && !_InterlockedExchange(&dword_1800BD8CC, 1) )
    {
      v10 = g_SNAC9Provider_Used;
LABEL_19:
      WinSqmSetDWORD(0, v10);
    }
  }
  else if ( (unsigned int)InlineIsEqualGUID((char *)this + 32, v13) )
  {
    if ( !dword_1800BD8D4 && !_InterlockedExchange(&dword_1800BD8D4, 1) )
    {
      v10 = g_SNAC10Provider_Used;
      goto LABEL_19;
    }
  }
  else if ( (unsigned int)InlineIsEqualGUID(v11, &CLSID_SQLOLEDB) )
  {
    if ( !dword_1800BD8DC && !_InterlockedExchange(&dword_1800BD8DC, 1) )
    {
      v10 = g_SQLOLEDBProvider_Used;
      goto LABEL_19;
    }
  }
  else if ( !dword_1800BD8E4 && !_InterlockedExchange(&dword_1800BD8E4, 1) )
  {
    v10 = g_OtherProvider_Used;
    goto LABEL_19;
  }
  if ( !*((_BYTE *)this + 17) )
    return CoCreateInstance(v4, pUnkOuter, *((_DWORD *)this + 12), riid, ppv);
  if ( *((_QWORD *)this + 1) )
    return (*(__int64 (__fastcall **)(_QWORD, LPUNKNOWN, IID *, LPVOID *))(**((_QWORD **)this + 1) + 24LL))(
             *((_QWORD *)this + 1),
             pUnkOuter,
             riid,
             ppv);
  result = CCMProviderInfo::AttachClassFactory(this, v4, *((_DWORD *)this + 12));
  if ( result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, LPUNKNOWN, IID *, LPVOID *))(**((_QWORD **)this + 1) + 24LL))(
             *((_QWORD *)this + 1),
             pUnkOuter,
             riid,
             ppv);
  return result;
}

```

## disassembly

```asm
0x180014674  push    rbp
0x180014676  push    rbx
0x180014677  push    rsi
0x180014678  push    rdi
0x180014679  push    r14
0x18001467b  push    r15
0x18001467d  mov     rbp, rsp
0x180014680  sub     rsp, 58h
0x180014684  lea     rbx, [rcx+20h]
0x180014688  mov     [rbp+var_24], 4B03BDD9h
0x18001468f  cmp     dword ptr [rbx], 85ECAFCCh
0x180014695  mov     rsi, r9
0x180014698  mov     r14, r8
0x18001469b  mov     [rbp+var_20], 65FAA897h
0x1800146a2  mov     r15, rdx
0x1800146a5  mov     [rbp+var_1C], 9B85E3CBh
0x1800146ac  mov     rdi, rcx
0x1800146af  mov     [rbp+var_18], 8F4A6B68h
0x1800146b6  mov     [rbp+var_14], 4E3C4F36h
0x1800146bd  mov     [rbp+var_10], 7CBC81BEh
0x1800146c4  mov     [rbp+var_C], 5CC4E9A4h
0x1800146cb  jnz     short loc_180014713
0x1800146cd  mov     eax, [rbp+var_24]
0x1800146d0  cmp     [rbx+4], eax
0x1800146d3  jnz     short loc_180014713
0x1800146d5  mov     eax, [rbp+var_20]
0x1800146d8  cmp     [rbx+8], eax
0x1800146db  jnz     short loc_180014713
0x1800146dd  mov     eax, [rbp+var_1C]
0x1800146e0  cmp     [rbx+0Ch], eax
0x1800146e3  jnz     short loc_180014713
0x1800146e5  mov     eax, cs:dword_1800BD8CC
0x1800146eb  test    eax, eax
0x1800146ed  jnz     loc_1800147A2
0x1800146f3  lea     r8d, [rax+1]
0x1800146f7  mov     eax, r8d
0x1800146fa  xchg    eax, cs:dword_1800BD8CC
0x180014700  test    eax, eax
0x180014702  jnz     loc_1800147A2
0x180014708  mov     edx, cs:?g_SNAC9Provider_Used@@3Utag_SQMDataPoint@@A; tag_SQMDataPoint g_SNAC9Provider_Used
0x18001470e  jmp     loc_18001479A
0x180014713  lea     rdx, [rbp+var_18]
0x180014717  mov     rcx, rbx
0x18001471a  call    InlineIsEqualGUID
0x18001471f  test    eax, eax
0x180014721  jz      short loc_180014746
0x180014723  mov     eax, cs:dword_1800BD8D4
0x180014729  test    eax, eax
0x18001472b  jnz     short loc_1800147A2
0x18001472d  lea     r8d, [rax+1]
0x180014731  mov     eax, r8d
0x180014734  xchg    eax, cs:dword_1800BD8D4
0x18001473a  test    eax, eax
0x18001473c  jnz     short loc_1800147A2
0x18001473e  mov     edx, cs:?g_SNAC10Provider_Used@@3Utag_SQMDataPoint@@A; tag_SQMDataPoint g_SNAC10Provider_Used
0x180014744  jmp     short loc_18001479A
0x180014746  lea     rdx, ?CLSID_SQLOLEDB@@3U_GUID@@B; _GUID const CLSID_SQLOLEDB
0x18001474d  call    InlineIsEqualGUID
0x180014752  test    eax, eax
0x180014754  jz      short loc_180014779
0x180014756  mov     eax, cs:dword_1800BD8DC
0x18001475c  test    eax, eax
0x18001475e  jnz     short loc_1800147A2
0x180014760  lea     r8d, [rax+1]
0x180014764  mov     eax, r8d
0x180014767  xchg    eax, cs:dword_1800BD8DC
0x18001476d  test    eax, eax
0x18001476f  jnz     short loc_1800147A2
0x180014771  mov     edx, cs:?g_SQLOLEDBProvider_Used@@3Utag_SQMDataPoint@@A; tag_SQMDataPoint g_SQLOLEDBProvider_Used
0x180014777  jmp     short loc_18001479A
0x180014779  mov     eax, cs:dword_1800BD8E4
0x18001477f  test    eax, eax
0x180014781  jnz     short loc_1800147A2
0x180014783  lea     r8d, [rax+1]
0x180014787  mov     eax, r8d
0x18001478a  xchg    eax, cs:dword_1800BD8E4
0x180014790  test    eax, eax
0x180014792  jnz     short loc_1800147A2
0x180014794  mov     edx, cs:?g_OtherProvider_Used@@3Utag_SQMDataPoint@@A; tag_SQMDataPoint g_OtherProvider_Used
0x18001479a  xor     ecx, ecx
0x18001479c  call    cs:__imp_WinSqmSetDWORD
0x1800147a2  cmp     byte ptr [rdi+11h], 0
0x1800147a6  jz      short loc_1800147DD
0x1800147a8  cmp     qword ptr [rdi+8], 0
0x1800147ad  jnz     short loc_1800147C2
0x1800147af  mov     r8d, [rdi+30h]; unsigned int
0x1800147b3  mov     rdx, rbx; struct _GUID *
0x1800147b6  mov     rcx, rdi; this
0x1800147b9  call    ?AttachClassFactory@CCMProviderInfo@@QEAAJAEBU_GUID@@K@Z; CCMProviderInfo::AttachClassFactory(_GUID const &,ulong)
0x1800147be  test    eax, eax
0x1800147c0  js      short loc_1800147F5
0x1800147c2  mov     rcx, [rdi+8]
0x1800147c6  mov     r9, rsi
0x1800147c9  mov     r8, r14
0x1800147cc  mov     rdx, r15
0x1800147cf  mov     rax, [rcx]
0x1800147d2  mov     rax, [rax+18h]
0x1800147d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147db  jmp     short loc_1800147F5
0x1800147dd  mov     r8d, [rdi+30h]; dwClsContext
0x1800147e1  mov     r9, r14; riid
0x1800147e4  mov     rdx, r15; pUnkOuter
0x1800147e7  mov     [rsp+58h+ppv], rsi; ppv
0x1800147ec  mov     rcx, rbx; rclsid
0x1800147ef  call    cs:__imp_CoCreateInstance
0x1800147f5  add     rsp, 58h
0x1800147f9  pop     r15
0x1800147fb  pop     r14
0x1800147fd  pop     rdi
0x1800147fe  pop     rsi
0x1800147ff  pop     rbx
0x180014800  pop     rbp
0x180014801  retn
```
