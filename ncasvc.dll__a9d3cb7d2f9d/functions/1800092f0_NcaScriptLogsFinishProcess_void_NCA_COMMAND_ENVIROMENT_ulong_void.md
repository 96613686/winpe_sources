# NcaScriptLogsFinishProcess(void *,NCA_COMMAND_ENVIROMENT_ *,ulong,void *)

- ea: `0x1800092f0`
- end: `0x180009666`
- name: `?NcaScriptLogsFinishProcess@@YAKPEAXPEAUNCA_COMMAND_ENVIROMENT_@@K0@Z`
- size: `886`
- prototype: `__int64 __fastcall(void *, struct NCA_COMMAND_ENVIROMENT_ *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a398`

## callees

- `0x180004f34`
- `0x180008ee8`
- `0x1800092f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000957e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800094e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000957e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009613`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800093a0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800093db`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009413`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009449`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009481`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800094ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800093a0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800093db`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009413`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009449`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180009481`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800094ca`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180009320`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180009320`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsFinishProcess(void *a1, struct NCA_COMMAND_ENVIROMENT_ *a2, unsigned int a3, void *a4)
{
  unsigned int LastError; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int i; // edi
  __int64 v12; // r8
  __int64 v13; // r8
  _WORD *v14; // rdx
  __int64 v15; // r8
  _WORD *v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-58h] BYREF

  NumberOfBytesWritten = 0;
  LastError = SetFilePointer(a4, 0, 0, 0);
  if ( LastError == -1 )
  {
    LastError = GetLastError();
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 59;
LABEL_48:
      WPP_SF_d(v9[2], v10, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, LastError);
    }
  }
  else
  {
    for ( i = 0; i < a3; ++i )
    {
      v12 = -1;
      do
        ++v12;
      while ( *((_WORD *)wszNcaScriptLogProcessStatus + v12) );
      if ( !WriteFile(a1, wszNcaScriptLogProcessStatus, 2 * v12, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 60;
          goto LABEL_48;
        }
        return LastError;
      }
      v13 = -1;
      v14 = (_WORD *)*((_QWORD *)a2 + 3 * i);
      do
        ++v13;
      while ( v14[v13] );
      if ( !WriteFile(a1, v14, 2 * v13, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 61;
          goto LABEL_48;
        }
        return LastError;
      }
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)lpBuffer + v15) );
      if ( !WriteFile(a1, lpBuffer, 2 * v15, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 62;
          goto LABEL_48;
        }
        return LastError;
      }
      v16 = (_WORD *)*((_QWORD *)a2 + 3 * i + 1);
      v17 = -1;
      do
        ++v17;
      while ( v16[v17] );
      if ( !WriteFile(a1, v16, 2 * v17, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 63;
          goto LABEL_48;
        }
        return LastError;
      }
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)qword_180029638 + v18) );
      if ( !WriteFile(a1, qword_180029638, 2 * v18, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 64;
          goto LABEL_48;
        }
        return LastError;
      }
      LastError = NcaScriptLogsCopyOutput(a1, a4);
      if ( LastError )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 65;
          goto LABEL_48;
        }
        return LastError;
      }
      v19 = -1;
      do
        ++v19;
      while ( *((_WORD *)qword_180029640 + v19) );
      if ( !WriteFile(a1, qword_180029640, 2 * v19, &NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 66;
          goto LABEL_48;
        }
        return LastError;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800092f0  push    rbx
0x1800092f2  push    rbp
0x1800092f3  push    rsi
0x1800092f4  push    rdi
0x1800092f5  push    r12
0x1800092f7  push    r13
0x1800092f9  push    r14
0x1800092fb  push    r15
0x1800092fd  sub     rsp, 48h
0x180009301  mov     rbp, r9
0x180009304  mov     r15d, r8d
0x180009307  mov     r14, rdx
0x18000930a  mov     rsi, rcx
0x18000930d  xor     r12d, r12d
0x180009310  mov     rcx, rbp; hFile
0x180009313  xor     r9d, r9d; dwMoveMethod
0x180009316  mov     [rsp+88h+NumberOfBytesWritten], r12d
0x18000931b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000931e  xor     edx, edx; lDistanceToMove
0x180009320  call    cs:__imp_SetFilePointer
0x180009327  nop     dword ptr [rax+rax+00h]
0x18000932c  mov     ebx, eax
0x18000932e  cmp     eax, 0FFFFFFFFh
0x180009331  jnz     short loc_18000936C
0x180009333  call    cs:__imp_GetLastError
0x18000933a  nop     dword ptr [rax+rax+00h]
0x18000933f  mov     ebx, eax
0x180009341  mov     rcx, cs:WPP_GLOBAL_Control
0x180009348  lea     rax, WPP_GLOBAL_Control
0x18000934f  cmp     rcx, rax
0x180009352  jz      loc_180009652
0x180009358  test    byte ptr [rcx+1Ch], 1
0x18000935c  jz      loc_180009652
0x180009362  lea     edx, [r12+3Bh]
0x180009367  jmp     loc_18000963F
0x18000936c  mov     edi, r12d
0x18000936f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180009373  cmp     edi, r15d
0x180009376  jnb     loc_180009652
0x18000937c  mov     rdx, cs:?wszNcaScriptLogProcessStatus@@3PAPEAGA; lpBuffer
0x180009383  mov     r8, r13
0x180009386  inc     r8
0x180009389  cmp     [rdx+r8*2], r12w
0x18000938e  jnz     short loc_180009386
0x180009390  add     r8d, r8d; nNumberOfBytesToWrite
0x180009393  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x180009398  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000939d  mov     rcx, rsi; hFile
0x1800093a0  call    cs:__imp_WriteFile
0x1800093a7  nop     dword ptr [rax+rax+00h]
0x1800093ac  test    eax, eax
0x1800093ae  jz      loc_180009613
0x1800093b4  mov     eax, edi
0x1800093b6  mov     r8, r13
0x1800093b9  lea     rbx, [rax+rax*2]
0x1800093bd  mov     rdx, [r14+rbx*8]; lpBuffer
0x1800093c1  inc     r8
0x1800093c4  cmp     [rdx+r8*2], r12w
0x1800093c9  jnz     short loc_1800093C1
0x1800093cb  add     r8d, r8d; nNumberOfBytesToWrite
0x1800093ce  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x1800093d3  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800093d8  mov     rcx, rsi; hFile
0x1800093db  call    cs:__imp_WriteFile
0x1800093e2  nop     dword ptr [rax+rax+00h]
0x1800093e7  test    eax, eax
0x1800093e9  jz      loc_1800095E5
0x1800093ef  mov     rdx, cs:lpBuffer; lpBuffer
0x1800093f6  mov     r8, r13
0x1800093f9  inc     r8
0x1800093fc  cmp     [rdx+r8*2], r12w
0x180009401  jnz     short loc_1800093F9
0x180009403  add     r8d, r8d; nNumberOfBytesToWrite
0x180009406  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x18000940b  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180009410  mov     rcx, rsi; hFile
0x180009413  call    cs:__imp_WriteFile
0x18000941a  nop     dword ptr [rax+rax+00h]
0x18000941f  test    eax, eax
0x180009421  jz      loc_1800095B7
0x180009427  mov     rdx, [r14+rbx*8+8]; lpBuffer
0x18000942c  mov     r8, r13
0x18000942f  inc     r8
0x180009432  cmp     [rdx+r8*2], r12w
0x180009437  jnz     short loc_18000942F
0x180009439  add     r8d, r8d; nNumberOfBytesToWrite
0x18000943c  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x180009441  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180009446  mov     rcx, rsi; hFile
0x180009449  call    cs:__imp_WriteFile
0x180009450  nop     dword ptr [rax+rax+00h]
0x180009455  test    eax, eax
0x180009457  jz      loc_18000957E
0x18000945d  mov     rdx, cs:qword_180029638; lpBuffer
0x180009464  mov     r8, r13
0x180009467  inc     r8
0x18000946a  cmp     [rdx+r8*2], r12w
0x18000946f  jnz     short loc_180009467
0x180009471  add     r8d, r8d; nNumberOfBytesToWrite
0x180009474  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x180009479  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000947e  mov     rcx, rsi; hFile
0x180009481  call    cs:__imp_WriteFile
0x180009488  nop     dword ptr [rax+rax+00h]
0x18000948d  test    eax, eax
0x18000948f  jz      loc_180009545
0x180009495  mov     rdx, rbp; void *
0x180009498  mov     rcx, rsi; void *
0x18000949b  call    ?NcaScriptLogsCopyOutput@@YAKPEAX0@Z; NcaScriptLogsCopyOutput(void *,void *)
0x1800094a0  mov     ebx, eax
0x1800094a2  test    eax, eax
0x1800094a4  jnz     short loc_18000951A
0x1800094a6  mov     rdx, cs:qword_180029640; lpBuffer
0x1800094ad  mov     r8, r13
0x1800094b0  inc     r8
0x1800094b3  cmp     [rdx+r8*2], r12w
0x1800094b8  jnz     short loc_1800094B0
0x1800094ba  add     r8d, r8d; nNumberOfBytesToWrite
0x1800094bd  mov     [rsp+88h+lpOverlapped], r12; lpOverlapped
0x1800094c2  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800094c7  mov     rcx, rsi; hFile
0x1800094ca  call    cs:__imp_WriteFile
0x1800094d1  nop     dword ptr [rax+rax+00h]
0x1800094d6  test    eax, eax
0x1800094d8  jz      short loc_1800094E1
0x1800094da  inc     edi
0x1800094dc  jmp     loc_180009373
0x1800094e1  call    cs:__imp_GetLastError
0x1800094e8  nop     dword ptr [rax+rax+00h]
0x1800094ed  mov     ebx, eax
0x1800094ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094f6  lea     rax, WPP_GLOBAL_Control
0x1800094fd  cmp     rcx, rax
0x180009500  jz      loc_180009652
0x180009506  test    byte ptr [rcx+1Ch], 1
0x18000950a  jz      loc_180009652
0x180009510  mov     edx, 42h ; 'B'
0x180009515  jmp     loc_18000963F
0x18000951a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009521  lea     rax, WPP_GLOBAL_Control
0x180009528  cmp     rcx, rax
0x18000952b  jz      loc_180009652
0x180009531  test    byte ptr [rcx+1Ch], 1
0x180009535  jz      loc_180009652
0x18000953b  mov     edx, 41h ; 'A'
0x180009540  jmp     loc_18000963F
0x180009545  call    cs:__imp_GetLastError
0x18000954c  nop     dword ptr [rax+rax+00h]
0x180009551  mov     ebx, eax
0x180009553  mov     rcx, cs:WPP_GLOBAL_Control
0x18000955a  lea     rax, WPP_GLOBAL_Control
0x180009561  cmp     rcx, rax
0x180009564  jz      loc_180009652
0x18000956a  test    byte ptr [rcx+1Ch], 1
0x18000956e  jz      loc_180009652
0x180009574  mov     edx, 40h ; '@'
0x180009579  jmp     loc_18000963F
0x18000957e  call    cs:__imp_GetLastError
0x180009585  nop     dword ptr [rax+rax+00h]
0x18000958a  mov     ebx, eax
0x18000958c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009593  lea     rax, WPP_GLOBAL_Control
0x18000959a  cmp     rcx, rax
0x18000959d  jz      loc_180009652
0x1800095a3  test    byte ptr [rcx+1Ch], 1
0x1800095a7  jz      loc_180009652
0x1800095ad  mov     edx, 3Fh ; '?'
0x1800095b2  jmp     loc_18000963F
0x1800095b7  call    cs:__imp_GetLastError
0x1800095be  nop     dword ptr [rax+rax+00h]
0x1800095c3  mov     ebx, eax
0x1800095c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095cc  lea     rax, WPP_GLOBAL_Control
0x1800095d3  cmp     rcx, rax
0x1800095d6  jz      short loc_180009652
0x1800095d8  test    byte ptr [rcx+1Ch], 1
0x1800095dc  jz      short loc_180009652
0x1800095de  mov     edx, 3Eh ; '>'
0x1800095e3  jmp     short loc_18000963F
0x1800095e5  call    cs:__imp_GetLastError
0x1800095ec  nop     dword ptr [rax+rax+00h]
0x1800095f1  mov     ebx, eax
0x1800095f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095fa  lea     rax, WPP_GLOBAL_Control
0x180009601  cmp     rcx, rax
0x180009604  jz      short loc_180009652
0x180009606  test    byte ptr [rcx+1Ch], 1
0x18000960a  jz      short loc_180009652
0x18000960c  mov     edx, 3Dh ; '='
0x180009611  jmp     short loc_18000963F
0x180009613  call    cs:__imp_GetLastError
0x18000961a  nop     dword ptr [rax+rax+00h]
0x18000961f  mov     ebx, eax
0x180009621  mov     rcx, cs:WPP_GLOBAL_Control
0x180009628  lea     rax, WPP_GLOBAL_Control
0x18000962f  cmp     rcx, rax
0x180009632  jz      short loc_180009652
0x180009634  test    byte ptr [rcx+1Ch], 1
0x180009638  jz      short loc_180009652
0x18000963a  mov     edx, 3Ch ; '<'
0x18000963f  mov     rcx, [rcx+10h]
0x180009643  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000964a  mov     r9d, ebx
0x18000964d  call    WPP_SF_d
0x180009652  mov     eax, ebx
0x180009654  add     rsp, 48h
0x180009658  pop     r15
0x18000965a  pop     r14
0x18000965c  pop     r13
0x18000965e  pop     r12
0x180009660  pop     rdi
0x180009661  pop     rsi
0x180009662  pop     rbp
0x180009663  pop     rbx
0x180009664  retn
```
