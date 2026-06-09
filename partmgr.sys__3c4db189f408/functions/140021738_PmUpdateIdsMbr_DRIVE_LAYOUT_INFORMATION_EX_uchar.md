# PmUpdateIdsMbr(_DRIVE_LAYOUT_INFORMATION_EX *,uchar)

- ea: `0x140021738`
- end: `0x1400217e2`
- name: `?PmUpdateIdsMbr@@YAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@E@Z`
- size: `170`
- prototype: `void __fastcall(struct _DRIVE_LAYOUT_INFORMATION_EX *, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400214fc`

## callees

- `0x140010f20`
- `0x140021738`
- `0x1400217e8`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400217b8`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400217b8`

## pseudocode

```c
void __fastcall PmUpdateIdsMbr(struct _DRIVE_LAYOUT_INFORMATION_EX *a1)
{
  char *DeviceExtension; // rsi
  ULONG v3; // ebx
  __int64 Buffer; // [rsp+20h] [rbp-48h] BYREF
  __int128 v5; // [rsp+28h] [rbp-40h]
  __int128 v6; // [rsp+38h] [rbp-30h]
  struct _GUID v7; // [rsp+48h] [rbp-20h] BYREF

  *(_DWORD *)&v7.Data2 = *(_DWORD *)&GUID_NULL.Data2;
  *(_DWORD *)v7.Data4 = *(_DWORD *)GUID_NULL.Data4;
  *(_DWORD *)&v7.Data4[4] = *(_DWORD *)&GUID_NULL.Data4[4];
  Buffer = 0;
  v5 = 0;
  v7.Data1 = 0;
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  v6 = 0;
  do
  {
    PmUuidCreate(&v7);
    v3 = *(_DWORD *)&v7.Data4[4] ^ *(_DWORD *)v7.Data4 ^ *(_DWORD *)&v7.Data2 ^ v7.Data1;
    LODWORD(v6) = v3;
  }
  while ( RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(DeviceExtension + 200), &Buffer) );
  a1->Mbr.Signature = v3;
}

```

## disassembly

```asm
0x140021738  push    rbp
0x14002173a  push    rbx
0x14002173b  push    rsi
0x14002173c  push    rdi
0x14002173d  mov     rbp, rsp
0x140021740  sub     rsp, 68h
0x140021744  mov     rax, cs:__security_cookie
0x14002174b  xor     rax, rsp
0x14002174e  mov     [rbp+var_10], rax
0x140021752  mov     eax, dword ptr cs:?GUID_NULL@@3U_GUID@@B.Data2; _GUID const GUID_NULL ...
0x140021758  xorps   xmm0, xmm0
0x14002175b  mov     dword ptr [rbp+var_20.Data2], eax
0x14002175e  mov     rdi, rcx
0x140021761  mov     eax, dword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x140021767  mov     dword ptr [rbp+var_20.Data4], eax
0x14002176a  mov     eax, dword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4+4; _GUID const GUID_NULL ...
0x140021770  mov     dword ptr [rbp+var_20.Data4+4], eax
0x140021773  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14002177a  mov     [rbp+Buffer], 0
0x140021782  movups  [rbp+var_40], xmm0
0x140021786  mov     [rbp+var_20.Data1], 0
0x14002178d  mov     rsi, [rax+40h]
0x140021791  movups  [rbp+var_30], xmm0
0x140021795  lea     rcx, [rbp+var_20]; struct _GUID *
0x140021799  call    ?PmUuidCreate@@YAXPEAU_GUID@@@Z; PmUuidCreate(_GUID *)
0x14002179e  mov     ebx, [rbp+var_20.Data1]
0x1400217a1  lea     rdx, [rbp+Buffer]; Buffer
0x1400217a5  xor     ebx, dword ptr [rbp+var_20.Data2]
0x1400217a8  lea     rcx, [rsi+0C8h]; Table
0x1400217af  xor     ebx, dword ptr [rbp+var_20.Data4]
0x1400217b2  xor     ebx, dword ptr [rbp+var_20.Data4+4]
0x1400217b5  mov     dword ptr [rbp+var_30], ebx
0x1400217b8  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400217bf  nop     dword ptr [rax+rax+00h]
0x1400217c4  test    rax, rax
0x1400217c7  jnz     short loc_140021795
0x1400217c9  mov     [rdi+8], ebx
0x1400217cc  mov     rcx, [rbp+var_10]
0x1400217d0  xor     rcx, rsp; StackCookie
0x1400217d3  call    __security_check_cookie
0x1400217d8  add     rsp, 68h
0x1400217dc  pop     rdi
0x1400217dd  pop     rsi
0x1400217de  pop     rbx
0x1400217df  pop     rbp
0x1400217e0  retn
```
