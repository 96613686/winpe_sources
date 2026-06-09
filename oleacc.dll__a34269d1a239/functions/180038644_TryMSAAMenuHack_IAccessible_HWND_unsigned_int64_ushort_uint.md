# TryMSAAMenuHack(IAccessible *,HWND__ *,unsigned __int64,ushort *,uint)

- ea: `0x180038644`
- end: `0x1800387c7`
- name: `?TryMSAAMenuHack@@YAHPEAUIAccessible@@PEAUHWND__@@_KPEAGI@Z`
- size: `387`
- prototype: `int(struct IAccessible *, HWND, unsigned __int64, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180004de4`

## callees

- `0x180038644`
- `0x18003b574`
- `0x180047ff8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800386b8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800386b8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800386eb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180038758`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800386eb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180038758`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800387a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800387a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003879c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003879c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038734`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038734`
- `USER32!GetWindowThreadProcessId` at `0x180038698`
- `USER32!GetWindowThreadProcessId` at `0x180038698`

## pseudocode

```c
__int64 __fastcall TryMSAAMenuHack(
        struct IAccessible *a1,
        HWND a2,
        const void *a3,
        unsigned __int16 *a4,
        DWORD dwProcessId)
{
  HWND v7; // r10
  unsigned int v9; // r14d
  HANDLE v10; // rsi
  unsigned __int64 v11; // rax
  __int64 v12; // rbx
  HLOCAL v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rbx
  SIZE_T NumberOfBytesRead; // [rsp+30h] [rbp-20h] BYREF
  __int128 Buffer; // [rsp+38h] [rbp-18h] BYREF
  HWND v18; // [rsp+88h] [rbp+38h] BYREF

  v18 = a2;
  *a4 = 0;
  v7 = a2;
  if ( !a2 )
  {
    if ( (unsigned int)WindowFromAccessibleObjectEx(a1, &v18) )
      return 0;
    v7 = v18;
    if ( !v18 )
      return 0;
  }
  dwProcessId = 0;
  GetWindowThreadProcessId(v7, &dwProcessId);
  if ( !dwProcessId )
    return 0;
  v9 = 0;
  v10 = OpenProcess(0x10u, 0, dwProcessId);
  if ( v10 )
  {
    NumberOfBytesRead = 0;
    Buffer = 0;
    if ( ReadProcessMemory(v10, a3, &Buffer, 0x10u, &NumberOfBytesRead) )
    {
      if ( NumberOfBytesRead == 16
        && (_DWORD)Buffer == -1441927155
        && (unsigned int)(DWORD1(Buffer) + 1) >= DWORD1(Buffer) )
      {
        v11 = 2LL * (unsigned int)(DWORD1(Buffer) + 1);
        if ( v11 <= 0xFFFFFFFF )
        {
          v12 = (unsigned int)v11;
          v13 = LocalAlloc(0x40u, (unsigned int)v11);
          if ( v13 )
          {
            if ( ReadProcessMemory(v10, *((LPCVOID *)&Buffer + 1), v13, (unsigned int)v12, &NumberOfBytesRead) )
            {
              if ( NumberOfBytesRead == v12 )
              {
                v14 = DWORD1(Buffer);
                if ( !*((_WORD *)v13 + DWORD1(Buffer)) )
                {
                  if ( DWORD1(Buffer) > 0xFF )
                    v14 = 255;
                  v15 = v14;
                  memcpy_0(a4, v13, 2 * v14);
                  a4[v15] = 0;
                  v9 = 1;
                }
              }
            }
            LocalFree(v13);
          }
        }
      }
    }
    CloseHandle(v10);
  }
  return v9;
}

