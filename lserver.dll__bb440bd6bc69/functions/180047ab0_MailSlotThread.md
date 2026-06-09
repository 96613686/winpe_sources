# MailSlotThread

- ea: `0x180047ab0`
- end: `0x180047cb8`
- name: `MailSlotThread`
- size: `520`
- prototype: `void __fastcall __noreturn(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005665`
- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x180047ab0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180047b00`
- `msvcrt!swprintf_s` at `0x180047b00`
- `msvcrt!_wcsnicmp` at `0x180047c56`
- `msvcrt!_wcsnicmp` at `0x180047c56`
- `KERNEL32!CreateMailslotW` at `0x180047b20`
- `KERNEL32!CreateMailslotW` at `0x180047b20`
- `KERNEL32!ReadFile` at `0x180047bba`
- `KERNEL32!ReadFile` at `0x180047bba`
- `KERNEL32!ExitThread` at `0x180047b46`
- `KERNEL32!ExitThread` at `0x180047b46`
- `KERNEL32!GetLastError` at `0x180047b38`
- `KERNEL32!GetLastError` at `0x180047bdc`
- `KERNEL32!GetLastError` at `0x180047b38`
- `KERNEL32!GetLastError` at `0x180047bdc`
- `KERNEL32!SetEvent` at `0x180047b56`
- `KERNEL32!SetEvent` at `0x180047b56`

## pseudocode

```c
void __fastcall __noreturn MailSlotThread(void *a1)
{
  HANDLE MailslotW; // rsi
  DWORD LastError; // eax
  DWORD v4; // eax
  struct _ProtocolFuncMapper near **v5; // rbx
  __int64 v6; // rdi
  const wchar_t *v7; // rdx
  size_t v8; // r8
  struct _ProtocolFuncMapper near *v9; // rcx
  __int64 v10; // rax
  wchar_t *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rcx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-518h] BYREF
  wchar_t Buffer[360]; // [rsp+40h] [rbp-508h] BYREF
  WCHAR Name[264]; // [rsp+310h] [rbp-238h] BYREF

  NumberOfBytesRead = 0;
  swprintf_s(Name, 0x105u, L"\\\\.\\mailslot\\%s", L"HydraLsServer");
  MailslotW = CreateMailslotW(Name, 0x163u, 0xFFFFFFFF, 0);
  if ( MailslotW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    ExitThread(LastError);
  }
  SetEvent(a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids);
  while ( 1 )
  {
    while ( 1 )
    {
      memset_0(Buffer, 0, 0x2C8u);
      if ( ReadFile(MailslotW, Buffer, 0x2C6u, &NumberOfBytesRead, 0) )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v4 = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids, v4);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids, Buffer);
    v5 = &pfm;
    v6 = 2;
    do
    {
      v7 = (const wchar_t *)*v5;
      v8 = -1;
      do
        ++v8;
      while ( v7[v8] );
      if ( !_wcsnicmp(Buffer, v7, v8) )
      {
        v9 = *v5;
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)v9 + v10) );
        v11 = &Buffer[v10];
        v12 = -1;
        do
          ++v12;
        while ( *((_WORD *)v9 + v12) );
        v13 = -1;
        do
          ++v13;
        while ( Buffer[v13] );
        ((void (__fastcall *)(_QWORD, wchar_t *, wchar_t *))v5[1])((unsigned int)(2 * (v13 - v12)), v11, Buffer);
      }
      v5 += 2;
      --v6;
    }
    while ( v6 );
  }
}

