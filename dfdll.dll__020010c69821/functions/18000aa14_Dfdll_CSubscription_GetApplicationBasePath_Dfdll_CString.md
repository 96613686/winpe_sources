# Dfdll::CSubscription::GetApplicationBasePath(Dfdll::CString &)

- ea: `0x18000aa14`
- end: `0x18000ab8b`
- name: `?GetApplicationBasePath@CSubscription@Dfdll@@QEAAJAEAVCString@2@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, struct Dfdll::CString *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180006180`

## callees

- `0x180002604`
- `0x180009e0c`
- `0x18000a040`
- `0x18000aa14`
- `0x180010f34`
- `0x18001efd0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000aae6`
- `ole32!CoTaskMemFree` at `0x18000ab27`
- `ole32!CoTaskMemFree` at `0x18000ab56`
- `ole32!CoTaskMemFree` at `0x18000ab75`
- `ole32!CoTaskMemFree` at `0x18000aae6`
- `ole32!CoTaskMemFree` at `0x18000ab27`
- `ole32!CoTaskMemFree` at `0x18000ab56`
- `ole32!CoTaskMemFree` at `0x18000ab75`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Dfdll::CSubscription::GetApplicationBasePath(Dfdll::CSubscription *this, struct Dfdll::CString *a2)
{
  int Identities; // ebx
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  int v7; // [rsp+40h] [rbp-10h]
  char v8; // [rsp+44h] [rbp-Ch]
  int v9; // [rsp+70h] [rbp+20h] BYREF
  __int64 v10; // [rsp+80h] [rbp+30h] BYREF

  if ( !*((_QWORD *)this + 8) )
    return (unsigned int)-2147023893;
  Identities = Dfdll::CSubscription::EnsureInitialization(this);
  if ( Identities >= 0 )
  {
    v9 = 1;
    Identities = Dfdll::CSubscription::CheckShellVisibility(this, &v9);
    if ( Identities >= 0 )
    {
      if ( !v9 )
        return (unsigned int)-2147023893;
      if ( *((_QWORD *)this + 14) || (Identities = Dfdll::CSubscription::LoadIdentities(this), Identities >= 0) )
      {
        v10 = 0;
        pv = 0;
        v8 = 0;
        v7 = 0;
        Identities = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *, LPVOID *))(**((_QWORD **)this + 16)
                                                                                            + 144LL))(
                       *((_QWORD *)this + 16),
                       0,
                       *((_QWORD *)this + 10),
                       &v10,
                       &pv);
        if ( Identities >= 0 )
        {
          Identities = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 16) + 152LL))(
                         *((_QWORD *)this + 16),
                         v10);
          if ( Identities >= 0 )
          {
            Identities = Dfdll::CString::Assign(a2, (const unsigned __int16 *)pv);
            if ( Identities >= 0 )
            {
              Identities = 0;
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
        else if ( pv )
        {
          CoTaskMemFree(pv);
        }
      }
    }
  }
  return (unsigned int)Identities;
}

