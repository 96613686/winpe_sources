# DuplicateHandleForRasman

- ea: `0x180005738`
- end: `0x180005a1a`
- name: `DuplicateHandleForRasman`
- size: `738`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180005ad8`
- `0x180026980`

## callees

- `0x180005738`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x180005c94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800058e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800059bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800058e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800059bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000579e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000579e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005967`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005916`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005916`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000597f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000597f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800057ba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005859`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800057ba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005859`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000586d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000586d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059d3`
- `RPCRT4!RpcImpersonateClient` at `0x18000580e`
- `RPCRT4!RpcImpersonateClient` at `0x18000580e`
- `RPCRT4!RpcRevertToSelf` at `0x18000598f`
- `RPCRT4!RpcRevertToSelf` at `0x18000598f`

## pseudocode

```c
HANDLE __fastcall DuplicateHandleForRasman(HANDLE hSourceHandle, DWORD dwProcessId)
{
  int v4; // esi
  HANDLE v5; // rbx
  DWORD LastError; // eax
  DWORD v7; // eax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  DWORD v10; // eax
  HANDLE CurrentProcess; // rax
  DWORD v12; // eax
  HANDLE TargetHandle; // [rsp+80h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids);
  }
  TargetHandle = 0;
  v4 = 0;
  if ( dwProcessId != GetCurrentProcessId() )
  {
    v5 = OpenProcess(0x40u, 0, dwProcessId);
    if ( !v5 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          11,
          WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids,
          dwProcessId,
          LastError);
      }
      v7 = RpcImpersonateClient(0);
      if ( v7 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
        {
          v9 = 12;
LABEL_41:
          WPP_SF_d(v8[1].Flink, v9, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids, v7);
          goto LABEL_30;
        }
        goto LABEL_30;
      }
      v4 = 1;
      v5 = OpenProcess(0x40u, 0, dwProcessId);
      if ( !v5 )
      {
        v10 = GetLastError();
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u )
        {
          WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 13, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids, dwProcessId, v10);
        }
        goto LABEL_30;
      }
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids);
      }
    }
LABEL_25:
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(v5, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      v12 = GetLastError();
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_dqD(
          WPP_GLOBAL_Control[1].Flink,
          16,
          WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids,
          dwProcessId,
          hSourceHandle,
          v12);
      }
    }
    goto LABEL_30;
  }
  v5 = GetCurrentProcess();
  if ( v5 )
    goto LABEL_25;
  v7 = GetLastError();
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v9 = 15;
    goto LABEL_41;
  }
LABEL_30:
  if ( dwProcessId != GetCurrentProcessId() && v5 )
    CloseHandle(v5);
  if ( v4 )
    RpcRevertToSelf();
  return TargetHandle;
}

