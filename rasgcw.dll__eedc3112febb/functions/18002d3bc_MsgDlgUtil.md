# MsgDlgUtil

- ea: `0x18002d3bc`
- end: `0x18002d56e`
- name: `MsgDlgUtil`
- size: `434`
- prototype: `__int64 __fastcall(HWND hWnd, UINT uID, va_list *Arguments, HINSTANCE hInstance, UINT)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800202e0`
- `0x180020bac`
- `0x180025730`
- `0x18002a824`

## callees

- `0x18002b37c`
- `0x18002b8c0`
- `0x18002d3bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d4e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d4e9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002d446`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002d489`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002d446`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002d489`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d492`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18002d492`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d54f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d54f`
- `USER32!MessageBoxW` at `0x18002d524`
- `USER32!MessageBoxW` at `0x18002d524`
- `USER32!UnhookWindowsHookEx` at `0x18002d534`
- `USER32!UnhookWindowsHookEx` at `0x18002d534`
- `USER32!SetWindowsHookExW` at `0x18002d501`
- `USER32!SetWindowsHookExW` at `0x18002d501`
- `rtutils!TracePrintfExA` at `0x18002d3fd`
- `rtutils!TracePrintfExA` at `0x18002d3fd`

## pseudocode

```c
__int64 __fastcall MsgDlgUtil(HWND hWnd, UINT uID, va_list *Arguments, HINSTANCE hInstance, UINT uIDa)
{
  va_list v9; // rdx
  unsigned int v10; // edi
  void *v11; // rsi
  va_list v12; // rax
  UINT v13; // esi
  const WCHAR *v14; // rbp
  DWORD CurrentThreadId; // eax
  HHOOK v16; // rbx
  WCHAR *Buffer; // [rsp+80h] [rbp+18h] BYREF

  Buffer = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "MsgDlgUtil");
  Buffer = (WCHAR *)&cchOriginalDestLength;
  if ( Arguments && (v9 = Arguments[10]) != 0 )
  {
    v10 = 1;
    FormatMessageW(0x2500u, v9, 0, 0, (LPWSTR)&Buffer, 1u, Arguments);
  }
  else
  {
    v11 = (void *)PszFromId(hInstance, uID);
    v10 = 1;
    if ( v11 )
    {
      FormatMessageW(0x2500u, v11, 0, 0, (LPWSTR)&Buffer, 1u, Arguments);
      GlobalFree(v11);
    }
    if ( !Arguments )
      goto LABEL_13;
  }
  if ( *((_DWORD *)Arguments + 22) )
  {
    v12 = 0;
    if ( Buffer != &cchOriginalDestLength )
      v12 = (va_list)Buffer;
    Arguments[12] = v12;
    return v10;
  }
LABEL_13:
  v10 = 0;
  if ( !Arguments || (v13 = *((_DWORD *)Arguments + 18)) == 0 )
    v13 = 65600;
  v14 = (const WCHAR *)PszFromId(hInstance, uIDa);
  if ( hWnd )
  {
    CurrentThreadId = GetCurrentThreadId();
    v16 = SetWindowsHookExW(4, CenterDlgOnOwnerCallWndProc, hInstance, CurrentThreadId);
  }
  else
  {
    v16 = 0;
  }
  if ( Buffer )
    v10 = MessageBoxW(hWnd, Buffer, v14, v13);
  if ( v16 )
    UnhookWindowsHookEx(v16);
  Free0(v14);
  if ( Buffer != &cchOriginalDestLength )
    LocalFree(Buffer);
  return v10;
}

```

## disassembly

