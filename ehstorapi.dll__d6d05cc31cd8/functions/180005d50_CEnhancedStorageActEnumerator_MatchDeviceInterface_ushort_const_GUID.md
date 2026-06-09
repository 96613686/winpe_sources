# CEnhancedStorageActEnumerator::MatchDeviceInterface(ushort const *,_GUID *)

- ea: `0x180005d50`
- end: `0x180005f4a`
- name: `?MatchDeviceInterface@CEnhancedStorageActEnumerator@@AEAAHPEBGPEAU_GUID@@@Z`
- size: `506`
- prototype: `int(CEnhancedStorageActEnumerator *__hidden this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180005960`

## callees

- `0x180003bdc`
- `0x180003c54`
- `0x180003db4`
- `0x180003ed0`
- `0x180005d50`
- `0x1800060e8`
- `0x18000c4f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005dfd`
- `KERNEL32!GetLastError` at `0x180005e5a`
- `KERNEL32!GetLastError` at `0x180005eba`
- `KERNEL32!GetLastError` at `0x180005dfd`
- `KERNEL32!GetLastError` at `0x180005e5a`
- `KERNEL32!GetLastError` at `0x180005eba`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005f11`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180005f11`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180005dee`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180005dee`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180005e50`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x180005e50`
- `SETUPAPI!SetupDiGetDeviceInterfaceAlias` at `0x180005eb0`
- `SETUPAPI!SetupDiGetDeviceInterfaceAlias` at `0x180005eb0`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageActEnumerator::MatchDeviceInterface(
        CEnhancedStorageActEnumerator *this,
        const unsigned __int16 *a2,
        struct _GUID *a3)
{
  unsigned int v5; // esi
  HDEVINFO DeviceInfoList; // rax
  void *v7; // rbx
  signed int v8; // eax
  char LastError; // al
  _QWORD *v10; // rcx
  int v11; // edx
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+30h] [rbp-188h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA AliasDeviceInterfaceData; // [rsp+50h] [rbp-168h] BYREF
  _BYTE v15[272]; // [rsp+70h] [rbp-148h] BYREF

  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  v5 = 0;
  memset(&AliasDeviceInterfaceData, 0, sizeof(AliasDeviceInterfaceData));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, a2);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v15, "CEnhancedStorageActEnumerator::MatchDeviceInterface");
  DeviceInterfaceData.cbSize = 32;
  AliasDeviceInterfaceData.cbSize = 32;
  DeviceInfoList = SetupDiCreateDeviceInfoList(0, 0);
  v7 = DeviceInfoList;
  if ( DeviceInfoList != (HDEVINFO)-1LL )
  {
    if ( SetupDiOpenDeviceInterfaceW(DeviceInfoList, a2, 0, &DeviceInterfaceData) )
    {
      if ( SetupDiGetDeviceInterfaceAlias(v7, &DeviceInterfaceData, a3, &AliasDeviceInterfaceData) )
      {
        v5 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, 1);
        goto LABEL_22;
      }
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_22:
        SetupDiDestroyDeviceInfoList(v7);
        goto LABEL_23;
      }
      v11 = 32;
    }
    else
    {
      LastError = GetLastError();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_22;
      v11 = 31;
    }
    WPP_SF_Sd(v10[2], v11, (unsigned int)&WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, (_DWORD)a2, LastError);
    goto LABEL_22;
  }
  v8 = GetLastError();
  if ( v8 > 0 )
    v8 = (unsigned __int16)v8 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
      (unsigned int)v8);
LABEL_23:
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v15);
  return v5;
}

