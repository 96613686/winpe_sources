# AccessMcastMfe

- ea: `0x180007d10`
- end: `0x180007f99`
- name: `AccessMcastMfe`
- size: `649`
- prototype: `__int64 __fastcall(int, unsigned int, __int64, unsigned int *, __int64, int, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`
- `0x1800276bc`

## callees

- `0x180007d10`
- `0x18000ac60`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `rtm!MgmGetNextMfe` at `0x180007e56`
- `rtm!MgmGetNextMfe` at `0x180007e56`
- `rtm!MgmGetFirstMfe` at `0x180007e9b`
- `rtm!MgmGetFirstMfe` at `0x180007e9b`
- `rtm!MgmGetMfe` at `0x180007f39`
- `rtm!MgmGetMfe` at `0x180007f39`

## string_xrefs

- `0x180007d8e`: `AccessMcastMfe`
- `0x180007ecd`: `Leaving: AccessMcastMfe`
- `0x180007f57`: `Leaving: AccessMcastMfe`

## pseudocode

```c
__int64 __fastcall AccessMcastMfe(int a1, unsigned int a2, __int64 a3, unsigned int *a4, __int64 a5, int a6, int a7)
{
  unsigned int v12; // esi
  int v13; // ebx
  int v14; // ebx
  unsigned int v15; // ecx
  DWORD NextMfe; // eax
  unsigned int v17; // ecx
  unsigned int v18; // edx
  DWORD v19; // ecx
  DWORD pdwBufferSize; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pdwNumEntries[3]; // [rsp+24h] [rbp-DCh] BYREF
  _MIB_IPMCAST_MFE pimmStart; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+80h] [rbp-80h] BYREF
  char v24[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  pdwBufferSize = 0;
  pdwNumEntries[0] = 0;
  memset_0(&pimmStart, 0, sizeof(pimmStart));
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"Entered: %ws", L"AccessMcastMfe");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v23);
  }
  if ( a7 == 87 )
    return 50;
  v12 = (a2 >> 2) - 1;
  v13 = a1 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
LABEL_28:
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasRtrmgrTraceInfo,
            L"Leaving: AccessMcastMfe");
        return 0;
      }
      v15 = *a4;
      if ( *a4 >= 0x400 )
      {
        *(_DWORD *)(a5 + 8) = 0;
        pdwBufferSize = v15 - 12;
        pdwNumEntries[0] = 0;
        memset_0(&pimmStart, 0, sizeof(pimmStart));
        pimmStart.dwSrcMask = -1;
        if ( v12 )
        {
          pimmStart.dwGroup = *(_DWORD *)(a3 + 4);
          if ( v12 != 1 )
            pimmStart.dwSource = *(_DWORD *)(a3 + 8);
        }
        NextMfe = MgmGetNextMfe(&pimmStart, &pdwBufferSize, (PBYTE)(a5 + 12), pdwNumEntries);
        goto LABEL_17;
      }
    }
    else
    {
      v17 = *a4;
      if ( *a4 >= 0x400 )
      {
        *(_DWORD *)(a5 + 8) = 0;
        pdwBufferSize = v17 - 12;
        pdwNumEntries[0] = 0;
        NextMfe = MgmGetFirstMfe(&pdwBufferSize, (PBYTE)(a5 + 12), pdwNumEntries);
LABEL_17:
        if ( NextMfe == 234 || NextMfe == 259 )
          *(_DWORD *)(a5 + 8) = pdwNumEntries[0];
        goto LABEL_28;
      }
    }
    *a4 = 1024;
    return 122;
  }
  if ( v12 >= 3 )
  {
    memset_0(&pimmStart, 0, sizeof(pimmStart));
    v18 = *a4;
    v19 = 0;
    pimmStart.dwGroup = *(_DWORD *)(a3 + 4);
    pimmStart.dwSource = *(_DWORD *)(a3 + 8);
    if ( v18 >= 8 )
      v19 = v18 - 8;
    pimmStart.dwSrcMask = -1;
    pdwBufferSize = v19;
    if ( MgmGetMfe(&pimmStart, &pdwBufferSize, (PBYTE)(a5 + 8)) == 122 )
      *a4 = pdwBufferSize + 8;
    goto LABEL_28;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: AccessMcastMfe");
  return 1413;
}

```

## disassembly

