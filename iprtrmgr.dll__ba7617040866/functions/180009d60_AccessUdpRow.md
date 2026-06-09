# AccessUdpRow

- ea: `0x180009d60`
- end: `0x180009f62`
- name: `AccessUdpRow`
- size: `514`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180009d60`
- `0x18000ac60`
- `0x18000baa8`
- `0x18002ea88`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180009f0f`
- `ntdll!RtlReleaseResource` at `0x180009f0f`
- `ntdll!RtlAcquireResourceShared` at `0x180009ed1`
- `ntdll!RtlAcquireResourceShared` at `0x180009ed1`

## string_xrefs

- `0x180009dcc`: `AccessUdpRow`
- `0x180009e34`: `Leaving: AccessUdpRow`
- `0x180009f1e`: `Leaving: AccessUdpRow`
- `0x180009e7f`: `AccessUdpRow: Couldnt update Udp Cache. Error %d`

## pseudocode

```c
__int64 __fastcall AccessUdpRow(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  unsigned int v12; // eax
  unsigned int updated; // eax
  unsigned int UdpRow; // ebx
  char v15; // cl
  bool v16; // zf
  _DWORD v17[4]; // [rsp+20h] [rbp-848h] BYREF
  int v18; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v19[2044]; // [rsp+34h] [rbp-834h] BYREF

  v17[0] = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Entered: %ws", L"AccessUdpRow");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v18);
  }
  if ( a7 == 87 )
    return 50;
  v12 = *a4;
  *a4 = 16;
  if ( v12 >= 0x10 )
  {
    *(_DWORD *)a5 = 17;
    updated = UpdateCache(5, a6);
    UdpRow = updated;
    if ( updated )
    {
      v15 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v18, L"AccessUdpRow: Couldnt update Udp Cache. Error %d", updated);
        v15 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v18);
          v15 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v16 = v15 >= 0;
    }
    else
    {
      RtlAcquireResourceShared(&stru_18008C3E0, 1u);
      UdpRow = LocateUdpRow(a1, (a2 >> 2) - 1, a3 + 4, v17);
      if ( !UdpRow )
        *(_QWORD *)(a5 + 8) = *(_QWORD *)((char *)g_UdpInfo + 8 * v17[0] + 4);
      RtlReleaseResource(&stru_18008C3E0);
      v16 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    }
    if ( !v16 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessUdpRow");
    return UdpRow;
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessUdpRow");
    return 122;
  }
}

```

## disassembly

