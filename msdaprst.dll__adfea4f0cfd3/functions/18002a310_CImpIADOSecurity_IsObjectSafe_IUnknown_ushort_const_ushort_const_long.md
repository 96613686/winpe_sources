# CImpIADOSecurity::IsObjectSafe(IUnknown *,ushort const *,ushort const *,long *)

- ea: `0x18002a310`
- end: `0x18002a4a5`
- name: `?IsObjectSafe@CImpIADOSecurity@@UEAAHPEAUIUnknown@@PEBG1PEAJ@Z`
- size: `405`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, struct IUnknown *, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18002a310`
- `0x18002abe0`
- `0x180031010`

## pseudocode

```c
_BOOL8 __fastcall CImpIADOSecurity::IsObjectSafe(
        CImpIADOSecurity *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int *a5)
{
  int *v5; // rbx
  const unsigned __int16 *v10; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int *v12; // r8
  __int64 v13; // rcx
  char v14; // si
  int v15; // eax
  int v16; // eax
  _QWORD v18[3]; // [rsp+30h] [rbp-18h] BYREF
  int v19; // [rsp+80h] [rbp+38h] BYREF

  v5 = &v19;
  v19 = 0;
  if ( a5 )
    v5 = a5;
  *v5 = 0;
  v10 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  if ( !v10 || !(unsigned int)CImpIADOSecurity::isTrustedMachine(this, v10) )
    return 1;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    a5 = 0;
    v18[0] = 0;
    ((void (__fastcall *)(struct IUnknown *, GUID *, int **))lpVtbl->QueryInterface)(a2, &IID_IADOSecurity, &a5);
    ((void (__fastcall *)(struct IUnknown *, GUID *, _QWORD *))a2->lpVtbl->QueryInterface)(
      a2,
      &IID_IObjectWithSite,
      v18);
    v12 = a5;
    v13 = v18[0];
    if ( a5 && v18[0] )
    {
      v14 = 1;
      if ( *((_QWORD *)this + 5) )
      {
        v15 = (*(__int64 (**)(void))(*(_QWORD *)v18[0] + 24LL))();
        v12 = a5;
        v13 = v18[0];
        *v5 = v15;
      }
      if ( *v5 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(int *, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, *((unsigned int *)this + 6));
        *v5 = v16;
        if ( v16 >= 0 && *((_QWORD *)this + 4) )
          *v5 = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)a5 + 24LL))(a5);
        v12 = a5;
        v13 = v18[0];
      }
    }
    else
    {
      v14 = 0;
    }
    if ( v12 )
    {
      (*(void (__fastcall **)(int *))(*(_QWORD *)v12 + 16LL))(v12);
      v13 = v18[0];
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v14 )
      return *v5 >= 0;
  }
  if ( a3 )
    return (*(unsigned int (__fastcall **)(CImpIADOSecurity *, _QWORD, _QWORD, const unsigned __int16 *, const unsigned __int16 *))(*(_QWORD *)this + 80LL))(
             this,
             *((_QWORD *)this + 5),
             *((_QWORD *)this + 4),
             a3,
             a4) == 0;
  return 0;
}

