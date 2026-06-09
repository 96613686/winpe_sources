# SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x180034f60`
- end: `0x180035202`
- name: `?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z`
- size: `674`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c408`
- `0x180011c70`
- `0x180019c1c`
- `0x18001a454`
- `0x18001a914`
- `0x18001e4f0`
- `0x18001e8b0`
- `0x18001f1a4`
- `0x1800217e0`
- `0x180022dec`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180034f60`
- `0x1800353e4`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180034fe3`
- `ntdll!EtwEventEnabled` at `0x180034fe3`
- `ntdll!EtwEventWrite` at `0x180035187`
- `ntdll!EtwEventWrite` at `0x180035187`

## string_xrefs

- `0x180035192`: `Event: %u, label: %ws, message: %ws, info: %ws, inf path: %ws, driver: %ws, install section: %ws, platform: %ws, LE: 0x%08X, hr: 0x%08X, EventWrite: %d`

## pseudocode

```c
void __fastcall SplLogPrinterSetupEvent(
        const struct _EVENT_DESCRIPTOR *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        unsigned int a9,
        unsigned int a10)
{
  __int64 v13; // rax
  const wchar_t *v14; // rdx
  __int64 v15; // rcx
  int v16; // ecx
  const wchar_t *v17; // r8
  __int64 v18; // rcx
  int v19; // ecx
  const wchar_t *v20; // r8
  __int64 v21; // rcx
  int v22; // ecx
  const wchar_t *v23; // r8
  __int64 v24; // rcx
  int v25; // ecx
  const wchar_t *v26; // r8
  __int64 v27; // rcx
  int v28; // ecx
  const wchar_t *v29; // r8
  __int64 v30; // rcx
  int v31; // ecx
  const wchar_t *v32; // r8
  int v33; // eax
  int v34; // [rsp+60h] [rbp-A0h]
  const wchar_t *v36; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v37[2]; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v38; // [rsp+90h] [rbp-70h]
  int v39; // [rsp+98h] [rbp-68h]
  int v40; // [rsp+9Ch] [rbp-64h]
  const wchar_t *v41; // [rsp+A0h] [rbp-60h]
  int v42; // [rsp+A8h] [rbp-58h]
  int v43; // [rsp+ACh] [rbp-54h]
  const wchar_t *v44; // [rsp+B0h] [rbp-50h]
  int v45; // [rsp+B8h] [rbp-48h]
  int v46; // [rsp+BCh] [rbp-44h]
  const wchar_t *v47; // [rsp+C0h] [rbp-40h]
  int v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+CCh] [rbp-34h]
  const wchar_t *v50; // [rsp+D0h] [rbp-30h]
  int v51; // [rsp+D8h] [rbp-28h]
  int v52; // [rsp+DCh] [rbp-24h]
  const wchar_t *v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+E8h] [rbp-18h]
  int v55; // [rsp+ECh] [rbp-14h]
  unsigned int *v56; // [rsp+F0h] [rbp-10h]
  __int64 v57; // [rsp+F8h] [rbp-8h]
  unsigned int *v58; // [rsp+100h] [rbp+0h]
  __int64 v59; // [rsp+108h] [rbp+8h]

  v36 = 0;
  memset_0(v37, 0, 0x98u);
  if ( g_bTracingEnabled && (unsigned __int8)EtwEventEnabled(g_splRegistrationHandle, a1) && a1 )
  {
    v13 = -1;
    v14 = L"-";
    if ( a2 )
    {
      v15 = -1;
      do
        ++v15;
      while ( a2[v15] );
      v16 = 2 * v15 + 2;
      v17 = a2;
    }
    else
    {
      v16 = 4;
      v17 = L"-";
    }
    v36 = v17;
    v37[0] = v16;
    v37[1] = 0;
    if ( a3 )
    {
      v18 = -1;
      do
        ++v18;
      while ( a3[v18] );
      v19 = 2 * v18 + 2;
      v20 = a3;
    }
    else
    {
      v19 = 4;
      v20 = L"-";
    }
    v38 = v20;
    v39 = v19;
    v40 = 0;
    if ( a4 )
    {
      v21 = -1;
      do
        ++v21;
      while ( a4[v21] );
      v22 = 2 * v21 + 2;
      v23 = a4;
    }
    else
    {
      v22 = 4;
      v23 = L"-";
    }
    v41 = v23;
    v42 = v22;
    v43 = 0;
    if ( a5 )
    {
      v24 = -1;
      do
        ++v24;
      while ( a5[v24] );
      v25 = 2 * v24 + 2;
      v26 = a5;
    }
    else
    {
      v25 = 4;
      v26 = L"-";
    }
    v44 = v26;
    v45 = v25;
    v46 = 0;
    if ( a6 )
    {
      v27 = -1;
      do
        ++v27;
      while ( a6[v27] );
      v28 = 2 * v27 + 2;
      v29 = a6;
    }
    else
    {
      v28 = 4;
      v29 = L"-";
    }
    v47 = v29;
    v48 = v28;
    v49 = 0;
    if ( a7 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a7[v30] );
      v31 = 2 * v30 + 2;
      v32 = a7;
    }
    else
    {
      v31 = 4;
      v32 = L"-";
    }
    v50 = v32;
    v51 = v31;
    v52 = 0;
    if ( a8 )
    {
      do
        ++v13;
      while ( a8[v13] );
      v33 = 2 * v13 + 2;
      v14 = a8;
    }
    else
    {
      v33 = 4;
    }
    v54 = v33;
    v56 = &a9;
    v53 = v14;
    v55 = 0;
    v58 = &a10;
    v57 = 4;
    v59 = 4;
    v34 = EtwEventWrite(g_splRegistrationHandle, a1, 9, &v36);
    PerfLibTelemetry::WriteDbgTraceInfo(
      "SplLogPrinterSetupEvent",
      L"Event: %u, label: %ws, message: %ws, info: %ws, inf path: %ws, driver: %ws, install section: %ws, platform: %ws, L"
       "E: 0x%08X, hr: 0x%08X, EventWrite: %d",
      a1->Id,
      a2,
      a3,
      a4,
      a5,
      a6,
      a7,
      a8,
      a9,
      a10,
      v34);
  }
}

