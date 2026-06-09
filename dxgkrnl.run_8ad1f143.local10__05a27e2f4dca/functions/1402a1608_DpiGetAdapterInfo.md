# DpiGetAdapterInfo

- ea: `0x1402a1608`
- end: `0x1402a3214`
- name: `DpiGetAdapterInfo`
- size: `7180`
- prototype: `__int64 __fastcall(int, void *, void *)`
- caller_count: `2`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1401c6fe0`
- `0x1401eacdc`

## callees

- `0x140047b0c`
- `0x140070b48`
- `0x14007fc5c`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x14019ce18`
- `0x1402a146c`
- `0x1402a1608`
- `0x1402a3460`
- `0x1402a3b10`
- `0x1402bc7f4`
- `0x1403c7220`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402a30cc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402a30cc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1402a30dc`
- `ntoskrnl!ZwClose` at `0x1402a2c21`
- `ntoskrnl!ZwClose` at `0x1402a3101`
- `ntoskrnl!ZwClose` at `0x1402a3112`
- `ntoskrnl!ZwClose` at `0x1402a2c21`
- `ntoskrnl!ZwClose` at `0x1402a3101`
- `ntoskrnl!ZwClose` at `0x1402a3112`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2920`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a298f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a29da`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2a25`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2a75`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2ac0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2b26`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2b8c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2bda`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2c39`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2c87`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2cd5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2d23`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2d71`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2dbf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2e29`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2e7a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2eff`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2f65`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2fb3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2920`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a298f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a29da`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2a25`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2a75`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2ac0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2b26`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2b8c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2bda`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2c39`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2c87`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2cd5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2d23`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2d71`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2dbf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2e29`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2e7a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2eff`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2f65`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402a2fb3`
- `ntoskrnl!ZwOpenKey` at `0x1402a2b6c`
- `ntoskrnl!ZwOpenKey` at `0x1402a2f45`
- `ntoskrnl!ZwOpenKey` at `0x1402a2b6c`
- `ntoskrnl!ZwOpenKey` at `0x1402a2f45`
- `watchdog!WdLogSingleEntry3` at `0x1402a2807`
- `watchdog!WdLogSingleEntry3` at `0x1402a2807`
- `watchdog!WdLogSingleEntry1` at `0x1402a28c8`
- `watchdog!WdLogSingleEntry1` at `0x1402a2958`
- `watchdog!WdLogSingleEntry1` at `0x1402a29b8`
- `watchdog!WdLogSingleEntry1` at `0x1402a2a03`
- `watchdog!WdLogSingleEntry1` at `0x1402a2a4e`
- `watchdog!WdLogSingleEntry1` at `0x1402a2a9e`
- `watchdog!WdLogSingleEntry1` at `0x1402a2ae9`
- `watchdog!WdLogSingleEntry1` at `0x1402a2bb8`
- `watchdog!WdLogSingleEntry1` at `0x1402a2c06`
- `watchdog!WdLogSingleEntry1` at `0x1402a2c65`
- `watchdog!WdLogSingleEntry1` at `0x1402a2cb3`
- `watchdog!WdLogSingleEntry1` at `0x1402a2d01`
- `watchdog!WdLogSingleEntry1` at `0x1402a2d4f`
- `watchdog!WdLogSingleEntry1` at `0x1402a2d9d`
- `watchdog!WdLogSingleEntry1` at `0x1402a2deb`
- `watchdog!WdLogSingleEntry1` at `0x1402a2e07`
- `watchdog!WdLogSingleEntry1` at `0x1402a2e58`
- `watchdog!WdLogSingleEntry1` at `0x1402a2ead`
- `watchdog!WdLogSingleEntry1` at `0x1402a2f91`
- `watchdog!WdLogSingleEntry1` at `0x1402a2fdf`
- `watchdog!WdLogSingleEntry1` at `0x1402a30e6`
- `watchdog!WdLogSingleEntry1` at `0x1402a28c8`
- `watchdog!WdLogSingleEntry1` at `0x1402a2958`
- `watchdog!WdLogSingleEntry1` at `0x1402a29b8`
- `watchdog!WdLogSingleEntry1` at `0x1402a2a03`
- `watchdog!WdLogSingleEntry1` at `0x1402a2a4e`
- `watchdog!WdLogSingleEntry1` at `0x1402a2a9e`
- `watchdog!WdLogSingleEntry1` at `0x1402a2ae9`
- `watchdog!WdLogSingleEntry1` at `0x1402a2bb8`
- `watchdog!WdLogSingleEntry1` at `0x1402a2c06`
- `watchdog!WdLogSingleEntry1` at `0x1402a2c65`
- `watchdog!WdLogSingleEntry1` at `0x1402a2cb3`
- `watchdog!WdLogSingleEntry1` at `0x1402a2d01`
- `watchdog!WdLogSingleEntry1` at `0x1402a2d4f`
- `watchdog!WdLogSingleEntry1` at `0x1402a2d9d`
- `watchdog!WdLogSingleEntry1` at `0x1402a2deb`
- `watchdog!WdLogSingleEntry1` at `0x1402a2e07`
- `watchdog!WdLogSingleEntry1` at `0x1402a2e58`
- `watchdog!WdLogSingleEntry1` at `0x1402a2ead`
- `watchdog!WdLogSingleEntry1` at `0x1402a2f91`
- `watchdog!WdLogSingleEntry1` at `0x1402a2fdf`
- `watchdog!WdLogSingleEntry1` at `0x1402a30e6`

