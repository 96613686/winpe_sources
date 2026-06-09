# MsgDlgUtil

- ea: `0x180048f0c`
- end: `0x1800490be`
- name: `MsgDlgUtil`
- size: `434`
- prototype: `__int64 __fastcall(HWND hWnd, UINT uID, va_list *Arguments, HINSTANCE hInstance, UINT)`
- caller_count: `37`
- callee_count: `3`
- tags: ``

## callers

- `0x1800062d0`
- `0x18000c9c8`
- `0x18000cfb0`
- `0x1800103ec`
- `0x180010594`
- `0x180011174`
- `0x180014198`
- `0x1800146fc`
- `0x180016a74`
- `0x180018558`
- `0x180018628`
- `0x180018fec`
- `0x180019328`
- `0x18001a170`
- `0x18001a9e0`
- `0x18001bae4`
- `0x18001c960`
- `0x18001d508`
- `0x18001e074`
- `0x18001ff44`
- `0x18002039c`
- `0x180021660`
- `0x180021a70`
- `0x180022cac`
- `0x180024370`
- `0x1800247ac`
- `0x180024ca4`
- `0x1800251a0`
- `0x180025350`
- `0x1800286ec`
- `0x180029ab0`
- `0x180029dc8`
- `0x18002e75c`
- `0x18002f040`
- `0x1800328bc`
- `0x1800388e4`
- `0x180048b6c`

## callees

- `0x18003bea0`
- `0x18003c43c`
- `0x180048f0c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004909f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004909f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180048fe2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180048fe2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048f96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048fd9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048f96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180048fd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049039`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049039`
- `USER32!MessageBoxW` at `0x180049074`
- `USER32!MessageBoxW` at `0x180049074`
- `USER32!UnhookWindowsHookEx` at `0x180049084`
- `USER32!UnhookWindowsHookEx` at `0x180049084`
- `USER32!SetWindowsHookExW` at `0x180049051`
- `USER32!SetWindowsHookExW` at `0x180049051`
- `rtutils!TracePrintfExA` at `0x180048f4d`
- `rtutils!TracePrintfExA` at `0x180048f4d`

## pseudocode

```c
__int64 __fastcall MsgDlgUtil(HWND hWnd, UINT uID, va_list *Arguments, HINSTANCE hInstance, UINT uIDa)
{
  va_list v9; // rdx
  unsigned int v10; // edi
  void *v11; // rsi
  va_list v12; // rax
  UINT v13; // esi
  WCHAR *v14; // rbp
  DWORD CurrentThreadId; // eax
  HHOOK v16; // rbx
  WCHAR *Buffer; // [rsp+80h] [rbp+18h] BYREF

  Buffer = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "MsgDlgUtil");
  Buffer = (WCHAR *)&WideCharStr;
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
    if ( Buffer != &WideCharStr )
      v12 = (va_list)Buffer;
    Arguments[12] = v12;
    return v10;
  }
LABEL_13:
  v10 = 0;
  if ( !Arguments || (v13 = *((_DWORD *)Arguments + 18)) == 0 )
    v13 = 65600;
  v14 = (WCHAR *)PszFromId(hInstance, uIDa);
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
  if ( Buffer != &WideCharStr )
    LocalFree(Buffer);
  return v10;
}

