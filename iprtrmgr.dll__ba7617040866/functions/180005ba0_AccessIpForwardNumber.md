# AccessIpForwardNumber

- ea: `0x180005ba0`
- end: `0x180005d9f`
- name: `AccessIpForwardNumber`
- size: `511`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180005ba0`
- `0x18000ac60`
- `0x18000baa8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180005d5b`
- `ntdll!RtlReleaseResource` at `0x180005d5b`
- `ntdll!RtlAcquireResourceShared` at `0x180005d3c`
- `ntdll!RtlAcquireResourceShared` at `0x180005d3c`

## string_xrefs

- `0x180005c0c`: `AccessIpForwardNumber`
- `0x180005c69`: `Leaving: AccessIpForwardNumber`
- `0x180005c9b`: `Leaving: AccessIpForwardNumber`
- `0x180005d1d`: `Leaving: AccessIpForwardNumber`
- `0x180005d6a`: `Leaving: AccessIpForwardNumber`
- `0x180005cd8`: `AccessIpForwardNumber: Couldnt update IpForward Cache. Error %d`

## pseudocode

```c
__int64 __fastcall AccessIpForwardNumber(
        int a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        _DWORD *a5,
        _DWORD *a6,
        int a7)
{
  char v9; // al
  unsigned int v11; // eax
  unsigned int updated; // eax
  unsigned int v13; // ebx
  char v14; // cl
  int v15; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v16[2044]; // [rsp+34h] [rbp-844h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"Entered: %ws", L"AccessIpForwardNumber");
    v9 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v15);
      v9 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 == 1 )
  {
    v11 = *a4;
    *a4 = 12;
    if ( v11 >= 0xC )
    {
      updated = UpdateCache(1, a6);
      v13 = updated;
      if ( updated )
      {
        v14 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"AccessIpForwardNumber: Couldnt update IpForward Cache. Error %d", updated);
          v14 = Microsoft_Windows_RRASEnableBits;
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v15);
            v14 = Microsoft_Windows_RRASEnableBits;
          }
        }
        if ( v14 < 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessIpForwardNumber");
        return v13;
      }
      else
      {
        RtlAcquireResourceShared(&stru_18008C260, 1u);
        *a5 = 0;
        *a5 = 6;
        *a6 = 1;
        RtlReleaseResource(&stru_18008C260);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessIpForwardNumber");
        return 0;
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessIpForwardNumber");
      return 122;
    }
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpForwardNumber");
    return 87;
  }
}

