# SaveMetabase(void)

- ea: `0x180001c04`
- end: `0x180001cde`
- name: `?SaveMetabase@@YAHXZ`
- size: `218`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180001cf0`

## callees

- `0x180001c04`
- `0x180005010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180001cc9`
- `KERNEL32!SetLastError` at `0x180001cc9`
- `ole32!CoCreateInstance` at `0x180001c31`
- `ole32!CoCreateInstance` at `0x180001c31`
- `IisRTL!PuDbgPrint` at `0x180001cb1`
- `IisRTL!PuDbgPrint` at `0x180001cb1`

## string_xrefs

- `0x180001c8d`: `IISAdmin Service, SaveMetabase() failed, hr=%lu\n`

## pseudocode

```c
__int64 SaveMetabase(void)
{
  HRESULT v0; // ebx
  DWORD v1; // ecx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  v0 = CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x15u, &IID_IMSAdminBase_W, &ppv);
  if ( v0 >= 0 )
  {
    v0 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 160LL))(ppv);
    if ( v0 >= 0 )
      v0 = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v0 >= 0 )
    return 1;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\iisadmin\\main.cxx",
      370,
      "SaveMetabase",
      "IISAdmin Service, SaveMetabase() failed, hr=%lu\n",
      v0);
  v1 = (unsigned __int16)v0;
  if ( (v0 & 0x1FFF0000) != 0x70000 )
    v1 = v0;
  SetLastError(v1);
  return 0;
}

```

## disassembly

```asm
0x180001c04  push    rbx
0x180001c06  sub     rsp, 30h
0x180001c0a  xor     edx, edx; pUnkOuter
0x180001c0c  mov     [rsp+38h+arg_0], 0
0x180001c15  lea     rax, [rsp+38h+arg_0]
0x180001c1a  lea     r9, IID_IMSAdminBase_W; riid
0x180001c21  mov     [rsp+38h+ppv], rax; ppv
0x180001c26  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x180001c2d  lea     r8d, [rdx+15h]; dwClsContext
0x180001c31  call    cs:__imp_CoCreateInstance
0x180001c37  mov     ebx, eax
0x180001c39  test    eax, eax
0x180001c3b  js      short loc_180001C5A
0x180001c3d  mov     rcx, [rsp+38h+arg_0]
0x180001c42  mov     rax, [rcx]
0x180001c45  mov     rax, [rax+0A0h]
0x180001c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c51  mov     ebx, eax
0x180001c53  xor     eax, eax
0x180001c55  test    ebx, ebx
0x180001c57  cmovns  ebx, eax
0x180001c5a  mov     rcx, [rsp+38h+arg_0]
0x180001c5f  test    rcx, rcx
0x180001c62  jz      short loc_180001C79
0x180001c64  mov     rax, [rcx]
0x180001c67  mov     rax, [rax+10h]
0x180001c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c70  mov     [rsp+38h+arg_0], 0
0x180001c79  test    ebx, ebx
0x180001c7b  jns     short loc_180001CD3
0x180001c7d  test    byte ptr cs:g_dwDebugFlags, 3
0x180001c84  jz      short loc_180001CB7
0x180001c86  mov     rcx, cs:g_pDebug
0x180001c8d  lea     rax, aIisadminServic_2; "IISAdmin Service, SaveMetabase() failed"...
0x180001c94  mov     [rsp+38h+var_10], ebx
0x180001c98  lea     r9, aSavemetabase; "SaveMetabase"
0x180001c9f  mov     r8d, 172h
0x180001ca5  mov     [rsp+38h+ppv], rax
0x180001caa  lea     rdx, aInetsrvIisMbIi_0; "inetsrv\\iis\\mb\\iisadmin\\main.cxx"
0x180001cb1  call    cs:__imp_PuDbgPrint
0x180001cb7  mov     eax, ebx
0x180001cb9  movzx   ecx, bx
0x180001cbc  and     eax, 1FFF0000h
0x180001cc1  cmp     eax, 70000h
0x180001cc6  cmovnz  ecx, ebx; dwErrCode
0x180001cc9  call    cs:__imp_SetLastError
0x180001ccf  xor     eax, eax
0x180001cd1  jmp     short loc_180001CD8
0x180001cd3  mov     eax, 1
0x180001cd8  add     rsp, 30h
0x180001cdc  pop     rbx
0x180001cdd  retn
```
