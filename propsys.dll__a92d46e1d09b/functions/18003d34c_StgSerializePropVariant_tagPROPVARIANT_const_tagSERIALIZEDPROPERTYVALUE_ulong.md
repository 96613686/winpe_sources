# _StgSerializePropVariant(tagPROPVARIANT const *,tagSERIALIZEDPROPERTYVALUE * *,ulong *)

- ea: `0x18003d34c`
- end: `0x18003d4f6`
- name: `?_StgSerializePropVariant@@YAJPEBUtagPROPVARIANT@@PEAPEAUtagSERIALIZEDPROPERTYVALUE@@PEAK@Z`
- size: `426`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, struct tagSERIALIZEDPROPERTYVALUE **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18007fac0`

## callees

- `0x18003d34c`
- `0x18003d500`
- `0x18003d630`
- `0x18003ef7c`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003d448`
- `ntdll!RtlNtStatusToDosError` at `0x18003d448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d46c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d46c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d3e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d3e0`

## pseudocode

```c
__int64 __fastcall _StgSerializePropVariant(
        const struct tagPROPVARIANT *a1,
        struct tagSERIALIZEDPROPERTYVALUE **a2,
        unsigned int *a3)
{
  bool v3; // zf
  struct tagSERIALIZEDPROPERTYVALUE *v7; // rdi
  unsigned int v8; // ebx
  signed int v10; // eax
  int (__fastcall ***QuadPart)(_QWORD, GUID *, char *); // rcx
  __int128 v12; // [rsp+58h] [rbp-28h] BYREF
  __int64 v13; // [rsp+68h] [rbp-18h]
  NTSTATUS Status; // [rsp+70h] [rbp-10h]

  v3 = a1->vt == 13;
  v13 = 0;
  v12 = 0;
  if ( v3 )
  {
    QuadPart = (int (__fastcall ***)(_QWORD, GUID *, char *))a1->hVal.QuadPart;
    if ( QuadPart )
    {
      if ( (**QuadPart)(QuadPart, &GUID_0000000c_0000_0000_c000_000000000046, (char *)&v12 + 8) >= 0 )
      {
        LOWORD(v12) = 66;
        v8 = StgSerializePropVariantEx(1, &v12, a2, a3);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v12 + 1) + 16LL))(*((_QWORD *)&v12 + 1));
        return v8;
      }
    }
  }
  v7 = 0;
  Status = 0;
  if ( !a2 || !a3 )
  {
    v8 = -2147024809;
    goto LABEL_12;
  }
  StgConvertVariantToPropertyNoEH(1, a1);
  if ( Status < 0 )
  {
    v8 = MapNTStatusToHResult(Status);
LABEL_11:
    if ( (v8 & 0x80000000) == 0 )
      return v8;
LABEL_12:
    if ( !a2 )
      goto LABEL_14;
    goto LABEL_13;
  }
  v7 = (struct tagSERIALIZEDPROPERTYVALUE *)CoTaskMemAlloc(0);
  if ( v7 )
  {
    *a3 = 0;
    StgConvertVariantToPropertyNoEH(1, a1);
    if ( Status >= 0 )
    {
      v8 = 0;
      *a2 = v7;
      return v8;
    }
    v10 = RtlNtStatusToDosError(Status);
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_11;
  }
  v8 = -2147024882;
LABEL_13:
  *a2 = 0;
LABEL_14:
  if ( v7 )
    CoTaskMemFree(v7);
  return v8;
}

```

## disassembly

