# MigrateBlueToThresholdNeeded

- ea: `0x180007890`
- end: `0x180007973`
- name: `MigrateBlueToThresholdNeeded`
- size: `227`
- prototype: `char()`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800022e0`
- `0x1800034ac`
- `0x1800076a4`
- `0x180007890`
- `0x180008010`
- `0x1800097fc`
- `0x18000a688`
- `0x18000c214`

## string_xrefs

- `0x1800078f6`: `C:\Windows\System32\MDMAgent.exe`

## pseudocode

```c
char MigrateBlueToThresholdNeeded()
{
  const unsigned __int16 *v0; // rdx
  const unsigned __int16 *v1; // rcx
  __int64 v2; // r8
  _QWORD *v3; // rax
  ScheduleMigrator *v4; // rcx
  char v5; // bl
  __int128 v7; // [rsp+70h] [rbp-58h] BYREF
  _BYTE v8[40]; // [rsp+80h] [rbp-48h] BYREF
  _BYTE v9[16]; // [rsp+A8h] [rbp-20h] BYREF

  blue2th::Migrator::Migrator((blue2th::Migrator *)v8, &dword_18002237C);
  if ( RegistryHelper::IsDwordValuePresent(v1, v0) )
  {
    v5 = 1;
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, NoMigrationNeeded, v2, 1, v9);
    v7 = 0;
    v3 = operator new(0x60u);
    *v3 = v3;
    v3[1] = v3;
    v3[2] = v3;
    *((_WORD *)v3 + 12) = 257;
    *(_QWORD *)&v7 = v3;
    ScheduleMigrator::DeleteSchedule(v4, 0);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v7);
    v5 = 0;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v8);
  return v5;
}

```

## disassembly

```asm
0x180007890  mov     r11, rsp
0x180007893  push    rbx
0x180007894  sub     rsp, 0C0h
0x18000789b  mov     rax, cs:__security_cookie
0x1800078a2  xor     rax, rsp
0x1800078a5  mov     [rsp+0C8h+var_10], rax
0x1800078ad  lea     rdx, dword_18002237C; unsigned __int16 *
0x1800078b4  lea     rcx, [r11-48h]; this
0x1800078b8  call    ??0Migrator@blue2th@@QEAA@PEBG@Z; blue2th::Migrator::Migrator(ushort const *)
0x1800078bd  nop
0x1800078be  call    ?IsDwordValuePresent@RegistryHelper@@SA_NPEBG0@Z; RegistryHelper::IsDwordValuePresent(ushort const *,ushort const *)
0x1800078c3  test    al, al
0x1800078c5  jnz     short loc_180007941
0x1800078c7  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x1800078ce  jz      short loc_1800078F6
0x1800078d0  lea     rax, [rsp+0C8h+var_20]
0x1800078d8  mov     [rsp+0C8h+var_A8], rax
0x1800078dd  mov     r9d, 1
0x1800078e3  lea     rdx, NoMigrationNeeded
0x1800078ea  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x1800078f1  call    McGenEventWrite_EventWriteTransfer
0x1800078f6  lea     rax, aCWindowsSystem; "C:\\Windows\\System32\\MDMAgent.exe"
0x1800078fd  mov     [rsp+0C8h+var_60], rax
0x180007902  xorps   xmm0, xmm0
0x180007905  movdqu  [rsp+0C8h+var_58], xmm0
0x18000790b  mov     ecx, 60h ; '`'; Size
0x180007910  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007915  mov     [rax], rax
0x180007918  mov     [rax+8], rax
0x18000791c  mov     [rax+10h], rax
0x180007920  mov     word ptr [rax+18h], 101h
0x180007926  mov     qword ptr [rsp+0C8h+var_58], rax
0x18000792b  xor     edx, edx; unsigned __int16 *
0x18000792d  call    ?DeleteSchedule@ScheduleMigrator@@QEAAJPEBG@Z; ScheduleMigrator::DeleteSchedule(ushort const *)
0x180007932  nop
0x180007933  lea     rcx, [rsp+0C8h+var_58]
0x180007938  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18000793d  xor     bl, bl
0x18000793f  jmp     short loc_180007946
0x180007941  mov     ebx, 1
0x180007946  lea     rcx, [rsp+0C8h+var_48]
0x18000794e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180007953  mov     al, bl
0x180007955  jmp     short loc_180007959
0x180007957  xor     al, al
0x180007959  mov     rcx, [rsp+0C8h+var_10]
0x180007961  xor     rcx, rsp; StackCookie
0x180007964  call    __security_check_cookie
0x180007969  add     rsp, 0C0h
0x180007970  pop     rbx
0x180007971  retn
```
