# CComImpersonator::Impersonate(int *)

- ea: `0x18002a198`
- end: `0x18002a1d9`
- name: `?Impersonate@CComImpersonator@@QEAAJPEAH@Z`
- size: `65`
- prototype: `__int64 __fastcall(CComImpersonator *__hidden this, int *)`
- caller_count: `16`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017350`
- `0x180017650`
- `0x180017830`
- `0x1800239a0`
- `0x180023a10`
- `0x180023c40`
- `0x180024020`
- `0x180024650`
- `0x1800249d0`
- `0x180024c80`
- `0x180024f40`
- `0x1800254a0`
- `0x180025520`
- `0x180025700`
- `0x180025c20`
- `0x180025cc0`

## callees

- `0x18002a110`
- `0x18002a198`

## pseudocode

```c
__int64 __fastcall CComImpersonator::Impersonate(CComImpersonator *this, int *a2)
{
  __int64 result; // rax
  int v4; // [rsp+38h] [rbp+10h] BYREF
  int v5; // [rsp+3Ch] [rbp+14h]

  v5 = HIDWORD(a2);
  v4 = 0;
  result = CscCom_ImpersonateClient(&v4);
  if ( (_DWORD)result == -2147417833 )
    return 0;
  if ( (int)result >= 0 && !v4 )
    *(_DWORD *)this = 1;
  return result;
}

```

## disassembly

```asm
0x18002a198  mov     qword ptr [rsp+arg_8], rdx
0x18002a19d  push    rbx
0x18002a19e  sub     rsp, 20h
0x18002a1a2  mov     rbx, rcx
0x18002a1a5  mov     [rsp+28h+arg_8], 0
0x18002a1ad  lea     rcx, [rsp+28h+arg_8]; int *
0x18002a1b2  call    ?CscCom_ImpersonateClient@@YAJPEAH@Z; CscCom_ImpersonateClient(int *)
0x18002a1b7  cmp     eax, 80010117h
0x18002a1bc  jnz     short loc_18002A1C2
0x18002a1be  xor     eax, eax
0x18002a1c0  jmp     short loc_18002A1D3
0x18002a1c2  test    eax, eax
0x18002a1c4  js      short loc_18002A1D3
0x18002a1c6  cmp     [rsp+28h+arg_8], 0
0x18002a1cb  jnz     short loc_18002A1D3
0x18002a1cd  mov     dword ptr [rbx], 1
0x18002a1d3  add     rsp, 20h
0x18002a1d7  pop     rbx
0x18002a1d8  retn
```
