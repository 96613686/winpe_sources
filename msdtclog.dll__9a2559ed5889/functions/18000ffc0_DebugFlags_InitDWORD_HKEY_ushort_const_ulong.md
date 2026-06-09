# DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)

- ea: `0x18000ffc0`
- end: `0x180010067`
- name: `?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z`
- size: `167`
- prototype: `void __fastcall(HKEY hKey, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180010070`

## callees

- `0x18000ffc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010051`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010051`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010012`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010012`

## pseudocode

```c
void __fastcall DebugFlags::InitDWORD(HKEY hKey, const unsigned __int16 *a2, unsigned int *a3)
{
  int v3; // ebx
  DWORD v5; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+4Ch] [rbp+14h]
  DWORD v7; // [rsp+50h] [rbp+18h] BYREF
  int v8; // [rsp+54h] [rbp+1Ch]

  v8 = HIDWORD(a3);
  v6 = HIDWORD(a2);
  v3 = *(_DWORD *)&DebugFlags::sm_dwEventDispatchTime;
  v5 = 4;
  v7 = 4;
  if ( RegQueryValueExW(hKey, L"EventDispatchTtime", 0, &v7, &DebugFlags::sm_dwEventDispatchTime, &v5) )
  {
    *(_DWORD *)&DebugFlags::sm_dwEventDispatchTime = v3;
    RegSetValueExW(hKey, L"EventDispatchTtime", 0, 4u, &DebugFlags::sm_dwEventDispatchTime, 4u);
  }
  else if ( v7 != 4 )
  {
    *(_DWORD *)&DebugFlags::sm_dwEventDispatchTime = v3;
  }
}

```

## disassembly

```asm
0x18000ffc0  mov     r11, rsp
0x18000ffc3  mov     [r11+8], rbx
0x18000ffc7  mov     [r11+20h], rbp
0x18000ffcb  mov     [r11+18h], r8
0x18000ffcf  mov     [r11+10h], rdx
0x18000ffd3  push    rdi
0x18000ffd4  sub     rsp, 30h
0x18000ffd8  mov     ebx, cs:?sm_dwEventDispatchTime@DebugFlags@@0KA; ulong DebugFlags::sm_dwEventDispatchTime
0x18000ffde  lea     rax, [r11+10h]
0x18000ffe2  mov     [r11-10h], rax
0x18000ffe6  lea     rbp, ?sm_dwEventDispatchTime@DebugFlags@@0KA; ulong DebugFlags::sm_dwEventDispatchTime
0x18000ffed  lea     r9, [r11+18h]; lpType
0x18000fff1  mov     [r11-18h], rbp
0x18000fff5  xor     r8d, r8d; lpReserved
0x18000fff8  mov     [rsp+38h+arg_8], 4
0x180010000  lea     rdx, aEventdispatcht; "EventDispatchTtime"
0x180010007  mov     [rsp+38h+arg_10], 4
0x18001000f  mov     rdi, rcx
0x180010012  call    cs:__imp_RegQueryValueExW
0x180010018  test    eax, eax
0x18001001a  jnz     short loc_18001002B
0x18001001c  cmp     [rsp+38h+arg_10], 4
0x180010021  jz      short loc_180010057
0x180010023  mov     cs:?sm_dwEventDispatchTime@DebugFlags@@0KA, ebx; ulong DebugFlags::sm_dwEventDispatchTime
0x180010029  jmp     short loc_180010057
0x18001002b  mov     [rsp+38h+cbData], 4; cbData
0x180010033  lea     rdx, aEventdispatcht; "EventDispatchTtime"
0x18001003a  mov     r9d, 4; dwType
0x180010040  mov     [rsp+38h+lpData], rbp; lpData
0x180010045  xor     r8d, r8d; Reserved
0x180010048  mov     cs:?sm_dwEventDispatchTime@DebugFlags@@0KA, ebx; ulong DebugFlags::sm_dwEventDispatchTime
0x18001004e  mov     rcx, rdi; hKey
0x180010051  call    cs:__imp_RegSetValueExW
0x180010057  mov     rbx, [rsp+38h+arg_0]
0x18001005c  mov     rbp, [rsp+38h+arg_18]
0x180010061  add     rsp, 30h
0x180010065  pop     rdi
0x180010066  retn
```
