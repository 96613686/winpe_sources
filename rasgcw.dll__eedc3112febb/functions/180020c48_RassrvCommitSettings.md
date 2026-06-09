# RassrvCommitSettings

- ea: `0x180020c48`
- end: `0x180020dc0`
- name: `RassrvCommitSettings`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f680`
- `0x180020670`

## callees

- `0x180020b80`
- `0x180020c48`
- `0x180020e0c`
- `0x180026710`
- `0x180026a24`
- `0x180026f44`
- `0x180027e84`
- `0x180028120`
- `0x180028164`
- `0x1800283bc`
- `0x180028f8c`
- `0x18002b204`

## import_xrefs

- `USER32!GetPropW` at `0x180020ce2`
- `USER32!GetPropW` at `0x180020ce2`

## string_xrefs

- `0x180020ccc`: `RassrvCommitSettings: keep svc running.`
- `0x180020c60`: `RassrvCommitSettings entered : %x`
- `0x180020d35`: `RassrvCommitSettings: devGetVpnEnable failed. Error %d`
- `0x180020d0d`: `RassrvCommitSettings: DevOpenDatabase failed!`
- `0x180020da0`: `RassrvCommitSettings: pvContext is NULL`

## pseudocode

```c
__int64 __fastcall RassrvCommitSettings(__int64 a1, int a2)
{
  __int64 v3; // rcx
  BOOL v4; // ebp
  __int64 v5; // rcx
  _DWORD *PropW; // rax
  __int64 v7; // rcx
  unsigned int v8; // edi
  int VpnEnable; // eax
  int v10; // esi
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = 0;
  v13 = 0;
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
    PropW = GetPropW(*(HWND *)a1, lpString);
    if ( PropW )
      PropW[2] = 1;
  }
  v7 = *(_QWORD *)(a1 + 16);
  if ( !v7 )
  {
    v8 = devOpenDatabase(&v12);
    if ( v8 )
    {
      DbgOutputTrace("RassrvCommitSettings: DevOpenDatabase failed!");
      return v8;
    }
    v7 = v12;
  }
  VpnEnable = devGetVpnEnable(v7, &v13);
  v8 = VpnEnable;
  if ( VpnEnable )
  {
    DbgOutputTrace("RassrvCommitSettings: devGetVpnEnable failed. Error %d", VpnEnable);
  }
  else
  {
    v10 = 0;
    LODWORD(v12) = 0;
    RasSrvUiInit();
    if ( !(unsigned int)RassrvICConfigAccess(0, (BYTE *)&v12) )
      LOBYTE(v10) = (_DWORD)v12 != 0;
    if ( (v4 || !v10) && FIsUserAdmin() )
      FwRASGlobalPortOpenings(v13);
    *(_DWORD *)(a1 + 56) = 0;
    LODWORD(v12) = 1;
    RassrvICConfigAccess(1, (BYTE *)&v12);
  }
  return v8;
}

