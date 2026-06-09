# NhSetComponentMode(NH_COMPONENT_MODE)

- ea: `0x18003ce70`
- end: `0x18003d0d6`
- name: `?NhSetComponentMode@@YAEW4NH_COMPONENT_MODE@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180040fa8`
- `0x180057b40`
- `0x180073a7c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180013650`
- `0x18003ce70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cec2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cec2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ceeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d092`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ceeb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003d092`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003cf6d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18003cf6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cf80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d00c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d00c`

## pseudocode

```c
char __fastcall NhSetComponentMode(unsigned int a1)
{
  PVOID *v2; // rcx
  __int64 v3; // rdx
  DWORD LastError; // eax
  DWORD v5; // edi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids, a1);
  }
  EnterCriticalSection(&NhLock);
  if ( NhpComponentEvent )
  {
    if ( NhComponentMode != a1 )
    {
      LeaveCriticalSection(&NhLock);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          109,
          &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids,
          a1,
          NhComponentMode);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 6u )
        return 0;
      v3 = 110;
LABEL_33:
      WPP_SF_(v2[2], v3, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids);
      return 0;
    }
  }
  else
  {
    NhpComponentEvent = CreateEventA(0, 0, 0, "IPNAT");
    LastError = GetLastError();
    v5 = LastError;
    if ( !NhpComponentEvent )
    {
      LeaveCriticalSection(&NhLock);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids, v5);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 6u )
        return 0;
      v3 = 112;
      goto LABEL_33;
    }
    if ( LastError == 183 )
    {
      CloseHandle(NhpComponentEvent);
      NhpComponentEvent = 0;
      LeaveCriticalSection(&NhLock);
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids, 183);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 == &WPP_GLOBAL_Control || (*((_BYTE *)v2 + 28) & 8) == 0 || *((_BYTE *)v2 + 25) < 6u )
        return 0;
      v3 = 114;
      goto LABEL_33;
    }
  }
  NhComponentMode = a1;
  LeaveCriticalSection(&NhLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x18003ce70  push    rbx
0x18003ce72  push    rbp
0x18003ce73  push    rdi
0x18003ce74  push    r12
0x18003ce76  push    r14
0x18003ce78  sub     rsp, 30h
0x18003ce7c  mov     ebx, ecx
0x18003ce7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ce85  lea     rbp, WPP_GLOBAL_Control
0x18003ce8c  lea     r14, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x18003ce93  cmp     rcx, rbp
0x18003ce96  jz      short loc_18003CEB8
0x18003ce98  test    byte ptr [rcx+1Ch], 8
0x18003ce9c  jz      short loc_18003CEB8
0x18003ce9e  cmp     byte ptr [rcx+19h], 6
0x18003cea2  jb      short loc_18003CEB8
0x18003cea4  mov     rcx, [rcx+10h]
0x18003cea8  mov     edx, 6Ch ; 'l'
0x18003cead  mov     r9d, ebx
0x18003ceb0  mov     r8, r14
0x18003ceb3  call    WPP_SF_d
0x18003ceb8  lea     r12, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION NhLock
0x18003cebf  mov     rcx, r12; lpCriticalSection
0x18003cec2  call    cs:__imp_EnterCriticalSection
0x18003cec9  nop     dword ptr [rax+rax+00h]
0x18003cece  cmp     cs:?NhpComponentEvent@@3PEAXEA, 0; void * NhpComponentEvent
0x18003ced6  jz      loc_18003CF5F
0x18003cedc  cmp     cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A, ebx; NH_COMPONENT_MODE NhComponentMode
0x18003cee2  jz      loc_18003D089
0x18003cee8  mov     rcx, r12; lpCriticalSection
0x18003ceeb  call    cs:__imp_LeaveCriticalSection
0x18003cef2  nop     dword ptr [rax+rax+00h]
0x18003cef7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cefe  cmp     rcx, rbp
0x18003cf01  jz      loc_18003D085
0x18003cf07  test    byte ptr [rcx+1Ch], 8
0x18003cf0b  jz      short loc_18003CF38
0x18003cf0d  cmp     byte ptr [rcx+19h], 2
0x18003cf11  jb      short loc_18003CF38
0x18003cf13  mov     eax, cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A; NH_COMPONENT_MODE NhComponentMode
0x18003cf19  mov     edx, 6Dh ; 'm'
0x18003cf1e  mov     rcx, [rcx+10h]
0x18003cf22  mov     r9d, ebx
0x18003cf25  mov     r8, r14
0x18003cf28  mov     [rsp+58h+var_38], eax
0x18003cf2c  call    WPP_SF_dd
0x18003cf31  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cf38  cmp     rcx, rbp
0x18003cf3b  jz      loc_18003D085
0x18003cf41  test    byte ptr [rcx+1Ch], 8
0x18003cf45  jz      loc_18003D085
0x18003cf4b  cmp     byte ptr [rcx+19h], 6
0x18003cf4f  jb      loc_18003D085
0x18003cf55  mov     edx, 6Eh ; 'n'
0x18003cf5a  jmp     loc_18003D079
0x18003cf5f  lea     r9, Name; "IPNAT"
0x18003cf66  xor     r8d, r8d; bInitialState
0x18003cf69  xor     edx, edx; bManualReset
0x18003cf6b  xor     ecx, ecx; lpEventAttributes
0x18003cf6d  call    cs:__imp_CreateEventA
0x18003cf74  nop     dword ptr [rax+rax+00h]
0x18003cf79  mov     cs:?NhpComponentEvent@@3PEAXEA, rax; void * NhpComponentEvent
0x18003cf80  call    cs:__imp_GetLastError
0x18003cf87  nop     dword ptr [rax+rax+00h]
0x18003cf8c  mov     rcx, cs:?NhpComponentEvent@@3PEAXEA; hObject
0x18003cf93  mov     edi, eax
0x18003cf95  test    rcx, rcx
0x18003cf98  jnz     short loc_18003D004
0x18003cf9a  mov     rcx, r12; lpCriticalSection
0x18003cf9d  call    cs:__imp_LeaveCriticalSection
0x18003cfa4  nop     dword ptr [rax+rax+00h]
0x18003cfa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfb0  cmp     rcx, rbp
0x18003cfb3  jz      loc_18003D085
0x18003cfb9  test    byte ptr [rcx+1Ch], 8
0x18003cfbd  jz      short loc_18003CFE0
0x18003cfbf  cmp     byte ptr [rcx+19h], 2
0x18003cfc3  jb      short loc_18003CFE0
0x18003cfc5  mov     rcx, [rcx+10h]
0x18003cfc9  mov     edx, 6Fh ; 'o'
0x18003cfce  mov     r9d, edi
0x18003cfd1  mov     r8, r14
0x18003cfd4  call    WPP_SF_d
0x18003cfd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cfe0  cmp     rcx, rbp
0x18003cfe3  jz      loc_18003D085
0x18003cfe9  test    byte ptr [rcx+1Ch], 8
0x18003cfed  jz      loc_18003D085
0x18003cff3  cmp     byte ptr [rcx+19h], 6
0x18003cff7  jb      loc_18003D085
0x18003cffd  mov     edx, 70h ; 'p'
0x18003d002  jmp     short loc_18003D079
0x18003d004  cmp     edi, 0B7h
0x18003d00a  jnz     short loc_18003D089
0x18003d00c  call    cs:__imp_CloseHandle
0x18003d013  nop     dword ptr [rax+rax+00h]
0x18003d018  mov     rcx, r12; lpCriticalSection
0x18003d01b  mov     cs:?NhpComponentEvent@@3PEAXEA, 0; void * NhpComponentEvent
0x18003d026  call    cs:__imp_LeaveCriticalSection
0x18003d02d  nop     dword ptr [rax+rax+00h]
0x18003d032  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d039  cmp     rcx, rbp
0x18003d03c  jz      short loc_18003D085
0x18003d03e  test    byte ptr [rcx+1Ch], 8
0x18003d042  jz      short loc_18003D063
0x18003d044  cmp     byte ptr [rcx+19h], 2
0x18003d048  jb      short loc_18003D063
0x18003d04a  mov     rcx, [rcx+10h]
0x18003d04e  lea     edx, [rdi-46h]
0x18003d051  mov     r9d, edi
0x18003d054  mov     r8, r14
0x18003d057  call    WPP_SF_d
0x18003d05c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d063  cmp     rcx, rbp
0x18003d066  jz      short loc_18003D085
0x18003d068  test    byte ptr [rcx+1Ch], 8
0x18003d06c  jz      short loc_18003D085
0x18003d06e  cmp     byte ptr [rcx+19h], 6
0x18003d072  jb      short loc_18003D085
0x18003d074  mov     edx, 72h ; 'r'
0x18003d079  mov     rcx, [rcx+10h]
0x18003d07d  mov     r8, r14
0x18003d080  call    WPP_SF_
0x18003d085  xor     al, al
0x18003d087  jmp     short loc_18003D0C9
0x18003d089  mov     rcx, r12; lpCriticalSection
0x18003d08c  mov     cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A, ebx; NH_COMPONENT_MODE NhComponentMode
0x18003d092  call    cs:__imp_LeaveCriticalSection
0x18003d099  nop     dword ptr [rax+rax+00h]
0x18003d09e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d0a5  cmp     rcx, rbp
0x18003d0a8  jz      short loc_18003D0C7
0x18003d0aa  test    byte ptr [rcx+1Ch], 8
0x18003d0ae  jz      short loc_18003D0C7
0x18003d0b0  cmp     byte ptr [rcx+19h], 6
0x18003d0b4  jb      short loc_18003D0C7
0x18003d0b6  mov     rcx, [rcx+10h]
0x18003d0ba  mov     edx, 73h ; 's'
0x18003d0bf  mov     r8, r14
0x18003d0c2  call    WPP_SF_
0x18003d0c7  mov     al, 1
0x18003d0c9  add     rsp, 30h
0x18003d0cd  pop     r14
0x18003d0cf  pop     r12
0x18003d0d1  pop     rdi
0x18003d0d2  pop     rbp
0x18003d0d3  pop     rbx
0x18003d0d4  retn
```
