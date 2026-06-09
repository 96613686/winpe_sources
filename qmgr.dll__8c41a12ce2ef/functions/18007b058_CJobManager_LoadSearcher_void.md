# CJobManager::LoadSearcher(void)

- ea: `0x18007b058`
- end: `0x18007b37d`
- name: `?LoadSearcher@CJobManager@@AEAAXXZ`
- size: `805`
- prototype: `void __fastcall(CJobManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18008f1ec`

## callees

- `0x1800634e0`
- `0x18007b058`
- `0x180091acc`
- `0x180091afc`
- `0x180091b20`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007b1e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007b1e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b28a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b28a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b24a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b2e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b24a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b2e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b21a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007b1b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007b1b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b0b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007b0b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b18a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007b18a`

## string_xrefs

- `0x18007b1ac`: `IGDSearcherDLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CJobManager::LoadSearcher(CJobManager *this)
{
  __int64 v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  _QWORD *v4; // r14
  __int64 inserted; // rcx
  __int64 v6; // rax
  int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rbx
  HKEY v10; // rbx
  HMODULE Library; // rax
  signed int LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  EVENT_LOG *v15; // rcx
  FARPROC ProcAddress; // rax
  _QWORD *v17; // rbx
  int v18; // esi
  FARPROC v19; // rax
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Data[259]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v27; // [rsp+286h] [rbp+186h]

  Type = 0;
  cbData = 520;
  v2 = *((_QWORD *)g_GlobalInfo + 2);
  v20 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)(v2 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  v4 = (_QWORD *)(v2 + 48);
  inserted = *(_QWORD *)(v2 + 48);
  v6 = *(_QWORD *)(inserted + 8);
  v23 = (unsigned __int64)v6;
  while ( !*(_BYTE *)(v6 + 25) )
  {
    *(_QWORD *)&v23 = v6;
    if ( *(int *)(v6 + 32) >= 0 )
    {
      DWORD2(v23) = 1;
      inserted = v6;
    }
    else
    {
      DWORD2(v23) = 0;
      v6 += 16;
    }
    v6 = *(_QWORD *)v6;
  }
  if ( *(_BYTE *)(inserted + 25) || *(int *)(inserted + 32) > 0 )
  {
    std::_Tree<std::_Tmap_traits<enum NotifiableSystemEvent,ITriggerableNotifier *,std::less<enum NotifiableSystemEvent>,std::allocator<std::pair<enum NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1(v2 + 48);
    *(_QWORD *)&v24 = &v20;
    v8 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<enum RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(
           (unsigned int)v25,
           (int)v2 + 48,
           *v4,
           v7,
           (__int64)&v24);
    v9 = *(_QWORD *)(v8 + 8);
    *(_QWORD *)(v8 + 8) = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<enum _CRM_CLIENT_ID const,void *>,void *>>>(v25);
    v24 = v23;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>::_Insert_node(
                 v4,
                 &v24,
                 v9);
  }
  v10 = (HKEY)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(inserted + 40) + 16LL))(*(_QWORD *)(inserted + 40));
  if ( v3 )
    LeaveCriticalSection(v3);
  if ( RegQueryValueExW(v10, L"IGDSearcherDLL", 0, &Type, (LPBYTE)Data, &cbData) || Type != 1 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
  }
  else
  {
    v27 = 48;
    Library = LoadLibraryExW(Data, 0, 0x800u);
    *((_QWORD *)this + 205) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "InitializeEx");
      if ( ProcAddress )
      {
        v17 = (_QWORD *)((char *)this + 1664);
        v18 = ((__int64 (__fastcall *)(LPVOID (__fastcall *)(SIZE_T), void (__fastcall *)(void *), char *, char *))ProcAddress)(
                operator new,
                operator delete,
                (char *)this + 1648,
                (char *)this + 1664);
        if ( v18 < 0 )
        {
          if ( *v17 )
          {
            v19 = GetProcAddress(*((HMODULE *)this + 205), "UninitializeEx");
            if ( v19 )
              ((void (__fastcall *)(_QWORD))v19)(*v17);
          }
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v13 = 16;
            v14 = (unsigned int)v18;
LABEL_32:
            WPP_SF_d(*((_QWORD *)v15 + 2), v13, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, v14);
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
        FreeLibrary(*((HMODULE *)this + 205));
        *((_QWORD *)this + 205) = 0;
      }
    }
    else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = 14;
      v14 = (unsigned int)LastError;
      v15 = WPP_GLOBAL_Control;
      goto LABEL_32;
    }
  }
}

