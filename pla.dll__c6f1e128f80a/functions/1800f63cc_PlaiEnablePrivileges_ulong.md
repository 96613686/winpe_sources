# PlaiEnablePrivileges(ulong,...)

- ea: `0x1800f63cc`
- end: `0x1800f67c5`
- name: `?PlaiEnablePrivileges@@YAJKZZ`
- size: `1017`
- prototype: `__int64(unsigned int, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800018b0`
- `0x180054450`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x1800f63cc`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f64ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f64ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f6699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f678a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f678a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f64f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f64f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f64e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f64e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f6426`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f6426`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f6410`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f6410`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800f6687`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800f6687`

## string_xrefs

- `0x1800f6747`: `PlaiEnablePrivileges`

## pseudocode

```c
__int64 PlaiEnablePrivileges(DWORD a1, ...)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  int v3; // eax
  unsigned int v4; // ebx
  struct _TOKEN_PRIVILEGES *v5; // rdi
  __int64 v6; // rax
  int *v7; // rcx
  int *v8; // r9
  HANDLE CurrentProcess; // rax
  DWORD v10; // eax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  va_list v14; // r8
  DWORD i; // edx
  __int64 v16; // rax
  __int64 v17; // rcx
  DWORD v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int PreviousState; // [rsp+28h] [rbp-E0h]
  int v23; // [rsp+78h] [rbp-90h] BYREF
  int v24; // [rsp+80h] [rbp-88h] BYREF
  void *TokenHandle[2]; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int16 v26[64]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 v27[64]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 v28[64]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int16 v29[64]; // [rsp+218h] [rbp+110h] BYREF
  va_list va; // [rsp+2F0h] [rbp+1E8h] BYREF

  va_start(va, a1);
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20u, 0, TokenHandle) )
    goto LABEL_18;
  LastError = GetLastError();
  v3 = PlaiHResultFromWin32(LastError);
  v4 = v3;
  if ( v3 >= 0 )
    goto LABEL_18;
  v5 = 0;
  if ( v3 == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20u, TokenHandle) )
    {
      v10 = GetLastError();
      v11 = PlaiHResultFromWin32(v10);
      v4 = v11;
      if ( v11 < 0 )
      {
        v24 = 0;
        v23 = v11;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_37;
        }
        PlaiWhoAmI(v27, 0x4000000000000800uLL);
        v12 = -1;
        do
          ++v12;
        while ( v27[v12] );
        goto LABEL_35;
      }
    }
LABEL_18:
    v5 = (struct _TOKEN_PRIVILEGES *)PlaiAlloc(12LL * a1 + 16, 1, 0, qword_180147320, PreviousState);
    if ( v5 )
    {
      va_copy(v14, va);
      v5->PrivilegeCount = a1;
      for ( i = 0; i < a1; v5->Privileges[v17].Luid = (LUID)*((unsigned int *)v14 - 2) )
      {
        v16 = i;
        v14 += 8;
        ++i;
        v17 = v16;
        v5->Privileges[v17].Attributes = 2;
      }
      if ( AdjustTokenPrivileges(TokenHandle[0], 0, v5, 0, 0, 0) )
      {
        v4 = 0;
        goto LABEL_37;
      }
      v18 = GetLastError();
      v19 = PlaiHResultFromWin32(v18);
      v4 = v19;
      if ( v19 >= 0 )
        goto LABEL_37;
      v24 = 0;
      v23 = v19;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_37;
      }
      PlaiWhoAmI(v29, 0x4000000000000800uLL);
      v20 = -1;
      do
        ++v20;
      while ( v29[v20] );
    }
    else
    {
      v4 = -2147024882;
      v23 = -2147024882;
      v24 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_37;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v28[v13] );
    }
LABEL_35:
    v8 = &v23;
    v7 = &v24;
LABEL_36:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v8, 4, qword_180147320, 1, v7, 4, "PlaiEnablePrivileges", 21);
    goto LABEL_37;
  }
  v23 = 0;
  v24 = v3;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v26, 0x4000000000000800uLL);
    v6 = -1;
    do
      ++v6;
    while ( v26[v6] );
    v7 = &v23;
    v8 = &v24;
    goto LABEL_36;
  }
