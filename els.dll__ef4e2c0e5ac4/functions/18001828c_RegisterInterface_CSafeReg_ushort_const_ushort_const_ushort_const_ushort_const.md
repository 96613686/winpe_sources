# RegisterInterface(CSafeReg *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18001828c`
- end: `0x180018397`
- name: `?RegisterInterface@@YAJPEAVCSafeReg@@PEBG111@Z`
- size: `267`
- prototype: `int(struct CSafeReg *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018580`

## callees

- `0x18001828c`
- `0x18001abd8`
- `0x18001ac74`
- `0x18001b11c`

## string_xrefs

- `0x18001833b`: `ProxyStubClsid32`

## pseudocode

```c
__int64 __fastcall RegisterInterface(
        HKEY *a1,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int16 *a5)
{
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r8
  HKEY v14; // [rsp+30h] [rbp-18h] BYREF
  HKEY v15[2]; // [rsp+38h] [rbp-10h] BYREF

  a5 = 0;
  v15[0] = 0;
  v14 = 0;
  v7 = CSafeReg::Create(a1, a2, (HKEY *)&a5);
  if ( v7 >= 0 )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a3[2 * v10] );
    v7 = CSafeReg::SetValue((HKEY *)&a5, 0, v8, a3, 2 * (int)v10 + 2);
    if ( v7 >= 0 )
    {
      v7 = CSafeReg::Create((HKEY *)&a5, L"NumMethods", v15);
      if ( v7 >= 0 )
      {
        do
          ++v9;
        while ( *(_WORD *)&a4[2 * v9] );
        v7 = CSafeReg::SetValue(v15, 0, v11, a4, 2 * (int)v9 + 2);
        if ( v7 >= 0 )
        {
          v7 = CSafeReg::Create((HKEY *)&a5, L"ProxyStubClsid32", &v14);
          if ( v7 >= 0 )
            v7 = CSafeReg::SetValue(
                   &v14,
                   0,
                   v12,
                   (const unsigned __int8 *)L"{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}",
                   0x4Eu);
        }
      }
    }
  }
  CSafeReg::Close((CSafeReg *)&v14);
  CSafeReg::Close((CSafeReg *)v15);
  CSafeReg::Close((CSafeReg *)&a5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001828c  push    rbp
0x18001828e  push    rbx
0x18001828f  push    rsi
0x180018290  push    rdi
0x180018291  push    r14
0x180018293  push    r15
0x180018295  mov     rbp, rsp
0x180018298  sub     rsp, 48h
0x18001829c  xor     r15d, r15d
0x18001829f  mov     rsi, r8
0x1800182a2  lea     r8, [rbp+arg_20]; struct CSafeReg *
0x1800182a6  mov     [rbp+arg_20], r15
0x1800182aa  mov     [rbp+var_10], r15
0x1800182ae  mov     r14, r9
0x1800182b1  mov     [rbp+var_18], r15
0x1800182b5  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x1800182ba  mov     ebx, eax
0x1800182bc  test    eax, eax
0x1800182be  js      loc_18001836D
0x1800182c4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800182c8  mov     rax, rdi
0x1800182cb  inc     rax
0x1800182ce  cmp     [rsi+rax*2], r15w
0x1800182d3  jnz     short loc_1800182CB
0x1800182d5  lea     eax, ds:2[rax*2]
0x1800182dc  mov     r9, rsi; unsigned __int8 *
0x1800182df  xor     edx, edx; unsigned __int16 *
0x1800182e1  mov     [rsp+48h+var_28], eax; unsigned int
0x1800182e5  lea     rcx, [rbp+arg_20]; this
0x1800182e9  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x1800182ee  mov     ebx, eax
0x1800182f0  test    eax, eax
0x1800182f2  js      short loc_18001836D
0x1800182f4  lea     r8, [rbp+var_10]; struct CSafeReg *
0x1800182f8  lea     rdx, aNummethods; "NumMethods"
0x1800182ff  lea     rcx, [rbp+arg_20]; this
0x180018303  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x180018308  mov     ebx, eax
0x18001830a  test    eax, eax
0x18001830c  js      short loc_18001836D
0x18001830e  inc     rdi
0x180018311  cmp     [r14+rdi*2], r15w
0x180018316  jnz     short loc_18001830E
0x180018318  lea     eax, ds:2[rdi*2]
0x18001831f  mov     r9, r14; unsigned __int8 *
0x180018322  xor     edx, edx; unsigned __int16 *
0x180018324  mov     [rsp+48h+var_28], eax; unsigned int
0x180018328  lea     rcx, [rbp+var_10]; this
0x18001832c  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018331  mov     ebx, eax
0x180018333  test    eax, eax
0x180018335  js      short loc_18001836D
0x180018337  lea     r8, [rbp+var_18]; struct CSafeReg *
0x18001833b  lea     rdx, aProxystubclsid; "ProxyStubClsid32"
0x180018342  lea     rcx, [rbp+arg_20]; this
0x180018346  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x18001834b  mov     ebx, eax
0x18001834d  test    eax, eax
0x18001834f  js      short loc_18001836D
0x180018351  lea     r9, a05238c14A6e111; "{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}"
0x180018358  mov     [rsp+48h+var_28], 4Eh ; 'N'; unsigned int
0x180018360  xor     edx, edx; unsigned __int16 *
0x180018362  lea     rcx, [rbp+var_18]; this
0x180018366  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x18001836b  mov     ebx, eax
0x18001836d  lea     rcx, [rbp+var_18]; this
0x180018371  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018376  lea     rcx, [rbp+var_10]; this
0x18001837a  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001837f  lea     rcx, [rbp+arg_20]; this
0x180018383  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018388  mov     eax, ebx
0x18001838a  add     rsp, 48h
0x18001838e  pop     r15
0x180018390  pop     r14
0x180018392  pop     rdi
0x180018393  pop     rsi
0x180018394  pop     rbx
0x180018395  pop     rbp
0x180018396  retn
```
