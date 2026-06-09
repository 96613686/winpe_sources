# SetClientAppID(void)

- ea: `0x1400592a4`
- end: `0x14005948f`
- name: `?SetClientAppID@@YAJXZ`
- size: `491`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14006379c`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14001e210`
- `0x1400592a4`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1400592fc`
- `KERNEL32!LoadLibraryW` at `0x1400592fc`
- `KERNEL32!FreeLibrary` at `0x140059424`
- `KERNEL32!FreeLibrary` at `0x140059424`
- `KERNEL32!GetProcAddress` at `0x140059318`
- `KERNEL32!GetProcAddress` at `0x140059318`

## string_xrefs

- `0x1400592c7`: `shell32.dll`

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
0x1400592a4  mov     [rsp+arg_0], rbx
0x1400592a9  push    rdi
0x1400592aa  sub     rsp, 80h
0x1400592b1  mov     rax, cs:__security_cookie
0x1400592b8  xor     rax, rsp
0x1400592bb  mov     [rsp+88h+var_18], rax
0x1400592c0  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo; "Microsoft.Windows.RemoteDesktop"
0x1400592c7  lea     rcx, aShell32Dll_0; "shell32.dll"
0x1400592ce  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo+10h; "t.Windows.RemoteDesktop"
0x1400592d5  mov     ebx, 80004005h
0x1400592da  movaps  [rsp+88h+var_58], xmm0
0x1400592df  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo+20h; "s.RemoteDesktop"
0x1400592e6  movaps  [rsp+88h+var_48], xmm1
0x1400592eb  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo+30h; "Desktop"
0x1400592f2  movaps  [rsp+88h+var_38], xmm0
0x1400592f7  movaps  [rsp+88h+var_28], xmm1
0x1400592fc  call    cs:__imp_LoadLibraryW
0x140059302  mov     rdi, rax
0x140059305  test    rax, rax
0x140059308  jz      loc_14005942C
0x14005930e  lea     rdx, aSetcurrentproc; "SetCurrentProcessExplicitAppUserModelID"
0x140059315  mov     rcx, rax; hModule
0x140059318  call    cs:__imp_GetProcAddress
0x14005931e  test    rax, rax
0x140059321  jz      loc_1400593DE
0x140059327  lea     rcx, [rsp+88h+var_58]
0x14005932c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059331  mov     ebx, eax
0x140059333  test    eax, eax
0x140059335  js      short loc_140059395
0x140059337  mov     rdx, cs:WPP_GLOBAL_Control
0x14005933e  lea     rcx, WPP_GLOBAL_Control
0x140059345  cmp     rdx, rcx
0x140059348  jz      loc_140059421
0x14005934e  test    byte ptr [rdx+1Ch], 1
0x140059352  jz      loc_140059421
0x140059358  cmp     byte ptr [rdx+19h], 4
0x14005935c  jb      loc_140059421
0x140059362  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059367  lea     rcx, [rsp+88h+var_58]
0x14005936c  mov     edx, 0Ah
0x140059371  mov     [rsp+88h+var_68], rcx
0x140059376  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005937d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059384  mov     r9d, eax
0x140059387  mov     rcx, [rcx+10h]
0x14005938b  call    WPP_SF_DS
0x140059390  jmp     loc_140059421
0x140059395  mov     rax, cs:WPP_GLOBAL_Control
0x14005939c  lea     rcx, WPP_GLOBAL_Control
0x1400593a3  cmp     rax, rcx
0x1400593a6  jz      short loc_140059421
0x1400593a8  test    byte ptr [rax+1Ch], 1
0x1400593ac  jz      short loc_140059421
0x1400593ae  cmp     byte ptr [rax+19h], 2
0x1400593b2  jb      short loc_140059421
0x1400593b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400593b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400593c0  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x1400593c7  mov     edx, 0Bh
0x1400593cc  mov     dword ptr [rsp+88h+var_68], ebx
0x1400593d0  mov     r9d, eax
0x1400593d3  mov     rcx, [rcx+10h]
0x1400593d7  call    WPP_SF_Dd
0x1400593dc  jmp     short loc_140059421
0x1400593de  mov     rax, cs:WPP_GLOBAL_Control
0x1400593e5  lea     rcx, WPP_GLOBAL_Control
0x1400593ec  cmp     rax, rcx
0x1400593ef  jz      short loc_140059421
0x1400593f1  test    byte ptr [rax+1Ch], 1
0x1400593f5  jz      short loc_140059421
0x1400593f7  cmp     byte ptr [rax+19h], 4
0x1400593fb  jb      short loc_140059421
0x1400593fd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059402  mov     rcx, cs:WPP_GLOBAL_Control
0x140059409  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x140059410  mov     edx, 0Ch
0x140059415  mov     r9d, eax
0x140059418  mov     rcx, [rcx+10h]
0x14005941c  call    WPP_SF_d
0x140059421  mov     rcx, rdi; hLibModule
0x140059424  call    cs:__imp_FreeLibrary
0x14005942a  jmp     short loc_14005946F
0x14005942c  mov     rax, cs:WPP_GLOBAL_Control
0x140059433  lea     rcx, WPP_GLOBAL_Control
0x14005943a  cmp     rax, rcx
0x14005943d  jz      short loc_14005946F
0x14005943f  test    byte ptr [rax+1Ch], 1
0x140059443  jz      short loc_14005946F
0x140059445  cmp     byte ptr [rax+19h], 2
0x140059449  jb      short loc_14005946F
0x14005944b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140059450  mov     rcx, cs:WPP_GLOBAL_Control
0x140059457  lea     r8, WPP_5ab83ca8af173af9e591661ee0a2837d_Traceguids
0x14005945e  mov     edx, 0Dh
0x140059463  mov     r9d, eax
0x140059466  mov     rcx, [rcx+10h]
0x14005946a  call    WPP_SF_d
0x14005946f  mov     eax, ebx
0x140059471  mov     rcx, [rsp+88h+var_18]
0x140059476  xor     rcx, rsp; StackCookie
0x140059479  call    __security_check_cookie
0x14005947e  mov     rbx, [rsp+88h+arg_0]
0x140059486  add     rsp, 80h
0x14005948d  pop     rdi
0x14005948e  retn
```
