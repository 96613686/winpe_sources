# GetServerVariable(void *,char *,void *,ulong *)

- ea: `0x1800034c0`
- end: `0x18000373c`
- name: `?GetServerVariable@@YAHPEAXPEAD0PEAK@Z`
- size: `636`
- prototype: `__int64 __fastcall(_QWORD *, char *, unsigned __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800033a0`
- `0x1800034c0`
- `0x180005ed0`
- `0x180013010`

## import_xrefs

- `msvcrt!_strnicmp` at `0x180003675`
- `msvcrt!_strnicmp` at `0x180003675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003727`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003727`
- `iisutil!PuDbgPrint` at `0x180003536`
- `iisutil!PuDbgPrint` at `0x1800035a5`
- `iisutil!PuDbgPrint` at `0x180003640`
- `iisutil!PuDbgPrint` at `0x1800036ce`
- `iisutil!PuDbgPrint` at `0x18000371c`
- `iisutil!PuDbgPrint` at `0x180003536`
- `iisutil!PuDbgPrint` at `0x1800035a5`
- `iisutil!PuDbgPrint` at `0x180003640`
- `iisutil!PuDbgPrint` at `0x1800036ce`
- `iisutil!PuDbgPrint` at `0x18000371c`

## string_xrefs

- `0x1800034ec`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\w3isapi.cxx`
- `0x1800036f5`: `\n  GetServerVariable[%p]: Parameter validation failure\n    Variable Name: %s\n    Buffer Size Ptr: %p\n    Returing FALSE, LastError=ERROR_INVALID_PARAMETER\n  <END>\n\n`

## pseudocode

