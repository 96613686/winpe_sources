# Date_SetHijriDate(HWND__ *)

- ea: `0x1800120f0`
- end: `0x1800121c9`
- name: `?Date_SetHijriDate@@YAXPEAUHWND__@@@Z`
- size: `217`
- prototype: `void __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010c48`

## callees

- `0x1800120f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800121a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800121a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012162`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012162`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121b3`
- `USER32!SendMessageW` at `0x180012114`
- `USER32!SendMessageW` at `0x180012134`
- `USER32!SendMessageW` at `0x180012114`
- `USER32!SendMessageW` at `0x180012134`

## pseudocode

```c
void __fastcall Date_SetHijriDate(HWND hWnd)
{
  int v2; // eax
  __int64 v3; // rbx
  int v4; // edi
  const BYTE *v5; // rcx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = SendMessageW(hWnd, 0x147u, 0, 0);
  v3 = -1;
  if ( v2 != -1 )
  {
    v4 = SendMessageW(hWnd, 0x150u, v2, 0);
    if ( v4 != -1 && !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\International", 0, 0x2001Fu, &hKey) )
    {
      v5 = (const BYTE *)off_18002D5C0[v4];
      do
        ++v3;
      while ( *(_WORD *)&v5[2 * v3] );
      RegSetValueExW(hKey, L"AddHijriDate", 0, 1u, v5, 2 * v3 + 2);
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x1800120f0  mov     [rsp+arg_0], rbx
0x1800120f5  mov     [rsp+arg_10], rsi
0x1800120fa  push    rdi
0x1800120fb  sub     rsp, 30h
0x1800120ff  xor     esi, esi
0x180012101  xor     r9d, r9d; lParam
0x180012104  xor     r8d, r8d; wParam
0x180012107  mov     [rsp+38h+hKey], rsi
0x18001210c  mov     edx, 147h; Msg
0x180012111  mov     rdi, rcx
0x180012114  call    cs:__imp_SendMessageW
0x18001211a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001211e  cmp     eax, ebx
0x180012120  jz      loc_1800121B9
0x180012126  movsxd  r8, eax; wParam
0x180012129  xor     r9d, r9d; lParam
0x18001212c  mov     edx, 150h; Msg
0x180012131  mov     rcx, rdi; hWnd
0x180012134  call    cs:__imp_SendMessageW
0x18001213a  mov     rdi, rax
0x18001213d  cmp     eax, ebx
0x18001213f  jz      short loc_1800121B9
0x180012141  lea     rax, [rsp+38h+hKey]
0x180012146  mov     r9d, 2001Fh; samDesired
0x18001214c  xor     r8d, r8d; ulOptions
0x18001214f  mov     [rsp+38h+phkResult], rax; phkResult
0x180012154  lea     rdx, aControlPanelIn_2; "Control Panel\\International"
0x18001215b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180012162  call    cs:__imp_RegOpenKeyExW
0x180012168  test    eax, eax
0x18001216a  jnz     short loc_1800121B9
0x18001216c  movsxd  rax, edi
0x18001216f  lea     rcx, off_18002D5C0; "AddHijriDate-2"
0x180012176  mov     rcx, [rcx+rax*8]
0x18001217a  inc     rbx
0x18001217d  cmp     [rcx+rbx*2], si
0x180012181  jnz     short loc_18001217A
0x180012183  lea     eax, ds:2[rbx*2]
0x18001218a  mov     r9d, 1; dwType
0x180012190  mov     [rsp+38h+cbData], eax; cbData
0x180012194  lea     rdx, aAddhijridate_0; "AddHijriDate"
0x18001219b  mov     [rsp+38h+phkResult], rcx; lpData
0x1800121a0  xor     r8d, r8d; Reserved
0x1800121a3  mov     rcx, [rsp+38h+hKey]; hKey
0x1800121a8  call    cs:__imp_RegSetValueExW
0x1800121ae  mov     rcx, [rsp+38h+hKey]; hKey
0x1800121b3  call    cs:__imp_RegCloseKey
0x1800121b9  mov     rbx, [rsp+38h+arg_0]
0x1800121be  mov     rsi, [rsp+38h+arg_10]
0x1800121c3  add     rsp, 30h
0x1800121c7  pop     rdi
0x1800121c8  retn
```
