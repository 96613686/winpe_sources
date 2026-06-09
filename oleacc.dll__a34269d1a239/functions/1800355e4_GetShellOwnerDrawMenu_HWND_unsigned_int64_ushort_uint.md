# GetShellOwnerDrawMenu(HWND__ *,unsigned __int64,ushort *,uint)

- ea: `0x1800355e4`
- end: `0x180035794`
- name: `?GetShellOwnerDrawMenu@@YAHPEAUHWND__@@_KPEAGI@Z`
- size: `432`
- prototype: `int(HWND, unsigned __int64, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180004de4`

## callees

- `0x18001e4c0`
- `0x1800355e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035635`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180035635`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003566d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800356a4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800356e1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180035733`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003566d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800356a4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800356e1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180035733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035766`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035766`
- `USER32!GetWindowThreadProcessId` at `0x18003561d`
- `USER32!GetWindowThreadProcessId` at `0x18003561d`

## pseudocode

```c
_BOOL8 __fastcall GetShellOwnerDrawMenu(HWND a1, const void *a2, unsigned __int16 *a3)
{
  HANDLE v5; // rsi
  unsigned int v6; // edi
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  SIZE_T NumberOfBytesRead; // [rsp+30h] [rbp-50h] BYREF
  DWORD dwProcessId; // [rsp+38h] [rbp-48h] BYREF
  __int128 Buffer; // [rsp+40h] [rbp-40h] BYREF
  LPCVOID lpBaseAddress[2]; // [rsp+50h] [rbp-30h]
  __int128 v15; // [rsp+60h] [rbp-20h] BYREF

  if ( !a3 )
    return 0;
  dwProcessId = 0;
  GetWindowThreadProcessId(a1, &dwProcessId);
  if ( !dwProcessId )
    return 0;
  v5 = OpenProcess(0x10u, 0, dwProcessId);
  if ( !v5 )
    return 0;
  NumberOfBytesRead = 0;
  Buffer = 0;
  *(_OWORD *)lpBaseAddress = 0;
  if ( ReadProcessMemory(v5, a2, &Buffer, 0x20u, &NumberOfBytesRead) && NumberOfBytesRead == 32 )
  {
    if ( lpBaseAddress[1] )
    {
      ReadProcessMemory(v5, lpBaseAddress[1], a3, 0x100u, &NumberOfBytesRead);
      a3[255] = 0;
    }
    else if ( lpBaseAddress[0] )
    {
      v15 = 0;
      if ( ReadProcessMemory(v5, lpBaseAddress[0], &v15, 0x10u, &NumberOfBytesRead) )
      {
        if ( NumberOfBytesRead == 16 )
        {
          v6 = 256;
          LOWORD(v15) = v15 - 14;
          if ( (unsigned __int16)v15 < 0x100u )
          {
            v7 = (__int16)v15;
            if ( (unsigned int)(__int16)v15 <= 1 )
              v7 = 1;
            v6 = v7;
          }
          ReadProcessMemory(v5, (char *)lpBaseAddress[0] + 14, a3, v6, &NumberOfBytesRead);
          a3[v6 - 1] = 0;
          v8 = -1;
          do
            ++v8;
          while ( a3[v8] );
          if ( (unsigned int)v8 >= 4 )
          {
            v9 = (unsigned int)(v8 - 4);
            if ( a3[v9] == 46 )
              a3[v9] = 0;
          }
        }
      }
    }
  }
  CloseHandle(v5);
  return *a3 != 0;
}

```

## disassembly

