# SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x180035208`
- end: `0x1800353db`
- name: `?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z`
- size: `467`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `13`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ed30`
- `0x1800110a0`
- `0x18001a1d8`
- `0x18001d93c`
- `0x180020b60`
- `0x18002a104`
- `0x18002a5ac`
- `0x18002a83c`
- `0x18002ab6c`
- `0x18002ae2c`
- `0x18002b2fc`
- `0x18002b6f0`
- `0x18002b960`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180035208`
- `0x1800353e4`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18003526e`
- `ntdll!EtwEventEnabled` at `0x18003526e`
- `ntdll!EtwEventWrite` at `0x18003537c`
- `ntdll!EtwEventWrite` at `0x18003537c`

## string_xrefs

- `0x180035386`: `Event: %u, label: %ws, message: %ws, info: %ws, platform: %ws, LE: 0x%08X, hr: 0x%08X, EventWrite: %d`

## pseudocode

```c
void __fastcall SplLogPrinterSetupGenericEvent(
        const struct _EVENT_DESCRIPTOR *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v11; // rax
  const wchar_t *v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // ecx
  const wchar_t *v15; // r8
  __int64 v16; // rcx
  unsigned int v17; // ecx
  const wchar_t *v18; // r8
  __int64 v19; // rcx
  unsigned int v20; // ecx
  const wchar_t *v21; // r8
  unsigned int v22; // eax
  int v23; // [rsp+48h] [rbp-99h]
  const wchar_t *v24; // [rsp+50h] [rbp-91h] BYREF
  __int64 v25; // [rsp+58h] [rbp-89h] BYREF
  const wchar_t *v26; // [rsp+60h] [rbp-81h]
  __int64 v27; // [rsp+68h] [rbp-79h]
  const wchar_t *v28; // [rsp+70h] [rbp-71h]
  __int64 v29; // [rsp+78h] [rbp-69h]
  const wchar_t *v30; // [rsp+80h] [rbp-61h]
  __int64 v31; // [rsp+88h] [rbp-59h]
  unsigned int *v32; // [rsp+90h] [rbp-51h]
  __int64 v33; // [rsp+98h] [rbp-49h]
  unsigned int *v34; // [rsp+A0h] [rbp-41h]
  __int64 v35; // [rsp+A8h] [rbp-39h]

  v24 = 0;
  memset_0(&v25, 0, 0x88u);
  if ( g_bTracingEnabled && (unsigned __int8)EtwEventEnabled(g_splRegistrationHandle, a1) && a1 )
  {
    v11 = -1;
    v12 = L"-";
    if ( a2 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      v14 = 2 * v13 + 2;
      v15 = a2;
    }
    else
    {
      v14 = 4;
      v15 = L"-";
    }
    v24 = v15;
    v25 = v14;
    if ( a3 )
    {
      v16 = -1;
      do
        ++v16;
      while ( a3[v16] );
      v17 = 2 * v16 + 2;
      v18 = a3;
    }
    else
    {
      v17 = 4;
      v18 = L"-";
    }
    v26 = v18;
    v27 = v17;
    if ( a4 )
    {
      v19 = -1;
      do
        ++v19;
      while ( a4[v19] );
      v20 = 2 * v19 + 2;
      v21 = a4;
    }
    else
    {
      v20 = 4;
      v21 = L"-";
    }
    v28 = v21;
    v29 = v20;
    if ( a5 )
    {
      do
        ++v11;
      while ( a5[v11] );
      v22 = 2 * v11 + 2;
      v12 = a5;
    }
    else
    {
      v22 = 4;
    }
    v31 = v22;
    v32 = &a6;
    v30 = v12;
    v33 = 4;
    v35 = 4;
    v34 = &a7;
    v23 = EtwEventWrite(g_splRegistrationHandle, a1, 6, &v24);
    PerfLibTelemetry::WriteDbgTraceInfo(
      "SplLogPrinterSetupGenericEvent",
      L"Event: %u, label: %ws, message: %ws, info: %ws, platform: %ws, LE: 0x%08X, hr: 0x%08X, EventWrite: %d",
      a1->Id,
      a2,
      a3,
      a4,
      a5,
      a6,
      a7,
      v23,
      v24,
      v25,
      v26,
      v27,
      v28,
      v29);
  }
}

