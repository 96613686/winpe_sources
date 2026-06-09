# CDeviceCollection::CheckDeviceReady(ushort *)

- ea: `0x18056dd58`
- end: `0x18056e018`
- name: `?CheckDeviceReady@CDeviceCollection@@AEAAHPEAG@Z`
- size: `704`
- prototype: `__int64 __fastcall(CDeviceCollection *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18056d1a0`

## callees

- `0x180039ce4`
- `0x1800e9b1c`
- `0x18056dd58`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18056ddbf`
- `KERNEL32!GetLastError` at `0x18056de5b`
- `KERNEL32!GetLastError` at `0x18056defd`
- `KERNEL32!GetLastError` at `0x18056df84`
- `KERNEL32!GetLastError` at `0x18056ddbf`
- `KERNEL32!GetLastError` at `0x18056de5b`
- `KERNEL32!GetLastError` at `0x18056defd`
- `KERNEL32!GetLastError` at `0x18056df84`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056de51`
- `DEVOBJ!DevObjGetClassDevs` at `0x18056de51`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056dfeb`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18056dfeb`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18056df7a`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18056df7a`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18056def3`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18056def3`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056ddaa`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18056ddaa`

## string_xrefs

- `0x18056de05`: `DevObjCreateDeviceInfoList FAILED`
- `0x18056df48`: `DevObjOpenDeviceInfo failed`
- `0x18056dfcd`: `DevObjGetDeviceRegistryProperty failed`

## pseudocode

```c
__int64 __fastcall CDeviceCollection::CheckDeviceReady(CDeviceCollection *this, unsigned __int16 *a2)
{
  unsigned int v3; // esi
  __int64 DeviceInfoList; // rdi
  signed int LastError; // eax
  signed int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v8; // eax
  signed int v9; // ebx
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  signed int v13; // eax
  signed int v14; // eax
  __int64 v16; // [rsp+28h] [rbp-70h]
  int v17; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v18[3]; // [rsp+48h] [rbp-50h] BYREF

  v17 = 0;
  v3 = 0;
  memset(v18, 0, sizeof(v18));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"DevObjCreateDeviceInfoList FAILED",
          v6);
      }
      return v3;
    }
  }
  if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, a2, 22, 0, 0) )
    goto LABEL_18;
  v8 = GetLastError();
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_18:
    LODWORD(v18[0]) = 48;
    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, a2, 0, 0, v18) )
      goto LABEL_31;
    v13 = GetLastError();
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( v9 >= 0 )
    {
LABEL_31:
      if ( (unsigned int)DevObjGetDeviceRegistryProperty(DeviceInfoList, v18, 34, 0, &v17, 4, 0) )
        goto LABEL_36;
      v14 = GetLastError();
      v9 = v14;
      if ( v14 == 13 )
      {
        v3 = 1;
        goto LABEL_37;
      }
      if ( v14 > 0 )
        v9 = (unsigned __int16)v14 | 0x80070000;
      if ( v9 >= 0 )
      {
LABEL_36:
        LOBYTE(v3) = v17 != 3;
      }
      else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
             && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        v11 = 109;
        v12 = "DevObjGetDeviceRegistryProperty failed";
        goto LABEL_17;
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 108;
      v12 = "DevObjOpenDeviceInfo failed";
      goto LABEL_17;
    }
  }
  else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
         && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 107;
    v12 = "DevObjGetClassDevs FAILED";
LABEL_17:
    LODWORD(v16) = v9;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_714a6d298d2233154907540e19009056_Traceguids,
      v10,
      (__int64)v12,
      v16);
  }
LABEL_37:
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return v3;
}

```

## disassembly

