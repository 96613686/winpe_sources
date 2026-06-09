# DdmThreadPool::Initialize(ulong,ulong)

- ea: `0x180048510`
- end: `0x180048828`
- name: `?Initialize@DdmThreadPool@@UEAAKKK@Z`
- size: `792`
- prototype: `unsigned int(DdmThreadPool *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007b7c`
- `0x180048510`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!CreateThreadpool` at `0x1800485e1`
- `KERNEL32!CreateThreadpool` at `0x1800485e1`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180048681`
- `KERNEL32!CreateThreadpoolCleanupGroup` at `0x180048681`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800486fd`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800486fd`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x18004870a`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x18004870a`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800487c4`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1800487c4`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800487cd`
- `KERNEL32!CloseThreadpoolCleanupGroup` at `0x1800487cd`
- `KERNEL32!CloseThreadpool` at `0x1800487df`
- `KERNEL32!CloseThreadpool` at `0x1800487df`
- `KERNEL32!CloseHandle` at `0x1800487f2`
- `KERNEL32!CloseHandle` at `0x1800487f2`
- `KERNEL32!GetLastError` at `0x1800485f4`
- `KERNEL32!GetLastError` at `0x180048693`
- `KERNEL32!GetLastError` at `0x18004872d`
- `KERNEL32!GetLastError` at `0x1800485f4`
- `KERNEL32!GetLastError` at `0x180048693`
- `KERNEL32!GetLastError` at `0x18004872d`
- `KERNEL32!CreateEventW` at `0x18004871a`
- `KERNEL32!CreateEventW` at `0x18004871a`

## string_xrefs

- `0x18004856d`: `DdmThreadPool::Initialize() called when helper is already initialized`
- `0x18004860e`: `Thread Pool Creation Failed with error = %!WINERROR!`
- `0x1800486b1`: `Thread Pool Cleanup Group creation Failed with error = %!WINERROR!`
- `0x180048747`: `DdmThreadPool::Initialize: CreateEvent failed with 0x%x`

## pseudocode

```c
__int64 __fastcall DdmThreadPool::Initialize(DdmThreadPool *this, DWORD a2, DWORD a3)
{
  __int64 v6; // r8
  PTP_POOL Threadpool; // rax
  DWORD LastError; // eax
  DWORD v10; // esi
  __int64 v11; // r8
  __int64 v12; // rax
  PTP_CLEANUP_GROUP *v13; // rdi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  DWORD v15; // eax
  __int64 v16; // r8
  __int64 v17; // rax
  struct _TP_POOL *v18; // rcx
  HANDLE EventW; // rax
  DWORD v20; // eax
  struct _TP_POOL *v21; // rcx
  void *v22; // rcx
  _BYTE v23[16]; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  int v26; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  if ( !*((_DWORD *)this + 24) )
  {
    *((_DWORD *)this + 6) = 3;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_QWORD *)this + 8) = 0;
    *((_QWORD *)this + 9) = 0;
    *((_DWORD *)this + 20) = 0;
    *((_DWORD *)this + 21) = 1;
    *((_DWORD *)this + 22) = 72;
    Threadpool = CreateThreadpool(0);
    *((_QWORD *)this + 1) = Threadpool;
    if ( !Threadpool )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v26, L"Thread Pool Creation Failed with error = %!WINERROR!", LastError);
        if ( (byte_1800C8404 & 8) != 0 )
        {
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)&v27[2 * v12 - 4] );
          v25 = (unsigned int)(2 * v12 + 2);
          v24 = (const wchar_t *)&v26;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v11, 2, v23);
        }
      }
      v13 = (PTP_CLEANUP_GROUP *)((char *)this + 16);
      goto LABEL_24;
    }
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    v13 = (PTP_CLEANUP_GROUP *)((char *)this + 16);
    *((_QWORD *)this + 2) = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      v18 = (struct _TP_POOL *)*((_QWORD *)this + 1);
      *((_QWORD *)this + 4) = v18;
      v10 = 0;
      *((_QWORD *)this + 5) = ThreadpoolCleanupGroup;
      *((_QWORD *)this + 6) = 0;
      SetThreadpoolThreadMaximum(v18, a2);
      SetThreadpoolThreadMinimum(*((PTP_POOL *)this + 1), a3);
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 13) = EventW;
      if ( EventW )
        goto LABEL_31;
      v20 = GetLastError();
      v10 = v20;
      if ( (byte_1800C8404 & 8) == 0
        || (LOWORD(v26) = 0,
            FormatRRASErrorString(&v26, L"DdmThreadPool::Initialize: CreateEvent failed with 0x%x", v20),
            (byte_1800C8404 & 8) == 0) )
      {
LABEL_24:
        if ( v10 )
        {
          if ( *v13 )
          {
            CloseThreadpoolCleanupGroupMembers(*v13, 1, 0);
            CloseThreadpoolCleanupGroup(*v13);
            *v13 = 0;
          }
          v21 = (struct _TP_POOL *)*((_QWORD *)this + 1);
          if ( v21 )
          {
            CloseThreadpool(v21);
            *((_QWORD *)this + 1) = 0;
          }
          v22 = (void *)*((_QWORD *)this + 13);
          if ( v22 )
          {
            CloseHandle(v22);
            *((_QWORD *)this + 13) = 0;
          }
          return v10;
        }
LABEL_31:
        *((_DWORD *)this + 24) = 1;
        return v10;
      }
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v27[2 * v17 - 4] );
    }
    else
    {
      v15 = GetLastError();
      v10 = v15;
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_24;
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"Thread Pool Cleanup Group creation Failed with error = %!WINERROR!", v15);
      if ( (byte_1800C8404 & 8) == 0 )
        goto LABEL_24;
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v27[2 * v17 - 4] );
    }
    v25 = (unsigned int)(2 * v17 + 2);
    v24 = (const wchar_t *)&v26;
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v16, 2, v23);
    goto LABEL_24;
  }
  if ( (byte_1800C8404 & 8) != 0 )
  {
    v25 = 140;
    v24 = L"DdmThreadPool::Initialize() called when helper is already initialized";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v6, 2, v23);
  }
  return 4317;
}

