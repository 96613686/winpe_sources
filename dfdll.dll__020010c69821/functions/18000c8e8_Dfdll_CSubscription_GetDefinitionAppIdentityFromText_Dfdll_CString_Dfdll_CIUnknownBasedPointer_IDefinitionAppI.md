# Dfdll::CSubscription::GetDefinitionAppIdentityFromText(Dfdll::CString &,Dfdll::CIUnknownBasedPointer<IDefinitionAppId> &)

- ea: `0x18000c8e8`
- end: `0x18000c954`
- name: `?GetDefinitionAppIdentityFromText@CSubscription@Dfdll@@IEAAJAEAVCString@2@AEAV?$CIUnknownBasedPointer@UIDefinitionAppId@@@2@@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010f34`

## callees

- `0x18000a040`
- `0x18000c8e8`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::GetDefinitionAppIdentityFromText(
        Dfdll::CSubscription *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 result; // rax

  if ( !*(_DWORD *)(a2 + 32) )
    return 2147942487LL;
  result = Dfdll::CSubscription::EnsureInitialization(a1);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, __int64))(**((_QWORD **)a1 + 20) + 24LL))(
               *((_QWORD **)a1 + 20),
               0,
               *(_QWORD *)(a2 + 16),
               a3 + 8);
    if ( (int)result >= 0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c8e8  mov     [rsp+arg_0], rbx
0x18000c8ed  mov     [rsp+arg_8], rbp
0x18000c8f2  mov     [rsp+arg_10], rsi
0x18000c8f7  push    rdi
0x18000c8f8  sub     rsp, 30h
0x18000c8fc  xor     ebp, ebp
0x18000c8fe  mov     rsi, r8
0x18000c901  mov     rdi, rdx
0x18000c904  mov     rbx, rcx
0x18000c907  cmp     [rdx+20h], ebp
0x18000c90a  jnz     short loc_18000C913
0x18000c90c  mov     eax, 80070057h
0x18000c911  jmp     short loc_18000C93F
0x18000c913  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000c918  test    eax, eax
0x18000c91a  js      short loc_18000C93F
0x18000c91c  mov     rcx, [rbx+0A0h]
0x18000c923  lea     r9, [rsi+8]
0x18000c927  mov     r8, [rdi+10h]
0x18000c92b  xor     edx, edx
0x18000c92d  mov     rax, [rcx]
0x18000c930  mov     rax, [rax+18h]
0x18000c934  call    cs:__guard_dispatch_icall_fptr
0x18000c93a  test    eax, eax
0x18000c93c  cmovns  eax, ebp
0x18000c93f  mov     rbx, [rsp+38h+arg_0]
0x18000c944  mov     rbp, [rsp+38h+arg_8]
0x18000c949  mov     rsi, [rsp+38h+arg_10]
0x18000c94e  add     rsp, 30h
0x18000c952  pop     rdi
0x18000c953  retn
```
