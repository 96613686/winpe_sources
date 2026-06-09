# NlpWatchCachedLogonsCountKey(void *,uchar)

- ea: `0x180043180`
- end: `0x180043269`
- name: `?NlpWatchCachedLogonsCountKey@@YAXPEAXE@Z`
- size: `233`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18002ee7c`
- `0x180040fec`
- `0x180043180`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800431b5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800431b5`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileIntW` at `0x1800431fd`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileIntW` at `0x1800431fd`
- `ntdll!RtlAcquireResourceExclusive` at `0x180043216`
- `ntdll!RtlAcquireResourceExclusive` at `0x180043216`
- `ntdll!RtlReleaseResource` at `0x180043258`
- `ntdll!RtlReleaseResource` at `0x180043258`

## string_xrefs

- `0x1800431ef`: `CachedLogonsCount`

## pseudocode

```c
void __fastcall NlpWatchCachedLogonsCountKey(void *a1)
{
  unsigned int v1; // eax
  UINT ProfileIntW; // ebx
  int v3; // eax

  if ( hObject )
  {
    v1 = RegNotifyChangeKeyValue(hKey, 1, 5u, hObject, 1);
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_905305d962583d6f838b30057de84013_Traceguids, v1);
    }
  }
  ProfileIntW = GetProfileIntW(L"Winlogon", L"CachedLogonsCount", 10);
  if ( ProfileIntW != HIDWORD(NlpCacheControl) )
  {
    RtlAcquireResourceExclusive(&NlpLogonCacheCritSec, 1u);
    v3 = NlpChangeCacheSizeIfNecessary(ProfileIntW);
    if ( v3 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        WPP_905305d962583d6f838b30057de84013_Traceguids,
        (unsigned int)v3);
    }
    RtlReleaseResource(&NlpLogonCacheCritSec);
  }
}

```

## disassembly

```asm
0x180043180  mov     [rsp+arg_0], rbx
0x180043185  push    rsi
0x180043186  sub     rsp, 30h
0x18004318a  mov     r9, cs:hObject; hEvent
0x180043191  lea     rsi, WPP_GLOBAL_Control
0x180043198  test    r9, r9
0x18004319b  jz      short loc_1800431E9
0x18004319d  mov     rcx, cs:hKey; hKey
0x1800431a4  mov     edx, 1; bWatchSubtree
0x1800431a9  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x1800431b1  lea     r8d, [rdx+4]; dwNotifyFilter
0x1800431b5  call    cs:__imp_RegNotifyChangeKeyValue
0x1800431bb  test    eax, eax
0x1800431bd  jz      short loc_1800431E9
0x1800431bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800431c6  cmp     rcx, rsi
0x1800431c9  jz      short loc_1800431E9
0x1800431cb  test    byte ptr [rcx+1Ch], 1
0x1800431cf  jz      short loc_1800431E9
0x1800431d1  mov     rcx, [rcx+10h]
0x1800431d5  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x1800431dc  mov     edx, 32h ; '2'
0x1800431e1  mov     r9d, eax
0x1800431e4  call    WPP_SF_d
0x1800431e9  mov     r8d, 0Ah; nDefault
0x1800431ef  lea     rdx, KeyName; "CachedLogonsCount"
0x1800431f6  lea     rcx, AppName; "Winlogon"
0x1800431fd  call    cs:__imp_GetProfileIntW
0x180043203  cmp     eax, dword ptr cs:NlpCacheControl+4
0x180043209  mov     ebx, eax
0x18004320b  jz      short loc_18004325E
0x18004320d  mov     dl, 1; Wait
0x18004320f  lea     rcx, NlpLogonCacheCritSec; Resource
0x180043216  call    cs:__imp_RtlAcquireResourceExclusive
0x18004321c  mov     ecx, ebx; unsigned int
0x18004321e  call    ?NlpChangeCacheSizeIfNecessary@@YAJI@Z; NlpChangeCacheSizeIfNecessary(uint)
0x180043223  test    eax, eax
0x180043225  jns     short loc_180043251
0x180043227  mov     rcx, cs:WPP_GLOBAL_Control
0x18004322e  cmp     rcx, rsi
0x180043231  jz      short loc_180043251
0x180043233  test    byte ptr [rcx+1Ch], 1
0x180043237  jz      short loc_180043251
0x180043239  mov     rcx, [rcx+10h]
0x18004323d  lea     r8, WPP_905305d962583d6f838b30057de84013_Traceguids
0x180043244  mov     edx, 33h ; '3'
0x180043249  mov     r9d, eax
0x18004324c  call    WPP_SF_d
0x180043251  lea     rcx, NlpLogonCacheCritSec; Resource
0x180043258  call    cs:__imp_RtlReleaseResource
0x18004325e  mov     rbx, [rsp+38h+arg_0]
0x180043263  add     rsp, 30h
0x180043267  pop     rsi
0x180043268  retn
```
