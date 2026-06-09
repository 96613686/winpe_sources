# RassrvCommitSettings

- ea: `0x18002f0dc`
- end: `0x18002f239`
- name: `RassrvCommitSettings`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002eaf0`

## callees

- `0x18002ec90`
- `0x18002f0dc`
- `0x18002f240`
- `0x1800348f0`
- `0x180034c0c`
- `0x180035134`
- `0x1800360b8`
- `0x180036354`
- `0x180036398`
- `0x1800365a8`
- `0x18003708c`
- `0x18003bcf4`

## import_xrefs

- `USER32!GetPropW` at `0x18002f17a`
- `USER32!GetPropW` at `0x18002f17a`

## string_xrefs

- `0x18002f0f0`: `RassrvCommitSettings entered : %x`
- `0x18002f164`: `RassrvCommitSettings: keep svc running.`
- `0x18002f1a5`: `RassrvCommitSettings: DevOpenDatabase failed!`
- `0x18002f1ca`: `RassrvCommitSettings: devGetVpnEnable failed. Error %d`
- `0x18002f21e`: `RassrvCommitSettings: pvContext is NULL`

## pseudocode

```c
__int64 __fastcall RassrvCommitSettings(__int64 a1, int a2)
{
  __int64 v3; // rcx
  BOOL v4; // esi
  __int64 v5; // rcx
  _DWORD *PropW; // rax
  __int64 v7; // rcx
  unsigned int v8; // edi
  int VpnEnable; // eax
  int v11; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+50h] [rbp+18h] BYREF
  __int64 v13; // [rsp+58h] [rbp+20h] BYREF

  v13 = 0;
  v12 = 0;
  v11 = 0;
  DbgOutputTrace("RassrvCommitSettings entered : %x", a2);
  if ( !a1 )
  {
    DbgOutputTrace("RassrvCommitSettings: pvContext is NULL");
    return 87;
  }
  v3 = *(_QWORD *)(a1 + 24);
  v4 = 1;
  if ( v3 )
    usrFlushLocalDatabase(v3);
  v5 = *(_QWORD *)(a1 + 16);
  if ( v5 )
  {
    v4 = *(_DWORD *)(v5 + 20) != *(_DWORD *)(v5 + 24);
    devFlushDatabase();
  }
  if ( *(_QWORD *)(a1 + 40) )
    miscFlushDatabase();
  if ( *(_QWORD *)(a1 + 32) )
    netDbFlush();
  if ( *(_QWORD *)a1 )
  {
    DbgOutputTrace("RassrvCommitSettings: keep svc running.");
    PropW = GetPropW(*(HWND *)a1, qword_180064998);
    if ( PropW )
      PropW[2] = 1;
  }
  v7 = *(_QWORD *)(a1 + 16);
  if ( !v7 )
  {
    v8 = devOpenDatabase(&v13);
    if ( v8 )
    {
      DbgOutputTrace("RassrvCommitSettings: DevOpenDatabase failed!");
      return v8;
    }
    v7 = v13;
  }
  VpnEnable = devGetVpnEnable(v7, &v12);
  v8 = VpnEnable;
  if ( VpnEnable )
  {
    DbgOutputTrace("RassrvCommitSettings: devGetVpnEnable failed. Error %d", VpnEnable);
  }
  else
  {
    RasSrvIsICConfigured(&v11);
    if ( (v4 || !v11) && FIsUserAdmin() )
      FwRASGlobalPortOpenings(v12);
    *(_DWORD *)(a1 + 56) = 0;
    v11 = 1;
    RassrvICConfigAccess(1, (BYTE *)&v11);
  }
  return v8;
}

