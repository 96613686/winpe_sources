# InitMetadataCachePathProperty(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180056060`
- end: `0x180056196`
- name: `?InitMetadataCachePathProperty@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `310`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180055448`
- `0x180055470`
- `0x180056060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800560e1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800560d7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800560d7`

## string_xrefs

- `0x1800560d0`: `%PROGRAMDATA%\Microsoft\Windows\DeviceMetadataCache\`

## pseudocode

```c
__int64 __fastcall InitMetadataCachePathProperty(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  _QWORD *v4; // rcx
  DWORD v5; // eax
  signed int LastError; // eax
  signed int v7; // ebx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
      WPP_SF_(v4[2], 38, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
  }
  v5 = ExpandEnvironmentStringsW(
         L"%PROGRAMDATA%\\Microsoft\\Windows\\DeviceMetadataCache\\",
         &RegistryPropertyBag::MetadataCachePathProperty::s_szDeviceMetadataCachePath,
         0x104u);
  if ( v5 )
  {
    if ( v5 <= 0x104 )
    {
      RegistryPropertyBag::MetadataCachePathProperty::s_cchDeviceMetadataCachePath = v5 - 1;
      v7 = 0;
    }
    else
    {
      v7 = -2147024774;
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids,
      (unsigned int)v7);
  *Context = (PVOID)v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
    return 1;
  }
}

```

## disassembly

```asm
0x180056060  push    rbx
0x180056062  push    rbp
0x180056063  push    rdi
0x180056064  push    r14
0x180056066  sub     rsp, 28h
0x18005606a  mov     rdi, r8
0x18005606d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056074  lea     rbp, WPP_GLOBAL_Control
0x18005607b  lea     r14, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180056082  cmp     rcx, rbp
0x180056085  jz      short loc_1800560C1
0x180056087  test    byte ptr [rcx+1Ch], 10h
0x18005608b  jz      short loc_1800560A5
0x18005608d  mov     rcx, [rcx+10h]
0x180056091  mov     edx, 28h ; '('
0x180056096  mov     r8, r14
0x180056099  call    WPP_SF_
0x18005609e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560a5  cmp     rcx, rbp
0x1800560a8  jz      short loc_1800560C1
0x1800560aa  test    byte ptr [rcx+1Ch], 10h
0x1800560ae  jz      short loc_1800560C1
0x1800560b0  mov     rcx, [rcx+10h]
0x1800560b4  mov     edx, 26h ; '&'
0x1800560b9  mov     r8, r14
0x1800560bc  call    WPP_SF_
0x1800560c1  mov     ebx, 104h
0x1800560c6  lea     rdx, ?s_szDeviceMetadataCachePath@MetadataCachePathProperty@RegistryPropertyBag@@0PAGA; lpDst
0x1800560cd  mov     r8d, ebx; nSize
0x1800560d0  lea     rcx, Src; "%PROGRAMDATA%\\Microsoft\\Windows\\Devi"...
0x1800560d7  call    cs:__imp_ExpandEnvironmentStringsW
0x1800560dd  test    eax, eax
0x1800560df  jnz     short loc_1800560F8
0x1800560e1  call    cs:__imp_GetLastError
0x1800560e7  mov     ebx, eax
0x1800560e9  test    eax, eax
0x1800560eb  jle     short loc_18005610D
0x1800560ed  movzx   ebx, ax
0x1800560f0  or      ebx, 80070000h
0x1800560f6  jmp     short loc_18005610D
0x1800560f8  cmp     eax, ebx
0x1800560fa  jbe     short loc_180056103
0x1800560fc  mov     ebx, 8007007Ah
0x180056101  jmp     short loc_18005610D
0x180056103  dec     eax
0x180056105  mov     cs:?s_cchDeviceMetadataCachePath@MetadataCachePathProperty@RegistryPropertyBag@@0HA, eax; int RegistryPropertyBag::MetadataCachePathProperty::s_cchDeviceMetadataCachePath
0x18005610b  xor     ebx, ebx
0x18005610d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056114  cmp     rcx, rbp
0x180056117  jz      short loc_180056133
0x180056119  test    byte ptr [rcx+1Ch], 10h
0x18005611d  jz      short loc_180056133
0x18005611f  mov     rcx, [rcx+10h]
0x180056123  mov     edx, 27h ; '''
0x180056128  mov     r9d, ebx
0x18005612b  mov     r8, r14
0x18005612e  call    WPP_SF_d
0x180056133  movsxd  rax, ebx
0x180056136  mov     [rdi], rax
0x180056139  test    ebx, ebx
0x18005613b  js      short loc_180056167
0x18005613d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056144  cmp     rcx, rbp
0x180056147  jz      short loc_180056160
0x180056149  test    byte ptr [rcx+1Ch], 10h
0x18005614d  jz      short loc_180056160
0x18005614f  mov     rcx, [rcx+10h]
0x180056153  mov     edx, 29h ; ')'
0x180056158  mov     r8, r14
0x18005615b  call    WPP_SF_
0x180056160  mov     eax, 1
0x180056165  jmp     short loc_18005618C
0x180056167  mov     rcx, cs:WPP_GLOBAL_Control
0x18005616e  cmp     rcx, rbp
0x180056171  jz      short loc_18005618A
0x180056173  test    byte ptr [rcx+1Ch], 10h
0x180056177  jz      short loc_18005618A
0x180056179  mov     rcx, [rcx+10h]
0x18005617d  mov     edx, 2Ah ; '*'
0x180056182  mov     r8, r14
0x180056185  call    WPP_SF_
0x18005618a  xor     eax, eax
0x18005618c  add     rsp, 28h
0x180056190  pop     r14
0x180056192  pop     rdi
0x180056193  pop     rbp
0x180056194  pop     rbx
0x180056195  retn
```
