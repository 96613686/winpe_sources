# std::basic_ostream<ushort,std::char_traits<ushort>>::sentry::sentry(std::basic_ostream<ushort,std::char_traits<ushort>> &)

- ea: `0x1800075d8`
- end: `0x1800076eb`
- name: `??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z`
- size: `275`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007018`
- `0x180007208`
- `0x1800075d8`

## callees

- `0x180002048`
- `0x1800075d8`
- `0x180009260`
- `0x1800093d4`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall std::basic_ostream<unsigned short>::sentry::sentry(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v10; // [rsp+20h] [rbp-18h] BYREF
  char v11; // [rsp+28h] [rbp-10h]

  *(_QWORD *)a1 = a2;
  v4 = *(_QWORD *)(*(int *)(*(_QWORD *)a2 + 4LL) + a2 + 72);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  v5 = *(int *)(*(_QWORD *)a2 + 4LL);
  if ( !*(_DWORD *)(v5 + a2 + 16) )
  {
    v6 = *(_QWORD *)(v5 + a2 + 80);
    if ( v6 )
    {
      if ( *(_QWORD *)(*(int *)(*(_QWORD *)v6 + 4LL) + v6 + 72) )
      {
        std::basic_ostream<unsigned short>::sentry::sentry(&v10, v6);
        if ( v11 )
        {
          v7 = *(_QWORD *)(*(int *)(*(_QWORD *)v6 + 4LL) + v6 + 72);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 104LL))(v7) == -1 )
            std::basic_ios<unsigned short>::setstate(v6 + *(int *)(*(_QWORD *)v6 + 4LL), 4);
        }
        if ( !std::uncaught_exception() )
          std::basic_ostream<unsigned short>::_Osfx(v10);
        v8 = *(_QWORD *)(*(int *)(*(_QWORD *)v10 + 4LL) + v10 + 72);
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
  }
  *(_BYTE *)(a1 + 8) = *(_DWORD *)(*(int *)(*(_QWORD *)a2 + 4LL) + a2 + 16) == 0;
  return a1;
}

```

## disassembly

```asm
0x1800075d8  mov     [rsp+arg_8], rbx
0x1800075dd  mov     [rsp+arg_10], rsi
0x1800075e2  mov     [rsp+arg_0], rcx
0x1800075e7  push    rdi
0x1800075e8  sub     rsp, 30h
0x1800075ec  mov     rbx, rdx
0x1800075ef  mov     rsi, rcx
0x1800075f2  mov     [rcx], rdx
0x1800075f5  mov     rax, [rdx]
0x1800075f8  movsxd  r8, dword ptr [rax+4]
0x1800075fc  mov     rcx, [r8+rdx+48h]
0x180007601  test    rcx, rcx
0x180007604  jz      short loc_180007613
0x180007606  mov     rax, [rcx]
0x180007609  mov     rax, [rax+8]
0x18000760d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007612  nop
0x180007613  mov     rax, [rbx]
0x180007616  movsxd  rdi, dword ptr [rax+4]
0x18000761a  cmp     dword ptr [rdi+rbx+10h], 0
0x18000761f  jnz     loc_1800076C6
0x180007625  mov     rdi, [rdi+rbx+50h]
0x18000762a  test    rdi, rdi
0x18000762d  jz      loc_1800076C6
0x180007633  mov     rax, [rdi]
0x180007636  movsxd  rcx, dword ptr [rax+4]
0x18000763a  cmp     qword ptr [rcx+rdi+48h], 0
0x180007640  jz      loc_1800076C6
0x180007646  mov     rdx, rdi
0x180007649  lea     rcx, [rsp+38h+var_18]
0x18000764e  call    ??0sentry@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAA@AEAV12@@Z; std::basic_ostream<ushort>::sentry::sentry(std::basic_ostream<ushort> &)
0x180007653  nop
0x180007654  cmp     [rsp+38h+var_10], 0
0x180007659  jz      short loc_18000768F
0x18000765b  mov     rax, [rdi]
0x18000765e  movsxd  rcx, dword ptr [rax+4]
0x180007662  mov     rcx, [rcx+rdi+48h]
0x180007667  mov     rax, [rcx]
0x18000766a  mov     rax, [rax+68h]
0x18000766e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007673  cmp     eax, 0FFFFFFFFh
0x180007676  jnz     short loc_18000768F
0x180007678  mov     rax, [rdi]
0x18000767b  movsxd  rcx, dword ptr [rax+4]
0x18000767f  add     rcx, rdi
0x180007682  xor     r8d, r8d
0x180007685  lea     edx, [r8+4]
0x180007689  call    ?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18000768e  nop
0x18000768f  call    ?uncaught_exception@std@@YA_NXZ; std::uncaught_exception(void)
0x180007694  test    al, al
0x180007696  jnz     short loc_1800076A3
0x180007698  mov     rcx, [rsp+38h+var_18]
0x18000769d  call    ?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ostream<ushort>::_Osfx(void)
0x1800076a2  nop
0x1800076a3  mov     rdx, [rsp+38h+var_18]
0x1800076a8  mov     rax, [rdx]
0x1800076ab  movsxd  rcx, dword ptr [rax+4]
0x1800076af  mov     rcx, [rcx+rdx+48h]
0x1800076b4  test    rcx, rcx
0x1800076b7  jz      short loc_1800076C6
0x1800076b9  mov     rax, [rcx]
0x1800076bc  mov     rax, [rax+10h]
0x1800076c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076c5  nop
0x1800076c6  mov     rax, [rbx]
0x1800076c9  movsxd  rcx, dword ptr [rax+4]
0x1800076cd  cmp     dword ptr [rcx+rbx+10h], 0
0x1800076d2  setz    al
0x1800076d5  mov     [rsi+8], al
0x1800076d8  mov     rax, rsi
0x1800076db  mov     rbx, [rsp+38h+arg_8]
0x1800076e0  mov     rsi, [rsp+38h+arg_10]
0x1800076e5  add     rsp, 30h
0x1800076e9  pop     rdi
0x1800076ea  retn
```
