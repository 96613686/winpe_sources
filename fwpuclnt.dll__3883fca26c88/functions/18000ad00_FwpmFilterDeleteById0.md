# FwpmFilterDeleteById0

- ea: `0x18000ad00`
- end: `0x18000ade7`
- name: `FwpmFilterDeleteById0`
- size: `231`
- prototype: `DWORD __stdcall(HANDLE engineHandle, UINT64 id)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800034e0`
- `0x18000ad00`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ad39`
- `RPCRT4!NdrClientCall3` at `0x18000ad39`

## string_xrefs

- `0x18000ada8`: `FwpmFilterDeleteById0`
- `0x18000ad49`: `FwppProxyFilterDeleteById`
- `0x18000adb1`: `BfeRpcFilterDeleteById`

## pseudocode

```c
DWORD __stdcall FwpmFilterDeleteById0(HANDLE engineHandle, UINT64 id)
{
  __int64 v3; // rdx
  unsigned int Pointer; // eax
  const char *v5; // rdx
  __int64 v7; // rax
  DWORD v8; // edx
  __int64 v9; // r8

  if ( !engineHandle )
  {
    v9 = 2150760476LL;
    v5 = "FwpmFilterDeleteById0";
    goto LABEL_7;
  }
  v3 = *((_QWORD *)engineHandle + 14);
  if ( v3 )
  {
    Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, UINT64))(g_pBfeDirectDispatchTable + 40))(0, v3, id);
    if ( Pointer )
    {
      v5 = "BfeRpcFilterDeleteById";
      goto LABEL_14;
    }
    return 0;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x47u,
                            0,
                            *(_QWORD *)engineHandle,
                            *((_QWORD *)engineHandle + 1),
                            id).Pointer;
  if ( !Pointer )
    return 0;
  v5 = "FwppProxyFilterDeleteById";
LABEL_14:
  v9 = Pointer;
LABEL_7:
  v7 = WfpReportSysErrorAsWinError(engineHandle, v5, v9);
  if ( !v7 )
    return 0;
  v8 = (unsigned __int16)v7;
  if ( (v7 & 0x1FFF0000) != 0x70000 )
    v8 = v7;
  switch ( v8 )
  {
    case 0x6BFu:
    case 6u:
      return -2144206832;
    case 0x6C5u:
      return -2144206819;
    case 0x6EFu:
    case 0x6F4u:
      return -2144206820;
  }
  return v8;
}

```

## disassembly

```asm
0x18000ad00  sub     rsp, 38h
0x18000ad04  mov     r8, rdx
0x18000ad07  test    rcx, rcx
0x18000ad0a  jz      loc_18000ADA2
0x18000ad10  mov     rdx, [rcx+70h]
0x18000ad14  test    rdx, rdx
0x18000ad17  jnz     short loc_18000AD52
0x18000ad19  mov     rax, [rcx+8]
0x18000ad1d  mov     edx, 47h ; 'G'; nProcNum
0x18000ad22  mov     r9, [rcx]
0x18000ad25  lea     rcx, pProxyInfo; pProxyInfo
0x18000ad2c  mov     [rsp+38h+var_10], r8
0x18000ad31  xor     r8d, r8d; pReturnValue
0x18000ad34  mov     [rsp+38h+var_18], rax
0x18000ad39  call    cs:__imp_NdrClientCall3
0x18000ad40  nop     dword ptr [rax+rax+00h]
0x18000ad45  test    eax, eax
0x18000ad47  jz      short loc_18000AD68
0x18000ad49  lea     rdx, aFwppproxyfilte_1; "FwppProxyFilterDeleteById"
0x18000ad50  jmp     short loc_18000ADB8
0x18000ad52  mov     rax, cs:g_pBfeDirectDispatchTable
0x18000ad59  xor     ecx, ecx
0x18000ad5b  mov     rax, [rax+28h]
0x18000ad5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad64  test    eax, eax
0x18000ad66  jnz     short loc_18000ADB1
0x18000ad68  xor     eax, eax
0x18000ad6a  add     rsp, 38h
0x18000ad6e  retn
0x18000ad70  call    WfpReportSysErrorAsWinError
0x18000ad75  mov     rcx, rax
0x18000ad78  test    rax, rax
0x18000ad7b  jz      short loc_18000AD68
0x18000ad7d  mov     eax, ecx
0x18000ad7f  movzx   edx, cx
0x18000ad82  and     eax, 1FFF0000h
0x18000ad87  cmp     eax, 70000h
0x18000ad8c  cmovnz  edx, ecx
0x18000ad8f  cmp     edx, 6BFh
0x18000ad95  jnz     short loc_18000ADBD
0x18000ad97  mov     eax, 80320010h
0x18000ad9c  add     rsp, 38h
0x18000ada0  retn
0x18000ada2  mov     r8d, 8032001Ch
0x18000ada8  lea     rdx, aFwpmfilterdele_1; "FwpmFilterDeleteById0"
0x18000adaf  jmp     short loc_18000AD70
0x18000adb1  lea     rdx, aBferpcfilterde_0; "BfeRpcFilterDeleteById"
0x18000adb8  mov     r8d, eax
0x18000adbb  jmp     short loc_18000AD70
0x18000adbd  mov     eax, edx
0x18000adbf  sub     eax, 6
0x18000adc2  jz      short loc_18000AD97
0x18000adc4  sub     eax, 6BFh
0x18000adc9  jz      short loc_18000ADE0
0x18000adcb  sub     eax, 2Ah ; '*'
0x18000adce  jz      short loc_18000ADD9
0x18000add0  cmp     eax, 5
0x18000add3  jz      short loc_18000ADD9
0x18000add5  mov     eax, edx
0x18000add7  jmp     short loc_18000AD6A
0x18000add9  mov     eax, 8032001Ch
0x18000adde  jmp     short loc_18000AD6A
0x18000ade0  mov     eax, 8032001Dh
0x18000ade5  jmp     short loc_18000AD6A
```