```

## disassembly

```asm
0x18002f0dc  push    rbx
0x18002f0de  push    rsi
0x18002f0df  push    rdi
0x18002f0e0  sub     rsp, 20h
0x18002f0e4  mov     rbx, rcx
0x18002f0e7  mov     [rsp+38h+arg_18], 0
0x18002f0f0  lea     rcx, aRassrvcommitse_3; "RassrvCommitSettings entered : %x"
0x18002f0f7  mov     [rsp+38h+arg_10], 0
0x18002f0ff  mov     [rsp+38h+arg_0], 0
0x18002f107  call    DbgOutputTrace
0x18002f10c  test    rbx, rbx
0x18002f10f  jz      loc_18002F21E
0x18002f115  mov     rcx, [rbx+18h]
0x18002f119  mov     esi, 1
0x18002f11e  test    rcx, rcx
0x18002f121  jz      short loc_18002F128
0x18002f123  call    usrFlushLocalDatabase
0x18002f128  mov     rcx, [rbx+10h]
0x18002f12c  test    rcx, rcx
0x18002f12f  jz      short loc_18002F142
0x18002f131  mov     eax, [rcx+18h]
0x18002f134  xor     esi, esi
0x18002f136  cmp     [rcx+14h], eax
0x18002f139  setnz   sil
0x18002f13d  call    devFlushDatabase
0x18002f142  mov     rcx, [rbx+28h]
0x18002f146  test    rcx, rcx
0x18002f149  jz      short loc_18002F150
0x18002f14b  call    miscFlushDatabase
0x18002f150  mov     rcx, [rbx+20h]
0x18002f154  test    rcx, rcx
0x18002f157  jz      short loc_18002F15E
0x18002f159  call    netDbFlush
0x18002f15e  cmp     qword ptr [rbx], 0
0x18002f162  jz      short loc_18002F18C
0x18002f164  lea     rcx, aRassrvcommitse_1; "RassrvCommitSettings: keep svc running."
0x18002f16b  call    DbgOutputTrace
0x18002f170  mov     rdx, cs:qword_180064998; lpString
0x18002f177  mov     rcx, [rbx]; hWnd
0x18002f17a  call    cs:__imp_GetPropW
0x18002f180  test    rax, rax
0x18002f183  jz      short loc_18002F18C
0x18002f185  mov     dword ptr [rax+8], 1
0x18002f18c  mov     rcx, [rbx+10h]
0x18002f190  test    rcx, rcx
0x18002f193  jnz     short loc_18002F1B8
0x18002f195  lea     rcx, [rsp+38h+arg_18]
0x18002f19a  call    devOpenDatabase
0x18002f19f  mov     edi, eax
0x18002f1a1  test    eax, eax
0x18002f1a3  jz      short loc_18002F1B3
0x18002f1a5  lea     rcx, aRassrvcommitse_2; "RassrvCommitSettings: DevOpenDatabase f"...
0x18002f1ac  call    DbgOutputTrace
0x18002f1b1  jmp     short loc_18002F22F
0x18002f1b3  mov     rcx, [rsp+38h+arg_18]
0x18002f1b8  lea     rdx, [rsp+38h+arg_10]
0x18002f1bd  call    devGetVpnEnable
0x18002f1c2  mov     edi, eax
0x18002f1c4  test    eax, eax
0x18002f1c6  jz      short loc_18002F1D8
0x18002f1c8  mov     edx, eax
0x18002f1ca  lea     rcx, aRassrvcommitse_0; "RassrvCommitSettings: devGetVpnEnable f"...
0x18002f1d1  call    DbgOutputTrace
0x18002f1d6  jmp     short loc_18002F22F
0x18002f1d8  lea     rcx, [rsp+38h+arg_0]
0x18002f1dd  call    RasSrvIsICConfigured
0x18002f1e2  test    esi, esi
0x18002f1e4  jnz     short loc_18002F1EC
0x18002f1e6  cmp     [rsp+38h+arg_0], esi
0x18002f1ea  jnz     short loc_18002F1FE
0x18002f1ec  call    FIsUserAdmin
0x18002f1f1  test    eax, eax
0x18002f1f3  jz      short loc_18002F1FE
0x18002f1f5  mov     ecx, [rsp+38h+arg_10]
0x18002f1f9  call    FwRASGlobalPortOpenings
0x18002f1fe  lea     rdx, [rsp+38h+arg_0]
0x18002f203  mov     dword ptr [rbx+38h], 0
0x18002f20a  mov     ecx, 1
0x18002f20f  mov     [rsp+38h+arg_0], 1
0x18002f217  call    RassrvICConfigAccess
0x18002f21c  jmp     short loc_18002F22F
0x18002f21e  lea     rcx, aRassrvcommitse; "RassrvCommitSettings: pvContext is NULL"
0x18002f225  call    DbgOutputTrace
0x18002f22a  mov     edi, 57h ; 'W'
0x18002f22f  mov     eax, edi
0x18002f231  add     rsp, 20h
0x18002f235  pop     rdi
0x18002f236  pop     rsi
0x18002f237  pop     rbx
0x18002f238  retn
```
