# CAppExport::ExportRoleSet(_GUID,ushort *)

- ea: `0x18004cd0c`
- end: `0x18004d097`
- name: `?ExportRoleSet@CAppExport@@AEAAJU_GUID@@PEAG@Z`
- size: `907`
- prototype: `int(CAppExport *__hidden this, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004d0a0`

## callees

- `0x18001a6c8`
- `0x18004cd0c`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x18004cd75`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004ce8f`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004cd75`
- `CLBCatQ!GetSimpleTableDispenser` at `0x18004ce8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d045`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cf59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004cf59`

## pseudocode

```c
__int64 __fastcall CAppExport::ExportRoleSet(CAppExport *this, struct _GUID *a2, unsigned __int16 *a3)
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
  struct _GUID *v19; // [rsp+70h] [rbp+7h] BYREF
  int v20; // [rsp+78h] [rbp+Fh]
  int v21; // [rsp+7Ch] [rbp+13h]
  int v22; // [rsp+80h] [rbp+17h]
  int v23; // [rsp+84h] [rbp+1Bh]
  unsigned __int16 *v24; // [rsp+88h] [rbp+1Fh] BYREF
  int v25; // [rsp+90h] [rbp+27h]
  int v26; // [rsp+94h] [rbp+2Bh]
  int v27; // [rsp+98h] [rbp+2Fh]
  int v28; // [rsp+9Ch] [rbp+33h]

  v19 = a2;
  v16 = 0;
  v20 = 0;
  v21 = 2;
  v23 = 16;
  v22 = 72;
  v17 = 0;
  if ( *((_QWORD *)this + 22) )
  {
LABEL_5:
    v6 = memcmp_0(&tidCOMSERVICES_ROLESET, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, struct _GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLESET,
                             &v19,
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
  v24 = a3;
  v25 = 0;
  v26 = -268435455;
  v27 = 130;
  v7 = safe_lstrlenW(a3);
  v16 = 0;
  v28 = 2 * v7 + 2;
  if ( *((_QWORD *)this + 22) )
    goto LABEL_15;
  v15 = 0;
  SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v15);
  if ( SimpleTableDispenser >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 22, v15, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_15:
    v8 = memcmp_0(&tidCOMSERVICES_ROLESET_EXPORT, &TID_APPLICATION, 0x10u);
    SimpleTableDispenser = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int128 *, unsigned __int16 **, __int64, int, int, __int64 **))(**((_QWORD **)this + 22) + 24LL))(
                             *((_QWORD *)this + 22),
                             didCOMSERVICES,
                             &tidCOMSERVICES_ROLESET_EXPORT,
                             &v24,
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
0x18004cd0c  mov     [rsp-8+arg_8], rbx
0x18004cd11  mov     [rsp-8+arg_10], rsi
0x18004cd16  push    rbp
0x18004cd17  push    rdi
0x18004cd18  push    r12
0x18004cd1a  push    r14
0x18004cd1c  push    r15
0x18004cd1e  lea     rbp, [rsp-37h]
0x18004cd23  sub     rsp, 0A0h
0x18004cd2a  xor     r15d, r15d
0x18004cd2d  mov     [rbp+57h+var_50], rdx
0x18004cd31  mov     rsi, r8
0x18004cd34  mov     rdi, rcx
0x18004cd37  mov     [rbp+57h+var_68], r15
0x18004cd3b  mov     [rbp+57h+var_48], r15d
0x18004cd3f  lea     r14d, [r15+10h]
0x18004cd43  mov     [rbp+57h+var_44], 2
0x18004cd4a  lea     r12d, [r15+1]
0x18004cd4e  mov     [rbp+57h+var_3C], r14d
0x18004cd52  mov     [rbp+57h+var_40], 48h ; 'H'
0x18004cd59  mov     [rbp+57h+var_60], r15
0x18004cd5d  cmp     [rcx+0B0h], r15
0x18004cd64  jnz     short loc_18004CDA2
0x18004cd66  lea     rdx, [rbp+57h+var_70]
0x18004cd6a  mov     [rbp+57h+var_70], r15
0x18004cd6e  lea     rcx, IID_ISimpleTableDispenser
0x18004cd75  call    cs:__imp_GetSimpleTableDispenser
0x18004cd7b  mov     ebx, eax
0x18004cd7d  test    eax, eax
0x18004cd7f  js      short loc_18004CE00
0x18004cd81  mov     rcx, [rbp+57h+var_70]
0x18004cd85  xor     eax, eax
0x18004cd87  lock cmpxchg [rdi+0B0h], rcx
0x18004cd90  jz      short loc_18004CDA2
0x18004cd92  mov     rcx, [rbp+57h+var_70]
0x18004cd96  mov     rax, [rcx]
0x18004cd99  mov     rax, [rax+10h]
0x18004cd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cda2  mov     r8, r14; Size
0x18004cda5  lea     rdx, TID_APPLICATION; Buf2
0x18004cdac  lea     rcx, tidCOMSERVICES_ROLESET; Buf1
0x18004cdb3  call    memcmp_0
0x18004cdb8  mov     rcx, [rdi+0B0h]
0x18004cdbf  lea     r9, [rbp+57h+var_60]
0x18004cdc3  mov     [rsp+0C0h+var_88], r9
0x18004cdc8  lea     r8, tidCOMSERVICES_ROLESET
0x18004cdcf  neg     eax
0x18004cdd1  lea     r9, [rbp+57h+var_50]
0x18004cdd5  mov     rax, [rcx]
0x18004cdd8  sbb     edx, edx
0x18004cdda  and     edx, 2
0x18004cddd  add     edx, 5
0x18004cde0  mov     [rsp+0C0h+var_90], edx
0x18004cde4  lea     rdx, didCOMSERVICES
0x18004cdeb  mov     rax, [rax+18h]
0x18004cdef  mov     [rsp+0C0h+var_98], r12d
0x18004cdf4  mov     [rsp+0C0h+var_A0], r12
0x18004cdf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdfe  mov     ebx, eax
0x18004ce00  test    ebx, ebx
0x18004ce02  js      loc_18004D04B
0x18004ce08  mov     rcx, [rbp+57h+var_60]
0x18004ce0c  test    rcx, rcx
0x18004ce0f  jnz     short loc_18004CE1B
0x18004ce11  mov     ebx, 8007000Eh
0x18004ce16  jmp     loc_18004D064
0x18004ce1b  mov     rax, [rcx]
0x18004ce1e  mov     rax, [rax+18h]
0x18004ce22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce27  mov     ebx, eax
0x18004ce29  test    eax, eax
0x18004ce2b  js      loc_18004D04B
0x18004ce31  mov     rcx, [rbp+57h+var_60]
0x18004ce35  mov     rax, [rcx]
0x18004ce38  mov     rax, [rax+20h]
0x18004ce3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce41  mov     ebx, eax
0x18004ce43  test    eax, eax
0x18004ce45  js      loc_18004D04B
0x18004ce4b  mov     rcx, rsi; unsigned __int16 *
0x18004ce4e  mov     [rbp+57h+var_38], rsi
0x18004ce52  mov     [rbp+57h+var_30], r15d
0x18004ce56  mov     [rbp+57h+var_2C], 0F0000001h
0x18004ce5d  mov     [rbp+57h+var_28], 82h
0x18004ce64  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004ce69  mov     [rbp+57h+var_68], r15
0x18004ce6d  lea     eax, ds:2[rax*2]
0x18004ce74  mov     [rbp+57h+var_24], eax
0x18004ce77  cmp     [rdi+0B0h], r15
0x18004ce7e  jnz     short loc_18004CEC0
0x18004ce80  lea     rdx, [rbp+57h+var_70]
0x18004ce84  mov     [rbp+57h+var_70], r15
0x18004ce88  lea     rcx, IID_ISimpleTableDispenser
0x18004ce8f  call    cs:__imp_GetSimpleTableDispenser
0x18004ce95  mov     ebx, eax
0x18004ce97  test    eax, eax
0x18004ce99  js      loc_18004CF22
0x18004ce9f  mov     rcx, [rbp+57h+var_70]
0x18004cea3  xor     eax, eax
0x18004cea5  lock cmpxchg [rdi+0B0h], rcx
0x18004ceae  jz      short loc_18004CEC0
0x18004ceb0  mov     rcx, [rbp+57h+var_70]
0x18004ceb4  mov     rax, [rcx]
0x18004ceb7  mov     rax, [rax+10h]
0x18004cebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cec0  mov     r8, r14; Size
0x18004cec3  lea     rdx, TID_APPLICATION; Buf2
0x18004ceca  lea     rcx, tidCOMSERVICES_ROLESET_EXPORT; Buf1
0x18004ced1  call    memcmp_0
0x18004ced6  mov     rcx, [rdi+0B0h]
0x18004cedd  lea     r10, [rbp+57h+var_68]
0x18004cee1  neg     eax
0x18004cee3  mov     [rsp+0C0h+var_88], r10
0x18004cee8  lea     r8, tidCOMSERVICES_ROLESET_EXPORT
0x18004ceef  sbb     r9d, r9d
0x18004cef2  lea     rdx, didCOMSERVICES
0x18004cef9  mov     rax, [rcx]
0x18004cefc  and     r9d, 2
0x18004cf00  add     r9d, 4
0x18004cf04  mov     [rsp+0C0h+var_90], r9d
0x18004cf09  lea     r9, [rbp+57h+var_38]
0x18004cf0d  mov     [rsp+0C0h+var_98], r12d
0x18004cf12  mov     rax, [rax+18h]
0x18004cf16  mov     [rsp+0C0h+var_A0], r12
0x18004cf1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf20  mov     ebx, eax
0x18004cf22  test    ebx, ebx
0x18004cf24  js      loc_18004D04B
0x18004cf2a  cmp     [rbp+57h+var_68], r15
0x18004cf2e  jnz     short loc_18004CF3A
0x18004cf30  mov     ebx, 8007000Eh
0x18004cf35  jmp     loc_18004D04B
0x18004cf3a  mov     rcx, [rbp+57h+var_68]
0x18004cf3e  mov     rax, [rcx]
0x18004cf41  mov     rax, [rax+18h]
0x18004cf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf4a  mov     ebx, eax
0x18004cf4c  test    eax, eax
0x18004cf4e  js      loc_18004D04B
0x18004cf54  mov     ecx, 18h; cb
0x18004cf59  call    cs:__imp_CoTaskMemAlloc
0x18004cf5f  mov     rsi, rax
0x18004cf62  test    rax, rax
0x18004cf65  jz      short loc_18004CF30
0x18004cf67  mov     rcx, [rbp+57h+var_60]
0x18004cf6b  mov     rax, [rcx]
0x18004cf6e  mov     rax, [rax+28h]
0x18004cf72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf77  mov     rcx, [rbp+57h+var_68]
0x18004cf7b  cmp     eax, 80110801h
0x18004cf80  mov     rax, [rcx]
0x18004cf83  jz      loc_18004D032
0x18004cf89  mov     rax, [rax+78h]
0x18004cf8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf92  mov     ebx, eax
0x18004cf94  test    eax, eax
0x18004cf96  js      loc_18004D03D
0x18004cf9c  xor     eax, eax
0x18004cf9e  mov     edi, r15d
0x18004cfa1  mov     [rsi], rax
0x18004cfa4  cmp     edi, 3
0x18004cfa7  jnb     short loc_18004D013
0x18004cfa9  mov     rcx, [rbp+57h+var_60]
0x18004cfad  lea     r9, [rbp+57h+var_70]
0x18004cfb1  mov     eax, edi
0x18004cfb3  lea     r8, [rbp+57h+var_58]
0x18004cfb7  mov     [rbp+57h+var_58], r15d
0x18004cfbb  mov     edx, edi
0x18004cfbd  mov     dword ptr [rbp+57h+var_70], r15d
0x18004cfc1  lea     r14, [rsi+rax*8]
0x18004cfc5  mov     rax, [rcx]
0x18004cfc8  mov     [rsp+0C0h+var_A0], r14
0x18004cfcd  mov     rax, [rax+40h]
0x18004cfd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfd6  mov     ebx, eax
0x18004cfd8  test    eax, eax
0x18004cfda  js      short loc_18004D03D
0x18004cfdc  mov     r9, [r14]
0x18004cfdf  test    r9, r9
0x18004cfe2  jz      short loc_18004D00E
0x18004cfe4  mov     rcx, [rbp+57h+var_68]
0x18004cfe8  mov     r8d, r15d
0x18004cfeb  cmp     [rbp+57h+var_58], 80h
0x18004cff2  mov     edx, edi
0x18004cff4  cmovz   r8d, dword ptr [rbp+57h+var_70]
0x18004cff9  mov     rax, [rcx]
0x18004cffc  mov     rax, [rax+0A0h]
0x18004d003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d008  mov     ebx, eax
0x18004d00a  test    eax, eax
0x18004d00c  js      short loc_18004D03D
0x18004d00e  add     edi, r12d
0x18004d011  jmp     short loc_18004CFA4
0x18004d013  mov     rcx, [rbp+57h+var_68]
0x18004d017  mov     rax, [rcx]
0x18004d01a  mov     rax, [rax+90h]
0x18004d021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d026  mov     ebx, eax
0x18004d028  test    eax, eax
0x18004d02a  jns     loc_18004CF67
0x18004d030  jmp     short loc_18004D03D
0x18004d032  mov     rax, [rax+60h]
0x18004d036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d03b  mov     ebx, eax
0x18004d03d  xor     eax, eax
0x18004d03f  mov     rcx, rsi; pv
0x18004d042  mov     [rsi], rax
0x18004d045  call    cs:__imp_CoTaskMemFree
0x18004d04b  mov     rcx, [rbp+57h+var_60]
0x18004d04f  test    rcx, rcx
0x18004d052  jz      short loc_18004D064
0x18004d054  mov     rax, [rcx]
0x18004d057  mov     rax, [rax+10h]
0x18004d05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d060  mov     [rbp+57h+var_60], r15
0x18004d064  mov     rcx, [rbp+57h+var_68]
0x18004d068  test    rcx, rcx
0x18004d06b  jz      short loc_18004D079
0x18004d06d  mov     rax, [rcx]
0x18004d070  mov     rax, [rax+10h]
0x18004d074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d079  lea     r11, [rsp+0C0h+var_20]
0x18004d081  mov     eax, ebx
0x18004d083  mov     rbx, [r11+38h]
0x18004d087  mov     rsi, [r11+40h]
0x18004d08b  mov     rsp, r11
0x18004d08e  pop     r15
0x18004d090  pop     r14
0x18004d092  pop     r12
0x18004d094  pop     rdi
0x18004d095  pop     rbp
0x18004d096  retn
```
