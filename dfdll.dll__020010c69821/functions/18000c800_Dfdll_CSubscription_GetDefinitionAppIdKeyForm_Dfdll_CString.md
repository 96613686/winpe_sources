# Dfdll::CSubscription::GetDefinitionAppIdKeyForm(Dfdll::CString &)

- ea: `0x18000c800`
- end: `0x18000c8e8`
- name: `?GetDefinitionAppIdKeyForm@CSubscription@Dfdll@@QEAAJAEAVCString@2@@Z`
- size: `232`
- prototype: `int(Dfdll::CSubscription *__hidden this, struct Dfdll::CString *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180006e60`

## callees

- `0x180002604`
- `0x18000a040`
- `0x18000c800`
- `0x18001efd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000c87c`
- `ole32!CoTaskMemFree` at `0x18000c8ab`
- `ole32!CoTaskMemFree` at `0x18000c8ca`
- `ole32!CoTaskMemFree` at `0x18000c87c`
- `ole32!CoTaskMemFree` at `0x18000c8ab`
- `ole32!CoTaskMemFree` at `0x18000c8ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::GetDefinitionAppIdKeyForm(
        Dfdll::CSubscription *this,
        struct Dfdll::CString *a2)
{
  int v4; // ebx
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  int v7; // [rsp+40h] [rbp-10h]
  char v8; // [rsp+44h] [rbp-Ch]

  v4 = Dfdll::CSubscription::EnsureInitialization(this);
  if ( v4 >= 0 )
  {
    pv = 0;
    v8 = 0;
    v7 = 0;
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, LPVOID *))(**((_QWORD **)this + 20) + 120LL))(
           *((_QWORD *)this + 20),
           0,
           *((_QWORD *)this + 8),
           &pv);
    if ( v4 >= 0 )
    {
      v4 = Dfdll::CString::Assign(a2, (const unsigned __int16 *)pv);
      if ( v4 >= 0 )
      {
        v4 = 0;
        if ( pv )
          CoTaskMemFree(pv);
      }
      else if ( pv )
      {
        CoTaskMemFree(pv);
      }
    }
    else if ( pv )
    {
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c800  mov     [rsp-8+arg_0], rbx
0x18000c805  mov     [rsp-8+arg_8], rsi
0x18000c80a  mov     [rsp-8+arg_10], rdi
0x18000c80f  push    rbp
0x18000c810  mov     rbp, rsp
0x18000c813  sub     rsp, 50h
0x18000c817  mov     rsi, rdx
0x18000c81a  mov     rdi, rcx
0x18000c81d  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000c822  mov     ebx, eax
0x18000c824  test    eax, eax
0x18000c826  js      loc_18000C8D1
0x18000c82c  and     [rbp+pv], 0
0x18000c831  mov     [rbp+var_C], 0
0x18000c835  and     [rbp+var_10], 0
0x18000c839  lea     rax, ??_7?$CCOMPointer@G@Dfdll@@6B@; const Dfdll::CCOMPointer<ushort>::`vftable'
0x18000c840  mov     [rbp+var_20], rax
0x18000c844  mov     rcx, [rdi+0A0h]
0x18000c84b  mov     rax, [rcx]
0x18000c84e  lea     r9, [rbp+pv]
0x18000c852  mov     r8, [rdi+40h]
0x18000c856  xor     edx, edx
0x18000c858  mov     rax, [rax+78h]
0x18000c85c  call    cs:__guard_dispatch_icall_fptr
0x18000c862  mov     ebx, eax
0x18000c864  test    eax, eax
0x18000c866  jns     short loc_18000C885
0x18000c868  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000c86f  mov     [rbp+var_20], rax
0x18000c873  mov     rcx, [rbp+pv]; pv
0x18000c877  test    rcx, rcx
0x18000c87a  jz      short loc_18000C883
0x18000c87c  call    cs:__imp_CoTaskMemFree
0x18000c882  nop
0x18000c883  jmp     short loc_18000C8D1
0x18000c885  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18000c889  mov     rcx, rsi; this
0x18000c88c  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x18000c891  mov     ebx, eax
0x18000c893  test    eax, eax
0x18000c895  jns     short loc_18000C8B4
0x18000c897  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000c89e  mov     [rbp+var_20], rax
0x18000c8a2  mov     rcx, [rbp+pv]; pv
0x18000c8a6  test    rcx, rcx
0x18000c8a9  jz      short loc_18000C8B2
0x18000c8ab  call    cs:__imp_CoTaskMemFree
0x18000c8b1  nop
0x18000c8b2  jmp     short loc_18000C8D1
0x18000c8b4  xor     ebx, ebx
0x18000c8b6  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000c8bd  mov     [rbp+var_20], rax
0x18000c8c1  mov     rcx, [rbp+pv]; pv
0x18000c8c5  test    rcx, rcx
0x18000c8c8  jz      short loc_18000C8D1
0x18000c8ca  call    cs:__imp_CoTaskMemFree
0x18000c8d0  nop
0x18000c8d1  mov     eax, ebx
0x18000c8d3  mov     rbx, [rsp+50h+arg_0]
0x18000c8d8  mov     rsi, [rsp+50h+arg_8]
0x18000c8dd  mov     rdi, [rsp+50h+arg_10]
0x18000c8e2  add     rsp, 50h
0x18000c8e6  pop     rbp
0x18000c8e7  retn
```