```

## disassembly

```asm
0x180005738  mov     [rsp+arg_0], rbx
0x18000573d  mov     [rsp+arg_8], rbp
0x180005742  push    rsi
0x180005743  push    rdi
0x180005744  push    r12
0x180005746  push    r13
0x180005748  push    r15
0x18000574a  sub     rsp, 40h
0x18000574e  mov     edi, edx
0x180005750  mov     rbp, rcx
0x180005753  mov     rcx, cs:WPP_GLOBAL_Control
0x18000575a  lea     r12, WPP_GLOBAL_Control
0x180005761  lea     r13, WPP_51703e5ea2af3e423ed22f24729f7d2b_Traceguids
0x180005768  mov     r15d, 2000h
0x18000576e  cmp     rcx, r12
0x180005771  jz      short loc_180005790
0x180005773  test    [rcx+1Ch], r15d
0x180005777  jz      short loc_180005790
0x180005779  cmp     byte ptr [rcx+19h], 6
0x18000577d  jb      short loc_180005790
0x18000577f  mov     rcx, [rcx+10h]
0x180005783  mov     edx, 0Ah
0x180005788  mov     r8, r13
0x18000578b  call    WPP_SF_
0x180005790  mov     [rsp+68h+TargetHandle], 0
0x18000579c  xor     esi, esi
0x18000579e  call    cs:__imp_GetCurrentProcessId
0x1800057a5  nop     dword ptr [rax+rax+00h]
0x1800057aa  cmp     edi, eax
0x1800057ac  jz      loc_1800059BB
0x1800057b2  mov     r8d, edi; dwProcessId
0x1800057b5  lea     ecx, [rsi+40h]; dwDesiredAccess
0x1800057b8  xor     edx, edx; bInheritHandle
0x1800057ba  call    cs:__imp_OpenProcess
0x1800057c1  nop     dword ptr [rax+rax+00h]
0x1800057c6  mov     rbx, rax
0x1800057c9  test    rax, rax
0x1800057cc  jnz     loc_1800058E1
0x1800057d2  call    cs:__imp_GetLastError
0x1800057d9  nop     dword ptr [rax+rax+00h]
0x1800057de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057e5  cmp     rcx, r12
0x1800057e8  jz      short loc_18000580C
0x1800057ea  test    [rcx+1Ch], r15d
0x1800057ee  jz      short loc_18000580C
0x1800057f0  cmp     byte ptr [rcx+19h], 3
0x1800057f4  jb      short loc_18000580C
0x1800057f6  mov     rcx, [rcx+10h]
0x1800057fa  lea     edx, [rsi+0Bh]
0x1800057fd  mov     r9d, edi
0x180005800  mov     [rsp+68h+dwDesiredAccess], eax
0x180005804  mov     r8, r13
0x180005807  call    WPP_SF_Dd
0x18000580c  xor     ecx, ecx; BindingHandle
0x18000580e  call    cs:__imp_RpcImpersonateClient
0x180005815  nop     dword ptr [rax+rax+00h]
0x18000581a  test    eax, eax
0x18000581c  jz      short loc_18000584C
0x18000581e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005825  cmp     rcx, r12
0x180005828  jz      loc_180005967
0x18000582e  test    [rcx+1Ch], r15d
0x180005832  jz      loc_180005967
0x180005838  cmp     byte ptr [rcx+19h], 3
0x18000583c  jb      loc_180005967
0x180005842  mov     edx, 0Ch
0x180005847  jmp     loc_180005A06
0x18000584c  mov     esi, 1
0x180005851  mov     r8d, edi; dwProcessId
0x180005854  xor     edx, edx; bInheritHandle
0x180005856  lea     ecx, [rsi+3Fh]; dwDesiredAccess
0x180005859  call    cs:__imp_OpenProcess
0x180005860  nop     dword ptr [rax+rax+00h]
0x180005865  mov     rbx, rax
0x180005868  test    rax, rax
0x18000586b  jnz     short loc_1800058B8
0x18000586d  call    cs:__imp_GetLastError
0x180005874  nop     dword ptr [rax+rax+00h]
0x180005879  mov     rcx, cs:WPP_GLOBAL_Control
0x180005880  cmp     rcx, r12
0x180005883  jz      loc_180005967
0x180005889  test    [rcx+1Ch], r15d
0x18000588d  jz      loc_180005967
0x180005893  cmp     byte ptr [rcx+19h], 3
0x180005897  jb      loc_180005967
0x18000589d  mov     rcx, [rcx+10h]
0x1800058a1  lea     edx, [rsi+0Ch]
0x1800058a4  mov     r9d, edi
0x1800058a7  mov     [rsp+68h+dwDesiredAccess], eax
0x1800058ab  mov     r8, r13
0x1800058ae  call    WPP_SF_Dd
0x1800058b3  jmp     loc_180005967
0x1800058b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058bf  cmp     rcx, r12
0x1800058c2  jz      short loc_1800058E1
0x1800058c4  test    [rcx+1Ch], r15d
0x1800058c8  jz      short loc_1800058E1
0x1800058ca  cmp     byte ptr [rcx+19h], 4
0x1800058ce  jb      short loc_1800058E1
0x1800058d0  mov     rcx, [rcx+10h]
0x1800058d4  mov     edx, 0Eh
0x1800058d9  mov     r8, r13
0x1800058dc  call    WPP_SF_
0x1800058e1  call    cs:__imp_GetCurrentProcess
0x1800058e8  nop     dword ptr [rax+rax+00h]
0x1800058ed  mov     [rsp+68h+dwOptions], 2; dwOptions
0x1800058f5  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x1800058fd  mov     r8, rax; hTargetProcessHandle
0x180005900  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180005908  mov     rdx, rbp; hSourceHandle
0x18000590b  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180005913  mov     rcx, rbx; hSourceProcessHandle
0x180005916  call    cs:__imp_DuplicateHandle
0x18000591d  nop     dword ptr [rax+rax+00h]
0x180005922  test    eax, eax
0x180005924  jnz     short loc_180005967
0x180005926  call    cs:__imp_GetLastError
0x18000592d  nop     dword ptr [rax+rax+00h]
0x180005932  mov     rcx, cs:WPP_GLOBAL_Control
0x180005939  cmp     rcx, r12
0x18000593c  jz      short loc_180005967
0x18000593e  test    [rcx+1Ch], r15d
0x180005942  jz      short loc_180005967
0x180005944  cmp     byte ptr [rcx+19h], 2
0x180005948  jb      short loc_180005967
0x18000594a  mov     rcx, [rcx+10h]
0x18000594e  mov     edx, 10h
0x180005953  mov     [rsp+68h+bInheritHandle], eax
0x180005957  mov     r9d, edi
0x18000595a  mov     r8, r13
0x18000595d  mov     qword ptr [rsp+68h+dwDesiredAccess], rbp
0x180005962  call    WPP_SF_dqD
0x180005967  call    cs:__imp_GetCurrentProcessId
0x18000596e  nop     dword ptr [rax+rax+00h]
0x180005973  cmp     edi, eax
0x180005975  jz      short loc_18000598B
0x180005977  test    rbx, rbx
0x18000597a  jz      short loc_18000598B
0x18000597c  mov     rcx, rbx; hObject
0x18000597f  call    cs:__imp_CloseHandle
0x180005986  nop     dword ptr [rax+rax+00h]
0x18000598b  test    esi, esi
0x18000598d  jz      short loc_18000599B
0x18000598f  call    cs:__imp_RpcRevertToSelf
0x180005996  nop     dword ptr [rax+rax+00h]
0x18000599b  mov     rax, [rsp+68h+TargetHandle]
0x1800059a3  mov     rbx, [rsp+68h+arg_0]
0x1800059a8  mov     rbp, [rsp+68h+arg_8]
0x1800059ad  add     rsp, 40h
0x1800059b1  pop     r15
0x1800059b3  pop     r13
0x1800059b5  pop     r12
0x1800059b7  pop     rdi
0x1800059b8  pop     rsi
0x1800059b9  retn
0x1800059bb  call    cs:__imp_GetCurrentProcess
0x1800059c2  nop     dword ptr [rax+rax+00h]
0x1800059c7  mov     rbx, rax
0x1800059ca  test    rax, rax
0x1800059cd  jnz     loc_1800058E1
0x1800059d3  call    cs:__imp_GetLastError
0x1800059da  nop     dword ptr [rax+rax+00h]
0x1800059df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059e6  cmp     rcx, r12
0x1800059e9  jz      loc_180005967
0x1800059ef  test    [rcx+1Ch], r15d
0x1800059f3  jz      loc_180005967
0x1800059f9  cmp     byte ptr [rcx+19h], 2
0x1800059fd  jb      loc_180005967
0x180005a03  lea     edx, [rbx+0Fh]
0x180005a06  mov     rcx, [rcx+10h]
0x180005a0a  mov     r9d, eax
0x180005a0d  mov     r8, r13
0x180005a10  call    WPP_SF_d
0x180005a15  jmp     loc_180005967
```
