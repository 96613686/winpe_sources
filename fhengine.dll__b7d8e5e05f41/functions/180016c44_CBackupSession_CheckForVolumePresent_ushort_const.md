# CBackupSession::CheckForVolumePresent(ushort const *)

- ea: `0x180016c44`
- end: `0x180016d98`
- name: `?CheckForVolumePresent@CBackupSession@@AEAAXPEBG@Z`
- size: `340`
- prototype: `void __fastcall(CBackupSession *this, wint_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180016da0`

## callees

- `0x180009258`
- `0x180012278`
- `0x180016c44`
- `0x180031680`
- `0x180031740`

## import_xrefs

- `msvcrt!towupper` at `0x180016c89`
- `msvcrt!towupper` at `0x180016c89`
- `KERNEL32!GetLastError` at `0x180016d21`
- `KERNEL32!GetLastError` at `0x180016d21`
- `KERNEL32!CloseHandle` at `0x180016d64`
- `KERNEL32!CloseHandle` at `0x180016d64`
- `KERNEL32!ReadFile` at `0x180016cc3`
- `KERNEL32!ReadFile` at `0x180016cc3`

## pseudocode

```c
void __fastcall CBackupSession::CheckForVolumePresent(CBackupSession *this, wint_t *a2)
{
  __int64 v4; // rax
  __int64 v5; // rdi
  void *v6; // rcx
  char LastError; // al
  void *v8; // rcx
  DWORD NumberOfBytesRead[1024]; // [rsp+1030h] [rbp+0h] BYREF

  *(_DWORD *)((unsigned __int64)NumberOfBytesRead & 0xFFFFFFFFFFFFF000uLL) = 0;
  v4 = (unsigned int)towupper(*a2) - 65;
  v5 = (unsigned int)v4;
  v6 = (void *)*((_QWORD *)this + v4 + 71);
  if ( v6 != (void *)-1LL )
  {
    if ( ReadFile(
           v6,
           (LPVOID)(((unsigned __int64)NumberOfBytesRead & 0xFFFFFFFFFFFFF000uLL) + 4096),
           0x1000u,
           (LPDWORD)((unsigned __int64)NumberOfBytesRead & 0xFFFFFFFFFFFFF000uLL),
           0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 435, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, a2);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          436,
          (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
          (_DWORD)a2,
          LastError);
      }
      v8 = (void *)*((_QWORD *)this + v5 + 71);
      if ( v8 != (void *)-1LL )
        CloseHandle(v8);
      *((_QWORD *)this + v5 + 71) = -1;
    }
  }
}

```

## disassembly

```asm
0x180016c44  mov     [rsp-8+arg_10], rbx
0x180016c49  push    rbp
0x180016c4a  push    rsi
0x180016c4b  push    rdi
0x180016c4c  mov     eax, 3040h
0x180016c51  call    _alloca_probe
0x180016c56  sub     rsp, rax
0x180016c59  lea     rbp, [rsp+3050h+NumberOfBytesRead]
0x180016c61  and     rbp, 0FFFFFFFFFFFFF000h
0x180016c68  mov     rax, cs:__security_cookie
0x180016c6f  xor     rax, rsp
0x180016c72  mov     [rbp+2020h+var_20], rax
0x180016c79  mov     rbx, rcx
0x180016c7c  mov     [rbp+2020h+NumberOfBytesRead], 0
0x180016c83  movzx   ecx, word ptr [rdx]; C
0x180016c86  mov     rsi, rdx
0x180016c89  call    cs:__imp_towupper
0x180016c8f  movzx   eax, ax
0x180016c92  sub     eax, 41h ; 'A'
0x180016c95  mov     edi, eax
0x180016c97  mov     rcx, [rbx+rax*8+238h]; hFile
0x180016c9f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016ca3  jz      loc_180016D76
0x180016ca9  lea     r9, [rbp+2020h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180016cad  mov     qword ptr [rsp+20h], 0; lpOverlapped
0x180016cb6  mov     r8d, 1000h; nNumberOfBytesToRead
0x180016cbc  lea     rdx, [rbp+2020h+Buffer]; lpBuffer
0x180016cc3  call    cs:__imp_ReadFile
0x180016cc9  test    eax, eax
0x180016ccb  jz      short loc_180016D08
0x180016ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cd4  lea     rax, WPP_GLOBAL_Control
0x180016cdb  cmp     rcx, rax
0x180016cde  jz      loc_180016D76
0x180016ce4  test    byte ptr [rcx+1Ch], 8
0x180016ce8  jz      loc_180016D76
0x180016cee  mov     rcx, [rcx+10h]
0x180016cf2  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180016cf9  mov     edx, 1B3h
0x180016cfe  mov     r9, rsi
0x180016d01  call    WPP_SF_S
0x180016d06  jmp     short loc_180016D76
0x180016d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d0f  lea     rax, WPP_GLOBAL_Control
0x180016d16  cmp     rcx, rax
0x180016d19  jz      short loc_180016D56
0x180016d1b  test    byte ptr [rcx+1Ch], 8
0x180016d1f  jz      short loc_180016D56
0x180016d21  call    cs:__imp_GetLastError
0x180016d27  test    eax, eax
0x180016d29  jle     short loc_180016D33
0x180016d2b  movzx   eax, ax
0x180016d2e  or      eax, 80070000h
0x180016d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d3a  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180016d41  mov     edx, 1B4h
0x180016d46  mov     [rsp+20h], eax
0x180016d4a  mov     r9, rsi
0x180016d4d  mov     rcx, [rcx+10h]
0x180016d51  call    WPP_SF_Sd
0x180016d56  mov     rcx, [rbx+rdi*8+238h]; hObject
0x180016d5e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016d62  jz      short loc_180016D6A
0x180016d64  call    cs:__imp_CloseHandle
0x180016d6a  mov     qword ptr [rbx+rdi*8+238h], 0FFFFFFFFFFFFFFFFh
0x180016d76  mov     rcx, [rbp+2020h+var_20]
0x180016d7d  xor     rcx, rsp; StackCookie
0x180016d80  call    __security_check_cookie
0x180016d85  mov     rbx, [rsp+3050h+arg_10]
0x180016d8d  add     rsp, 3040h
0x180016d94  pop     rdi
0x180016d95  pop     rsi
0x180016d96  pop     rbp
0x180016d97  retn
```
