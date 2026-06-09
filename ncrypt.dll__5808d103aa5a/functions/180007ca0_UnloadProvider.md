# UnloadProvider

- ea: `0x180007ca0`
- end: `0x180007d3d`
- name: `UnloadProvider`
- size: `157`
- prototype: `__int64(void)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180006730`
- `0x180006f40`
- `0x180007b80`
- `0x18000cb50`
- `0x18000d100`
- `0x18000e640`
- `0x18000f5c0`
- `0x1800102c0`
- `0x1800146e0`

## callees

- `0x180007ca0`
- `0x180007d50`
- `0x18000a770`
- `0x180016304`
- `0x180016464`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007d14`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007cbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007cbe`

## pseudocode

```c
void __fastcall UnloadProvider(__int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rcx

  if ( g_fLoaderInitialized && a1 )
  {
    EnterCriticalSection(&g_csLoaderLock);
    --*(_DWORD *)(a1 + 16);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_qSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)WPP_67679bdabad938a7dfcc8815ccec1def_Traceguids,
        a1,
        *(_QWORD *)a1,
        *(_DWORD *)(a1 + 16));
    if ( !*(_DWORD *)(a1 + 16) )
    {
      v2 = *(_QWORD *)(a1 + 8);
      if ( v2 )
        FreeImage(v2);
      RemoveFromLoadedProviderList(a1);
      MSCryptFree(v3);
    }
    LeaveCriticalSection(&g_csLoaderLock);
  }
}

```

## disassembly

```asm
0x180007ca0  push    rbx
0x180007ca2  sub     rsp, 30h
0x180007ca6  cmp     cs:g_fLoaderInitialized, 0
0x180007cad  mov     rbx, rcx
0x180007cb0  jz      short loc_180007D1A
0x180007cb2  test    rcx, rcx
0x180007cb5  jz      short loc_180007D1A
0x180007cb7  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180007cbe  call    cs:__imp_EnterCriticalSection
0x180007cc4  dec     dword ptr [rbx+10h]
0x180007cc7  mov     eax, [rbx+10h]
0x180007cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cd1  lea     rdx, WPP_GLOBAL_Control
0x180007cd8  cmp     rcx, rdx
0x180007cdb  jz      short loc_180007D07
0x180007cdd  test    byte ptr [rcx+1Ch], 20h
0x180007ce1  jz      short loc_180007D07
0x180007ce3  mov     rcx, [rcx+10h]
0x180007ce7  lea     r8, WPP_67679bdabad938a7dfcc8815ccec1def_Traceguids
0x180007cee  mov     [rsp+38h+var_10], eax
0x180007cf2  mov     edx, 1Dh
0x180007cf7  mov     rax, [rbx]
0x180007cfa  mov     r9, rbx
0x180007cfd  mov     [rsp+38h+var_18], rax
0x180007d02  call    WPP_SF_qSD
0x180007d07  cmp     dword ptr [rbx+10h], 0
0x180007d0b  jz      short loc_180007D20
0x180007d0d  lea     rcx, g_csLoaderLock; lpCriticalSection
0x180007d14  call    cs:__imp_LeaveCriticalSection
0x180007d1a  add     rsp, 30h
0x180007d1e  pop     rbx
0x180007d1f  retn
0x180007d20  mov     rcx, [rbx+8]
0x180007d24  test    rcx, rcx
0x180007d27  jz      short loc_180007D2E
0x180007d29  call    _FreeImage
0x180007d2e  mov     rcx, rbx
0x180007d31  call    _RemoveFromLoadedProviderList
0x180007d36  call    MSCryptFree
0x180007d3b  jmp     short loc_180007D0D
```
