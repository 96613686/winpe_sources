# IkeDestroyTimerContext

- ea: `0x18003cfa0`
- end: `0x18003d2a4`
- name: `IkeDestroyTimerContext`
- size: `772`
- prototype: ``
- caller_count: `34`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c880`
- `0x180027f50`
- `0x18003aa50`
- `0x18003fa20`
- `0x18004add0`
- `0x18004b818`
- `0x180066d30`
- `0x1800687ac`
- `0x180068e48`
- `0x180069248`
- `0x180069e80`
- `0x18006a328`
- `0x18006c098`
- `0x1800be508`
- `0x1800bf268`
- `0x1800ce2d0`
- `0x1800d1040`
- `0x1800d742c`
- `0x1800d7afc`
- `0x1800d89ac`
- `0x1800dd564`
- `0x1800ddbe8`
- `0x1800e0590`
- `0x1800e17b8`
- `0x1800e1944`
- `0x1800e1c98`
- `0x1800e2414`
- `0x1800eecd4`
- `0x1800eedd0`
- `0x1800ef0d8`
- `0x1801073f4`
- `0x180108160`
- `0x180108f38`
- `0x18010935c`

## callees

- `0x180016300`
- `0x18003c9f0`
- `0x18003cfa0`
- `0x180050850`
- `0x18006e3f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d018`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d051`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d0cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d111`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d018`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d051`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d0cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003d111`
- `ntdll!EtwEventWriteTransfer` at `0x18003d232`
- `ntdll!EtwEventWriteTransfer` at `0x18003d232`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d23b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003d23b`

## pseudocode

```c
void __fastcall IkeDestroyTimerContext(__int64 *a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  _QWORD *v3; // rcx
  LPCRITICAL_SECTION v4; // rdx
  DWORD LockSemaphore; // eax
  LPVOID Value; // rax
  LPVOID v7; // r8
  __int64 v8; // rdi
  DWORD v9; // eax
  __int64 *v10; // rax
  __int64 v11; // r9
  LPCRITICAL_SECTION v12; // rax
  DWORD v13; // ecx
  __int64 *v14; // rax
  __int64 v15; // rcx
  DWORD v16; // ecx
  char *v17; // rax
  const WCHAR *v18; // rdx
  __int64 v19; // rax
  int v21; // eax
  __int64 v22; // rcx
  int v23; // [rsp+44h] [rbp-75h] BYREF
  __int64 v24; // [rsp+48h] [rbp-71h] BYREF
  __int64 v25; // [rsp+50h] [rbp-69h] BYREF
  __int64 v26; // [rsp+58h] [rbp-61h] BYREF
  _DWORD v27[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v28; // [rsp+68h] [rbp-51h]
  char *v29; // [rsp+70h] [rbp-49h] BYREF
  int v30; // [rsp+78h] [rbp-41h]
  int v31; // [rsp+7Ch] [rbp-3Dh]
  char *v32; // [rsp+80h] [rbp-39h]
  int v33; // [rsp+88h] [rbp-31h]
  int v34; // [rsp+8Ch] [rbp-2Dh]
  __int64 *v35; // [rsp+90h] [rbp-29h]
  __int64 v36; // [rsp+98h] [rbp-21h]
  const WCHAR *v37; // [rsp+A0h] [rbp-19h]
  int v38; // [rsp+A8h] [rbp-11h]
  int v39; // [rsp+ACh] [rbp-Dh]
  const char *v40; // [rsp+B0h] [rbp-9h]
  __int64 v41; // [rsp+B8h] [rbp-1h]
  __int64 *v42; // [rsp+C0h] [rbp+7h]
  __int64 v43; // [rsp+C8h] [rbp+Fh]
  int *v44; // [rsp+D0h] [rbp+17h]
  __int64 v45; // [rsp+D8h] [rbp+1Fh]
  __int64 *v46; // [rsp+E0h] [rbp+27h]
  __int64 v47; // [rsp+E8h] [rbp+2Fh]

  v1 = (struct _RTL_CRITICAL_SECTION *)*a1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v4 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore, LockSemaphore == -1) )
    {
      v7 = 0;
    }
    else
    {
      Value = TlsGetValue(LockSemaphore);
      v3 = WPP_GLOBAL_Control;
      v7 = Value;
      v4 = gIkeExtGlobals;
    }
    v8 = (__int64)v7 + 8;
    if ( !v7 )
      v8 = 0;
    if ( v4
      && (v9 = (DWORD)v4[86].LockSemaphore, v9 != -1)
      && (v10 = (__int64 *)TlsGetValue(v9), v3 = WPP_GLOBAL_Control, v10) )
    {
      v11 = *v10;
    }
    else
    {
      LODWORD(v11) = 0;
    }
    WPP_SF_iSqdq(
      v3[2],
      12,
      (unsigned int)WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids,
      v11,
      v8,
      *a1,
      *(_DWORD *)(*a1 + 100),
      *(_QWORD *)(*a1 + 104));
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v12 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v13 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v13 != -1 )
      {
        v14 = (__int64 *)TlsGetValue(v13);
        if ( v14 )
        {
          v15 = *v14;
          v12 = gIkeExtGlobals;
LABEL_23:
          v24 = v15;
          v35 = &v24;
          v36 = 8;
          if ( !v12 )
            goto LABEL_31;
          v16 = (DWORD)v12[86].LockSemaphore;
          if ( v16 == -1 )
            goto LABEL_31;
          v17 = (char *)TlsGetValue(v16);
          v18 = (const WCHAR *)(v17 + 8);
          if ( !v17 )
            v18 = 0;
          if ( v18 )
          {
            v19 = -1;
            while ( v18[++v19] != 0 )
              ;
            v21 = 2 * v19 + 2;
          }
          else
          {
LABEL_31:
            v18 = &LocaleName;
            v21 = 2;
          }
          v22 = *a1;
          v38 = v21;
          v25 = v22;
          v40 = "Destroying TimerContext";
          v42 = &v25;
          v37 = v18;
          v39 = 0;
          v41 = 24;
          v43 = 8;
          v23 = *(_DWORD *)(v22 + 100);
          v44 = &v23;
          v45 = 4;
          v26 = *(_QWORD *)(v22 + 104);
          v46 = &v26;
          v27[1] = 4;
          v29 = off_180173280;
          v47 = 8;
          v27[0] = 184549376;
          v28 = 0;
          v30 = *(unsigned __int16 *)off_180173280;
          v32 = byte_18015DFC3;
          v31 = 2;
          v33 = 83;
          v34 = 1;
          EtwEventWriteTransfer(qword_180173298, v27, 0, 0, 8, &v29);
          goto LABEL_33;
        }
        v12 = gIkeExtGlobals;
      }
    }
    v15 = 0;
    goto LABEL_23;
  }
