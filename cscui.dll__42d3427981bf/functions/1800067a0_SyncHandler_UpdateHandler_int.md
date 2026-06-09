# SyncHandler_UpdateHandler(int)

- ea: `0x1800067a0`
- end: `0x180006860`
- name: `?SyncHandler_UpdateHandler@@YAJH@Z`
- size: `192`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006740`
- `0x180019a20`

## callees

- `0x1800067a0`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800067e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800067e6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006802`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180006802`

## pseudocode

```c
HRESULT __fastcall SyncHandler_UpdateHandler(int a1)
{
  HRESULT result; // eax
  int v3; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-78h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-68h] BYREF

  ppv = 0;
  result = CoCreateInstance(&CLSID_SyncMgrControl, 0, 0x15u, &GUID_9b63616c_36b2_46bc_959f_c1593952d19b, &ppv);
  if ( result >= 0 )
  {
    if ( StringFromGUID2(&CLSID_CscUpdateHandler, sz, 39) <= 0 )
      v3 = -2147024774;
    else
      v3 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, bool))(*(_QWORD *)ppv + 80LL))(ppv, sz, a1 != 0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800067a0  push    rbx
0x1800067a2  sub     rsp, 0A0h
0x1800067a9  mov     rax, cs:__security_cookie
0x1800067b0  xor     rax, rsp
0x1800067b3  mov     [rsp+0A8h+var_18], rax
0x1800067bb  mov     ebx, ecx
0x1800067bd  mov     [rsp+0A8h+var_78], 0
0x1800067c6  lea     rax, [rsp+0A8h+var_78]
0x1800067cb  xor     edx, edx; pUnkOuter
0x1800067cd  lea     rcx, CLSID_SyncMgrControl; rclsid
0x1800067d4  mov     [rsp+0A8h+ppv], rax; ppv
0x1800067d9  lea     r9, _GUID_9b63616c_36b2_46bc_959f_c1593952d19b; riid
0x1800067e0  mov     r8d, 15h; dwClsContext
0x1800067e6  call    cs:__imp_CoCreateInstance
0x1800067ec  test    eax, eax
0x1800067ee  js      short loc_180006847
0x1800067f0  mov     r8d, 27h ; '''; cchMax
0x1800067f6  lea     rdx, [rsp+0A8h+sz]; lpsz
0x1800067fb  lea     rcx, CLSID_CscUpdateHandler; rguid
0x180006802  call    cs:__imp_StringFromGUID2
0x180006808  test    eax, eax
0x18000680a  jle     short loc_18000682F
0x18000680c  mov     rcx, [rsp+0A8h+var_78]
0x180006811  lea     rdx, [rsp+0A8h+sz]
0x180006816  xor     r8d, r8d
0x180006819  test    ebx, ebx
0x18000681b  mov     rax, [rcx]
0x18000681e  setnz   r8b
0x180006822  mov     rax, [rax+50h]
0x180006826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000682b  mov     ebx, eax
0x18000682d  jmp     short loc_180006834
0x18000682f  mov     ebx, 8007007Ah
0x180006834  mov     rcx, [rsp+0A8h+var_78]
0x180006839  mov     rax, [rcx]
0x18000683c  mov     rax, [rax+10h]
0x180006840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006845  mov     eax, ebx
0x180006847  mov     rcx, [rsp+0A8h+var_18]
0x18000684f  xor     rcx, rsp; StackCookie
0x180006852  call    __security_check_cookie
0x180006857  add     rsp, 0A0h
0x18000685e  pop     rbx
0x18000685f  retn
```
