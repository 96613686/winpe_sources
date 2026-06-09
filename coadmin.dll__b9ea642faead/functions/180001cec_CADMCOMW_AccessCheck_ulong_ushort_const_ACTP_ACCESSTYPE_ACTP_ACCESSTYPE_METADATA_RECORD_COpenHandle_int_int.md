# CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)

- ea: `0x180001cec`
- end: `0x1800020bf`
- name: `?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *, struct COpenHandle *, int *, int *)`
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002cd0`
- `0x180003dd0`
- `0x1800048c0`
- `0x180004b50`
- `0x180004dd0`
- `0x1800063c0`
- `0x180006e44`
- `0x18000716c`
- `0x180007f40`
- `0x180008ae0`

## callees

- `0x180001cec`
- `0x180006f0c`
- `0x18000ac10`
- `0x18000b988`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180001e0a`
- `IisRTL!PuDbgPrint` at `0x180001f22`
- `IisRTL!PuDbgPrint` at `0x180001fb0`
- `IisRTL!PuDbgPrint` at `0x180001fe5`
- `IisRTL!PuDbgPrint` at `0x18000202b`
- `IisRTL!PuDbgPrint` at `0x180002068`
- `IisRTL!PuDbgPrint` at `0x18000209e`
- `IisRTL!PuDbgPrint` at `0x180001e0a`
- `IisRTL!PuDbgPrint` at `0x180001f22`
- `IisRTL!PuDbgPrint` at `0x180001fb0`
- `IisRTL!PuDbgPrint` at `0x180001fe5`
- `IisRTL!PuDbgPrint` at `0x18000202b`
- `IisRTL!PuDbgPrint` at `0x180002068`
- `IisRTL!PuDbgPrint` at `0x18000209e`

## string_xrefs

- `0x180001dea`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180001fde`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x18000205e`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180002082`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180001f0f`: `inetsrv\iis\mb\coadmin\admacl.cxx`
- `0x180001fa9`: `inetsrv\iis\mb\coadmin\admacl.cxx`
- `0x180002024`: `inetsrv\iis\mb\coadmin\admacl.cxx`

## pseudocode

