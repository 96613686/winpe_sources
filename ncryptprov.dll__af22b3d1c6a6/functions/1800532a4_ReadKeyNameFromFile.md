# ReadKeyNameFromFile

- ea: `0x1800532a4`
- end: `0x1800534ed`
- name: `ReadKeyNameFromFile`
- size: `585`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, unsigned int, _QWORD *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800528f4`
- `0x180052b74`
- `0x180052f84`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180010530`
- `0x180010cc0`
- `0x180019d90`
- `0x1800398b0`
- `0x1800532a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005336b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005336b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800534ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800534ba`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005335b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005335b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180053306`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180053306`

## string_xrefs

- `0x18005349a`: `onecore\ds\security\cryptoapi\ncrypt\storage\enum.c`

## pseudocode

```c
__int64 __fastcall ReadKeyNameFromFile(_WORD *a1, _WORD *a2, unsigned int a3, _QWORD *a4)
{
  _DWORD *v4; // rsi
  unsigned int LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  DWORD FileSize; // ebx
  _DWORD *v10; // rax
  __int64 v11; // rcx
  __int64 SupportedAlgById; // rax
  int v13; // ebp
  size_t v14; // rbx
  _WORD *v15; // r12
  __int64 v16; // rax
  __int64 v17; // r13
  _QWORD *v18; // rax
  _QWORD *v19; // r15
  _QWORD *v20; // rdi
  char *v21; // rdi
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hFile[6]; // [rsp+38h] [rbp-30h] BYREF

  hFile[0] = (HANDLE)-1LL;
  NumberOfBytesRead = 0;
  v4 = 0;
  LastError = OpenFileInStorageArea(a3, 0x80000000, a1, a2, hFile);
  v6 = LastError;
  if ( !LastError )
  {
    FileSize = GetFileSize(hFile[0], 0);
    if ( FileSize - 44 > 0xFFFFD4 )
    {
      v7 = 1921;
    }
    else
    {
      v10 = (_DWORD *)SafeAllocaAllocateFromHeap(FileSize);
      v4 = v10;
      if ( !v10 )
      {
        v7 = 1930;
LABEL_7:
        v6 = -2146893810;
        v8 = 2148073486LL;
        goto LABEL_30;
      }
      if ( !ReadFile(hFile[0], v10, FileSize, &NumberOfBytesRead, 0) )
      {
        LastError = GetLastError();
        v6 = LastError;
        v7 = 1941;
        goto LABEL_3;
      }
      if ( NumberOfBytesRead == FileSize )
      {
        LastError = KspValidateKeyFile(v4, FileSize);
        v6 = LastError;
        if ( LastError )
        {
          v7 = 1963;
          goto LABEL_3;
        }
        v11 = (unsigned int)v4[3];
        if ( (_DWORD)v11 || (v11 = (unsigned int)v4[7], (_DWORD)v11) )
        {
          SupportedAlgById = KspFindSupportedAlgById(v11);
          if ( SupportedAlgById )
          {
            v13 = *(_DWORD *)(SupportedAlgById + 56);
            v14 = (unsigned int)v4[2];
            v15 = *(_WORD **)SupportedAlgById;
            if ( v13 && v4[7] )
              v13 = 2;
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            v17 = (unsigned int)(2 * v16);
            v18 = (_QWORD *)SafeAllocaAllocateFromHeap((unsigned int)(v17 + v14 + 28));
            v19 = v18;
            if ( v18 )
            {
              v20 = v18 + 3;
              *v18 = v18 + 3;
              memcpy_0(v18 + 3, v4 + 11, v14);
              *(_WORD *)((char *)v20 + v14) = 0;
              v21 = (char *)v20 + v14 + 2;
              v19[1] = v21;
              memcpy_0(v21, v15, (unsigned int)v17);
              *(_WORD *)&v21[v17] = 0;
              v6 = 0;
              *((_DWORD *)v19 + 4) = v13;
              *((_DWORD *)v19 + 5) = 0;
              *a4 = v19;
              goto LABEL_31;
            }
            v7 = 2022;
            goto LABEL_7;
          }
          v7 = 1996;
        }
        else
        {
          v7 = 1988;
        }
        v6 = -2146893811;
        v8 = 2148073485LL;
        goto LABEL_30;
      }
      v7 = 1948;
    }
    v8 = 2148073498LL;
    v6 = -2146893798;
    goto LABEL_30;
  }
  v7 = 1910;
LABEL_3:
  v8 = LastError;
LABEL_30:
  DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\enum.c", v7);
LABEL_31:
  if ( hFile[0] != (HANDLE)-1LL )
    CloseHandle(hFile[0]);
  if ( v4 )
    MSCryptFree(v4);
  return v6;
}

```

