# AccessIpAddrTable

- ea: `0x180005910`
- end: `0x180005b8f`
- name: `AccessIpAddrTable`
- size: `639`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180005910`
- `0x18000ac60`
- `0x18000baa8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180005b4b`
- `ntdll!RtlReleaseResource` at `0x180005b4b`
- `ntdll!RtlAcquireResourceShared` at `0x180005a62`
- `ntdll!RtlAcquireResourceShared` at `0x180005a62`

## string_xrefs

- `0x18000597b`: `AccessIpAddrTable`
- `0x1800059d7`: `Leaving: AccessIpAddrTable`
- `0x180005b5a`: `Leaving: AccessIpAddrTable`
- `0x180005a11`: `AccessIpAddrTable: Error %d updating IpAddr Cache`

## pseudocode

```c
__int64 __fastcall AccessIpAddrTable(int a1, __int64 a2, __int64 a3, _DWORD *a4, _DWORD *a5, __int64 a6, int a7)
{
  char v9; // al
  unsigned int updated; // eax
  unsigned int v12; // ebx
  char v13; // cl
  bool v14; // zf
  __int64 v15; // rdx
  __int64 v16; // r8
  char *v17; // rdx
  int i; // eax
  __int64 v19; // rcx
  int v20; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v21[2044]; // [rsp+34h] [rbp-844h] BYREF

  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    FormatRRASErrorString(&v20, L"Entered: %ws", L"AccessIpAddrTable");
    v9 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v20);
      v9 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  if ( a1 == 1 )
  {
    updated = UpdateCache(0, a6);
    v12 = updated;
    if ( updated )
    {
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"AccessIpAddrTable: Error %d updating IpAddr Cache", updated);
        v13 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v20);
          v13 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v14 = v13 >= 0;
    }
    else
    {
      RtlAcquireResourceShared(&g_LockTable, 1u);
      if ( g_IpInfo && (v15 = *(unsigned int *)g_IpInfo, (_DWORD)v15) )
      {
        if ( (unsigned int)*a4 >= (unsigned __int64)(24 * v15 + 20) )
        {
          *a5 = 4;
          v16 = 0;
          *a4 = 24 * *(_DWORD *)g_IpInfo + 20;
          v17 = (char *)g_IpInfo;
          for ( i = *(_DWORD *)g_IpInfo; (unsigned int)v16 < *(_DWORD *)g_IpInfo; i = *(_DWORD *)g_IpInfo )
          {
            v19 = 3 * v16;
            v16 = (unsigned int)(v16 + 1);
            *(_OWORD *)&a5[2 * v19 + 3] = *(_OWORD *)&v17[8 * v19 + 4];
            *(_QWORD *)&a5[2 * v19 + 7] = *(_QWORD *)&v17[8 * v19 + 20];
            v17 = (char *)g_IpInfo;
          }
          a5[2] = i;
          v12 = 0;
        }
        else
        {
          v12 = 122;
          *a4 = 24 * v15 + 20;
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
          *a5 = 4;
          v12 = 0;
          a5[2] = 0;
        }
        else
        {
          v12 = 122;
        }
        *a4 = 36;
      }
      RtlReleaseResource(&g_LockTable);
      v14 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    }
    if ( !v14 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpAddrTable");
    return v12;
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpAddrTable");
    return 87;
  }
}