```asm
0x180009d60  mov     [rsp+arg_0], rbx
0x180009d65  push    rsi
0x180009d66  push    rdi
0x180009d67  push    r13
0x180009d69  push    r14
0x180009d6b  push    r15
0x180009d6d  sub     rsp, 840h
0x180009d74  mov     rax, cs:__security_cookie
0x180009d7b  xor     rax, rsp
0x180009d7e  mov     [rsp+868h+var_38], rax
0x180009d86  mov     rsi, [rsp+868h+arg_20]
0x180009d8e  mov     r13, r8
0x180009d91  mov     r14, [rsp+868h+arg_28]
0x180009d99  mov     edi, edx
0x180009d9b  mov     r15d, ecx
0x180009d9e  mov     [rsp+868h+var_848], 0
0x180009da6  xor     eax, eax
0x180009da8  lea     rcx, [rsp+868h+var_834]; void *
0x180009dad  xor     edx, edx; Val
0x180009daf  mov     [rsp+868h+var_838], eax
0x180009db3  mov     r8d, 7FCh; Size
0x180009db9  mov     rbx, r9
0x180009dbc  call    memset_0
0x180009dc1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180009dc8  jge     short loc_180009E0A
0x180009dca  xor     eax, eax
0x180009dcc  lea     r8, aAccessudprow; "AccessUdpRow"
0x180009dd3  lea     rdx, aEnteredWs; "Entered: %ws"
0x180009dda  mov     word ptr [rsp+868h+var_838], ax
0x180009ddf  lea     rcx, [rsp+868h+var_838]
0x180009de4  call    FormatRRASErrorString
0x180009de9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180009df0  jge     short loc_180009E0A
0x180009df2  lea     r8, [rsp+868h+var_838]
0x180009df7  lea     rdx, RasRtrmgrTraceInfo
0x180009dfe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009e05  call    McTemplateU0z_EventWriteTransfer
0x180009e0a  cmp     [rsp+868h+arg_30], 57h ; 'W'
0x180009e12  jnz     short loc_180009E1E
0x180009e14  mov     eax, 32h ; '2'
0x180009e19  jmp     loc_180009F3A
0x180009e1e  mov     eax, [rbx]
0x180009e20  mov     dword ptr [rbx], 10h
0x180009e26  cmp     eax, 10h
0x180009e29  jnb     short loc_180009E58
0x180009e2b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009e32  jz      short loc_180009E4E
0x180009e34  lea     r8, aLeavingAccessu_1; "Leaving: AccessUdpRow"
0x180009e3b  lea     rdx, RasRtrmgrTraceInfo
0x180009e42  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009e49  call    McTemplateU0z_EventWriteTransfer
0x180009e4e  mov     eax, 7Ah ; 'z'
0x180009e53  jmp     loc_180009F3A
0x180009e58  mov     rdx, r14
0x180009e5b  mov     dword ptr [rsi], 11h
0x180009e61  mov     ecx, 5
0x180009e66  call    UpdateCache
0x180009e6b  mov     ebx, eax
0x180009e6d  test    eax, eax
0x180009e6f  jz      short loc_180009EC8
0x180009e71  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180009e78  test    cl, 40h
0x180009e7b  jz      short loc_180009EC3
0x180009e7d  xor     ecx, ecx
0x180009e7f  lea     rdx, aAccessudprowCo; "AccessUdpRow: Couldnt update Udp Cache."...
0x180009e86  mov     word ptr [rsp+868h+var_838], cx
0x180009e8b  mov     r8d, eax
0x180009e8e  lea     rcx, [rsp+868h+var_838]
0x180009e93  call    FormatRRASErrorString
0x180009e98  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180009e9f  test    cl, 40h
0x180009ea2  jz      short loc_180009EC3
0x180009ea4  lea     r8, [rsp+868h+var_838]
0x180009ea9  lea     rdx, RasRtrMgrTraceError
0x180009eb0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009eb7  call    McTemplateU0z_EventWriteTransfer
0x180009ebc  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180009ec3  test    cl, 80h
0x180009ec6  jmp     short loc_180009F1C
0x180009ec8  mov     dl, 1; Wait
0x180009eca  lea     rcx, stru_18008C3E0; Resource
0x180009ed1  call    cs:__imp_RtlAcquireResourceShared
0x180009ed7  shr     edi, 2
0x180009eda  lea     r8, [r13+4]
0x180009ede  lea     r9, [rsp+868h+var_848]
0x180009ee3  mov     ecx, r15d
0x180009ee6  lea     edx, [rdi-1]
0x180009ee9  call    LocateUdpRow
0x180009eee  mov     ebx, eax
0x180009ef0  test    eax, eax
0x180009ef2  jnz     short loc_180009F08
0x180009ef4  mov     edx, [rsp+868h+var_848]
0x180009ef8  mov     rax, cs:g_UdpInfo
0x180009eff  mov     rdx, [rax+rdx*8+4]
0x180009f04  mov     [rsi+8], rdx
0x180009f08  lea     rcx, stru_18008C3E0; Resource
0x180009f0f  call    cs:__imp_RtlReleaseResource
0x180009f15  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009f1c  jz      short loc_180009F38
0x180009f1e  lea     r8, aLeavingAccessu_1; "Leaving: AccessUdpRow"
0x180009f25  lea     rdx, RasRtrmgrTraceInfo
0x180009f2c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009f33  call    McTemplateU0z_EventWriteTransfer
0x180009f38  mov     eax, ebx
0x180009f3a  mov     rcx, [rsp+868h+var_38]
0x180009f42  xor     rcx, rsp; StackCookie
0x180009f45  call    __security_check_cookie
0x180009f4a  mov     rbx, [rsp+868h+arg_0]
0x180009f52  add     rsp, 840h
0x180009f59  pop     r15
0x180009f5b  pop     r14
0x180009f5d  pop     r13
0x180009f5f  pop     rdi
0x180009f60  pop     rsi
0x180009f61  retn
```
