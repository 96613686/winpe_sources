# CPortableWorkspaceLauncher::CheckLauncherCompatibility(__MIDL_IPortableWorkspaceLauncher_0001 *)

- ea: `0x18000bb80`
- end: `0x18000bca8`
- name: `?CheckLauncherCompatibility@CPortableWorkspaceLauncher@@UEAAJPEAW4__MIDL_IPortableWorkspaceLauncher_0001@@@Z`
- size: `296`
- prototype: `signed int __fastcall(CPortableWorkspaceLauncher *this, enum __MIDL_IPortableWorkspaceLauncher_0001 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005a68`
- `0x180008ac8`
- `0x180008af0`
- `0x18000bb80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000bc23`
- `KERNEL32!GetLastError` at `0x18000bc46`
- `KERNEL32!GetLastError` at `0x18000bc23`
- `KERNEL32!GetLastError` at `0x18000bc46`

## pseudocode

```c
signed int __fastcall CPortableWorkspaceLauncher::CheckLauncherCompatibility(
        CPortableWorkspaceLauncher *this,
        enum __MIDL_IPortableWorkspaceLauncher_0001 *a2)
{
  _QWORD *v3; // rcx
  signed int result; // eax
  int v5; // ebx
  DWORD LastError; // eax
  int v7; // [rsp+38h] [rbp+10h] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v5 = 2;
    v7 = 2;
    if ( (unsigned int)CheckLauncherCompatibilityStatus((enum CompatibilityStatus *)&v7) )
    {
      if ( v7 )
      {
        if ( v7 == 1 )
          v5 = 1;
      }
      else
      {
        v5 = 0;
      }
      *(_DWORD *)a2 = v5;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids, LastError);
      }
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_(v3[2], 11, &WPP_92f1f72f1bef3498f21e8df521798946_Traceguids);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x18000bb80  mov     [rsp+arg_0], rbx
0x18000bb85  mov     [rsp+arg_10], rsi
0x18000bb8a  push    rdi
0x18000bb8b  sub     rsp, 20h
0x18000bb8f  mov     rdi, rdx
0x18000bb92  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb99  lea     rsi, WPP_GLOBAL_Control
0x18000bba0  cmp     rcx, rsi
0x18000bba3  jz      short loc_18000BBC7
0x18000bba5  test    byte ptr [rcx+1Ch], 8
0x18000bba9  jz      short loc_18000BBC7
0x18000bbab  mov     rcx, [rcx+10h]
0x18000bbaf  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000bbb6  mov     edx, 0Ah
0x18000bbbb  call    WPP_SF_
0x18000bbc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbc7  test    rdi, rdi
0x18000bbca  jnz     short loc_18000BBF6
0x18000bbcc  cmp     rcx, rsi
0x18000bbcf  jz      short loc_18000BBEC
0x18000bbd1  lea     ebx, [rdi+1]
0x18000bbd4  test    [rcx+1Ch], bl
0x18000bbd7  jz      short loc_18000BBEC
0x18000bbd9  mov     rcx, [rcx+10h]
0x18000bbdd  lea     edx, [rdi+0Bh]
0x18000bbe0  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000bbe7  call    WPP_SF_
0x18000bbec  mov     eax, 80070057h
0x18000bbf1  jmp     loc_18000BC98
0x18000bbf6  mov     ebx, 2
0x18000bbfb  lea     rcx, [rsp+28h+arg_8]; enum CompatibilityStatus *
0x18000bc00  mov     [rsp+28h+arg_8], ebx
0x18000bc04  call    ?CheckLauncherCompatibilityStatus@@YAHPEAW4CompatibilityStatus@@@Z; CheckLauncherCompatibilityStatus(CompatibilityStatus *)
0x18000bc09  test    eax, eax
0x18000bc0b  jnz     short loc_18000BC5A
0x18000bc0d  mov     rax, cs:WPP_GLOBAL_Control
0x18000bc14  cmp     rax, rsi
0x18000bc17  jz      short loc_18000BC46
0x18000bc19  mov     ebx, 1
0x18000bc1e  test    [rax+1Ch], bl
0x18000bc21  jz      short loc_18000BC46
0x18000bc23  call    cs:__imp_GetLastError
0x18000bc29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc30  lea     edx, [rbx+0Bh]
0x18000bc33  mov     r9d, eax
0x18000bc36  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000bc3d  mov     rcx, [rcx+10h]
0x18000bc41  call    WPP_SF_d
0x18000bc46  call    cs:__imp_GetLastError
0x18000bc4c  test    eax, eax
0x18000bc4e  jle     short loc_18000BC98
0x18000bc50  movzx   eax, ax
0x18000bc53  or      eax, 80070000h
0x18000bc58  jmp     short loc_18000BC98
0x18000bc5a  mov     ecx, [rsp+28h+arg_8]
0x18000bc5e  test    ecx, ecx
0x18000bc60  jz      short loc_18000BC6B
0x18000bc62  cmp     ecx, 1
0x18000bc65  jnz     short loc_18000BC6D
0x18000bc67  mov     ebx, ecx
0x18000bc69  jmp     short loc_18000BC6D
0x18000bc6b  xor     ebx, ebx
0x18000bc6d  mov     [rdi], ebx
0x18000bc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc76  cmp     rcx, rsi
0x18000bc79  jz      short loc_18000BC96
0x18000bc7b  test    byte ptr [rcx+1Ch], 8
0x18000bc7f  jz      short loc_18000BC96
0x18000bc81  mov     rcx, [rcx+10h]
0x18000bc85  lea     r8, WPP_92f1f72f1bef3498f21e8df521798946_Traceguids
0x18000bc8c  mov     edx, 0Dh
0x18000bc91  call    WPP_SF_
0x18000bc96  xor     eax, eax
0x18000bc98  mov     rbx, [rsp+28h+arg_0]
0x18000bc9d  mov     rsi, [rsp+28h+arg_10]
0x18000bca2  add     rsp, 20h
0x18000bca6  pop     rdi
0x18000bca7  retn
```
