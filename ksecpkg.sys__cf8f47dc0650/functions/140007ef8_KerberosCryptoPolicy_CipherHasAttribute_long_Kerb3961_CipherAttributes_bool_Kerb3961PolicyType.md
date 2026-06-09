# KerberosCryptoPolicy::CipherHasAttribute(long,Kerb3961::CipherAttributes,bool &,Kerb3961PolicyType)

- ea: `0x140007ef8`
- end: `0x140007f60`
- name: `?CipherHasAttribute@KerberosCryptoPolicy@@SAJJW4CipherAttributes@Kerb3961@@AEA_NW4Kerb3961PolicyType@@@Z`
- size: `104`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000561c`
- `0x140005bc4`
- `0x140007600`
- `0x1400078f8`
- `0x1400263c0`

## callees

- `0x140007ef8`
- `0x140010240`

## import_xrefs

- `Kerb3961Kernel!__imp_GetLocalCipherPolicy` at `0x140007f12`
- `Kerb3961Kernel!__imp_GetLocalCipherPolicy` at `0x140007f12`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::CipherHasAttribute(unsigned int a1, int a2, bool *a3)
{
  __int64 LocalCipherPolicy; // rax
  __int64 result; // rax
  int v8; // [rsp+40h] [rbp+18h] BYREF
  int v9; // [rsp+44h] [rbp+1Ch]

  *a3 = 0;
  LocalCipherPolicy = GetLocalCipherPolicy();
  (*(void (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)LocalCipherPolicy + 192LL))(LocalCipherPolicy, &v8, a1);
  result = (unsigned int)v9;
  if ( v9 >= 0 )
  {
    *a3 = (a2 & v8) == a2;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140007ef8  mov     [rsp+arg_0], rbx
0x140007efd  mov     [rsp+arg_8], rsi
0x140007f02  push    rdi
0x140007f03  sub     rsp, 20h
0x140007f07  mov     rsi, r8
0x140007f0a  mov     byte ptr [r8], 0
0x140007f0e  mov     edi, edx
0x140007f10  mov     ebx, ecx
0x140007f12  call    cs:__imp_GetLocalCipherPolicy
0x140007f19  nop     dword ptr [rax+rax+00h]
0x140007f1e  mov     r8d, ebx
0x140007f21  lea     rdx, [rsp+28h+arg_10]
0x140007f26  mov     rcx, rax
0x140007f29  mov     r9, [rax]
0x140007f2c  mov     rax, [r9+0C0h]
0x140007f33  call    _guard_dispatch_icall
0x140007f38  mov     eax, [rsp+28h+arg_14]
0x140007f3c  test    eax, eax
0x140007f3e  js      short loc_140007F4F
0x140007f40  mov     eax, [rsp+28h+arg_10]
0x140007f44  and     eax, edi
0x140007f46  cmp     eax, edi
0x140007f48  setz    al
0x140007f4b  mov     [rsi], al
0x140007f4d  xor     eax, eax
0x140007f4f  mov     rbx, [rsp+28h+arg_0]
0x140007f54  mov     rsi, [rsp+28h+arg_8]
0x140007f59  add     rsp, 20h
0x140007f5d  pop     rdi
0x140007f5e  retn
```
