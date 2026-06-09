# AdapterCacheUpdate::~AdapterCacheUpdate(void)

- ea: `0x1400066ac`
- end: `0x1400066f8`
- name: `??1AdapterCacheUpdate@@QEAA@XZ`
- size: `76`
- prototype: `void __fastcall(AdapterCacheUpdate *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140011a40`

## callees

- `0x14000625c`
- `0x140006334`
- `0x140006640`
- `0x1400066ac`

## import_xrefs

- `ntdll!NtClose` at `0x1400066ec`
- `ntdll!NtClose` at `0x1400066ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400066d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400066d9`

## pseudocode

```c
void __fastcall AdapterCacheUpdate::~AdapterCacheUpdate(AdapterCacheUpdate *this)
{
  HKEY v2; // rcx

  std::wstring::~wstring((char **)this + 9);
  std::vector<unsigned char>::~vector<unsigned char>((char *)this + 48);
  std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>((void **)this + 2);
  v2 = (HKEY)*((_QWORD *)this + 1);
  if ( v2 )
    RegCloseKey(v2);
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    NtClose(*(HANDLE *)this);
}

```

## disassembly

```asm
0x1400066ac  push    rbx
0x1400066ae  sub     rsp, 20h
0x1400066b2  mov     rbx, rcx
0x1400066b5  add     rcx, 48h ; 'H'
0x1400066b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400066be  lea     rcx, [rbx+30h]
0x1400066c2  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1400066c7  lea     rcx, [rbx+10h]
0x1400066cb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>(void)
0x1400066d0  mov     rcx, [rbx+8]; hKey
0x1400066d4  test    rcx, rcx
0x1400066d7  jz      short loc_1400066DF
0x1400066d9  call    cs:__imp_RegCloseKey
0x1400066df  mov     rcx, [rbx]; Handle
0x1400066e2  lea     rax, [rcx-1]
0x1400066e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400066ea  ja      short loc_1400066F2
0x1400066ec  call    cs:__imp_NtClose
0x1400066f2  add     rsp, 20h
0x1400066f6  pop     rbx
0x1400066f7  retn
```
