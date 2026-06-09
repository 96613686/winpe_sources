# PpfEvtLogGetEventStringFromType

- ea: `0x1800288c0`
- end: `0x180028c1f`
- name: `PpfEvtLogGetEventStringFromType`
- size: `863`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002da6c`
- `0x180055b4c`

## callees

- `0x1800277d8`
- `0x1800288c0`

## string_xrefs

- `0x18002895c`: `EV_PLATFORM_CONFIG_FLAGS`
- `0x180028972`: `EV_COMPACT_HASH`
- `0x18002899e`: `EV_NONHOST_CONFIG`
- `0x1800289ca`: `EV_EFI_VARIABLE_DRIVER_CONFIG`
- `0x1800289e0`: `EV_EFI_BOOT_SERVICES_APPLICATION`
- `0x1800289ee`: `EV_EFI_BOOT_SERVICES_DRIVER`
- `0x1800289fc`: `EV_EFI_RUNTIME_SERVICES_DRIVER`
- `0x180028b76`: `EV_EFI_SPDM_FIRMWARE_CONFIG`

## pseudocode

```c
const char *__fastcall PpfEvtLogGetEventStringFromType(int a1)
{
  unsigned int v2; // ecx
  unsigned int v4; // eax
  _DWORD v5[2]; // [rsp+20h] [rbp-E0h]
  const char *v6; // [rsp+28h] [rbp-D8h]
  int v7; // [rsp+30h] [rbp-D0h]
  const char *v8; // [rsp+38h] [rbp-C8h]
  int v9; // [rsp+40h] [rbp-C0h]
  const char *v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+50h] [rbp-B0h]
  const char *v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+60h] [rbp-A0h]
  const char *v14; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+70h] [rbp-90h]
  const char *v16; // [rsp+78h] [rbp-88h]
  int v17; // [rsp+80h] [rbp-80h]
  const char *v18; // [rsp+88h] [rbp-78h]
  int v19; // [rsp+90h] [rbp-70h]
  const char *v20; // [rsp+98h] [rbp-68h]
  int v21; // [rsp+A0h] [rbp-60h]
  const char *v22; // [rsp+A8h] [rbp-58h]
  int v23; // [rsp+B0h] [rbp-50h]
  const char *v24; // [rsp+B8h] [rbp-48h]
  int v25; // [rsp+C0h] [rbp-40h]
  const char *v26; // [rsp+C8h] [rbp-38h]
  int v27; // [rsp+D0h] [rbp-30h]
  const char *v28; // [rsp+D8h] [rbp-28h]
  int v29; // [rsp+E0h] [rbp-20h]
  const char *v30; // [rsp+E8h] [rbp-18h]
  int v31; // [rsp+F0h] [rbp-10h]
  const char *v32; // [rsp+F8h] [rbp-8h]
  int v33; // [rsp+100h] [rbp+0h]
  const char *v34; // [rsp+108h] [rbp+8h]
  int v35; // [rsp+110h] [rbp+10h]
  const char *v36; // [rsp+118h] [rbp+18h]
  int v37; // [rsp+120h] [rbp+20h]
  const char *v38; // [rsp+128h] [rbp+28h]
  int v39; // [rsp+130h] [rbp+30h]
  const char *v40; // [rsp+138h] [rbp+38h]
  int v41; // [rsp+140h] [rbp+40h]
  const char *v42; // [rsp+148h] [rbp+48h]
  unsigned int v43; // [rsp+150h] [rbp+50h]
  const char *v44; // [rsp+158h] [rbp+58h]
  int v45; // [rsp+160h] [rbp+60h]
  const char *v46; // [rsp+168h] [rbp+68h]
  int v47; // [rsp+170h] [rbp+70h]
  const char *v48; // [rsp+178h] [rbp+78h]
  int v49; // [rsp+180h] [rbp+80h]
  const char *v50; // [rsp+188h] [rbp+88h]
  int v51; // [rsp+190h] [rbp+90h]
  const char *v52; // [rsp+198h] [rbp+98h]
  int v53; // [rsp+1A0h] [rbp+A0h]
  const char *v54; // [rsp+1A8h] [rbp+A8h]
  int v55; // [rsp+1B0h] [rbp+B0h]
  const char *v56; // [rsp+1B8h] [rbp+B8h]
  int v57; // [rsp+1C0h] [rbp+C0h]
  const char *v58; // [rsp+1C8h] [rbp+C8h]
  int v59; // [rsp+1D0h] [rbp+D0h]
  const char *v60; // [rsp+1D8h] [rbp+D8h]
  int v61; // [rsp+1E0h] [rbp+E0h]
  const char *v62; // [rsp+1E8h] [rbp+E8h]
  int v63; // [rsp+1F0h] [rbp+F0h]
  const char *v64; // [rsp+1F8h] [rbp+F8h]
  int v65; // [rsp+200h] [rbp+100h]
  const char *v66; // [rsp+208h] [rbp+108h]
  int v67; // [rsp+210h] [rbp+110h]
  const char *v68; // [rsp+218h] [rbp+118h]
  int v69; // [rsp+220h] [rbp+120h]
  const char *v70; // [rsp+228h] [rbp+128h]
  int v71; // [rsp+230h] [rbp+130h]
  const char *v72; // [rsp+238h] [rbp+138h]
  int v73; // [rsp+240h] [rbp+140h]
  const char *v74; // [rsp+248h] [rbp+148h]
  int v75; // [rsp+250h] [rbp+150h]
  const char *v76; // [rsp+258h] [rbp+158h]

  if ( (unsigned int)Feature_Ppf_PilotFish_Integration__private_IsEnabledDeviceUsageNoInline() )
  {
    v4 = 0;
    while ( a1 != LODWORD(g_EventTypeStrings[2 * v4]) )
    {
      if ( ++v4 >= 0x24 )
        return "UNKNOWN";
    }
    return (const char *)g_EventTypeStrings[2 * v4 + 1];
  }
  else
  {
    v5[0] = 0;
    v6 = "EV_PREBOOT_CERT";
    v8 = "EV_POST_CODE";
    v10 = "EV_UNUSED";
    v12 = "EV_NO_ACTION";
    v14 = "EV_SEPARATOR";
    v16 = "EV_ACTION";
    v18 = "EV_EVENT_TAG";
    v20 = "EV_S_CRTM_CONTENTS";
    v22 = "EV_S_CRTM_VERSION";
    v24 = "EV_CPU_MICROCODE";
    v26 = "EV_PLATFORM_CONFIG_FLAGS";
    v28 = "EV_TABLE_OF_DEVICES";
    v30 = "EV_COMPACT_HASH";
    v32 = "EV_IPL";
    v34 = "EV_IPL_PARTITION_DATA";
    v36 = "EV_NONHOST_CODE";
    v38 = "EV_NONHOST_CONFIG";
    v40 = "EV_NONHOST_INFO";
    v42 = "EV_OMIT_BOOT_DEVICE_EVENTS";
    v44 = "EV_EFI_EVENT_BASE";
    v46 = "EV_EFI_VARIABLE_DRIVER_CONFIG";
    v48 = "EV_EFI_VARIABLE_BOOT";
    v50 = "EV_EFI_BOOT_SERVICES_APPLICATION";
    v52 = "EV_EFI_BOOT_SERVICES_DRIVER";
    v54 = "EV_EFI_RUNTIME_SERVICES_DRIVER";
    v56 = "EV_EFI_GPT_EVENT";
    v58 = "EV_EFI_ACTION";
    v7 = 1;
    v9 = 2;
    v11 = 3;
    v13 = 4;
    v15 = 5;
    v17 = 6;
    v19 = 7;
    v21 = 8;
    v23 = 9;
    v25 = 10;
    v27 = 11;
    v29 = 12;
    v31 = 13;
    v33 = 14;
    v35 = 15;
    v37 = 16;
    v39 = 17;
    v41 = 18;
    v43 = 0x80000000;
    v45 = -2147483647;
    v47 = -2147483646;
    v49 = -2147483645;
    v51 = -2147483644;
    v53 = -2147483643;
    v55 = -2147483642;
    v57 = -2147483641;
    v59 = -2147483640;
    v60 = "EV_EFI_PLATFORM_FIRMWARE_BLOB";
    v2 = 0;
    v61 = -2147483639;
    v62 = "EV_EFI_HANDOFF_TABLES";
    v64 = "EV_EFI_PLATFORM_FIRMWARE_BLOB2";
    v66 = "EV_EFI_HANDOFF_TABLES2";
    v68 = "EV_EFI_VARIABLE_BOOT2";
    v70 = "EV_EFI_HCRTM_EVENT";
    v72 = "EV_EFI_VARIABLE_AUTHORITY";
    v74 = "EV_EFI_SPDM_FIRMWARE_BLOB";
    v76 = "EV_EFI_SPDM_FIRMWARE_CONFIG";
    v63 = -2147483638;
    v65 = -2147483637;
    v67 = -2147483636;
    v69 = -2147483632;
    v71 = -2147483424;
    v73 = -2147483423;
    v75 = -2147483422;
    while ( a1 != v5[4 * v2] )
    {
      if ( ++v2 >= 0x24 )
        return "UNKNOWN";
    }
    return (&v6)[2 * v2];
  }
}

