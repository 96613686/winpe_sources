# CLTPartitionUsers::GetSimpleMeta(ISimpleTableDispenser *,ulong *)

- ea: `0x18004e1a0`
- end: `0x18004e404`
- name: `?GetSimpleMeta@CLTPartitionUsers@@CAPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@PEAUISimpleTableDispenser@@PEAK@Z`
- size: `612`
- prototype: `struct __MIDL___MIDL_itf_stable_0000_0000_0001 *__fastcall(struct ISimpleTableDispenser *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004e410`

## callees

- `0x18004e1a0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e3c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e2b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e2b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct __MIDL___MIDL_itf_stable_0000_0000_0001 *__fastcall CLTPartitionUsers::GetSimpleMeta(
        struct ISimpleTableDispenser *a1,
        unsigned int *a2)
{
  unsigned int i; // ebx
  int v4; // ecx
  int v5; // eax
  _DWORD *v6; // rsi
  __int64 v7; // rdi
  __int64 *v9; // [rsp+50h] [rbp-20h] BYREF
  int v10; // [rsp+58h] [rbp-18h]
  int v11; // [rsp+5Ch] [rbp-14h]
  int v12; // [rsp+60h] [rbp-10h]
  int v13; // [rsp+64h] [rbp-Ch]
  __int64 v14; // [rsp+B0h] [rbp+40h] BYREF
  _DWORD *v15; // [rsp+B8h] [rbp+48h]

  v9 = tidCOMSERVICES_LT_PARTITION_USERS;
  v10 = 0;
  v11 = -268435450;
  v12 = 72;
  v13 = 16;
  if ( !CLTPartitionUsers::s_ColumnMeta )
  {
    v14 = 0;
    if ( (*(int (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, __int64 *, __int64 **, __int64, int, int, __int64 *))(*(_QWORD *)a1 + 24LL))(
           a1,
           &didCOMSERVICES,
           tidMETA,
           &v9,
           1,
           1,
           3,
           &v14) >= 0
      && (*(int (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14) >= 0
      && (*(int (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14) >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
        if ( v4 )
          break;
      }
      v5 = 0;
      if ( v4 != -2146367487 )
        v5 = v4;
      if ( v5 >= 0 )
      {
        v6 = CoTaskMemAlloc(saturated_mul(i, 0xCu));
        if ( !v6 )
          goto LABEL_21;
        if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v14 + 32LL))(v14) >= 0 )
        {
          v7 = 0;
          while ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14) )
          {
            if ( (unsigned int)v7 >= i )
              goto LABEL_23;
            v15 = 0;
            if ( (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v14 + 64LL))(v14, 1, 0) < 0 )
              goto LABEL_23;
            v6[3 * v7] = *v15;
            if ( (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v14 + 64LL))(v14, 2, 0) < 0 )
              goto LABEL_23;
            v6[3 * v7 + 1] = *v15;
            if ( (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v14 + 64LL))(v14, 3, 0) < 0 )
              goto LABEL_23;
            v6[3 * v7 + 2] = *v15;
            v7 = (unsigned int)(v7 + 1);
          }
          if ( (_DWORD)v7 == i )
          {
LABEL_21:
            CLTPartitionUsers::s_cMetaRows = i;
            if ( _InterlockedCompareExchange64(
                   (volatile signed __int64 *)&CLTPartitionUsers::s_ColumnMeta,
                   (signed __int64)v6,
                   0) )
            {
              CoTaskMemFree(v6);
            }
          }
        }
      }
    }
LABEL_23:
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  *a2 = CLTPartitionUsers::s_cMetaRows;
  return CLTPartitionUsers::s_ColumnMeta;
}

```

## disassembly

