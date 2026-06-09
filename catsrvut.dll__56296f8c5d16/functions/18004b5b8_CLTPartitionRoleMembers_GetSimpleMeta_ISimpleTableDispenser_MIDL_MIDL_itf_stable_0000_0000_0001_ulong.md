# CLTPartitionRoleMembers::GetSimpleMeta(ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0001 * *,ulong *)

- ea: `0x18004b5b8`
- end: `0x18004b840`
- name: `?GetSimpleMeta@CLTPartitionRoleMembers@@AEAAJPEAUISimpleTableDispenser@@PEAPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@PEAK@Z`
- size: `648`
- prototype: `__int64 __fastcall(CLTPartitionRoleMembers *__hidden this, struct ISimpleTableDispenser *, struct __MIDL___MIDL_itf_stable_0000_0000_0001 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b850`

## callees

- `0x18004b5b8`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b81c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b81c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b6ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004b6ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTPartitionRoleMembers::GetSimpleMeta(
        CLTPartitionRoleMembers *this,
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
  CLTPartitionRoleMembers *v16; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+B0h] [rbp+40h] BYREF

  v16 = this;
  v17 = 0;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v11 = tidCOMSERVICES_LT_PARTITIONROLEMEMBERS;
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
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, CLTPartitionRoleMembers **, _QWORD))(*(_QWORD *)v17 + 72LL))(
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
0x18004b5b8  mov     [rsp-28h+arg_8], rbx
0x18004b5bd  mov     [rsp-28h+arg_0], rcx
0x18004b5c2  push    rbp
0x18004b5c3  push    rsi
0x18004b5c4  push    rdi
0x18004b5c5  push    r14
0x18004b5c7  push    r15
0x18004b5c9  mov     rbp, rsp
0x18004b5cc  sub     rsp, 70h
0x18004b5d0  mov     r15, r9
0x18004b5d3  mov     rdi, r8
0x18004b5d6  mov     r10, rdx
0x18004b5d9  mov     [rbp+arg_10], 0
0x18004b5e1  test    r8, r8
0x18004b5e4  jnz     short loc_18004B5F0
0x18004b5e6  mov     eax, 80004003h
0x18004b5eb  jmp     loc_18004B82C
0x18004b5f0  mov     qword ptr [r8], 0
0x18004b5f7  lea     rax, tidCOMSERVICES_LT_PARTITIONROLEMEMBERS
0x18004b5fe  mov     [rbp+var_18], rax
0x18004b602  mov     [rbp+var_10], 0
0x18004b609  mov     [rbp+var_C], 0F0000006h
0x18004b610  mov     [rbp+var_8], 48h ; 'H'
0x18004b617  mov     [rbp+var_4], 10h
0x18004b61e  mov     dword ptr [rbp+arg_0], 0
0x18004b625  mov     rax, [rdx]
0x18004b628  lea     rcx, [rbp+arg_10]
0x18004b62c  mov     [rsp+70h+var_38], rcx
0x18004b631  mov     dword ptr [rsp+70h+var_40], 3
0x18004b639  mov     dword ptr [rsp+70h+var_48], 1
0x18004b641  mov     [rsp+70h+var_50], 1
0x18004b64a  lea     r9, [rbp+var_18]
0x18004b64e  lea     r8, tidMETA
0x18004b655  lea     rdx, didCOMSERVICES
0x18004b65c  mov     rcx, r10
0x18004b65f  mov     rax, [rax+18h]
0x18004b663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b668  mov     ebx, eax
0x18004b66a  test    eax, eax
0x18004b66c  js      loc_18004B7F2
0x18004b672  mov     rcx, [rbp+arg_10]
0x18004b676  mov     rax, [rcx]
0x18004b679  mov     rax, [rax+18h]
0x18004b67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b682  mov     ebx, eax
0x18004b684  test    eax, eax
0x18004b686  js      loc_18004B7F2
0x18004b68c  mov     rcx, [rbp+arg_10]
0x18004b690  mov     rax, [rcx]
0x18004b693  mov     [rsp+70h+var_30], 0
0x18004b69c  lea     rdx, [rbp+arg_0]
0x18004b6a0  mov     [rsp+70h+var_38], rdx
0x18004b6a5  mov     [rsp+70h+var_40], 0
0x18004b6ae  mov     [rsp+70h+var_48], 0
0x18004b6b7  mov     [rsp+70h+var_50], 0
0x18004b6c0  xor     r9d, r9d
0x18004b6c3  xor     r8d, r8d
0x18004b6c6  xor     edx, edx
0x18004b6c8  mov     rax, [rax+48h]
0x18004b6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b6d1  mov     ecx, dword ptr [rbp+arg_0]
0x18004b6d4  mov     eax, 0Ch
0x18004b6d9  mul     rcx
0x18004b6dc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004b6e3  cmovb   rax, rcx
0x18004b6e7  mov     rcx, rax; cb
0x18004b6ea  call    cs:__imp_CoTaskMemAlloc
0x18004b6f0  mov     [rdi], rax
0x18004b6f3  test    rax, rax
0x18004b6f6  jz      loc_18004B7ED
0x18004b6fc  xor     esi, esi
0x18004b6fe  mov     rcx, [rbp+arg_10]
0x18004b702  mov     rax, [rcx]
0x18004b705  mov     rax, [rax+28h]
0x18004b709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b70e  test    eax, eax
0x18004b710  jnz     loc_18004B7E1
0x18004b716  cmp     esi, dword ptr [rbp+arg_0]
0x18004b719  jnb     loc_18004B7DA
0x18004b71f  mov     [rbp+var_20], 0
0x18004b727  mov     rcx, [rbp+arg_10]
0x18004b72b  mov     rax, [rcx]
0x18004b72e  lea     rdx, [rbp+var_20]
0x18004b732  mov     [rsp+70h+var_50], rdx
0x18004b737  xor     r9d, r9d
0x18004b73a  xor     r8d, r8d
0x18004b73d  lea     edx, [r9+1]
0x18004b741  mov     rax, [rax+40h]
0x18004b745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b74a  mov     ebx, eax
0x18004b74c  test    eax, eax
0x18004b74e  js      loc_18004B7F2
0x18004b754  lea     r14, [rsi+rsi*2]
0x18004b758  mov     rdx, [rdi]
0x18004b75b  mov     rax, [rbp+var_20]
0x18004b75f  mov     ecx, [rax]
0x18004b761  mov     [rdx+r14*4], ecx
0x18004b765  mov     rcx, [rbp+arg_10]
0x18004b769  mov     rax, [rcx]
0x18004b76c  lea     rdx, [rbp+var_20]
0x18004b770  mov     [rsp+70h+var_50], rdx
0x18004b775  xor     r9d, r9d
0x18004b778  xor     r8d, r8d
0x18004b77b  lea     edx, [r9+2]
0x18004b77f  mov     rax, [rax+40h]
0x18004b783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b788  mov     ebx, eax
0x18004b78a  test    eax, eax
0x18004b78c  js      short loc_18004B7F2
0x18004b78e  mov     rdx, [rdi]
0x18004b791  mov     rax, [rbp+var_20]
0x18004b795  mov     ecx, [rax]
0x18004b797  mov     [rdx+r14*4+4], ecx
0x18004b79c  mov     rcx, [rbp+arg_10]
0x18004b7a0  mov     rax, [rcx]
0x18004b7a3  lea     rdx, [rbp+var_20]
0x18004b7a7  mov     [rsp+70h+var_50], rdx
0x18004b7ac  xor     r9d, r9d
0x18004b7af  xor     r8d, r8d
0x18004b7b2  lea     edx, [r9+3]
0x18004b7b6  mov     rax, [rax+40h]
0x18004b7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7bf  mov     ebx, eax
0x18004b7c1  test    eax, eax
0x18004b7c3  js      short loc_18004B7F2
0x18004b7c5  mov     rdx, [rdi]
0x18004b7c8  mov     rax, [rbp+var_20]
0x18004b7cc  mov     ecx, [rax]
0x18004b7ce  mov     [rdx+r14*4+8], ecx
0x18004b7d3  inc     esi
0x18004b7d5  jmp     loc_18004B6FE
0x18004b7da  mov     ebx, 8000FFFFh
0x18004b7df  jmp     short loc_18004B7F2
0x18004b7e1  xor     ebx, ebx
0x18004b7e3  cmp     eax, 80110801h
0x18004b7e8  cmovnz  ebx, eax
0x18004b7eb  jmp     short loc_18004B7F2
0x18004b7ed  mov     ebx, 8007000Eh
0x18004b7f2  mov     rcx, [rbp+arg_10]
0x18004b7f6  test    rcx, rcx
0x18004b7f9  jz      short loc_18004B80F
0x18004b7fb  mov     rax, [rcx]
0x18004b7fe  mov     rax, [rax+10h]
0x18004b802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b807  mov     [rbp+arg_10], 0
0x18004b80f  mov     eax, dword ptr [rbp+arg_0]
0x18004b812  mov     [r15], eax
0x18004b815  test    ebx, ebx
0x18004b817  jns     short loc_18004B82A
0x18004b819  mov     rcx, [rdi]; pv
0x18004b81c  call    cs:__imp_CoTaskMemFree
0x18004b822  nop
0x18004b823  mov     qword ptr [rdi], 0
0x18004b82a  mov     eax, ebx
0x18004b82c  mov     rbx, [rsp+70h+arg_8]
0x18004b834  add     rsp, 70h
0x18004b838  pop     r15
0x18004b83a  pop     r14
0x18004b83c  pop     rdi
0x18004b83d  pop     rsi
0x18004b83e  pop     rbp
0x18004b83f  retn
```