```asm
0x18002d3bc  mov     rax, rsp
0x18002d3bf  mov     [rax+8], rbx
0x18002d3c3  mov     [rax+10h], rbp
0x18002d3c7  push    rsi
0x18002d3c8  push    rdi
0x18002d3c9  push    r12
0x18002d3cb  push    r14
0x18002d3cd  push    r15
0x18002d3cf  sub     rsp, 40h
0x18002d3d3  mov     r15, rcx
0x18002d3d6  mov     qword ptr [rax+18h], 0
0x18002d3de  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002d3e4  mov     r14, r9
0x18002d3e7  mov     rbx, r8
0x18002d3ea  mov     edi, edx
0x18002d3ec  cmp     ecx, 0FFFFFFFFh
0x18002d3ef  jz      short loc_18002D403
0x18002d3f1  lea     r8, aMsgdlgutil; "MsgDlgUtil"
0x18002d3f8  mov     edx, 0Ch; dwFlags
0x18002d3fd  call    cs:__imp_TracePrintfExA
0x18002d403  lea     r12, cchOriginalDestLength
0x18002d40a  mov     [rsp+68h+Buffer], r12
0x18002d412  test    rbx, rbx
0x18002d415  jz      short loc_18002D44E
0x18002d417  mov     rdx, [rbx+50h]; lpSource
0x18002d41b  test    rdx, rdx
0x18002d41e  jz      short loc_18002D44E
0x18002d420  mov     [rsp+68h+Arguments], rbx; Arguments
0x18002d425  lea     rax, [rsp+68h+Buffer]
0x18002d42d  mov     edi, 1
0x18002d432  xor     r9d, r9d; dwLanguageId
0x18002d435  mov     [rsp+68h+nSize], edi; nSize
0x18002d439  xor     r8d, r8d; dwMessageId
0x18002d43c  mov     ecx, 2500h; dwFlags
0x18002d441  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x18002d446  call    cs:__imp_FormatMessageW
0x18002d44c  jmp     short loc_18002D49D
0x18002d44e  mov     edx, edi; uID
0x18002d450  mov     rcx, r14; hInstance
0x18002d453  call    PszFromId
0x18002d458  mov     rsi, rax
0x18002d45b  mov     edi, 1
0x18002d460  test    rax, rax
0x18002d463  jz      short loc_18002D498
0x18002d465  mov     [rsp+68h+Arguments], rbx; Arguments
0x18002d46a  lea     rax, [rsp+68h+Buffer]
0x18002d472  mov     [rsp+68h+nSize], edi; nSize
0x18002d476  xor     r9d, r9d; dwLanguageId
0x18002d479  xor     r8d, r8d; dwMessageId
0x18002d47c  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x18002d481  mov     rdx, rsi; lpSource
0x18002d484  mov     ecx, 2500h; dwFlags
0x18002d489  call    cs:__imp_FormatMessageW
0x18002d48f  mov     rcx, rsi; hMem
0x18002d492  call    cs:__imp_GlobalFree
0x18002d498  test    rbx, rbx
0x18002d49b  jz      short loc_18002D4BF
0x18002d49d  cmp     dword ptr [rbx+58h], 0
0x18002d4a1  jz      short loc_18002D4BF
0x18002d4a3  xor     eax, eax
0x18002d4a5  cmp     [rsp+68h+Buffer], r12
0x18002d4ad  cmovnz  rax, [rsp+68h+Buffer]
0x18002d4b6  mov     [rbx+60h], rax
0x18002d4ba  jmp     loc_18002D555
0x18002d4bf  xor     edi, edi
0x18002d4c1  test    rbx, rbx
0x18002d4c4  jz      short loc_18002D4CD
0x18002d4c6  mov     esi, [rbx+48h]
0x18002d4c9  test    esi, esi
0x18002d4cb  jnz     short loc_18002D4D2
0x18002d4cd  mov     esi, 10040h
0x18002d4d2  mov     edx, [rsp+68h+uID]; uID
0x18002d4d9  mov     rcx, r14; hInstance
0x18002d4dc  call    PszFromId
0x18002d4e1  mov     rbp, rax
0x18002d4e4  test    r15, r15
0x18002d4e7  jz      short loc_18002D50C
0x18002d4e9  call    cs:__imp_GetCurrentThreadId
0x18002d4ef  mov     r8, r14; hmod
0x18002d4f2  lea     rdx, CenterDlgOnOwnerCallWndProc; lpfn
0x18002d4f9  mov     r9d, eax; dwThreadId
0x18002d4fc  mov     ecx, 4; idHook
0x18002d501  call    cs:__imp_SetWindowsHookExW
0x18002d507  mov     rbx, rax
0x18002d50a  jmp     short loc_18002D50E
0x18002d50c  xor     ebx, ebx
0x18002d50e  mov     rdx, [rsp+68h+Buffer]; lpText
0x18002d516  test    rdx, rdx
0x18002d519  jz      short loc_18002D52C
0x18002d51b  mov     r9d, esi; uType
0x18002d51e  mov     r8, rbp; lpCaption
0x18002d521  mov     rcx, r15; hWnd
0x18002d524  call    cs:__imp_MessageBoxW
0x18002d52a  mov     edi, eax
0x18002d52c  test    rbx, rbx
0x18002d52f  jz      short loc_18002D53A
0x18002d531  mov     rcx, rbx; hhk
0x18002d534  call    cs:__imp_UnhookWindowsHookEx
0x18002d53a  mov     rcx, rbp
0x18002d53d  call    Free0
0x18002d542  mov     rcx, [rsp+68h+Buffer]; hMem
0x18002d54a  cmp     rcx, r12
0x18002d54d  jz      short loc_18002D555
0x18002d54f  call    cs:__imp_LocalFree
0x18002d555  mov     rbx, [rsp+68h+arg_0]
0x18002d55a  mov     eax, edi
0x18002d55c  mov     rbp, [rsp+68h+arg_8]
0x18002d561  add     rsp, 40h
0x18002d565  pop     r15
0x18002d567  pop     r14
0x18002d569  pop     r12
0x18002d56b  pop     rdi
0x18002d56c  pop     rsi
0x18002d56d  retn
```
