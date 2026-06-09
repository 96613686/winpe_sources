# NetTabAddComponent

- ea: `0x180024eec`
- end: `0x180024fd5`
- name: `NetTabAddComponent`
- size: `233`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024fdc`

## callees

- `0x18002049c`
- `0x180021348`
- `0x180024eec`
- `0x1800252b8`
- `0x180025a5c`
- `0x18002990c`
- `0x180030010`

## import_xrefs

- `USER32!GetDlgItem` at `0x180024f8e`
- `USER32!GetDlgItem` at `0x180024f8e`

## pseudocode

```c
__int64 __fastcall NetTabAddComponent(HWND hWnd)
{
  _QWORD *v2; // rdi
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // eax
  HWND DlgItem; // rax
  __int128 v9; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  _QWORD *v11; // [rsp+68h] [rbp+10h] BYREF

  v11 = 0;
  RasSrvGetDatabaseHandle(hWnd, 16, (__int64 *)&v11);
  v2 = v11;
  if ( !v11 )
    return 87;
  v4 = v11[5];
  if ( !v4 )
    return 1003;
  v5 = *v11;
  v9 = 0;
  LODWORD(v9) = 1;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, HWND, __int64, __int128 *))(*(_QWORD *)v4 + 40LL))(v4, hWnd, v5, &v9);
  v3 = v6;
  if ( v6 == 303136 )
    goto LABEL_9;
  if ( v6 == 1 )
    return 1223;
  if ( v6 >= 0 )
  {
    v3 = 0;
LABEL_9:
    netDbReload(v2);
    DlgItem = GetDlgItem(hWnd, 7036);
    if ( DlgItem )
      NetTabRefreshListView(DlgItem);
    NetTabDisableRollback(hWnd);
    if ( v3 == 303136 )
      RasSrvReboot(hWnd);
  }
  return v3;
}

```

## disassembly

```asm
0x180024eec  mov     rax, rsp
0x180024eef  mov     [rax+8], rbx
0x180024ef3  mov     [rax+18h], rsi
0x180024ef7  push    rdi
0x180024ef8  sub     rsp, 50h
0x180024efc  lea     r8, [rax+10h]
0x180024f00  mov     qword ptr [rax+10h], 0
0x180024f08  mov     edx, 10h
0x180024f0d  mov     rsi, rcx
0x180024f10  call    RasSrvGetDatabaseHandle
0x180024f15  mov     rdi, [rsp+58h+arg_8]
0x180024f1a  test    rdi, rdi
0x180024f1d  jnz     short loc_180024F27
0x180024f1f  lea     ebx, [rdi+57h]
0x180024f22  jmp     loc_180024FC3
0x180024f27  mov     rcx, [rdi+28h]
0x180024f2b  test    rcx, rcx
0x180024f2e  jnz     short loc_180024F3A
0x180024f30  mov     ebx, 3EBh
0x180024f35  jmp     loc_180024FC3
0x180024f3a  mov     r8, [rdi]
0x180024f3d  lea     r9, [rsp+58h+var_28]
0x180024f42  xor     eax, eax
0x180024f44  xorps   xmm0, xmm0
0x180024f47  movups  [rsp+58h+var_28], xmm0
0x180024f4c  mov     dword ptr [rsp+58h+var_28], 1
0x180024f54  mov     rdx, rsi
0x180024f57  mov     [rsp+58h+var_18], rax
0x180024f5c  mov     rax, [rcx]
0x180024f5f  mov     rax, [rax+28h]
0x180024f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f68  mov     ebx, eax
0x180024f6a  cmp     eax, 4A020h
0x180024f6f  jnz     short loc_180024F73
0x180024f71  jmp     short loc_180024F7E
0x180024f73  cmp     eax, 1
0x180024f76  jz      short loc_180024FBE
0x180024f78  test    eax, eax
0x180024f7a  js      short loc_180024FC3
0x180024f7c  xor     ebx, ebx
0x180024f7e  mov     rcx, rdi
0x180024f81  call    netDbReload
0x180024f86  mov     edx, 1B7Ch; nIDDlgItem
0x180024f8b  mov     rcx, rsi; hDlg
0x180024f8e  call    cs:__imp_GetDlgItem
0x180024f94  test    rax, rax
0x180024f97  jz      short loc_180024FA4
0x180024f99  mov     rdx, rdi
0x180024f9c  mov     rcx, rax; hWnd
0x180024f9f  call    NetTabRefreshListView
0x180024fa4  mov     rcx, rsi; hWnd
0x180024fa7  call    NetTabDisableRollback
0x180024fac  cmp     ebx, 4A020h
0x180024fb2  jnz     short loc_180024FC3
0x180024fb4  mov     rcx, rsi; hWnd
0x180024fb7  call    RasSrvReboot
0x180024fbc  jmp     short loc_180024FC3
0x180024fbe  mov     ebx, 4C7h
0x180024fc3  mov     rsi, [rsp+58h+arg_10]
0x180024fc8  mov     eax, ebx
0x180024fca  mov     rbx, [rsp+58h+arg_0]
0x180024fcf  add     rsp, 50h
0x180024fd3  pop     rdi
0x180024fd4  retn
```
