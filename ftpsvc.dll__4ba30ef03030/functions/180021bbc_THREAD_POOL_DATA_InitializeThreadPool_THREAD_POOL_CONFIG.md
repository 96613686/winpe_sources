# THREAD_POOL_DATA::InitializeThreadPool(THREAD_POOL_CONFIG *)

- ea: `0x180021bbc`
- end: `0x180021d68`
- name: `?InitializeThreadPool@THREAD_POOL_DATA@@QEAAHPEAUTHREAD_POOL_CONFIG@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(THREAD_POOL_DATA *__hidden this, struct THREAD_POOL_CONFIG *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180021a98`

## callees

- `0x180001210`
- `0x180001250`
- `0x1800205f8`
- `0x18002083c`
- `0x180021bbc`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180021cf4`
- `KERNEL32!GetTickCount` at `0x180021cf4`
- `KERNEL32!LeaveCriticalSection` at `0x180021d2c`
- `KERNEL32!LeaveCriticalSection` at `0x180021d2c`
- `KERNEL32!EnterCriticalSection` at `0x180021c58`
- `KERNEL32!EnterCriticalSection` at `0x180021c58`
- `KERNEL32!CloseHandle` at `0x180021d4c`
- `KERNEL32!CloseHandle` at `0x180021d4c`
- `KERNEL32!CreateIoCompletionPort` at `0x180021c25`
- `KERNEL32!CreateIoCompletionPort` at `0x180021c25`
- `iisutil!PuDbgPrint` at `0x180021cdb`
- `iisutil!PuDbgPrint` at `0x180021cdb`

## string_xrefs

- `0x180021cd4`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180021cbb`: `W3TP: CreateThread thread creation\n`
- `0x180021cc2`: `THREAD_MANAGER::CreateThread`

## pseudocode

