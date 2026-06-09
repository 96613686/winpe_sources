# SetIpForwardRow

- ea: `0x18000ace0`
- end: `0x18000b0fb`
- name: `SetIpForwardRow`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180007298`

## callees

- `0x18000aa9c`
- `0x18000ac60`
- `0x18000ace0`
- `0x180017aa8`
- `0x18002f000`
- `0x1800488c0`
- `0x18004a340`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000af6f`
- `ntdll!RtlReleaseResource` at `0x18000afb5`
- `ntdll!RtlReleaseResource` at `0x18000af6f`
- `ntdll!RtlReleaseResource` at `0x18000afb5`
- `ntdll!RtlAcquireResourceShared` at `0x18000af43`
- `ntdll!RtlAcquireResourceShared` at `0x18000af43`

## string_xrefs

- `0x18000b074`: `SetIpForwardRow: Protocol %d not valid`
- `0x18000aec3`: `SetIpForwardRow: Unable to delete route from RTM. Error %d`

## pseudocode

```c
__int64 __fastcall SetIpForwardRow(__int64 a1, unsigned __int8 *a2)
{
  char v4; // al
  unsigned int i; // edx
  void *v6; // rsi
  int v7; // ecx
  ULONG v8; // edx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // r8
  ULONG v12; // ecx
  __int64 v13; // r9
  unsigned int v14; // eax
  char v15; // cl
  unsigned int BestNextHopMaskGivenIndex; // ebx
  __int64 v18; // rax
  __int64 v19; // r8
  const wchar_t *v20; // rdx
  int v21; // ecx
  unsigned __int8 *v22; // rax
  unsigned int v23; // ebx
  __int64 v24; // r8
  ULONG v25; // [rsp+20h] [rbp-8C8h]
  ULONG v26; // [rsp+20h] [rbp-8C8h]
  int v27; // [rsp+28h] [rbp-8C0h]
  int v28; // [rsp+28h] [rbp-8C0h]
  int v29; // [rsp+30h] [rbp-8B8h]
  int v30; // [rsp+38h] [rbp-8B0h]
  int v31; // [rsp+40h] [rbp-8A8h]
  int v32; // [rsp+48h] [rbp-8A0h]
  _BYTE v33[80]; // [rsp+60h] [rbp-888h] BYREF
  struct _GUID v34; // [rsp+B0h] [rbp-838h] BYREF
  int v35; // [rsp+C0h] [rbp-828h] BYREF
  _BYTE v36[2044]; // [rsp+C4h] [rbp-824h] BYREF

  memset_0(v33, 0, 0x48u);
  v35 = 0;
  v34 = GUID_NULL;
  memset_0(v36, 0, sizeof(v36));
  v4 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, L"Entered: %ws", L"SetIpForwardRow");
    v4 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v35);
      v4 = Microsoft_Windows_RRASEnableBits;
    }
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 5 )
      goto LABEL_38;
    if ( *((_DWORD *)a2 + 6) == LODWORD(g_rgRtmHandlesV4[2 * i]) )
      break;
  }
  v6 = (void *)g_rgRtmHandlesV4[2 * i + 1];
  if ( !v6 )
  {
LABEL_38:
    if ( v4 >= 0 )
      goto LABEL_43;
    v19 = *((unsigned int *)a2 + 6);
    v20 = L"SetIpForwardRow: Protocol %d not valid";
LABEL_40:
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, v20, v19);
    goto LABEL_41;
  }
  if ( (*(_DWORD *)a2 & *((_DWORD *)a2 + 1)) != *(_DWORD *)a2 )
  {
    if ( v4 < 0 )
    {
      v7 = a2[3];
      v8 = a2[2];
      v9 = a2[1];
      v10 = *a2;
      v32 = a2[7];
      v31 = a2[6];
      v30 = a2[5];
      LOWORD(v35) = 0;
      v29 = a2[4];
      v27 = v7;
      v25 = v8;
      FormatRRASErrorString(
        &v35,
        L"SetIpForwardRow: Dest %d.%d.%d.%d and Mask %d.%d.%d.%d wrong",
        v10,
        v9,
        v25,
        v27,
        v29,
        v30,
        v31,
        v32);
      goto LABEL_41;
    }
LABEL_43:
    if ( v4 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: SetIpForwardRow");
    return 87;
  }
  v11 = *a2;
  if ( (unsigned int)v11 >= 0xE0 )
  {
    if ( v4 >= 0 )
      goto LABEL_43;
    v12 = a2[2];
    v13 = a2[1];
    LOWORD(v35) = 0;
    v28 = a2[3];
    v26 = v12;
    FormatRRASErrorString(&v35, L"SetIpForwardRow: Dest %d.%d.%d.%d is invalid", v11, v13, v26, v28);
LABEL_41:
    v4 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v35);
      v4 = Microsoft_Windows_RRASEnableBits;
    }
    goto LABEL_43;
  }
  if ( a1 )
  {
    v14 = DeleteIpForwardRow(a1);
    if ( v14 )
    {
      v15 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"SetIpForwardRow: Unable to delete route from RTM. Error %d", v14);
        v15 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v35);
          v15 = Microsoft_Windows_RRASEnableBits;
        }
      }
      if ( v15 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: SetIpForwardRow");
      return 1003;
    }
  }
  if ( *((_DWORD *)a2 + 6) != 3 )
    *((_DWORD *)a2 + 7) = -1;
  RtlAcquireResourceShared(&Resource, 1u);
  BestNextHopMaskGivenIndex = GetBestNextHopMaskGivenIndex(*((unsigned int *)a2 + 4), *((unsigned int *)a2 + 3));
  v18 = InterfaceLookupByIfIndex(*((unsigned int *)a2 + 4), 1);
  if ( !v18 )
  {
    RtlReleaseResource(&Resource);
    v4 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_43;
    v19 = *((unsigned int *)a2 + 4);
    v20 = L"SetIpForwardRow: I/f 0x%x doesnt exist";
    goto LABEL_40;
  }
  v21 = *(_DWORD *)(v18 + 144);
  if ( (unsigned int)(v21 - 1) <= 1 || v21 == 7 )
    *((_DWORD *)a2 + 3) = 0;
  RtlReleaseResource(&Resource);
  v22 = (unsigned __int8 *)ConvertMibRouteToRouteInfo(a2, v33);
  v23 = AddRtmRoute(v6, v22, 48, BestNextHopMaskGivenIndex, *((_DWORD *)a2 + 7), 1u, &v34, 0);
  if ( v23 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v24 = *(unsigned int *)a2;
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"SetIpForwardRow: Could not set route to RTM: Dest %x\n", v24);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v35);
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: SetIpForwardRow");
  return v23;
}

```

