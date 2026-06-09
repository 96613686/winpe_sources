# IkeOptionalConstructNatDisc

- ea: `0x180047450`
- end: `0x180047ba8`
- name: `IkeOptionalConstructNatDisc`
- size: `1880`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800428c0`
- `0x180043270`
- `0x1800e5d1c`
- `0x1800e6040`
- `0x1800e638c`
- `0x1800e66d8`
- `0x1800e6a58`
- `0x1800e6c28`
- `0x1800e6e2c`
- `0x1800e7294`
- `0x1800e77b4`
- `0x1800e7b04`

## callees

- `0x1800037c4`
- `0x180008388`
- `0x18000fe50`
- `0x180047450`
- `0x18004882c`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`
- `0x180101854`
- `0x180110d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800474f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047537`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047662`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800476c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004770e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047a1b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047a65`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800474f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047537`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047662`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800476c7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004770e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047a1b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047a65`
- `ntdll!EtwEventWriteTransfer` at `0x180047606`
- `ntdll!EtwEventWriteTransfer` at `0x1800477f0`
- `ntdll!EtwEventWriteTransfer` at `0x180047b3f`
- `ntdll!EtwEventWriteTransfer` at `0x180047606`
- `ntdll!EtwEventWriteTransfer` at `0x1800477f0`
- `ntdll!EtwEventWriteTransfer` at `0x180047b3f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800479af`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800479af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047971`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800479ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047971`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800479ca`

## pseudocode

