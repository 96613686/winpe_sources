# UtsemWin32Error(ushort *,ushort *,ulong)

- ea: `0x140003094`
- end: `0x1400031b9`
- name: `?UtsemWin32Error@@YAXPEAG0K@Z`
- size: `293`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400025c0`
- `0x1400029f0`

## callees

- `0x140003094`
- `0x140003fec`
- `0x14000407c`
- `0x1400042cc`
- `0x140006f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400030be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400030be`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400030eb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400030eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000317b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000317b`

## string_xrefs

- `0x14000314d`: `com\complus\src\inc\utsem.h`

## pseudocode

```c
void __fastcall UtsemWin32Error(unsigned __int16 *a1, unsigned __int16 *a2, int a3)
{
  DWORD LastError; // eax
  __int64 v6; // rcx
  const wchar_t *v7; // r8
  __int64 v8; // rdx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rcx
  __int64 v13; // r8
  LPWSTR lpBuffer; // [rsp+20h] [rbp-148h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-128h] BYREF
  unsigned __int16 v16[128]; // [rsp+50h] [rbp-118h] BYREF

  LastError = GetLastError();
  *(_QWORD *)Buffer = 0;
  FormatMessageW(0x1300u, 0, LastError, 0, Buffer, 0, 0);
  v6 = 2147483646;
  v7 = L"*** Error in %s(%d), %s: %s";
  v8 = 128;
  v9 = v16;
  do
  {
    if ( !v6 )
      break;
    if ( !*v7 )
      break;
    *v9++ = *v7++;
    --v6;
    --v8;
  }
  while ( v8 );
  v10 = v9 - 1;
  if ( v8 )
    v10 = v9;
  *v10 = 0;
  GetFormatString(0x3A6u, v16);
  LODWORD(lpBuffer) = a3;
  Log(8u, 0xC0021251, v16, L"com\\complus\\src\\inc\\utsem.h", lpBuffer, *(_QWORD *)Buffer, a1);
  LocalFree(*(HLOCAL *)Buffer);
  FailFastStr(v12, v11, v13, 1, 1);
}

```

## disassembly

```asm
0x140003094  mov     [rsp+arg_8], rbx
0x140003099  mov     [rsp+arg_18], rsi
0x14000309e  push    rdi
0x14000309f  sub     rsp, 160h
0x1400030a6  mov     rax, cs:__security_cookie
0x1400030ad  xor     rax, rsp
0x1400030b0  mov     [rsp+168h+var_18], rax
0x1400030b8  mov     edi, r8d
0x1400030bb  mov     rbx, rcx
0x1400030be  call    cs:__imp_GetLastError
0x1400030c4  xor     esi, esi
0x1400030c6  lea     rcx, [rsp+168h+Buffer]
0x1400030cb  mov     [rsp+168h+Arguments], rsi; Arguments
0x1400030d0  xor     r9d, r9d; dwLanguageId
0x1400030d3  mov     [rsp+168h+nSize], esi; nSize
0x1400030d7  mov     r8d, eax; dwMessageId
0x1400030da  mov     [rsp+168h+lpBuffer], rcx; lpBuffer
0x1400030df  xor     edx, edx; lpSource
0x1400030e1  mov     ecx, 1300h; dwFlags
0x1400030e6  mov     qword ptr [rsp+168h+Buffer], rsi
0x1400030eb  call    cs:__imp_FormatMessageW
0x1400030f1  mov     ecx, 7FFFFFFEh
0x1400030f6  lea     r8, aErrorInSDSS; "*** Error in %s(%d), %s: %s"
0x1400030fd  mov     edx, 80h
0x140003102  lea     rax, [rsp+168h+var_118]
0x140003107  test    rcx, rcx
0x14000310a  jz      short loc_14000312B
0x14000310c  movzx   r9d, word ptr [r8]
0x140003110  test    r9w, r9w
0x140003114  jz      short loc_14000312B
0x140003116  mov     [rax], r9w
0x14000311a  add     r8, 2
0x14000311e  add     rax, 2
0x140003122  dec     rcx
0x140003125  sub     rdx, 1
0x140003129  jnz     short loc_140003107
0x14000312b  test    rdx, rdx
0x14000312e  lea     rcx, [rax-2]
0x140003132  lea     rdx, [rsp+168h+var_118]; unsigned __int16 *
0x140003137  cmovnz  rcx, rax
0x14000313b  mov     [rcx], si
0x14000313e  mov     ecx, 3A6h; unsigned int
0x140003143  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x140003148  mov     rax, qword ptr [rsp+168h+Buffer]
0x14000314d  lea     r9, aComComplusSrcI; "com\\complus\\src\\inc\\utsem.h"
0x140003154  mov     [rsp+168h+Arguments], rbx
0x140003159  lea     r8, [rsp+168h+var_118]; unsigned __int16 *
0x14000315e  mov     qword ptr [rsp+168h+nSize], rax; struct _EXCEPTION_POINTERS *
0x140003163  mov     ecx, 8; unsigned __int16
0x140003168  mov     edx, 0C0021251h; unsigned int
0x14000316d  mov     dword ptr [rsp+168h+lpBuffer], edi
0x140003171  call    ?Log@@YAXGKPEBGZZ; Log(ushort,ulong,ushort const *,...)
0x140003176  mov     rcx, qword ptr [rsp+168h+Buffer]; hMem
0x14000317b  call    cs:__imp_LocalFree
0x140003181  mov     r9d, 1; int
0x140003187  mov     dword ptr [rsp+168h+lpBuffer], 1; int
0x14000318f  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x140003194  mov     rcx, [rsp+168h+var_18]
0x14000319c  xor     rcx, rsp; StackCookie
0x14000319f  call    __security_check_cookie
0x1400031a4  lea     r11, [rsp+168h+var_8]
0x1400031ac  mov     rbx, [r11+18h]
0x1400031b0  mov     rsi, [r11+28h]
0x1400031b4  mov     rsp, r11
0x1400031b7  pop     rdi
0x1400031b8  retn
```
