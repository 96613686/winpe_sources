# CMbaeMutexFactory::_OpenOrCreateMutex(void * *)

- ea: `0x180031c28`
- end: `0x180031def`
- name: `?_OpenOrCreateMutex@CMbaeMutexFactory@@CAJPEAPEAX@Z`
- size: `455`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031744`

## callees

- `0x1800024e0`
- `0x180009ffc`
- `0x180014410`
- `0x180031aec`
- `0x180031c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180031c6c`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180031c6c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180031d69`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180031d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d8b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180031d4a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180031d4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031d80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031d80`

## string_xrefs

- `0x180031cfe`: `CMbaeMutexFactory::_OpenOrCreateMutex`
- `0x180031db3`: `CMbaeMutexFactory::_OpenOrCreateMutex`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMbaeMutexFactory::_OpenOrCreateMutex(void **a1)
{
  signed int v2; // ebx
  __int64 v3; // rcx
  HANDLE v4; // rdi
  signed int LastError; // eax
  __int64 v6; // r9
  __int64 *v7; // rdx
  int CurrentUserSid; // eax
  HLOCAL v9; // rsi
  signed int v10; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR StringSecurityDescriptor[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
  *a1 = 0;
  v4 = OpenMutexW(0x100000u, 0, L"Global\\mbaeapi.mutex");
  if ( v4 )
  {
LABEL_20:
    *a1 = v4;
    goto LABEL_21;
  }
  if ( GetLastError() != 2 )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 < 0 )
    {
      if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 2) == 0 )
        goto LABEL_21;
      v6 = (unsigned int)v2;
      v7 = CMbaeMutexFactory_cpp214;
LABEL_11:
      McTemplateU0sd_EventWriteTransfer(v3, v7, "CMbaeMutexFactory::_OpenOrCreateMutex", v6);
      goto LABEL_21;
    }
    goto LABEL_20;
  }
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  MutexAttributes.lpSecurityDescriptor = 0;
  hMem = 0;
  CurrentUserSid = CMbaeMutexFactory::_GetCurrentUserSid((unsigned __int16 **)&hMem);
  v2 = CurrentUserSid;
  if ( CurrentUserSid < 0 )
  {
    if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 2) == 0 )
      goto LABEL_21;
    v6 = (unsigned int)CurrentUserSid;
    v7 = CMbaeMutexFactory_cpp237;
    goto LABEL_11;
  }
  v9 = hMem;
  if ( (int)StringCchPrintfW(
              StringSecurityDescriptor,
              0x400u,
              L"D:(A;;0x%08x;;;%s)(A;;GA;;;BA)(A;;GA;;;SY)",
              2031617,
              hMem) >= 0 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           StringSecurityDescriptor,
           1u,
           &MutexAttributes.lpSecurityDescriptor,
           0) )
    {
      v4 = CreateMutexExW(&MutexAttributes, L"Global\\mbaeapi.mutex", 0, 0x1F0001u);
    }
    LocalFree(MutexAttributes.lpSecurityDescriptor);
  }
  LocalFree(v9);
  if ( v4 )
    goto LABEL_20;
  v10 = GetLastError();
  v2 = v10;
  if ( v10 > 0 )
    v2 = (unsigned __int16)v10 | 0x80070000;
  if ( v2 >= 0 )
    goto LABEL_20;
LABEL_21:
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    McTemplateU0sd_EventWriteTransfer(
      v3,
      CMbaeMutexFactory_cpp269,
      "CMbaeMutexFactory::_OpenOrCreateMutex",
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180031c28  mov     [rsp-8+arg_8], rbx
0x180031c2d  mov     [rsp-8+arg_10], rsi
0x180031c32  push    rbp
0x180031c33  push    rdi
0x180031c34  push    r14
0x180031c36  lea     rbp, [rsp-760h]
0x180031c3e  sub     rsp, 860h
0x180031c45  mov     rax, cs:__security_cookie
0x180031c4c  xor     rax, rsp
0x180031c4f  mov     [rbp+770h+var_20], rax
0x180031c56  mov     r14, rcx
0x180031c59  lea     r8, Name; "Global\\mbaeapi.mutex"
0x180031c60  xor     ebx, ebx
0x180031c62  xor     edx, edx; bInheritHandle
0x180031c64  mov     [rcx], rbx
0x180031c67  mov     ecx, 100000h; dwDesiredAccess
0x180031c6c  call    cs:__imp_OpenMutexW
0x180031c72  mov     rdi, rax
0x180031c75  test    rax, rax
0x180031c78  jnz     loc_180031DA4
0x180031c7e  call    cs:__imp_GetLastError
0x180031c84  cmp     eax, 2
0x180031c87  jz      short loc_180031CBF
0x180031c89  call    cs:__imp_GetLastError
0x180031c8f  mov     ebx, eax
0x180031c91  test    eax, eax
0x180031c93  jle     short loc_180031C9E
0x180031c95  movzx   ebx, ax
0x180031c98  or      ebx, 80070000h
0x180031c9e  test    ebx, ebx
0x180031ca0  jns     loc_180031DA4
0x180031ca6  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 2
0x180031cad  jz      loc_180031DA7
0x180031cb3  mov     r9d, ebx
0x180031cb6  lea     rdx, CMbaeMutexFactory_cpp214
0x180031cbd  jmp     short loc_180031CFE
0x180031cbf  lea     rcx, [rsp+870h+hMem]; unsigned __int16 **
0x180031cc4  mov     qword ptr [rsp+870h+MutexAttributes.nLength], 18h
0x180031ccd  mov     qword ptr [rsp+870h+MutexAttributes.bInheritHandle], rbx
0x180031cd2  mov     [rsp+870h+MutexAttributes.lpSecurityDescriptor], rbx
0x180031cd7  mov     [rsp+870h+hMem], rbx
0x180031cdc  call    ?_GetCurrentUserSid@CMbaeMutexFactory@@CAJPEAPEAG@Z; CMbaeMutexFactory::_GetCurrentUserSid(ushort * *)
0x180031ce1  mov     ebx, eax
0x180031ce3  test    eax, eax
0x180031ce5  jns     short loc_180031D0F
0x180031ce7  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 2
0x180031cee  jz      loc_180031DA7
0x180031cf4  mov     r9d, eax
0x180031cf7  lea     rdx, CMbaeMutexFactory_cpp237
0x180031cfe  lea     r8, aCmbaemutexfact_1; "CMbaeMutexFactory::_OpenOrCreateMutex"
0x180031d05  call    McTemplateU0sd_EventWriteTransfer
0x180031d0a  jmp     loc_180031DA7
0x180031d0f  mov     rsi, [rsp+870h+hMem]
0x180031d14  lea     r8, aDA0x08xSAGaBaA; "D:(A;;0x%08x;;;%s)(A;;GA;;;BA)(A;;GA;;;"...
0x180031d1b  mov     r9d, 1F0001h
0x180031d21  mov     [rsp+870h+var_850], rsi
0x180031d26  mov     edx, 400h; unsigned __int64
0x180031d2b  lea     rcx, [rsp+870h+StringSecurityDescriptor]; unsigned __int16 *
0x180031d30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180031d35  test    eax, eax
0x180031d37  js      short loc_180031D7D
0x180031d39  xor     r9d, r9d; SecurityDescriptorSize
0x180031d3c  lea     r8, [rsp+870h+MutexAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x180031d41  lea     rcx, [rsp+870h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180031d46  lea     edx, [r9+1]; StringSDRevision
0x180031d4a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180031d50  test    eax, eax
0x180031d52  jz      short loc_180031D72
0x180031d54  mov     r9d, 1F0001h; dwDesiredAccess
0x180031d5a  lea     rdx, Name; "Global\\mbaeapi.mutex"
0x180031d61  xor     r8d, r8d; dwFlags
0x180031d64  lea     rcx, [rsp+870h+MutexAttributes]; lpMutexAttributes
0x180031d69  call    cs:__imp_CreateMutexExW
0x180031d6f  mov     rdi, rax
0x180031d72  mov     rcx, [rsp+870h+MutexAttributes.lpSecurityDescriptor]; hMem
0x180031d77  call    cs:__imp_LocalFree
0x180031d7d  mov     rcx, rsi; hMem
0x180031d80  call    cs:__imp_LocalFree
0x180031d86  test    rdi, rdi
0x180031d89  jnz     short loc_180031DA4
0x180031d8b  call    cs:__imp_GetLastError
0x180031d91  mov     ebx, eax
0x180031d93  test    eax, eax
0x180031d95  jle     short loc_180031DA0
0x180031d97  movzx   ebx, ax
0x180031d9a  or      ebx, 80070000h
0x180031da0  test    ebx, ebx
0x180031da2  js      short loc_180031DA7
0x180031da4  mov     [r14], rdi
0x180031da7  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x180031dae  jz      short loc_180031DC6
0x180031db0  mov     r9d, ebx
0x180031db3  lea     r8, aCmbaemutexfact_1; "CMbaeMutexFactory::_OpenOrCreateMutex"
0x180031dba  lea     rdx, CMbaeMutexFactory_cpp269
0x180031dc1  call    McTemplateU0sd_EventWriteTransfer
0x180031dc6  mov     eax, ebx
0x180031dc8  mov     rcx, [rbp+770h+var_20]
0x180031dcf  xor     rcx, rsp; StackCookie
0x180031dd2  call    __security_check_cookie
0x180031dd7  lea     r11, [rsp+870h+var_10]
0x180031ddf  mov     rbx, [r11+28h]
0x180031de3  mov     rsi, [r11+30h]
0x180031de7  mov     rsp, r11
0x180031dea  pop     r14
0x180031dec  pop     rdi
0x180031ded  pop     rbp
0x180031dee  retn
```
