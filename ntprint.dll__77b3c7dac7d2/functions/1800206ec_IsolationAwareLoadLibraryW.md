# IsolationAwareLoadLibraryW

- ea: `0x1800206ec`
- end: `0x180020817`
- name: `IsolationAwareLoadLibraryW`
- size: `299`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180020820`
- `0x1800257a8`
- `0x18002bee0`
- `0x18002eea4`
- `0x18002f5a0`

## callees

- `0x1800206ec`
- `0x180023cac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002080c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039201`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002080c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020785`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002073b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002073b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800207c6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800207c6`
- `KERNEL32!ActivateActCtx` at `0x180020771`
- `KERNEL32!ActivateActCtx` at `0x180020771`
- `KERNEL32!DeactivateActCtx` at `0x180020800`
- `KERNEL32!DeactivateActCtx` at `0x1800391f5`
- `KERNEL32!DeactivateActCtx` at `0x180020800`
- `KERNEL32!DeactivateActCtx` at `0x1800391f5`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryW(LPCWSTR lpLibFileName)
{
  int v2; // eax
  int v3; // edx
  int v4; // edi
  int v5; // ebx
  DWORD LastError; // eax
  HMODULE LibraryW; // rax
  HMODULE v9; // rdi
  DWORD v10; // esi
  ULONG_PTR Cookie; // [rsp+48h] [rbp+10h] BYREF

  Cookie = 0;
  if ( IsolationAwarePrivateT_SAbnPgpgk )
    goto LABEL_19;
  v2 = IsolationAwarePrivateT_SqbjaYRiRY;
  if ( IsolationAwarePrivateT_SqbjaYRiRY )
    goto LABEL_19;
  v3 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  if ( WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ )
  {
    OutputDebugStringA("IsolationAware function called after IsolationAwareCleanup\n");
    v2 = IsolationAwarePrivateT_SqbjaYRiRY;
    v3 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  }
  if ( v2 )
  {
LABEL_19:
    v5 = 1;
  }
  else
  {
    v4 = 0;
    if ( v3 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk() )
    {
      v5 = 1;
      if ( ActivateActCtx(WinbaseIsolationAwarePrivateT_UnPgpgk, &Cookie) )
        v4 = 1;
    }
    else
    {
      v5 = 1;
    }
    if ( !v4 )
    {
      LastError = GetLastError();
      if ( LastError == 120 || LastError == 50 || LastError == 1 || LastError - 126 <= 1 )
      {
        IsolationAwarePrivateT_SqbjaYRiRY = 1;
        v4 = 1;
      }
      if ( !v4 )
        return 0;
    }
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  v9 = LibraryW;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( LibraryW )
    {
      v5 = 0;
      v10 = 0;
    }
    else
    {
      v10 = GetLastError();
    }
    DeactivateActCtx(0, Cookie);
    if ( v5 )
      SetLastError(v10);
  }
  return v9;
}

```

## disassembly

