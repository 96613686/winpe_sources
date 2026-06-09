# InitializeThreadPool

- ea: `0x1800525f0`
- end: `0x180052814`
- name: `InitializeThreadPool`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001fbc8`

## callees

- `0x18000ac60`
- `0x180052594`
- `0x1800525f0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!CreateThreadpool` at `0x180052715`
- `KERNEL32!CreateThreadpool` at `0x180052715`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18005273d`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x18005273d`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800527b7`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800527b7`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800527c2`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x1800527c2`
- `KERNEL32!GetLastError` at `0x180052723`
- `KERNEL32!GetLastError` at `0x18005274c`
- `KERNEL32!GetLastError` at `0x180052723`
- `KERNEL32!GetLastError` at `0x18005274c`
- `KERNEL32!HeapAlloc` at `0x180052686`
- `KERNEL32!HeapAlloc` at `0x180052686`

## string_xrefs

- `0x18005263f`: `InitializeThreadPool`
- `0x1800526ac`: `InitializeThreadPool: Failed to allocate mempory for thread pool, Error = %d`
- `0x180052734`: `InitializeThreadPool: Thread pool creation failed with error = %d`
- `0x18005275d`: `InitializeThreadPool: Thread pool clean group creation failed with error = %d`
- `0x1800527df`: `Leaving: InitializeThreadPool`

## pseudocode

```c
__int64 InitializeThreadPool()
{
  _DWORD *v0; // rax
  _DWORD *v1; // rbx
  unsigned int v2; // edi
  PTP_POOL Threadpool; // rax
  DWORD LastError; // eax
  const wchar_t *v5; // rdx
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  struct _TP_POOL *v7; // rcx
  int v9; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v10[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v9 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"Entered: %ws", L"InitializeThreadPool");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v9);
  }
  v0 = HeapAlloc(IPRouterHeap, 0, 0x60u);
  v1 = v0;
  if ( !v0 )
  {
    v2 = 8;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"InitializeThreadPool: Failed to allocate mempory for thread pool, Error = %d", 8);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v9);
    }
    goto LABEL_17;
  }
  v0[4] = 3;
  *((_QWORD *)v0 + 3) = 0;
  *((_QWORD *)v0 + 4) = 0;
  *((_QWORD *)v0 + 5) = 0;
  *((_QWORD *)v0 + 6) = 0;
  *((_QWORD *)v0 + 7) = 0;
  *((_QWORD *)v0 + 8) = 0;
  v0[18] = 0;
  v0[19] = 1;
  v0[20] = 72;
  Threadpool = CreateThreadpool(0);
  *(_QWORD *)v1 = Threadpool;
  if ( !Threadpool )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      goto LABEL_16;
    v5 = L"InitializeThreadPool: Thread pool creation failed with error = %d";
    goto LABEL_14;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)v1 + 1) = ThreadpoolCleanupGroup;
  if ( ThreadpoolCleanupGroup )
  {
    v7 = *(struct _TP_POOL **)v1;
    *((_QWORD *)v1 + 3) = *(_QWORD *)v1;
    v2 = 0;
    *((_QWORD *)v1 + 4) = ThreadpoolCleanupGroup;
    *((_QWORD *)v1 + 5) = 0;
    SetThreadpoolThreadMaximum(v7, 0x14u);
    SetThreadpoolThreadMinimum(*(PTP_POOL *)v1, 0);
    goto LABEL_19;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    v5 = L"InitializeThreadPool: Thread pool clean group creation failed with error = %d";
LABEL_14:
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, v5, LastError);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v9);
  }
LABEL_16:
  if ( v2 )
  {
LABEL_17:
    DestroyThreadPoolInternal(v1);
    goto LABEL_20;
  }
LABEL_19:
  v1[22] = 1;
  g_hDDEventThreadPool = v1;
LABEL_20:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: InitializeThreadPool");
  return v2;
}