```

## disassembly

```asm
0x18007b058  mov     [rsp-8+arg_8], rbx
0x18007b05d  mov     [rsp-8+arg_10], rsi
0x18007b062  push    rbp
0x18007b063  push    rdi
0x18007b064  push    r14
0x18007b066  lea     rbp, [rsp-1A0h]
0x18007b06e  sub     rsp, 2A0h
0x18007b075  mov     rax, cs:__security_cookie
0x18007b07c  xor     rax, rsp
0x18007b07f  mov     [rbp+1B0h+var_20], rax
0x18007b086  mov     rdi, rcx
0x18007b089  mov     [rsp+2B0h+Type], 0
0x18007b091  mov     [rsp+2B0h+cbData], 208h
0x18007b099  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18007b0a0  mov     rbx, [rax+10h]
0x18007b0a4  mov     [rsp+2B0h+var_280], 0
0x18007b0ac  lea     rsi, [rbx+8]
0x18007b0b0  mov     rcx, rsi; lpCriticalSection
0x18007b0b3  call    cs:__imp_EnterCriticalSection
0x18007b0b9  lea     r14, [rbx+30h]
0x18007b0bd  mov     rcx, [r14]
0x18007b0c0  mov     rax, [rcx+8]
0x18007b0c4  mov     qword ptr [rsp+2B0h+var_270], rax
0x18007b0c9  mov     qword ptr [rsp+2B0h+var_270+8], 0
0x18007b0d2  mov     edx, [rsp+2B0h+var_280]
0x18007b0d6  jmp     short loc_18007B0FE
0x18007b0d8  mov     qword ptr [rsp+2B0h+var_270], rax
0x18007b0dd  cmp     [rax+20h], edx
0x18007b0e0  jge     short loc_18007B0F0
0x18007b0e2  mov     dword ptr [rsp+2B0h+var_270+8], 0
0x18007b0ea  add     rax, 10h
0x18007b0ee  jmp     short loc_18007B0FB
0x18007b0f0  mov     dword ptr [rsp+2B0h+var_270+8], 1
0x18007b0f8  mov     rcx, rax
0x18007b0fb  mov     rax, [rax]
0x18007b0fe  cmp     byte ptr [rax+19h], 0
0x18007b102  jz      short loc_18007B0D8
0x18007b104  cmp     byte ptr [rcx+19h], 0
0x18007b108  jnz     short loc_18007B10F
0x18007b10a  cmp     edx, [rcx+20h]
0x18007b10d  jge     short loc_18007B16F
0x18007b10f  mov     rcx, r14
0x18007b112  call    ?_Check_grow_by_1@?$_Tree@V?$_Tmap_traits@W4NotifiableSystemEvent@@PEAVITriggerableNotifier@@U?$less@W4NotifiableSystemEvent@@@std@@V?$allocator@U?$pair@$$CBW4NotifiableSystemEvent@@PEAVITriggerableNotifier@@@std@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<NotifiableSystemEvent,ITriggerableNotifier *,std::less<NotifiableSystemEvent>,std::allocator<std::pair<NotifiableSystemEvent const,ITriggerableNotifier *>>,0>>::_Check_grow_by_1(void)
0x18007b117  lea     rax, [rsp+2B0h+var_280]
0x18007b11c  mov     qword ptr [rsp+2B0h+var_250], rax
0x18007b121  lea     rax, [rsp+2B0h+var_250]
0x18007b126  mov     [rsp+2B0h+lpData], rax
0x18007b12b  mov     r8, [r14]
0x18007b12e  mov     rdx, r14
0x18007b131  lea     rcx, [rsp+2B0h+var_240]
0x18007b136  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEBW4RegistryKeyType@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4RegistryKeyType@@PEAVIRegistryKeyTypeInfo@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBW4RegistryKeyType@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>>>(std::allocator<std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *>> &,std::_Tree_node<std::pair<RegistryKeyType const,IRegistryKeyTypeInfo *>,void *> *,std::piecewise_construct_t const &,std::tuple<RegistryKeyType const &> &&,std::tuple<> &&)
0x18007b13b  mov     rbx, [rax+8]
0x18007b13f  mov     qword ptr [rax+8], 0
0x18007b147  lea     rcx, [rsp+2B0h+var_240]
0x18007b14c  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4_CRM_CLIENT_ID@@PEAX@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<_CRM_CLIENT_ID const,void *>,void *>>>(void)
0x18007b151  movups  xmm0, [rsp+2B0h+var_270]
0x18007b156  movdqu  [rsp+2B0h+var_250], xmm0
0x18007b15c  mov     r8, rbx
0x18007b15f  lea     rdx, [rsp+2B0h+var_250]
0x18007b164  mov     rcx, r14
0x18007b167  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CEncryptedCredentials *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> *>,std::_Tree_node<std::pair<ulong const,CEncryptedCredentials *>,void *> * const)
0x18007b16c  mov     rcx, rax
0x18007b16f  mov     rcx, [rcx+28h]
0x18007b173  mov     rax, [rcx]
0x18007b176  mov     rax, [rax+10h]
0x18007b17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b17f  mov     rbx, rax
0x18007b182  test    rsi, rsi
0x18007b185  jz      short loc_18007B191
0x18007b187  mov     rcx, rsi; lpCriticalSection
0x18007b18a  call    cs:__imp_LeaveCriticalSection
0x18007b190  nop
0x18007b191  lea     rax, [rsp+2B0h+cbData]
0x18007b196  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18007b19b  lea     rax, [rbp+1B0h+Data]
0x18007b19f  mov     [rsp+2B0h+lpData], rax; lpData
0x18007b1a4  lea     r9, [rsp+2B0h+Type]; lpType
0x18007b1a9  xor     r8d, r8d; lpReserved
0x18007b1ac  lea     rdx, aIgdsearcherdll; "IGDSearcherDLL"
0x18007b1b3  mov     rcx, rbx; hKey
0x18007b1b6  call    cs:__imp_RegQueryValueExW
0x18007b1bc  test    eax, eax
0x18007b1be  jnz     loc_18007B328
0x18007b1c4  cmp     [rsp+2B0h+Type], 1
0x18007b1c9  jnz     loc_18007B328
0x18007b1cf  mov     eax, 30h ; '0'
0x18007b1d4  mov     [rbp+1B0h+var_2A], ax
0x18007b1db  xor     edx, edx; hFile
0x18007b1dd  mov     r8d, 800h; dwFlags
0x18007b1e3  lea     rcx, [rbp+1B0h+Data]; lpLibFileName
0x18007b1e7  call    cs:__imp_LoadLibraryExW
0x18007b1ed  mov     [rdi+668h], rax
0x18007b1f4  test    rax, rax
0x18007b1f7  jnz     short loc_18007B240
0x18007b1f9  lea     rax, WPP_GLOBAL_Control
0x18007b200  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b207  cmp     rcx, rax
0x18007b20a  jz      loc_18007B356
0x18007b210  test    byte ptr [rcx+1Ch], 4
0x18007b214  jz      loc_18007B356
0x18007b21a  call    cs:__imp_GetLastError
0x18007b220  test    eax, eax
0x18007b222  jle     short loc_18007B22C
0x18007b224  movzx   eax, ax
0x18007b227  or      eax, 80070000h
0x18007b22c  mov     edx, 0Eh
0x18007b231  mov     r9d, eax
0x18007b234  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b23b  jmp     loc_18007B316
0x18007b240  lea     rdx, aInitializeex; "InitializeEx"
0x18007b247  mov     rcx, rax; hModule
0x18007b24a  call    cs:__imp_GetProcAddress
0x18007b250  test    rax, rax
0x18007b253  jnz     short loc_18007B2A0
0x18007b255  lea     rax, WPP_GLOBAL_Control
0x18007b25c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b263  cmp     rcx, rax
0x18007b266  jz      short loc_18007B283
0x18007b268  test    byte ptr [rcx+1Ch], 4
0x18007b26c  jz      short loc_18007B283
0x18007b26e  mov     edx, 0Fh
0x18007b273  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18007b27a  mov     rcx, [rcx+10h]
0x18007b27e  call    WPP_SF_
0x18007b283  mov     rcx, [rdi+668h]; hLibModule
0x18007b28a  call    cs:__imp_FreeLibrary
0x18007b290  mov     qword ptr [rdi+668h], 0
0x18007b29b  jmp     loc_18007B356
0x18007b2a0  lea     rbx, [rdi+680h]
0x18007b2a7  lea     r8, [rdi+670h]
0x18007b2ae  mov     r9, rbx
0x18007b2b1  lea     rdx, ??3@YAXPEAX@Z; operator delete(void *)
0x18007b2b8  lea     rcx, ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007b2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b2c4  mov     esi, eax
0x18007b2c6  test    eax, eax
0x18007b2c8  jns     loc_18007B356
0x18007b2ce  cmp     qword ptr [rbx], 0
0x18007b2d2  jz      short loc_18007B2F5
0x18007b2d4  lea     rdx, ProcName; "UninitializeEx"
0x18007b2db  mov     rcx, [rdi+668h]; hModule
0x18007b2e2  call    cs:__imp_GetProcAddress
0x18007b2e8  test    rax, rax
0x18007b2eb  jz      short loc_18007B2F5
0x18007b2ed  mov     rcx, [rbx]
0x18007b2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b2f5  lea     rax, WPP_GLOBAL_Control
0x18007b2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b303  cmp     rcx, rax
0x18007b306  jz      short loc_18007B356
0x18007b308  test    byte ptr [rcx+1Ch], 4
0x18007b30c  jz      short loc_18007B356
0x18007b30e  mov     edx, 10h
0x18007b313  mov     r9d, esi
0x18007b316  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18007b31d  mov     rcx, [rcx+10h]
0x18007b321  call    WPP_SF_d
0x18007b326  jmp     short loc_18007B356
0x18007b328  lea     rax, WPP_GLOBAL_Control
0x18007b32f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b336  cmp     rcx, rax
0x18007b339  jz      short loc_18007B356
0x18007b33b  test    byte ptr [rcx+1Ch], 1
0x18007b33f  jz      short loc_18007B356
0x18007b341  mov     edx, 0Dh
0x18007b346  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18007b34d  mov     rcx, [rcx+10h]
0x18007b351  call    WPP_SF_
0x18007b356  mov     rcx, [rbp+1B0h+var_20]
0x18007b35d  xor     rcx, rsp; StackCookie
0x18007b360  call    __security_check_cookie
0x18007b365  lea     r11, [rsp+2B0h+var_10]
0x18007b36d  mov     rbx, [r11+28h]
0x18007b371  mov     rsi, [r11+30h]
0x18007b375  mov     rsp, r11
0x18007b378  pop     r14
0x18007b37a  pop     rdi
0x18007b37b  pop     rbp
0x18007b37c  retn
```
