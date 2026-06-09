# lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)

- ea: `0x18006e4dc`
- end: `0x18006e6f3`
- name: `?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z`
- size: `535`
- prototype: `__int64 __fastcall(unsigned __int8 *, HKEY *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014270`
- `0x180029100`

## callees

- `0x18006e38c`
- `0x18006e4dc`
- `0x180073f90`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006e6bc`
- `KERNEL32!LocalFree` at `0x18006e6bc`
- `KERNEL32!GetLastError` at `0x18006e5b1`
- `KERNEL32!GetLastError` at `0x18006e5b1`
- `KERNEL32!LocalAlloc` at `0x18006e59d`
- `KERNEL32!LocalAlloc` at `0x18006e59d`
- `ADVAPI32!RegCloseKey` at `0x18006e66e`
- `ADVAPI32!RegCloseKey` at `0x18006e6a6`
- `ADVAPI32!RegCloseKey` at `0x18006e66e`
- `ADVAPI32!RegCloseKey` at `0x18006e6a6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x18006e568`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x18006e568`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006e57f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006e5e4`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006e57f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006e5e4`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18006e60d`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18006e60d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18006e5cd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18006e5cd`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18006e63f`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18006e63f`

## pseudocode

```c
__int64 __fastcall lrGetRegKeyFromGuid(unsigned __int8 *a1, HKEY *a2, unsigned int *a3)
{
  HKEY v3; // rbx
  DWORD v6; // edi
  CONFIGRET Device_ID_List_SizeW; // eax
  WCHAR *v9; // rax
  WCHAR *v10; // rsi
  CONFIGRET Device_ID_ListW; // eax
  WCHAR *i; // r14
  __int64 v13; // rax
  ULONG pulLen; // [rsp+30h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-49h] BYREF
  int v18; // [rsp+44h] [rbp-45h] BYREF
  GUID v19; // [rsp+48h] [rbp-41h] BYREF
  WCHAR pszFilter[40]; // [rsp+60h] [rbp-29h] BYREF

  v3 = 0;
  hKey = 0;
  v18 = 0;
  pulLen = 0;
  pdnDevInst = 0;
  v6 = 0;
  memset_0(pszFilter, 0, 0x4Eu);
  v19 = GUID_DEVCLASS_NET;
  if ( !(unsigned int)RegHelpStringFromGuid(&v19, pszFilter, 39) )
    return 87;
  Device_ID_List_SizeW = CM_Get_Device_ID_List_SizeW(&pulLen, pszFilter, 0x300u);
  if ( Device_ID_List_SizeW )
    return CM_MapCrToWin32Err(Device_ID_List_SizeW, 0xDu);
  v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * pulLen);
  v10 = v9;
  if ( !v9 )
    return GetLastError();
  Device_ID_ListW = CM_Get_Device_ID_ListW(pszFilter, v9, pulLen, 0x300u);
  if ( Device_ID_ListW )
  {
    v6 = CM_MapCrToWin32Err(Device_ID_ListW, 0xDu);
    goto LABEL_23;
  }
  for ( i = v10; *i; i += v13 + 1 )
  {
    if ( !CM_Locate_DevNodeW(&pdnDevInst, i, 0) && !CM_Open_DevNode_Key(pdnDevInst, 0xF003Fu, 0, 1u, &hKey, 1u) )
    {
      v6 = lrCheckKey(hKey, a1, &v18);
      if ( v6 )
      {
        RegCloseKey(hKey);
        hKey = 0;
LABEL_22:
        *a2 = v3;
        break;
      }
      if ( v18 )
      {
        v3 = hKey;
        goto LABEL_22;
      }
      RegCloseKey(hKey);
    }
    v13 = -1;
    do
      ++v13;
    while ( i[v13] );
  }
LABEL_23:
  LocalFree(v10);
  return v6;
}

```

## disassembly

