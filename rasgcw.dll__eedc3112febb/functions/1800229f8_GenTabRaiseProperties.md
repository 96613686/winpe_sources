# GenTabRaiseProperties

- ea: `0x1800229f8`
- end: `0x180022ae3`
- name: `GenTabRaiseProperties`
- size: `235`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180022184`
- `0x1800222c0`

## callees

- `0x18002049c`
- `0x1800229f8`
- `0x180027ff0`
- `0x18002b970`

## import_xrefs

- `USER32!MessageBoxW` at `0x180022ac9`
- `USER32!MessageBoxW` at `0x180022ac9`
- `TAPI32!lineConfigDialogW` at `0x180022a6e`
- `TAPI32!lineConfigDialogW` at `0x180022a6e`

## pseudocode

```c
LONG __fastcall GenTabRaiseProperties(HWND hWnd, unsigned int a2)
{
  DWORD v4; // r9d
  __int64 v5; // rcx
  LONG result; // eax
  const WCHAR *StringPcch; // rbx
  const WCHAR *v8; // rax
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  RasSrvGetDatabaseHandle(hWnd);
  if ( (unsigned int)devGetDeviceHandle(0, a2, &v9) || !v9 )
    return 1003;
  v4 = *(_DWORD *)(v9 + 12);
  if ( (*(_BYTE *)(v9 + 20) & 4) != 0 )
  {
    v5 = *(_QWORD *)(v9 + 64);
    if ( v5 )
      v4 = *(_DWORD *)(v5 + 12);
  }
  result = lineConfigDialogW(v4, hWnd, 0);
  if ( result == -2147483575 )
  {
    StringPcch = (const WCHAR *)PszLoadStringPcch(hInstance);
    v8 = (const WCHAR *)PszLoadStringPcch(hInstance);
    MessageBoxW(hWnd, StringPcch, v8, 0x10u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800229f8  mov     rax, rsp
0x1800229fb  mov     [rax+8], rbx
0x1800229ff  push    rdi
0x180022a00  sub     rsp, 20h
0x180022a04  mov     ebx, edx
0x180022a06  mov     qword ptr [rax+18h], 0
0x180022a0e  mov     edx, 1
0x180022a13  mov     qword ptr [rax+20h], 0
0x180022a1b  lea     r8, [rax+18h]
0x180022a1f  mov     rdi, rcx
0x180022a22  call    RasSrvGetDatabaseHandle
0x180022a27  mov     rcx, [rsp+28h+arg_10]
0x180022a2c  lea     r8, [rsp+28h+arg_18]
0x180022a31  mov     edx, ebx
0x180022a33  call    devGetDeviceHandle
0x180022a38  test    eax, eax
0x180022a3a  jnz     loc_180022AD3
0x180022a40  mov     rax, [rsp+28h+arg_18]
0x180022a45  test    rax, rax
0x180022a48  jz      loc_180022AD3
0x180022a4e  test    byte ptr [rax+14h], 4
0x180022a52  mov     r9d, [rax+0Ch]
0x180022a56  jz      short loc_180022A65
0x180022a58  mov     rcx, [rax+40h]
0x180022a5c  test    rcx, rcx
0x180022a5f  jz      short loc_180022A65
0x180022a61  mov     r9d, [rcx+0Ch]
0x180022a65  xor     r8d, r8d; lpszDeviceClass
0x180022a68  mov     rdx, rdi; hwndOwner
0x180022a6b  mov     ecx, r9d; dwDeviceID
0x180022a6e  call    cs:__imp_lineConfigDialogW
0x180022a74  cmp     eax, 80000049h
0x180022a79  jnz     short loc_180022AD8
0x180022a7b  mov     rcx, cs:hInstance; hModule
0x180022a82  lea     r8, [rsp+28h+arg_10]
0x180022a87  mov     edx, 1CDDh
0x180022a8c  mov     dword ptr [rsp+28h+arg_10], 0
0x180022a94  call    PszLoadStringPcch
0x180022a99  mov     rcx, cs:hInstance; hModule
0x180022aa0  lea     r8, [rsp+28h+arg_10]
0x180022aa5  mov     edx, 1C8Bh
0x180022aaa  mov     dword ptr [rsp+28h+arg_10], 0
0x180022ab2  mov     rbx, rax
0x180022ab5  call    PszLoadStringPcch
0x180022aba  mov     r9d, 10h; uType
0x180022ac0  mov     r8, rax; lpCaption
0x180022ac3  mov     rdx, rbx; lpText
0x180022ac6  mov     rcx, rdi; hWnd
0x180022ac9  call    cs:__imp_MessageBoxW
0x180022acf  xor     eax, eax
0x180022ad1  jmp     short loc_180022AD8
0x180022ad3  mov     eax, 3EBh
0x180022ad8  mov     rbx, [rsp+28h+arg_0]
0x180022add  add     rsp, 20h
0x180022ae1  pop     rdi
0x180022ae2  retn
```
