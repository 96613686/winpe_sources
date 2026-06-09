# IIS_MODULE::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000cfa0`
- end: `0x18000d1e7`
- name: `?OnAsyncCompletion@IIS_MODULE@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `583`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002128`
- `0x180006bcc`
- `0x180006ce8`
- `0x180009128`
- `0x18000b3ac`
- `0x18000bb5c`
- `0x18000cfa0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d00d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d194`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d00d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d0de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d0de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1c0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d19a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d19a`

## pseudocode

```c
__int64 __fastcall IIS_MODULE::OnAsyncCompletion(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 (__fastcall ***a6)(_QWORD))
{
  __int64 (__fastcall ***v6)(_QWORD); // rbx
  int started; // esi
  int v10; // r13d
  __int64 v11; // rax
  int v12; // r14d
  __int64 v13; // r12
  int v14; // r15d
  _QWORD **v15; // rbx
  _QWORD *v16; // rcx
  _QWORD *v17; // rax
  int v18; // ebx
  __int64 v19; // rcx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rbx
  __int64 v23; // rdi
  DWORD TickCount; // eax
  int v25; // r8d
  int v27; // [rsp+90h] [rbp+8h] BYREF

  v6 = a6;
  started = (*a6)[1](a6);
  v10 = (**v6)(v6);
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 32LL))(a2);
  v12 = 0;
  LODWORD(a6) = 0;
  v27 = 0;
  v13 = v11;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v14 = *(_DWORD *)(a1 + 116);
  v15 = (_QWORD **)(a1 + 208);
  *(_DWORD *)(a1 + 60) = 0;
  while ( 1 )
  {
    v16 = *v15;
    if ( *v15 == v15 )
      break;
    if ( (_QWORD **)v16[1] != v15 || (v17 = (_QWORD *)*v16, *(_QWORD **)(*v16 + 8LL) != v16) )
      __fastfail(3u);
    *v15 = v17;
    v17[1] = v15;
    FCGI_BUFFER::Free((FCGI_BUFFER *)(v16 - 4));
  }
  if ( *(_DWORD *)(a1 + 64) )
  {
    started = 0;
    v18 = 1;
    goto LABEL_19;
  }
  v18 = 0;
  if ( started >= 0 && v14 )
  {
    if ( *(_DWORD *)(a1 + 56) )
    {
      started = -2147023901;
      goto LABEL_19;
    }
    v19 = *(_QWORD *)(a1 + 104);
    *(_QWORD *)(v19 + 16) = *(_QWORD *)v19;
    *(_DWORD *)(v19 + 24) = v10;
    v20 = APPLICATION::SendFcgiStdIn(*(SEND_QUEUE ***)(a1 + 8), *(struct FCGI_BUFFER **)(a1 + 104), (int *)&a6);
    *(_QWORD *)(a1 + 104) = 0;
    started = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -2147024858 )
        goto LABEL_19;
      started = 0;
    }
    if ( (_DWORD)a6 )
    {
      *(_DWORD *)(a1 + 120) = 1;
    }
    else
    {
      v21 = IIS_MODULE::BeginReceiveEntity((IIS_MODULE *)(a1 - 32), &v27);
      v12 = v27;
      started = v21;
    }
  }
LABEL_19:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( v18 )
  {
    v22 = *(_QWORD *)(a1 + 136);
    *(_QWORD *)(a1 + 136) = 0;
    (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v13 + 24LL))(v13, 500, "Internal Server Error");
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 64LL))(v22, 2);
  }
  else if ( v14 )
  {
    if ( started < 0 || v12 && (started = APPLICATION::StartIISSends(*(APPLICATION **)(a1 + 8)), started < 0) )
      IIS_MODULE::EndResponse((IIS_MODULE *)(a1 - 32), 0, started, 0, 0, 0);
  }
  else if ( !*(_DWORD *)(a1 + 76) )
  {
    v23 = *(_QWORD *)(a1 + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)(v23 + 112));
    TickCount = GetTickCount();
    v25 = *(_DWORD *)(v23 + 104);
    *(_DWORD *)(v23 + 260) = TickCount;
    if ( v25 )
      started = -2147023901;
    *(_DWORD *)(v23 + 52) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v23 + 112));
    SEND_QUEUE::SendCompletion(*(SEND_QUEUE **)(v23 + 72), started);
  }
  return 1;
}

