# AccessUdpTable

- ea: `0x18000a0c0`
- end: `0x18000a300`
- name: `AccessUdpTable`
- size: `576`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x18000a0c0`
- `0x18000ac60`
- `0x18000baa8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000a2bc`
- `ntdll!RtlReleaseResource` at `0x18000a2bc`
- `ntdll!RtlAcquireResourceShared` at `0x18000a215`
- `ntdll!RtlAcquireResourceShared` at `0x18000a215`

## string_xrefs

- `0x18000a12b`: `AccessUdpTable`
- `0x18000a187`: `Leaving: AccessUdpTable`
- `0x18000a2cb`: `Leaving: AccessUdpTable`
- `0x18000a1c4`: `AccessUdpTable: Couldnt update Udp Cache. Error %d`
- `0x18000a282`: `AccessUdpTable: No valid entries found`

## pseudocode

```c
__int64 __fastcall AccessUdpTable(int a1, __int64 a2, __int64 a3, _DWORD *a4, _DWORD *a5, __int64 a6, int a7)
{
  char v9; // al
  unsigned int updated; // eax
  unsigned int v12; // ebx
  char v13; // cl
  bool v14; // zf
  int *v15; // rdx
  __int64 v16; // r8
  unsigned __int64 v17; // rcx
  __int64 v18; // r8
  int i; // eax
  int v20; // [rsp+30h] [rbp-848h] BYREF
  _BYTE v21[2044]; // [rsp+34h] [rbp-844h] BYREF

  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v9 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    FormatRRASErrorString(&v20, L"Entered: %ws", L"AccessUdpTable");
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
    updated = UpdateCache(5, a6);
    v12 = updated;
    if ( updated )
    {
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString(&v20, L"AccessUdpTable: Couldnt update Udp Cache. Error %d", updated);
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
      RtlAcquireResourceShared(&stru_18008C3E0, 1u);
      v15 = (int *)g_UdpInfo;
      if ( g_UdpInfo && (v16 = *(unsigned int *)g_UdpInfo, (_DWORD)v16) )
      {
        v17 = (unsigned int)*a4;
        *a4 = 8 * v16 + 20;
        if ( v17 >= 8 * v16 + 20 )
        {
          *a5 = 16;
          v18 = 0;
          for ( i = *v15; (unsigned int)v18 < *v15; i = *v15 )
          {
            *(_QWORD *)&a5[2 * v18 + 3] = *(_QWORD *)&v15[2 * v18 + 1];
            v18 = (unsigned int)(v18 + 1);
          }
          a5[2] = i;
          v12 = 0;
        }
        else
        {
          v12 = 122;
        }
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"AccessUdpTable: No valid entries found");
        if ( *a4 >= 0x14u )
        {
          *a5 = 16;
          v12 = 0;
          a5[2] = 0;
        }
        else
        {
          v12 = 122;
        }
        *a4 = 20;
      }
      RtlReleaseResource(&stru_18008C3E0);
      v14 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    }
    if ( !v14 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessUdpTable");
    return v12;
  }
  else
  {
    if ( v9 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessUdpTable");
    return 87;
  }
}