```

## disassembly

```asm
0x180005910  push    rbx
0x180005912  push    rsi
0x180005913  push    rdi
0x180005914  push    r12
0x180005916  push    r14
0x180005918  push    r15
0x18000591a  sub     rsp, 848h
0x180005921  mov     rax, cs:__security_cookie
0x180005928  xor     rax, rsp
0x18000592b  mov     [rsp+878h+var_48], rax
0x180005933  mov     rsi, [rsp+878h+arg_20]
0x18000593b  mov     ebx, ecx
0x18000593d  mov     r14, [rsp+878h+arg_28]
0x180005945  lea     rcx, [rsp+878h+var_844]; void *
0x18000594a  xor     eax, eax
0x18000594c  xor     edx, edx; Val
0x18000594e  mov     r8d, 7FCh; Size
0x180005954  mov     [rsp+878h+var_848], eax
0x180005958  mov     rdi, r9
0x18000595b  call    memset_0
0x180005960  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180005967  lea     r12, RasRtrmgrTraceInfo
0x18000596e  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005975  test    al, al
0x180005977  jns     short loc_1800059BA
0x180005979  xor     eax, eax
0x18000597b  lea     r8, aAccessipaddrta; "AccessIpAddrTable"
0x180005982  lea     rdx, aEnteredWs; "Entered: %ws"
0x180005989  mov     word ptr [rsp+878h+var_848], ax
0x18000598e  lea     rcx, [rsp+878h+var_848]
0x180005993  call    FormatRRASErrorString
0x180005998  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000599f  test    al, al
0x1800059a1  jns     short loc_1800059BA
0x1800059a3  lea     r8, [rsp+878h+var_848]
0x1800059a8  mov     rdx, r12
0x1800059ab  mov     rcx, r15
0x1800059ae  call    McTemplateU0z_EventWriteTransfer
0x1800059b3  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800059ba  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x1800059c2  jnz     short loc_1800059CE
0x1800059c4  mov     eax, 32h ; '2'
0x1800059c9  jmp     loc_180005B6E
0x1800059ce  cmp     ebx, 1
0x1800059d1  jz      short loc_1800059F3
0x1800059d3  test    al, 80h
0x1800059d5  jz      short loc_1800059E9
0x1800059d7  lea     r8, aLeavingAccessi_3; "Leaving: AccessIpAddrTable"
0x1800059de  mov     rdx, r12
0x1800059e1  mov     rcx, r15
0x1800059e4  call    McTemplateU0z_EventWriteTransfer
0x1800059e9  mov     eax, 57h ; 'W'
0x1800059ee  jmp     loc_180005B6E
0x1800059f3  mov     rdx, r14
0x1800059f6  xor     ecx, ecx
0x1800059f8  call    UpdateCache
0x1800059fd  mov     ebx, eax
0x1800059ff  test    eax, eax
0x180005a01  jz      short loc_180005A59
0x180005a03  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005a0a  test    cl, 40h
0x180005a0d  jz      short loc_180005A51
0x180005a0f  xor     ecx, ecx
0x180005a11  lea     rdx, aAccessipaddrta_0; "AccessIpAddrTable: Error %d updating Ip"...
0x180005a18  mov     word ptr [rsp+878h+var_848], cx
0x180005a1d  mov     r8d, eax
0x180005a20  lea     rcx, [rsp+878h+var_848]
0x180005a25  call    FormatRRASErrorString
0x180005a2a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005a31  test    cl, 40h
0x180005a34  jz      short loc_180005A51
0x180005a36  lea     r8, [rsp+878h+var_848]
0x180005a3b  mov     rcx, r15
0x180005a3e  lea     rdx, RasRtrMgrTraceError
0x180005a45  call    McTemplateU0z_EventWriteTransfer
0x180005a4a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180005a51  test    cl, 80h
0x180005a54  jmp     loc_180005B58
0x180005a59  mov     dl, 1; Wait
0x180005a5b  lea     rcx, g_LockTable; Resource
0x180005a62  call    cs:__imp_RtlAcquireResourceShared
0x180005a68  mov     rdx, cs:g_IpInfo
0x180005a6f  test    rdx, rdx
0x180005a72  jz      loc_180005B08
0x180005a78  mov     edx, [rdx]
0x180005a7a  test    edx, edx
0x180005a7c  jz      loc_180005B08
0x180005a82  mov     eax, [rdi]
0x180005a84  lea     rcx, [rdx+rdx*2]
0x180005a88  lea     rcx, ds:14h[rcx*8]
0x180005a90  cmp     rax, rcx
0x180005a93  jnb     short loc_180005AAB
0x180005a95  lea     eax, [rdx+rdx*2]
0x180005a98  mov     ebx, 7Ah ; 'z'
0x180005a9d  lea     eax, ds:14h[rax*8]
0x180005aa4  mov     [rdi], eax
0x180005aa6  jmp     loc_180005B44
0x180005aab  mov     dword ptr [rsi], 4
0x180005ab1  xor     r8d, r8d
0x180005ab4  mov     rax, cs:g_IpInfo
0x180005abb  mov     ecx, [rax]
0x180005abd  lea     eax, [rcx+rcx*2]
0x180005ac0  lea     eax, ds:14h[rax*8]
0x180005ac7  mov     [rdi], eax
0x180005ac9  mov     rdx, cs:g_IpInfo
0x180005ad0  mov     eax, [rdx]
0x180005ad2  test    eax, eax
0x180005ad4  jz      short loc_180005B01
0x180005ad6  lea     rcx, [r8+r8*2]
0x180005ada  inc     r8d
0x180005add  movups  xmm0, xmmword ptr [rdx+rcx*8+4]
0x180005ae2  movups  xmmword ptr [rsi+rcx*8+0Ch], xmm0
0x180005ae7  movsd   xmm1, qword ptr [rdx+rcx*8+14h]
0x180005aed  movsd   qword ptr [rsi+rcx*8+1Ch], xmm1
0x180005af3  mov     rdx, cs:g_IpInfo
0x180005afa  mov     eax, [rdx]
0x180005afc  cmp     r8d, eax
0x180005aff  jb      short loc_180005AD6
0x180005b01  mov     [rsi+8], eax
0x180005b04  xor     ebx, ebx
0x180005b06  jmp     short loc_180005B44
0x180005b08  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180005b0f  jz      short loc_180005B23
0x180005b11  lea     r8, aNoValidEntries; "No valid entries found"
0x180005b18  mov     rdx, r12
0x180005b1b  mov     rcx, r15
0x180005b1e  call    McTemplateU0z_EventWriteTransfer
0x180005b23  cmp     dword ptr [rdi], 24h ; '$'
0x180005b26  jnb     short loc_180005B2F
0x180005b28  mov     ebx, 7Ah ; 'z'
0x180005b2d  jmp     short loc_180005B3E
0x180005b2f  mov     dword ptr [rsi], 4
0x180005b35  xor     ebx, ebx
0x180005b37  mov     dword ptr [rsi+8], 0
0x180005b3e  mov     dword ptr [rdi], 24h ; '$'
0x180005b44  lea     rcx, g_LockTable; Resource
0x180005b4b  call    cs:__imp_RtlReleaseResource
0x180005b51  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180005b58  jz      short loc_180005B6C
0x180005b5a  lea     r8, aLeavingAccessi_3; "Leaving: AccessIpAddrTable"
0x180005b61  mov     rdx, r12
0x180005b64  mov     rcx, r15
0x180005b67  call    McTemplateU0z_EventWriteTransfer
0x180005b6c  mov     eax, ebx
0x180005b6e  mov     rcx, [rsp+878h+var_48]
0x180005b76  xor     rcx, rsp; StackCookie
0x180005b79  call    __security_check_cookie
0x180005b7e  add     rsp, 848h
0x180005b85  pop     r15
0x180005b87  pop     r14
0x180005b89  pop     r12
0x180005b8b  pop     rdi
0x180005b8c  pop     rsi
0x180005b8d  pop     rbx
0x180005b8e  retn
```
