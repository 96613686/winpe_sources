# IkeMatchFwpmFilter

- ea: `0x18002f2f0`
- end: `0x18002f754`
- name: `IkeMatchFwpmFilter`
- size: `1124`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180035234`
- `0x1800356c0`
- `0x180078324`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180008590`
- `0x18000af84`
- `0x180013200`
- `0x180020b00`
- `0x18002f2f0`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f510`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f575`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f5ba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f510`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f575`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002f5ba`
- `ntdll!EtwEventWriteTransfer` at `0x18002f69f`
- `ntdll!EtwEventWriteTransfer` at `0x18002f69f`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f70f`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002f70f`

## pseudocode

```c
__int64 __fastcall IkeMatchFwpmFilter(
        int *a1,
        __int64 a2,
        __int64 a3,
        GUID *a4,
        __int64 a5,
        UINT32 a6,
        int a7,
        void **a8,
        __int64 a9)
{
  __int64 v13; // rax
  __int64 v14; // rcx
  UINT32 v15; // r12d
  __int64 v16; // rbx
  int v17; // ecx
  int v18; // eax
  int v19; // edx
  int v20; // esi
  __int64 LockSemaphore_low; // rcx
  _QWORD *v22; // rbx
  __int64 *Value; // rax
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v27; // rax
  DWORD LockSemaphore; // ecx
  __int64 *v29; // rax
  __int64 v30; // rcx
  DWORD v31; // ecx
  char *v32; // rax
  const WCHAR *v33; // rdx
  __int64 v34; // rax
  int v36; // eax
  int v38; // [rsp+64h] [rbp-95h] BYREF
  UINT32 v39; // [rsp+68h] [rbp-91h] BYREF
  int v40; // [rsp+6Ch] [rbp-8Dh]
  int v41[2]; // [rsp+70h] [rbp-89h] BYREF
  void *p; // [rsp+78h] [rbp-81h] BYREF
  int v43[2]; // [rsp+80h] [rbp-79h] BYREF
  _QWORD v44[3]; // [rsp+88h] [rbp-71h] BYREF
  char *v45; // [rsp+A0h] [rbp-59h] BYREF
  int v46; // [rsp+A8h] [rbp-51h]
  int v47; // [rsp+ACh] [rbp-4Dh]
  char *v48; // [rsp+B0h] [rbp-49h]
  int v49; // [rsp+B8h] [rbp-41h]
  int v50; // [rsp+BCh] [rbp-3Dh]
  int *v51; // [rsp+C0h] [rbp-39h]
  __int64 v52; // [rsp+C8h] [rbp-31h]
  const WCHAR *v53; // [rsp+D0h] [rbp-29h]
  int v54; // [rsp+D8h] [rbp-21h]
  int v55; // [rsp+DCh] [rbp-1Dh]
  const char *v56; // [rsp+E0h] [rbp-19h]
  __int64 v57; // [rsp+E8h] [rbp-11h]

  *(_QWORD *)v43 = a5;
  v40 = a7;
  v44[0] = a9;
  *(_QWORD *)v41 = 0;
  v38 = 0;
  p = 0;
  v39 = 0;
  v13 = IkeMMorQMSelectorToFwpmFilterConditions(a2, a3, (_DWORD)a4, (unsigned int)v41, (__int64)&v38);
  v15 = v38;
  v16 = v13;
  if ( v13 )
  {
    v20 = v40;
LABEL_59:
    IkeFreeFwpmFilterConditions(v14, v41, v15, 0xFFFFFFFFLL);
    if ( !v16 )
      goto LABEL_62;
    goto LABEL_60;
  }
  if ( a2 )
  {
    if ( *a1 )
    {
      v17 = 10;
      if ( *a1 == 1 )
        v17 = 6;
    }
    else
    {
      v17 = 5;
    }
    if ( (*(_QWORD *)&a4->Data1 == *(_QWORD *)&FWPM_LAYER_IPSEC_V4.Data1
       && *(_QWORD *)a4->Data4 == *(_QWORD *)FWPM_LAYER_IPSEC_V4.Data4
       || *(_QWORD *)&a4->Data1 == *(_QWORD *)&FWPM_LAYER_IPSEC_V6.Data1
       && *(_QWORD *)a4->Data4 == *(_QWORD *)FWPM_LAYER_IPSEC_V6.Data4)
      && (*(_BYTE *)(*((_QWORD *)a1 + 4) + 8LL) & 1) != 0 )
    {
      v17 = 9;
    }
  }
  else
  {
    if ( (unsigned int)IkeIsFwpTransportLayer(a4) )
    {
      v17 = 14;
      goto LABEL_26;
    }
    if ( *(_DWORD *)(a3 + 128) == 1 )
    {
      v18 = *a1;
      if ( !*a1 )
      {
        v17 = 1;
        goto LABEL_26;
      }
      v17 = 12;
      v19 = 3;
    }
    else
    {
      if ( *(_DWORD *)(a3 + 128) != 2 )
        __fastfail(5u);
      v18 = *a1;
      if ( !*a1 )
      {
        v17 = 2;
        goto LABEL_26;
      }
      v17 = 9;
      v19 = 4;
    }
    if ( v18 == 1 )
      v17 = v19;
  }
LABEL_26:
  v20 = v40;
  v16 = IkeEnumFwpmLayer(
          *(FWPM_FILTER_CONDITION0 **)v41,
          v15,
          a4,
          *(GUID **)v43,
          0,
          v17,
          a6,
          v40,
          0xFFFFFFFF,
          (FWPM_FILTER0 ***)&p,
          &v39);
  if ( v16 )
    goto LABEL_59;
  LockSemaphore_low = v39;
  if ( v39 )
  {
    *a8 = p;
    *(_DWORD *)v44[0] = LockSemaphore_low;
    IkeFreeFwpmFilterConditions(LockSemaphore_low, v41, v15, 0xFFFFFFFFLL);
    goto LABEL_62;
  }
  if ( !v20 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals
        && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
        && (Value = (__int64 *)TlsGetValue(LockSemaphore_low), v22 = WPP_GLOBAL_Control, Value) )
      {
        v24 = *Value;
      }
      else
      {
        LODWORD(v24) = 0;
      }
      v25 = v22[2];
      TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
      WPP_SF_iS(v25, 10, (unsigned int)WPP_610130b6229e37757f1f9736af3100d0_Traceguids, v24, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_56;
    v27 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( LockSemaphore != -1 )
      {
        v29 = (__int64 *)TlsGetValue(LockSemaphore);
        if ( v29 )
        {
          v30 = *v29;
          v27 = gIkeExtGlobals;
LABEL_46:
          *(_QWORD *)v43 = v30;
          v51 = v43;
          v52 = 8;
          if ( !v27 )
            goto LABEL_54;
          v31 = (DWORD)v27[86].LockSemaphore;
          if ( v31 == -1 )
            goto LABEL_54;
          v32 = (char *)TlsGetValue(v31);
          v33 = (const WCHAR *)(v32 + 8);
          if ( !v32 )
            v33 = 0;
          if ( v33 )
          {
            v34 = -1;
            while ( v33[++v34] != 0 )
              ;
            v36 = 2 * v34 + 2;
          }
          else
          {
LABEL_54:
            v33 = &LocaleName;
            v36 = 2;
          }
          v54 = v36;
          v53 = v33;
          v56 = "FwpmFilterEnum returned no matching filters";
          v45 = off_180173280;
          v55 = 0;
          v57 = 44;
          v44[0] = 0x40B000000LL;
          v44[1] = 0;
          v46 = *(unsigned __int16 *)off_180173280;
          v48 = byte_180154A1D;
          v47 = 2;
          v49 = 58;
          v50 = 1;
          EtwEventWriteTransfer(qword_180173298, v44, 0, 0, 5, &v45);
LABEL_56:
          v16 = WfpReportSysErrorAsWinError(LockSemaphore_low, "IkeMatchFwpmFilter", 13825, 1);
          goto LABEL_59;
        }
        v27 = gIkeExtGlobals;
      }
    }
    v30 = 0;
    goto LABEL_46;
  }
  v16 = -2147011071;
  IkeFreeFwpmFilterConditions(v39, v41, v15, 0xFFFFFFFFLL);
