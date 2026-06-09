# lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)

- ea: `0x18006b9a0`
- end: `0x18006bb7f`
- name: `?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z`
- size: `479`
- prototype: `__int64 __fastcall(unsigned __int8 *, HKEY *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180013eb0`
- `0x180026e38`

## callees

- `0x18006b870`
- `0x18006b9a0`
- `0x18007079c`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006bb4f`
- `KERNEL32!LocalFree` at `0x18006bb4f`
- `KERNEL32!GetLastError` at `0x18006ba66`
- `KERNEL32!GetLastError` at `0x18006ba66`
- `KERNEL32!LocalAlloc` at `0x18006ba58`
- `KERNEL32!LocalAlloc` at `0x18006ba58`
- `ADVAPI32!RegCloseKey` at `0x18006bb0a`
- `ADVAPI32!RegCloseKey` at `0x18006bb3c`
- `ADVAPI32!RegCloseKey` at `0x18006bb0a`
- `ADVAPI32!RegCloseKey` at `0x18006bb3c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x18006ba2f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x18006ba2f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006ba40`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006ba8d`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006ba40`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18006ba8d`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18006bab4`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18006bab4`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18006ba7c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x18006ba7c`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18006bae0`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18006bae0`

## pseudocode

```c
__int64 __fastcall lrGetRegKeyFromGuid(unsigned __int8 *a1, HKEY *a2, unsigned int *a3)
{
  DWORD v5; // ebx
  CONFIGRET Device_ID_List_SizeW; // eax
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  CONFIGRET Device_ID_ListW; // eax
  WCHAR *i; // rsi
  __int64 v12; // rax
  HKEY v13; // rax
  ULONG pulLen; // [rsp+30h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-51h] BYREF
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-49h] BYREF
  int v18; // [rsp+44h] [rbp-45h] BYREF
  GUID v19; // [rsp+48h] [rbp-41h] BYREF
  WCHAR pszFilter[40]; // [rsp+60h] [rbp-29h] BYREF

  hKey = 0;
  v18 = 0;
  pulLen = 0;
  pdnDevInst = 0;
  memset_0(pszFilter, 0, 0x4Eu);
  v19 = GUID_DEVCLASS_NET;
  if ( !(unsigned int)RegHelpStringFromGuid(&v19, pszFilter, 39) )
    return 87;
  Device_ID_List_SizeW = CM_Get_Device_ID_List_SizeW(&pulLen, pszFilter, 0x300u);
  if ( Device_ID_List_SizeW )
    return CM_MapCrToWin32Err(Device_ID_List_SizeW, 0xDu);
  v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * pulLen);
  v9 = v8;
  if ( !v8 )
    return GetLastError();
  Device_ID_ListW = CM_Get_Device_ID_ListW(pszFilter, v8, pulLen, 0x300u);
  if ( Device_ID_ListW )
  {
    v5 = CM_MapCrToWin32Err(Device_ID_ListW, 0xDu);
    goto LABEL_23;
  }
  v5 = 0;
  for ( i = v9; *i; i += v12 + 1 )
  {
    if ( !CM_Locate_DevNodeW(&pdnDevInst, i, 0) && !CM_Open_DevNode_Key(pdnDevInst, 0xF003Fu, 0, 1u, &hKey, 1u) )
    {
      v5 = lrCheckKey(hKey, a1, &v18);
      if ( v5 )
      {
        RegCloseKey(hKey);
        v13 = 0;
        hKey = 0;
LABEL_22:
        *a2 = v13;
        break;
      }
      if ( v18 )
      {
        v13 = hKey;
        goto LABEL_22;
      }
      RegCloseKey(hKey);
    }
    v12 = -1;
    do
      ++v12;
    while ( i[v12] );
  }
LABEL_23:
  LocalFree(v9);
  return v5;
}

