# CContactRegistry::Connect(ulong,_GUID *,ushort const *,_GUID *,int)

- ea: `0x180008940`
- end: `0x1800092eb`
- name: `?Connect@CContactRegistry@@UEAAJKPEAU_GUID@@PEBG0H@Z`
- size: `2475`
- prototype: `__int64 __usercall@<rax>(CContactRegistry *__hidden this@<rcx>, unsigned int@<edx>, struct _GUID *@<r8>, const unsigned __int16 *@<r9>, struct _GUID *, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180008940`
- `0x1800092f4`
- `0x18000bbf8`
- `0x180012130`
- `0x180078524`
- `0x1800789c4`
- `0x180078a68`
- `0x180079178`
- `0x180079348`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a1d`
- `RPCRT4!UuidFromStringA` at `0x180008d38`
- `RPCRT4!UuidFromStringA` at `0x180008d38`
- `RPCRT4!RpcStringFreeA` at `0x180008b91`
- `RPCRT4!RpcStringFreeA` at `0x180008bd5`
- `RPCRT4!RpcStringFreeA` at `0x180008b91`
- `RPCRT4!RpcStringFreeA` at `0x180008bd5`
- `RPCRT4!UuidToStringA` at `0x180008b67`
- `RPCRT4!UuidToStringA` at `0x180008bb5`
- `RPCRT4!UuidToStringA` at `0x180008b67`
- `RPCRT4!UuidToStringA` at `0x180008bb5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800089e3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800089e3`

## string_xrefs

- `0x180008e32`: `Protocol`
- `0x180008e01`: `Clsid`

## pseudocode

```c
__int64 __fastcall CContactRegistry::Connect(
        CContactRegistry *this,
        int a2,
        struct _GUID *a3,
        char *a4,
        struct _GUID *Uuid,
        int a6)
{
  unsigned int v6; // r13d
  WCHAR *v8; // rcx
  bool v11; // zf
  int PhysicalNodeNameW; // ebx
  const WCHAR *v14; // rcx
  int v15; // eax
  int v17; // eax
  unsigned int v18; // edx
  int v19; // eax
  unsigned int v20; // edx
  unsigned __int16 *v21; // rax
  int v22; // ecx
  int v23; // edx
  int v24; // eax
  unsigned int v25; // edx
  char *v26; // r9
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  unsigned int v30; // edx
  unsigned __int8 *v31; // rax
  int v32; // r8d
  int v33; // edx
  unsigned int v34; // edx
  LPCWSTR pv; // [rsp+40h] [rbp-C0h]
  HKEY v36; // [rsp+48h] [rbp-B8h] BYREF
  LPCWSTR lpString2; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v38; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v39; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v40; // [rsp+68h] [rbp-98h] BYREF
  HKEY v41; // [rsp+70h] [rbp-90h] BYREF
  HKEY v42; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 StringUuid[40]; // [rsp+80h] [rbp-80h] BYREF
  char v44[40]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v45[256]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = 0;
  v40 = 0;
  v8 = 0;
  v36 = 0;
  v38 = 0;
  v41 = 0;
  v11 = *((_DWORD *)this + 2) == 1;
  v39 = 0;
  v42 = 0;
  lpString2 = 0;
  if ( v11 )
  {
    PhysicalNodeNameW = -2146434988;
    goto LABEL_11;
  }
  PhysicalNodeNameW = GetPhysicalNodeNameW((BYTE **)&lpString2);
  if ( PhysicalNodeNameW < 0 )
  {
    v8 = (WCHAR *)lpString2;
    goto LABEL_11;
  }
  v14 = (const WCHAR *)*((_QWORD *)this + 7);
  pv = lpString2;
  if ( !v14 || (v11 = lstrcmpiW(v14, lpString2) == 0, v15 = 1, v11) )
    v15 = 0;
  *((_DWORD *)this + 12) = v15;
  LOBYTE(v6) = a2 != 1;
  if ( !a3 )
  {
    if ( a2 != 1 )
    {
      PhysicalNodeNameW = -2146435069;
LABEL_10:
      v8 = (WCHAR *)pv;
      goto LABEL_11;
    }
    if ( !a4 )
    {
      PhysicalNodeNameW = -2146435068;
      goto LABEL_10;
    }
  }
  v17 = (*(__int64 (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 96LL))(this, &v40);
  PhysicalNodeNameW = v17;
  if ( v17 >= 0 )
  {
    if ( a3 )
    {
      lpString2 = 0;
      if ( UuidToStringA(a3, (RPC_CSTR *)&lpString2) )
      {
LABEL_31:
        PhysicalNodeNameW = -2147024882;
        goto LABEL_10;
      }
      StringCbCopyA((char *)StringUuid, 0x25u, (const char *)lpString2);
      RpcStringFreeA((RPC_CSTR *)&lpString2);
      *((struct _GUID *)this + 2) = *a3;
    }
    if ( Uuid )
    {
      lpString2 = 0;
      if ( UuidToStringA(Uuid, (RPC_CSTR *)&lpString2) )
        goto LABEL_31;
      StringCbCopyA(v44, 0x25u, (const char *)lpString2);
      RpcStringFreeA((RPC_CSTR *)&lpString2);
      *((_DWORD *)this + 3) = 1;
    }
    v18 = 0;
    if ( !*((_QWORD *)this + 7) )
      v18 = v6;
    v17 = CContactRegistry::OpenKeyW(this, v18, 0, &v40, *((const unsigned __int16 **)this + 8), &v38);
    PhysicalNodeNameW = v17;
    if ( v17 < 0 )
      goto LABEL_27;
    if ( !a3 )
    {
      while ( 1 )
      {
        v19 = (*(__int64 (__fastcall **)(CContactRegistry *, HKEY, _QWORD, unsigned __int8 *, int))(*(_QWORD *)this
                                                                                                  + 192LL))(
                this,
                v38,
                (unsigned int)a3,
                StringUuid,
                37);
        if ( v19 == -2147024637 )
          break;
        if ( v19 < 0 )
        {
          PhysicalNodeNameW = -2146435002;
          goto LABEL_10;
        }
        PhysicalNodeNameW = CContactRegistry::OpenKey(this, 0, 0, &v38, (const char *)StringUuid, &v39);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        PhysicalNodeNameW = CContactRegistry::OpenKey(this, 0, 0, &v39, "Description", &v42);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        PhysicalNodeNameW = CContactRegistry::ReadKeyValueW(this, v20, &v42, v45, 0x100u);
        (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v39);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        if ( a4 )
        {
          v21 = v45;
          do
          {
            v22 = *(unsigned __int16 *)((char *)v21 + a4 - (char *)v45);
            v23 = *v21 - v22;
            if ( v23 )
              break;
            ++v21;
          }
          while ( v22 );
          if ( !v23 )
          {
            UuidFromStringA(StringUuid, (UUID *)this + 2);
            goto LABEL_52;
          }
        }
        LODWORD(a3) = (_DWORD)a3 + 1;
      }
      if ( v38 )
        (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v38);
      goto LABEL_78;
    }
LABEL_52:
    v24 = CContactRegistry::OpenKey(this, v6, a2 != 3, &v38, (const char *)StringUuid, (HKEY *)this + 2);
    PhysicalNodeNameW = v24;
    if ( v24 == -2146435004 )
    {
LABEL_78:
      PhysicalNodeNameW = -2146434815;
      goto LABEL_10;
    }
    if ( v24 < 0 )
      goto LABEL_10;
    if ( a2 == 2 )
    {
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 2u, (HKEY *)this + 2, "Description", &v36);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 2u, (HKEY *)this + 2, "Host", &v36);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 2u, (HKEY *)this + 2, "Clsid", &v36);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 2u, (HKEY *)this + 2, "Protocol", &v36);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 2u, (HKEY *)this + 2, "Endpoint", &v36);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 2u, (HKEY *)this + 2, "CustomProperties", &v36);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 0, (HKEY *)this + 2, "Svcid", &v36);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      v26 = v44;
      if ( !*((_DWORD *)this + 3) )
        v26 = (char *)Class;
      PhysicalNodeNameW = CContactRegistry::WriteKeyValue(this, v25, &v36, v26);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
    }
    if ( !*((_DWORD *)this + 3) )
    {
      if ( a2 == 2 )
        goto LABEL_80;
      v27 = *(_QWORD *)this;
      *((_DWORD *)this + 2) = 1;
      v28 = (*(__int64 (__fastcall **)(CContactRegistry *, __int64, _QWORD))(v27 + 48))(this, 4, 0);
      *((_DWORD *)this + 2) = 0;
      PhysicalNodeNameW = v28;
      if ( v28 < 0 )
        goto LABEL_10;
      v29 = -1;
      do
        ++v29;
      while ( v44[v29] );
      if ( v29 == 36 )
        *((_DWORD *)this + 3) = 1;
    }
    if ( a2 == 3 )
    {
      CContactRegistry::DeleteHive(this, *((HKEY *)this + 2));
      (*(void (__fastcall **)(CContactRegistry *, char *))(*(_QWORD *)this + 176LL))(this, (char *)this + 16);
      PhysicalNodeNameW = (*(__int64 (__fastcall **)(CContactRegistry *, HKEY, unsigned __int8 *))(*(_QWORD *)this
                                                                                                 + 144LL))(
                            this,
                            v38,
                            StringUuid);
      if ( PhysicalNodeNameW < 0 )
      {
LABEL_74:
        PhysicalNodeNameW = -2146435038;
        goto LABEL_10;
      }
      (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v38);
    }
