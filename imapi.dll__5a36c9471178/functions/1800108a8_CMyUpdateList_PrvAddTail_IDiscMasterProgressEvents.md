# CMyUpdateList::PrvAddTail(IDiscMasterProgressEvents *)

- ea: `0x1800108a8`
- end: `0x1800109c7`
- name: `?PrvAddTail@CMyUpdateList@@AEAAEPEAUIDiscMasterProgressEvents@@@Z`
- size: `287`
- prototype: `unsigned __int8 __fastcall(CMyUpdateList *__hidden this, struct IDiscMasterProgressEvents *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x18000d4d0`

## callees

- `0x180001144`
- `0x18000115c`
- `0x1800108a8`
- `0x180019010`

## pseudocode

```c
char __fastcall CMyUpdateList::PrvAddTail(CMyUpdateList *this, struct IDiscMasterProgressEvents *a2)
{
  bool v2; // zf
  _QWORD *v5; // rdi
  char v6; // bp
  __int64 *v7; // rax
  __int64 *v8; // rcx
  char v9; // dl
  _QWORD *v10; // rax
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 3) == 0;
  v12 = 0;
  if ( v2 || !a2 )
    return 0;
  v5 = 0;
  v6 = 0;
  if ( ((__int64 (__fastcall *)(struct IDiscMasterProgressEvents *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IDiscMasterProgressEvents,
         &v12) >= 0 )
  {
    v7 = (__int64 *)*((_QWORD *)this + 4);
    v8 = 0;
    v9 = 0;
    if ( !v7 )
      goto LABEL_23;
    do
    {
      if ( v9 )
        break;
      if ( (struct IDiscMasterProgressEvents *)v7[1] == a2 )
      {
        v9 = 1;
        v8 = v7;
      }
      v7 = (__int64 *)*v7;
    }
    while ( v7 );
    if ( !v8 )
    {
LABEL_23:
      if ( !*((_QWORD *)this + 3) )
      {
        *((_QWORD *)this + 8) = this;
        *((_QWORD *)this + 7) = (char *)this + 96;
        *((_QWORD *)this + 6) = *((_QWORD *)this + 18);
        *((_QWORD *)this + 4) = 0;
        *((_QWORD *)this + 3) = -1;
      }
      v10 = operator new(0x10u);
      v5 = v10;
      if ( v10 )
      {
        *v10 = 0;
        v10[1] = a2;
        ((void (__fastcall *)(struct IDiscMasterProgressEvents *))a2->lpVtbl->AddRef)(a2);
        v6 = 1;
        *v5 = *((_QWORD *)this + 4);
        *((_QWORD *)this + 4) = v5;
      }
    }
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( !v6 )
  {
    if ( v5 )
      operator delete(v5);
  }
  return v6;
}

```

## disassembly

```asm
0x1800108a8  push    rbx
0x1800108aa  push    rbp
0x1800108ab  push    rsi
0x1800108ac  push    rdi
0x1800108ad  sub     rsp, 28h
0x1800108b1  cmp     dword ptr [rcx+0Ch], 0
0x1800108b5  mov     rsi, rdx
0x1800108b8  mov     rbx, rcx
0x1800108bb  mov     [rsp+48h+arg_0], 0
0x1800108c4  jz      loc_1800109BC
0x1800108ca  test    rdx, rdx
0x1800108cd  jz      loc_1800109BC
0x1800108d3  mov     rax, [rdx]
0x1800108d6  lea     r8, [rsp+48h+arg_0]
0x1800108db  lea     rdx, IID_IDiscMasterProgressEvents
0x1800108e2  mov     rcx, rsi
0x1800108e5  xor     edi, edi
0x1800108e7  xor     bpl, bpl
0x1800108ea  mov     rax, [rax]
0x1800108ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108f2  test    eax, eax
0x1800108f4  js      loc_180010986
0x1800108fa  mov     rax, [rbx+20h]
0x1800108fe  xor     ecx, ecx
0x180010900  xor     dl, dl
0x180010902  test    rax, rax
0x180010905  jz      short loc_180010923
0x180010907  test    dl, dl
0x180010909  jnz     short loc_18001091E
0x18001090b  cmp     [rax+8], rsi
0x18001090f  jnz     short loc_180010916
0x180010911  mov     dl, 1
0x180010913  mov     rcx, rax
0x180010916  mov     rax, [rax]
0x180010919  test    rax, rax
0x18001091c  jnz     short loc_180010907
0x18001091e  test    rcx, rcx
0x180010921  jnz     short loc_180010986
0x180010923  cmp     [rbx+18h], rdi
0x180010927  jnz     short loc_18001094C
0x180010929  lea     rax, [rbx+60h]
0x18001092d  mov     [rbx+40h], rbx
0x180010931  mov     [rbx+38h], rax
0x180010935  mov     rax, [rbx+90h]
0x18001093c  mov     [rbx+30h], rax
0x180010940  mov     [rbx+20h], rdi
0x180010944  mov     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x18001094c  mov     ecx, 10h; Size
0x180010951  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010956  mov     rdi, rax
0x180010959  test    rax, rax
0x18001095c  jz      short loc_180010986
0x18001095e  mov     qword ptr [rax], 0
0x180010965  mov     rcx, rsi
0x180010968  mov     [rax+8], rsi
0x18001096c  mov     rax, [rsi]
0x18001096f  mov     rax, [rax+8]
0x180010973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010978  mov     rax, [rbx+20h]
0x18001097c  mov     bpl, 1
0x18001097f  mov     [rdi], rax
0x180010982  mov     [rbx+20h], rdi
0x180010986  mov     rcx, [rsp+48h+arg_0]
0x18001098b  test    rcx, rcx
0x18001098e  jz      short loc_1800109A5
0x180010990  mov     rax, [rcx]
0x180010993  mov     rax, [rax+10h]
0x180010997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099c  mov     [rsp+48h+arg_0], 0
0x1800109a5  test    bpl, bpl
0x1800109a8  jnz     short loc_1800109B7
0x1800109aa  test    rdi, rdi
0x1800109ad  jz      short loc_1800109B7
0x1800109af  mov     rcx, rdi; Block
0x1800109b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800109b7  mov     al, bpl
0x1800109ba  jmp     short loc_1800109BE
0x1800109bc  xor     al, al
0x1800109be  add     rsp, 28h
0x1800109c2  pop     rdi
0x1800109c3  pop     rsi
0x1800109c4  pop     rbp
0x1800109c5  pop     rbx
0x1800109c6  retn
```