```

## disassembly

```asm
0x180047ab0  mov     r11, rsp
0x180047ab3  mov     [r11+10h], rbx
0x180047ab7  mov     [r11+18h], rbp
0x180047abb  mov     [r11+20h], rsi
0x180047abf  push    rdi
0x180047ac0  push    r14
0x180047ac2  push    r15
0x180047ac4  sub     rsp, 530h
0x180047acb  mov     rax, cs:__security_cookie
0x180047ad2  xor     rax, rsp
0x180047ad5  mov     [rsp+548h+var_28], rax
0x180047add  mov     rbx, rcx
0x180047ae0  lea     r9, aHydralsserver; "HydraLsServer"
0x180047ae7  xor     ebp, ebp
0x180047ae9  lea     rcx, [r11-238h]; Buffer
0x180047af0  lea     r8, aMailslotS; "\\\\.\\mailslot\\%s"
0x180047af7  mov     [rsp+548h+NumberOfBytesRead], ebp
0x180047afb  mov     edx, 105h; BufferCount
0x180047b00  call    cs:__imp_swprintf_s
0x180047b07  nop     dword ptr [rax+rax+00h]
0x180047b0c  xor     r9d, r9d; lpSecurityAttributes
0x180047b0f  lea     rcx, [rsp+548h+Name]; lpName
0x180047b17  or      r8d, 0FFFFFFFFh; lReadTimeout
0x180047b1b  mov     edx, 163h; nMaxMessageSize
0x180047b20  call    cs:__imp_CreateMailslotW
0x180047b27  nop     dword ptr [rax+rax+00h]
0x180047b2c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180047b30  mov     rsi, rax
0x180047b33  cmp     rax, r14
0x180047b36  jnz     short loc_180047B53
0x180047b38  call    cs:__imp_GetLastError
0x180047b3f  nop     dword ptr [rax+rax+00h]
0x180047b44  mov     ecx, eax; dwExitCode
0x180047b46  call    cs:__imp_ExitThread
0x180047b53  mov     rcx, rbx; hEvent
0x180047b56  call    cs:__imp_SetEvent
0x180047b5d  nop     dword ptr [rax+rax+00h]
0x180047b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b69  lea     r15, WPP_GLOBAL_Control
0x180047b70  cmp     rcx, r15
0x180047b73  jz      short loc_180047B90
0x180047b75  test    byte ptr [rcx+1Ch], 10h
0x180047b79  jz      short loc_180047B90
0x180047b7b  mov     rcx, [rcx+10h]
0x180047b7f  lea     r8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids
0x180047b86  mov     edx, 11h
0x180047b8b  call    WPP_SF_
0x180047b90  xor     edx, edx; Val
0x180047b92  lea     rcx, [rsp+548h+Buffer]; void *
0x180047b97  mov     r8d, 2C8h; Size
0x180047b9d  call    memset_0
0x180047ba2  lea     r9, [rsp+548h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180047ba7  mov     [rsp+548h+lpOverlapped], rbp; lpOverlapped
0x180047bac  mov     r8d, 2C6h; nNumberOfBytesToRead
0x180047bb2  lea     rdx, [rsp+548h+Buffer]; lpBuffer
0x180047bb7  mov     rcx, rsi; hFile
0x180047bba  call    cs:__imp_ReadFile
0x180047bc1  nop     dword ptr [rax+rax+00h]
0x180047bc6  test    eax, eax
0x180047bc8  jnz     short loc_180047C09
0x180047bca  mov     rax, cs:WPP_GLOBAL_Control
0x180047bd1  cmp     rax, r15
0x180047bd4  jz      short loc_180047B90
0x180047bd6  test    byte ptr [rax+1Ch], 10h
0x180047bda  jz      short loc_180047B90
0x180047bdc  call    cs:__imp_GetLastError
0x180047be3  nop     dword ptr [rax+rax+00h]
0x180047be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180047bef  lea     r8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids
0x180047bf6  mov     edx, 12h
0x180047bfb  mov     r9d, eax
0x180047bfe  mov     rcx, [rcx+10h]
0x180047c02  call    WPP_SF_D
0x180047c07  jmp     short loc_180047B90
0x180047c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180047c10  cmp     rcx, r15
0x180047c13  jz      short loc_180047C35
0x180047c15  test    byte ptr [rcx+1Ch], 40h
0x180047c19  jz      short loc_180047C35
0x180047c1b  mov     rcx, [rcx+10h]
0x180047c1f  lea     r9, [rsp+548h+Buffer]
0x180047c24  mov     edx, 13h
0x180047c29  lea     r8, WPP_c61626c209a4337108b75ff9dbcad54b_Traceguids
0x180047c30  call    WPP_SF_S
0x180047c35  lea     rbx, ?pfm@@3PAU_ProtocolFuncMapper@@A; _ProtocolFuncMapper near * pfm
0x180047c3c  mov     edi, 2
0x180047c41  mov     rdx, [rbx]; String2
0x180047c44  mov     r8, r14
0x180047c47  inc     r8; MaxCount
0x180047c4a  cmp     [rdx+r8*2], bp
0x180047c4f  jnz     short loc_180047C47
0x180047c51  lea     rcx, [rsp+548h+Buffer]; String1
0x180047c56  call    cs:__imp__wcsnicmp
0x180047c5d  nop     dword ptr [rax+rax+00h]
0x180047c62  test    eax, eax
0x180047c64  jnz     short loc_180047CA9
0x180047c66  mov     rcx, [rbx]
0x180047c69  mov     rax, r14
0x180047c6c  inc     rax
0x180047c6f  cmp     [rcx+rax*2], bp
0x180047c73  jnz     short loc_180047C6C
0x180047c75  lea     rdx, [rsp+548h+Buffer]
0x180047c7a  lea     rdx, [rdx+rax*2]
0x180047c7e  mov     rax, r14
0x180047c81  inc     rax
0x180047c84  cmp     [rcx+rax*2], bp
0x180047c88  jnz     short loc_180047C81
0x180047c8a  lea     r8, [rsp+548h+Buffer]
0x180047c8f  mov     rcx, r14
0x180047c92  inc     rcx
0x180047c95  cmp     [r8+rcx*2], bp
0x180047c9a  jnz     short loc_180047C92
0x180047c9c  sub     ecx, eax
0x180047c9e  mov     rax, [rbx+8]
0x180047ca2  add     ecx, ecx
0x180047ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ca9  add     rbx, 10h
0x180047cad  sub     rdi, 1
0x180047cb1  jnz     short loc_180047C41
0x180047cb3  jmp     loc_180047B90
```
