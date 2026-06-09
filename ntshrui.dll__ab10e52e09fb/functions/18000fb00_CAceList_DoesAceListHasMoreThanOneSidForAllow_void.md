# CAceList::DoesAceListHasMoreThanOneSidForAllow(void)

- ea: `0x18000fb00`
- end: `0x18000fde1`
- name: `?DoesAceListHasMoreThanOneSidForAllow@CAceList@@QEAA_NXZ`
- size: `737`
- prototype: `bool __fastcall(CAceList *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bea0`
- `0x18000c6f0`

## callees

- `0x18000f720`
- `0x18000f7a0`
- `0x18000fb00`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fcd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fdac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fcd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fd45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fdac`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fc36`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fc6c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fc36`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fc6c`

## pseudocode

```c
char __fastcall CAceList::DoesAceListHasMoreThanOneSidForAllow(CAceList *this)
{
  int *v1; // rbx
  void *v2; // r14
  FARPROC v4; // rax
  HMODULE v5; // r8
  int v6; // edi
  _DWORD *v7; // rbx
  int v8; // ecx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rbx
  FARPROC ProcAddress; // rax
  __int64 v13; // rax
  int i; // ebx
  struct _DPA *v15; // rcx
  int v16; // eax
  PSID *Ptr; // rax
  void *v18; // rax
  HMODULE v20; // rcx

  v1 = (int *)*((_QWORD *)this + 1);
  v2 = 0;
  if ( v1 && *v1 > 0 )
  {
    ProcAddress = (FARPROC)qword_180095A20;
    if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
    {
      v20 = g_hinstCC;
      if ( !g_hinstCC )
      {
        DelayLoadCC();
        v20 = g_hinstCC;
        if ( !g_hinstCC )
        {
          qword_180095A20 = 0;
          goto LABEL_54;
        }
      }
      ProcAddress = GetProcAddress(v20, (LPCSTR)0x14C);
      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
    }
    if ( ProcAddress )
    {
      v13 = ((__int64 (__fastcall *)(int *, _QWORD))ProcAddress)(v1, 0);
      goto LABEL_21;
    }
LABEL_54:
    v13 = 0;
LABEL_21:
    v2 = *(void **)(v13 + 8);
    for ( i = 1; ; ++i )
    {
      v15 = (struct _DPA *)*((_QWORD *)this + 1);
      v16 = v15 ? *(_DWORD *)v15 : 0;
      if ( i >= v16 )
        break;
      Ptr = (PSID *)DPA_GetPtr(v15, i);
      if ( !EqualSid(v2, Ptr[1]) )
        return 1;
    }
  }
  if ( !*((_QWORD *)this + 2) )
    return 0;
  v4 = (FARPROC)qword_180095A20;
  v5 = g_hinstCC;
  v6 = 0;
  while ( 1 )
  {
    v7 = (_DWORD *)*((_QWORD *)this + 2);
    v8 = v7 ? *v7 : 0;
    if ( v6 >= v8 )
      return 0;
    if ( v4 == (FARPROC)-1LL )
    {
      if ( v5 || (DelayLoadCC(), (v5 = g_hinstCC) != 0) )
      {
        v4 = GetProcAddress(v5, (LPCSTR)0x14C);
        v5 = g_hinstCC;
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))v4;
      }
      else
      {
        v4 = 0;
        qword_180095A20 = 0;
      }
    }
    if ( v4 )
    {
      v9 = ((__int64 (__fastcall *)(_DWORD *, _QWORD, HMODULE))v4)(v7, v6, v5);
      v5 = g_hinstCC;
      v10 = v9;
      v4 = (FARPROC)qword_180095A20;
    }
    else
    {
      v10 = 0;
    }
    if ( (*(_BYTE *)(v10 + 28) & 1) != 0 )
    {
      v11 = *((_QWORD *)this + 2);
      if ( v2 )
      {
        if ( v4 != (FARPROC)-1LL )
          goto LABEL_28;
        if ( v5 || (DelayLoadCC(), (v5 = g_hinstCC) != 0) )
        {
          v4 = GetProcAddress(v5, (LPCSTR)0x14C);
          qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))v4;
LABEL_28:
          if ( v4 )
          {
            v18 = (void *)((__int64 (__fastcall *)(__int64, _QWORD, HMODULE))v4)(v11, v6, v5);
            goto LABEL_30;
          }
        }
        else
        {
          qword_180095A20 = 0;
        }
        v18 = 0;
LABEL_30:
        if ( !EqualSid(v2, v18) )
          return 1;
        goto LABEL_15;
      }
      if ( v4 == (FARPROC)-1LL )
      {
        if ( !v5 )
        {
          DelayLoadCC();
          v5 = g_hinstCC;
          if ( !g_hinstCC )
          {
            v4 = 0;
            qword_180095A20 = 0;
            goto LABEL_47;
          }
        }
        v4 = GetProcAddress(v5, (LPCSTR)0x14C);
        v5 = g_hinstCC;
        qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))v4;
      }
      if ( v4 )
      {
        v2 = (void *)((__int64 (__fastcall *)(__int64, _QWORD, HMODULE))v4)(v11, v6, v5);
LABEL_15:
        v5 = g_hinstCC;
        v4 = (FARPROC)qword_180095A20;
        goto LABEL_16;
      }
LABEL_47:
      v2 = 0;
      ++v6;
    }
    else
    {
LABEL_16:
      ++v6;
    }
  }
}

```

