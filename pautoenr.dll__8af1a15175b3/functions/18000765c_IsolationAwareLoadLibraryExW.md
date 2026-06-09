# IsolationAwareLoadLibraryExW

- ea: `0x18000765c`
- end: `0x180007790`
- name: `IsolationAwareLoadLibraryExW`
- size: `308`
- prototype: `HMODULE __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000680c`

## callees

- `0x180004720`
- `0x18000765c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007785`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007785`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800080ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000773f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000773f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800076af`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800076af`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800076e5`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800076e5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007779`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800080f3`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007779`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800080f3`

## pseudocode

```c
HMODULE __fastcall IsolationAwareLoadLibraryExW(LPCWSTR lpLibFileName)
{
  int v2; // eax
  int v3; // edx
  int v4; // edi
  int v5; // ebx
  DWORD LastError; // eax
  HMODULE Library; // rax
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
    if ( v3 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk(lpLibFileName) )
    {
      v5 = 1;
      if ( ActivateActCtx(*(HANDLE *)&WinbaseIsolationAwarePrivateT_UnPgpgk, &Cookie) )
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
  Library = LoadLibraryExW(lpLibFileName, 0, 0);
  v9 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
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
0x18000765c  mov     rax, rsp
0x18000765f  mov     [rax+8], rbx
0x180007663  mov     [rax+18h], rsi
0x180007667  mov     [rax+10h], rdx
0x18000766b  push    rdi
0x18000766c  sub     rsp, 30h
0x180007670  mov     rsi, rcx
0x180007673  mov     qword ptr [rax-18h], 0
0x18000767b  mov     qword ptr [rax+10h], 0
0x180007683  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000768a  jnz     loc_180007732
0x180007690  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x180007696  test    eax, eax
0x180007698  jnz     loc_180007732
0x18000769e  mov     edx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x1800076a4  test    edx, edx
0x1800076a6  jz      short loc_1800076C1
0x1800076a8  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x1800076af  call    cs:__imp_OutputDebugStringA
0x1800076b5  mov     eax, cs:IsolationAwarePrivateT_SqbjaYRiRY
0x1800076bb  mov     edx, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x1800076c1  test    eax, eax
0x1800076c3  jnz     short loc_180007732
0x1800076c5  xor     edi, edi
0x1800076c7  test    edx, edx
0x1800076c9  jnz     short loc_1800076D9
0x1800076cb  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x1800076d0  test    eax, eax
0x1800076d2  jnz     short loc_1800076D9
0x1800076d4  lea     ebx, [rdi+1]
0x1800076d7  jmp     short loc_1800076F5
0x1800076d9  lea     rdx, [rsp+38h+Cookie]; lpCookie
0x1800076de  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800076e5  call    cs:__imp_ActivateActCtx
0x1800076eb  mov     ebx, 1
0x1800076f0  test    eax, eax
0x1800076f2  cmovnz  edi, ebx
0x1800076f5  test    edi, edi
0x1800076f7  jnz     short loc_180007737
0x1800076f9  call    cs:__imp_GetLastError
0x1800076ff  cmp     eax, 78h ; 'x'
0x180007702  jz      short loc_180007714
0x180007704  cmp     eax, 32h ; '2'
0x180007707  jz      short loc_180007714
0x180007709  cmp     eax, ebx
0x18000770b  jz      short loc_180007714
0x18000770d  add     eax, 0FFFFFF82h
0x180007710  cmp     eax, ebx
0x180007712  ja      short loc_18000771C
0x180007714  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x18000771a  mov     edi, ebx
0x18000771c  test    edi, edi
0x18000771e  jnz     short loc_180007737
0x180007720  xor     eax, eax
0x180007722  mov     rbx, [rsp+38h+arg_0]
0x180007727  mov     rsi, [rsp+38h+arg_10]
0x18000772c  add     rsp, 30h
0x180007730  pop     rdi
0x180007731  retn
0x180007732  mov     ebx, 1
0x180007737  xor     r8d, r8d; dwFlags
0x18000773a  xor     edx, edx; hFile
0x18000773c  mov     rcx, rsi; lpLibFileName
0x18000773f  call    cs:__imp_LoadLibraryExW
0x180007745  mov     rdi, rax
0x180007748  mov     [rsp+38h+var_18], rax
0x18000774d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007754  jz      short loc_18000775F
0x180007756  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000775d  jnz     short loc_18000778B
0x18000775f  test    rdi, rdi
0x180007762  jnz     short loc_18000776E
0x180007764  call    cs:__imp_GetLastError
0x18000776a  mov     esi, eax
0x18000776c  jmp     short loc_180007772
0x18000776e  xor     ebx, ebx
0x180007770  xor     esi, esi
0x180007772  mov     rdx, [rsp+38h+Cookie]; ulCookie
0x180007777  xor     ecx, ecx; dwFlags
0x180007779  call    cs:__imp_DeactivateActCtx
0x18000777f  test    ebx, ebx
0x180007781  jz      short loc_18000778B
0x180007783  mov     ecx, esi; dwErrCode
0x180007785  call    cs:__imp_SetLastError
0x18000778b  mov     rax, rdi
0x18000778e  jmp     short loc_180007722
0x1800080b6  push    rbx
0x1800080b8  push    rbp
0x1800080b9  push    rdi
0x1800080ba  sub     rsp, 20h
0x1800080be  mov     rbp, rdx
0x1800080c1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800080c8  jz      short loc_1800080D3
0x1800080ca  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800080d1  jnz     short loc_180008106
0x1800080d3  cmp     qword ptr [rbp+20h], 0
0x1800080d8  jnz     short loc_1800080E9
0x1800080da  mov     edi, 1
0x1800080df  call    cs:__imp_GetLastError
0x1800080e5  mov     ebx, eax
0x1800080e7  jmp     short loc_1800080ED
0x1800080e9  xor     edi, edi
0x1800080eb  xor     ebx, ebx
0x1800080ed  mov     rdx, [rbp+48h]; ulCookie
0x1800080f1  xor     ecx, ecx; dwFlags
0x1800080f3  call    cs:__imp_DeactivateActCtx
0x1800080f9  test    edi, edi
0x1800080fb  jz      short loc_180008106
0x1800080fd  mov     ecx, ebx; dwErrCode
0x1800080ff  call    cs:__imp_SetLastError
0x180008105  nop
0x180008106  add     rsp, 20h
0x18000810a  pop     rdi
0x18000810b  pop     rbp
0x18000810c  pop     rbx
0x18000810d  retn
```
