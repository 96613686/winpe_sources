# CHost::initDebugger(void)

- ea: `0x14000f988`
- end: `0x14000fa72`
- name: `?initDebugger@CHost@@IEAAJXZ`
- size: `234`
- prototype: `__int64 __fastcall(CHost *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400014b0`

## callees

- `0x140002180`
- `0x14000f988`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000fa43`
- `OLEAUT32!__imp_SysFreeString` at `0x14000fa43`
- `ole32!CoCreateInstance` at `0x14000f9c8`
- `ole32!CoCreateInstance` at `0x14000f9c8`

## pseudocode

```c
HRESULT __fastcall CHost::initDebugger(CHost *this)
{
  bool v1; // zf
  _QWORD *v3; // rdi
  HRESULT result; // eax
  _QWORD *v5; // r14
  OLECHAR *v6; // rdi
  int v7; // esi
  BSTR bstrString; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_BYTE *)this + 71) == 0;
  bstrString = 0;
  if ( v1 )
    return 0;
  v3 = (_QWORD *)((char *)this + 656);
  result = CoCreateInstance(&CLSID_ProcessDebugManager, 0, 0x17u, &IID_IProcessDebugManager64, (LPVOID *)this + 82);
  if ( result >= 0 )
  {
    v5 = (_QWORD *)((char *)this + 664);
    result = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 32LL))(*v3, (char *)this + 664);
    if ( result < 0 )
      return result;
    LoadStr(&bstrString, Global::g_lResourceBase + (*((_BYTE *)this + 71) != 0 ? 1 : 3));
    v6 = bstrString;
    if ( !bstrString )
      return -2147467259;
    v7 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)*v5 + 112LL))(*v5, bstrString);
    SysFreeString(v6);
    if ( v7 < 0 )
      return v7;
    if ( *((_BYTE *)this + 72) )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 32LL))(*v5);
    return 0;
  }
  if ( result == -2147221164 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14000f988  push    rbx
0x14000f98a  push    rsi
0x14000f98b  push    rdi
0x14000f98c  push    r14
0x14000f98e  sub     rsp, 38h
0x14000f992  cmp     byte ptr [rcx+47h], 0
0x14000f996  mov     rbx, rcx
0x14000f999  mov     [rsp+58h+bstrString], 0
0x14000f9a2  jz      loc_14000FA66
0x14000f9a8  lea     rdi, [rcx+290h]
0x14000f9af  xor     edx, edx; pUnkOuter
0x14000f9b1  lea     r9, IID_IProcessDebugManager64; riid
0x14000f9b8  mov     [rsp+58h+ppv], rdi; ppv
0x14000f9bd  lea     rcx, CLSID_ProcessDebugManager; rclsid
0x14000f9c4  lea     r8d, [rdx+17h]; dwClsContext
0x14000f9c8  call    cs:__imp_CoCreateInstance
0x14000f9ce  test    eax, eax
0x14000f9d0  jns     short loc_14000F9E1
0x14000f9d2  xor     ecx, ecx
0x14000f9d4  cmp     eax, 80040154h
0x14000f9d9  cmovz   eax, ecx
0x14000f9dc  jmp     loc_14000FA68
0x14000f9e1  mov     rcx, [rdi]
0x14000f9e4  lea     r14, [rbx+298h]
0x14000f9eb  mov     rdx, r14
0x14000f9ee  mov     rax, [rcx]
0x14000f9f1  mov     rax, [rax+20h]
0x14000f9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9fa  test    eax, eax
0x14000f9fc  js      short loc_14000FA68
0x14000f9fe  mov     al, [rbx+47h]
0x14000fa01  lea     rcx, [rsp+58h+bstrString]; unsigned __int16 **
0x14000fa06  neg     al
0x14000fa08  sbb     edx, edx
0x14000fa0a  and     edx, 0FFFFFFFEh
0x14000fa0d  add     edx, 3
0x14000fa10  add     edx, cs:?g_lResourceBase@Global@@2JA; unsigned int
0x14000fa16  call    ?LoadStr@@YAHPEAPEAGI@Z; LoadStr(ushort * *,uint)
0x14000fa1b  mov     rdi, [rsp+58h+bstrString]
0x14000fa20  test    rdi, rdi
0x14000fa23  jnz     short loc_14000FA2C
0x14000fa25  mov     eax, 80004005h
0x14000fa2a  jmp     short loc_14000FA68
0x14000fa2c  mov     rcx, [r14]
0x14000fa2f  mov     rdx, rdi
0x14000fa32  mov     rax, [rcx]
0x14000fa35  mov     rax, [rax+70h]
0x14000fa39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa3e  mov     rcx, rdi; bstrString
0x14000fa41  mov     esi, eax
0x14000fa43  call    cs:__imp_SysFreeString
0x14000fa49  test    esi, esi
0x14000fa4b  jns     short loc_14000FA51
0x14000fa4d  mov     eax, esi
0x14000fa4f  jmp     short loc_14000FA68
0x14000fa51  cmp     byte ptr [rbx+48h], 0
0x14000fa55  jz      short loc_14000FA66
0x14000fa57  mov     rcx, [r14]
0x14000fa5a  mov     rax, [rcx]
0x14000fa5d  mov     rax, [rax+20h]
0x14000fa61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fa66  xor     eax, eax
0x14000fa68  add     rsp, 38h
0x14000fa6c  pop     r14
0x14000fa6e  pop     rdi
0x14000fa6f  pop     rsi
0x14000fa70  pop     rbx
0x14000fa71  retn
```