## disassembly

```asm
0x1800532a4  mov     r11, rsp
0x1800532a7  mov     [r11+8], rbx
0x1800532ab  mov     [r11+10h], rbp
0x1800532af  mov     [r11+20h], r9
0x1800532b3  push    rsi
0x1800532b4  push    rdi
0x1800532b5  push    r12
0x1800532b7  push    r13
0x1800532b9  push    r15
0x1800532bb  sub     rsp, 40h
0x1800532bf  mov     eax, r8d
0x1800532c2  mov     qword ptr [r11-30h], 0FFFFFFFFFFFFFFFFh
0x1800532ca  lea     r8, [r11-30h]
0x1800532ce  xor     edi, edi
0x1800532d0  mov     [r11-48h], r8
0x1800532d4  mov     r9, rdx
0x1800532d7  mov     r8, rcx
0x1800532da  mov     [rsp+68h+NumberOfBytesRead], edi
0x1800532de  mov     ecx, eax
0x1800532e0  mov     edx, 80000000h
0x1800532e5  mov     esi, edi
0x1800532e7  call    OpenFileInStorageArea
0x1800532ec  mov     ebx, eax
0x1800532ee  test    eax, eax
0x1800532f0  jz      short loc_1800532FF
0x1800532f2  mov     r9d, 776h
0x1800532f8  mov     ecx, eax
0x1800532fa  jmp     loc_18005349A
0x1800532ff  mov     rcx, [rsp+68h+hFile]; hFile
0x180053304  xor     edx, edx; lpFileSizeHigh
0x180053306  call    cs:__imp_GetFileSize
0x18005330d  nop     dword ptr [rax+rax+00h]
0x180053312  mov     ebx, eax
0x180053314  lea     eax, [rbx-2Ch]
0x180053317  cmp     eax, 0FFFFD4h
0x18005331c  ja      loc_18005348A
0x180053322  mov     ecx, ebx
0x180053324  call    SafeAllocaAllocateFromHeap
0x180053329  mov     rsi, rax
0x18005332c  test    rax, rax
0x18005332f  jnz     short loc_180053346
0x180053331  mov     r9d, 78Ah
0x180053337  mov     ebx, 8009000Eh
0x18005333c  mov     ecx, 8009000Eh
0x180053341  jmp     loc_18005349A
0x180053346  mov     rcx, [rsp+68h+hFile]; hFile
0x18005334b  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180053350  mov     r8d, ebx; nNumberOfBytesToRead
0x180053353  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x180053358  mov     rdx, rsi; lpBuffer
0x18005335b  call    cs:__imp_ReadFile
0x180053362  nop     dword ptr [rax+rax+00h]
0x180053367  test    eax, eax
0x180053369  jnz     short loc_180053384
0x18005336b  call    cs:__imp_GetLastError
0x180053372  nop     dword ptr [rax+rax+00h]
0x180053377  mov     ebx, eax
0x180053379  mov     r9d, 795h
0x18005337f  jmp     loc_1800532F8
0x180053384  cmp     [rsp+68h+NumberOfBytesRead], ebx
0x180053388  jz      short loc_180053395
0x18005338a  mov     r9d, 79Ch
0x180053390  jmp     loc_180053490
0x180053395  mov     edx, ebx
0x180053397  mov     rcx, rsi
0x18005339a  call    KspValidateKeyFile
0x18005339f  mov     ebx, eax
0x1800533a1  test    eax, eax
0x1800533a3  jz      short loc_1800533B0
0x1800533a5  mov     r9d, 7ABh
0x1800533ab  jmp     loc_1800532F8
0x1800533b0  mov     ecx, [rsi+0Ch]
0x1800533b3  test    ecx, ecx
0x1800533b5  jnz     short loc_1800533C2
0x1800533b7  mov     ecx, [rsi+1Ch]
0x1800533ba  test    ecx, ecx
0x1800533bc  jz      loc_18005347F
0x1800533c2  call    KspFindSupportedAlgById
0x1800533c7  test    rax, rax
0x1800533ca  jnz     short loc_1800533E1
0x1800533cc  mov     r9d, 7CCh
0x1800533d2  mov     ebx, 8009000Dh
0x1800533d7  mov     ecx, 8009000Dh
0x1800533dc  jmp     loc_18005349A
0x1800533e1  mov     ebp, [rax+38h]
0x1800533e4  mov     ebx, [rsi+8]
0x1800533e7  mov     r12, [rax]
0x1800533ea  test    ebp, ebp
0x1800533ec  jz      short loc_1800533F9
0x1800533ee  cmp     [rsi+1Ch], edi
0x1800533f1  mov     eax, 2
0x1800533f6  cmovnz  ebp, eax
0x1800533f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800533fd  inc     rax
0x180053400  cmp     [r12+rax*2], di
0x180053405  jnz     short loc_1800533FD
0x180053407  lea     r13d, [rax+rax]
0x18005340b  lea     ecx, [rbx+1Ch]
0x18005340e  add     ecx, r13d
0x180053411  call    SafeAllocaAllocateFromHeap
0x180053416  mov     r15, rax
0x180053419  test    rax, rax
0x18005341c  jnz     short loc_180053429
0x18005341e  mov     r9d, 7E6h
0x180053424  jmp     loc_180053337
0x180053429  lea     rdi, [rax+18h]
0x18005342d  mov     r8, rbx; Size
0x180053430  mov     rcx, rdi; void *
0x180053433  mov     [rax], rdi
0x180053436  lea     rdx, [rsi+2Ch]; Src
0x18005343a  call    memcpy_0
0x18005343f  xor     eax, eax
0x180053441  mov     r8d, r13d; Size
0x180053444  mov     [rbx+rdi], ax
0x180053448  mov     rdx, r12; Src
0x18005344b  add     rdi, 2
0x18005344f  add     rdi, rbx
0x180053452  mov     rcx, rdi; void *
0x180053455  mov     [r15+8], rdi
0x180053459  call    memcpy_0
0x18005345e  xor     eax, eax
0x180053460  mov     [r13+rdi+0], ax
0x180053466  xor     edi, edi
0x180053468  mov     rax, [rsp+68h+arg_18]
0x180053470  mov     ebx, edi
0x180053472  mov     [r15+10h], ebp
0x180053476  mov     [r15+14h], edi
0x18005347a  mov     [rax], r15
0x18005347d  jmp     short loc_1800534AD
0x18005347f  mov     r9d, 7C4h
0x180053485  jmp     loc_1800533D2
0x18005348a  mov     r9d, 781h
0x180053490  mov     ecx, 8009001Ah
0x180053495  mov     ebx, 8009001Ah
0x18005349a  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800534a1  lea     rdx, aStatus; "Status"
0x1800534a8  call    DebugTraceError
0x1800534ad  cmp     [rsp+68h+hFile], 0FFFFFFFFFFFFFFFFh
0x1800534b3  jz      short loc_1800534C6
0x1800534b5  mov     rcx, [rsp+68h+hFile]; hObject
0x1800534ba  call    cs:__imp_CloseHandle
0x1800534c1  nop     dword ptr [rax+rax+00h]
0x1800534c6  test    rsi, rsi
0x1800534c9  jz      short loc_1800534D3
0x1800534cb  mov     rcx, rsi
0x1800534ce  call    MSCryptFree
0x1800534d3  mov     rbp, [rsp+68h+arg_8]
0x1800534d8  mov     eax, ebx
0x1800534da  mov     rbx, [rsp+68h+arg_0]
0x1800534df  add     rsp, 40h
0x1800534e3  pop     r15
0x1800534e5  pop     r13
0x1800534e7  pop     r12
0x1800534e9  pop     rdi
0x1800534ea  pop     rsi
0x1800534eb  retn
```