LABEL_33:
  EnterCriticalSection(v1);
  if ( !v1[2].RecursionCount )
  {
    v1[2].RecursionCount = 1;
    if ( !WfpStopTimer(gIkeExtGlobals + 67, (__int64)&v1[1].LockCount) )
      IkeDerefTimerContext(v1, 0);
  }
  IkeDerefTimerContext(v1, 1);
  *a1 = 0;
}

```

## disassembly

```asm
0x18003cfa0  mov     [rsp-8+arg_10], rbx
0x18003cfa5  push    rbp
0x18003cfa6  push    rsi
0x18003cfa7  push    r14
0x18003cfa9  lea     rbp, [rsp-47h]
0x18003cfae  sub     rsp, 100h
0x18003cfb5  mov     rax, cs:__security_cookie
0x18003cfbc  xor     rax, rsp
0x18003cfbf  mov     [rbp+57h+var_20], rax
0x18003cfc3  mov     rbx, [rcx]
0x18003cfc6  mov     rsi, rcx
0x18003cfc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfd0  lea     rax, WPP_GLOBAL_Control
0x18003cfd7  xor     r14d, r14d
0x18003cfda  cmp     rcx, rax
0x18003cfdd  jz      loc_18003D0A6
0x18003cfe3  cmp     byte ptr [rcx+19h], 4
0x18003cfe7  jb      loc_18003D0A6
0x18003cfed  test    byte ptr [rcx+1Ch], 10h
0x18003cff1  jz      loc_18003D0A6
0x18003cff7  mov     rdx, cs:gIkeExtGlobals
0x18003cffe  mov     [rsp+110h+arg_8], rdi
0x18003d006  test    rdx, rdx
0x18003d009  jz      short loc_18003D031
0x18003d00b  mov     eax, [rdx+0D88h]
0x18003d011  cmp     eax, 0FFFFFFFFh
0x18003d014  jz      short loc_18003D031
0x18003d016  mov     ecx, eax; dwTlsIndex
0x18003d018  call    cs:__imp_TlsGetValue
0x18003d01e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d025  mov     r8, rax
0x18003d028  mov     rdx, cs:gIkeExtGlobals
0x18003d02f  jmp     short loc_18003D034
0x18003d031  mov     r8, r14
0x18003d034  test    r8, r8
0x18003d037  lea     rdi, [r8+8]
0x18003d03b  cmovz   rdi, r14
0x18003d03f  test    rdx, rdx
0x18003d042  jz      short loc_18003D068
0x18003d044  mov     eax, [rdx+0D88h]
0x18003d04a  cmp     eax, 0FFFFFFFFh
0x18003d04d  jz      short loc_18003D068
0x18003d04f  mov     ecx, eax; dwTlsIndex
0x18003d051  call    cs:__imp_TlsGetValue
0x18003d057  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d05e  test    rax, rax
0x18003d061  jz      short loc_18003D068
0x18003d063  mov     r9, [rax]
0x18003d066  jmp     short loc_18003D06B
0x18003d068  mov     r9, r14
0x18003d06b  mov     r8, [rsi]
0x18003d06e  mov     edx, 0Ch
0x18003d073  mov     rcx, [rcx+10h]
0x18003d077  mov     rax, [r8+68h]
0x18003d07b  mov     [rsp+110h+var_D8], rax
0x18003d080  mov     eax, [r8+64h]
0x18003d084  mov     [rsp+110h+var_E0], eax
0x18003d088  mov     [rsp+110h+var_E8], r8
0x18003d08d  lea     r8, WPP_4c56edd497003658c4b83fd296af3c1f_Traceguids
0x18003d094  mov     [rsp+110h+var_F0], rdi
0x18003d099  call    WPP_SF_iSqdq
0x18003d09e  mov     rdi, [rsp+110h+arg_8]
0x18003d0a6  mov     eax, cs:dword_180173278
0x18003d0ac  cmp     eax, 4
0x18003d0af  jbe     loc_18003D238
0x18003d0b5  mov     rax, cs:gIkeExtGlobals
0x18003d0bc  test    rax, rax
0x18003d0bf  jz      short loc_18003D0EA
0x18003d0c1  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003d0c7  cmp     ecx, 0FFFFFFFFh
0x18003d0ca  jz      short loc_18003D0EA
0x18003d0cc  call    cs:__imp_TlsGetValue
0x18003d0d2  test    rax, rax
0x18003d0d5  jz      short loc_18003D0E3
0x18003d0d7  mov     rcx, [rax]
0x18003d0da  mov     rax, cs:gIkeExtGlobals
0x18003d0e1  jmp     short loc_18003D0ED
0x18003d0e3  mov     rax, cs:gIkeExtGlobals
0x18003d0ea  mov     rcx, r14
0x18003d0ed  mov     [rbp+57h+var_C8], rcx
0x18003d0f1  lea     rcx, [rbp+57h+var_C8]
0x18003d0f5  mov     [rbp+57h+var_80], rcx
0x18003d0f9  mov     [rbp+57h+var_78], 8
0x18003d101  test    rax, rax
0x18003d104  jz      short loc_18003D145
0x18003d106  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003d10c  cmp     ecx, 0FFFFFFFFh
0x18003d10f  jz      short loc_18003D145
0x18003d111  call    cs:__imp_TlsGetValue
0x18003d117  test    rax, rax
0x18003d11a  lea     rdx, [rax+8]
0x18003d11e  cmovz   rdx, r14
0x18003d122  test    rdx, rdx
0x18003d125  jz      short loc_18003D145
0x18003d127  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003d12e  xchg    ax, ax
0x18003d130  cmp     [rdx+rax*2+2], r14w
0x18003d136  lea     rax, [rax+1]
0x18003d13a  jnz     short loc_18003D130
0x18003d13c  lea     eax, ds:2[rax*2]
0x18003d143  jmp     short loc_18003D151
0x18003d145  lea     rdx, LocaleName
0x18003d14c  mov     eax, 2
0x18003d151  mov     rcx, [rsi]
0x18003d154  xor     r9d, r9d
0x18003d157  mov     [rbp+57h+var_68], eax
0x18003d15a  xor     r8d, r8d
0x18003d15d  mov     [rbp+57h+var_C0], rcx
0x18003d161  lea     rax, aDestroyingTime; "Destroying TimerContext"
0x18003d168  mov     [rbp+57h+var_60], rax
0x18003d16c  lea     rax, [rbp+57h+var_C0]
0x18003d170  mov     [rbp+57h+var_50], rax
0x18003d174  mov     [rbp+57h+var_70], rdx
0x18003d178  lea     rdx, [rbp+57h+var_B0]
0x18003d17c  mov     [rbp+57h+var_64], r14d
0x18003d180  mov     [rbp+57h+var_58], 18h
0x18003d188  mov     [rbp+57h+var_48], 8
0x18003d190  mov     eax, [rcx+64h]
0x18003d193  mov     [rbp+57h+var_CC], eax
0x18003d196  lea     rax, [rbp+57h+var_CC]
0x18003d19a  mov     [rbp+57h+var_40], rax
0x18003d19e  mov     [rbp+57h+var_38], 4
0x18003d1a6  mov     rax, [rcx+68h]
0x18003d1aa  lea     rcx, _TraceLoggingMetadata
0x18003d1b1  mov     [rbp+57h+var_B8], rax
0x18003d1b5  lea     rax, [rbp+57h+var_B8]
0x18003d1b9  mov     [rbp+57h+var_30], rax
0x18003d1bd  movzx   eax, cs:word_18015DFB9
0x18003d1c4  mov     [rbp+57h+var_AC], eax
0x18003d1c7  mov     rax, cs:off_180173280
0x18003d1ce  mov     [rbp+57h+var_A0], rax
0x18003d1d2  mov     [rbp+57h+var_28], 8
0x18003d1da  mov     [rbp+57h+var_B0], 0B000000h
0x18003d1e1  mov     [rbp+57h+var_A8], r14
0x18003d1e5  movzx   eax, word ptr [rax]
0x18003d1e8  mov     [rbp+57h+var_98], eax
0x18003d1eb  lea     rax, byte_18015DFC3
0x18003d1f2  mov     [rbp+57h+var_90], rax
0x18003d1f6  lea     rax, _TraceLoggingMetadataEnd
0x18003d1fd  sub     eax, ecx
0x18003d1ff  mov     [rbp+57h+var_94], 2
0x18003d206  mov     [rbp+57h+var_88], 53h ; 'S'
0x18003d20d  mov     [rbp+57h+var_84], 1
0x18003d214  mov     [rbp+57h+var_D0], eax
0x18003d217  mov     eax, [rbp+57h+var_D0]
0x18003d21a  mov     rcx, cs:qword_180173298
0x18003d221  lea     rax, [rbp+57h+var_A0]
0x18003d225  mov     [rsp+110h+var_E8], rax
0x18003d22a  mov     dword ptr [rsp+110h+var_F0], 8
0x18003d232  call    cs:__imp_EtwEventWriteTransfer
0x18003d238  mov     rcx, rbx; lpCriticalSection
0x18003d23b  call    cs:__imp_EnterCriticalSection
0x18003d241  cmp     [rbx+5Ch], r14d
0x18003d245  jnz     short loc_18003D274
0x18003d247  mov     dword ptr [rbx+5Ch], 1
0x18003d24e  lea     rdx, [rbx+30h]
0x18003d252  mov     rcx, cs:gIkeExtGlobals
0x18003d259  add     rcx, 0A78h; lpCriticalSection
0x18003d260  call    WfpStopTimer
0x18003d265  test    rax, rax
0x18003d268  jnz     short loc_18003D274
0x18003d26a  xor     edx, edx
0x18003d26c  mov     rcx, rbx; lpCriticalSection
0x18003d26f  call    IkeDerefTimerContext
0x18003d274  mov     edx, 1
0x18003d279  mov     rcx, rbx; lpCriticalSection
0x18003d27c  call    IkeDerefTimerContext
0x18003d281  mov     [rsi], r14
0x18003d284  mov     rcx, [rbp+57h+var_20]
0x18003d288  xor     rcx, rsp; StackCookie
0x18003d28b  call    __security_check_cookie
0x18003d290  mov     rbx, [rsp+110h+arg_10]
0x18003d298  add     rsp, 100h
0x18003d29f  pop     r14
0x18003d2a1  pop     rsi
0x18003d2a2  pop     rbp
0x18003d2a3  retn
```
