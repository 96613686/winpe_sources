# NetTabActivate

- ea: `0x180024e38`
- end: `0x180024ee5`
- name: `NetTabActivate`
- size: `173`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800250c0`

## callees

- `0x18002049c`
- `0x180024e38`
- `0x180025a5c`
- `0x180026710`
- `0x180029fc0`

## import_xrefs

- `USER32!GetDlgItem` at `0x180024eb6`
- `USER32!GetDlgItem` at `0x180024eb6`

## string_xrefs

- `0x180024e56`: `NetTabActivate: updating components.`

## pseudocode

```c
__int64 __fastcall NetTabActivate(HWND hWnd, __int16 a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 0;
  DbgOutputTrace("NetTabActivate: updating components.");
  result = RasSrvGetDatabaseHandle(hWnd);
  if ( !(_DWORD)result )
    return 87;
  return result;
}

```

## disassembly

```asm
0x180024e38  mov     [rsp+arg_0], rbx
0x180024e3d  mov     [rsp+arg_10], rsi
0x180024e42  push    rdi
0x180024e43  sub     rsp, 20h
0x180024e47  xor     esi, esi
0x180024e49  mov     rdi, rcx
0x180024e4c  mov     [rsp+28h+arg_8], rsi
0x180024e51  test    dx, dx
0x180024e54  jz      short loc_180024ECC
0x180024e56  lea     rcx, aNettabactivate; "NetTabActivate: updating components."
0x180024e5d  call    DbgOutputTrace
0x180024e62  lea     r8, [rsp+28h+arg_8]
0x180024e67  mov     rcx, rdi; hWnd
0x180024e6a  lea     edx, [rsi+10h]
0x180024e6d  call    RasSrvGetDatabaseHandle
0x180024e72  test    eax, eax
0x180024e74  jnz     short loc_180024ECE
0x180024e76  mov     rbx, [rsp+28h+arg_8]
0x180024e7b  test    rbx, rbx
0x180024e7e  jnz     short loc_180024E85
0x180024e80  lea     eax, [rsi+57h]
0x180024e83  jmp     short loc_180024ECE
0x180024e85  mov     edx, esi
0x180024e87  cmp     edx, [rbx+10h]
0x180024e8a  jnb     short loc_180024EDE
0x180024e8c  mov     rax, [rbx+18h]
0x180024e90  mov     ecx, edx
0x180024e92  mov     rcx, [rax+rcx*8]
0x180024e96  cmp     dword ptr [rcx+34h], 4
0x180024e9a  jz      short loc_180024EA0
0x180024e9c  inc     edx
0x180024e9e  jmp     short loc_180024E87
0x180024ea0  test    rcx, rcx
0x180024ea3  jz      short loc_180024EDE
0x180024ea5  add     rcx, 38h ; '8'
0x180024ea9  call    svcGetEnabling
0x180024eae  mov     edx, 1B7Ch; nIDDlgItem
0x180024eb3  mov     rcx, rdi; hDlg
0x180024eb6  call    cs:__imp_GetDlgItem
0x180024ebc  test    rax, rax
0x180024ebf  jz      short loc_180024ECC
0x180024ec1  mov     rdx, rbx
0x180024ec4  mov     rcx, rax; hWnd
0x180024ec7  call    NetTabRefreshListView
0x180024ecc  xor     eax, eax
0x180024ece  mov     rbx, [rsp+28h+arg_0]
0x180024ed3  mov     rsi, [rsp+28h+arg_10]
0x180024ed8  add     rsp, 20h
0x180024edc  pop     rdi
0x180024edd  retn
0x180024ede  mov     eax, 490h
0x180024ee3  jmp     short loc_180024ECE
```
