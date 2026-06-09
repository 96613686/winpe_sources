# DllMainDetach

- ea: `0x180005660`
- end: `0x1800057e9`
- name: `DllMainDetach`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005000`
- `0x180005e60`

## callees

- `0x180005660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056d9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005714`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000575f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005783`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056d9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005714`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000575f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005783`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005679`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005679`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005776`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005776`
- `ntdll!EtwUnregisterTraceGuids` at `0x1800057b9`
- `ntdll!EtwUnregisterTraceGuids` at `0x1800057b9`

## pseudocode

```c
void __fastcall DllMainDetach(_BYTE *a1)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  _QWORD *v7; // rbx

  if ( (!a1 || (*a1 & 0x10) != 0) && (EnterCriticalSection(&g_csInitilization), !a1) || (*a1 & 8) != 0 )
  {
    v2 = CscUmpLibraryState;
    if ( CscUmpLibraryState )
    {
      --CscUmpLibraryState;
      if ( v2 == 1 )
      {
        v3 = dword_18000E990;
        if ( dword_18000E990 )
        {
          --dword_18000E990;
          if ( v3 == 1 )
            DeleteCriticalSection(&CriticalSection);
        }
      }
    }
    if ( !a1 )
      goto LABEL_19;
  }
  if ( (*a1 & 4) != 0 )
  {
LABEL_19:
    if ( _InterlockedExchangeAdd(&dword_18000E984, 0xFFFFFFFF) == 1 )
    {
      v4 = dword_18000E990;
      if ( dword_18000E990 )
      {
        --dword_18000E990;
        if ( v4 == 1 )
          DeleteCriticalSection(&CriticalSection);
      }
    }
    if ( !a1 )
      goto LABEL_26;
  }
  if ( (*a1 & 2) != 0 )
  {
LABEL_26:
    if ( _InterlockedExchangeAdd(&dword_18000E980, 0xFFFFFFFF) == 1 )
    {
      v5 = CscUmpLibraryState;
      if ( CscUmpLibraryState )
      {
        --CscUmpLibraryState;
        if ( v5 == 1 )
        {
          v6 = dword_18000E990;
          if ( dword_18000E990 )
          {
            --dword_18000E990;
            if ( v6 == 1 )
              DeleteCriticalSection(&CriticalSection);
          }
        }
      }
    }
    if ( !a1 )
      goto LABEL_40;
  }
  if ( (*a1 & 0x10) != 0 )
  {
LABEL_40:
    LeaveCriticalSection(&g_csInitilization);
    DeleteCriticalSection(&g_csInitilization);
    if ( !a1 )
      goto LABEL_29;
  }
  if ( (*a1 & 1) != 0 )
  {
LABEL_29:
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( WPP_GLOBAL_Control )
      {
        do
        {
          if ( v7[1] )
          {
            EtwUnregisterTraceGuids();
            v7[1] = 0;
          }
          v7 = (_QWORD *)*v7;
        }
        while ( v7 );
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
}

```

## disassembly

