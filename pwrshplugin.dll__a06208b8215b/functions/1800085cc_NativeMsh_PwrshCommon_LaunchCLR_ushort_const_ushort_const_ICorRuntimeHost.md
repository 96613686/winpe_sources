# NativeMsh::PwrshCommon::LaunchCLR(ushort const *,ushort const *,ICorRuntimeHost * *)

- ea: `0x1800085cc`
- end: `0x1800086b2`
- name: `?LaunchCLR@PwrshCommon@NativeMsh@@QEAAIPEBG0PEAPEAUICorRuntimeHost@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(NativeMsh::PwrshCommon *this, const unsigned __int16 *, const unsigned __int16 *, struct ICorRuntimeHost **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800054c0`
- `0x1800054e0`

## callees

- `0x1800085cc`
- `0x18000b010`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x180008614`
- `KERNEL32!SetErrorMode` at `0x180008614`
- `mscoree!CorBindToRuntimeEx` at `0x180008642`
- `mscoree!CorBindToRuntimeEx` at `0x180008642`

## pseudocode

```c
__int64 __fastcall NativeMsh::PwrshCommon::LaunchCLR(
        NativeMsh::PwrshCommon *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ICorRuntimeHost **a4)
{
  int v8; // eax

  if ( a2 && *a2 && a3 && *a3 && a4 )
  {
    SetErrorMode(1u);
    if ( (unsigned int)CorBindToRuntimeEx(a3, L"wks", 4, &CLSID_CorRuntimeHost, &IID_ICorRuntimeHost, a4) == -2146232576
      || !*a4 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, const unsigned __int16 *, const unsigned __int16 *))(**((_QWORD **)this + 1) + 8LL))(
        *((_QWORD *)this + 1),
        0,
        3,
        a3,
        a2);
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 80LL))(*a4);
      if ( v8 >= 0 )
        return 0;
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 1) + 8LL))(
        *((_QWORD *)this + 1),
        0,
        5,
        (unsigned int)v8);
    }
  }
  return 4294901760LL;
}

```

## disassembly

```asm
0x1800085cc  push    rbx
0x1800085ce  push    rbp
0x1800085cf  push    rsi
0x1800085d0  push    rdi
0x1800085d1  sub     rsp, 38h
0x1800085d5  mov     rdi, r9
0x1800085d8  mov     rbx, r8
0x1800085db  mov     rsi, rdx
0x1800085de  mov     rbp, rcx
0x1800085e1  test    rdx, rdx
0x1800085e4  jz      loc_1800086A4
0x1800085ea  xor     eax, eax
0x1800085ec  cmp     ax, [rdx]
0x1800085ef  jz      loc_1800086A4
0x1800085f5  test    rbx, rbx
0x1800085f8  jz      loc_1800086A4
0x1800085fe  cmp     ax, [r8]
0x180008602  jz      loc_1800086A4
0x180008608  test    r9, r9
0x18000860b  jz      loc_1800086A4
0x180008611  lea     ecx, [rax+1]; uMode
0x180008614  call    cs:__imp_SetErrorMode
0x18000861a  lea     rax, IID_ICorRuntimeHost
0x180008621  mov     [rsp+58h+var_30], rdi
0x180008626  lea     r9, CLSID_CorRuntimeHost
0x18000862d  mov     [rsp+58h+var_38], rax
0x180008632  mov     r8d, 4
0x180008638  lea     rdx, aWks; "wks"
0x18000863f  mov     rcx, rbx
0x180008642  call    cs:__imp_CorBindToRuntimeEx
0x180008648  cmp     eax, 80131700h
0x18000864d  jz      short loc_180008686
0x18000864f  mov     rcx, [rdi]
0x180008652  test    rcx, rcx
0x180008655  jz      short loc_180008686
0x180008657  mov     rax, [rcx]
0x18000865a  mov     rax, [rax+50h]
0x18000865e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008663  mov     r9d, eax
0x180008666  test    eax, eax
0x180008668  jns     short loc_180008682
0x18000866a  mov     rcx, [rbp+8]
0x18000866e  mov     rdx, [rcx]
0x180008671  mov     rax, [rdx+8]
0x180008675  xor     edx, edx
0x180008677  lea     r8d, [rdx+5]
0x18000867b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008680  jmp     short loc_1800086A4
0x180008682  xor     eax, eax
0x180008684  jmp     short loc_1800086A9
0x180008686  mov     rcx, [rbp+8]
0x18000868a  xor     edx, edx
0x18000868c  mov     r9, rbx
0x18000868f  mov     [rsp+58h+var_38], rsi
0x180008694  mov     rax, [rcx]
0x180008697  lea     r8d, [rdx+3]
0x18000869b  mov     rax, [rax+8]
0x18000869f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086a4  mov     eax, 0FFFF0000h
0x1800086a9  add     rsp, 38h
0x1800086ad  pop     rdi
0x1800086ae  pop     rsi
0x1800086af  pop     rbp
0x1800086b0  pop     rbx
0x1800086b1  retn
```
