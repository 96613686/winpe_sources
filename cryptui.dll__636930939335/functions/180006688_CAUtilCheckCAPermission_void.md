# CAUtilCheckCAPermission(void *)

- ea: `0x180006688`
- end: `0x1800066f1`
- name: `?CAUtilCheckCAPermission@@YAHPEAX@Z`
- size: `105`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800067b8`

## callees

- `0x180006688`
- `0x180006cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066de`
- `certca!__imp_CAAccessCheck` at `0x1800066b5`
- `certca!__imp_CAAccessCheck` at `0x1800066b5`

## pseudocode

```c
_BOOL8 __fastcall CAUtilCheckCAPermission(void *a1)
{
  HANDLE ClientIdentity; // rax
  void *v3; // rbx
  BOOL v4; // edi

  ClientIdentity = GetClientIdentity();
  v3 = ClientIdentity;
  if ( ClientIdentity )
  {
    v4 = CAAccessCheck(a1, ClientIdentity) == 0;
  }
  else
  {
    GetLastError();
    v4 = 0;
  }
  if ( v3 )
    CloseHandle(v3);
  return v4;
}

```

## disassembly

```asm
0x180006688  mov     [rsp+arg_0], rbx
0x18000668d  push    rdi
0x18000668e  sub     rsp, 30h
0x180006692  mov     rdi, rcx
0x180006695  call    ?GetClientIdentity@@YAPEAXXZ; GetClientIdentity(void)
0x18000669a  mov     rbx, rax
0x18000669d  mov     [rsp+38h+arg_8], rax
0x1800066a2  test    rax, rax
0x1800066a5  jnz     short loc_1800066AF
0x1800066a7  call    cs:__imp_GetLastError
0x1800066ad  jmp     short loc_1800066D4
0x1800066af  mov     rdx, rax
0x1800066b2  mov     rcx, rdi
0x1800066b5  call    cs:__imp_CAAccessCheck
0x1800066bb  xor     edi, edi
0x1800066bd  test    eax, eax
0x1800066bf  setz    dil
0x1800066c3  mov     [rsp+38h+var_18], edi
0x1800066c7  jmp     short loc_1800066D6
0x1800066c9  call    cs:__imp_GetLastError
0x1800066cf  mov     rbx, [rsp+38h+arg_8]
0x1800066d4  xor     edi, edi
0x1800066d6  test    rbx, rbx
0x1800066d9  jz      short loc_1800066E4
0x1800066db  mov     rcx, rbx; hObject
0x1800066de  call    cs:__imp_CloseHandle
0x1800066e4  mov     eax, edi
0x1800066e6  mov     rbx, [rsp+38h+arg_0]
0x1800066eb  add     rsp, 30h
0x1800066ef  pop     rdi
0x1800066f0  retn
```
