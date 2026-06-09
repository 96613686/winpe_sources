# SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)

- ea: `0x180034bec`
- end: `0x180034f58`
- name: `?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z`
- size: `876`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `16`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180009d64`
- `0x18000b498`
- `0x18000b7ec`
- `0x18000d314`
- `0x18000db80`
- `0x18000eb10`
- `0x18000ed30`
- `0x18000f698`
- `0x1800113c0`
- `0x180011c70`
- `0x18001825c`
- `0x180019908`
- `0x18001c978`
- `0x18001f958`
- `0x1800217e0`
- `0x180022dec`

## callees

- `0x180001efc`
- `0x180002300`
- `0x180002f48`
- `0x1800348d8`
- `0x180034bec`
- `0x1800353e4`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180034c8a`
- `ntdll!EtwEventEnabled` at `0x180034c8a`
- `ntdll!EtwEventWrite` at `0x180034ebc`
- `ntdll!EtwEventWrite` at `0x180034ebc`

## string_xrefs

- `0x180034ec6`: `Event: %u, label: %ws, message: %ws, info: %ws, inf path: %ws, driver: %ws, install section: %ws, platform: %ws, package aware: %u, core deps: %ws, LE: 0x%08X, hr: 0x%08X, EventWrite: %d`

## pseudocode

