# Enrollment::set_SspHyperLink(HKEY__ *,ushort *)

- ea: `0x18003ff0c`
- end: `0x180040011`
- name: `?set_SspHyperLink@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `261`
- prototype: `int(Enrollment *__hidden this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003bf04`

## callees

- `0x18003ff0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ffab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ffab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ff97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ff97`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ff53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fff4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ff53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003fff4`

## string_xrefs

- `0x18003ff2d`: `SSPHyperLink`
- `0x18003ffd9`: `SSPHyperLink`

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
0x18003ff0c  mov     r11, rsp
0x18003ff0f  push    rbx
0x18003ff10  push    rbp
0x18003ff11  push    rsi
0x18003ff12  push    rdi
0x18003ff13  sub     rsp, 48h
0x18003ff17  mov     rsi, r8
0x18003ff1a  mov     dword ptr [r11+20h], 0
0x18003ff22  mov     rbp, rdx
0x18003ff25  lea     rax, [r11+20h]
0x18003ff29  mov     [r11-38h], rax
0x18003ff2d  lea     r8, aSsphyperlink; "SSPHyperLink"
0x18003ff34  mov     rdi, rcx
0x18003ff37  mov     qword ptr [r11-40h], 0
0x18003ff3f  mov     r9d, 2; dwFlags
0x18003ff45  mov     qword ptr [r11-48h], 0
0x18003ff4d  mov     rdx, rsi; lpSubKey
0x18003ff50  mov     rcx, rbp; hkey
0x18003ff53  call    cs:__imp_RegGetValueW
0x18003ff5a  nop     dword ptr [rax+rax+00h]
0x18003ff5f  mov     ebx, eax
0x18003ff61  cmp     eax, 2
0x18003ff64  jnz     short loc_18003FF75
0x18003ff66  mov     qword ptr [rdi+728h], 0
0x18003ff71  xor     eax, eax
0x18003ff73  jmp     short loc_18003FF86
0x18003ff75  test    eax, eax
0x18003ff77  jz      short loc_18003FF90
0x18003ff79  jle     short loc_18003FF84
0x18003ff7b  movzx   ebx, ax
0x18003ff7e  or      ebx, 80070000h
0x18003ff84  mov     eax, ebx
0x18003ff86  add     rsp, 48h
0x18003ff8a  pop     rdi
0x18003ff8b  pop     rsi
0x18003ff8c  pop     rbp
0x18003ff8d  pop     rbx
0x18003ff8e  retn
0x18003ff90  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x18003ff97  call    cs:__imp_GetProcessHeap
0x18003ff9e  nop     dword ptr [rax+rax+00h]
0x18003ffa3  mov     r8d, ebx; dwBytes
0x18003ffa6  xor     edx, edx; dwFlags
0x18003ffa8  mov     rcx, rax; hHeap
0x18003ffab  call    cs:__imp_HeapAlloc
0x18003ffb2  nop     dword ptr [rax+rax+00h]
0x18003ffb7  mov     [rdi+728h], rax
0x18003ffbe  test    rax, rax
0x18003ffc1  jnz     short loc_18003FFCA
0x18003ffc3  mov     ebx, 8007000Eh
0x18003ffc8  jmp     short loc_18003FF84
0x18003ffca  xor     ebx, ebx
0x18003ffcc  lea     rcx, [rsp+68h+dwBytes]
0x18003ffd4  mov     [rsp+68h+pcbData], rcx; pcbData
0x18003ffd9  lea     r8, aSsphyperlink; "SSPHyperLink"
0x18003ffe0  mov     [rsp+68h+pvData], rax; pvData
0x18003ffe5  mov     rdx, rsi; lpSubKey
0x18003ffe8  mov     rcx, rbp; hkey
0x18003ffeb  mov     [rsp+68h+pdwType], rbx; pdwType
0x18003fff0  lea     r9d, [rbx+2]; dwFlags
0x18003fff4  call    cs:__imp_RegGetValueW
0x18003fffb  nop     dword ptr [rax+rax+00h]
0x180040000  test    eax, eax
0x180040002  jz      short loc_18003FF84
0x180040004  jg      loc_18003FF7B
0x18004000a  mov     ebx, eax
0x18004000c  jmp     loc_18003FF84
```
