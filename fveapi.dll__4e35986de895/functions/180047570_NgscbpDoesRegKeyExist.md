# NgscbpDoesRegKeyExist

- ea: `0x180047570`
- end: `0x180047602`
- name: `NgscbpDoesRegKeyExist`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180047a48`
- `0x1800566a4`
- `0x18009ba80`
- `0x18009c910`
- `0x18009dd3c`
- `0x1800a0988`
- `0x1800ae368`
- `0x1800b6964`
- `0x1800b7ce0`
- `0x1800b9a84`
- `0x1800bc56c`
- `0x1800c7ff8`
- `0x1800ce2cc`
- `0x1800d6bf8`
- `0x1800da860`

## callees

- `0x180047570`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800475db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800475db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800475aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800475aa`

## pseudocode

```c
__int64 __fastcall NgscbpDoesRegKeyExist(__int64 a1, __int64 a2, _DWORD *a3)
{
  LSTATUS v4; // eax
  int v5; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 == 2 )
    {
      *a3 = 0;
      v5 = 0;
    }
  }
  else
  {
    *a3 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180047570  mov     r11, rsp
0x180047573  mov     [r11+8], rbx
0x180047577  mov     [r11+10h], rdx
0x18004757b  push    rdi
0x18004757c  sub     rsp, 30h
0x180047580  mov     rdi, r8
0x180047583  mov     qword ptr [r11+10h], 0
0x18004758b  lea     rax, [r11+10h]
0x18004758f  xor     r8d, r8d; ulOptions
0x180047592  mov     r9d, 20019h; samDesired
0x180047598  mov     [r11-18h], rax
0x18004759c  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x1800475a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800475aa  call    cs:__imp_RegOpenKeyExW
0x1800475b1  nop     dword ptr [rax+rax+00h]
0x1800475b6  mov     ebx, eax
0x1800475b8  test    eax, eax
0x1800475ba  jnz     short loc_1800475C4
0x1800475bc  mov     dword ptr [rdi], 1
0x1800475c2  jmp     short loc_1800475D1
0x1800475c4  cmp     eax, 2
0x1800475c7  jnz     short loc_1800475D1
0x1800475c9  mov     dword ptr [rdi], 0
0x1800475cf  xor     ebx, ebx
0x1800475d1  mov     rcx, [rsp+38h+hKey]; hKey
0x1800475d6  test    rcx, rcx
0x1800475d9  jz      short loc_1800475E7
0x1800475db  call    cs:__imp_RegCloseKey
0x1800475e2  nop     dword ptr [rax+rax+00h]
0x1800475e7  test    ebx, ebx
0x1800475e9  jle     short loc_1800475F4
0x1800475eb  movzx   ebx, bx
0x1800475ee  or      ebx, 80070000h
0x1800475f4  mov     eax, ebx
0x1800475f6  mov     rbx, [rsp+38h+arg_0]
0x1800475fb  add     rsp, 30h
0x1800475ff  pop     rdi
0x180047600  retn
```
