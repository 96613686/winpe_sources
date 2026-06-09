# FreeDllWaitForCallback(void *,uchar)

- ea: `0x180082bd0`
- end: `0x180082e04`
- name: `?FreeDllWaitForCallback@@YAXPEAXE@Z`
- size: `564`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180082bd0`
- `0x180082e0c`
- `0x180082e70`
- `0x1800bec20`
- `0x1800bf57c`
- `0x180115040`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082d63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082cba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180082d63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082bfb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180082bfb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082dd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082dd6`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180082db9`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180082db9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082d71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082dc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082d71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082dc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180082d9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180082d9e`

## pseudocode

```c
void __fastcall FreeDllWaitForCallback(void *a1)
{
  int *v1; // rbx
  __int64 v2; // rdi
  unsigned int v3; // r15d
  unsigned __int64 v4; // rax
  SIZE_T v5; // rdx
  __int64 v6; // rax
  void *v7; // rsp
  struct _DLL_ELEMENT *v8; // r14
  struct _DLL_ELEMENT *v9; // rsi
  __int64 v11; // rcx
  unsigned int (__fastcall *v12)(__int64); // rax
  _QWORD *i; // rax
  HLOCAL v14; // r14
  HMODULE v15; // rsi
  int *v16; // rax
  __int64 v17; // [rsp+0h] [rbp-20h] BYREF
  int v18; // [rsp+20h] [rbp+0h] BYREF

  v1 = 0;
  v2 = 0;
  EnterCriticalSection(&CriticalSection);
  v3 = dword_1801583A8;
  if ( !dword_1801583A8 )
  {
LABEL_17:
    if ( !qword_1801583A0 && _InterlockedExchange(&dword_1801583AC, 0) )
    {
      v14 = qword_1801583B0;
      v15 = hLibModule;
      qword_1801583B0 = 0;
      hLibModule = 0;
      LeaveCriticalSection(&CriticalSection);
      while ( (_DWORD)v2 )
      {
        LODWORD(v2) = v2 - 1;
        FreeLibrary(*(HMODULE *)&v1[2 * (unsigned int)v2]);
      }
      if ( v1 && *(v1 - 4) == 56797 )
        free(v1 - 4);
      ILS_UnregisterWait(v14);
      if ( v15 )
        FreeLibraryAndExitThread(v15, 0);
      ExitThread(0);
    }
    goto LABEL_18;
  }
  v4 = 8LL * (unsigned int)dword_1801583A8;
  v5 = v4 + 16;
  if ( v4 + 16 < v4 )
    goto LABEL_18;
  if ( v5 > 0x400 )
  {
    v16 = (int *)LocalAlloc(0x40u, v5);
    v1 = v16;
    if ( !v16 )
      goto LABEL_9;
    *v16 = 56797;
LABEL_8:
    v1 += 4;
LABEL_9:
    if ( !v1 )
      goto LABEL_18;
    v8 = qword_1801583A0;
    while ( v8 )
    {
      v9 = v8;
      v8 = (struct _DLL_ELEMENT *)*((_QWORD *)v8 + 8);
      if ( (*((_DWORD *)v9 + 14))-- == 1 )
      {
        RemoveFreeDll(v9);
        if ( *((_DWORD *)v9 + 9) )
        {
          v12 = (unsigned int (__fastcall *)(__int64))*((_QWORD *)v9 + 6);
          if ( (!v12 || !v12(v11)) && (unsigned int)v2 < v3 )
          {
            for ( i = (_QWORD *)*((_QWORD *)v9 + 5); i; i = (_QWORD *)*i )
              i[3] = 0;
            *((_QWORD *)v9 + 6) = 0;
            *(_QWORD *)&v1[2 * v2] = *((_QWORD *)v9 + 3);
            v2 = (unsigned int)(v2 + 1);
            *((_QWORD *)v9 + 3) = 0;
            *((_DWORD *)v9 + 9) = 0;
          }
        }
      }
    }
    goto LABEL_17;
  }
  v6 = v4 + 31;
  if ( v5 + 15 < v5 )
    v6 = 0xFFFFFFFFFFFFFF0LL;
  v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
  v1 = &v18;
  if ( &v17 != (__int64 *)-32LL )
  {
    v18 = 52428;
    goto LABEL_8;
  }
LABEL_18:
  LeaveCriticalSection(&CriticalSection);
  while ( (_DWORD)v2 )
  {
    LODWORD(v2) = v2 - 1;
    FreeLibrary(*(HMODULE *)&v1[2 * (unsigned int)v2]);
  }
  if ( v1 && *(v1 - 4) == 56797 )
    free(v1 - 4);
}

```

