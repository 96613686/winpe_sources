# CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)

- ea: `0x1800056a4`
- end: `0x18000579a`
- name: `?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z`
- size: `246`
- prototype: `int(CAccessible *__hidden this, bool, HWND, unsigned int, unsigned __int64, __int64, __int64 *)`
- caller_count: `99`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d54`
- `0x180004b90`
- `0x180004ff0`
- `0x180005050`
- `0x180005220`
- `0x180005454`
- `0x1800065b4`
- `0x1800179e0`
- `0x18001b8c0`
- `0x18001be00`
- `0x18001c9f0`
- `0x1800274b0`
- `0x1800279c0`
- `0x1800285c0`
- `0x180028620`
- `0x180029040`
- `0x180029610`
- `0x180029940`
- `0x180029d14`
- `0x18002b0f0`
- `0x18002b230`
- `0x18002c280`
- `0x18002c4d0`
- `0x18002c660`
- `0x18002c7d0`
- `0x18002c980`
- `0x18002d120`
- `0x18002d690`
- `0x18002d88c`
- `0x18002df80`
- `0x18002e200`
- `0x18002e5b0`
- `0x18002e6d0`
- `0x18002f980`
- `0x18002fb30`
- `0x18002fcc0`
- `0x18002fea0`
- `0x180030090`
- `0x1800304d0`
- `0x1800308d0`
- `0x180030964`
- `0x180030bb0`
- `0x180030e60`
- `0x180030ff0`
- `0x1800313a0`
- `0x180031780`
- `0x180031a60`
- `0x180031ca0`
- `0x180031e30`
- `0x1800321c0`

## callees

- `0x1800056a4`
- `0x18000baa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000573b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000573b`
- `USER32!SendMessageTimeoutW` at `0x1800056ff`
- `USER32!SendMessageTimeoutW` at `0x1800056ff`
- `USER32!SendMessageW` at `0x180005733`
- `USER32!SendMessageW` at `0x180005733`

## string_xrefs

- `0x18000578a`: `CAccessible::AccSendMessageTimeout`

## pseudocode

```c
__int64 __fastcall CAccessible::AccSendMessageTimeout(
        CAccessible *this,
        unsigned __int8 a2,
        HWND a3,
        UINT a4,
        WPARAM wParam,
        LPARAM lParam,
        __int64 *a7)
{
  signed int v7; // ebx
  bool v9; // cc
  UINT uTimeout; // edx
  LRESULT v11; // rax
  signed int LastError; // eax
  LRESULT v14; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  v9 = *((_DWORD *)this + 25) <= 0x70000u;
  uTimeout = *((_DWORD *)this + (a2 ^ 1LL) + 16);
  v14 = 0;
  if ( v9 )
  {
    v11 = SendMessageW(a3, a4, wParam, lParam);
  }
  else
  {
    if ( uTimeout < 0x32 )
      uTimeout = 20000;
    if ( !SendMessageTimeoutW(a3, a4, wParam, lParam, 2u, uTimeout, (PDWORD_PTR)&v14) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError == 1460 )
      {
        v7 = -2146233083;
      }
      else if ( LastError > 0 )
      {
        v7 = (unsigned __int16)LastError | 0x80070000;
      }
      Error::IAccessibleError(0, L"SendMessageTimeoutHelper", v7, a3, 5002);
    }
    v11 = v14;
  }
  if ( a7 )
    *a7 = v11;
  if ( v7 < 0 )
    Error::IAccessibleError(0, L"CAccessible::AccSendMessageTimeout", v7, a3, 5002);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800056a4  mov     r11, rsp
0x1800056a7  mov     [r11+10h], rbx
0x1800056ab  push    rdi
0x1800056ac  sub     rsp, 40h
0x1800056b0  movzx   eax, dl
0x1800056b3  xor     ebx, ebx
0x1800056b5  xor     rax, 1
0x1800056b9  mov     rdi, r8
0x1800056bc  cmp     dword ptr [rcx+64h], 70000h
0x1800056c3  mov     r10d, r9d
0x1800056c6  mov     r9, [rsp+48h+lParam]; lParam
0x1800056cb  mov     r8, [rsp+48h+wParam]; wParam
0x1800056d0  mov     edx, [rcx+rax*4+40h]
0x1800056d4  mov     rcx, rdi; hWnd
0x1800056d7  mov     [r11+8], rbx
0x1800056db  jbe     short loc_180005730
0x1800056dd  cmp     edx, 32h ; '2'
0x1800056e0  mov     eax, 4E20h
0x1800056e5  cmovb   edx, eax
0x1800056e8  lea     rax, [r11+8]
0x1800056ec  mov     [r11-18h], rax
0x1800056f0  mov     [rsp+48h+uTimeout], edx; uTimeout
0x1800056f4  mov     edx, r10d; Msg
0x1800056f7  mov     [rsp+48h+fuFlags], 2; fuFlags
0x1800056ff  call    cs:__imp_SendMessageTimeoutW
0x180005705  test    rax, rax
0x180005708  jz      short loc_18000573B
0x18000570a  mov     rax, [rsp+48h+arg_0]
0x18000570f  mov     rcx, [rsp+48h+arg_30]
0x180005717  test    rcx, rcx
0x18000571a  jz      short loc_18000571F
0x18000571c  mov     [rcx], rax
0x18000571f  test    ebx, ebx
0x180005721  js      short loc_18000577C
0x180005723  mov     eax, ebx
0x180005725  mov     rbx, [rsp+48h+arg_8]
0x18000572a  add     rsp, 40h
0x18000572e  pop     rdi
0x18000572f  retn
0x180005730  mov     edx, r10d; Msg
0x180005733  call    cs:__imp_SendMessageW
0x180005739  jmp     short loc_18000570F
0x18000573b  call    cs:__imp_GetLastError
0x180005741  mov     ebx, eax
0x180005743  cmp     eax, 5B4h
0x180005748  jz      short loc_180005775
0x18000574a  test    eax, eax
0x18000574c  jle     short loc_180005757
0x18000574e  movzx   ebx, ax
0x180005751  or      ebx, 80070000h
0x180005757  mov     r9, rdi; HWND
0x18000575a  mov     [rsp+48h+fuFlags], 138Ah; int
0x180005762  mov     r8d, ebx; int
0x180005765  lea     rdx, aSendmessagetim_0
0x18000576c  xor     ecx, ecx; struct IUnknown *
0x18000576e  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z
0x180005773  jmp     short loc_18000570A
0x180005775  mov     ebx, 80131505h
0x18000577a  jmp     short loc_180005757
0x18000577c  mov     r9, rdi; HWND
0x18000577f  mov     [rsp+48h+fuFlags], 138Ah; int
0x180005787  mov     r8d, ebx; int
0x18000578a  lea     rdx, aCaccessibleAcc
0x180005791  xor     ecx, ecx; struct IUnknown *
0x180005793  call    ?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z
0x180005798  jmp     short loc_180005723
```
