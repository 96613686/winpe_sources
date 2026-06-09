# lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)

- ea: `0x180016b30`
- end: `0x180016d3a`
- name: `?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z`
- size: `522`
- prototype: `__int64 __fastcall(unsigned __int8 *, HKEY *, unsigned int *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800030f0`
- `0x1800173a4`
- `0x1800175d8`

## callees

- `0x180016948`
- `0x180016a74`
- `0x180016b30`
- `0x180020988`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016bf0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016bf0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d0b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016bfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016cad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016cdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016cad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016cdf`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x180016bc7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x180016bc7`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180016c4a`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180016c4a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x180016c14`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x180016c14`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180016c74`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x180016c74`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180016bd8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180016c25`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180016bd8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180016c25`

## pseudocode

```c
__int64 __fastcall lrGetRegKeyFromGuid(WCHAR *a1, HKEY *a2, unsigned int *a3, int a4)
{
  DWORD v4; // ebx
  GUID v9; // xmm0
  CONFIGRET Device_ID_List_SizeW; // eax
  WCHAR *v12; // rax
  WCHAR *v13; // rdi
  CONFIGRET Device_ID_ListW; // eax
  WCHAR *i; // rsi
  DWORD v16; // eax
  __int64 v17; // rax
  HKEY v18; // rax
  ULONG pulLen; // [rsp+30h] [rbp-69h] BYREF
  int v21; // [rsp+34h] [rbp-65h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-61h] BYREF
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-59h] BYREF
  GUID v24; // [rsp+48h] [rbp-51h] BYREF
  WCHAR pszFilter[40]; // [rsp+60h] [rbp-39h] BYREF

  v4 = 0;
  hKey = 0;
  v21 = 0;
  pulLen = 0;
  pdnDevInst = 0;
  memset_0(pszFilter, 0, 0x4Eu);
  if ( a4 )
    v9 = GUID_DEVCLASS_MODEM;
  else
    v9 = GUID_DEVCLASS_NET;
  v24 = v9;
  if ( !(unsigned int)RegHelpStringFromGuid(&v24, pszFilter) )
    return 87;
  Device_ID_List_SizeW = CM_Get_Device_ID_List_SizeW(&pulLen, pszFilter, 0x300u);
  if ( Device_ID_List_SizeW )
    return CM_MapCrToWin32Err(Device_ID_List_SizeW, 0xDu);
  v12 = (WCHAR *)LocalAlloc(0x40u, 2LL * pulLen);
  v13 = v12;
  if ( !v12 )
    return GetLastError();
  Device_ID_ListW = CM_Get_Device_ID_ListW(pszFilter, v12, pulLen, 0x300u);
  if ( Device_ID_ListW )
  {
    v4 = CM_MapCrToWin32Err(Device_ID_ListW, 0xDu);
    goto LABEL_30;
  }
  for ( i = v13; *i; i += v17 + 1 )
  {
    if ( !CM_Locate_DevNodeW(&pdnDevInst, i, 0) && !CM_Open_DevNode_Key(pdnDevInst, 0xF003Fu, 0, 1u, &hKey, 1u) )
    {
      if ( a4 )
        v16 = lrCheckModemKey(hKey, a1, &v21);
      else
        v16 = lrCheckKey(hKey, (unsigned __int8 *)a1, &v21);
      v4 = v16;
      if ( v16 )
      {
        RegCloseKey(hKey);
        v18 = 0;
        hKey = 0;
LABEL_28:
        *a2 = v18;
        if ( a3 )
          *a3 = _InterlockedIncrement((volatile signed __int32 *)&g_dwInstanceNumber);
        break;
      }
      if ( v21 )
      {
        v18 = hKey;
        goto LABEL_28;
      }
      RegCloseKey(hKey);
    }
    v17 = -1;
    do
      ++v17;
    while ( i[v17] );
  }
LABEL_30:
  LocalFree(v13);
  return v4;
}

