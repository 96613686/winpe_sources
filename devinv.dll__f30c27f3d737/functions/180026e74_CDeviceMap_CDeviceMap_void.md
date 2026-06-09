# CDeviceMap::~CDeviceMap(void)

- ea: `0x180026e74`
- end: `0x180026f3c`
- name: `??1CDeviceMap@@QEAA@XZ`
- size: `200`
- prototype: `void __fastcall(CDeviceMap *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180031e30`
- `0x180039b88`
- `0x18003d6b8`

## callees

- `0x180006210`
- `0x180016598`
- `0x180025e70`
- `0x180026ba8`
- `0x180026c18`
- `0x180026e74`
- `0x180026f44`
- `0x1800384e4`

## import_xrefs

- `drvstore!DriverStoreClose` at `0x180026e92`
- `drvstore!DriverStoreClose` at `0x180026e92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026ec5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026ec5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026e9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026e9f`

## pseudocode

```c
void __fastcall CDeviceMap::~CDeviceMap(CDeviceMap *this)
{
  HMODULE v2; // rcx
  _QWORD *v3; // rdi
  void *v4; // rcx

  if ( *((_QWORD *)this + 94) )
    DriverStoreClose();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 696));
  CDeviceMap::Release(this);
  std::_Tree<std::_Tmap_traits<std::wstring,_MEDIA_DEVICE_INFO,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,_MEDIA_DEVICE_INFO,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>>,0>>((char *)this + 736);
  v2 = (HMODULE)*((_QWORD *)this + 84);
  if ( v2 )
    FreeLibrary(v2);
  CMachine::~CMachine((CDeviceMap *)((char *)this + 104));
  v3 = *(_QWORD **)(*((_QWORD *)this + 8) + 8LL);
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,CDriver *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,CDriver *>,void *>>>(
      (char *)this + 64,
      (char *)this + 64,
      v3[2]);
    v4 = v3;
    v3 = (_QWORD *)*v3;
    operator delete(v4);
  }
  operator delete(*((void **)this + 8));
  std::_Tree<std::_Tmap_traits<std::wstring,CDriverPackage *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDriverPackage *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDriverPackage *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDriverPackage *>>,0>>((char *)this + 48);
  std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>((char *)this + 24);
  std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(this);
}

```

## disassembly

```asm
0x180026e74  mov     [rsp+arg_0], rbx
0x180026e79  mov     [rsp+arg_8], rsi
0x180026e7e  push    rdi
0x180026e7f  sub     rsp, 20h
0x180026e83  mov     rbx, rcx
0x180026e86  mov     rcx, [rcx+2F0h]
0x180026e8d  test    rcx, rcx
0x180026e90  jz      short loc_180026E98
0x180026e92  call    cs:__imp_DriverStoreClose
0x180026e98  lea     rcx, [rbx+2B8h]; lpCriticalSection
0x180026e9f  call    cs:__imp_DeleteCriticalSection
0x180026ea5  mov     rcx, rbx; this
0x180026ea8  call    ?Release@CDeviceMap@@QEAAXXZ; CDeviceMap::Release(void)
0x180026ead  lea     rcx, [rbx+2E0h]
0x180026eb4  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_MEDIA_DEVICE_INFO@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_MEDIA_DEVICE_INFO@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,_MEDIA_DEVICE_INFO,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,_MEDIA_DEVICE_INFO,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_MEDIA_DEVICE_INFO>>,0>>(void)
0x180026eb9  mov     rcx, [rbx+2A0h]; hLibModule
0x180026ec0  test    rcx, rcx
0x180026ec3  jz      short loc_180026ECB
0x180026ec5  call    cs:__imp_FreeLibrary
0x180026ecb  lea     rcx, [rbx+68h]; this
0x180026ecf  call    ??1CMachine@@QEAA@XZ; CMachine::~CMachine(void)
0x180026ed4  lea     rsi, [rbx+40h]
0x180026ed8  mov     rax, [rsi]
0x180026edb  mov     rdi, [rax+8]
0x180026edf  jmp     short loc_180026F00
0x180026ee1  mov     r8, [rdi+10h]
0x180026ee5  mov     rdx, rsi
0x180026ee8  mov     rcx, rsi
0x180026eeb  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEAVCDriver@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEAVCDriver@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEAVCDriver@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEAVCDriver@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,CDriver *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,CDriver *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,CDriver *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,CDriver *>,void *> *)
0x180026ef0  mov     rcx, rdi; Block
0x180026ef3  mov     rdi, [rdi]
0x180026ef6  mov     edx, 30h ; '0'
0x180026efb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026f00  cmp     byte ptr [rdi+19h], 0
0x180026f04  jz      short loc_180026EE1
0x180026f06  mov     edx, 30h ; '0'
0x180026f0b  mov     rcx, [rsi]; Block
0x180026f0e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026f13  lea     rcx, [rbx+30h]
0x180026f17  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,CDriverPackage *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDriverPackage *>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,CDriverPackage *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CDriverPackage *>>,0>>(void)
0x180026f1c  lea     rcx, [rbx+18h]
0x180026f20  call    ??1?$vector@PEAVCDriverPackageDetailed@@V?$allocator@PEAVCDriverPackageDetailed@@@std@@@std@@QEAA@XZ; std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(void)
0x180026f25  mov     rcx, rbx
0x180026f28  mov     rbx, [rsp+28h+arg_0]
0x180026f2d  mov     rsi, [rsp+28h+arg_8]
0x180026f32  add     rsp, 20h
0x180026f36  pop     rdi
0x180026f37  jmp     ??1?$vector@PEAVCDriverPackageDetailed@@V?$allocator@PEAVCDriverPackageDetailed@@@std@@@std@@QEAA@XZ; std::vector<CDriverPackageDetailed *>::~vector<CDriverPackageDetailed *>(void)
```
