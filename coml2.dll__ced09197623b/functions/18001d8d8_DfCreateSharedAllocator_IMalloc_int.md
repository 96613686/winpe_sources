# DfCreateSharedAllocator(IMalloc * *,int)

- ea: `0x18001d8d8`
- end: `0x18001da97`
- name: `?DfCreateSharedAllocator@@YAJPEAPEAUIMalloc@@H@Z`
- size: `447`
- prototype: `__int64 __fastcall(struct IMalloc **, int)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c2ac`
- `0x18001eaa0`
- `0x180036c90`
- `0x18004a130`
- `0x18005ac70`

## callees

- `0x180018680`
- `0x18001d8d8`
- `0x18001f5cc`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001da5c`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18001da5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001da8c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d937`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d920`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d920`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18001d967`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x18001d967`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001da49`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001da49`

## pseudocode

```c
signed int __fastcall DfCreateSharedAllocator(struct IMalloc **a1, int a2)
{
  int v4; // ebx
  struct CSmAllocator *TlsSmAllocator; // rdi
  HANDLE CurrentThread; // rax
  DWORD LowPart; // r9d
  struct _TEB *v8; // rax
  signed int result; // eax
  PVOID v10[5]; // [rsp+30h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+18h] BYREF
  _LUID Luid; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle = 0;
  v10[0] = NtCurrentTeb()->ReservedForOle;
  if ( v10[0] )
  {
    v4 = 0;
  }
  else
  {
    result = InternalTlsAllocData(v10);
    v4 = result;
    if ( result < 0 )
      return result;
  }
  TlsSmAllocator = GetTlsSmAllocator();
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    a2 = 1;
    CloseHandle(TokenHandle);
  }
  if ( (unsigned int)gs_iSharedHeaps > 0x80 || a2 )
  {
    if ( g_pTaskAllocator || (result = CoGetMalloc(1u, &g_pTaskAllocator), v4 = result, result >= 0) )
    {
      *((_QWORD *)TlsSmAllocator + 1) = 0;
      *((_QWORD *)TlsSmAllocator + 2) = 0;
      *((_QWORD *)TlsSmAllocator + 4) = 0;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
      *((_QWORD *)TlsSmAllocator + 3) = 0;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
      *a1 = g_pTaskAllocator;
      return v4;
    }
  }
  else
  {
    Luid = 0;
    if ( AllocateLocallyUniqueId(&Luid) )
    {
      *((_QWORD *)TlsSmAllocator + 1) = 0;
      *((_QWORD *)TlsSmAllocator + 2) = 0;
      *((_QWORD *)TlsSmAllocator + 4) = 0;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
      LowPart = Luid.LowPart;
      *((_QWORD *)TlsSmAllocator + 3) = 0;
      v4 = CSmAllocator::Init(TlsSmAllocator, 0, 0, LowPart, 0);
      if ( v4 >= 0 )
      {
        v8 = NtCurrentTeb();
        *a1 = (struct IMalloc *)TlsSmAllocator;
        *(_QWORD *)v8->ReservedForOle = *((_QWORD *)TlsSmAllocator + 2);
        (*(void (__fastcall **)(struct CSmAllocator *))(*(_QWORD *)TlsSmAllocator + 8LL))(TlsSmAllocator);
      }
      return v4;
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001d8d8  mov     r11, rsp
0x18001d8db  mov     [r11+8], rbx
0x18001d8df  mov     [r11+10h], rbp
0x18001d8e3  push    rsi
0x18001d8e4  push    rdi
0x18001d8e5  push    r14
0x18001d8e7  sub     rsp, 40h
0x18001d8eb  xor     ebp, ebp
0x18001d8ed  mov     esi, edx
0x18001d8ef  mov     [r11+18h], rbp
0x18001d8f3  mov     r14, rcx
0x18001d8f6  mov     rax, gs:30h
0x18001d8ff  mov     r8, [rax+1758h]
0x18001d906  mov     [r11-28h], r8
0x18001d90a  test    r8, r8
0x18001d90d  jz      loc_18001DA57
0x18001d913  mov     ebx, ebp
0x18001d915  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001d91a  mov     rdi, rax
0x18001d91d  mov     [r14], rbp
0x18001d920  call    cs:__imp_GetCurrentThread
0x18001d926  mov     edx, 8; DesiredAccess
0x18001d92b  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18001d930  mov     rcx, rax; ThreadHandle
0x18001d933  lea     r8d, [rdx-7]; OpenAsSelf
0x18001d937  call    cs:__imp_OpenThreadToken
0x18001d93d  test    eax, eax
0x18001d93f  jnz     loc_18001DA82
0x18001d945  cmp     cs:?gs_iSharedHeaps@@3HA, 80h; int gs_iSharedHeaps
0x18001d94f  ja      loc_18001D9DF
0x18001d955  test    esi, esi
0x18001d957  jnz     loc_18001D9DF
0x18001d95d  lea     rcx, [rsp+58h+Luid]; Luid
0x18001d962  mov     qword ptr [rsp+58h+Luid.LowPart], rbp
0x18001d967  call    cs:__imp_AllocateLocallyUniqueId
0x18001d96d  test    eax, eax
0x18001d96f  jz      loc_18001DA6E
0x18001d975  mov     [rdi+8], rbp
0x18001d979  xor     r8d, r8d; unsigned int
0x18001d97c  mov     [rdi+10h], rbp
0x18001d980  xor     edx, edx; void *
0x18001d982  mov     [rdi+20h], rbp
0x18001d986  mov     rax, gs:30h
0x18001d98f  mov     [rsp+58h+var_38], ebp; int
0x18001d993  mov     rcx, [rax+1758h]
0x18001d99a  mov     [rcx], rbp
0x18001d99d  mov     rcx, rdi; this
0x18001d9a0  mov     r9d, [rsp+58h+Luid.LowPart]; unsigned int
0x18001d9a5  mov     [rdi+18h], rbp
0x18001d9a9  call    ?Init@CSmAllocator@@QEAAJPEAXKKH@Z; CSmAllocator::Init(void *,ulong,ulong,int)
0x18001d9ae  mov     ebx, eax
0x18001d9b0  test    eax, eax
0x18001d9b2  js      short loc_18001DA28
0x18001d9b4  mov     rax, gs:30h
0x18001d9bd  mov     [r14], rdi
0x18001d9c0  mov     rcx, [rax+1758h]
0x18001d9c7  mov     rax, [rdi+10h]
0x18001d9cb  mov     [rcx], rax
0x18001d9ce  mov     rcx, rdi
0x18001d9d1  mov     rax, [rdi]
0x18001d9d4  mov     rax, [rax+8]
0x18001d9d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9dd  jmp     short loc_18001DA28
0x18001d9df  cmp     cs:?g_pTaskAllocator@@3PEAUIMalloc@@EA, rbp; IMalloc * g_pTaskAllocator
0x18001d9e6  jz      short loc_18001DA3D
0x18001d9e8  mov     [rdi+8], rbp
0x18001d9ec  mov     [rdi+10h], rbp
0x18001d9f0  mov     [rdi+20h], rbp
0x18001d9f4  mov     rax, gs:30h
0x18001d9fd  mov     rcx, [rax+1758h]
0x18001da04  mov     [rcx], rbp
0x18001da07  mov     [rdi+18h], rbp
0x18001da0b  mov     rax, gs:30h
0x18001da14  mov     rcx, [rax+1758h]
0x18001da1b  mov     [rcx], rbp
0x18001da1e  mov     rax, cs:?g_pTaskAllocator@@3PEAUIMalloc@@EA; IMalloc * g_pTaskAllocator
0x18001da25  mov     [r14], rax
0x18001da28  mov     eax, ebx
0x18001da2a  mov     rbx, [rsp+58h+arg_0]
0x18001da2f  mov     rbp, [rsp+58h+arg_8]
0x18001da34  add     rsp, 40h
0x18001da38  pop     r14
0x18001da3a  pop     rdi
0x18001da3b  pop     rsi
0x18001da3c  retn
0x18001da3d  lea     rdx, ?g_pTaskAllocator@@3PEAUIMalloc@@EA; ppMalloc
0x18001da44  mov     ecx, 1; dwMemContext
0x18001da49  call    cs:__imp_CoGetMalloc
0x18001da4f  mov     ebx, eax
0x18001da51  test    eax, eax
0x18001da53  js      short loc_18001DA2A
0x18001da55  jmp     short loc_18001D9E8
0x18001da57  lea     rcx, [rsp+58h+var_28]
0x18001da5c  call    cs:__imp_InternalTlsAllocData
0x18001da62  mov     ebx, eax
0x18001da64  test    eax, eax
0x18001da66  jns     loc_18001D915
0x18001da6c  jmp     short loc_18001DA2A
0x18001da6e  call    cs:__imp_GetLastError
0x18001da74  test    eax, eax
0x18001da76  jle     short loc_18001DA2A
0x18001da78  movzx   eax, ax
0x18001da7b  or      eax, 80070000h
0x18001da80  jmp     short loc_18001DA2A
0x18001da82  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18001da87  mov     esi, 1
0x18001da8c  call    cs:__imp_CloseHandle
0x18001da92  jmp     loc_18001D945
```
