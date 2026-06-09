# InstallTunnelInterface

- ea: `0x18004ad68`
- end: `0x18004b11e`
- name: `InstallTunnelInterface`
- size: `950`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180045db8`
- `0x1800598cc`

## callees

- `0x18000d7c0`
- `0x18004ad68`
- `0x18004b5f0`

## import_xrefs

- `IPHLPAPI!ConvertCompartmentIdToGuid` at `0x18004add2`
- `IPHLPAPI!ConvertCompartmentIdToGuid` at `0x18004add2`
- `NetSetupApi!NetSetupCreateObject` at `0x18004b0a0`
- `NetSetupApi!NetSetupCreateObject` at `0x18004b0a0`
- `NetSetupApi!NetSetupClose` at `0x18004b0f0`
- `NetSetupApi!NetSetupClose` at `0x18004b0f0`
- `NetSetupApi!NetSetupCommit` at `0x18004b0c0`
- `NetSetupApi!NetSetupCommit` at `0x18004b0c0`
- `NetSetupApi!NetSetupInitialize` at `0x18004b06d`
- `NetSetupApi!NetSetupInitialize` at `0x18004b06d`

## string_xrefs

- `0x18004adf4`: `Failed to get Compartment GUID from compartment Id %d: 0x%x`
- `0x18004b0b2`: `Failed to create new Tunnel interface 0x%x`
- `0x18004b0d2`: `Failed to commit transaction 0x%x`

## pseudocode

```c
__int64 __fastcall InstallTunnelInterface(int a1, __int64 a2, __int64 a3, NET_IF_COMPARTMENT_ID a4, __int64 a5)
{
  NTSTATUS v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  char v16; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  GUID CompartmentGuid; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+74h] [rbp-8Ch]
  int v25; // [rsp+7Ch] [rbp-84h]
  int v26; // [rsp+80h] [rbp-80h]
  int v27; // [rsp+84h] [rbp-7Ch]
  __int64 *v28; // [rsp+88h] [rbp-78h]
  __int128 v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A4h] [rbp-5Ch]
  int v32; // [rsp+ACh] [rbp-54h]
  int v33; // [rsp+B0h] [rbp-50h]
  int v34; // [rsp+B4h] [rbp-4Ch]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int128 v36; // [rsp+C0h] [rbp-40h]
  int v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D4h] [rbp-2Ch]
  int v39; // [rsp+DCh] [rbp-24h]
  int v40; // [rsp+E0h] [rbp-20h]
  int v41; // [rsp+E4h] [rbp-1Ch]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  __int128 v43; // [rsp+F0h] [rbp-10h]
  int v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+104h] [rbp+4h]
  int v46; // [rsp+10Ch] [rbp+Ch]
  int v47; // [rsp+110h] [rbp+10h]
  int v48; // [rsp+114h] [rbp+14h]
  int *v49; // [rsp+118h] [rbp+18h]
  __int128 v50; // [rsp+120h] [rbp+20h]
  int v51; // [rsp+130h] [rbp+30h]
  __int64 v52; // [rsp+134h] [rbp+34h]
  int v53; // [rsp+13Ch] [rbp+3Ch]
  int v54; // [rsp+140h] [rbp+40h]
  int v55; // [rsp+144h] [rbp+44h]
  GUID *p_CompartmentGuid; // [rsp+148h] [rbp+48h]
  __int128 v57; // [rsp+150h] [rbp+50h]
  int v58; // [rsp+160h] [rbp+60h]
  __int64 v59; // [rsp+164h] [rbp+64h]
  int v60; // [rsp+16Ch] [rbp+6Ch]
  int v61; // [rsp+170h] [rbp+70h]
  int v62; // [rsp+174h] [rbp+74h]
  int *v63; // [rsp+178h] [rbp+78h]
  __int128 v64; // [rsp+180h] [rbp+80h]
  int v65; // [rsp+190h] [rbp+90h]
  __int64 v66; // [rsp+194h] [rbp+94h]
  int v67; // [rsp+19Ch] [rbp+9Ch]
  int v68; // [rsp+1A0h] [rbp+A0h]
  int v69; // [rsp+1A4h] [rbp+A4h]
  char *v70; // [rsp+1A8h] [rbp+A8h]
  __int128 v71; // [rsp+1B0h] [rbp+B0h]
  int v72; // [rsp+1C0h] [rbp+C0h]
  __int64 v73; // [rsp+1C4h] [rbp+C4h]
  int v74; // [rsp+1CCh] [rbp+CCh]
  int v75; // [rsp+1D0h] [rbp+D0h]
  int v76; // [rsp+1D4h] [rbp+D4h]
  char *v77; // [rsp+1D8h] [rbp+D8h]
  __int128 v78; // [rsp+1E0h] [rbp+E0h]
  int v79; // [rsp+1F0h] [rbp+F0h]
  __int64 v80; // [rsp+1F4h] [rbp+F4h]
  int v81; // [rsp+1FCh] [rbp+FCh]
  int v82; // [rsp+200h] [rbp+100h]
  int v83; // [rsp+204h] [rbp+104h]
  char *v84; // [rsp+208h] [rbp+108h]
  __int128 v85; // [rsp+210h] [rbp+110h]
  int v86; // [rsp+220h] [rbp+120h]
  __int64 v87; // [rsp+224h] [rbp+124h]
  int v88; // [rsp+22Ch] [rbp+12Ch]
  int v89; // [rsp+230h] [rbp+130h]
  int v90; // [rsp+234h] [rbp+134h]
  int *v91; // [rsp+238h] [rbp+138h]

  v20 = a1;
  v18 = 9;
  v19 = 2;
  v17 = 0;
  CompartmentGuid = 0;
  v16 = 1;
  v8 = ConvertCompartmentIdToGuid(a4, &CompartmentGuid);
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    else
      v9 = v8;
    EventWrite0(0x800000, L"Failed to get Compartment GUID from compartment Id %d: 0x%x", a4, (unsigned int)v8);
  }
  else
  {
    v23 = 90;
    v24 = 0;
    v25 = 0;
    v22 = NETSETUPPKEY_Interface_DriverId;
    v26 = 13;
    v27 = 16;
    v28 = TUNNEL_DRIVER_GUID;
    v30 = 20;
    v10 = -1;
    v31 = 0;
    v32 = 0;
    v29 = NETSETUPPKEY_Interface_IfAliasBase;
    v11 = -1;
    v33 = 18;
    do
      ++v11;
    while ( *(_WORD *)(a2 + 2 * v11) );
    v35 = a2;
    v34 = 2 * v11 + 2;
    v37 = 18;
    v38 = 0;
    v39 = 0;
    v36 = NETSETUPPKEY_Interface_IfDescr;
    v40 = 18;
    do
      ++v10;
    while ( *(_WORD *)(a3 + 2 * v10) );
    v42 = a3;
    v41 = 2 * v10 + 2;
    v44 = 6;
    v45 = 0;
    v46 = 0;
    v43 = NETSETUPPKEY_INF_Characteristics;
    v54 = 13;
    v48 = 4;
    v50 = NETSETUPPKEY_Interface_IsolationCompartmentId;
    v49 = &v18;
    v51 = 72;
    v52 = 0;
    v53 = 0;
    p_CompartmentGuid = &CompartmentGuid;
    v58 = 20;
    v59 = 0;
    v60 = 0;
    v63 = &v19;
    v65 = 32;
    v66 = 0;
    v67 = 0;
    v70 = &v16;
    v72 = 20;
    v73 = 0;
    v74 = 0;
    v77 = &v16;
    v57 = NETSETUPPKEY_Object_CreatedBy;
    v79 = 32;
    v80 = 0;
    v64 = NETSETUPPKEY_Object_BlockMigration;
    v81 = 0;
    v84 = &v16;
    v71 = NETSETUPPKEY_Driver_HideInUi;
    v86 = 2;
    v87 = 0;
    v78 = NETSETUPPKEY_Interface_IsVirtual;
    v88 = 0;
    v47 = 7;
    v55 = 16;
    v61 = 7;
    v62 = 4;
    v68 = 17;
    v69 = 1;
    v75 = 17;
    v76 = 1;
    v82 = 17;
    v83 = 1;
    v85 = NETSETUPPKEY_TunnelInterface_TunnelType;
    v89 = 7;
    v90 = 4;
    v91 = &v20;
    v12 = NetSetupInitialize(0, &v17);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v13 = NetSetupCreateObject(v17, 2, 10, &v22, a5);
      v9 = v13;
      if ( v13 >= 0 )
      {
        v14 = NetSetupCommit(v17);
        v9 = v14;
        if ( v14 < 0 )
          EventWrite0(0x800000, L"Failed to commit transaction 0x%x", (unsigned int)v14);
      }
      else
      {
        EventWrite0(0x800000, L"Failed to create new Tunnel interface 0x%x", (unsigned int)v13);
      }
    }
    else
    {
      EventWrite0(0x800000, L"Failed to initialize NetSetup 0x%x", (unsigned int)v12);
    }
  }
  if ( v17 )
    NetSetupClose();
  return v9;
}