```c
__int64 __fastcall IkeOptionalConstructNatDisc(__int64 LockSemaphore_low, struct HINSTANCE__ *a2, __int64 a3)
{
  struct HINSTANCE__ *v3; // rsi
  __int64 v4; // r12
  __int64 v5; // rdi
  LPCRITICAL_SECTION v6; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v9; // rcx
  DWORD v10; // ecx
  char *v11; // rax
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  bool v14; // zf
  int v15; // eax
  _QWORD *v16; // rbx
  __int64 *v17; // rax
  __int64 v18; // rsi
  __int64 v19; // rbx
  __int64 TlsPeerAddr; // rax
  LPCRITICAL_SECTION v21; // rax
  DWORD v22; // ecx
  __int64 *v23; // rax
  __int64 v24; // rcx
  DWORD v25; // ecx
  char *v26; // rax
  const WCHAR *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  void *v30; // rbx
  __int64 NatHash; // rax
  __int64 v32; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  BOOL v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  LPCRITICAL_SECTION v38; // rax
  DWORD v39; // ecx
  __int64 *v40; // rax
  __int64 v41; // rcx
  DWORD v42; // ecx
  char *v43; // rax
  const WCHAR *v44; // rdx
  int v45; // edi
  LPVOID lpMem[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  int v50; // [rsp+68h] [rbp-98h] BYREF
  int v51; // [rsp+6Ch] [rbp-94h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  char *v53; // [rsp+80h] [rbp-80h] BYREF
  int v54; // [rsp+88h] [rbp-78h]
  int v55; // [rsp+8Ch] [rbp-74h]
  char *v56; // [rsp+90h] [rbp-70h]
  int v57; // [rsp+98h] [rbp-68h]
  int v58; // [rsp+9Ch] [rbp-64h]
  __int64 *v59; // [rsp+A0h] [rbp-60h]
  __int64 v60; // [rsp+A8h] [rbp-58h]
  const WCHAR *v61; // [rsp+B0h] [rbp-50h]
  int v62; // [rsp+B8h] [rbp-48h]
  int v63; // [rsp+BCh] [rbp-44h]
  const char *v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  _DWORD v66[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v67; // [rsp+D8h] [rbp-28h]
  char *v68; // [rsp+E0h] [rbp-20h] BYREF
  int v69; // [rsp+E8h] [rbp-18h]
  int v70; // [rsp+ECh] [rbp-14h]
  int *v71; // [rsp+F0h] [rbp-10h]
  int v72; // [rsp+F8h] [rbp-8h]
  int v73; // [rsp+FCh] [rbp-4h]
  __int64 *v74; // [rsp+100h] [rbp+0h]
  __int64 v75; // [rsp+108h] [rbp+8h]
  const WCHAR *v76; // [rsp+110h] [rbp+10h]
  int v77; // [rsp+118h] [rbp+18h]
  int v78; // [rsp+11Ch] [rbp+1Ch]
  const char *v79; // [rsp+120h] [rbp+20h]
  __int64 v80; // [rsp+128h] [rbp+28h]

  v48 = LockSemaphore_low;
  v3 = a2;
  v4 = 0;
  v5 = -1;
  *(_OWORD *)lpMem = 0;
  if ( (unsigned int)dword_180173278 <= 5 )
    goto LABEL_20;
  LockSemaphore_low = qword_180173290;
  if ( (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v6 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v6 = gIkeExtGlobals;
LABEL_9:
    v9 = 0;
    goto LABEL_10;
  }
  v9 = *Value;
  v6 = gIkeExtGlobals;
LABEL_10:
  v49 = v9;
  v74 = &v49;
  v75 = 8;
  if ( !v6 )
    goto LABEL_18;
  v10 = (DWORD)v6[86].LockSemaphore;
  if ( v10 == -1 )
    goto LABEL_18;
  v11 = (char *)TlsGetValue(v10);
  v12 = (const WCHAR *)(v11 + 8);
  if ( !v11 )
    v12 = 0;
  if ( v12 )
  {
    v13 = -1;
    do
      v14 = v12[++v13] == 0;
    while ( !v14 );
    v15 = 2 * v13 + 2;
  }
  else
  {
LABEL_18:
    v12 = &LocaleName;
    v15 = 2;
  }
  v77 = v15;
  v66[1] = 5;
  v68 = off_180173280;
  v76 = v12;
  v78 = 0;
  v79 = "IkeOptionalConstructNatDisc";
  v80 = 28;
  v66[0] = 184549376;
  v67 = 1;
  v69 = *(unsigned __int16 *)off_180173280;
  v71 = &dword_180166EA4;
  v70 = 2;
  v72 = 45;
  v73 = 1;
  EtwEventWriteTransfer(qword_180173298, v66, 0, 0, 5, &v68);
LABEL_20:
  if ( !*((_DWORD *)v3 + 146) && ((_DWORD)v3[266] & 0x108) == 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( gIkeExtGlobals
        && (LockSemaphore_low = LODWORD(gIkeExtGlobals[86].LockSemaphore), (_DWORD)LockSemaphore_low != -1)
        && (v17 = (__int64 *)TlsGetValue(LockSemaphore_low), v16 = WPP_GLOBAL_Control, v17) )
      {
        v18 = *v17;
      }
      else
      {
        LODWORD(v18) = 0;
      }
      v19 = v16[2];
      TlsPeerAddr = IkeGetTlsPeerAddr(LockSemaphore_low);
      WPP_SF_iS(v19, 11, (unsigned int)WPP_57172ff675e53d91b4da64edae3854ff_Traceguids, v18, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
    {
LABEL_57:
      v30 = lpMem[1];
      goto LABEL_54;
    }
    v21 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v22 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v22 != -1 )
      {
        v23 = (__int64 *)TlsGetValue(v22);
        if ( v23 )
        {
          v24 = *v23;
          v21 = gIkeExtGlobals;
LABEL_38:
          v48 = v24;
          v59 = &v48;
          v60 = 8;
          if ( !v21 )
            goto LABEL_46;
          v25 = (DWORD)v21[86].LockSemaphore;
          if ( v25 == -1 )
            goto LABEL_46;
          v26 = (char *)TlsGetValue(v25);
          v27 = (const WCHAR *)(v26 + 8);
          if ( !v26 )
            v27 = 0;
          if ( v27 )
          {
            v28 = -1;
            do
              v14 = v27[++v28] == 0;
            while ( !v14 );
            v29 = 2 * v28 + 2;
          }
          else
          {
LABEL_46:
            v27 = &LocaleName;
            v29 = 2;
          }
          v62 = v29;
          v61 = v27;
          v64 = "Not creating NAT-D payloads.  Peer doesn't support it";
          v51 = 4;
          v53 = off_180173280;
          v63 = 0;
          v65 = 54;
          v50 = 184549376;
          v52 = 0;
          v54 = *(unsigned __int16 *)off_180173280;
          v56 = byte_1801650C3;
          v55 = 2;
          v57 = 50;
          v58 = 1;
          EtwEventWriteTransfer(qword_180173298, &v50, 0, 0, 5, &v53);
          v30 = lpMem[1];
          goto LABEL_54;
        }
        v21 = gIkeExtGlobals;
      }
    }
    v24 = 0;
    goto LABEL_38;
  }
  a2 = &_ImageBase;
  switch ( *((_BYTE *)v3 + 376) )
  {
    case 1:
    case 4:
    case 7:
      NatHash = GetNatHash(
                  (PUCHAR)v3 + 680,
                  (PUCHAR)v3 + 688,
                  (__int64)(v3 + 94),
                  (__int64)(v3 + 188),
                  0,
                  (_DWORD *)v3 + 146,
                  (__int64)lpMem);
      if ( NatHash )
      {
        v4 = NatHash;
        goto LABEL_57;
      }
      v30 = lpMem[1];
      v32 = IkeConstructNatDisc(v3, v48, lpMem[1], LOWORD(lpMem[0]));
      if ( !v32 )
      {
        WfpMemFree((LPCVOID *)&lpMem[1]);
        *(_OWORD *)lpMem = 0;
        v4 = GetNatHash(
               (PUCHAR)v3 + 680,
               (PUCHAR)v3 + 688,
               (__int64)(v3 + 94),
               (__int64)(v3 + 188),
               1,
               (_DWORD *)v3 + 146,
               (__int64)lpMem);
        if ( v4 )
          goto LABEL_57;
        v30 = lpMem[1];
        v32 = IkeConstructNatDisc(v3, v48, lpMem[1], LOWORD(lpMem[0]));
      }
      v4 = v32;
      break;
    case 5:
    case 6:
    case 8:
      goto LABEL_57;
    default:
      __fastfail(5u);
  }
LABEL_54:
  if ( (Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( gWfpTrackHeapAllocs && v30 && _InterlockedDecrement(&gWfpNumHeapAllocs) < 0 )
    {
      if ( !gMisalignedHeapTelemFired )
      {
        if ( gWfpNumHeapAllocs <= 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs(LockSemaphore_low, a2, a3);
        gMisalignedHeapTelemFired = 1;
      }
      _InterlockedIncrement(&gWfpNumHeapAllocs);
    }
    else
    {
      v34 = HeapFree(gWfpHeap, 0, v30);
      if ( !gHeapFreeFailedFired && !v34 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v36, v35, v37);
        gHeapFreeFailedFired = 1;
      }
    }
  }
  else
  {
    if ( gWfpTrackHeapBytes && v30 )
      _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v30));
    HeapFree(gWfpHeap, 0, v30);
  }
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v38 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v39 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v39 != -1 )
      {
        v40 = (__int64 *)TlsGetValue(v39);
        if ( v40 )
        {
          v41 = *v40;
          v38 = gIkeExtGlobals;
LABEL_84:
          v49 = v41;
          v59 = &v49;
          v60 = 8;
          if ( !v38 )
            goto LABEL_91;
          v42 = (DWORD)v38[86].LockSemaphore;
          if ( v42 == -1 )
            goto LABEL_91;
          v43 = (char *)TlsGetValue(v42);
          v44 = (const WCHAR *)(v43 + 8);
          if ( !v43 )
            v44 = 0;
          if ( v44 )
          {
            do
              v14 = v44[++v5] == 0;
            while ( !v14 );
            v45 = 2 * v5 + 2;
          }
          else
          {
LABEL_91:
            v44 = &LocaleName;
            v45 = 2;
          }
          v51 = 5;
          v53 = off_180173280;
          v62 = v45;
          v61 = v44;
          v63 = 0;
          v64 = "IkeOptionalConstructNatDisc";
          v65 = 28;
          v50 = 184549376;
          v52 = 1;
          v54 = *(unsigned __int16 *)off_180173280;
          v56 = byte_180166E6B;
          v55 = 2;
          v57 = 45;
          v58 = 1;
          EtwEventWriteTransfer(qword_180173298, &v50, 0, 0, 5, &v53);
          return IkeReturnError(v4, "IkeOptionalConstructNatDisc");
        }
        v38 = gIkeExtGlobals;
      }
    }
    v41 = 0;
    goto LABEL_84;
  }
  return IkeReturnError(v4, "IkeOptionalConstructNatDisc");
}

```