```

## disassembly

```asm
0x180005d50  mov     [rsp+arg_0], rbx
0x180005d55  push    rbp
0x180005d56  push    rsi
0x180005d57  push    rdi
0x180005d58  push    r12
0x180005d5a  push    r14
0x180005d5c  sub     rsp, 190h
0x180005d63  mov     rax, cs:__security_cookie
0x180005d6a  xor     rax, rsp
0x180005d6d  mov     [rsp+1B8h+var_38], rax
0x180005d75  xorps   xmm0, xmm0
0x180005d78  xorps   xmm1, xmm1
0x180005d7b  movups  xmmword ptr [rsp+1B8h+DeviceInterfaceData.cbSize], xmm0
0x180005d80  mov     rbp, r8
0x180005d83  mov     rdi, rdx
0x180005d86  movups  xmmword ptr [rsp+1B8h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x180005d8b  xor     esi, esi
0x180005d8d  movups  xmmword ptr [rsp+1B8h+AliasDeviceInterfaceData.cbSize], xmm1
0x180005d92  movups  xmmword ptr [rsp+1B8h+AliasDeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm1
0x180005d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d9e  lea     r14, WPP_GLOBAL_Control
0x180005da5  lea     r12, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180005dac  cmp     rcx, r14
0x180005daf  jz      short loc_180005DC9
0x180005db1  test    byte ptr [rcx+1Ch], 10h
0x180005db5  jz      short loc_180005DC9
0x180005db7  mov     rcx, [rcx+10h]
0x180005dbb  lea     edx, [rsi+1Dh]
0x180005dbe  mov     r9, rdi
0x180005dc1  mov     r8, r12
0x180005dc4  call    WPP_SF_S
0x180005dc9  lea     rdx, aCenhancedstora_2; "CEnhancedStorageActEnumerator::MatchDev"...
0x180005dd0  lea     rcx, [rsp+1B8h+var_148]; this
0x180005dd5  call    ??0CESTTrackFn@@QEAA@PEBD@Z; CESTTrackFn::CESTTrackFn(char const *)
0x180005dda  xor     edx, edx; hwndParent
0x180005ddc  mov     [rsp+1B8h+DeviceInterfaceData.cbSize], 20h ; ' '
0x180005de4  xor     ecx, ecx; ClassGuid
0x180005de6  mov     [rsp+1B8h+AliasDeviceInterfaceData.cbSize], 20h ; ' '
0x180005dee  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180005df4  mov     rbx, rax
0x180005df7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005dfb  jnz     short loc_180005E42
0x180005dfd  call    cs:__imp_GetLastError
0x180005e03  test    eax, eax
0x180005e05  jle     short loc_180005E0F
0x180005e07  movzx   eax, ax
0x180005e0a  or      eax, 80070000h
0x180005e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e16  cmp     rcx, r14
0x180005e19  jz      loc_180005F17
0x180005e1f  test    byte ptr [rcx+1Ch], 2
0x180005e23  jz      loc_180005F17
0x180005e29  mov     rcx, [rcx+10h]
0x180005e2d  mov     edx, 1Eh
0x180005e32  mov     r9d, eax
0x180005e35  mov     r8, r12
0x180005e38  call    WPP_SF_d
0x180005e3d  jmp     loc_180005F17
0x180005e42  lea     r9, [rsp+1B8h+DeviceInterfaceData]; DeviceInterfaceData
0x180005e47  xor     r8d, r8d; OpenFlags
0x180005e4a  mov     rdx, rdi; DevicePath
0x180005e4d  mov     rcx, rbx; DeviceInfoSet
0x180005e50  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x180005e56  test    eax, eax
0x180005e58  jnz     short loc_180005EA0
0x180005e5a  call    cs:__imp_GetLastError
0x180005e60  test    eax, eax
0x180005e62  jle     short loc_180005E6C
0x180005e64  movzx   eax, ax
0x180005e67  or      eax, 80070000h
0x180005e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e73  cmp     rcx, r14
0x180005e76  jz      loc_180005F0E
0x180005e7c  test    byte ptr [rcx+1Ch], 2
0x180005e80  jz      loc_180005F0E
0x180005e86  mov     edx, 1Fh
0x180005e8b  mov     rcx, [rcx+10h]
0x180005e8f  mov     r9, rdi
0x180005e92  mov     r8, r12
0x180005e95  mov     [rsp+1B8h+var_198], eax
0x180005e99  call    WPP_SF_Sd
0x180005e9e  jmp     short loc_180005F0E
0x180005ea0  lea     r9, [rsp+1B8h+AliasDeviceInterfaceData]; AliasDeviceInterfaceData
0x180005ea5  mov     r8, rbp; AliasInterfaceClassGuid
0x180005ea8  lea     rdx, [rsp+1B8h+DeviceInterfaceData]; DeviceInterfaceData
0x180005ead  mov     rcx, rbx; DeviceInfoSet
0x180005eb0  call    cs:__imp_SetupDiGetDeviceInterfaceAlias
0x180005eb6  test    eax, eax
0x180005eb8  jnz     short loc_180005EE5
0x180005eba  call    cs:__imp_GetLastError
0x180005ec0  test    eax, eax
0x180005ec2  jle     short loc_180005ECC
0x180005ec4  movzx   eax, ax
0x180005ec7  or      eax, 80070000h
0x180005ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ed3  cmp     rcx, r14
0x180005ed6  jz      short loc_180005F0E
0x180005ed8  test    byte ptr [rcx+1Ch], 2
0x180005edc  jz      short loc_180005F0E
0x180005ede  mov     edx, 20h ; ' '
0x180005ee3  jmp     short loc_180005E8B
0x180005ee5  mov     esi, 1
0x180005eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ef1  cmp     rcx, r14
0x180005ef4  jz      short loc_180005F0E
0x180005ef6  test    byte ptr [rcx+1Ch], 20h
0x180005efa  jz      short loc_180005F0E
0x180005efc  mov     rcx, [rcx+10h]
0x180005f00  lea     edx, [rsi+20h]
0x180005f03  mov     r9d, esi
0x180005f06  mov     r8, r12
0x180005f09  call    WPP_SF_d
0x180005f0e  mov     rcx, rbx; DeviceInfoSet
0x180005f11  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180005f17  lea     rcx, [rsp+1B8h+var_148]; this
0x180005f1c  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x180005f21  mov     eax, esi
0x180005f23  mov     rcx, [rsp+1B8h+var_38]
0x180005f2b  xor     rcx, rsp; StackCookie
0x180005f2e  call    __security_check_cookie
0x180005f33  mov     rbx, [rsp+1B8h+arg_0]
0x180005f3b  add     rsp, 190h
0x180005f42  pop     r14
0x180005f44  pop     r12
0x180005f46  pop     rdi
0x180005f47  pop     rsi
0x180005f48  pop     rbp
0x180005f49  retn
```
