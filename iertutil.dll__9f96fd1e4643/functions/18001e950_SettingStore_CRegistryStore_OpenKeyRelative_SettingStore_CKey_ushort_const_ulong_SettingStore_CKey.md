# SettingStore::CRegistryStore::OpenKeyRelative(SettingStore::CKey *,ushort const *,ulong,SettingStore::CKey * *)

- ea: `0x18001e950`
- end: `0x18001ec4c`
- name: `?OpenKeyRelative@CRegistryStore@SettingStore@@UEAAJPEAVCKey@2@PEBGKPEAPEAV32@@Z`
- size: `764`
- prototype: `int(SettingStore::CRegistryStore *__hidden this, struct SettingStore::CKey *, const unsigned __int16 *, unsigned int, struct SettingStore::CKey **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180054400`

## callees

- `0x180018410`
- `0x18001d0f0`
- `0x18001d8cc`
- `0x18001e950`
- `0x180022eb0`
- `0x180077b20`
- `0x180077e50`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ea4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ea93`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ea4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ea93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ea81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e9e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eb1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e9e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eb1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea0f`

## pseudocode

```c
__int64 __fastcall SettingStore::CRegistryStore::OpenKeyRelative(
        SettingStore::CRegistryStore *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        __int16 a4,
        struct SettingStore::CKey **a5)
{
  signed int v9; // ebx
  int v10; // eax
  int v11; // r13d
  REGSAM v12; // r9d
  LSTATUS v13; // eax
  HANDLE v15; // rax
  _QWORD *v16; // rdi
  HKEY v17; // rcx
  HANDLE ProcessHeap; // rax
  SettingStore::CRegistryProtectedKey *v19; // rax
  SettingStore::CRegistryProtectedKey *v20; // rsi
  REGSAM v21; // r9d
  LSTATUS v22; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  __int64 v24; // [rsp+38h] [rbp-20h] BYREF
  struct IEUserBroker *v25; // [rsp+40h] [rbp-18h] BYREF
  __int64 v26; // [rsp+48h] [rbp-10h] BYREF

  hKey = 0;
  v9 = SettingStore::CRegistryStore::_Init(this);
  if ( v9 < 0 )
    return (unsigned int)v9;
  if ( (a4 & 0x2000) != 0 )
  {
    ProcessHeap = GetProcessHeap();
    v19 = (SettingStore::CRegistryProtectedKey *)HeapAlloc(ProcessHeap, 8u, 0x28u);
    v20 = v19;
    if ( v19 )
    {
      *((_QWORD *)v19 + 2) = 0;
      *((_DWORD *)v19 + 3) = a4 & 0x8013;
      *((_DWORD *)v19 + 2) = 1;
      *((_QWORD *)v19 + 4) = 0;
      *(_QWORD *)v19 = &SettingStore::CRegistryProtectedKey::`vftable';
      v9 = SettingStore::CRegistryProtectedKey::Init(v19, a2[2], a3);
      if ( v9 < 0 )
      {
        v16 = 0;
        SettingStore::CRegistryProtectedKey::`scalar deleting destructor'(v20, 1u);
      }
      else
      {
        v16 = v20;
      }
      if ( v16 )
        goto LABEL_14;
    }
  }
  else
  {
    v10 = ((a4 & 1) != 0 ? 6 : 0) | 0x20019;
    v11 = a4 & 2;
    if ( (a4 & 2) == 0 )
      v10 = (a4 & 1) != 0 ? 0x20006 : 0;
    v12 = v10 | 0x100;
    if ( (a4 & 0x10) == 0 )
      v12 = v10;
    v13 = RegOpenKeyExW(a2[2], a3, 0, v12, &hKey);
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( v9 != -2147024891 )
    {
LABEL_10:
      if ( v9 >= 0 )
      {
        v15 = GetProcessHeap();
        v16 = HeapAlloc(v15, 8u, 0x18u);
        if ( v16 )
        {
          v17 = hKey;
          *v16 = &SettingStore::CRegistryKey::`vftable';
          v16[2] = v17;
          *((_DWORD *)v16 + 3) = a4 & 0x8013;
          *((_DWORD *)v16 + 2) = 1;
LABEL_14:
          *a5 = (struct SettingStore::CKey *)v16;
          return (unsigned int)v9;
        }
      }
      goto LABEL_11;
    }
    if ( (unsigned int)IEConfiguration_GetDWORD(268435501) == 2 )
    {
      if ( (unsigned __int8)IEConfiguration_GetBool(536870914) )
      {
        if ( (a4 & 1) == 0 && a2 == *((HKEY **)this + 826) )
        {
          v26 = 0;
          v25 = 0;
          v9 = CoCreateUserBroker(&v25);
          if ( v9 >= 0 )
          {
            v24 = 0;
            v9 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v25 + 48LL))(
                   v25,
                   &CLSID_CEdgeManagerBroker,
                   &IID_IUnknown,
                   &v24);
            if ( v9 >= 0 )
            {
              v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v24)(
                     v24,
                     &GUID_26ea2529_1012_4dd2_8a8b_3d2de75d3529,
                     &v26);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
            (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v25 + 16LL))(v25);
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 120LL))(v26);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              if ( v9 >= 0 )
              {
                v21 = (v11 != 0 ? 0x20019 : 0) | 0x100;
                if ( (a4 & 0x10) == 0 )
                  v21 = v11 != 0 ? 0x20019 : 0;
                v22 = RegOpenKeyExW(a2[2], a3, 0, v21, &hKey);
                v9 = v22;
                if ( v22 > 0 )
                  v9 = (unsigned __int16)v22 | 0x80070000;
                goto LABEL_10;
              }
            }
          }
        }
      }
    }
  }
