# CComExport::GetPartitionProperties(_GUID const &,ISimpleTableDispenser *,ulong,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x180052bd8`
- end: `0x180052e2d`
- name: `?GetPartitionProperties@CComExport@@IEAAJAEBU_GUID@@PEAUISimpleTableDispenser@@KPEAPEAG222@Z`
- size: `597`
- prototype: `int(CComExport *__hidden this, const struct _GUID *, struct ISimpleTableDispenser *, unsigned int, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180051f20`

## callees

- `0x180050fd8`
- `0x180052bd8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052de6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052df2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052dc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052de6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052df2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180052d29`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180052d29`

## pseudocode

```c
__int64 __fastcall CComExport::GetPartitionProperties(
        CComExport *this,
        const struct _GUID *a2,
        struct ISimpleTableDispenser *a3,
        char a4,
        LPVOID *lplpsz,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  LPVOID *v8; // rdi
  unsigned __int16 **v9; // rsi
  unsigned __int16 **v10; // r15
  unsigned __int16 **v11; // r14
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD *, __int64, int, int, __int64 *); // rax
  HRESULT v16; // ebx
  int v17; // eax
  unsigned __int16 *v18; // rax
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // rcx
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // rcx
  unsigned __int16 *v25; // rcx
  unsigned __int16 *v26; // rcx
  unsigned __int16 *Src; // [rsp+50h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v30[2]; // [rsp+60h] [rbp-20h] BYREF
  int v31; // [rsp+70h] [rbp-10h]
  int v32; // [rsp+74h] [rbp-Ch]
  int v33; // [rsp+C0h] [rbp+40h] BYREF
  int v34; // [rsp+C4h] [rbp+44h]
  int v35; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v36; // [rsp+D0h] [rbp+50h] BYREF

  v34 = HIDWORD(this);
  v8 = lplpsz;
  v9 = a6;
  v10 = a7;
  v11 = a8;
  *lplpsz = 0;
  *v9 = 0;
  *v10 = 0;
  *v11 = 0;
  v36 = 0;
  v35 = 0;
  v33 = 0;
  Src = 0;
  v29 = 0;
  v30[1] = 0;
  v14 = *(_QWORD *)a3;
  v30[0] = a2;
  v15 = *(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD *, __int64, int, int, __int64 *))(v14 + 24);
  v31 = 72;
  v32 = 16;
  v16 = v15(a3, didCOMSERVICES, &TID_APPLICATIONPARTITION, v30, 1, 1, 1, &v36);
  if ( v16 < 0 )
    goto LABEL_22;
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
  if ( v16 < 0 )
    goto LABEL_22;
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36);
  v16 = v17;
  if ( v17 == -2146367487 )
  {
    v16 = -2146368509;
LABEL_22:
    CoTaskMemFree(*v8);
    v24 = *v9;
    *v8 = 0;
    CoTaskMemFree(v24);
    v25 = *v10;
    *v9 = 0;
    CoTaskMemFree(v25);
    v26 = *v11;
    *v10 = 0;
    CoTaskMemFree(v26);
    *v11 = 0;
    goto LABEL_23;
  }
  if ( v17 < 0 )
    goto LABEL_22;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned __int16 **))(*(_QWORD *)v36 + 64LL))(
          v36,
          1,
          &v35,
          &v33,
          &Src);
  if ( v16 < 0 )
    goto LABEL_22;
  if ( Src && *Src )
  {
    v18 = AllocString(Src);
    *v8 = v18;
    if ( !v18 )
      goto LABEL_21;
  }
  else
  {
    v16 = StringFromCLSID(a2, (LPOLESTR *)v8);
    if ( v16 < 0 )
      goto LABEL_22;
  }
  v19 = AllocString(&word_18005C890);
  *v11 = v19;
  if ( !v19 )
    goto LABEL_21;
  v20 = L"1.0.0";
  if ( (a4 & 0x20) == 0 )
    v20 = L"128.0.0";
  v21 = AllocString(v20);
  *v10 = v21;
  if ( !v21 )
    goto LABEL_21;
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, const unsigned __int16 **))(*(_QWORD *)v36 + 64LL))(
          v36,
          2,
          &v35,
          &v33,
          &v29);
  if ( v16 < 0 )
    goto LABEL_22;
  v22 = v29;
  if ( !v29 || !*v29 )
    v22 = &word_18005C890;
  v23 = AllocString(v22);
  *v9 = v23;
  if ( !v23 )
  {
LABEL_21:
    v16 = -2147024882;
    goto LABEL_22;
  }