```asm
0x18003d34c  mov     [rsp-28h+arg_18], rbx
0x18003d351  push    rbp
0x18003d352  push    rsi
0x18003d353  push    rdi
0x18003d354  push    r14
0x18003d356  push    r15
0x18003d358  mov     rbp, rsp
0x18003d35b  sub     rsp, 80h
0x18003d362  mov     rax, cs:__security_cookie
0x18003d369  xor     rax, rsp
0x18003d36c  mov     [rbp+var_8], rax
0x18003d370  xor     eax, eax
0x18003d372  xorps   xmm0, xmm0
0x18003d375  cmp     word ptr [rcx], 0Dh
0x18003d379  mov     r15, r8
0x18003d37c  mov     rsi, rdx
0x18003d37f  mov     [rbp+var_18], rax
0x18003d383  mov     rbx, rcx
0x18003d386  movups  [rbp+var_28], xmm0
0x18003d38a  jz      loc_18003D48F
0x18003d390  xor     edi, edi
0x18003d392  mov     dword ptr [rbp+cb], 0
0x18003d399  mov     [rbp+Status], edi
0x18003d39c  test    rsi, rsi
0x18003d39f  jz      loc_18003D47F
0x18003d3a5  test    r15, r15
0x18003d3a8  jz      loc_18003D47F
0x18003d3ae  lea     rax, [rbp+Status]
0x18003d3b2  xor     r9d, r9d
0x18003d3b5  mov     [rsp+80h+var_40], rax
0x18003d3ba  lea     ecx, [rdi+1]
0x18003d3bd  lea     rax, [rbp+cb]
0x18003d3c1  mov     rdx, rbx
0x18003d3c4  mov     [rsp+80h+var_60], rax
0x18003d3c9  call    StgConvertVariantToPropertyNoEH
0x18003d3ce  mov     ecx, [rbp+Status]; int
0x18003d3d1  test    ecx, ecx
0x18003d3d3  js      loc_18003D486
0x18003d3d9  mov     r14d, dword ptr [rbp+cb]
0x18003d3dd  mov     ecx, r14d; cb
0x18003d3e0  call    cs:__imp_CoTaskMemAlloc
0x18003d3e6  mov     rdi, rax
0x18003d3e9  test    rax, rax
0x18003d3ec  jz      loc_18003D4EC
0x18003d3f2  lea     rax, [rbp+Status]
0x18003d3f6  mov     [r15], r14d
0x18003d3f9  mov     [rsp+80h+var_40], rax
0x18003d3fe  mov     r9, rdi
0x18003d401  lea     rax, [rbp+cb]
0x18003d405  mov     rdx, rbx
0x18003d408  mov     ecx, 1
0x18003d40d  mov     [rsp+80h+var_60], rax
0x18003d412  call    StgConvertVariantToPropertyNoEH
0x18003d417  mov     ecx, [rbp+Status]; Status
0x18003d41a  test    ecx, ecx
0x18003d41c  js      short loc_18003D448
0x18003d41e  xor     ebx, ebx
0x18003d420  mov     [rsi], rdi
0x18003d423  mov     eax, ebx
0x18003d425  mov     rcx, [rbp+var_8]
0x18003d429  xor     rcx, rsp; StackCookie
0x18003d42c  call    __security_check_cookie
0x18003d431  mov     rbx, [rsp+80h+arg_18]
0x18003d439  add     rsp, 80h
0x18003d440  pop     r15
0x18003d442  pop     r14
0x18003d444  pop     rdi
0x18003d445  pop     rsi
0x18003d446  pop     rbp
0x18003d447  retn
0x18003d448  call    cs:__imp_RtlNtStatusToDosError
0x18003d44e  mov     ebx, eax
0x18003d450  test    eax, eax
0x18003d452  jg      short loc_18003D474
0x18003d454  test    ebx, ebx
0x18003d456  jns     short loc_18003D423
0x18003d458  test    rsi, rsi
0x18003d45b  jz      short loc_18003D464
0x18003d45d  mov     qword ptr [rsi], 0
0x18003d464  test    rdi, rdi
0x18003d467  jz      short loc_18003D423
0x18003d469  mov     rcx, rdi; pv
0x18003d46c  call    cs:__imp_CoTaskMemFree
0x18003d472  jmp     short loc_18003D423
0x18003d474  movzx   ebx, ax
0x18003d477  or      ebx, 80070000h
0x18003d47d  jmp     short loc_18003D454
0x18003d47f  mov     ebx, 80070057h
0x18003d484  jmp     short loc_18003D458
0x18003d486  call    ?MapNTStatusToHResult@@YAJJ@Z; MapNTStatusToHResult(long)
0x18003d48b  mov     ebx, eax
0x18003d48d  jmp     short loc_18003D454
0x18003d48f  mov     rcx, [rcx+8]
0x18003d493  test    rcx, rcx
0x18003d496  jz      loc_18003D390
0x18003d49c  mov     rax, [rcx]
0x18003d49f  lea     r8, [rbp+var_28+8]
0x18003d4a3  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18003d4aa  mov     rax, [rax]
0x18003d4ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4b2  test    eax, eax
0x18003d4b4  js      loc_18003D390
0x18003d4ba  mov     eax, 42h ; 'B'
0x18003d4bf  lea     rdx, [rbp+var_28]
0x18003d4c3  mov     r9, r15
0x18003d4c6  mov     word ptr [rbp+var_28], ax
0x18003d4ca  mov     r8, rsi
0x18003d4cd  lea     ecx, [rax-41h]
0x18003d4d0  call    StgSerializePropVariantEx
0x18003d4d5  mov     rcx, qword ptr [rbp+var_28+8]
0x18003d4d9  mov     ebx, eax
0x18003d4db  mov     rdx, [rcx]
0x18003d4de  mov     rax, [rdx+10h]
0x18003d4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4e7  jmp     loc_18003D423
0x18003d4ec  mov     ebx, 8007000Eh
0x18003d4f1  jmp     loc_18003D45D
```