LABEL_80:
    if ( *((_DWORD *)this + 3) == 1 )
    {
      v30 = 0;
      if ( !*((_QWORD *)this + 7) )
        v30 = v6;
      PhysicalNodeNameW = CContactRegistry::OpenKeyW(this, v30, 0, &v40, *((const unsigned __int16 **)this + 9), &v41);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      PhysicalNodeNameW = CContactRegistry::OpenKey(this, v6, 1u, &v41, v44, (HKEY *)this + 3);
      if ( PhysicalNodeNameW < 0 )
        goto LABEL_10;
      if ( a2 == 3 )
      {
        PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 0, (HKEY *)this + 3, "DefaultProvider", &v36);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        PhysicalNodeNameW = CContactRegistry::ReadKeyValue(this, 0, &v36, v44, 0x25u);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        v31 = StringUuid;
        do
        {
          v32 = v31[40];
          v33 = *v31 - v32;
          if ( v33 )
            break;
          ++v31;
        }
        while ( v32 );
        if ( v33
          || (*(int (__fastcall **)(CContactRegistry *, HKEY, _QWORD))(*(_QWORD *)this + 152LL))(this, v36, 0) >= 0 )
        {
          (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v36);
          PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 0, (HKEY *)this + 3, "Providers", &v36);
          if ( PhysicalNodeNameW < 0 )
            goto LABEL_10;
          PhysicalNodeNameW = (*(__int64 (__fastcall **)(CContactRegistry *, HKEY, unsigned __int8 *))(*(_QWORD *)this + 144LL))(
                                this,
                                v36,
                                StringUuid);
          if ( PhysicalNodeNameW >= 0 )
          {
            (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v36);
            (*(void (__fastcall **)(CContactRegistry *, char *))(*(_QWORD *)this + 176LL))(this, (char *)this + 24);
            goto LABEL_10;
          }
        }
        goto LABEL_74;
      }
      if ( a2 == 2 )
      {
        PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 2u, (HKEY *)this + 3, "DefaultProvider", &v36);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 0, (HKEY *)this + 3, "DefaultProvider", &v36);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        if ( a6 == 1 )
        {
          PhysicalNodeNameW = CContactRegistry::WriteKeyValue(this, v34, &v36, (const char *)StringUuid);
          if ( PhysicalNodeNameW < 0 )
            goto LABEL_10;
        }
        PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 0, (HKEY *)this + 3, "Providers", &v36);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        PhysicalNodeNameW = CContactRegistry::OpenKey(this, 1u, 1u, &v36, (const char *)StringUuid, &v39);
        if ( PhysicalNodeNameW < 0 )
          goto LABEL_10;
        (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v39);
      }
    }
    else if ( a2 == 3 )
    {
      goto LABEL_10;
    }
    *((_DWORD *)this + 2) = 1;
    goto LABEL_10;
  }