```

## disassembly

```asm
0x18000aa14  mov     [rsp-18h+arg_8], rbx
0x18000aa19  push    rbp
0x18000aa1a  push    rsi
0x18000aa1b  push    rdi
0x18000aa1c  mov     rbp, rsp
0x18000aa1f  sub     rsp, 50h
0x18000aa23  mov     rsi, rdx
0x18000aa26  mov     rdi, rcx
0x18000aa29  cmp     qword ptr [rcx+40h], 0
0x18000aa2e  jnz     short loc_18000AA3A
0x18000aa30  mov     ebx, 800703EBh
0x18000aa35  jmp     loc_18000AB7C
0x18000aa3a  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000aa3f  mov     ebx, eax
0x18000aa41  test    eax, eax
0x18000aa43  js      loc_18000AB7C
0x18000aa49  mov     [rbp+arg_0], 1
0x18000aa50  lea     rdx, [rbp+arg_0]; int *
0x18000aa54  mov     rcx, rdi; this
0x18000aa57  call    ?CheckShellVisibility@CSubscription@Dfdll@@IEAAJAEAH@Z; Dfdll::CSubscription::CheckShellVisibility(int &)
0x18000aa5c  mov     ebx, eax
0x18000aa5e  test    eax, eax
0x18000aa60  js      loc_18000AB7C
0x18000aa66  cmp     [rbp+arg_0], 0
0x18000aa6a  jz      short loc_18000AA30
0x18000aa6c  cmp     qword ptr [rdi+70h], 0
0x18000aa71  jnz     short loc_18000AA85
0x18000aa73  mov     rcx, rdi; this
0x18000aa76  call    ?LoadIdentities@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::LoadIdentities(void)
0x18000aa7b  mov     ebx, eax
0x18000aa7d  test    eax, eax
0x18000aa7f  js      loc_18000AB7C
0x18000aa85  and     [rbp+arg_10], 0
0x18000aa8a  and     [rbp+pv], 0
0x18000aa8f  mov     [rbp+var_C], 0
0x18000aa93  and     [rbp+var_10], 0
0x18000aa97  lea     rax, ??_7?$CCOMPointer@G@Dfdll@@6B@; const Dfdll::CCOMPointer<ushort>::`vftable'
0x18000aa9e  mov     [rbp+var_20], rax
0x18000aaa2  mov     rcx, [rdi+80h]
0x18000aaa9  mov     rax, [rcx]
0x18000aaac  lea     rdx, [rbp+pv]
0x18000aab0  mov     [rsp+50h+var_30], rdx
0x18000aab5  lea     r9, [rbp+arg_10]
0x18000aab9  mov     r8, [rdi+50h]
0x18000aabd  xor     edx, edx
0x18000aabf  mov     rax, [rax+90h]
0x18000aac6  call    cs:__guard_dispatch_icall_fptr
0x18000aacc  mov     ebx, eax
0x18000aace  test    eax, eax
0x18000aad0  jns     short loc_18000AAF2
0x18000aad2  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000aad9  mov     [rbp+var_20], rax
0x18000aadd  mov     rcx, [rbp+pv]; pv
0x18000aae1  test    rcx, rcx
0x18000aae4  jz      short loc_18000AAED
0x18000aae6  call    cs:__imp_CoTaskMemFree
0x18000aaec  nop
0x18000aaed  jmp     loc_18000AB7C
0x18000aaf2  mov     rcx, [rdi+80h]
0x18000aaf9  mov     rax, [rcx]
0x18000aafc  mov     rdx, [rbp+arg_10]
0x18000ab00  mov     rax, [rax+98h]
0x18000ab07  call    cs:__guard_dispatch_icall_fptr
0x18000ab0d  mov     ebx, eax
0x18000ab0f  test    eax, eax
0x18000ab11  jns     short loc_18000AB30
0x18000ab13  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000ab1a  mov     [rbp+var_20], rax
0x18000ab1e  mov     rcx, [rbp+pv]; pv
0x18000ab22  test    rcx, rcx
0x18000ab25  jz      short loc_18000AB2E
0x18000ab27  call    cs:__imp_CoTaskMemFree
0x18000ab2d  nop
0x18000ab2e  jmp     short loc_18000AB7C
0x18000ab30  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18000ab34  mov     rcx, rsi; this
0x18000ab37  call    ?Assign@CString@Dfdll@@QEAAJPEBG@Z; Dfdll::CString::Assign(ushort const *)
0x18000ab3c  mov     ebx, eax
0x18000ab3e  test    eax, eax
0x18000ab40  jns     short loc_18000AB5F
0x18000ab42  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000ab49  mov     [rbp+var_20], rax
0x18000ab4d  mov     rcx, [rbp+pv]; pv
0x18000ab51  test    rcx, rcx
0x18000ab54  jz      short loc_18000AB5D
0x18000ab56  call    cs:__imp_CoTaskMemFree
0x18000ab5c  nop
0x18000ab5d  jmp     short loc_18000AB7C
0x18000ab5f  xor     ebx, ebx
0x18000ab61  lea     rax, ??_7CCOMPointerBase@Dfdll@@6B@; const Dfdll::CCOMPointerBase::`vftable'
0x18000ab68  mov     [rbp+var_20], rax
0x18000ab6c  mov     rcx, [rbp+pv]; pv
0x18000ab70  test    rcx, rcx
0x18000ab73  jz      short loc_18000AB7C
0x18000ab75  call    cs:__imp_CoTaskMemFree
0x18000ab7b  nop
0x18000ab7c  mov     eax, ebx
0x18000ab7e  mov     rbx, [rsp+50h+arg_8]
0x18000ab83  add     rsp, 50h
0x18000ab87  pop     rdi
0x18000ab88  pop     rsi
0x18000ab89  pop     rbp
0x18000ab8a  retn
```