```asm
0x180007d10  mov     [rsp-8+arg_0], rbx
0x180007d15  push    rbp
0x180007d16  push    rsi
0x180007d17  push    rdi
0x180007d18  push    r14
0x180007d1a  push    r15
0x180007d1c  lea     rbp, [rsp-790h]
0x180007d24  sub     rsp, 890h
0x180007d2b  mov     rax, cs:__security_cookie
0x180007d32  xor     rax, rsp
0x180007d35  mov     [rbp+7B0h+var_30], rax
0x180007d3c  mov     rdi, [rbp+7B0h+arg_20]
0x180007d43  mov     esi, edx
0x180007d45  xor     edx, edx; Val
0x180007d47  mov     [rsp+8B0h+pdwBufferSize], 0
0x180007d4f  mov     r15, r8
0x180007d52  mov     [rsp+8B0h+pdwNumEntries], 0
0x180007d5a  mov     ebx, ecx
0x180007d5c  mov     r14, r9
0x180007d5f  lea     rcx, [rsp+8B0h+pimmStart]; void *
0x180007d64  lea     r8d, [rdx+4Ch]; Size
0x180007d68  call    memset_0
0x180007d6d  xor     eax, eax
0x180007d6f  lea     rcx, [rbp+7B0h+var_82C]; void *
0x180007d73  xor     edx, edx; Val
0x180007d75  mov     [rbp+7B0h+var_830], eax
0x180007d78  mov     r8d, 7FCh; Size
0x180007d7e  call    memset_0
0x180007d83  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007d8a  jge     short loc_180007DC9
0x180007d8c  xor     eax, eax
0x180007d8e  lea     r8, aAccessmcastmfe_0; "AccessMcastMfe"
0x180007d95  lea     rdx, aEnteredWs; "Entered: %ws"
0x180007d9c  mov     word ptr [rbp+7B0h+var_830], ax
0x180007da0  lea     rcx, [rbp+7B0h+var_830]
0x180007da4  call    FormatRRASErrorString
0x180007da9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007db0  jge     short loc_180007DC9
0x180007db2  lea     r8, [rbp+7B0h+var_830]
0x180007db6  lea     rdx, RasRtrmgrTraceInfo
0x180007dbd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007dc4  call    McTemplateU0z_EventWriteTransfer
0x180007dc9  cmp     [rbp+7B0h+arg_30], 57h ; 'W'
0x180007dd0  jnz     short loc_180007DDC
0x180007dd2  mov     eax, 32h ; '2'
0x180007dd7  jmp     loc_180007F73
0x180007ddc  shr     esi, 2
0x180007ddf  dec     esi
0x180007de1  sub     ebx, 1
0x180007de4  jz      loc_180007EBF
0x180007dea  sub     ebx, 1
0x180007ded  jz      short loc_180007E5E
0x180007def  sub     ebx, 2
0x180007df2  jnz     loc_180007F4E
0x180007df8  mov     ecx, [r14]
0x180007dfb  mov     eax, 400h
0x180007e00  cmp     ecx, eax
0x180007e02  jb      short loc_180007E6A
0x180007e04  lea     eax, [rcx-0Ch]
0x180007e07  mov     [rdi+8], ebx
0x180007e0a  lea     rcx, [rsp+8B0h+pimmStart]; void *
0x180007e0f  mov     [rsp+8B0h+pdwBufferSize], eax
0x180007e13  xor     edx, edx; Val
0x180007e15  mov     [rsp+8B0h+pdwNumEntries], ebx
0x180007e19  lea     r8d, [rbx+4Ch]; Size
0x180007e1d  call    memset_0
0x180007e22  mov     [rsp+8B0h+pimmStart.dwSrcMask], 0FFFFFFFFh
0x180007e2a  test    esi, esi
0x180007e2c  jz      short loc_180007E43
0x180007e2e  mov     eax, [r15+4]
0x180007e32  mov     [rsp+8B0h+pimmStart.dwGroup], eax
0x180007e36  cmp     esi, 1
0x180007e39  jz      short loc_180007E43
0x180007e3b  mov     eax, [r15+8]
0x180007e3f  mov     [rsp+8B0h+pimmStart.dwSource], eax
0x180007e43  lea     r8, [rdi+0Ch]; pbBuffer
0x180007e47  lea     r9, [rsp+8B0h+pdwNumEntries]; pdwNumEntries
0x180007e4c  lea     rdx, [rsp+8B0h+pdwBufferSize]; pdwBufferSize
0x180007e51  lea     rcx, [rsp+8B0h+pimmStart]; pimmStart
0x180007e56  call    cs:__imp_MgmGetNextMfe
0x180007e5c  jmp     short loc_180007EA1
0x180007e5e  mov     ecx, [r14]
0x180007e61  mov     eax, 400h
0x180007e66  cmp     ecx, eax
0x180007e68  jnb     short loc_180007E77
0x180007e6a  mov     [r14], eax
0x180007e6d  mov     eax, 7Ah ; 'z'
0x180007e72  jmp     loc_180007F73
0x180007e77  lea     eax, [rcx-0Ch]
0x180007e7a  mov     dword ptr [rdi+8], 0
0x180007e81  lea     rcx, [rsp+8B0h+pdwBufferSize]; pdwBufferSize
0x180007e86  mov     [rsp+8B0h+pdwBufferSize], eax
0x180007e8a  lea     rdx, [rdi+0Ch]; pbBuffer
0x180007e8e  mov     [rsp+8B0h+pdwNumEntries], 0
0x180007e96  lea     r8, [rsp+8B0h+pdwNumEntries]; pdwNumEntries
0x180007e9b  call    cs:__imp_MgmGetFirstMfe
0x180007ea1  cmp     eax, 0EAh
0x180007ea6  jz      short loc_180007EB3
0x180007ea8  cmp     eax, 103h
0x180007ead  jnz     loc_180007F4E
0x180007eb3  mov     eax, [rsp+8B0h+pdwNumEntries]
0x180007eb7  mov     [rdi+8], eax
0x180007eba  jmp     loc_180007F4E
0x180007ebf  cmp     esi, 3
0x180007ec2  jnb     short loc_180007EF1
0x180007ec4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180007ecb  jz      short loc_180007EE7
0x180007ecd  lea     r8, aLeavingAccessm_2; "Leaving: AccessMcastMfe"
0x180007ed4  lea     rdx, RasRtrmgrTraceInfo
0x180007edb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007ee2  call    McTemplateU0z_EventWriteTransfer
0x180007ee7  mov     eax, 585h
0x180007eec  jmp     loc_180007F73
0x180007ef1  xor     edx, edx; Val
0x180007ef3  lea     rcx, [rsp+8B0h+pimmStart]; void *
0x180007ef8  lea     r8d, [rdx+4Ch]; Size
0x180007efc  call    memset_0
0x180007f01  mov     edx, [r14]
0x180007f04  lea     r8, [rdi+8]; pbBuffer
0x180007f08  mov     eax, [r15+4]
0x180007f0c  xor     ecx, ecx
0x180007f0e  mov     [rsp+8B0h+pimmStart.dwGroup], eax
0x180007f12  cmp     edx, 8
0x180007f15  mov     eax, [r15+8]
0x180007f19  mov     [rsp+8B0h+pimmStart.dwSource], eax
0x180007f1d  lea     eax, [rdx-8]
0x180007f20  cmovnb  ecx, eax
0x180007f23  mov     [rsp+8B0h+pimmStart.dwSrcMask], 0FFFFFFFFh
0x180007f2b  mov     [rsp+8B0h+pdwBufferSize], ecx
0x180007f2f  lea     rdx, [rsp+8B0h+pdwBufferSize]; pdwBufferSize
0x180007f34  lea     rcx, [rsp+8B0h+pimmStart]; pimm
0x180007f39  call    cs:__imp_MgmGetMfe
0x180007f3f  cmp     eax, 7Ah ; 'z'
0x180007f42  jnz     short loc_180007F4E
0x180007f44  mov     eax, [rsp+8B0h+pdwBufferSize]
0x180007f48  add     eax, 8
0x180007f4b  mov     [r14], eax
0x180007f4e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180007f55  jz      short loc_180007F71
0x180007f57  lea     r8, aLeavingAccessm_2; "Leaving: AccessMcastMfe"
0x180007f5e  lea     rdx, RasRtrmgrTraceInfo
0x180007f65  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007f6c  call    McTemplateU0z_EventWriteTransfer
0x180007f71  xor     eax, eax
0x180007f73  mov     rcx, [rbp+7B0h+var_30]
0x180007f7a  xor     rcx, rsp; StackCookie
0x180007f7d  call    __security_check_cookie
0x180007f82  mov     rbx, [rsp+8B0h+arg_0]
0x180007f8a  add     rsp, 890h
0x180007f91  pop     r15
0x180007f93  pop     r14
0x180007f95  pop     rdi
0x180007f96  pop     rsi
0x180007f97  pop     rbp
0x180007f98  retn
```
