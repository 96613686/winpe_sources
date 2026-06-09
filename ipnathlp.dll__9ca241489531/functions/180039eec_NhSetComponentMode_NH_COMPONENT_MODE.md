# NhSetComponentMode(NH_COMPONENT_MODE)

- ea: `0x180039eec`
- end: `0x18003a119`
- name: `?NhSetComponentMode@@YAEW4NH_COMPONENT_MODE@@@Z`
- size: `557`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003dc2c`
- `0x1800539c0`
- `0x18006e294`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180012730`
- `0x180039eec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039f3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039f3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039f5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ffd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a0dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039f5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ffd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a0dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180039fd9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180039fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039fe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a062`

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
0x180039eec  push    rbx
0x180039eee  push    rbp
0x180039eef  push    rdi
0x180039ef0  push    r12
0x180039ef2  push    r14
0x180039ef4  sub     rsp, 30h
0x180039ef8  mov     ebx, ecx
0x180039efa  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f01  lea     rbp, WPP_GLOBAL_Control
0x180039f08  lea     r14, WPP_1aaa4111f34f303c0aa2c26dd507e416_Traceguids
0x180039f0f  cmp     rcx, rbp
0x180039f12  jz      short loc_180039F34
0x180039f14  test    byte ptr [rcx+1Ch], 8
0x180039f18  jz      short loc_180039F34
0x180039f1a  cmp     byte ptr [rcx+19h], 6
0x180039f1e  jb      short loc_180039F34
0x180039f20  mov     rcx, [rcx+10h]
0x180039f24  mov     edx, 6Ch ; 'l'
0x180039f29  mov     r9d, ebx
0x180039f2c  mov     r8, r14
0x180039f2f  call    WPP_SF_d
0x180039f34  lea     r12, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION NhLock
0x180039f3b  mov     rcx, r12; lpCriticalSection
0x180039f3e  call    cs:__imp_EnterCriticalSection
0x180039f44  cmp     cs:?NhpComponentEvent@@3PEAXEA, 0; void * NhpComponentEvent
0x180039f4c  jz      short loc_180039FCB
0x180039f4e  cmp     cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A, ebx; NH_COMPONENT_MODE NhComponentMode
0x180039f54  jz      loc_18003A0D3
0x180039f5a  mov     rcx, r12; lpCriticalSection
0x180039f5d  call    cs:__imp_LeaveCriticalSection
0x180039f63  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f6a  cmp     rcx, rbp
0x180039f6d  jz      loc_18003A0CF
0x180039f73  test    byte ptr [rcx+1Ch], 8
0x180039f77  jz      short loc_180039FA4
0x180039f79  cmp     byte ptr [rcx+19h], 2
0x180039f7d  jb      short loc_180039FA4
0x180039f7f  mov     eax, cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A; NH_COMPONENT_MODE NhComponentMode
0x180039f85  mov     edx, 6Dh ; 'm'
0x180039f8a  mov     rcx, [rcx+10h]
0x180039f8e  mov     r9d, ebx
0x180039f91  mov     r8, r14
0x180039f94  mov     [rsp+58h+var_38], eax
0x180039f98  call    WPP_SF_dd
0x180039f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039fa4  cmp     rcx, rbp
0x180039fa7  jz      loc_18003A0CF
0x180039fad  test    byte ptr [rcx+1Ch], 8
0x180039fb1  jz      loc_18003A0CF
0x180039fb7  cmp     byte ptr [rcx+19h], 6
0x180039fbb  jb      loc_18003A0CF
0x180039fc1  mov     edx, 6Eh ; 'n'
0x180039fc6  jmp     loc_18003A0C3
0x180039fcb  lea     r9, Name; "IPNAT"
0x180039fd2  xor     r8d, r8d; bInitialState
0x180039fd5  xor     edx, edx; bManualReset
0x180039fd7  xor     ecx, ecx; lpEventAttributes
0x180039fd9  call    cs:__imp_CreateEventA
0x180039fdf  mov     cs:?NhpComponentEvent@@3PEAXEA, rax; void * NhpComponentEvent
0x180039fe6  call    cs:__imp_GetLastError
0x180039fec  mov     rcx, cs:?NhpComponentEvent@@3PEAXEA; hObject
0x180039ff3  mov     edi, eax
0x180039ff5  test    rcx, rcx
0x180039ff8  jnz     short loc_18003A05A
0x180039ffa  mov     rcx, r12; lpCriticalSection
0x180039ffd  call    cs:__imp_LeaveCriticalSection
0x18003a003  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a00a  cmp     rcx, rbp
0x18003a00d  jz      loc_18003A0CF
0x18003a013  test    byte ptr [rcx+1Ch], 8
0x18003a017  jz      short loc_18003A03A
0x18003a019  cmp     byte ptr [rcx+19h], 2
0x18003a01d  jb      short loc_18003A03A
0x18003a01f  mov     rcx, [rcx+10h]
0x18003a023  mov     edx, 6Fh ; 'o'
0x18003a028  mov     r9d, edi
0x18003a02b  mov     r8, r14
0x18003a02e  call    WPP_SF_d
0x18003a033  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a03a  cmp     rcx, rbp
0x18003a03d  jz      loc_18003A0CF
0x18003a043  test    byte ptr [rcx+1Ch], 8
0x18003a047  jz      loc_18003A0CF
0x18003a04d  cmp     byte ptr [rcx+19h], 6
0x18003a051  jb      short loc_18003A0CF
0x18003a053  mov     edx, 70h ; 'p'
0x18003a058  jmp     short loc_18003A0C3
0x18003a05a  cmp     edi, 0B7h
0x18003a060  jnz     short loc_18003A0D3
0x18003a062  call    cs:__imp_CloseHandle
0x18003a068  mov     rcx, r12; lpCriticalSection
0x18003a06b  mov     cs:?NhpComponentEvent@@3PEAXEA, 0; void * NhpComponentEvent
0x18003a076  call    cs:__imp_LeaveCriticalSection
0x18003a07c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a083  cmp     rcx, rbp
0x18003a086  jz      short loc_18003A0CF
0x18003a088  test    byte ptr [rcx+1Ch], 8
0x18003a08c  jz      short loc_18003A0AD
0x18003a08e  cmp     byte ptr [rcx+19h], 2
0x18003a092  jb      short loc_18003A0AD
0x18003a094  mov     rcx, [rcx+10h]
0x18003a098  lea     edx, [rdi-46h]
0x18003a09b  mov     r9d, edi
0x18003a09e  mov     r8, r14
0x18003a0a1  call    WPP_SF_d
0x18003a0a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0ad  cmp     rcx, rbp
0x18003a0b0  jz      short loc_18003A0CF
0x18003a0b2  test    byte ptr [rcx+1Ch], 8
0x18003a0b6  jz      short loc_18003A0CF
0x18003a0b8  cmp     byte ptr [rcx+19h], 6
0x18003a0bc  jb      short loc_18003A0CF
0x18003a0be  mov     edx, 72h ; 'r'
0x18003a0c3  mov     rcx, [rcx+10h]
0x18003a0c7  mov     r8, r14
0x18003a0ca  call    WPP_SF_
0x18003a0cf  xor     al, al
0x18003a0d1  jmp     short loc_18003A10D
0x18003a0d3  mov     rcx, r12; lpCriticalSection
0x18003a0d6  mov     cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A, ebx; NH_COMPONENT_MODE NhComponentMode
0x18003a0dc  call    cs:__imp_LeaveCriticalSection
0x18003a0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a0e9  cmp     rcx, rbp
0x18003a0ec  jz      short loc_18003A10B
0x18003a0ee  test    byte ptr [rcx+1Ch], 8
0x18003a0f2  jz      short loc_18003A10B
0x18003a0f4  cmp     byte ptr [rcx+19h], 6
0x18003a0f8  jb      short loc_18003A10B
0x18003a0fa  mov     rcx, [rcx+10h]
0x18003a0fe  mov     edx, 73h ; 's'
0x18003a103  mov     r8, r14
0x18003a106  call    WPP_SF_
0x18003a10b  mov     al, 1
0x18003a10d  add     rsp, 30h
0x18003a111  pop     r14
0x18003a113  pop     r12
0x18003a115  pop     rdi
0x18003a116  pop     rbp
0x18003a117  pop     rbx
0x18003a118  retn
```
