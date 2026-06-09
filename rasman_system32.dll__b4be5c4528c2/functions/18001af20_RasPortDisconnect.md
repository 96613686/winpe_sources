# RasPortDisconnect

- ea: `0x18001af20`
- end: `0x18001b120`
- name: `RasPortDisconnect`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800179f0`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001af20`
- `0x180021b14`
- `0x1800225a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b08a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b08a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001afd0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001afd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b02a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b02a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b0d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afe4`

## pseudocode

```c
__int64 __fastcall RasPortDisconnect(__int64 a1, void *a2, __int64 a3)
{
  HANDLE EventA; // rdi
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // esi
  DWORD LastError; // eax
  DWORD CurrentProcessId; // eax
  DWORD v12; // ebp
  unsigned int v13; // eax

  EventA = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, a3, a1, a2);
  }
  if ( (unsigned int)ValidatePortHandle(a1) )
  {
    if ( EventA == (HANDLE)-1LL )
    {
      v9 = 1;
      EventA = CreateEventA(0, 1, 0, 0);
      if ( !EventA )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( !LastError )
          goto LABEL_34;
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v5;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_35;
        v7 = 141;
        v8 = LastError;
LABEL_10:
        WPP_SF_d(v6[2], v7, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
LABEL_34:
        v6 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_35;
      }
    }
    else
    {
      v9 = 0;
    }
    CurrentProcessId = GetCurrentProcessId();
    v12 = CurrentProcessId;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
        CurrentProcessId);
    }
    v13 = SubmitLocalRequest(9u, a1, EventA, v12);
    v5 = v13;
    if ( v9 && v13 == 600 )
    {
      WaitForSingleObject(EventA, 0xFFFFFFFF);
      v5 = 0;
      goto LABEL_33;
    }
    if ( v13 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_32:
        if ( !v9 )
          goto LABEL_35;
LABEL_33:
        CloseHandle(EventA);
        goto LABEL_34;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v13);
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_32;
  }
  v5 = 601;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 140;
    v8 = 601;
    goto LABEL_10;
  }
LABEL_35:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    WPP_SF_d(v6[2], 144, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001af20  push    rbx
0x18001af22  push    rbp
0x18001af23  push    rsi
0x18001af24  push    rdi
0x18001af25  push    r12
0x18001af27  push    r15
0x18001af29  sub     rsp, 38h
0x18001af2d  mov     rdi, rdx
0x18001af30  mov     rbx, rcx
0x18001af33  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af3a  lea     r15, WPP_GLOBAL_Control
0x18001af41  cmp     rcx, r15
0x18001af44  jz      short loc_18001AF68
0x18001af46  test    byte ptr [rcx+1Ch], 40h
0x18001af4a  jz      short loc_18001AF68
0x18001af4c  cmp     byte ptr [rcx+19h], 6
0x18001af50  jb      short loc_18001AF68
0x18001af52  mov     rcx, [rcx+10h]
0x18001af56  mov     edx, 8Bh
0x18001af5b  mov     r9, rbx
0x18001af5e  mov     [rsp+68h+var_48], rdi
0x18001af63  call    WPP_SF_qq
0x18001af68  mov     rcx, rbx
0x18001af6b  call    ValidatePortHandle
0x18001af70  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001af77  test    eax, eax
0x18001af79  jnz     short loc_18001AFBD
0x18001af7b  mov     ebx, 259h
0x18001af80  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af87  cmp     rcx, r15
0x18001af8a  jz      loc_18001B110
0x18001af90  test    byte ptr [rcx+1Ch], 40h
0x18001af94  jz      loc_18001B0EB
0x18001af9a  cmp     byte ptr [rcx+19h], 2
0x18001af9e  jb      loc_18001B0EB
0x18001afa4  mov     edx, 8Ch
0x18001afa9  mov     r9d, ebx
0x18001afac  mov     rcx, [rcx+10h]
0x18001afb0  mov     r8, r12
0x18001afb3  call    WPP_SF_d
0x18001afb8  jmp     loc_18001B0E4
0x18001afbd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001afc1  jnz     short loc_18001B028
0x18001afc3  lea     esi, [rdi+2]
0x18001afc6  xor     r9d, r9d; lpName
0x18001afc9  mov     edx, esi; bManualReset
0x18001afcb  xor     r8d, r8d; bInitialState
0x18001afce  xor     ecx, ecx; lpEventAttributes
0x18001afd0  call    cs:__imp_CreateEventA
0x18001afd7  nop     dword ptr [rax+rax+00h]
0x18001afdc  mov     rdi, rax
0x18001afdf  test    rax, rax
0x18001afe2  jnz     short loc_18001B02A
0x18001afe4  call    cs:__imp_GetLastError
0x18001afeb  nop     dword ptr [rax+rax+00h]
0x18001aff0  mov     ebx, eax
0x18001aff2  test    eax, eax
0x18001aff4  jz      loc_18001B0E4
0x18001affa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b001  cmp     rcx, r15
0x18001b004  jz      loc_18001B110
0x18001b00a  test    byte ptr [rcx+1Ch], 40h
0x18001b00e  jz      loc_18001B0EB
0x18001b014  cmp     byte ptr [rcx+19h], 2
0x18001b018  jb      loc_18001B0EB
0x18001b01e  mov     edx, 8Dh
0x18001b023  mov     r9d, eax
0x18001b026  jmp     short loc_18001AFAC
0x18001b028  xor     esi, esi
0x18001b02a  call    cs:__imp_GetCurrentProcessId
0x18001b031  nop     dword ptr [rax+rax+00h]
0x18001b036  mov     ebp, eax
0x18001b038  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b03f  cmp     rcx, r15
0x18001b042  jz      short loc_18001B064
0x18001b044  test    byte ptr [rcx+1Ch], 40h
0x18001b048  jz      short loc_18001B064
0x18001b04a  cmp     byte ptr [rcx+19h], 5
0x18001b04e  jb      short loc_18001B064
0x18001b050  mov     rcx, [rcx+10h]
0x18001b054  mov     edx, 8Eh
0x18001b059  mov     r9d, eax
0x18001b05c  mov     r8, r12
0x18001b05f  call    WPP_SF_d
0x18001b064  mov     ecx, 9
0x18001b069  mov     r9d, ebp
0x18001b06c  mov     r8, rdi
0x18001b06f  mov     rdx, rbx
0x18001b072  call    SubmitLocalRequest
0x18001b077  mov     ebx, eax
0x18001b079  test    esi, esi
0x18001b07b  jz      short loc_18001B09A
0x18001b07d  cmp     eax, 258h
0x18001b082  jnz     short loc_18001B09A
0x18001b084  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b087  mov     rcx, rdi; hHandle
0x18001b08a  call    cs:__imp_WaitForSingleObject
0x18001b091  nop     dword ptr [rax+rax+00h]
0x18001b096  xor     ebx, ebx
0x18001b098  jmp     short loc_18001B0D5
0x18001b09a  test    eax, eax
0x18001b09c  jz      short loc_18001B0CA
0x18001b09e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0a5  cmp     rcx, r15
0x18001b0a8  jz      short loc_18001B0D1
0x18001b0aa  test    byte ptr [rcx+1Ch], 40h
0x18001b0ae  jz      short loc_18001B0D1
0x18001b0b0  cmp     byte ptr [rcx+19h], 2
0x18001b0b4  jb      short loc_18001B0D1
0x18001b0b6  mov     rcx, [rcx+10h]
0x18001b0ba  mov     edx, 8Fh
0x18001b0bf  mov     r9d, eax
0x18001b0c2  mov     r8, r12
0x18001b0c5  call    WPP_SF_d
0x18001b0ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0d1  test    esi, esi
0x18001b0d3  jz      short loc_18001B0EB
0x18001b0d5  mov     rcx, rdi; hObject
0x18001b0d8  call    cs:__imp_CloseHandle
0x18001b0df  nop     dword ptr [rax+rax+00h]
0x18001b0e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0eb  cmp     rcx, r15
0x18001b0ee  jz      short loc_18001B110
0x18001b0f0  test    byte ptr [rcx+1Ch], 40h
0x18001b0f4  jz      short loc_18001B110
0x18001b0f6  cmp     byte ptr [rcx+19h], 6
0x18001b0fa  jb      short loc_18001B110
0x18001b0fc  mov     rcx, [rcx+10h]
0x18001b100  mov     edx, 90h
0x18001b105  mov     r9d, ebx
0x18001b108  mov     r8, r12
0x18001b10b  call    WPP_SF_d
0x18001b110  mov     eax, ebx
0x18001b112  add     rsp, 38h
0x18001b116  pop     r15
0x18001b118  pop     r12
0x18001b11a  pop     rdi
0x18001b11b  pop     rsi
0x18001b11c  pop     rbp
0x18001b11d  pop     rbx
0x18001b11e  retn
```
