# CoCreateInstanceAndLoadFromFile(_GUID const &,ushort const *,_GUID const &,void * *)

- ea: `0x18000b13c`
- end: `0x18000b1de`
- name: `?CoCreateInstanceAndLoadFromFile@@YAJAEBU_GUID@@PEBG0PEAPEAX@Z`
- size: `162`
- prototype: `int(const struct _GUID *, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c714`

## callees

- `0x180002620`
- `0x18000b13c`
- `0x18000cf58`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b18e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b18e`

## pseudocode

```c
__int64 __fastcall CoCreateInstanceAndLoadFromFile(
        const struct _GUID *a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT Instance; // ebx
  unsigned int v7; // r8d
  const struct _GUID *v8; // r9
  struct IUnknown *v10; // [rsp+30h] [rbp-18h] BYREF

  *a4 = 0;
  v10 = 0;
  Instance = CoCreateInstance(
               &CLSID_PersistentZoneIdentifier,
               0,
               0x4001u,
               &GUID_cd45f185_1b21_48e2_967b_ead743a8914e,
               (LPVOID *)&v10);
  if ( Instance >= 0 )
  {
    Instance = _AndLoadFromFile(v10, a2, v7, v8, a4);
    ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000b13c  mov     r11, rsp
0x18000b13f  mov     [r11+8], rbx
0x18000b143  mov     [r11+18h], rsi
0x18000b147  push    rdi
0x18000b148  sub     rsp, 40h
0x18000b14c  mov     rax, cs:__security_cookie
0x18000b153  xor     rax, rsp
0x18000b156  mov     [rsp+48h+var_10], rax
0x18000b15b  mov     rdi, r9
0x18000b15e  mov     qword ptr [r9], 0
0x18000b165  mov     rsi, rdx
0x18000b168  mov     qword ptr [r11-18h], 0
0x18000b170  lea     rax, [r11-18h]
0x18000b174  xor     edx, edx; pUnkOuter
0x18000b176  lea     r9, _GUID_cd45f185_1b21_48e2_967b_ead743a8914e; riid
0x18000b17d  mov     [r11-28h], rax
0x18000b181  mov     r8d, 4001h; dwClsContext
0x18000b187  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x18000b18e  call    cs:__imp_CoCreateInstance
0x18000b194  mov     ebx, eax
0x18000b196  test    eax, eax
0x18000b198  js      short loc_18000B1BF
0x18000b19a  mov     rcx, [rsp+48h+var_18]; struct IUnknown *
0x18000b19f  mov     rdx, rsi; unsigned __int16 *
0x18000b1a2  mov     [rsp+48h+var_28], rdi; void **
0x18000b1a7  call    ?_AndLoadFromFile@@YAJPEAUIUnknown@@PEBGKAEBU_GUID@@PEAPEAX@Z; _AndLoadFromFile(IUnknown *,ushort const *,ulong,_GUID const &,void * *)
0x18000b1ac  mov     rcx, [rsp+48h+var_18]
0x18000b1b1  mov     ebx, eax
0x18000b1b3  mov     rax, [rcx]
0x18000b1b6  mov     rax, [rax+10h]
0x18000b1ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1bf  mov     eax, ebx
0x18000b1c1  mov     rcx, [rsp+48h+var_10]
0x18000b1c6  xor     rcx, rsp; StackCookie
0x18000b1c9  call    __security_check_cookie
0x18000b1ce  mov     rbx, [rsp+48h+arg_0]
0x18000b1d3  mov     rsi, [rsp+48h+arg_10]
0x18000b1d8  add     rsp, 40h
0x18000b1dc  pop     rdi
0x18000b1dd  retn
```
