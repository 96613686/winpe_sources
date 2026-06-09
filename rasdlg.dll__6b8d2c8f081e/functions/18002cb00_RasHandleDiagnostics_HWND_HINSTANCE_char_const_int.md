# RasHandleDiagnostics(HWND__ *,HINSTANCE__ *,char const *,int)

- ea: `0x18002cb00`
- end: `0x18002cc56`
- name: `?RasHandleDiagnostics@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@Z`
- size: `342`
- prototype: `void __fastcall(HWND, HINSTANCE, const char *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002cb00`
- `0x180039c3c`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `msvcrt!sscanf_s` at `0x18002cb9c`
- `msvcrt!sscanf_s` at `0x18002cb9c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002cbef`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002cbef`
- `rtutils!TracePrintfExA` at `0x18002cb5a`
- `rtutils!TracePrintfExA` at `0x18002cbc1`
- `rtutils!TracePrintfExA` at `0x18002cbe1`
- `rtutils!TracePrintfExA` at `0x18002cc38`
- `rtutils!TracePrintfExA` at `0x18002cb5a`
- `rtutils!TracePrintfExA` at `0x18002cbc1`
- `rtutils!TracePrintfExA` at `0x18002cbe1`
- `rtutils!TracePrintfExA` at `0x18002cc38`

## string_xrefs

- `0x18002cc2f`: `HandleRasDiagnostics: CLSIDFromString failed`

## pseudocode

```c
void __fastcall RasHandleDiagnostics(HWND a1, HINSTANCE a2, const char *a3)
{
  DWORD v4; // ecx
  int v5; // eax
  unsigned int started; // eax
  GUID v7; // [rsp+40h] [rbp-49h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-29h] BYREF

  memset_0(sz, 0, sizeof(sz));
  v4 = g_dwTraceId;
  pclsid = 0;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "RasHandleDiagnostics");
    v4 = g_dwTraceId;
  }
  if ( a3 )
  {
    v5 = sscanf_s(a3, "%S %u", sz, 80);
    if ( v5 >= 2 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "HandleRasDiagnostics: For connection with GUID %S and error %d", sz, 0);
      if ( CLSIDFromString(sz, &pclsid) < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "HandleRasDiagnostics: CLSIDFromString failed");
      }
      else
      {
        v7 = pclsid;
        started = StartDiagnosis((__int128 *)&v7, 0);
        if ( started && g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "HandleRasDiagnostics: StartDiagnosis failed with %d", started);
      }
    }
    else if ( g_dwTraceId != -1 )
    {
      TracePrintfExA(g_dwTraceId, 0xCu, "HandleRasDiagnostics: sscanf_s returned %d arguments", (unsigned int)v5);
    }
  }
  else if ( v4 != -1 )
  {
    TracePrintfExA(v4, 0xCu, "HandleRasDiagnostics: Invalid CmdLine buffer");
  }
}

