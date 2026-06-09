# IkeMoveMMToZombieList

- ea: `0x1800190d0`
- end: `0x18001965f`
- name: `IkeMoveMMToZombieList`
- size: `1423`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180019030`
- `0x18002a86c`

## callees

- `0x1800190d0`
- `0x180025d88`
- `0x18004890c`
- `0x180050850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019167`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800191ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800192ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001935b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800193a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001951a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001955f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180019167`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800191ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800192ea`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001935b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800193a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001951a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001955f`
- `ntdll!EtwEventWriteTransfer` at `0x180019280`
- `ntdll!EtwEventWriteTransfer` at `0x180019488`
- `ntdll!EtwEventWriteTransfer` at `0x180019637`
- `ntdll!EtwEventWriteTransfer` at `0x180019280`
- `ntdll!EtwEventWriteTransfer` at `0x180019488`
- `ntdll!EtwEventWriteTransfer` at `0x180019637`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800194c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800194c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019291`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019291`

## string_xrefs

- `0x1800190fd`: `IkeMoveMMToZombieList`
- `0x1800195a5`: `IkeMoveMMToZombieList`

## pseudocode

```c
__int64 __fastcall IkeMoveMMToZombieList(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdi
  LPCRITICAL_SECTION v4; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v7; // rcx
  DWORD v8; // ecx
  char *v9; // rax
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  bool v12; // zf
  int v13; // eax
  __int64 LockSemaphore_low; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // r14
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
  LONG *p_LockCount; // rax
  LPCRITICAL_SECTION *OwningThread; // rcx
  LPCRITICAL_SECTION v32; // rax
  DWORD v33; // ecx
  __int64 *v34; // rax
  __int64 v35; // rcx
  DWORD v36; // ecx
  char *v37; // rax
  const WCHAR *v38; // rdx
  int v39; // edi
  __int64 v41; // [rsp+38h] [rbp-81h] BYREF
  char *v42; // [rsp+40h] [rbp-79h] BYREF
  int v43; // [rsp+48h] [rbp-71h]
  int v44; // [rsp+4Ch] [rbp-6Dh]
  char *v45; // [rsp+50h] [rbp-69h]
  int v46; // [rsp+58h] [rbp-61h]
  int v47; // [rsp+5Ch] [rbp-5Dh]
  __int64 *v48; // [rsp+60h] [rbp-59h]
  __int64 v49; // [rsp+68h] [rbp-51h]
  const WCHAR *v50; // [rsp+70h] [rbp-49h]
  int v51; // [rsp+78h] [rbp-41h]
  int v52; // [rsp+7Ch] [rbp-3Dh]
  const char *v53; // [rsp+80h] [rbp-39h]
  __int64 v54; // [rsp+88h] [rbp-31h]
  _QWORD *v55; // [rsp+90h] [rbp-29h]
  __int64 v56; // [rsp+98h] [rbp-21h]
  _QWORD v57[2]; // [rsp+A0h] [rbp-19h] BYREF
  int v58; // [rsp+B0h] [rbp-9h] BYREF
  int v59; // [rsp+B4h] [rbp-5h]
  __int64 v60; // [rsp+B8h] [rbp-1h]

  v2 = 0;
  v3 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v4 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v4 = gIkeExtGlobals;
LABEL_9:
    v7 = 0;
    goto LABEL_10;
  }
  v7 = *Value;
  v4 = gIkeExtGlobals;
LABEL_10:
  v41 = v7;
  v48 = &v41;
  v49 = 8;
  if ( !v4 )
    goto LABEL_18;
  v8 = (DWORD)v4[86].LockSemaphore;
  if ( v8 == -1 )
    goto LABEL_18;
  v9 = (char *)TlsGetValue(v8);
  v10 = (const WCHAR *)(v9 + 8);
  if ( !v9 )
    v10 = 0;
  if ( v10 )
  {
    v11 = -1;
    do
      v12 = v10[++v11] == 0;
    while ( !v12 );
    v13 = 2 * v11 + 2;
  }
  else
  {
LABEL_18:
    v10 = &LocaleName;
    v13 = 2;
  }
  v51 = v13;
  v42 = off_180173280;
  v50 = v10;
  v52 = 0;
  v53 = "IkeMoveMMToZombieList";
  v54 = 22;
  v57[0] = 0x50B000000LL;
  v57[1] = 1;
  v43 = *(unsigned __int16 *)off_180173280;
  v45 = (char *)&dword_180166EA4;
  v44 = 2;
  v46 = 45;
  v47 = 1;
  EtwEventWriteTransfer(qword_180173298, v57, 0, 0, 5, &v42);
LABEL_20:
  EnterCriticalSection(gIkeExtGlobals + 3);
  v15 = (struct _RTL_CRITICAL_SECTION *)(a1 + 544);
  if ( *(_QWORD *)(a1 + 544) || *(_QWORD *)(a1 + 552) )
    goto LABEL_51;
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
    WPP_SF_iSq(v19, 11, (unsigned int)WPP_27bc70e61d40360834a5a0166f146b13_Traceguids, v18, TlsPeerAddr, a1);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
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
          v41 = v24;
          v48 = &v41;
          v49 = 8;
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
              v12 = v27[++v28] == 0;
            while ( !v12 );
            v29 = 2 * v28 + 2;
          }
          else
          {
LABEL_46:
            v27 = &LocaleName;
            v29 = 2;
          }
          v51 = v29;
          v50 = v27;
          v53 = "Moving mmSa to zombie list";
          v52 = 0;
          v55 = v57;
          v59 = 4;
          v42 = off_180173280;
          v54 = 27;
          v57[0] = a1;
          v56 = 8;
          v58 = 184549376;
          v60 = 0;
          v43 = *(unsigned __int16 *)off_180173280;
          v45 = byte_180152E2D;
          v44 = 2;
          v46 = 62;
          v47 = 1;
          EtwEventWriteTransfer(qword_180173298, &v58, 0, 0, 6, &v42);
          goto LABEL_48;
        }
        v21 = gIkeExtGlobals;
      }
    }
    v24 = 0;
    goto LABEL_38;
  }
LABEL_48:
  p_LockCount = &gIkeExtGlobals[4].LockCount;
  OwningThread = (LPCRITICAL_SECTION *)gIkeExtGlobals[4].OwningThread;
  if ( *OwningThread != (LPCRITICAL_SECTION)&gIkeExtGlobals[4].LockCount )
    __fastfail(3u);
  v15->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)p_LockCount;
  v2 = 1;
  *(_QWORD *)(a1 + 552) = OwningThread;
  *OwningThread = v15;
  *((_QWORD *)p_LockCount + 1) = v15;
LABEL_51:
  LeaveCriticalSection(gIkeExtGlobals + 3);
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return v2;
  v32 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_59;
  v33 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v33 == -1 )
    goto LABEL_59;
  v34 = (__int64 *)TlsGetValue(v33);
  if ( !v34 )
  {
    v32 = gIkeExtGlobals;
LABEL_59:
    v35 = 0;
    goto LABEL_60;
  }
  v35 = *v34;
  v32 = gIkeExtGlobals;
LABEL_60:
  v57[0] = v35;
  v48 = v57;
  v49 = 8;
  if ( !v32 )
    goto LABEL_67;
  v36 = (DWORD)v32[86].LockSemaphore;
  if ( v36 == -1 )
    goto LABEL_67;
  v37 = (char *)TlsGetValue(v36);
  v38 = (const WCHAR *)(v37 + 8);
  if ( !v37 )
    v38 = 0;
  if ( v38 )
  {
    do
      v12 = v38[++v3] == 0;
    while ( !v12 );
    v39 = 2 * v3 + 2;
  }
  else
  {
LABEL_67:
    v38 = &LocaleName;
    v39 = 2;
  }
  v50 = v38;
  v53 = "IkeMoveMMToZombieList";
  v59 = 5;
  v42 = off_180173280;
  v51 = v39;
  v52 = 0;
  v54 = 22;
  v58 = 184549376;
  v60 = 1;
  v43 = *(unsigned __int16 *)off_180173280;
  v45 = byte_180166E6B;
  v44 = 2;
  v46 = 45;
  v47 = 1;
  EtwEventWriteTransfer(qword_180173298, &v58, 0, 0, 5, &v42);
  return v2;
}

```