```c
__int64 __fastcall THREAD_POOL_DATA::InitializeThreadPool(THREAD_POOL_DATA *this, struct THREAD_POOL_CONFIG *a2)
{
  HANDLE *v3; // rbx
  int v4; // eax
  struct THREAD_POOL *v5; // rdx
  HANDLE IoCompletionPort; // rax
  int v7; // eax
  int v8; // ebp
  __int64 v9; // rsi
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  bool v12; // zf
  DWORD TickCount; // eax

  v3 = (HANDLE *)((char *)this + 8);
  *((_OWORD *)this + 3) = *(_OWORD *)a2;
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 4);
  v4 = *((_DWORD *)a2 + 20);
  v5 = (struct THREAD_POOL *)*((_QWORD *)this + 5);
  *((_DWORD *)this + 32) = v4;
  if ( (int)THREAD_MANAGER::CreateThreadManager((struct THREAD_MANAGER **)this + 4, v5, this) >= 0 )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, *((_DWORD *)this + 18));
    *v3 = IoCompletionPort;
    if ( IoCompletionPort )
    {
      v7 = *((_DWORD *)this + 21);
      if ( v7 )
        *((_DWORD *)this + 12) = v7;
      v8 = 0;
      if ( !*((_DWORD *)this + 12) )
        *((_DWORD *)this + 12) = 1;
      while ( 1 )
      {
        v9 = *((_QWORD *)this + 4);
        EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
        if ( !*(_DWORD *)(v9 + 48) )
        {
          v10 = operator new(0x30u);
          v11 = v10;
          if ( v10 )
          {
            v12 = (g_dwDebugFlags & 3) == 0;
            *(_DWORD *)v10 = 1380012116;
            v10[1] = 0;
            v10[2] = 0;
            v10[3] = 0;
            v10[4] = 0;
            *((_DWORD *)v10 + 10) = 0;
            if ( !v12 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
                1577,
                "THREAD_MANAGER::CreateThread",
                "W3TP: CreateThread thread creation\n");
            v11[2] = this;
            v11[1] = THREAD_POOL_DATA::ThreadPoolThread;
            v11[3] = v9;
            TickCount = GetTickCount();
            *((_DWORD *)v11 + 9) = 0;
            *((_DWORD *)v11 + 8) = TickCount;
            if ( (unsigned int)THREAD_MANAGER::DoThreadCreation(
                                 (THREAD_MANAGER *)v9,
                                 (struct THREAD_MANAGER::THREAD_PARAM *)v11) )
              goto LABEL_14;
            *(_DWORD *)v11 = 2017546324;
            operator delete(v11);
          }
        }
        *(_DWORD *)(v9 + 52) = 0;
LABEL_14:
        LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
        if ( (unsigned int)++v8 >= *((_DWORD *)this + 12) )
          return 1;
      }
    }
  }
  if ( *v3 )
  {
    CloseHandle(*v3);
    *v3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180021bbc  push    rbx
0x180021bbe  push    rbp
0x180021bbf  push    rsi
0x180021bc0  push    rdi
0x180021bc1  push    r14
0x180021bc3  push    r15
0x180021bc5  sub     rsp, 38h
0x180021bc9  movups  xmm0, xmmword ptr [rdx]
0x180021bcc  mov     rdi, rcx
0x180021bcf  lea     rbx, [rcx+8]
0x180021bd3  mov     r8, rcx; struct THREAD_POOL_DATA *
0x180021bd6  movups  xmmword ptr [rcx+30h], xmm0
0x180021bda  movups  xmm1, xmmword ptr [rdx+10h]
0x180021bde  movups  xmmword ptr [rcx+40h], xmm1
0x180021be2  movups  xmm0, xmmword ptr [rdx+20h]
0x180021be6  movups  xmmword ptr [rcx+50h], xmm0
0x180021bea  movups  xmm1, xmmword ptr [rdx+30h]
0x180021bee  movups  xmmword ptr [rcx+60h], xmm1
0x180021bf2  movups  xmm0, xmmword ptr [rdx+40h]
0x180021bf6  movups  xmmword ptr [rcx+70h], xmm0
0x180021bfa  mov     eax, [rdx+50h]
0x180021bfd  mov     rdx, [rcx+28h]; struct THREAD_POOL *
0x180021c01  mov     [rcx+80h], eax
0x180021c07  add     rcx, 20h ; ' '; struct THREAD_MANAGER **
0x180021c0b  call    ?CreateThreadManager@THREAD_MANAGER@@SAJPEAPEAV1@PEAVTHREAD_POOL@@PEAVTHREAD_POOL_DATA@@@Z; THREAD_MANAGER::CreateThreadManager(THREAD_MANAGER * *,THREAD_POOL *,THREAD_POOL_DATA *)
0x180021c10  test    eax, eax
0x180021c12  js      loc_180021D44
0x180021c18  mov     r9d, [rdi+48h]; NumberOfConcurrentThreads
0x180021c1c  xor     r8d, r8d; CompletionKey
0x180021c1f  xor     edx, edx; ExistingCompletionPort
0x180021c21  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x180021c25  call    cs:__imp_CreateIoCompletionPort
0x180021c2b  mov     [rbx], rax
0x180021c2e  test    rax, rax
0x180021c31  jz      loc_180021D44
0x180021c37  mov     eax, [rdi+54h]
0x180021c3a  test    eax, eax
0x180021c3c  jz      short loc_180021C41
0x180021c3e  mov     [rdi+30h], eax
0x180021c41  xor     ebp, ebp
0x180021c43  cmp     dword ptr [rdi+30h], 1
0x180021c47  jnb     short loc_180021C50
0x180021c49  mov     dword ptr [rdi+30h], 1
0x180021c50  mov     rsi, [rdi+20h]
0x180021c54  lea     rcx, [rsi+8]; lpCriticalSection
0x180021c58  call    cs:__imp_EnterCriticalSection
0x180021c5e  cmp     dword ptr [rsi+30h], 0
0x180021c62  jnz     loc_180021D21
0x180021c68  mov     ecx, 30h ; '0'; Size
0x180021c6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021c72  mov     rbx, rax
0x180021c75  test    rax, rax
0x180021c78  jz      loc_180021D21
0x180021c7e  test    byte ptr cs:g_dwDebugFlags, 3
0x180021c85  mov     dword ptr [rax], 52415054h
0x180021c8b  mov     qword ptr [rax+8], 0
0x180021c93  mov     qword ptr [rax+10h], 0
0x180021c9b  mov     qword ptr [rax+18h], 0
0x180021ca3  mov     qword ptr [rax+20h], 0
0x180021cab  mov     dword ptr [rax+28h], 0
0x180021cb2  jz      short loc_180021CE1
0x180021cb4  mov     rcx, cs:g_pDebug
0x180021cbb  lea     rax, aW3tpCreatethre_0; "W3TP: CreateThread thread creation\n"
0x180021cc2  lea     r9, aThreadManagerC; "THREAD_MANAGER::CreateThread"
0x180021cc9  mov     [rsp+68h+var_48], rax
0x180021cce  mov     r8d, 629h
0x180021cd4  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180021cdb  call    cs:__imp_PuDbgPrint
0x180021ce1  lea     rax, ?ThreadPoolThread@THREAD_POOL_DATA@@SAKPEAX@Z; THREAD_POOL_DATA::ThreadPoolThread(void *)
0x180021ce8  mov     [rbx+10h], rdi
0x180021cec  mov     [rbx+8], rax
0x180021cf0  mov     [rbx+18h], rsi
0x180021cf4  call    cs:__imp_GetTickCount
0x180021cfa  mov     rdx, rbx; lpParameter
0x180021cfd  mov     dword ptr [rbx+24h], 0
0x180021d04  mov     rcx, rsi; this
0x180021d07  mov     [rbx+20h], eax
0x180021d0a  call    ?DoThreadCreation@THREAD_MANAGER@@AEAAHPEAUTHREAD_PARAM@1@@Z; THREAD_MANAGER::DoThreadCreation(THREAD_MANAGER::THREAD_PARAM *)
0x180021d0f  test    eax, eax
0x180021d11  jnz     short loc_180021D28
0x180021d13  mov     rcx, rbx; Block
0x180021d16  mov     dword ptr [rbx], 78415054h
0x180021d1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021d21  mov     dword ptr [rsi+34h], 0
0x180021d28  lea     rcx, [rsi+8]; lpCriticalSection
0x180021d2c  call    cs:__imp_LeaveCriticalSection
0x180021d32  inc     ebp
0x180021d34  cmp     ebp, [rdi+30h]
0x180021d37  jb      loc_180021C50
0x180021d3d  mov     eax, 1
0x180021d42  jmp     short loc_180021D5B
0x180021d44  mov     rcx, [rbx]; hObject
0x180021d47  test    rcx, rcx
0x180021d4a  jz      short loc_180021D59
0x180021d4c  call    cs:__imp_CloseHandle
0x180021d52  mov     qword ptr [rbx], 0
0x180021d59  xor     eax, eax
0x180021d5b  add     rsp, 38h
0x180021d5f  pop     r15
0x180021d61  pop     r14
0x180021d63  pop     rdi
0x180021d64  pop     rsi
0x180021d65  pop     rbp
0x180021d66  pop     rbx
0x180021d67  retn
```