```

## disassembly

```asm
0x180016b30  mov     [rsp-8+arg_18], rbx
0x180016b35  push    rbp
0x180016b36  push    rsi
0x180016b37  push    rdi
0x180016b38  push    r12
0x180016b3a  push    r13
0x180016b3c  push    r14
0x180016b3e  push    r15
0x180016b40  lea     rbp, [rsp-27h]
0x180016b45  sub     rsp, 0C0h
0x180016b4c  mov     rax, cs:__security_cookie
0x180016b53  xor     rax, rsp
0x180016b56  mov     [rbp+57h+var_40], rax
0x180016b5a  xor     ebx, ebx
0x180016b5c  mov     r14, r8
0x180016b5f  mov     r13, rdx
0x180016b62  mov     [rbp+57h+hKey], rbx
0x180016b66  mov     r12, rcx
0x180016b69  mov     [rbp+57h+var_BC], ebx
0x180016b6c  xor     edx, edx; Val
0x180016b6e  mov     [rbp+57h+pulLen], ebx
0x180016b71  lea     r8d, [rbx+4Eh]; Size
0x180016b75  mov     [rbp+57h+pdnDevInst], ebx
0x180016b78  lea     rcx, [rbp+57h+pszFilter]; void *
0x180016b7c  mov     r15d, r9d
0x180016b7f  call    memset_0
0x180016b84  test    r15d, r15d
0x180016b87  jnz     short loc_180016B92
0x180016b89  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_NET.Data1
0x180016b90  jmp     short loc_180016B99
0x180016b92  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_MODEM.Data1
0x180016b99  lea     rdx, [rbp+57h+pszFilter]
0x180016b9d  lea     rcx, [rbp+57h+var_A8]
0x180016ba1  movdqu  xmmword ptr [rbp+57h+var_A8.Data1], xmm0
0x180016ba6  call    RegHelpStringFromGuid
0x180016bab  test    eax, eax
0x180016bad  jnz     short loc_180016BB7
0x180016baf  lea     ebx, [rax+57h]
0x180016bb2  jmp     loc_180016D11
0x180016bb7  mov     esi, 300h
0x180016bbc  lea     rdx, [rbp+57h+pszFilter]; pszFilter
0x180016bc0  mov     r8d, esi; ulFlags
0x180016bc3  lea     rcx, [rbp+57h+pulLen]; pulLen
0x180016bc7  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x180016bcd  test    eax, eax
0x180016bcf  jz      short loc_180016BE5
0x180016bd1  mov     edx, 0Dh; DefaultErr
0x180016bd6  mov     ecx, eax; CmReturnCode
0x180016bd8  call    cs:__imp_CM_MapCrToWin32Err
0x180016bde  mov     ebx, eax
0x180016be0  jmp     loc_180016D11
0x180016be5  mov     edx, [rbp+57h+pulLen]
0x180016be8  mov     ecx, 40h ; '@'; uFlags
0x180016bed  add     rdx, rdx; uBytes
0x180016bf0  call    cs:__imp_LocalAlloc
0x180016bf6  mov     rdi, rax
0x180016bf9  test    rax, rax
0x180016bfc  jnz     short loc_180016C06
0x180016bfe  call    cs:__imp_GetLastError
0x180016c04  jmp     short loc_180016BDE
0x180016c06  mov     r8d, [rbp+57h+pulLen]; BufferLen
0x180016c0a  lea     rcx, [rbp+57h+pszFilter]; pszFilter
0x180016c0e  mov     r9d, esi; ulFlags
0x180016c11  mov     rdx, rdi; Buffer
0x180016c14  call    cs:__imp_CM_Get_Device_ID_ListW
0x180016c1a  test    eax, eax
0x180016c1c  jz      short loc_180016C32
0x180016c1e  mov     edx, 0Dh; DefaultErr
0x180016c23  mov     ecx, eax; CmReturnCode
0x180016c25  call    cs:__imp_CM_MapCrToWin32Err
0x180016c2b  mov     ebx, eax
0x180016c2d  jmp     loc_180016D08
0x180016c32  xor     ecx, ecx
0x180016c34  mov     rsi, rdi
0x180016c37  cmp     [rdi], cx
0x180016c3a  jz      loc_180016D08
0x180016c40  xor     r8d, r8d; ulFlags
0x180016c43  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x180016c47  mov     rdx, rsi; pDeviceID
0x180016c4a  call    cs:__imp_CM_Locate_DevNodeW
0x180016c50  xor     ecx, ecx
0x180016c52  test    eax, eax
0x180016c54  jnz     short loc_180016CB5
0x180016c56  lea     ecx, [rax+1]
0x180016c59  xor     r8d, r8d; ulHardwareProfile
0x180016c5c  mov     [rsp+0F0h+ulFlags], ecx; ulFlags
0x180016c60  lea     rax, [rbp+57h+hKey]
0x180016c64  mov     r9d, ecx; Disposition
0x180016c67  mov     [rsp+0F0h+phkDevice], rax; phkDevice
0x180016c6c  mov     ecx, [rbp+57h+pdnDevInst]; dnDevNode
0x180016c6f  mov     edx, 0F003Fh; samDesired
0x180016c74  call    cs:__imp_CM_Open_DevNode_Key
0x180016c7a  xor     ecx, ecx
0x180016c7c  test    eax, eax
0x180016c7e  jnz     short loc_180016CB5
0x180016c80  mov     rcx, [rbp+57h+hKey]; hKey
0x180016c84  lea     r8, [rbp+57h+var_BC]; int *
0x180016c88  mov     rdx, r12; lpString1
0x180016c8b  test    r15d, r15d
0x180016c8e  jnz     short loc_180016C97
0x180016c90  call    ?lrCheckKey@@YAJPEAUHKEY__@@PEAEPEAH@Z; lrCheckKey(HKEY__ *,uchar *,int *)
0x180016c95  jmp     short loc_180016C9C
0x180016c97  call    ?lrCheckModemKey@@YAJPEAUHKEY__@@PEAEPEAH@Z; lrCheckModemKey(HKEY__ *,uchar *,int *)
0x180016c9c  mov     ebx, eax
0x180016c9e  xor     eax, eax
0x180016ca0  test    ebx, ebx
0x180016ca2  jnz     short loc_180016CDB
0x180016ca4  cmp     [rbp+57h+var_BC], eax
0x180016ca7  jnz     short loc_180016CD5
0x180016ca9  mov     rcx, [rbp+57h+hKey]; hKey
0x180016cad  call    cs:__imp_RegCloseKey
0x180016cb3  xor     ecx, ecx
0x180016cb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016cb9  inc     rax
0x180016cbc  cmp     [rsi+rax*2], cx
0x180016cc0  jnz     short loc_180016CB9
0x180016cc2  lea     rsi, [rsi+rax*2]
0x180016cc6  add     rsi, 2
0x180016cca  cmp     [rsi], cx
0x180016ccd  jnz     loc_180016C40
0x180016cd3  jmp     short loc_180016D08
0x180016cd5  mov     rax, [rbp+57h+hKey]
0x180016cd9  jmp     short loc_180016CED
0x180016cdb  mov     rcx, [rbp+57h+hKey]; hKey
0x180016cdf  call    cs:__imp_RegCloseKey
0x180016ce5  xor     ecx, ecx
0x180016ce7  mov     eax, ecx
0x180016ce9  mov     [rbp+57h+hKey], rcx
0x180016ced  mov     [r13+0], rax
0x180016cf1  test    r14, r14
0x180016cf4  jz      short loc_180016D08
0x180016cf6  mov     eax, 1
0x180016cfb  lock xadd cs:?g_dwInstanceNumber@@3KA, eax; ulong g_dwInstanceNumber
0x180016d03  inc     eax
0x180016d05  mov     [r14], eax
0x180016d08  mov     rcx, rdi; hMem
0x180016d0b  call    cs:__imp_LocalFree
0x180016d11  mov     eax, ebx
0x180016d13  mov     rcx, [rbp+57h+var_40]
0x180016d17  xor     rcx, rsp; StackCookie
0x180016d1a  call    __security_check_cookie
0x180016d1f  mov     rbx, [rsp+0F0h+arg_18]
0x180016d27  add     rsp, 0C0h
0x180016d2e  pop     r15
0x180016d30  pop     r14
0x180016d32  pop     r13
0x180016d34  pop     r12
0x180016d36  pop     rdi
0x180016d37  pop     rsi
0x180016d38  pop     rbp
0x180016d39  retn
```
