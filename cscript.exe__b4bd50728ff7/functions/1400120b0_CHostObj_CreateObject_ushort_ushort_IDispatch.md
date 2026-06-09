# CHostObj::CreateObject(ushort *,ushort *,IDispatch * *)

- ea: `0x1400120b0`
- end: `0x1400121e8`
- name: `?CreateObject@CHostObj@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x14000d2e0`
- `0x140011c00`
- `0x1400120b0`
- `0x1400121f0`
- `0x1400161d0`
- `0x140017010`

## string_xrefs

- `0x140012175`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::CreateObject(
        CHostObj *this,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        struct IDispatch **a4)
{
  unsigned __int64 v5; // rdi
  struct IDispatch *v8; // rcx
  int v9; // ebx
  struct IDispatch *v10; // [rsp+20h] [rbp-38h] BYREF
  struct IUnknown *v11; // [rsp+28h] [rbp-30h] BYREF
  struct _GUID v12; // [rsp+30h] [rbp-28h] BYREF

  v5 = a3;
  if ( !a4 )
    return 2147500035LL;
  v8 = 0;
  v11 = 0;
  v10 = 0;
  *a4 = 0;
  v12 = 0;
  if ( !a2 || !*a2 )
  {
    v9 = -2147024809;
LABEL_15:
    if ( v8 )
      ((void (__fastcall *)(struct IDispatch *))v8->lpVtbl->Release)(v8);
    goto LABEL_17;
  }
  if ( a3 )
    v5 = -(__int64)(*(_WORD *)a3 != 0) & a3;
  v9 = CHostObj::CreateObjectHelper(this, a2, &v12, (LPVOID *)&v11);
  if ( v9 < 0
    || (v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IDispatch **))v11->lpVtbl->QueryInterface)(
               v11,
               &IID_IDispatch,
               &v10),
        v9 < 0) )
  {
LABEL_12:
    v8 = v10;
    goto LABEL_15;
  }
  if ( v5 && (int)ConnectObject(&v12, v10, v5) < 0 )
  {
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Eu);
    v9 = -2147352567;
    goto LABEL_12;
  }
  v9 = 0;
  *a4 = v10;
  v10 = 0;
LABEL_17:
  if ( v11 )
    ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400120b0  push    rbp
0x1400120b2  push    rbx
0x1400120b3  push    rsi
0x1400120b4  push    rdi
0x1400120b5  mov     rbp, rsp
0x1400120b8  sub     rsp, 58h
0x1400120bc  mov     rax, cs:__security_cookie
0x1400120c3  xor     rax, rsp
0x1400120c6  mov     [rbp+var_18], rax
0x1400120ca  mov     rsi, r9
0x1400120cd  mov     rdi, r8
0x1400120d0  mov     r10, rcx
0x1400120d3  test    r9, r9
0x1400120d6  jnz     short loc_1400120E2
0x1400120d8  mov     eax, 80004003h
0x1400120dd  jmp     loc_1400121D3
0x1400120e2  xor     ecx, ecx
0x1400120e4  mov     [rbp+var_30], 0
0x1400120ec  mov     [rbp+var_38], rcx
0x1400120f0  xorps   xmm0, xmm0
0x1400120f3  mov     [r9], rcx
0x1400120f6  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x1400120fa  test    rdx, rdx
0x1400120fd  jz      loc_1400121A6
0x140012103  xor     eax, eax
0x140012105  cmp     ax, [rdx]
0x140012108  jz      loc_1400121A6
0x14001210e  test    rdi, rdi
0x140012111  jz      short loc_140012120
0x140012113  movzx   eax, word ptr [r8]
0x140012117  neg     ax
0x14001211a  sbb     r8, r8
0x14001211d  and     rdi, r8
0x140012120  lea     r9, [rbp+var_30]; struct IUnknown **
0x140012124  mov     rcx, r10; this
0x140012127  lea     r8, [rbp+var_28]; struct _GUID *
0x14001212b  call    ?CreateObjectHelper@CHostObj@@IEAAJPEAGPEAU_GUID@@PEAPEAUIUnknown@@@Z; CHostObj::CreateObjectHelper(ushort *,_GUID *,IUnknown * *)
0x140012130  mov     ebx, eax
0x140012132  test    eax, eax
0x140012134  js      short loc_14001218D
0x140012136  mov     rcx, [rbp+var_30]
0x14001213a  lea     r8, [rbp+var_38]
0x14001213e  lea     rdx, IID_IDispatch
0x140012145  mov     rax, [rcx]
0x140012148  mov     rax, [rax]
0x14001214b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012150  mov     ebx, eax
0x140012152  test    eax, eax
0x140012154  js      short loc_14001218D
0x140012156  test    rdi, rdi
0x140012159  jz      short loc_140012193
0x14001215b  mov     rdx, [rbp+var_38]
0x14001215f  lea     rcx, [rbp+var_28]
0x140012163  mov     r8, rdi
0x140012166  call    ConnectObject
0x14001216b  test    eax, eax
0x14001216d  jns     short loc_140012193
0x14001216f  mov     r8d, 0C1Eh; unsigned int
0x140012175  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14001217c  lea     rcx, IID_IHost; struct _GUID *
0x140012183  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x140012188  mov     ebx, 80020009h
0x14001218d  mov     rcx, [rbp+var_38]
0x140012191  jmp     short loc_1400121AB
0x140012193  mov     rax, [rbp+var_38]
0x140012197  xor     ebx, ebx
0x140012199  mov     [rsi], rax
0x14001219c  mov     [rbp+var_38], 0
0x1400121a4  jmp     short loc_1400121BC
0x1400121a6  mov     ebx, 80070057h
0x1400121ab  test    rcx, rcx
0x1400121ae  jz      short loc_1400121BC
0x1400121b0  mov     rax, [rcx]
0x1400121b3  mov     rax, [rax+10h]
0x1400121b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400121bc  mov     rcx, [rbp+var_30]
0x1400121c0  test    rcx, rcx
0x1400121c3  jz      short loc_1400121D1
0x1400121c5  mov     rax, [rcx]
0x1400121c8  mov     rax, [rax+10h]
0x1400121cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400121d1  mov     eax, ebx
0x1400121d3  mov     rcx, [rbp+var_18]
0x1400121d7  xor     rcx, rsp; StackCookie
0x1400121da  call    __security_check_cookie
0x1400121df  add     rsp, 58h
0x1400121e3  pop     rdi
0x1400121e4  pop     rsi
0x1400121e5  pop     rbx
0x1400121e6  pop     rbp
0x1400121e7  retn
```