## string_xrefs

- `0x1402a2849`: `d3d10warp.dll`
- `0x1402a2833`: `d3d10warp.dll`
- `0x1402a2e13`: `OpenGLDriverName`
- `0x1402a2db3`: `MiracastCompanionDriverName`
- `0x1402a2ef3`: `OpenGL`
- `0x1402a2e6e`: `OpenGLDriverNameWow`
- `0x1402a3044`: `OpenGLFlags`
- `0x1402a301d`: `OpenGLVersion`
- `0x1402a3070`: `OpenGLFlagsWow`
- `0x1402a305a`: `OpenGLVersionWow`

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
    memset(a3, 0, 0x630u);
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
      if ( (unsigned __int16)Handle > 2u )
      {
        v46 = 0;
        v37 = DpiQueryFeatureDriverInterface(a1, 4, (unsigned __int16)Handle, 16, &v46);
        v7 = v37;
        if ( v37 < 0 )
        {
          WdLogSingleEntry3(2, 4, v33, v37);
          WdLogGlobalForLineNumber = 858;
          goto LABEL_146;
        }
        v7 = 0;
        *((struct _UNICODE_STRING *)a3 + 91) = v46;
      }
      else
      {
        *((_QWORD *)a3 + 182) = 0;
        *((_QWORD *)a3 + 183) = 0;
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
      LODWORD(Handle) = 0;
      if ( (int)DpiIsFeatureEnabled(a1, 44, 0, &Handle) >= 0
        && (BYTE2(Handle) & 1) != 0
        && (unsigned __int16)Handle >= 2u )
      {
        v46 = 0;
        if ( (int)DpiQueryFeatureDriverInterface(a1, 44, 2, 16, &v46) >= 0 )
          *((struct _UNICODE_STRING *)a3 + 98) = v46;
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
LABEL_198:
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
    goto LABEL_198;
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
      WdLogGlobalForLineNumber = 1154;
      if ( !*(_BYTE *)(v8 + 2722) )
        a2[40] = 1;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1180;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWSL");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1234;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDriverWsaImage");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWsa64");
      if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1271;
      }
      RtlInitUnicodeString(&DestinationString, L"UserModeDriverNameWsa32");
      if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1289;
      }
    }
    else
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1252;
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
        WdLogGlobalForLineNumber = 1321;
      }
      RtlInitUnicodeString(&DestinationString, L"DriverNameWow");
      if ( (int)DxgkRetrieveStringFromRegistry(KeyHandle, &DestinationString) < 0 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 1334;
      }
      ZwClose(KeyHandle);
    }
    RtlInitUnicodeString(&DestinationString, L"DisplayUserModeDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1388;
    }
    RtlInitUnicodeString(&DestinationString, L"DisplayUserModeDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1406;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDListDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1460;
    }
    RtlInitUnicodeString(&DestinationString, L"UserModeDListDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1478;
    }
    RtlInitUnicodeString(&DestinationString, L"ContentProtectionDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1495;
    }
    RtlInitUnicodeString(&DestinationString, L"MiracastCompanionDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1512;
    }
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 1522;
    RtlInitUnicodeString(&DestinationString, L"OpenGLDriverName");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1534;
    }
    RtlInitUnicodeString(&DestinationString, L"OpenGLDriverNameWow");
    if ( (int)DxgkRetrieveStringFromRegistry(v43, &DestinationString) < 0 )
    {
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 1547;
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
          WdLogGlobalForLineNumber = 1588;
        }
        RtlInitUnicodeString(&DestinationString, L"DriverNameWow");
        if ( (int)DxgkRetrieveStringFromRegistry(Handle, &DestinationString) < 0 )
        {
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1601;
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
        WdLogGlobalForLineNumber = 1656;
      }
    }
    ZwClose(Handle);
    ZwClose(v43);
    goto LABEL_198;
  }
  WdLogSingleEntry1(2);
  WdLogGlobalForLineNumber = 1129;
