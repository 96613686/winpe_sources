# Dfdll::CSubscription::GetDefinitionIdentityFromText(Dfdll::CString &,Dfdll::CIUnknownBasedPointer<IDefinitionIdentity> &)

- ea: `0x18000ca34`
- end: `0x18000caa0`
- name: `?GetDefinitionIdentityFromText@CSubscription@Dfdll@@IEAAJAEAVCString@2@AEAV?$CIUnknownBasedPointer@UIDefinitionIdentity@@@2@@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010ea8`

## callees

- `0x18000a040`
- `0x18000ca34`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::GetDefinitionIdentityFromText(
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
    result = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, __int64))(**((_QWORD **)a1 + 18) + 24LL))(
               *((_QWORD **)a1 + 18),
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
0x18000ca34  mov     [rsp+arg_0], rbx
0x18000ca39  mov     [rsp+arg_8], rbp
0x18000ca3e  mov     [rsp+arg_10], rsi
0x18000ca43  push    rdi
0x18000ca44  sub     rsp, 30h
0x18000ca48  xor     ebp, ebp
0x18000ca4a  mov     rsi, r8
0x18000ca4d  mov     rdi, rdx
0x18000ca50  mov     rbx, rcx
0x18000ca53  cmp     [rdx+20h], ebp
0x18000ca56  jnz     short loc_18000CA5F
0x18000ca58  mov     eax, 80070057h
0x18000ca5d  jmp     short loc_18000CA8B
0x18000ca5f  call    ?EnsureInitialization@CSubscription@Dfdll@@IEAAJXZ; Dfdll::CSubscription::EnsureInitialization(void)
0x18000ca64  test    eax, eax
0x18000ca66  js      short loc_18000CA8B
0x18000ca68  mov     rcx, [rbx+90h]
0x18000ca6f  lea     r9, [rsi+8]
0x18000ca73  mov     r8, [rdi+10h]
0x18000ca77  xor     edx, edx
0x18000ca79  mov     rax, [rcx]
0x18000ca7c  mov     rax, [rax+18h]
0x18000ca80  call    cs:__guard_dispatch_icall_fptr
0x18000ca86  test    eax, eax
0x18000ca88  cmovns  eax, ebp
0x18000ca8b  mov     rbx, [rsp+38h+arg_0]
0x18000ca90  mov     rbp, [rsp+38h+arg_8]
0x18000ca95  mov     rsi, [rsp+38h+arg_10]
0x18000ca9a  add     rsp, 30h
0x18000ca9e  pop     rdi
0x18000ca9f  retn
```