## disassembly

```asm
0x180082bd0  push    rbp
0x180082bd2  push    rbx
0x180082bd3  push    rsi
0x180082bd4  push    rdi
0x180082bd5  push    r14
0x180082bd7  push    r15
0x180082bd9  sub     rsp, 38h
0x180082bdd  lea     rbp, [rsp+20h]
0x180082be2  mov     rax, cs:__security_cookie
0x180082be9  xor     rax, rbp
0x180082bec  mov     [rbp+40h+var_38], rax
0x180082bf0  lea     rcx, CriticalSection; lpCriticalSection
0x180082bf7  xor     ebx, ebx
0x180082bf9  xor     edi, edi
0x180082bfb  call    cs:__imp_EnterCriticalSection
0x180082c01  mov     r15d, cs:dword_1801583A8
0x180082c08  test    r15d, r15d
0x180082c0b  jz      loc_180082CA9
0x180082c11  mov     eax, r15d
0x180082c14  shl     rax, 3
0x180082c18  lea     rdx, [rax+10h]; uBytes
0x180082c1c  cmp     rdx, rax
0x180082c1f  jbe     loc_180082CB3
0x180082c25  cmp     rdx, 400h
0x180082c2c  ja      loc_180082DD1
0x180082c32  lea     rax, [rdx+0Fh]
0x180082c36  cmp     rax, rdx
0x180082c39  ja      short loc_180082C45
0x180082c3b  mov     rax, 0FFFFFFFFFFFFFF0h
0x180082c45  and     rax, 0FFFFFFFFFFFFFFF0h
0x180082c49  call    _alloca_probe
0x180082c4e  sub     rsp, rax
0x180082c51  lea     rbx, [rsp+60h+var_40]
0x180082c56  test    rbx, rbx
0x180082c59  jz      short loc_180082CB3
0x180082c5b  mov     dword ptr [rbx], 0CCCCh
0x180082c61  add     rbx, 10h
0x180082c65  test    rbx, rbx
0x180082c68  jz      short loc_180082CB3
0x180082c6a  mov     r14, cs:qword_1801583A0
0x180082c71  test    r14, r14
0x180082c74  jz      short loc_180082CA9
0x180082c76  mov     rsi, r14
0x180082c79  mov     r14, [r14+40h]
0x180082c7d  add     dword ptr [rsi+38h], 0FFFFFFFFh
0x180082c81  jnz     short loc_180082C71
0x180082c83  mov     rcx, rsi; struct _DLL_ELEMENT *
0x180082c86  call    ?RemoveFreeDll@@YAXPEAU_DLL_ELEMENT@@@Z; RemoveFreeDll(_DLL_ELEMENT *)
0x180082c8b  cmp     dword ptr [rsi+24h], 0
0x180082c8f  jz      short loc_180082C71
0x180082c91  mov     rax, [rsi+30h]
0x180082c95  test    rax, rax
0x180082c98  jnz     loc_180082DA5
0x180082c9e  cmp     edi, r15d
0x180082ca1  jnb     short loc_180082C71
0x180082ca3  mov     rax, [rsi+28h]
0x180082ca7  jmp     short loc_180082D01
0x180082ca9  cmp     cs:qword_1801583A0, 0
0x180082cb1  jz      short loc_180082D28
0x180082cb3  lea     rcx, CriticalSection; lpCriticalSection
0x180082cba  call    cs:__imp_LeaveCriticalSection
0x180082cc0  test    edi, edi
0x180082cc2  jnz     loc_180082DC0
0x180082cc8  test    rbx, rbx
0x180082ccb  jz      short loc_180082CDD
0x180082ccd  lea     rcx, [rbx-10h]; Block
0x180082cd1  cmp     dword ptr [rcx], 0DDDDh
0x180082cd7  jz      loc_180082DFA
0x180082cdd  mov     rcx, [rbp+40h+var_38]
0x180082ce1  xor     rcx, rbp; StackCookie
0x180082ce4  call    __security_check_cookie
0x180082ce9  lea     rsp, [rbp+18h]
0x180082ced  pop     r15
0x180082cef  pop     r14
0x180082cf1  pop     rdi
0x180082cf2  pop     rsi
0x180082cf3  pop     rbx
0x180082cf4  pop     rbp
0x180082cf5  retn
0x180082cf6  mov     qword ptr [rax+18h], 0
0x180082cfe  mov     rax, [rax]
0x180082d01  test    rax, rax
0x180082d04  jnz     short loc_180082CF6
0x180082d06  mov     [rsi+30h], rax
0x180082d0a  mov     rax, [rsi+18h]
0x180082d0e  mov     [rbx+rdi*8], rax
0x180082d12  inc     edi
0x180082d14  mov     qword ptr [rsi+18h], 0
0x180082d1c  mov     dword ptr [rsi+24h], 0
0x180082d23  jmp     loc_180082C71
0x180082d28  xor     eax, eax
0x180082d2a  xchg    eax, cs:dword_1801583AC
0x180082d30  test    eax, eax
0x180082d32  jz      loc_180082CB3
0x180082d38  mov     r14, cs:qword_1801583B0
0x180082d3f  lea     rcx, CriticalSection; lpCriticalSection
0x180082d46  mov     rsi, cs:hLibModule
0x180082d4d  mov     cs:qword_1801583B0, 0
0x180082d58  mov     cs:hLibModule, 0
0x180082d63  call    cs:__imp_LeaveCriticalSection
0x180082d69  jmp     short loc_180082D77
0x180082d6b  dec     edi
0x180082d6d  mov     rcx, [rbx+rdi*8]; hLibModule
0x180082d71  call    cs:__imp_FreeLibrary
0x180082d77  test    edi, edi
0x180082d79  jnz     short loc_180082D6B
0x180082d7b  test    rbx, rbx
0x180082d7e  jz      short loc_180082D8C
0x180082d80  lea     rcx, [rbx-10h]; Block
0x180082d84  cmp     dword ptr [rcx], 0DDDDh
0x180082d8a  jz      short loc_180082DF3
0x180082d8c  mov     rcx, r14; hMem
0x180082d8f  call    ?ILS_UnregisterWait@@YAHPEAX@Z; ILS_UnregisterWait(void *)
0x180082d94  test    rsi, rsi
0x180082d97  jz      short loc_180082DB7
0x180082d99  xor     edx, edx; dwExitCode
0x180082d9b  mov     rcx, rsi; hLibModule
0x180082d9e  call    cs:__imp_FreeLibraryAndExitThread
0x180082da4  int     3; Trap to Debugger
0x180082da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082daa  test    eax, eax
0x180082dac  jz      loc_180082C9E
0x180082db2  jmp     loc_180082C71
0x180082db7  xor     ecx, ecx; dwExitCode
0x180082db9  call    cs:__imp_ExitThread
0x180082dc0  dec     edi
0x180082dc2  mov     rcx, [rbx+rdi*8]; hLibModule
0x180082dc6  call    cs:__imp_FreeLibrary
0x180082dcc  jmp     loc_180082CC0
0x180082dd1  mov     ecx, 40h ; '@'; uFlags
0x180082dd6  call    cs:__imp_LocalAlloc
0x180082ddc  mov     rbx, rax
0x180082ddf  test    rax, rax
0x180082de2  jz      loc_180082C65
0x180082de8  mov     dword ptr [rax], 0DDDDh
0x180082dee  jmp     loc_180082C61
0x180082df3  call    free
0x180082df8  jmp     short loc_180082D8C
0x180082dfa  call    free
0x180082dff  jmp     loc_180082CDD
```