```asm
0x180005660  mov     [rsp+arg_10], rbx
0x180005665  push    rdi
0x180005666  sub     rsp, 20h
0x18000566a  mov     rbx, rcx
0x18000566d  test    rcx, rcx
0x180005670  jnz     short loc_1800056A1
0x180005672  lea     rcx, g_csInitilization; lpCriticalSection
0x180005679  call    cs:__imp_EnterCriticalSection
0x18000567f  test    rbx, rbx
0x180005682  jz      short loc_1800056A8
0x180005684  test    byte ptr [rbx], 8
0x180005687  jnz     short loc_1800056A8
0x180005689  test    byte ptr [rbx], 4
0x18000568c  jnz     short loc_1800056E4
0x18000568e  mov     edi, 0FFFFFFFFh
0x180005693  test    byte ptr [rbx], 2
0x180005696  jz      loc_18000576A
0x18000569c  jmp     loc_180005723
0x1800056a1  test    byte ptr [rcx], 10h
0x1800056a4  jz      short loc_180005684
0x1800056a6  jmp     short loc_180005672
0x1800056a8  mov     eax, cs:CscUmpLibraryState
0x1800056ae  test    eax, eax
0x1800056b0  jz      short loc_1800056DF
0x1800056b2  sub     eax, 1
0x1800056b5  mov     cs:CscUmpLibraryState, eax
0x1800056bb  jnz     short loc_1800056DF
0x1800056bd  mov     eax, cs:dword_18000E990
0x1800056c3  test    eax, eax
0x1800056c5  jz      short loc_1800056DF
0x1800056c7  sub     eax, 1
0x1800056ca  mov     cs:dword_18000E990, eax
0x1800056d0  jnz     short loc_1800056DF
0x1800056d2  lea     rcx, CriticalSection; lpCriticalSection
0x1800056d9  call    cs:__imp_DeleteCriticalSection
0x1800056df  test    rbx, rbx
0x1800056e2  jnz     short loc_180005689
0x1800056e4  mov     edi, 0FFFFFFFFh
0x1800056e9  mov     eax, edi
0x1800056eb  lock xadd cs:dword_18000E984, eax
0x1800056f3  cmp     eax, 1
0x1800056f6  jnz     short loc_18000571A
0x1800056f8  mov     eax, cs:dword_18000E990
0x1800056fe  test    eax, eax
0x180005700  jz      short loc_18000571A
0x180005702  sub     eax, 1
0x180005705  mov     cs:dword_18000E990, eax
0x18000570b  jnz     short loc_18000571A
0x18000570d  lea     rcx, CriticalSection; lpCriticalSection
0x180005714  call    cs:__imp_DeleteCriticalSection
0x18000571a  test    rbx, rbx
0x18000571d  jnz     loc_180005693
0x180005723  lock xadd cs:dword_18000E980, edi
0x18000572b  cmp     edi, 1
0x18000572e  jnz     short loc_180005765
0x180005730  mov     eax, cs:CscUmpLibraryState
0x180005736  test    eax, eax
0x180005738  jz      short loc_180005765
0x18000573a  sub     eax, edi
0x18000573c  mov     cs:CscUmpLibraryState, eax
0x180005742  jnz     short loc_180005765
0x180005744  mov     eax, cs:dword_18000E990
0x18000574a  test    eax, eax
0x18000574c  jz      short loc_180005765
0x18000574e  sub     eax, edi
0x180005750  mov     cs:dword_18000E990, eax
0x180005756  jnz     short loc_180005765
0x180005758  lea     rcx, CriticalSection; lpCriticalSection
0x18000575f  call    cs:__imp_DeleteCriticalSection
0x180005765  test    rbx, rbx
0x180005768  jz      short loc_18000576F
0x18000576a  test    byte ptr [rbx], 10h
0x18000576d  jz      short loc_1800057E2
0x18000576f  lea     rcx, g_csInitilization; lpCriticalSection
0x180005776  call    cs:__imp_LeaveCriticalSection
0x18000577c  lea     rcx, g_csInitilization; lpCriticalSection
0x180005783  call    cs:__imp_DeleteCriticalSection
0x180005789  test    rbx, rbx
0x18000578c  jnz     short loc_1800057E2
0x18000578e  mov     rbx, cs:WPP_GLOBAL_Control
0x180005795  mov     [rsp+28h+arg_8], rsi
0x18000579a  lea     rsi, WPP_GLOBAL_Control
0x1800057a1  cmp     rbx, rsi
0x1800057a4  jz      short loc_1800057D2
0x1800057a6  test    rbx, rbx
0x1800057a9  jz      short loc_1800057CB
0x1800057ab  xor     edi, edi
0x1800057ad  nop     dword ptr [rax]
0x1800057b0  mov     rcx, [rbx+8]
0x1800057b4  test    rcx, rcx
0x1800057b7  jz      short loc_1800057C3
0x1800057b9  call    cs:__imp_EtwUnregisterTraceGuids
0x1800057bf  mov     [rbx+8], rdi
0x1800057c3  mov     rbx, [rbx]
0x1800057c6  test    rbx, rbx
0x1800057c9  jnz     short loc_1800057B0
0x1800057cb  mov     cs:WPP_GLOBAL_Control, rsi
0x1800057d2  mov     rsi, [rsp+28h+arg_8]
0x1800057d7  mov     rbx, [rsp+28h+arg_10]
0x1800057dc  add     rsp, 20h
0x1800057e0  pop     rdi
0x1800057e1  retn
0x1800057e2  test    byte ptr [rbx], 1
0x1800057e5  jz      short loc_1800057D7
0x1800057e7  jmp     short loc_18000578E
```
