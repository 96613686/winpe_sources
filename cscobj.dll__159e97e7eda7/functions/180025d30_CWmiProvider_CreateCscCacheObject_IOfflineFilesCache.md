# CWmiProvider::_CreateCscCacheObject(IOfflineFilesCache * *)

- ea: `0x180025d30`
- end: `0x180025dd8`
- name: `?_CreateCscCacheObject@CWmiProvider@@AEAAJPEAPEAUIOfflineFilesCache@@@Z`
- size: `168`
- prototype: `int(CWmiProvider *__hidden this, struct IOfflineFilesCache **)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023c40`
- `0x180024020`
- `0x180024650`
- `0x1800249d0`
- `0x180024c80`
- `0x180024f40`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180025d30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025d56`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025d56`

## pseudocode

```c
__int64 __fastcall CWmiProvider::_CreateCscCacheObject(CWmiProvider *this, LPVOID *ppv)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx

  *ppv = 0;
  Instance = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, ppv);
  v3 = Instance;
  if ( Instance < 0 )
  {
    if ( (_WORD)Instance == 1062 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 68, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids);
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        69,
        WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids,
        (unsigned int)Instance);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180025d30  push    rbx
0x180025d32  sub     rsp, 30h
0x180025d36  mov     qword ptr [rdx], 0
0x180025d3d  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180025d44  mov     [rsp+38h+ppv], rdx; ppv
0x180025d49  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180025d50  xor     edx, edx; pUnkOuter
0x180025d52  lea     r8d, [rdx+1]; dwClsContext
0x180025d56  call    cs:__imp_CoCreateInstance
0x180025d5c  mov     ebx, eax
0x180025d5e  test    eax, eax
0x180025d60  jns     short loc_180025DD0
0x180025d62  cmp     bx, 426h
0x180025d67  jnz     short loc_180025D9C
0x180025d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d70  lea     rdx, WPP_GLOBAL_Control
0x180025d77  cmp     rcx, rdx
0x180025d7a  jz      short loc_180025DD0
0x180025d7c  test    dword ptr [rcx+1Ch], 4000000h
0x180025d83  jz      short loc_180025DD0
0x180025d85  mov     rcx, [rcx+10h]
0x180025d89  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180025d90  mov     edx, 44h ; 'D'
0x180025d95  call    WPP_SF_
0x180025d9a  jmp     short loc_180025DD0
0x180025d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180025da3  lea     rdx, WPP_GLOBAL_Control
0x180025daa  cmp     rcx, rdx
0x180025dad  jz      short loc_180025DD0
0x180025daf  test    dword ptr [rcx+1Ch], 4000000h
0x180025db6  jz      short loc_180025DD0
0x180025db8  mov     rcx, [rcx+10h]
0x180025dbc  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180025dc3  mov     edx, 45h ; 'E'
0x180025dc8  mov     r9d, ebx
0x180025dcb  call    WPP_SF_d
0x180025dd0  mov     eax, ebx
0x180025dd2  add     rsp, 30h
0x180025dd6  pop     rbx
0x180025dd7  retn
```