```

## disassembly

```asm
0x180038644  mov     [rsp-28h+arg_0], rbx
0x180038649  mov     [rsp-28h+arg_10], rsi
0x18003864e  mov     [rsp-28h+arg_8], rdx
0x180038653  push    rbp
0x180038654  push    rdi
0x180038655  push    r12
0x180038657  push    r14
0x180038659  push    r15
0x18003865b  mov     rbp, rsp
0x18003865e  sub     rsp, 50h
0x180038662  xor     r12d, r12d
0x180038665  mov     r15, r9
0x180038668  mov     [r9], r12w
0x18003866c  mov     rbx, r8
0x18003866f  mov     r10, rdx
0x180038672  test    rdx, rdx
0x180038675  jnz     short loc_18003868D
0x180038677  lea     rdx, [rbp+arg_8]; HWND *
0x18003867b  call    WindowFromAccessibleObjectEx
0x180038680  test    eax, eax
0x180038682  jnz     short loc_1800386A7
0x180038684  mov     r10, [rbp+arg_8]
0x180038688  test    r10, r10
0x18003868b  jz      short loc_1800386A7
0x18003868d  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180038691  mov     [rbp+dwProcessId], r12d
0x180038695  mov     rcx, r10; hWnd
0x180038698  call    cs:__imp_GetWindowThreadProcessId
0x18003869e  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x1800386a2  test    r8d, r8d
0x1800386a5  jnz     short loc_1800386AE
0x1800386a7  xor     eax, eax
0x1800386a9  jmp     loc_1800387AE
0x1800386ae  xor     edx, edx; bInheritHandle
0x1800386b0  mov     r14d, r12d
0x1800386b3  lea     edi, [rdx+10h]
0x1800386b6  mov     ecx, edi; dwDesiredAccess
0x1800386b8  call    cs:__imp_OpenProcess
0x1800386be  mov     rsi, rax
0x1800386c1  test    rax, rax
0x1800386c4  jz      loc_1800387AB
0x1800386ca  xorps   xmm0, xmm0
0x1800386cd  mov     [rbp+NumberOfBytesRead], r12
0x1800386d1  lea     rax, [rbp+NumberOfBytesRead]
0x1800386d5  mov     r9d, edi; nSize
0x1800386d8  lea     r8, [rbp+Buffer]; lpBuffer
0x1800386dc  mov     [rsp+50h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1800386e1  mov     rdx, rbx; lpBaseAddress
0x1800386e4  mov     rcx, rsi; hProcess
0x1800386e7  movups  [rbp+Buffer], xmm0
0x1800386eb  call    cs:__imp_ReadProcessMemory
0x1800386f1  test    eax, eax
0x1800386f3  jz      loc_1800387A2
0x1800386f9  cmp     [rbp+NumberOfBytesRead], rdi
0x1800386fd  jnz     loc_1800387A2
0x180038703  cmp     dword ptr [rbp+Buffer], 0AA0DF00Dh
0x18003870a  jnz     loc_1800387A2
0x180038710  mov     eax, dword ptr [rbp+Buffer+4]
0x180038713  lea     ecx, [rax+1]
0x180038716  cmp     ecx, eax
0x180038718  jb      loc_1800387A2
0x18003871e  mov     eax, ecx
0x180038720  mov     ecx, 0FFFFFFFFh
0x180038725  add     rax, rax
0x180038728  cmp     rax, rcx
0x18003872b  ja      short loc_1800387A2
0x18003872d  mov     edx, eax; uBytes
0x18003872f  lea     ecx, [rdi+30h]; uFlags
0x180038732  mov     ebx, eax
0x180038734  call    cs:__imp_LocalAlloc
0x18003873a  mov     rdi, rax
0x18003873d  test    rax, rax
0x180038740  jz      short loc_1800387A2
0x180038742  mov     rdx, qword ptr [rbp+Buffer+8]; lpBaseAddress
0x180038746  lea     rax, [rbp+NumberOfBytesRead]
0x18003874a  mov     r9d, ebx; nSize
0x18003874d  mov     [rsp+50h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180038752  mov     r8, rdi; lpBuffer
0x180038755  mov     rcx, rsi; hProcess
0x180038758  call    cs:__imp_ReadProcessMemory
0x18003875e  test    eax, eax
0x180038760  jz      short loc_180038799
0x180038762  cmp     [rbp+NumberOfBytesRead], rbx
0x180038766  jnz     short loc_180038799
0x180038768  mov     ecx, dword ptr [rbp+Buffer+4]
0x18003876b  cmp     [rdi+rcx*2], r12w
0x180038770  jnz     short loc_180038799
0x180038772  mov     eax, 0FFh
0x180038777  mov     rdx, rdi; Src
0x18003877a  cmp     ecx, eax
0x18003877c  cmova   ecx, eax
0x18003877f  lea     rbx, [rcx+rcx]
0x180038783  mov     rcx, r15; void *
0x180038786  mov     r8, rbx; Size
0x180038789  call    memcpy_0
0x18003878e  mov     [rbx+r15], r12w
0x180038793  mov     r14d, 1
0x180038799  mov     rcx, rdi; hMem
0x18003879c  call    cs:__imp_LocalFree
0x1800387a2  mov     rcx, rsi; hObject
0x1800387a5  call    cs:__imp_CloseHandle
0x1800387ab  mov     eax, r14d
0x1800387ae  lea     r11, [rsp+50h+var_s0]
0x1800387b3  mov     rbx, [r11+30h]
0x1800387b7  mov     rsi, [r11+40h]
0x1800387bb  mov     rsp, r11
0x1800387be  pop     r15
0x1800387c0  pop     r14
0x1800387c2  pop     r12
0x1800387c4  pop     rdi
0x1800387c5  pop     rbp
0x1800387c6  retn
```
