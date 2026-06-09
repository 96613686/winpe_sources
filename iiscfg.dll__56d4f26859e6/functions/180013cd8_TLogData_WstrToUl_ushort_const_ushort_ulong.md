# TLogData::WstrToUl(ushort const *,ushort,ulong *)

- ea: `0x180013cd8`
- end: `0x180013d6d`
- name: `?WstrToUl@TLogData@@AEAA_NPEBGGPEAK@Z`
- size: `149`
- prototype: `char __fastcall(TLogData *this, const unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012b68`
- `0x180013140`

## callees

- `0x180013cd8`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180013d59`
- `IisRTL!PuDbgPrint` at `0x180013d59`

## string_xrefs

- `0x180013d4d`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`

## pseudocode

```c
char __fastcall TLogData::WstrToUl(TLogData *this, const unsigned __int16 *a2, __int64 a3, unsigned int *a4)
{
  __int64 v4; // rcx
  __int64 v5; // rax

  v4 = 0;
  while ( *a2 && *a2 != 46 )
  {
    v5 = (unsigned int)*a2 - 48;
    if ( (unsigned int)v5 > 9 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
          69,
          "TLogData::WstrToUl",
          "[WstrToUl] Invalid char encountered\n");
      return 0;
    }
    v4 = v5 + 10 * v4;
    if ( v4 > 0xFFFFFFFFLL )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
          76,
          "TLogData::WstrToUl",
          "[WstrToUl] Number is too big\n");
      return 0;
    }
    ++a2;
  }
  *a4 = v4;
  return 1;
}

```

## disassembly

```asm
0x180013cd8  sub     rsp, 38h
0x180013cdc  xor     r8d, r8d
0x180013cdf  mov     ecx, r8d
0x180013ce2  cmp     [rdx], r8w
0x180013ce6  jz      short loc_180013D63
0x180013ce8  cmp     word ptr [rdx], 2Eh ; '.'
0x180013cec  jz      short loc_180013D63
0x180013cee  movzx   eax, word ptr [rdx]
0x180013cf1  add     eax, 0FFFFFFD0h
0x180013cf4  cmp     eax, 9
0x180013cf7  ja      short loc_180013D29
0x180013cf9  lea     rcx, [rcx+rcx*4]
0x180013cfd  lea     rcx, [rax+rcx*2]
0x180013d01  mov     eax, 0FFFFFFFFh
0x180013d06  cmp     rcx, rax
0x180013d09  jg      short loc_180013D11
0x180013d0b  add     rdx, 2
0x180013d0f  jmp     short loc_180013CE2
0x180013d11  test    byte ptr cs:g_dwDebugFlags, 3
0x180013d18  jz      short loc_180013D5F
0x180013d1a  lea     rax, aWstrtoulNumber; "[WstrToUl] Number is too big\n"
0x180013d21  mov     r8d, 4Ch ; 'L'
0x180013d27  jmp     short loc_180013D3F
0x180013d29  test    byte ptr cs:g_dwDebugFlags, 3
0x180013d30  jz      short loc_180013D5F
0x180013d32  lea     rax, aWstrtoulInvali; "[WstrToUl] Invalid char encountered\n"
0x180013d39  mov     r8d, 45h ; 'E'
0x180013d3f  mov     rcx, cs:g_pDebug
0x180013d46  lea     r9, aTlogdataWstrto; "TLogData::WstrToUl"
0x180013d4d  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x180013d54  mov     [rsp+38h+var_18], rax
0x180013d59  call    cs:__imp_PuDbgPrint
0x180013d5f  xor     al, al
0x180013d61  jmp     short loc_180013D68
0x180013d63  mov     [r9], ecx
0x180013d66  mov     al, 1
0x180013d68  add     rsp, 38h
0x180013d6c  retn
```
