# CCOMComponentRegistrar::CheckForDuplicateProgID(_GUID const &)

- ea: `0x18002d9ec`
- end: `0x18002ded6`
- name: `?CheckForDuplicateProgID@CCOMComponentRegistrar@@AEAAJAEBU_GUID@@@Z`
- size: `1258`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000bf60`

## callees

- `0x180001e60`
- `0x180015594`
- `0x18002d9ec`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002da55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002da55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dc2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002deb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dc2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002dea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002deb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002db7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dc04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002db7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002dc04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCOMComponentRegistrar::CheckForDuplicateProgID(
        CCOMComponentRegistrar *this,
        const struct _GUID *a2)
{
  unsigned __int16 *v3; // rsi
  unsigned __int16 *v4; // rdi
  HRESULT v5; // ebx
  unsigned int v6; // ebx
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rax
  HRESULT v10; // eax
  int v11; // eax
  __int64 v13; // [rsp+50h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 *v15; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v16; // [rsp+68h] [rbp-11h] BYREF
  const struct _GUID *v17; // [rsp+70h] [rbp-9h] BYREF
  __int64 v18; // [rsp+78h] [rbp-1h]
  int v19; // [rsp+80h] [rbp+7h]
  int v20; // [rsp+84h] [rbp+Bh]
  unsigned __int16 *v21; // [rsp+88h] [rbp+Fh]
  int v22; // [rsp+90h] [rbp+17h]
  int v23; // [rsp+94h] [rbp+1Bh]
  int v24; // [rsp+98h] [rbp+1Fh]
  int v25; // [rsp+9Ch] [rbp+23h]
  unsigned int v26; // [rsp+E0h] [rbp+67h] BYREF
  int v27; // [rsp+E4h] [rbp+6Bh]
  int v28; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v29; // [rsp+F8h] [rbp+7Fh] BYREF

  v27 = HIDWORD(this);
  v15 = 0;
  v16 = 0;
  v28 = 0;
  v26 = 0;
  v29 = 0;
  v3 = 0;
  v4 = 0;
  ppv = 0;
  v13 = 0;
  v5 = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
  if ( v5 >= 0 )
  {
    if ( !ppv )
    {
      v5 = -2147024882;
      goto LABEL_47;
    }
    v17 = a2;
    v18 = 0;
    v19 = 72;
    v20 = 16;
    v5 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, const struct _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
           ppv,
           &didCOMSERVICES,
           &tidCOMSERVICES_CLASSES_INTERNAL,
           &v17,
           1,
           1,
           4,
           &v13);
    if ( v5 >= 0 )
    {
      if ( !v13 )
      {
LABEL_6:
        v5 = -2147024882;
        goto LABEL_45;
      }
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, unsigned __int16 **))(*(_QWORD *)v13 + 64LL))(
                   v13,
                   34,
                   &v28,
                   &v26,
                   &v15);
            if ( !v5 )
            {
              if ( v15 )
              {
                v6 = (v26 >> 1) + 1;
                v7 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v6, 2u));
                v3 = v7;
                if ( !v7 )
                  goto LABEL_6;
                v5 = StringCchCopyW(v7, v6, v15);
                if ( v5 < 0 )
                {
                  CoTaskMemFree(v3);
                  v3 = 0;
                  goto LABEL_45;
                }
              }
              v5 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, unsigned __int16 **))(*(_QWORD *)v13 + 64LL))(
                     v13,
                     36,
                     &v28,
                     &v29,
                     &v16);
              if ( !v5 )
              {
                if ( v16 )
                {
                  v8 = (v29 >> 1) + 1;
                  v9 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v8, 2u));
                  v4 = v9;
                  if ( !v9 )
                    goto LABEL_6;
                  v5 = StringCchCopyW(v9, v8, v16);
                  if ( v5 < 0 )
                  {
                    CoTaskMemFree(v4);
                    v4 = 0;
                    goto LABEL_45;
                  }
                }
                if ( !v3 || !*v3 )
                {
LABEL_30:
                  if ( !v4 || !*v4 )
                    goto LABEL_45;
                  v17 = a2;
                  v18 = 1;
                  v19 = 72;
                  v20 = 16;
                  v21 = v4;
                  v22 = 0;
                  v23 = 36;
                  v24 = 130;
                  v25 = 2 * safe_lstrlenW(v4) + 2;
                  if ( v13 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                    v13 = 0;
                  }
                  v5 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, const struct _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         &didCOMSERVICES,
                         &tidCOMSERVICES_CLASSES_INTERNAL,
                         &v17,
                         2,
                         1,
                         4,
                         &v13);
                  if ( v5 < 0 )
                    goto LABEL_45;
                  if ( v13 )
                  {
                    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
                    if ( v5 >= 0 )
                    {
                      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
                      if ( v5 >= 0 )
                      {
                        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
                        if ( v11 == -2146367487 )
                        {
                          v5 = 0;
                        }
                        else
                        {
                          if ( !v11 )
                            v11 = -2146368508;
                          v5 = v11;
                        }
                      }
                    }
                    goto LABEL_45;
                  }
                  goto LABEL_6;
                }
                v17 = a2;
                v18 = 1;
                v19 = 72;
                v20 = 16;
                v21 = v3;
                v22 = 0;
                v23 = 34;
                v24 = 130;
                v25 = 2 * safe_lstrlenW(v3) + 2;
                if ( v13 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                  v13 = 0;
                }
                v5 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, const struct _GUID *, const struct _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                       ppv,
                       &didCOMSERVICES,
                       &tidCOMSERVICES_CLASSES_INTERNAL,
                       &v17,
                       2,
                       1,
                       4,
                       &v13);
                if ( v5 < 0 )
                  goto LABEL_45;
                if ( !v13 )
                  goto LABEL_6;
                v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
                if ( v5 >= 0 )
                {
                  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
                  if ( v5 >= 0 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
                    v5 = v10;
                    if ( v10 != -2146367487 )
                    {
                      if ( !v10 )
                        v5 = -2146368508;
                      goto LABEL_45;
                    }
                    v5 = 0;
                    goto LABEL_30;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_45:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
LABEL_47:
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v4 )
    CoTaskMemFree(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002d9ec  mov     [rsp-8+arg_8], rbx
0x18002d9f1  mov     [rsp-8+arg_0], rcx
0x18002d9f6  push    rbp
0x18002d9f7  push    rsi
0x18002d9f8  push    rdi
0x18002d9f9  push    r12
0x18002d9fb  push    r13
0x18002d9fd  push    r14
0x18002d9ff  push    r15
0x18002da01  lea     rbp, [rsp-27h]
0x18002da06  sub     rsp, 0A0h
0x18002da0d  mov     r14, rdx
0x18002da10  xor     r15d, r15d
0x18002da13  mov     [rbp+57h+var_70], r15
0x18002da17  mov     [rbp+57h+var_68], r15
0x18002da1b  mov     [rbp+57h+arg_10], r15d
0x18002da1f  mov     dword ptr [rbp+57h+arg_0], r15d
0x18002da23  mov     [rbp+57h+arg_18], r15d
0x18002da27  mov     esi, r15d
0x18002da2a  mov     edi, r15d
0x18002da2d  mov     [rbp+57h+var_78], r15
0x18002da31  mov     [rbp+57h+var_80], r15
0x18002da35  lea     rax, [rbp+57h+var_78]
0x18002da39  mov     [rsp+0D0h+ppv], rax; ppv
0x18002da3e  lea     r9, IID_ISimpleTableDispenser; riid
0x18002da45  lea     r12d, [r15+1]
0x18002da49  mov     r8d, r12d; dwClsContext
0x18002da4c  xor     edx, edx; pUnkOuter
0x18002da4e  lea     rcx, CLSID_STDispenser; rclsid
0x18002da55  call    cs:__imp_CoCreateInstance
0x18002da5b  mov     ebx, eax
0x18002da5d  test    eax, eax
0x18002da5f  js      loc_18002DE69
0x18002da65  mov     rcx, [rbp+57h+var_78]
0x18002da69  test    rcx, rcx
0x18002da6c  jnz     short loc_18002DA78
0x18002da6e  mov     ebx, 8007000Eh
0x18002da73  jmp     loc_18002DE82
0x18002da78  mov     [rbp+57h+var_60], r14
0x18002da7c  mov     [rbp+57h+var_58], r15
0x18002da80  mov     [rbp+57h+var_50], 48h ; 'H'
0x18002da87  mov     [rbp+57h+var_4C], 10h
0x18002da8e  mov     rax, [rcx]
0x18002da91  lea     rdx, [rbp+57h+var_80]
0x18002da95  mov     [rsp+0D0h+var_98], rdx
0x18002da9a  mov     [rsp+0D0h+var_A0], 4
0x18002daa2  mov     [rsp+0D0h+var_A8], r12d
0x18002daa7  mov     [rsp+0D0h+ppv], r12
0x18002daac  lea     r9, [rbp+57h+var_60]
0x18002dab0  lea     r8, tidCOMSERVICES_CLASSES_INTERNAL
0x18002dab7  lea     rdx, didCOMSERVICES
0x18002dabe  mov     rax, [rax+18h]
0x18002dac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dac7  mov     ebx, eax
0x18002dac9  test    eax, eax
0x18002dacb  js      loc_18002DE69
0x18002dad1  cmp     [rbp+57h+var_80], r15
0x18002dad5  jnz     short loc_18002DAE1
0x18002dad7  mov     ebx, 8007000Eh
0x18002dadc  jmp     loc_18002DE69
0x18002dae1  mov     rcx, [rbp+57h+var_80]
0x18002dae5  mov     rax, [rcx]
0x18002dae8  mov     rax, [rax+18h]
0x18002daec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002daf1  mov     ebx, eax
0x18002daf3  test    eax, eax
0x18002daf5  js      loc_18002DE69
0x18002dafb  mov     rcx, [rbp+57h+var_80]
0x18002daff  mov     rax, [rcx]
0x18002db02  mov     rax, [rax+20h]
0x18002db06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db0b  mov     ebx, eax
0x18002db0d  test    eax, eax
0x18002db0f  js      loc_18002DE69
0x18002db15  mov     rcx, [rbp+57h+var_80]
0x18002db19  mov     rax, [rcx]
0x18002db1c  mov     rax, [rax+28h]
0x18002db20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db25  mov     ebx, eax
0x18002db27  test    eax, eax
0x18002db29  js      loc_18002DE69
0x18002db2f  mov     rcx, [rbp+57h+var_80]
0x18002db33  mov     rax, [rcx]
0x18002db36  lea     rdx, [rbp+57h+var_70]
0x18002db3a  mov     [rsp+0D0h+ppv], rdx
0x18002db3f  lea     r9, [rbp+57h+arg_0]
0x18002db43  lea     r8, [rbp+57h+arg_10]
0x18002db47  mov     edx, 22h ; '"'
0x18002db4c  mov     rax, [rax+40h]
0x18002db50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db55  mov     ebx, eax
0x18002db57  test    eax, eax
0x18002db59  jnz     loc_18002DE69
0x18002db5f  or      r13, 0FFFFFFFFFFFFFFFFh
0x18002db63  cmp     [rbp+57h+var_70], r15
0x18002db67  jz      short loc_18002DBB7
0x18002db69  mov     ebx, dword ptr [rbp+57h+arg_0]
0x18002db6c  shr     ebx, 1
0x18002db6e  add     ebx, r12d
0x18002db71  lea     eax, [r13+3]
0x18002db75  mul     rbx
0x18002db78  cmovb   rax, r13
0x18002db7c  mov     rcx, rax; cb
0x18002db7f  call    cs:__imp_CoTaskMemAlloc
0x18002db85  mov     rsi, rax
0x18002db88  test    rax, rax
0x18002db8b  jz      loc_18002DAD7
0x18002db91  mov     r8, [rbp+57h+var_70]; unsigned __int16 *
0x18002db95  mov     edx, ebx; unsigned __int64
0x18002db97  mov     rcx, rax; unsigned __int16 *
0x18002db9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002db9f  mov     ebx, eax
0x18002dba1  test    eax, eax
0x18002dba3  jns     short loc_18002DBB7
0x18002dba5  mov     rcx, rsi; pv
0x18002dba8  call    cs:__imp_CoTaskMemFree
0x18002dbae  nop
0x18002dbaf  mov     rsi, r15
0x18002dbb2  jmp     loc_18002DE69
0x18002dbb7  mov     rcx, [rbp+57h+var_80]
0x18002dbbb  mov     rax, [rcx]
0x18002dbbe  lea     rdx, [rbp+57h+var_68]
0x18002dbc2  mov     [rsp+0D0h+ppv], rdx
0x18002dbc7  lea     r9, [rbp+57h+arg_18]
0x18002dbcb  lea     r8, [rbp+57h+arg_10]
0x18002dbcf  mov     edx, 24h ; '$'
0x18002dbd4  mov     rax, [rax+40h]
0x18002dbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbdd  mov     ebx, eax
0x18002dbdf  test    eax, eax
0x18002dbe1  jnz     loc_18002DE69
0x18002dbe7  cmp     [rbp+57h+var_68], r15
0x18002dbeb  jz      short loc_18002DC3C
0x18002dbed  mov     ebx, [rbp+57h+arg_18]
0x18002dbf0  shr     ebx, 1
0x18002dbf2  add     ebx, r12d
0x18002dbf5  mov     eax, 2
0x18002dbfa  mul     rbx
0x18002dbfd  cmovb   rax, r13
0x18002dc01  mov     rcx, rax; cb
0x18002dc04  call    cs:__imp_CoTaskMemAlloc
0x18002dc0a  mov     rdi, rax
0x18002dc0d  test    rax, rax
0x18002dc10  jz      loc_18002DAD7
0x18002dc16  mov     r8, [rbp+57h+var_68]; unsigned __int16 *
0x18002dc1a  mov     edx, ebx; unsigned __int64
0x18002dc1c  mov     rcx, rax; unsigned __int16 *
0x18002dc1f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dc24  mov     ebx, eax
0x18002dc26  test    eax, eax
0x18002dc28  jns     short loc_18002DC3C
0x18002dc2a  mov     rcx, rdi; pv
0x18002dc2d  call    cs:__imp_CoTaskMemFree
0x18002dc33  nop
0x18002dc34  mov     rdi, r15
0x18002dc37  jmp     loc_18002DE69
0x18002dc3c  mov     r13d, 82h
0x18002dc42  test    rsi, rsi
0x18002dc45  jz      loc_18002DD52
0x18002dc4b  cmp     [rsi], r15w
0x18002dc4f  jz      loc_18002DD52
0x18002dc55  mov     [rbp+57h+var_60], r14
0x18002dc59  mov     [rbp+57h+var_58], r12
0x18002dc5d  mov     [rbp+57h+var_50], 48h ; 'H'
0x18002dc64  mov     [rbp+57h+var_4C], 10h
0x18002dc6b  mov     [rbp+57h+var_48], rsi
0x18002dc6f  mov     [rbp+57h+var_40], r15d
0x18002dc73  mov     [rbp+57h+var_3C], 22h ; '"'
0x18002dc7a  mov     [rbp+57h+var_38], r13d
0x18002dc7e  mov     rcx, rsi; unsigned __int16 *
0x18002dc81  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002dc86  lea     eax, ds:2[rax*2]
0x18002dc8d  mov     [rbp+57h+var_34], eax
0x18002dc90  mov     rcx, [rbp+57h+var_80]
0x18002dc94  test    rcx, rcx
0x18002dc97  jz      short loc_18002DCA9
0x18002dc99  mov     rax, [rcx]
0x18002dc9c  mov     rax, [rax+10h]
0x18002dca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dca5  mov     [rbp+57h+var_80], r15
0x18002dca9  mov     rcx, [rbp+57h+var_78]
0x18002dcad  mov     rax, [rcx]
0x18002dcb0  lea     rdx, [rbp+57h+var_80]
0x18002dcb4  mov     [rsp+0D0h+var_98], rdx
0x18002dcb9  mov     [rsp+0D0h+var_A0], 4
0x18002dcc1  mov     [rsp+0D0h+var_A8], r12d
0x18002dcc6  mov     [rsp+0D0h+ppv], 2
0x18002dccf  lea     r9, [rbp+57h+var_60]
0x18002dcd3  lea     r8, tidCOMSERVICES_CLASSES_INTERNAL
0x18002dcda  lea     rdx, didCOMSERVICES
0x18002dce1  mov     rax, [rax+18h]
0x18002dce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dcea  mov     ebx, eax
0x18002dcec  test    eax, eax
0x18002dcee  js      loc_18002DE69
0x18002dcf4  cmp     [rbp+57h+var_80], r15
0x18002dcf8  jz      loc_18002DAD7
0x18002dcfe  mov     rcx, [rbp+57h+var_80]
0x18002dd02  mov     rax, [rcx]
0x18002dd05  mov     rax, [rax+18h]
0x18002dd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd0e  mov     ebx, eax
0x18002dd10  test    eax, eax
0x18002dd12  js      loc_18002DE69
0x18002dd18  mov     rcx, [rbp+57h+var_80]
0x18002dd1c  mov     rax, [rcx]
0x18002dd1f  mov     rax, [rax+20h]
0x18002dd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd28  mov     ebx, eax
0x18002dd2a  test    eax, eax
0x18002dd2c  js      loc_18002DE69
0x18002dd32  mov     rcx, [rbp+57h+var_80]
0x18002dd36  mov     rax, [rcx]
0x18002dd39  mov     rax, [rax+28h]
0x18002dd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd42  mov     ebx, eax
0x18002dd44  cmp     eax, 80110801h
0x18002dd49  jnz     loc_18002DE52
0x18002dd4f  mov     ebx, r15d
0x18002dd52  test    rdi, rdi
0x18002dd55  jz      loc_18002DE69
0x18002dd5b  cmp     [rdi], r15w
0x18002dd5f  jz      loc_18002DE69
0x18002dd65  mov     [rbp+57h+var_60], r14
0x18002dd69  mov     [rbp+57h+var_58], r12
0x18002dd6d  mov     [rbp+57h+var_50], 48h ; 'H'
0x18002dd74  mov     [rbp+57h+var_4C], 10h
0x18002dd7b  mov     [rbp+57h+var_48], rdi
0x18002dd7f  mov     [rbp+57h+var_40], r15d
0x18002dd83  mov     [rbp+57h+var_3C], 24h ; '$'
0x18002dd8a  mov     [rbp+57h+var_38], r13d
0x18002dd8e  mov     rcx, rdi; unsigned __int16 *
0x18002dd91  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002dd96  lea     eax, ds:2[rax*2]
0x18002dd9d  mov     [rbp+57h+var_34], eax
0x18002dda0  mov     rcx, [rbp+57h+var_80]
0x18002dda4  test    rcx, rcx
0x18002dda7  jz      short loc_18002DDB9
0x18002dda9  mov     rax, [rcx]
0x18002ddac  mov     rax, [rax+10h]
0x18002ddb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddb5  mov     [rbp+57h+var_80], r15
0x18002ddb9  mov     rcx, [rbp+57h+var_78]
0x18002ddbd  mov     rax, [rcx]
0x18002ddc0  lea     r9, [rbp+57h+var_80]
0x18002ddc4  mov     [rsp+0D0h+var_98], r9
0x18002ddc9  mov     [rsp+0D0h+var_A0], 4
0x18002ddd1  mov     [rsp+0D0h+var_A8], r12d
0x18002ddd6  mov     [rsp+0D0h+ppv], 2
0x18002dddf  lea     r9, [rbp+57h+var_60]
0x18002dde3  lea     r8, tidCOMSERVICES_CLASSES_INTERNAL
0x18002ddea  lea     rdx, didCOMSERVICES
0x18002ddf1  mov     rax, [rax+18h]
0x18002ddf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddfa  mov     ebx, eax
0x18002ddfc  test    eax, eax
0x18002ddfe  js      short loc_18002DE69
0x18002de00  cmp     [rbp+57h+var_80], r15
0x18002de04  jz      loc_18002DAD7
0x18002de0a  mov     rcx, [rbp+57h+var_80]
0x18002de0e  mov     rax, [rcx]
0x18002de11  mov     rax, [rax+18h]
0x18002de15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de1a  mov     ebx, eax
0x18002de1c  test    eax, eax
0x18002de1e  js      short loc_18002DE69
0x18002de20  mov     rcx, [rbp+57h+var_80]
0x18002de24  mov     rax, [rcx]
0x18002de27  mov     rax, [rax+20h]
0x18002de2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de30  mov     ebx, eax
0x18002de32  test    eax, eax
0x18002de34  js      short loc_18002DE69
0x18002de36  mov     rcx, [rbp+57h+var_80]
0x18002de3a  mov     rax, [rcx]
0x18002de3d  mov     rax, [rax+28h]
0x18002de41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de46  cmp     eax, 80110801h
0x18002de4b  jnz     short loc_18002DE5D
0x18002de4d  mov     ebx, r15d
0x18002de50  jmp     short loc_18002DE69
0x18002de52  test    eax, eax
0x18002de54  jnz     short loc_18002DE69
0x18002de56  mov     ebx, 80110404h
0x18002de5b  jmp     short loc_18002DE69
0x18002de5d  mov     ebx, 80110404h
0x18002de62  test    eax, eax
0x18002de64  cmovz   eax, ebx
0x18002de67  mov     ebx, eax
0x18002de69  mov     rcx, [rbp+57h+var_78]
0x18002de6d  test    rcx, rcx
0x18002de70  jz      short loc_18002DE82
0x18002de72  mov     rax, [rcx]
0x18002de75  mov     rax, [rax+10h]
0x18002de79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de7e  mov     [rbp+57h+var_78], r15
0x18002de82  mov     rcx, [rbp+57h+var_80]
0x18002de86  test    rcx, rcx
0x18002de89  jz      short loc_18002DE9B
0x18002de8b  mov     rax, [rcx]
  ... truncated ...
```