```

## disassembly

```asm
0x18006b9a0  mov     [rsp-8+arg_10], rbx
0x18006b9a5  mov     [rsp-8+arg_18], rsi
0x18006b9aa  push    rbp
0x18006b9ab  push    rdi
0x18006b9ac  push    r12
0x18006b9ae  push    r14
0x18006b9b0  push    r15
0x18006b9b2  lea     rbp, [rsp-37h]
0x18006b9b7  sub     rsp, 0C0h
0x18006b9be  mov     rax, cs:__security_cookie
0x18006b9c5  xor     rax, rsp
0x18006b9c8  mov     [rbp+57h+var_30], rax
0x18006b9cc  xor     r12d, r12d
0x18006b9cf  mov     r14, rdx
0x18006b9d2  mov     r15, rcx
0x18006b9d5  mov     [rbp+57h+hKey], r12
0x18006b9d9  xor     edx, edx; Val
0x18006b9db  mov     [rbp+57h+var_9C], r12d
0x18006b9df  lea     rcx, [rbp+57h+pszFilter]; void *
0x18006b9e3  mov     [rbp+57h+pulLen], r12d
0x18006b9e7  lea     r8d, [r12+4Eh]; Size
0x18006b9ec  mov     [rbp+57h+pdnDevInst], r12d
0x18006b9f0  call    memset_0
0x18006b9f5  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_NET.Data1
0x18006b9fc  lea     r8d, [r12+27h]
0x18006ba01  lea     rdx, [rbp+57h+pszFilter]
0x18006ba05  lea     rcx, [rbp+57h+var_98]
0x18006ba09  movdqu  xmmword ptr [rbp+57h+var_98.Data1], xmm0
0x18006ba0e  call    RegHelpStringFromGuid
0x18006ba13  test    eax, eax
0x18006ba15  jnz     short loc_18006BA1F
0x18006ba17  lea     ebx, [rax+57h]
0x18006ba1a  jmp     loc_18006BB55
0x18006ba1f  mov     ebx, 300h
0x18006ba24  lea     rdx, [rbp+57h+pszFilter]; pszFilter
0x18006ba28  mov     r8d, ebx; ulFlags
0x18006ba2b  lea     rcx, [rbp+57h+pulLen]; pulLen
0x18006ba2f  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x18006ba35  test    eax, eax
0x18006ba37  jz      short loc_18006BA4D
0x18006ba39  mov     edx, 0Dh; DefaultErr
0x18006ba3e  mov     ecx, eax; CmReturnCode
0x18006ba40  call    cs:__imp_CM_MapCrToWin32Err
0x18006ba46  mov     ebx, eax
0x18006ba48  jmp     loc_18006BB55
0x18006ba4d  mov     edx, [rbp+57h+pulLen]
0x18006ba50  mov     ecx, 40h ; '@'; uFlags
0x18006ba55  add     rdx, rdx; uBytes
0x18006ba58  call    cs:__imp_LocalAlloc
0x18006ba5e  mov     rdi, rax
0x18006ba61  test    rax, rax
0x18006ba64  jnz     short loc_18006BA6E
0x18006ba66  call    cs:__imp_GetLastError
0x18006ba6c  jmp     short loc_18006BA46
0x18006ba6e  mov     r8d, [rbp+57h+pulLen]; BufferLen
0x18006ba72  lea     rcx, [rbp+57h+pszFilter]; pszFilter
0x18006ba76  mov     r9d, ebx; ulFlags
0x18006ba79  mov     rdx, rdi; Buffer
0x18006ba7c  call    cs:__imp_CM_Get_Device_ID_ListW
0x18006ba82  test    eax, eax
0x18006ba84  jz      short loc_18006BA9A
0x18006ba86  mov     edx, 0Dh; DefaultErr
0x18006ba8b  mov     ecx, eax; CmReturnCode
0x18006ba8d  call    cs:__imp_CM_MapCrToWin32Err
0x18006ba93  mov     ebx, eax
0x18006ba95  jmp     loc_18006BB4C
0x18006ba9a  mov     ebx, r12d
0x18006ba9d  mov     rsi, rdi
0x18006baa0  cmp     [rdi], r12w
0x18006baa4  jz      loc_18006BB4C
0x18006baaa  xor     r8d, r8d; ulFlags
0x18006baad  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x18006bab1  mov     rdx, rsi; pDeviceID
0x18006bab4  call    cs:__imp_CM_Locate_DevNodeW
0x18006baba  test    eax, eax
0x18006babc  jnz     short loc_18006BB10
0x18006babe  mov     ecx, [rbp+57h+pdnDevInst]; dnDevNode
0x18006bac1  lea     rax, [rbp+57h+hKey]
0x18006bac5  mov     [rsp+0E0h+ulFlags], 1; ulFlags
0x18006bacd  mov     r9d, 1; Disposition
0x18006bad3  xor     r8d, r8d; ulHardwareProfile
0x18006bad6  mov     [rsp+0E0h+phkDevice], rax; phkDevice
0x18006badb  mov     edx, 0F003Fh; samDesired
0x18006bae0  call    cs:__imp_CM_Open_DevNode_Key
0x18006bae6  test    eax, eax
0x18006bae8  jnz     short loc_18006BB10
0x18006baea  mov     rcx, [rbp+57h+hKey]; hKey
0x18006baee  lea     r8, [rbp+57h+var_9C]; int *
0x18006baf2  mov     rdx, r15; unsigned __int8 *
0x18006baf5  call    ?lrCheckKey@@YAJPEAUHKEY__@@PEAEPEAH@Z; lrCheckKey(HKEY__ *,uchar *,int *)
0x18006bafa  mov     ebx, eax
0x18006bafc  test    eax, eax
0x18006bafe  jnz     short loc_18006BB38
0x18006bb00  cmp     [rbp+57h+var_9C], r12d
0x18006bb04  jnz     short loc_18006BB32
0x18006bb06  mov     rcx, [rbp+57h+hKey]; hKey
0x18006bb0a  call    cs:__imp_RegCloseKey
0x18006bb10  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006bb14  inc     rax
0x18006bb17  cmp     [rsi+rax*2], r12w
0x18006bb1c  jnz     short loc_18006BB14
0x18006bb1e  lea     rsi, [rsi+rax*2]
0x18006bb22  add     rsi, 2
0x18006bb26  cmp     [rsi], r12w
0x18006bb2a  jnz     loc_18006BAAA
0x18006bb30  jmp     short loc_18006BB4C
0x18006bb32  mov     rax, [rbp+57h+hKey]
0x18006bb36  jmp     short loc_18006BB49
0x18006bb38  mov     rcx, [rbp+57h+hKey]; hKey
0x18006bb3c  call    cs:__imp_RegCloseKey
0x18006bb42  mov     rax, r12
0x18006bb45  mov     [rbp+57h+hKey], rax
0x18006bb49  mov     [r14], rax
0x18006bb4c  mov     rcx, rdi; hMem
0x18006bb4f  call    cs:__imp_LocalFree
0x18006bb55  mov     eax, ebx
0x18006bb57  mov     rcx, [rbp+57h+var_30]
0x18006bb5b  xor     rcx, rsp; StackCookie
0x18006bb5e  call    __security_check_cookie
0x18006bb63  lea     r11, [rsp+0E0h+var_20]
0x18006bb6b  mov     rbx, [r11+40h]
0x18006bb6f  mov     rsi, [r11+48h]
0x18006bb73  mov     rsp, r11
0x18006bb76  pop     r15
0x18006bb78  pop     r14
0x18006bb7a  pop     r12
0x18006bb7c  pop     rdi
0x18006bb7d  pop     rbp
0x18006bb7e  retn
```