```asm
0x18006e4dc  mov     [rsp-8+arg_10], rbx
0x18006e4e1  mov     [rsp-8+arg_18], rsi
0x18006e4e6  push    rbp
0x18006e4e7  push    rdi
0x18006e4e8  push    r12
0x18006e4ea  push    r14
0x18006e4ec  push    r15
0x18006e4ee  lea     rbp, [rsp-37h]
0x18006e4f3  sub     rsp, 0C0h
0x18006e4fa  mov     rax, cs:__security_cookie
0x18006e501  xor     rax, rsp
0x18006e504  mov     [rbp+57h+var_30], rax
0x18006e508  xor     ebx, ebx
0x18006e50a  mov     r15, rdx
0x18006e50d  mov     r12, rcx
0x18006e510  mov     [rbp+57h+hKey], rbx
0x18006e514  xor     edx, edx; Val
0x18006e516  mov     [rbp+57h+var_9C], ebx
0x18006e519  lea     rcx, [rbp+57h+pszFilter]; void *
0x18006e51d  mov     [rbp+57h+pulLen], ebx
0x18006e520  lea     r8d, [rbx+4Eh]; Size
0x18006e524  mov     [rbp+57h+pdnDevInst], ebx
0x18006e527  mov     edi, ebx
0x18006e529  call    memset_0
0x18006e52e  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_NET.Data1
0x18006e535  lea     r8d, [rbx+27h]
0x18006e539  lea     rdx, [rbp+57h+pszFilter]
0x18006e53d  lea     rcx, [rbp+57h+var_98]
0x18006e541  movdqu  xmmword ptr [rbp+57h+var_98.Data1], xmm0
0x18006e546  call    RegHelpStringFromGuid
0x18006e54b  test    eax, eax
0x18006e54d  jnz     short loc_18006E557
0x18006e54f  lea     edi, [rbx+57h]
0x18006e552  jmp     loc_18006E6C8
0x18006e557  mov     r14d, 300h
0x18006e55d  lea     rdx, [rbp+57h+pszFilter]; pszFilter
0x18006e561  mov     r8d, r14d; ulFlags
0x18006e564  lea     rcx, [rbp+57h+pulLen]; pulLen
0x18006e568  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x18006e56f  nop     dword ptr [rax+rax+00h]
0x18006e574  test    eax, eax
0x18006e576  jz      short loc_18006E592
0x18006e578  mov     edx, 0Dh; DefaultErr
0x18006e57d  mov     ecx, eax; CmReturnCode
0x18006e57f  call    cs:__imp_CM_MapCrToWin32Err
0x18006e586  nop     dword ptr [rax+rax+00h]
0x18006e58b  mov     edi, eax
0x18006e58d  jmp     loc_18006E6C8
0x18006e592  mov     edx, [rbp+57h+pulLen]
0x18006e595  mov     ecx, 40h ; '@'; uFlags
0x18006e59a  add     rdx, rdx; uBytes
0x18006e59d  call    cs:__imp_LocalAlloc
0x18006e5a4  nop     dword ptr [rax+rax+00h]
0x18006e5a9  mov     rsi, rax
0x18006e5ac  test    rax, rax
0x18006e5af  jnz     short loc_18006E5BF
0x18006e5b1  call    cs:__imp_GetLastError
0x18006e5b8  nop     dword ptr [rax+rax+00h]
0x18006e5bd  jmp     short loc_18006E58B
0x18006e5bf  mov     r8d, [rbp+57h+pulLen]; BufferLen
0x18006e5c3  lea     rcx, [rbp+57h+pszFilter]; pszFilter
0x18006e5c7  mov     r9d, r14d; ulFlags
0x18006e5ca  mov     rdx, rsi; Buffer
0x18006e5cd  call    cs:__imp_CM_Get_Device_ID_ListW
0x18006e5d4  nop     dword ptr [rax+rax+00h]
0x18006e5d9  test    eax, eax
0x18006e5db  jz      short loc_18006E5F7
0x18006e5dd  mov     edx, 0Dh; DefaultErr
0x18006e5e2  mov     ecx, eax; CmReturnCode
0x18006e5e4  call    cs:__imp_CM_MapCrToWin32Err
0x18006e5eb  nop     dword ptr [rax+rax+00h]
0x18006e5f0  mov     edi, eax
0x18006e5f2  jmp     loc_18006E6B9
0x18006e5f7  mov     r14, rsi
0x18006e5fa  cmp     [rsi], bx
0x18006e5fd  jz      loc_18006E6B9
0x18006e603  xor     r8d, r8d; ulFlags
0x18006e606  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x18006e60a  mov     rdx, r14; pDeviceID
0x18006e60d  call    cs:__imp_CM_Locate_DevNodeW
0x18006e614  nop     dword ptr [rax+rax+00h]
0x18006e619  test    eax, eax
0x18006e61b  jnz     short loc_18006E67A
0x18006e61d  mov     ecx, [rbp+57h+pdnDevInst]; dnDevNode
0x18006e620  lea     rax, [rbp+57h+hKey]
0x18006e624  mov     [rsp+0E0h+ulFlags], 1; ulFlags
0x18006e62c  mov     r9d, 1; Disposition
0x18006e632  xor     r8d, r8d; ulHardwareProfile
0x18006e635  mov     [rsp+0E0h+phkDevice], rax; phkDevice
0x18006e63a  mov     edx, 0F003Fh; samDesired
0x18006e63f  call    cs:__imp_CM_Open_DevNode_Key
0x18006e646  nop     dword ptr [rax+rax+00h]
0x18006e64b  test    eax, eax
0x18006e64d  jnz     short loc_18006E67A
0x18006e64f  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e653  lea     r8, [rbp+57h+var_9C]; int *
0x18006e657  mov     rdx, r12; unsigned __int8 *
0x18006e65a  call    ?lrCheckKey@@YAJPEAUHKEY__@@PEAEPEAH@Z; lrCheckKey(HKEY__ *,uchar *,int *)
0x18006e65f  mov     edi, eax
0x18006e661  test    eax, eax
0x18006e663  jnz     short loc_18006E6A2
0x18006e665  cmp     [rbp+57h+var_9C], ebx
0x18006e668  jnz     short loc_18006E69C
0x18006e66a  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e66e  call    cs:__imp_RegCloseKey
0x18006e675  nop     dword ptr [rax+rax+00h]
0x18006e67a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e67e  inc     rax
0x18006e681  cmp     [r14+rax*2], bx
0x18006e686  jnz     short loc_18006E67E
0x18006e688  lea     r14, [r14+rax*2]
0x18006e68c  add     r14, 2
0x18006e690  cmp     [r14], bx
0x18006e694  jnz     loc_18006E603
0x18006e69a  jmp     short loc_18006E6B9
0x18006e69c  mov     rbx, [rbp+57h+hKey]
0x18006e6a0  jmp     short loc_18006E6B6
0x18006e6a2  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e6a6  call    cs:__imp_RegCloseKey
0x18006e6ad  nop     dword ptr [rax+rax+00h]
0x18006e6b2  mov     [rbp+57h+hKey], rbx
0x18006e6b6  mov     [r15], rbx
0x18006e6b9  mov     rcx, rsi; hMem
0x18006e6bc  call    cs:__imp_LocalFree
0x18006e6c3  nop     dword ptr [rax+rax+00h]
0x18006e6c8  mov     eax, edi
0x18006e6ca  mov     rcx, [rbp+57h+var_30]
0x18006e6ce  xor     rcx, rsp; StackCookie
0x18006e6d1  call    __security_check_cookie
0x18006e6d6  lea     r11, [rsp+0E0h+var_20]
0x18006e6de  mov     rbx, [r11+40h]
0x18006e6e2  mov     rsi, [r11+48h]
0x18006e6e6  mov     rsp, r11
0x18006e6e9  pop     r15
0x18006e6eb  pop     r14
0x18006e6ed  pop     r12
0x18006e6ef  pop     rdi
0x18006e6f0  pop     rbp
0x18006e6f1  retn
```
