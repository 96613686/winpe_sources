# CLTPartitionRoles::GetSimpleMeta(ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0001 * *,ulong *)

- ea: `0x18004f364`
- end: `0x18004f5ec`
- name: `?GetSimpleMeta@CLTPartitionRoles@@AEAAJPEAUISimpleTableDispenser@@PEAPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@PEAK@Z`
- size: `648`
- prototype: `__int64 __fastcall(CLTPartitionRoles *__hidden this, struct ISimpleTableDispenser *, struct __MIDL___MIDL_itf_stable_0000_0000_0001 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f600`

## callees

- `0x18004f364`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f5c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f5c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f496`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f496`

## pseudocode

```c
__int64 __fastcall CLTPartitionRoles::GetSimpleMeta(
        CLTPartitionRoles *this,
        struct ISimpleTableDispenser *a2,
        LPVOID *a3,
        unsigned int *a4)
{
  int v7; // ebx
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 *v8; // rax
  __int64 i; // rsi
  int v10; // eax
  __int64 *v11; // [rsp+58h] [rbp-18h] BYREF
  int v12; // [rsp+60h] [rbp-10h]
  int v13; // [rsp+64h] [rbp-Ch]
  int v14; // [rsp+68h] [rbp-8h]
  int v15; // [rsp+6Ch] [rbp-4h]
  CLTPartitionRoles *v16; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+40h] BYREF

  v16 = this;
  v17 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v11 = tidCOMSERVICES_LT_PARTITIONROLES;
  v12 = 0;
  v13 = -268435450;
  v14 = 72;
  v15 = 16;
  LODWORD(v16) = 0;
  v7 = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, __int64 *, __int64 **, __int64, int, int, __int64 *))(*(_QWORD *)a2 + 24LL))(
         a2,
         &didCOMSERVICES,
         tidMETA,
         &v11,
         1,
         1,
         3,
         &v17);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
    if ( v7 >= 0 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, CLTPartitionRoles **, _QWORD))(*(_QWORD *)v17 + 72LL))(
        v17,
        0,
        0,
        0,
        0,
        0,
        0,
        &v16,
        0);
      v8 = (struct __MIDL___MIDL_itf_stable_0000_0000_0001 *)CoTaskMemAlloc(saturated_mul((unsigned int)v16, 0xCu));
      *a3 = v8;
      if ( v8 )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
          if ( v10 )
            break;
          if ( (unsigned int)i >= (unsigned int)v16 )
          {
            v7 = -2147418113;
            goto LABEL_18;
          }
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v17 + 64LL))(v17, 1, 0);
          if ( v7 < 0 )
            goto LABEL_18;
          *((_DWORD *)*a3 + 3 * i) = MEMORY[0];
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v17 + 64LL))(v17, 2, 0);
          if ( v7 < 0 )
            goto LABEL_18;
          *((_DWORD *)*a3 + 3 * i + 1) = MEMORY[0];
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v17 + 64LL))(v17, 3, 0);
          if ( v7 < 0 )
            goto LABEL_18;
          *((_DWORD *)*a3 + 3 * i + 2) = MEMORY[0];
        }
        v7 = 0;
        if ( v10 != -2146367487 )
          v7 = v10;
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
LABEL_18:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  *a4 = (unsigned int)v16;
  if ( v7 < 0 )
  {
    CoTaskMemFree(*a3);
    *a3 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004f364  mov     [rsp-28h+arg_8], rbx
0x18004f369  mov     [rsp-28h+arg_0], rcx
0x18004f36e  push    rbp
0x18004f36f  push    rsi
0x18004f370  push    rdi
0x18004f371  push    r14
0x18004f373  push    r15
0x18004f375  mov     rbp, rsp
0x18004f378  sub     rsp, 70h
0x18004f37c  mov     r15, r9
0x18004f37f  mov     rdi, r8
0x18004f382  mov     r10, rdx
0x18004f385  mov     [rbp+arg_10], 0
0x18004f38d  test    r8, r8
0x18004f390  jnz     short loc_18004F39C
0x18004f392  mov     eax, 80004003h
0x18004f397  jmp     loc_18004F5D8
0x18004f39c  mov     qword ptr [r8], 0
0x18004f3a3  lea     rax, tidCOMSERVICES_LT_PARTITIONROLES
0x18004f3aa  mov     [rbp+var_18], rax
0x18004f3ae  mov     [rbp+var_10], 0
0x18004f3b5  mov     [rbp+var_C], 0F0000006h
0x18004f3bc  mov     [rbp+var_8], 48h ; 'H'
0x18004f3c3  mov     [rbp+var_4], 10h
0x18004f3ca  mov     dword ptr [rbp+arg_0], 0
0x18004f3d1  mov     rax, [rdx]
0x18004f3d4  lea     rcx, [rbp+arg_10]
0x18004f3d8  mov     [rsp+70h+var_38], rcx
0x18004f3dd  mov     dword ptr [rsp+70h+var_40], 3
0x18004f3e5  mov     dword ptr [rsp+70h+var_48], 1
0x18004f3ed  mov     [rsp+70h+var_50], 1
0x18004f3f6  lea     r9, [rbp+var_18]
0x18004f3fa  lea     r8, tidMETA
0x18004f401  lea     rdx, didCOMSERVICES
0x18004f408  mov     rcx, r10
0x18004f40b  mov     rax, [rax+18h]
0x18004f40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f414  mov     ebx, eax
0x18004f416  test    eax, eax
0x18004f418  js      loc_18004F59E
0x18004f41e  mov     rcx, [rbp+arg_10]
0x18004f422  mov     rax, [rcx]
0x18004f425  mov     rax, [rax+18h]
0x18004f429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f42e  mov     ebx, eax
0x18004f430  test    eax, eax
0x18004f432  js      loc_18004F59E
0x18004f438  mov     rcx, [rbp+arg_10]
0x18004f43c  mov     rax, [rcx]
0x18004f43f  mov     [rsp+70h+var_30], 0
0x18004f448  lea     rdx, [rbp+arg_0]
0x18004f44c  mov     [rsp+70h+var_38], rdx
0x18004f451  mov     [rsp+70h+var_40], 0
0x18004f45a  mov     [rsp+70h+var_48], 0
0x18004f463  mov     [rsp+70h+var_50], 0
0x18004f46c  xor     r9d, r9d
0x18004f46f  xor     r8d, r8d
0x18004f472  xor     edx, edx
0x18004f474  mov     rax, [rax+48h]
0x18004f478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f47d  mov     ecx, dword ptr [rbp+arg_0]
0x18004f480  mov     eax, 0Ch
0x18004f485  mul     rcx
0x18004f488  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f48f  cmovb   rax, rcx
0x18004f493  mov     rcx, rax; cb
0x18004f496  call    cs:__imp_CoTaskMemAlloc
0x18004f49c  mov     [rdi], rax
0x18004f49f  test    rax, rax
0x18004f4a2  jz      loc_18004F599
0x18004f4a8  xor     esi, esi
0x18004f4aa  mov     rcx, [rbp+arg_10]
0x18004f4ae  mov     rax, [rcx]
0x18004f4b1  mov     rax, [rax+28h]
0x18004f4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4ba  test    eax, eax
0x18004f4bc  jnz     loc_18004F58D
0x18004f4c2  cmp     esi, dword ptr [rbp+arg_0]
0x18004f4c5  jnb     loc_18004F586
0x18004f4cb  mov     [rbp+var_20], 0
0x18004f4d3  mov     rcx, [rbp+arg_10]
0x18004f4d7  mov     rax, [rcx]
0x18004f4da  lea     rdx, [rbp+var_20]
0x18004f4de  mov     [rsp+70h+var_50], rdx
0x18004f4e3  xor     r9d, r9d
0x18004f4e6  xor     r8d, r8d
0x18004f4e9  lea     edx, [r9+1]
0x18004f4ed  mov     rax, [rax+40h]
0x18004f4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4f6  mov     ebx, eax
0x18004f4f8  test    eax, eax
0x18004f4fa  js      loc_18004F59E
0x18004f500  lea     r14, [rsi+rsi*2]
0x18004f504  mov     rdx, [rdi]
0x18004f507  mov     rax, [rbp+var_20]
0x18004f50b  mov     ecx, [rax]
0x18004f50d  mov     [rdx+r14*4], ecx
0x18004f511  mov     rcx, [rbp+arg_10]
0x18004f515  mov     rax, [rcx]
0x18004f518  lea     rdx, [rbp+var_20]
0x18004f51c  mov     [rsp+70h+var_50], rdx
0x18004f521  xor     r9d, r9d
0x18004f524  xor     r8d, r8d
0x18004f527  lea     edx, [r9+2]
0x18004f52b  mov     rax, [rax+40h]
0x18004f52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f534  mov     ebx, eax
0x18004f536  test    eax, eax
0x18004f538  js      short loc_18004F59E
0x18004f53a  mov     rdx, [rdi]
0x18004f53d  mov     rax, [rbp+var_20]
0x18004f541  mov     ecx, [rax]
0x18004f543  mov     [rdx+r14*4+4], ecx
0x18004f548  mov     rcx, [rbp+arg_10]
0x18004f54c  mov     rax, [rcx]
0x18004f54f  lea     rdx, [rbp+var_20]
0x18004f553  mov     [rsp+70h+var_50], rdx
0x18004f558  xor     r9d, r9d
0x18004f55b  xor     r8d, r8d
0x18004f55e  lea     edx, [r9+3]
0x18004f562  mov     rax, [rax+40h]
0x18004f566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f56b  mov     ebx, eax
0x18004f56d  test    eax, eax
0x18004f56f  js      short loc_18004F59E
0x18004f571  mov     rdx, [rdi]
0x18004f574  mov     rax, [rbp+var_20]
0x18004f578  mov     ecx, [rax]
0x18004f57a  mov     [rdx+r14*4+8], ecx
0x18004f57f  inc     esi
0x18004f581  jmp     loc_18004F4AA
0x18004f586  mov     ebx, 8000FFFFh
0x18004f58b  jmp     short loc_18004F59E
0x18004f58d  xor     ebx, ebx
0x18004f58f  cmp     eax, 80110801h
0x18004f594  cmovnz  ebx, eax
0x18004f597  jmp     short loc_18004F59E
0x18004f599  mov     ebx, 8007000Eh
0x18004f59e  mov     rcx, [rbp+arg_10]
0x18004f5a2  test    rcx, rcx
0x18004f5a5  jz      short loc_18004F5BB
0x18004f5a7  mov     rax, [rcx]
0x18004f5aa  mov     rax, [rax+10h]
0x18004f5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5b3  mov     [rbp+arg_10], 0
0x18004f5bb  mov     eax, dword ptr [rbp+arg_0]
0x18004f5be  mov     [r15], eax
0x18004f5c1  test    ebx, ebx
0x18004f5c3  jns     short loc_18004F5D6
0x18004f5c5  mov     rcx, [rdi]; pv
0x18004f5c8  call    cs:__imp_CoTaskMemFree
0x18004f5ce  nop
0x18004f5cf  mov     qword ptr [rdi], 0
0x18004f5d6  mov     eax, ebx
0x18004f5d8  mov     rbx, [rsp+70h+arg_8]
0x18004f5e0  add     rsp, 70h
0x18004f5e4  pop     r15
0x18004f5e6  pop     r14
0x18004f5e8  pop     rdi
0x18004f5e9  pop     rsi
0x18004f5ea  pop     rbp
0x18004f5eb  retn
```
