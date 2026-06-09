# ReportLeakyScope

- ea: `0x180034038`
- end: `0x180034380`
- name: `ReportLeakyScope`
- size: `840`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800327ec`
- `0x180033344`

## callees

- `0x18000ac60`
- `0x180021674`
- `0x180031df8`
- `0x180034038`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180034350`
- `KERNEL32!HeapFree` at `0x180034350`
- `KERNEL32!HeapAlloc` at `0x1800340fa`
- `KERNEL32!HeapAlloc` at `0x1800340fa`
- `rtutils!RouterLogEventExW` at `0x18003433e`
- `rtutils!RouterLogEventExW` at `0x18003433e`

## string_xrefs

- `0x1800340b1`: `ERROR: Leak detected in '%ls' scope!  One of the following routers is misconfigured:`

## pseudocode

```c
int __fastcall ReportLeakyScope(__int64 a1, unsigned __int8 *a2, unsigned __int8 *a3)
{
  __int64 DefaultName; // rax
  SIZE_T v7; // rsi
  wchar_t *v8; // rax
  wchar_t *v9; // r14
  __int64 v10; // r15
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned int v14; // r15d
  size_t v15; // rsi
  wchar_t *v16; // r13
  __int64 v17; // rdi
  __int64 v18; // r12
  int v19; // ecx
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // r8
  __int64 v24; // rax
  LPCWSTR ptszFormat; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+30h] [rbp-D0h]
  int v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v30) = 0;
    DefaultName = GetDefaultName(a1);
    FormatRRASErrorString(
      &v30,
      L"ERROR: Leak detected in '%ls' scope!  One of the following routers is misconfigured:",
      DefaultName);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v30);
  }
  v7 = 20LL * *a3 + 1;
  v8 = (wchar_t *)HeapAlloc(IPRouterHeap, 0, v7);
  v9 = v8;
  if ( v8 )
  {
    StringCbPrintfW(v8, v7, L"   %d.%d.%d.%d", a2[4], a2[5], a2[6], a2[7]);
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v11 = a2[5];
      v12 = a2[4];
      LODWORD(v27) = a2[7];
      LODWORD(ptszFormat) = a2[6];
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, L"   %d.%d.%d.%d", v12, v11, ptszFormat, v27);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v30);
    }
    v13 = v10;
    v14 = 0;
    v15 = v7 - v13 * 2;
    v16 = &v9[v13];
    while ( v14 < *a3 )
    {
      v17 = 2 * v14 + 1;
      LODWORD(v28) = a3[4 * v17 + 7];
      LODWORD(v27) = a3[4 * v17 + 6];
      LODWORD(ptszFormat) = a3[4 * v17 + 5];
      if ( StringCbPrintfW(v16, v15, L"   %d.%d.%d.%d", a3[4 * v17 + 4], ptszFormat, v27, v28) < 0 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v22 = a3[4 * v17 + 5];
          v23 = a3[4 * v17 + 4];
          LODWORD(v27) = a3[4 * v17 + 7];
          LODWORD(ptszFormat) = a3[4 * v17 + 6];
          LOWORD(v30) = 0;
          FormatRRASErrorString(&v30, L"Insufficient buffer. Couldn't add %d.%d.%d.%d", v23, v22, ptszFormat, v27);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v30);
        }
        break;
      }
      v18 = -1;
      do
        ++v18;
      while ( v16[v18] );
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v19 = a3[4 * v17 + 6];
        v20 = a3[4 * v17 + 5];
        v21 = a3[4 * v17 + 4];
        LOWORD(v30) = 0;
        LODWORD(v27) = a3[4 * v17 + 7];
        LODWORD(ptszFormat) = v19;
        FormatRRASErrorString(&v30, L"   %d.%d.%d.%d", v21, v20, ptszFormat, v27);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v30);
      }
      ++v14;
      v15 -= 2 * v18;
      v16 += v18;
    }
    v24 = GetDefaultName(a1);
    RouterLogEventExW(g_hLogHandle, 1u, 0, 0x4ED0u, L"%S%S", v24, v9);
    LODWORD(v8) = HeapFree(IPRouterHeap, 0, v9);
  }
  else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LODWORD(v8) = McTemplateU0z_EventWriteTransfer(
                    &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    RasRtrMgrTraceError,
                    L"ERROR: Couldn't allocate space for rest of message");
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180034038  mov     [rsp-8+arg_18], rbx
0x18003403d  push    rbp
0x18003403e  push    rsi
0x18003403f  push    rdi
0x180034040  push    r12
0x180034042  push    r13
0x180034044  push    r14
0x180034046  push    r15
0x180034048  lea     rbp, [rsp-760h]
0x180034050  sub     rsp, 860h
0x180034057  mov     rax, cs:__security_cookie
0x18003405e  xor     rax, rsp
0x180034061  mov     [rbp+790h+var_40], rax
0x180034068  mov     rbx, r8
0x18003406b  mov     [rsp+890h+var_850], rcx
0x180034070  mov     rdi, rdx
0x180034073  mov     r12, rcx
0x180034076  xor     esi, esi
0x180034078  lea     rcx, [rsp+890h+var_83C]; void *
0x18003407d  xor     edx, edx; Val
0x18003407f  mov     [rsp+890h+var_840], esi
0x180034083  mov     r8d, 7FCh; Size
0x180034089  call    memset_0
0x18003408e  mov     r15b, 40h ; '@'
0x180034091  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180034098  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18003409f  jz      short loc_1800340DF
0x1800340a1  mov     rcx, r12
0x1800340a4  mov     word ptr [rsp+890h+var_840], si
0x1800340a9  call    GetDefaultName
0x1800340ae  mov     r8, rax
0x1800340b1  lea     rdx, aErrorLeakDetec; "ERROR: Leak detected in '%ls' scope!  O"...
0x1800340b8  lea     rcx, [rsp+890h+var_840]
0x1800340bd  call    FormatRRASErrorString
0x1800340c2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800340c9  jz      short loc_1800340DF
0x1800340cb  lea     r8, [rsp+890h+var_840]
0x1800340d0  mov     rcx, r13
0x1800340d3  lea     rdx, RasRtrMgrTraceError
0x1800340da  call    McTemplateU0z_EventWriteTransfer
0x1800340df  movzx   eax, byte ptr [rbx]
0x1800340e2  xor     edx, edx; dwFlags
0x1800340e4  lea     rcx, [rax+rax*4]
0x1800340e8  lea     rsi, ds:1[rcx*4]
0x1800340f0  mov     rcx, cs:IPRouterHeap; hHeap
0x1800340f7  mov     r8, rsi; dwBytes
0x1800340fa  call    cs:__imp_HeapAlloc
0x180034100  xor     r12d, r12d
0x180034103  mov     r14, rax
0x180034106  test    rax, rax
0x180034109  jnz     short loc_180034133
0x18003410b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180034112  jz      loc_180034356
0x180034118  lea     r8, aErrorCouldnTAl; "ERROR: Couldn't allocate space for rest"...
0x18003411f  mov     rcx, r13
0x180034122  lea     rdx, RasRtrMgrTraceError
0x180034129  call    McTemplateU0z_EventWriteTransfer
0x18003412e  jmp     loc_180034356
0x180034133  movzx   ecx, byte ptr [rdi+6]
0x180034137  lea     r8, aDDDD_0; "   %d.%d.%d.%d"
0x18003413e  movzx   edx, byte ptr [rdi+5]
0x180034142  movzx   eax, byte ptr [rdi+7]
0x180034146  movzx   r9d, byte ptr [rdi+4]
0x18003414b  mov     dword ptr [rsp+890h+var_860], eax
0x18003414f  mov     dword ptr [rsp+890h+var_868], ecx
0x180034153  mov     rcx, r14; pszDest
0x180034156  mov     dword ptr [rsp+890h+ptszFormat], edx
0x18003415a  mov     rdx, rsi; cbDest
0x18003415d  call    StringCbPrintfW
0x180034162  or      r15, 0FFFFFFFFFFFFFFFFh
0x180034166  inc     r15
0x180034169  cmp     [r14+r15*2], r12w
0x18003416e  jnz     short loc_180034166
0x180034170  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x180034177  jge     short loc_1800341C7
0x180034179  movzx   ecx, byte ptr [rdi+6]
0x18003417d  lea     rdx, aDDDD_0; "   %d.%d.%d.%d"
0x180034184  movzx   eax, byte ptr [rdi+7]
0x180034188  movzx   r9d, byte ptr [rdi+5]
0x18003418d  movzx   r8d, byte ptr [rdi+4]
0x180034192  mov     dword ptr [rsp+890h+var_868], eax
0x180034196  mov     dword ptr [rsp+890h+ptszFormat], ecx
0x18003419a  lea     rcx, [rsp+890h+var_840]
0x18003419f  mov     word ptr [rsp+890h+var_840], r12w
0x1800341a5  call    FormatRRASErrorString
0x1800341aa  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800341b1  jge     short loc_1800341C7
0x1800341b3  lea     r8, [rsp+890h+var_840]
0x1800341b8  mov     rcx, r13
0x1800341bb  lea     rdx, RasRtrmgrTraceInfo
0x1800341c2  call    McTemplateU0z_EventWriteTransfer
0x1800341c7  lea     rax, [r15+r15]
0x1800341cb  mov     r15d, r12d
0x1800341ce  sub     rsi, rax
0x1800341d1  lea     r13, [rax+r14]
0x1800341d5  movzx   eax, byte ptr [rbx]
0x1800341d8  cmp     r15d, eax
0x1800341db  jnb     loc_18003430A
0x1800341e1  lea     eax, ds:1[r15*2]
0x1800341e9  mov     edi, eax
0x1800341eb  lea     r8, aDDDD_0; "   %d.%d.%d.%d"
0x1800341f2  movzx   eax, byte ptr [rbx+rax*4+7]
0x1800341f7  mov     dword ptr [rsp+890h+var_860], eax
0x1800341fb  movzx   ecx, byte ptr [rbx+rdi*4+6]
0x180034200  movzx   edx, byte ptr [rbx+rdi*4+5]
0x180034205  movzx   r9d, byte ptr [rbx+rdi*4+4]
0x18003420b  mov     dword ptr [rsp+890h+var_868], ecx
0x18003420f  mov     rcx, r13; pszDest
0x180034212  mov     dword ptr [rsp+890h+ptszFormat], edx
0x180034216  mov     rdx, rsi; cbDest
0x180034219  call    StringCbPrintfW
0x18003421e  test    eax, eax
0x180034220  js      loc_1800342A9
0x180034226  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003422a  xor     eax, eax
0x18003422c  inc     r12
0x18003422f  cmp     [r13+r12*2+0], ax
0x180034235  jnz     short loc_18003422C
0x180034237  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, al
0x18003423d  jge     short loc_180034294
0x18003423f  movzx   ecx, byte ptr [rbx+rdi*4+6]
0x180034244  lea     rdx, aDDDD_0; "   %d.%d.%d.%d"
0x18003424b  movzx   r9d, byte ptr [rbx+rdi*4+5]
0x180034251  movzx   r8d, byte ptr [rbx+rdi*4+4]
0x180034257  mov     word ptr [rsp+890h+var_840], ax
0x18003425c  movzx   eax, byte ptr [rbx+rdi*4+7]
0x180034261  mov     dword ptr [rsp+890h+var_868], eax
0x180034265  mov     dword ptr [rsp+890h+ptszFormat], ecx
0x180034269  lea     rcx, [rsp+890h+var_840]
0x18003426e  call    FormatRRASErrorString
0x180034273  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003427a  jge     short loc_180034294
0x18003427c  lea     r8, [rsp+890h+var_840]
0x180034281  lea     rdx, RasRtrmgrTraceInfo
0x180034288  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003428f  call    McTemplateU0z_EventWriteTransfer
0x180034294  lea     rax, [r12+r12]
0x180034298  inc     r15d
0x18003429b  sub     rsi, rax
0x18003429e  add     r13, rax
0x1800342a1  xor     r12d, r12d
0x1800342a4  jmp     loc_1800341D5
0x1800342a9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800342b0  jge     short loc_18003430A
0x1800342b2  movzx   eax, byte ptr [rbx+rdi*4+7]
0x1800342b7  lea     rdx, aInsufficientBu; "Insufficient buffer. Couldn't add %d.%d"...
0x1800342be  movzx   r10d, byte ptr [rbx+rdi*4+6]
0x1800342c4  lea     rcx, [rsp+890h+var_840]
0x1800342c9  movzx   r9d, byte ptr [rbx+rdi*4+5]
0x1800342cf  movzx   r8d, byte ptr [rbx+rdi*4+4]
0x1800342d5  mov     dword ptr [rsp+890h+var_868], eax
0x1800342d9  mov     dword ptr [rsp+890h+ptszFormat], r10d
0x1800342de  mov     word ptr [rsp+890h+var_840], r12w
0x1800342e4  call    FormatRRASErrorString
0x1800342e9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x1800342f0  jge     short loc_18003430A
0x1800342f2  lea     r8, [rsp+890h+var_840]
0x1800342f7  lea     rdx, RasRtrmgrTraceInfo
0x1800342fe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180034305  call    McTemplateU0z_EventWriteTransfer
0x18003430a  mov     rcx, [rsp+890h+var_850]
0x18003430f  call    GetDefaultName
0x180034314  mov     rcx, cs:g_hLogHandle; hLogHandle
0x18003431b  xor     r8d, r8d; dwErrorCode
0x18003431e  mov     [rsp+890h+var_860], r14
0x180034323  mov     r9d, 4ED0h; dwMessageId
0x180034329  mov     [rsp+890h+var_868], rax
0x18003432e  lea     rax, aSS_0; "%S%S"
0x180034335  mov     [rsp+890h+ptszFormat], rax; ptszFormat
0x18003433a  lea     edx, [r8+1]; dwEventType
0x18003433e  call    cs:__imp_RouterLogEventExW
0x180034344  mov     rcx, cs:IPRouterHeap; hHeap
0x18003434b  mov     r8, r14; lpMem
0x18003434e  xor     edx, edx; dwFlags
0x180034350  call    cs:__imp_HeapFree
0x180034356  mov     rcx, [rbp+790h+var_40]
0x18003435d  xor     rcx, rsp; StackCookie
0x180034360  call    __security_check_cookie
0x180034365  mov     rbx, [rsp+890h+arg_18]
0x18003436d  add     rsp, 860h
0x180034374  pop     r15
0x180034376  pop     r14
0x180034378  pop     r13
0x18003437a  pop     r12
0x18003437c  pop     rdi
0x18003437d  pop     rsi
0x18003437e  pop     rbp
0x18003437f  retn
```
