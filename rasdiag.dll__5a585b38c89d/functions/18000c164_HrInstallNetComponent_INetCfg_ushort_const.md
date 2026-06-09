# HrInstallNetComponent(INetCfg *,ushort const *)

- ea: `0x18000c164`
- end: `0x18000c262`
- name: `?HrInstallNetComponent@@YAJPEAUINetCfg@@PEBG@Z`
- size: `254`
- prototype: `__int64 __fastcall(struct INetCfg *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c7f0`

## callees

- `0x18000c164`
- `0x18000ca8c`
- `0x18000f010`

## string_xrefs

- `0x18000c229`: `HrInstallNetComponent: IID_INetCfgClassSetup::Install failed with 0x%x`

## pseudocode

```c
__int64 __fastcall HrInstallNetComponent(struct INetCfg *a1, const unsigned __int16 *a2)
{
  struct INetCfgVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryNetCfgClass)(INetCfg *, const GUID *, const IID *const, void **); // rax
  int v5; // ebx
  int v6; // eax
  _OWORD v8[3]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v9; // [rsp+90h] [rbp+10h] BYREF
  __int64 v10; // [rsp+A0h] [rbp+20h] BYREF

  lpVtbl = a1->lpVtbl;
  v9 = 0;
  v10 = 0;
  memset(v8, 0, sizeof(v8));
  QueryNetCfgClass = lpVtbl->QueryNetCfgClass;
  LODWORD(v8[0]) = 1;
  v5 = ((__int64 (__fastcall *)(struct INetCfg *, GUID *, GUID *, __int64 *))QueryNetCfgClass)(
         a1,
         &GUID_DEVCLASS_NETTRANS,
         &IID_INetCfgClassSetup,
         &v9);
  if ( v5 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _OWORD *, __int64, _DWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v9 + 32LL))(
           v9,
           a2,
           v8,
           2,
           0,
           0,
           0,
           &v10);
    v5 = v6;
    if ( v6 )
    {
      RasDiagTrace("HrInstallNetComponent: IID_INetCfgClassSetup::Install failed with 0x%x", v6);
    }
    else if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c164  mov     [rsp-8+arg_8], rbx
0x18000c169  mov     [rsp-8+arg_18], rdi
0x18000c16e  push    rbp
0x18000c16f  mov     rbp, rsp
0x18000c172  sub     rsp, 80h
0x18000c179  mov     rax, [rcx]
0x18000c17c  lea     r9, [rbp+arg_0]
0x18000c180  xorps   xmm0, xmm0
0x18000c183  mov     [rbp+arg_0], 0
0x18000c18b  mov     rdi, rdx
0x18000c18e  mov     [rbp+arg_10], 0
0x18000c196  movups  [rbp+var_30], xmm0
0x18000c19a  mov     rax, [rax+48h]
0x18000c19e  lea     r8, IID_INetCfgClassSetup
0x18000c1a5  lea     rdx, GUID_DEVCLASS_NETTRANS
0x18000c1ac  mov     dword ptr [rbp+var_30], 1
0x18000c1b3  movups  [rbp+var_20], xmm0
0x18000c1b7  movups  [rbp+var_10], xmm0
0x18000c1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c0  mov     ebx, eax
0x18000c1c2  test    eax, eax
0x18000c1c4  js      loc_18000C24A
0x18000c1ca  mov     rcx, [rbp+arg_0]
0x18000c1ce  lea     rdx, [rbp+arg_10]
0x18000c1d2  mov     [rsp+80h+var_48], rdx
0x18000c1d7  lea     r8, [rbp+var_30]
0x18000c1db  mov     [rsp+80h+var_50], 0
0x18000c1e4  mov     r9d, 2
0x18000c1ea  mov     [rsp+80h+var_58], 0
0x18000c1f3  mov     rdx, rdi
0x18000c1f6  mov     rax, [rcx]
0x18000c1f9  mov     [rsp+80h+var_60], 0
0x18000c201  mov     rax, [rax+20h]
0x18000c205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c20a  mov     ebx, eax
0x18000c20c  test    eax, eax
0x18000c20e  jnz     short loc_18000C227
0x18000c210  mov     rcx, [rbp+arg_10]
0x18000c214  test    rcx, rcx
0x18000c217  jz      short loc_18000C235
0x18000c219  mov     rax, [rcx]
0x18000c21c  mov     rax, [rax+10h]
0x18000c220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c225  jmp     short loc_18000C235
0x18000c227  mov     edx, eax
0x18000c229  lea     rcx, aHrinstallnetco; "HrInstallNetComponent: IID_INetCfgClass"...
0x18000c230  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c235  mov     rcx, [rbp+arg_0]
0x18000c239  test    rcx, rcx
0x18000c23c  jz      short loc_18000C24A
0x18000c23e  mov     rax, [rcx]
0x18000c241  mov     rax, [rax+10h]
0x18000c245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c24a  lea     r11, [rsp+80h+var_s0]
0x18000c252  mov     eax, ebx
0x18000c254  mov     rbx, [r11+18h]
0x18000c258  mov     rdi, [r11+28h]
0x18000c25c  mov     rsp, r11
0x18000c25f  pop     rbp
0x18000c260  retn
```
