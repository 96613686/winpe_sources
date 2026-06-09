# BcpFindMessage

- ea: `0x140cb5970`
- end: `0x140cb5b32`
- name: `BcpFindMessage`
- size: `450`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1406d1e14`
- `0x140cb5b38`

## callees

- `0x140bf2dc4`
- `0x140cb5970`

## string_xrefs

- `0x140cb5a35`: `Your Windows Insider Build ran into a problem and needs to restart.`
- `0x140cb5a95`: `https://www.windows.com/stopcode`
- `0x140cb5ae6`: `%1% complete`

## pseudocode

```c
const wchar_t *__fastcall BcpFindMessage(unsigned int a1)
{
  wchar_t *Message; // rcx
  unsigned int v3; // r8d
  __int64 v4; // rax
  wchar_t v5; // ax
  unsigned __int64 v6; // rdx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx

  if ( a1 != 1090551832 || (Message = Dst) == 0 )
  {
    Message = (wchar_t *)ResFwFindMessage(a1);
    if ( !Message )
    {
      if ( a1 > 0x41008018 )
      {
        switch ( a1 )
        {
          case 0x41008019u:
            return L"Please release the power button.";
          case 0x41008020u:
            return L"We just need a few more seconds to shut down.";
          case 0x41008021u:
            return L"It is now safe to power off the system.";
          case 0xC1008001:
            return L"Your device ran into a problem and needs to restart.";
          case 0xC1008003:
            return L"If you call a support person, give them this info:";
          case 0xC1008008:
            return L"We're just collecting some error info, and then we'll restart for you.";
          case 0xC1008012:
          case 0xC1008013:
            return L"%1% complete";
        }
      }
      else
      {
        if ( a1 == 1090551832 )
          return L"https://www.windows.com/stopcode";
        v7 = a1 - 1090551814;
        if ( !v7 )
          return L"1";
        v8 = v7 - 3;
        if ( !v8 )
          return L"We're just collecting some error info, and then you can restart.";
        v9 = v8 - 7;
        if ( !v9 )
          return L"We'll restart for you.";
        v10 = v9 - 1;
        if ( !v10 )
          return L"You can restart.";
        v11 = v10 - 3;
        if ( !v11 )
          return L"What failed:";
        v12 = v11 - 1;
        if ( !v12 )
          return L"Stop Code:";
        v13 = v12 - 1;
        if ( !v13 )
          return L"For more information about this issue and possible fixes, visit ";
        if ( v13 == 1 )
          return L"Your Windows Insider Build ran into a problem and needs to restart.";
      }
      return 0;
    }
    v3 = 0;
    v4 = -1;
    do
      ++v4;
    while ( Message[v4] );
    if ( v4 )
    {
      do
      {
        v5 = Message[v3];
        if ( v5 == 13 || v5 == 10 )
          Message[v3] = 0;
        ++v3;
        v6 = -1;
        do
          ++v6;
        while ( Message[v6] );
      }
      while ( v3 < v6 );
    }
  }
  return Message;
}

```

## disassembly

