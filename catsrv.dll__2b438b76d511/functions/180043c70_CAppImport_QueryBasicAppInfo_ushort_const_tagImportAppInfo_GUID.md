# CAppImport::QueryBasicAppInfo(ushort const *,tagImportAppInfo *,_GUID *)

- ea: `0x180043c70`
- end: `0x18004401c`
- name: `?QueryBasicAppInfo@CAppImport@@AEAAJPEBGPEAUtagImportAppInfo@@PEAU_GUID@@@Z`
- size: `940`
- prototype: `__int64 __fastcall(CAppImport *__hidden this, const unsigned __int16 *, struct tagImportAppInfo *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043b4c`

## callees

- `0x18000a01c`
- `0x18001a6c8`
- `0x180042d60`
- `0x180043c70`
- `0x180055502`
- `0x180058010`

## import_xrefs

- `CLBCatQ!GetSimpleTableDispenser` at `0x180043ced`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180043ced`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043fef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043ee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043ee3`

## pseudocode

```c
__int64 __fastcall CAppImport::QueryBasicAppInfo(
        CAppImport *this,
        const unsigned __int16 *a2,
        struct tagImportAppInfo *a3,
        struct _GUID *a4)
{
  int SimpleTableDispenser; // eax
  bool v9; // zf
  int v10; // eax
  int v11; // ebx
  unsigned __int16 *v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // rax
  unsigned __int64 v15; // r15
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rbx
  unsigned __int64 v18; // rsi
  unsigned __int16 *v19; // rax
  __int64 v20; // rcx
  void *v21; // rcx
  int v23; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v24; // [rsp+54h] [rbp-25h] BYREF
  unsigned __int16 *v25; // [rsp+58h] [rbp-21h] BYREF
  __int64 v26; // [rsp+60h] [rbp-19h] BYREF
  signed __int64 v27; // [rsp+68h] [rbp-11h] BYREF
  const unsigned __int16 *v28; // [rsp+70h] [rbp-9h] BYREF
  int v29; // [rsp+78h] [rbp-1h]
  int v30; // [rsp+7Ch] [rbp+3h]
  int v31; // [rsp+80h] [rbp+7h]
  int v32; // [rsp+84h] [rbp+Bh]
  int v33; // [rsp+E8h] [rbp+6Fh] BYREF

  v28 = a2;
  v24 = 0;
  v23 = 0;
  v33 = 0;
  v25 = 0;
  v29 = 0;
  v30 = -268435455;
  v31 = 130;
  v26 = 0;
  v32 = 2 * safe_lstrlenW(a2) + 2;
  if ( !*((_QWORD *)this + 9) )
  {
    v27 = 0;
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v27);
    v9 = SimpleTableDispenser == 0;
    if ( SimpleTableDispenser < 0 )
      goto LABEL_6;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, v27, 0) )
      (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v10 = memcmp_0(tidCOMSERVICES_APLICATION_EXPORT, &TID_APPLICATION, 0x10u);
  v9 = (*(unsigned int (__fastcall **)(_QWORD, __int64 *, __int64 *, const unsigned __int16 **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
         *((_QWORD *)this + 9),
         didCOMSERVICES,
         tidCOMSERVICES_APLICATION_EXPORT,
         &v28,
         1,
         1,
         v10 != 0 ? 7 : 5,
         &v26) == 0;
LABEL_6:
  if ( !v9 )
  {
    v11 = -2146368504;
    goto LABEL_33;
  }
  if ( !v26 )
  {
    v11 = -2147024882;
LABEL_36:
    CoTaskMemFree(*(LPVOID *)a3);
    v21 = (void *)*((_QWORD *)a3 + 1);
    *(_QWORD *)a3 = 0;
    CoTaskMemFree(v21);
    *((_QWORD *)a3 + 1) = 0;
    return (unsigned int)v11;
  }
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26);
  if ( !v11 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, _QWORD))(*(_QWORD *)v26 + 72LL))(
            v26,
            0,
            0,
            0,
            0,
            0,
            0,
            &v24,
            0);
    if ( v11 >= 0 )
    {
      if ( v24 > 1 )
      {
        v11 = -2147418113;
        goto LABEL_33;
      }
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v26 + 40LL))(v26) == -2146367487 )
      {
        v11 = 0;
        goto LABEL_33;
      }
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned __int16 **))(*(_QWORD *)v26 + 64LL))(
              v26,
              1,
              &v23,
              &v33,
              &v25);
      if ( v11 >= 0 )
      {
        v12 = v25;
        v13 = -1;
        if ( !v25 )
          goto LABEL_23;
        v14 = -1;
        do
          ++v14;
        while ( v25[v14] );
        v15 = v14 + 1;
        v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v14 + 1));
        *(_QWORD *)a3 = v16;
        if ( !v16 )
        {
          v11 = -2147024882;
          goto LABEL_33;
        }
        v11 = StringCchCopyW(v16, v15, v12);
        if ( v11 >= 0 )
        {
LABEL_23:
          v11 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned __int16 **))(*(_QWORD *)v26 + 64LL))(
                  v26,
                  10,
                  &v23,
                  &v33,
                  &v25);
          if ( !v11 )
          {
            v17 = v25;
            if ( !v25 )
              goto LABEL_29;
            do
              ++v13;
            while ( v25[v13] );
            v18 = v13 + 1;
            v19 = (unsigned __int16 *)CoTaskMemAlloc(2 * v18);
            *((_QWORD *)a3 + 1) = v19;
            if ( !v19 )
            {
              v11 = -2147024882;
              goto LABEL_33;
            }
            v11 = StringCchCopyW(v19, v18, v17);
            if ( v11 >= 0 )
            {
LABEL_29:
              v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, int *, unsigned __int16 **))(*(_QWORD *)v26 + 64LL))(
                      v26,
                      0,
                      &v23,
                      &v33,
                      &v25);
              if ( !v11 )
              {
                v20 = v26;
                *a4 = *(struct _GUID *)v25;
                v11 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned __int16 **))(*(_QWORD *)v20 + 64LL))(
                        v20,
                        33,
                        &v23,
                        &v33,
                        &v25);
                if ( !v11 )
                {
                  *((_DWORD *)a3 + 5) = *(_DWORD *)v25 != 0;
                  v11 = (*(__int64 (__fastcall **)(__int64, __int64, int *, int *, unsigned __int16 **))(*(_QWORD *)v26 + 64LL))(
                          v26,
                          6,
                          &v23,
                          &v33,
                          &v25);
                  if ( v11 >= 0 )
                  {
                    *((_DWORD *)a3 + 6) = v25 != 0;
                    v11 = CAppImport::AreUsersPresent(this, a4, a2, (int *)a3 + 4);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_33:
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v11 < 0 )
    goto LABEL_36;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180043c70  push    rbp
0x180043c72  push    rbx
0x180043c73  push    rsi
0x180043c74  push    rdi
0x180043c75  push    r12
0x180043c77  push    r13
0x180043c79  push    r14
0x180043c7b  push    r15
0x180043c7d  lea     rbp, [rsp-1Fh]
0x180043c82  sub     rsp, 98h
0x180043c89  xor     r15d, r15d
0x180043c8c  mov     [rbp+57h+var_60], rdx
0x180043c90  mov     r14, rcx
0x180043c93  mov     [rbp+57h+var_7C], r15d
0x180043c97  mov     rcx, rdx; unsigned __int16 *
0x180043c9a  mov     [rbp+57h+var_80], r15d
0x180043c9e  mov     [rbp+57h+arg_8], r15d
0x180043ca2  mov     r13, r9
0x180043ca5  mov     [rbp+57h+var_78], r15
0x180043ca9  mov     rdi, r8
0x180043cac  mov     [rbp+57h+var_58], r15d
0x180043cb0  mov     r12, rdx
0x180043cb3  mov     [rbp+57h+var_54], 0F0000001h
0x180043cba  mov     [rbp+57h+var_50], 82h
0x180043cc1  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180043cc6  lea     esi, [r15+1]
0x180043cca  mov     [rbp+57h+var_70], r15
0x180043cce  lea     eax, ds:2[rax*2]
0x180043cd5  mov     [rbp+57h+var_4C], eax
0x180043cd8  cmp     [r14+48h], r15
0x180043cdc  jnz     short loc_180043D15
0x180043cde  lea     rdx, [rbp+57h+var_68]
0x180043ce2  mov     [rbp+57h+var_68], r15
0x180043ce6  lea     rcx, IID_ISimpleTableDispenser
0x180043ced  call    cs:__imp_GetSimpleTableDispenser
0x180043cf3  test    eax, eax
0x180043cf5  js      short loc_180043D72
0x180043cf7  mov     rcx, [rbp+57h+var_68]
0x180043cfb  xor     eax, eax
0x180043cfd  lock cmpxchg [r14+48h], rcx
0x180043d03  jz      short loc_180043D15
0x180043d05  mov     rcx, [rbp+57h+var_68]
0x180043d09  mov     rax, [rcx]
0x180043d0c  mov     rax, [rax+10h]
0x180043d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d15  mov     r8d, 10h; Size
0x180043d1b  lea     rdx, TID_APPLICATION; Buf2
0x180043d22  lea     rcx, tidCOMSERVICES_APLICATION_EXPORT; Buf1
0x180043d29  call    memcmp_0
0x180043d2e  mov     rcx, [r14+48h]
0x180043d32  lea     r9, [rbp+57h+var_70]
0x180043d36  mov     [rsp+0D0h+var_98], r9
0x180043d3b  lea     r8, tidCOMSERVICES_APLICATION_EXPORT
0x180043d42  neg     eax
0x180043d44  lea     r9, [rbp+57h+var_60]
0x180043d48  mov     rax, [rcx]
0x180043d4b  sbb     edx, edx
0x180043d4d  and     edx, 2
0x180043d50  add     edx, 5
0x180043d53  mov     dword ptr [rsp+0D0h+var_A0], edx
0x180043d57  lea     rdx, didCOMSERVICES
0x180043d5e  mov     rax, [rax+18h]
0x180043d62  mov     dword ptr [rsp+0D0h+var_A8], esi
0x180043d66  mov     [rsp+0D0h+var_B0], rsi
0x180043d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d70  test    eax, eax
0x180043d72  jz      short loc_180043D7E
0x180043d74  mov     ebx, 80110408h
0x180043d79  jmp     loc_180043FD3
0x180043d7e  mov     rcx, [rbp+57h+var_70]
0x180043d82  test    rcx, rcx
0x180043d85  jnz     short loc_180043D91
0x180043d87  mov     ebx, 8007000Eh
0x180043d8c  jmp     loc_180043FEC
0x180043d91  mov     rax, [rcx]
0x180043d94  mov     rax, [rax+18h]
0x180043d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d9d  mov     ebx, eax
0x180043d9f  test    eax, eax
0x180043da1  jnz     loc_180043FD3
0x180043da7  mov     rcx, [rbp+57h+var_70]
0x180043dab  lea     rdx, [rbp+57h+var_7C]
0x180043daf  mov     [rsp+0D0h+var_90], r15
0x180043db4  xor     r9d, r9d
0x180043db7  mov     [rsp+0D0h+var_98], rdx
0x180043dbc  xor     r8d, r8d
0x180043dbf  mov     [rsp+0D0h+var_A0], r15
0x180043dc4  xor     edx, edx
0x180043dc6  mov     rax, [rcx]
0x180043dc9  mov     [rsp+0D0h+var_A8], r15
0x180043dce  mov     [rsp+0D0h+var_B0], r15
0x180043dd3  mov     rax, [rax+48h]
0x180043dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ddc  mov     ebx, eax
0x180043dde  test    eax, eax
0x180043de0  js      loc_180043FD3
0x180043de6  cmp     [rbp+57h+var_7C], esi
0x180043de9  jbe     short loc_180043DF5
0x180043deb  mov     ebx, 8000FFFFh
0x180043df0  jmp     loc_180043FD3
0x180043df5  mov     rcx, [rbp+57h+var_70]
0x180043df9  mov     rax, [rcx]
0x180043dfc  mov     rax, [rax+28h]
0x180043e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e05  cmp     eax, 80110801h
0x180043e0a  jnz     short loc_180043E14
0x180043e0c  mov     ebx, r15d
0x180043e0f  jmp     loc_180043FD3
0x180043e14  mov     rcx, [rbp+57h+var_70]
0x180043e18  lea     r8, [rbp+57h+var_78]
0x180043e1c  mov     [rsp+0D0h+var_B0], r8
0x180043e21  lea     r9, [rbp+57h+arg_8]
0x180043e25  lea     r8, [rbp+57h+var_80]
0x180043e29  mov     edx, esi
0x180043e2b  mov     rax, [rcx]
0x180043e2e  mov     rax, [rax+40h]
0x180043e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e37  mov     ebx, eax
0x180043e39  test    eax, eax
0x180043e3b  js      loc_180043FD3
0x180043e41  mov     rbx, [rbp+57h+var_78]
0x180043e45  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180043e49  test    rbx, rbx
0x180043e4c  jz      short loc_180043E99
0x180043e4e  mov     rax, rsi
0x180043e51  inc     rax
0x180043e54  cmp     [rbx+rax*2], r15w
0x180043e59  jnz     short loc_180043E51
0x180043e5b  lea     r15, [rax+1]
0x180043e5f  lea     rcx, [r15+r15]; cb
0x180043e63  call    cs:__imp_CoTaskMemAlloc
0x180043e69  mov     [rdi], rax
0x180043e6c  test    rax, rax
0x180043e6f  jnz     short loc_180043E7E
0x180043e71  mov     ebx, 8007000Eh
0x180043e76  xor     r15d, r15d
0x180043e79  jmp     loc_180043FD3
0x180043e7e  mov     r8, rbx; unsigned __int16 *
0x180043e81  mov     rdx, r15; unsigned __int64
0x180043e84  mov     rcx, rax; unsigned __int16 *
0x180043e87  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043e8c  xor     r15d, r15d
0x180043e8f  mov     ebx, eax
0x180043e91  test    eax, eax
0x180043e93  js      loc_180043FD3
0x180043e99  mov     rcx, [rbp+57h+var_70]
0x180043e9d  lea     rdx, [rbp+57h+var_78]
0x180043ea1  mov     [rsp+0D0h+var_B0], rdx
0x180043ea6  lea     r9, [rbp+57h+arg_8]
0x180043eaa  lea     r8, [rbp+57h+var_80]
0x180043eae  mov     edx, 0Ah
0x180043eb3  mov     rax, [rcx]
0x180043eb6  mov     rax, [rax+40h]
0x180043eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ebf  mov     ebx, eax
0x180043ec1  test    eax, eax
0x180043ec3  jnz     loc_180043FD3
0x180043ec9  mov     rbx, [rbp+57h+var_78]
0x180043ecd  test    rbx, rbx
0x180043ed0  jz      short loc_180043F14
0x180043ed2  inc     rsi
0x180043ed5  cmp     [rbx+rsi*2], r15w
0x180043eda  jnz     short loc_180043ED2
0x180043edc  inc     rsi
0x180043edf  lea     rcx, [rsi+rsi]; cb
0x180043ee3  call    cs:__imp_CoTaskMemAlloc
0x180043ee9  mov     [rdi+8], rax
0x180043eed  test    rax, rax
0x180043ef0  jnz     short loc_180043EFC
0x180043ef2  mov     ebx, 8007000Eh
0x180043ef7  jmp     loc_180043FD3
0x180043efc  mov     r8, rbx; unsigned __int16 *
0x180043eff  mov     rdx, rsi; unsigned __int64
0x180043f02  mov     rcx, rax; unsigned __int16 *
0x180043f05  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043f0a  mov     ebx, eax
0x180043f0c  test    eax, eax
0x180043f0e  js      loc_180043FD3
0x180043f14  mov     rcx, [rbp+57h+var_70]
0x180043f18  lea     rdx, [rbp+57h+var_78]
0x180043f1c  mov     [rsp+0D0h+var_B0], rdx
0x180043f21  lea     r9, [rbp+57h+arg_8]
0x180043f25  lea     r8, [rbp+57h+var_80]
0x180043f29  xor     edx, edx
0x180043f2b  mov     rax, [rcx]
0x180043f2e  mov     rax, [rax+40h]
0x180043f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f37  mov     ebx, eax
0x180043f39  test    eax, eax
0x180043f3b  jnz     loc_180043FD3
0x180043f41  mov     rax, [rbp+57h+var_78]
0x180043f45  lea     rdx, [rbp+57h+var_78]
0x180043f49  mov     rcx, [rbp+57h+var_70]
0x180043f4d  lea     r9, [rbp+57h+arg_8]
0x180043f51  mov     [rsp+0D0h+var_B0], rdx
0x180043f56  lea     r8, [rbp+57h+var_80]
0x180043f5a  lea     edx, [rbx+21h]
0x180043f5d  movups  xmm0, xmmword ptr [rax]
0x180043f60  movdqu  xmmword ptr [r13+0], xmm0
0x180043f66  mov     rax, [rcx]
0x180043f69  mov     rax, [rax+40h]
0x180043f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f72  mov     ebx, eax
0x180043f74  test    eax, eax
0x180043f76  jnz     short loc_180043FD3
0x180043f78  mov     rax, [rbp+57h+var_78]
0x180043f7c  lea     rdx, [rbp+57h+var_78]
0x180043f80  mov     ecx, r15d
0x180043f83  mov     [rsp+0D0h+var_B0], rdx
0x180043f88  lea     r9, [rbp+57h+arg_8]
0x180043f8c  lea     r8, [rbp+57h+var_80]
0x180043f90  cmp     [rax], r15d
0x180043f93  lea     edx, [rbx+6]
0x180043f96  setnz   cl
0x180043f99  mov     [rdi+14h], ecx
0x180043f9c  mov     rcx, [rbp+57h+var_70]
0x180043fa0  mov     rax, [rcx]
0x180043fa3  mov     rax, [rax+40h]
0x180043fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fac  mov     ebx, eax
0x180043fae  test    eax, eax
0x180043fb0  js      short loc_180043FD3
0x180043fb2  cmp     [rbp+57h+var_78], r15
0x180043fb6  lea     r9, [rdi+10h]; int *
0x180043fba  mov     eax, r15d
0x180043fbd  mov     r8, r12; unsigned __int16 *
0x180043fc0  setnz   al
0x180043fc3  mov     rdx, r13; struct _GUID *
0x180043fc6  mov     rcx, r14; this
0x180043fc9  mov     [rdi+18h], eax
0x180043fcc  call    ?AreUsersPresent@CAppImport@@AEAAJAEBU_GUID@@PEBGPEAH@Z; CAppImport::AreUsersPresent(_GUID const &,ushort const *,int *)
0x180043fd1  mov     ebx, eax
0x180043fd3  mov     rcx, [rbp+57h+var_70]
0x180043fd7  test    rcx, rcx
0x180043fda  jz      short loc_180043FE8
0x180043fdc  mov     rax, [rcx]
0x180043fdf  mov     rax, [rax+10h]
0x180043fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fe8  test    ebx, ebx
0x180043fea  jns     short loc_180044006
0x180043fec  mov     rcx, [rdi]; pv
0x180043fef  call    cs:__imp_CoTaskMemFree
0x180043ff5  mov     rcx, [rdi+8]; pv
0x180043ff9  mov     [rdi], r15
0x180043ffc  call    cs:__imp_CoTaskMemFree
0x180044002  mov     [rdi+8], r15
0x180044006  mov     eax, ebx
0x180044008  add     rsp, 98h
0x18004400f  pop     r15
0x180044011  pop     r14
0x180044013  pop     r13
0x180044015  pop     r12
0x180044017  pop     rdi
0x180044018  pop     rsi
0x180044019  pop     rbx
0x18004401a  pop     rbp
0x18004401b  retn
```