LABEL_146:
  DpiFreeAdapterInfo(a2);
  memset(a2, 0, 0x160u);
  if ( a3 )
    memset(a3, 0, 0x630u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1402a1608  push    rbp
0x1402a160a  push    rbx
0x1402a160b  push    rsi
0x1402a160c  push    rdi
0x1402a160d  push    r12
0x1402a160f  push    r13
0x1402a1611  push    r14
0x1402a1613  push    r15
0x1402a1615  lea     rbp, [rsp-0D8h]
0x1402a161d  sub     rsp, 1D8h
0x1402a1624  mov     rax, cs:__security_cookie
0x1402a162b  xor     rax, rsp
0x1402a162e  mov     [rbp+110h+var_50], rax
0x1402a1635  mov     rdi, r8
0x1402a1638  mov     [rbp+110h+var_178], r9
0x1402a163c  mov     rsi, rdx
0x1402a163f  mov     r13, rcx
0x1402a1642  xor     r12d, r12d
0x1402a1645  lea     rcx, [rbp+110h+var_168]; void *
0x1402a1649  xor     edx, edx; Val
0x1402a164b  mov     [rsp+210h+var_1D8], r12
0x1402a1650  mov     r8d, 110h; Size
0x1402a1656  mov     [rbp+110h+var_170], r12
0x1402a165a  call    memset
0x1402a165f  mov     r14, [r13+40h]
0x1402a1663  lea     ebx, [r12+2]
0x1402a1668  lea     r15d, [r12+1]
0x1402a166d  test    rdi, rdi
0x1402a1670  jz      loc_1402A2827
0x1402a1676  mov     rbx, [r14+28h]
0x1402a167a  xor     edx, edx; Val
0x1402a167c  mov     r8d, 630h; Size
0x1402a1682  mov     rcx, rdi; void *
0x1402a1685  call    memset
0x1402a168a  mov     rax, [r14+30h]
0x1402a168e  lea     r8d, [r12+4Eh]
0x1402a1693  mov     [rdi], rax
0x1402a1696  mov     ecx, r15d
0x1402a1699  mov     eax, [r14+1F8h]
0x1402a16a0  test    eax, eax
0x1402a16a2  cmovnz  ecx, eax
0x1402a16a5  mov     [rdi+8], ecx
0x1402a16a8  movups  xmm0, xmmword ptr [r14+0A78h]
0x1402a16b0  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x1402a16b5  movups  xmm1, xmmword ptr [r14+1340h]
0x1402a16bd  movdqu  xmmword ptr [rdi+1Ch], xmm1
0x1402a16c2  movzx   eax, word ptr [r14+1320h]
0x1402a16ca  cmp     ax, r8w
0x1402a16ce  jnb     short loc_1402A16D3
0x1402a16d0  mov     r8d, eax; Size
0x1402a16d3  mov     rdx, [r14+1328h]; Src
0x1402a16da  lea     rcx, [rdi+2Ch]; void *
0x1402a16de  call    memmove
0x1402a16e3  mov     rax, [r14+0A88h]
0x1402a16ea  mov     rcx, r13
0x1402a16ed  mov     [rdi+7Ch], rax
0x1402a16f1  mov     eax, [r14+464h]
0x1402a16f8  mov     [rdi+84h], eax
0x1402a16fe  mov     eax, [r14+468h]
0x1402a1705  mov     [rdi+88h], eax
0x1402a170b  mov     eax, [r14+46Ch]
0x1402a1712  mov     [rdi+8Ch], eax
0x1402a1718  mov     eax, [r14+470h]
0x1402a171f  mov     [rdi+90h], eax
0x1402a1725  mov     eax, [r14+474h]
0x1402a172c  mov     [rdi+94h], eax
0x1402a1732  mov     eax, [r14+460h]
0x1402a1739  mov     [rdi+98h], eax
0x1402a173f  call    DpiFdoIsPostDevice
0x1402a1744  test    al, al
0x1402a1746  mov     edx, r12d
0x1402a1749  mov     eax, [rdi+9Ch]
0x1402a174f  mov     r9d, 4000h
0x1402a1755  setnz   dl
0x1402a1758  and     eax, 0FFFFFFFEh
0x1402a175b  or      edx, eax
0x1402a175d  mov     [rdi+9Ch], edx
0x1402a1763  mov     al, [r14+480h]
0x1402a176a  neg     al
0x1402a176c  sbb     ecx, ecx
0x1402a176e  and     edx, 0FFFFFFFDh
0x1402a1771  and     ecx, 2
0x1402a1774  or      ecx, edx
0x1402a1776  mov     [rdi+9Ch], ecx
0x1402a177c  mov     al, [r14+1E0h]
0x1402a1783  neg     al
0x1402a1785  sbb     edx, edx
0x1402a1787  and     ecx, 0FFFFFFFBh
0x1402a178a  and     edx, 4
0x1402a178d  or      edx, ecx
0x1402a178f  mov     [rdi+9Ch], edx
0x1402a1795  mov     al, [r14+0A9Ch]
0x1402a179c  neg     al
0x1402a179e  sbb     r8d, r8d
0x1402a17a1  and     edx, 0FFFFFFF7h
0x1402a17a4  and     r8d, 8
0x1402a17a8  or      r8d, edx
0x1402a17ab  mov     [rdi+9Ch], r8d
0x1402a17b2  mov     al, [r14+0A9Dh]
0x1402a17b9  neg     al
0x1402a17bb  sbb     ecx, ecx
0x1402a17bd  and     r8d, 0FFFFFFEFh
0x1402a17c1  and     ecx, 10h
0x1402a17c4  or      ecx, r8d
0x1402a17c7  mov     [rdi+9Ch], ecx
0x1402a17cd  mov     al, [r14+481h]
0x1402a17d4  neg     al
0x1402a17d6  sbb     edx, edx
0x1402a17d8  and     ecx, 0FFFFFFDFh
0x1402a17db  and     edx, 20h
0x1402a17de  or      edx, ecx
0x1402a17e0  mov     [rdi+9Ch], edx
0x1402a17e6  mov     al, [r14+1E1h]
0x1402a17ed  neg     al
0x1402a17ef  sbb     ecx, ecx
0x1402a17f1  btr     edx, 0Eh
0x1402a17f5  and     ecx, r9d
0x1402a17f8  or      r8d, 0FFFFFFFFh
0x1402a17fc  or      ecx, edx
0x1402a17fe  mov     [rdi+9Ch], ecx
0x1402a1804  mov     eax, [r14+0E24h]
0x1402a180b  sub     eax, r8d
0x1402a180e  neg     eax
0x1402a1810  sbb     edx, edx
0x1402a1812  btr     ecx, 0Ch
0x1402a1816  and     edx, 1000h
0x1402a181c  or      edx, ecx
0x1402a181e  mov     [rdi+9Ch], edx
0x1402a1824  mov     eax, [r14+0D20h]
0x1402a182b  sub     eax, r8d
0x1402a182e  neg     eax
0x1402a1830  sbb     ecx, ecx
0x1402a1832  and     edx, 0FFFFFFBFh
0x1402a1835  and     ecx, 40h
0x1402a1838  or      ecx, edx
0x1402a183a  mov     [rdi+9Ch], ecx
0x1402a1840  mov     al, [r14+0B1Ch]
0x1402a1847  neg     al
0x1402a1849  sbb     edx, edx
0x1402a184b  btr     ecx, 7
0x1402a184f  and     edx, 80h
0x1402a1855  or      edx, ecx
0x1402a1857  mov     [rdi+9Ch], edx
0x1402a185d  mov     al, [r14+486h]
0x1402a1864  neg     al
0x1402a1866  sbb     ecx, ecx
0x1402a1868  btr     edx, 8
0x1402a186c  and     ecx, 100h
0x1402a1872  or      ecx, edx
0x1402a1874  mov     [rdi+9Ch], ecx
0x1402a187a  mov     al, [r14+0A9Fh]
0x1402a1881  neg     al
0x1402a1883  sbb     edx, edx
0x1402a1885  btr     ecx, 9
0x1402a1889  and     edx, 200h
0x1402a188f  or      edx, ecx
0x1402a1891  mov     [rdi+9Ch], edx
0x1402a1897  mov     al, [r14+0A9Eh]
0x1402a189e  neg     al
0x1402a18a0  sbb     ecx, ecx
0x1402a18a2  btr     edx, 0Dh
0x1402a18a6  and     ecx, 2000h
0x1402a18ac  or      ecx, edx
0x1402a18ae  mov     [rdi+9Ch], ecx
0x1402a18b4  mov     al, [r14+0AA4h]
0x1402a18bb  neg     al
0x1402a18bd  sbb     edx, edx
0x1402a18bf  btr     ecx, 0Ah
0x1402a18c3  and     edx, 400h
0x1402a18c9  or      edx, ecx
0x1402a18cb  mov     [rdi+9Ch], edx
0x1402a18d1  mov     al, [r14+0AA5h]
0x1402a18d8  neg     al
0x1402a18da  sbb     ecx, ecx
0x1402a18dc  btr     edx, 0Bh
0x1402a18e0  and     ecx, 800h
0x1402a18e6  or      ecx, edx
0x1402a18e8  mov     [rdi+9Ch], ecx
0x1402a18ee  mov     al, [r14+0B1Dh]
0x1402a18f5  neg     al
0x1402a18f7  sbb     edx, edx
0x1402a18f9  btr     ecx, 0Fh
0x1402a18fd  and     edx, 8000h
0x1402a1903  or      edx, ecx
0x1402a1905  mov     [rdi+9Ch], edx
0x1402a190b  mov     al, [r14+0B1Eh]
0x1402a1912  neg     al
0x1402a1914  sbb     ecx, ecx
0x1402a1916  btr     edx, 10h
0x1402a191a  and     ecx, 10000h
0x1402a1920  or      ecx, edx
0x1402a1922  mov     [rdi+9Ch], ecx
0x1402a1928  btr     ecx, 11h
0x1402a192c  mov     r8d, [r14+52Ch]
0x1402a1933  and     r8d, 10h
0x1402a1937  shl     r8d, 0Dh
0x1402a193b  or      r8d, ecx
0x1402a193e  mov     [rdi+9Ch], r8d
0x1402a1945  mov     al, [r14+487h]
0x1402a194c  neg     al
0x1402a194e  sbb     edx, edx
0x1402a1950  btr     r8d, 12h
0x1402a1955  and     edx, 40000h
0x1402a195b  or      edx, r8d
0x1402a195e  mov     [rdi+9Ch], edx
0x1402a1964  mov     al, [r14+0AA2h]
0x1402a196b  neg     al
0x1402a196d  sbb     ecx, ecx
0x1402a196f  btr     edx, 13h
0x1402a1973  and     ecx, 80000h
0x1402a1979  or      ecx, edx
0x1402a197b  mov     [rdi+9Ch], ecx
0x1402a1981  cmp     [rbx+0B8h], r12
0x1402a1988  jz      short loc_1402A1996
0x1402a198a  mov     al, r15b
0x1402a198d  cmp     [rbx+0C0h], r12
0x1402a1994  jnz     short loc_1402A1999
0x1402a1996  mov     al, r12b
0x1402a1999  mov     [rdi+0A0h], al
0x1402a199f  mov     rax, [rbx+110h]
0x1402a19a6  mov     [rdi+0A8h], rax
0x1402a19ad  mov     rax, [rbx+118h]
0x1402a19b4  mov     [rdi+0B0h], rax
0x1402a19bb  mov     rax, [rbx+120h]
0x1402a19c2  mov     [rdi+0B8h], rax
0x1402a19c9  mov     rax, [rbx+128h]
0x1402a19d0  mov     [rdi+0C0h], rax
0x1402a19d7  mov     rax, [rbx+130h]
0x1402a19de  mov     [rdi+0C8h], rax
0x1402a19e5  mov     rax, [rbx+138h]
0x1402a19ec  mov     [rdi+0D0h], rax
0x1402a19f3  mov     rax, [rbx+140h]
0x1402a19fa  mov     [rdi+0D8h], rax
0x1402a1a01  mov     rax, [rbx+148h]
0x1402a1a08  mov     [rdi+0E0h], rax
0x1402a1a0f  mov     rax, [rbx+150h]
0x1402a1a16  mov     [rdi+0E8h], rax
0x1402a1a1d  mov     rax, [rbx+158h]
0x1402a1a24  mov     [rdi+0F0h], rax
0x1402a1a2b  mov     rax, [rbx+160h]
0x1402a1a32  mov     [rdi+0F8h], rax
0x1402a1a39  mov     rax, [rbx+168h]
0x1402a1a40  mov     [rdi+100h], rax
0x1402a1a47  mov     rax, [rbx+170h]
0x1402a1a4e  mov     [rdi+108h], rax
0x1402a1a55  mov     rax, [rbx+178h]
0x1402a1a5c  mov     [rdi+110h], rax
0x1402a1a63  mov     rax, [rbx+180h]
0x1402a1a6a  mov     [rdi+118h], rax
0x1402a1a71  mov     rax, [rbx+188h]
0x1402a1a78  mov     [rdi+120h], rax
0x1402a1a7f  mov     rax, [rbx+190h]
0x1402a1a86  mov     [rdi+128h], rax
0x1402a1a8d  mov     rax, [rbx+198h]
0x1402a1a94  mov     [rdi+130h], rax
0x1402a1a9b  mov     rax, [rbx+1A0h]
0x1402a1aa2  mov     [rdi+138h], rax
0x1402a1aa9  mov     rax, [rbx+1A8h]
0x1402a1ab0  mov     [rdi+140h], rax
0x1402a1ab7  mov     rax, [rbx+1B0h]
0x1402a1abe  mov     [rdi+148h], rax
0x1402a1ac5  mov     rax, [rbx+1B8h]
0x1402a1acc  mov     [rdi+150h], rax
0x1402a1ad3  mov     rax, [rbx+1C0h]
0x1402a1ada  mov     [rdi+158h], rax
0x1402a1ae1  mov     rax, [rbx+1C8h]
0x1402a1ae8  mov     [rdi+160h], rax
0x1402a1aef  mov     rax, [rbx+1D0h]
0x1402a1af6  mov     [rdi+168h], rax
0x1402a1afd  mov     rax, [rbx+1D8h]
0x1402a1b04  mov     [rdi+170h], rax
0x1402a1b0b  mov     rax, [rbx+1E0h]
0x1402a1b12  mov     [rdi+178h], rax
0x1402a1b19  mov     rax, [rbx+1E8h]
0x1402a1b20  mov     [rdi+180h], rax
0x1402a1b27  mov     rax, [rbx+1F8h]
0x1402a1b2e  mov     [rdi+188h], rax
0x1402a1b35  mov     rax, [rbx+200h]
0x1402a1b3c  mov     [rdi+190h], rax
0x1402a1b43  mov     rax, [rbx+208h]
0x1402a1b4a  mov     [rdi+198h], rax
0x1402a1b51  mov     rax, [rbx+210h]
0x1402a1b58  mov     [rdi+1A0h], rax
0x1402a1b5f  mov     rax, [rbx+218h]
0x1402a1b66  mov     [rdi+1A8h], rax
0x1402a1b6d  mov     rax, [rbx+220h]
0x1402a1b74  mov     [rdi+1B0h], rax
0x1402a1b7b  mov     rax, [rbx+228h]
0x1402a1b82  mov     [rdi+1B8h], rax
0x1402a1b89  mov     rax, [rbx+230h]
0x1402a1b90  mov     [rdi+1C0h], rax
0x1402a1b97  mov     rax, [rbx+238h]
0x1402a1b9e  mov     [rdi+1C8h], rax
0x1402a1ba5  mov     rax, [rbx+240h]
0x1402a1bac  mov     [rdi+1D0h], rax
0x1402a1bb3  mov     rax, [rbx+248h]
0x1402a1bba  mov     [rdi+1D8h], rax
0x1402a1bc1  mov     rax, [rbx+250h]
0x1402a1bc8  mov     [rdi+1E0h], rax
0x1402a1bcf  mov     rax, [rbx+258h]
  ... truncated ...
```
