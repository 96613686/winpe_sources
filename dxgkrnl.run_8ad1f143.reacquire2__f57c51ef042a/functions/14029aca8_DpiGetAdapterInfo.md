# DpiGetAdapterInfo

- ea: `0x14029aca8`
- end: `0x14029c85b`
- name: `DpiGetAdapterInfo`
- size: `7091`
- prototype: `__int64 __fastcall(int, void *, void *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401c43e0`
- `0x1401e890c`

## callees

- `0x14004790c`
- `0x140070598`
- `0x14007f35c`
- `0x1400a0100`
- `0x1400a0240`
- `0x1400a0540`
- `0x140198e18`
- `0x14029ab0c`
- `0x14029aca8`
- `0x14029cab0`
- `0x14029d160`
- `0x1402b5e44`
- `0x1403c7e70`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14029c713`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14029c713`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14029c723`
- `ntoskrnl!ZwClose` at `0x14029c268`
- `ntoskrnl!ZwClose` at `0x14029c748`
- `ntoskrnl!ZwClose` at `0x14029c759`
- `ntoskrnl!ZwClose` at `0x14029c268`
- `ntoskrnl!ZwClose` at `0x14029c748`
- `ntoskrnl!ZwClose` at `0x14029c759`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029bf6a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029bfd9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c024`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c06f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c0bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c10a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c170`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c1d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c221`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c280`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c2ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c31c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c36a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c3b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c406`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c470`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c4c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c546`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c5ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c5fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029bf6a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029bfd9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c024`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c06f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c0bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c10a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c170`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c1d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c221`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c280`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c2ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c31c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c36a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c3b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c406`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c470`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c4c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c546`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c5ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x14029c5fa`
- `ntoskrnl!ZwOpenKey` at `0x14029c1b3`
- `ntoskrnl!ZwOpenKey` at `0x14029c58c`
- `ntoskrnl!ZwOpenKey` at `0x14029c1b3`
- `ntoskrnl!ZwOpenKey` at `0x14029c58c`
- `watchdog!WdLogSingleEntry3` at `0x14029be4c`
- `watchdog!WdLogSingleEntry3` at `0x14029be4c`
- `watchdog!WdLogSingleEntry1` at `0x14029bf12`
- `watchdog!WdLogSingleEntry1` at `0x14029bfa2`
- `watchdog!WdLogSingleEntry1` at `0x14029c002`
- `watchdog!WdLogSingleEntry1` at `0x14029c04d`
- `watchdog!WdLogSingleEntry1` at `0x14029c098`
- `watchdog!WdLogSingleEntry1` at `0x14029c0e8`
- `watchdog!WdLogSingleEntry1` at `0x14029c133`
- `watchdog!WdLogSingleEntry1` at `0x14029c1ff`
- `watchdog!WdLogSingleEntry1` at `0x14029c24d`
- `watchdog!WdLogSingleEntry1` at `0x14029c2ac`
- `watchdog!WdLogSingleEntry1` at `0x14029c2fa`
- `watchdog!WdLogSingleEntry1` at `0x14029c348`
- `watchdog!WdLogSingleEntry1` at `0x14029c396`
- `watchdog!WdLogSingleEntry1` at `0x14029c3e4`
- `watchdog!WdLogSingleEntry1` at `0x14029c432`
- `watchdog!WdLogSingleEntry1` at `0x14029c44e`
- `watchdog!WdLogSingleEntry1` at `0x14029c49f`
- `watchdog!WdLogSingleEntry1` at `0x14029c4f4`
- `watchdog!WdLogSingleEntry1` at `0x14029c5d8`
- `watchdog!WdLogSingleEntry1` at `0x14029c626`
- `watchdog!WdLogSingleEntry1` at `0x14029c72d`
- `watchdog!WdLogSingleEntry1` at `0x14029bf12`
- `watchdog!WdLogSingleEntry1` at `0x14029bfa2`
- `watchdog!WdLogSingleEntry1` at `0x14029c002`
- `watchdog!WdLogSingleEntry1` at `0x14029c04d`
- `watchdog!WdLogSingleEntry1` at `0x14029c098`
- `watchdog!WdLogSingleEntry1` at `0x14029c0e8`
- `watchdog!WdLogSingleEntry1` at `0x14029c133`
- `watchdog!WdLogSingleEntry1` at `0x14029c1ff`
- `watchdog!WdLogSingleEntry1` at `0x14029c24d`
- `watchdog!WdLogSingleEntry1` at `0x14029c2ac`
- `watchdog!WdLogSingleEntry1` at `0x14029c2fa`
- `watchdog!WdLogSingleEntry1` at `0x14029c348`
- `watchdog!WdLogSingleEntry1` at `0x14029c396`
- `watchdog!WdLogSingleEntry1` at `0x14029c3e4`
- `watchdog!WdLogSingleEntry1` at `0x14029c432`
- `watchdog!WdLogSingleEntry1` at `0x14029c44e`
- `watchdog!WdLogSingleEntry1` at `0x14029c49f`
- `watchdog!WdLogSingleEntry1` at `0x14029c4f4`
- `watchdog!WdLogSingleEntry1` at `0x14029c5d8`
- `watchdog!WdLogSingleEntry1` at `0x14029c626`
- `watchdog!WdLogSingleEntry1` at `0x14029c72d`

## string_xrefs

- `0x14029be78`: `d3d10warp.dll`
- `0x14029be8e`: `d3d10warp.dll`
- `0x14029c3fa`: `MiracastCompanionDriverName`
- `0x14029c4b5`: `OpenGLDriverNameWow`
- `0x14029c45a`: `OpenGLDriverName`
- `0x14029c664`: `OpenGLVersion`
- `0x14029c53a`: `OpenGL`
- `0x14029c6a1`: `OpenGLVersionWow`
- `0x14029c68b`: `OpenGLFlags`
- `0x14029c6b7`: `OpenGLFlagsWow`

## pseudocode

