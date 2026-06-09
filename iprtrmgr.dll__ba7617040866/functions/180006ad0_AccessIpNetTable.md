# AccessIpNetTable

- ea: `0x180006ad0`
- end: `0x180006e02`
- name: `AccessIpNetTable`
- size: `818`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180006ad0`
- `0x18000ac60`
- `0x18000baa8`
- `0x18002f000`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180006c08`
- `ntdll!RtlReleaseResource` at `0x180006c20`
- `ntdll!RtlReleaseResource` at `0x180006dae`
- `ntdll!RtlReleaseResource` at `0x180006c08`
- `ntdll!RtlReleaseResource` at `0x180006c20`
- `ntdll!RtlReleaseResource` at `0x180006dae`
- `ntdll!RtlAcquireResourceShared` at `0x180006be2`
- `ntdll!RtlAcquireResourceShared` at `0x180006cc1`
- `ntdll!RtlAcquireResourceShared` at `0x180006be2`
- `ntdll!RtlAcquireResourceShared` at `0x180006cc1`
- `IPHLPAPI!FlushIpNetTable` at `0x180006c10`
- `IPHLPAPI!FlushIpNetTable` at `0x180006c10`

## string_xrefs

- `0x180006b43`: `AccessIpNetTable`
- `0x180006bb2`: `Leaving: AccessIpNetTable`
- `0x180006c2f`: `Leaving: AccessIpNetTable`
- `0x180006dbd`: `Leaving: AccessIpNetTable`
- `0x180006c70`: `AccessIpNetTable: Couldnt update IpNet Cache. Error %d`

## pseudocode

```c
__int64 __fastcall AccessIpNetTable(int a1, unsigned int a2, __int64 a3, _DWORD *a4, _DWORD *a5, __int64 a6, int a7)
{
  char v11; // al
  unsigned int v13; // ebx
  __int64 v14; // rax
  DWORD v15; // ebx
  DWORD v16; // ebx
  DWORD updated; // eax
  char v18; // cl
  bool v19; // zf
  __int64 v20; // rdx
  __int64 v21; // r8
  char *v22; // rdx
  int i; // eax
  __int64 v24; // rcx
  int v25; // [rsp+30h] [rbp-838h] BYREF
  _BYTE v26[2044]; // [rsp+34h] [rbp-834h] BYREF

  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"Entered: %ws", L"AccessIpNetTable");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v25);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 == 1 )
  {
    updated = UpdateCache(3, a6);
    v16 = updated;
    if ( updated )
    {
      v18 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, L"AccessIpNetTable: Couldnt update IpNet Cache. Error %d", updated);
        v18 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v25);
          v18 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v19 = v18 >= 0;
      goto LABEL_38;
    }
    RtlAcquireResourceShared(&stru_18008C320, 1u);
    if ( qword_18008C7F0 && (v20 = *(unsigned int *)qword_18008C7F0, (_DWORD)v20) )
    {
      if ( (unsigned int)*a4 >= (unsigned __int64)(24 * v20 + 20) )
      {
        *a5 = 9;
        v21 = 0;
        *a4 = 24 * *(_DWORD *)qword_18008C7F0 + 20;
        v22 = (char *)qword_18008C7F0;
        for ( i = *(_DWORD *)qword_18008C7F0; (unsigned int)v21 < *(_DWORD *)qword_18008C7F0; i = *(_DWORD *)qword_18008C7F0 )
        {
          v24 = 3 * v21;
          v21 = (unsigned int)(v21 + 1);
          *(_OWORD *)&a5[2 * v24 + 3] = *(_OWORD *)&v22[8 * v24 + 4];
          *(_QWORD *)&a5[2 * v24 + 7] = *(_QWORD *)&v22[8 * v24 + 20];
          v22 = (char *)qword_18008C7F0;
        }
        a5[2] = i;
        v16 = 0;
      }
      else
      {
        v16 = 122;
        *a4 = 24 * v20 + 20;
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"No valid entries found");
      if ( *a4 >= 0x24u )
      {
        *a5 = 9;
        v16 = 0;
        a5[2] = 0;
      }
      else
      {
        v16 = 122;
      }
      *a4 = 36;
    }
    RtlReleaseResource(&stru_18008C320);
LABEL_37:
    v19 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
LABEL_38:
    if ( !v19 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpNetTable");
    return v16;
  }
  if ( a1 != 9 || a2 < 8 )
  {
    if ( v11 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpNetTable");
    return 87;
  }
  v13 = *(_DWORD *)(a3 + 4);
  RtlAcquireResourceShared(&Resource, 1u);
  v14 = InterfaceLookupByIfIndex(v13, 1);
  if ( v14 && *(_DWORD *)(v14 + 512) )
  {
    v15 = *(_DWORD *)(v14 + 16);
    RtlReleaseResource(&Resource);
    v16 = FlushIpNetTable(v15);
    goto LABEL_37;
  }
  RtlReleaseResource(&Resource);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessIpNetTable");
  return 1413;
}

```

## disassembly