## disassembly

```asm
0x1800190d0  push    rbp
0x1800190d2  push    rbx
0x1800190d3  push    rsi
0x1800190d4  push    rdi
0x1800190d5  push    r12
0x1800190d7  push    r13
0x1800190d9  push    r14
0x1800190db  push    r15
0x1800190dd  lea     rbp, [rsp-1Fh]
0x1800190e2  sub     rsp, 0D8h
0x1800190e9  mov     rax, cs:__security_cookie
0x1800190f0  xor     rax, rsp
0x1800190f3  mov     [rbp+57h+var_50], rax
0x1800190f7  mov     eax, cs:dword_180173278
0x1800190fd  lea     r14, aIkemovemmtozom; "IkeMoveMMToZombieList"
0x180019104  xor     r13d, r13d
0x180019107  lea     r12, _TraceLoggingMetadataEnd
0x18001910e  lea     rsi, _TraceLoggingMetadata
0x180019115  mov     r15, rcx
0x180019118  mov     ebx, r13d
0x18001911b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180019122  cmp     eax, 5
0x180019125  jbe     loc_180019286
0x18001912b  mov     rcx, cs:qword_180173290
0x180019132  mov     rax, cs:qword_180173288
0x180019139  test    al, 1
0x18001913b  jz      loc_180019286
0x180019141  mov     rax, rcx
0x180019144  and     eax, 1
0x180019147  cmp     rax, rcx
0x18001914a  jnz     loc_180019286
0x180019150  mov     rax, cs:gIkeExtGlobals
0x180019157  test    rax, rax
0x18001915a  jz      short loc_180019185
0x18001915c  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180019162  cmp     ecx, 0FFFFFFFFh
0x180019165  jz      short loc_180019185
0x180019167  call    cs:__imp_TlsGetValue
0x18001916d  test    rax, rax
0x180019170  jz      short loc_18001917E
0x180019172  mov     rcx, [rax]
0x180019175  mov     rax, cs:gIkeExtGlobals
0x18001917c  jmp     short loc_180019188
0x18001917e  mov     rax, cs:gIkeExtGlobals
0x180019185  mov     rcx, r13
0x180019188  mov     [rsp+110h+var_D8], rcx
0x18001918d  lea     rcx, [rsp+110h+var_D8]
0x180019192  mov     [rbp+57h+var_B0], rcx
0x180019196  mov     [rbp+57h+var_A8], 8
0x18001919e  test    rax, rax
0x1800191a1  jz      short loc_1800191E4
0x1800191a3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800191a9  cmp     ecx, 0FFFFFFFFh
0x1800191ac  jz      short loc_1800191E4
0x1800191ae  call    cs:__imp_TlsGetValue
0x1800191b4  test    rax, rax
0x1800191b7  lea     rdx, [rax+8]
0x1800191bb  cmovz   rdx, r13
0x1800191bf  test    rdx, rdx
0x1800191c2  jz      short loc_1800191E4
0x1800191c4  mov     rax, rdi
0x1800191c7  nop     word ptr [rax+rax+00000000h]
0x1800191d0  cmp     [rdx+rax*2+2], bx
0x1800191d5  lea     rax, [rax+1]
0x1800191d9  jnz     short loc_1800191D0
0x1800191db  lea     eax, ds:2[rax*2]
0x1800191e2  jmp     short loc_1800191F0
0x1800191e4  lea     rdx, LocaleName
0x1800191eb  mov     eax, 2
0x1800191f0  mov     [rbp+57h+var_98], eax
0x1800191f3  xor     r9d, r9d
0x1800191f6  movzx   eax, cs:word_180166E9A
0x1800191fd  xor     r8d, r8d
0x180019200  mov     dword ptr [rbp+57h+var_70+4], eax
0x180019203  mov     rax, cs:off_180173280
0x18001920a  mov     [rbp+57h+var_D0], rax
0x18001920e  mov     [rbp+57h+var_A0], rdx
0x180019212  lea     rdx, [rbp+57h+var_70]
0x180019216  mov     [rbp+57h+var_94], r13d
0x18001921a  mov     [rbp+57h+var_90], r14
0x18001921e  mov     [rbp+57h+var_88], 16h
0x180019226  mov     dword ptr [rbp+57h+var_70], 0B000000h
0x18001922d  mov     [rbp+57h+var_68], 1
0x180019235  movzx   eax, word ptr [rax]
0x180019238  mov     [rbp+57h+var_C8], eax
0x18001923b  lea     rax, dword_180166EA4
0x180019242  mov     [rbp+57h+var_C0], rax
0x180019246  mov     rax, r12
0x180019249  sub     eax, esi
0x18001924b  mov     [rbp+57h+var_C4], 2
0x180019252  mov     [rbp+57h+var_B8], 2Dh ; '-'
0x180019259  mov     [rbp+57h+var_B4], 1
0x180019260  mov     [rsp+110h+var_E0], eax
0x180019264  mov     eax, [rsp+110h+var_E0]
0x180019268  mov     rcx, cs:qword_180173298
0x18001926f  lea     rax, [rbp+57h+var_D0]
0x180019273  mov     [rsp+110h+var_E8], rax
0x180019278  mov     dword ptr [rsp+110h+var_F0], 5
0x180019280  call    cs:__imp_EtwEventWriteTransfer
0x180019286  mov     rcx, cs:gIkeExtGlobals
0x18001928d  add     rcx, 78h ; 'x'; lpCriticalSection
0x180019291  call    cs:__imp_EnterCriticalSection
0x180019297  lea     r14, [r15+220h]
0x18001929e  cmp     [r14], rbx
0x1800192a1  jnz     loc_1800194BE
0x1800192a7  cmp     [r15+228h], rbx
0x1800192ae  jnz     loc_1800194BE
0x1800192b4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800192bb  lea     rax, WPP_GLOBAL_Control
0x1800192c2  cmp     rbx, rax
0x1800192c5  jz      short loc_180019335
0x1800192c7  cmp     byte ptr [rbx+19h], 4
0x1800192cb  jb      short loc_180019335
0x1800192cd  test    byte ptr [rbx+1Ch], 10h
0x1800192d1  jz      short loc_180019335
0x1800192d3  mov     rax, cs:gIkeExtGlobals
0x1800192da  test    rax, rax
0x1800192dd  jz      short loc_180019301
0x1800192df  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800192e5  cmp     ecx, 0FFFFFFFFh
0x1800192e8  jz      short loc_180019301
0x1800192ea  call    cs:__imp_TlsGetValue
0x1800192f0  mov     rbx, cs:WPP_GLOBAL_Control
0x1800192f7  test    rax, rax
0x1800192fa  jz      short loc_180019301
0x1800192fc  mov     rsi, [rax]
0x1800192ff  jmp     short loc_180019304
0x180019301  mov     rsi, r13
0x180019304  mov     rbx, [rbx+10h]
0x180019308  call    IkeGetTlsPeerAddr
0x18001930d  mov     edx, 0Bh
0x180019312  mov     [rsp+110h+var_E8], r15
0x180019317  mov     r9, rsi
0x18001931a  mov     [rsp+110h+var_F0], rax
0x18001931f  lea     r8, WPP_27bc70e61d40360834a5a0166f146b13_Traceguids
0x180019326  mov     rcx, rbx
0x180019329  call    WPP_SF_iSq
0x18001932e  lea     rsi, _TraceLoggingMetadata
0x180019335  mov     eax, cs:dword_180173278
0x18001933b  cmp     eax, 4
0x18001933e  jbe     loc_18001948E
0x180019344  mov     rax, cs:gIkeExtGlobals
0x18001934b  test    rax, rax
0x18001934e  jz      short loc_180019379
0x180019350  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180019356  cmp     ecx, 0FFFFFFFFh
0x180019359  jz      short loc_180019379
0x18001935b  call    cs:__imp_TlsGetValue
0x180019361  test    rax, rax
0x180019364  jz      short loc_180019372
0x180019366  mov     rcx, [rax]
0x180019369  mov     rax, cs:gIkeExtGlobals
0x180019370  jmp     short loc_18001937C
0x180019372  mov     rax, cs:gIkeExtGlobals
0x180019379  mov     rcx, r13
0x18001937c  mov     [rsp+110h+var_D8], rcx
0x180019381  lea     rcx, [rsp+110h+var_D8]
0x180019386  mov     [rbp+57h+var_B0], rcx
0x18001938a  mov     [rbp+57h+var_A8], 8
0x180019392  test    rax, rax
0x180019395  jz      short loc_1800193D5
0x180019397  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001939d  cmp     ecx, 0FFFFFFFFh
0x1800193a0  jz      short loc_1800193D5
0x1800193a2  call    cs:__imp_TlsGetValue
0x1800193a8  test    rax, rax
0x1800193ab  lea     rdx, [rax+8]
0x1800193af  cmovz   rdx, r13
0x1800193b3  test    rdx, rdx
0x1800193b6  jz      short loc_1800193D5
0x1800193b8  mov     rax, rdi
0x1800193bb  nop     dword ptr [rax+rax+00h]
0x1800193c0  cmp     [rdx+rax*2+2], r13w
0x1800193c6  lea     rax, [rax+1]
0x1800193ca  jnz     short loc_1800193C0
0x1800193cc  lea     eax, ds:2[rax*2]
0x1800193d3  jmp     short loc_1800193E1
0x1800193d5  lea     rdx, LocaleName
0x1800193dc  mov     eax, 2
0x1800193e1  mov     [rbp+57h+var_98], eax
0x1800193e4  xor     r9d, r9d
0x1800193e7  mov     [rbp+57h+var_A0], rdx
0x1800193eb  lea     rax, aMovingMmsaToZo; "Moving mmSa to zombie list"
0x1800193f2  mov     [rbp+57h+var_90], rax
0x1800193f6  lea     rdx, [rbp+57h+var_60]
0x1800193fa  lea     rax, [rbp+57h+var_70]
0x1800193fe  mov     [rbp+57h+var_94], r13d
0x180019402  mov     [rbp+57h+var_80], rax
0x180019406  xor     r8d, r8d
0x180019409  movzx   eax, cs:word_180152E23
0x180019410  mov     [rbp+57h+var_5C], eax
0x180019413  mov     rax, cs:off_180173280
0x18001941a  mov     [rbp+57h+var_D0], rax
0x18001941e  mov     [rbp+57h+var_88], 1Bh
0x180019426  mov     [rbp+57h+var_70], r15
0x18001942a  mov     [rbp+57h+var_78], 8
0x180019432  mov     [rbp+57h+var_60], 0B000000h
0x180019439  mov     [rbp+57h+var_58], r13
0x18001943d  movzx   eax, word ptr [rax]
0x180019440  mov     [rbp+57h+var_C8], eax
0x180019443  lea     rax, byte_180152E2D
0x18001944a  mov     [rbp+57h+var_C0], rax
0x18001944e  mov     rax, r12
0x180019451  sub     eax, esi
0x180019453  mov     [rbp+57h+var_C4], 2
0x18001945a  mov     [rbp+57h+var_B8], 3Eh ; '>'
0x180019461  mov     [rbp+57h+var_B4], 1
0x180019468  mov     [rsp+110h+var_E0], eax
0x18001946c  mov     eax, [rsp+110h+var_E0]
0x180019470  mov     rcx, cs:qword_180173298
0x180019477  lea     rax, [rbp+57h+var_D0]
0x18001947b  mov     [rsp+110h+var_E8], rax
0x180019480  mov     dword ptr [rsp+110h+var_F0], 6
0x180019488  call    cs:__imp_EtwEventWriteTransfer
0x18001948e  mov     rax, cs:gIkeExtGlobals
0x180019495  add     rax, 0A8h
0x18001949b  mov     rcx, [rax+8]
0x18001949f  cmp     [rcx], rax
0x1800194a2  jz      short loc_1800194AB
0x1800194a4  mov     ecx, 3
0x1800194a9  int     29h; Win8: RtlFailFast(ecx)
0x1800194ab  mov     [r14], rax
0x1800194ae  mov     ebx, 1
0x1800194b3  mov     [r14+8], rcx
0x1800194b7  mov     [rcx], r14
0x1800194ba  mov     [rax+8], r14
0x1800194be  mov     rcx, cs:gIkeExtGlobals
0x1800194c5  add     rcx, 78h ; 'x'; lpCriticalSection
0x1800194c9  call    cs:__imp_LeaveCriticalSection
0x1800194cf  mov     eax, cs:dword_180173278
0x1800194d5  cmp     eax, 5
0x1800194d8  jbe     loc_18001963D
0x1800194de  mov     rcx, cs:qword_180173290
0x1800194e5  mov     rax, cs:qword_180173288
0x1800194ec  test    al, 1
0x1800194ee  jz      loc_18001963D
0x1800194f4  mov     rax, rcx
0x1800194f7  and     eax, 1
0x1800194fa  cmp     rax, rcx
0x1800194fd  jnz     loc_18001963D
0x180019503  mov     rax, cs:gIkeExtGlobals
0x18001950a  test    rax, rax
0x18001950d  jz      short loc_180019538
0x18001950f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180019515  cmp     ecx, 0FFFFFFFFh
0x180019518  jz      short loc_180019538
0x18001951a  call    cs:__imp_TlsGetValue
0x180019520  test    rax, rax
0x180019523  jz      short loc_180019531
0x180019525  mov     rcx, [rax]
0x180019528  mov     rax, cs:gIkeExtGlobals
0x18001952f  jmp     short loc_18001953B
0x180019531  mov     rax, cs:gIkeExtGlobals
0x180019538  mov     rcx, r13
0x18001953b  mov     [rbp+57h+var_70], rcx
0x18001953f  lea     rcx, [rbp+57h+var_70]
0x180019543  mov     [rbp+57h+var_B0], rcx
0x180019547  mov     [rbp+57h+var_A8], 8
0x18001954f  test    rax, rax
0x180019552  jz      short loc_180019595
0x180019554  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18001955a  cmp     ecx, 0FFFFFFFFh
0x18001955d  jz      short loc_180019595
0x18001955f  call    cs:__imp_TlsGetValue
0x180019565  test    rax, rax
0x180019568  lea     rdx, [rax+8]
0x18001956c  cmovz   rdx, r13
0x180019570  test    rdx, rdx
0x180019573  jz      short loc_180019595
0x180019575  nop     word ptr [rax+rax+00000000h]
0x180019580  cmp     [rdx+rdi*2+2], r13w
0x180019586  lea     rdi, [rdi+1]
0x18001958a  jnz     short loc_180019580
0x18001958c  lea     edi, ds:2[rdi*2]
0x180019593  jmp     short loc_1800195A1
0x180019595  lea     rdx, LocaleName
0x18001959c  mov     edi, 2
0x1800195a1  mov     [rbp+57h+var_A0], rdx
0x1800195a5  lea     rax, aIkemovemmtozom; "IkeMoveMMToZombieList"
0x1800195ac  mov     [rbp+57h+var_90], rax
0x1800195b0  lea     rdx, [rbp+57h+var_60]
0x1800195b4  movzx   eax, cs:word_180166E61
0x1800195bb  sub     r12d, esi
0x1800195be  mov     [rbp+57h+var_5C], eax
0x1800195c1  xor     r9d, r9d
0x1800195c4  mov     rax, cs:off_180173280
0x1800195cb  xor     r8d, r8d
0x1800195ce  mov     [rbp+57h+var_D0], rax
0x1800195d2  mov     [rbp+57h+var_98], edi
0x1800195d5  mov     [rbp+57h+var_94], r13d
0x1800195d9  mov     [rbp+57h+var_88], 16h
0x1800195e1  mov     [rbp+57h+var_60], 0B000000h
0x1800195e8  mov     [rbp+57h+var_58], 1
0x1800195f0  movzx   eax, word ptr [rax]
0x1800195f3  mov     [rbp+57h+var_C8], eax
0x1800195f6  lea     rax, byte_180166E6B
0x1800195fd  mov     [rbp+57h+var_C0], rax
0x180019601  lea     rax, [rbp+57h+var_D0]
0x180019605  mov     [rbp+57h+var_C4], 2
0x18001960c  mov     [rbp+57h+var_B8], 2Dh ; '-'
  ... truncated ...
```
