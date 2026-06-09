# CImpIADOSecurity::SecurityDialog(IUnknown *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002a660`
- end: `0x18002a726`
- name: `?SecurityDialog@CImpIADOSecurity@@UEAAJPEAUIUnknown@@PEBG11@Z`
- size: `198`
- prototype: `int(CImpIADOSecurity *__hidden this, struct IUnknown *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18002a660`
- `0x18002a920`
- `0x18002aa28`
- `0x18002ab14`

## import_xrefs

- `USER32!MessageBoxW` at `0x18002a6fb`
- `USER32!MessageBoxW` at `0x18002a6fb`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::SecurityDialog(
        CImpIADOSecurity *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *lpCaption)
{
  __int64 result; // rax
  CImpIADOSecurity *v8; // rcx
  CImpIADOSecurity *v9; // rcx
  HWND WindowHandle; // rax
  __int64 v11; // rcx
  unsigned int v12; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v13[5]; // [rsp+24h] [rbp-14h] BYREF

  v12 = 0;
  v13[0] = 0;
  result = CImpIADOSecurity::getZone(this, a3, &v12, 0);
  if ( (int)result >= 0 )
  {
    result = CImpIADOSecurity::getPolicy(v8, v12, v13);
    if ( (int)result >= 0 )
    {
      if ( v13[0] )
      {
        if ( v13[0] != 1 )
        {
          if ( v13[0] != 3 )
            return 2147500037LL;
          return 1;
        }
        if ( !a2 )
          return 1;
        WindowHandle = CImpIADOSecurity::getWindowHandle(v9, a2);
        if ( !a4 )
          return 1;
        if ( !lpCaption )
          return 1;
        v11 = -1;
        do
          ++v11;
        while ( a4[v11] );
        if ( !v11 || MessageBoxW(WindowHandle, a4, lpCaption, 0x2034u) != 6 )
          return 1;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a660  mov     [rsp+arg_0], rbx
0x18002a665  mov     [rsp+arg_8], rsi
0x18002a66a  push    rdi
0x18002a66b  sub     rsp, 30h
0x18002a66f  mov     rax, r8
0x18002a672  mov     rdi, r9
0x18002a675  mov     rbx, rdx
0x18002a678  lea     r8, [rsp+38h+var_18]; unsigned int *
0x18002a67d  xor     esi, esi
0x18002a67f  mov     rdx, rax; unsigned __int16 *
0x18002a682  xor     r9d, r9d; struct IInternetSecurityManager **
0x18002a685  mov     [rsp+38h+var_18], esi
0x18002a689  mov     [rsp+38h+var_14], esi
0x18002a68d  call    ?getZone@CImpIADOSecurity@@AEAAJPEBGPEAKPEAPEAUIInternetSecurityManager@@@Z; CImpIADOSecurity::getZone(ushort const *,ulong *,IInternetSecurityManager * *)
0x18002a692  test    eax, eax
0x18002a694  js      short loc_18002A715
0x18002a696  mov     edx, [rsp+38h+var_18]; unsigned int
0x18002a69a  lea     r8, [rsp+38h+var_14]; unsigned int *
0x18002a69f  call    ?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z; CImpIADOSecurity::getPolicy(ulong,ulong *)
0x18002a6a4  test    eax, eax
0x18002a6a6  js      short loc_18002A715
0x18002a6a8  mov     eax, [rsp+38h+var_14]
0x18002a6ac  test    eax, eax
0x18002a6ae  jz      short loc_18002A713
0x18002a6b0  sub     eax, 1
0x18002a6b3  jz      short loc_18002A6C1
0x18002a6b5  cmp     eax, 2
0x18002a6b8  jz      short loc_18002A70C
0x18002a6ba  mov     eax, 80004005h
0x18002a6bf  jmp     short loc_18002A715
0x18002a6c1  test    rbx, rbx
0x18002a6c4  jz      short loc_18002A70C
0x18002a6c6  mov     rdx, rbx; struct IUnknown *
0x18002a6c9  call    ?getWindowHandle@CImpIADOSecurity@@AEAAPEAUHWND__@@PEAUIUnknown@@@Z; CImpIADOSecurity::getWindowHandle(IUnknown *)
0x18002a6ce  test    rdi, rdi
0x18002a6d1  jz      short loc_18002A70C
0x18002a6d3  mov     r8, [rsp+38h+lpCaption]; lpCaption
0x18002a6d8  test    r8, r8
0x18002a6db  jz      short loc_18002A70C
0x18002a6dd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002a6e1  inc     rcx
0x18002a6e4  cmp     [rdi+rcx*2], si
0x18002a6e8  jnz     short loc_18002A6E1
0x18002a6ea  test    rcx, rcx
0x18002a6ed  jz      short loc_18002A70C
0x18002a6ef  mov     r9d, 2034h; uType
0x18002a6f5  mov     rdx, rdi; lpText
0x18002a6f8  mov     rcx, rax; hWnd
0x18002a6fb  call    cs:__imp_MessageBoxW
0x18002a702  nop     dword ptr [rax+rax+00h]
0x18002a707  cmp     eax, 6
0x18002a70a  jz      short loc_18002A713
0x18002a70c  mov     eax, 1
0x18002a711  jmp     short loc_18002A715
0x18002a713  xor     eax, eax
0x18002a715  mov     rbx, [rsp+38h+arg_0]
0x18002a71a  mov     rsi, [rsp+38h+arg_8]
0x18002a71f  add     rsp, 30h
0x18002a723  pop     rdi
0x18002a724  retn
```