```

## disassembly

```asm
0x18002cb00  push    rbp
0x18002cb02  push    rbx
0x18002cb03  push    rsi
0x18002cb04  push    rdi
0x18002cb05  lea     rbp, [rsp-3Fh]
0x18002cb0a  sub     rsp, 0C8h
0x18002cb11  mov     rax, cs:__security_cookie
0x18002cb18  xor     rax, rsp
0x18002cb1b  mov     [rbp+57h+var_30], rax
0x18002cb1f  xor     edx, edx; Val
0x18002cb21  lea     rcx, [rbp+57h+sz]; void *
0x18002cb25  mov     rbx, r8
0x18002cb28  lea     r8d, [rdx+50h]; Size
0x18002cb2c  call    memset_0
0x18002cb31  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002cb37  or      edi, 0FFFFFFFFh
0x18002cb3a  mov     [rbp+57h+var_B0], 0
0x18002cb41  xorps   xmm0, xmm0
0x18002cb44  mov     esi, 0Ch
0x18002cb49  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18002cb4d  cmp     ecx, edi
0x18002cb4f  jz      short loc_18002CB66
0x18002cb51  lea     r8, aRashandlediagn_0; "RasHandleDiagnostics"
0x18002cb58  mov     edx, esi; dwFlags
0x18002cb5a  call    cs:__imp_TracePrintfExA
0x18002cb60  mov     ecx, cs:g_dwTraceId
0x18002cb66  test    rbx, rbx
0x18002cb69  jnz     short loc_18002CB7F
0x18002cb6b  cmp     ecx, edi
0x18002cb6d  jz      loc_18002CC3E
0x18002cb73  lea     r8, aHandlerasdiagn_3; "HandleRasDiagnostics: Invalid CmdLine b"...
0x18002cb7a  jmp     loc_18002CC36
0x18002cb7f  lea     rax, [rbp+57h+var_B0]
0x18002cb83  mov     r9d, 50h ; 'P'
0x18002cb89  lea     r8, [rbp+57h+sz]
0x18002cb8d  mov     [rsp+0E0h+var_C0], rax
0x18002cb92  lea     rdx, aSU; "%S %u"
0x18002cb99  mov     rcx, rbx; Buffer
0x18002cb9c  call    cs:__imp_sscanf_s
0x18002cba2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002cba8  cmp     eax, 2
0x18002cbab  jge     short loc_18002CBC9
0x18002cbad  cmp     ecx, edi
0x18002cbaf  jz      loc_18002CC3E
0x18002cbb5  lea     r8, aHandlerasdiagn_2; "HandleRasDiagnostics: sscanf_s returned"...
0x18002cbbc  mov     r9d, eax
0x18002cbbf  mov     edx, esi; dwFlags
0x18002cbc1  call    cs:__imp_TracePrintfExA
0x18002cbc7  jmp     short loc_18002CC3E
0x18002cbc9  cmp     ecx, edi
0x18002cbcb  jz      short loc_18002CBE7
0x18002cbcd  mov     eax, [rbp+57h+var_B0]
0x18002cbd0  lea     r9, [rbp+57h+sz]
0x18002cbd4  lea     r8, aHandlerasdiagn_0; "HandleRasDiagnostics: For connection wi"...
0x18002cbdb  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18002cbdf  mov     edx, esi; dwFlags
0x18002cbe1  call    cs:__imp_TracePrintfExA
0x18002cbe7  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18002cbeb  lea     rcx, [rbp+57h+sz]; lpsz
0x18002cbef  call    cs:__imp_CLSIDFromString
0x18002cbf5  test    eax, eax
0x18002cbf7  js      short loc_18002CC25
0x18002cbf9  movaps  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18002cbfd  lea     rcx, [rbp+57h+var_A0]
0x18002cc01  mov     edx, [rbp+57h+var_B0]
0x18002cc04  movdqa  [rbp+57h+var_A0], xmm0
0x18002cc09  call    StartDiagnosis
0x18002cc0e  test    eax, eax
0x18002cc10  jz      short loc_18002CC3E
0x18002cc12  mov     ecx, cs:g_dwTraceId
0x18002cc18  cmp     ecx, edi
0x18002cc1a  jz      short loc_18002CC3E
0x18002cc1c  lea     r8, aHandlerasdiagn; "HandleRasDiagnostics: StartDiagnosis fa"...
0x18002cc23  jmp     short loc_18002CBBC
0x18002cc25  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002cc2b  cmp     ecx, edi
0x18002cc2d  jz      short loc_18002CC3E
0x18002cc2f  lea     r8, aHandlerasdiagn_1; "HandleRasDiagnostics: CLSIDFromString f"...
0x18002cc36  mov     edx, esi; dwFlags
0x18002cc38  call    cs:__imp_TracePrintfExA
0x18002cc3e  mov     rcx, [rbp+57h+var_30]
0x18002cc42  xor     rcx, rsp; StackCookie
0x18002cc45  call    __security_check_cookie
0x18002cc4a  add     rsp, 0C8h
0x18002cc51  pop     rdi
0x18002cc52  pop     rsi
0x18002cc53  pop     rbx
0x18002cc54  pop     rbp
0x18002cc55  retn
```