```c
__int64 __fastcall DpiGetAdapterInfo(__int64 a1, _BYTE *a2, char *a3, _OWORD *a4)
{
  int v7; // r12d
  __int64 v8; // r14
  char v9; // r15
  __int64 v10; // rbx
  size_t v11; // r8
  int v12; // ecx
  unsigned int v13; // edx
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned int v16; // r8d
  unsigned int v17; // ecx
  unsigned int v18; // edx
  unsigned int v19; // ecx
  unsigned int v20; // edx
  unsigned int v21; // ecx
  unsigned int v22; // edx
  unsigned int v23; // ecx
  unsigned int v24; // edx
  unsigned int v25; // ecx
  unsigned int v26; // edx
  unsigned int v27; // ecx
  unsigned int v28; // edx
  unsigned int v29; // ecx
  unsigned int v30; // r8d
  unsigned int v31; // edx
  char v32; // al
  unsigned __int16 v33; // bx
  int v34; // r8d
  __int128 v35; // xmm1
  PVOID SecurityDescriptor; // xmm0_8
  int v37; // eax
  HANDLE v38; // rdx
  __int64 v39; // rcx
  _OWORD *v40; // rax
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v43; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v46; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _OWORD *v48; // [rsp+98h] [rbp-68h]
  _QWORD v49[36]; // [rsp+A0h] [rbp-60h] BYREF

  v48 = a4;
  v7 = 0;
  v43 = 0;
  memset(v49, 0, 280);
  v8 = *(_QWORD *)(a1 + 64);
  v9 = 1;
  if ( a3 )
  {
    v10 = *(_QWORD *)(v8 + 40);
    memset(a3, 0, 0x620u);
    v11 = 78;
    *(_QWORD *)a3 = *(_QWORD *)(v8 + 48);
    v12 = 1;
    if ( *(_DWORD *)(v8 + 504) )
      v12 = *(_DWORD *)(v8 + 504);
    *((_DWORD *)a3 + 2) = v12;
    *(_OWORD *)(a3 + 12) = *(_OWORD *)(v8 + 2680);
    *(_OWORD *)(a3 + 28) = *(_OWORD *)(v8 + 4928);
    if ( *(_WORD *)(v8 + 4896) < 0x4Eu )
      v11 = *(unsigned __int16 *)(v8 + 4896);
    memmove(a3 + 44, *(const void **)(v8 + 4904), v11);
    *(_QWORD *)(a3 + 124) = *(_QWORD *)(v8 + 2696);
    *((_DWORD *)a3 + 33) = *(_DWORD *)(v8 + 1124);
    *((_DWORD *)a3 + 34) = *(_DWORD *)(v8 + 1128);
    *((_DWORD *)a3 + 35) = *(_DWORD *)(v8 + 1132);
    *((_DWORD *)a3 + 36) = *(_DWORD *)(v8 + 1136);
    *((_DWORD *)a3 + 37) = *(_DWORD *)(v8 + 1140);
    *((_DWORD *)a3 + 38) = *(_DWORD *)(v8 + 1120);
    v13 = *((_DWORD *)a3 + 39) & 0xFFFFFFFE | ((unsigned __int8)DpiFdoIsPostDevice(a1) != 0);
    *((_DWORD *)a3 + 39) = v13;
    v14 = v13 & 0xFFFFFFFD | (*(_BYTE *)(v8 + 1152) != 0 ? 2 : 0);
    *((_DWORD *)a3 + 39) = v14;
    v15 = v14 & 0xFFFFFFFB | (*(_BYTE *)(v8 + 480) != 0 ? 4 : 0);
    *((_DWORD *)a3 + 39) = v15;
    v16 = v15 & 0xFFFFFFF7 | (*(_BYTE *)(v8 + 2716) != 0 ? 8 : 0);
    *((_DWORD *)a3 + 39) = v16;
    v17 = v16 & 0xFFFFFFEF | (*(_BYTE *)(v8 + 2717) != 0 ? 0x10 : 0);
    *((_DWORD *)a3 + 39) = v17;
    v18 = v17 & 0xFFFFFFDF | (*(_BYTE *)(v8 + 1153) != 0 ? 0x20 : 0);
    *((_DWORD *)a3 + 39) = v18;
    v19 = v18 & 0xFFFFBFFF | (*(_BYTE *)(v8 + 481) != 0 ? 0x4000 : 0);
    *((_DWORD *)a3 + 39) = v19;
    v20 = v19 & 0xFFFFEFFF | (*(_DWORD *)(v8 + 3620) != -1 ? 0x1000 : 0);
    *((_DWORD *)a3 + 39) = v20;
    v21 = v20 & 0xFFFFFFBF | (*(_DWORD *)(v8 + 3360) != -1 ? 0x40 : 0);
    *((_DWORD *)a3 + 39) = v21;
    v22 = v21 & 0xFFFFFF7F | (*(_BYTE *)(v8 + 2844) != 0 ? 0x80 : 0);
    *((_DWORD *)a3 + 39) = v22;
    v23 = v22 & 0xFFFFFEFF | (*(_BYTE *)(v8 + 1158) != 0 ? 0x100 : 0);
    *((_DWORD *)a3 + 39) = v23;
    v24 = v23 & 0xFFFFFDFF | (*(_BYTE *)(v8 + 2719) != 0 ? 0x200 : 0);
    *((_DWORD *)a3 + 39) = v24;
    v25 = v24 & 0xFFFFDFFF | (*(_BYTE *)(v8 + 2718) != 0 ? 0x2000 : 0);
    *((_DWORD *)a3 + 39) = v25;
    v26 = v25 & 0xFFFFFBFF | (*(_BYTE *)(v8 + 2724) != 0 ? 0x400 : 0);
    *((_DWORD *)a3 + 39) = v26;
    v27 = v26 & 0xFFFFF7FF | (*(_BYTE *)(v8 + 2725) != 0 ? 0x800 : 0);
    *((_DWORD *)a3 + 39) = v27;
    v28 = v27 & 0xFFFF7FFF | (*(_BYTE *)(v8 + 2845) != 0 ? 0x8000 : 0);
    *((_DWORD *)a3 + 39) = v28;
    v29 = v28 & 0xFFFEFFFF | (*(_BYTE *)(v8 + 2846) != 0 ? 0x10000 : 0);
    *((_DWORD *)a3 + 39) = v29;
    v30 = v29 & 0xFFFDFFFF | ((*(_DWORD *)(v8 + 1324) & 0x10) << 13);
    *((_DWORD *)a3 + 39) = v30;
    v31 = v30 & 0xFFFBFFFF | (*(_BYTE *)(v8 + 1159) != 0 ? 0x40000 : 0);
    *((_DWORD *)a3 + 39) = v31;
    *((_DWORD *)a3 + 39) = v31 & 0xFFF7FFFF | (*(_BYTE *)(v8 + 2722) != 0 ? 0x80000 : 0);
    if ( !*(_QWORD *)(v10 + 184) || (v32 = 1, !*(_QWORD *)(v10 + 192)) )
      v32 = 0;
    a3[160] = v32;
    *((_QWORD *)a3 + 21) = *(_QWORD *)(v10 + 272);
    *((_QWORD *)a3 + 22) = *(_QWORD *)(v10 + 280);
    *((_QWORD *)a3 + 23) = *(_QWORD *)(v10 + 288);
    *((_QWORD *)a3 + 24) = *(_QWORD *)(v10 + 296);
    *((_QWORD *)a3 + 25) = *(_QWORD *)(v10 + 304);
    *((_QWORD *)a3 + 26) = *(_QWORD *)(v10 + 312);
    *((_QWORD *)a3 + 27) = *(_QWORD *)(v10 + 320);
    *((_QWORD *)a3 + 28) = *(_QWORD *)(v10 + 328);
    *((_QWORD *)a3 + 29) = *(_QWORD *)(v10 + 336);
    *((_QWORD *)a3 + 30) = *(_QWORD *)(v10 + 344);
    *((_QWORD *)a3 + 31) = *(_QWORD *)(v10 + 352);
    *((_QWORD *)a3 + 32) = *(_QWORD *)(v10 + 360);
    *((_QWORD *)a3 + 33) = *(_QWORD *)(v10 + 368);
    *((_QWORD *)a3 + 34) = *(_QWORD *)(v10 + 376);
    *((_QWORD *)a3 + 35) = *(_QWORD *)(v10 + 384);
    *((_QWORD *)a3 + 36) = *(_QWORD *)(v10 + 392);
    *((_QWORD *)a3 + 37) = *(_QWORD *)(v10 + 400);
    *((_QWORD *)a3 + 38) = *(_QWORD *)(v10 + 408);
    *((_QWORD *)a3 + 39) = *(_QWORD *)(v10 + 416);
    *((_QWORD *)a3 + 40) = *(_QWORD *)(v10 + 424);
    *((_QWORD *)a3 + 41) = *(_QWORD *)(v10 + 432);
    *((_QWORD *)a3 + 42) = *(_QWORD *)(v10 + 440);
    *((_QWORD *)a3 + 43) = *(_QWORD *)(v10 + 448);
    *((_QWORD *)a3 + 44) = *(_QWORD *)(v10 + 456);
    *((_QWORD *)a3 + 45) = *(_QWORD *)(v10 + 464);
    *((_QWORD *)a3 + 46) = *(_QWORD *)(v10 + 472);
    *((_QWORD *)a3 + 47) = *(_QWORD *)(v10 + 480);
    *((_QWORD *)a3 + 48) = *(_QWORD *)(v10 + 488);
    *((_QWORD *)a3 + 49) = *(_QWORD *)(v10 + 504);
    *((_QWORD *)a3 + 50) = *(_QWORD *)(v10 + 512);
    *((_QWORD *)a3 + 51) = *(_QWORD *)(v10 + 520);
    *((_QWORD *)a3 + 52) = *(_QWORD *)(v10 + 528);
    *((_QWORD *)a3 + 53) = *(_QWORD *)(v10 + 536);
    *((_QWORD *)a3 + 54) = *(_QWORD *)(v10 + 544);
    *((_QWORD *)a3 + 55) = *(_QWORD *)(v10 + 552);
    *((_QWORD *)a3 + 56) = *(_QWORD *)(v10 + 560);
    *((_QWORD *)a3 + 57) = *(_QWORD *)(v10 + 568);
    *((_QWORD *)a3 + 58) = *(_QWORD *)(v10 + 576);
    *((_QWORD *)a3 + 59) = *(_QWORD *)(v10 + 584);
    *((_QWORD *)a3 + 60) = *(_QWORD *)(v10 + 592);
    *((_QWORD *)a3 + 61) = *(_QWORD *)(v10 + 600);
    *((_QWORD *)a3 + 62) = *(_QWORD *)(v10 + 608);
    *((_QWORD *)a3 + 63) = *(_QWORD *)(v10 + 624);
    if ( *(_DWORD *)(v10 + 28) >= 0x2002u )
      *((_QWORD *)a3 + 64) = *(_QWORD *)(v10 + 680);
    if ( *(_DWORD *)(v10 + 28) >= 0x3001u )
    {
      *((_QWORD *)a3 + 65) = *(_QWORD *)(v10 + 712);
      *((_QWORD *)a3 + 66) = *(_QWORD *)(v10 + 720);
      *((_QWORD *)a3 + 67) = *(_QWORD *)(v10 + 728);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x3004u )
      *((_QWORD *)a3 + 72) = *(_QWORD *)(v10 + 760);
    if ( *(_DWORD *)(v10 + 28) >= 0x3005u )
    {
      *((_QWORD *)a3 + 69) = *(_QWORD *)(v10 + 704);
      *((_QWORD *)a3 + 70) = *(_QWORD *)(v10 + 776);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x3000u )
      *((_QWORD *)a3 + 68) = *(_QWORD *)(v10 + 1680);
    if ( *(_DWORD *)(v10 + 28) >= 0x4000u )
    {
      *((_QWORD *)a3 + 75) = *(_QWORD *)(v10 + 808);
      *((_QWORD *)a3 + 76) = *(_QWORD *)(v10 + 816);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x300Bu )
      *((_QWORD *)a3 + 73) = *(_QWORD *)(v10 + 784);
    if ( *(_DWORD *)(v10 + 28) >= 0x4001u )
      *((_QWORD *)a3 + 77) = *(_QWORD *)(v10 + 824);
    if ( *(_DWORD *)(v10 + 28) >= 0x4000u )
      *((_QWORD *)a3 + 74) = *(_QWORD *)(v10 + 800);
    if ( *(_DWORD *)(v10 + 28) >= 0x4002u )
    {
      *((_QWORD *)a3 + 78) = *(_QWORD *)(v10 + 832);
      *((_QWORD *)a3 + 79) = *(_QWORD *)(v10 + 840);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x5001u )
    {
      *((_QWORD *)a3 + 80) = *(_QWORD *)(v10 + 848);
      *((_QWORD *)a3 + 81) = *(_QWORD *)(v10 + 856);
      *((_QWORD *)a3 + 82) = *(_QWORD *)(v10 + 864);
      *((_QWORD *)a3 + 83) = *(_QWORD *)(v10 + 872);
      *((_QWORD *)a3 + 84) = *(_QWORD *)(v10 + 880);
      *((_QWORD *)a3 + 85) = *(_QWORD *)(v10 + 888);
      *((_QWORD *)a3 + 86) = *(_QWORD *)(v10 + 904);
      *((_QWORD *)a3 + 87) = *(_QWORD *)(v10 + 912);
      *((_QWORD *)a3 + 88) = *(_QWORD *)(v10 + 896);
      *((_QWORD *)a3 + 89) = *(_QWORD *)(v10 + 920);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x5006u )
      *((_QWORD *)a3 + 71) = *(_QWORD *)(v10 + 944);
    if ( *(_DWORD *)(v10 + 28) >= 0x5008u )
    {
      *((_QWORD *)a3 + 90) = *(_QWORD *)(v10 + 952);
      *((_QWORD *)a3 + 91) = *(_QWORD *)(v10 + 960);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x6000u )
    {
      *((_QWORD *)a3 + 92) = *(_QWORD *)(v10 + 968);
      *((_QWORD *)a3 + 93) = *(_QWORD *)(v10 + 976);
      *((_QWORD *)a3 + 94) = *(_QWORD *)(v10 + 984);
      *((_QWORD *)a3 + 95) = v8 + 5024;
      *((_QWORD *)a3 + 97) = v8 + 5152;
      *((_QWORD *)a3 + 96) = v8 + 5288;
      *((_QWORD *)a3 + 98) = v8 + 5344;
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x6002u )
    {
      *((_QWORD *)a3 + 99) = *(_QWORD *)(v10 + 1000);
      *((_QWORD *)a3 + 100) = *(_QWORD *)(v10 + 1008);
      *((_QWORD *)a3 + 101) = *(_QWORD *)(v10 + 992);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x7000u )
    {
      *((_QWORD *)a3 + 102) = *(_QWORD *)(v10 + 1032);
      *((_QWORD *)a3 + 103) = *(_QWORD *)(v10 + 1040);
      *((_QWORD *)a3 + 104) = *(_QWORD *)(v10 + 1048);
      *((_QWORD *)a3 + 105) = *(_QWORD *)(v10 + 1064);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x7002u )
    {
      *((_QWORD *)a3 + 107) = *(_QWORD *)(v10 + 1072);
      *((_QWORD *)a3 + 108) = *(_QWORD *)(v10 + 1080);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x7003u )
    {
      *((_QWORD *)a3 + 109) = *(_QWORD *)(v10 + 1088);
      *((_QWORD *)a3 + 110) = *(_QWORD *)(v10 + 1096);
      *((_QWORD *)a3 + 111) = *(_QWORD *)(v10 + 1104);
      *((_QWORD *)a3 + 112) = *(_QWORD *)(v10 + 1112);
      *((_QWORD *)a3 + 113) = *(_QWORD *)(v10 + 1120);
      *((_QWORD *)a3 + 114) = *(_QWORD *)(v10 + 1128);
      *((_QWORD *)a3 + 115) = *(_QWORD *)(v10 + 1136);
      *((_QWORD *)a3 + 116) = *(_QWORD *)(v10 + 1144);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x7004u )
    {
      *((_QWORD *)a3 + 117) = *(_QWORD *)(v10 + 1152);
      *((_QWORD *)a3 + 118) = *(_QWORD *)(v10 + 1160);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x8001u )
    {
      *((_QWORD *)a3 + 119) = *(_QWORD *)(v10 + 1176);
      *((_QWORD *)a3 + 120) = *(_QWORD *)(v10 + 1184);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x9000u )
    {
      *((_QWORD *)a3 + 121) = *(_QWORD *)(v10 + 1192);
      *((_QWORD *)a3 + 122) = *(_QWORD *)(v10 + 1200);
      *((_QWORD *)a3 + 123) = *(_QWORD *)(v10 + 1208);
      *((_QWORD *)a3 + 124) = *(_QWORD *)(v10 + 1216);
      *((_QWORD *)a3 + 125) = *(_QWORD *)(v10 + 1224);
      *((_QWORD *)a3 + 126) = *(_QWORD *)(v10 + 1232);
      *((_QWORD *)a3 + 127) = *(_QWORD *)(v10 + 1240);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x9003u )
    {
      *((_QWORD *)a3 + 128) = *(_QWORD *)(v10 + 1248);
      *((_QWORD *)a3 + 129) = *(_QWORD *)(v10 + 1256);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x9005u )
    {
      *((_QWORD *)a3 + 130) = *(_QWORD *)(v10 + 1264);
      *((_QWORD *)a3 + 131) = *(_QWORD *)(v10 + 1272);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x9006u )
      *((_QWORD *)a3 + 106) = *(_QWORD *)(v10 + 1280);
    if ( *(_DWORD *)(v10 + 28) >= 0xA001u )
      *((_QWORD *)a3 + 132) = *(_QWORD *)(v10 + 1288);
    if ( *(_DWORD *)(v10 + 28) >= 0xA002u )
      *((_QWORD *)a3 + 133) = *(_QWORD *)(v10 + 1296);
    if ( *(_DWORD *)(v10 + 28) >= 0xA005u )
      *((_QWORD *)a3 + 134) = *(_QWORD *)(v10 + 1304);
    if ( *(_DWORD *)(v10 + 28) >= 0xA009u )
      *((_QWORD *)a3 + 135) = *(_QWORD *)(v10 + 1320);
    if ( *(_DWORD *)(v10 + 28) >= 0xB002u )
    {
      *((_QWORD *)a3 + 136) = *(_QWORD *)(v10 + 1328);
      *((_QWORD *)a3 + 137) = *(_QWORD *)(v10 + 1336);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0xB003u )
      *((_QWORD *)a3 + 138) = *(_QWORD *)(v10 + 1344);
    if ( *(_DWORD *)(v10 + 28) >= 0xC001u )
      *((_QWORD *)a3 + 139) = *(_QWORD *)(v10 + 1360);
    if ( *(_DWORD *)(v10 + 28) >= 0xC002u )
      *((_QWORD *)a3 + 144) = v8 + 5600;
    if ( *(_DWORD *)(v10 + 28) >= 0xC004u )
    {
      *((_QWORD *)a3 + 146) = v8 + 5656;
      if ( *(_DWORD *)(v10 + 28) >= 0xC004u )
        *((_QWORD *)a3 + 145) = v8 + 5728;
    }
    if ( *(_DWORD *)(v10 + 28) >= 0xE003u )
    {
      *((_QWORD *)a3 + 140) = *(_QWORD *)(v10 + 1368);
      *((_QWORD *)a3 + 141) = *(_QWORD *)(v10 + 1376);
      *((_QWORD *)a3 + 142) = *(_QWORD *)(v10 + 1384);
      *((_QWORD *)a3 + 143) = *(_QWORD *)(v10 + 1392);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0xF001u )
    {
      *((_QWORD *)a3 + 147) = *(_QWORD *)(v10 + 1400);
      *((_QWORD *)a3 + 148) = *(_QWORD *)(v10 + 1408);
      *((_QWORD *)a3 + 149) = *(_QWORD *)(v10 + 1416);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0xF003u )
      *((_QWORD *)a3 + 150) = *(_QWORD *)(v10 + 1424);
    if ( *(_DWORD *)(v10 + 28) >= 0x10003u )
    {
      *((_QWORD *)a3 + 155) = *(_QWORD *)(v10 + 1464);
      *((_QWORD *)a3 + 156) = *(_QWORD *)(v10 + 1472);
      *((_QWORD *)a3 + 157) = *(_QWORD *)(v10 + 1480);
      *((_QWORD *)a3 + 158) = *(_QWORD *)(v10 + 1488);
      *((_QWORD *)a3 + 159) = *(_QWORD *)(v10 + 1496);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x11001u )
    {
      *((_QWORD *)a3 + 160) = *(_QWORD *)(v10 + 1512);
      *((_QWORD *)a3 + 161) = *(_QWORD *)(v10 + 1520);
      *((_QWORD *)a3 + 162) = *(_QWORD *)(v10 + 1528);
      *((_QWORD *)a3 + 163) = *(_QWORD *)(v10 + 1536);
      *((_QWORD *)a3 + 164) = *(_QWORD *)(v10 + 1544);
      *((_QWORD *)a3 + 165) = *(_QWORD *)(v10 + 1552);
      *((_QWORD *)a3 + 166) = *(_QWORD *)(v10 + 1560);
      *((_QWORD *)a3 + 167) = *(_QWORD *)(v10 + 1568);
      *((_QWORD *)a3 + 168) = *(_QWORD *)(v10 + 1576);
      *((_QWORD *)a3 + 169) = *(_QWORD *)(v10 + 1584);
      *((_QWORD *)a3 + 170) = *(_QWORD *)(v10 + 1592);
      *((_QWORD *)a3 + 171) = *(_QWORD *)(v10 + 1600);
      *((_QWORD *)a3 + 172) = *(_QWORD *)(v10 + 1608);
      *((_QWORD *)a3 + 173) = *(_QWORD *)(v10 + 1616);
      *((_QWORD *)a3 + 151) = *(_QWORD *)(v10 + 1432);
      *((_QWORD *)a3 + 174) = *(_QWORD *)(v10 + 1624);
      *((_QWORD *)a3 + 175) = *(_QWORD *)(v10 + 1632);
      *((_QWORD *)a3 + 152) = *(_QWORD *)(v10 + 1440);
      *((_QWORD *)a3 + 153) = *(_QWORD *)(v10 + 1448);
      *((_QWORD *)a3 + 154) = *(_QWORD *)(v10 + 1456);
      *((_QWORD *)a3 + 176) = *(_QWORD *)(v10 + 1640);
      *((_QWORD *)a3 + 177) = *(_QWORD *)(v10 + 1648);
    }
    if ( *(_DWORD *)(v10 + 28) >= 0x11003u )
      *((_QWORD *)a3 + 178) = *(_QWORD *)(v10 + 1656);
    if ( *(_DWORD *)(v10 + 28) >= 0x11006u )
      *((_QWORD *)a3 + 180) = *(_QWORD *)(v10 + 1664);
    if ( *(_DWORD *)(v10 + 28) >= 0x11007u )
      *((_QWORD *)a3 + 181) = *(_QWORD *)(v10 + 1672);
    LODWORD(Handle) = 0;
    DpiIsFeatureEnabled(a1, 4, 0, &Handle);
    if ( (BYTE2(Handle) & 4) != 0 )
    {
      v33 = (unsigned __int16)Handle;
      if ( (_WORD)Handle == 1 )
      {
        *((_QWORD *)a3 + 182) = 0;
        *((_QWORD *)a3 + 183) = 0;
      }
      else if ( (unsigned __int16)Handle >= 2u )
      {
        v46 = 0;
        v37 = DpiQueryFeatureDriverInterface(a1, 4, (unsigned __int16)Handle, 16, &v46);
        v7 = v37;
        if ( v37 < 0 )
        {
          WdLogSingleEntry3(2, 4, v33, v37);
          WdLogGlobalForLineNumber = 858;
          goto LABEL_142;
        }
        v7 = 0;
        *((struct _UNICODE_STRING *)a3 + 91) = v46;
      }
    }
    if ( !a2[41] )
    {
      LODWORD(Handle) = 0;
      DpiIsFeatureEnabled(a1, 33, 0, &Handle);
      if ( (BYTE2(Handle) & 4) != 0 )
      {
        v34 = (int)Handle;
        if ( (_WORD)Handle )
        {
          Handle = 0;
          if ( (int)DpiQueryFeatureDriverInterface(a1, 33, v34, 8, &Handle) >= 0 )
          {
            KeyHandle = 0;
            if ( (int)DpiQueryFeatureDriverInterface(a1, 33, 1, 8, &KeyHandle) >= 0 )
              *((_QWORD *)a3 + 179) = KeyHandle;
          }
        }
      }
      LODWORD(Handle) = 0;
      if ( (int)DpiIsFeatureEnabled(a1, 39, 0, &Handle) >= 0 && (BYTE2(Handle) & 1) != 0 )
      {
        if ( (_WORD)Handle )
        {
          v46 = 0;
          if ( (int)DpiQueryFeatureDriverInterface(a1, 39, 1, 16, &v46) >= 0 )
            *((struct _UNICODE_STRING *)a3 + 92) = v46;
        }
      }
      Feature_NotifyResidency2__private_IsEnabledPreCheck();
      LODWORD(Handle) = 0;
      if ( (int)DpiIsFeatureEnabled(a1, 43, 0, &Handle) >= 0 && (BYTE2(Handle) & 1) != 0 )
      {
        if ( (_WORD)Handle )
        {
          KeyHandle = 0;
          if ( (int)DpiQueryFeatureDriverInterface(a1, 43, 1, 8, &KeyHandle) >= 0 )
            *((_QWORD *)a3 + 186) = KeyHandle;
        }
      }
      LODWORD(Handle) = 0;
      if ( (int)DpiIsFeatureEnabled(a1, 45, 0, &Handle) >= 0 && (BYTE2(Handle) & 1) != 0 )
      {
        if ( (_WORD)Handle )
        {
          v46 = 0;
          if ( (int)DpiQueryFeatureDriverInterface(a1, 45, 1, 16, &v46) >= 0 )
            *(struct _UNICODE_STRING *)(a3 + 1496) = v46;
        }
      }
      LODWORD(Handle) = 0;
      if ( (int)DpiIsFeatureEnabled(a1, 47, 0, &Handle) >= 0 && (BYTE2(Handle) & 1) != 0 )
      {
        if ( (_WORD)Handle )
        {
          memset(&ObjectAttributes, 0, 40);
          if ( (int)DpiQueryFeatureDriverInterface(a1, 47, 1, 40, &ObjectAttributes) >= 0 )
          {
            v35 = *(_OWORD *)&ObjectAttributes.ObjectName;
            *(_OWORD *)(a3 + 1512) = *(_OWORD *)&ObjectAttributes.Length;
            SecurityDescriptor = ObjectAttributes.SecurityDescriptor;
            *(_OWORD *)(a3 + 1528) = v35;
            *((_QWORD *)a3 + 193) = SecurityDescriptor;
          }
        }
      }
      LODWORD(Handle) = 0;
      if ( (int)DpiIsFeatureEnabled(a1, 48, 0, &Handle) >= 0 && (BYTE2(Handle) & 1) != 0 )
      {
        if ( (_WORD)Handle )
        {
          KeyHandle = 0;
          if ( (int)DpiQueryFeatureDriverInterface(a1, 48, 1, 8, &KeyHandle) >= 0 )
            *((_QWORD *)a3 + 194) = KeyHandle;
        }
      }
      if ( (unsigned int)Feature_TargetProperties__private_IsEnabledDeviceUsageNoInline() )
      {
        LODWORD(Handle) = 0;
        if ( (int)DpiIsFeatureEnabled(a1, 49, 0, &Handle) >= 0 && (BYTE2(Handle) & 1) != 0 )
        {
          if ( (_WORD)Handle )
          {
            KeyHandle = 0;
            if ( (int)DpiQueryFeatureDriverInterface(a1, 49, 1, 8, &KeyHandle) >= 0 )
              *((_QWORD *)a3 + 195) = KeyHandle;
          }
        }
      }
    }
  }
  *a2 = 0;
  if ( *(_BYTE *)(v8 + 2717) )
  {
    *((_DWORD *)a2 + 2) = 7471218;
    *((_QWORD *)a2 + 2) = L"d3d10warp.dll";
    *((_QWORD *)a2 + 4) = L"d3d10warp.dll";
    *((_QWORD *)a2 + 25) = L"d3d10warp.dll";
    *((_QWORD *)a2 + 27) = L"d3d10warp.dll";
    *((_DWORD *)a2 + 6) = 7471218;
    *((_DWORD *)a2 + 48) = 1966110;
    *((_DWORD *)a2 + 52) = 1966110;
LABEL_194:
    *((_QWORD *)a2 + 22) = *(_QWORD *)(v8 + 4960);
    *((_QWORD *)a2 + 23) = v8 + 2848;
    *((_DWORD *)a2 + 28) = *(_DWORD *)(v8 + 2708);
    *((_DWORD *)a2 + 29) = *(_DWORD *)(v8 + 3616);
    *((_DWORD *)a2 + 30) = *(_DWORD *)(v8 + 2704) - *(_DWORD *)(v8 + 3616);
    *((_QWORD *)a2 + 32) = *(_QWORD *)(v8 + 4968);
    *((_QWORD *)a2 + 33) = *(_QWORD *)(v8 + 4976);
    *((_DWORD *)a2 + 68) = *(_DWORD *)(v8 + 4984);
    *((_DWORD *)a2 + 78) = *(unsigned __int16 *)(v8 + 4810);
    v40 = v48;
    *v48 = *(_OWORD *)(v8 + 1000);
    v40[1] = *(_OWORD *)(v8 + 1016);
    v40[2] = *(_OWORD *)(v8 + 1032);
    v40[3] = *(_OWORD *)(v8 + 1048);
    v40[4] = *(_OWORD *)(v8 + 1064);
    v40[5] = *(_OWORD *)(v8 + 1080);
    v40[6] = *(_OWORD *)(v8 + 1096);
    return (unsigned int)v7;
  }
  if ( *(_BYTE *)(*(_QWORD *)(v8 + 40) + 133LL) || *(_BYTE *)(v8 + 481) )
    goto LABEL_194;
  *a2 = 1;
  DestinationString = 0;
  v7 = DpiOpenPnpRegistryKey(a1, 2, 131097, &v43);
  if ( v7 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"UserModeDriverName");
    v7 = 0;
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1132;
      if ( !*(_BYTE *)(v8 + 2722) )
        a2[40] = 1;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1158;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWSL");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1212;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDriverWsaImage");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWsa64");
      if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1249;
      }
      RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWsa32");
      if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1267;
      }
    }
    else
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1230;
    }
    KeyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v46 = 0;
    RtlInitUnicodeString(&v46, L"DX9");
    ObjectAttributes.RootDirectory = v43;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v46;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"DriverName");
      if ( (int)DxgkRetrieveStringFromRegistry(KeyHandle, &DestinationString) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1299;
      }
      RtlInitUnicodeString(&DestinationString, L"DriverNameWow");
      if ( (int)DxgkRetrieveStringFromRegistry(KeyHandle, &DestinationString) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1312;
      }
      ZwClose(KeyHandle);
    }
    RtlInitUnicodeString(&DestinationString, L"DisplayUserModeDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1366;
    }
    RtlInitUnicodeString(&DestinationString, L"DisplayUserModeDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1384;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDListDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1438;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDListDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1456;
    }
    RtlInitUnicodeString(&DestinationString, L"ContentProtectionDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1473;
    }
    RtlInitUnicodeString(&DestinationString, L"MiracastCompanionDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1490;
    }
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 1500;
    RtlInitUnicodeString(&DestinationString, L"OpenGLDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1512;
    }
    RtlInitUnicodeString(&DestinationString, L"OpenGLDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1525;
    }
    if ( *((_WORD *)a2 + 64) && **((_WORD **)a2 + 17) == 35 )
    {
      Handle = 0;
      DxgkFreeUnicodeString(a2 + 128);
      DxgkFreeUnicodeString(a2 + 152);
      RtlInitUnicodeString(&v46, L"OpenGL");
      ObjectAttributes.RootDirectory = v43;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &v46;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"DriverName");
        if ( (int)DxgkRetrieveStringFromRegistry(Handle, &DestinationString) < 0 )
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1566;
        }
        RtlInitUnicodeString(&DestinationString, L"DriverNameWow");
        if ( (int)DxgkRetrieveStringFromRegistry(Handle, &DestinationString) < 0 )
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1579;
        }
      }
    }
    else
    {
      v9 = 0;
      Handle = 0;
    }
    if ( *((_QWORD *)a2 + 17) )
    {
      v49[5] = 0;
      LODWORD(v49[1]) = 288;
      LODWORD(v49[4]) = 0x4000000;
      v49[2] = L"OpenGLVersion";
      LODWORD(v49[6]) = 0;
      v49[3] = a2 + 144;
      LODWORD(v49[8]) = 288;
      v49[9] = L"OpenGLFlags";
      v49[10] = a2 + 148;
      v49[16] = L"OpenGLVersionWow";
      v49[17] = a2 + 168;
      v49[23] = L"OpenGLFlagsWow";
      v49[24] = a2 + 172;
      LODWORD(v49[11]) = 0x4000000;
      v49[12] = 0;
      LODWORD(v49[13]) = 0;
      LODWORD(v49[15]) = 288;
      LODWORD(v49[18]) = 0x4000000;
      v49[19] = 0;
      LODWORD(v49[20]) = 0;
      LODWORD(v49[22]) = 288;
      LODWORD(v49[25]) = 0x4000000;
      v49[26] = 0;
      LODWORD(v49[27]) = 0;
      if ( v9 )
      {
        v38 = Handle;
        v39 = 0x40000000;
      }
      else
      {
        v38 = *(HANDLE *)(v8 + 536);
        v39 = 0;
      }
      if ( (int)RtlQueryRegistryValuesEx(v39, v38, v49, 0, 0) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1634;
      }
    }
    ZwClose(Handle);
    ZwClose(v43);
    goto LABEL_194;
  }
  WdLogSingleEntry1(2);
  WdLogGlobalForLineNumber = 1107;
LABEL_142:
  DpiFreeAdapterInfo(a2);
  memset(a2, 0, 0x160u);
  if ( a3 )
    memset(a3, 0, 0x620u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14029aca8  push    rbp
0x14029acaa  push    rbx
0x14029acab  push    rsi
0x14029acac  push    rdi
0x14029acad  push    r12
0x14029acaf  push    r13
0x14029acb1  push    r14
0x14029acb3  push    r15
0x14029acb5  lea     rbp, [rsp-0D8h]
0x14029acbd  sub     rsp, 1D8h
0x14029acc4  mov     rax, cs:__security_cookie
0x14029accb  xor     rax, rsp
0x14029acce  mov     [rbp+110h+var_50], rax
0x14029acd5  mov     rdi, r8
0x14029acd8  mov     [rbp+110h+var_178], r9
0x14029acdc  mov     rsi, rdx
0x14029acdf  mov     r13, rcx
0x14029ace2  xor     r12d, r12d
0x14029ace5  lea     rcx, [rbp+110h+var_168]; void *
0x14029ace9  xor     edx, edx; Val
0x14029aceb  mov     [rsp+210h+var_1D8], r12
0x14029acf0  mov     r8d, 110h; Size
0x14029acf6  mov     [rbp+110h+var_170], r12
0x14029acfa  call    memset
0x14029acff  mov     r14, [r13+40h]
0x14029ad03  lea     ecx, [r12+2]
0x14029ad08  lea     r15d, [r12+1]
0x14029ad0d  test    rdi, rdi
0x14029ad10  jz      loc_14029BE6C
0x14029ad16  mov     rbx, [r14+28h]
0x14029ad1a  xor     edx, edx; Val
0x14029ad1c  mov     r8d, 620h; Size
0x14029ad22  mov     rcx, rdi; void *
0x14029ad25  call    memset
0x14029ad2a  mov     rax, [r14+30h]
0x14029ad2e  lea     r8d, [r12+4Eh]
0x14029ad33  mov     [rdi], rax
0x14029ad36  mov     ecx, r15d
0x14029ad39  mov     eax, [r14+1F8h]
0x14029ad40  test    eax, eax
0x14029ad42  cmovnz  ecx, eax
0x14029ad45  mov     [rdi+8], ecx
0x14029ad48  movups  xmm0, xmmword ptr [r14+0A78h]
0x14029ad50  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x14029ad55  movups  xmm1, xmmword ptr [r14+1340h]
0x14029ad5d  movdqu  xmmword ptr [rdi+1Ch], xmm1
0x14029ad62  movzx   eax, word ptr [r14+1320h]
0x14029ad6a  cmp     ax, r8w
0x14029ad6e  jnb     short loc_14029AD73
0x14029ad70  mov     r8d, eax; Size
0x14029ad73  mov     rdx, [r14+1328h]; Src
0x14029ad7a  lea     rcx, [rdi+2Ch]; void *
0x14029ad7e  call    memmove
0x14029ad83  mov     rax, [r14+0A88h]
0x14029ad8a  mov     rcx, r13
0x14029ad8d  mov     [rdi+7Ch], rax
0x14029ad91  mov     eax, [r14+464h]
0x14029ad98  mov     [rdi+84h], eax
0x14029ad9e  mov     eax, [r14+468h]
0x14029ada5  mov     [rdi+88h], eax
0x14029adab  mov     eax, [r14+46Ch]
0x14029adb2  mov     [rdi+8Ch], eax
0x14029adb8  mov     eax, [r14+470h]
0x14029adbf  mov     [rdi+90h], eax
0x14029adc5  mov     eax, [r14+474h]
0x14029adcc  mov     [rdi+94h], eax
0x14029add2  mov     eax, [r14+460h]
0x14029add9  mov     [rdi+98h], eax
0x14029addf  call    DpiFdoIsPostDevice
0x14029ade4  test    al, al
0x14029ade6  mov     edx, r12d
0x14029ade9  mov     eax, [rdi+9Ch]
0x14029adef  mov     r9d, 4000h
0x14029adf5  setnz   dl
0x14029adf8  and     eax, 0FFFFFFFEh
0x14029adfb  or      edx, eax
0x14029adfd  mov     [rdi+9Ch], edx
0x14029ae03  mov     al, [r14+480h]
0x14029ae0a  neg     al
0x14029ae0c  sbb     ecx, ecx
0x14029ae0e  and     edx, 0FFFFFFFDh
0x14029ae11  and     ecx, 2
0x14029ae14  or      ecx, edx
0x14029ae16  mov     [rdi+9Ch], ecx
0x14029ae1c  mov     al, [r14+1E0h]
0x14029ae23  neg     al
0x14029ae25  sbb     edx, edx
0x14029ae27  and     ecx, 0FFFFFFFBh
0x14029ae2a  and     edx, 4
0x14029ae2d  or      edx, ecx
0x14029ae2f  mov     [rdi+9Ch], edx
0x14029ae35  mov     al, [r14+0A9Ch]
0x14029ae3c  neg     al
0x14029ae3e  sbb     r8d, r8d
0x14029ae41  and     edx, 0FFFFFFF7h
0x14029ae44  and     r8d, 8
0x14029ae48  or      r8d, edx
0x14029ae4b  mov     [rdi+9Ch], r8d
0x14029ae52  mov     al, [r14+0A9Dh]
0x14029ae59  neg     al
0x14029ae5b  sbb     ecx, ecx
0x14029ae5d  and     r8d, 0FFFFFFEFh
0x14029ae61  and     ecx, 10h
0x14029ae64  or      ecx, r8d
0x14029ae67  mov     [rdi+9Ch], ecx
0x14029ae6d  mov     al, [r14+481h]
0x14029ae74  neg     al
0x14029ae76  sbb     edx, edx
0x14029ae78  and     ecx, 0FFFFFFDFh
0x14029ae7b  and     edx, 20h
0x14029ae7e  or      edx, ecx
0x14029ae80  mov     [rdi+9Ch], edx
0x14029ae86  mov     al, [r14+1E1h]
0x14029ae8d  neg     al
0x14029ae8f  sbb     ecx, ecx
0x14029ae91  btr     edx, 0Eh
0x14029ae95  and     ecx, r9d
0x14029ae98  or      r8d, 0FFFFFFFFh
0x14029ae9c  or      ecx, edx
0x14029ae9e  mov     [rdi+9Ch], ecx
0x14029aea4  mov     eax, [r14+0E24h]
0x14029aeab  sub     eax, r8d
0x14029aeae  neg     eax
0x14029aeb0  sbb     edx, edx
0x14029aeb2  btr     ecx, 0Ch
0x14029aeb6  and     edx, 1000h
0x14029aebc  or      edx, ecx
0x14029aebe  mov     [rdi+9Ch], edx
0x14029aec4  mov     eax, [r14+0D20h]
0x14029aecb  sub     eax, r8d
0x14029aece  neg     eax
0x14029aed0  sbb     ecx, ecx
0x14029aed2  and     edx, 0FFFFFFBFh
0x14029aed5  and     ecx, 40h
0x14029aed8  or      ecx, edx
0x14029aeda  mov     [rdi+9Ch], ecx
0x14029aee0  mov     al, [r14+0B1Ch]
0x14029aee7  neg     al
0x14029aee9  sbb     edx, edx
0x14029aeeb  btr     ecx, 7
0x14029aeef  and     edx, 80h
0x14029aef5  or      edx, ecx
0x14029aef7  mov     [rdi+9Ch], edx
0x14029aefd  mov     al, [r14+486h]
0x14029af04  neg     al
0x14029af06  sbb     ecx, ecx
0x14029af08  btr     edx, 8
0x14029af0c  and     ecx, 100h
0x14029af12  or      ecx, edx
0x14029af14  mov     [rdi+9Ch], ecx
0x14029af1a  mov     al, [r14+0A9Fh]
0x14029af21  neg     al
0x14029af23  sbb     edx, edx
0x14029af25  btr     ecx, 9
0x14029af29  and     edx, 200h
0x14029af2f  or      edx, ecx
0x14029af31  mov     [rdi+9Ch], edx
0x14029af37  mov     al, [r14+0A9Eh]
0x14029af3e  neg     al
0x14029af40  sbb     ecx, ecx
0x14029af42  btr     edx, 0Dh
0x14029af46  and     ecx, 2000h
0x14029af4c  or      ecx, edx
0x14029af4e  mov     [rdi+9Ch], ecx
0x14029af54  mov     al, [r14+0AA4h]
0x14029af5b  neg     al
0x14029af5d  sbb     edx, edx
0x14029af5f  btr     ecx, 0Ah
0x14029af63  and     edx, 400h
0x14029af69  or      edx, ecx
0x14029af6b  mov     [rdi+9Ch], edx
0x14029af71  mov     al, [r14+0AA5h]
0x14029af78  neg     al
0x14029af7a  sbb     ecx, ecx
0x14029af7c  btr     edx, 0Bh
0x14029af80  and     ecx, 800h
0x14029af86  or      ecx, edx
0x14029af88  mov     [rdi+9Ch], ecx
0x14029af8e  mov     al, [r14+0B1Dh]
0x14029af95  neg     al
0x14029af97  sbb     edx, edx
0x14029af99  btr     ecx, 0Fh
0x14029af9d  and     edx, 8000h
0x14029afa3  or      edx, ecx
0x14029afa5  mov     [rdi+9Ch], edx
0x14029afab  mov     al, [r14+0B1Eh]
0x14029afb2  neg     al
0x14029afb4  sbb     ecx, ecx
0x14029afb6  btr     edx, 10h
0x14029afba  and     ecx, 10000h
0x14029afc0  or      ecx, edx
0x14029afc2  mov     [rdi+9Ch], ecx
0x14029afc8  btr     ecx, 11h
0x14029afcc  mov     r8d, [r14+52Ch]
0x14029afd3  and     r8d, 10h
0x14029afd7  shl     r8d, 0Dh
0x14029afdb  or      r8d, ecx
0x14029afde  mov     [rdi+9Ch], r8d
0x14029afe5  mov     al, [r14+487h]
0x14029afec  neg     al
0x14029afee  sbb     edx, edx
0x14029aff0  btr     r8d, 12h
0x14029aff5  and     edx, 40000h
0x14029affb  or      edx, r8d
0x14029affe  mov     [rdi+9Ch], edx
0x14029b004  mov     al, [r14+0AA2h]
0x14029b00b  neg     al
0x14029b00d  sbb     ecx, ecx
0x14029b00f  btr     edx, 13h
0x14029b013  and     ecx, 80000h
0x14029b019  or      ecx, edx
0x14029b01b  mov     [rdi+9Ch], ecx
0x14029b021  cmp     [rbx+0B8h], r12
0x14029b028  jz      short loc_14029B036
0x14029b02a  mov     al, r15b
0x14029b02d  cmp     [rbx+0C0h], r12
0x14029b034  jnz     short loc_14029B039
0x14029b036  mov     al, r12b
0x14029b039  mov     [rdi+0A0h], al
0x14029b03f  mov     rax, [rbx+110h]
0x14029b046  mov     [rdi+0A8h], rax
0x14029b04d  mov     rax, [rbx+118h]
0x14029b054  mov     [rdi+0B0h], rax
0x14029b05b  mov     rax, [rbx+120h]
0x14029b062  mov     [rdi+0B8h], rax
0x14029b069  mov     rax, [rbx+128h]
0x14029b070  mov     [rdi+0C0h], rax
0x14029b077  mov     rax, [rbx+130h]
0x14029b07e  mov     [rdi+0C8h], rax
0x14029b085  mov     rax, [rbx+138h]
0x14029b08c  mov     [rdi+0D0h], rax
0x14029b093  mov     rax, [rbx+140h]
0x14029b09a  mov     [rdi+0D8h], rax
0x14029b0a1  mov     rax, [rbx+148h]
0x14029b0a8  mov     [rdi+0E0h], rax
0x14029b0af  mov     rax, [rbx+150h]
0x14029b0b6  mov     [rdi+0E8h], rax
0x14029b0bd  mov     rax, [rbx+158h]
0x14029b0c4  mov     [rdi+0F0h], rax
0x14029b0cb  mov     rax, [rbx+160h]
0x14029b0d2  mov     [rdi+0F8h], rax
0x14029b0d9  mov     rax, [rbx+168h]
0x14029b0e0  mov     [rdi+100h], rax
0x14029b0e7  mov     rax, [rbx+170h]
0x14029b0ee  mov     [rdi+108h], rax
0x14029b0f5  mov     rax, [rbx+178h]
0x14029b0fc  mov     [rdi+110h], rax
0x14029b103  mov     rax, [rbx+180h]
0x14029b10a  mov     [rdi+118h], rax
0x14029b111  mov     rax, [rbx+188h]
0x14029b118  mov     [rdi+120h], rax
0x14029b11f  mov     rax, [rbx+190h]
0x14029b126  mov     [rdi+128h], rax
0x14029b12d  mov     rax, [rbx+198h]
0x14029b134  mov     [rdi+130h], rax
0x14029b13b  mov     rax, [rbx+1A0h]
0x14029b142  mov     [rdi+138h], rax
0x14029b149  mov     rax, [rbx+1A8h]
0x14029b150  mov     [rdi+140h], rax
0x14029b157  mov     rax, [rbx+1B0h]
0x14029b15e  mov     [rdi+148h], rax
0x14029b165  mov     rax, [rbx+1B8h]
0x14029b16c  mov     [rdi+150h], rax
0x14029b173  mov     rax, [rbx+1C0h]
0x14029b17a  mov     [rdi+158h], rax
0x14029b181  mov     rax, [rbx+1C8h]
0x14029b188  mov     [rdi+160h], rax
0x14029b18f  mov     rax, [rbx+1D0h]
0x14029b196  mov     [rdi+168h], rax
0x14029b19d  mov     rax, [rbx+1D8h]
0x14029b1a4  mov     [rdi+170h], rax
0x14029b1ab  mov     rax, [rbx+1E0h]
0x14029b1b2  mov     [rdi+178h], rax
0x14029b1b9  mov     rax, [rbx+1E8h]
0x14029b1c0  mov     [rdi+180h], rax
0x14029b1c7  mov     rax, [rbx+1F8h]
0x14029b1ce  mov     [rdi+188h], rax
0x14029b1d5  mov     rax, [rbx+200h]
0x14029b1dc  mov     [rdi+190h], rax
0x14029b1e3  mov     rax, [rbx+208h]
0x14029b1ea  mov     [rdi+198h], rax
0x14029b1f1  mov     rax, [rbx+210h]
0x14029b1f8  mov     [rdi+1A0h], rax
0x14029b1ff  mov     rax, [rbx+218h]
0x14029b206  mov     [rdi+1A8h], rax
0x14029b20d  mov     rax, [rbx+220h]
0x14029b214  mov     [rdi+1B0h], rax
0x14029b21b  mov     rax, [rbx+228h]
0x14029b222  mov     [rdi+1B8h], rax
0x14029b229  mov     rax, [rbx+230h]
0x14029b230  mov     [rdi+1C0h], rax
0x14029b237  mov     rax, [rbx+238h]
0x14029b23e  mov     [rdi+1C8h], rax
0x14029b245  mov     rax, [rbx+240h]
0x14029b24c  mov     [rdi+1D0h], rax
0x14029b253  mov     rax, [rbx+248h]
0x14029b25a  mov     [rdi+1D8h], rax
0x14029b261  mov     rax, [rbx+250h]
0x14029b268  mov     [rdi+1E0h], rax
0x14029b26f  mov     rax, [rbx+258h]
  ... truncated ...
```
