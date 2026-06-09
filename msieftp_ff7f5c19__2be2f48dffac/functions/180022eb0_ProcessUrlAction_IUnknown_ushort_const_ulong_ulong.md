# ProcessUrlAction(IUnknown *,ushort const *,ulong,ulong)

- ea: `0x180022eb0`
- end: `0x180022fa9`
- name: `?ProcessUrlAction@@YAHPEAUIUnknown@@PEBGKK@Z`
- size: `249`
- prototype: `__int64 __fastcall(IUnknown *punkSite, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023034`

## callees

- `0x180022eb0`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180022f1f`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180022f82`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180022f1f`
- `SHLWAPI!__imp_IUnknown_SetSite` at `0x180022f82`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022efb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022efb`

## pseudocode

```c
_BOOL8 __fastcall ProcessUrlAction(IUnknown *punkSite, const unsigned __int16 *a2, int a3, int a4)
{
  BOOL v4; // ebx
  IUnknown *punk; // [rsp+78h] [rbp+10h] BYREF
  int v9; // [rsp+80h] [rbp+18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF

  v10 = a4;
  v9 = a3;
  v4 = 0;
  if ( a2 )
  {
    punk = 0;
    if ( CoCreateInstance(
           &CLSID_InternetSecurityManager,
           0,
           1u,
           &GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b,
           (LPVOID *)&punk) >= 0 )
    {
      v10 = 0;
      v9 = 0;
      IUnknown_SetSite(punk, punkSite);
      if ( !((unsigned int (__fastcall *)(IUnknown *, const unsigned __int16 *, __int64, int *, int, int *, int, int, _DWORD))punk->lpVtbl[2].AddRef)(
              punk,
              a2,
              6147,
              &v10,
              4,
              &v9,
              4,
              4,
              0) )
        v4 = (v10 & 0xF) == 0;
      IUnknown_SetSite(punk, 0);
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180022eb0  mov     r11, rsp
0x180022eb3  mov     [r11+8], rbx
0x180022eb7  mov     [r11+20h], r9d
0x180022ebb  mov     [r11+18h], r8d
0x180022ebf  push    rsi
0x180022ec0  push    rdi
0x180022ec1  push    r14
0x180022ec3  sub     rsp, 50h
0x180022ec7  xor     ebx, ebx
0x180022ec9  mov     rdi, rdx
0x180022ecc  mov     rsi, rcx
0x180022ecf  test    rdx, rdx
0x180022ed2  jz      loc_180022F99
0x180022ed8  lea     rax, [r11+10h]
0x180022edc  mov     [r11+10h], rbx
0x180022ee0  lea     r14d, [rbx+1]
0x180022ee4  mov     [r11-48h], rax
0x180022ee8  mov     r8d, r14d; dwClsContext
0x180022eeb  lea     r9, _GUID_79eac9ee_baf9_11ce_8c82_00aa004ba90b; riid
0x180022ef2  xor     edx, edx; pUnkOuter
0x180022ef4  lea     rcx, CLSID_InternetSecurityManager; rclsid
0x180022efb  call    cs:__imp_CoCreateInstance
0x180022f01  test    eax, eax
0x180022f03  js      loc_180022F99
0x180022f09  mov     rcx, [rsp+68h+punk]; punk
0x180022f0e  mov     rdx, rsi; punkSite
0x180022f11  mov     [rsp+68h+arg_18], ebx
0x180022f18  mov     [rsp+68h+arg_10], ebx
0x180022f1f  call    cs:__imp_IUnknown_SetSite
0x180022f25  mov     rcx, [rsp+68h+punk]
0x180022f2a  lea     r8d, [rbx+4]
0x180022f2e  mov     [rsp+68h+var_28], ebx
0x180022f32  lea     rdx, [rsp+68h+arg_10]
0x180022f3a  mov     [rsp+68h+var_30], r8d
0x180022f3f  lea     r9, [rsp+68h+arg_18]
0x180022f47  mov     [rsp+68h+var_38], r8d
0x180022f4c  mov     rax, [rcx]
0x180022f4f  mov     [rsp+68h+var_40], rdx
0x180022f54  mov     rdx, rdi
0x180022f57  mov     [rsp+68h+var_48], r8d
0x180022f5c  mov     r8d, 1803h
0x180022f62  mov     rax, [rax+38h]
0x180022f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f6b  test    eax, eax
0x180022f6d  jnz     short loc_180022F7B
0x180022f6f  test    byte ptr [rsp+68h+arg_18], 0Fh
0x180022f77  cmovz   ebx, r14d
0x180022f7b  mov     rcx, [rsp+68h+punk]; punk
0x180022f80  xor     edx, edx; punkSite
0x180022f82  call    cs:__imp_IUnknown_SetSite
0x180022f88  mov     rcx, [rsp+68h+punk]
0x180022f8d  mov     rdx, [rcx]
0x180022f90  mov     rax, [rdx+10h]
0x180022f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f99  mov     eax, ebx
0x180022f9b  mov     rbx, [rsp+68h+arg_0]
0x180022fa0  add     rsp, 50h
0x180022fa4  pop     r14
0x180022fa6  pop     rdi
0x180022fa7  pop     rsi
0x180022fa8  retn
```
