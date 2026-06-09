# RasPortDisconnect

- ea: `0x18001a530`
- end: `0x18001a711`
- name: `RasPortDisconnect`
- size: `481`
- prototype: `__int64 __fastcall(__int64, void *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180017040`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001a530`
- `0x180021000`
- `0x1800219f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a688`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a688`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001a5e0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001a5e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a62e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a62e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a6d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5ee`

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
0x18001a530  push    rbx
0x18001a532  push    rbp
0x18001a533  push    rsi
0x18001a534  push    rdi
0x18001a535  push    r12
0x18001a537  push    r15
0x18001a539  sub     rsp, 38h
0x18001a53d  mov     rdi, rdx
0x18001a540  mov     rbx, rcx
0x18001a543  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a54a  lea     r15, WPP_GLOBAL_Control
0x18001a551  cmp     rcx, r15
0x18001a554  jz      short loc_18001A578
0x18001a556  test    byte ptr [rcx+1Ch], 40h
0x18001a55a  jz      short loc_18001A578
0x18001a55c  cmp     byte ptr [rcx+19h], 6
0x18001a560  jb      short loc_18001A578
0x18001a562  mov     rcx, [rcx+10h]
0x18001a566  mov     edx, 8Bh
0x18001a56b  mov     r9, rbx
0x18001a56e  mov     [rsp+68h+var_48], rdi
0x18001a573  call    WPP_SF_qq
0x18001a578  mov     rcx, rbx
0x18001a57b  call    ValidatePortHandle
0x18001a580  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001a587  test    eax, eax
0x18001a589  jnz     short loc_18001A5CD
0x18001a58b  mov     ebx, 259h
0x18001a590  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a597  cmp     rcx, r15
0x18001a59a  jz      loc_18001A702
0x18001a5a0  test    byte ptr [rcx+1Ch], 40h
0x18001a5a4  jz      loc_18001A6DD
0x18001a5aa  cmp     byte ptr [rcx+19h], 2
0x18001a5ae  jb      loc_18001A6DD
0x18001a5b4  mov     edx, 8Ch
0x18001a5b9  mov     r9d, ebx
0x18001a5bc  mov     rcx, [rcx+10h]
0x18001a5c0  mov     r8, r12
0x18001a5c3  call    WPP_SF_d
0x18001a5c8  jmp     loc_18001A6D6
0x18001a5cd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001a5d1  jnz     short loc_18001A62C
0x18001a5d3  lea     esi, [rdi+2]
0x18001a5d6  xor     r9d, r9d; lpName
0x18001a5d9  mov     edx, esi; bManualReset
0x18001a5db  xor     r8d, r8d; bInitialState
0x18001a5de  xor     ecx, ecx; lpEventAttributes
0x18001a5e0  call    cs:__imp_CreateEventA
0x18001a5e6  mov     rdi, rax
0x18001a5e9  test    rax, rax
0x18001a5ec  jnz     short loc_18001A62E
0x18001a5ee  call    cs:__imp_GetLastError
0x18001a5f4  mov     ebx, eax
0x18001a5f6  test    eax, eax
0x18001a5f8  jz      loc_18001A6D6
0x18001a5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a605  cmp     rcx, r15
0x18001a608  jz      loc_18001A702
0x18001a60e  test    byte ptr [rcx+1Ch], 40h
0x18001a612  jz      loc_18001A6DD
0x18001a618  cmp     byte ptr [rcx+19h], 2
0x18001a61c  jb      loc_18001A6DD
0x18001a622  mov     edx, 8Dh
0x18001a627  mov     r9d, eax
0x18001a62a  jmp     short loc_18001A5BC
0x18001a62c  xor     esi, esi
0x18001a62e  call    cs:__imp_GetCurrentProcessId
0x18001a634  mov     ebp, eax
0x18001a636  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a63d  cmp     rcx, r15
0x18001a640  jz      short loc_18001A662
0x18001a642  test    byte ptr [rcx+1Ch], 40h
0x18001a646  jz      short loc_18001A662
0x18001a648  cmp     byte ptr [rcx+19h], 5
0x18001a64c  jb      short loc_18001A662
0x18001a64e  mov     rcx, [rcx+10h]
0x18001a652  mov     edx, 8Eh
0x18001a657  mov     r9d, eax
0x18001a65a  mov     r8, r12
0x18001a65d  call    WPP_SF_d
0x18001a662  mov     ecx, 9
0x18001a667  mov     r9d, ebp
0x18001a66a  mov     r8, rdi
0x18001a66d  mov     rdx, rbx
0x18001a670  call    SubmitLocalRequest
0x18001a675  mov     ebx, eax
0x18001a677  test    esi, esi
0x18001a679  jz      short loc_18001A692
0x18001a67b  cmp     eax, 258h
0x18001a680  jnz     short loc_18001A692
0x18001a682  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001a685  mov     rcx, rdi; hHandle
0x18001a688  call    cs:__imp_WaitForSingleObject
0x18001a68e  xor     ebx, ebx
0x18001a690  jmp     short loc_18001A6CD
0x18001a692  test    eax, eax
0x18001a694  jz      short loc_18001A6C2
0x18001a696  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a69d  cmp     rcx, r15
0x18001a6a0  jz      short loc_18001A6C9
0x18001a6a2  test    byte ptr [rcx+1Ch], 40h
0x18001a6a6  jz      short loc_18001A6C9
0x18001a6a8  cmp     byte ptr [rcx+19h], 2
0x18001a6ac  jb      short loc_18001A6C9
0x18001a6ae  mov     rcx, [rcx+10h]
0x18001a6b2  mov     edx, 8Fh
0x18001a6b7  mov     r9d, eax
0x18001a6ba  mov     r8, r12
0x18001a6bd  call    WPP_SF_d
0x18001a6c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6c9  test    esi, esi
0x18001a6cb  jz      short loc_18001A6DD
0x18001a6cd  mov     rcx, rdi; hObject
0x18001a6d0  call    cs:__imp_CloseHandle
0x18001a6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6dd  cmp     rcx, r15
0x18001a6e0  jz      short loc_18001A702
0x18001a6e2  test    byte ptr [rcx+1Ch], 40h
0x18001a6e6  jz      short loc_18001A702
0x18001a6e8  cmp     byte ptr [rcx+19h], 6
0x18001a6ec  jb      short loc_18001A702
0x18001a6ee  mov     rcx, [rcx+10h]
0x18001a6f2  mov     edx, 90h
0x18001a6f7  mov     r9d, ebx
0x18001a6fa  mov     r8, r12
0x18001a6fd  call    WPP_SF_d
0x18001a702  mov     eax, ebx
0x18001a704  add     rsp, 38h
0x18001a708  pop     r15
0x18001a70a  pop     r12
0x18001a70c  pop     rdi
0x18001a70d  pop     rsi
0x18001a70e  pop     rbp
0x18001a70f  pop     rbx
0x18001a710  retn
```