```

## disassembly

```asm
0x180035208  push    rbp
0x18003520a  push    rbx
0x18003520b  push    rsi
0x18003520c  push    rdi
0x18003520d  push    r12
0x18003520f  push    r14
0x180035211  push    r15
0x180035213  lea     rbp, [rsp-0Fh]
0x180035218  sub     rsp, 0F0h
0x18003521f  mov     rax, cs:__security_cookie
0x180035226  xor     rax, rsp
0x180035229  mov     [rbp+3Fh+var_40], rax
0x18003522d  mov     rbx, [rbp+3Fh+arg_20]
0x180035231  mov     rsi, r8
0x180035234  mov     rdi, rdx
0x180035237  mov     r15, rcx
0x18003523a  xor     r12d, r12d
0x18003523d  lea     rcx, [rsp+120h+var_C8]; void *
0x180035242  xor     edx, edx; Val
0x180035244  mov     [rsp+120h+var_D0], r12
0x180035249  mov     r8d, 88h; Size
0x18003524f  mov     r14, r9
0x180035252  call    memset_0
0x180035257  cmp     cs:?g_bTracingEnabled@@3HA, r12d; int g_bTracingEnabled
0x18003525e  jz      loc_1800353BD
0x180035264  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x18003526b  mov     rdx, r15
0x18003526e  call    cs:__imp_EtwEventEnabled
0x180035274  test    al, al
0x180035276  jz      loc_1800353BD
0x18003527c  test    r15, r15
0x18003527f  jz      loc_1800353BD
0x180035285  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035289  lea     r9d, [r12+4]
0x18003528e  lea     rdx, asc_18004D604; "-"
0x180035295  test    rdi, rdi
0x180035298  jz      short loc_1800352B3
0x18003529a  mov     rcx, rax
0x18003529d  inc     rcx
0x1800352a0  cmp     [rdi+rcx*2], r12w
0x1800352a5  jnz     short loc_18003529D
0x1800352a7  lea     ecx, ds:2[rcx*2]
0x1800352ae  mov     r8, rdi
0x1800352b1  jmp     short loc_1800352B9
0x1800352b3  mov     ecx, r9d
0x1800352b6  mov     r8, rdx
0x1800352b9  mov     [rsp+120h+var_D0], r8
0x1800352be  mov     [rsp+120h+var_C8], ecx
0x1800352c2  mov     [rsp+120h+var_C4], r12d
0x1800352c7  test    rsi, rsi
0x1800352ca  jz      short loc_1800352E5
0x1800352cc  mov     rcx, rax
0x1800352cf  inc     rcx
0x1800352d2  cmp     [rsi+rcx*2], r12w
0x1800352d7  jnz     short loc_1800352CF
0x1800352d9  lea     ecx, ds:2[rcx*2]
0x1800352e0  mov     r8, rsi
0x1800352e3  jmp     short loc_1800352EB
0x1800352e5  mov     ecx, r9d
0x1800352e8  mov     r8, rdx
0x1800352eb  mov     [rsp+120h+var_C0], r8
0x1800352f0  mov     [rbp+3Fh+var_B8], ecx
0x1800352f3  mov     [rbp+3Fh+var_B4], r12d
0x1800352f7  test    r14, r14
0x1800352fa  jz      short loc_180035315
0x1800352fc  mov     rcx, rax
0x1800352ff  inc     rcx
0x180035302  cmp     [r14+rcx*2], r12w
0x180035307  jnz     short loc_1800352FF
0x180035309  lea     ecx, ds:2[rcx*2]
0x180035310  mov     r8, r14
0x180035313  jmp     short loc_18003531B
0x180035315  mov     ecx, r9d
0x180035318  mov     r8, rdx
0x18003531b  mov     [rbp+3Fh+var_B0], r8
0x18003531f  mov     [rbp+3Fh+var_A8], ecx
0x180035322  mov     [rbp+3Fh+var_A4], r12d
0x180035326  test    rbx, rbx
0x180035329  jz      short loc_180035341
0x18003532b  inc     rax
0x18003532e  cmp     [rbx+rax*2], r12w
0x180035333  jnz     short loc_18003532B
0x180035335  lea     eax, ds:2[rax*2]
0x18003533c  mov     rdx, rbx
0x18003533f  jmp     short loc_180035344
0x180035341  mov     eax, r9d
0x180035344  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x18003534b  mov     r8d, 6
0x180035351  mov     dword ptr [rbp+3Fh+var_98], eax
0x180035354  lea     rax, [rbp+3Fh+arg_28]
0x180035358  mov     [rbp+3Fh+var_90], rax
0x18003535c  lea     rax, [rbp+3Fh+arg_30]
0x180035360  mov     [rbp+3Fh+var_A0], rdx
0x180035364  mov     rdx, r15
0x180035367  mov     [rbp+3Fh+var_88], r9
0x18003536b  mov     [rbp+3Fh+var_78], r9
0x18003536f  lea     r9, [rsp+120h+var_D0]
0x180035374  mov     [rbp+3Fh+var_80], rax
0x180035378  mov     dword ptr [rbp+3Fh+var_98+4], r12d
0x18003537c  call    cs:__imp_EtwEventWrite
0x180035382  movzx   r8d, word ptr [r15]
0x180035386  lea     rdx, aEventULabelWsM_0; "Event: %u, label: %ws, message: %ws, in"...
0x18003538d  mov     [rsp+120h+var_D8], eax
0x180035391  lea     rcx, aSpllogprinters_0; "SplLogPrinterSetupGenericEvent"
0x180035398  mov     eax, [rbp+3Fh+arg_30]
0x18003539b  mov     r9, rdi
0x18003539e  mov     [rsp+120h+var_E0], eax
0x1800353a2  mov     eax, [rbp+3Fh+arg_28]
0x1800353a5  mov     [rsp+120h+var_E8], eax
0x1800353a9  mov     [rsp+120h+var_F0], rbx
0x1800353ae  mov     [rsp+120h+var_F8], r14
0x1800353b3  mov     [rsp+120h+var_100], rsi
0x1800353b8  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800353bd  mov     rcx, [rbp+3Fh+var_40]
0x1800353c1  xor     rcx, rsp; StackCookie
0x1800353c4  call    __security_check_cookie
0x1800353c9  add     rsp, 0F0h
0x1800353d0  pop     r15
0x1800353d2  pop     r14
0x1800353d4  pop     r12
0x1800353d6  pop     rdi
0x1800353d7  pop     rsi
0x1800353d8  pop     rbx
0x1800353d9  pop     rbp
0x1800353da  retn
```
