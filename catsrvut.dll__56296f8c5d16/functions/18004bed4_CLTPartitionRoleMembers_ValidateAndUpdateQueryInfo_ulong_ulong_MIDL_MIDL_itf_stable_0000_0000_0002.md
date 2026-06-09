# CLTPartitionRoleMembers::ValidateAndUpdateQueryInfo(ulong,ulong,__MIDL___MIDL_itf_stable_0000_0000_0002 *)

- ea: `0x18004bed4`
- end: `0x18004c263`
- name: `?ValidateAndUpdateQueryInfo@CLTPartitionRoleMembers@@AEAAJKKPEAU__MIDL___MIDL_itf_stable_0000_0000_0002@@@Z`
- size: `911`
- prototype: `__int64 __fastcall(CLTPartitionRoleMembers *__hidden this, unsigned int, unsigned int, struct __MIDL___MIDL_itf_stable_0000_0000_0002 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004b850`

## callees

- `0x180001e60`
- `0x18000717c`
- `0x180015594`
- `0x18004bed4`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bf70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bf84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bf70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004bf84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004bff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c170`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTPartitionRoleMembers::ValidateAndUpdateQueryInfo(
        CLTPartitionRoleMembers *this,
        __int64 a2,
        unsigned int a3,
        struct __MIDL___MIDL_itf_stable_0000_0000_0002 *a4)
{
  GUID *v7; // r13
  __int64 i; // rsi
  int v9; // ebx
  void *v10; // rcx
  void *v11; // rcx
  __int64 v12; // r8
  int v13; // ecx
  const unsigned __int16 *v14; // rcx
  unsigned int v15; // ebx
  SIZE_T v16; // r8
  SIZE_T v17; // rax
  unsigned __int16 *v18; // rax
  _OWORD *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
  unsigned __int16 *v25; // rax
  unsigned __int16 *v27; // [rsp+50h] [rbp-28h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-20h] BYREF
  int v29; // [rsp+68h] [rbp-10h]
  int v30; // [rsp+6Ch] [rbp-Ch]
  __int64 v31; // [rsp+C0h] [rbp+48h] BYREF

  v31 = 0;
  v27 = 0;
  v7 = (GUID *)((char *)this + 64);
  v28[0] = (char *)this + 64;
  v28[1] = 0;
  v29 = 72;
  v30 = 16;
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    if ( *((_DWORD *)a4 + 6 * i + 3) <= 0xF0000000 )
      break;
  }
  if ( (_DWORD)a2 != 1 || a3 - (_DWORD)i != 2 )
    return 2147942487LL;
  v9 = 0;
  *v7 = GUID_NULL;
  v10 = (void *)*((_QWORD *)this + 10);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 10) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 11);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    *((_QWORD *)this + 11) = 0;
  }
  v12 = -1;
  while ( (unsigned int)i < a3 )
  {
    v13 = *((_DWORD *)a4 + 6 * i + 3);
    if ( v13 )
    {
      if ( v13 != 1 )
        goto LABEL_41;
      if ( *((_DWORD *)a4 + 6 * i + 4) != 130 )
        goto LABEL_41;
      if ( *((_DWORD *)a4 + 6 * i + 2) )
        goto LABEL_41;
      v14 = (const unsigned __int16 *)*((_QWORD *)a4 + 3 * i);
      if ( !v14 )
        goto LABEL_41;
      v15 = safe_lstrlenW(v14) + 1;
      v17 = 2LL * v15;
      if ( !is_mul_ok(v15, 2u) )
        v17 = v16;
      v18 = (unsigned __int16 *)CoTaskMemAlloc(v17);
      *((_QWORD *)this + 10) = v18;
      if ( !v18 )
      {
        v9 = -2147024882;
        goto LABEL_43;
      }
      v9 = StringCchCopyW(v18, v15, *((const unsigned __int16 **)a4 + 3 * i));
      if ( v9 < 0 )
      {
        CoTaskMemFree(*((LPVOID *)this + 10));
        *((_QWORD *)this + 10) = 0;
        goto LABEL_43;
      }
      v12 = -1;
    }
    else
    {
      if ( *((_DWORD *)a4 + 6 * i + 4) != 72 )
        goto LABEL_41;
      if ( *((_DWORD *)a4 + 6 * i + 2) )
        goto LABEL_41;
      v19 = (_OWORD *)*((_QWORD *)a4 + 3 * i);
      if ( !v19 )
        goto LABEL_41;
      *((_OWORD *)this + 4) = *v19;
    }
    i = (unsigned int)(i + 1);
  }
  v20 = *(_QWORD *)&v7->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v20 = *(_QWORD *)v7->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v20 )
  {
    if ( *((_QWORD *)this + 10) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(**((_QWORD **)this + 7) + 24LL))(
             *((_QWORD *)this + 7),
             &didCOMSERVICES,
             TID_LT_APPLICATIONPARTITION,
             v28,
             1,
             1,
             1,
             &v31);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 24LL))(v31);
        if ( v9 >= 0 )
        {
          v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 40LL))(v31);
          v9 = v21;
          if ( v21 == -2146367487 )
          {
LABEL_41:
            v9 = -2147024809;
            goto LABEL_43;
          }
          if ( v21 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v31 + 64LL))(
                   v31,
                   1,
                   0,
                   0,
                   &v27);
            if ( v9 >= 0 )
            {
              safe_lstrlenW(*((const unsigned __int16 **)this + 10));
              v22 = safe_lstrlenW(v27);
              v24 = v23 + v22 + 2;
              v25 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v24, 2u));
              *((_QWORD *)this + 11) = v25;
              if ( v25 )
              {
                v9 = StringCchPrintfW(v25, v24, L"%s\\%s", v27, *((_QWORD *)this + 10));
                if ( v9 >= 0 )
                {
                  *((_QWORD *)this + 12) = &CLSID_SystemApplication;
                  *((_QWORD *)this + 13) = 0;
                  *((_DWORD *)this + 28) = 72;
                  *((_DWORD *)this + 29) = 16;
                  *((_QWORD *)this + 15) = *((_QWORD *)this + 11);
                  *((_DWORD *)this + 32) = 0;
                  *((_DWORD *)this + 33) = 1;
                  *((_DWORD *)this + 34) = 130;
                  *((_DWORD *)this + 35) = 2 * v24 + 2;
                }
                else
                {
                  CoTaskMemFree(*((LPVOID *)this + 11));
                  *((_QWORD *)this + 11) = 0;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  if ( v31 )
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v31 + 16LL))(v31, a2, v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004bed4  push    rbp
0x18004bed6  push    rbx
0x18004bed7  push    rsi
0x18004bed8  push    rdi
0x18004bed9  push    r12
0x18004bedb  push    r13
0x18004bedd  push    r14
0x18004bedf  push    r15
0x18004bee1  mov     rbp, rsp
0x18004bee4  sub     rsp, 78h
0x18004bee8  mov     r15, r9
0x18004beeb  mov     r12d, r8d
0x18004beee  mov     rdi, rcx
0x18004bef1  mov     [rbp+arg_0], 0
0x18004bef9  mov     [rbp+var_28], 0
0x18004bf01  lea     r13, [rcx+40h]
0x18004bf05  mov     [rbp+var_20], r13
0x18004bf09  mov     [rbp+var_18], 0
0x18004bf11  mov     [rbp+var_10], 48h ; 'H'
0x18004bf18  mov     [rbp+var_C], 10h
0x18004bf1f  xor     esi, esi
0x18004bf21  lea     r14d, [rsi+1]
0x18004bf25  test    r8d, r8d
0x18004bf28  jz      short loc_18004BF41
0x18004bf2a  lea     rcx, [rsi+rsi*2]
0x18004bf2e  cmp     dword ptr [r9+rcx*8+0Ch], 0F0000000h
0x18004bf37  jbe     short loc_18004BF41
0x18004bf39  add     esi, r14d
0x18004bf3c  cmp     esi, r12d
0x18004bf3f  jb      short loc_18004BF2A
0x18004bf41  cmp     edx, r14d
0x18004bf44  jnz     loc_18004C24D
0x18004bf4a  mov     eax, r12d
0x18004bf4d  sub     eax, esi
0x18004bf4f  cmp     eax, 2
0x18004bf52  jnz     loc_18004C24D
0x18004bf58  xor     ebx, ebx
0x18004bf5a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004bf61  movdqu  xmmword ptr [r13+0], xmm0
0x18004bf67  mov     rcx, [rdi+50h]; pv
0x18004bf6b  test    rcx, rcx
0x18004bf6e  jz      short loc_18004BF7B
0x18004bf70  call    cs:__imp_CoTaskMemFree
0x18004bf76  nop
0x18004bf77  mov     [rdi+50h], rbx
0x18004bf7b  mov     rcx, [rdi+58h]; pv
0x18004bf7f  test    rcx, rcx
0x18004bf82  jz      short loc_18004BF93
0x18004bf84  call    cs:__imp_CoTaskMemFree
0x18004bf8a  nop
0x18004bf8b  mov     qword ptr [rdi+58h], 0
0x18004bf93  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004bf97  jmp     loc_18004C058
0x18004bf9c  lea     r14, [rsi+rsi*2]
0x18004bfa0  mov     ecx, [r15+r14*8+0Ch]
0x18004bfa5  test    ecx, ecx
0x18004bfa7  jz      short loc_18004C022
0x18004bfa9  cmp     ecx, 1
0x18004bfac  jnz     loc_18004C1D9
0x18004bfb2  cmp     dword ptr [r15+r14*8+10h], 82h
0x18004bfbb  jnz     loc_18004C1D9
0x18004bfc1  cmp     dword ptr [r15+r14*8+8], 0
0x18004bfc7  jnz     loc_18004C1D9
0x18004bfcd  mov     rcx, [r15+r14*8]; unsigned __int16 *
0x18004bfd1  test    rcx, rcx
0x18004bfd4  jz      loc_18004C1D9
0x18004bfda  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004bfdf  lea     ebx, [rax+1]
0x18004bfe2  mov     eax, 2
0x18004bfe7  mul     rbx
0x18004bfea  cmovb   rax, r8
0x18004bfee  mov     rcx, rax; cb
0x18004bff1  call    cs:__imp_CoTaskMemAlloc
0x18004bff7  mov     [rdi+50h], rax
0x18004bffb  test    rax, rax
0x18004bffe  jz      loc_18004C1D2
0x18004c004  mov     r8, [r15+r14*8]; unsigned __int16 *
0x18004c008  mov     edx, ebx; unsigned __int64
0x18004c00a  mov     rcx, rax; unsigned __int16 *
0x18004c00d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004c012  mov     ebx, eax
0x18004c014  test    eax, eax
0x18004c016  js      loc_18004C1BD
0x18004c01c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004c020  jmp     short loc_18004C04F
0x18004c022  cmp     dword ptr [r15+r14*8+10h], 48h ; 'H'
0x18004c028  jnz     loc_18004C1D9
0x18004c02e  cmp     dword ptr [r15+r14*8+8], 0
0x18004c034  jnz     loc_18004C1D9
0x18004c03a  mov     rax, [r15+r14*8]
0x18004c03e  test    rax, rax
0x18004c041  jz      loc_18004C1D9
0x18004c047  movups  xmm0, xmmword ptr [rax]
0x18004c04a  movdqu  xmmword ptr [rdi+40h], xmm0
0x18004c04f  mov     r14d, 1
0x18004c055  add     esi, r14d
0x18004c058  cmp     esi, r12d
0x18004c05b  jb      loc_18004BF9C
0x18004c061  mov     rax, [r13+0]
0x18004c065  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18004c06c  jnz     short loc_18004C079
0x18004c06e  mov     rax, [r13+8]
0x18004c072  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18004c079  test    rax, rax
0x18004c07c  jz      loc_18004C234
0x18004c082  cmp     qword ptr [rdi+50h], 0
0x18004c087  jz      loc_18004C234
0x18004c08d  mov     rcx, [rdi+38h]
0x18004c091  mov     rax, [rcx]
0x18004c094  lea     rdx, [rbp+arg_0]
0x18004c098  mov     [rsp+78h+var_40], rdx
0x18004c09d  mov     [rsp+78h+var_48], r14d
0x18004c0a2  mov     [rsp+78h+var_50], r14d
0x18004c0a7  mov     [rsp+78h+var_58], r14
0x18004c0ac  lea     r9, [rbp+var_20]
0x18004c0b0  lea     r8, TID_LT_APPLICATIONPARTITION
0x18004c0b7  lea     rdx, didCOMSERVICES
0x18004c0be  mov     rax, [rax+18h]
0x18004c0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0c7  mov     ebx, eax
0x18004c0c9  test    eax, eax
0x18004c0cb  js      loc_18004C234
0x18004c0d1  mov     rcx, [rbp+arg_0]
0x18004c0d5  mov     rax, [rcx]
0x18004c0d8  mov     rax, [rax+18h]
0x18004c0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0e1  mov     ebx, eax
0x18004c0e3  test    eax, eax
0x18004c0e5  js      loc_18004C234
0x18004c0eb  mov     rcx, [rbp+arg_0]
0x18004c0ef  mov     rax, [rcx]
0x18004c0f2  mov     rax, [rax+28h]
0x18004c0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0fb  mov     ebx, eax
0x18004c0fd  cmp     eax, 80110801h
0x18004c102  jz      loc_18004C1D9
0x18004c108  test    eax, eax
0x18004c10a  js      loc_18004C234
0x18004c110  mov     rcx, [rbp+arg_0]
0x18004c114  mov     rax, [rcx]
0x18004c117  lea     rdx, [rbp+var_28]
0x18004c11b  mov     [rsp+78h+var_58], rdx
0x18004c120  xor     r9d, r9d
0x18004c123  xor     r8d, r8d
0x18004c126  mov     edx, r14d
0x18004c129  mov     rax, [rax+40h]
0x18004c12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c132  mov     ebx, eax
0x18004c134  test    eax, eax
0x18004c136  js      loc_18004C234
0x18004c13c  mov     rcx, [rdi+50h]; unsigned __int16 *
0x18004c140  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004c145  mov     r8d, eax
0x18004c148  mov     rcx, [rbp+var_28]; unsigned __int16 *
0x18004c14c  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004c151  lea     esi, [rax+2]
0x18004c154  add     esi, r8d
0x18004c157  mov     r14d, esi
0x18004c15a  mov     eax, 2
0x18004c15f  mul     r14
0x18004c162  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004c169  cmovb   rax, rcx
0x18004c16d  mov     rcx, rax; cb
0x18004c170  call    cs:__imp_CoTaskMemAlloc
0x18004c176  mov     [rdi+58h], rax
0x18004c17a  test    rax, rax
0x18004c17d  jz      loc_18004C234
0x18004c183  mov     rcx, [rdi+50h]
0x18004c187  mov     [rsp+78h+var_58], rcx
0x18004c18c  mov     r9, [rbp+var_28]
0x18004c190  lea     r8, aSS_0; "%s\\%s"
0x18004c197  mov     edx, r14d; unsigned __int64
0x18004c19a  mov     rcx, rax; unsigned __int16 *
0x18004c19d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c1a2  mov     ebx, eax
0x18004c1a4  test    eax, eax
0x18004c1a6  jns     short loc_18004C1E0
0x18004c1a8  mov     rcx, [rdi+58h]; pv
0x18004c1ac  call    cs:__imp_CoTaskMemFree
0x18004c1b2  nop
0x18004c1b3  mov     qword ptr [rdi+58h], 0
0x18004c1bb  jmp     short loc_18004C234
0x18004c1bd  mov     rcx, [rdi+50h]; pv
0x18004c1c1  call    cs:__imp_CoTaskMemFree
0x18004c1c7  nop
0x18004c1c8  mov     qword ptr [rdi+50h], 0
0x18004c1d0  jmp     short loc_18004C234
0x18004c1d2  mov     ebx, 8007000Eh
0x18004c1d7  jmp     short loc_18004C234
0x18004c1d9  mov     ebx, 80070057h
0x18004c1de  jmp     short loc_18004C234
0x18004c1e0  lea     rax, CLSID_SystemApplication
0x18004c1e7  mov     [rdi+60h], rax
0x18004c1eb  mov     qword ptr [rdi+68h], 0
0x18004c1f3  mov     dword ptr [rdi+70h], 48h ; 'H'
0x18004c1fa  mov     dword ptr [rdi+74h], 10h
0x18004c201  mov     rax, [rdi+58h]
0x18004c205  mov     [rdi+78h], rax
0x18004c209  mov     dword ptr [rdi+80h], 0
0x18004c213  mov     dword ptr [rdi+84h], 1
0x18004c21d  mov     dword ptr [rdi+88h], 82h
0x18004c227  lea     eax, ds:2[rsi*2]
0x18004c22e  mov     [rdi+8Ch], eax
0x18004c234  mov     rcx, [rbp+arg_0]
0x18004c238  test    rcx, rcx
0x18004c23b  jz      short loc_18004C249
0x18004c23d  mov     rax, [rcx]
0x18004c240  mov     rax, [rax+10h]
0x18004c244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c249  mov     eax, ebx
0x18004c24b  jmp     short loc_18004C252
0x18004c24d  mov     eax, 80070057h
0x18004c252  add     rsp, 78h
0x18004c256  pop     r15
0x18004c258  pop     r14
0x18004c25a  pop     r13
0x18004c25c  pop     r12
0x18004c25e  pop     rdi
0x18004c25f  pop     rsi
0x18004c260  pop     rbx
0x18004c261  pop     rbp
0x18004c262  retn
```