```

## disassembly

```asm
0x18000a0c0  push    rbx
0x18000a0c2  push    rsi
0x18000a0c3  push    rdi
0x18000a0c4  push    r12
0x18000a0c6  push    r14
0x18000a0c8  push    r15
0x18000a0ca  sub     rsp, 848h
0x18000a0d1  mov     rax, cs:__security_cookie
0x18000a0d8  xor     rax, rsp
0x18000a0db  mov     [rsp+878h+var_48], rax
0x18000a0e3  mov     rdi, [rsp+878h+arg_20]
0x18000a0eb  mov     ebx, ecx
0x18000a0ed  mov     r14, [rsp+878h+arg_28]
0x18000a0f5  lea     rcx, [rsp+878h+var_844]; void *
0x18000a0fa  xor     eax, eax
0x18000a0fc  xor     edx, edx; Val
0x18000a0fe  mov     r8d, 7FCh; Size
0x18000a104  mov     [rsp+878h+var_848], eax
0x18000a108  mov     rsi, r9
0x18000a10b  call    memset_0
0x18000a110  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000a117  lea     r12, RasRtrmgrTraceInfo
0x18000a11e  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000a125  test    al, al
0x18000a127  jns     short loc_18000A16A
0x18000a129  xor     eax, eax
0x18000a12b  lea     r8, aAccessudptable; "AccessUdpTable"
0x18000a132  lea     rdx, aEnteredWs; "Entered: %ws"
0x18000a139  mov     word ptr [rsp+878h+var_848], ax
0x18000a13e  lea     rcx, [rsp+878h+var_848]
0x18000a143  call    FormatRRASErrorString
0x18000a148  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000a14f  test    al, al
0x18000a151  jns     short loc_18000A16A
0x18000a153  lea     r8, [rsp+878h+var_848]
0x18000a158  mov     rdx, r12
0x18000a15b  mov     rcx, r15
0x18000a15e  call    McTemplateU0z_EventWriteTransfer
0x18000a163  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000a16a  cmp     [rsp+878h+arg_30], 57h ; 'W'
0x18000a172  jnz     short loc_18000A17E
0x18000a174  mov     eax, 32h ; '2'
0x18000a179  jmp     loc_18000A2DF
0x18000a17e  cmp     ebx, 1
0x18000a181  jz      short loc_18000A1A3
0x18000a183  test    al, 80h
0x18000a185  jz      short loc_18000A199
0x18000a187  lea     r8, aLeavingAccessu_0; "Leaving: AccessUdpTable"
0x18000a18e  mov     rdx, r12
0x18000a191  mov     rcx, r15
0x18000a194  call    McTemplateU0z_EventWriteTransfer
0x18000a199  mov     eax, 57h ; 'W'
0x18000a19e  jmp     loc_18000A2DF
0x18000a1a3  mov     rdx, r14
0x18000a1a6  mov     ecx, 5
0x18000a1ab  call    UpdateCache
0x18000a1b0  mov     ebx, eax
0x18000a1b2  test    eax, eax
0x18000a1b4  jz      short loc_18000A20C
0x18000a1b6  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000a1bd  test    cl, 40h
0x18000a1c0  jz      short loc_18000A204
0x18000a1c2  xor     ecx, ecx
0x18000a1c4  lea     rdx, aAccessudptable_0; "AccessUdpTable: Couldnt update Udp Cach"...
0x18000a1cb  mov     word ptr [rsp+878h+var_848], cx
0x18000a1d0  mov     r8d, eax
0x18000a1d3  lea     rcx, [rsp+878h+var_848]
0x18000a1d8  call    FormatRRASErrorString
0x18000a1dd  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000a1e4  test    cl, 40h
0x18000a1e7  jz      short loc_18000A204
0x18000a1e9  lea     r8, [rsp+878h+var_848]
0x18000a1ee  mov     rcx, r15
0x18000a1f1  lea     rdx, RasRtrMgrTraceError
0x18000a1f8  call    McTemplateU0z_EventWriteTransfer
0x18000a1fd  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000a204  test    cl, 80h
0x18000a207  jmp     loc_18000A2C9
0x18000a20c  mov     dl, 1; Wait
0x18000a20e  lea     rcx, stru_18008C3E0; Resource
0x18000a215  call    cs:__imp_RtlAcquireResourceShared
0x18000a21b  mov     rdx, cs:g_UdpInfo
0x18000a222  test    rdx, rdx
0x18000a225  jz      short loc_18000A279
0x18000a227  mov     r8d, [rdx]
0x18000a22a  test    r8d, r8d
0x18000a22d  jz      short loc_18000A279
0x18000a22f  mov     ecx, [rsi]
0x18000a231  lea     eax, ds:14h[r8*8]
0x18000a239  mov     [rsi], eax
0x18000a23b  lea     rax, ds:14h[r8*8]
0x18000a243  cmp     rcx, rax
0x18000a246  jnb     short loc_18000A24F
0x18000a248  mov     ebx, 7Ah ; 'z'
0x18000a24d  jmp     short loc_18000A2B5
0x18000a24f  mov     dword ptr [rdi], 10h
0x18000a255  xor     r8d, r8d
0x18000a258  mov     eax, [rdx]
0x18000a25a  test    eax, eax
0x18000a25c  jz      short loc_18000A272
0x18000a25e  mov     rax, [rdx+r8*8+4]
0x18000a263  mov     [rdi+r8*8+0Ch], rax
0x18000a268  inc     r8d
0x18000a26b  mov     eax, [rdx]
0x18000a26d  cmp     r8d, eax
0x18000a270  jb      short loc_18000A25E
0x18000a272  mov     [rdi+8], eax
0x18000a275  xor     ebx, ebx
0x18000a277  jmp     short loc_18000A2B5
0x18000a279  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000a280  jz      short loc_18000A294
0x18000a282  lea     r8, aAccessudptable_1; "AccessUdpTable: No valid entries found"
0x18000a289  mov     rdx, r12
0x18000a28c  mov     rcx, r15
0x18000a28f  call    McTemplateU0z_EventWriteTransfer
0x18000a294  cmp     dword ptr [rsi], 14h
0x18000a297  jnb     short loc_18000A2A0
0x18000a299  mov     ebx, 7Ah ; 'z'
0x18000a29e  jmp     short loc_18000A2AF
0x18000a2a0  mov     dword ptr [rdi], 10h
0x18000a2a6  xor     ebx, ebx
0x18000a2a8  mov     dword ptr [rdi+8], 0
0x18000a2af  mov     dword ptr [rsi], 14h
0x18000a2b5  lea     rcx, stru_18008C3E0; Resource
0x18000a2bc  call    cs:__imp_RtlReleaseResource
0x18000a2c2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000a2c9  jz      short loc_18000A2DD
0x18000a2cb  lea     r8, aLeavingAccessu_0; "Leaving: AccessUdpTable"
0x18000a2d2  mov     rdx, r12
0x18000a2d5  mov     rcx, r15
0x18000a2d8  call    McTemplateU0z_EventWriteTransfer
0x18000a2dd  mov     eax, ebx
0x18000a2df  mov     rcx, [rsp+878h+var_48]
0x18000a2e7  xor     rcx, rsp; StackCookie
0x18000a2ea  call    __security_check_cookie
0x18000a2ef  add     rsp, 848h
0x18000a2f6  pop     r15
0x18000a2f8  pop     r14
0x18000a2fa  pop     r12
0x18000a2fc  pop     rdi
0x18000a2fd  pop     rsi
0x18000a2fe  pop     rbx
0x18000a2ff  retn
```
