# COleScript::EnsureBrowserMembers(void)

- ea: `0x180079b8c`
- end: `0x180079c50`
- name: `?EnsureBrowserMembers@COleScript@@IEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(COleScript *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180079658`
- `0x1800796f0`
- `0x1800797fc`

## callees

- `0x18000c860`
- `0x18000c8c0`
- `0x180079b8c`
- `0x18007c704`
- `0x18008be2c`
- `0x180095084`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180079c27`
- `ole32!CoCreateInstance` at `0x180079c27`

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
0x180079b8c  mov     [rsp+arg_8], rbx
0x180079b91  mov     [rsp+arg_10], rsi
0x180079b96  push    rdi
0x180079b97  sub     rsp, 30h
0x180079b9b  lea     rsi, [rcx+358h]
0x180079ba2  mov     rdi, rcx
0x180079ba5  mov     rcx, rsi; this
0x180079ba8  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180079bad  test    eax, eax
0x180079baf  jnz     short loc_180079BBB
0x180079bb1  mov     eax, 80004005h
0x180079bb6  jmp     loc_180079C3F
0x180079bbb  xor     ebx, ebx
0x180079bbd  cmp     [rdi+330h], rbx
0x180079bc4  jnz     short loc_180079BE7
0x180079bc6  lea     rcx, [rsp+38h+arg_0]; struct ComDebugFormatter **
0x180079bcb  mov     [rsp+38h+arg_0], rbx
0x180079bd0  call    ?Create@ComDebugFormatter@@SAJPEAPEAV1@@Z; ComDebugFormatter::Create(ComDebugFormatter * *)
0x180079bd5  mov     ebx, eax
0x180079bd7  test    eax, eax
0x180079bd9  js      short loc_180079C35
0x180079bdb  mov     rcx, [rsp+38h+arg_0]
0x180079be0  mov     [rdi+330h], rcx
0x180079be7  add     rdi, 328h
0x180079bee  cmp     qword ptr [rdi], 0
0x180079bf2  jnz     short loc_180079C35
0x180079bf4  call    ?IsHostIE@@YAHXZ; IsHostIE(void)
0x180079bf9  lea     rcx, CLSID_DebugHelper; struct _GUID *
0x180079c00  test    eax, eax
0x180079c02  jz      short loc_180079C15
0x180079c04  mov     r8, rdi; ppv
0x180079c07  lea     rdx, IID_IDebugHelper; riid
0x180079c0e  call    ?LoadLatestPDM@@YAJAEBU_GUID@@0PEAPEAX@Z; LoadLatestPDM(_GUID const &,_GUID const &,void * *)
0x180079c13  jmp     short loc_180079C33
0x180079c15  xor     edx, edx; pUnkOuter
0x180079c17  mov     [rsp+38h+ppv], rdi; ppv
0x180079c1c  lea     r9, IID_IDebugHelper; riid
0x180079c23  lea     r8d, [rdx+15h]; dwClsContext
0x180079c27  call    cs:__imp_CoCreateInstance
0x180079c2e  nop     dword ptr [rax+rax+00h]
0x180079c33  mov     ebx, eax
0x180079c35  mov     rcx, rsi; this
0x180079c38  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180079c3d  mov     eax, ebx
0x180079c3f  mov     rbx, [rsp+38h+arg_8]
0x180079c44  mov     rsi, [rsp+38h+arg_10]
0x180079c49  add     rsp, 30h
0x180079c4d  pop     rdi
0x180079c4e  retn
```