LABEL_27:
  v8 = (WCHAR *)pv;
  if ( v17 == -2147024894 )
    PhysicalNodeNameW = -2146434815;
LABEL_11:
  CoTaskMemFree(v8);
  if ( v40 )
    (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v40);
  if ( v36 )
    (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v36);
  if ( v38 )
    (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v38);
  if ( v41 )
    (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v41);
  if ( v39 )
    (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v39);
  if ( v42 )
    (*(void (__fastcall **)(CContactRegistry *, HKEY *))(*(_QWORD *)this + 176LL))(this, &v42);
  return (unsigned int)PhysicalNodeNameW;
}

```

## disassembly

```asm
0x180008940  mov     [rsp-8+arg_8], rbx
0x180008945  push    rbp
0x180008946  push    rsi
0x180008947  push    rdi
0x180008948  push    r12
0x18000894a  push    r13
0x18000894c  push    r14
0x18000894e  push    r15
0x180008950  lea     rbp, [rsp-1E0h]
0x180008958  sub     rsp, 2E0h
0x18000895f  mov     rax, cs:__security_cookie
0x180008966  xor     rax, rsp
0x180008969  mov     [rbp+210h+var_40], rax
0x180008970  mov     r15, [rbp+210h+Uuid]
0x180008977  xor     r13d, r13d
0x18000897a  mov     rdi, rcx
0x18000897d  mov     [rsp+310h+var_2A8], r13
0x180008982  mov     ecx, r13d
0x180008985  mov     [rsp+310h+var_2C8], r13
0x18000898a  mov     r12, r9
0x18000898d  mov     [rsp+310h+var_2B8], r13
0x180008992  mov     rsi, r8
0x180008995  mov     [rsp+310h+var_2A0], r13
0x18000899a  cmp     dword ptr [rdi+8], 1
0x18000899e  mov     r14d, edx
0x1800089a1  mov     [rsp+310h+var_2B0], r13
0x1800089a6  mov     [rsp+310h+var_298], r13
0x1800089ab  mov     [rsp+310h+lpString2], rcx
0x1800089b0  jnz     short loc_1800089B9
0x1800089b2  mov     ebx, 80100054h
0x1800089b7  jmp     short loc_180008A1D
0x1800089b9  lea     rcx, [rsp+310h+lpString2]; unsigned __int16 **
0x1800089be  call    ?GetPhysicalNodeNameW@@YAJPEAPEAG@Z; GetPhysicalNodeNameW(ushort * *)
0x1800089c3  mov     ebx, eax
0x1800089c5  test    eax, eax
0x1800089c7  js      loc_1800092E1
0x1800089cd  mov     rcx, [rdi+38h]; lpString1
0x1800089d1  mov     rax, [rsp+310h+lpString2]
0x1800089d6  mov     [rsp+310h+pv], rax
0x1800089db  test    rcx, rcx
0x1800089de  jz      short loc_1800089F2
0x1800089e0  mov     rdx, rax; lpString2
0x1800089e3  call    cs:__imp_lstrcmpiW
0x1800089e9  test    eax, eax
0x1800089eb  mov     eax, 1
0x1800089f0  jnz     short loc_1800089F5
0x1800089f2  mov     eax, r13d
0x1800089f5  cmp     r14d, 1
0x1800089f9  mov     [rdi+30h], eax
0x1800089fc  setnz   r13b
0x180008a00  test    rsi, rsi
0x180008a03  jnz     loc_180008B18
0x180008a09  cmp     r14d, 1
0x180008a0d  jz      loc_180008B09
0x180008a13  mov     ebx, 80100003h
0x180008a18  mov     rcx, [rsp+310h+pv]; pv
0x180008a1d  call    cs:__imp_CoTaskMemFree
0x180008a23  cmp     [rsp+310h+var_2A8], 0
0x180008a29  jz      short loc_180008A42
0x180008a2b  mov     rax, [rdi]
0x180008a2e  lea     rdx, [rsp+310h+var_2A8]
0x180008a33  mov     rcx, rdi
0x180008a36  mov     rax, [rax+0B0h]
0x180008a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a42  cmp     [rsp+310h+var_2C8], 0
0x180008a48  jz      short loc_180008A61
0x180008a4a  mov     rax, [rdi]
0x180008a4d  lea     rdx, [rsp+310h+var_2C8]
0x180008a52  mov     rcx, rdi
0x180008a55  mov     rax, [rax+0B0h]
0x180008a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a61  cmp     [rsp+310h+var_2B8], 0
0x180008a67  jz      short loc_180008A80
0x180008a69  mov     rax, [rdi]
0x180008a6c  lea     rdx, [rsp+310h+var_2B8]
0x180008a71  mov     rcx, rdi
0x180008a74  mov     rax, [rax+0B0h]
0x180008a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a80  cmp     [rsp+310h+var_2A0], 0
0x180008a86  jz      short loc_180008A9F
0x180008a88  mov     rax, [rdi]
0x180008a8b  lea     rdx, [rsp+310h+var_2A0]
0x180008a90  mov     rcx, rdi
0x180008a93  mov     rax, [rax+0B0h]
0x180008a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a9f  cmp     [rsp+310h+var_2B0], 0
0x180008aa5  jz      short loc_180008ABE
0x180008aa7  mov     rax, [rdi]
0x180008aaa  lea     rdx, [rsp+310h+var_2B0]
0x180008aaf  mov     rcx, rdi
0x180008ab2  mov     rax, [rax+0B0h]
0x180008ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008abe  cmp     [rsp+310h+var_298], 0
0x180008ac4  jz      short loc_180008ADD
0x180008ac6  mov     rax, [rdi]
0x180008ac9  lea     rdx, [rsp+310h+var_298]
0x180008ace  mov     rcx, rdi
0x180008ad1  mov     rax, [rax+0B0h]
0x180008ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008add  mov     eax, ebx
0x180008adf  mov     rcx, [rbp+210h+var_40]
0x180008ae6  xor     rcx, rsp; StackCookie
0x180008ae9  call    __security_check_cookie
0x180008aee  mov     rbx, [rsp+310h+arg_8]
0x180008af6  add     rsp, 2E0h
0x180008afd  pop     r15
0x180008aff  pop     r14
0x180008b01  pop     r13
0x180008b03  pop     r12
0x180008b05  pop     rdi
0x180008b06  pop     rsi
0x180008b07  pop     rbp
0x180008b08  retn
0x180008b09  test    r12, r12
0x180008b0c  jnz     short loc_180008B18
0x180008b0e  mov     ebx, 80100004h
0x180008b13  jmp     loc_180008A18
0x180008b18  mov     rax, [rdi]
0x180008b1b  lea     rdx, [rsp+310h+var_2A8]
0x180008b20  mov     rcx, rdi
0x180008b23  mov     rax, [rax+60h]
0x180008b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b2c  mov     ebx, eax
0x180008b2e  test    eax, eax
0x180008b30  jns     short loc_180008B4C
0x180008b32  mov     rcx, [rsp+310h+pv]
0x180008b37  cmp     eax, 80070002h
0x180008b3c  jnz     loc_180008A1D
0x180008b42  mov     ebx, 80100101h
0x180008b47  jmp     loc_180008A1D
0x180008b4c  mov     ebx, 25h ; '%'
0x180008b51  test    rsi, rsi
0x180008b54  jz      short loc_180008B9F
0x180008b56  lea     rdx, [rsp+310h+lpString2]; StringUuid
0x180008b5b  mov     [rsp+310h+lpString2], 0
0x180008b64  mov     rcx, rsi; Uuid
0x180008b67  call    cs:__imp_UuidToStringA
0x180008b6d  test    eax, eax
0x180008b6f  jz      short loc_180008B7B
0x180008b71  mov     ebx, 8007000Eh
0x180008b76  jmp     loc_180008A18
0x180008b7b  mov     r8, [rsp+310h+lpString2]; char *
0x180008b80  lea     rcx, [rbp+210h+StringUuid]; char *
0x180008b84  mov     rdx, rbx; unsigned __int64
0x180008b87  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180008b8c  lea     rcx, [rsp+310h+lpString2]; String
0x180008b91  call    cs:__imp_RpcStringFreeA
0x180008b97  movups  xmm0, xmmword ptr [rsi]
0x180008b9a  movdqu  xmmword ptr [rdi+20h], xmm0
0x180008b9f  test    r15, r15
0x180008ba2  jz      short loc_180008BE7
0x180008ba4  lea     rdx, [rsp+310h+lpString2]; StringUuid
0x180008ba9  mov     [rsp+310h+lpString2], 0
0x180008bb2  mov     rcx, r15; Uuid
0x180008bb5  call    cs:__imp_UuidToStringA
0x180008bbb  test    eax, eax
0x180008bbd  jnz     short loc_180008B71
0x180008bbf  mov     r8, [rsp+310h+lpString2]; char *
0x180008bc4  lea     rcx, [rbp+210h+var_268]; char *
0x180008bc8  mov     rdx, rbx; unsigned __int64
0x180008bcb  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180008bd0  lea     rcx, [rsp+310h+lpString2]; String
0x180008bd5  call    cs:__imp_RpcStringFreeA
0x180008bdb  mov     r15d, 1
0x180008be1  mov     [rdi+0Ch], r15d
0x180008be5  jmp     short loc_180008BED
0x180008be7  mov     r15d, 1
0x180008bed  mov     rax, [rdi+40h]
0x180008bf1  lea     rcx, [rsp+310h+var_2B8]
0x180008bf6  xor     edx, edx
0x180008bf8  mov     [rsp+310h+var_2E8], rcx; HKEY *
0x180008bfd  cmp     [rdi+38h], rdx
0x180008c01  lea     r9, [rsp+310h+var_2A8]; HKEY *
0x180008c06  mov     rcx, rdi; this
0x180008c09  mov     [rsp+310h+var_2F0], rax; unsigned __int16 *
0x180008c0e  cmovz   edx, r13d; unsigned int
0x180008c12  xor     r8d, r8d; unsigned int
0x180008c15  call    ?OpenKeyW@CContactRegistry@@AEAAJKKPEAPEAUHKEY__@@PEBG0@Z; CContactRegistry::OpenKeyW(ulong,ulong,HKEY__ * *,ushort const *,HKEY__ * *)
0x180008c1a  mov     ebx, eax
0x180008c1c  test    eax, eax
0x180008c1e  js      loc_180008B32
0x180008c24  test    rsi, rsi
0x180008c27  jnz     loc_180008D3E
0x180008c2d  mov     rax, [rdi]
0x180008c30  lea     r9, [rbp+210h+StringUuid]
0x180008c34  mov     rdx, [rsp+310h+var_2B8]
0x180008c39  mov     r8d, esi
0x180008c3c  mov     rcx, rdi
0x180008c3f  mov     dword ptr [rsp+310h+var_2F0], 25h ; '%'
0x180008c47  mov     rax, [rax+0C0h]
0x180008c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c53  cmp     eax, 80070103h
0x180008c58  jz      loc_180008FD8
0x180008c5e  test    eax, eax
0x180008c60  js      loc_180008FCE
0x180008c66  lea     rax, [rsp+310h+var_2B0]
0x180008c6b  xor     r8d, r8d; unsigned int
0x180008c6e  mov     [rsp+310h+var_2E8], rax; HKEY *
0x180008c73  lea     r9, [rsp+310h+var_2B8]; HKEY *
0x180008c78  lea     rax, [rbp+210h+StringUuid]
0x180008c7c  xor     edx, edx; unsigned int
0x180008c7e  mov     rcx, rdi; this
0x180008c81  mov     [rsp+310h+var_2F0], rax; char *
0x180008c86  call    ?OpenKey@CContactRegistry@@AEAAJKKPEAPEAUHKEY__@@PEBD0@Z; CContactRegistry::OpenKey(ulong,ulong,HKEY__ * *,char const *,HKEY__ * *)
0x180008c8b  mov     ebx, eax
0x180008c8d  test    eax, eax
0x180008c8f  js      loc_180008A18
0x180008c95  lea     rax, [rsp+310h+var_298]
0x180008c9a  xor     r8d, r8d; unsigned int
0x180008c9d  mov     [rsp+310h+var_2E8], rax; HKEY *
0x180008ca2  lea     r9, [rsp+310h+var_2B0]; HKEY *
0x180008ca7  lea     rax, aDescription; "Description"
0x180008cae  xor     edx, edx; unsigned int
0x180008cb0  mov     rcx, rdi; this
0x180008cb3  mov     [rsp+310h+var_2F0], rax; char *
0x180008cb8  call    ?OpenKey@CContactRegistry@@AEAAJKKPEAPEAUHKEY__@@PEBD0@Z; CContactRegistry::OpenKey(ulong,ulong,HKEY__ * *,char const *,HKEY__ * *)
0x180008cbd  mov     ebx, eax
0x180008cbf  test    eax, eax
0x180008cc1  js      loc_180008A18
0x180008cc7  lea     r9, [rbp+210h+var_240]; unsigned __int16 *
0x180008ccb  mov     dword ptr [rsp+310h+var_2F0], 100h; unsigned int
0x180008cd3  lea     r8, [rsp+310h+var_298]; HKEY *
0x180008cd8  mov     rcx, rdi; this
0x180008cdb  call    ?ReadKeyValueW@CContactRegistry@@AEAAJKPEAPEAUHKEY__@@PEAGK@Z; CContactRegistry::ReadKeyValueW(ulong,HKEY__ * *,ushort *,ulong)
0x180008ce0  mov     ebx, eax
0x180008ce2  lea     rdx, [rsp+310h+var_2B0]
0x180008ce7  mov     rax, [rdi]
0x180008cea  mov     rcx, rdi
0x180008ced  mov     rax, [rax+0B0h]
0x180008cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf9  test    ebx, ebx
0x180008cfb  js      loc_180008A18
0x180008d01  test    r12, r12
0x180008d04  jz      short loc_180008D28
0x180008d06  lea     rax, [rbp+210h+var_240]
0x180008d0a  mov     r8, r12
0x180008d0d  sub     r8, rax
0x180008d10  movzx   edx, word ptr [rax]
0x180008d13  movzx   ecx, word ptr [rax+r8]
0x180008d18  sub     edx, ecx
0x180008d1a  jnz     short loc_180008D24
0x180008d1c  add     rax, 2
0x180008d20  test    ecx, ecx
0x180008d22  jnz     short loc_180008D10
0x180008d24  test    edx, edx
0x180008d26  jz      short loc_180008D30
0x180008d28  add     esi, r15d
0x180008d2b  jmp     loc_180008C2D
0x180008d30  lea     rdx, [rdi+20h]; Uuid
0x180008d34  lea     rcx, [rbp+210h+StringUuid]; StringUuid
0x180008d38  call    cs:__imp_UuidFromStringA
0x180008d3e  xor     r8d, r8d
0x180008d41  lea     rax, [rbp+210h+StringUuid]
0x180008d45  cmp     r14d, 3
0x180008d49  lea     rsi, [rdi+10h]
0x180008d4d  mov     [rsp+310h+var_2E8], rsi; HKEY *
0x180008d52  lea     r9, [rsp+310h+var_2B8]; HKEY *
0x180008d57  setnz   r8b; unsigned int
0x180008d5b  mov     [rsp+310h+var_2F0], rax; char *
0x180008d60  mov     edx, r13d; unsigned int
0x180008d63  mov     rcx, rdi; this
0x180008d66  call    ?OpenKey@CContactRegistry@@AEAAJKKPEAPEAUHKEY__@@PEBD0@Z; CContactRegistry::OpenKey(ulong,ulong,HKEY__ * *,char const *,HKEY__ * *)
0x180008d6b  mov     ebx, eax
0x180008d6d  cmp     eax, 80100044h
0x180008d72  jz      loc_180008FF7
0x180008d78  test    eax, eax
0x180008d7a  js      loc_180008A18
0x180008d80  mov     r12d, 2
0x180008d86  cmp     r14d, r12d
0x180008d89  jnz     loc_180008F10
0x180008d8f  lea     rax, [rsp+310h+var_2C8]
0x180008d94  mov     r9, rsi; HKEY *
0x180008d97  mov     [rsp+310h+var_2E8], rax; HKEY *
0x180008d9c  mov     r8d, r12d; unsigned int
0x180008d9f  lea     rax, aDescription; "Description"
0x180008da6  mov     edx, r15d; unsigned int
0x180008da9  mov     rcx, rdi; this
0x180008dac  mov     [rsp+310h+var_2F0], rax; char *
0x180008db1  call    ?OpenKey@CContactRegistry@@AEAAJKKPEAPEAUHKEY__@@PEBD0@Z; CContactRegistry::OpenKey(ulong,ulong,HKEY__ * *,char const *,HKEY__ * *)
0x180008db6  mov     ebx, eax
0x180008db8  test    eax, eax
0x180008dba  js      loc_180008A18
0x180008dc0  lea     rax, [rsp+310h+var_2C8]
0x180008dc5  mov     r9, rsi; HKEY *
0x180008dc8  mov     [rsp+310h+var_2E8], rax; HKEY *
0x180008dcd  mov     r8d, r12d; unsigned int
0x180008dd0  lea     rax, aHost; "Host"
0x180008dd7  mov     edx, r15d; unsigned int
0x180008dda  mov     rcx, rdi; this
0x180008ddd  mov     [rsp+310h+var_2F0], rax; char *
0x180008de2  call    ?OpenKey@CContactRegistry@@AEAAJKKPEAPEAUHKEY__@@PEBD0@Z; CContactRegistry::OpenKey(ulong,ulong,HKEY__ * *,char const *,HKEY__ * *)
0x180008de7  mov     ebx, eax
0x180008de9  test    eax, eax
0x180008deb  js      loc_180008A18
0x180008df1  lea     rax, [rsp+310h+var_2C8]
0x180008df6  mov     r9, rsi; HKEY *
0x180008df9  mov     [rsp+310h+var_2E8], rax; HKEY *
0x180008dfe  mov     r8d, r12d; unsigned int
0x180008e01  lea     rax, aClsid; "Clsid"
0x180008e08  mov     edx, r15d; unsigned int
  ... truncated ...
```
