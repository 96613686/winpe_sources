# NtWriteLogRestartAreaInternal(void *,_CLS_LSN *,void *,ulong,__int64 * const,__int64 *,__int64 * const,_CLS_LSN *,_CLS_LSN *,ulong *,void *,ulong,_OVERLAPPED *)

- ea: `0x180009378`
- end: `0x1800095d8`
- name: `?NtWriteLogRestartAreaInternal@@YAKPEAXPEAT_CLS_LSN@@0KQEA_JPEA_J211PEAK0KPEAU_OVERLAPPED@@@Z`
- size: `608`
- prototype: `unsigned int(void *, union _CLS_LSN *, void *, unsigned int, __int64 *const, __int64 *, __int64 *const, union _CLS_LSN *, union _CLS_LSN *, unsigned int *, void *, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014328`

## callees

- `0x180009378`
- `0x180014e00`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000956b`
- `ntdll!RtlNtStatusToDosError` at `0x18000956b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009538`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000958a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000958a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009522`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180009522`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180009492`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180009492`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009552`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009552`

## pseudocode

```c
__int64 __fastcall NtWriteLogRestartAreaInternal(
        void *a1,
        union _CLS_LSN *a2,
        _QWORD *a3,
        DWORD nOutBufferSize,
        __int64 *const a5,
        __int64 *a6,
        __int64 *const a7,
        union _CLS_LSN *a8,
        union _CLS_LSN *a9,
        LPDWORD a10,
        void *a11,
        char a12)
{
  DWORD LastError; // ebx
  DWORD *lpBytesReturned; // rcx
  unsigned __int64 EventA; // rax
  void *v17; // rcx
  DWORD v18; // [rsp+40h] [rbp-81h]
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-79h] BYREF
  unsigned int *v20; // [rsp+68h] [rbp-59h]
  union _CLS_LSN *v21; // [rsp+70h] [rbp-51h]
  __int64 *v22; // [rsp+78h] [rbp-49h]
  HANDLE hDevice; // [rsp+80h] [rbp-41h]
  __int128 InBuffer; // [rsp+88h] [rbp-39h] BYREF
  __int64 v25; // [rsp+98h] [rbp-29h]
  _BYTE v26[20]; // [rsp+A0h] [rbp-21h] BYREF
  int v27; // [rsp+B4h] [rbp-Dh]

  LastError = 0;
  hDevice = a1;
  lpBytesReturned = a10;
  v18 = nOutBufferSize;
  v21 = a2;
  v22 = a5;
  v20 = a10;
  memset(&Overlapped, 0, sizeof(Overlapped));
  v25 = 0;
  memset(v26, 0, sizeof(v26));
  v27 = 0;
  InBuffer = 0;
  if ( !a2
    || !a5
    || !a6
    || !a7
    || !a9
    || !a8
    || !a10
    || CLFS_LSN_INVALID.ullOffset == a8->ullOffset
    || *a6 < 0
    || *a7 < 0 )
  {
    return 87;
  }
  if ( nOutBufferSize && !a3 )
    return 1784;
  if ( a11 )
  {
    EventA = (unsigned __int64)a11;
  }
  else
  {
    EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
    if ( !EventA )
      return 8;
    nOutBufferSize = v18;
    lpBytesReturned = v20;
    a2 = v21;
  }
  Overlapped.hEvent = (HANDLE)(EventA | 1);
  *(union _CLS_LSN *)v26 = *a2;
  *(union _CLS_LSN *)&v26[8] = *a8;
  v25 = *a6;
  *((_QWORD *)&InBuffer + 1) = *a7;
  *(_QWORD *)&InBuffer = *v22;
  v26[16] = (a12 & 2) != 0;
  if ( !DeviceIoControl(hDevice, 0x8007281F, &InBuffer, 0x30u, a3, nOutBufferSize, lpBytesReturned, &Overlapped) )
  {
    LastError = GetLastError();
    if ( LastError == 997 )
    {
      if ( WaitForSingleObject(Overlapped.hEvent, 0xFFFFFFFF) )
        LastError = 1117;
      else
        LastError = RtlNtStatusToDosError(Overlapped.Internal);
    }
  }
  v17 = (void *)((unsigned __int64)Overlapped.hEvent & 0xFFFFFFFFFFFFFFFEuLL);
  Overlapped.hEvent = (HANDLE)((unsigned __int64)Overlapped.hEvent & ~1uLL);
  if ( !a11 )
    CloseHandle(v17);
  if ( !LastError || LastError == 997 )
  {
    *a9 = (union _CLS_LSN)a3[4];
    *a6 = a3[3];
  }
  return LastError;
}

