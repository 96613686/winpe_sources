# Windows::Compat::Inventory::CacheUtilities::HiveCache::GetProviders(void *,RtlStringArray &,_iobuf *)

- ea: `0x14001016c`
- end: `0x140010279`
- name: `?GetProviders@HiveCache@CacheUtilities@Inventory@Compat@Windows@@CAJPEAXAEAVRtlStringArray@@PEAU_iobuf@@@Z`
- size: `269`
- prototype: `static int(void *, struct RtlStringArray *, struct _iobuf *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400105e0`

## callees

- `0x140001ba0`
- `0x1400026d8`
- `0x14000ddf4`
- `0x14000f000`
- `0x14001016c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400101f8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400101f8`

## string_xrefs

- `0x1400101ab`: `Failed to get handle to the AMI cache.`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::GetProviders(
        HKEY *a1,
        struct RtlStringArray *a2,
        struct _iobuf *a3)
{
  int v6; // ebx
  DWORD i; // edi
  HKEY v8; // rcx
  unsigned int v9; // eax
  unsigned __int64 v10; // r8
  int v11; // eax
  DWORD cchName[4]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-248h] BYREF

  cchName[0] = 0;
  RtlStringArray::Clear(a2);
  if ( *a1 )
  {
    for ( i = 0; ; ++i )
    {
      v8 = *a1;
      cchName[0] = 260;
      Name[0] = 0;
      v9 = RegEnumKeyExW(v8, i, Name, cchName, 0, 0, 0, 0);
      v6 = v9;
      if ( v9 == 259 )
        return 0;
      if ( v9 )
        break;
      v11 = RtlStringArray::Append(a2, Name, v10);
      v6 = v11;
      if ( v11 < 0 )
      {
        fwprintf(a3, L"Failed Append [0x%x]", (unsigned int)v11);
        return (unsigned int)v6;
      }
    }
    fwprintf(a3, L"RegEnumKeyExW failed [%d]", v9);
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    fwprintf(a3, L"Failed to get handle to the AMI cache.");
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001016c  push    rbx
0x14001016e  push    rbp
0x14001016f  push    rsi
0x140010170  push    rdi
0x140010171  push    r14
0x140010173  sub     rsp, 270h
0x14001017a  mov     rax, cs:__security_cookie
0x140010181  xor     rax, rsp
0x140010184  mov     [rsp+298h+var_38], rax
0x14001018c  mov     r14, rcx
0x14001018f  mov     [rsp+298h+cchName], 0
0x140010197  mov     rcx, rdx; this
0x14001019a  mov     rsi, r8
0x14001019d  mov     rbp, rdx
0x1400101a0  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x1400101a5  cmp     qword ptr [r14], 0
0x1400101a9  jnz     short loc_1400101C4
0x1400101ab  lea     rdx, aFailedToGetHan; "Failed to get handle to the AMI cache."
0x1400101b2  mov     rcx, rsi; Stream
0x1400101b5  call    fwprintf
0x1400101ba  mov     ebx, 80070057h
0x1400101bf  jmp     loc_140010259
0x1400101c4  xor     edi, edi
0x1400101c6  mov     rcx, [r14]; hKey
0x1400101c9  lea     r9, [rsp+298h+cchName]; lpcchName
0x1400101ce  xor     eax, eax
0x1400101d0  mov     [rsp+298h+cchName], 104h
0x1400101d8  mov     [rsp+298h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400101dd  lea     r8, [rsp+298h+Name]; lpName
0x1400101e2  mov     [rsp+298h+lpcchClass], rax; lpcchClass
0x1400101e7  mov     edx, edi; dwIndex
0x1400101e9  mov     [rsp+298h+lpClass], rax; lpClass
0x1400101ee  mov     [rsp+298h+lpReserved], rax; lpReserved
0x1400101f3  mov     [rsp+298h+Name], ax
0x1400101f8  call    cs:__imp_RegEnumKeyExW
0x1400101fe  mov     ebx, eax
0x140010200  cmp     eax, 103h
0x140010205  jz      short loc_140010257
0x140010207  test    eax, eax
0x140010209  jnz     short loc_140010236
0x14001020b  lea     rdx, [rsp+298h+Name]; unsigned __int16 *
0x140010210  mov     rcx, rbp; this
0x140010213  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x140010218  mov     ebx, eax
0x14001021a  test    eax, eax
0x14001021c  js      short loc_140010222
0x14001021e  inc     edi
0x140010220  jmp     short loc_1400101C6
0x140010222  mov     r8d, eax
0x140010225  lea     rdx, aFailedAppend0x; "Failed Append [0x%x]"
0x14001022c  mov     rcx, rsi; Stream
0x14001022f  call    fwprintf
0x140010234  jmp     short loc_140010259
0x140010236  mov     r8d, ebx
0x140010239  lea     rdx, aRegenumkeyexwF; "RegEnumKeyExW failed [%d]"
0x140010240  mov     rcx, rsi; Stream
0x140010243  call    fwprintf
0x140010248  test    ebx, ebx
0x14001024a  jle     short loc_140010259
0x14001024c  movzx   ebx, bx
0x14001024f  or      ebx, 80070000h
0x140010255  jmp     short loc_140010259
0x140010257  xor     ebx, ebx
0x140010259  mov     eax, ebx
0x14001025b  mov     rcx, [rsp+298h+var_38]
0x140010263  xor     rcx, rsp; StackCookie
0x140010266  call    __security_check_cookie
0x14001026b  add     rsp, 270h
0x140010272  pop     r14
0x140010274  pop     rdi
0x140010275  pop     rsi
0x140010276  pop     rbp
0x140010277  pop     rbx
0x140010278  retn
```
