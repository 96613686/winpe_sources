# CAsyncHttp::StartRequestThread(void)

- ea: `0x1800a7604`
- end: `0x1800a77d3`
- name: `?StartRequestThread@CAsyncHttp@@AEAAJXZ`
- size: `463`
- prototype: `__int64 __fastcall(CAsyncHttp *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a77dc`

## callees

- `0x1800a7604`
- `0x1800cc9ba`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800a775f`
- `KERNEL32!WaitForSingleObject` at `0x1800a775f`
- `KERNEL32!CloseHandle` at `0x1800a7775`
- `KERNEL32!CloseHandle` at `0x1800a779e`
- `KERNEL32!CloseHandle` at `0x1800a7775`
- `KERNEL32!CloseHandle` at `0x1800a779e`
- `KERNEL32!GetLastError` at `0x1800a777d`
- `KERNEL32!GetLastError` at `0x1800a77a6`
- `KERNEL32!GetLastError` at `0x1800a777d`
- `KERNEL32!GetLastError` at `0x1800a77a6`
- `KERNEL32!CreateThread` at `0x1800a7748`
- `KERNEL32!CreateThread` at `0x1800a7748`
- `KERNEL32!CreateEventA` at `0x1800a769c`
- `KERNEL32!CreateEventA` at `0x1800a769c`
- `USER32!IsWindow` at `0x1800a7633`
- `USER32!IsWindow` at `0x1800a7633`

## pseudocode

```c
__int64 __fastcall CAsyncHttp::StartRequestThread(CAsyncHttp *this)
{
  HWND v2; // rcx
  HANDLE v3; // rsi
  unsigned int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  int Parameter; // [rsp+30h] [rbp-29h] BYREF
  HANDLE hHandle; // [rsp+38h] [rbp-21h]
  __int64 v10; // [rsp+40h] [rbp-19h]
  __int64 v11; // [rsp+48h] [rbp-11h]
  __int64 v12; // [rsp+50h] [rbp-9h]
  __int64 v13; // [rsp+58h] [rbp-1h]
  char *v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  __int64 v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+78h] [rbp+1Fh]
  int v18; // [rsp+7Ch] [rbp+23h]
  char *v19; // [rsp+80h] [rbp+27h]

  if ( !*((_QWORD *)this + 9) )
    return 2148322308LL;
  v2 = (HWND)*((_QWORD *)this + 348);
  if ( !v2
    || !IsWindow(v2)
    || !*((_BYTE *)this + 398)
    || !*((_QWORD *)this + 339)
    || !*((_QWORD *)this + 340)
    || !*((_QWORD *)this + 11)
    || !*((_QWORD *)this + 12) )
  {
    return 2148322308LL;
  }
  memset_0(&Parameter, 0, 0x58u);
  hHandle = CreateEventA(0, 0, 0, 0);
  if ( hHandle )
  {
    v12 = *((_QWORD *)this + 9);
    v13 = *((_QWORD *)this + 348);
    v15 = *((_QWORD *)this + 339);
    v16 = *((_QWORD *)this + 340);
    v17 = *((_DWORD *)this + 34);
    v10 = *((_QWORD *)this + 11);
    v11 = *((_QWORD *)this + 12);
    v14 = (char *)this + 398;
    if ( *((_WORD *)this + 70) == 443 )
    {
      v18 = 1;
      v19 = (char *)this + 142;
    }
    else
    {
      v18 = 0;
    }
    Parameter = -2146644988;
    v3 = CreateThread(
           0,
           0,
           (LPTHREAD_START_ROUTINE)CAsyncHttp::AsyncHttpThreadEntry,
           &Parameter,
           0,
           (LPDWORD)this + 698);
    if ( v3 )
    {
      WaitForSingleObject(hHandle, 0x2710u);
      v4 = Parameter;
      if ( Parameter >= 0 )
        v4 = -2147483638;
      CloseHandle(v3);
    }
    else
    {
      LastError = GetLastError();
      *((_DWORD *)this + 29) = LastError;
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( hHandle )
      CloseHandle(hHandle);
  }
  else
  {
    v6 = GetLastError();
    *((_DWORD *)this + 29) = v6;
    v4 = v6;
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return v4;
}

```

## disassembly

```asm
0x1800a7604  push    rbp
0x1800a7606  push    rbx
0x1800a7607  push    rsi
0x1800a7608  push    rdi
0x1800a7609  lea     rbp, [rsp-3Fh]
0x1800a760e  sub     rsp, 98h
0x1800a7615  cmp     qword ptr [rcx+48h], 0
0x1800a761a  mov     rdi, rcx
0x1800a761d  jz      loc_1800A77C2
0x1800a7623  mov     rcx, [rcx+0AE0h]; hWnd
0x1800a762a  test    rcx, rcx
0x1800a762d  jz      loc_1800A77C2
0x1800a7633  call    cs:__imp_IsWindow
0x1800a7639  test    eax, eax
0x1800a763b  jz      loc_1800A77C2
0x1800a7641  lea     rbx, [rdi+18Eh]
0x1800a7648  cmp     byte ptr [rbx], 0
0x1800a764b  jz      loc_1800A77C2
0x1800a7651  cmp     qword ptr [rdi+0A98h], 0
0x1800a7659  jz      loc_1800A77C2
0x1800a765f  cmp     qword ptr [rdi+0AA0h], 0
0x1800a7667  jz      loc_1800A77C2
0x1800a766d  cmp     qword ptr [rdi+58h], 0
0x1800a7672  jz      loc_1800A77C2
0x1800a7678  cmp     qword ptr [rdi+60h], 0
0x1800a767d  jz      loc_1800A77C2
0x1800a7683  xor     edx, edx; Val
0x1800a7685  lea     rcx, [rbp+57h+Parameter]; void *
0x1800a7689  lea     r8d, [rdx+58h]; Size
0x1800a768d  call    memset_0
0x1800a7692  xor     r9d, r9d; lpName
0x1800a7695  xor     r8d, r8d; bInitialState
0x1800a7698  xor     edx, edx; bManualReset
0x1800a769a  xor     ecx, ecx; lpEventAttributes
0x1800a769c  call    cs:__imp_CreateEventA
0x1800a76a2  mov     [rbp+57h+hHandle], rax
0x1800a76a6  test    rax, rax
0x1800a76a9  jz      loc_1800A77A6
0x1800a76af  mov     rax, [rdi+48h]
0x1800a76b3  mov     [rbp+57h+var_60], rax
0x1800a76b7  mov     rax, [rdi+0AE0h]
0x1800a76be  mov     [rbp+57h+var_58], rax
0x1800a76c2  mov     rax, [rdi+0A98h]
0x1800a76c9  mov     [rbp+57h+var_48], rax
0x1800a76cd  mov     rax, [rdi+0AA0h]
0x1800a76d4  mov     [rbp+57h+var_40], rax
0x1800a76d8  mov     eax, [rdi+88h]
0x1800a76de  mov     [rbp+57h+var_38], eax
0x1800a76e1  mov     rax, [rdi+58h]
0x1800a76e5  mov     [rbp+57h+var_70], rax
0x1800a76e9  mov     rax, [rdi+60h]
0x1800a76ed  mov     [rbp+57h+var_68], rax
0x1800a76f1  mov     eax, 1BBh
0x1800a76f6  mov     [rbp+57h+var_50], rbx
0x1800a76fa  cmp     ax, [rdi+8Ch]
0x1800a7701  jnz     short loc_1800A7717
0x1800a7703  lea     rax, [rdi+8Eh]
0x1800a770a  mov     [rbp+57h+var_34], 1
0x1800a7711  mov     [rbp+57h+var_30], rax
0x1800a7715  jmp     short loc_1800A771E
0x1800a7717  mov     [rbp+57h+var_34], 0
0x1800a771e  lea     rax, [rdi+0AE8h]
0x1800a7725  mov     [rbp+57h+Parameter], 800CCC04h
0x1800a772c  mov     [rsp+0B0h+lpThreadId], rax; lpThreadId
0x1800a7731  lea     r9, [rbp+57h+Parameter]; lpParameter
0x1800a7735  lea     r8, ?AsyncHttpThreadEntry@CAsyncHttp@@CAKPEAK@Z; lpStartAddress
0x1800a773c  mov     [rsp+0B0h+dwCreationFlags], 0; dwCreationFlags
0x1800a7744  xor     edx, edx; dwStackSize
0x1800a7746  xor     ecx, ecx; lpThreadAttributes
0x1800a7748  call    cs:__imp_CreateThread
0x1800a774e  mov     rsi, rax
0x1800a7751  test    rax, rax
0x1800a7754  jz      short loc_1800A777D
0x1800a7756  mov     rcx, [rbp+57h+hHandle]; hHandle
0x1800a775a  mov     edx, 2710h; dwMilliseconds
0x1800a775f  call    cs:__imp_WaitForSingleObject
0x1800a7765  mov     ebx, [rbp+57h+Parameter]
0x1800a7768  mov     eax, 8000000Ah
0x1800a776d  test    ebx, ebx
0x1800a776f  mov     rcx, rsi; hObject
0x1800a7772  cmovns  ebx, eax
0x1800a7775  call    cs:__imp_CloseHandle
0x1800a777b  jmp     short loc_1800A7795
0x1800a777d  call    cs:__imp_GetLastError
0x1800a7783  mov     [rdi+74h], eax
0x1800a7786  mov     ebx, eax
0x1800a7788  test    eax, eax
0x1800a778a  jle     short loc_1800A7795
0x1800a778c  movzx   ebx, ax
0x1800a778f  or      ebx, 80070000h
0x1800a7795  mov     rcx, [rbp+57h+hHandle]; hObject
0x1800a7799  test    rcx, rcx
0x1800a779c  jz      short loc_1800A77BE
0x1800a779e  call    cs:__imp_CloseHandle
0x1800a77a4  jmp     short loc_1800A77BE
0x1800a77a6  call    cs:__imp_GetLastError
0x1800a77ac  mov     [rdi+74h], eax
0x1800a77af  mov     ebx, eax
0x1800a77b1  test    eax, eax
0x1800a77b3  jle     short loc_1800A77BE
0x1800a77b5  movzx   ebx, ax
0x1800a77b8  or      ebx, 80070000h
0x1800a77be  mov     eax, ebx
0x1800a77c0  jmp     short loc_1800A77C7
0x1800a77c2  mov     eax, 800CCC04h
0x1800a77c7  add     rsp, 98h
0x1800a77ce  pop     rdi
0x1800a77cf  pop     rsi
0x1800a77d0  pop     rbx
0x1800a77d1  pop     rbp
0x1800a77d2  retn
```