```

## disassembly

```asm
0x180009378  push    rbp
0x18000937a  push    rbx
0x18000937b  push    rsi
0x18000937c  push    rdi
0x18000937d  push    r12
0x18000937f  push    r13
0x180009381  push    r14
0x180009383  push    r15
0x180009385  lea     rbp, [rsp-7]
0x18000938a  sub     rsp, 0C8h
0x180009391  mov     rax, cs:__security_cookie
0x180009398  xor     rax, rsp
0x18000939b  mov     [rbp+3Fh+var_48], rax
0x18000939f  mov     rax, [rbp+3Fh+arg_20]
0x1800093a3  xor     ebx, ebx
0x1800093a5  mov     r12, [rbp+3Fh+arg_38]
0x1800093ac  xorps   xmm0, xmm0
0x1800093af  mov     rsi, [rbp+3Fh+arg_28]
0x1800093b3  mov     rdi, r8
0x1800093b6  mov     r15, [rbp+3Fh+arg_30]
0x1800093ba  xor     r8d, r8d; bInitialState
0x1800093bd  mov     r13, [rbp+3Fh+arg_40]
0x1800093c4  mov     r14, [rbp+3Fh+arg_50]
0x1800093cb  mov     [rbp+3Fh+hDevice], rcx
0x1800093cf  mov     rcx, [rbp+3Fh+arg_48]
0x1800093d6  mov     [rsp+100h+var_C0], r9d
0x1800093db  mov     [rbp+3Fh+var_90], rdx
0x1800093df  mov     [rbp+3Fh+var_88], rax
0x1800093e3  mov     [rbp+3Fh+var_98], rcx
0x1800093e7  mov     [rbp+3Fh+Overlapped.Internal], rbx
0x1800093eb  mov     [rbp+3Fh+Overlapped.InternalHigh], rbx
0x1800093ef  mov     qword ptr [rbp+3Fh+Overlapped.10h], rbx
0x1800093f3  mov     [rbp+3Fh+Overlapped.hEvent], rbx
0x1800093f7  mov     [rbp+3Fh+var_68], rbx
0x1800093fb  mov     dword ptr [rbp+3Fh+var_60], ebx
0x1800093fe  mov     [rbp+3Fh+var_4C], r8d
0x180009402  movdqu  [rbp+3Fh+InBuffer], xmm0
0x180009407  movups  xmmword ptr [rbp+3Fh+var_60+4], xmm0
0x18000940b  test    rdx, rdx
0x18000940e  jz      loc_1800095B2
0x180009414  test    rax, rax
0x180009417  jz      loc_1800095B2
0x18000941d  test    rsi, rsi
0x180009420  jz      loc_1800095B2
0x180009426  test    r15, r15
0x180009429  jz      loc_1800095B2
0x18000942f  test    r13, r13
0x180009432  jz      loc_1800095B2
0x180009438  test    r12, r12
0x18000943b  jz      loc_1800095B2
0x180009441  test    rcx, rcx
0x180009444  jz      loc_1800095B2
0x18000944a  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180009451  cmp     rax, [r12]
0x180009455  jz      loc_1800095B2
0x18000945b  cmp     [rsi], rbx
0x18000945e  jl      loc_1800095B2
0x180009464  cmp     [r15], rbx
0x180009467  jl      loc_1800095B2
0x18000946d  test    r9d, r9d
0x180009470  jz      short loc_180009481
0x180009472  test    rdi, rdi
0x180009475  jnz     short loc_180009481
0x180009477  mov     eax, 6F8h
0x18000947c  jmp     loc_1800095B7
0x180009481  test    r14, r14
0x180009484  jz      short loc_18000948B
0x180009486  mov     rax, r14
0x180009489  jmp     short loc_1800094BA
0x18000948b  xor     r9d, r9d; lpName
0x18000948e  xor     edx, edx; bManualReset
0x180009490  xor     ecx, ecx; lpEventAttributes
0x180009492  call    cs:__imp_CreateEventA
0x180009499  nop     dword ptr [rax+rax+00h]
0x18000949e  test    rax, rax
0x1800094a1  jnz     short loc_1800094AD
0x1800094a3  mov     eax, 8
0x1800094a8  jmp     loc_1800095B7
0x1800094ad  mov     r9d, [rsp+100h+var_C0]
0x1800094b2  mov     rcx, [rbp+3Fh+var_98]
0x1800094b6  mov     rdx, [rbp+3Fh+var_90]
0x1800094ba  or      rax, 1
0x1800094be  lea     r8, [rbp+3Fh+InBuffer]; lpInBuffer
0x1800094c2  mov     [rbp+3Fh+Overlapped.hEvent], rax
0x1800094c6  mov     rax, [rdx]
0x1800094c9  mov     edx, 8007281Fh; dwIoControlCode
0x1800094ce  mov     [rbp+3Fh+var_60], rax
0x1800094d2  mov     rax, [r12]
0x1800094d6  mov     [rbp+3Fh+var_58], rax
0x1800094da  mov     rax, [rsi]
0x1800094dd  mov     [rbp+3Fh+var_68], rax
0x1800094e1  mov     rax, [r15]
0x1800094e4  mov     qword ptr [rbp+3Fh+InBuffer+8], rax
0x1800094e8  mov     rax, [rbp+3Fh+var_88]
0x1800094ec  mov     rax, [rax]
0x1800094ef  mov     qword ptr [rbp+3Fh+InBuffer], rax
0x1800094f3  mov     eax, [rbp+3Fh+arg_58]
0x1800094f9  shr     eax, 1
0x1800094fb  and     al, 1
0x1800094fd  mov     [rbp+3Fh+var_50], al
0x180009500  lea     rax, [rbp+3Fh+Overlapped]
0x180009504  mov     [rsp+100h+lpOverlapped], rax; lpOverlapped
0x180009509  mov     [rsp+100h+lpBytesReturned], rcx; lpBytesReturned
0x18000950e  mov     rcx, [rbp+3Fh+hDevice]; hDevice
0x180009512  mov     [rsp+100h+nOutBufferSize], r9d; nOutBufferSize
0x180009517  mov     r9d, 30h ; '0'; nInBufferSize
0x18000951d  mov     [rsp+100h+lpOutBuffer], rdi; lpOutBuffer
0x180009522  call    cs:__imp_DeviceIoControl
0x180009529  nop     dword ptr [rax+rax+00h]
0x18000952e  mov     r15d, 3E5h
0x180009534  test    eax, eax
0x180009536  jnz     short loc_180009579
0x180009538  call    cs:__imp_GetLastError
0x18000953f  nop     dword ptr [rax+rax+00h]
0x180009544  mov     ebx, eax
0x180009546  cmp     eax, r15d
0x180009549  jnz     short loc_180009579
0x18000954b  mov     rcx, [rbp+3Fh+Overlapped.hEvent]; hHandle
0x18000954f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009552  call    cs:__imp_WaitForSingleObject
0x180009559  nop     dword ptr [rax+rax+00h]
0x18000955e  test    eax, eax
0x180009560  jz      short loc_180009568
0x180009562  lea     ebx, [r15+78h]
0x180009566  jmp     short loc_180009579
0x180009568  mov     ecx, dword ptr [rbp+3Fh+Overlapped.Internal]; Status
0x18000956b  call    cs:__imp_RtlNtStatusToDosError
0x180009572  nop     dword ptr [rax+rax+00h]
0x180009577  mov     ebx, eax
0x180009579  mov     rcx, [rbp+3Fh+Overlapped.hEvent]
0x18000957d  and     rcx, 0FFFFFFFFFFFFFFFEh; hObject
0x180009581  mov     [rbp+3Fh+Overlapped.hEvent], rcx
0x180009585  test    r14, r14
0x180009588  jnz     short loc_180009596
0x18000958a  call    cs:__imp_CloseHandle
0x180009591  nop     dword ptr [rax+rax+00h]
0x180009596  test    ebx, ebx
0x180009598  jz      short loc_18000959F
0x18000959a  cmp     ebx, r15d
0x18000959d  jnz     short loc_1800095AE
0x18000959f  mov     rax, [rdi+20h]
0x1800095a3  mov     [r13+0], rax
0x1800095a7  mov     rax, [rdi+18h]
0x1800095ab  mov     [rsi], rax
0x1800095ae  mov     eax, ebx
0x1800095b0  jmp     short loc_1800095B7
0x1800095b2  mov     eax, 57h ; 'W'
0x1800095b7  mov     rcx, [rbp+3Fh+var_48]
0x1800095bb  xor     rcx, rsp; StackCookie
0x1800095be  call    __security_check_cookie
0x1800095c3  add     rsp, 0C8h
0x1800095ca  pop     r15
0x1800095cc  pop     r14
0x1800095ce  pop     r13
0x1800095d0  pop     r12
0x1800095d2  pop     rdi
0x1800095d3  pop     rsi
0x1800095d4  pop     rbx
0x1800095d5  pop     rbp
0x1800095d6  retn
```
