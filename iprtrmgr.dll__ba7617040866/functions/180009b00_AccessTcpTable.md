# AccessTcpTable

- ea: `0x180009b00`
- end: `0x180009d4e`
- name: `AccessTcpTable`
- size: `590`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180009b00`
- `0x18000ac60`
- `0x18000baa8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180009cfe`
- `ntdll!RtlReleaseResource` at `0x180009cfe`
- `ntdll!RtlAcquireResourceShared` at `0x180009c32`
- `ntdll!RtlAcquireResourceShared` at `0x180009c32`

## string_xrefs

- `0x180009b67`: `AccessTcpTable`
- `0x180009be1`: `AccessTcpTable: Couldnt update Tcp Cache. Error %d`
- `0x180009d0d`: `Leaving: AccessTcpTable`
- `0x180009cc0`: `AccessTcpTable: No valid entries found`

## pseudocode

```c
__int64 __fastcall AccessTcpTable(int a1, __int64 a2, __int64 a3, _DWORD *a4, _DWORD *a5, __int64 a6, int a7)
{
  __int64 result; // rax
  unsigned int updated; // eax
  unsigned int v11; // ebx
  char v12; // cl
  bool v13; // zf
  int *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r8
  int i; // eax
  __int64 v18; // rcx
  int v19; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v20[2044]; // [rsp+34h] [rbp-824h] BYREF

  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"Entered: %ws", L"AccessTcpTable");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v19);
  }
  result = 87;
  if ( a7 == 87 )
    return 50;
  if ( a1 == 1 )
  {
    updated = UpdateCache(4, a6);
    v11 = updated;
    if ( updated )
    {
      v12 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"AccessTcpTable: Couldnt update Tcp Cache. Error %d", updated);
        v12 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v19);
          v12 = Microsoft_Windows_RRASEnableBits;
        }
      }
      v13 = v12 >= 0;
    }
    else
    {
      RtlAcquireResourceShared(&stru_18008C380, 1u);
      v14 = (int *)g_TcpInfo;
      if ( g_TcpInfo && (v15 = *(unsigned int *)g_TcpInfo, (_DWORD)v15) )
      {
        if ( (unsigned int)*a4 >= (unsigned __int64)(20 * (v15 + 1)) )
        {
          *a5 = 13;
          v16 = 0;
          *a4 = 20 * (*v14 + 1);
          for ( i = *v14; (unsigned int)v16 < *v14; i = *v14 )
          {
            v18 = 5 * v16;
            v16 = (unsigned int)(v16 + 1);
            *(_OWORD *)&a5[v18 + 3] = *(_OWORD *)&v14[v18 + 1];
            a5[v18 + 7] = v14[v18 + 5];
          }
          a5[2] = i;
          v11 = 0;
        }
        else
        {
          v11 = 122;
          *a4 = 20 * (v15 + 1);
        }
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"AccessTcpTable: No valid entries found");
        if ( *a4 >= 0x20u )
        {
          *a5 = 13;
          v11 = 0;
          a5[2] = 0;
        }
        else
        {
          v11 = 122;
        }
        *a4 = 32;
      }
      RtlReleaseResource(&stru_18008C380);
      v13 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
    }
    if ( !v13 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessTcpTable");
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180009b00  mov     [rsp+arg_0], rbx
0x180009b05  mov     [rsp+arg_8], rsi
0x180009b0a  push    rdi
0x180009b0b  push    r12
0x180009b0d  push    r14
0x180009b0f  sub     rsp, 840h
0x180009b16  mov     rax, cs:__security_cookie
0x180009b1d  xor     rax, rsp
0x180009b20  mov     [rsp+858h+var_28], rax
0x180009b28  mov     rsi, [rsp+858h+arg_20]
0x180009b30  mov     ebx, ecx
0x180009b32  mov     r14, [rsp+858h+arg_28]
0x180009b3a  lea     rcx, [rsp+858h+var_824]; void *
0x180009b3f  xor     eax, eax
0x180009b41  xor     edx, edx; Val
0x180009b43  mov     r8d, 7FCh; Size
0x180009b49  mov     [rsp+858h+var_828], eax
0x180009b4d  mov     rdi, r9
0x180009b50  call    memset_0
0x180009b55  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180009b5c  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009b63  jge     short loc_180009BA1
0x180009b65  xor     eax, eax
0x180009b67  lea     r8, aAccesstcptable_1; "AccessTcpTable"
0x180009b6e  lea     rdx, aEnteredWs; "Entered: %ws"
0x180009b75  mov     word ptr [rsp+858h+var_828], ax
0x180009b7a  lea     rcx, [rsp+858h+var_828]
0x180009b7f  call    FormatRRASErrorString
0x180009b84  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180009b8b  jge     short loc_180009BA1
0x180009b8d  lea     r8, [rsp+858h+var_828]
0x180009b92  mov     rcx, r12
0x180009b95  lea     rdx, RasRtrmgrTraceInfo
0x180009b9c  call    McTemplateU0z_EventWriteTransfer
0x180009ba1  mov     eax, 57h ; 'W'
0x180009ba6  cmp     [rsp+858h+arg_30], eax
0x180009bad  jnz     short loc_180009BB9
0x180009baf  mov     eax, 32h ; '2'
0x180009bb4  jmp     loc_180009D25
0x180009bb9  cmp     ebx, 1
0x180009bbc  jnz     loc_180009D25
0x180009bc2  mov     rdx, r14
0x180009bc5  lea     ecx, [rbx+3]
0x180009bc8  call    UpdateCache
0x180009bcd  mov     ebx, eax
0x180009bcf  test    eax, eax
0x180009bd1  jz      short loc_180009C29
0x180009bd3  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180009bda  test    cl, 40h
0x180009bdd  jz      short loc_180009C21
0x180009bdf  xor     ecx, ecx
0x180009be1  lea     rdx, aAccesstcptable; "AccessTcpTable: Couldnt update Tcp Cach"...
0x180009be8  mov     word ptr [rsp+858h+var_828], cx
0x180009bed  mov     r8d, eax
0x180009bf0  lea     rcx, [rsp+858h+var_828]
0x180009bf5  call    FormatRRASErrorString
0x180009bfa  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180009c01  test    cl, 40h
0x180009c04  jz      short loc_180009C21
0x180009c06  lea     r8, [rsp+858h+var_828]
0x180009c0b  mov     rcx, r12
0x180009c0e  lea     rdx, RasRtrMgrTraceError
0x180009c15  call    McTemplateU0z_EventWriteTransfer
0x180009c1a  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180009c21  test    cl, 80h
0x180009c24  jmp     loc_180009D0B
0x180009c29  mov     dl, 1; Wait
0x180009c2b  lea     rcx, stru_18008C380; Resource
0x180009c32  call    cs:__imp_RtlAcquireResourceShared
0x180009c38  mov     rdx, cs:g_TcpInfo
0x180009c3f  test    rdx, rdx
0x180009c42  jz      short loc_180009CB7
0x180009c44  mov     r8d, [rdx]
0x180009c47  test    r8d, r8d
0x180009c4a  jz      short loc_180009CB7
0x180009c4c  lea     rax, [r8+1]
0x180009c50  lea     rcx, [rax+rax*4]
0x180009c54  mov     eax, [rdi]
0x180009c56  shl     rcx, 2
0x180009c5a  cmp     rax, rcx
0x180009c5d  jnb     short loc_180009C75
0x180009c5f  lea     eax, [r8+1]
0x180009c63  mov     ebx, 7Ah ; 'z'
0x180009c68  lea     ecx, [rax+rax*4]
0x180009c6b  shl     ecx, 2
0x180009c6e  mov     [rdi], ecx
0x180009c70  jmp     loc_180009CF7
0x180009c75  mov     dword ptr [rsi], 0Dh
0x180009c7b  xor     r8d, r8d
0x180009c7e  mov     eax, [rdx]
0x180009c80  inc     eax
0x180009c82  lea     eax, [rax+rax*4]
0x180009c85  shl     eax, 2
0x180009c88  mov     [rdi], eax
0x180009c8a  mov     eax, [rdx]
0x180009c8c  test    eax, eax
0x180009c8e  jz      short loc_180009CB0
0x180009c90  lea     rcx, [r8+r8*4]
0x180009c94  inc     r8d
0x180009c97  movups  xmm0, xmmword ptr [rdx+rcx*4+4]
0x180009c9c  movups  xmmword ptr [rsi+rcx*4+0Ch], xmm0
0x180009ca1  mov     eax, [rdx+rcx*4+14h]
0x180009ca5  mov     [rsi+rcx*4+1Ch], eax
0x180009ca9  mov     eax, [rdx]
0x180009cab  cmp     r8d, eax
0x180009cae  jb      short loc_180009C90
0x180009cb0  mov     [rsi+8], eax
0x180009cb3  xor     ebx, ebx
0x180009cb5  jmp     short loc_180009CF7
0x180009cb7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009cbe  jz      short loc_180009CD6
0x180009cc0  lea     r8, aAccesstcptable_0; "AccessTcpTable: No valid entries found"
0x180009cc7  mov     rcx, r12
0x180009cca  lea     rdx, RasRtrmgrTraceInfo
0x180009cd1  call    McTemplateU0z_EventWriteTransfer
0x180009cd6  cmp     dword ptr [rdi], 20h ; ' '
0x180009cd9  jnb     short loc_180009CE2
0x180009cdb  mov     ebx, 7Ah ; 'z'
0x180009ce0  jmp     short loc_180009CF1
0x180009ce2  mov     dword ptr [rsi], 0Dh
0x180009ce8  xor     ebx, ebx
0x180009cea  mov     dword ptr [rsi+8], 0
0x180009cf1  mov     dword ptr [rdi], 20h ; ' '
0x180009cf7  lea     rcx, stru_18008C380; Resource
0x180009cfe  call    cs:__imp_RtlReleaseResource
0x180009d04  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009d0b  jz      short loc_180009D23
0x180009d0d  lea     r8, aLeavingAccesst_1; "Leaving: AccessTcpTable"
0x180009d14  mov     rcx, r12
0x180009d17  lea     rdx, RasRtrmgrTraceInfo
0x180009d1e  call    McTemplateU0z_EventWriteTransfer
0x180009d23  mov     eax, ebx
0x180009d25  mov     rcx, [rsp+858h+var_28]
0x180009d2d  xor     rcx, rsp; StackCookie
0x180009d30  call    __security_check_cookie
0x180009d35  lea     r11, [rsp+858h+var_18]
0x180009d3d  mov     rbx, [r11+20h]
0x180009d41  mov     rsi, [r11+28h]
0x180009d45  mov     rsp, r11
0x180009d48  pop     r14
0x180009d4a  pop     r12
0x180009d4c  pop     rdi
0x180009d4d  retn
```
