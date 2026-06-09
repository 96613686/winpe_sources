# DeviceEncryptionResourceManager::~DeviceEncryptionResourceManager(void)

- ea: `0x18001443c`
- end: `0x180014478`
- name: `??1DeviceEncryptionResourceManager@@QEAA@XZ`
- size: `60`
- prototype: `void __fastcall(FveEasNetworkStatus **this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ba4`

## callees

- `0x180014310`
- `0x180014340`
- `0x1800143e4`
- `0x180014400`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014471`

## pseudocode

```c
void __fastcall DeviceEncryptionResourceManager::~DeviceEncryptionResourceManager(
        FveEasNetworkStatus **this,
        unsigned int a2)
{
  std::unique_ptr<FveEasNetworkStatus>::~unique_ptr<FveEasNetworkStatus>(this + 12, a2);
  std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>(this + 9);
  std::unique_ptr<VolumeEntry>::~unique_ptr<VolumeEntry>(this + 8);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(this + 6);
  DeleteCriticalSection((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x18001443c  push    rbx
0x18001443e  sub     rsp, 20h
0x180014442  mov     rbx, rcx
0x180014445  add     rcx, 60h ; '`'
0x180014449  call    ??1?$unique_ptr@VFveEasNetworkStatus@@U?$default_delete@VFveEasNetworkStatus@@@std@@@std@@QEAA@XZ; std::unique_ptr<FveEasNetworkStatus>::~unique_ptr<FveEasNetworkStatus>(void)
0x18001444e  lea     rcx, [rbx+48h]
0x180014452  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>(void)
0x180014457  lea     rcx, [rbx+40h]
0x18001445b  call    ??1?$unique_ptr@UVolumeEntry@@U?$default_delete@UVolumeEntry@@@std@@@std@@QEAA@XZ; std::unique_ptr<VolumeEntry>::~unique_ptr<VolumeEntry>(void)
0x180014460  lea     rcx, [rbx+30h]
0x180014464  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180014469  mov     rcx, rbx
0x18001446c  add     rsp, 20h
0x180014470  pop     rbx
0x180014471  jmp     cs:__imp_DeleteCriticalSection
```
