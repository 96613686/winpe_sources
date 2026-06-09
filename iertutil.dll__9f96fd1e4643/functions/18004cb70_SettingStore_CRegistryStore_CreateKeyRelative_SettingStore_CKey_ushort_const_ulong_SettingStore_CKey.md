# SettingStore::CRegistryStore::CreateKeyRelative(SettingStore::CKey *,ushort const *,ulong,SettingStore::CKey * *)

- ea: `0x18004cb70`
- end: `0x18004cd26`
- name: `?CreateKeyRelative@CRegistryStore@SettingStore@@UEAAJPEAVCKey@2@PEBGKPEAPEAV32@@Z`
- size: `438`
- prototype: `int(SettingStore::CRegistryStore *__hidden this, struct SettingStore::CKey *, const unsigned __int16 *, unsigned int, struct SettingStore::CKey **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180072284`
- `0x1800727d8`
- `0x180072ba0`

## callees

- `0x18001d8cc`
- `0x18004cb70`
- `0x180077b20`
- `0x180077e50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cbbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cce1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cbbf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004cce1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cbad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cccf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cbad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004cccf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cc31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cc31`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004ccb2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004ccb2`

## pseudocode

```c
__int64 __fastcall SettingStore::CRegistryStore::CreateKeyRelative(
        SettingStore::CRegistryStore *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        __int16 a4,
        struct SettingStore::CKey **a5)
{
  signed int v8; // ebx
  HANDLE v9; // rax
  SettingStore::CRegistryProtectedKey *v10; // rax
  SettingStore::CRegistryProtectedKey *v11; // rsi
  _QWORD *v12; // rdi
  int v14; // edx
  REGSAM samDesired; // ecx
  LSTATUS v16; // eax
  HANDLE ProcessHeap; // rax
  HKEY v18; // rcx
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v8 = SettingStore::CRegistryStore::_Init(this);
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( (a4 & 0x2000) == 0 )
  {
    v14 = ((a4 & 1) != 0 ? 6 : 0) | 0x20019;
    if ( (a4 & 2) == 0 )
      v14 = (a4 & 1) != 0 ? 0x20006 : 0;
    samDesired = v14 | 0x100;
    if ( (a4 & 0x10) == 0 )
      samDesired = v14;
    v16 = RegCreateKeyExW(a2[2], a3, 0, 0, 0, samDesired, 0, &hKey, 0);
    v8 = v16;
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    if ( v8 < 0 )
      goto LABEL_8;
    ProcessHeap = GetProcessHeap();
    v12 = HeapAlloc(ProcessHeap, 8u, 0x18u);
    if ( !v12 )
      goto LABEL_8;
    v18 = hKey;
    *v12 = &SettingStore::CRegistryKey::`vftable';
    v12[2] = v18;
    *((_DWORD *)v12 + 3) = a4 & 0x8013;
    *((_DWORD *)v12 + 2) = 1;
LABEL_20:
    *a5 = (struct SettingStore::CKey *)v12;
    return (unsigned int)v8;
  }
  v9 = GetProcessHeap();
  v10 = (SettingStore::CRegistryProtectedKey *)HeapAlloc(v9, 8u, 0x28u);
  v11 = v10;
  if ( v10 )
  {
    *((_QWORD *)v10 + 2) = 0;
    *((_DWORD *)v10 + 3) = a4 & 0x8013;
    *((_DWORD *)v10 + 2) = 1;
    *((_QWORD *)v10 + 4) = 0;
    *(_QWORD *)v10 = &SettingStore::CRegistryProtectedKey::`vftable';
    v8 = SettingStore::CRegistryProtectedKey::Init(v10, a2[2], a3);
    if ( v8 < 0 )
    {
      v12 = 0;
      SettingStore::CRegistryProtectedKey::`scalar deleting destructor'(v11, 1u);
    }
    else
    {
      v12 = v11;
    }
    if ( v12 )
      goto LABEL_20;
  }
LABEL_8:
  if ( hKey )
  {
    RegCloseKey(hKey);
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004cb70  mov     [rsp+arg_0], rbx
0x18004cb75  mov     [rsp+arg_10], rbp
0x18004cb7a  push    rsi
0x18004cb7b  push    rdi
0x18004cb7c  push    r14
0x18004cb7e  sub     rsp, 50h
0x18004cb82  mov     ebp, r9d
0x18004cb85  mov     [rsp+68h+hKey], 0
0x18004cb8e  mov     rdi, r8
0x18004cb91  mov     r14, rdx
0x18004cb94  call    ?_Init@CRegistryStore@SettingStore@@AEAAJXZ; SettingStore::CRegistryStore::_Init(void)
0x18004cb99  mov     ebx, eax
0x18004cb9b  test    eax, eax
0x18004cb9d  js      loc_18004CC3C
0x18004cba3  bt      ebp, 0Dh
0x18004cba7  jnb     loc_18004CC53
0x18004cbad  call    cs:__imp_GetProcessHeap
0x18004cbb3  mov     edx, 8; dwFlags
0x18004cbb8  mov     rcx, rax; hHeap
0x18004cbbb  lea     r8d, [rdx+20h]; dwBytes
0x18004cbbf  call    cs:__imp_HeapAlloc
0x18004cbc5  mov     rsi, rax
0x18004cbc8  test    rax, rax
0x18004cbcb  jz      short loc_18004CC27
0x18004cbcd  mov     qword ptr [rax+10h], 0
0x18004cbd5  and     ebp, 8013h
0x18004cbdb  mov     [rax+0Ch], ebp
0x18004cbde  mov     r8, rdi; unsigned __int16 *
0x18004cbe1  mov     dword ptr [rax+8], 1
0x18004cbe8  mov     rcx, rsi; this
0x18004cbeb  lea     rax, ??_7CRegistryProtectedKey@SettingStore@@6B@; const SettingStore::CRegistryProtectedKey::`vftable'
0x18004cbf2  mov     qword ptr [rsi+20h], 0
0x18004cbfa  mov     [rsi], rax
0x18004cbfd  mov     rdx, [r14+10h]; HKEY
0x18004cc01  call    ?Init@CRegistryProtectedKey@SettingStore@@QEAAJPEAUHKEY__@@PEBG@Z; SettingStore::CRegistryProtectedKey::Init(HKEY__ *,ushort const *)
0x18004cc06  mov     ebx, eax
0x18004cc08  test    eax, eax
0x18004cc0a  js      short loc_18004CC11
0x18004cc0c  mov     rdi, rsi
0x18004cc0f  jmp     short loc_18004CC1E
0x18004cc11  xor     edi, edi
0x18004cc13  mov     rcx, rsi; this
0x18004cc16  lea     edx, [rdi+1]; unsigned int
0x18004cc19  call    ??_GCRegistryProtectedKey@SettingStore@@UEAAPEAXI@Z; SettingStore::CRegistryProtectedKey::`scalar deleting destructor'(uint)
0x18004cc1e  test    rdi, rdi
0x18004cc21  jnz     loc_18004CD16
0x18004cc27  mov     rcx, [rsp+68h+hKey]; hKey
0x18004cc2c  test    rcx, rcx
0x18004cc2f  jz      short loc_18004CC3C
0x18004cc31  call    cs:__imp_RegCloseKey
0x18004cc37  mov     ebx, 8007000Eh
0x18004cc3c  lea     r11, [rsp+68h+var_18]
0x18004cc41  mov     eax, ebx
0x18004cc43  mov     rbx, [r11+20h]
0x18004cc47  mov     rbp, [r11+30h]
0x18004cc4b  mov     rsp, r11
0x18004cc4e  pop     r14
0x18004cc50  pop     rdi
0x18004cc51  pop     rsi
0x18004cc52  retn
0x18004cc53  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x18004cc5c  mov     eax, ebp
0x18004cc5e  and     al, 1
0x18004cc60  neg     al
0x18004cc62  lea     rax, [rsp+68h+hKey]
0x18004cc67  sbb     ecx, ecx
0x18004cc69  mov     [rsp+68h+phkResult], rax; phkResult
0x18004cc6e  and     ecx, 20006h
0x18004cc74  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004cc7d  mov     edx, ecx
0x18004cc7f  or      edx, 20019h
0x18004cc85  test    bpl, 2
0x18004cc89  cmovz   edx, ecx
0x18004cc8c  mov     ecx, edx
0x18004cc8e  bts     ecx, 8
0x18004cc92  test    bpl, 10h
0x18004cc96  cmovz   ecx, edx
0x18004cc99  xor     r9d, r9d; lpClass
0x18004cc9c  mov     [rsp+68h+samDesired], ecx; samDesired
0x18004cca0  xor     r8d, r8d; Reserved
0x18004cca3  mov     rcx, [r14+10h]; hKey
0x18004cca7  mov     rdx, rdi; lpSubKey
0x18004ccaa  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18004ccb2  call    cs:__imp_RegCreateKeyExW
0x18004ccb8  mov     ebx, eax
0x18004ccba  test    eax, eax
0x18004ccbc  jle     short loc_18004CCC7
0x18004ccbe  movzx   ebx, ax
0x18004ccc1  or      ebx, 80070000h
0x18004ccc7  test    ebx, ebx
0x18004ccc9  js      loc_18004CC27
0x18004cccf  call    cs:__imp_GetProcessHeap
0x18004ccd5  mov     edx, 8; dwFlags
0x18004ccda  mov     rcx, rax; hHeap
0x18004ccdd  lea     r8d, [rdx+10h]; dwBytes
0x18004cce1  call    cs:__imp_HeapAlloc
0x18004cce7  mov     rdi, rax
0x18004ccea  test    rax, rax
0x18004cced  jz      loc_18004CC27
0x18004ccf3  mov     rcx, [rsp+68h+hKey]
0x18004ccf8  lea     rax, ??_7CRegistryKey@SettingStore@@6B@; const SettingStore::CRegistryKey::`vftable'
0x18004ccff  and     ebp, 8013h
0x18004cd05  mov     [rdi], rax
0x18004cd08  mov     [rdi+10h], rcx
0x18004cd0c  mov     [rdi+0Ch], ebp
0x18004cd0f  mov     dword ptr [rdi+8], 1
0x18004cd16  mov     rax, [rsp+68h+arg_20]
0x18004cd1e  mov     [rax], rdi
0x18004cd21  jmp     loc_18004CC3C
```
