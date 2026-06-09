# SpoolerCopyFileEvent

- ea: `0x180044ed0`
- end: `0x180045171`
- name: `SpoolerCopyFileEvent`
- size: `673`
- prototype: `BOOL __stdcall(LPWSTR pszPrinterName, LPWSTR pszKey, DWORD dwCopyFileEvent)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callees

- `0x180008cc0`
- `0x1800098b0`
- `0x18000b828`
- `0x18000be44`
- `0x18001e68c`
- `0x18001f8bc`
- `0x18002e5f0`
- `0x18003d8c8`
- `0x180043ad4`
- `0x180044470`
- `0x180044ab0`
- `0x180044ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800450ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045138`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800450ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045138`

## pseudocode

```c
BOOL __stdcall SpoolerCopyFileEvent(LPWSTR pszPrinterName, LPWSTR pszKey, DWORD dwCopyFileEvent)
{
  BOOL v3; // r14d
  DWORD v5; // r8d
  DWORD v6; // r8d
  DWORD v7; // r8d
  void *v8; // rsi
  unsigned __int64 v9; // rdx
  const unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // r15
  unsigned __int64 v12; // rbx
  const WCHAR *v13; // r14
  unsigned __int64 v14; // rbx
  unsigned int v16; // [rsp+28h] [rbp-D8h]
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbNeeded; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pProfileName[264]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = 0;
  pcbNeeded = 0;
  v17 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v5 = dwCopyFileEvent - 1;
  if ( !v5 )
  {
LABEL_5:
    if ( (unsigned int)GetDeviceDataSize(WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, pszPrinterName, &v17) )
    {
      v8 = (void *)MemAlloc(v17);
      if ( v8 )
      {
        if ( !(unsigned int)GetDeviceData(WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, pszPrinterName, v8, &v17) )
          goto LABEL_28;
        pcbNeeded = 520;
        if ( !InternalGetColorDirectory(0, pProfileName, &pcbNeeded) )
          goto LABEL_28;
        if ( (int)StringCchCatExW(pProfileName, v9, v10, &v21, &v20, v16) < 0 || !v20 )
        {
LABEL_27:
          SetLastError(0x7Au);
          goto LABEL_28;
        }
        v11 = (unsigned __int16 *)v8;
        v12 = (unsigned __int64)v17 >> 1;
        while ( v12 > 1 )
        {
          if ( (int)StringCchCopyW(v21, v20, v11) < 0 )
            goto LABEL_27;
          InstallColorProfileW(0, pProfileName);
          if ( (int)StringCchLengthW(v11, v12, &v19) < 0 || v12 <= v19 )
            break;
          v12 += -1LL - v19;
          v11 += v19 + 1;
        }
        goto LABEL_26;
      }
LABEL_19:
      SetLastError(0xEu);
      return v3;
    }
    return v3;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 && v7 != 2 )
      return v3;
    goto LABEL_5;
  }
  if ( (unsigned int)GetDeviceDataSize(WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, pszPrinterName, &v17) )
  {
    v8 = (void *)MemAlloc(v17);
    if ( v8 )
    {
      if ( !(unsigned int)GetDeviceData(WCS_PROFILE_MANAGEMENT_SCOPE_SYSTEM_WIDE, pszPrinterName, v8, &v17) )
      {
LABEL_28:
        MemFree(v8);
        return v3;
      }
      v13 = (const WCHAR *)v8;
      v14 = (unsigned __int64)v17 >> 1;
      while ( v14 > 1 )
      {
        DisassociateColorProfileFromDeviceW(0, v13, pszPrinterName);
        if ( (int)StringCchLengthW(v13, v14, &v19) < 0 || v14 <= v19 )
          break;
        v14 += -1LL - v19;
        v13 += v19 + 1;
      }
LABEL_26:
      v3 = 1;
      goto LABEL_28;
    }
    goto LABEL_19;
  }
  return v3;
}

```

## disassembly