```asm
0x1800206ec  mov     rax, rsp
0x1800206ef  mov     [rax+8], rbx
0x1800206f3  mov     [rax+18h], rsi
0x1800206f7  push    rdi
0x1800206f8  sub     rsp, 30h
0x1800206fc  mov     rsi, rcx
0x1800206ff  mov     qword ptr [rax-18h], 0
0x180020707  mov     qword ptr [rax+10h], 0
0x18002070f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180020716  jnz     loc_1800207BE
0x18002071c  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x180020722  test    eax, eax
0x180020724  jnz     loc_1800207BE
0x18002072a  mov     edx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180020730  test    edx, edx
0x180020732  jz      short loc_18002074D
0x180020734  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x18002073b  call    cs:__imp_OutputDebugStringA
0x180020741  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x180020747  mov     edx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x18002074d  test    eax, eax
0x18002074f  jnz     short loc_1800207BE
0x180020751  xor     edi, edi
0x180020753  test    edx, edx
0x180020755  jnz     short loc_180020765
0x180020757  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x18002075c  test    eax, eax
0x18002075e  jnz     short loc_180020765
0x180020760  lea     ebx, [rdi+1]
0x180020763  jmp     short loc_180020781
0x180020765  lea     rdx, [rsp+38h+Cookie]; lpCookie
0x18002076a  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180020771  call    cs:__imp_ActivateActCtx
0x180020777  mov     ebx, 1
0x18002077c  test    eax, eax
0x18002077e  cmovnz  edi, ebx
0x180020781  test    edi, edi
0x180020783  jnz     short loc_1800207C3
0x180020785  call    cs:__imp_GetLastError
0x18002078b  cmp     eax, 78h ; 'x'
0x18002078e  jz      short loc_1800207A0
0x180020790  cmp     eax, 32h ; '2'
0x180020793  jz      short loc_1800207A0
0x180020795  cmp     eax, ebx
0x180020797  jz      short loc_1800207A0
0x180020799  add     eax, 0FFFFFF82h
0x18002079c  cmp     eax, ebx
0x18002079e  ja      short loc_1800207A8
0x1800207a0  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x1800207a6  mov     edi, ebx
0x1800207a8  test    edi, edi
0x1800207aa  jnz     short loc_1800207C3
0x1800207ac  xor     eax, eax
0x1800207ae  mov     rbx, [rsp+38h+arg_0]
0x1800207b3  mov     rsi, [rsp+38h+arg_10]
0x1800207b8  add     rsp, 30h
0x1800207bc  pop     rdi
0x1800207bd  retn
0x1800207be  mov     ebx, 1
0x1800207c3  mov     rcx, rsi; lpLibFileName
0x1800207c6  call    cs:__imp_LoadLibraryW
0x1800207cc  mov     rdi, rax
0x1800207cf  mov     [rsp+38h+var_18], rax
0x1800207d4  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800207db  jz      short loc_1800207E6
0x1800207dd  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800207e4  jnz     short loc_180020812
0x1800207e6  test    rdi, rdi
0x1800207e9  jnz     short loc_1800207F5
0x1800207eb  call    cs:__imp_GetLastError
0x1800207f1  mov     esi, eax
0x1800207f3  jmp     short loc_1800207F9
0x1800207f5  xor     ebx, ebx
0x1800207f7  xor     esi, esi
0x1800207f9  mov     rdx, [rsp+38h+Cookie]; ulCookie
0x1800207fe  xor     ecx, ecx; dwFlags
0x180020800  call    cs:__imp_DeactivateActCtx
0x180020806  test    ebx, ebx
0x180020808  jz      short loc_180020812
0x18002080a  mov     ecx, esi; dwErrCode
0x18002080c  call    cs:__imp_SetLastError
0x180020812  mov     rax, rdi
0x180020815  jmp     short loc_1800207AE
0x1800391b8  push    rbx
0x1800391ba  push    rbp
0x1800391bb  push    rdi
0x1800391bc  sub     rsp, 20h
0x1800391c0  mov     rbp, rdx
0x1800391c3  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800391ca  jz      short loc_1800391D5
0x1800391cc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800391d3  jnz     short loc_180039208
0x1800391d5  cmp     qword ptr [rbp+20h], 0
0x1800391da  jnz     short loc_1800391EB
0x1800391dc  mov     edi, 1
0x1800391e1  call    cs:__imp_GetLastError
0x1800391e7  mov     ebx, eax
0x1800391e9  jmp     short loc_1800391EF
0x1800391eb  xor     edi, edi
0x1800391ed  xor     ebx, ebx
0x1800391ef  mov     rdx, [rbp+48h]; ulCookie
0x1800391f3  xor     ecx, ecx; dwFlags
0x1800391f5  call    cs:__imp_DeactivateActCtx
0x1800391fb  test    edi, edi
0x1800391fd  jz      short loc_180039208
0x1800391ff  mov     ecx, ebx; dwErrCode
0x180039201  call    cs:__imp_SetLastError
0x180039207  nop
0x180039208  add     rsp, 20h
0x18003920c  pop     rdi
0x18003920d  pop     rbp
0x18003920e  pop     rbx
0x18003920f  retn
```