LABEL_60:
  if ( p )
    FwpmFreeMemory0(&p);
LABEL_62:
  if ( v20 )
    return v16;
  else
    return IkeReturnError(v16, "IkeMatchFwpmFilter");
}

```

## disassembly

```asm
0x18002f2f0  mov     [rsp-8+arg_0], rbx
0x18002f2f5  push    rbp
0x18002f2f6  push    rsi
0x18002f2f7  push    rdi
0x18002f2f8  push    r12
0x18002f2fa  push    r13
0x18002f2fc  push    r14
0x18002f2fe  push    r15
0x18002f300  lea     rbp, [rsp-7]
0x18002f305  sub     rsp, 100h
0x18002f30c  mov     rax, cs:__security_cookie
0x18002f313  xor     rax, rsp
0x18002f316  mov     [rbp+37h+var_40], rax
0x18002f31a  mov     rax, [rbp+37h+arg_20]
0x18002f31e  mov     rdi, r9
0x18002f321  mov     r13, [rbp+37h+arg_38]
0x18002f325  lea     r9, [rsp+130h+var_C0]
0x18002f32a  mov     qword ptr [rbp+37h+var_B0], rax
0x18002f32e  mov     r14, r8
0x18002f331  mov     eax, [rbp+37h+arg_28]
0x18002f334  mov     r15, rdx
0x18002f337  mov     [rsp+130h+var_D0], eax
0x18002f33b  mov     rsi, rcx
0x18002f33e  mov     eax, [rbp+37h+arg_30]
0x18002f341  mov     r8, rdi
0x18002f344  mov     dword ptr [rsp+130h+var_C8+4], eax
0x18002f348  mov     rdx, r14
0x18002f34b  mov     rax, [rbp+37h+arg_40]
0x18002f352  mov     rcx, r15
0x18002f355  mov     [rbp+37h+var_A8], rax
0x18002f359  xor     eax, eax
0x18002f35b  mov     qword ptr [rsp+130h+var_C0], rax
0x18002f360  mov     [rsp+130h+var_CC], eax
0x18002f364  mov     [rsp+130h+p], rax
0x18002f369  mov     dword ptr [rsp+130h+var_C8], eax
0x18002f36d  lea     rax, [rsp+130h+var_CC]
0x18002f372  mov     [rsp+130h+var_110], rax
0x18002f377  call    IkeMMorQMSelectorToFwpmFilterConditions
0x18002f37c  mov     r12d, [rsp+130h+var_CC]
0x18002f381  mov     rbx, rax
0x18002f384  test    rax, rax
0x18002f387  jnz     loc_18002F6E6
0x18002f38d  test    r15, r15
0x18002f390  jz      short loc_18002F3F2
0x18002f392  mov     eax, [rsi]
0x18002f394  test    eax, eax
0x18002f396  jnz     short loc_18002F39F
0x18002f398  mov     ecx, 5
0x18002f39d  jmp     short loc_18002F3AF
0x18002f39f  cmp     eax, 1
0x18002f3a2  mov     ecx, 0Ah
0x18002f3a7  mov     edx, 6
0x18002f3ac  cmovz   ecx, edx
0x18002f3af  mov     rax, [rdi]
0x18002f3b2  cmp     rax, qword ptr cs:FWPM_LAYER_IPSEC_V4.Data1
0x18002f3b9  jnz     short loc_18002F3C8
0x18002f3bb  mov     rax, [rdi+8]
0x18002f3bf  cmp     rax, qword ptr cs:FWPM_LAYER_IPSEC_V4.Data4
0x18002f3c6  jz      short loc_18002F3E1
0x18002f3c8  mov     rax, [rdi]
0x18002f3cb  cmp     rax, qword ptr cs:FWPM_LAYER_IPSEC_V6.Data1
0x18002f3d2  jnz     short loc_18002F453
0x18002f3d4  mov     rax, [rdi+8]
0x18002f3d8  cmp     rax, qword ptr cs:FWPM_LAYER_IPSEC_V6.Data4
0x18002f3df  jnz     short loc_18002F453
0x18002f3e1  mov     rax, [rsi+20h]
0x18002f3e5  test    byte ptr [rax+8], 1
0x18002f3e9  jz      short loc_18002F453
0x18002f3eb  mov     ecx, 9
0x18002f3f0  jmp     short loc_18002F453
0x18002f3f2  mov     rcx, rdi
0x18002f3f5  call    IkeIsFwpTransportLayer
0x18002f3fa  test    eax, eax
0x18002f3fc  jz      short loc_18002F405
0x18002f3fe  mov     ecx, 0Eh
0x18002f403  jmp     short loc_18002F453
0x18002f405  mov     edx, [r14+80h]
0x18002f40c  sub     edx, 1
0x18002f40f  jz      short loc_18002F436
0x18002f411  cmp     edx, 1
0x18002f414  jz      short loc_18002F41D
0x18002f416  mov     ecx, 5
0x18002f41b  int     29h; Win8: RtlFailFast(ecx)
0x18002f41d  mov     eax, [rsi]
0x18002f41f  test    eax, eax
0x18002f421  jnz     short loc_18002F42A
0x18002f423  mov     ecx, 2
0x18002f428  jmp     short loc_18002F453
0x18002f42a  mov     ecx, 9
0x18002f42f  mov     edx, 4
0x18002f434  jmp     short loc_18002F44D
0x18002f436  mov     eax, [rsi]
0x18002f438  test    eax, eax
0x18002f43a  jnz     short loc_18002F443
0x18002f43c  mov     ecx, 1
0x18002f441  jmp     short loc_18002F453
0x18002f443  mov     ecx, 0Ch
0x18002f448  mov     edx, 3
0x18002f44d  cmp     eax, 1
0x18002f450  cmovz   ecx, edx
0x18002f453  mov     esi, dword ptr [rsp+130h+var_C8+4]
0x18002f457  lea     rax, [rsp+130h+var_C8]
0x18002f45c  mov     r9, qword ptr [rbp+37h+var_B0]; int
0x18002f460  xor     r14d, r14d
0x18002f463  mov     [rsp+130h+var_E0], rax; __int64
0x18002f468  mov     r8, rdi; int
0x18002f46b  lea     rax, [rsp+130h+p]
0x18002f470  mov     edx, r12d; int
0x18002f473  mov     [rsp+130h+var_E8], rax; __int64
0x18002f478  mov     eax, [rsp+130h+var_D0]
0x18002f47c  mov     [rsp+130h+numEntriesRequested], 0FFFFFFFFh; numEntriesRequested
0x18002f484  mov     [rsp+130h+var_F8], esi; int
0x18002f488  mov     [rsp+130h+var_100], eax; int
0x18002f48c  mov     [rsp+130h+var_108], ecx; int
0x18002f490  mov     rcx, qword ptr [rsp+130h+var_C0]; int
0x18002f495  mov     [rsp+130h+var_110], r14; __int64
0x18002f49a  call    IkeEnumFwpmLayer
0x18002f49f  mov     rbx, rax
0x18002f4a2  test    rax, rax
0x18002f4a5  jnz     loc_18002F6EA
0x18002f4ab  mov     ecx, dword ptr [rsp+130h+var_C8]
0x18002f4af  test    ecx, ecx
0x18002f4b1  jnz     loc_18002F6C2
0x18002f4b7  test    esi, esi
0x18002f4b9  jz      short loc_18002F4DA
0x18002f4bb  mov     r9d, 0FFFFFFFFh
0x18002f4c1  lea     rdx, [rsp+130h+var_C0]
0x18002f4c6  mov     r8d, r12d
0x18002f4c9  mov     rbx, 0FFFFFFFF80073601h
0x18002f4d0  call    IkeFreeFwpmFilterConditions
0x18002f4d5  jmp     loc_18002F702
0x18002f4da  mov     rbx, cs:WPP_GLOBAL_Control
0x18002f4e1  lea     rax, WPP_GLOBAL_Control
0x18002f4e8  cmp     rbx, rax
0x18002f4eb  jz      short loc_18002F54F
0x18002f4ed  cmp     byte ptr [rbx+19h], 4
0x18002f4f1  jb      short loc_18002F54F
0x18002f4f3  test    byte ptr [rbx+1Ch], 10h
0x18002f4f7  jz      short loc_18002F54F
0x18002f4f9  mov     rax, cs:gIkeExtGlobals
0x18002f500  test    rax, rax
0x18002f503  jz      short loc_18002F527
0x18002f505  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002f50b  cmp     ecx, 0FFFFFFFFh
0x18002f50e  jz      short loc_18002F527
0x18002f510  call    cs:__imp_TlsGetValue
0x18002f516  mov     rbx, cs:WPP_GLOBAL_Control
0x18002f51d  test    rax, rax
0x18002f520  jz      short loc_18002F527
0x18002f522  mov     rdi, [rax]
0x18002f525  jmp     short loc_18002F52A
0x18002f527  mov     rdi, r14
0x18002f52a  mov     rbx, [rbx+10h]
0x18002f52e  call    IkeGetTlsPeerAddr
0x18002f533  mov     edx, 0Ah
0x18002f538  mov     [rsp+130h+var_110], rax
0x18002f53d  mov     r9, rdi
0x18002f540  lea     r8, WPP_610130b6229e37757f1f9736af3100d0_Traceguids
0x18002f547  mov     rcx, rbx
0x18002f54a  call    WPP_SF_iS
0x18002f54f  mov     eax, cs:dword_180173278
0x18002f555  cmp     eax, 4
0x18002f558  jbe     loc_18002F6A5
0x18002f55e  mov     rax, cs:gIkeExtGlobals
0x18002f565  test    rax, rax
0x18002f568  jz      short loc_18002F593
0x18002f56a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002f570  cmp     ecx, 0FFFFFFFFh
0x18002f573  jz      short loc_18002F593
0x18002f575  call    cs:__imp_TlsGetValue
0x18002f57b  test    rax, rax
0x18002f57e  jz      short loc_18002F58C
0x18002f580  mov     rcx, [rax]
0x18002f583  mov     rax, cs:gIkeExtGlobals
0x18002f58a  jmp     short loc_18002F596
0x18002f58c  mov     rax, cs:gIkeExtGlobals
0x18002f593  mov     rcx, r14
0x18002f596  mov     qword ptr [rbp+37h+var_B0], rcx
0x18002f59a  lea     rcx, [rbp+37h+var_B0]
0x18002f59e  mov     [rbp+37h+var_70], rcx
0x18002f5a2  mov     [rbp+37h+var_68], 8
0x18002f5aa  test    rax, rax
0x18002f5ad  jz      short loc_18002F5F5
0x18002f5af  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002f5b5  cmp     ecx, 0FFFFFFFFh
0x18002f5b8  jz      short loc_18002F5F5
0x18002f5ba  call    cs:__imp_TlsGetValue
0x18002f5c0  test    rax, rax
0x18002f5c3  lea     rdx, [rax+8]
0x18002f5c7  cmovz   rdx, r14
0x18002f5cb  test    rdx, rdx
0x18002f5ce  jz      short loc_18002F5F5
0x18002f5d0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002f5d7  nop     word ptr [rax+rax+00000000h]
0x18002f5e0  cmp     [rdx+rax*2+2], r14w
0x18002f5e6  lea     rax, [rax+1]
0x18002f5ea  jnz     short loc_18002F5E0
0x18002f5ec  lea     eax, ds:2[rax*2]
0x18002f5f3  jmp     short loc_18002F601
0x18002f5f5  lea     rdx, LocaleName
0x18002f5fc  mov     eax, 2
0x18002f601  mov     [rbp+37h+var_58], eax
0x18002f604  lea     rcx, _TraceLoggingMetadata
0x18002f60b  mov     [rbp+37h+var_60], rdx
0x18002f60f  lea     rax, aFwpmfilterenum; "FwpmFilterEnum returned no matching fil"...
0x18002f616  mov     [rbp+37h+var_50], rax
0x18002f61a  lea     rdx, [rbp+37h+var_A8]
0x18002f61e  movzx   eax, cs:word_180154A13
0x18002f625  xor     r9d, r9d
0x18002f628  mov     dword ptr [rbp+37h+var_A8+4], eax
0x18002f62b  xor     r8d, r8d
0x18002f62e  mov     rax, cs:off_180173280
0x18002f635  mov     [rbp+37h+var_90], rax
0x18002f639  mov     [rbp+37h+var_54], r14d
0x18002f63d  mov     [rbp+37h+var_48], 2Ch ; ','
0x18002f645  mov     dword ptr [rbp+37h+var_A8], 0B000000h
0x18002f64c  mov     [rbp+37h+var_A0], r14
0x18002f650  movzx   eax, word ptr [rax]
0x18002f653  mov     [rbp+37h+var_88], eax
0x18002f656  lea     rax, byte_180154A1D
0x18002f65d  mov     [rbp+37h+var_80], rax
0x18002f661  lea     rax, _TraceLoggingMetadataEnd
0x18002f668  sub     eax, ecx
0x18002f66a  mov     [rbp+37h+var_84], 2
0x18002f671  mov     [rbp+37h+var_78], 3Ah ; ':'
0x18002f678  mov     [rbp+37h+var_74], 1
0x18002f67f  mov     [rsp+130h+var_D0], eax
0x18002f683  mov     eax, [rsp+130h+var_D0]
0x18002f687  mov     rcx, cs:qword_180173298
0x18002f68e  lea     rax, [rbp+37h+var_90]
0x18002f692  mov     qword ptr [rsp+130h+var_108], rax
0x18002f697  mov     dword ptr [rsp+130h+var_110], 5
0x18002f69f  call    cs:__imp_EtwEventWriteTransfer
0x18002f6a5  mov     r9d, 1
0x18002f6ab  lea     rdx, aIkematchfwpmfi; "IkeMatchFwpmFilter"
0x18002f6b2  mov     r8d, 3601h
0x18002f6b8  call    WfpReportSysErrorAsWinError
0x18002f6bd  mov     rbx, rax
0x18002f6c0  jmp     short loc_18002F6EA
0x18002f6c2  mov     rax, [rsp+130h+p]
0x18002f6c7  lea     rdx, [rsp+130h+var_C0]
0x18002f6cc  mov     [r13+0], rax
0x18002f6d0  mov     r9d, 0FFFFFFFFh
0x18002f6d6  mov     rax, [rbp+37h+var_A8]
0x18002f6da  mov     r8d, r12d
0x18002f6dd  mov     [rax], ecx
0x18002f6df  call    IkeFreeFwpmFilterConditions
0x18002f6e4  jmp     short loc_18002F715
0x18002f6e6  mov     esi, dword ptr [rsp+130h+var_C8+4]
0x18002f6ea  mov     r9d, 0FFFFFFFFh
0x18002f6f0  lea     rdx, [rsp+130h+var_C0]
0x18002f6f5  mov     r8d, r12d
0x18002f6f8  call    IkeFreeFwpmFilterConditions
0x18002f6fd  test    rbx, rbx
0x18002f700  jz      short loc_18002F715
0x18002f702  cmp     [rsp+130h+p], 0
0x18002f708  jz      short loc_18002F715
0x18002f70a  lea     rcx, [rsp+130h+p]; p
0x18002f70f  call    cs:__imp_FwpmFreeMemory0
0x18002f715  test    esi, esi
0x18002f717  jz      short loc_18002F71E
0x18002f719  mov     rax, rbx
0x18002f71c  jmp     short loc_18002F72D
0x18002f71e  lea     rdx, aIkematchfwpmfi; "IkeMatchFwpmFilter"
0x18002f725  mov     rcx, rbx
0x18002f728  call    IkeReturnError
0x18002f72d  mov     rcx, [rbp+37h+var_40]
0x18002f731  xor     rcx, rsp; StackCookie
0x18002f734  call    __security_check_cookie
0x18002f739  mov     rbx, [rsp+130h+arg_0]
0x18002f741  add     rsp, 100h
0x18002f748  pop     r15
0x18002f74a  pop     r14
0x18002f74c  pop     r13
0x18002f74e  pop     r12
0x18002f750  pop     rdi
0x18002f751  pop     rsi
0x18002f752  pop     rbp
0x18002f753  retn
```
