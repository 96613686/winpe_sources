# CAppExport::ExportRoleSDCache(_GUID,ushort *)

- ea: `0x18004c980`
- end: `0x18004cd04`
- name: `?ExportRoleSDCache@CAppExport@@AEAAJU_GUID@@PEAG@Z`
- size: `900`
- prototype: `int(CAppExport *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d0a0`

## callees

- `0x18001a6c8`
- `0x18004c980`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c9e2`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004cafc`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004c9e2`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004cafc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ccb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ccb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cbc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cbc6`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportRoleSDCache(CAppExport *this, struct _GUID *a2, unsigned __int16 *a3)
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
    v6 = memcmp_0(&tidCOMSERVICES_ROLESDCACHE, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, _QWORD *, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLESDCACHE,
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
    v8 = memcmp_0(&tidCOMSERVICES_ROLESDCACHE_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, unsigned __int16 **, __int64, int, int, __int64 **))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLESDCACHE_EXPORT,
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
0x18004c980  mov     [rsp-8+arg_8], rbx
0x18004c985  mov     [rsp-8+arg_10], rsi
0x18004c98a  push    rbp
0x18004c98b  push    rdi
0x18004c98c  push    r12
0x18004c98e  push    r14
0x18004c990  push    r15
0x18004c992  lea     rbp, [rsp-37h]
0x18004c997  sub     rsp, 0A0h
0x18004c99e  xor     r15d, r15d
0x18004c9a1  mov     [rbp+57h+var_50], rdx
0x18004c9a5  mov     rsi, r8
0x18004c9a8  mov     rdi, rcx
0x18004c9ab  mov     [rbp+57h+var_68], r15
0x18004c9af  mov     [rbp+57h+var_48], r15
0x18004c9b3  lea     r14d, [r15+10h]
0x18004c9b7  mov     [rbp+57h+var_40], 48h ; 'H'
0x18004c9be  lea     r12d, [r15+1]
0x18004c9c2  mov     [rbp+57h+var_3C], r14d
0x18004c9c6  mov     [rbp+57h+var_60], r15
0x18004c9ca  cmp     [rcx+0B0h], r15
0x18004c9d1  jnz     short loc_18004CA0F
0x18004c9d3  lea     rdx, [rbp+57h+var_70]
0x18004c9d7  mov     [rbp+57h+var_70], r15
0x18004c9db  lea     rcx, IID_ISimpleTableDispenser
0x18004c9e2  call    cs:__imp_GetSimpleTableDispenser
0x18004c9e8  mov     ebx, eax
0x18004c9ea  test    eax, eax
0x18004c9ec  js      short loc_18004CA6D
0x18004c9ee  mov     rcx, [rbp+57h+var_70]
0x18004c9f2  xor     eax, eax
0x18004c9f4  lock cmpxchg [rdi+0B0h], rcx
0x18004c9fd  jz      short loc_18004CA0F
0x18004c9ff  mov     rcx, [rbp+57h+var_70]
0x18004ca03  mov     rax, [rcx]
0x18004ca06  mov     rax, [rax+10h]
0x18004ca0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca0f  mov     r8, r14; Size
0x18004ca12  lea     rdx, TID_APPLICATION; Buf2
0x18004ca19  lea     rcx, tidCOMSERVICES_ROLESDCACHE; Buf1
0x18004ca20  call    memcmp_0
0x18004ca25  mov     rcx, [rdi+0B0h]
0x18004ca2c  lea     r9, [rbp+57h+var_60]
0x18004ca30  mov     [rsp+0C0h+var_88], r9
0x18004ca35  lea     r8, tidCOMSERVICES_ROLESDCACHE
0x18004ca3c  neg     eax
0x18004ca3e  lea     r9, [rbp+57h+var_50]
0x18004ca42  mov     rax, [rcx]
0x18004ca45  sbb     edx, edx
0x18004ca47  and     edx, 2
0x18004ca4a  add     edx, 5
0x18004ca4d  mov     [rsp+0C0h+var_90], edx
0x18004ca51  lea     rdx, didCOMSERVICES
0x18004ca58  mov     rax, [rax+18h]
0x18004ca5c  mov     [rsp+0C0h+var_98], r12d
0x18004ca61  mov     [rsp+0C0h+var_A0], r12
0x18004ca66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca6b  mov     ebx, eax
0x18004ca6d  test    ebx, ebx
0x18004ca6f  js      loc_18004CCB8
0x18004ca75  mov     rcx, [rbp+57h+var_60]
0x18004ca79  test    rcx, rcx
0x18004ca7c  jnz     short loc_18004CA88
0x18004ca7e  mov     ebx, 8007000Eh
0x18004ca83  jmp     loc_18004CCD1
0x18004ca88  mov     rax, [rcx]
0x18004ca8b  mov     rax, [rax+18h]
0x18004ca8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca94  mov     ebx, eax
0x18004ca96  test    eax, eax
0x18004ca98  js      loc_18004CCB8
0x18004ca9e  mov     rcx, [rbp+57h+var_60]
0x18004caa2  mov     rax, [rcx]
0x18004caa5  mov     rax, [rax+20h]
0x18004caa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caae  mov     ebx, eax
0x18004cab0  test    eax, eax
0x18004cab2  js      loc_18004CCB8
0x18004cab8  mov     rcx, rsi; unsigned __int16 *
0x18004cabb  mov     [rbp+57h+var_38], rsi
0x18004cabf  mov     [rbp+57h+var_30], r15d
0x18004cac3  mov     [rbp+57h+var_2C], 0F0000001h
0x18004caca  mov     [rbp+57h+var_28], 82h
0x18004cad1  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004cad6  mov     [rbp+57h+var_68], r15
0x18004cada  lea     eax, ds:2[rax*2]
0x18004cae1  mov     [rbp+57h+var_24], eax
0x18004cae4  cmp     [rdi+0B0h], r15
0x18004caeb  jnz     short loc_18004CB2D
0x18004caed  lea     rdx, [rbp+57h+var_70]
0x18004caf1  mov     [rbp+57h+var_70], r15
0x18004caf5  lea     rcx, IID_ISimpleTableDispenser
0x18004cafc  call    cs:__imp_GetSimpleTableDispenser
0x18004cb02  mov     ebx, eax
0x18004cb04  test    eax, eax
0x18004cb06  js      loc_18004CB8F
0x18004cb0c  mov     rcx, [rbp+57h+var_70]
0x18004cb10  xor     eax, eax
0x18004cb12  lock cmpxchg [rdi+0B0h], rcx
0x18004cb1b  jz      short loc_18004CB2D
0x18004cb1d  mov     rcx, [rbp+57h+var_70]
0x18004cb21  mov     rax, [rcx]
0x18004cb24  mov     rax, [rax+10h]
0x18004cb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb2d  mov     r8, r14; Size
0x18004cb30  lea     rdx, TID_APPLICATION; Buf2
0x18004cb37  lea     rcx, tidCOMSERVICES_ROLESDCACHE_EXPORT; Buf1
0x18004cb3e  call    memcmp_0
0x18004cb43  mov     rcx, [rdi+0B0h]
0x18004cb4a  lea     r10, [rbp+57h+var_68]
0x18004cb4e  neg     eax
0x18004cb50  mov     [rsp+0C0h+var_88], r10
0x18004cb55  lea     r8, tidCOMSERVICES_ROLESDCACHE_EXPORT
0x18004cb5c  sbb     r9d, r9d
0x18004cb5f  lea     rdx, didCOMSERVICES
0x18004cb66  mov     rax, [rcx]
0x18004cb69  and     r9d, 2
0x18004cb6d  add     r9d, 4
0x18004cb71  mov     [rsp+0C0h+var_90], r9d
0x18004cb76  lea     r9, [rbp+57h+var_38]
0x18004cb7a  mov     [rsp+0C0h+var_98], r12d
0x18004cb7f  mov     rax, [rax+18h]
0x18004cb83  mov     [rsp+0C0h+var_A0], r12
0x18004cb88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb8d  mov     ebx, eax
0x18004cb8f  test    ebx, ebx
0x18004cb91  js      loc_18004CCB8
0x18004cb97  cmp     [rbp+57h+var_68], r15
0x18004cb9b  jnz     short loc_18004CBA7
0x18004cb9d  mov     ebx, 8007000Eh
0x18004cba2  jmp     loc_18004CCB8
0x18004cba7  mov     rcx, [rbp+57h+var_68]
0x18004cbab  mov     rax, [rcx]
0x18004cbae  mov     rax, [rax+18h]
0x18004cbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbb7  mov     ebx, eax
0x18004cbb9  test    eax, eax
0x18004cbbb  js      loc_18004CCB8
0x18004cbc1  mov     ecx, 18h; cb
0x18004cbc6  call    cs:__imp_CoTaskMemAlloc
0x18004cbcc  mov     rsi, rax
0x18004cbcf  test    rax, rax
0x18004cbd2  jz      short loc_18004CB9D
0x18004cbd4  mov     rcx, [rbp+57h+var_60]
0x18004cbd8  mov     rax, [rcx]
0x18004cbdb  mov     rax, [rax+28h]
0x18004cbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbe4  mov     rcx, [rbp+57h+var_68]
0x18004cbe8  cmp     eax, 80110801h
0x18004cbed  mov     rax, [rcx]
0x18004cbf0  jz      loc_18004CC9F
0x18004cbf6  mov     rax, [rax+78h]
0x18004cbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cbff  mov     ebx, eax
0x18004cc01  test    eax, eax
0x18004cc03  js      loc_18004CCAA
0x18004cc09  xor     eax, eax
0x18004cc0b  mov     edi, r15d
0x18004cc0e  mov     [rsi], rax
0x18004cc11  cmp     edi, 3
0x18004cc14  jnb     short loc_18004CC80
0x18004cc16  mov     rcx, [rbp+57h+var_60]
0x18004cc1a  lea     r9, [rbp+57h+var_70]
0x18004cc1e  mov     eax, edi
0x18004cc20  lea     r8, [rbp+57h+var_58]
0x18004cc24  mov     [rbp+57h+var_58], r15d
0x18004cc28  mov     edx, edi
0x18004cc2a  mov     dword ptr [rbp+57h+var_70], r15d
0x18004cc2e  lea     r14, [rsi+rax*8]
0x18004cc32  mov     rax, [rcx]
0x18004cc35  mov     [rsp+0C0h+var_A0], r14
0x18004cc3a  mov     rax, [rax+40h]
0x18004cc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc43  mov     ebx, eax
0x18004cc45  test    eax, eax
0x18004cc47  js      short loc_18004CCAA
0x18004cc49  mov     r9, [r14]
0x18004cc4c  test    r9, r9
0x18004cc4f  jz      short loc_18004CC7B
0x18004cc51  mov     rcx, [rbp+57h+var_68]
0x18004cc55  mov     r8d, r15d
0x18004cc58  cmp     [rbp+57h+var_58], 80h
0x18004cc5f  mov     edx, edi
0x18004cc61  cmovz   r8d, dword ptr [rbp+57h+var_70]
0x18004cc66  mov     rax, [rcx]
0x18004cc69  mov     rax, [rax+0A0h]
0x18004cc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc75  mov     ebx, eax
0x18004cc77  test    eax, eax
0x18004cc79  js      short loc_18004CCAA
0x18004cc7b  add     edi, r12d
0x18004cc7e  jmp     short loc_18004CC11
0x18004cc80  mov     rcx, [rbp+57h+var_68]
0x18004cc84  mov     rax, [rcx]
0x18004cc87  mov     rax, [rax+90h]
0x18004cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc93  mov     ebx, eax
0x18004cc95  test    eax, eax
0x18004cc97  jns     loc_18004CBD4
0x18004cc9d  jmp     short loc_18004CCAA
0x18004cc9f  mov     rax, [rax+60h]
0x18004cca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cca8  mov     ebx, eax
0x18004ccaa  xor     eax, eax
0x18004ccac  mov     rcx, rsi; pv
0x18004ccaf  mov     [rsi], rax
0x18004ccb2  call    cs:__imp_CoTaskMemFree
0x18004ccb8  mov     rcx, [rbp+57h+var_60]
0x18004ccbc  test    rcx, rcx
0x18004ccbf  jz      short loc_18004CCD1
0x18004ccc1  mov     rax, [rcx]
0x18004ccc4  mov     rax, [rax+10h]
0x18004ccc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cccd  mov     [rbp+57h+var_60], r15
0x18004ccd1  mov     rcx, [rbp+57h+var_68]
0x18004ccd5  test    rcx, rcx
0x18004ccd8  jz      short loc_18004CCE6
0x18004ccda  mov     rax, [rcx]
0x18004ccdd  mov     rax, [rax+10h]
0x18004cce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cce6  lea     r11, [rsp+0C0h+var_20]
0x18004ccee  mov     eax, ebx
0x18004ccf0  mov     rbx, [r11+38h]
0x18004ccf4  mov     rsi, [r11+40h]
0x18004ccf8  mov     rsp, r11
0x18004ccfb  pop     r15
0x18004ccfd  pop     r14
0x18004ccff  pop     r12
0x18004cd01  pop     rdi
0x18004cd02  pop     rbp
0x18004cd03  retn
```