```

## disassembly

```asm
0x18004ad68  push    rbp
0x18004ad6a  push    rbx
0x18004ad6b  push    rsi
0x18004ad6c  push    rdi
0x18004ad6d  push    r14
0x18004ad6f  push    r15
0x18004ad71  lea     rbp, [rsp-158h]
0x18004ad79  sub     rsp, 258h
0x18004ad80  mov     rax, cs:__security_cookie
0x18004ad87  xor     rax, rsp
0x18004ad8a  mov     [rbp+180h+var_40], rax
0x18004ad91  mov     r14, [rbp+180h+arg_20]
0x18004ad98  mov     rbx, rdx
0x18004ad9b  mov     [rsp+280h+var_238], ecx
0x18004ad9f  lea     rdx, [rsp+280h+CompartmentGuid]; CompartmentGuid
0x18004ada4  xorps   xmm0, xmm0
0x18004ada7  mov     [rsp+280h+var_240], 9
0x18004adaf  xor     r15d, r15d
0x18004adb2  mov     [rsp+280h+var_23C], 2
0x18004adba  mov     ecx, r9d; CompartmentId
0x18004adbd  mov     [rsp+280h+var_248], r15
0x18004adc2  movups  xmmword ptr [rsp+280h+CompartmentGuid.Data1], xmm0
0x18004adc7  mov     edi, r9d
0x18004adca  mov     [rsp+280h+var_250], 1
0x18004adcf  mov     rsi, r8
0x18004add2  call    cs:__imp_ConvertCompartmentIdToGuid
0x18004add9  nop     dword ptr [rax+rax+00h]
0x18004adde  test    eax, eax
0x18004ade0  jz      short loc_18004AE0D
0x18004ade2  jg      short loc_18004ADE8
0x18004ade4  mov     ebx, eax
0x18004ade6  jmp     short loc_18004ADF1
0x18004ade8  movzx   ebx, ax
0x18004adeb  or      ebx, 80070000h
0x18004adf1  mov     r9d, eax
0x18004adf4  lea     rdx, aFailedToGetCom; "Failed to get Compartment GUID from com"...
0x18004adfb  mov     r8d, edi
0x18004adfe  mov     ecx, 800000h
0x18004ae03  call    EventWrite0
0x18004ae08  jmp     loc_18004B0E6
0x18004ae0d  mov     eax, cs:dword_18009A6B0
0x18004ae13  movups  xmm0, cs:NETSETUPPKEY_Interface_DriverId
0x18004ae1a  mov     [rsp+280h+var_210], eax
0x18004ae1e  xor     eax, eax
0x18004ae20  mov     [rsp+280h+var_20C], rax
0x18004ae25  mov     [rsp+280h+var_204], eax
0x18004ae29  movaps  [rsp+280h+var_220], xmm0
0x18004ae2e  movups  xmm0, cs:NETSETUPPKEY_Interface_IfAliasBase
0x18004ae35  lea     r9d, [rax+0Dh]
0x18004ae39  lea     r10d, [rax+10h]
0x18004ae3d  mov     [rbp+180h+var_200], r9d
0x18004ae41  lea     rax, TUNNEL_DRIVER_GUID
0x18004ae48  mov     [rbp+180h+var_1FC], r10d
0x18004ae4c  mov     [rbp+180h+var_1F8], rax
0x18004ae50  mov     eax, cs:dword_18009A5D0
0x18004ae56  mov     [rbp+180h+var_1E0], eax
0x18004ae59  xor     eax, eax
0x18004ae5b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004ae5f  mov     [rbp+180h+var_1DC], rax
0x18004ae63  mov     [rbp+180h+var_1D4], eax
0x18004ae66  movaps  [rbp+180h+var_1F0], xmm0
0x18004ae6a  lea     edx, [rax+12h]
0x18004ae6d  mov     rax, rcx
0x18004ae70  mov     [rbp+180h+var_1D0], edx
0x18004ae73  inc     rax
0x18004ae76  cmp     [rbx+rax*2], r15w
0x18004ae7b  jnz     short loc_18004AE73
0x18004ae7d  movups  xmm0, cs:NETSETUPPKEY_Interface_IfDescr
0x18004ae84  lea     eax, ds:2[rax*2]
0x18004ae8b  mov     [rbp+180h+var_1C8], rbx
0x18004ae8f  mov     [rbp+180h+var_1CC], eax
0x18004ae92  mov     eax, cs:dword_18009A290
0x18004ae98  mov     [rbp+180h+var_1B0], eax
0x18004ae9b  xor     eax, eax
0x18004ae9d  mov     [rbp+180h+var_1AC], rax
0x18004aea1  mov     [rbp+180h+var_1A4], eax
0x18004aea4  movaps  [rbp+180h+var_1C0], xmm0
0x18004aea8  mov     [rbp+180h+var_1A0], edx
0x18004aeab  inc     rcx
0x18004aeae  cmp     [rsi+rcx*2], r15w
0x18004aeb3  jnz     short loc_18004AEAB
0x18004aeb5  movups  xmm0, cs:NETSETUPPKEY_INF_Characteristics
0x18004aebc  lea     eax, ds:2[rcx*2]
0x18004aec3  mov     [rbp+180h+var_198], rsi
0x18004aec7  mov     [rbp+180h+var_19C], eax
0x18004aeca  mov     eax, cs:dword_18009A608
0x18004aed0  mov     [rbp+180h+var_180], eax
0x18004aed3  xor     eax, eax
0x18004aed5  mov     [rbp+180h+var_17C], rax
0x18004aed9  mov     [rbp+180h+var_174], eax
0x18004aedc  movaps  [rbp+180h+var_190], xmm0
0x18004aee0  movups  xmm0, cs:NETSETUPPKEY_Interface_IsolationCompartmentId
0x18004aee7  lea     edx, [rax+4]
0x18004aeea  mov     [rbp+180h+var_140], r9d
0x18004aeee  lea     r8d, [rax+7]
0x18004aef2  mov     [rbp+180h+var_16C], edx
0x18004aef5  movaps  [rbp+180h+var_160], xmm0
0x18004aef9  lea     rax, [rsp+280h+var_240]
0x18004aefe  movups  xmm0, cs:NETSETUPPKEY_Object_CreatedBy
0x18004af05  mov     [rbp+180h+var_168], rax
0x18004af09  lea     ecx, [rdx+0Dh]
0x18004af0c  mov     eax, cs:dword_18009A918
0x18004af12  mov     [rbp+180h+var_150], eax
0x18004af15  xor     eax, eax
0x18004af17  mov     [rbp+180h+var_14C], rax
0x18004af1b  mov     [rbp+180h+var_144], eax
0x18004af1e  lea     rax, [rsp+280h+CompartmentGuid]
0x18004af23  mov     [rbp+180h+var_138], rax
0x18004af27  mov     eax, cs:dword_18009A930
0x18004af2d  mov     [rbp+180h+var_120], eax
0x18004af30  xor     eax, eax
0x18004af32  mov     [rbp+180h+var_11C], rax
0x18004af36  mov     [rbp+180h+var_114], eax
0x18004af39  lea     rax, [rsp+280h+var_23C]
0x18004af3e  mov     [rbp+180h+var_108], rax
0x18004af42  mov     eax, cs:dword_18009A720
0x18004af48  mov     [rbp+180h+var_F0], eax
0x18004af4e  xor     eax, eax
0x18004af50  mov     [rbp+180h+var_EC], rax
0x18004af57  mov     [rbp+180h+var_E4], eax
0x18004af5d  lea     rax, [rsp+280h+var_250]
0x18004af62  mov     [rbp+180h+var_D8], rax
0x18004af69  mov     eax, cs:dword_18009AD40
0x18004af6f  mov     [rbp+180h+var_C0], eax
0x18004af75  xor     eax, eax
0x18004af77  mov     [rbp+180h+var_BC], rax
0x18004af7e  mov     [rbp+180h+var_B4], eax
0x18004af84  lea     rax, [rsp+280h+var_250]
0x18004af89  mov     [rbp+180h+var_A8], rax
0x18004af90  mov     eax, cs:dword_18009A360
0x18004af96  movaps  [rbp+180h+var_130], xmm0
0x18004af9a  movups  xmm0, cs:NETSETUPPKEY_Object_BlockMigration
0x18004afa1  mov     [rbp+180h+var_90], eax
0x18004afa7  xor     eax, eax
0x18004afa9  mov     [rbp+180h+var_8C], rax
0x18004afb0  movaps  [rbp+180h+var_100], xmm0
0x18004afb7  movups  xmm0, cs:NETSETUPPKEY_Driver_HideInUi
0x18004afbe  mov     [rbp+180h+var_84], eax
0x18004afc4  lea     rax, [rsp+280h+var_250]
0x18004afc9  mov     [rbp+180h+var_78], rax
0x18004afd0  mov     eax, cs:dword_18009AB88
0x18004afd6  movaps  [rbp+180h+var_D0], xmm0
0x18004afdd  movups  xmm0, cs:NETSETUPPKEY_Interface_IsVirtual
0x18004afe4  mov     [rbp+180h+var_60], eax
0x18004afea  xor     eax, eax
0x18004afec  mov     [rbp+180h+var_5C], rax
0x18004aff3  movaps  [rbp+180h+var_A0], xmm0
0x18004affa  movups  xmm0, cs:NETSETUPPKEY_TunnelInterface_TunnelType
0x18004b001  mov     [rbp+180h+var_54], eax
0x18004b007  mov     [rbp+180h+var_170], r8d
0x18004b00b  mov     [rbp+180h+var_13C], r10d
0x18004b00f  mov     [rbp+180h+var_110], r8d
0x18004b013  mov     [rbp+180h+var_10C], edx
0x18004b016  mov     [rbp+180h+var_E0], ecx
0x18004b01c  mov     [rbp+180h+var_DC], 1
0x18004b026  mov     [rbp+180h+var_B0], ecx
0x18004b02c  mov     [rbp+180h+var_AC], 1
0x18004b036  mov     [rbp+180h+var_80], ecx
0x18004b03c  mov     [rbp+180h+var_7C], 1
0x18004b046  movaps  [rbp+180h+var_70], xmm0
0x18004b04d  mov     [rbp+180h+var_50], r8d
0x18004b054  mov     [rbp+180h+var_4C], edx
0x18004b05a  lea     rax, [rsp+280h+var_238]
0x18004b05f  xor     ecx, ecx
0x18004b061  lea     rdx, [rsp+280h+var_248]
0x18004b066  mov     [rbp+180h+var_48], rax
0x18004b06d  call    cs:__imp_NetSetupInitialize
0x18004b074  nop     dword ptr [rax+rax+00h]
0x18004b079  mov     ebx, eax
0x18004b07b  test    eax, eax
0x18004b07d  jns     short loc_18004B088
0x18004b07f  lea     rdx, aFailedToInitia; "Failed to initialize NetSetup 0x%x"
0x18004b086  jmp     short loc_18004B0D9
0x18004b088  mov     rcx, [rsp+280h+var_248]
0x18004b08d  lea     r9, [rsp+280h+var_220]
0x18004b092  mov     edx, 2
0x18004b097  mov     [rsp+280h+var_260], r14
0x18004b09c  lea     r8d, [rdx+8]
0x18004b0a0  call    cs:__imp_NetSetupCreateObject
0x18004b0a7  nop     dword ptr [rax+rax+00h]
0x18004b0ac  mov     ebx, eax
0x18004b0ae  test    eax, eax
0x18004b0b0  jns     short loc_18004B0BB
0x18004b0b2  lea     rdx, aFailedToCreate_0; "Failed to create new Tunnel interface 0"...
0x18004b0b9  jmp     short loc_18004B0D9
0x18004b0bb  mov     rcx, [rsp+280h+var_248]
0x18004b0c0  call    cs:__imp_NetSetupCommit
0x18004b0c7  nop     dword ptr [rax+rax+00h]
0x18004b0cc  mov     ebx, eax
0x18004b0ce  test    eax, eax
0x18004b0d0  jns     short loc_18004B0E6
0x18004b0d2  lea     rdx, aFailedToCommit; "Failed to commit transaction 0x%x"
0x18004b0d9  mov     r8d, eax
0x18004b0dc  mov     ecx, 800000h
0x18004b0e1  call    EventWrite0
0x18004b0e6  mov     rcx, [rsp+280h+var_248]
0x18004b0eb  test    rcx, rcx
0x18004b0ee  jz      short loc_18004B0FC
0x18004b0f0  call    cs:__imp_NetSetupClose
0x18004b0f7  nop     dword ptr [rax+rax+00h]
0x18004b0fc  mov     eax, ebx
0x18004b0fe  mov     rcx, [rbp+180h+var_40]
0x18004b105  xor     rcx, rsp; StackCookie
0x18004b108  call    __security_check_cookie
0x18004b10d  add     rsp, 258h
0x18004b114  pop     r15
0x18004b116  pop     r14
0x18004b118  pop     rdi
0x18004b119  pop     rsi
0x18004b11a  pop     rbx
0x18004b11b  pop     rbp
0x18004b11c  retn
```