```

## disassembly

```asm
0x1800288c0  mov     [rsp-8+arg_0], rbx
0x1800288c5  push    rbp
0x1800288c6  lea     rbp, [rsp-160h]
0x1800288ce  sub     rsp, 260h
0x1800288d5  mov     ebx, ecx
0x1800288d7  call    Feature_Ppf_PilotFish_Integration__private_IsEnabledDeviceUsageNoInline
0x1800288dc  test    eax, eax
0x1800288de  jnz     loc_180028BE5
0x1800288e4  mov     [rsp+260h+var_240], eax
0x1800288e8  lea     rax, aEvPrebootCert; "EV_PREBOOT_CERT"
0x1800288ef  mov     [rsp+260h+var_238], rax
0x1800288f4  lea     rax, aEvPostCode; "EV_POST_CODE"
0x1800288fb  mov     [rsp+260h+var_228], rax
0x180028900  lea     rax, aEvUnused; "EV_UNUSED"
0x180028907  mov     [rsp+260h+var_218], rax
0x18002890c  lea     rax, aEvNoAction; "EV_NO_ACTION"
0x180028913  mov     [rsp+260h+var_208], rax
0x180028918  lea     rax, aEvSeparator; "EV_SEPARATOR"
0x18002891f  mov     [rsp+260h+var_1F8], rax
0x180028924  lea     rax, aEvAction; "EV_ACTION"
0x18002892b  mov     [rsp+260h+var_1E8], rax
0x180028930  lea     rax, aEvEventTag; "EV_EVENT_TAG"
0x180028937  mov     [rbp+160h+var_1D8], rax
0x18002893b  lea     rax, aEvSCrtmContent; "EV_S_CRTM_CONTENTS"
0x180028942  mov     [rbp+160h+var_1C8], rax
0x180028946  lea     rax, aEvSCrtmVersion; "EV_S_CRTM_VERSION"
0x18002894d  mov     [rbp+160h+var_1B8], rax
0x180028951  lea     rax, aEvCpuMicrocode; "EV_CPU_MICROCODE"
0x180028958  mov     [rbp+160h+var_1A8], rax
0x18002895c  lea     rax, aEvPlatformConf; "EV_PLATFORM_CONFIG_FLAGS"
0x180028963  mov     [rbp+160h+var_198], rax
0x180028967  lea     rax, aEvTableOfDevic; "EV_TABLE_OF_DEVICES"
0x18002896e  mov     [rbp+160h+var_188], rax
0x180028972  lea     rax, aEvCompactHash; "EV_COMPACT_HASH"
0x180028979  mov     [rbp+160h+var_178], rax
0x18002897d  lea     rax, aEvIpl; "EV_IPL"
0x180028984  mov     [rbp+160h+var_168], rax
0x180028988  lea     rax, aEvIplPartition; "EV_IPL_PARTITION_DATA"
0x18002898f  mov     [rbp+160h+var_158], rax
0x180028993  lea     rax, aEvNonhostCode; "EV_NONHOST_CODE"
0x18002899a  mov     [rbp+160h+var_148], rax
0x18002899e  lea     rax, aEvNonhostConfi; "EV_NONHOST_CONFIG"
0x1800289a5  mov     [rbp+160h+var_138], rax
0x1800289a9  lea     rax, aEvNonhostInfo; "EV_NONHOST_INFO"
0x1800289b0  mov     [rbp+160h+var_128], rax
0x1800289b4  lea     rax, aEvOmitBootDevi; "EV_OMIT_BOOT_DEVICE_EVENTS"
0x1800289bb  mov     [rbp+160h+var_118], rax
0x1800289bf  lea     rax, aEvEfiEventBase; "EV_EFI_EVENT_BASE"
0x1800289c6  mov     [rbp+160h+var_108], rax
0x1800289ca  lea     rax, aEvEfiVariableD; "EV_EFI_VARIABLE_DRIVER_CONFIG"
0x1800289d1  mov     [rbp+160h+var_F8], rax
0x1800289d5  lea     rax, aEvEfiVariableB_0; "EV_EFI_VARIABLE_BOOT"
0x1800289dc  mov     [rbp+160h+var_E8], rax
0x1800289e0  lea     rax, aEvEfiBootServi_1; "EV_EFI_BOOT_SERVICES_APPLICATION"
0x1800289e7  mov     [rbp+160h+var_D8], rax
0x1800289ee  lea     rax, aEvEfiBootServi_0; "EV_EFI_BOOT_SERVICES_DRIVER"
0x1800289f5  mov     [rbp+160h+var_C8], rax
0x1800289fc  lea     rax, aEvEfiRuntimeSe; "EV_EFI_RUNTIME_SERVICES_DRIVER"
0x180028a03  mov     [rbp+160h+var_B8], rax
0x180028a0a  lea     rax, aEvEfiGptEvent; "EV_EFI_GPT_EVENT"
0x180028a11  mov     [rbp+160h+var_A8], rax
0x180028a18  lea     rax, aEvEfiAction; "EV_EFI_ACTION"
0x180028a1f  mov     [rbp+160h+var_98], rax
0x180028a26  mov     [rsp+260h+var_230], 1
0x180028a2e  mov     [rsp+260h+var_220], 2
0x180028a36  mov     [rsp+260h+var_210], 3
0x180028a3e  mov     [rsp+260h+var_200], 4
0x180028a46  mov     [rsp+260h+var_1F0], 5
0x180028a4e  mov     [rbp+160h+var_1E0], 6
0x180028a55  mov     [rbp+160h+var_1D0], 7
0x180028a5c  mov     [rbp+160h+var_1C0], 8
0x180028a63  mov     [rbp+160h+var_1B0], 9
0x180028a6a  mov     [rbp+160h+var_1A0], 0Ah
0x180028a71  mov     [rbp+160h+var_190], 0Bh
0x180028a78  mov     [rbp+160h+var_180], 0Ch
0x180028a7f  mov     [rbp+160h+var_170], 0Dh
0x180028a86  mov     [rbp+160h+var_160], 0Eh
0x180028a8d  mov     [rbp+160h+var_150], 0Fh
0x180028a94  mov     [rbp+160h+var_140], 10h
0x180028a9b  mov     [rbp+160h+var_130], 11h
0x180028aa2  mov     [rbp+160h+var_120], 12h
0x180028aa9  mov     [rbp+160h+var_110], 80000000h
0x180028ab0  mov     [rbp+160h+var_100], 80000001h
0x180028ab7  mov     [rbp+160h+var_F0], 80000002h
0x180028abe  mov     [rbp+160h+var_E0], 80000003h
0x180028ac8  mov     [rbp+160h+var_D0], 80000004h
0x180028ad2  mov     [rbp+160h+var_C0], 80000005h
0x180028adc  mov     [rbp+160h+var_B0], 80000006h
0x180028ae6  mov     [rbp+160h+var_A0], 80000007h
0x180028af0  lea     rax, aEvEfiPlatformF_0; "EV_EFI_PLATFORM_FIRMWARE_BLOB"
0x180028af7  mov     [rbp+160h+var_90], 80000008h
0x180028b01  mov     [rbp+160h+var_88], rax
0x180028b08  xor     ecx, ecx
0x180028b0a  lea     rax, aEvEfiHandoffTa; "EV_EFI_HANDOFF_TABLES"
0x180028b11  mov     [rbp+160h+var_80], 80000009h
0x180028b1b  mov     [rbp+160h+var_78], rax
0x180028b22  lea     rax, aEvEfiPlatformF; "EV_EFI_PLATFORM_FIRMWARE_BLOB2"
0x180028b29  mov     [rbp+160h+var_68], rax
0x180028b30  lea     rax, aEvEfiHandoffTa_0; "EV_EFI_HANDOFF_TABLES2"
0x180028b37  mov     [rbp+160h+var_58], rax
0x180028b3e  lea     rax, aEvEfiVariableB; "EV_EFI_VARIABLE_BOOT2"
0x180028b45  mov     [rbp+160h+var_48], rax
0x180028b4c  lea     rax, aEvEfiHcrtmEven; "EV_EFI_HCRTM_EVENT"
0x180028b53  mov     [rbp+160h+var_38], rax
0x180028b5a  lea     rax, aEvEfiVariableA_0; "EV_EFI_VARIABLE_AUTHORITY"
0x180028b61  mov     [rbp+160h+var_28], rax
0x180028b68  lea     rax, aEvEfiSpdmFirmw_0; "EV_EFI_SPDM_FIRMWARE_BLOB"
0x180028b6f  mov     [rbp+160h+var_18], rax
0x180028b76  lea     rax, aEvEfiSpdmFirmw; "EV_EFI_SPDM_FIRMWARE_CONFIG"
0x180028b7d  mov     [rbp+160h+var_8], rax
0x180028b84  mov     [rbp+160h+var_70], 8000000Ah
0x180028b8e  mov     [rbp+160h+var_60], 8000000Bh
0x180028b98  mov     [rbp+160h+var_50], 8000000Ch
0x180028ba2  mov     [rbp+160h+var_40], 80000010h
0x180028bac  mov     [rbp+160h+var_30], 800000E0h
0x180028bb6  mov     [rbp+160h+var_20], 800000E1h
0x180028bc0  mov     [rbp+160h+var_10], 800000E2h
0x180028bca  mov     eax, ecx
0x180028bcc  add     rax, rax
0x180028bcf  cmp     ebx, [rsp+rax*8+260h+var_240]
0x180028bd3  jz      short loc_180028BDE
0x180028bd5  inc     ecx
0x180028bd7  cmp     ecx, 24h ; '$'
0x180028bda  jb      short loc_180028BCA
0x180028bdc  jmp     short loc_180028BFF
0x180028bde  mov     rax, [rsp+rax*8+260h+var_238]
0x180028be3  jmp     short loc_180028C0D
0x180028be5  xor     eax, eax
0x180028be7  lea     rdx, g_EventTypeStrings
0x180028bee  mov     ecx, eax
0x180028bf0  add     rcx, rcx
0x180028bf3  cmp     ebx, [rdx+rcx*8]
0x180028bf6  jz      short loc_180028C08
0x180028bf8  inc     eax
0x180028bfa  cmp     eax, 24h ; '$'
0x180028bfd  jb      short loc_180028BEE
0x180028bff  lea     rax, aUnknown; "UNKNOWN"
0x180028c06  jmp     short loc_180028C0D
0x180028c08  mov     rax, [rdx+rcx*8+8]
0x180028c0d  mov     rbx, [rsp+260h+arg_0]
0x180028c15  add     rsp, 260h
0x180028c1c  pop     rbp
0x180028c1d  retn
```