```

## disassembly

```asm
0x18002a310  push    rbp
0x18002a312  push    rbx
0x18002a313  push    rsi
0x18002a314  push    rdi
0x18002a315  push    r14
0x18002a317  push    r15
0x18002a319  mov     rbp, rsp
0x18002a31c  sub     rsp, 48h
0x18002a320  mov     rax, [rbp+arg_20]
0x18002a324  lea     rbx, [rbp+arg_0]
0x18002a328  test    rax, rax
0x18002a32b  mov     [rbp+arg_0], 0
0x18002a332  mov     rsi, rdx
0x18002a335  mov     r15, r9
0x18002a338  cmovnz  rbx, rax
0x18002a33c  mov     r14, r8
0x18002a33f  mov     rdi, rcx
0x18002a342  mov     dword ptr [rbx], 0
0x18002a348  mov     rdx, [rcx+20h]; unsigned __int16 *
0x18002a34c  test    rdx, rdx
0x18002a34f  jz      loc_18002A492
0x18002a355  call    ?isTrustedMachine@CImpIADOSecurity@@AEAAJPEBG@Z; CImpIADOSecurity::isTrustedMachine(ushort const *)
0x18002a35a  test    eax, eax
0x18002a35c  jz      loc_18002A492
0x18002a362  test    rsi, rsi
0x18002a365  jz      loc_18002A45F
0x18002a36b  mov     rax, [rsi]
0x18002a36e  lea     r8, [rbp+arg_20]
0x18002a372  lea     rdx, IID_IADOSecurity
0x18002a379  mov     [rbp+arg_20], 0
0x18002a381  mov     rcx, rsi
0x18002a384  mov     [rbp+var_18], 0
0x18002a38c  mov     rax, [rax]
0x18002a38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a394  mov     rax, [rsi]
0x18002a397  lea     r8, [rbp+var_18]
0x18002a39b  lea     rdx, IID_IObjectWithSite
0x18002a3a2  mov     rcx, rsi
0x18002a3a5  mov     rax, [rax]
0x18002a3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3ad  mov     r8, [rbp+arg_20]
0x18002a3b1  mov     rcx, [rbp+var_18]
0x18002a3b5  test    r8, r8
0x18002a3b8  jz      short loc_18002A425
0x18002a3ba  test    rcx, rcx
0x18002a3bd  jz      short loc_18002A425
0x18002a3bf  mov     rdx, [rdi+28h]
0x18002a3c3  mov     esi, 1
0x18002a3c8  test    rdx, rdx
0x18002a3cb  jz      short loc_18002A3E3
0x18002a3cd  mov     rax, [rcx]
0x18002a3d0  mov     rax, [rax+18h]
0x18002a3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3d9  mov     r8, [rbp+arg_20]
0x18002a3dd  mov     rcx, [rbp+var_18]
0x18002a3e1  mov     [rbx], eax
0x18002a3e3  cmp     dword ptr [rbx], 0
0x18002a3e6  jl      short loc_18002A428
0x18002a3e8  mov     rax, [r8]
0x18002a3eb  mov     rcx, r8
0x18002a3ee  mov     edx, [rdi+18h]
0x18002a3f1  mov     rax, [rax+20h]
0x18002a3f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3fa  mov     [rbx], eax
0x18002a3fc  test    eax, eax
0x18002a3fe  js      short loc_18002A41B
0x18002a400  mov     rdx, [rdi+20h]
0x18002a404  test    rdx, rdx
0x18002a407  jz      short loc_18002A41B
0x18002a409  mov     rcx, [rbp+arg_20]
0x18002a40d  mov     rax, [rcx]
0x18002a410  mov     rax, [rax+18h]
0x18002a414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a419  mov     [rbx], eax
0x18002a41b  mov     r8, [rbp+arg_20]
0x18002a41f  mov     rcx, [rbp+var_18]
0x18002a423  jmp     short loc_18002A428
0x18002a425  xor     sil, sil
0x18002a428  test    r8, r8
0x18002a42b  jz      short loc_18002A440
0x18002a42d  mov     rax, [r8]
0x18002a430  mov     rcx, r8
0x18002a433  mov     rax, [rax+10h]
0x18002a437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a43c  mov     rcx, [rbp+var_18]
0x18002a440  test    rcx, rcx
0x18002a443  jz      short loc_18002A451
0x18002a445  mov     rax, [rcx]
0x18002a448  mov     rax, [rax+10h]
0x18002a44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a451  test    sil, sil
0x18002a454  jz      short loc_18002A45F
0x18002a456  mov     eax, [rbx]
0x18002a458  not     eax
0x18002a45a  shr     eax, 1Fh
0x18002a45d  jmp     short loc_18002A497
0x18002a45f  test    r14, r14
0x18002a462  jz      short loc_18002A48E
0x18002a464  mov     rax, [rdi]
0x18002a467  mov     r9, r14
0x18002a46a  mov     r8, [rdi+20h]
0x18002a46e  mov     rcx, rdi
0x18002a471  mov     rdx, [rdi+28h]
0x18002a475  mov     [rsp+48h+var_28], r15
0x18002a47a  mov     rax, [rax+50h]
0x18002a47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a483  xor     ecx, ecx
0x18002a485  test    eax, eax
0x18002a487  setz    cl
0x18002a48a  mov     eax, ecx
0x18002a48c  jmp     short loc_18002A497
0x18002a48e  xor     eax, eax
0x18002a490  jmp     short loc_18002A497
0x18002a492  mov     eax, 1
0x18002a497  add     rsp, 48h
0x18002a49b  pop     r15
0x18002a49d  pop     r14
0x18002a49f  pop     rdi
0x18002a4a0  pop     rsi
0x18002a4a1  pop     rbx
0x18002a4a2  pop     rbp
0x18002a4a3  retn
```
