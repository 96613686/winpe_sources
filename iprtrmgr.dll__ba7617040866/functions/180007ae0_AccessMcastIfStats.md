# AccessMcastIfStats

- ea: `0x180007ae0`
- end: `0x180007d01`
- name: `AccessMcastIfStats`
- size: `545`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180007ae0`
- `0x18000ac60`
- `0x18002e558`
- `0x180036a90`
- `0x180037564`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180007bf6`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007bf6`
- `ntdll!RtlReleaseResource` at `0x180007ca3`
- `ntdll!RtlReleaseResource` at `0x180007ca3`
- `ntdll!RtlAcquireResourceShared` at `0x180007bfe`
- `ntdll!RtlAcquireResourceShared` at `0x180007bfe`

## string_xrefs

- `0x180007c44`: `AccessIfRow: Wrong query type %d`
- `0x180007b56`: `AccessMcastIfTable`
- `0x180007bbd`: `Leaving: AccessMcastIfTable`
- `0x180007cba`: `Leaving: AccessMcastIfTable`

## pseudocode

```c
__int64 __fastcall AccessMcastIfStats(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        _DWORD *a5,
        _DWORD *a6,
        int a7)
{
  unsigned int v12; // eax
  unsigned int v13; // ebx
  _DWORD *v14; // rdx
  unsigned int InterfaceMcastStatistics; // eax
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v16 = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"Entered: %ws", L"AccessMcastIfTable");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
  }
  if ( a7 == 87 )
    return 50;
  v12 = *a4;
  *a4 = 32;
  if ( v12 < 0x20 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessMcastIfTable");
    return 122;
  }
  *a5 = 23;
  if ( a1 == 5 )
    RtlAcquireResourceExclusive(&Resource, 1u);
  else
    RtlAcquireResourceShared(&Resource, 1u);
  v13 = LocateIfRow(a1, (a2 >> 2) - 1, a3 + 4, &v16);
  if ( !v13 )
  {
    v14 = a5 + 2;
    if ( a1 == 1 || a1 == 2 || a1 == 4 )
    {
      InterfaceMcastStatistics = GetInterfaceMcastStatistics(v16, v14);
    }
    else
    {
      if ( a1 != 5 )
      {
        if ( (char)Microsoft_Windows_RRASEnableBits < (char)v13 )
        {
          LOWORD(v17) = 0;
          FormatRRASErrorString(&v17, L"AccessIfRow: Wrong query type %d", a1);
          if ( (char)Microsoft_Windows_RRASEnableBits < (char)v13 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v17);
        }
        v13 = 87;
        goto LABEL_25;
      }
      InterfaceMcastStatistics = SetInterfaceMcastStatistics(v16, v14);
    }
    v13 = InterfaceMcastStatistics;
  }
LABEL_25:
  RtlReleaseResource(&Resource);
  *a6 = 1;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessMcastIfTable");
  return v13;
}