```asm
0x18056dd58  mov     [rsp+arg_0], rbx
0x18056dd5d  mov     [rsp+arg_10], rbp
0x18056dd62  push    rsi
0x18056dd63  push    rdi
0x18056dd64  push    r15
0x18056dd66  sub     rsp, 80h
0x18056dd6d  mov     rax, cs:__security_cookie
0x18056dd74  xor     rax, rsp
0x18056dd77  mov     [rsp+98h+var_20], rax
0x18056dd7c  xorps   xmm0, xmm0
0x18056dd7f  mov     [rsp+98h+var_58], 0
0x18056dd87  mov     rbp, rdx
0x18056dd8a  xor     esi, esi
0x18056dd8c  xor     edx, edx
0x18056dd8e  mov     [rsp+98h+var_78], rsi
0x18056dd93  xor     r9d, r9d
0x18056dd96  xor     r8d, r8d
0x18056dd99  xor     ecx, ecx
0x18056dd9b  movups  [rsp+98h+var_50], xmm0
0x18056dda0  movups  [rsp+98h+var_40], xmm0
0x18056dda5  movups  [rsp+98h+var_30], xmm0
0x18056ddaa  call    cs:__imp_DevObjCreateDeviceInfoList
0x18056ddb0  mov     rdi, rax
0x18056ddb3  mov     r15d, 80070000h
0x18056ddb9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18056ddbd  jnz     short loc_18056DE39
0x18056ddbf  call    cs:__imp_GetLastError
0x18056ddc5  mov     ebx, eax
0x18056ddc7  test    eax, eax
0x18056ddc9  jle     short loc_18056DDD1
0x18056ddcb  movzx   ebx, ax
0x18056ddce  or      ebx, r15d
0x18056ddd1  test    ebx, ebx
0x18056ddd3  jns     short loc_18056DE39
0x18056ddd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18056dddc  lea     rax, WPP_GLOBAL_Control
0x18056dde3  cmp     rcx, rax
0x18056dde6  jz      loc_18056DFF1
0x18056ddec  test    byte ptr [rcx+1Ch], 8
0x18056ddf0  jz      loc_18056DFF1
0x18056ddf6  cmp     byte ptr [rcx+19h], 2
0x18056ddfa  jb      loc_18056DFF1
0x18056de00  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056de05  lea     rcx, aDevobjcreatede; "DevObjCreateDeviceInfoList FAILED"
0x18056de0c  mov     dword ptr [rsp+98h+var_70], ebx
0x18056de10  mov     [rsp+98h+var_78], rcx
0x18056de15  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056de1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18056de23  mov     edx, 6Ah ; 'j'
0x18056de28  mov     r9d, eax
0x18056de2b  mov     rcx, [rcx+10h]
0x18056de2f  call    WPP_SF_DsD
0x18056de34  jmp     loc_18056DFF1
0x18056de39  mov     [rsp+98h+var_70], rsi
0x18056de3e  mov     r9d, 16h
0x18056de44  mov     r8, rbp
0x18056de47  mov     [rsp+98h+var_78], rsi
0x18056de4c  xor     edx, edx
0x18056de4e  mov     rcx, rdi
0x18056de51  call    cs:__imp_DevObjGetClassDevs
0x18056de57  test    eax, eax
0x18056de59  jnz     short loc_18056DED5
0x18056de5b  call    cs:__imp_GetLastError
0x18056de61  mov     ebx, eax
0x18056de63  test    eax, eax
0x18056de65  jle     short loc_18056DE6D
0x18056de67  movzx   ebx, ax
0x18056de6a  or      ebx, r15d
0x18056de6d  test    ebx, ebx
0x18056de6f  jns     short loc_18056DED5
0x18056de71  mov     rcx, cs:WPP_GLOBAL_Control
0x18056de78  lea     rax, WPP_GLOBAL_Control
0x18056de7f  cmp     rcx, rax
0x18056de82  jz      loc_18056DFE2
0x18056de88  test    byte ptr [rcx+1Ch], 8
0x18056de8c  jz      loc_18056DFE2
0x18056de92  cmp     byte ptr [rcx+19h], 2
0x18056de96  jb      loc_18056DFE2
0x18056de9c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056dea1  mov     edx, 6Bh ; 'k'
0x18056dea6  lea     rcx, aDevobjgetclass_0; "DevObjGetClassDevs FAILED"
0x18056dead  mov     dword ptr [rsp+98h+var_70], ebx
0x18056deb1  lea     r8, WPP_714a6d298d2233154907540e19009056_Traceguids
0x18056deb8  mov     [rsp+98h+var_78], rcx
0x18056debd  mov     r9d, eax
0x18056dec0  mov     rcx, cs:WPP_GLOBAL_Control
0x18056dec7  mov     rcx, [rcx+10h]
0x18056decb  call    WPP_SF_DsD
0x18056ded0  jmp     loc_18056DFE2
0x18056ded5  lea     rax, [rsp+98h+var_50]
0x18056deda  mov     dword ptr [rsp+98h+var_50], 30h ; '0'
0x18056dee2  xor     r9d, r9d
0x18056dee5  mov     [rsp+98h+var_78], rax
0x18056deea  xor     r8d, r8d
0x18056deed  mov     rdx, rbp
0x18056def0  mov     rcx, rdi
0x18056def3  call    cs:__imp_DevObjOpenDeviceInfo
0x18056def9  test    eax, eax
0x18056defb  jnz     short loc_18056DF54
0x18056defd  call    cs:__imp_GetLastError
0x18056df03  mov     ebx, eax
0x18056df05  test    eax, eax
0x18056df07  jle     short loc_18056DF0F
0x18056df09  movzx   ebx, ax
0x18056df0c  or      ebx, r15d
0x18056df0f  test    ebx, ebx
0x18056df11  jns     short loc_18056DF54
0x18056df13  mov     rcx, cs:WPP_GLOBAL_Control
0x18056df1a  lea     rax, WPP_GLOBAL_Control
0x18056df21  cmp     rcx, rax
0x18056df24  jz      loc_18056DFE2
0x18056df2a  test    byte ptr [rcx+1Ch], 8
0x18056df2e  jz      loc_18056DFE2
0x18056df34  cmp     byte ptr [rcx+19h], 2
0x18056df38  jb      loc_18056DFE2
0x18056df3e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056df43  mov     edx, 6Ch ; 'l'
0x18056df48  lea     rcx, aDevobjopendevi_0; "DevObjOpenDeviceInfo failed"
0x18056df4f  jmp     loc_18056DEAD
0x18056df54  xor     r9d, r9d
0x18056df57  mov     [rsp+98h+var_68], rsi
0x18056df5c  lea     rax, [rsp+98h+var_58]
0x18056df61  mov     dword ptr [rsp+98h+var_70], 4
0x18056df69  lea     rdx, [rsp+98h+var_50]
0x18056df6e  mov     [rsp+98h+var_78], rax
0x18056df73  mov     rcx, rdi
0x18056df76  lea     r8d, [r9+22h]
0x18056df7a  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x18056df80  test    eax, eax
0x18056df82  jnz     short loc_18056DFD9
0x18056df84  call    cs:__imp_GetLastError
0x18056df8a  mov     ebx, eax
0x18056df8c  cmp     eax, 0Dh
0x18056df8f  jnz     short loc_18056DF96
0x18056df91  lea     esi, [rax-0Ch]
0x18056df94  jmp     short loc_18056DFE2
0x18056df96  test    eax, eax
0x18056df98  jle     short loc_18056DFA0
0x18056df9a  movzx   ebx, ax
0x18056df9d  or      ebx, r15d
0x18056dfa0  test    ebx, ebx
0x18056dfa2  jns     short loc_18056DFD9
0x18056dfa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18056dfab  lea     rax, WPP_GLOBAL_Control
0x18056dfb2  cmp     rcx, rax
0x18056dfb5  jz      short loc_18056DFE2
0x18056dfb7  test    byte ptr [rcx+1Ch], 8
0x18056dfbb  jz      short loc_18056DFE2
0x18056dfbd  cmp     byte ptr [rcx+19h], 2
0x18056dfc1  jb      short loc_18056DFE2
0x18056dfc3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18056dfc8  mov     edx, 6Dh ; 'm'
0x18056dfcd  lea     rcx, aDevobjgetdevic_3; "DevObjGetDeviceRegistryProperty failed"
0x18056dfd4  jmp     loc_18056DEAD
0x18056dfd9  cmp     [rsp+98h+var_58], 3
0x18056dfde  setnz   sil
0x18056dfe2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18056dfe6  jz      short loc_18056DFF1
0x18056dfe8  mov     rcx, rdi
0x18056dfeb  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18056dff1  mov     eax, esi
0x18056dff3  mov     rcx, [rsp+98h+var_20]
0x18056dff8  xor     rcx, rsp; StackCookie
0x18056dffb  call    __security_check_cookie
0x18056e000  lea     r11, [rsp+98h+var_18]
0x18056e008  mov     rbx, [r11+20h]
0x18056e00c  mov     rbp, [r11+30h]
0x18056e010  mov     rsp, r11
0x18056e013  pop     r15
0x18056e015  pop     rdi
0x18056e016  pop     rsi
0x18056e017  retn
```
