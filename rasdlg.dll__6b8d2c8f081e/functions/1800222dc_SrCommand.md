# SrCommand

- ea: `0x1800222dc`
- end: `0x1800223ab`
- name: `SrCommand`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800223c0`

## callees

- `0x1800222dc`
- `0x1800227f8`
- `0x180022940`
- `0x180039124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002236d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002236d`
- `rtutils!TracePrintfExA` at `0x180022304`
- `rtutils!TracePrintfExA` at `0x18002238d`
- `rtutils!TracePrintfExA` at `0x180022304`
- `rtutils!TracePrintfExA` at `0x18002238d`
- `SHELL32!InitNetworkAddressControl` at `0x18002232a`
- `SHELL32!InitNetworkAddressControl` at `0x18002232a`

## string_xrefs

- `0x1800222f8`: `SrCommand`
- `0x180022364`: `SrCommand failed to launch DialogBoxParam for DID_SR_StaticRoute: Error:%d`

## pseudocode

```c
__int64 __fastcall SrCommand(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  int v4; // edi
  __int64 v6; // rcx
  DWORD LastError; // eax
  DWORD v8; // eax

  v4 = a3;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "SrCommand");
  if ( v4 == 1693 )
  {
    if ( InitNetworkAddressControl() )
    {
      if ( (unsigned int)SHFusionDialogBoxParam(v6, 591, *(_QWORD *)(a1 + 48), SrAddDlgProc) == -1 )
      {
        LastError = GetLastError();
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "SrCommand failed to launch DialogBoxParam for DID_SR_StaticRoute: Error:%d",
            LastError);
      }
    }
    else
    {
      v8 = GetLastError();
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "InitNetworkAddressControl failed: Error:%d", v8);
    }
    SrRefresSRouteList(a1);
  }
  else
  {
    if ( v4 != 1694 )
      return 0;
    SrRemoveRoute(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x1800222dc  mov     [rsp+arg_0], rbx
0x1800222e1  push    rdi
0x1800222e2  sub     rsp, 30h
0x1800222e6  mov     rbx, rcx
0x1800222e9  movzx   edi, r8w
0x1800222ed  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800222f3  cmp     ecx, 0FFFFFFFFh
0x1800222f6  jz      short loc_18002230A
0x1800222f8  lea     r8, aSrcommand; "SrCommand"
0x1800222ff  mov     edx, 0Ch; dwFlags
0x180022304  call    cs:__imp_TracePrintfExA
0x18002230a  mov     edx, edi
0x18002230c  sub     edx, 69Dh
0x180022312  jz      short loc_18002232A
0x180022314  cmp     edx, 1
0x180022317  jz      short loc_180022320
0x180022319  xor     eax, eax
0x18002231b  jmp     loc_1800223A0
0x180022320  mov     rcx, rbx
0x180022323  call    SrRemoveRoute
0x180022328  jmp     short loc_18002239B
0x18002232a  call    cs:__imp_InitNetworkAddressControl
0x180022330  test    eax, eax
0x180022332  jz      short loc_18002236D
0x180022334  mov     r8, [rbx+30h]
0x180022338  lea     r9, SrAddDlgProc
0x18002233f  mov     edx, 24Fh
0x180022344  mov     [rsp+38h+var_18], rbx
0x180022349  call    SHFusionDialogBoxParam
0x18002234e  cmp     eax, 0FFFFFFFFh
0x180022351  jnz     short loc_180022393
0x180022353  call    cs:__imp_GetLastError
0x180022359  mov     ecx, cs:g_dwTraceId
0x18002235f  cmp     ecx, 0FFFFFFFFh
0x180022362  jz      short loc_180022393
0x180022364  lea     r8, aSrcommandFaile; "SrCommand failed to launch DialogBoxPar"...
0x18002236b  jmp     short loc_180022385
0x18002236d  call    cs:__imp_GetLastError
0x180022373  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180022379  cmp     ecx, 0FFFFFFFFh
0x18002237c  jz      short loc_180022393
0x18002237e  lea     r8, aInitnetworkadd_0; "InitNetworkAddressControl failed: Error"...
0x180022385  mov     r9d, eax
0x180022388  mov     edx, 0Ch; dwFlags
0x18002238d  call    cs:__imp_TracePrintfExA
0x180022393  mov     rcx, rbx
0x180022396  call    SrRefresSRouteList
0x18002239b  mov     eax, 1
0x1800223a0  mov     rbx, [rsp+38h+arg_0]
0x1800223a5  add     rsp, 30h
0x1800223a9  pop     rdi
0x1800223aa  retn
```