```asm
0x180006ad0  mov     [rsp+arg_0], rbx
0x180006ad5  mov     [rsp+arg_8], rsi
0x180006ada  push    rdi
0x180006adb  push    r12
0x180006add  push    r13
0x180006adf  push    r14
0x180006ae1  push    r15
0x180006ae3  sub     rsp, 840h
0x180006aea  mov     rax, cs:__security_cookie
0x180006af1  xor     rax, rsp
0x180006af4  mov     [rsp+868h+var_38], rax
0x180006afc  mov     rsi, [rsp+868h+arg_20]
0x180006b04  mov     r13, r8
0x180006b07  mov     r15, [rsp+868h+arg_28]
0x180006b0f  mov     r14d, edx
0x180006b12  mov     ebx, ecx
0x180006b14  xor     eax, eax
0x180006b16  xor     edx, edx; Val
0x180006b18  mov     [rsp+868h+var_838], eax
0x180006b1c  mov     r8d, 7FCh; Size
0x180006b22  lea     rcx, [rsp+868h+var_834]; void *
0x180006b27  mov     rdi, r9
0x180006b2a  call    memset_0
0x180006b2f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180006b36  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006b3d  test    al, al
0x180006b3f  jns     short loc_180006B86
0x180006b41  xor     eax, eax
0x180006b43  lea     r8, aAccessipnettab; "AccessIpNetTable"
0x180006b4a  lea     rdx, aEnteredWs; "Entered: %ws"
0x180006b51  mov     word ptr [rsp+868h+var_838], ax
0x180006b56  lea     rcx, [rsp+868h+var_838]
0x180006b5b  call    FormatRRASErrorString
0x180006b60  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180006b67  test    al, al
0x180006b69  jns     short loc_180006B86
0x180006b6b  lea     r8, [rsp+868h+var_838]
0x180006b70  mov     rcx, r12
0x180006b73  lea     rdx, RasRtrmgrTraceInfo
0x180006b7a  call    McTemplateU0z_EventWriteTransfer
0x180006b7f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180006b86  cmp     [rsp+868h+arg_30], 57h ; 'W'
0x180006b8e  jnz     short loc_180006B9A
0x180006b90  mov     eax, 32h ; '2'
0x180006b95  jmp     loc_180006DD5
0x180006b9a  cmp     ebx, 1
0x180006b9d  jz      loc_180006C4F
0x180006ba3  cmp     ebx, 9
0x180006ba6  jnz     short loc_180006BAE
0x180006ba8  cmp     r14d, 8
0x180006bac  jnb     short loc_180006BD2
0x180006bae  test    al, 80h
0x180006bb0  jz      short loc_180006BC8
0x180006bb2  lea     r8, aLeavingAccessi_12; "Leaving: AccessIpNetTable"
0x180006bb9  mov     rcx, r12
0x180006bbc  lea     rdx, RasRtrmgrTraceInfo
0x180006bc3  call    McTemplateU0z_EventWriteTransfer
0x180006bc8  mov     eax, 57h ; 'W'
0x180006bcd  jmp     loc_180006DD5
0x180006bd2  mov     ebx, [r13+4]
0x180006bd6  lea     rdi, Resource
0x180006bdd  mov     rcx, rdi; Resource
0x180006be0  mov     dl, 1; Wait
0x180006be2  call    cs:__imp_RtlAcquireResourceShared
0x180006be8  mov     edx, 1
0x180006bed  mov     ecx, ebx
0x180006bef  call    InterfaceLookupByIfIndex
0x180006bf4  test    rax, rax
0x180006bf7  jz      short loc_180006C1D
0x180006bf9  cmp     dword ptr [rax+200h], 0
0x180006c00  jz      short loc_180006C1D
0x180006c02  mov     ebx, [rax+10h]
0x180006c05  mov     rcx, rdi; Resource
0x180006c08  call    cs:__imp_RtlReleaseResource
0x180006c0e  mov     ecx, ebx; dwIfIndex
0x180006c10  call    cs:__imp_FlushIpNetTable
0x180006c16  mov     ebx, eax
0x180006c18  jmp     loc_180006DB4
0x180006c1d  mov     rcx, rdi; Resource
0x180006c20  call    cs:__imp_RtlReleaseResource
0x180006c26  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006c2d  jz      short loc_180006C45
0x180006c2f  lea     r8, aLeavingAccessi_12; "Leaving: AccessIpNetTable"
0x180006c36  mov     rcx, r12
0x180006c39  lea     rdx, RasRtrmgrTraceInfo
0x180006c40  call    McTemplateU0z_EventWriteTransfer
0x180006c45  mov     eax, 585h
0x180006c4a  jmp     loc_180006DD5
0x180006c4f  mov     rdx, r15
0x180006c52  mov     ecx, 3
0x180006c57  call    UpdateCache
0x180006c5c  mov     ebx, eax
0x180006c5e  test    eax, eax
0x180006c60  jz      short loc_180006CB8
0x180006c62  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180006c69  test    cl, 40h
0x180006c6c  jz      short loc_180006CB0
0x180006c6e  xor     ecx, ecx
0x180006c70  lea     rdx, aAccessipnettab_0; "AccessIpNetTable: Couldnt update IpNet "...
0x180006c77  mov     word ptr [rsp+868h+var_838], cx
0x180006c7c  mov     r8d, eax
0x180006c7f  lea     rcx, [rsp+868h+var_838]
0x180006c84  call    FormatRRASErrorString
0x180006c89  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180006c90  test    cl, 40h
0x180006c93  jz      short loc_180006CB0
0x180006c95  lea     r8, [rsp+868h+var_838]
0x180006c9a  mov     rcx, r12
0x180006c9d  lea     rdx, RasRtrMgrTraceError
0x180006ca4  call    McTemplateU0z_EventWriteTransfer
0x180006ca9  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180006cb0  test    cl, 80h
0x180006cb3  jmp     loc_180006DBB
0x180006cb8  mov     dl, 1; Wait
0x180006cba  lea     rcx, stru_18008C320; Resource
0x180006cc1  call    cs:__imp_RtlAcquireResourceShared
0x180006cc7  mov     rdx, cs:qword_18008C7F0
0x180006cce  test    rdx, rdx
0x180006cd1  jz      loc_180006D67
0x180006cd7  mov     edx, [rdx]
0x180006cd9  test    edx, edx
0x180006cdb  jz      loc_180006D67
0x180006ce1  mov     eax, [rdi]
0x180006ce3  lea     rcx, [rdx+rdx*2]
0x180006ce7  lea     rcx, ds:14h[rcx*8]
0x180006cef  cmp     rax, rcx
0x180006cf2  jnb     short loc_180006D0A
0x180006cf4  lea     eax, [rdx+rdx*2]
0x180006cf7  mov     ebx, 7Ah ; 'z'
0x180006cfc  lea     eax, ds:14h[rax*8]
0x180006d03  mov     [rdi], eax
0x180006d05  jmp     loc_180006DA7
0x180006d0a  mov     dword ptr [rsi], 9
0x180006d10  xor     r8d, r8d
0x180006d13  mov     rax, cs:qword_18008C7F0
0x180006d1a  mov     ecx, [rax]
0x180006d1c  lea     eax, [rcx+rcx*2]
0x180006d1f  lea     eax, ds:14h[rax*8]
0x180006d26  mov     [rdi], eax
0x180006d28  mov     rdx, cs:qword_18008C7F0
0x180006d2f  mov     eax, [rdx]
0x180006d31  test    eax, eax
0x180006d33  jz      short loc_180006D60
0x180006d35  lea     rcx, [r8+r8*2]
0x180006d39  inc     r8d
0x180006d3c  movups  xmm0, xmmword ptr [rdx+rcx*8+4]
0x180006d41  movups  xmmword ptr [rsi+rcx*8+0Ch], xmm0
0x180006d46  movsd   xmm1, qword ptr [rdx+rcx*8+14h]
0x180006d4c  movsd   qword ptr [rsi+rcx*8+1Ch], xmm1
0x180006d52  mov     rdx, cs:qword_18008C7F0
0x180006d59  mov     eax, [rdx]
0x180006d5b  cmp     r8d, eax
0x180006d5e  jb      short loc_180006D35
0x180006d60  mov     [rsi+8], eax
0x180006d63  xor     ebx, ebx
0x180006d65  jmp     short loc_180006DA7
0x180006d67  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006d6e  jz      short loc_180006D86
0x180006d70  lea     r8, aNoValidEntries; "No valid entries found"
0x180006d77  mov     rcx, r12
0x180006d7a  lea     rdx, RasRtrmgrTraceInfo
0x180006d81  call    McTemplateU0z_EventWriteTransfer
0x180006d86  cmp     dword ptr [rdi], 24h ; '$'
0x180006d89  jnb     short loc_180006D92
0x180006d8b  mov     ebx, 7Ah ; 'z'
0x180006d90  jmp     short loc_180006DA1
0x180006d92  mov     dword ptr [rsi], 9
0x180006d98  xor     ebx, ebx
0x180006d9a  mov     dword ptr [rsi+8], 0
0x180006da1  mov     dword ptr [rdi], 24h ; '$'
0x180006da7  lea     rcx, stru_18008C320; Resource
0x180006dae  call    cs:__imp_RtlReleaseResource
0x180006db4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006dbb  jz      short loc_180006DD3
0x180006dbd  lea     r8, aLeavingAccessi_12; "Leaving: AccessIpNetTable"
0x180006dc4  mov     rcx, r12
0x180006dc7  lea     rdx, RasRtrmgrTraceInfo
0x180006dce  call    McTemplateU0z_EventWriteTransfer
0x180006dd3  mov     eax, ebx
0x180006dd5  mov     rcx, [rsp+868h+var_38]
0x180006ddd  xor     rcx, rsp; StackCookie
0x180006de0  call    __security_check_cookie
0x180006de5  lea     r11, [rsp+868h+var_28]
0x180006ded  mov     rbx, [r11+30h]
0x180006df1  mov     rsi, [r11+38h]
0x180006df5  mov     rsp, r11
0x180006df8  pop     r15
0x180006dfa  pop     r14
0x180006dfc  pop     r13
0x180006dfe  pop     r12
0x180006e00  pop     rdi
0x180006e01  retn
```
