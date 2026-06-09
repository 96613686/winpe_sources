# CleanupMgrTelemetry::CleanmgrPluginInitialize::Stop(ushort const *,_GUID,bool,ushort *,ushort *,bool,bool,bool,double,double,long)

- ea: `0x140010894`
- end: `0x140010974`
- name: `?Stop@CleanmgrPluginInitialize@CleanupMgrTelemetry@@QEAAXPEBGU_GUID@@_NPEAG3222NNJ@Z`
- size: `224`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanmgrPluginInitialize *this, const unsigned __int16 *, struct _GUID *, char, unsigned __int16 *, unsigned __int16 *, char, char, char, double, double, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013530`

## callees

- `0x140010894`
- `0x1400169d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400108a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400108a5`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanmgrPluginInitialize::Stop(
        CleanupMgrTelemetry::CleanmgrPluginInitialize *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        char a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        char a7,
        char a8,
        char a9,
        double a10,
        double a11,
        char a12)
{
  int v13; // edi
  ULONGLONG TickCount64; // rax
  ULONGLONG v15; // rcx
  double v16; // xmm2_8
  double v17; // xmm2_8

  v13 = (int)a2;
  TickCount64 = GetTickCount64();
  if ( (Microsoft_Windows_CleanmgrEnableBits & 1) != 0 )
  {
    v15 = TickCount64 - cleanmgrBeforePluginInitializationTick;
    if ( (__int64)(TickCount64 - cleanmgrBeforePluginInitializationTick) < 0 )
      v16 = (double)(int)(v15 & 1 | (v15 >> 1)) + (double)(int)(v15 & 1 | (v15 >> 1));
    else
      v16 = (double)(int)v15;
    v17 = v16 / 1000.0;
    McTemplateU0qztzztttgggd_EventWriteTransfer(
      (unsigned __int8)a9,
      (unsigned __int8)a8,
      (unsigned __int8)a7,
      v13,
      a4,
      (__int64)a5,
      (__int64)a6,
      a7,
      a8,
      a9,
      SLOBYTE(v17),
      SLOBYTE(a10),
      SLOBYTE(a11),
      a12);
  }
}

```

## disassembly

```asm
0x140010894  mov     [rsp+arg_0], rbx
0x140010899  push    rdi
0x14001089a  sub     rsp, 70h
0x14001089e  movzx   ebx, r9b
0x1400108a2  mov     rdi, rdx
0x1400108a5  call    cs:__imp_GetTickCount64
0x1400108ab  test    cs:Microsoft_Windows_CleanmgrEnableBits, 1
0x1400108b2  mov     rcx, rax
0x1400108b5  jz      loc_140010966
0x1400108bb  sub     rcx, cs:?cleanmgrBeforePluginInitializationTick@@3_KA; unsigned __int64 cleanmgrBeforePluginInitializationTick
0x1400108c2  xorps   xmm2, xmm2
0x1400108c5  js      short loc_1400108CE
0x1400108c7  cvtsi2sd xmm2, rcx
0x1400108cc  jmp     short loc_1400108E3
0x1400108ce  mov     rax, rcx
0x1400108d1  and     ecx, 1
0x1400108d4  shr     rax, 1
0x1400108d7  or      rax, rcx
0x1400108da  cvtsi2sd xmm2, rax
0x1400108df  addsd   xmm2, xmm2
0x1400108e3  divsd   xmm2, cs:__real@408f400000000000
0x1400108eb  mov     eax, [rsp+78h+arg_58]
0x1400108f2  mov     r9, rdi
0x1400108f5  movzx   ecx, [rsp+78h+arg_40]
0x1400108fd  movzx   edx, [rsp+78h+arg_38]
0x140010905  movzx   r8d, [rsp+78h+arg_30]
0x14001090e  mov     [rsp+78h+var_10], eax
0x140010912  mov     rax, [rsp+78h+arg_28]
0x14001091a  movsd   xmm0, [rsp+78h+arg_50]
0x140010923  movsd   xmm1, [rsp+78h+arg_48]
0x14001092c  movsd   qword ptr [rsp+78h+var_20+8], xmm0
0x140010932  movsd   qword ptr [rsp+78h+var_20], xmm1
0x140010938  movsd   [rsp+78h+var_28], xmm2
0x14001093e  mov     [rsp+78h+var_30], ecx
0x140010942  mov     [rsp+78h+var_38], edx
0x140010946  mov     [rsp+78h+var_40], r8d
0x14001094b  mov     [rsp+78h+var_48], rax
0x140010950  mov     rax, [rsp+78h+arg_20]
0x140010958  mov     [rsp+78h+var_50], rax
0x14001095d  mov     [rsp+78h+var_58], ebx
0x140010961  call    McTemplateU0qztzztttgggd_EventWriteTransfer
0x140010966  mov     rbx, [rsp+78h+arg_0]
0x14001096e  add     rsp, 70h
0x140010972  pop     rdi
0x140010973  retn
```