```c
__int64 __fastcall CADMCOMW::AccessCheck(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        struct COpenHandle *a7,
        int *a8,
        int *a9)
{
  unsigned int *v12; // rdi
  int v13; // ebx
  unsigned int v14; // edx
  int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // esi
  int *v19; // rbx
  struct IMDCOM *v20; // rcx
  int v21; // eax
  int v22; // edi
  __int64 v23; // r8
  unsigned int *v25; // [rsp+28h] [rbp-28h]
  int v26; // [rsp+40h] [rbp-10h] BYREF
  int v27[3]; // [rsp+44h] [rbp-Ch] BYREF
  unsigned int v28; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v29; // [rsp+88h] [rbp+38h]

  v29 = a2;
  v28 = 0;
  if ( *(_DWORD *)(a1 + 164) && a5 )
  {
    v12 = a6;
    if ( !a6 )
    {
      v13 = -2147024891;
      if ( (g_dwDebugFlags & 4) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4889, &word_1800127E6, "*%08x\n", -2147024891);
      goto LABEL_54;
    }
    v14 = *a6;
    if ( *a6 == 6269 || v14 == 1099 || v14 - 2042 <= 3 )
    {
      a6[1] |= 0x10u;
    }
    else
    {
      if ( (a6[1] & 0x10) == 0 )
      {
        v13 = -2147024891;
        if ( (g_dwDebugFlags & 4) != 0 )
          PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4918, &word_1800127E6, "*%08x\n", -2147024891);
        goto LABEL_54;
      }
      v15 = IsSchemaForPropertyVolatile(*(struct IMDCOM **)(a1 + 32), v14, (int *)&v28);
      v13 = v15;
      if ( v15 < 0 && (g_dwDebugFlags & 4) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4921, &word_1800127E6, "*%08x\n", v15);
      if ( v13 == -2146646015 )
      {
        v16 = 1;
      }
      else
      {
        if ( v13 < 0 )
        {
          if ( (g_dwDebugFlags & 4) == 0 )
            goto LABEL_54;
          LODWORD(v25) = v13;
          v17 = 4933;
          goto LABEL_53;
        }
        v16 = v28;
      }
      if ( !v16 )
      {
        v13 = -2147024891;
        if ( (g_dwDebugFlags & 4) == 0 )
          goto LABEL_54;
        LODWORD(v25) = -2147024891;
        v17 = 4940;
LABEL_53:
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", v17, &word_1800127E6, "*%08x\n", v25);
LABEL_54:
        if ( (g_dwDebugFlags & 8) != 0 )
          PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4959, &word_1800127E6, "*%08x\n", v13);
        return (unsigned int)v13;
      }
    }
    a2 = v29;
    goto LABEL_26;
  }
  v12 = a6;
  if ( a6 )
  {
LABEL_26:
    v18 = *v12;
    goto LABEL_29;
  }
  v18 = 0;
LABEL_29:
  v19 = a8;
  v20 = *(struct IMDCOM **)(a1 + 32);
  v26 = 0;
  v28 = 0;
  v27[0] = 0;
  if ( a8 )
    *a8 = 0;
  if ( !v20 || !a7 )
  {
    v13 = -2147024809;
    v22 = -2147024809;
    goto LABEL_49;
  }
  v21 = QueryHandleMaxAllowedAccess(v20, (void *)a1, a2, a3, a7, &v28, v27);
  v22 = v21;
  if ( v21 < 0 )
  {
    v13 = v21;
    if ( (g_dwDebugFlags & 4) == 0 )
    {
LABEL_49:
      if ( (g_dwDebugFlags & 8) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 660, &word_1800127E6, "*%08x\n", v22);
      if ( (g_dwDebugFlags & 4) == 0 )
        goto LABEL_54;
      LODWORD(v25) = v22;
      v17 = 4955;
      goto LABEL_53;
    }
    v23 = 638;
LABEL_36:
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", v23, &word_1800127E6, "*%08x\n", v21);
    goto LABEL_49;
  }
  v21 = AccessTypeCheck(a4, a5, v28, v18, &v26);
  v22 = v21;
  if ( v21 < 0 )
  {
    v13 = v21;
    if ( (g_dwDebugFlags & 4) == 0 )
      goto LABEL_49;
    v23 = 645;
    goto LABEL_36;
  }
  if ( v19 )
    *v19 = v26 & 1;
  if ( a9 )
    *a9 = v27[0];
  if ( (g_dwDebugFlags & 1) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 660, &word_1800127E6, "\n");
  v13 = 0;
  if ( (g_dwDebugFlags & 1) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4959, &word_1800127E6, "\n");
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180001cec  mov     [rsp-28h+arg_10], rbx
0x180001cf1  mov     [rsp-28h+arg_18], rsi
0x180001cf6  mov     [rsp-28h+arg_8], edx
0x180001cfa  push    rbp
0x180001cfb  push    rdi
0x180001cfc  push    r12
0x180001cfe  push    r13
0x180001d00  push    r14
0x180001d02  mov     rbp, rsp
0x180001d05  sub     rsp, 50h
0x180001d09  mov     r14, rcx
0x180001d0c  mov     [rbp+arg_0], 0
0x180001d13  mov     r12d, r9d
0x180001d16  lea     rcx, a08x; "*%08x\n"
0x180001d1d  mov     r13, r8
0x180001d20  lea     rsi, word_1800127E6
0x180001d27  cmp     dword ptr [r14+0A4h], 0
0x180001d2f  jz      loc_180001E74
0x180001d35  cmp     [rbp+arg_20], 0
0x180001d39  jz      loc_180001E74
0x180001d3f  mov     rdi, [rbp+arg_28]
0x180001d43  test    rdi, rdi
0x180001d46  jnz     short loc_180001D70
0x180001d48  test    byte ptr cs:g_dwDebugFlags, 4
0x180001d4f  mov     eax, 80070005h
0x180001d54  mov     ebx, eax
0x180001d56  jz      loc_180002075
0x180001d5c  mov     dword ptr [rsp+50h+var_28], eax
0x180001d60  mov     r8d, 1319h
0x180001d66  mov     [rsp+50h+var_30], rcx
0x180001d6b  jmp     loc_180002057
0x180001d70  mov     edx, [rdi]; unsigned int
0x180001d72  cmp     edx, 187Dh
0x180001d78  jz      loc_180001E69
0x180001d7e  cmp     edx, 44Bh
0x180001d84  jz      loc_180001E69
0x180001d8a  lea     eax, [rdx-7FAh]
0x180001d90  cmp     eax, 3
0x180001d93  jbe     loc_180001E69
0x180001d99  test    byte ptr [rdi+4], 10h
0x180001d9d  jnz     short loc_180001DC7
0x180001d9f  test    byte ptr cs:g_dwDebugFlags, 4
0x180001da6  mov     eax, 80070005h
0x180001dab  mov     ebx, eax
0x180001dad  jz      loc_180002075
0x180001db3  mov     dword ptr [rsp+50h+var_28], eax
0x180001db7  mov     r8d, 1336h
0x180001dbd  mov     [rsp+50h+var_30], rcx
0x180001dc2  jmp     loc_180002057
0x180001dc7  mov     rcx, [r14+20h]; struct IMDCOM *
0x180001dcb  lea     r8, [rbp+arg_0]; int *
0x180001dcf  call    ?IsSchemaForPropertyVolatile@@YAJPEAUIMDCOM@@KPEAH@Z; IsSchemaForPropertyVolatile(IMDCOM *,ulong,int *)
0x180001dd4  mov     ebx, eax
0x180001dd6  test    eax, eax
0x180001dd8  jns     short loc_180001E10
0x180001dda  test    byte ptr cs:g_dwDebugFlags, 4
0x180001de1  jz      short loc_180001E10
0x180001de3  mov     rcx, cs:g_pDebug
0x180001dea  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180001df1  mov     dword ptr [rsp+50h+var_28], eax
0x180001df5  mov     r9, rsi
0x180001df8  lea     rax, a08x; "*%08x\n"
0x180001dff  mov     r8d, 1339h
0x180001e05  mov     [rsp+50h+var_30], rax
0x180001e0a  call    cs:__imp_PuDbgPrint
0x180001e10  cmp     ebx, 800CC801h
0x180001e16  jnz     short loc_180001E1F
0x180001e18  mov     eax, 1
0x180001e1d  jmp     short loc_180001E42
0x180001e1f  test    ebx, ebx
0x180001e21  jns     short loc_180001E3F
0x180001e23  test    byte ptr cs:g_dwDebugFlags, 4
0x180001e2a  jz      loc_18000206E
0x180001e30  mov     dword ptr [rsp+50h+var_28], ebx
0x180001e34  mov     r8d, 1345h
0x180001e3a  jmp     loc_18000204B
0x180001e3f  mov     eax, [rbp+arg_0]
0x180001e42  test    eax, eax
0x180001e44  jnz     short loc_180001E6D
0x180001e46  test    byte ptr cs:g_dwDebugFlags, 4
0x180001e4d  mov     eax, 80070005h
0x180001e52  mov     ebx, eax
0x180001e54  jz      loc_18000206E
0x180001e5a  mov     dword ptr [rsp+50h+var_28], eax
0x180001e5e  mov     r8d, 134Ch
0x180001e64  jmp     loc_18000204B
0x180001e69  or      dword ptr [rdi+4], 10h
0x180001e6d  mov     edx, [rbp+arg_8]
0x180001e70  mov     esi, [rdi]
0x180001e72  jmp     short loc_180001E7F
0x180001e74  mov     rdi, [rbp+arg_28]
0x180001e78  test    rdi, rdi
0x180001e7b  jnz     short loc_180001E70
0x180001e7d  xor     esi, esi
0x180001e7f  mov     rbx, [rbp+arg_38]
0x180001e83  mov     rcx, [r14+20h]; struct IMDCOM *
0x180001e87  mov     [rbp+var_10], 0
0x180001e8e  mov     [rbp+arg_0], 0
0x180001e95  mov     [rbp+var_C], 0
0x180001e9c  test    rbx, rbx
0x180001e9f  jz      short loc_180001EA7
0x180001ea1  mov     dword ptr [rbx], 0
0x180001ea7  test    rcx, rcx
0x180001eaa  jz      loc_180001FF0
0x180001eb0  mov     rax, [rbp+arg_30]
0x180001eb4  test    rax, rax
0x180001eb7  jz      loc_180001FF0
0x180001ebd  lea     r8, [rbp+var_C]
0x180001ec1  mov     r9, r13; unsigned __int16 *
0x180001ec4  mov     [rsp+50h+var_20], r8; int *
0x180001ec9  lea     r8, [rbp+arg_0]
0x180001ecd  mov     [rsp+50h+var_28], r8; unsigned int *
0x180001ed2  mov     r8d, edx; unsigned int
0x180001ed5  mov     rdx, r14; void *
0x180001ed8  mov     [rsp+50h+var_30], rax; struct COpenHandle *
0x180001edd  call    ?QueryHandleMaxAllowedAccess@@YAJPEAUIMDCOM@@PEAXKPEBGPEAVCOpenHandle@@PEAKPEAH@Z; QueryHandleMaxAllowedAccess(IMDCOM *,void *,ulong,ushort const *,COpenHandle *,ulong *,int *)
0x180001ee2  mov     edi, eax
0x180001ee4  test    eax, eax
0x180001ee6  jns     short loc_180001F2D
0x180001ee8  test    byte ptr cs:g_dwDebugFlags, 4
0x180001eef  mov     ebx, eax
0x180001ef1  jz      loc_180001FF7
0x180001ef7  mov     r8d, 27Eh
0x180001efd  mov     rcx, cs:g_pDebug
0x180001f04  lea     r9, word_1800127E6
0x180001f0b  mov     dword ptr [rsp+50h+var_28], eax
0x180001f0f  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x180001f16  lea     rax, a08x; "*%08x\n"
0x180001f1d  mov     [rsp+50h+var_30], rax
0x180001f22  call    cs:__imp_PuDbgPrint
0x180001f28  jmp     loc_180001FF7
0x180001f2d  mov     r8d, [rbp+arg_0]
0x180001f31  lea     rax, [rbp+var_10]
0x180001f35  mov     edx, [rbp+arg_20]
0x180001f38  mov     r9d, esi
0x180001f3b  mov     ecx, r12d
0x180001f3e  mov     [rsp+50h+var_30], rax
0x180001f43  call    ?AccessTypeCheck@@YAJW4ACTP_ACCESSTYPE@@0KKPEAK@Z; AccessTypeCheck(ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,ulong,ulong,ulong *)
0x180001f48  mov     edi, eax
0x180001f4a  test    eax, eax
0x180001f4c  jns     short loc_180001F65
0x180001f4e  test    byte ptr cs:g_dwDebugFlags, 4
0x180001f55  mov     ebx, eax
0x180001f57  jz      loc_180001FF7
0x180001f5d  mov     r8d, 285h
0x180001f63  jmp     short loc_180001EFD
0x180001f65  test    rbx, rbx
0x180001f68  jz      short loc_180001F72
0x180001f6a  mov     eax, [rbp+var_10]
0x180001f6d  and     eax, 1
0x180001f70  mov     [rbx], eax
0x180001f72  mov     rcx, [rbp+arg_40]
0x180001f76  test    rcx, rcx
0x180001f79  jz      short loc_180001F80
0x180001f7b  mov     eax, [rbp+var_C]
0x180001f7e  mov     [rcx], eax
0x180001f80  test    byte ptr cs:g_dwDebugFlags, 1
0x180001f87  lea     rsi, asc_1800127E4; "\n"
0x180001f8e  jz      short loc_180001FB6
0x180001f90  mov     rcx, cs:g_pDebug
0x180001f97  lea     r9, word_1800127E6
0x180001f9e  mov     r8d, 294h
0x180001fa4  mov     [rsp+50h+var_30], rsi
0x180001fa9  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x180001fb0  call    cs:__imp_PuDbgPrint
0x180001fb6  xor     ebx, ebx
0x180001fb8  test    byte ptr cs:g_dwDebugFlags, 1
0x180001fbf  jz      loc_1800020A4
0x180001fc5  mov     rcx, cs:g_pDebug
0x180001fcc  lea     r9, word_1800127E6
0x180001fd3  mov     r8d, 135Fh
0x180001fd9  mov     [rsp+50h+var_30], rsi
0x180001fde  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180001fe5  call    cs:__imp_PuDbgPrint
0x180001feb  jmp     loc_1800020A4
0x180001ff0  mov     ebx, 80070057h
0x180001ff5  mov     edi, ebx
0x180001ff7  test    byte ptr cs:g_dwDebugFlags, 8
0x180001ffe  jz      short loc_180002031
0x180002000  mov     rcx, cs:g_pDebug
0x180002007  lea     rax, a08x; "*%08x\n"
0x18000200e  mov     dword ptr [rsp+50h+var_28], edi
0x180002012  lea     r9, word_1800127E6
0x180002019  mov     r8d, 294h
0x18000201f  mov     [rsp+50h+var_30], rax
0x180002024  lea     rdx, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x18000202b  call    cs:__imp_PuDbgPrint
0x180002031  test    byte ptr cs:g_dwDebugFlags, 4
0x180002038  lea     rsi, word_1800127E6
0x18000203f  jz      short loc_18000206E
0x180002041  mov     dword ptr [rsp+50h+var_28], edi
0x180002045  mov     r8d, 135Bh
0x18000204b  lea     rax, a08x; "*%08x\n"
0x180002052  mov     [rsp+50h+var_30], rax
0x180002057  mov     rcx, cs:g_pDebug
0x18000205e  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180002065  mov     r9, rsi
0x180002068  call    cs:__imp_PuDbgPrint
0x18000206e  lea     rcx, a08x; "*%08x\n"
0x180002075  test    byte ptr cs:g_dwDebugFlags, 8
0x18000207c  jz      short loc_1800020A4
0x18000207e  mov     dword ptr [rsp+50h+var_28], ebx
0x180002082  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180002089  mov     [rsp+50h+var_30], rcx
0x18000208e  mov     r9, rsi
0x180002091  mov     rcx, cs:g_pDebug
0x180002098  mov     r8d, 135Fh
0x18000209e  call    cs:__imp_PuDbgPrint
0x1800020a4  lea     r11, [rsp+50h+var_s0]
0x1800020a9  mov     eax, ebx
0x1800020ab  mov     rbx, [r11+40h]
0x1800020af  mov     rsi, [r11+48h]
0x1800020b3  mov     rsp, r11
0x1800020b6  pop     r14
0x1800020b8  pop     r13
0x1800020ba  pop     r12
0x1800020bc  pop     rdi
0x1800020bd  pop     rbp
0x1800020be  retn
```
