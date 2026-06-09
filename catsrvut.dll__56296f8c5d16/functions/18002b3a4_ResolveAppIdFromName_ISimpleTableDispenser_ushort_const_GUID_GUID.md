# ResolveAppIdFromName(ISimpleTableDispenser *,ushort const *,_GUID *,_GUID *)

- ea: `0x18002b3a4`
- end: `0x18002b654`
- name: `?ResolveAppIdFromName@@YAJPEAUISimpleTableDispenser@@PEBGPEAU_GUID@@2@Z`
- size: `688`
- prototype: `int(struct ISimpleTableDispenser *, const unsigned __int16 *, struct _GUID *, struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002e660`
- `0x18002f050`
- `0x18002fb90`

## callees

- `0x180006f40`
- `0x18002b3a4`
- `0x180055822`
- `0x180057010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b535`
- `msvcrt!_wcsicmp` at `0x18002b535`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b467`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b467`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002b409`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002b409`

## pseudocode

```c
__int64 __fastcall ResolveAppIdFromName(
        struct ISimpleTableDispenser *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  HRESULT Instance; // ebx
  int v9; // eax
  struct _GUID *v10; // [rsp+50h] [rbp-10h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-8h]
  struct ISimpleTableDispenser *ppv; // [rsp+80h] [rbp+20h] BYREF
  __int64 v13; // [rsp+88h] [rbp+28h] BYREF

  ppv = a1;
  v13 = 0;
  v10 = 0;
  String1 = 0;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = GUID_NULL;
  if ( *a2 == 123 )
  {
    if ( CLSIDFromString(a2, a3) >= 0 )
    {
      if ( a4 )
        return GetPartitionFromAppId(ppv, a3, a4);
      else
        return 0;
    }
    a1 = ppv;
  }
  if ( a1 )
  {
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)a1 + 8LL))(a1);
LABEL_12:
    Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)ppv + 24LL))(
                 ppv,
                 &didCOMSERVICES,
                 &TID_APPLICATION,
                 0,
                 0,
                 1,
                 1,
                 &v13);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
      if ( Instance >= 0 )
      {
        while ( 1 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
          Instance = v9;
          if ( v9 < 0 )
            break;
          Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 64LL))(v13, 1, 0);
          if ( Instance < 0 )
            goto LABEL_27;
          if ( !String1 )
          {
            Instance = -2147418113;
            goto LABEL_27;
          }
          if ( !_wcsicmp(String1, a2) )
          {
            if ( memcmp_0(a3, &GUID_NULL, 0x10u) )
            {
              Instance = -2146368420;
              goto LABEL_27;
            }
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct _GUID **))(*(_QWORD *)v13 + 64LL))(
                         v13,
                         0,
                         0,
                         0,
                         &v10);
            if ( Instance < 0 )
              goto LABEL_27;
            *a3 = *v10;
            if ( a4 )
            {
              Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 64LL))(v13, 41, 0);
              if ( Instance < 0 )
                goto LABEL_27;
              *a4 = *v10;
            }
          }
        }
        if ( v9 == -2146367487 )
          Instance = memcmp_0(a3, &GUID_NULL, 0x10u) == 0 ? 0x80110809 : 0;
      }
    }
    goto LABEL_27;
  }
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 0x17u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
    goto LABEL_12;
LABEL_27:
  if ( ppv )
  {
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002b3a4  mov     [rsp-18h+arg_10], rbx
0x18002b3a9  mov     [rsp-18h+arg_18], rsi
0x18002b3ae  mov     [rsp-18h+arg_0], rcx
0x18002b3b3  push    rbp
0x18002b3b4  push    rdi
0x18002b3b5  push    r14
0x18002b3b7  mov     rbp, rsp
0x18002b3ba  sub     rsp, 60h
0x18002b3be  mov     [rbp+arg_8], 0
0x18002b3c6  mov     rsi, r9
0x18002b3c9  mov     [rbp+var_10], 0
0x18002b3d1  mov     rdi, r8
0x18002b3d4  mov     [rbp+String1], 0
0x18002b3dc  mov     r14, rdx
0x18002b3df  test    rdx, rdx
0x18002b3e2  jz      loc_18002B63A
0x18002b3e8  test    r8, r8
0x18002b3eb  jz      loc_18002B63A
0x18002b3f1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002b3f8  movdqu  xmmword ptr [r8], xmm0
0x18002b3fd  cmp     word ptr [rdx], 7Bh ; '{'
0x18002b401  jnz     short loc_18002B437
0x18002b403  mov     rdx, r8; pclsid
0x18002b406  mov     rcx, r14; lpsz
0x18002b409  call    cs:__imp_CLSIDFromString
0x18002b40f  test    eax, eax
0x18002b411  js      short loc_18002B433
0x18002b413  test    rsi, rsi
0x18002b416  jnz     short loc_18002B41F
0x18002b418  xor     eax, eax
0x18002b41a  jmp     loc_18002B63F
0x18002b41f  mov     rcx, [rbp+arg_0]; struct ISimpleTableDispenser *
0x18002b423  mov     r8, rsi; struct _GUID *
0x18002b426  mov     rdx, rdi; struct _GUID *
0x18002b429  call    ?GetPartitionFromAppId@@YAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAU2@@Z; GetPartitionFromAppId(ISimpleTableDispenser *,_GUID const &,_GUID *)
0x18002b42e  jmp     loc_18002B63F
0x18002b433  mov     rcx, [rbp+arg_0]
0x18002b437  test    rcx, rcx
0x18002b43a  jz      short loc_18002B44A
0x18002b43c  mov     rax, [rcx]
0x18002b43f  mov     rax, [rax+8]
0x18002b443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b448  jmp     short loc_18002B477
0x18002b44a  xor     edx, edx; pUnkOuter
0x18002b44c  lea     rax, [rbp+arg_0]
0x18002b450  lea     r9, IID_ISimpleTableDispenser; riid
0x18002b457  mov     [rsp+60h+ppv], rax; ppv
0x18002b45c  lea     rcx, CLSID_STDispenser; rclsid
0x18002b463  lea     r8d, [rdx+17h]; dwClsContext
0x18002b467  call    cs:__imp_CoCreateInstance
0x18002b46d  mov     ebx, eax
0x18002b46f  test    eax, eax
0x18002b471  js      loc_18002B604
0x18002b477  mov     rcx, [rbp+arg_0]
0x18002b47b  lea     rdx, [rbp+arg_8]
0x18002b47f  mov     [rsp+60h+var_28], rdx
0x18002b484  lea     r8, TID_APPLICATION
0x18002b48b  mov     [rsp+60h+var_30], 1
0x18002b493  lea     rdx, didCOMSERVICES
0x18002b49a  mov     [rsp+60h+var_38], 1
0x18002b4a2  xor     r9d, r9d
0x18002b4a5  mov     rax, [rcx]
0x18002b4a8  mov     [rsp+60h+ppv], 0
0x18002b4b1  mov     rax, [rax+18h]
0x18002b4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4ba  mov     ebx, eax
0x18002b4bc  test    eax, eax
0x18002b4be  js      loc_18002B604
0x18002b4c4  mov     rcx, [rbp+arg_8]
0x18002b4c8  mov     rax, [rcx]
0x18002b4cb  mov     rax, [rax+18h]
0x18002b4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4d4  mov     ebx, eax
0x18002b4d6  test    eax, eax
0x18002b4d8  js      loc_18002B604
0x18002b4de  mov     rcx, [rbp+arg_8]
0x18002b4e2  mov     rax, [rcx]
0x18002b4e5  mov     rax, [rax+28h]
0x18002b4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4ee  mov     ebx, eax
0x18002b4f0  test    eax, eax
0x18002b4f2  js      loc_18002B5DC
0x18002b4f8  mov     rcx, [rbp+arg_8]
0x18002b4fc  lea     rdx, [rbp+String1]
0x18002b500  xor     r9d, r9d
0x18002b503  mov     [rsp+60h+ppv], rdx
0x18002b508  xor     r8d, r8d
0x18002b50b  mov     rax, [rcx]
0x18002b50e  lea     edx, [r9+1]
0x18002b512  mov     rax, [rax+40h]
0x18002b516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b51b  mov     ebx, eax
0x18002b51d  test    eax, eax
0x18002b51f  js      loc_18002B604
0x18002b525  mov     rcx, [rbp+String1]; String1
0x18002b529  test    rcx, rcx
0x18002b52c  jz      loc_18002B5D5
0x18002b532  mov     rdx, r14; String2
0x18002b535  call    cs:__imp__wcsicmp
0x18002b53b  test    eax, eax
0x18002b53d  jnz     short loc_18002B4DE
0x18002b53f  lea     r8d, [rax+10h]; Size
0x18002b543  mov     rcx, rdi; Buf1
0x18002b546  lea     rdx, GUID_NULL; Buf2
0x18002b54d  call    memcmp_0
0x18002b552  test    eax, eax
0x18002b554  jnz     short loc_18002B5CE
0x18002b556  mov     rcx, [rbp+arg_8]
0x18002b55a  lea     rdx, [rbp+var_10]
0x18002b55e  mov     [rsp+60h+ppv], rdx
0x18002b563  xor     r9d, r9d
0x18002b566  xor     r8d, r8d
0x18002b569  xor     edx, edx
0x18002b56b  mov     rax, [rcx]
0x18002b56e  mov     rax, [rax+40h]
0x18002b572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b577  mov     ebx, eax
0x18002b579  test    eax, eax
0x18002b57b  js      loc_18002B604
0x18002b581  mov     rax, [rbp+var_10]
0x18002b585  movups  xmm0, xmmword ptr [rax]
0x18002b588  movdqu  xmmword ptr [rdi], xmm0
0x18002b58c  test    rsi, rsi
0x18002b58f  jz      loc_18002B4DE
0x18002b595  mov     rcx, [rbp+arg_8]
0x18002b599  lea     rdx, [rbp+var_10]
0x18002b59d  xor     r9d, r9d
0x18002b5a0  mov     [rsp+60h+ppv], rdx
0x18002b5a5  xor     r8d, r8d
0x18002b5a8  mov     rax, [rcx]
0x18002b5ab  lea     edx, [r9+29h]
0x18002b5af  mov     rax, [rax+40h]
0x18002b5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5b8  mov     ebx, eax
0x18002b5ba  test    eax, eax
0x18002b5bc  js      short loc_18002B604
0x18002b5be  mov     rax, [rbp+var_10]
0x18002b5c2  movups  xmm0, xmmword ptr [rax]
0x18002b5c5  movdqu  xmmword ptr [rsi], xmm0
0x18002b5c9  jmp     loc_18002B4DE
0x18002b5ce  mov     ebx, 8011045Ch
0x18002b5d3  jmp     short loc_18002B604
0x18002b5d5  mov     ebx, 8000FFFFh
0x18002b5da  jmp     short loc_18002B604
0x18002b5dc  cmp     eax, 80110801h
0x18002b5e1  jnz     short loc_18002B604
0x18002b5e3  mov     r8d, 10h; Size
0x18002b5e9  lea     rdx, GUID_NULL; Buf2
0x18002b5f0  mov     rcx, rdi; Buf1
0x18002b5f3  call    memcmp_0
0x18002b5f8  neg     eax
0x18002b5fa  sbb     ebx, ebx
0x18002b5fc  not     ebx
0x18002b5fe  and     ebx, 80110809h
0x18002b604  mov     rcx, [rbp+arg_0]
0x18002b608  test    rcx, rcx
0x18002b60b  jz      short loc_18002B621
0x18002b60d  mov     rax, [rcx]
0x18002b610  mov     rax, [rax+10h]
0x18002b614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b619  mov     [rbp+arg_0], 0
0x18002b621  mov     rcx, [rbp+arg_8]
0x18002b625  test    rcx, rcx
0x18002b628  jz      short loc_18002B636
0x18002b62a  mov     rax, [rcx]
0x18002b62d  mov     rax, [rax+10h]
0x18002b631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b636  mov     eax, ebx
0x18002b638  jmp     short loc_18002B63F
0x18002b63a  mov     eax, 80004003h
0x18002b63f  lea     r11, [rsp+60h+var_s0]
0x18002b644  mov     rbx, [r11+30h]
0x18002b648  mov     rsi, [r11+38h]
0x18002b64c  mov     rsp, r11
0x18002b64f  pop     r14
0x18002b651  pop     rdi
0x18002b652  pop     rbp
0x18002b653  retn
```
