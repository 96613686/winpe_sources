# CAppExport::ExportRoleDefinition(_GUID,ushort *)

- ea: `0x18004c5f4`
- end: `0x18004c978`
- name: `?ExportRoleDefinition@CAppExport@@AEAAJU_GUID@@PEAG@Z`
- size: `900`
- prototype: `int(CAppExport *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d0a0`

## callees

- `0x18001a6c8`
- `0x18004c5f4`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c656`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c770`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c656`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c770`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c83a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c83a`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportRoleDefinition(CAppExport *this, struct _GUID *a2, unsigned __int16 *a3)
{
  int SimpleTableDispenser; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  _QWORD *v9; // rsi
  bool v10; // zf
  __int64 v11; // rax
  unsigned int v12; // edi
  __int64 v13; // r8
  signed __int64 v15; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+58h] [rbp-11h] BYREF
  __int64 v17; // [rsp+60h] [rbp-9h] BYREF
  int v18; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v19[2]; // [rsp+70h] [rbp+7h] BYREF
  int v20; // [rsp+80h] [rbp+17h]
  int v21; // [rsp+84h] [rbp+1Bh]
  unsigned __int16 *v22; // [rsp+88h] [rbp+1Fh] BYREF
  int v23; // [rsp+90h] [rbp+27h]
  int v24; // [rsp+94h] [rbp+2Bh]
  int v25; // [rsp+98h] [rbp+2Fh]
  int v26; // [rsp+9Ch] [rbp+33h]

  v19[0] = a2;
  v16 = 0;
  v19[1] = 0;
  v20 = 72;
  v21 = 16;
  v17 = 0;
  if ( *((_QWORD *)this + 22) )
  {
LABEL_5:
    v6 = memcmp_0(&tidCOMSERVICES_ROLEDEFINITION, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLEDEFINITION,
                             v19,
                             1,
                             1,
                             v6 != 0 ? 7 : 5,
                             &v17);
    goto LABEL_6;
  }
  v15 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v15);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v15, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_5;
  }
LABEL_6:
  if ( SimpleTableDispenser < 0 )
    goto LABEL_35;
  if ( !v17 )
  {
    SimpleTableDispenser = -2147024882;
    goto LABEL_37;
  }
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_35;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17);
  if ( SimpleTableDispenser < 0 )
    goto LABEL_35;
  v22 = a3;
  v23 = 0;
  v24 = -268435455;
  v25 = 130;
  v7 = safe_lstrlenW(a3);
  v16 = 0;
  v26 = 2 * v7 + 2;
  if ( *((_QWORD *)this + 22) )
    goto LABEL_15;
  v15 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v15);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v15, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_15:
    v8 = memcmp_0(&tidCOMSERVICES_ROLEDEFINITION_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, unsigned __int16 **, __int64, int, int, __int64 **))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLEDEFINITION_EXPORT,
                             &v22,
                             1,
                             1,
                             v8 != 0 ? 6 : 4,
                             &v16);
  }
  if ( SimpleTableDispenser < 0 )
    goto LABEL_35;
  if ( !v16 )
    goto LABEL_18;
  SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *))(*v16 + 24))(v16);
  if ( SimpleTableDispenser >= 0 )
  {
    v9 = CoTaskMemAlloc(0x18u);
    if ( v9 )
    {
      while ( 1 )
      {
        v10 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17) == -2146367487;
        v11 = *v16;
        if ( v10 )
          break;
        SimpleTableDispenser = (*(__int64 (**)(void))(v11 + 120))();
        if ( SimpleTableDispenser >= 0 )
        {
          v12 = 0;
          *v9 = 0;
          while ( v12 < 3 )
          {
            v18 = 0;
            LODWORD(v15) = 0;
            SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, signed __int64 *, _QWORD *))(*(_QWORD *)v17 + 64LL))(
                                     v17,
                                     v12,
                                     &v18,
                                     &v15,
                                     &v9[v12]);
            if ( SimpleTableDispenser < 0 )
              goto LABEL_34;
            if ( v9[v12] )
            {
              v13 = 0;
              if ( v18 == 128 )
                v13 = (unsigned int)v15;
              SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64))(*v16 + 160))(v16, v12, v13);
              if ( SimpleTableDispenser < 0 )
                goto LABEL_34;
            }
            ++v12;
          }
          SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64 *))(*v16 + 144))(v16);
          if ( SimpleTableDispenser >= 0 )
            continue;
        }
        goto LABEL_34;
      }
      SimpleTableDispenser = (*(__int64 (**)(void))(v11 + 96))();
LABEL_34:
      *v9 = 0;
      CoTaskMemFree(v9);
      goto LABEL_35;
    }
LABEL_18:
    SimpleTableDispenser = -2147024882;
  }
LABEL_35:
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
LABEL_37:
  if ( v16 )
    (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x18004c5f4  mov     [rsp-8+arg_8], rbx
0x18004c5f9  mov     [rsp-8+arg_10], rsi
0x18004c5fe  push    rbp
0x18004c5ff  push    rdi
0x18004c600  push    r12
0x18004c602  push    r14
0x18004c604  push    r15
0x18004c606  lea     rbp, [rsp-37h]
0x18004c60b  sub     rsp, 0A0h
0x18004c612  xor     r15d, r15d
0x18004c615  mov     [rbp+57h+var_50], rdx
0x18004c619  mov     rsi, r8
0x18004c61c  mov     rdi, rcx
0x18004c61f  mov     [rbp+57h+var_68], r15
0x18004c623  mov     [rbp+57h+var_48], r15
0x18004c627  lea     r14d, [r15+10h]
0x18004c62b  mov     [rbp+57h+var_40], 48h ; 'H'
0x18004c632  lea     r12d, [r15+1]
0x18004c636  mov     [rbp+57h+var_3C], r14d
0x18004c63a  mov     [rbp+57h+var_60], r15
0x18004c63e  cmp     [rcx+0B0h], r15
0x18004c645  jnz     short loc_18004C683
0x18004c647  lea     rdx, [rbp+57h+var_70]
0x18004c64b  mov     [rbp+57h+var_70], r15
0x18004c64f  lea     rcx, IID_ISimpleTableDispenser
0x18004c656  call    cs:__imp_GetSimpleTableDispenser
0x18004c65c  mov     ebx, eax
0x18004c65e  test    eax, eax
0x18004c660  js      short loc_18004C6E1
0x18004c662  mov     rcx, [rbp+57h+var_70]
0x18004c666  xor     eax, eax
0x18004c668  lock cmpxchg [rdi+0B0h], rcx
0x18004c671  jz      short loc_18004C683
0x18004c673  mov     rcx, [rbp+57h+var_70]
0x18004c677  mov     rax, [rcx]
0x18004c67a  mov     rax, [rax+10h]
0x18004c67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c683  mov     r8, r14; Size
0x18004c686  lea     rdx, TID_APPLICATION; Buf2
0x18004c68d  lea     rcx, tidCOMSERVICES_ROLEDEFINITION; Buf1
0x18004c694  call    memcmp_0
0x18004c699  mov     rcx, [rdi+0B0h]
0x18004c6a0  lea     r9, [rbp+57h+var_60]
0x18004c6a4  mov     [rsp+0C0h+var_88], r9
0x18004c6a9  lea     r8, tidCOMSERVICES_ROLEDEFINITION
0x18004c6b0  neg     eax
0x18004c6b2  lea     r9, [rbp+57h+var_50]
0x18004c6b6  mov     rax, [rcx]
0x18004c6b9  sbb     edx, edx
0x18004c6bb  and     edx, 2
0x18004c6be  add     edx, 5
0x18004c6c1  mov     [rsp+0C0h+var_90], edx
0x18004c6c5  lea     rdx, didCOMSERVICES
0x18004c6cc  mov     rax, [rax+18h]
0x18004c6d0  mov     [rsp+0C0h+var_98], r12d
0x18004c6d5  mov     [rsp+0C0h+var_A0], r12
0x18004c6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c6df  mov     ebx, eax
0x18004c6e1  test    ebx, ebx
0x18004c6e3  js      loc_18004C92C
0x18004c6e9  mov     rcx, [rbp+57h+var_60]
0x18004c6ed  test    rcx, rcx
0x18004c6f0  jnz     short loc_18004C6FC
0x18004c6f2  mov     ebx, 8007000Eh
0x18004c6f7  jmp     loc_18004C945
0x18004c6fc  mov     rax, [rcx]
0x18004c6ff  mov     rax, [rax+18h]
0x18004c703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c708  mov     ebx, eax
0x18004c70a  test    eax, eax
0x18004c70c  js      loc_18004C92C
0x18004c712  mov     rcx, [rbp+57h+var_60]
0x18004c716  mov     rax, [rcx]
0x18004c719  mov     rax, [rax+20h]
0x18004c71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c722  mov     ebx, eax
0x18004c724  test    eax, eax
0x18004c726  js      loc_18004C92C
0x18004c72c  mov     rcx, rsi; unsigned __int16 *
0x18004c72f  mov     [rbp+57h+var_38], rsi
0x18004c733  mov     [rbp+57h+var_30], r15d
0x18004c737  mov     [rbp+57h+var_2C], 0F0000001h
0x18004c73e  mov     [rbp+57h+var_28], 82h
0x18004c745  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004c74a  mov     [rbp+57h+var_68], r15
0x18004c74e  lea     eax, ds:2[rax*2]
0x18004c755  mov     [rbp+57h+var_24], eax
0x18004c758  cmp     [rdi+0B0h], r15
0x18004c75f  jnz     short loc_18004C7A1
0x18004c761  lea     rdx, [rbp+57h+var_70]
0x18004c765  mov     [rbp+57h+var_70], r15
0x18004c769  lea     rcx, IID_ISimpleTableDispenser
0x18004c770  call    cs:__imp_GetSimpleTableDispenser
0x18004c776  mov     ebx, eax
0x18004c778  test    eax, eax
0x18004c77a  js      loc_18004C803
0x18004c780  mov     rcx, [rbp+57h+var_70]
0x18004c784  xor     eax, eax
0x18004c786  lock cmpxchg [rdi+0B0h], rcx
0x18004c78f  jz      short loc_18004C7A1
0x18004c791  mov     rcx, [rbp+57h+var_70]
0x18004c795  mov     rax, [rcx]
0x18004c798  mov     rax, [rax+10h]
0x18004c79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7a1  mov     r8, r14; Size
0x18004c7a4  lea     rdx, TID_APPLICATION; Buf2
0x18004c7ab  lea     rcx, tidCOMSERVICES_ROLEDEFINITION_EXPORT; Buf1
0x18004c7b2  call    memcmp_0
0x18004c7b7  mov     rcx, [rdi+0B0h]
0x18004c7be  lea     r10, [rbp+57h+var_68]
0x18004c7c2  neg     eax
0x18004c7c4  mov     [rsp+0C0h+var_88], r10
0x18004c7c9  lea     r8, tidCOMSERVICES_ROLEDEFINITION_EXPORT
0x18004c7d0  sbb     r9d, r9d
0x18004c7d3  lea     rdx, didCOMSERVICES
0x18004c7da  mov     rax, [rcx]
0x18004c7dd  and     r9d, 2
0x18004c7e1  add     r9d, 4
0x18004c7e5  mov     [rsp+0C0h+var_90], r9d
0x18004c7ea  lea     r9, [rbp+57h+var_38]
0x18004c7ee  mov     [rsp+0C0h+var_98], r12d
0x18004c7f3  mov     rax, [rax+18h]
0x18004c7f7  mov     [rsp+0C0h+var_A0], r12
0x18004c7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c801  mov     ebx, eax
0x18004c803  test    ebx, ebx
0x18004c805  js      loc_18004C92C
0x18004c80b  cmp     [rbp+57h+var_68], r15
0x18004c80f  jnz     short loc_18004C81B
0x18004c811  mov     ebx, 8007000Eh
0x18004c816  jmp     loc_18004C92C
0x18004c81b  mov     rcx, [rbp+57h+var_68]
0x18004c81f  mov     rax, [rcx]
0x18004c822  mov     rax, [rax+18h]
0x18004c826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c82b  mov     ebx, eax
0x18004c82d  test    eax, eax
0x18004c82f  js      loc_18004C92C
0x18004c835  mov     ecx, 18h; cb
0x18004c83a  call    cs:__imp_CoTaskMemAlloc
0x18004c840  mov     rsi, rax
0x18004c843  test    rax, rax
0x18004c846  jz      short loc_18004C811
0x18004c848  mov     rcx, [rbp+57h+var_60]
0x18004c84c  mov     rax, [rcx]
0x18004c84f  mov     rax, [rax+28h]
0x18004c853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c858  mov     rcx, [rbp+57h+var_68]
0x18004c85c  cmp     eax, 80110801h
0x18004c861  mov     rax, [rcx]
0x18004c864  jz      loc_18004C913
0x18004c86a  mov     rax, [rax+78h]
0x18004c86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c873  mov     ebx, eax
0x18004c875  test    eax, eax
0x18004c877  js      loc_18004C91E
0x18004c87d  xor     eax, eax
0x18004c87f  mov     edi, r15d
0x18004c882  mov     [rsi], rax
0x18004c885  cmp     edi, 3
0x18004c888  jnb     short loc_18004C8F4
0x18004c88a  mov     rcx, [rbp+57h+var_60]
0x18004c88e  lea     r9, [rbp+57h+var_70]
0x18004c892  mov     eax, edi
0x18004c894  lea     r8, [rbp+57h+var_58]
0x18004c898  mov     [rbp+57h+var_58], r15d
0x18004c89c  mov     edx, edi
0x18004c89e  mov     dword ptr [rbp+57h+var_70], r15d
0x18004c8a2  lea     r14, [rsi+rax*8]
0x18004c8a6  mov     rax, [rcx]
0x18004c8a9  mov     [rsp+0C0h+var_A0], r14
0x18004c8ae  mov     rax, [rax+40h]
0x18004c8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8b7  mov     ebx, eax
0x18004c8b9  test    eax, eax
0x18004c8bb  js      short loc_18004C91E
0x18004c8bd  mov     r9, [r14]
0x18004c8c0  test    r9, r9
0x18004c8c3  jz      short loc_18004C8EF
0x18004c8c5  mov     rcx, [rbp+57h+var_68]
0x18004c8c9  mov     r8d, r15d
0x18004c8cc  cmp     [rbp+57h+var_58], 80h
0x18004c8d3  mov     edx, edi
0x18004c8d5  cmovz   r8d, dword ptr [rbp+57h+var_70]
0x18004c8da  mov     rax, [rcx]
0x18004c8dd  mov     rax, [rax+0A0h]
0x18004c8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8e9  mov     ebx, eax
0x18004c8eb  test    eax, eax
0x18004c8ed  js      short loc_18004C91E
0x18004c8ef  add     edi, r12d
0x18004c8f2  jmp     short loc_18004C885
0x18004c8f4  mov     rcx, [rbp+57h+var_68]
0x18004c8f8  mov     rax, [rcx]
0x18004c8fb  mov     rax, [rax+90h]
0x18004c902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c907  mov     ebx, eax
0x18004c909  test    eax, eax
0x18004c90b  jns     loc_18004C848
0x18004c911  jmp     short loc_18004C91E
0x18004c913  mov     rax, [rax+60h]
0x18004c917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c91c  mov     ebx, eax
0x18004c91e  xor     eax, eax
0x18004c920  mov     rcx, rsi; pv
0x18004c923  mov     [rsi], rax
0x18004c926  call    cs:__imp_CoTaskMemFree
0x18004c92c  mov     rcx, [rbp+57h+var_60]
0x18004c930  test    rcx, rcx
0x18004c933  jz      short loc_18004C945
0x18004c935  mov     rax, [rcx]
0x18004c938  mov     rax, [rax+10h]
0x18004c93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c941  mov     [rbp+57h+var_60], r15
0x18004c945  mov     rcx, [rbp+57h+var_68]
0x18004c949  test    rcx, rcx
0x18004c94c  jz      short loc_18004C95A
0x18004c94e  mov     rax, [rcx]
0x18004c951  mov     rax, [rax+10h]
0x18004c955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c95a  lea     r11, [rsp+0C0h+var_20]
0x18004c962  mov     eax, ebx
0x18004c964  mov     rbx, [r11+38h]
0x18004c968  mov     rsi, [r11+40h]
0x18004c96c  mov     rsp, r11
0x18004c96f  pop     r15
0x18004c971  pop     r14
0x18004c973  pop     r12
0x18004c975  pop     rdi
0x18004c976  pop     rbp
0x18004c977  retn
```
