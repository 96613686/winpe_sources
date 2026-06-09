# FwpmFilterDeleteByKey0

- ea: `0x18000c9d0`
- end: `0x18000cb39`
- name: `FwpmFilterDeleteByKey0`
- size: `361`
- prototype: `DWORD __stdcall(HANDLE engineHandle, const GUID *key)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800034e0`
- `0x18000c9d0`
- `0x18000e898`
- `0x18003b2c8`
- `0x18004b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000ca09`
- `RPCRT4!NdrClientCall3` at `0x18000ca09`

## string_xrefs

- `0x18000ca8e`: `FwpmFilterDeleteByKey0`
- `0x18000caf6`: `FwppProxyFilterDeleteByKey`
- `0x18000ca3b`: `BfeRpcFilterDeleteByKey`

## pseudocode

```c
DWORD __stdcall FwpmFilterDeleteByKey0(HANDLE engineHandle, const GUID *key)
{
  __int64 v3; // rdx
  unsigned int Pointer; // eax
  CLIENT_CALL_RETURN v5; // rcx
  const char *v7; // rdx
  __int64 v8; // rax
  int v9; // ecx
  DWORD v10; // edx
  void *v11; // rcx

  if ( engineHandle )
  {
    v3 = *((_QWORD *)engineHandle + 14);
    if ( v3 )
    {
      Pointer = (*(__int64 (__fastcall **)(_QWORD, __int64, const GUID *))(g_pBfeDirectDispatchTable + 64))(0, v3, key);
      if ( !Pointer )
        return 0;
      v7 = "BfeRpcFilterDeleteByKey";
    }
    else
    {
      Pointer = (unsigned int)NdrClientCall3(
                                (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                                0x48u,
                                0,
                                *(_QWORD *)engineHandle,
                                *((_QWORD *)engineHandle + 1),
                                key).Pointer;
      if ( !Pointer )
        return 0;
      v7 = "FwppProxyFilterDeleteByKey";
    }
    v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))WfpReportSysErrorAsWinError)(
           (CLIENT_CALL_RETURN)v5.Simple,
           v7,
           Pointer);
    v9 = v8;
    if ( !v8 )
      return 0;
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (_DWORD)key,
        0,
        (__int64)"FwpmFilterDeleteByKey0",
        -2144206820);
    }
    if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v11, key, "FwpmFilterDeleteByKey0", 2150760476LL);
    v9 = -2144206820;
  }
  v10 = (unsigned __int16)v9;
  if ( (v9 & 0x1FFF0000) != 0x70000 )
    v10 = v9;
  switch ( v10 )
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
  return v10;
}

```

## disassembly

```asm
0x18000c9d0  sub     rsp, 38h
0x18000c9d4  mov     r8, rdx
0x18000c9d7  test    rcx, rcx
0x18000c9da  jz      loc_18000CA7B
0x18000c9e0  mov     rdx, [rcx+70h]
0x18000c9e4  test    rdx, rdx
0x18000c9e7  jnz     short loc_18000CA25
0x18000c9e9  mov     rax, [rcx+8]
0x18000c9ed  mov     edx, 48h ; 'H'; nProcNum
0x18000c9f2  mov     r9, [rcx]
0x18000c9f5  lea     rcx, pProxyInfo; pProxyInfo
0x18000c9fc  mov     [rsp+38h+var_10], r8
0x18000ca01  xor     r8d, r8d; pReturnValue
0x18000ca04  mov     [rsp+38h+var_18], rax
0x18000ca09  call    cs:__imp_NdrClientCall3
0x18000ca10  nop     dword ptr [rax+rax+00h]
0x18000ca15  test    eax, eax
0x18000ca17  jnz     loc_18000CAF6
0x18000ca1d  xor     eax, eax
0x18000ca1f  add     rsp, 38h
0x18000ca23  retn
0x18000ca25  mov     rax, cs:g_pBfeDirectDispatchTable
0x18000ca2c  xor     ecx, ecx
0x18000ca2e  mov     rax, [rax+40h]
0x18000ca32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca37  test    eax, eax
0x18000ca39  jz      short loc_18000CA1D
0x18000ca3b  lea     rdx, aBferpcfilterde; "BfeRpcFilterDeleteByKey"
0x18000ca42  mov     r8d, eax
0x18000ca45  call    WfpReportSysErrorAsWinError
0x18000ca4a  mov     rcx, rax
0x18000ca4d  test    rax, rax
0x18000ca50  jz      short loc_18000CA1D
0x18000ca52  mov     eax, ecx
0x18000ca54  movzx   edx, cx
0x18000ca57  and     eax, 1FFF0000h
0x18000ca5c  cmp     eax, 70000h
0x18000ca61  cmovnz  edx, ecx
0x18000ca64  cmp     edx, 6BFh
0x18000ca6a  jnz     loc_18000CB02
0x18000ca70  mov     eax, 80320010h
0x18000ca75  add     rsp, 38h
0x18000ca79  retn
0x18000ca7b  mov     [rsp+38h+var_8], rbx
0x18000ca80  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca87  lea     rax, WPP_GLOBAL_Control
0x18000ca8e  lea     rbx, aFwpmfilterdele_2; "FwpmFilterDeleteByKey0"
0x18000ca95  cmp     rcx, rax
0x18000ca98  jz      short loc_18000CAA0
0x18000ca9a  cmp     byte ptr [rcx+19h], 2
0x18000ca9e  jnb     short loc_18000CAC0
0x18000caa0  cmp     cs:gWfpLogUserModeErrors, 0
0x18000caa7  jz      short loc_18000CAB2
0x18000caa9  test    cs:byte_18007C665, 1
0x18000cab0  jnz     short loc_18000CAE6
0x18000cab2  mov     rbx, [rsp+38h+var_8]
0x18000cab7  mov     rcx, 0FFFFFFFF8032001Ch
0x18000cabe  jmp     short loc_18000CA52
0x18000cac0  test    byte ptr [rcx+1Ch], 1
0x18000cac4  jz      short loc_18000CAA0
0x18000cac6  mov     rcx, [rcx+10h]
0x18000caca  mov     edx, 17h
0x18000cacf  mov     dword ptr [rsp+38h+var_10], 8032001Ch
0x18000cad7  xor     r9d, r9d
0x18000cada  mov     [rsp+38h+var_18], rbx
0x18000cadf  call    WPP_SF_Ssd
0x18000cae4  jmp     short loc_18000CAA0
0x18000cae6  mov     r9d, 8032001Ch
0x18000caec  mov     r8, rbx
0x18000caef  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000caf4  jmp     short loc_18000CAB2
0x18000caf6  lea     rdx, aFwppproxyfilte; "FwppProxyFilterDeleteByKey"
0x18000cafd  jmp     loc_18000CA42
0x18000cb02  mov     eax, edx
0x18000cb04  sub     eax, 6
0x18000cb07  jz      loc_18000CA70
0x18000cb0d  sub     eax, 6BFh
0x18000cb12  jz      short loc_18000CB2F
0x18000cb14  sub     eax, 2Ah ; '*'
0x18000cb17  jz      short loc_18000CB25
0x18000cb19  cmp     eax, 5
0x18000cb1c  jz      short loc_18000CB25
0x18000cb1e  mov     eax, edx
0x18000cb20  jmp     loc_18000CA1F
0x18000cb25  mov     eax, 8032001Ch
0x18000cb2a  jmp     loc_18000CA1F
0x18000cb2f  mov     eax, 8032001Dh
0x18000cb34  jmp     loc_18000CA1F
```