LABEL_37:
  if ( TokenHandle[0] )
  {
    CloseHandle(TokenHandle[0]);
    TokenHandle[0] = 0;
  }
  if ( v5 )
    PlaiFree(v5, 1);
  return v4;
}

```

## disassembly

```asm
0x1800f63cc  mov     rax, rsp
0x1800f63cf  mov     [rax+8], ecx
0x1800f63d2  mov     [rax+10h], rdx
0x1800f63d6  mov     [rax+18h], r8
0x1800f63da  mov     [rax+20h], r9
0x1800f63de  push    rbp
0x1800f63df  push    rbx
0x1800f63e0  push    rsi
0x1800f63e1  push    rdi
0x1800f63e2  push    r14
0x1800f63e4  push    r15
0x1800f63e6  lea     rbp, [rax-1D8h]
0x1800f63ed  sub     rsp, 2A8h
0x1800f63f4  mov     rax, cs:__security_cookie
0x1800f63fb  xor     rax, rsp
0x1800f63fe  mov     [rbp+1D0h+var_40], rax
0x1800f6405  xor     r14d, r14d
0x1800f6408  mov     [rbp+1D0h+TokenHandle], r14
0x1800f640c  mov     [rbp+1D0h+TokenHandle], r14
0x1800f6410  call    cs:__imp_GetCurrentThread
0x1800f6416  lea     esi, [r14+20h]
0x1800f641a  xor     r8d, r8d; OpenAsSelf
0x1800f641d  mov     rcx, rax; ThreadHandle
0x1800f6420  lea     r9, [rbp+1D0h+TokenHandle]; TokenHandle
0x1800f6424  mov     edx, esi; DesiredAccess
0x1800f6426  call    cs:__imp_OpenThreadToken
0x1800f642c  lea     r15d, [r14+1]
0x1800f6430  test    eax, eax
0x1800f6432  jnz     loc_1800F6584
0x1800f6438  call    cs:__imp_GetLastError
0x1800f643e  mov     ecx, eax; unsigned int
0x1800f6440  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f6445  mov     ebx, eax
0x1800f6447  test    eax, eax
0x1800f6449  jns     loc_1800F6584
0x1800f644f  mov     edi, r14d
0x1800f6452  cmp     eax, 800703F0h
0x1800f6457  jz      loc_1800F64E2
0x1800f645d  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f6464  mov     [rsp+2D0h+var_260], r14d
0x1800f6469  mov     [rsp+2D0h+var_258], eax
0x1800f646d  jz      loc_1800F6781
0x1800f6473  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f647d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f6484  jz      loc_1800F6781
0x1800f648a  mov     rax, cs:qword_180169748
0x1800f6491  and     rax, rdx
0x1800f6494  cmp     cs:qword_180169748, rax
0x1800f649b  jnz     loc_1800F6781
0x1800f64a1  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x1800f64a5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f64aa  lea     rcx, [rbp+1D0h+var_240]
0x1800f64ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f64b2  inc     rax
0x1800f64b5  cmp     [rcx+rax*2], r14w
0x1800f64ba  jnz     short loc_1800F64B2
0x1800f64bc  lea     ecx, [rax+rax]
0x1800f64bf  add     rcx, 2
0x1800f64c3  lea     rax, [rbp+1D0h+var_240]
0x1800f64c7  mov     [rsp+60h], rcx
0x1800f64cc  lea     rsi, qword_180147320
0x1800f64d3  lea     rcx, [rsp+2D0h+var_260]
0x1800f64d8  lea     r9, [rsp+2D0h+var_258]
0x1800f64dd  jmp     loc_1800F6732
0x1800f64e2  call    cs:__imp_GetCurrentProcess
0x1800f64e8  lea     r8, [rbp+1D0h+TokenHandle]; TokenHandle
0x1800f64ec  mov     edx, esi; DesiredAccess
0x1800f64ee  mov     rcx, rax; ProcessHandle
0x1800f64f1  call    cs:__imp_OpenProcessToken
0x1800f64f7  test    eax, eax
0x1800f64f9  jnz     loc_1800F6584
0x1800f64ff  call    cs:__imp_GetLastError
0x1800f6505  mov     ecx, eax; unsigned int
0x1800f6507  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f650c  mov     ebx, eax
0x1800f650e  test    eax, eax
0x1800f6510  jns     short loc_1800F6584
0x1800f6512  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f6519  mov     [rsp+2D0h+var_258], r14d
0x1800f651e  mov     [rsp+2D0h+var_260], eax
0x1800f6522  jz      loc_1800F6781
0x1800f6528  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f6532  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f6539  jz      loc_1800F6781
0x1800f653f  mov     rax, cs:qword_180169748
0x1800f6546  and     rax, rdx
0x1800f6549  cmp     cs:qword_180169748, rax
0x1800f6550  jnz     loc_1800F6781
0x1800f6556  lea     rcx, [rbp+1D0h+var_1C0]; unsigned __int16 *
0x1800f655a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f655f  lea     rcx, [rbp+1D0h+var_1C0]
0x1800f6563  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f6567  inc     rax
0x1800f656a  cmp     [rcx+rax*2], r14w
0x1800f656f  jnz     short loc_1800F6567
0x1800f6571  lea     ecx, [rax+rax]
0x1800f6574  lea     rax, [rbp+1D0h+var_1C0]
0x1800f6578  lea     rsi, qword_180147320
0x1800f657f  jmp     loc_1800F671F
0x1800f6584  mov     eax, [rbp+1D0h+arg_0]
0x1800f658a  lea     rsi, qword_180147320
0x1800f6591  mov     r9, rsi; char *
0x1800f6594  xor     r8d, r8d; int
0x1800f6597  mov     edx, r15d; int
0x1800f659a  lea     rcx, [rax+rax*2]
0x1800f659e  lea     rcx, ds:10h[rcx*4]; dwBytes
0x1800f65a6  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800f65ab  mov     rdi, rax
0x1800f65ae  test    rax, rax
0x1800f65b1  jnz     short loc_1800F662C
0x1800f65b3  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f65ba  mov     ebx, 8007000Eh
0x1800f65bf  mov     [rsp+2D0h+var_260], ebx
0x1800f65c3  mov     [rsp+2D0h+var_258], r14d
0x1800f65c8  jz      loc_1800F6781
0x1800f65ce  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f65d8  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f65df  jz      loc_1800F6781
0x1800f65e5  mov     rax, cs:qword_180169748
0x1800f65ec  and     rax, rdx
0x1800f65ef  cmp     cs:qword_180169748, rax
0x1800f65f6  jnz     loc_1800F6781
0x1800f65fc  lea     rcx, [rbp+1D0h+var_140]; unsigned __int16 *
0x1800f6603  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f6608  lea     rcx, [rbp+1D0h+var_140]
0x1800f660f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f6613  inc     rax
0x1800f6616  cmp     [rcx+rax*2], r14w
0x1800f661b  jnz     short loc_1800F6613
0x1800f661d  lea     ecx, [rax+rax]
0x1800f6620  lea     rax, [rbp+1D0h+var_140]
0x1800f6627  jmp     loc_1800F671F
0x1800f662c  mov     eax, [rbp+1D0h+arg_0]
0x1800f6632  lea     r8, [rbp+1D0h+arg_8]
0x1800f6639  mov     [rdi], eax
0x1800f663b  mov     edx, r14d
0x1800f663e  cmp     [rbp+1D0h+arg_0], r14d
0x1800f6645  jbe     short loc_1800F6671
0x1800f6647  mov     eax, edx
0x1800f6649  lea     r8, [r8+8]
0x1800f664d  add     edx, r15d
0x1800f6650  lea     rcx, [rax+rax*2]
0x1800f6654  mov     dword ptr [rdi+rcx*4+0Ch], 2
0x1800f665c  mov     eax, [r8-8]
0x1800f6660  mov     [rdi+rcx*4+4], eax
0x1800f6664  mov     [rdi+rcx*4+8], r14d
0x1800f6669  cmp     edx, [rbp+1D0h+arg_0]
0x1800f666f  jb      short loc_1800F6647
0x1800f6671  mov     rcx, [rbp+1D0h+TokenHandle]; TokenHandle
0x1800f6675  xor     r9d, r9d; BufferLength
0x1800f6678  mov     [rsp+2D0h+ReturnLength], r14; ReturnLength
0x1800f667d  mov     r8, rdi; NewState
0x1800f6680  xor     edx, edx; DisableAllPrivileges
0x1800f6682  mov     [rsp+2D0h+PreviousState], r14; PreviousState
0x1800f6687  call    cs:__imp_AdjustTokenPrivileges
0x1800f668d  test    eax, eax
0x1800f668f  jz      short loc_1800F6699
0x1800f6691  mov     ebx, r14d
0x1800f6694  jmp     loc_1800F6781
0x1800f6699  call    cs:__imp_GetLastError
0x1800f669f  mov     ecx, eax; unsigned int
0x1800f66a1  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f66a6  mov     ebx, eax
0x1800f66a8  test    eax, eax
0x1800f66aa  jns     loc_1800F6781
0x1800f66b0  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f66b7  mov     [rsp+2D0h+var_258], r14d
0x1800f66bc  mov     [rsp+2D0h+var_260], eax
0x1800f66c0  jz      loc_1800F6781
0x1800f66c6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f66d0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f66d7  jz      loc_1800F6781
0x1800f66dd  mov     rax, cs:qword_180169748
0x1800f66e4  and     rax, rdx
0x1800f66e7  cmp     cs:qword_180169748, rax
0x1800f66ee  jnz     loc_1800F6781
0x1800f66f4  lea     rcx, [rbp+1D0h+var_C0]; unsigned __int16 *
0x1800f66fb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f6700  lea     rcx, [rbp+1D0h+var_C0]
0x1800f6707  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f670b  inc     rax
0x1800f670e  cmp     [rcx+rax*2], r14w
0x1800f6713  jnz     short loc_1800F670B
0x1800f6715  lea     ecx, [rax+rax]
0x1800f6718  lea     rax, [rbp+1D0h+var_C0]
0x1800f671f  add     rcx, 2
0x1800f6723  lea     r9, [rsp+2D0h+var_260]
0x1800f6728  mov     [rsp+60h], rcx
0x1800f672d  lea     rcx, [rsp+2D0h+var_258]
0x1800f6732  mov     [rsp+2D0h+var_278], rax
0x1800f6737  lea     rdx, PLA_EVENT_ERROR
0x1800f673e  mov     [rsp+2D0h+var_280], 15h
0x1800f6747  lea     rax, aPlaienablepriv; "PlaiEnablePrivileges"
0x1800f674e  mov     [rsp+2D0h+var_288], rax
0x1800f6753  mov     eax, 4
0x1800f6758  mov     [rsp+2D0h+var_290], rax
0x1800f675d  mov     [rsp+2D0h+var_298], rcx
0x1800f6762  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f6769  mov     [rsp+2D0h+var_2A0], r15
0x1800f676e  mov     [rsp+2D0h+ReturnLength], rsi
0x1800f6773  lea     r8d, [rax+1]
0x1800f6777  mov     [rsp+2D0h+PreviousState], rax
0x1800f677c  call    EventingWriteEvent
0x1800f6781  mov     rcx, [rbp+1D0h+TokenHandle]; hObject
0x1800f6785  test    rcx, rcx
0x1800f6788  jz      short loc_1800F6794
0x1800f678a  call    cs:__imp_CloseHandle
0x1800f6790  mov     [rbp+1D0h+TokenHandle], r14
0x1800f6794  test    rdi, rdi
0x1800f6797  jz      short loc_1800F67A4
0x1800f6799  mov     edx, r15d; int
0x1800f679c  mov     rcx, rdi; lpMem
0x1800f679f  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800f67a4  mov     eax, ebx
0x1800f67a6  mov     rcx, [rbp+1D0h+var_40]
0x1800f67ad  xor     rcx, rsp; StackCookie
0x1800f67b0  call    __security_check_cookie
0x1800f67b5  add     rsp, 2A8h
0x1800f67bc  pop     r15
0x1800f67be  pop     r14
0x1800f67c0  pop     rdi
0x1800f67c1  pop     rsi
0x1800f67c2  pop     rbx
0x1800f67c3  pop     rbp
0x1800f67c4  retn
```
