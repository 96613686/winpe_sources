# CAppExport::ExportRoleConfig(_GUID,ushort *)

- ea: `0x18004c268`
- end: `0x18004c5ec`
- name: `?ExportRoleConfig@CAppExport@@AEAAJU_GUID@@PEAG@Z`
- size: `900`
- prototype: `int(CAppExport *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d0a0`

## callees

- `0x18001a6c8`
- `0x18004c268`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c2ca`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c3e4`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c2ca`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c3e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c59a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c59a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c4ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004c4ae`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportRoleConfig(CAppExport *this, struct _GUID *a2, unsigned __int16 *a3)
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
    v6 = memcmp_0(&tidCOMSERVICES_ROLECONFIG, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLECONFIG,
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
    v8 = memcmp_0(&tidCOMSERVICES_ROLECONFIG_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, unsigned __int16 **, __int64, int, int, __int64 **))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLECONFIG_EXPORT,
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
    v9 = CoTaskMemAlloc(0x20u);
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
          while ( v12 < 4 )
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
0x18004c268  mov     [rsp-8+arg_8], rbx
0x18004c26d  mov     [rsp-8+arg_10], rsi
0x18004c272  push    rbp
0x18004c273  push    rdi
0x18004c274  push    r12
0x18004c276  push    r14
0x18004c278  push    r15
0x18004c27a  lea     rbp, [rsp-37h]
0x18004c27f  sub     rsp, 0A0h
0x18004c286  xor     r15d, r15d
0x18004c289  mov     [rbp+57h+var_50], rdx
0x18004c28d  mov     rsi, r8
0x18004c290  mov     rdi, rcx
0x18004c293  mov     [rbp+57h+var_68], r15
0x18004c297  mov     [rbp+57h+var_48], r15
0x18004c29b  lea     r14d, [r15+10h]
0x18004c29f  mov     [rbp+57h+var_40], 48h ; 'H'
0x18004c2a6  lea     r12d, [r15+1]
0x18004c2aa  mov     [rbp+57h+var_3C], r14d
0x18004c2ae  mov     [rbp+57h+var_60], r15
0x18004c2b2  cmp     [rcx+0B0h], r15
0x18004c2b9  jnz     short loc_18004C2F7
0x18004c2bb  lea     rdx, [rbp+57h+var_70]
0x18004c2bf  mov     [rbp+57h+var_70], r15
0x18004c2c3  lea     rcx, IID_ISimpleTableDispenser
0x18004c2ca  call    cs:__imp_GetSimpleTableDispenser
0x18004c2d0  mov     ebx, eax
0x18004c2d2  test    eax, eax
0x18004c2d4  js      short loc_18004C355
0x18004c2d6  mov     rcx, [rbp+57h+var_70]
0x18004c2da  xor     eax, eax
0x18004c2dc  lock cmpxchg [rdi+0B0h], rcx
0x18004c2e5  jz      short loc_18004C2F7
0x18004c2e7  mov     rcx, [rbp+57h+var_70]
0x18004c2eb  mov     rax, [rcx]
0x18004c2ee  mov     rax, [rax+10h]
0x18004c2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2f7  mov     r8, r14; Size
0x18004c2fa  lea     rdx, TID_APPLICATION; Buf2
0x18004c301  lea     rcx, tidCOMSERVICES_ROLECONFIG; Buf1
0x18004c308  call    memcmp_0
0x18004c30d  mov     rcx, [rdi+0B0h]
0x18004c314  lea     r9, [rbp+57h+var_60]
0x18004c318  mov     [rsp+0C0h+var_88], r9
0x18004c31d  lea     r8, tidCOMSERVICES_ROLECONFIG
0x18004c324  neg     eax
0x18004c326  lea     r9, [rbp+57h+var_50]
0x18004c32a  mov     rax, [rcx]
0x18004c32d  sbb     edx, edx
0x18004c32f  and     edx, 2
0x18004c332  add     edx, 5
0x18004c335  mov     [rsp+0C0h+var_90], edx
0x18004c339  lea     rdx, didCOMSERVICES
0x18004c340  mov     rax, [rax+18h]
0x18004c344  mov     [rsp+0C0h+var_98], r12d
0x18004c349  mov     [rsp+0C0h+var_A0], r12
0x18004c34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c353  mov     ebx, eax
0x18004c355  test    ebx, ebx
0x18004c357  js      loc_18004C5A0
0x18004c35d  mov     rcx, [rbp+57h+var_60]
0x18004c361  test    rcx, rcx
0x18004c364  jnz     short loc_18004C370
0x18004c366  mov     ebx, 8007000Eh
0x18004c36b  jmp     loc_18004C5B9
0x18004c370  mov     rax, [rcx]
0x18004c373  mov     rax, [rax+18h]
0x18004c377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c37c  mov     ebx, eax
0x18004c37e  test    eax, eax
0x18004c380  js      loc_18004C5A0
0x18004c386  mov     rcx, [rbp+57h+var_60]
0x18004c38a  mov     rax, [rcx]
0x18004c38d  mov     rax, [rax+20h]
0x18004c391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c396  mov     ebx, eax
0x18004c398  test    eax, eax
0x18004c39a  js      loc_18004C5A0
0x18004c3a0  mov     rcx, rsi; unsigned __int16 *
0x18004c3a3  mov     [rbp+57h+var_38], rsi
0x18004c3a7  mov     [rbp+57h+var_30], r15d
0x18004c3ab  mov     [rbp+57h+var_2C], 0F0000001h
0x18004c3b2  mov     [rbp+57h+var_28], 82h
0x18004c3b9  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004c3be  mov     [rbp+57h+var_68], r15
0x18004c3c2  lea     eax, ds:2[rax*2]
0x18004c3c9  mov     [rbp+57h+var_24], eax
0x18004c3cc  cmp     [rdi+0B0h], r15
0x18004c3d3  jnz     short loc_18004C415
0x18004c3d5  lea     rdx, [rbp+57h+var_70]
0x18004c3d9  mov     [rbp+57h+var_70], r15
0x18004c3dd  lea     rcx, IID_ISimpleTableDispenser
0x18004c3e4  call    cs:__imp_GetSimpleTableDispenser
0x18004c3ea  mov     ebx, eax
0x18004c3ec  test    eax, eax
0x18004c3ee  js      loc_18004C477
0x18004c3f4  mov     rcx, [rbp+57h+var_70]
0x18004c3f8  xor     eax, eax
0x18004c3fa  lock cmpxchg [rdi+0B0h], rcx
0x18004c403  jz      short loc_18004C415
0x18004c405  mov     rcx, [rbp+57h+var_70]
0x18004c409  mov     rax, [rcx]
0x18004c40c  mov     rax, [rax+10h]
0x18004c410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c415  mov     r8, r14; Size
0x18004c418  lea     rdx, TID_APPLICATION; Buf2
0x18004c41f  lea     rcx, tidCOMSERVICES_ROLECONFIG_EXPORT; Buf1
0x18004c426  call    memcmp_0
0x18004c42b  mov     rcx, [rdi+0B0h]
0x18004c432  lea     r10, [rbp+57h+var_68]
0x18004c436  neg     eax
0x18004c438  mov     [rsp+0C0h+var_88], r10
0x18004c43d  lea     r8, tidCOMSERVICES_ROLECONFIG_EXPORT
0x18004c444  sbb     r9d, r9d
0x18004c447  lea     rdx, didCOMSERVICES
0x18004c44e  mov     rax, [rcx]
0x18004c451  and     r9d, 2
0x18004c455  add     r9d, 4
0x18004c459  mov     [rsp+0C0h+var_90], r9d
0x18004c45e  lea     r9, [rbp+57h+var_38]
0x18004c462  mov     [rsp+0C0h+var_98], r12d
0x18004c467  mov     rax, [rax+18h]
0x18004c46b  mov     [rsp+0C0h+var_A0], r12
0x18004c470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c475  mov     ebx, eax
0x18004c477  test    ebx, ebx
0x18004c479  js      loc_18004C5A0
0x18004c47f  cmp     [rbp+57h+var_68], r15
0x18004c483  jnz     short loc_18004C48F
0x18004c485  mov     ebx, 8007000Eh
0x18004c48a  jmp     loc_18004C5A0
0x18004c48f  mov     rcx, [rbp+57h+var_68]
0x18004c493  mov     rax, [rcx]
0x18004c496  mov     rax, [rax+18h]
0x18004c49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c49f  mov     ebx, eax
0x18004c4a1  test    eax, eax
0x18004c4a3  js      loc_18004C5A0
0x18004c4a9  mov     ecx, 20h ; ' '; cb
0x18004c4ae  call    cs:__imp_CoTaskMemAlloc
0x18004c4b4  mov     rsi, rax
0x18004c4b7  test    rax, rax
0x18004c4ba  jz      short loc_18004C485
0x18004c4bc  mov     rcx, [rbp+57h+var_60]
0x18004c4c0  mov     rax, [rcx]
0x18004c4c3  mov     rax, [rax+28h]
0x18004c4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4cc  mov     rcx, [rbp+57h+var_68]
0x18004c4d0  cmp     eax, 80110801h
0x18004c4d5  mov     rax, [rcx]
0x18004c4d8  jz      loc_18004C587
0x18004c4de  mov     rax, [rax+78h]
0x18004c4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4e7  mov     ebx, eax
0x18004c4e9  test    eax, eax
0x18004c4eb  js      loc_18004C592
0x18004c4f1  xor     eax, eax
0x18004c4f3  mov     edi, r15d
0x18004c4f6  mov     [rsi], rax
0x18004c4f9  cmp     edi, 4
0x18004c4fc  jnb     short loc_18004C568
0x18004c4fe  mov     rcx, [rbp+57h+var_60]
0x18004c502  lea     r9, [rbp+57h+var_70]
0x18004c506  mov     eax, edi
0x18004c508  lea     r8, [rbp+57h+var_58]
0x18004c50c  mov     [rbp+57h+var_58], r15d
0x18004c510  mov     edx, edi
0x18004c512  mov     dword ptr [rbp+57h+var_70], r15d
0x18004c516  lea     r14, [rsi+rax*8]
0x18004c51a  mov     rax, [rcx]
0x18004c51d  mov     [rsp+0C0h+var_A0], r14
0x18004c522  mov     rax, [rax+40h]
0x18004c526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c52b  mov     ebx, eax
0x18004c52d  test    eax, eax
0x18004c52f  js      short loc_18004C592
0x18004c531  mov     r9, [r14]
0x18004c534  test    r9, r9
0x18004c537  jz      short loc_18004C563
0x18004c539  mov     rcx, [rbp+57h+var_68]
0x18004c53d  mov     r8d, r15d
0x18004c540  cmp     [rbp+57h+var_58], 80h
0x18004c547  mov     edx, edi
0x18004c549  cmovz   r8d, dword ptr [rbp+57h+var_70]
0x18004c54e  mov     rax, [rcx]
0x18004c551  mov     rax, [rax+0A0h]
0x18004c558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c55d  mov     ebx, eax
0x18004c55f  test    eax, eax
0x18004c561  js      short loc_18004C592
0x18004c563  add     edi, r12d
0x18004c566  jmp     short loc_18004C4F9
0x18004c568  mov     rcx, [rbp+57h+var_68]
0x18004c56c  mov     rax, [rcx]
0x18004c56f  mov     rax, [rax+90h]
0x18004c576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c57b  mov     ebx, eax
0x18004c57d  test    eax, eax
0x18004c57f  jns     loc_18004C4BC
0x18004c585  jmp     short loc_18004C592
0x18004c587  mov     rax, [rax+60h]
0x18004c58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c590  mov     ebx, eax
0x18004c592  xor     eax, eax
0x18004c594  mov     rcx, rsi; pv
0x18004c597  mov     [rsi], rax
0x18004c59a  call    cs:__imp_CoTaskMemFree
0x18004c5a0  mov     rcx, [rbp+57h+var_60]
0x18004c5a4  test    rcx, rcx
0x18004c5a7  jz      short loc_18004C5B9
0x18004c5a9  mov     rax, [rcx]
0x18004c5ac  mov     rax, [rax+10h]
0x18004c5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5b5  mov     [rbp+57h+var_60], r15
0x18004c5b9  mov     rcx, [rbp+57h+var_68]
0x18004c5bd  test    rcx, rcx
0x18004c5c0  jz      short loc_18004C5CE
0x18004c5c2  mov     rax, [rcx]
0x18004c5c5  mov     rax, [rax+10h]
0x18004c5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c5ce  lea     r11, [rsp+0C0h+var_20]
0x18004c5d6  mov     eax, ebx
0x18004c5d8  mov     rbx, [r11+38h]
0x18004c5dc  mov     rsi, [r11+40h]
0x18004c5e0  mov     rsp, r11
0x18004c5e3  pop     r15
0x18004c5e5  pop     r14
0x18004c5e7  pop     r12
0x18004c5e9  pop     rdi
0x18004c5ea  pop     rbp
0x18004c5eb  retn
```