```

## disassembly

```asm
0x180048510  push    rbp
0x180048512  push    rbx
0x180048513  push    rsi
0x180048514  push    rdi
0x180048515  push    r12
0x180048517  push    r14
0x180048519  push    r15
0x18004851b  lea     rbp, [rsp-770h]
0x180048523  sub     rsp, 870h
0x18004852a  mov     rax, cs:__security_cookie
0x180048531  xor     rax, rsp
0x180048534  mov     [rbp+7A0h+var_40], rax
0x18004853b  mov     r15d, r8d
0x18004853e  mov     r14d, edx
0x180048541  mov     rbx, rcx
0x180048544  xor     r12d, r12d
0x180048547  xor     edx, edx; Val
0x180048549  mov     [rsp+8A0h+var_840], r12d
0x18004854e  mov     r8d, 7FCh; Size
0x180048554  lea     rcx, [rsp+8A0h+var_83C]; void *
0x180048559  call    memset_0
0x18004855e  cmp     [rbx+60h], r12d
0x180048562  jz      short loc_1800485AE
0x180048564  test    cs:byte_1800C8404, 8
0x18004856b  jz      short loc_1800485A4
0x18004856d  lea     rax, aDdmthreadpoolI; "DdmThreadPool::Initialize() called when"...
0x180048574  mov     [rsp+8A0h+var_850], 8Ch
0x18004857d  mov     [rsp+8A0h+var_858], rax
0x180048582  lea     r9d, [r12+2]
0x180048587  lea     rax, [rsp+8A0h+var_868]
0x18004858c  lea     rdx, RasDdmTraceError
0x180048593  mov     [rsp+8A0h+var_880], rax
0x180048598  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004859f  call    McGenEventWrite_EventWriteTransfer
0x1800485a4  mov     eax, 10DDh
0x1800485a9  jmp     loc_180048807
0x1800485ae  xor     ecx, ecx; reserved
0x1800485b0  mov     dword ptr [rbx+18h], 3
0x1800485b7  mov     [rbx+20h], r12
0x1800485bb  mov     [rbx+28h], r12
0x1800485bf  mov     [rbx+30h], r12
0x1800485c3  mov     [rbx+38h], r12
0x1800485c7  mov     [rbx+40h], r12
0x1800485cb  mov     [rbx+48h], r12
0x1800485cf  mov     [rbx+50h], r12d
0x1800485d3  mov     dword ptr [rbx+54h], 1
0x1800485da  mov     dword ptr [rbx+58h], 48h ; 'H'
0x1800485e1  call    cs:__imp_CreateThreadpool
0x1800485e7  mov     [rbx+8], rax
0x1800485eb  test    rax, rax
0x1800485ee  jnz     loc_180048681
0x1800485f4  call    cs:__imp_GetLastError
0x1800485fa  test    cs:byte_1800C8404, 8
0x180048601  mov     esi, eax
0x180048603  jz      short loc_180048678
0x180048605  mov     r8d, eax
0x180048608  mov     word ptr [rsp+8A0h+var_840], r12w
0x18004860e  lea     rdx, aThreadPoolCrea; "Thread Pool Creation Failed with error "...
0x180048615  lea     rcx, [rsp+8A0h+var_840]
0x18004861a  call    FormatRRASErrorString
0x18004861f  test    cs:byte_1800C8404, 8
0x180048626  jz      short loc_180048678
0x180048628  lea     rcx, [rsp+8A0h+var_840]
0x18004862d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048631  inc     rax
0x180048634  cmp     [rcx+rax*2], r12w
0x180048639  jnz     short loc_180048631
0x18004863b  lea     eax, ds:2[rax*2]
0x180048642  mov     dword ptr [rsp+8A0h+var_850+4], r12d
0x180048647  lea     rcx, [rsp+8A0h+var_840]
0x18004864c  mov     dword ptr [rsp+8A0h+var_850], eax
0x180048650  lea     rax, [rsp+8A0h+var_868]
0x180048655  mov     [rsp+8A0h+var_858], rcx
0x18004865a  mov     r9d, 2
0x180048660  mov     [rsp+8A0h+var_880], rax
0x180048665  lea     rdx, RasDdmTraceError
0x18004866c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180048673  call    McGenEventWrite_EventWriteTransfer
0x180048678  lea     rdi, [rbx+10h]
0x18004867c  jmp     loc_1800487B1
0x180048681  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180048687  lea     rdi, [rbx+10h]
0x18004868b  mov     [rdi], rax
0x18004868e  test    rax, rax
0x180048691  jnz     short loc_1800486E7
0x180048693  call    cs:__imp_GetLastError
0x180048699  test    cs:byte_1800C8404, 8
0x1800486a0  mov     esi, eax
0x1800486a2  jz      loc_1800487B1
0x1800486a8  mov     r8d, eax
0x1800486ab  mov     word ptr [rsp+8A0h+var_840], r12w
0x1800486b1  lea     rdx, aThreadPoolClea; "Thread Pool Cleanup Group creation Fail"...
0x1800486b8  lea     rcx, [rsp+8A0h+var_840]
0x1800486bd  call    FormatRRASErrorString
0x1800486c2  test    cs:byte_1800C8404, 8
0x1800486c9  jz      loc_1800487B1
0x1800486cf  lea     rcx, [rsp+8A0h+var_840]
0x1800486d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800486d8  inc     rax
0x1800486db  cmp     [rcx+rax*2], r12w
0x1800486e0  jnz     short loc_1800486D8
0x1800486e2  jmp     loc_180048774
0x1800486e7  mov     rcx, [rbx+8]; ptpp
0x1800486eb  mov     edx, r14d; cthrdMost
0x1800486ee  mov     [rbx+20h], rcx
0x1800486f2  mov     esi, r12d
0x1800486f5  mov     [rbx+28h], rax
0x1800486f9  mov     [rbx+30h], r12
0x1800486fd  call    cs:__imp_SetThreadpoolThreadMaximum
0x180048703  mov     rcx, [rbx+8]; ptpp
0x180048707  mov     edx, r15d; cthrdMic
0x18004870a  call    cs:__imp_SetThreadpoolThreadMinimum
0x180048710  xor     r9d, r9d; lpName
0x180048713  xor     r8d, r8d; bInitialState
0x180048716  xor     edx, edx; bManualReset
0x180048718  xor     ecx, ecx; lpEventAttributes
0x18004871a  call    cs:__imp_CreateEventW
0x180048720  mov     [rbx+68h], rax
0x180048724  test    rax, rax
0x180048727  jnz     loc_1800487FE
0x18004872d  call    cs:__imp_GetLastError
0x180048733  test    cs:byte_1800C8404, 8
0x18004873a  mov     esi, eax
0x18004873c  jz      short loc_1800487B1
0x18004873e  mov     r8d, eax
0x180048741  mov     word ptr [rsp+8A0h+var_840], r12w
0x180048747  lea     rdx, aDdmthreadpoolI_0; "DdmThreadPool::Initialize: CreateEvent "...
0x18004874e  lea     rcx, [rsp+8A0h+var_840]
0x180048753  call    FormatRRASErrorString
0x180048758  test    cs:byte_1800C8404, 8
0x18004875f  jz      short loc_1800487B1
0x180048761  lea     rcx, [rsp+8A0h+var_840]
0x180048766  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004876a  inc     rax
0x18004876d  cmp     [rcx+rax*2], r12w
0x180048772  jnz     short loc_18004876A
0x180048774  lea     eax, ds:2[rax*2]
0x18004877b  mov     dword ptr [rsp+8A0h+var_850+4], r12d
0x180048780  lea     rcx, [rsp+8A0h+var_840]
0x180048785  mov     dword ptr [rsp+8A0h+var_850], eax
0x180048789  lea     rax, [rsp+8A0h+var_868]
0x18004878e  mov     [rsp+8A0h+var_858], rcx
0x180048793  mov     r9d, 2
0x180048799  mov     [rsp+8A0h+var_880], rax
0x18004879e  lea     rdx, RasDdmTraceError
0x1800487a5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800487ac  call    McGenEventWrite_EventWriteTransfer
0x1800487b1  test    esi, esi
0x1800487b3  jz      short loc_1800487FE
0x1800487b5  mov     rcx, [rdi]; ptpcg
0x1800487b8  test    rcx, rcx
0x1800487bb  jz      short loc_1800487D6
0x1800487bd  xor     r8d, r8d; pvCleanupContext
0x1800487c0  lea     edx, [r8+1]; fCancelPendingCallbacks
0x1800487c4  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800487ca  mov     rcx, [rdi]; ptpcg
0x1800487cd  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800487d3  mov     [rdi], r12
0x1800487d6  mov     rcx, [rbx+8]; ptpp
0x1800487da  test    rcx, rcx
0x1800487dd  jz      short loc_1800487E9
0x1800487df  call    cs:__imp_CloseThreadpool
0x1800487e5  mov     [rbx+8], r12
0x1800487e9  mov     rcx, [rbx+68h]; hObject
0x1800487ed  test    rcx, rcx
0x1800487f0  jz      short loc_180048805
0x1800487f2  call    cs:__imp_CloseHandle
0x1800487f8  mov     [rbx+68h], r12
0x1800487fc  jmp     short loc_180048805
0x1800487fe  mov     dword ptr [rbx+60h], 1
0x180048805  mov     eax, esi
0x180048807  mov     rcx, [rbp+7A0h+var_40]
0x18004880e  xor     rcx, rsp; StackCookie
0x180048811  call    __security_check_cookie
0x180048816  add     rsp, 870h
0x18004881d  pop     r15
0x18004881f  pop     r14
0x180048821  pop     r12
0x180048823  pop     rdi
0x180048824  pop     rsi
0x180048825  pop     rbx
0x180048826  pop     rbp
0x180048827  retn
```