```

## disassembly

```asm
0x180048f0c  mov     rax, rsp
0x180048f0f  mov     [rax+8], rbx
0x180048f13  mov     [rax+10h], rbp
0x180048f17  push    rsi
0x180048f18  push    rdi
0x180048f19  push    r12
0x180048f1b  push    r14
0x180048f1d  push    r15
0x180048f1f  sub     rsp, 40h
0x180048f23  mov     r15, rcx
0x180048f26  mov     qword ptr [rax+18h], 0
0x180048f2e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180048f34  mov     r14, r9
0x180048f37  mov     rbx, r8
0x180048f3a  mov     edi, edx
0x180048f3c  cmp     ecx, 0FFFFFFFFh
0x180048f3f  jz      short loc_180048F53
0x180048f41  lea     r8, aMsgdlgutil; "MsgDlgUtil"
0x180048f48  mov     edx, 0Ch; dwFlags
0x180048f4d  call    cs:__imp_TracePrintfExA
0x180048f53  lea     r12, WideCharStr
0x180048f5a  mov     [rsp+68h+Buffer], r12
0x180048f62  test    rbx, rbx
0x180048f65  jz      short loc_180048F9E
0x180048f67  mov     rdx, [rbx+50h]; lpSource
0x180048f6b  test    rdx, rdx
0x180048f6e  jz      short loc_180048F9E
0x180048f70  mov     [rsp+68h+Arguments], rbx; Arguments
0x180048f75  lea     rax, [rsp+68h+Buffer]
0x180048f7d  mov     edi, 1
0x180048f82  xor     r9d, r9d; dwLanguageId
0x180048f85  mov     [rsp+68h+nSize], edi; nSize
0x180048f89  xor     r8d, r8d; dwMessageId
0x180048f8c  mov     ecx, 2500h; dwFlags
0x180048f91  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x180048f96  call    cs:__imp_FormatMessageW
0x180048f9c  jmp     short loc_180048FED
0x180048f9e  mov     edx, edi; uID
0x180048fa0  mov     rcx, r14; hInstance
0x180048fa3  call    PszFromId
0x180048fa8  mov     rsi, rax
0x180048fab  mov     edi, 1
0x180048fb0  test    rax, rax
0x180048fb3  jz      short loc_180048FE8
0x180048fb5  mov     [rsp+68h+Arguments], rbx; Arguments
0x180048fba  lea     rax, [rsp+68h+Buffer]
0x180048fc2  mov     [rsp+68h+nSize], edi; nSize
0x180048fc6  xor     r9d, r9d; dwLanguageId
0x180048fc9  xor     r8d, r8d; dwMessageId
0x180048fcc  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x180048fd1  mov     rdx, rsi; lpSource
0x180048fd4  mov     ecx, 2500h; dwFlags
0x180048fd9  call    cs:__imp_FormatMessageW
0x180048fdf  mov     rcx, rsi; hMem
0x180048fe2  call    cs:__imp_GlobalFree
0x180048fe8  test    rbx, rbx
0x180048feb  jz      short loc_18004900F
0x180048fed  cmp     dword ptr [rbx+58h], 0
0x180048ff1  jz      short loc_18004900F
0x180048ff3  xor     eax, eax
0x180048ff5  cmp     [rsp+68h+Buffer], r12
0x180048ffd  cmovnz  rax, [rsp+68h+Buffer]
0x180049006  mov     [rbx+60h], rax
0x18004900a  jmp     loc_1800490A5
0x18004900f  xor     edi, edi
0x180049011  test    rbx, rbx
0x180049014  jz      short loc_18004901D
0x180049016  mov     esi, [rbx+48h]
0x180049019  test    esi, esi
0x18004901b  jnz     short loc_180049022
0x18004901d  mov     esi, 10040h
0x180049022  mov     edx, [rsp+68h+uID]; uID
0x180049029  mov     rcx, r14; hInstance
0x18004902c  call    PszFromId
0x180049031  mov     rbp, rax
0x180049034  test    r15, r15
0x180049037  jz      short loc_18004905C
0x180049039  call    cs:__imp_GetCurrentThreadId
0x18004903f  mov     r8, r14; hmod
0x180049042  lea     rdx, CenterDlgOnOwnerCallWndProc; lpfn
0x180049049  mov     r9d, eax; dwThreadId
0x18004904c  mov     ecx, 4; idHook
0x180049051  call    cs:__imp_SetWindowsHookExW
0x180049057  mov     rbx, rax
0x18004905a  jmp     short loc_18004905E
0x18004905c  xor     ebx, ebx
0x18004905e  mov     rdx, [rsp+68h+Buffer]; lpText
0x180049066  test    rdx, rdx
0x180049069  jz      short loc_18004907C
0x18004906b  mov     r9d, esi; uType
0x18004906e  mov     r8, rbp; lpCaption
0x180049071  mov     rcx, r15; hWnd
0x180049074  call    cs:__imp_MessageBoxW
0x18004907a  mov     edi, eax
0x18004907c  test    rbx, rbx
0x18004907f  jz      short loc_18004908A
0x180049081  mov     rcx, rbx; hhk
0x180049084  call    cs:__imp_UnhookWindowsHookEx
0x18004908a  mov     rcx, rbp
0x18004908d  call    Free0
0x180049092  mov     rcx, [rsp+68h+Buffer]; hMem
0x18004909a  cmp     rcx, r12
0x18004909d  jz      short loc_1800490A5
0x18004909f  call    cs:__imp_LocalFree
0x1800490a5  mov     rbx, [rsp+68h+arg_0]
0x1800490aa  mov     eax, edi
0x1800490ac  mov     rbp, [rsp+68h+arg_8]
0x1800490b1  add     rsp, 40h
0x1800490b5  pop     r15
0x1800490b7  pop     r14
0x1800490b9  pop     r12
0x1800490bb  pop     rdi
0x1800490bc  pop     rsi
0x1800490bd  retn
```
