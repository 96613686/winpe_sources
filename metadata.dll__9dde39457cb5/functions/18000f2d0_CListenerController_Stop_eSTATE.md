# CListenerController::Stop(eSTATE)

- ea: `0x18000f2d0`
- end: `0x18000f3d3`
- name: `?Stop@CListenerController@@QEAAJW4eSTATE@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180008718`
- `0x18000edec`
- `0x18001a050`
- `0x18001fa58`
- `0x180023548`
- `0x180026cb8`

## callees

- `0x18000ea0c`
- `0x18000eea0`
- `0x18000f2d0`
- `0x180031010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000f34a`
- `KERNEL32!LeaveCriticalSection` at `0x18000f395`
- `KERNEL32!LeaveCriticalSection` at `0x18000f34a`
- `KERNEL32!LeaveCriticalSection` at `0x18000f395`
- `KERNEL32!EnterCriticalSection` at `0x18000f2f8`
- `KERNEL32!EnterCriticalSection` at `0x18000f37d`
- `KERNEL32!EnterCriticalSection` at `0x18000f3ad`
- `KERNEL32!EnterCriticalSection` at `0x18000f2f8`
- `KERNEL32!EnterCriticalSection` at `0x18000f37d`
- `KERNEL32!EnterCriticalSection` at `0x18000f3ad`
- `IisRTL!RemoveWorkItem` at `0x18000f356`
- `IisRTL!RemoveWorkItem` at `0x18000f356`

## pseudocode

```c
__int64 __fastcall CListenerController::Stop(__int64 a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  CFileListener *v5; // rsi
  unsigned int v6; // ebp
  void (__fastcall ***v7)(_QWORD); // rcx
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-38h] BYREF
  __int64 v11; // [rsp+28h] [rbp-30h]

  v10 = 1;
  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  v11 = a1 + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( (a2 & 0xFFFFFFFC) != 0 || a2 == 2 )
  {
    v8 = -2147024809;
  }
  else
  {
    v5 = 0;
    v6 = 0;
    if ( a2 != 3 || *(_DWORD *)(a1 + 8) > 1u )
      *(_DWORD *)(a1 + 8) = a2;
    if ( *(_DWORD *)(a1 + 88) )
    {
      v6 = *(_DWORD *)(a1 + 88);
      *(_DWORD *)(a1 + 88) = 0;
    }
    v7 = *(void (__fastcall ****)(_QWORD))(a1 + 80);
    if ( v7 )
    {
      v5 = *(CFileListener **)(a1 + 80);
      (**v7)(v7);
    }
    LeaveCriticalSection(v2);
    if ( v6 )
      RemoveWorkItem(v6);
    if ( v5 )
    {
      if ( g_fcsEditWhileRunningInitialized )
      {
        CFileListener::StopListening(v5, *(void **)(a1 + 96));
        EnterCriticalSection(&g_csEditWhileRunning);
        g_EWRProcessedMetabaseTimeStamp = 0;
        LeaveCriticalSection(&g_csEditWhileRunning);
      }
      (*(void (__fastcall **)(CFileListener *))(*(_QWORD *)v5 + 8LL))(v5);
    }
    EnterCriticalSection(v2);
    v8 = 0;
  }
  CLock::~CLock((CLock *)&v10);
  return v8;
}

```

## disassembly

```asm
0x18000f2d0  push    rbx
0x18000f2d2  push    rbp
0x18000f2d3  push    rsi
0x18000f2d4  push    rdi
0x18000f2d5  push    r14
0x18000f2d7  sub     rsp, 30h
0x18000f2db  lea     rax, [rcx+10h]
0x18000f2df  mov     [rsp+58h+var_38], 1
0x18000f2e7  lea     r14, [rax+8]
0x18000f2eb  mov     [rsp+58h+var_30], rax
0x18000f2f0  mov     rbx, rcx
0x18000f2f3  mov     edi, edx
0x18000f2f5  mov     rcx, r14; lpCriticalSection
0x18000f2f8  call    cs:__imp_EnterCriticalSection
0x18000f2fe  test    edi, 0FFFFFFFCh
0x18000f304  jnz     loc_18000F3B7
0x18000f30a  cmp     edi, 2
0x18000f30d  jz      loc_18000F3B7
0x18000f313  xor     esi, esi
0x18000f315  xor     ebp, ebp
0x18000f317  cmp     edi, 3
0x18000f31a  jnz     short loc_18000F322
0x18000f31c  cmp     dword ptr [rbx+8], 1
0x18000f320  jbe     short loc_18000F325
0x18000f322  mov     [rbx+8], edi
0x18000f325  cmp     [rbx+58h], esi
0x18000f328  jz      short loc_18000F330
0x18000f32a  mov     ebp, [rbx+58h]
0x18000f32d  mov     [rbx+58h], esi
0x18000f330  mov     rcx, [rbx+50h]
0x18000f334  test    rcx, rcx
0x18000f337  jz      short loc_18000F347
0x18000f339  mov     rax, [rcx]
0x18000f33c  mov     rsi, rcx
0x18000f33f  mov     rax, [rax]
0x18000f342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f347  mov     rcx, r14; lpCriticalSection
0x18000f34a  call    cs:__imp_LeaveCriticalSection
0x18000f350  test    ebp, ebp
0x18000f352  jz      short loc_18000F35C
0x18000f354  mov     ecx, ebp
0x18000f356  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x18000f35c  test    rsi, rsi
0x18000f35f  jz      short loc_18000F3AA
0x18000f361  cmp     cs:?g_fcsEditWhileRunningInitialized@@3HA, 0; int g_fcsEditWhileRunningInitialized
0x18000f368  jz      short loc_18000F39B
0x18000f36a  mov     rdx, [rbx+60h]; void *
0x18000f36e  mov     rcx, rsi; this
0x18000f371  call    ?StopListening@CFileListener@@AEAAJPEAX@Z; CFileListener::StopListening(void *)
0x18000f376  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000f37d  call    cs:__imp_EnterCriticalSection
0x18000f383  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000f38a  mov     cs:?g_EWRProcessedMetabaseTimeStamp@@3U_FILETIME@@A, 0; _FILETIME g_EWRProcessedMetabaseTimeStamp
0x18000f395  call    cs:__imp_LeaveCriticalSection
0x18000f39b  mov     rax, [rsi]
0x18000f39e  mov     rcx, rsi
0x18000f3a1  mov     rax, [rax+8]
0x18000f3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3aa  mov     rcx, r14; lpCriticalSection
0x18000f3ad  call    cs:__imp_EnterCriticalSection
0x18000f3b3  xor     ebx, ebx
0x18000f3b5  jmp     short loc_18000F3BC
0x18000f3b7  mov     ebx, 80070057h
0x18000f3bc  lea     rcx, [rsp+58h+var_38]; this
0x18000f3c1  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x18000f3c6  mov     eax, ebx
0x18000f3c8  add     rsp, 30h
0x18000f3cc  pop     r14
0x18000f3ce  pop     rdi
0x18000f3cf  pop     rsi
0x18000f3d0  pop     rbp
0x18000f3d1  pop     rbx
0x18000f3d2  retn
```
