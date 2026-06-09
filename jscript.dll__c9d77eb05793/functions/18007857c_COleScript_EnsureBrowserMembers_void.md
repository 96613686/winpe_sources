# COleScript::EnsureBrowserMembers(void)

- ea: `0x18007857c`
- end: `0x180078636`
- name: `?EnsureBrowserMembers@COleScript@@IEAAJXZ`
- size: `186`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078040`
- `0x1800780d8`
- `0x1800781e4`

## callees

- `0x18000f5e0`
- `0x18000f630`
- `0x18007857c`
- `0x18007af1c`
- `0x180089ddc`
- `0x180092cf0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180078614`
- `ole32!CoCreateInstance` at `0x180078614`

## pseudocode

```c
__int64 __fastcall COleScript::EnsureBrowserMembers(COleScript *this)
{
  MUTX *v1; // rsi
  int v4; // ebx
  LPVOID *ppv; // rdi
  HRESULT LatestPDM; // eax
  struct ComDebugFormatter *v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = (COleScript *)((char *)this + 856);
  if ( !(unsigned int)MUTX::Enter((COleScript *)((char *)this + 856)) )
    return 2147500037LL;
  v4 = 0;
  if ( *((_QWORD *)this + 102) )
    goto LABEL_6;
  v7 = 0;
  v4 = ComDebugFormatter::Create(&v7);
  if ( v4 >= 0 )
  {
    *((_QWORD *)this + 102) = v7;
LABEL_6:
    ppv = (LPVOID *)((char *)this + 808);
    if ( !*ppv )
    {
      if ( (unsigned int)IsHostIE() )
        LatestPDM = LoadLatestPDM(&CLSID_DebugHelper, &IID_IDebugHelper, ppv);
      else
        LatestPDM = CoCreateInstance(&CLSID_DebugHelper, 0, 0x15u, &IID_IDebugHelper, ppv);
      v4 = LatestPDM;
    }
  }
  MUTX::Leave(v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18007857c  mov     [rsp+arg_8], rbx
0x180078581  mov     [rsp+arg_10], rsi
0x180078586  push    rdi
0x180078587  sub     rsp, 30h
0x18007858b  lea     rsi, [rcx+358h]
0x180078592  mov     rdi, rcx
0x180078595  mov     rcx, rsi; this
0x180078598  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18007859d  test    eax, eax
0x18007859f  jnz     short loc_1800785A8
0x1800785a1  mov     eax, 80004005h
0x1800785a6  jmp     short loc_180078626
0x1800785a8  xor     ebx, ebx
0x1800785aa  cmp     [rdi+330h], rbx
0x1800785b1  jnz     short loc_1800785D4
0x1800785b3  lea     rcx, [rsp+38h+arg_0]; struct ComDebugFormatter **
0x1800785b8  mov     [rsp+38h+arg_0], rbx
0x1800785bd  call    ?Create@ComDebugFormatter@@SAJPEAPEAV1@@Z; ComDebugFormatter::Create(ComDebugFormatter * *)
0x1800785c2  mov     ebx, eax
0x1800785c4  test    eax, eax
0x1800785c6  js      short loc_18007861C
0x1800785c8  mov     rcx, [rsp+38h+arg_0]
0x1800785cd  mov     [rdi+330h], rcx
0x1800785d4  add     rdi, 328h
0x1800785db  cmp     qword ptr [rdi], 0
0x1800785df  jnz     short loc_18007861C
0x1800785e1  call    ?IsHostIE@@YAHXZ; IsHostIE(void)
0x1800785e6  lea     rcx, CLSID_DebugHelper; struct _GUID *
0x1800785ed  test    eax, eax
0x1800785ef  jz      short loc_180078602
0x1800785f1  mov     r8, rdi; ppv
0x1800785f4  lea     rdx, IID_IDebugHelper; riid
0x1800785fb  call    ?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z; LoadLatestPDM(_GUID const &,_GUID const &,void * *)
0x180078600  jmp     short loc_18007861A
0x180078602  xor     edx, edx; pUnkOuter
0x180078604  mov     [rsp+38h+ppv], rdi; ppv
0x180078609  lea     r9, IID_IDebugHelper; riid
0x180078610  lea     r8d, [rdx+15h]; dwClsContext
0x180078614  call    cs:__imp_CoCreateInstance
0x18007861a  mov     ebx, eax
0x18007861c  mov     rcx, rsi; this
0x18007861f  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180078624  mov     eax, ebx
0x180078626  mov     rbx, [rsp+38h+arg_8]
0x18007862b  mov     rsi, [rsp+38h+arg_10]
0x180078630  add     rsp, 30h
0x180078634  pop     rdi
0x180078635  retn
```
