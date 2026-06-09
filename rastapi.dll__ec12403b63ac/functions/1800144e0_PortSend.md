# PortSend

- ea: `0x1800144e0`
- end: `0x1800146d6`
- name: `PortSend`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180012340`
- `0x1800144e0`
- `0x180029266`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x18001451b`
- `msvcrt!_stricmp` at `0x18001451b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800145ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800145ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800146b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014658`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800146b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014686`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014588`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800145ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800145e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001467c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014588`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800145ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800145e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001467c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014543`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180014543`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDevSpecific` at `0x180014645`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDevSpecific` at `0x180014645`

## pseudocode

```c
DWORD __fastcall PortSend(__int64 a1, const void *a2, __int64 a3, __int64 a4)
{
  size_t v4; // rsi
  DWORD LastError; // ebx
  _DWORD *v9; // rax
  void *v10; // rdi
  __int64 v11; // rcx
  HCALL v12; // r8d
  DWORD v13; // edx
  unsigned int v14; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-38h] BYREF

  v4 = (unsigned int)a3;
  NumberOfBytesWritten = 0;
  GetMutex(a1, a2, a3, a4);
  if ( !_stricmp((const char *)(a1 + 64), "MODEM") )
  {
    if ( !WriteFile(*(HANDLE *)(a1 + 888), a2, v4, &NumberOfBytesWritten, (LPOVERLAPPED)(a1 + 952)) )
    {
      LastError = GetLastError();
      if ( LastError != 997 )
      {
LABEL_21:
        if ( !ReleaseMutex(RasTapiMutex) )
          GetLastError();
        return LastError;
      }
    }
LABEL_4:
    LastError = 600;
    goto LABEL_21;
  }
  if ( !*(_DWORD *)(*(_QWORD *)(a1 + 216) + 32LL) )
  {
LABEL_20:
    LastError = 0;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(a1 + 56) != 3 )
  {
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    return 0;
  }
  if ( (int)v4 + 16 < (unsigned int)v4 )
  {
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    return 534;
  }
  v9 = LocalAlloc(0x40u, (unsigned int)(v4 + 16));
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    v9[2] = v4;
    memcpy_0(v9 + 3, a2, v4);
    v11 = *(_QWORD *)(a1 + 216);
    v12 = *(_DWORD *)(a1 + 232);
    v13 = *(_DWORD *)(a1 + 224);
    *(_QWORD *)(a1 + 1128) = v10;
    *(_DWORD *)(a1 + 1192) = 1;
    v14 = lineDevSpecific(*(_DWORD *)(v11 + 12), v13, v12, v10, v4 + 16);
    *(_DWORD *)(a1 + 1120) = v14;
    if ( v14 )
    {
      if ( v14 > 0x80000000 )
      {
        LocalFree(v10);
        *(_QWORD *)(a1 + 1128) = 0;
        *(_DWORD *)(a1 + 1120) = -1;
        LastError = 651;
        goto LABEL_21;
      }
      goto LABEL_4;
    }
    LocalFree(v10);
    *(_QWORD *)(a1 + 1128) = 0;
    *(_DWORD *)(a1 + 1120) = -1;
    goto LABEL_20;
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return GetLastError();
}