```asm
0x18004e1a0  mov     [rsp-28h+arg_0], rbx
0x18004e1a5  push    rbp
0x18004e1a6  push    rsi
0x18004e1a7  push    rdi
0x18004e1a8  push    r14
0x18004e1aa  push    r15
0x18004e1ac  mov     rbp, rsp
0x18004e1af  sub     rsp, 70h
0x18004e1b3  mov     r15, rdx
0x18004e1b6  lea     rax, tidCOMSERVICES_LT_PARTITION_USERS
0x18004e1bd  mov     [rbp+var_20], rax
0x18004e1c1  mov     [rbp+var_18], 0
0x18004e1c8  mov     [rbp+var_14], 0F0000006h
0x18004e1cf  mov     [rbp+var_10], 48h ; 'H'
0x18004e1d6  mov     [rbp+var_C], 10h
0x18004e1dd  cmp     cs:?s_ColumnMeta@CLTPartitionUsers@@0PEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@EA, 0; __MIDL___MIDL_itf_stable_0000_0000_0001 * CLTPartitionUsers::s_ColumnMeta
0x18004e1e5  jnz     loc_18004E3E0
0x18004e1eb  mov     [rbp+arg_10], 0
0x18004e1f3  mov     rax, [rcx]
0x18004e1f6  lea     rdx, [rbp+arg_10]
0x18004e1fa  mov     [rsp+70h+var_38], rdx
0x18004e1ff  mov     [rsp+70h+var_40], 3
0x18004e207  mov     [rsp+70h+var_48], 1
0x18004e20f  mov     [rsp+70h+var_50], 1
0x18004e218  lea     r9, [rbp+var_20]
0x18004e21c  lea     r8, tidMETA
0x18004e223  lea     rdx, didCOMSERVICES
0x18004e22a  mov     rax, [rax+18h]
0x18004e22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e233  test    eax, eax
0x18004e235  js      loc_18004E3CB
0x18004e23b  mov     rcx, [rbp+arg_10]
0x18004e23f  mov     rax, [rcx]
0x18004e242  mov     rax, [rax+18h]
0x18004e246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e24b  test    eax, eax
0x18004e24d  js      loc_18004E3CB
0x18004e253  mov     rcx, [rbp+arg_10]
0x18004e257  mov     rax, [rcx]
0x18004e25a  mov     rax, [rax+20h]
0x18004e25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e263  test    eax, eax
0x18004e265  js      loc_18004E3CB
0x18004e26b  xor     ebx, ebx
0x18004e26d  mov     rcx, [rbp+arg_10]
0x18004e271  mov     rax, [rcx]
0x18004e274  mov     rax, [rax+28h]
0x18004e278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e27d  mov     ecx, eax
0x18004e27f  test    eax, eax
0x18004e281  jnz     short loc_18004E287
0x18004e283  inc     ebx
0x18004e285  jmp     short loc_18004E26D
0x18004e287  xor     eax, eax
0x18004e289  cmp     ecx, 80110801h
0x18004e28f  cmovnz  eax, ecx
0x18004e292  test    eax, eax
0x18004e294  js      loc_18004E3CB
0x18004e29a  mov     ecx, ebx
0x18004e29c  mov     eax, 0Ch
0x18004e2a1  mul     rcx
0x18004e2a4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004e2ab  cmovb   rax, rcx
0x18004e2af  mov     rcx, rax; cb
0x18004e2b2  call    cs:__imp_CoTaskMemAlloc
0x18004e2b8  mov     rsi, rax
0x18004e2bb  test    rax, rax
0x18004e2be  jz      loc_18004E3AE
0x18004e2c4  mov     rcx, [rbp+arg_10]
0x18004e2c8  mov     rdx, [rcx]
0x18004e2cb  mov     rax, [rdx+20h]
0x18004e2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2d4  test    eax, eax
0x18004e2d6  js      loc_18004E3CB
0x18004e2dc  xor     edi, edi
0x18004e2de  mov     rcx, [rbp+arg_10]
0x18004e2e2  mov     rax, [rcx]
0x18004e2e5  mov     rax, [rax+28h]
0x18004e2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2ee  test    eax, eax
0x18004e2f0  jnz     loc_18004E3AA
0x18004e2f6  cmp     edi, ebx
0x18004e2f8  jnb     loc_18004E3CB
0x18004e2fe  mov     [rbp+arg_18], 0
0x18004e306  mov     rcx, [rbp+arg_10]
0x18004e30a  mov     rax, [rcx]
0x18004e30d  lea     rdx, [rbp+arg_18]
0x18004e311  mov     [rsp+70h+var_50], rdx
0x18004e316  xor     r9d, r9d
0x18004e319  xor     r8d, r8d
0x18004e31c  lea     edx, [r9+1]
0x18004e320  mov     rax, [rax+40h]
0x18004e324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e329  test    eax, eax
0x18004e32b  js      loc_18004E3CB
0x18004e331  lea     r14, [rdi+rdi*2]
0x18004e335  mov     rax, [rbp+arg_18]
0x18004e339  mov     ecx, [rax]
0x18004e33b  mov     [rsi+r14*4], ecx
0x18004e33f  mov     rcx, [rbp+arg_10]
0x18004e343  mov     rax, [rcx]
0x18004e346  lea     rdx, [rbp+arg_18]
0x18004e34a  mov     [rsp+70h+var_50], rdx
0x18004e34f  xor     r9d, r9d
0x18004e352  xor     r8d, r8d
0x18004e355  lea     edx, [r9+2]
0x18004e359  mov     rax, [rax+40h]
0x18004e35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e362  test    eax, eax
0x18004e364  js      short loc_18004E3CB
0x18004e366  mov     rax, [rbp+arg_18]
0x18004e36a  mov     ecx, [rax]
0x18004e36c  mov     [rsi+r14*4+4], ecx
0x18004e371  mov     rcx, [rbp+arg_10]
0x18004e375  mov     rax, [rcx]
0x18004e378  lea     rdx, [rbp+arg_18]
0x18004e37c  mov     [rsp+70h+var_50], rdx
0x18004e381  xor     r9d, r9d
0x18004e384  xor     r8d, r8d
0x18004e387  lea     edx, [r9+3]
0x18004e38b  mov     rax, [rax+40h]
0x18004e38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e394  test    eax, eax
0x18004e396  js      short loc_18004E3CB
0x18004e398  mov     rax, [rbp+arg_18]
0x18004e39c  mov     ecx, [rax]
0x18004e39e  mov     [rsi+r14*4+8], ecx
0x18004e3a3  inc     edi
0x18004e3a5  jmp     loc_18004E2DE
0x18004e3aa  cmp     edi, ebx
0x18004e3ac  jnz     short loc_18004E3CB
0x18004e3ae  mov     cs:?s_cMetaRows@CLTPartitionUsers@@0KA, ebx; ulong CLTPartitionUsers::s_cMetaRows
0x18004e3b4  xor     eax, eax
0x18004e3b6  lock cmpxchg cs:?s_ColumnMeta@CLTPartitionUsers@@0PEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@EA, rsi; __MIDL___MIDL_itf_stable_0000_0000_0001 * CLTPartitionUsers::s_ColumnMeta
0x18004e3bf  jz      short loc_18004E3CB
0x18004e3c1  mov     rcx, rsi; pv
0x18004e3c4  call    cs:__imp_CoTaskMemFree
0x18004e3ca  nop
0x18004e3cb  mov     rcx, [rbp+arg_10]
0x18004e3cf  test    rcx, rcx
0x18004e3d2  jz      short loc_18004E3E0
0x18004e3d4  mov     rax, [rcx]
0x18004e3d7  mov     rax, [rax+10h]
0x18004e3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3e0  mov     eax, cs:?s_cMetaRows@CLTPartitionUsers@@0KA; ulong CLTPartitionUsers::s_cMetaRows
0x18004e3e6  mov     [r15], eax
0x18004e3e9  mov     rax, cs:?s_ColumnMeta@CLTPartitionUsers@@0PEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@EA; __MIDL___MIDL_itf_stable_0000_0000_0001 * CLTPartitionUsers::s_ColumnMeta
0x18004e3f0  mov     rbx, [rsp+70h+arg_0]
0x18004e3f8  add     rsp, 70h
0x18004e3fc  pop     r15
0x18004e3fe  pop     r14
0x18004e400  pop     rdi
0x18004e401  pop     rsi
0x18004e402  pop     rbp
0x18004e403  retn
```