LABEL_23:
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180052bd8  mov     [rsp-38h+arg_18], rbx
0x180052bdd  mov     [rsp-38h+arg_0], rcx
0x180052be2  push    rbp
0x180052be3  push    rsi
0x180052be4  push    rdi
0x180052be5  push    r12
0x180052be7  push    r13
0x180052be9  push    r14
0x180052beb  push    r15
0x180052bed  mov     rbp, rsp
0x180052bf0  sub     rsp, 80h
0x180052bf7  mov     rdi, [rbp+lplpsz]
0x180052bfb  lea     rcx, [rbp+arg_10]
0x180052bff  mov     rsi, [rbp+arg_28]
0x180052c03  xor     eax, eax
0x180052c05  mov     r15, [rbp+arg_30]
0x180052c09  mov     r10, r8
0x180052c0c  mov     r14, [rbp+arg_38]
0x180052c10  mov     r13d, r9d
0x180052c13  mov     [rsp+80h+var_48], rcx
0x180052c18  lea     r9, [rbp+var_20]
0x180052c1c  mov     ecx, 1
0x180052c21  mov     [rdi], rax
0x180052c24  mov     [rsp+80h+var_50], ecx
0x180052c28  mov     r12, rdx
0x180052c2b  mov     [rsi], rax
0x180052c2e  mov     [r15], rax
0x180052c31  mov     [r14], rax
0x180052c34  mov     [rbp+arg_10], rax
0x180052c38  mov     [rbp+arg_8], eax
0x180052c3b  mov     dword ptr [rbp+arg_0], eax
0x180052c3e  mov     [rbp+Src], rax
0x180052c42  mov     [rbp+var_28], rax
0x180052c46  mov     [rbp+var_18], rax
0x180052c4a  mov     rax, [r8]
0x180052c4d  lea     r8, TID_APPLICATIONPARTITION
0x180052c54  mov     [rsp+80h+var_58], ecx
0x180052c58  mov     [rbp+var_20], rdx
0x180052c5c  lea     rdx, didCOMSERVICES
0x180052c63  mov     [rsp+80h+var_60], rcx
0x180052c68  mov     rcx, r10
0x180052c6b  mov     rax, [rax+18h]
0x180052c6f  mov     [rbp+var_10], 48h ; 'H'
0x180052c76  mov     [rbp+var_C], 10h
0x180052c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c82  mov     ebx, eax
0x180052c84  test    eax, eax
0x180052c86  js      loc_180052DC5
0x180052c8c  mov     rcx, [rbp+arg_10]
0x180052c90  mov     rax, [rcx]
0x180052c93  mov     rax, [rax+18h]
0x180052c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052c9c  mov     ebx, eax
0x180052c9e  test    eax, eax
0x180052ca0  js      loc_180052DC5
0x180052ca6  mov     rcx, [rbp+arg_10]
0x180052caa  mov     rax, [rcx]
0x180052cad  mov     rax, [rax+28h]
0x180052cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cb6  mov     ebx, eax
0x180052cb8  cmp     eax, 80110801h
0x180052cbd  jnz     short loc_180052CC9
0x180052cbf  mov     ebx, 80110403h
0x180052cc4  jmp     loc_180052DC5
0x180052cc9  test    eax, eax
0x180052ccb  js      loc_180052DC5
0x180052cd1  mov     rcx, [rbp+arg_10]
0x180052cd5  lea     r8, [rbp+Src]
0x180052cd9  mov     [rsp+80h+var_60], r8
0x180052cde  lea     r9, [rbp+arg_0]
0x180052ce2  lea     r8, [rbp+arg_8]
0x180052ce6  mov     edx, 1
0x180052ceb  mov     rax, [rcx]
0x180052cee  mov     rax, [rax+40h]
0x180052cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cf7  mov     ebx, eax
0x180052cf9  test    eax, eax
0x180052cfb  js      loc_180052DC5
0x180052d01  mov     rcx, [rbp+Src]; Src
0x180052d05  xor     ebx, ebx
0x180052d07  test    rcx, rcx
0x180052d0a  jz      short loc_180052D23
0x180052d0c  cmp     [rcx], bx
0x180052d0f  jz      short loc_180052D23
0x180052d11  call    ?AllocString@@YAPEAGPEBG@Z; AllocString(ushort const *)
0x180052d16  mov     [rdi], rax
0x180052d19  test    rax, rax
0x180052d1c  jnz     short loc_180052D39
0x180052d1e  jmp     loc_180052DC0
0x180052d23  mov     rdx, rdi; lplpsz
0x180052d26  mov     rcx, r12; rclsid
0x180052d29  call    cs:__imp_StringFromCLSID
0x180052d2f  mov     ebx, eax
0x180052d31  test    eax, eax
0x180052d33  js      loc_180052DC5
0x180052d39  lea     rcx, word_18005C890; Src
0x180052d40  call    ?AllocString@@YAPEAGPEBG@Z; AllocString(ushort const *)
0x180052d45  mov     [r14], rax
0x180052d48  test    rax, rax
0x180052d4b  jz      short loc_180052DC0
0x180052d4d  lea     rax, ?g_wchSERVERVERSION@@3QBGB; "128.0.0"
0x180052d54  test    r13b, 20h
0x180052d58  lea     rcx, ?g_wchCLIENTVERSION@@3QBGB; "1.0.0"
0x180052d5f  cmovz   rcx, rax; Src
0x180052d63  call    ?AllocString@@YAPEAGPEBG@Z; AllocString(ushort const *)
0x180052d68  mov     [r15], rax
0x180052d6b  test    rax, rax
0x180052d6e  jz      short loc_180052DC0
0x180052d70  mov     rcx, [rbp+arg_10]
0x180052d74  lea     rdx, [rbp+var_28]
0x180052d78  mov     [rsp+80h+var_60], rdx
0x180052d7d  lea     r9, [rbp+arg_0]
0x180052d81  lea     r8, [rbp+arg_8]
0x180052d85  mov     edx, 2
0x180052d8a  mov     rax, [rcx]
0x180052d8d  mov     rax, [rax+40h]
0x180052d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d96  mov     ebx, eax
0x180052d98  xor     eax, eax
0x180052d9a  test    ebx, ebx
0x180052d9c  js      short loc_180052DC5
0x180052d9e  mov     rcx, [rbp+var_28]
0x180052da2  test    rcx, rcx
0x180052da5  jz      short loc_180052DAC
0x180052da7  cmp     [rcx], ax
0x180052daa  jnz     short loc_180052DB3
0x180052dac  lea     rcx, word_18005C890; Src
0x180052db3  call    ?AllocString@@YAPEAGPEBG@Z; AllocString(ushort const *)
0x180052db8  mov     [rsi], rax
0x180052dbb  test    rax, rax
0x180052dbe  jnz     short loc_180052DFB
0x180052dc0  mov     ebx, 8007000Eh
0x180052dc5  mov     rcx, [rdi]; pv
0x180052dc8  call    cs:__imp_CoTaskMemFree
0x180052dce  mov     rcx, [rsi]; pv
0x180052dd1  mov     qword ptr [rdi], 0
0x180052dd8  call    cs:__imp_CoTaskMemFree
0x180052dde  mov     rcx, [r15]; pv
0x180052de1  xor     edi, edi
0x180052de3  mov     [rsi], rdi
0x180052de6  call    cs:__imp_CoTaskMemFree
0x180052dec  mov     rcx, [r14]; pv
0x180052def  mov     [r15], rdi
0x180052df2  call    cs:__imp_CoTaskMemFree
0x180052df8  mov     [r14], rdi
0x180052dfb  mov     rcx, [rbp+arg_10]
0x180052dff  test    rcx, rcx
0x180052e02  jz      short loc_180052E10
0x180052e04  mov     rax, [rcx]
0x180052e07  mov     rax, [rax+10h]
0x180052e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e10  mov     eax, ebx
0x180052e12  mov     rbx, [rsp+80h+arg_18]
0x180052e1a  add     rsp, 80h
0x180052e21  pop     r15
0x180052e23  pop     r14
0x180052e25  pop     r13
0x180052e27  pop     r12
0x180052e29  pop     rdi
0x180052e2a  pop     rsi
0x180052e2b  pop     rbp
0x180052e2c  retn
```