```c
__int64 __fastcall GetServerVariable(_QWORD *a1, char *a2, unsigned __int64 a3, unsigned int *a4)
{
  int v4; // r11d
  __int64 (__fastcall ***v9)(_QWORD, char *, unsigned __int64, __int64, unsigned int *); // rcx
  __int64 v10; // r9
  bool v11; // cf
  int v12; // esi
  ISAPI_CONTEXT *v13; // rcx
  unsigned int v14; // eax
  DWORD v15; // ecx
  void *v17; // [rsp+80h] [rbp+8h] BYREF

  v4 = g_dwDebugFlags;
  v17 = 0;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x1000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
      478,
      "GetServerVariable",
      "\r\n  GetServerVariable[%p]: Function Entry\r\n    Variable Name: %s\r\n  <END>\r\n\r\n",
      a1,
      a2);
    v4 = g_dwDebugFlags;
  }
  if ( !a1 || !a2 || !a4 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        500,
        "GetServerVariable",
        "\r\n"
        "  GetServerVariable[%p]: Parameter validation failure\r\n"
        "    Variable Name: %s\r\n"
        "    Buffer Size Ptr: %p\r\n"
        "    Returing FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
        "  <END>\r\n"
        "\r\n",
        a1,
        a2,
        a4);
    goto LABEL_24;
  }
  v9 = (__int64 (__fastcall ***)(_QWORD, char *, unsigned __int64, __int64, unsigned int *))a1[24];
  if ( !v9 )
  {
    if ( (v4 & 3) != 0 && (v4 & 0x100000) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        518,
        "GetServerVariable",
        "\r\n"
        "  GetServerVariable[%p]: Failed to get interface to server core\r\n"
        "    Returning FALSE, LastError=ERROR_INVALID_PARAMETER\r\n"
        "  <END>\r\n"
        "\r\n",
        a1);
LABEL_24:
    v15 = 87;
LABEL_25:
    SetLastError(v15);
    return 0;
  }
  if ( !a3 )
    *a4 = 0;
  v10 = *a4;
  v11 = *a4 != 0;
  v17 = 0;
  v12 = (**v9)(v9, a2, a3 & -(__int64)v11, v10, a4);
  ISAPI_CONTEXT::IsapiUndoRevertHack(v13, &v17);
  if ( v12 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    {
      v14 = WIN32_FROM_HRESULT(v12);
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        562,
        "GetServerVariable",
        "\r\n  GetServerVariable[%p]: Failed\r\n    Returning FALSE, LastError=0x%08x (%d)\r\n  <END>\r\n\r\n",
        a1,
        v12,
        v14);
    }
    v15 = WIN32_FROM_HRESULT(v12);
    goto LABEL_25;
  }
  if ( (g_dwDebugFlags & 0x1200000) == 0x1200000 )
  {
    if ( !_strnicmp(a2, "UNICODE_", 8u) )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
          583,
          "GetServerVariable",
          "\r\n  GetServerVariable[%p]: Succeeded\r\n    %s value: '%S'\r\n    Returning TRUE\r\n  <END>\r\n\r\n",
          a1,
          a2,
          a3);
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\w3isapi.cxx",
        595,
        "GetServerVariable",
        "\r\n  GetServerVariable[%p]: Succeeded\r\n    %s value: '%s'\r\n    Returning TRUE\r\n  <END>\r\n\r\n",
        a1,
        a2,
        a3);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800034c0  mov     rax, rsp
0x1800034c3  push    rbx
0x1800034c4  push    rbp
0x1800034c5  push    rsi
0x1800034c6  push    rdi
0x1800034c7  push    r12
0x1800034c9  push    r13
0x1800034cb  sub     rsp, 48h
0x1800034cf  mov     r11d, cs:g_dwDebugFlags
0x1800034d6  lea     r12, aGetservervaria; "GetServerVariable"
0x1800034dd  test    r11b, 3
0x1800034e1  mov     qword ptr [rax+8], 0
0x1800034e9  mov     rsi, r9
0x1800034ec  lea     r13, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800034f3  setnz   r10b
0x1800034f7  mov     rbp, r8
0x1800034fa  bt      r11d, 18h
0x1800034ff  mov     rdi, rdx
0x180003502  mov     rbx, rcx
0x180003505  setb    al
0x180003508  test    al, r10b
0x18000350b  jz      short loc_180003543
0x18000350d  mov     [rsp+78h+var_48], rdx
0x180003512  lea     rax, aGetservervaria_0; "\r\n  GetServerVariable[%p]: Function E"...
0x180003519  mov     [rsp+78h+var_50], rcx
0x18000351e  mov     r9, r12
0x180003521  mov     rcx, cs:g_pDebug
0x180003528  mov     r8d, 1DEh
0x18000352e  mov     rdx, r13
0x180003531  mov     [rsp+78h+var_58], rax
0x180003536  call    cs:__imp_PuDbgPrint
0x18000353c  mov     r11d, cs:g_dwDebugFlags
0x180003543  test    rbx, rbx
0x180003546  jz      loc_1800036DB
0x18000354c  test    rdi, rdi
0x18000354f  jz      loc_1800036DB
0x180003555  test    rsi, rsi
0x180003558  jz      loc_1800036DB
0x18000355e  mov     rcx, [rbx+0C0h]
0x180003565  test    rcx, rcx
0x180003568  jnz     short loc_1800035B0
0x18000356a  test    r11b, 3
0x18000356e  setnz   cl
0x180003571  bt      r11d, 14h
0x180003576  setb    al
0x180003579  test    al, cl
0x18000357b  jz      loc_180003722
0x180003581  mov     rcx, cs:g_pDebug
0x180003588  lea     rax, aGetservervaria_4; "\r\n  GetServerVariable[%p]: Failed to "...
0x18000358f  mov     [rsp+78h+var_50], rbx
0x180003594  mov     r9, r12
0x180003597  mov     r8d, 206h
0x18000359d  mov     [rsp+78h+var_58], rax
0x1800035a2  mov     rdx, r13
0x1800035a5  call    cs:__imp_PuDbgPrint
0x1800035ab  jmp     loc_180003722
0x1800035b0  test    rbp, rbp
0x1800035b3  jnz     short loc_1800035B7
0x1800035b5  mov     [rsi], ebp
0x1800035b7  mov     eax, [rsi]
0x1800035b9  mov     r9d, [rsi]
0x1800035bc  neg     eax
0x1800035be  mov     [rsp+78h+arg_0], 0
0x1800035ca  mov     rdx, [rcx]
0x1800035cd  sbb     r8, r8
0x1800035d0  and     r8, rbp
0x1800035d3  mov     [rsp+78h+var_58], rsi
0x1800035d8  mov     rax, [rdx]
0x1800035db  mov     rdx, rdi
0x1800035de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e3  lea     rdx, [rsp+78h+arg_0]; void **
0x1800035eb  mov     esi, eax
0x1800035ed  call    ?IsapiUndoRevertHack@ISAPI_CONTEXT@@QEAAXPEAPEAX@Z; ISAPI_CONTEXT::IsapiUndoRevertHack(void * *)
0x1800035f2  test    esi, esi
0x1800035f4  jns     short loc_180003654
0x1800035f6  mov     ecx, cs:g_dwDebugFlags
0x1800035fc  test    cl, 3
0x1800035ff  setnz   dl
0x180003602  bt      ecx, 14h
0x180003606  setb    cl
0x180003609  test    cl, dl
0x18000360b  jz      short loc_180003646
0x18000360d  mov     ecx, esi; int
0x18000360f  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180003614  mov     rcx, cs:g_pDebug
0x18000361b  mov     r9, r12
0x18000361e  mov     dword ptr [rsp+78h+var_40], eax
0x180003622  mov     r8d, 232h
0x180003628  mov     dword ptr [rsp+78h+var_48], esi
0x18000362c  lea     rax, aGetservervaria_3; "\r\n  GetServerVariable[%p]: Failed\r\n"...
0x180003633  mov     [rsp+78h+var_50], rbx
0x180003638  mov     rdx, r13
0x18000363b  mov     [rsp+78h+var_58], rax
0x180003640  call    cs:__imp_PuDbgPrint
0x180003646  mov     ecx, esi; int
0x180003648  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000364d  mov     ecx, eax
0x18000364f  jmp     loc_180003727
0x180003654  mov     eax, cs:g_dwDebugFlags
0x18000365a  mov     ecx, 1200000h
0x18000365f  and     eax, ecx
0x180003661  cmp     eax, ecx
0x180003663  jnz     short loc_1800036D4
0x180003665  mov     r8d, 8; MaxCount
0x18000366b  lea     rdx, aUnicode; "UNICODE_"
0x180003672  mov     rcx, rdi; String1
0x180003675  call    cs:__imp__strnicmp
0x18000367b  test    eax, eax
0x18000367d  jnz     short loc_180003697
0x18000367f  test    byte ptr cs:g_dwDebugFlags, 3
0x180003686  jz      short loc_1800036D4
0x180003688  lea     rax, aGetservervaria_5; "\r\n  GetServerVariable[%p]: Succeeded"...
0x18000368f  mov     r8d, 247h
0x180003695  jmp     short loc_1800036AD
0x180003697  test    byte ptr cs:g_dwDebugFlags, 3
0x18000369e  jz      short loc_1800036D4
0x1800036a0  lea     rax, aGetservervaria_1; "\r\n  GetServerVariable[%p]: Succeeded"...
0x1800036a7  mov     r8d, 253h
0x1800036ad  mov     rcx, cs:g_pDebug
0x1800036b4  mov     r9, r12
0x1800036b7  mov     [rsp+78h+var_40], rbp
0x1800036bc  mov     rdx, r13
0x1800036bf  mov     [rsp+78h+var_48], rdi
0x1800036c4  mov     [rsp+78h+var_50], rbx
0x1800036c9  mov     [rsp+78h+var_58], rax
0x1800036ce  call    cs:__imp_PuDbgPrint
0x1800036d4  mov     eax, 1
0x1800036d9  jmp     short loc_18000372F
0x1800036db  test    r11b, 3
0x1800036df  setnz   cl
0x1800036e2  bt      r11d, 14h
0x1800036e7  setb    al
0x1800036ea  test    al, cl
0x1800036ec  jz      short loc_180003722
0x1800036ee  mov     rcx, cs:g_pDebug
0x1800036f5  lea     rax, aGetservervaria_2; "\r\n  GetServerVariable[%p]: Parameter "...
0x1800036fc  mov     [rsp+78h+var_40], rsi
0x180003701  mov     r9, r12
0x180003704  mov     [rsp+78h+var_48], rdi
0x180003709  mov     r8d, 1F4h
0x18000370f  mov     [rsp+78h+var_50], rbx
0x180003714  mov     rdx, r13
0x180003717  mov     [rsp+78h+var_58], rax
0x18000371c  call    cs:__imp_PuDbgPrint
0x180003722  mov     ecx, 57h ; 'W'; dwErrCode
0x180003727  call    cs:__imp_SetLastError
0x18000372d  xor     eax, eax
0x18000372f  add     rsp, 48h
0x180003733  pop     r13
0x180003735  pop     r12
0x180003737  pop     rdi
0x180003738  pop     rsi
0x180003739  pop     rbp
0x18000373a  pop     rbx
0x18000373b  retn
```