LABEL_11:
  if ( hKey )
  {
    RegCloseKey(hKey);
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e950  push    rbp
0x18001e952  push    rbx
0x18001e953  push    rsi
0x18001e954  push    rdi
0x18001e955  push    r12
0x18001e957  push    r13
0x18001e959  push    r14
0x18001e95b  push    r15
0x18001e95d  mov     rbp, rsp
0x18001e960  sub     rsp, 58h
0x18001e964  mov     r14d, r9d
0x18001e967  mov     [rbp+hKey], 0
0x18001e96f  mov     r15, r8
0x18001e972  mov     rdi, rdx
0x18001e975  mov     rsi, rcx
0x18001e978  call    ?_Init@CRegistryStore@SettingStore@@AEAAJXZ; SettingStore::CRegistryStore::_Init(void)
0x18001e97d  mov     ebx, eax
0x18001e97f  test    eax, eax
0x18001e981  js      loc_18001EA28
0x18001e987  bt      r14d, 0Dh
0x18001e98c  jb      loc_18001EA81
0x18001e992  mov     r12d, r14d
0x18001e995  mov     r13d, r14d
0x18001e998  and     r12d, 1
0x18001e99c  mov     rdx, r15; lpSubKey
0x18001e99f  mov     eax, r12d
0x18001e9a2  neg     eax
0x18001e9a4  sbb     ecx, ecx
0x18001e9a6  and     ecx, 20006h
0x18001e9ac  mov     eax, ecx
0x18001e9ae  or      eax, 20019h
0x18001e9b3  and     r13d, 2
0x18001e9b7  cmovz   eax, ecx
0x18001e9ba  mov     ecx, r14d
0x18001e9bd  and     ecx, 10h
0x18001e9c0  mov     r9d, eax
0x18001e9c3  bts     r9d, 8
0x18001e9c8  mov     [rbp+arg_8], ecx
0x18001e9cb  test    ecx, ecx
0x18001e9cd  mov     rcx, [rdi+10h]; hKey
0x18001e9d1  cmovz   r9d, eax; samDesired
0x18001e9d5  lea     rax, [rbp+hKey]
0x18001e9d9  xor     r8d, r8d; ulOptions
0x18001e9dc  mov     [rsp+58h+phkResult], rax; phkResult
0x18001e9e1  call    cs:__imp_RegOpenKeyExW
0x18001e9e7  mov     ebx, eax
0x18001e9e9  test    eax, eax
0x18001e9eb  jle     short loc_18001E9F6
0x18001e9ed  movzx   ebx, ax
0x18001e9f0  or      ebx, 80070000h
0x18001e9f6  cmp     ebx, 80070005h
0x18001e9fc  jz      loc_18001EB4B
0x18001ea02  test    ebx, ebx
0x18001ea04  jns     short loc_18001EA3B
0x18001ea06  mov     rcx, [rbp+hKey]; hKey
0x18001ea0a  test    rcx, rcx
0x18001ea0d  jz      short loc_18001EA28
0x18001ea0f  call    cs:__imp_RegCloseKey
0x18001ea15  mov     ebx, 8007000Eh
0x18001ea1a  jmp     short loc_18001EA28
0x18001ea1c  test    rdi, rdi
0x18001ea1f  jz      short loc_18001EA06
0x18001ea21  mov     rax, [rbp+arg_20]
0x18001ea25  mov     [rax], rdi
0x18001ea28  mov     eax, ebx
0x18001ea2a  add     rsp, 58h
0x18001ea2e  pop     r15
0x18001ea30  pop     r14
0x18001ea32  pop     r13
0x18001ea34  pop     r12
0x18001ea36  pop     rdi
0x18001ea37  pop     rsi
0x18001ea38  pop     rbx
0x18001ea39  pop     rbp
0x18001ea3a  retn
0x18001ea3b  call    cs:__imp_GetProcessHeap
0x18001ea41  mov     edx, 8; dwFlags
0x18001ea46  mov     rcx, rax; hHeap
0x18001ea49  lea     r8d, [rdx+10h]; dwBytes
0x18001ea4d  call    cs:__imp_HeapAlloc
0x18001ea53  mov     rdi, rax
0x18001ea56  test    rax, rax
0x18001ea59  jz      short loc_18001EA06
0x18001ea5b  mov     rcx, [rbp+hKey]
0x18001ea5f  lea     rax, ??_7CRegistryKey@SettingStore@@6B@; const SettingStore::CRegistryKey::`vftable'
0x18001ea66  and     r14d, 8013h
0x18001ea6d  mov     [rdi], rax
0x18001ea70  mov     [rdi+10h], rcx
0x18001ea74  mov     [rdi+0Ch], r14d
0x18001ea78  mov     dword ptr [rdi+8], 1
0x18001ea7f  jmp     short loc_18001EA21
0x18001ea81  call    cs:__imp_GetProcessHeap
0x18001ea87  mov     edx, 8; dwFlags
0x18001ea8c  mov     rcx, rax; hHeap
0x18001ea8f  lea     r8d, [rdx+20h]; dwBytes
0x18001ea93  call    cs:__imp_HeapAlloc
0x18001ea99  mov     rsi, rax
0x18001ea9c  test    rax, rax
0x18001ea9f  jz      loc_18001EA06
0x18001eaa5  mov     qword ptr [rax+10h], 0
0x18001eaad  and     r14d, 8013h
0x18001eab4  mov     [rax+0Ch], r14d
0x18001eab8  mov     r8, r15; unsigned __int16 *
0x18001eabb  mov     dword ptr [rax+8], 1
0x18001eac2  mov     rcx, rsi; this
0x18001eac5  lea     rax, ??_7CRegistryProtectedKey@SettingStore@@6B@; const SettingStore::CRegistryProtectedKey::`vftable'
0x18001eacc  mov     qword ptr [rsi+20h], 0
0x18001ead4  mov     [rsi], rax
0x18001ead7  mov     rdx, [rdi+10h]; HKEY
0x18001eadb  call    ?Init@CRegistryProtectedKey@SettingStore@@QEAAJPEAUHKEY__@@PEBG@Z; SettingStore::CRegistryProtectedKey::Init(HKEY__ *,ushort const *)
0x18001eae0  mov     ebx, eax
0x18001eae2  test    eax, eax
0x18001eae4  js      short loc_18001EB39
0x18001eae6  mov     rdi, rsi
0x18001eae9  jmp     loc_18001EA1C
0x18001eaee  mov     rcx, [rdi+10h]; hKey
0x18001eaf2  neg     r13d
0x18001eaf5  mov     rdx, r15; lpSubKey
0x18001eaf8  sbb     eax, eax
0x18001eafa  and     eax, 20019h
0x18001eaff  mov     r9d, eax
0x18001eb02  bts     r9d, 8
0x18001eb07  cmp     [rbp+arg_8], 0
0x18001eb0b  cmovz   r9d, eax; samDesired
0x18001eb0f  lea     rax, [rbp+hKey]
0x18001eb13  xor     r8d, r8d; ulOptions
0x18001eb16  mov     [rsp+58h+phkResult], rax; phkResult
0x18001eb1b  call    cs:__imp_RegOpenKeyExW
0x18001eb21  mov     ebx, eax
0x18001eb23  test    eax, eax
0x18001eb25  jle     loc_18001EA02
0x18001eb2b  movzx   ebx, ax
0x18001eb2e  or      ebx, 80070000h
0x18001eb34  jmp     loc_18001EA02
0x18001eb39  xor     edi, edi
0x18001eb3b  mov     rcx, rsi; this
0x18001eb3e  lea     edx, [rdi+1]; unsigned int
0x18001eb41  call    ??_GCRegistryProtectedKey@SettingStore@@UEAAPEAXI@Z; SettingStore::CRegistryProtectedKey::`scalar deleting destructor'(uint)
0x18001eb46  jmp     loc_18001EA1C
0x18001eb4b  mov     ecx, 1000002Dh
0x18001eb50  call    ?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18001eb55  cmp     eax, 2
0x18001eb58  jnz     loc_18001EA06
0x18001eb5e  mov     ecx, 20000002h
0x18001eb63  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18001eb68  test    al, al
0x18001eb6a  jz      loc_18001EA06
0x18001eb70  test    r12d, r12d
0x18001eb73  jnz     loc_18001EA06
0x18001eb79  cmp     rdi, [rsi+19D0h]
0x18001eb80  jnz     loc_18001EA06
0x18001eb86  lea     rcx, [rbp+var_18]; struct IEUserBroker **
0x18001eb8a  mov     [rbp+var_10], 0
0x18001eb92  mov     [rbp+var_18], 0
0x18001eb9a  call    ?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x18001eb9f  mov     ebx, eax
0x18001eba1  test    eax, eax
0x18001eba3  js      loc_18001EA06
0x18001eba9  mov     rcx, [rbp+var_18]
0x18001ebad  lea     r9, [rbp+var_20]
0x18001ebb1  mov     [rbp+var_20], 0
0x18001ebb9  lea     r8, IID_IUnknown
0x18001ebc0  lea     rdx, CLSID_CEdgeManagerBroker
0x18001ebc7  mov     rax, [rcx]
0x18001ebca  mov     rax, [rax+30h]
0x18001ebce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebd3  mov     ebx, eax
0x18001ebd5  test    eax, eax
0x18001ebd7  js      short loc_18001EC05
0x18001ebd9  mov     rcx, [rbp+var_20]
0x18001ebdd  lea     r8, [rbp+var_10]
0x18001ebe1  lea     rdx, _GUID_26ea2529_1012_4dd2_8a8b_3d2de75d3529
0x18001ebe8  mov     rax, [rcx]
0x18001ebeb  mov     rax, [rax]
0x18001ebee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebf3  mov     rcx, [rbp+var_20]
0x18001ebf7  mov     ebx, eax
0x18001ebf9  mov     rax, [rcx]
0x18001ebfc  mov     rax, [rax+10h]
0x18001ec00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec05  mov     rcx, [rbp+var_18]
0x18001ec09  mov     rax, [rcx]
0x18001ec0c  mov     rax, [rax+10h]
0x18001ec10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec15  test    ebx, ebx
0x18001ec17  js      loc_18001EA06
0x18001ec1d  mov     rcx, [rbp+var_10]
0x18001ec21  mov     rax, [rcx]
0x18001ec24  mov     rax, [rax+78h]
0x18001ec28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec2d  mov     rcx, [rbp+var_10]
0x18001ec31  mov     ebx, eax
0x18001ec33  mov     rax, [rcx]
0x18001ec36  mov     rax, [rax+10h]
0x18001ec3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec3f  test    ebx, ebx
0x18001ec41  js      loc_18001EA06
0x18001ec47  jmp     loc_18001EAEE
```
