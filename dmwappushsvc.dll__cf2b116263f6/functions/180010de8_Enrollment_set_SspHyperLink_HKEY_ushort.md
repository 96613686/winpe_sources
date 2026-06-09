# Enrollment::set_SspHyperLink(HKEY__ *,ushort *)

- ea: `0x180010de8`
- end: `0x180010ecd`
- name: `?set_SspHyperLink@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `229`
- prototype: `__int64 __fastcall(Enrollment *this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000df4c`

## callees

- `0x180010de8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010e6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010e6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010e7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010e7a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010e2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010ebd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010e2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010ebd`

## string_xrefs

- `0x180010e09`: `SSPHyperLink`
- `0x180010ea2`: `SSPHyperLink`

## pseudocode

```c
__int64 __fastcall Enrollment::set_SspHyperLink(Enrollment *this, HKEY a2, unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v7; // ebx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rax
  SIZE_T dwBytes; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  ValueW = RegGetValueW(a2, a3, L"SSPHyperLink", 2u, 0, 0, (LPDWORD)&dwBytes);
  v7 = ValueW;
  if ( ValueW == 2 )
  {
    *((_QWORD *)this + 229) = 0;
    return 0;
  }
  if ( !ValueW )
  {
    v9 = dwBytes;
    ProcessHeap = GetProcessHeap();
    pvData = HeapAlloc(ProcessHeap, 0, v9);
    *((_QWORD *)this + 229) = pvData;
    if ( !pvData )
      return (unsigned int)-2147024882;
    v7 = 0;
    ValueW = RegGetValueW(a2, a3, L"SSPHyperLink", 2u, 0, pvData, (LPDWORD)&dwBytes);
    if ( !ValueW )
      return v7;
    if ( ValueW <= 0 )
      return (unsigned int)ValueW;
    return (unsigned __int16)ValueW | 0x80070000;
  }
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x180010de8  mov     r11, rsp
0x180010deb  push    rbx
0x180010dec  push    rbp
0x180010ded  push    rsi
0x180010dee  push    rdi
0x180010def  sub     rsp, 48h
0x180010df3  mov     rsi, r8
0x180010df6  mov     dword ptr [r11+20h], 0
0x180010dfe  mov     rbp, rdx
0x180010e01  lea     rax, [r11+20h]
0x180010e05  mov     [r11-38h], rax
0x180010e09  lea     r8, aSsphyperlink; "SSPHyperLink"
0x180010e10  mov     rdi, rcx
0x180010e13  mov     qword ptr [r11-40h], 0
0x180010e1b  mov     r9d, 2; dwFlags
0x180010e21  mov     qword ptr [r11-48h], 0
0x180010e29  mov     rdx, rsi; lpSubKey
0x180010e2c  mov     rcx, rbp; hkey
0x180010e2f  call    cs:__imp_RegGetValueW
0x180010e35  mov     ebx, eax
0x180010e37  cmp     eax, 2
0x180010e3a  jnz     short loc_180010E4B
0x180010e3c  mov     qword ptr [rdi+728h], 0
0x180010e47  xor     eax, eax
0x180010e49  jmp     short loc_180010E5C
0x180010e4b  test    eax, eax
0x180010e4d  jz      short loc_180010E65
0x180010e4f  jle     short loc_180010E5A
0x180010e51  movzx   ebx, ax
0x180010e54  or      ebx, 80070000h
0x180010e5a  mov     eax, ebx
0x180010e5c  add     rsp, 48h
0x180010e60  pop     rdi
0x180010e61  pop     rsi
0x180010e62  pop     rbp
0x180010e63  pop     rbx
0x180010e64  retn
0x180010e65  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x180010e6c  call    cs:__imp_GetProcessHeap
0x180010e72  mov     r8d, ebx; dwBytes
0x180010e75  xor     edx, edx; dwFlags
0x180010e77  mov     rcx, rax; hHeap
0x180010e7a  call    cs:__imp_HeapAlloc
0x180010e80  mov     [rdi+728h], rax
0x180010e87  test    rax, rax
0x180010e8a  jnz     short loc_180010E93
0x180010e8c  mov     ebx, 8007000Eh
0x180010e91  jmp     short loc_180010E5A
0x180010e93  xor     ebx, ebx
0x180010e95  lea     rcx, [rsp+68h+dwBytes]
0x180010e9d  mov     [rsp+68h+pcbData], rcx; pcbData
0x180010ea2  lea     r8, aSsphyperlink; "SSPHyperLink"
0x180010ea9  mov     [rsp+68h+pvData], rax; pvData
0x180010eae  mov     rdx, rsi; lpSubKey
0x180010eb1  mov     rcx, rbp; hkey
0x180010eb4  mov     [rsp+68h+pdwType], rbx; pdwType
0x180010eb9  lea     r9d, [rbx+2]; dwFlags
0x180010ebd  call    cs:__imp_RegGetValueW
0x180010ec3  test    eax, eax
0x180010ec5  jz      short loc_180010E5A
0x180010ec7  jg      short loc_180010E51
0x180010ec9  mov     ebx, eax
0x180010ecb  jmp     short loc_180010E5A
```