## disassembly

```asm
0x180047450  mov     [rsp-8+arg_10], rbx
0x180047455  push    rbp
0x180047456  push    rsi
0x180047457  push    rdi
0x180047458  push    r12
0x18004745a  push    r13
0x18004745c  push    r14
0x18004745e  push    r15
0x180047460  lea     rbp, [rsp-40h]
0x180047465  sub     rsp, 140h
0x18004746c  mov     rax, cs:__security_cookie
0x180047473  xor     rax, rsp
0x180047476  mov     [rbp+70h+var_40], rax
0x18004747a  mov     eax, cs:dword_180173278
0x180047480  lea     rbx, aIkeoptionalcon_5; "IkeOptionalConstructNatDisc"
0x180047487  xor     r15d, r15d
0x18004748a  mov     [rsp+170h+var_118], rcx
0x18004748f  lea     r13, _TraceLoggingMetadata
0x180047496  xorps   xmm0, xmm0
0x180047499  mov     rsi, rdx
0x18004749c  mov     r12d, r15d
0x18004749f  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800474a6  movups  xmmword ptr [rsp+170h+lpMem], xmm0
0x1800474ab  cmp     eax, 5
0x1800474ae  jbe     loc_18004760C
0x1800474b4  mov     rcx, cs:qword_180173290
0x1800474bb  mov     rax, cs:qword_180173288
0x1800474c2  test    al, 1
0x1800474c4  jz      loc_18004760C
0x1800474ca  mov     rax, rcx
0x1800474cd  and     eax, 1
0x1800474d0  cmp     rax, rcx
0x1800474d3  jnz     loc_18004760C
0x1800474d9  mov     rax, cs:gIkeExtGlobals
0x1800474e0  test    rax, rax
0x1800474e3  jz      short loc_18004750E
0x1800474e5  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800474eb  cmp     ecx, 0FFFFFFFFh
0x1800474ee  jz      short loc_18004750E
0x1800474f0  call    cs:__imp_TlsGetValue
0x1800474f6  test    rax, rax
0x1800474f9  jz      short loc_180047507
0x1800474fb  mov     rcx, [rax]
0x1800474fe  mov     rax, cs:gIkeExtGlobals
0x180047505  jmp     short loc_180047511
0x180047507  mov     rax, cs:gIkeExtGlobals
0x18004750e  mov     rcx, r15
0x180047511  mov     [rsp+170h+var_110], rcx
0x180047516  lea     rcx, [rsp+170h+var_110]
0x18004751b  mov     [rbp+70h+var_70], rcx
0x18004751f  mov     [rbp+70h+var_68], 8
0x180047527  test    rax, rax
0x18004752a  jz      short loc_180047565
0x18004752c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180047532  cmp     ecx, 0FFFFFFFFh
0x180047535  jz      short loc_180047565
0x180047537  call    cs:__imp_TlsGetValue
0x18004753d  test    rax, rax
0x180047540  lea     rdx, [rax+8]
0x180047544  cmovz   rdx, r15
0x180047548  test    rdx, rdx
0x18004754b  jz      short loc_180047565
0x18004754d  mov     rax, rdi
0x180047550  cmp     [rdx+rax*2+2], r15w
0x180047556  lea     rax, [rax+1]
0x18004755a  jnz     short loc_180047550
0x18004755c  lea     eax, ds:2[rax*2]
0x180047563  jmp     short loc_180047571
0x180047565  lea     rdx, LocaleName
0x18004756c  mov     eax, 2
0x180047571  mov     [rbp+70h+var_58], eax
0x180047574  xor     r9d, r9d
0x180047577  movzx   eax, cs:word_180166E9A
0x18004757e  xor     r8d, r8d
0x180047581  mov     [rbp+70h+var_9C], eax
0x180047584  mov     rax, cs:off_180173280
0x18004758b  mov     [rbp+70h+var_90], rax
0x18004758f  mov     [rbp+70h+var_60], rdx
0x180047593  lea     rdx, [rbp+70h+var_A0]
0x180047597  mov     [rbp+70h+var_54], r15d
0x18004759b  mov     [rbp+70h+var_50], rbx
0x18004759f  mov     [rbp+70h+var_48], 1Ch
0x1800475a7  mov     [rbp+70h+var_A0], 0B000000h
0x1800475ae  mov     [rbp+70h+var_98], 1
0x1800475b6  movzx   eax, word ptr [rax]
0x1800475b9  mov     [rbp+70h+var_88], eax
0x1800475bc  lea     rax, dword_180166EA4
0x1800475c3  mov     [rbp+70h+var_80], rax
0x1800475c7  lea     rax, _TraceLoggingMetadataEnd
0x1800475ce  sub     eax, r13d
0x1800475d1  mov     [rbp+70h+var_84], 2
0x1800475d8  mov     [rbp+70h+var_78], 2Dh ; '-'
0x1800475df  mov     [rbp+70h+var_74], 1
0x1800475e6  mov     [rsp+170h+var_130], eax
0x1800475ea  mov     eax, [rsp+170h+var_130]
0x1800475ee  mov     rcx, cs:qword_180173298
0x1800475f5  lea     rax, [rbp+70h+var_90]
0x1800475f9  mov     [rsp+170h+var_148], rax
0x1800475fe  mov     [rsp+170h+var_150], 5
0x180047606  call    cs:__imp_EtwEventWriteTransfer
0x18004760c  lea     r14, [rsi+248h]
0x180047613  cmp     [r14], r15d
0x180047616  jnz     loc_180047800
0x18004761c  test    dword ptr [rsi+428h], 108h
0x180047626  jnz     loc_180047800
0x18004762c  mov     rbx, cs:WPP_GLOBAL_Control
0x180047633  lea     rax, WPP_GLOBAL_Control
0x18004763a  cmp     rbx, rax
0x18004763d  jz      short loc_1800476A1
0x18004763f  cmp     byte ptr [rbx+19h], 4
0x180047643  jb      short loc_1800476A1
0x180047645  test    byte ptr [rbx+1Ch], 10h
0x180047649  jz      short loc_1800476A1
0x18004764b  mov     rax, cs:gIkeExtGlobals
0x180047652  test    rax, rax
0x180047655  jz      short loc_180047679
0x180047657  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18004765d  cmp     ecx, 0FFFFFFFFh
0x180047660  jz      short loc_180047679
0x180047662  call    cs:__imp_TlsGetValue
0x180047668  mov     rbx, cs:WPP_GLOBAL_Control
0x18004766f  test    rax, rax
0x180047672  jz      short loc_180047679
0x180047674  mov     rsi, [rax]
0x180047677  jmp     short loc_18004767C
0x180047679  mov     rsi, r15
0x18004767c  mov     rbx, [rbx+10h]
0x180047680  call    IkeGetTlsPeerAddr
0x180047685  mov     edx, 0Bh
0x18004768a  mov     qword ptr [rsp+170h+var_150], rax
0x18004768f  mov     r9, rsi
0x180047692  lea     r8, WPP_57172ff675e53d91b4da64edae3854ff_Traceguids
0x180047699  mov     rcx, rbx
0x18004769c  call    WPP_SF_iS
0x1800476a1  mov     eax, cs:dword_180173278
0x1800476a7  cmp     eax, 4
0x1800476aa  jbe     loc_18004790E; jumptable 0000000180047825 cases 5,6,8
0x1800476b0  mov     rax, cs:gIkeExtGlobals
0x1800476b7  test    rax, rax
0x1800476ba  jz      short loc_1800476E5
0x1800476bc  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800476c2  cmp     ecx, 0FFFFFFFFh
0x1800476c5  jz      short loc_1800476E5
0x1800476c7  call    cs:__imp_TlsGetValue
0x1800476cd  test    rax, rax
0x1800476d0  jz      short loc_1800476DE
0x1800476d2  mov     rcx, [rax]
0x1800476d5  mov     rax, cs:gIkeExtGlobals
0x1800476dc  jmp     short loc_1800476E8
0x1800476de  mov     rax, cs:gIkeExtGlobals
0x1800476e5  mov     rcx, r15
0x1800476e8  mov     [rsp+170h+var_118], rcx
0x1800476ed  lea     rcx, [rsp+170h+var_118]
0x1800476f2  mov     [rbp+70h+var_D0], rcx
0x1800476f6  mov     [rbp+70h+var_C8], 8
0x1800476fe  test    rax, rax
0x180047701  jz      short loc_180047745
0x180047703  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180047709  cmp     ecx, 0FFFFFFFFh
0x18004770c  jz      short loc_180047745
0x18004770e  call    cs:__imp_TlsGetValue
0x180047714  test    rax, rax
0x180047717  lea     rdx, [rax+8]
0x18004771b  cmovz   rdx, r15
0x18004771f  test    rdx, rdx
0x180047722  jz      short loc_180047745
0x180047724  mov     rax, rdi
0x180047727  nop     word ptr [rax+rax+00000000h]
0x180047730  cmp     [rdx+rax*2+2], r15w
0x180047736  lea     rax, [rax+1]
0x18004773a  jnz     short loc_180047730
0x18004773c  lea     eax, ds:2[rax*2]
0x180047743  jmp     short loc_180047751
0x180047745  lea     rdx, LocaleName
0x18004774c  mov     eax, 2
0x180047751  mov     [rbp+70h+var_B8], eax
0x180047754  lea     rsi, _TraceLoggingMetadataEnd
0x18004775b  mov     [rbp+70h+var_C0], rdx
0x18004775f  lea     rax, aNotCreatingNat; "Not creating NAT-D payloads.  Peer does"...
0x180047766  mov     [rbp+70h+var_B0], rax
0x18004776a  lea     rdx, [rsp+170h+var_108]
0x18004776f  movzx   eax, cs:word_1801650B9
0x180047776  xor     r9d, r9d
0x180047779  mov     [rsp+170h+var_104], eax
0x18004777d  xor     r8d, r8d
0x180047780  mov     rax, cs:off_180173280
0x180047787  mov     [rbp+70h+var_F0], rax
0x18004778b  mov     [rbp+70h+var_B4], r15d
0x18004778f  mov     [rbp+70h+var_A8], 36h ; '6'
0x180047797  mov     [rsp+170h+var_108], 0B000000h
0x18004779f  mov     [rsp+170h+var_100], r15
0x1800477a4  movzx   eax, word ptr [rax]
0x1800477a7  mov     [rbp+70h+var_E8], eax
0x1800477aa  lea     rax, byte_1801650C3
0x1800477b1  mov     [rbp+70h+var_E0], rax
0x1800477b5  mov     rax, rsi
0x1800477b8  sub     eax, r13d
0x1800477bb  mov     [rbp+70h+var_E4], 2
0x1800477c2  mov     [rbp+70h+var_D8], 32h ; '2'
0x1800477c9  mov     [rbp+70h+var_D4], 1
0x1800477d0  mov     [rsp+170h+var_130], eax
0x1800477d4  mov     eax, [rsp+170h+var_130]
0x1800477d8  mov     rcx, cs:qword_180173298
0x1800477df  lea     rax, [rbp+70h+var_F0]
0x1800477e3  mov     [rsp+170h+var_148], rax
0x1800477e8  mov     [rsp+170h+var_150], 5
0x1800477f0  call    cs:__imp_EtwEventWriteTransfer
0x1800477f6  mov     rbx, [rsp+170h+lpMem+8]
0x1800477fb  jmp     loc_1800478FC
0x180047800  movzx   eax, byte ptr [rsi+178h]
0x180047807  dec     eax; switch 8 cases
0x180047809  cmp     eax, 7
0x18004780c  ja      def_180047825; jumptable 0000000180047825 default case, cases 2,3
0x180047812  lea     rdx, __ImageBase
0x180047819  cdqe
0x18004781b  mov     ecx, ds:(jpt_180047825 - 180000000h)[rdx+rax*4]
0x180047822  add     rcx, rdx
0x180047825  jmp     rcx; switch jump
0x180047827  lea     rcx, [rsp+170h+lpMem]; jumptable 0000000180047825 cases 1,4,7
0x18004782c  mov     [rsp+170h+var_140], rcx; __int64
0x180047831  lea     r9, [rsi+2F0h]
0x180047838  mov     [rsp+170h+var_148], r14; __int64
0x18004783d  lea     rcx, [rsi+2A8h]; pbInput
0x180047844  lea     r8, [rsi+178h]
0x18004784b  mov     [rsp+170h+var_150], r15d; int
0x180047850  lea     rdx, [rsi+2B0h]; PUCHAR
0x180047857  call    GetNatHash
0x18004785c  test    rax, rax
0x18004785f  jnz     loc_18004790B
0x180047865  mov     rbx, [rsp+170h+lpMem+8]
0x18004786a  mov     rcx, rsi
0x18004786d  movzx   r9d, word ptr [rsp+170h+lpMem]
0x180047873  mov     r8, rbx
0x180047876  mov     rdx, [rsp+170h+var_118]
0x18004787b  call    IkeConstructNatDisc
0x180047880  test    rax, rax
0x180047883  jnz     short loc_1800478F2
0x180047885  lea     rcx, [rsp+170h+lpMem+8]
0x18004788a  call    WfpMemFree
0x18004788f  lea     rax, [rsp+170h+lpMem]
0x180047894  xorps   xmm0, xmm0
0x180047897  mov     [rsp+170h+var_140], rax; __int64
0x18004789c  lea     r9, [rsi+2F0h]
0x1800478a3  mov     [rsp+170h+var_148], r14; __int64
0x1800478a8  lea     r8, [rsi+178h]
0x1800478af  lea     rdx, [rsi+2B0h]; PUCHAR
0x1800478b6  mov     [rsp+170h+var_150], 1; int
0x1800478be  lea     rcx, [rsi+2A8h]; pbInput
0x1800478c5  movups  xmmword ptr [rsp+170h+lpMem], xmm0
0x1800478ca  call    GetNatHash
0x1800478cf  mov     r12, rax
0x1800478d2  test    rax, rax
0x1800478d5  jnz     short loc_18004790E; jumptable 0000000180047825 cases 5,6,8
0x1800478d7  mov     rbx, [rsp+170h+lpMem+8]
0x1800478dc  mov     rcx, rsi
0x1800478df  movzx   r9d, word ptr [rsp+170h+lpMem]
0x1800478e5  mov     r8, rbx
0x1800478e8  mov     rdx, [rsp+170h+var_118]
0x1800478ed  call    IkeConstructNatDisc
0x1800478f2  mov     r12, rax
0x1800478f5  lea     rsi, _TraceLoggingMetadataEnd
0x1800478fc  mov     eax, cs:Feature_BFE_MemAlloc_BugFixes_25B__private_featureState
0x180047902  test    al, 10h
0x180047904  jz      short loc_180047915
0x180047906  and     eax, 1
0x180047909  jmp     short loc_18004791A
0x18004790b  mov     r12, rax
0x18004790e  mov     rbx, [rsp+170h+lpMem+8]; jumptable 0000000180047825 cases 5,6,8
0x180047913  jmp     short loc_1800478F5
0x180047915  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageNoInline
0x18004791a  test    eax, eax
0x18004791c  jz      short loc_180047995
0x18004791e  cmp     cs:gWfpTrackHeapAllocs, r15d
0x180047925  jz      short loc_180047965
0x180047927  test    rbx, rbx
0x18004792a  jz      short loc_180047965
0x18004792c  mov     eax, edi
0x18004792e  lock xadd cs:gWfpNumHeapAllocs, eax
0x180047936  cmp     eax, 1
0x180047939  jns     short loc_180047965
0x18004793b  cmp     cs:gMisalignedHeapTelemFired, r15d
0x180047942  jnz     short loc_18004795C
0x180047944  cmp     cs:gWfpNumHeapAllocs, r15d
0x18004794b  jg      short loc_180047952
0x18004794d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gWfpNumHeapAllocs > 0", "allocs and frees are out of sync")
0x180047952  mov     cs:gMisalignedHeapTelemFired, 1
0x18004795c  lock inc cs:gWfpNumHeapAllocs
0x180047963  jmp     short loc_1800479D0
0x180047965  mov     rcx, cs:gWfpHeap; hHeap
0x18004796c  mov     r8, rbx; lpMem
0x18004796f  xor     edx, edx; dwFlags
0x180047971  call    cs:__imp_HeapFree
0x180047977  cmp     cs:gHeapFreeFailedFired, r15d
0x18004797e  jnz     short loc_1800479D0
0x180047980  test    eax, eax
0x180047982  jnz     short loc_1800479D0
0x180047984  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success", "HeapFree failed")
0x180047989  mov     cs:gHeapFreeFailedFired, 1
0x180047993  jmp     short loc_1800479D0
0x180047995  cmp     cs:gWfpTrackHeapBytes, r15d
  ... truncated ...
```
