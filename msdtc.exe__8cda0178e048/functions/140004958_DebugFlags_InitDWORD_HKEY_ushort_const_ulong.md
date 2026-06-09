# DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)

- ea: `0x140004958`
- end: `0x1400049ff`
- name: `?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z`
- size: `167`
- prototype: `void __fastcall(HKEY hKey, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x140004a08`

## callees

- `0x140004958`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400049aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400049aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400049e9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400049e9`

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
0x140004958  mov     r11, rsp
0x14000495b  mov     [r11+8], rbx
0x14000495f  mov     [r11+20h], rbp
0x140004963  mov     [r11+18h], r8
0x140004967  mov     [r11+10h], rdx
0x14000496b  push    rdi
0x14000496c  sub     rsp, 30h
0x140004970  mov     ebx, cs:?sm_dwEventDispatchTime@DebugFlags@@0KA; ulong DebugFlags::sm_dwEventDispatchTime
0x140004976  lea     rax, [r11+10h]
0x14000497a  mov     [r11-10h], rax
0x14000497e  lea     rbp, ?sm_dwEventDispatchTime@DebugFlags@@0KA; ulong DebugFlags::sm_dwEventDispatchTime
0x140004985  lea     r9, [r11+18h]; lpType
0x140004989  mov     [r11-18h], rbp
0x14000498d  xor     r8d, r8d; lpReserved
0x140004990  mov     [rsp+38h+arg_8], 4
0x140004998  lea     rdx, aEventdispatcht; "EventDispatchTtime"
0x14000499f  mov     [rsp+38h+arg_10], 4
0x1400049a7  mov     rdi, rcx
0x1400049aa  call    cs:__imp_RegQueryValueExW
0x1400049b0  test    eax, eax
0x1400049b2  jnz     short loc_1400049C3
0x1400049b4  cmp     [rsp+38h+arg_10], 4
0x1400049b9  jz      short loc_1400049EF
0x1400049bb  mov     cs:?sm_dwEventDispatchTime@DebugFlags@@0KA, ebx; ulong DebugFlags::sm_dwEventDispatchTime
0x1400049c1  jmp     short loc_1400049EF
0x1400049c3  mov     [rsp+38h+cbData], 4; cbData
0x1400049cb  lea     rdx, aEventdispatcht; "EventDispatchTtime"
0x1400049d2  mov     r9d, 4; dwType
0x1400049d8  mov     [rsp+38h+lpData], rbp; lpData
0x1400049dd  xor     r8d, r8d; Reserved
0x1400049e0  mov     cs:?sm_dwEventDispatchTime@DebugFlags@@0KA, ebx; ulong DebugFlags::sm_dwEventDispatchTime
0x1400049e6  mov     rcx, rdi; hKey
0x1400049e9  call    cs:__imp_RegSetValueExW
0x1400049ef  mov     rbx, [rsp+38h+arg_0]
0x1400049f4  mov     rbp, [rsp+38h+arg_18]
0x1400049f9  add     rsp, 30h
0x1400049fd  pop     rdi
0x1400049fe  retn
```