## disassembly

```asm
0x18000fb00  mov     [rsp+arg_10], rbx
0x18000fb05  mov     [rsp+arg_18], rsi
0x18000fb0a  push    r14
0x18000fb0c  sub     rsp, 20h
0x18000fb10  mov     rbx, [rcx+8]
0x18000fb14  xor     r14d, r14d
0x18000fb17  mov     rsi, rcx
0x18000fb1a  test    rbx, rbx
0x18000fb1d  jnz     loc_18000FBDA
0x18000fb23  cmp     qword ptr [rsi+10h], 0
0x18000fb28  jz      loc_18000FC9B
0x18000fb2e  mov     rax, cs:qword_180095A20
0x18000fb35  mov     r8, cs:g_hinstCC
0x18000fb3c  mov     [rsp+28h+arg_8], rdi
0x18000fb41  xor     edi, edi
0x18000fb43  mov     [rsp+28h+arg_0], rbp
0x18000fb48  mov     rbx, [rsi+10h]
0x18000fb4c  test    rbx, rbx
0x18000fb4f  jz      loc_18000FDDA
0x18000fb55  mov     ecx, [rbx]
0x18000fb57  cmp     edi, ecx
0x18000fb59  jge     loc_18000FC7E
0x18000fb5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fb63  jz      loc_18000FCAE
0x18000fb69  movsxd  rbp, edi
0x18000fb6c  test    rax, rax
0x18000fb6f  jz      loc_18000FD20
0x18000fb75  mov     rdx, rbp
0x18000fb78  mov     rcx, rbx
0x18000fb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb80  mov     r8, cs:g_hinstCC
0x18000fb87  mov     rcx, rax
0x18000fb8a  mov     rax, cs:qword_180095A20
0x18000fb91  test    byte ptr [rcx+1Ch], 1
0x18000fb95  jz      short loc_18000FBD3
0x18000fb97  mov     rbx, [rsi+10h]
0x18000fb9b  test    r14, r14
0x18000fb9e  jnz     loc_18000FC48
0x18000fba4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fba8  jz      loc_18000FCE9
0x18000fbae  test    rax, rax
0x18000fbb1  jz      loc_18000FD6E
0x18000fbb7  mov     rdx, rbp
0x18000fbba  mov     rcx, rbx
0x18000fbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc2  mov     r14, rax
0x18000fbc5  mov     r8, cs:g_hinstCC
0x18000fbcc  mov     rax, cs:qword_180095A20
0x18000fbd3  inc     edi
0x18000fbd5  jmp     loc_18000FB48
0x18000fbda  cmp     [rbx], r14d
0x18000fbdd  jle     loc_18000FB23
0x18000fbe3  mov     rax, cs:qword_180095A20
0x18000fbea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fbee  jz      loc_18000FD8A
0x18000fbf4  test    rax, rax
0x18000fbf7  jz      loc_18000FDC5
0x18000fbfd  xor     edx, edx
0x18000fbff  mov     rcx, rbx
0x18000fc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc07  mov     r14, [rax+8]
0x18000fc0b  mov     ebx, 1
0x18000fc10  mov     rcx, [rsi+8]; hdpa
0x18000fc14  test    rcx, rcx
0x18000fc17  jz      loc_18000FDCC
0x18000fc1d  mov     eax, [rcx]
0x18000fc1f  cmp     ebx, eax
0x18000fc21  jge     loc_18000FB23
0x18000fc27  movsxd  rdx, ebx; i
0x18000fc2a  call    DPA_GetPtr
0x18000fc2f  mov     rcx, r14; pSid1
0x18000fc32  mov     rdx, [rax+8]; pSid2
0x18000fc36  call    cs:__imp_EqualSid
0x18000fc3c  test    eax, eax
0x18000fc3e  jz      loc_18000FDD3
0x18000fc44  inc     ebx
0x18000fc46  jmp     short loc_18000FC10
0x18000fc48  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fc4c  jz      loc_18000FD27
0x18000fc52  test    rax, rax
0x18000fc55  jz      loc_18000FD83
0x18000fc5b  mov     rdx, rbp
0x18000fc5e  mov     rcx, rbx
0x18000fc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc66  mov     rdx, rax; pSid2
0x18000fc69  mov     rcx, r14; pSid1
0x18000fc6c  call    cs:__imp_EqualSid
0x18000fc72  test    eax, eax
0x18000fc74  jnz     loc_18000FBC5
0x18000fc7a  mov     al, 1
0x18000fc7c  jmp     short loc_18000FC80
0x18000fc7e  xor     al, al
0x18000fc80  mov     rbp, [rsp+28h+arg_0]
0x18000fc85  mov     rdi, [rsp+28h+arg_8]
0x18000fc8a  mov     rbx, [rsp+28h+arg_10]
0x18000fc8f  mov     rsi, [rsp+28h+arg_18]
0x18000fc94  add     rsp, 20h
0x18000fc98  pop     r14
0x18000fc9a  retn
0x18000fc9b  mov     rbx, [rsp+28h+arg_10]
0x18000fca0  xor     al, al
0x18000fca2  mov     rsi, [rsp+28h+arg_18]
0x18000fca7  add     rsp, 20h
0x18000fcab  pop     r14
0x18000fcad  retn
0x18000fcae  test    r8, r8
0x18000fcb1  jnz     short loc_18000FCC8
0x18000fcb3  call    DelayLoadCC
0x18000fcb8  mov     r8, cs:g_hinstCC
0x18000fcbf  test    r8, r8
0x18000fcc2  jz      loc_18000FD57
0x18000fcc8  mov     edx, 14Ch; lpProcName
0x18000fccd  mov     rcx, r8; hModule
0x18000fcd0  call    cs:__imp_GetProcAddress
0x18000fcd6  mov     r8, cs:g_hinstCC
0x18000fcdd  mov     cs:qword_180095A20, rax
0x18000fce4  jmp     loc_18000FB69
0x18000fce9  test    r8, r8
0x18000fcec  jnz     short loc_18000FCFF
0x18000fcee  call    DelayLoadCC
0x18000fcf3  mov     r8, cs:g_hinstCC
0x18000fcfa  test    r8, r8
0x18000fcfd  jz      short loc_18000FD65
0x18000fcff  mov     edx, 14Ch; lpProcName
0x18000fd04  mov     rcx, r8; hModule
0x18000fd07  call    cs:__imp_GetProcAddress
0x18000fd0d  mov     r8, cs:g_hinstCC
0x18000fd14  mov     cs:qword_180095A20, rax
0x18000fd1b  jmp     loc_18000FBAE
0x18000fd20  xor     ecx, ecx
0x18000fd22  jmp     loc_18000FB91
0x18000fd27  test    r8, r8
0x18000fd2a  jnz     short loc_18000FD3D
0x18000fd2c  call    DelayLoadCC
0x18000fd31  mov     r8, cs:g_hinstCC
0x18000fd38  test    r8, r8
0x18000fd3b  jz      short loc_18000FD78
0x18000fd3d  mov     edx, 14Ch; lpProcName
0x18000fd42  mov     rcx, r8; hModule
0x18000fd45  call    cs:__imp_GetProcAddress
0x18000fd4b  mov     cs:qword_180095A20, rax
0x18000fd52  jmp     loc_18000FC52
0x18000fd57  xor     eax, eax
0x18000fd59  mov     cs:qword_180095A20, rax
0x18000fd60  jmp     loc_18000FB69
0x18000fd65  xor     eax, eax
0x18000fd67  mov     cs:qword_180095A20, rax
0x18000fd6e  xor     r14d, r14d
0x18000fd71  inc     edi
0x18000fd73  jmp     loc_18000FB48
0x18000fd78  mov     cs:qword_180095A20, 0
0x18000fd83  xor     eax, eax
0x18000fd85  jmp     loc_18000FC66
0x18000fd8a  mov     rcx, cs:g_hinstCC
0x18000fd91  test    rcx, rcx
0x18000fd94  jnz     short loc_18000FDA7
0x18000fd96  call    DelayLoadCC
0x18000fd9b  mov     rcx, cs:g_hinstCC; hModule
0x18000fda2  test    rcx, rcx
0x18000fda5  jz      short loc_18000FDBE
0x18000fda7  mov     edx, 14Ch; lpProcName
0x18000fdac  call    cs:__imp_GetProcAddress
0x18000fdb2  mov     cs:qword_180095A20, rax
0x18000fdb9  jmp     loc_18000FBF4
0x18000fdbe  mov     cs:qword_180095A20, r14
0x18000fdc5  xor     eax, eax
0x18000fdc7  jmp     loc_18000FC07
0x18000fdcc  xor     eax, eax
0x18000fdce  jmp     loc_18000FC1F
0x18000fdd3  mov     al, 1
0x18000fdd5  jmp     loc_18000FC8A
0x18000fdda  xor     ecx, ecx
0x18000fddc  jmp     loc_18000FB57
```
