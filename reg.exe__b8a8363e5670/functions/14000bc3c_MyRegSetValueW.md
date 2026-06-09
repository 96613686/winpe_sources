# MyRegSetValueW

- ea: `0x14000bc3c`
- end: `0x14000bd26`
- name: `MyRegSetValueW`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000b91c`

## callees

- `0x14000bc3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000bce6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000bce6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000bcb4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14000bcb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bcfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000bcfe`

## pseudocode

```c
__int64 __fastcall MyRegSetValueW(HKEY a1, const WCHAR *a2, __int64 a3, const BYTE *a4)
{
  HKEY v5; // rdi
  __int64 v6; // rax
  unsigned __int64 v7; // rbp
  unsigned int v8; // ebx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF

  hKey = 0;
  v5 = a1;
  if ( a4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)&a4[2 * v6] );
    v7 = 2 * v6 + 2;
    if ( v7 > 0xFFFFFFFF )
    {
      return 87;
    }
    else
    {
      if ( !a2 || !*a2 )
      {
        hKey = a1;
LABEL_10:
        v8 = RegSetValueExW(a1, 0, 0, 1u, a4, v7);
        if ( hKey != v5 )
          RegCloseKey(hKey);
        return v8;
      }
      v8 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
      if ( !v8 )
      {
        a1 = hKey;
        goto LABEL_10;
      }
    }
    return v8;
  }
  return 87;
}

```

## disassembly

```asm
0x14000bc3c  push    rbx
0x14000bc3e  push    rbp
0x14000bc3f  push    rsi
0x14000bc40  push    rdi
0x14000bc41  push    r14
0x14000bc43  sub     rsp, 60h
0x14000bc47  xor     r14d, r14d
0x14000bc4a  mov     rsi, r9
0x14000bc4d  mov     [rsp+88h+hKey], r14
0x14000bc52  mov     rdi, rcx
0x14000bc55  test    r9, r9
0x14000bc58  jz      loc_14000BD15
0x14000bc5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000bc62  inc     rax
0x14000bc65  cmp     [r9+rax*2], r14w
0x14000bc6a  jnz     short loc_14000BC62
0x14000bc6c  lea     rbp, ds:2[rax*2]
0x14000bc74  mov     eax, 0FFFFFFFFh
0x14000bc79  cmp     rbp, rax
0x14000bc7c  ja      loc_14000BD0C
0x14000bc82  test    rdx, rdx
0x14000bc85  jz      short loc_14000BCCD
0x14000bc87  cmp     [rdx], r14w
0x14000bc8b  jz      short loc_14000BCCD
0x14000bc8d  mov     [rsp+88h+lpdwDisposition], r14; lpdwDisposition
0x14000bc92  lea     rax, [rsp+88h+hKey]
0x14000bc97  mov     [rsp+88h+phkResult], rax; phkResult
0x14000bc9c  xor     r9d, r9d; lpClass
0x14000bc9f  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000bca4  xor     r8d, r8d; Reserved
0x14000bca7  mov     [rsp+88h+samDesired], 2; samDesired
0x14000bcaf  mov     [rsp+88h+dwOptions], r14d; dwOptions
0x14000bcb4  call    cs:__imp_RegCreateKeyExW
0x14000bcbb  nop     dword ptr [rax+rax+00h]
0x14000bcc0  mov     ebx, eax
0x14000bcc2  test    eax, eax
0x14000bcc4  jnz     short loc_14000BD11
0x14000bcc6  mov     rcx, [rsp+88h+hKey]; hKey
0x14000bccb  jmp     short loc_14000BCD2
0x14000bccd  mov     [rsp+88h+hKey], rcx
0x14000bcd2  mov     [rsp+88h+samDesired], ebp; cbData
0x14000bcd6  mov     r9d, 1; dwType
0x14000bcdc  xor     r8d, r8d; Reserved
0x14000bcdf  mov     qword ptr [rsp+88h+dwOptions], rsi; lpData
0x14000bce4  xor     edx, edx; lpValueName
0x14000bce6  call    cs:__imp_RegSetValueExW
0x14000bced  nop     dword ptr [rax+rax+00h]
0x14000bcf2  mov     rcx, [rsp+88h+hKey]; hKey
0x14000bcf7  mov     ebx, eax
0x14000bcf9  cmp     rcx, rdi
0x14000bcfc  jz      short loc_14000BD11
0x14000bcfe  call    cs:__imp_RegCloseKey
0x14000bd05  nop     dword ptr [rax+rax+00h]
0x14000bd0a  jmp     short loc_14000BD11
0x14000bd0c  mov     ebx, 57h ; 'W'
0x14000bd11  mov     eax, ebx
0x14000bd13  jmp     short loc_14000BD1A
0x14000bd15  mov     eax, 57h ; 'W'
0x14000bd1a  add     rsp, 60h
0x14000bd1e  pop     r14
0x14000bd20  pop     rdi
0x14000bd21  pop     rsi
0x14000bd22  pop     rbp
0x14000bd23  pop     rbx
0x14000bd24  retn
```
