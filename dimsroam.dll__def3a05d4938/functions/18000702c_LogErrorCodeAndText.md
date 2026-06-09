# _LogErrorCodeAndText

- ea: `0x18000702c`
- end: `0x1800070af`
- name: `_LogErrorCodeAndText`
- size: `131`
- prototype: `__int64 __fastcall(DWORD dwMessageId, wchar_t **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045f4`
- `0x18000542c`
- `0x18000556c`
- `0x180005c00`
- `0x180006230`

## callees

- `0x18000702c`

## import_xrefs

- `msvcrt!wcscspn` at `0x180007082`
- `msvcrt!wcscspn` at `0x180007082`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007067`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007067`

## pseudocode

```c
__int64 __fastcall LogErrorCodeAndText(DWORD dwMessageId, wchar_t **a2)
{
  size_t v3; // rax
  wchar_t *String; // [rsp+60h] [rbp+18h] BYREF

  String = 0;
  if ( FormatMessageW(0x1100u, 0, dwMessageId, 0x400u, (LPWSTR)&String, 0, 0) && String )
  {
    v3 = wcscspn(String, L"\r\n");
    String[v3] = 0;
    *a2 = String;
    return 1;
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18000702c  mov     rax, rsp
0x18000702f  push    rbx
0x180007030  sub     rsp, 40h
0x180007034  mov     qword ptr [rax-18h], 0
0x18000703c  mov     rbx, rdx
0x18000703f  mov     dword ptr [rax-20h], 0
0x180007046  mov     r8d, ecx; dwMessageId
0x180007049  mov     qword ptr [rax+18h], 0
0x180007051  lea     rax, [rax+18h]
0x180007055  mov     r9d, 400h; dwLanguageId
0x18000705b  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x180007060  xor     edx, edx; lpSource
0x180007062  mov     ecx, 1100h; dwFlags
0x180007067  call    cs:__imp_FormatMessageW
0x18000706d  test    eax, eax
0x18000706f  jz      short loc_1800070A0
0x180007071  mov     rcx, [rsp+48h+String]; String
0x180007076  test    rcx, rcx
0x180007079  jz      short loc_1800070A0
0x18000707b  lea     rdx, Control; "\r\n"
0x180007082  call    cs:__imp_wcscspn
0x180007088  mov     rcx, [rsp+48h+String]
0x18000708d  xor     edx, edx
0x18000708f  mov     [rcx+rax*2], dx
0x180007093  mov     rax, [rsp+48h+String]
0x180007098  mov     [rbx], rax
0x18000709b  lea     eax, [rdx+1]
0x18000709e  jmp     short loc_1800070A9
0x1800070a0  mov     qword ptr [rbx], 0
0x1800070a7  xor     eax, eax
0x1800070a9  add     rsp, 40h
0x1800070ad  pop     rbx
0x1800070ae  retn
```
