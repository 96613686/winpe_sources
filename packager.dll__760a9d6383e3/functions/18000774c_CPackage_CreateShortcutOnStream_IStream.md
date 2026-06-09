# CPackage::CreateShortcutOnStream(IStream *)

- ea: `0x18000774c`
- end: `0x18000792d`
- name: `?CreateShortcutOnStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000882c`

## callees

- `0x18000774c`
- `0x18000ae84`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800077a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800077a6`

## pseudocode

```c
__int64 __fastcall CPackage::CreateShortcutOnStream(CPackage *this, struct IStream *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rax
  WCHAR *v6; // rdx
  WCHAR *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rcx
  WCHAR *v10; // rcx
  struct IStreamVtbl *lpVtbl; // rax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR sz[504]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v16[504]; // [rsp+430h] [rbp+330h] BYREF

  ppv = 0;
  v4 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &ppv);
  if ( v4 >= 0 )
  {
    v5 = *((_QWORD *)this + 15);
    v6 = sz;
    v14 = 0;
    v7 = (WCHAR *)(v5 + 4);
    v8 = 500;
    v9 = 2147483646;
    do
    {
      if ( !v9 )
        break;
      if ( !*v7 )
        break;
      *v6++ = *v7++;
      --v9;
      --v8;
    }
    while ( v8 );
    v10 = v6 - 1;
    if ( v8 )
      v10 = v6;
    *v10 = 0;
    PathSeparateArgs(sz, v16, 0x1F4u);
    (*(void (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 160LL))(ppv, sz);
    (*(void (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 136LL))(
      ppv,
      *((_QWORD *)this + 12) + 8LL,
      *(unsigned int *)(*((_QWORD *)this + 12) + 1048LL));
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 120LL))(ppv, 5);
    (*(void (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 88LL))(ppv, v16);
    v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IPersistStream, &v14);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, struct IStream *, __int64))(*(_QWORD *)v14 + 48LL))(v14, a2, 1);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  lpVtbl = a2->lpVtbl;
  v14 = 0;
  ((void (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))lpVtbl->Seek)(a2, 0, 0, 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000774c  mov     [rsp-8+arg_10], rbx
0x180007751  mov     [rsp-8+arg_18], rsi
0x180007756  push    rbp
0x180007757  push    rdi
0x180007758  push    r14
0x18000775a  lea     rbp, [rsp-730h]
0x180007762  sub     rsp, 830h
0x180007769  mov     rax, cs:__security_cookie
0x180007770  xor     rax, rsp
0x180007773  mov     [rbp+740h+var_20], rax
0x18000777a  xor     r14d, r14d
0x18000777d  lea     rax, [rsp+840h+var_810]
0x180007782  mov     rdi, rdx
0x180007785  mov     [rsp+840h+var_810], r14
0x18000778a  mov     rsi, rcx
0x18000778d  mov     [rsp+840h+ppv], rax; ppv
0x180007792  lea     r9, IID_IShellLinkW; riid
0x180007799  xor     edx, edx; pUnkOuter
0x18000779b  lea     r8d, [r14+1]; dwClsContext
0x18000779f  lea     rcx, CLSID_ShellLink; rclsid
0x1800077a6  call    cs:__imp_CoCreateInstance
0x1800077ac  mov     ebx, eax
0x1800077ae  test    eax, eax
0x1800077b0  js      loc_1800078E7
0x1800077b6  mov     rax, [rsi+78h]
0x1800077ba  lea     rdx, [rsp+840h+sz]
0x1800077bf  mov     r10d, 1F4h
0x1800077c5  mov     [rsp+840h+var_808], r14
0x1800077ca  add     rax, 4
0x1800077ce  mov     r8d, r10d
0x1800077d1  mov     ecx, 7FFFFFFEh
0x1800077d6  test    rcx, rcx
0x1800077d9  jz      short loc_1800077FA
0x1800077db  movzx   r9d, word ptr [rax]
0x1800077df  test    r9w, r9w
0x1800077e3  jz      short loc_1800077FA
0x1800077e5  mov     [rdx], r9w
0x1800077e9  add     rax, 2
0x1800077ed  add     rdx, 2
0x1800077f1  dec     rcx
0x1800077f4  sub     r8, 1
0x1800077f8  jnz     short loc_1800077D6
0x1800077fa  test    r8, r8
0x1800077fd  lea     rcx, [rdx-2]
0x180007801  mov     r8d, r10d; unsigned int
0x180007804  cmovnz  rcx, rdx
0x180007808  lea     rdx, [rbp+740h+var_410]; unsigned __int16 *
0x18000780f  mov     [rcx], r14w
0x180007813  lea     rcx, [rsp+840h+sz]; lpsz
0x180007818  call    ?PathSeparateArgs@@YAHPEAG0K@Z; PathSeparateArgs(ushort *,ushort *,ulong)
0x18000781d  mov     rcx, [rsp+840h+var_810]
0x180007822  lea     rdx, [rsp+840h+sz]
0x180007827  mov     rax, [rcx]
0x18000782a  mov     rax, [rax+0A0h]
0x180007831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007836  mov     r8, [rsi+60h]
0x18000783a  mov     rcx, [rsp+840h+var_810]
0x18000783f  lea     rdx, [r8+8]
0x180007843  mov     r8d, [r8+418h]
0x18000784a  mov     rax, [rcx]
0x18000784d  mov     rax, [rax+88h]
0x180007854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007859  mov     rcx, [rsp+840h+var_810]
0x18000785e  mov     edx, 5
0x180007863  mov     rax, [rcx]
0x180007866  mov     rax, [rax+78h]
0x18000786a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000786f  mov     rcx, [rsp+840h+var_810]
0x180007874  lea     rdx, [rbp+740h+var_410]
0x18000787b  mov     rax, [rcx]
0x18000787e  mov     rax, [rax+58h]
0x180007882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007887  mov     rcx, [rsp+840h+var_810]
0x18000788c  lea     r8, [rsp+840h+var_808]
0x180007891  lea     rdx, IID_IPersistStream
0x180007898  mov     rax, [rcx]
0x18000789b  mov     rax, [rax]
0x18000789e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078a3  mov     ebx, eax
0x1800078a5  test    eax, eax
0x1800078a7  js      short loc_1800078D6
0x1800078a9  mov     rcx, [rsp+840h+var_808]
0x1800078ae  mov     r8d, 1
0x1800078b4  mov     rdx, rdi
0x1800078b7  mov     rax, [rcx]
0x1800078ba  mov     rax, [rax+30h]
0x1800078be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078c3  mov     rcx, [rsp+840h+var_808]
0x1800078c8  mov     ebx, eax
0x1800078ca  mov     rax, [rcx]
0x1800078cd  mov     rax, [rax+10h]
0x1800078d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078d6  mov     rcx, [rsp+840h+var_810]
0x1800078db  mov     rax, [rcx]
0x1800078de  mov     rax, [rax+10h]
0x1800078e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e7  mov     rax, [rdi]
0x1800078ea  xor     r9d, r9d
0x1800078ed  xor     r8d, r8d
0x1800078f0  mov     [rsp+840h+var_808], r14
0x1800078f5  mov     rdx, r14
0x1800078f8  mov     rcx, rdi
0x1800078fb  mov     rax, [rax+28h]
0x1800078ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007904  mov     eax, ebx
0x180007906  mov     rcx, [rbp+740h+var_20]
0x18000790d  xor     rcx, rsp; StackCookie
0x180007910  call    __security_check_cookie
0x180007915  lea     r11, [rsp+840h+var_10]
0x18000791d  mov     rbx, [r11+30h]
0x180007921  mov     rsi, [r11+38h]
0x180007925  mov     rsp, r11
0x180007928  pop     r14
0x18000792a  pop     rdi
0x18000792b  pop     rbp
0x18000792c  retn
```
