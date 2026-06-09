# devGetSystemDeviceInfo

- ea: `0x180028050`
- end: `0x18002811a`
- name: `devGetSystemDeviceInfo`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180027e84`
- `0x1800281c8`

## callees

- `0x180021438`
- `0x180026710`
- `0x180028050`

## import_xrefs

- `rasman!RasGetDeviceConfigInfo` at `0x180028091`
- `rasman!RasGetDeviceConfigInfo` at `0x180028105`
- `rasman!RasGetDeviceConfigInfo` at `0x180028091`
- `rasman!RasGetDeviceConfigInfo` at `0x180028105`

## pseudocode

```c
__int64 __fastcall devGetSystemDeviceInfo(__int64 *a1, _DWORD *a2)
{
  unsigned int DeviceConfigInfo; // eax
  unsigned int v5; // ebx
  __int64 v7; // rcx
  __int64 v8; // rax
  _DWORD v9[6]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+18h] BYREF
  int v11; // [rsp+68h] [rbp+20h] BYREF

  v9[0] = 6;
  v10 = 0;
  v11 = 0;
  DeviceConfigInfo = RasGetDeviceConfigInfo(0, v9, &v11, &v10, 0);
  v5 = DeviceConfigInfo;
  if ( DeviceConfigInfo && DeviceConfigInfo != 603 )
  {
    DbgOutputTrace("devGetSysDevInfo: 0x%08x from RasGetDevCfgInfo (1)", DeviceConfigInfo);
    return v5;
  }
  v7 = v10;
  *a2 = v11;
  if ( !(_DWORD)v7 )
  {
    *a2 = 0;
    return 0;
  }
  v8 = RassrvAlloc(v7, 1);
  *a1 = v8;
  if ( v8 )
  {
    v5 = RasGetDeviceConfigInfo(0, v9, a2, &v10, v8);
    if ( v5 )
    {
      DbgOutputTrace("devGetSysDevInfo: 0x%08x from RasGetDevCfgInfo (2)", v5);
      return v5;
    }
    return 0;
  }
  return 8;
}

```

## disassembly

```asm
0x180028050  mov     rax, rsp
0x180028053  mov     [rax+8], rbx
0x180028057  mov     [rax+10h], rsi
0x18002805b  push    rdi
0x18002805c  sub     rsp, 40h
0x180028060  mov     rdi, rdx
0x180028063  mov     dword ptr [rax-18h], 6
0x18002806a  mov     rsi, rcx
0x18002806d  mov     dword ptr [rax+18h], 0
0x180028074  lea     rdx, [rax-18h]
0x180028078  mov     dword ptr [rax+20h], 0
0x18002807f  xor     ecx, ecx
0x180028081  mov     qword ptr [rax-28h], 0
0x180028089  lea     r9, [rax+18h]
0x18002808d  lea     r8, [rax+20h]
0x180028091  call    cs:__imp_RasGetDeviceConfigInfo
0x180028097  mov     ebx, eax
0x180028099  test    eax, eax
0x18002809b  jz      short loc_1800280B6
0x18002809d  cmp     eax, 25Bh
0x1800280a2  jz      short loc_1800280B6
0x1800280a4  lea     rcx, aDevgetsysdevin_0; "devGetSysDevInfo: 0x%08x from RasGetDev"...
0x1800280ab  mov     edx, ebx
0x1800280ad  call    DbgOutputTrace
0x1800280b2  mov     eax, ebx
0x1800280b4  jmp     short loc_1800280C8
0x1800280b6  mov     ecx, [rsp+48h+arg_10]
0x1800280ba  mov     eax, [rsp+48h+arg_18]
0x1800280be  mov     [rdi], eax
0x1800280c0  test    ecx, ecx
0x1800280c2  jnz     short loc_1800280D8
0x1800280c4  mov     [rdi], ecx
0x1800280c6  xor     eax, eax
0x1800280c8  mov     rbx, [rsp+48h+arg_0]
0x1800280cd  mov     rsi, [rsp+48h+arg_8]
0x1800280d2  add     rsp, 40h
0x1800280d6  pop     rdi
0x1800280d7  retn
0x1800280d8  mov     edx, 1
0x1800280dd  call    RassrvAlloc
0x1800280e2  mov     [rsi], rax
0x1800280e5  test    rax, rax
0x1800280e8  jnz     short loc_1800280F1
0x1800280ea  mov     eax, 8
0x1800280ef  jmp     short loc_1800280C8
0x1800280f1  lea     r9, [rsp+48h+arg_10]
0x1800280f6  mov     [rsp+48h+var_28], rax
0x1800280fb  mov     r8, rdi
0x1800280fe  lea     rdx, [rsp+48h+var_18]
0x180028103  xor     ecx, ecx
0x180028105  call    cs:__imp_RasGetDeviceConfigInfo
0x18002810b  mov     ebx, eax
0x18002810d  test    eax, eax
0x18002810f  jz      short loc_1800280C6
0x180028111  lea     rcx, aDevgetsysdevin; "devGetSysDevInfo: 0x%08x from RasGetDev"...
0x180028118  jmp     short loc_1800280AB
```
