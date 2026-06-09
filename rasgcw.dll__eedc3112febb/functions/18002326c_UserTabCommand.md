# UserTabCommand

- ea: `0x18002326c`
- end: `0x1800233f4`
- name: `UserTabCommand`
- size: `392`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180023400`

## callees

- `0x18002049c`
- `0x1800214a0`
- `0x180021af4`
- `0x18002326c`
- `0x180023994`
- `0x180023bac`
- `0x180023e5c`
- `0x180024c4c`
- `0x180026710`

## import_xrefs

- `USER32!PostMessageW` at `0x1800233b5`
- `USER32!PostMessageW` at `0x1800233b5`
- `USER32!GetDlgItem` at `0x180023286`
- `USER32!GetDlgItem` at `0x180023314`
- `USER32!GetDlgItem` at `0x18002335f`
- `USER32!GetDlgItem` at `0x180023286`
- `USER32!GetDlgItem` at `0x180023314`
- `USER32!GetDlgItem` at `0x18002335f`
- `USER32!SendMessageW` at `0x1800232b2`
- `USER32!SendMessageW` at `0x180023331`
- `USER32!SendMessageW` at `0x180023378`
- `USER32!SendMessageW` at `0x1800232b2`
- `USER32!SendMessageW` at `0x180023331`
- `USER32!SendMessageW` at `0x180023378`
- `USER32!GetParent` at `0x1800233a0`
- `USER32!GetParent` at `0x1800233a0`

## pseudocode

```c
__int64 __fastcall UserTabCommand(HWND hWnd, __int64 a2)
{
  HWND DlgItem; // rax
  unsigned int v5; // eax
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rbx
  HWND v11; // rax
  unsigned int v12; // ebx
  HWND v13; // rax
  HWND Parent; // rax

  DlgItem = GetDlgItem(hWnd, 7043);
  if ( DlgItem )
  {
    v5 = SendMessageW(DlgItem, 0x1042u, 0, 0);
    v6 = a2 - 7044;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              if ( v10 == 1 )
              {
                RasSrvGetDatabaseHandle(hWnd);
                v11 = GetDlgItem(hWnd, 7049);
                if ( v11 )
                  SendMessageW(v11, 0xF0u, 0, 0);
              }
            }
            else
            {
              v12 = 0;
              v13 = GetDlgItem(hWnd, 7048);
              if ( v13 )
                LOBYTE(v12) = SendMessageW(v13, 0xF0u, 0, 0) == 1;
              UserTabSaveEncryption(hWnd, v12);
            }
          }
          else if ( (unsigned int)RassrvWarnMMCSwitch(hWnd) )
          {
            Parent = GetParent(hWnd);
            PostMessageW(Parent, 0x471u, 3u, 0);
            RassrvLaunchMMC(2);
          }
        }
        else
        {
          UserTabHandleProperties(hWnd, v5);
        }
      }
      else
      {
        UserTabHandleDeleteUser(hWnd, v5);
      }
    }
    else
    {
      UserTabHandleNewUserRequest(hWnd);
    }
  }
  else
  {
    DbgOutputTrace("getDialogItemFromAnyoneResource failed with error %d", 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18002326c  mov     [rsp+arg_0], rbx
0x180023271  mov     [rsp+arg_10], r8
0x180023276  push    rdi
0x180023277  sub     rsp, 20h
0x18002327b  mov     rbx, rdx
0x18002327e  mov     rdi, rcx
0x180023281  mov     edx, 1B83h; nIDDlgItem
0x180023286  call    cs:__imp_GetDlgItem
0x18002328c  test    rax, rax
0x18002328f  jnz     short loc_1800232A4
0x180023291  xor     edx, edx
0x180023293  lea     rcx, aGetdialogitemf; "getDialogItemFromAnyoneResource failed "...
0x18002329a  call    DbgOutputTrace
0x18002329f  jmp     loc_1800233E7
0x1800232a4  xor     r9d, r9d; lParam
0x1800232a7  xor     r8d, r8d; wParam
0x1800232aa  mov     edx, 1042h; Msg
0x1800232af  mov     rcx, rax; hWnd
0x1800232b2  call    cs:__imp_SendMessageW
0x1800232b8  sub     rbx, 1B84h
0x1800232bf  jz      loc_1800233DF
0x1800232c5  sub     rbx, 1
0x1800232c9  jz      loc_1800233D3
0x1800232cf  sub     rbx, 1
0x1800232d3  jz      loc_1800233C7
0x1800232d9  sub     rbx, 1
0x1800232dd  jz      loc_180023391
0x1800232e3  sub     rbx, 1
0x1800232e7  jz      short loc_180023355
0x1800232e9  cmp     rbx, 1
0x1800232ed  jnz     loc_1800233E7
0x1800232f3  lea     r8, [rsp+28h+arg_10]
0x1800232f8  mov     [rsp+28h+arg_10], 0
0x180023301  lea     edx, [rbx+1]
0x180023304  mov     rcx, rdi; hWnd
0x180023307  call    RasSrvGetDatabaseHandle
0x18002330c  mov     edx, 1B89h; nIDDlgItem
0x180023311  mov     rcx, rdi; hDlg
0x180023314  call    cs:__imp_GetDlgItem
0x18002331a  test    rax, rax
0x18002331d  jz      loc_1800233E7
0x180023323  xor     r9d, r9d; lParam
0x180023326  xor     r8d, r8d; wParam
0x180023329  mov     edx, 0F0h; Msg
0x18002332e  mov     rcx, rax; hWnd
0x180023331  call    cs:__imp_SendMessageW
0x180023337  xor     ecx, ecx
0x180023339  cmp     rax, rbx
0x18002333c  mov     rax, [rsp+28h+arg_10]
0x180023341  setz    cl
0x180023344  test    rax, rax
0x180023347  jz      loc_1800233E7
0x18002334d  mov     [rax+14h], ecx
0x180023350  jmp     loc_1800233E7
0x180023355  mov     edx, 1B88h; nIDDlgItem
0x18002335a  mov     rcx, rdi; hDlg
0x18002335d  xor     ebx, ebx
0x18002335f  call    cs:__imp_GetDlgItem
0x180023365  test    rax, rax
0x180023368  jz      short loc_180023385
0x18002336a  xor     r9d, r9d; lParam
0x18002336d  xor     r8d, r8d; wParam
0x180023370  mov     edx, 0F0h; Msg
0x180023375  mov     rcx, rax; hWnd
0x180023378  call    cs:__imp_SendMessageW
0x18002337e  cmp     rax, 1
0x180023382  setz    bl
0x180023385  mov     edx, ebx
0x180023387  mov     rcx, rdi
0x18002338a  call    UserTabSaveEncryption
0x18002338f  jmp     short loc_1800233E7
0x180023391  mov     rcx, rdi; hWnd
0x180023394  call    RassrvWarnMMCSwitch
0x180023399  test    eax, eax
0x18002339b  jz      short loc_1800233E7
0x18002339d  mov     rcx, rdi; hWnd
0x1800233a0  call    cs:__imp_GetParent
0x1800233a6  xor     r9d, r9d; lParam
0x1800233a9  mov     edx, 471h; Msg
0x1800233ae  mov     rcx, rax; hWnd
0x1800233b1  lea     r8d, [r9+3]; wParam
0x1800233b5  call    cs:__imp_PostMessageW
0x1800233bb  mov     ecx, 2
0x1800233c0  call    RassrvLaunchMMC
0x1800233c5  jmp     short loc_1800233E7
0x1800233c7  mov     edx, eax
0x1800233c9  mov     rcx, rdi
0x1800233cc  call    UserTabHandleProperties
0x1800233d1  jmp     short loc_1800233E7
0x1800233d3  mov     edx, eax
0x1800233d5  mov     rcx, rdi; hWnd
0x1800233d8  call    UserTabHandleDeleteUser
0x1800233dd  jmp     short loc_1800233E7
0x1800233df  mov     rcx, rdi; hWnd
0x1800233e2  call    UserTabHandleNewUserRequest
0x1800233e7  mov     rbx, [rsp+28h+arg_0]
0x1800233ec  xor     eax, eax
0x1800233ee  add     rsp, 20h
0x1800233f2  pop     rdi
0x1800233f3  retn
```