```

## disassembly

```asm
0x1800525f0  push    rbp
0x1800525f2  push    rbx
0x1800525f3  push    rsi
0x1800525f4  push    rdi
0x1800525f5  push    r14
0x1800525f7  lea     rbp, [rsp-740h]
0x1800525ff  sub     rsp, 840h
0x180052606  mov     rax, cs:__security_cookie
0x18005260d  xor     rax, rsp
0x180052610  mov     [rbp+760h+var_30], rax
0x180052617  xor     esi, esi
0x180052619  lea     rcx, [rsp+860h+var_82C]; void *
0x18005261e  xor     edx, edx; Val
0x180052620  mov     [rsp+860h+var_830], esi
0x180052624  mov     r8d, 7FCh; Size
0x18005262a  call    memset_0
0x18005262f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180052636  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005263d  jge     short loc_180052679
0x18005263f  lea     r8, aInitializethre_1; "InitializeThreadPool"
0x180052646  mov     word ptr [rsp+860h+var_830], si
0x18005264b  lea     rdx, aEnteredWs; "Entered: %ws"
0x180052652  lea     rcx, [rsp+860h+var_830]
0x180052657  call    FormatRRASErrorString
0x18005265c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180052663  jge     short loc_180052679
0x180052665  lea     r8, [rsp+860h+var_830]
0x18005266a  mov     rcx, r14
0x18005266d  lea     rdx, RasRtrmgrTraceInfo
0x180052674  call    McTemplateU0z_EventWriteTransfer
0x180052679  mov     rcx, cs:IPRouterHeap; hHeap
0x180052680  xor     edx, edx; dwFlags
0x180052682  lea     r8d, [rdx+60h]; dwBytes
0x180052686  call    cs:__imp_HeapAlloc
0x18005268c  mov     rbx, rax
0x18005268f  test    rax, rax
0x180052692  jnz     short loc_1800526E3
0x180052694  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18005269b  lea     edi, [rax+8]
0x18005269e  jge     loc_180052797
0x1800526a4  mov     r8d, edi
0x1800526a7  mov     word ptr [rsp+860h+var_830], si
0x1800526ac  lea     rdx, aInitializethre_2; "InitializeThreadPool: Failed to allocat"...
0x1800526b3  lea     rcx, [rsp+860h+var_830]
0x1800526b8  call    FormatRRASErrorString
0x1800526bd  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800526c4  jge     loc_180052797
0x1800526ca  lea     r8, [rsp+860h+var_830]
0x1800526cf  mov     rcx, r14
0x1800526d2  lea     rdx, RasRtrmgrTraceInfo
0x1800526d9  call    McTemplateU0z_EventWriteTransfer
0x1800526de  jmp     loc_180052797
0x1800526e3  xor     ecx, ecx; reserved
0x1800526e5  mov     dword ptr [rax+10h], 3
0x1800526ec  mov     [rax+18h], rsi
0x1800526f0  mov     [rax+20h], rsi
0x1800526f4  mov     [rax+28h], rsi
0x1800526f8  mov     [rax+30h], rsi
0x1800526fc  mov     [rax+38h], rsi
0x180052700  mov     [rax+40h], rsi
0x180052704  mov     [rax+48h], esi
0x180052707  mov     dword ptr [rax+4Ch], 1
0x18005270e  mov     dword ptr [rax+50h], 48h ; 'H'
0x180052715  call    cs:__imp_CreateThreadpool
0x18005271b  mov     [rbx], rax
0x18005271e  test    rax, rax
0x180052721  jnz     short loc_18005273D
0x180052723  call    cs:__imp_GetLastError
0x180052729  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180052730  mov     edi, eax
0x180052732  jz      short loc_180052793
0x180052734  lea     rdx, aInitializethre; "InitializeThreadPool: Thread pool creat"...
0x18005273b  jmp     short loc_180052764
0x18005273d  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180052743  mov     [rbx+8], rax
0x180052747  test    rax, rax
0x18005274a  jnz     short loc_1800527A1
0x18005274c  call    cs:__imp_GetLastError
0x180052752  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180052759  mov     edi, eax
0x18005275b  jz      short loc_180052793
0x18005275d  lea     rdx, aInitializethre_0; "InitializeThreadPool: Thread pool clean"...
0x180052764  mov     r8d, eax
0x180052767  mov     word ptr [rsp+860h+var_830], si
0x18005276c  lea     rcx, [rsp+860h+var_830]
0x180052771  call    FormatRRASErrorString
0x180052776  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18005277d  jz      short loc_180052793
0x18005277f  lea     r8, [rsp+860h+var_830]
0x180052784  mov     rcx, r14
0x180052787  lea     rdx, RasRtrMgrTraceError
0x18005278e  call    McTemplateU0z_EventWriteTransfer
0x180052793  test    edi, edi
0x180052795  jz      short loc_1800527C8
0x180052797  mov     rcx, rbx; lpMem
0x18005279a  call    DestroyThreadPoolInternal
0x18005279f  jmp     short loc_1800527D6
0x1800527a1  mov     rcx, [rbx]; ptpp
0x1800527a4  mov     edx, 14h; cthrdMost
0x1800527a9  mov     [rbx+18h], rcx
0x1800527ad  mov     edi, esi
0x1800527af  mov     [rbx+20h], rax
0x1800527b3  mov     [rbx+28h], rsi
0x1800527b7  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800527bd  mov     rcx, [rbx]; ptpp
0x1800527c0  xor     edx, edx; cthrdMic
0x1800527c2  call    cs:__imp_SetThreadpoolThreadMinimum
0x1800527c8  mov     dword ptr [rbx+58h], 1
0x1800527cf  mov     cs:g_hDDEventThreadPool, rbx
0x1800527d6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800527dd  jz      short loc_1800527F5
0x1800527df  lea     r8, aLeavingInitial_2; "Leaving: InitializeThreadPool"
0x1800527e6  mov     rcx, r14
0x1800527e9  lea     rdx, RasRtrmgrTraceInfo
0x1800527f0  call    McTemplateU0z_EventWriteTransfer
0x1800527f5  mov     eax, edi
0x1800527f7  mov     rcx, [rbp+760h+var_30]
0x1800527fe  xor     rcx, rsp; StackCookie
0x180052801  call    __security_check_cookie
0x180052806  add     rsp, 840h
0x18005280d  pop     r14
0x18005280f  pop     rdi
0x180052810  pop     rsi
0x180052811  pop     rbx
0x180052812  pop     rbp
0x180052813  retn
```
