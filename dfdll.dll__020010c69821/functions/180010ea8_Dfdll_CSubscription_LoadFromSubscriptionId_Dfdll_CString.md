# Dfdll::CSubscription::LoadFromSubscriptionId(Dfdll::CString &)

- ea: `0x180010ea8`
- end: `0x180010f33`
- name: `?LoadFromSubscriptionId@CSubscription@Dfdll@@QEAAJAEAVCString@2@@Z`
- size: `139`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this, struct Dfdll::CString *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000444c`
- `0x180006180`

## callees

- `0x18000a040`
- `0x18000ca34`
- `0x180010ea8`
- `0x180011a8c`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::LoadFromSubscriptionId(Dfdll::CSubscription *this, struct Dfdll::CString *a2)
{
  __int64 result; // rax

  result = Dfdll::CSubscription::Reset(this);
  if ( (int)result >= 0 )
  {
    result = Dfdll::CSubscription::EnsureInitialization(this);
    if ( (int)result >= 0 )
    {
      result = Dfdll::CSubscription::GetDefinitionIdentityFromText(this, a2, (char *)this + 40);
      if ( (int)result >= 0 )
      {
        result = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 20) + 136LL))(
                   *((_QWORD *)this + 20),
                   (char *)this + 64);
        if ( (int)result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 8) + 64LL))(
                     *((_QWORD *)this + 8),
                     1,
                     (char *)this + 48);
          if ( (int)result >= 0 )
            return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010ea8  mov     [rsp+arg_0], rbx
0x180010ead  mov     [rsp+arg_8], rsi
0x180010eb2  push    rdi
0x180010eb3  sub     rsp, 20h
0x180010eb7  mov     rdi, rdx
0x180010eba  mov     rbx, rcx
0x180010ebd  call    ?Reset@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::Reset(void)
0x180010ec2  xor     esi, esi
0x180010ec4  test    eax, eax
0x180010ec6  js      short loc_180010F23
0x180010ec8  mov     rcx, rbx; this
0x180010ecb  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x180010ed0  test    eax, eax
0x180010ed2  js      short loc_180010F23
0x180010ed4  lea     r8, [rbx+28h]
0x180010ed8  mov     rdx, rdi
0x180010edb  mov     rcx, rbx
0x180010ede  call    ?GetDefinitionIdentityFromText@CSubscription@Dfdll@@IEAAJAEAVCString@2@AEAV?$CIUnknownBasedPointer@UIDefinitionIdentity@@@2@@Z; Dfdll::CSubscription::GetDefinitionIdentityFromText(Dfdll::CString &,Dfdll::CIUnknownBasedPointer<IDefinitionIdentity> &)
0x180010ee3  test    eax, eax
0x180010ee5  js      short loc_180010F23
0x180010ee7  mov     rcx, [rbx+0A0h]
0x180010eee  lea     rdx, [rbx+40h]
0x180010ef2  mov     rax, [rcx]
0x180010ef5  mov     rax, [rax+88h]
0x180010efc  call    cs:__guard_dispatch_icall_fptr
0x180010f02  test    eax, eax
0x180010f04  js      short loc_180010F23
0x180010f06  mov     rcx, [rbx+40h]
0x180010f0a  lea     r8, [rbx+30h]
0x180010f0e  lea     edx, [rsi+1]
0x180010f11  mov     rax, [rcx]
0x180010f14  mov     rax, [rax+40h]
0x180010f18  call    cs:__guard_dispatch_icall_fptr
0x180010f1e  test    eax, eax
0x180010f20  cmovns  eax, esi
0x180010f23  mov     rbx, [rsp+28h+arg_0]
0x180010f28  mov     rsi, [rsp+28h+arg_8]
0x180010f2d  add     rsp, 20h
0x180010f31  pop     rdi
0x180010f32  retn
```