```

## disassembly

```asm
0x180007ae0  mov     [rsp-8+arg_8], rbx
0x180007ae5  mov     [rsp-8+arg_10], rsi
0x180007aea  push    rbp
0x180007aeb  push    rdi
0x180007aec  push    r12
0x180007aee  push    r14
0x180007af0  push    r15
0x180007af2  lea     rbp, [rsp-750h]
0x180007afa  sub     rsp, 850h
0x180007b01  mov     rax, cs:__security_cookie
0x180007b08  xor     rax, rsp
0x180007b0b  mov     [rbp+770h+var_30], rax
0x180007b12  mov     r14, [rbp+770h+arg_20]
0x180007b19  mov     r15, r8
0x180007b1c  mov     r12, [rbp+770h+arg_28]
0x180007b23  mov     ebx, edx
0x180007b25  mov     edi, ecx
0x180007b27  mov     [rsp+870h+var_840], 0
0x180007b30  xor     eax, eax
0x180007b32  lea     rcx, [rsp+870h+var_82C]; void *
0x180007b37  xor     edx, edx; Val
0x180007b39  mov     [rsp+870h+var_830], eax
0x180007b3d  mov     r8d, 7FCh; Size
0x180007b43  mov     rsi, r9
0x180007b46  call    memset_0
0x180007b4b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007b52  jge     short loc_180007B94
0x180007b54  xor     eax, eax
0x180007b56  lea     r8, aAccessmcastift; "AccessMcastIfTable"
0x180007b5d  lea     rdx, aEnteredWs; "Entered: %ws"
0x180007b64  mov     word ptr [rsp+870h+var_830], ax
0x180007b69  lea     rcx, [rsp+870h+var_830]
0x180007b6e  call    FormatRRASErrorString
0x180007b73  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007b7a  jge     short loc_180007B94
0x180007b7c  lea     r8, [rsp+870h+var_830]
0x180007b81  lea     rdx, RasRtrmgrTraceInfo
0x180007b88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007b8f  call    McTemplateU0z_EventWriteTransfer
0x180007b94  cmp     [rbp+770h+arg_30], 57h ; 'W'
0x180007b9b  jnz     short loc_180007BA7
0x180007b9d  mov     eax, 32h ; '2'
0x180007ba2  jmp     loc_180007CD6
0x180007ba7  mov     eax, [rsi]
0x180007ba9  mov     dword ptr [rsi], 20h ; ' '
0x180007baf  cmp     eax, 20h ; ' '
0x180007bb2  jnb     short loc_180007BE1
0x180007bb4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180007bbb  jz      short loc_180007BD7
0x180007bbd  lea     r8, aLeavingAccessm_3; "Leaving: AccessMcastIfTable"
0x180007bc4  lea     rdx, RasRtrmgrTraceInfo
0x180007bcb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007bd2  call    McTemplateU0z_EventWriteTransfer
0x180007bd7  mov     eax, 7Ah ; 'z'
0x180007bdc  jmp     loc_180007CD6
0x180007be1  mov     dword ptr [r14], 17h
0x180007be8  mov     dl, 1; Wait
0x180007bea  lea     rcx, Resource; Resource
0x180007bf1  cmp     edi, 5
0x180007bf4  jnz     short loc_180007BFE
0x180007bf6  call    cs:__imp_RtlAcquireResourceExclusive
0x180007bfc  jmp     short loc_180007C04
0x180007bfe  call    cs:__imp_RtlAcquireResourceShared
0x180007c04  shr     ebx, 2
0x180007c07  lea     r8, [r15+4]
0x180007c0b  lea     r9, [rsp+870h+var_840]
0x180007c10  mov     ecx, edi
0x180007c12  lea     edx, [rbx-1]
0x180007c15  call    LocateIfRow
0x180007c1a  mov     ebx, eax
0x180007c1c  test    eax, eax
0x180007c1e  jnz     short loc_180007C9C
0x180007c20  mov     eax, edi
0x180007c22  lea     rdx, [r14+8]
0x180007c26  sub     eax, 1
0x180007c29  jz      short loc_180007C90
0x180007c2b  sub     eax, 1
0x180007c2e  jz      short loc_180007C90
0x180007c30  sub     eax, 2
0x180007c33  jz      short loc_180007C90
0x180007c35  cmp     eax, 1
0x180007c38  jz      short loc_180007C84
0x180007c3a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180007c40  jge     short loc_180007C7D
0x180007c42  xor     eax, eax
0x180007c44  lea     rdx, aAccessifrowWro; "AccessIfRow: Wrong query type %d"
0x180007c4b  mov     r8d, edi
0x180007c4e  mov     word ptr [rsp+870h+var_830], ax
0x180007c53  lea     rcx, [rsp+870h+var_830]
0x180007c58  call    FormatRRASErrorString
0x180007c5d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180007c63  jge     short loc_180007C7D
0x180007c65  lea     r8, [rsp+870h+var_830]
0x180007c6a  lea     rdx, RasRtrmgrTraceInfo
0x180007c71  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007c78  call    McTemplateU0z_EventWriteTransfer
0x180007c7d  mov     ebx, 57h ; 'W'
0x180007c82  jmp     short loc_180007C9C
0x180007c84  mov     rcx, [rsp+870h+var_840]
0x180007c89  call    SetInterfaceMcastStatistics
0x180007c8e  jmp     short loc_180007C9A
0x180007c90  mov     rcx, [rsp+870h+var_840]
0x180007c95  call    GetInterfaceMcastStatistics
0x180007c9a  mov     ebx, eax
0x180007c9c  lea     rcx, Resource; Resource
0x180007ca3  call    cs:__imp_RtlReleaseResource
0x180007ca9  mov     dword ptr [r12], 1
0x180007cb1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180007cb8  jz      short loc_180007CD4
0x180007cba  lea     r8, aLeavingAccessm_3; "Leaving: AccessMcastIfTable"
0x180007cc1  lea     rdx, RasRtrmgrTraceInfo
0x180007cc8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007ccf  call    McTemplateU0z_EventWriteTransfer
0x180007cd4  mov     eax, ebx
0x180007cd6  mov     rcx, [rbp+770h+var_30]
0x180007cdd  xor     rcx, rsp; StackCookie
0x180007ce0  call    __security_check_cookie
0x180007ce5  lea     r11, [rsp+870h+var_20]
0x180007ced  mov     rbx, [r11+38h]
0x180007cf1  mov     rsi, [r11+40h]
0x180007cf5  mov     rsp, r11
0x180007cf8  pop     r15
0x180007cfa  pop     r14
0x180007cfc  pop     r12
0x180007cfe  pop     rdi
0x180007cff  pop     rbp
0x180007d00  retn
```