```asm
0x140cb5970  mov     [rsp+arg_0], rbx
0x140cb5975  push    rdi
0x140cb5976  sub     rsp, 20h
0x140cb597a  xor     edi, edi
0x140cb597c  mov     ebx, ecx
0x140cb597e  cmp     ecx, 41008018h
0x140cb5984  jnz     short loc_140CB5996
0x140cb5986  mov     rcx, cs:Dst
0x140cb598d  test    rcx, rcx
0x140cb5990  jnz     loc_140CB5B23
0x140cb5996  mov     ecx, ebx
0x140cb5998  call    ResFwFindMessage
0x140cb599d  mov     rcx, rax
0x140cb59a0  test    rax, rax
0x140cb59a3  jz      short loc_140CB59F4
0x140cb59a5  or      r9, 0FFFFFFFFFFFFFFFFh
0x140cb59a9  mov     r8d, edi
0x140cb59ac  mov     rax, r9
0x140cb59af  inc     rax
0x140cb59b2  cmp     [rcx+rax*2], di
0x140cb59b6  jnz     short loc_140CB59AF
0x140cb59b8  test    rax, rax
0x140cb59bb  jz      loc_140CB5B23
0x140cb59c1  mov     edx, r8d
0x140cb59c4  movzx   eax, word ptr [rcx+rdx*2]
0x140cb59c8  cmp     ax, 0Dh
0x140cb59cc  jz      short loc_140CB59D4
0x140cb59ce  cmp     ax, 0Ah
0x140cb59d2  jnz     short loc_140CB59D8
0x140cb59d4  mov     [rcx+rdx*2], di
0x140cb59d8  inc     r8d
0x140cb59db  mov     rdx, r9
0x140cb59de  inc     rdx
0x140cb59e1  cmp     [rcx+rdx*2], di
0x140cb59e5  jnz     short loc_140CB59DE
0x140cb59e7  mov     eax, r8d
0x140cb59ea  cmp     rax, rdx
0x140cb59ed  jb      short loc_140CB59C1
0x140cb59ef  jmp     loc_140CB5B23
0x140cb59f4  cmp     ebx, 41008018h
0x140cb59fa  ja      loc_140CB5AA1
0x140cb5a00  jz      loc_140CB5A95
0x140cb5a06  sub     ebx, 41008006h
0x140cb5a0c  jz      short loc_140CB5A89
0x140cb5a0e  sub     ebx, 3
0x140cb5a11  jz      short loc_140CB5A7D
0x140cb5a13  sub     ebx, 7
0x140cb5a16  jz      short loc_140CB5A71
0x140cb5a18  sub     ebx, 1
0x140cb5a1b  jz      short loc_140CB5A65
0x140cb5a1d  sub     ebx, 3
0x140cb5a20  jz      short loc_140CB5A59
0x140cb5a22  sub     ebx, 1
0x140cb5a25  jz      short loc_140CB5A4D
0x140cb5a27  sub     ebx, 1
0x140cb5a2a  jz      short loc_140CB5A41
0x140cb5a2c  cmp     ebx, 1
0x140cb5a2f  jnz     loc_140CB5AE1
0x140cb5a35  lea     rcx, aYourWindowsIns; "Your Windows Insider Build ran into a p"...
0x140cb5a3c  jmp     loc_140CB5B23
0x140cb5a41  lea     rcx, aForMoreInforma; "For more information about this issue a"...
0x140cb5a48  jmp     loc_140CB5B23
0x140cb5a4d  lea     rcx, aStopCode; "Stop Code:"
0x140cb5a54  jmp     loc_140CB5B23
0x140cb5a59  lea     rcx, aWhatFailed; "What failed:"
0x140cb5a60  jmp     loc_140CB5B23
0x140cb5a65  lea     rcx, aYouCanRestart; "You can restart."
0x140cb5a6c  jmp     loc_140CB5B23
0x140cb5a71  lea     rcx, aWeLlRestartFor; "We'll restart for you."
0x140cb5a78  jmp     loc_140CB5B23
0x140cb5a7d  lea     rcx, aWeReJustCollec_0; "We're just collecting some error info, "...
0x140cb5a84  jmp     loc_140CB5B23
0x140cb5a89  lea     rcx, a1; "1"
0x140cb5a90  jmp     loc_140CB5B23
0x140cb5a95  lea     rcx, aHttpsWwwWindow; "https://www.windows.com/stopcode"
0x140cb5a9c  jmp     loc_140CB5B23
0x140cb5aa1  cmp     ebx, 41008019h
0x140cb5aa7  jz      short loc_140CB5B1C
0x140cb5aa9  cmp     ebx, 41008020h
0x140cb5aaf  jz      short loc_140CB5B13
0x140cb5ab1  cmp     ebx, 41008021h
0x140cb5ab7  jz      short loc_140CB5B0A
0x140cb5ab9  cmp     ebx, 0C1008001h
0x140cb5abf  jz      short loc_140CB5B01
0x140cb5ac1  cmp     ebx, 0C1008003h
0x140cb5ac7  jz      short loc_140CB5AF8
0x140cb5ac9  cmp     ebx, 0C1008008h
0x140cb5acf  jz      short loc_140CB5AEF
0x140cb5ad1  cmp     ebx, 0C1008012h
0x140cb5ad7  jz      short loc_140CB5AE6
0x140cb5ad9  cmp     ebx, 0C1008013h
0x140cb5adf  jz      short loc_140CB5AE6
0x140cb5ae1  mov     rcx, rdi
0x140cb5ae4  jmp     short loc_140CB5B23
0x140cb5ae6  lea     rcx, a1Complete; "%1% complete"
0x140cb5aed  jmp     short loc_140CB5B23
0x140cb5aef  lea     rcx, aWeReJustCollec; "We're just collecting some error info, "...
0x140cb5af6  jmp     short loc_140CB5B23
0x140cb5af8  lea     rcx, aIfYouCallASupp; "If you call a support person, give them"...
0x140cb5aff  jmp     short loc_140CB5B23
0x140cb5b01  lea     rcx, aYourDeviceRanI; "Your device ran into a problem and need"...
0x140cb5b08  jmp     short loc_140CB5B23
0x140cb5b0a  lea     rcx, aItIsNowSafeToP; "It is now safe to power off the system."
0x140cb5b11  jmp     short loc_140CB5B23
0x140cb5b13  lea     rcx, aWeJustNeedAFew; "We just need a few more seconds to shut"...
0x140cb5b1a  jmp     short loc_140CB5B23
0x140cb5b1c  lea     rcx, aPleaseReleaseT; "Please release the power button."
0x140cb5b23  mov     rbx, [rsp+28h+arg_0]
0x140cb5b28  mov     rax, rcx
0x140cb5b2b  add     rsp, 20h
0x140cb5b2f  pop     rdi
0x140cb5b30  retn
```