```

## disassembly

```asm
0x18000cfa0  push    rbx
0x18000cfa2  push    rbp
0x18000cfa3  push    rsi
0x18000cfa4  push    rdi
0x18000cfa5  push    r12
0x18000cfa7  push    r13
0x18000cfa9  push    r14
0x18000cfab  push    r15
0x18000cfad  sub     rsp, 48h
0x18000cfb1  mov     rbx, [rsp+88h+arg_28]
0x18000cfb9  mov     rbp, rcx
0x18000cfbc  mov     rcx, rbx
0x18000cfbf  mov     rdi, rdx
0x18000cfc2  mov     rax, [rbx]
0x18000cfc5  mov     rax, [rax+8]
0x18000cfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfce  mov     esi, eax
0x18000cfd0  mov     rcx, rbx
0x18000cfd3  mov     rax, [rbx]
0x18000cfd6  mov     rax, [rax]
0x18000cfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfde  mov     rcx, [rdi]
0x18000cfe1  mov     r13d, eax
0x18000cfe4  mov     rax, [rcx+20h]
0x18000cfe8  mov     rcx, rdi
0x18000cfeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cff0  xor     r14d, r14d
0x18000cff3  mov     dword ptr [rsp+88h+arg_28], 0
0x18000cffe  lea     rcx, [rbp+10h]; lpCriticalSection
0x18000d002  mov     [rsp+88h+arg_0], r14d
0x18000d00a  mov     r12, rax
0x18000d00d  call    cs:__imp_EnterCriticalSection
0x18000d013  mov     r15d, [rbp+74h]
0x18000d017  lea     rbx, [rbp+0D0h]
0x18000d01e  mov     [rbp+3Ch], r14d
0x18000d022  mov     rcx, [rbx]
0x18000d025  cmp     rcx, rbx
0x18000d028  jz      short loc_18000D052
0x18000d02a  cmp     [rcx+8], rbx
0x18000d02e  jnz     short loc_18000D04B
0x18000d030  mov     rax, [rcx]
0x18000d033  cmp     [rax+8], rcx
0x18000d037  jnz     short loc_18000D04B
0x18000d039  mov     [rbx], rax
0x18000d03c  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x18000d040  mov     [rax+8], rbx
0x18000d044  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x18000d049  jmp     short loc_18000D022
0x18000d04b  mov     ecx, 3
0x18000d050  int     29h; Win8: RtlFailFast(ecx)
0x18000d052  cmp     [rbp+40h], r14d
0x18000d056  jz      short loc_18000D05F
0x18000d058  xor     esi, esi
0x18000d05a  lea     ebx, [rsi+1]
0x18000d05d  jmp     short loc_18000D0DA
0x18000d05f  xor     ebx, ebx
0x18000d061  test    esi, esi
0x18000d063  js      short loc_18000D0DA
0x18000d065  test    r15d, r15d
0x18000d068  jz      short loc_18000D0DA
0x18000d06a  cmp     [rbp+38h], ebx
0x18000d06d  jz      short loc_18000D076
0x18000d06f  mov     esi, 800703E3h
0x18000d074  jmp     short loc_18000D0DA
0x18000d076  mov     rcx, [rbp+68h]
0x18000d07a  lea     r8, [rsp+88h+arg_28]; int *
0x18000d082  mov     rax, [rcx]
0x18000d085  mov     [rcx+10h], rax
0x18000d089  mov     [rcx+18h], r13d
0x18000d08d  mov     rdx, [rbp+68h]; struct FCGI_BUFFER *
0x18000d091  mov     rcx, [rbp+8]; this
0x18000d095  call    ?SendFcgiStdIn@APPLICATION@@QEAAJPEAVFCGI_BUFFER@@PEAH@Z; APPLICATION::SendFcgiStdIn(FCGI_BUFFER *,int *)
0x18000d09a  mov     [rbp+68h], rbx
0x18000d09e  mov     esi, eax
0x18000d0a0  test    eax, eax
0x18000d0a2  jns     short loc_18000D0AD
0x18000d0a4  cmp     eax, 80070026h
0x18000d0a9  jnz     short loc_18000D0DA
0x18000d0ab  xor     esi, esi
0x18000d0ad  cmp     dword ptr [rsp+88h+arg_28], ebx
0x18000d0b4  jnz     short loc_18000D0D3
0x18000d0b6  lea     rdx, [rsp+88h+arg_0]; int *
0x18000d0be  lea     rcx, [rbp-20h]; this
0x18000d0c2  call    ?BeginReceiveEntity@IIS_MODULE@@AEAAJPEAH@Z; IIS_MODULE::BeginReceiveEntity(int *)
0x18000d0c7  mov     r14d, [rsp+88h+arg_0]
0x18000d0cf  mov     esi, eax
0x18000d0d1  jmp     short loc_18000D0DA
0x18000d0d3  mov     dword ptr [rbp+78h], 1
0x18000d0da  lea     rcx, [rbp+10h]; lpCriticalSection
0x18000d0de  call    cs:__imp_LeaveCriticalSection
0x18000d0e4  test    ebx, ebx
0x18000d0e6  jz      short loc_18000D144
0x18000d0e8  mov     rbx, [rbp+88h]
0x18000d0ef  lea     r8, aInternalServer; "Internal Server Error"
0x18000d0f6  xor     r9d, r9d
0x18000d0f9  mov     qword ptr [rbp+88h], 0
0x18000d104  mov     rax, [r12]
0x18000d108  mov     edx, 1F4h
0x18000d10d  mov     [rsp+88h+var_58], r9d
0x18000d112  mov     rcx, r12
0x18000d115  mov     [rsp+88h+var_60], r9
0x18000d11a  mov     dword ptr [rsp+88h+var_68], 80004005h
0x18000d122  mov     rax, [rax+18h]
0x18000d126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d12b  mov     rax, [rbx]
0x18000d12e  mov     edx, 2
0x18000d133  mov     rcx, rbx
0x18000d136  mov     rax, [rax+40h]
0x18000d13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d13f  jmp     loc_18000D1D1
0x18000d144  test    r15d, r15d
0x18000d147  jz      short loc_18000D186
0x18000d149  test    esi, esi
0x18000d14b  js      short loc_18000D161
0x18000d14d  test    r14d, r14d
0x18000d150  jz      short loc_18000D1D1
0x18000d152  mov     rcx, [rbp+8]; this
0x18000d156  call    ?StartIISSends@APPLICATION@@QEAAJXZ; APPLICATION::StartIISSends(void)
0x18000d15b  mov     esi, eax
0x18000d15d  test    eax, eax
0x18000d15f  jns     short loc_18000D1D1
0x18000d161  mov     [rsp+88h+var_60], 0; unsigned __int16 *
0x18000d16a  lea     rcx, [rbp-20h]; this
0x18000d16e  xor     r9d, r9d; unsigned int
0x18000d171  mov     [rsp+88h+var_68], 0; struct IAppHostConfigException *
0x18000d17a  mov     r8d, esi; int
0x18000d17d  xor     edx, edx; int
0x18000d17f  call    ?EndResponse@IIS_MODULE@@AEAAXHJIPEAUIAppHostConfigException@@PEBG@Z; IIS_MODULE::EndResponse(int,long,uint,IAppHostConfigException *,ushort const *)
0x18000d184  jmp     short loc_18000D1D1
0x18000d186  cmp     dword ptr [rbp+4Ch], 0
0x18000d18a  jnz     short loc_18000D1D1
0x18000d18c  mov     rdi, [rbp+8]
0x18000d190  lea     rcx, [rdi+70h]; lpCriticalSection
0x18000d194  call    cs:__imp_EnterCriticalSection
0x18000d19a  call    cs:__imp_GetTickCount
0x18000d1a0  mov     r8d, [rdi+68h]
0x18000d1a4  test    r8d, r8d
0x18000d1a7  mov     [rdi+104h], eax
0x18000d1ad  mov     eax, 800703E3h
0x18000d1b2  cmovnz  esi, eax
0x18000d1b5  mov     dword ptr [rdi+34h], 0
0x18000d1bc  lea     rcx, [rdi+70h]; lpCriticalSection
0x18000d1c0  call    cs:__imp_LeaveCriticalSection
0x18000d1c6  mov     rcx, [rdi+48h]; this
0x18000d1ca  mov     edx, esi; int
0x18000d1cc  call    ?SendCompletion@SEND_QUEUE@@QEAAXJ@Z; SEND_QUEUE::SendCompletion(long)
0x18000d1d1  mov     eax, 1
0x18000d1d6  add     rsp, 48h
0x18000d1da  pop     r15
0x18000d1dc  pop     r14
0x18000d1de  pop     r13
0x18000d1e0  pop     r12
0x18000d1e2  pop     rdi
0x18000d1e3  pop     rsi
0x18000d1e4  pop     rbp
0x18000d1e5  pop     rbx
0x18000d1e6  retn
```