```

## disassembly

```asm
0x180005ba0  push    rbx
0x180005ba2  push    rsi
0x180005ba3  push    rdi
0x180005ba4  push    r12
0x180005ba6  push    r14
0x180005ba8  push    r15
0x180005baa  sub     rsp, 848h
0x180005bb1  mov     rax, cs:__security_cookie
0x180005bb8  xor     rax, rsp
0x180005bbb  mov     [rsp+878h+var_48], rax
0x180005bc3  mov     rsi, [rsp+878h+arg_20]
0x180005bcb  mov     r14d, ecx
0x180005bce  mov     rdi, [rsp+878h+arg_28]
0x180005bd6  lea     rcx, [rsp+878h+var_844]; void *
0x180005bdb  xor     eax, eax
0x180005bdd  xor     edx, edx; Val
0x180005bdf  mov     r8d, 7FCh; Size
0x180005be5  mov     [rsp+878h+var_848], eax
0x180005be9  mov     rbx, r9
0x180005bec  call    memset_0
0x180005bf1  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005bf8  lea     r12, RasRtrmgrTraceInfo
0x180005bff  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005c06  test    al, al
0x180005c08  jns     short loc_180005C4B
0x180005c0a  xor     eax, eax
0x180005c0c  lea     r8, aAccessipforwar_0; "AccessIpForwardNumber"
0x180005c13  lea     rdx, aEnteredWs; "Entered: %ws"
0x180005c1a  mov     word ptr [rsp+878h+var_848], ax
0x180005c1f  lea     rcx, [rsp+878h+var_848]
0x180005c24  call    FormatRRASErrorString
0x180005c29  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005c30  test    al, al
0x180005c32  jns     short loc_180005C4B
0x180005c34  lea     r8, [rsp+878h+var_848]
0x180005c39  mov     rdx, r12
0x180005c3c  mov     rcx, r15
0x180005c3f  call    McTemplateU0z_EventWriteTransfer
0x180005c44  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005c4b  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x180005c53  jnz     short loc_180005C5F
0x180005c55  mov     eax, 32h ; '2'
0x180005c5a  jmp     loc_180005D7E
0x180005c5f  cmp     r14d, 1
0x180005c63  jz      short loc_180005C85
0x180005c65  test    al, 80h
0x180005c67  jz      short loc_180005C7B
0x180005c69  lea     r8, aLeavingAccessi_1; "Leaving: AccessIpForwardNumber"
0x180005c70  mov     rdx, r12
0x180005c73  mov     rcx, r15
0x180005c76  call    McTemplateU0z_EventWriteTransfer
0x180005c7b  mov     eax, 57h ; 'W'
0x180005c80  jmp     loc_180005D7E
0x180005c85  mov     eax, [rbx]
0x180005c87  mov     dword ptr [rbx], 0Ch
0x180005c8d  cmp     eax, 0Ch
0x180005c90  jnb     short loc_180005CB7
0x180005c92  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180005c99  jz      short loc_180005CAD
0x180005c9b  lea     r8, aLeavingAccessi_1; "Leaving: AccessIpForwardNumber"
0x180005ca2  mov     rdx, r12
0x180005ca5  mov     rcx, r15
0x180005ca8  call    McTemplateU0z_EventWriteTransfer
0x180005cad  mov     eax, 7Ah ; 'z'
0x180005cb2  jmp     loc_180005D7E
0x180005cb7  mov     rdx, rdi
0x180005cba  mov     ecx, 1
0x180005cbf  call    UpdateCache
0x180005cc4  mov     ebx, eax
0x180005cc6  test    eax, eax
0x180005cc8  jz      short loc_180005D33
0x180005cca  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005cd1  test    cl, 40h
0x180005cd4  jz      short loc_180005D18
0x180005cd6  xor     ecx, ecx
0x180005cd8  lea     rdx, aAccessipforwar; "AccessIpForwardNumber: Couldnt update I"...
0x180005cdf  mov     word ptr [rsp+878h+var_848], cx
0x180005ce4  mov     r8d, eax
0x180005ce7  lea     rcx, [rsp+878h+var_848]
0x180005cec  call    FormatRRASErrorString
0x180005cf1  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005cf8  test    cl, 40h
0x180005cfb  jz      short loc_180005D18
0x180005cfd  lea     r8, [rsp+878h+var_848]
0x180005d02  mov     rcx, r15
0x180005d05  lea     rdx, RasRtrMgrTraceError
0x180005d0c  call    McTemplateU0z_EventWriteTransfer
0x180005d11  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005d18  test    cl, 80h
0x180005d1b  jz      short loc_180005D2F
0x180005d1d  lea     r8, aLeavingAccessi_1; "Leaving: AccessIpForwardNumber"
0x180005d24  mov     rdx, r12
0x180005d27  mov     rcx, r15
0x180005d2a  call    McTemplateU0z_EventWriteTransfer
0x180005d2f  mov     eax, ebx
0x180005d31  jmp     short loc_180005D7E
0x180005d33  mov     dl, 1; Wait
0x180005d35  lea     rcx, stru_18008C260; Resource
0x180005d3c  call    cs:__imp_RtlAcquireResourceShared
0x180005d42  mov     dword ptr [rsi], 0
0x180005d48  lea     rcx, stru_18008C260; Resource
0x180005d4f  mov     dword ptr [rsi], 6
0x180005d55  mov     dword ptr [rdi], 1
0x180005d5b  call    cs:__imp_RtlReleaseResource
0x180005d61  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180005d68  jz      short loc_180005D7C
0x180005d6a  lea     r8, aLeavingAccessi_1; "Leaving: AccessIpForwardNumber"
0x180005d71  mov     rdx, r12
0x180005d74  mov     rcx, r15
0x180005d77  call    McTemplateU0z_EventWriteTransfer
0x180005d7c  xor     eax, eax
0x180005d7e  mov     rcx, [rsp+878h+var_48]
0x180005d86  xor     rcx, rsp; StackCookie
0x180005d89  call    __security_check_cookie
0x180005d8e  add     rsp, 848h
0x180005d95  pop     r15
0x180005d97  pop     r14
0x180005d99  pop     r12
0x180005d9b  pop     rdi
0x180005d9c  pop     rsi
0x180005d9d  pop     rbx
0x180005d9e  retn
```