```c
void __fastcall SplLogPrinterSetupCoreDriverEvent(
        const struct _EVENT_DESCRIPTOR *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        int a9,
        unsigned __int16 *a10,
        unsigned int a11,
        unsigned int a12)
{
  void *v15; // rsi
  __int64 v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  const wchar_t *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  int v25; // eax
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  const wchar_t *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  const wchar_t *v32; // rcx
  const wchar_t *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const wchar_t *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rax
  int v40; // eax
  unsigned int v41; // ebx
  unsigned __int16 *p_Id; // rbx
  int v43; // [rsp+70h] [rbp-90h]
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v45; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v46; // [rsp+90h] [rbp-70h]
  const unsigned __int16 *v47; // [rsp+98h] [rbp-68h]
  const struct _EVENT_DESCRIPTOR *v48; // [rsp+A0h] [rbp-60h]
  const unsigned __int16 *v49; // [rsp+A8h] [rbp-58h]
  const wchar_t *v50; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v51[2]; // [rsp+B8h] [rbp-48h] BYREF
  const wchar_t *v52; // [rsp+C0h] [rbp-40h]
  int v53; // [rsp+C8h] [rbp-38h]
  int v54; // [rsp+CCh] [rbp-34h]
  const wchar_t *v55; // [rsp+D0h] [rbp-30h]
  int v56; // [rsp+D8h] [rbp-28h]
  int v57; // [rsp+DCh] [rbp-24h]
  const wchar_t *v58; // [rsp+E0h] [rbp-20h]
  int v59; // [rsp+E8h] [rbp-18h]
  int v60; // [rsp+ECh] [rbp-14h]
  const wchar_t *v61; // [rsp+F0h] [rbp-10h]
  int v62; // [rsp+F8h] [rbp-8h]
  int v63; // [rsp+FCh] [rbp-4h]
  const wchar_t *v64; // [rsp+100h] [rbp+0h]
  int v65; // [rsp+108h] [rbp+8h]
  int v66; // [rsp+10Ch] [rbp+Ch]
  const wchar_t *v67; // [rsp+110h] [rbp+10h]
  int v68; // [rsp+118h] [rbp+18h]
  int v69; // [rsp+11Ch] [rbp+1Ch]
  const wchar_t *v70; // [rsp+120h] [rbp+20h]
  int v71; // [rsp+128h] [rbp+28h]
  int v72; // [rsp+12Ch] [rbp+2Ch]
  const wchar_t *v73; // [rsp+130h] [rbp+30h]
  __int64 v74; // [rsp+138h] [rbp+38h]
  unsigned int *v75; // [rsp+140h] [rbp+40h]
  __int64 v76; // [rsp+148h] [rbp+48h]
  unsigned int *v77; // [rsp+150h] [rbp+50h]
  __int64 v78; // [rsp+158h] [rbp+58h]

  v48 = a1;
  v15 = 0;
  v47 = a7;
  v46 = a8;
  v45 = a10;
  v49 = a6;
  v50 = 0;
  memset_0(v51, 0, 0xB8u);
  Block = 0;
  if ( g_bTracingEnabled && (unsigned __int8)EtwEventEnabled(g_splRegistrationHandle, a1) && a1 )
  {
    v17 = -1;
    if ( a2 )
    {
      v18 = -1;
      do
        ++v18;
      while ( a2[v18] );
      v19 = 2 * v18 + 2;
      v20 = a2;
    }
    else
    {
      v19 = 4;
      v20 = L"-";
    }
    v50 = v20;
    v51[0] = v19;
    v51[1] = 0;
    if ( a3 )
    {
      v21 = -1;
      do
        ++v21;
      while ( a3[v21] );
      v22 = 2 * v21 + 2;
      v23 = a3;
    }
    else
    {
      v22 = 4;
      v23 = L"-";
    }
    v52 = v23;
    v53 = v22;
    v54 = 0;
    if ( a4 )
    {
      v24 = -1;
      do
        ++v24;
      while ( a4[v24] );
      v25 = 2 * v24 + 2;
      v26 = a4;
    }
    else
    {
      v25 = 4;
      v26 = L"-";
    }
    v55 = v26;
    v56 = v25;
    v57 = 0;
    if ( a5 )
    {
      v27 = -1;
      do
        ++v27;
      while ( a5[v27] );
      v28 = 2 * v27 + 2;
      v29 = a5;
    }
    else
    {
      v28 = 4;
      v29 = L"-";
    }
    v58 = v29;
    v59 = v28;
    v60 = 0;
    if ( a6 )
    {
      v30 = -1;
      do
        ++v30;
      while ( a6[v30] );
      v31 = 2 * v30 + 2;
      v32 = a6;
    }
    else
    {
      v31 = 4;
      v32 = L"-";
    }
    v61 = v32;
    v33 = v47;
    v62 = v31;
    v63 = 0;
    if ( v47 )
    {
      v34 = -1;
      do
        ++v34;
      while ( v47[v34] );
      v35 = 2 * v34 + 2;
    }
    else
    {
      v35 = 4;
      v33 = L"-";
    }
    v64 = v33;
    v36 = v46;
    v65 = v35;
    v66 = 0;
    if ( v46 )
    {
      v37 = -1;
      do
        ++v37;
      while ( v46[v37] );
      v38 = 2 * v37 + 2;
    }
    else
    {
      v38 = 4;
      v36 = L"-";
    }
    v68 = v38;
    v39 = L"Package aware";
    v67 = v36;
    if ( !a9 )
      v39 = L"Not package aware";
    v69 = 0;
    v70 = v39;
    v72 = 0;
    v71 = a9 != 0 ? 28 : 36;
    if ( v45 )
    {
      v40 = ConvertMultiToSingleSz(v45, (unsigned __int16 **)&Block);
      v15 = Block;
      if ( v40 >= 0 && Block )
      {
        do
          ++v17;
        while ( *((_WORD *)Block + v17) );
        v73 = (const wchar_t *)Block;
        v41 = 2 * v17 + 2;
      }
      else
      {
        v41 = 16;
        v73 = L"<error>";
      }
      v74 = v41;
    }
    else
    {
      v73 = L"-";
      v74 = 4;
    }
    p_Id = &v48->Id;
    v75 = &a11;
    v76 = 4;
    v77 = &a12;
    v78 = 4;
    v43 = EtwEventWrite(g_splRegistrationHandle, v48, 11, &v50);
    PerfLibTelemetry::WriteDbgTraceInfo(
      "SplLogPrinterSetupCoreDriverEvent",
      L"Event: %u, label: %ws, message: %ws, info: %ws, inf path: %ws, driver: %ws, install section: %ws, platform: %ws, p"
       "ackage aware: %u, core deps: %ws, LE: 0x%08X, hr: 0x%08X, EventWrite: %d",
      *p_Id,
      a2,
      a3,
      a4,
      a5,
      v49,
      v47,
      v46,
      a9,
      v45,
      a11,
      a12,
      v43);
    if ( v15 )
      operator delete(v15);
  }
}

```

## disassembly

