# GetSubclassHeader

- ea: `0x1800303b0`
- end: `0x180030435`
- name: `GetSubclassHeader`
- size: `133`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18002ff4c`
- `0x180030440`
- `0x1800306e0`

## callees

- `0x1800303b0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800303d6`
- `KERNEL32!GetCurrentProcessId` at `0x1800303d6`
- `KERNEL32!GlobalAddAtomW` at `0x1800303f9`
- `KERNEL32!GlobalAddAtomW` at `0x1800303f9`
- `USER32!GetPropW` at `0x180030424`
- `USER32!GetPropW` at `0x180030424`
- `USER32!GetWindowThreadProcessId` at `0x1800303c8`
- `USER32!GetWindowThreadProcessId` at `0x1800303c8`

## pseudocode

```c
HANDLE __fastcall GetSubclassHeader(HWND hWnd)
{
  ATOM v3; // ax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  dwProcessId = 0;
  if ( !GetWindowThreadProcessId(hWnd, &dwProcessId) )
    dwProcessId = 0;
  if ( dwProcessId != GetCurrentProcessId() )
    return 0;
  v3 = g_aCC32Subclass;
  if ( g_aCC32Subclass )
    return GetPropW(hWnd, (LPCWSTR)v3);
  v3 = GlobalAddAtomW(L"CC32SubclassInfo");
  if ( v3 )
    g_aCC32Subclass = v3;
  else
    v3 = g_aCC32Subclass;
  if ( v3 )
    return GetPropW(hWnd, (LPCWSTR)v3);
  else
    return 0;
}

```

## disassembly

```asm
0x1800303b0  mov     [rsp+arg_0], rbx
0x1800303b5  push    rdi
0x1800303b6  sub     rsp, 20h
0x1800303ba  xor     edi, edi
0x1800303bc  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x1800303c1  mov     [rsp+28h+dwProcessId], edi
0x1800303c5  mov     rbx, rcx
0x1800303c8  call    cs:__imp_GetWindowThreadProcessId
0x1800303ce  test    eax, eax
0x1800303d0  jnz     short loc_1800303D6
0x1800303d2  mov     [rsp+28h+dwProcessId], edi
0x1800303d6  call    cs:__imp_GetCurrentProcessId
0x1800303dc  cmp     [rsp+28h+dwProcessId], eax
0x1800303e0  jz      short loc_1800303E6
0x1800303e2  xor     eax, eax
0x1800303e4  jmp     short loc_18003042A
0x1800303e6  movzx   eax, cs:g_aCC32Subclass
0x1800303ed  test    ax, ax
0x1800303f0  jnz     short loc_18003041E
0x1800303f2  lea     rcx, c_szCC32Subclass; "CC32SubclassInfo"
0x1800303f9  call    cs:__imp_GlobalAddAtomW
0x1800303ff  test    ax, ax
0x180030402  jz      short loc_18003040D
0x180030404  mov     cs:g_aCC32Subclass, ax
0x18003040b  jmp     short loc_180030414
0x18003040d  movzx   eax, cs:g_aCC32Subclass
0x180030414  test    ax, ax
0x180030417  jnz     short loc_18003041E
0x180030419  mov     rax, rdi
0x18003041c  jmp     short loc_18003042A
0x18003041e  movzx   edx, ax; lpString
0x180030421  mov     rcx, rbx; hWnd
0x180030424  call    cs:__imp_GetPropW
0x18003042a  mov     rbx, [rsp+28h+arg_0]
0x18003042f  add     rsp, 20h
0x180030433  pop     rdi
0x180030434  retn
```