```asm
0x180044ed0  mov     [rsp-8+arg_8], rbx
0x180044ed5  mov     [rsp-8+arg_10], rsi
0x180044eda  push    rbp
0x180044edb  push    r14
0x180044edd  push    r15
0x180044edf  lea     rbp, [rsp-170h]
0x180044ee7  sub     rsp, 270h
0x180044eee  mov     rax, cs:__security_cookie
0x180044ef5  xor     rax, rsp
0x180044ef8  mov     [rbp+180h+var_20], rax
0x180044eff  xor     r14d, r14d
0x180044f02  mov     [rsp+280h+pcbNeeded], 0
0x180044f0a  mov     [rsp+280h+var_250], r14d
0x180044f0f  mov     r15, rcx
0x180044f12  mov     [rsp+280h+var_240], r14
0x180044f17  mov     [rsp+280h+var_248], r14
0x180044f1c  mov     [rsp+280h+var_238], r14
0x180044f21  sub     r8d, 1
0x180044f25  jz      short loc_180044F41
0x180044f27  sub     r8d, 1
0x180044f2b  jz      loc_18004506B
0x180044f31  sub     r8d, 1
0x180044f35  jz      short loc_180044F41
0x180044f37  cmp     r8d, 2
0x180044f3b  jnz     loc_180045146
0x180044f41  lea     rax, [rsp+280h+var_250]
0x180044f46  mov     ebx, 70727472h
0x180044f4b  mov     r8d, ebx
0x180044f4e  mov     [rsp+280h+var_260], rax; unsigned int *
0x180044f53  mov     r9d, 1
0x180044f59  mov     rdx, r15; unsigned __int16 *
0x180044f5c  xor     ecx, ecx; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180044f5e  call    GetDeviceDataSize
0x180044f63  test    eax, eax
0x180044f65  jz      loc_180045146
0x180044f6b  mov     ecx, [rsp+280h+var_250]
0x180044f6f  call    MemAlloc
0x180044f74  mov     rsi, rax
0x180044f77  test    rax, rax
0x180044f7a  jz      loc_1800450A6
0x180044f80  lea     rax, [rsp+280h+var_250]
0x180044f85  mov     r9d, 1
0x180044f8b  mov     [rsp+280h+var_258], rax; unsigned int
0x180044f90  mov     r8d, ebx
0x180044f93  mov     rdx, r15; unsigned __int16 *
0x180044f96  mov     [rsp+280h+var_260], rsi; void *
0x180044f9b  xor     ecx, ecx; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180044f9d  call    GetDeviceData
0x180044fa2  test    eax, eax
0x180044fa4  jz      loc_18004513E
0x180044faa  lea     r8, [rsp+280h+pcbNeeded]; pcbNeeded
0x180044faf  mov     [rsp+280h+pcbNeeded], 208h
0x180044fb7  lea     rdx, [rsp+280h+pProfileName]; unsigned __int16 *
0x180044fbc  xor     ecx, ecx; pName
0x180044fbe  call    ?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z; InternalGetColorDirectory(ushort const *,ushort *,ulong *)
0x180044fc3  test    eax, eax
0x180044fc5  jz      loc_18004513E
0x180044fcb  lea     rax, [rsp+280h+var_240]
0x180044fd0  lea     r9, [rsp+280h+var_238]; unsigned __int16 **
0x180044fd5  mov     [rsp+280h+var_260], rax; unsigned __int64 *
0x180044fda  lea     rcx, [rsp+280h+pProfileName]; unsigned __int16 *
0x180044fdf  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180044fe4  test    eax, eax
0x180044fe6  js      loc_180045133
0x180044fec  cmp     [rsp+280h+var_240], r14
0x180044ff1  jz      loc_180045133
0x180044ff7  mov     ebx, [rsp+280h+var_250]
0x180044ffb  mov     r15, rsi
0x180044ffe  shr     rbx, 1
0x180045001  cmp     rbx, 1
0x180045005  jbe     loc_18004512B
0x18004500b  mov     rdx, [rsp+280h+var_240]; unsigned __int64
0x180045010  mov     r8, r15; unsigned __int16 *
0x180045013  mov     rcx, [rsp+280h+var_238]; unsigned __int16 *
0x180045018  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004501d  test    eax, eax
0x18004501f  js      loc_180045133
0x180045025  lea     rdx, [rsp+280h+pProfileName]; pProfileName
0x18004502a  xor     ecx, ecx; pMachineName
0x18004502c  call    InstallColorProfileW
0x180045031  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180045036  mov     rdx, rbx; unsigned __int64
0x180045039  mov     rcx, r15; unsigned __int16 *
0x18004503c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180045041  test    eax, eax
0x180045043  js      loc_18004512B
0x180045049  mov     rcx, [rsp+280h+var_248]
0x18004504e  cmp     rbx, rcx
0x180045051  jbe     loc_18004512B
0x180045057  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004505b  lea     r15, [r15+rcx*2]
0x18004505f  sub     rax, rcx
0x180045062  add     rbx, rax
0x180045065  add     r15, 2
0x180045069  jmp     short loc_180045001
0x18004506b  lea     rax, [rsp+280h+var_250]
0x180045070  mov     ebx, 70727472h
0x180045075  mov     r8d, ebx
0x180045078  mov     [rsp+280h+var_260], rax; unsigned int *
0x18004507d  mov     r9d, 1
0x180045083  mov     rdx, r15; unsigned __int16 *
0x180045086  xor     ecx, ecx; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180045088  call    GetDeviceDataSize
0x18004508d  test    eax, eax
0x18004508f  jz      loc_180045146
0x180045095  mov     ecx, [rsp+280h+var_250]
0x180045099  call    MemAlloc
0x18004509e  mov     rsi, rax
0x1800450a1  test    rax, rax
0x1800450a4  jnz     short loc_1800450B6
0x1800450a6  mov     ecx, 0Eh; dwErrCode
0x1800450ab  call    cs:__imp_SetLastError
0x1800450b1  jmp     loc_180045146
0x1800450b6  lea     rax, [rsp+280h+var_250]
0x1800450bb  mov     r9d, 1
0x1800450c1  mov     [rsp+280h+var_258], rax; unsigned int *
0x1800450c6  mov     r8d, ebx
0x1800450c9  mov     rdx, r15; unsigned __int16 *
0x1800450cc  mov     [rsp+280h+var_260], rsi; void *
0x1800450d1  xor     ecx, ecx; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x1800450d3  call    GetDeviceData
0x1800450d8  test    eax, eax
0x1800450da  jz      short loc_18004513E
0x1800450dc  mov     ebx, [rsp+280h+var_250]
0x1800450e0  mov     r14, rsi
0x1800450e3  shr     rbx, 1
0x1800450e6  jmp     short loc_180045125
0x1800450e8  mov     r8, r15; pDeviceName
0x1800450eb  mov     rdx, r14; pProfileName
0x1800450ee  xor     ecx, ecx; pMachineName
0x1800450f0  call    DisassociateColorProfileFromDeviceW
0x1800450f5  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800450fa  mov     rdx, rbx; unsigned __int64
0x1800450fd  mov     rcx, r14; unsigned __int16 *
0x180045100  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180045105  test    eax, eax
0x180045107  js      short loc_18004512B
0x180045109  mov     rcx, [rsp+280h+var_248]
0x18004510e  cmp     rbx, rcx
0x180045111  jbe     short loc_18004512B
0x180045113  or      rax, 0FFFFFFFFFFFFFFFFh
0x180045117  lea     r14, [r14+rcx*2]
0x18004511b  sub     rax, rcx
0x18004511e  add     rbx, rax
0x180045121  add     r14, 2
0x180045125  cmp     rbx, 1
0x180045129  ja      short loc_1800450E8
0x18004512b  mov     r14d, 1
0x180045131  jmp     short loc_18004513E
0x180045133  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180045138  call    cs:__imp_SetLastError
0x18004513e  mov     rcx, rsi; lpMem
0x180045141  call    MemFree
0x180045146  mov     eax, r14d
0x180045149  mov     rcx, [rbp+180h+var_20]
0x180045150  xor     rcx, rsp; StackCookie
0x180045153  call    __security_check_cookie
0x180045158  lea     r11, [rsp+280h+var_10]
0x180045160  mov     rbx, [r11+28h]
0x180045164  mov     rsi, [r11+30h]
0x180045168  mov     rsp, r11
0x18004516b  pop     r15
0x18004516d  pop     r14
0x18004516f  pop     rbp
0x180045170  retn
```
