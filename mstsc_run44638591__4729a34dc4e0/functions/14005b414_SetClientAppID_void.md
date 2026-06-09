# SetClientAppID(void)

- ea: `0x14005b414`
- end: `0x14005b5ff`
- name: `?SetClientAppID@@YAJXZ`
- size: `491`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006590c`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14001e210`
- `0x14005b414`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14005b46c`
- `KERNEL32!LoadLibraryW` at `0x14005b46c`
- `KERNEL32!FreeLibrary` at `0x14005b594`
- `KERNEL32!FreeLibrary` at `0x14005b594`
- `KERNEL32!GetProcAddress` at `0x14005b488`
- `KERNEL32!GetProcAddress` at `0x14005b488`

## string_xrefs

- `0x14005b437`: `shell32.dll`

## pseudocode

```c
__int64 SetClientAppID(void)
{
  int v0; // ebx
  HMODULE LibraryW; // rax
  HMODULE v2; // rdi
  FARPROC ProcAddress; // rax
  unsigned int v4; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  _OWORD v9[4]; // [rsp+30h] [rbp-58h] BYREF

  v0 = -2147467259;
  v9[0] = *(_OWORD *)L"Microsoft.Windows.RemoteDesktop";
  v9[1] = *(_OWORD *)L"t.Windows.RemoteDesktop";
  v9[2] = *(_OWORD *)L"s.RemoteDesktop";
  v9[3] = *(_OWORD *)L"Desktop";
  LibraryW = LoadLibraryW(L"shell32.dll");
  v2 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SetCurrentProcessExplicitAppUserModelID");
    if ( ProcAddress )
    {
      v0 = ((__int64 (__fastcall *)(_OWORD *))ProcAddress)(v9);
      if ( v0 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            11,
            WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
            CurrentThreadActivityIdPrefix,
            v0);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v4 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids,
          v4,
          (__int64)v9);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids, v6);
    }
    FreeLibrary(v2);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids, v7);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14005b414  mov     [rsp+arg_0], rbx
0x14005b419  push    rdi
0x14005b41a  sub     rsp, 80h
0x14005b421  mov     rax, cs:__security_cookie
0x14005b428  xor     rax, rsp
0x14005b42b  mov     [rsp+88h+var_18], rax
0x14005b430  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo; "Microsoft.Windows.RemoteDesktop"
0x14005b437  lea     rcx, aShell32Dll_0; "shell32.dll"
0x14005b43e  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo+10h; "t.Windows.RemoteDesktop"
0x14005b445  mov     ebx, 80004005h
0x14005b44a  movaps  [rsp+88h+var_58], xmm0
0x14005b44f  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo+20h; "s.RemoteDesktop"
0x14005b456  movaps  [rsp+88h+var_48], xmm1
0x14005b45b  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo+30h; "Desktop"
0x14005b462  movaps  [rsp+88h+var_38], xmm0
0x14005b467  movaps  [rsp+88h+var_28], xmm1
0x14005b46c  call    cs:__imp_LoadLibraryW
0x14005b472  mov     rdi, rax
0x14005b475  test    rax, rax
0x14005b478  jz      loc_14005B59C
0x14005b47e  lea     rdx, aSetcurrentproc; "SetCurrentProcessExplicitAppUserModelID"
0x14005b485  mov     rcx, rax; hModule
0x14005b488  call    cs:__imp_GetProcAddress
0x14005b48e  test    rax, rax
0x14005b491  jz      loc_14005B54E
0x14005b497  lea     rcx, [rsp+88h+var_58]
0x14005b49c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b4a1  mov     ebx, eax
0x14005b4a3  test    eax, eax
0x14005b4a5  js      short loc_14005B505
0x14005b4a7  mov     rdx, cs:WPP_GLOBAL_Control
0x14005b4ae  lea     rcx, WPP_GLOBAL_Control
0x14005b4b5  cmp     rdx, rcx
0x14005b4b8  jz      loc_14005B591
0x14005b4be  test    byte ptr [rdx+1Ch], 1
0x14005b4c2  jz      loc_14005B591
0x14005b4c8  cmp     byte ptr [rdx+19h], 4
0x14005b4cc  jb      loc_14005B591
0x14005b4d2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b4d7  lea     rcx, [rsp+88h+var_58]
0x14005b4dc  mov     edx, 0Ah
0x14005b4e1  mov     [rsp+88h+var_68], rcx
0x14005b4e6  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b4f4  mov     r9d, eax
0x14005b4f7  mov     rcx, [rcx+10h]
0x14005b4fb  call    WPP_SF_DS
0x14005b500  jmp     loc_14005B591
0x14005b505  mov     rax, cs:WPP_GLOBAL_Control
0x14005b50c  lea     rcx, WPP_GLOBAL_Control
0x14005b513  cmp     rax, rcx
0x14005b516  jz      short loc_14005B591
0x14005b518  test    byte ptr [rax+1Ch], 1
0x14005b51c  jz      short loc_14005B591
0x14005b51e  cmp     byte ptr [rax+19h], 2
0x14005b522  jb      short loc_14005B591
0x14005b524  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b529  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b530  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b537  mov     edx, 0Bh
0x14005b53c  mov     dword ptr [rsp+88h+var_68], ebx
0x14005b540  mov     r9d, eax
0x14005b543  mov     rcx, [rcx+10h]
0x14005b547  call    WPP_SF_Dd
0x14005b54c  jmp     short loc_14005B591
0x14005b54e  mov     rax, cs:WPP_GLOBAL_Control
0x14005b555  lea     rcx, WPP_GLOBAL_Control
0x14005b55c  cmp     rax, rcx
0x14005b55f  jz      short loc_14005B591
0x14005b561  test    byte ptr [rax+1Ch], 1
0x14005b565  jz      short loc_14005B591
0x14005b567  cmp     byte ptr [rax+19h], 4
0x14005b56b  jb      short loc_14005B591
0x14005b56d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b572  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b579  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b580  mov     edx, 0Ch
0x14005b585  mov     r9d, eax
0x14005b588  mov     rcx, [rcx+10h]
0x14005b58c  call    WPP_SF_d
0x14005b591  mov     rcx, rdi; hLibModule
0x14005b594  call    cs:__imp_FreeLibrary
0x14005b59a  jmp     short loc_14005B5DF
0x14005b59c  mov     rax, cs:WPP_GLOBAL_Control
0x14005b5a3  lea     rcx, WPP_GLOBAL_Control
0x14005b5aa  cmp     rax, rcx
0x14005b5ad  jz      short loc_14005B5DF
0x14005b5af  test    byte ptr [rax+1Ch], 1
0x14005b5b3  jz      short loc_14005B5DF
0x14005b5b5  cmp     byte ptr [rax+19h], 2
0x14005b5b9  jb      short loc_14005B5DF
0x14005b5bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005b5c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b5c7  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005b5ce  mov     edx, 0Dh
0x14005b5d3  mov     r9d, eax
0x14005b5d6  mov     rcx, [rcx+10h]
0x14005b5da  call    WPP_SF_d
0x14005b5df  mov     eax, ebx
0x14005b5e1  mov     rcx, [rsp+88h+var_18]
0x14005b5e6  xor     rcx, rsp; StackCookie
0x14005b5e9  call    __security_check_cookie
0x14005b5ee  mov     rbx, [rsp+88h+arg_0]
0x14005b5f6  add     rsp, 80h
0x14005b5fd  pop     rdi
0x14005b5fe  retn
```