```

## disassembly

```asm
0x1800144e0  push    rbx
0x1800144e2  push    rbp
0x1800144e3  push    rsi
0x1800144e4  push    rdi
0x1800144e5  push    r14
0x1800144e7  sub     rsp, 40h
0x1800144eb  mov     rax, cs:__security_cookie
0x1800144f2  xor     rax, rsp
0x1800144f5  mov     [rsp+68h+var_30], rax
0x1800144fa  mov     esi, r8d
0x1800144fd  mov     r14, rdx
0x180014500  mov     rbx, rcx
0x180014503  mov     [rsp+68h+NumberOfBytesWritten], 0
0x18001450b  call    GetMutex
0x180014510  lea     rcx, [rbx+40h]; String1
0x180014514  lea     rdx, aModem; "MODEM"
0x18001451b  call    cs:__imp__stricmp
0x180014521  test    eax, eax
0x180014523  jnz     short loc_18001456A
0x180014525  mov     rcx, [rbx+378h]; hFile
0x18001452c  lea     rax, [rbx+3B8h]
0x180014533  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180014538  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18001453d  mov     r8d, esi; nNumberOfBytesToWrite
0x180014540  mov     rdx, r14; lpBuffer
0x180014543  call    cs:__imp_WriteFile
0x180014549  test    eax, eax
0x18001454b  jnz     short loc_180014560
0x18001454d  call    cs:__imp_GetLastError
0x180014553  mov     ebx, eax
0x180014555  cmp     eax, 3E5h
0x18001455a  jnz     loc_180014675
0x180014560  mov     ebx, 258h
0x180014565  jmp     loc_180014675
0x18001456a  mov     rax, [rbx+0D8h]
0x180014571  cmp     dword ptr [rax+20h], 0
0x180014575  jz      loc_180014673
0x18001457b  cmp     dword ptr [rbx+38h], 3
0x18001457f  jz      short loc_18001459F
0x180014581  mov     rcx, cs:RasTapiMutex; hMutex
0x180014588  call    cs:__imp_ReleaseMutex
0x18001458e  test    eax, eax
0x180014590  jnz     short loc_180014598
0x180014592  call    cs:__imp_GetLastError
0x180014598  xor     eax, eax
0x18001459a  jmp     loc_18001468E
0x18001459f  lea     ebp, [rsi+10h]
0x1800145a2  cmp     ebp, esi
0x1800145a4  jnb     short loc_1800145C7
0x1800145a6  mov     rcx, cs:RasTapiMutex; hMutex
0x1800145ad  call    cs:__imp_ReleaseMutex
0x1800145b3  test    eax, eax
0x1800145b5  jnz     short loc_1800145BD
0x1800145b7  call    cs:__imp_GetLastError
0x1800145bd  mov     eax, 216h
0x1800145c2  jmp     loc_18001468E
0x1800145c7  mov     edx, ebp; uBytes
0x1800145c9  mov     ecx, 40h ; '@'; uFlags
0x1800145ce  call    cs:__imp_LocalAlloc
0x1800145d4  mov     rdi, rax
0x1800145d7  test    rax, rax
0x1800145da  jnz     short loc_1800145FE
0x1800145dc  mov     rcx, cs:RasTapiMutex; hMutex
0x1800145e3  call    cs:__imp_ReleaseMutex
0x1800145e9  test    eax, eax
0x1800145eb  jnz     short loc_1800145F3
0x1800145ed  call    cs:__imp_GetLastError
0x1800145f3  call    cs:__imp_GetLastError
0x1800145f9  jmp     loc_18001468E
0x1800145fe  mov     r8, rsi; Size
0x180014601  mov     dword ptr [rax], 0
0x180014607  lea     rcx, [rax+0Ch]; void *
0x18001460b  mov     [rax+8], esi
0x18001460e  mov     rdx, r14; Src
0x180014611  call    memcpy_0
0x180014616  mov     rcx, [rbx+0D8h]
0x18001461d  mov     r9, rdi; lpParams
0x180014620  mov     r8d, [rbx+0E8h]; hCall
0x180014627  mov     edx, [rbx+0E0h]; dwAddressID
0x18001462d  mov     [rbx+468h], rdi
0x180014634  mov     dword ptr [rbx+4A8h], 1
0x18001463e  mov     ecx, [rcx+0Ch]; hLine
0x180014641  mov     dword ptr [rsp+68h+lpOverlapped], ebp; dwSize
0x180014645  call    cs:__imp_lineDevSpecific
0x18001464b  mov     [rbx+460h], eax
0x180014651  test    eax, eax
0x180014653  jnz     short loc_1800146A6
0x180014655  mov     rcx, rdi; hMem
0x180014658  call    cs:__imp_LocalFree
0x18001465e  mov     qword ptr [rbx+468h], 0
0x180014669  mov     dword ptr [rbx+460h], 0FFFFFFFFh
0x180014673  xor     ebx, ebx
0x180014675  mov     rcx, cs:RasTapiMutex; hMutex
0x18001467c  call    cs:__imp_ReleaseMutex
0x180014682  test    eax, eax
0x180014684  jnz     short loc_18001468C
0x180014686  call    cs:__imp_GetLastError
0x18001468c  mov     eax, ebx
0x18001468e  mov     rcx, [rsp+68h+var_30]
0x180014693  xor     rcx, rsp; StackCookie
0x180014696  call    __security_check_cookie
0x18001469b  add     rsp, 40h
0x18001469f  pop     r14
0x1800146a1  pop     rdi
0x1800146a2  pop     rsi
0x1800146a3  pop     rbp
0x1800146a4  pop     rbx
0x1800146a5  retn
0x1800146a6  cmp     eax, 80000000h
0x1800146ab  jbe     loc_180014560
0x1800146b1  mov     rcx, rdi; hMem
0x1800146b4  call    cs:__imp_LocalFree
0x1800146ba  mov     qword ptr [rbx+468h], 0
0x1800146c5  mov     dword ptr [rbx+460h], 0FFFFFFFFh
0x1800146cf  mov     ebx, 28Bh
0x1800146d4  jmp     short loc_180014675
```
