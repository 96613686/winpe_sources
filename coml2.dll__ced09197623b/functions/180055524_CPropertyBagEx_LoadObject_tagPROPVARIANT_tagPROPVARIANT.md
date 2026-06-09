# CPropertyBagEx::LoadObject(tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180055524`
- end: `0x180055704`
- name: `?LoadObject@CPropertyBagEx@@AEBAJPEAUtagPROPVARIANT@@0@Z`
- size: `480`
- prototype: `__int64 __fastcall(CPropertyBagEx *__hidden this, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055f40`

## callees

- `0x18003f6e0`
- `0x180042800`
- `0x180043100`
- `0x180055524`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800555c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055671`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800555c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055671`

## pseudocode

```c
__int64 __fastcall CPropertyBagEx::LoadObject(
        CPropertyBagEx *this,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 (__fastcall ***QuadPart)(void *, GUID *, _QWORD *); // rcx
  LARGE_INTEGER *p_hVal; // rdi
  HRESULT v6; // ebx
  int v7; // eax
  LONGLONG v8; // rcx
  __int64 (__fastcall ***v9)(LPVOID, GUID *, __int64 *); // rcx
  LPVOID ppv; // [rsp+30h] [rbp-49h] BYREF
  int v12; // [rsp+38h] [rbp-41h] BYREF
  __int64 v13; // [rsp+40h] [rbp-39h] BYREF
  __int64 v14; // [rsp+48h] [rbp-31h] BYREF
  IID v15; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v16[56]; // [rsp+60h] [rbp-19h] BYREF
  IID rclsid; // [rsp+98h] [rbp+1Fh] BYREF

  QuadPart = (__int64 (__fastcall ***)(void *, GUID *, _QWORD *))a2->hVal.QuadPart;
  p_hVal = &a3->hVal;
  v13 = 0;
  v14 = 0;
  ppv = QuadPart;
  if ( a3->vt == 69 )
  {
    if ( !QuadPart )
    {
      memset_0(v16, 0, 0x50u);
      v6 = (*(__int64 (__fastcall **)(LONGLONG, _BYTE *, __int64))(*(_QWORD *)p_hVal->QuadPart + 136LL))(
             p_hVal->QuadPart,
             v16,
             1);
      if ( v6 < 0 )
        goto LABEL_18;
      v6 = CoCreateInstance(&rclsid, 0, 0x17u, &IID_IUnknown, &ppv);
      if ( v6 < 0 )
        goto LABEL_18;
      QuadPart = (__int64 (__fastcall ***)(void *, GUID *, _QWORD *))ppv;
    }
    v6 = (**QuadPart)(QuadPart, &IID_IPersistStorage, &v13);
    if ( v6 < 0 )
      goto LABEL_18;
    v7 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v13 + 48LL))(v13, p_hVal->QuadPart);
  }
  else
  {
    v8 = p_hVal->QuadPart;
    v12 = 0;
    v15 = 0;
    v6 = (*(__int64 (__fastcall **)(LONGLONG, IID *, __int64, int *))(*(_QWORD *)v8 + 24LL))(v8, &v15, 16, &v12);
    if ( v6 < 0 )
      goto LABEL_18;
    if ( v12 != 16 )
    {
      v6 = -2147286789;
      goto LABEL_18;
    }
    v9 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    if ( !ppv )
    {
      v6 = CoCreateInstance(&v15, 0, 0x17u, &IID_IUnknown, &ppv);
      if ( v6 < 0 )
        goto LABEL_18;
      v9 = (__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    }
    v6 = (**v9)(v9, &IID_IPersistStream, &v14);
    if ( v6 < 0 )
      goto LABEL_18;
    v7 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v14 + 40LL))(v14, p_hVal->QuadPart);
  }
  v6 = v7;
  if ( v7 >= 0 )
  {
    v6 = 0;
    a2->hVal.QuadPart = (LONGLONG)ppv;
    ppv = 0;
  }
LABEL_18:
  RELEASE_INTERFACE<IUnknown>(&v13);
  RELEASE_INTERFACE<IUnknown>(&v14);
  RELEASE_INTERFACE<IUnknown>(&ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180055524  mov     [rsp-8+arg_0], rbx
0x180055529  push    rbp
0x18005552a  push    rsi
0x18005552b  push    rdi
0x18005552c  lea     rbp, [rsp-47h]
0x180055531  sub     rsp, 0C0h
0x180055538  mov     rax, cs:__security_cookie
0x18005553f  xor     rax, rsp
0x180055542  mov     [rbp+57h+var_20], rax
0x180055546  mov     rcx, [rdx+8]
0x18005554a  lea     rdi, [r8+8]
0x18005554e  mov     eax, 45h ; 'E'
0x180055553  mov     [rbp+57h+var_90], 0
0x18005555b  mov     rsi, rdx
0x18005555e  mov     [rbp+57h+var_88], 0
0x180055566  mov     [rbp+57h+var_A0], rcx
0x18005556a  cmp     ax, [r8]
0x18005556e  jnz     loc_18005560C
0x180055574  test    rcx, rcx
0x180055577  jnz     short loc_1800555DC
0x180055579  lea     r8d, [rcx+50h]; Size
0x18005557d  xor     edx, edx; Val
0x18005557f  lea     rcx, [rbp+57h+var_70]; void *
0x180055583  call    memset_0
0x180055588  mov     rcx, [rdi]
0x18005558b  lea     rdx, [rbp+57h+var_70]
0x18005558f  mov     r8d, 1
0x180055595  mov     rax, [rcx]
0x180055598  mov     rax, [rax+88h]
0x18005559f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555a4  mov     ebx, eax
0x1800555a6  test    eax, eax
0x1800555a8  js      loc_1800556C8
0x1800555ae  xor     edx, edx; pUnkOuter
0x1800555b0  lea     rax, [rbp+57h+var_A0]
0x1800555b4  lea     r9, IID_IUnknown; riid
0x1800555bb  mov     [rsp+0D0h+ppv], rax; ppv
0x1800555c0  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1800555c4  lea     r8d, [rdx+17h]; dwClsContext
0x1800555c8  call    cs:__imp_CoCreateInstance
0x1800555ce  mov     ebx, eax
0x1800555d0  test    eax, eax
0x1800555d2  js      loc_1800556C8
0x1800555d8  mov     rcx, [rbp+57h+var_A0]
0x1800555dc  mov     rax, [rcx]
0x1800555df  lea     r8, [rbp+57h+var_90]
0x1800555e3  lea     rdx, IID_IPersistStorage
0x1800555ea  mov     rax, [rax]
0x1800555ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800555f2  mov     ebx, eax
0x1800555f4  test    eax, eax
0x1800555f6  js      loc_1800556C8
0x1800555fc  mov     rcx, [rbp+57h+var_90]
0x180055600  mov     rax, [rcx]
0x180055603  mov     rax, [rax+30h]
0x180055607  jmp     loc_1800556A8
0x18005560c  mov     rcx, [rdi]
0x18005560f  lea     r9, [rbp+57h+var_98]
0x180055613  xorps   xmm0, xmm0
0x180055616  mov     [rbp+57h+var_98], 0
0x18005561d  movups  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x180055621  mov     r8d, 10h
0x180055627  lea     rdx, [rbp+57h+var_80]
0x18005562b  mov     rax, [rcx]
0x18005562e  mov     rax, [rax+18h]
0x180055632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055637  mov     ebx, eax
0x180055639  test    eax, eax
0x18005563b  js      loc_1800556C8
0x180055641  cmp     [rbp+57h+var_98], 10h
0x180055645  jz      short loc_18005564E
0x180055647  mov     ebx, 800300FBh
0x18005564c  jmp     short loc_1800556C8
0x18005564e  mov     rcx, [rbp+57h+var_A0]
0x180055652  test    rcx, rcx
0x180055655  jnz     short loc_180055681
0x180055657  lea     rax, [rbp+57h+var_A0]
0x18005565b  xor     edx, edx; pUnkOuter
0x18005565d  lea     r8d, [rcx+17h]; dwClsContext
0x180055661  mov     [rsp+0D0h+ppv], rax; ppv
0x180055666  lea     rcx, [rbp+57h+var_80]; rclsid
0x18005566a  lea     r9, IID_IUnknown; riid
0x180055671  call    cs:__imp_CoCreateInstance
0x180055677  mov     ebx, eax
0x180055679  test    eax, eax
0x18005567b  js      short loc_1800556C8
0x18005567d  mov     rcx, [rbp+57h+var_A0]
0x180055681  mov     rax, [rcx]
0x180055684  lea     r8, [rbp+57h+var_88]
0x180055688  lea     rdx, IID_IPersistStream
0x18005568f  mov     rax, [rax]
0x180055692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055697  mov     ebx, eax
0x180055699  test    eax, eax
0x18005569b  js      short loc_1800556C8
0x18005569d  mov     rcx, [rbp+57h+var_88]
0x1800556a1  mov     rax, [rcx]
0x1800556a4  mov     rax, [rax+28h]
0x1800556a8  mov     rdx, [rdi]
0x1800556ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800556b0  mov     ebx, eax
0x1800556b2  test    eax, eax
0x1800556b4  js      short loc_1800556C8
0x1800556b6  mov     rax, [rbp+57h+var_A0]
0x1800556ba  xor     ebx, ebx
0x1800556bc  mov     [rsi+8], rax
0x1800556c0  mov     [rbp+57h+var_A0], 0
0x1800556c8  lea     rcx, [rbp+57h+var_90]
0x1800556cc  call    ??$RELEASE_INTERFACE@UIUnknown@@@@YAKAEAPEAUIUnknown@@@Z; RELEASE_INTERFACE<IUnknown>(IUnknown * &)
0x1800556d1  lea     rcx, [rbp+57h+var_88]
0x1800556d5  call    ??$RELEASE_INTERFACE@UIUnknown@@@@YAKAEAPEAUIUnknown@@@Z; RELEASE_INTERFACE<IUnknown>(IUnknown * &)
0x1800556da  lea     rcx, [rbp+57h+var_A0]
0x1800556de  call    ??$RELEASE_INTERFACE@UIUnknown@@@@YAKAEAPEAUIUnknown@@@Z; RELEASE_INTERFACE<IUnknown>(IUnknown * &)
0x1800556e3  mov     eax, ebx
0x1800556e5  mov     rcx, [rbp+57h+var_20]
0x1800556e9  xor     rcx, rsp; StackCookie
0x1800556ec  call    __security_check_cookie
0x1800556f1  mov     rbx, [rsp+0D0h+arg_0]
0x1800556f9  add     rsp, 0C0h
0x180055700  pop     rdi
0x180055701  pop     rsi
0x180055702  pop     rbp
0x180055703  retn
```