## disassembly

```asm
0x18000ace0  mov     [rsp+arg_10], rbx
0x18000ace5  mov     [rsp+arg_18], rsi
0x18000acea  push    rdi
0x18000aceb  push    r12
0x18000aced  push    r15
0x18000acef  sub     rsp, 8D0h
0x18000acf6  mov     rax, cs:__security_cookie
0x18000acfd  xor     rax, rsp
0x18000ad00  mov     [rsp+8E8h+var_28], rax
0x18000ad08  mov     rdi, rdx
0x18000ad0b  mov     rbx, rcx
0x18000ad0e  xor     edx, edx; Val
0x18000ad10  lea     rcx, [rsp+8E8h+var_888]; void *
0x18000ad15  lea     r8d, [rdx+48h]; Size
0x18000ad19  call    memset_0
0x18000ad1e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000ad25  xor     eax, eax
0x18000ad27  lea     rcx, [rsp+8E8h+var_824]; void *
0x18000ad2f  xor     edx, edx; Val
0x18000ad31  mov     [rsp+8E8h+var_828], eax
0x18000ad38  mov     r8d, 7FCh; Size
0x18000ad3e  movdqu  xmmword ptr [rsp+8E8h+var_838.Data1], xmm0
0x18000ad47  call    memset_0
0x18000ad4c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000ad53  lea     r12, RasRtrmgrTraceInfo
0x18000ad5a  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000ad61  test    al, al
0x18000ad63  jns     short loc_18000ADAF
0x18000ad65  xor     eax, eax
0x18000ad67  lea     r8, aSetipforwardro; "SetIpForwardRow"
0x18000ad6e  lea     rdx, aEnteredWs; "Entered: %ws"
0x18000ad75  mov     word ptr [rsp+8E8h+var_828], ax
0x18000ad7d  lea     rcx, [rsp+8E8h+var_828]
0x18000ad85  call    FormatRRASErrorString
0x18000ad8a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000ad91  test    al, al
0x18000ad93  jns     short loc_18000ADAF
0x18000ad95  lea     r8, [rsp+8E8h+var_828]
0x18000ad9d  mov     rdx, r12
0x18000ada0  mov     rcx, r15
0x18000ada3  call    McTemplateU0z_EventWriteTransfer
0x18000ada8  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000adaf  xor     edx, edx
0x18000adb1  lea     rsi, g_rgRtmHandlesV4
0x18000adb8  cmp     edx, 5
0x18000adbb  jnb     loc_18000B06C
0x18000adc1  mov     r8d, edx
0x18000adc4  add     r8, r8
0x18000adc7  mov     ecx, [rsi+r8*8]
0x18000adcb  cmp     [rdi+18h], ecx
0x18000adce  jz      short loc_18000ADD4
0x18000add0  inc     edx
0x18000add2  jmp     short loc_18000ADB8
0x18000add4  mov     rsi, [rsi+r8*8+8]
0x18000add9  test    rsi, rsi
0x18000addc  jz      loc_18000B06C
0x18000ade2  mov     ecx, [rdi+4]
0x18000ade5  and     ecx, [rdi]
0x18000ade7  cmp     ecx, [rdi]
0x18000ade9  jz      short loc_18000AE53
0x18000adeb  test    al, al
0x18000aded  jns     loc_18000B0B7
0x18000adf3  movzx   ecx, byte ptr [rdi+3]
0x18000adf7  xor     eax, eax
0x18000adf9  movzx   edx, byte ptr [rdi+2]
0x18000adfd  movzx   r10d, byte ptr [rdi+7]
0x18000ae02  movzx   r11d, byte ptr [rdi+6]
0x18000ae07  movzx   ebx, byte ptr [rdi+5]
0x18000ae0b  movzx   r9d, byte ptr [rdi+1]
0x18000ae10  movzx   r8d, byte ptr [rdi]
0x18000ae14  mov     [rsp+8E8h+var_8A0], r10d
0x18000ae19  mov     [rsp+8E8h+var_8A8], r11d
0x18000ae1e  mov     dword ptr [rsp+8E8h+var_8B0], ebx
0x18000ae22  mov     word ptr [rsp+8E8h+var_828], ax
0x18000ae2a  movzx   eax, byte ptr [rdi+4]
0x18000ae2e  mov     dword ptr [rsp+8E8h+var_8B8], eax
0x18000ae32  mov     [rsp+8E8h+var_8C0], ecx
0x18000ae36  lea     rcx, [rsp+8E8h+var_828]
0x18000ae3e  mov     [rsp+8E8h+var_8C8], edx
0x18000ae42  lea     rdx, aSetipforwardro_0; "SetIpForwardRow: Dest %d.%d.%d.%d and M"...
0x18000ae49  call    FormatRRASErrorString
0x18000ae4e  jmp     loc_18000B092
0x18000ae53  movzx   r8d, byte ptr [rdi]
0x18000ae57  cmp     r8d, 0E0h
0x18000ae5e  jb      short loc_18000AEA0
0x18000ae60  test    al, al
0x18000ae62  jns     loc_18000B0B7
0x18000ae68  movzx   ecx, byte ptr [rdi+2]
0x18000ae6c  lea     rdx, aSetipforwardro_3; "SetIpForwardRow: Dest %d.%d.%d.%d is in"...
0x18000ae73  movzx   r9d, byte ptr [rdi+1]
0x18000ae78  xor     eax, eax
0x18000ae7a  mov     word ptr [rsp+8E8h+var_828], ax
0x18000ae82  movzx   eax, byte ptr [rdi+3]
0x18000ae86  mov     [rsp+8E8h+var_8C0], eax
0x18000ae8a  mov     [rsp+8E8h+var_8C8], ecx
0x18000ae8e  lea     rcx, [rsp+8E8h+var_828]
0x18000ae96  call    FormatRRASErrorString
0x18000ae9b  jmp     loc_18000B092
0x18000aea0  test    rbx, rbx
0x18000aea3  jz      loc_18000AF2D
0x18000aea9  mov     rcx, rbx
0x18000aeac  call    DeleteIpForwardRow
0x18000aeb1  test    eax, eax
0x18000aeb3  jz      short loc_18000AF2D
0x18000aeb5  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000aebc  test    cl, 40h
0x18000aebf  jz      short loc_18000AF0C
0x18000aec1  xor     ecx, ecx
0x18000aec3  lea     rdx, aSetipforwardro_5; "SetIpForwardRow: Unable to delete route"...
0x18000aeca  mov     word ptr [rsp+8E8h+var_828], cx
0x18000aed2  mov     r8d, eax
0x18000aed5  lea     rcx, [rsp+8E8h+var_828]
0x18000aedd  call    FormatRRASErrorString
0x18000aee2  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000aee9  test    cl, 40h
0x18000aeec  jz      short loc_18000AF0C
0x18000aeee  lea     r8, [rsp+8E8h+var_828]
0x18000aef6  mov     rcx, r15
0x18000aef9  lea     rdx, RasRtrMgrTraceError
0x18000af00  call    McTemplateU0z_EventWriteTransfer
0x18000af05  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000af0c  test    cl, 80h
0x18000af0f  jz      short loc_18000AF23
0x18000af11  lea     r8, aLeavingSetipfo; "Leaving: SetIpForwardRow"
0x18000af18  mov     rdx, r12
0x18000af1b  mov     rcx, r15
0x18000af1e  call    McTemplateU0z_EventWriteTransfer
0x18000af23  mov     eax, 3EBh
0x18000af28  jmp     loc_18000B0D2
0x18000af2d  cmp     dword ptr [rdi+18h], 3
0x18000af31  jz      short loc_18000AF3A
0x18000af33  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x18000af3a  mov     dl, 1; Wait
0x18000af3c  lea     rcx, Resource; Resource
0x18000af43  call    cs:__imp_RtlAcquireResourceShared
0x18000af49  mov     edx, [rdi+0Ch]
0x18000af4c  mov     ecx, [rdi+10h]
0x18000af4f  call    GetBestNextHopMaskGivenIndex
0x18000af54  mov     ecx, [rdi+10h]
0x18000af57  mov     edx, 1
0x18000af5c  mov     ebx, eax
0x18000af5e  call    InterfaceLookupByIfIndex
0x18000af63  test    rax, rax
0x18000af66  jnz     short loc_18000AF94
0x18000af68  lea     rcx, Resource; Resource
0x18000af6f  call    cs:__imp_RtlReleaseResource
0x18000af75  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000af7c  test    al, al
0x18000af7e  jns     loc_18000B0B7
0x18000af84  mov     r8d, [rdi+10h]
0x18000af88  lea     rdx, aSetipforwardro_4; "SetIpForwardRow: I/f 0x%x doesnt exist"
0x18000af8f  jmp     loc_18000B07B
0x18000af94  mov     ecx, [rax+90h]
0x18000af9a  lea     eax, [rcx-1]
0x18000af9d  cmp     eax, 1
0x18000afa0  jbe     short loc_18000AFA7
0x18000afa2  cmp     ecx, 7
0x18000afa5  jnz     short loc_18000AFAE
0x18000afa7  mov     dword ptr [rdi+0Ch], 0
0x18000afae  lea     rcx, Resource; Resource
0x18000afb5  call    cs:__imp_RtlReleaseResource
0x18000afbb  lea     rdx, [rsp+8E8h+var_888]
0x18000afc0  mov     rcx, rdi
0x18000afc3  call    ConvertMibRouteToRouteInfo
0x18000afc8  mov     rdx, rax
0x18000afcb  mov     [rsp+8E8h+var_8B0], 0; __int64
0x18000afd4  lea     rax, [rsp+8E8h+var_838]
0x18000afdc  mov     r9d, ebx
0x18000afdf  mov     [rsp+8E8h+var_8B8], rax; struct _GUID *
0x18000afe4  mov     r8d, 30h ; '0'
0x18000afea  mov     eax, [rdi+1Ch]
0x18000afed  mov     rcx, rsi; RtmRegHandle
0x18000aff0  mov     [rsp+8E8h+var_8C0], 1; int
0x18000aff8  mov     [rsp+8E8h+var_8C8], eax; ULONG
0x18000affc  call    AddRtmRoute
0x18000b001  mov     ebx, eax
0x18000b003  test    eax, eax
0x18000b005  jz      short loc_18000B04D
0x18000b007  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000b00e  jge     short loc_18000B04D
0x18000b010  mov     r8d, [rdi]
0x18000b013  lea     rdx, aSetipforwardro_1; "SetIpForwardRow: Could not set route to"...
0x18000b01a  xor     ecx, ecx
0x18000b01c  mov     word ptr [rsp+8E8h+var_828], cx
0x18000b024  lea     rcx, [rsp+8E8h+var_828]
0x18000b02c  call    FormatRRASErrorString
0x18000b031  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000b038  jge     short loc_18000B04D
0x18000b03a  lea     r8, [rsp+8E8h+var_828]
0x18000b042  mov     rdx, r12
0x18000b045  mov     rcx, r15
0x18000b048  call    McTemplateU0z_EventWriteTransfer
0x18000b04d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000b054  jz      short loc_18000B068
0x18000b056  lea     r8, aLeavingSetipfo; "Leaving: SetIpForwardRow"
0x18000b05d  mov     rdx, r12
0x18000b060  mov     rcx, r15
0x18000b063  call    McTemplateU0z_EventWriteTransfer
0x18000b068  mov     eax, ebx
0x18000b06a  jmp     short loc_18000B0D2
0x18000b06c  test    al, al
0x18000b06e  jns     short loc_18000B0B7
0x18000b070  mov     r8d, [rdi+18h]
0x18000b074  lea     rdx, aSetipforwardro_2; "SetIpForwardRow: Protocol %d not valid"
0x18000b07b  xor     eax, eax
0x18000b07d  lea     rcx, [rsp+8E8h+var_828]
0x18000b085  mov     word ptr [rsp+8E8h+var_828], ax
0x18000b08d  call    FormatRRASErrorString
0x18000b092  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000b099  test    al, al
0x18000b09b  jns     short loc_18000B0B7
0x18000b09d  lea     r8, [rsp+8E8h+var_828]
0x18000b0a5  mov     rdx, r12
0x18000b0a8  mov     rcx, r15
0x18000b0ab  call    McTemplateU0z_EventWriteTransfer
0x18000b0b0  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000b0b7  test    al, 80h
0x18000b0b9  jz      short loc_18000B0CD
0x18000b0bb  lea     r8, aLeavingSetipfo; "Leaving: SetIpForwardRow"
0x18000b0c2  mov     rdx, r12
0x18000b0c5  mov     rcx, r15
0x18000b0c8  call    McTemplateU0z_EventWriteTransfer
0x18000b0cd  mov     eax, 57h ; 'W'
0x18000b0d2  mov     rcx, [rsp+8E8h+var_28]
0x18000b0da  xor     rcx, rsp; StackCookie
0x18000b0dd  call    __security_check_cookie
0x18000b0e2  lea     r11, [rsp+8E8h+var_18]
0x18000b0ea  mov     rbx, [r11+30h]
0x18000b0ee  mov     rsi, [r11+38h]
0x18000b0f2  mov     rsp, r11
0x18000b0f5  pop     r15
0x18000b0f7  pop     r12
0x18000b0f9  pop     rdi
0x18000b0fa  retn
```