```

## disassembly

```asm
0x180020c48  mov     [rsp+arg_8], rbx
0x180020c4d  push    rbp
0x180020c4e  push    rsi
0x180020c4f  push    rdi
0x180020c50  sub     rsp, 20h
0x180020c54  mov     rbx, rcx
0x180020c57  mov     [rsp+38h+arg_0], 0
0x180020c60  lea     rcx, aRassrvcommitse_4; "RassrvCommitSettings entered : %x"
0x180020c67  mov     [rsp+38h+arg_10], 0
0x180020c6f  call    DbgOutputTrace
0x180020c74  test    rbx, rbx
0x180020c77  jz      loc_180020DA0
0x180020c7d  mov     rcx, [rbx+18h]
0x180020c81  mov     ebp, 1
0x180020c86  test    rcx, rcx
0x180020c89  jz      short loc_180020C90
0x180020c8b  call    usrFlushLocalDatabase
0x180020c90  mov     rcx, [rbx+10h]
0x180020c94  test    rcx, rcx
0x180020c97  jz      short loc_180020CAA
0x180020c99  mov     eax, [rcx+18h]
0x180020c9c  xor     ebp, ebp
0x180020c9e  cmp     [rcx+14h], eax
0x180020ca1  setnz   bpl
0x180020ca5  call    devFlushDatabase
0x180020caa  mov     rcx, [rbx+28h]
0x180020cae  test    rcx, rcx
0x180020cb1  jz      short loc_180020CB8
0x180020cb3  call    miscFlushDatabase
0x180020cb8  mov     rcx, [rbx+20h]
0x180020cbc  test    rcx, rcx
0x180020cbf  jz      short loc_180020CC6
0x180020cc1  call    netDbFlush
0x180020cc6  cmp     qword ptr [rbx], 0
0x180020cca  jz      short loc_180020CF4
0x180020ccc  lea     rcx, aRassrvcommitse_1; "RassrvCommitSettings: keep svc running."
0x180020cd3  call    DbgOutputTrace
0x180020cd8  mov     rdx, cs:lpString; lpString
0x180020cdf  mov     rcx, [rbx]; hWnd
0x180020ce2  call    cs:__imp_GetPropW
0x180020ce8  test    rax, rax
0x180020ceb  jz      short loc_180020CF4
0x180020ced  mov     dword ptr [rax+8], 1
0x180020cf4  mov     rcx, [rbx+10h]
0x180020cf8  test    rcx, rcx
0x180020cfb  jnz     short loc_180020D23
0x180020cfd  lea     rcx, [rsp+38h+arg_0]
0x180020d02  call    devOpenDatabase
0x180020d07  mov     edi, eax
0x180020d09  test    eax, eax
0x180020d0b  jz      short loc_180020D1E
0x180020d0d  lea     rcx, aRassrvcommitse_3; "RassrvCommitSettings: DevOpenDatabase f"...
0x180020d14  call    DbgOutputTrace
0x180020d19  jmp     loc_180020DB1
0x180020d1e  mov     rcx, [rsp+38h+arg_0]
0x180020d23  lea     rdx, [rsp+38h+arg_10]
0x180020d28  call    devGetVpnEnable
0x180020d2d  mov     edi, eax
0x180020d2f  test    eax, eax
0x180020d31  jz      short loc_180020D43
0x180020d33  mov     edx, eax
0x180020d35  lea     rcx, aRassrvcommitse_0; "RassrvCommitSettings: devGetVpnEnable f"...
0x180020d3c  call    DbgOutputTrace
0x180020d41  jmp     short loc_180020DB1
0x180020d43  xor     esi, esi
0x180020d45  mov     dword ptr [rsp+38h+arg_0], esi
0x180020d49  call    RasSrvUiInit
0x180020d4e  lea     rdx, [rsp+38h+arg_0]
0x180020d53  xor     ecx, ecx
0x180020d55  call    RassrvICConfigAccess
0x180020d5a  test    eax, eax
0x180020d5c  jnz     short loc_180020D66
0x180020d5e  cmp     dword ptr [rsp+38h+arg_0], esi
0x180020d62  setnbe  sil
0x180020d66  test    ebp, ebp
0x180020d68  jnz     short loc_180020D6E
0x180020d6a  test    esi, esi
0x180020d6c  jnz     short loc_180020D80
0x180020d6e  call    FIsUserAdmin
0x180020d73  test    eax, eax
0x180020d75  jz      short loc_180020D80
0x180020d77  mov     ecx, [rsp+38h+arg_10]
0x180020d7b  call    FwRASGlobalPortOpenings
0x180020d80  lea     rdx, [rsp+38h+arg_0]
0x180020d85  mov     dword ptr [rbx+38h], 0
0x180020d8c  mov     ecx, 1
0x180020d91  mov     dword ptr [rsp+38h+arg_0], 1
0x180020d99  call    RassrvICConfigAccess
0x180020d9e  jmp     short loc_180020DB1
0x180020da0  lea     rcx, aRassrvcommitse; "RassrvCommitSettings: pvContext is NULL"
0x180020da7  call    DbgOutputTrace
0x180020dac  mov     edi, 57h ; 'W'
0x180020db1  mov     rbx, [rsp+38h+arg_8]
0x180020db6  mov     eax, edi
0x180020db8  add     rsp, 20h
0x180020dbc  pop     rdi
0x180020dbd  pop     rsi
0x180020dbe  pop     rbp
0x180020dbf  retn
```