```asm
0x180034bec  push    rbp
0x180034bee  push    rbx
0x180034bef  push    rsi
0x180034bf0  push    rdi
0x180034bf1  push    r12
0x180034bf3  push    r13
0x180034bf5  push    r14
0x180034bf7  push    r15
0x180034bf9  lea     rbp, [rsp-88h]
0x180034c01  sub     rsp, 188h
0x180034c08  mov     rax, cs:__security_cookie
0x180034c0f  xor     rax, rsp
0x180034c12  mov     [rbp+0C0h+var_50], rax
0x180034c16  mov     rax, [rbp+0C0h+arg_30]
0x180034c1d  mov     rbx, rcx
0x180034c20  mov     rdi, [rbp+0C0h+arg_28]
0x180034c27  mov     r15, r8
0x180034c2a  mov     r13, [rbp+0C0h+arg_20]
0x180034c31  mov     r14, rdx
0x180034c34  mov     [rbp+0C0h+var_120], rcx
0x180034c38  xor     esi, esi
0x180034c3a  mov     rcx, [rbp+0C0h+arg_38]
0x180034c41  xor     edx, edx; Val
0x180034c43  mov     [rbp+0C0h+var_128], rax
0x180034c47  mov     r8d, 0B8h; Size
0x180034c4d  mov     rax, [rbp+0C0h+arg_48]
0x180034c54  mov     r12, r9
0x180034c57  mov     [rbp+0C0h+var_130], rcx
0x180034c5b  lea     rcx, [rbp+0C0h+var_108]; void *
0x180034c5f  mov     [rbp+0C0h+var_138], rax
0x180034c63  mov     [rbp+0C0h+var_118], rdi
0x180034c67  mov     [rbp+0C0h+var_110], rsi
0x180034c6b  call    memset_0
0x180034c70  cmp     cs:?g_bTracingEnabled@@3HA, esi; int g_bTracingEnabled
0x180034c76  mov     [rbp+0C0h+Block], rsi
0x180034c7a  jz      loc_180034F38
0x180034c80  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180034c87  mov     rdx, rbx
0x180034c8a  call    cs:__imp_EtwEventEnabled
0x180034c90  xor     edx, edx
0x180034c92  test    al, al
0x180034c94  jz      loc_180034F38
0x180034c9a  test    rbx, rbx
0x180034c9d  jz      loc_180034F38
0x180034ca3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034ca7  lea     r9d, [rsi+4]
0x180034cab  lea     r8, asc_18004D604; "-"
0x180034cb2  test    r14, r14
0x180034cb5  jz      short loc_180034CD0
0x180034cb7  mov     rax, rbx
0x180034cba  inc     rax
0x180034cbd  cmp     [r14+rax*2], dx
0x180034cc2  jnz     short loc_180034CBA
0x180034cc4  lea     eax, ds:2[rax*2]
0x180034ccb  mov     rcx, r14
0x180034cce  jmp     short loc_180034CD6
0x180034cd0  mov     eax, r9d
0x180034cd3  mov     rcx, r8
0x180034cd6  mov     [rbp+0C0h+var_110], rcx
0x180034cda  mov     [rbp+0C0h+var_108], eax
0x180034cdd  mov     [rbp+0C0h+var_104], edx
0x180034ce0  test    r15, r15
0x180034ce3  jz      short loc_180034CFE
0x180034ce5  mov     rax, rbx
0x180034ce8  inc     rax
0x180034ceb  cmp     [r15+rax*2], dx
0x180034cf0  jnz     short loc_180034CE8
0x180034cf2  lea     eax, ds:2[rax*2]
0x180034cf9  mov     rcx, r15
0x180034cfc  jmp     short loc_180034D04
0x180034cfe  mov     eax, r9d
0x180034d01  mov     rcx, r8
0x180034d04  mov     [rbp+0C0h+var_100], rcx
0x180034d08  mov     [rbp+0C0h+var_F8], eax
0x180034d0b  mov     [rbp+0C0h+var_F4], edx
0x180034d0e  test    r12, r12
0x180034d11  jz      short loc_180034D2C
0x180034d13  mov     rax, rbx
0x180034d16  inc     rax
0x180034d19  cmp     [r12+rax*2], dx
0x180034d1e  jnz     short loc_180034D16
0x180034d20  lea     eax, ds:2[rax*2]
0x180034d27  mov     rcx, r12
0x180034d2a  jmp     short loc_180034D32
0x180034d2c  mov     eax, r9d
0x180034d2f  mov     rcx, r8
0x180034d32  mov     [rbp+0C0h+var_F0], rcx
0x180034d36  mov     [rbp+0C0h+var_E8], eax
0x180034d39  mov     [rbp+0C0h+var_E4], edx
0x180034d3c  test    r13, r13
0x180034d3f  jz      short loc_180034D5B
0x180034d41  mov     rax, rbx
0x180034d44  inc     rax
0x180034d47  cmp     [r13+rax*2+0], dx
0x180034d4d  jnz     short loc_180034D44
0x180034d4f  lea     eax, ds:2[rax*2]
0x180034d56  mov     rcx, r13
0x180034d59  jmp     short loc_180034D61
0x180034d5b  mov     eax, r9d
0x180034d5e  mov     rcx, r8
0x180034d61  mov     [rbp+0C0h+var_E0], rcx
0x180034d65  mov     [rbp+0C0h+var_D8], eax
0x180034d68  mov     [rbp+0C0h+var_D4], edx
0x180034d6b  test    rdi, rdi
0x180034d6e  jz      short loc_180034D88
0x180034d70  mov     rax, rbx
0x180034d73  inc     rax
0x180034d76  cmp     [rdi+rax*2], dx
0x180034d7a  jnz     short loc_180034D73
0x180034d7c  lea     eax, ds:2[rax*2]
0x180034d83  mov     rcx, rdi
0x180034d86  jmp     short loc_180034D8E
0x180034d88  mov     eax, r9d
0x180034d8b  mov     rcx, r8
0x180034d8e  mov     [rbp+0C0h+var_D0], rcx
0x180034d92  mov     rcx, [rbp+0C0h+var_128]
0x180034d96  mov     [rbp+0C0h+var_C8], eax
0x180034d99  mov     [rbp+0C0h+var_C4], edx
0x180034d9c  test    rcx, rcx
0x180034d9f  jz      short loc_180034DB6
0x180034da1  mov     rax, rbx
0x180034da4  inc     rax
0x180034da7  cmp     [rcx+rax*2], dx
0x180034dab  jnz     short loc_180034DA4
0x180034dad  lea     eax, ds:2[rax*2]
0x180034db4  jmp     short loc_180034DBC
0x180034db6  mov     eax, r9d
0x180034db9  mov     rcx, r8
0x180034dbc  mov     [rbp+0C0h+var_C0], rcx
0x180034dc0  mov     rcx, [rbp+0C0h+var_130]
0x180034dc4  mov     [rbp+0C0h+var_B8], eax
0x180034dc7  mov     [rbp+0C0h+var_B4], edx
0x180034dca  test    rcx, rcx
0x180034dcd  jz      short loc_180034DE4
0x180034dcf  mov     rax, rbx
0x180034dd2  inc     rax
0x180034dd5  cmp     [rcx+rax*2], dx
0x180034dd9  jnz     short loc_180034DD2
0x180034ddb  lea     eax, ds:2[rax*2]
0x180034de2  jmp     short loc_180034DEA
0x180034de4  mov     eax, r9d
0x180034de7  mov     rcx, r8
0x180034dea  mov     edi, [rbp+0C0h+arg_40]
0x180034df0  test    edi, edi
0x180034df2  mov     [rbp+0C0h+var_A8], eax
0x180034df5  lea     rax, aPackageAware; "Package aware"
0x180034dfc  mov     [rbp+0C0h+var_B0], rcx
0x180034e00  lea     rcx, aNotPackageAwar_0; "Not package aware"
0x180034e07  cmovz   rax, rcx
0x180034e0b  mov     [rbp+0C0h+var_A4], edx
0x180034e0e  mov     [rbp+0C0h+var_A0], rax
0x180034e12  mov     eax, edi
0x180034e14  neg     eax
0x180034e16  mov     [rbp+0C0h+var_94], edx
0x180034e19  mov     rax, [rbp+0C0h+var_138]
0x180034e1d  sbb     ecx, ecx
0x180034e1f  and     ecx, 0FFFFFFF8h
0x180034e22  add     ecx, 24h ; '$'
0x180034e25  mov     [rbp+0C0h+var_98], ecx
0x180034e28  test    rax, rax
0x180034e2b  jz      short loc_180034E76
0x180034e2d  lea     rdx, [rbp+0C0h+Block]; unsigned __int16 **
0x180034e31  mov     rcx, rax; unsigned __int16 *
0x180034e34  call    ?ConvertMultiToSingleSz@@YAJPEBGPEAPEAG@Z; ConvertMultiToSingleSz(ushort const *,ushort * *)
0x180034e39  mov     rsi, [rbp+0C0h+Block]
0x180034e3d  xor     edx, edx
0x180034e3f  test    eax, eax
0x180034e41  js      short loc_180034E5E
0x180034e43  test    rsi, rsi
0x180034e46  jz      short loc_180034E5E
0x180034e48  inc     rbx
0x180034e4b  cmp     [rsi+rbx*2], dx
0x180034e4f  jnz     short loc_180034E48
0x180034e51  mov     [rbp+0C0h+var_90], rsi
0x180034e55  lea     ebx, ds:2[rbx*2]
0x180034e5c  jmp     short loc_180034E6E
0x180034e5e  lea     rax, aError; "<error>"
0x180034e65  mov     ebx, 10h
0x180034e6a  mov     [rbp+0C0h+var_90], rax
0x180034e6e  mov     dword ptr [rbp+0C0h+var_88], ebx
0x180034e71  mov     dword ptr [rbp+0C0h+var_88+4], edx
0x180034e74  jmp     short loc_180034E7E
0x180034e76  mov     [rbp+0C0h+var_90], r8
0x180034e7a  mov     [rbp+0C0h+var_88], r9
0x180034e7e  mov     rbx, [rbp+0C0h+var_120]
0x180034e82  lea     rax, [rbp+0C0h+arg_50]
0x180034e89  mov     rcx, cs:?g_splRegistrationHandle@@3_KA; unsigned __int64 g_splRegistrationHandle
0x180034e90  lea     r9, [rbp+0C0h+var_110]
0x180034e94  mov     [rbp+0C0h+var_80], rax
0x180034e98  mov     r8d, 0Bh
0x180034e9e  lea     rax, [rbp+0C0h+arg_58]
0x180034ea5  mov     [rbp+0C0h+var_78], 4
0x180034ead  mov     rdx, rbx
0x180034eb0  mov     [rbp+0C0h+var_70], rax
0x180034eb4  mov     [rbp+0C0h+var_68], 4
0x180034ebc  call    cs:__imp_EtwEventWrite
0x180034ec2  mov     rcx, [rbp+0C0h+var_130]
0x180034ec6  lea     rdx, aEventULabelWsM; "Event: %u, label: %ws, message: %ws, in"...
0x180034ecd  movzx   r8d, word ptr [rbx]
0x180034ed1  mov     r9, r14
0x180034ed4  mov     [rsp+1C0h+var_150], eax
0x180034ed8  mov     eax, [rbp+0C0h+arg_58]
0x180034ede  mov     [rsp+1C0h+var_158], eax
0x180034ee2  mov     eax, [rbp+0C0h+arg_50]
0x180034ee8  mov     [rsp+1C0h+var_160], eax
0x180034eec  mov     rax, [rbp+0C0h+var_138]
0x180034ef0  mov     [rsp+1C0h+var_168], rax
0x180034ef5  mov     rax, [rbp+0C0h+var_128]
0x180034ef9  mov     [rsp+1C0h+var_170], edi
0x180034efd  mov     [rsp+1C0h+var_178], rcx
0x180034f02  lea     rcx, aSpllogprinters; "SplLogPrinterSetupCoreDriverEvent"
0x180034f09  mov     [rsp+1C0h+var_180], rax
0x180034f0e  mov     rax, [rbp+0C0h+var_118]
0x180034f12  mov     [rsp+1C0h+var_188], rax
0x180034f17  mov     [rsp+1C0h+var_190], r13
0x180034f1c  mov     [rsp+1C0h+var_198], r12
0x180034f21  mov     [rsp+1C0h+var_1A0], r15
0x180034f26  call    ?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ; PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180034f2b  test    rsi, rsi
0x180034f2e  jz      short loc_180034F38
0x180034f30  mov     rcx, rsi; Block
0x180034f33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034f38  mov     rcx, [rbp+0C0h+var_50]
0x180034f3c  xor     rcx, rsp; StackCookie
0x180034f3f  call    __security_check_cookie
0x180034f44  add     rsp, 188h
0x180034f4b  pop     r15
0x180034f4d  pop     r14
0x180034f4f  pop     r13
0x180034f51  pop     r12
0x180034f53  pop     rdi
0x180034f54  pop     rsi
0x180034f55  pop     rbx
0x180034f56  pop     rbp
0x180034f57  retn
```