```asm
0x1800355e4  push    rbp
0x1800355e6  push    rbx
0x1800355e7  push    rsi
0x1800355e8  push    rdi
0x1800355e9  push    r14
0x1800355eb  mov     rbp, rsp
0x1800355ee  sub     rsp, 80h
0x1800355f5  mov     rax, cs:__security_cookie
0x1800355fc  xor     rax, rsp
0x1800355ff  mov     [rbp+var_10], rax
0x180035603  xor     r14d, r14d
0x180035606  mov     rbx, r8
0x180035609  mov     rdi, rdx
0x18003560c  test    r8, r8
0x18003560f  jz      loc_180035778
0x180035615  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180035619  mov     [rbp+dwProcessId], r14d
0x18003561d  call    cs:__imp_GetWindowThreadProcessId
0x180035623  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180035627  test    r8d, r8d
0x18003562a  jz      loc_180035778
0x180035630  xor     edx, edx; bInheritHandle
0x180035632  lea     ecx, [rdx+10h]; dwDesiredAccess
0x180035635  call    cs:__imp_OpenProcess
0x18003563b  mov     rsi, rax
0x18003563e  test    rax, rax
0x180035641  jz      loc_180035778
0x180035647  xorps   xmm0, xmm0
0x18003564a  mov     [rbp+NumberOfBytesRead], r14
0x18003564e  lea     rax, [rbp+NumberOfBytesRead]
0x180035652  mov     rdx, rdi; lpBaseAddress
0x180035655  lea     r9d, [r14+20h]; nSize
0x180035659  mov     [rsp+80h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18003565e  lea     r8, [rbp+Buffer]; lpBuffer
0x180035662  mov     rcx, rsi; hProcess
0x180035665  movups  [rbp+Buffer], xmm0
0x180035669  movups  xmmword ptr [rbp+lpBaseAddress], xmm0
0x18003566d  call    cs:__imp_ReadProcessMemory
0x180035673  test    eax, eax
0x180035675  jz      loc_180035763
0x18003567b  cmp     [rbp+NumberOfBytesRead], 20h ; ' '
0x180035680  jnz     loc_180035763
0x180035686  mov     rdx, [rbp+lpBaseAddress+8]; lpBaseAddress
0x18003568a  test    rdx, rdx
0x18003568d  jz      short loc_1800356B7
0x18003568f  lea     rax, [rbp+NumberOfBytesRead]
0x180035693  mov     r9d, 100h; nSize
0x180035699  mov     r8, rbx; lpBuffer
0x18003569c  mov     [rsp+80h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800356a1  mov     rcx, rsi; hProcess
0x1800356a4  call    cs:__imp_ReadProcessMemory
0x1800356aa  mov     [rbx+1FEh], r14w
0x1800356b2  jmp     loc_180035763
0x1800356b7  mov     rdx, [rbp+lpBaseAddress]; lpBaseAddress
0x1800356bb  test    rdx, rdx
0x1800356be  jz      loc_180035763
0x1800356c4  xorps   xmm0, xmm0
0x1800356c7  lea     rax, [rbp+NumberOfBytesRead]
0x1800356cb  mov     r9d, 10h; nSize
0x1800356d1  mov     [rsp+80h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800356d6  lea     r8, [rbp+var_20]; lpBuffer
0x1800356da  mov     rcx, rsi; hProcess
0x1800356dd  movups  [rbp+var_20], xmm0
0x1800356e1  call    cs:__imp_ReadProcessMemory
0x1800356e7  test    eax, eax
0x1800356e9  jz      short loc_180035763
0x1800356eb  cmp     [rbp+NumberOfBytesRead], 10h
0x1800356f0  jnz     short loc_180035763
0x1800356f2  movzx   eax, word ptr [rbp+var_20]
0x1800356f6  mov     edi, 100h
0x1800356fb  sub     ax, 0Eh
0x1800356ff  movsx   ecx, ax
0x180035702  mov     word ptr [rbp+var_20], ax
0x180035706  cmp     cx, di
0x180035709  jnb     short loc_180035719
0x18003570b  mov     eax, ecx
0x18003570d  mov     ecx, 1
0x180035712  cmp     eax, ecx
0x180035714  cmovbe  eax, ecx
0x180035717  mov     edi, eax
0x180035719  mov     rdx, [rbp+lpBaseAddress]
0x18003571d  lea     rax, [rbp+NumberOfBytesRead]
0x180035721  add     rdx, 0Eh; lpBaseAddress
0x180035725  mov     r9d, edi; nSize
0x180035728  mov     r8, rbx; lpBuffer
0x18003572b  mov     [rsp+80h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180035730  mov     rcx, rsi; hProcess
0x180035733  call    cs:__imp_ReadProcessMemory
0x180035739  lea     eax, [rdi-1]
0x18003573c  mov     [rbx+rax*2], r14w
0x180035741  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035745  inc     rax
0x180035748  cmp     [rbx+rax*2], r14w
0x18003574d  jnz     short loc_180035745
0x18003574f  cmp     eax, 4
0x180035752  jb      short loc_180035763
0x180035754  add     eax, 0FFFFFFFCh
0x180035757  cmp     word ptr [rbx+rax*2], 2Eh ; '.'
0x18003575c  jnz     short loc_180035763
0x18003575e  mov     [rbx+rax*2], r14w
0x180035763  mov     rcx, rsi; hObject
0x180035766  call    cs:__imp_CloseHandle
0x18003576c  cmp     [rbx], r14w
0x180035770  mov     eax, r14d
0x180035773  setnz   al
0x180035776  jmp     short loc_18003577A
0x180035778  xor     eax, eax
0x18003577a  mov     rcx, [rbp+var_10]
0x18003577e  xor     rcx, rsp; StackCookie
0x180035781  call    __security_check_cookie
0x180035786  add     rsp, 80h
0x18003578d  pop     r14
0x18003578f  pop     rdi
0x180035790  pop     rsi
0x180035791  pop     rbx
0x180035792  pop     rbp
0x180035793  retn
```