```

## disassembly

```asm
0x180034f60  push    rbp
0x180034f62  push    rbx
0x180034f63  push    rsi
0x180034f64  push    rdi
0x180034f65  push    r12
0x180034f67  push    r13
0x180034f69  push    r14
0x180034f6b  push    r15
0x180034f6d  lea     rbp, [rsp-38h]
0x180034f72  sub     rsp, 138h
0x180034f79  mov     rax, cs:__security_cookie
0x180034f80  xor     rax, rsp
0x180034f83  mov     [rbp+70h+var_50], rax
0x180034f87  mov     r15, [rbp+70h+arg_20]
0x180034f8e  mov     rsi, r8
0x180034f91  mov     r12, [rbp+70h+arg_28]
0x180034f98  mov     rdi, rdx
0x180034f9b  mov     r13, [rbp+70h+arg_30]
0x180034fa2  xor     edx, edx; Val
0x180034fa4  mov     rbx, [rbp+70h+arg_38]
0x180034fab  mov     r8d, 98h; Size
0x180034fb1  mov     [rsp+170h+var_100], rcx
0x180034fb6  mov     r14, r9
0x180034fb9  lea     rcx, [rbp+70h+var_E8]; void *
0x180034fbd  mov     [rbp+70h+var_F0], 0
0x180034fc5  call    memset_0
0x180034fca  cmp     cs:?g_bTracingEnabled@@3HA, 0; int g_bTracingEnabled
0x180034fd1  jz      loc_1800351E2
0x180034fd7  mov     rdx, [rsp+170h+var_100]
0x180034fdc  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180034fe3  call    cs:__imp_EtwEventEnabled
0x180034fe9  xor     r9d, r9d
0x180034fec  test    al, al
0x180034fee  jz      loc_1800351E2
0x180034ff4  mov     r10, [rsp+170h+var_100]
0x180034ff9  test    r10, r10
0x180034ffc  jz      loc_1800351E2
0x180035002  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035006  lea     r11d, [r9+4]
0x18003500a  lea     rdx, asc_18004D604; "-"
0x180035011  test    rdi, rdi
0x180035014  jz      short loc_18003502F
0x180035016  mov     rcx, rax
0x180035019  inc     rcx
0x18003501c  cmp     [rdi+rcx*2], r9w
0x180035021  jnz     short loc_180035019
0x180035023  lea     ecx, ds:2[rcx*2]
0x18003502a  mov     r8, rdi
0x18003502d  jmp     short loc_180035035
0x18003502f  mov     ecx, r11d
0x180035032  mov     r8, rdx
0x180035035  mov     [rbp+70h+var_F0], r8
0x180035039  mov     [rbp+70h+var_E8], ecx
0x18003503c  mov     [rbp+70h+var_E4], r9d
0x180035040  test    rsi, rsi
0x180035043  jz      short loc_18003505E
0x180035045  mov     rcx, rax
0x180035048  inc     rcx
0x18003504b  cmp     [rsi+rcx*2], r9w
0x180035050  jnz     short loc_180035048
0x180035052  lea     ecx, ds:2[rcx*2]
0x180035059  mov     r8, rsi
0x18003505c  jmp     short loc_180035064
0x18003505e  mov     ecx, r11d
0x180035061  mov     r8, rdx
0x180035064  mov     [rbp+70h+var_E0], r8
0x180035068  mov     [rbp+70h+var_D8], ecx
0x18003506b  mov     [rbp+70h+var_D4], r9d
0x18003506f  test    r14, r14
0x180035072  jz      short loc_18003508D
0x180035074  mov     rcx, rax
0x180035077  inc     rcx
0x18003507a  cmp     [r14+rcx*2], r9w
0x18003507f  jnz     short loc_180035077
0x180035081  lea     ecx, ds:2[rcx*2]
0x180035088  mov     r8, r14
0x18003508b  jmp     short loc_180035093
0x18003508d  mov     ecx, r11d
0x180035090  mov     r8, rdx
0x180035093  mov     [rbp+70h+var_D0], r8
0x180035097  mov     [rbp+70h+var_C8], ecx
0x18003509a  mov     [rbp+70h+var_C4], r9d
0x18003509e  test    r15, r15
0x1800350a1  jz      short loc_1800350BC
0x1800350a3  mov     rcx, rax
0x1800350a6  inc     rcx
0x1800350a9  cmp     [r15+rcx*2], r9w
0x1800350ae  jnz     short loc_1800350A6
0x1800350b0  lea     ecx, ds:2[rcx*2]
0x1800350b7  mov     r8, r15
0x1800350ba  jmp     short loc_1800350C2
0x1800350bc  mov     ecx, r11d
0x1800350bf  mov     r8, rdx
0x1800350c2  mov     [rbp+70h+var_C0], r8
0x1800350c6  mov     [rbp+70h+var_B8], ecx
0x1800350c9  mov     [rbp+70h+var_B4], r9d
0x1800350cd  test    r12, r12
0x1800350d0  jz      short loc_1800350EB
0x1800350d2  mov     rcx, rax
0x1800350d5  inc     rcx
0x1800350d8  cmp     [r12+rcx*2], r9w
0x1800350dd  jnz     short loc_1800350D5
0x1800350df  lea     ecx, ds:2[rcx*2]
0x1800350e6  mov     r8, r12
0x1800350e9  jmp     short loc_1800350F1
0x1800350eb  mov     ecx, r11d
0x1800350ee  mov     r8, rdx
0x1800350f1  mov     [rbp+70h+var_B0], r8
0x1800350f5  mov     [rbp+70h+var_A8], ecx
0x1800350f8  mov     [rbp+70h+var_A4], r9d
0x1800350fc  test    r13, r13
0x1800350ff  jz      short loc_18003511B
0x180035101  mov     rcx, rax
0x180035104  inc     rcx
0x180035107  cmp     [r13+rcx*2+0], r9w
0x18003510d  jnz     short loc_180035104
0x18003510f  lea     ecx, ds:2[rcx*2]
0x180035116  mov     r8, r13
0x180035119  jmp     short loc_180035121
0x18003511b  mov     ecx, r11d
0x18003511e  mov     r8, rdx
0x180035121  mov     [rbp+70h+var_A0], r8
0x180035125  mov     [rbp+70h+var_98], ecx
0x180035128  mov     [rbp+70h+var_94], r9d
0x18003512c  test    rbx, rbx
0x18003512f  jz      short loc_180035147
0x180035131  inc     rax
0x180035134  cmp     [rbx+rax*2], r9w
0x180035139  jnz     short loc_180035131
0x18003513b  lea     eax, ds:2[rax*2]
0x180035142  mov     rdx, rbx
0x180035145  jmp     short loc_18003514A
0x180035147  mov     eax, r11d
0x18003514a  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180035151  mov     r8d, 9
0x180035157  mov     [rbp+70h+var_88], eax
0x18003515a  lea     rax, [rbp+70h+arg_40]
0x180035161  mov     [rbp+70h+var_80], rax
0x180035165  lea     rax, [rbp+70h+arg_48]
0x18003516c  mov     [rbp+70h+var_90], rdx
0x180035170  mov     rdx, r10
0x180035173  mov     [rbp+70h+var_84], r9d
0x180035177  lea     r9, [rbp+70h+var_F0]
0x18003517b  mov     [rbp+70h+var_70], rax
0x18003517f  mov     [rbp+70h+var_78], r11
0x180035183  mov     [rbp+70h+var_68], r11
0x180035187  call    cs:__imp_EtwEventWrite
0x18003518d  mov     rcx, [rsp+170h+var_100]
0x180035192  lea     rdx, aEventULabelWsM_1; "Event: %u, label: %ws, message: %ws, in"...
0x180035199  mov     [rsp+170h+var_110], eax
0x18003519d  mov     r9, rdi
0x1800351a0  mov     eax, [rbp+70h+arg_48]
0x1800351a6  mov     [rsp+170h+var_118], eax
0x1800351aa  mov     eax, [rbp+70h+arg_40]
0x1800351b0  movzx   r8d, word ptr [rcx]
0x1800351b4  lea     rcx, aSpllogprinters_1; "SplLogPrinterSetupEvent"
0x1800351bb  mov     [rsp+170h+var_120], eax
0x1800351bf  mov     [rsp+170h+var_128], rbx
0x1800351c4  mov     [rsp+170h+var_130], r13
0x1800351c9  mov     [rsp+170h+var_138], r12
0x1800351ce  mov     [rsp+170h+var_140], r15
0x1800351d3  mov     [rsp+170h+var_148], r14
0x1800351d8  mov     [rsp+170h+var_150], rsi
0x1800351dd  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800351e2  mov     rcx, [rbp+70h+var_50]
0x1800351e6  xor     rcx, rsp; StackCookie
0x1800351e9  call    __security_check_cookie
0x1800351ee  add     rsp, 138h
0x1800351f5  pop     r15
0x1800351f7  pop     r14
0x1800351f9  pop     r13
0x1800351fb  pop     r12
0x1800351fd  pop     rdi
0x1800351fe  pop     rsi
0x1800351ff  pop     rbx
0x180035200  pop     rbp
0x180035201  retn
```
