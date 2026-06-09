# CRdpWindowTracker::IsDefaultDesktopInteractive(void)

- ea: `0x14005e17c`
- end: `0x14005e2b9`
- name: `?IsDefaultDesktopInteractive@CRdpWindowTracker@@AEAAHXZ`
- size: `317`
- prototype: `__int64 __fastcall(CRdpWindowTracker *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14005d16c`
- `0x14005d874`
- `0x14005f1c0`
- `0x14005f888`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x14005e17c`

## import_xrefs

- `USER32!CloseDesktop` at `0x14005e2a4`
- `USER32!CloseDesktop` at `0x14005e2a4`
- `USER32!GetUserObjectInformationW` at `0x14005e235`
- `USER32!GetUserObjectInformationW` at `0x14005e235`
- `USER32!OpenDesktopW` at `0x14005e1a5`
- `USER32!OpenDesktopW` at `0x14005e1a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e20f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e25e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e29b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e1d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e20f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e25e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005e29b`

## pseudocode

```c
__int64 __fastcall CRdpWindowTracker::IsDefaultDesktopInteractive(CRdpWindowTracker *this)
{
  HDESK v1; // rax
  HDESK v2; // rdi
  signed int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int pvInfo; // [rsp+40h] [rbp+8h] BYREF
  int pvInfo_4; // [rsp+44h] [rbp+Ch]

  pvInfo_4 = HIDWORD(this);
  pvInfo = 0;
  v1 = OpenDesktopW(L"Default", 0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    if ( !GetUserObjectInformationW(v1, 6, &pvInfo, 4u, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          120,
          &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids,
          CurrentThreadActivityIdPrefix,
          v7);
      }
      GetLastError();
    }
    CloseDesktop(v2);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = GetLastError();
      v4 = v3;
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids, v5, v4);
    }
    GetLastError();
  }
  return pvInfo;
}

```

## disassembly

```asm
0x14005e17c  mov     [rsp+arg_8], rbx
0x14005e181  mov     [rsp+pvInfo], rcx
0x14005e186  push    rdi
0x14005e187  sub     rsp, 30h
0x14005e18b  mov     r9d, 1; dwDesiredAccess
0x14005e191  mov     dword ptr [rsp+38h+pvInfo], 0
0x14005e199  xor     r8d, r8d; fInherit
0x14005e19c  lea     rcx, szDesktop; "Default"
0x14005e1a3  xor     edx, edx; dwFlags
0x14005e1a5  call    cs:__imp_OpenDesktopW
0x14005e1ab  mov     rdi, rax
0x14005e1ae  test    rax, rax
0x14005e1b1  jnz     short loc_14005E21A
0x14005e1b3  mov     rax, cs:WPP_GLOBAL_Control
0x14005e1ba  lea     rcx, WPP_GLOBAL_Control
0x14005e1c1  cmp     rax, rcx
0x14005e1c4  jz      short loc_14005E20F
0x14005e1c6  test    byte ptr [rax+1Ch], 8
0x14005e1ca  jz      short loc_14005E20F
0x14005e1cc  cmp     byte ptr [rax+19h], 2
0x14005e1d0  jb      short loc_14005E20F
0x14005e1d2  call    cs:__imp_GetLastError
0x14005e1d8  mov     ebx, eax
0x14005e1da  test    eax, eax
0x14005e1dc  jle     short loc_14005E1E7
0x14005e1de  movzx   ebx, ax
0x14005e1e1  or      ebx, 80070000h
0x14005e1e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e1f3  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005e1fa  mov     edx, 77h ; 'w'
0x14005e1ff  mov     dword ptr [rsp+38h+lpnLengthNeeded], ebx
0x14005e203  mov     r9d, eax
0x14005e206  mov     rcx, [rcx+10h]
0x14005e20a  call    WPP_SF_Dd
0x14005e20f  call    cs:__imp_GetLastError
0x14005e215  jmp     loc_14005E2AA
0x14005e21a  mov     r9d, 4; nLength
0x14005e220  mov     [rsp+38h+lpnLengthNeeded], 0; lpnLengthNeeded
0x14005e229  lea     r8, [rsp+38h+pvInfo]; pvInfo
0x14005e22e  mov     rcx, rdi; hObj
0x14005e231  lea     edx, [r9+2]; nIndex
0x14005e235  call    cs:__imp_GetUserObjectInformationW
0x14005e23b  test    eax, eax
0x14005e23d  jnz     short loc_14005E2A1
0x14005e23f  mov     rax, cs:WPP_GLOBAL_Control
0x14005e246  lea     rcx, WPP_GLOBAL_Control
0x14005e24d  cmp     rax, rcx
0x14005e250  jz      short loc_14005E29B
0x14005e252  test    byte ptr [rax+1Ch], 8
0x14005e256  jz      short loc_14005E29B
0x14005e258  cmp     byte ptr [rax+19h], 2
0x14005e25c  jb      short loc_14005E29B
0x14005e25e  call    cs:__imp_GetLastError
0x14005e264  mov     ebx, eax
0x14005e266  test    eax, eax
0x14005e268  jle     short loc_14005E273
0x14005e26a  movzx   ebx, ax
0x14005e26d  or      ebx, 80070000h
0x14005e273  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005e278  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e27f  lea     r8, WPP_4a4d75114a723d29cbccb95737f23bf1_Traceguids
0x14005e286  mov     edx, 78h ; 'x'
0x14005e28b  mov     dword ptr [rsp+38h+lpnLengthNeeded], ebx
0x14005e28f  mov     r9d, eax
0x14005e292  mov     rcx, [rcx+10h]
0x14005e296  call    WPP_SF_Dd
0x14005e29b  call    cs:__imp_GetLastError
0x14005e2a1  mov     rcx, rdi; hDesktop
0x14005e2a4  call    cs:__imp_CloseDesktop
0x14005e2aa  mov     eax, dword ptr [rsp+38h+pvInfo]
0x14005e2ae  mov     rbx, [rsp+38h+arg_8]
0x14005e2b3  add     rsp, 30h
0x14005e2b7  pop     rdi
0x14005e2b8  retn
```
