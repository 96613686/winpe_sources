# NtReserveAndAppendLogInternal(void *,void *,ulong,__int64 *,__int64 *,__int64 * const,ulong,_CLS_LSN *,ulong *,_CLS_LSN *,_CLS_LSN *,_CLS_INFORMATION *,ulong *,void *,uchar,_OVERLAPPED *)

- ea: `0x180009090`
- end: `0x18000936f`
- name: `?NtReserveAndAppendLogInternal@@YAKPEAX0KPEA_J1QEA_JKPEAT_CLS_LSN@@PEAK33PEAU_CLS_INFORMATION@@40EPEAU_OVERLAPPED@@@Z`
- size: `735`
- prototype: `unsigned int __fastcall(void *, void *, unsigned int, __int64 *, __int64 *, __int64 *const, unsigned int, union _CLS_LSN *, DWORD BytesReturned, union _CLS_LSN *, union _CLS_LSN *, struct _CLS_INFORMATION *, unsigned int *, void *, char, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000efa0`
- `0x1800135a4`

## callees

- `0x180009090`
- `0x180014dce`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800092ee`
- `ntdll!RtlNtStatusToDosError` at `0x1800092ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000930f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000930f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000929b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000929b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800091be`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800091be`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800092d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800092d5`

## pseudocode

```c
__int64 __fastcall NtReserveAndAppendLogInternal(
        void *a1,
        void *a2,
        int a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *const a6,
        unsigned int a7,
        union _CLS_LSN *a8,
        DWORD BytesReturned,
        union _CLS_LSN *a10,
        union _CLS_LSN *a11,
        struct _CLS_INFORMATION *a12,
        unsigned int *a13,
        unsigned __int64 a14,
        char a15,
        struct _OVERLAPPED *a16)
{
  unsigned int *v19; // r14
  CLFS_LSN *v21; // rcx
  unsigned __int64 v22; // r15
  struct _OVERLAPPED *v23; // rsi
  struct _OVERLAPPED *p_Overlapped; // rbx
  unsigned __int64 EventA; // rax
  DWORD LastError; // edi
  const CLFS_LSN *v27; // rax
  CLFS_LSN v28; // [rsp+48h] [rbp-71h] BYREF
  CLFS_LSN *v29; // [rsp+50h] [rbp-69h]
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-61h] BYREF
  _QWORD InBuffer[6]; // [rsp+78h] [rbp-41h] BYREF
  struct _CLS_INFORMATION *v32; // [rsp+A8h] [rbp-11h]
  unsigned int v33; // [rsp+B0h] [rbp-9h]
  bool v34; // [rsp+B4h] [rbp-5h]

  BytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  memset_0(InBuffer, 0, 0x40u);
  v28 = CLFS_LSN_INVALID;
  if ( !a4 || !a5 || !a6 || !a10 || *a5 < 0 || *a6 < 0 || (a7 & 0xFFFFFFFD) != 0 )
    return 87;
  if ( a3 && !a2 )
    return 1784;
  v19 = a13;
  if ( a13 )
  {
    if ( *a13 && !a12 )
      return 1784;
  }
  v21 = &v28;
  v22 = a14;
  v23 = a16;
  if ( a11 )
    v21 = a11;
  v29 = v21;
  if ( a14 )
  {
    p_Overlapped = &Overlapped;
    Overlapped.hEvent = (HANDLE)(a14 | 1);
  }
  else if ( a16 )
  {
    p_Overlapped = a16;
  }
  else
  {
    EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
    if ( !EventA )
      return 8;
    v21 = v29;
    p_Overlapped = &Overlapped;
    Overlapped.hEvent = (HANDLE)(EventA | 1);
  }
  LastError = 0;
  InBuffer[1] = a5;
  InBuffer[4] = v21;
  InBuffer[0] = *a4;
  InBuffer[2] = *a6;
  InBuffer[3] = a10;
  v27 = a8;
  if ( !a8 )
    v27 = &CLFS_LSN_NULL;
  InBuffer[5] = v27->ullOffset;
  v34 = (a7 & 2) != 0;
  if ( v19 )
  {
    v32 = a12;
    v33 = *v19;
  }
  else
  {
    v32 = 0;
    v33 = 0;
  }
  if ( !DeviceIoControl(a1, 0x8007A827, InBuffer, 0x40u, a2, (a3 + 511) & 0xFFFFFE00, &BytesReturned, p_Overlapped) )
    LastError = GetLastError();
  if ( v22 || !v23 )
  {
    if ( LastError == 997 )
    {
      if ( WaitForSingleObject(p_Overlapped->hEvent, 0xFFFFFFFF) )
        LastError = 1117;
      else
        LastError = RtlNtStatusToDosError(p_Overlapped->Internal);
    }
    p_Overlapped->hEvent = (HANDLE)((unsigned __int64)p_Overlapped->hEvent & ~1uLL);
    if ( !v22 && !v23 )
      CloseHandle(p_Overlapped->hEvent);
    p_Overlapped->hEvent = 0;
  }
  if ( !LastError && v23 && a15 && (!v23->hEvent || ((__int64)v23->hEvent & 1) == 0) )
    return 997;
  if ( v19 )
  {
    if ( !LastError )
      *v19 = v33;
  }
  return LastError;
}

```

## disassembly

```asm
0x180009090  mov     rax, rsp
0x180009093  mov     [rax+20h], r9
0x180009097  mov     [rax+18h], r8d
0x18000909b  mov     [rax+10h], rdx
0x18000909f  mov     [rax+8], rcx
0x1800090a3  push    rbp
0x1800090a4  push    rbx
0x1800090a5  push    rsi
0x1800090a6  push    rdi
0x1800090a7  push    r12
0x1800090a9  push    r13
0x1800090ab  push    r14
0x1800090ad  push    r15
0x1800090af  lea     rbp, [rax-47h]
0x1800090b3  sub     rsp, 0B8h
0x1800090ba  xor     r15d, r15d
0x1800090bd  lea     rcx, [rbp+3Fh+InBuffer]; void *
0x1800090c1  mov     ebx, r8d
0x1800090c4  mov     [rbp+3Fh+BytesReturned], r15d
0x1800090cb  mov     rdi, rdx
0x1800090ce  mov     [rbp+3Fh+Overlapped.Internal], r15
0x1800090d2  xor     edx, edx; Val
0x1800090d4  mov     [rbp+3Fh+Overlapped.InternalHigh], r15
0x1800090d8  lea     r8d, [r15+40h]; Size
0x1800090dc  mov     qword ptr [rbp+3Fh+Overlapped.10h], r15
0x1800090e0  mov     rsi, r9
0x1800090e3  mov     [rbp+3Fh+Overlapped.hEvent], r15
0x1800090e7  call    memset_0
0x1800090ec  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x1800090f3  mov     [rbp+3Fh+var_B0], rax
0x1800090f7  test    rsi, rsi
0x1800090fa  jz      loc_180009355
0x180009100  mov     r12, [rbp+3Fh+arg_20]
0x180009104  test    r12, r12
0x180009107  jz      loc_180009355
0x18000910d  mov     r13, [rbp+3Fh+arg_28]
0x180009111  test    r13, r13
0x180009114  jz      loc_180009355
0x18000911a  cmp     [rbp+3Fh+arg_48], r15
0x180009121  jz      loc_180009355
0x180009127  cmp     [r12], r15
0x18000912b  jl      loc_180009355
0x180009131  cmp     [r13+0], r15
0x180009135  jl      loc_180009355
0x18000913b  test    [rbp+3Fh+arg_30], 0FFFFFFFDh
0x180009142  jnz     loc_180009355
0x180009148  test    ebx, ebx
0x18000914a  jz      short loc_180009151
0x18000914c  test    rdi, rdi
0x18000914f  jz      short loc_18000916B
0x180009151  mov     r14, [rbp+3Fh+arg_60]
0x180009158  test    r14, r14
0x18000915b  jz      short loc_180009175
0x18000915d  cmp     [r14], r15d
0x180009160  jbe     short loc_180009175
0x180009162  cmp     [rbp+3Fh+arg_58], r15
0x180009169  jnz     short loc_180009175
0x18000916b  mov     eax, 6F8h
0x180009170  jmp     loc_18000935A
0x180009175  mov     rax, [rbp+3Fh+arg_50]
0x18000917c  lea     rcx, [rbp+3Fh+var_B0]
0x180009180  mov     r15, [rbp+3Fh+arg_68]
0x180009187  test    rax, rax
0x18000918a  mov     rsi, [rbp+3Fh+arg_78]
0x180009191  cmovnz  rcx, rax
0x180009195  mov     [rbp+3Fh+var_A8], rcx
0x180009199  test    r15, r15
0x18000919c  jz      short loc_1800091AF
0x18000919e  mov     rax, r15
0x1800091a1  lea     rbx, [rbp+3Fh+Overlapped]
0x1800091a5  or      rax, 1
0x1800091a9  mov     [rbp+3Fh+Overlapped.hEvent], rax
0x1800091ad  jmp     short loc_1800091EC
0x1800091af  test    rsi, rsi
0x1800091b2  jnz     short loc_1800091E9
0x1800091b4  xor     r9d, r9d; lpName
0x1800091b7  xor     r8d, r8d; bInitialState
0x1800091ba  xor     edx, edx; bManualReset
0x1800091bc  xor     ecx, ecx; lpEventAttributes
0x1800091be  call    cs:__imp_CreateEventA
0x1800091c5  nop     dword ptr [rax+rax+00h]
0x1800091ca  test    rax, rax
0x1800091cd  jnz     short loc_1800091D7
0x1800091cf  lea     eax, [rsi+8]
0x1800091d2  jmp     loc_18000935A
0x1800091d7  mov     rcx, [rbp+3Fh+var_A8]
0x1800091db  lea     rbx, [rbp+3Fh+Overlapped]
0x1800091df  or      rax, 1
0x1800091e3  mov     [rbp+3Fh+Overlapped.hEvent], rax
0x1800091e7  jmp     short loc_1800091EC
0x1800091e9  mov     rbx, rsi
0x1800091ec  mov     rax, [rbp+3Fh+arg_18]
0x1800091f0  xor     edi, edi
0x1800091f2  mov     [rbp+3Fh+var_78], r12
0x1800091f6  xor     r12d, r12d
0x1800091f9  mov     [rbp+3Fh+var_60], rcx
0x1800091fd  lea     rcx, CLFS_LSN_NULL
0x180009204  mov     rax, [rax]
0x180009207  mov     [rbp+3Fh+InBuffer], rax
0x18000920b  mov     rax, [r13+0]
0x18000920f  mov     [rbp+3Fh+var_70], rax
0x180009213  mov     rax, [rbp+3Fh+arg_48]
0x18000921a  mov     [rbp+3Fh+var_68], rax
0x18000921e  mov     rax, [rbp+3Fh+arg_38]
0x180009225  test    rax, rax
0x180009228  cmovz   rax, rcx
0x18000922c  mov     rax, [rax]
0x18000922f  mov     [rbp+3Fh+var_58], rax
0x180009233  mov     eax, [rbp+3Fh+arg_30]
0x180009236  shr     al, 1
0x180009238  and     al, 1
0x18000923a  mov     [rbp+3Fh+var_44], al
0x18000923d  test    r14, r14
0x180009240  jz      short loc_180009255
0x180009242  mov     rax, [rbp+3Fh+arg_58]
0x180009249  mov     [rbp+3Fh+var_50], rax
0x18000924d  mov     eax, [r14]
0x180009250  mov     [rbp+3Fh+var_48], eax
0x180009253  jmp     short loc_18000925D
0x180009255  mov     [rbp+3Fh+var_50], r12
0x180009259  mov     [rbp+3Fh+var_48], r12d
0x18000925d  mov     eax, [rbp+3Fh+arg_10]
0x180009260  lea     rcx, [rbp+3Fh+BytesReturned]
0x180009267  add     eax, 1FFh
0x18000926c  mov     [rsp+38h], rbx; lpOverlapped
0x180009271  mov     [rsp+0F0h+lpBytesReturned], rcx; lpBytesReturned
0x180009276  lea     r8, [rbp+3Fh+InBuffer]; lpInBuffer
0x18000927a  mov     rcx, [rbp+3Fh+hDevice]; hDevice
0x18000927e  and     eax, 0FFFFFE00h
0x180009283  mov     [rsp+0F0h+nOutBufferSize], eax; nOutBufferSize
0x180009287  mov     r9d, 40h ; '@'; nInBufferSize
0x18000928d  mov     rax, [rbp+3Fh+arg_8]
0x180009291  mov     edx, 8007A827h; dwIoControlCode
0x180009296  mov     [rsp+0F0h+lpOutBuffer], rax; lpOutBuffer
0x18000929b  call    cs:__imp_DeviceIoControl
0x1800092a2  nop     dword ptr [rax+rax+00h]
0x1800092a7  test    eax, eax
0x1800092a9  jnz     short loc_1800092B9
0x1800092ab  call    cs:__imp_GetLastError
0x1800092b2  nop     dword ptr [rax+rax+00h]
0x1800092b7  mov     edi, eax
0x1800092b9  mov     r13d, 3E5h
0x1800092bf  test    r15, r15
0x1800092c2  jnz     short loc_1800092C9
0x1800092c4  test    rsi, rsi
0x1800092c7  jnz     short loc_18000931F
0x1800092c9  cmp     edi, r13d
0x1800092cc  jnz     short loc_1800092FC
0x1800092ce  mov     rcx, [rbx+18h]; hHandle
0x1800092d2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800092d5  call    cs:__imp_WaitForSingleObject
0x1800092dc  nop     dword ptr [rax+rax+00h]
0x1800092e1  test    eax, eax
0x1800092e3  jz      short loc_1800092EC
0x1800092e5  mov     edi, 45Dh
0x1800092ea  jmp     short loc_1800092FC
0x1800092ec  mov     ecx, [rbx]; Status
0x1800092ee  call    cs:__imp_RtlNtStatusToDosError
0x1800092f5  nop     dword ptr [rax+rax+00h]
0x1800092fa  mov     edi, eax
0x1800092fc  and     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFEh
0x180009301  test    r15, r15
0x180009304  jnz     short loc_18000931B
0x180009306  test    rsi, rsi
0x180009309  jnz     short loc_18000931B
0x18000930b  mov     rcx, [rbx+18h]; hObject
0x18000930f  call    cs:__imp_CloseHandle
0x180009316  nop     dword ptr [rax+rax+00h]
0x18000931b  mov     [rbx+18h], r12
0x18000931f  test    edi, edi
0x180009321  jnz     short loc_180009342
0x180009323  test    rsi, rsi
0x180009326  jz      short loc_180009342
0x180009328  cmp     [rbp+3Fh+arg_70], r12b
0x18000932f  jz      short loc_180009342
0x180009331  cmp     [rsi+18h], r12
0x180009335  jz      short loc_18000933D
0x180009337  test    byte ptr [rsi+18h], 1
0x18000933b  jnz     short loc_180009342
0x18000933d  mov     eax, r13d
0x180009340  jmp     short loc_18000935A
0x180009342  test    r14, r14
0x180009345  jz      short loc_180009351
0x180009347  test    edi, edi
0x180009349  jnz     short loc_180009351
0x18000934b  mov     eax, [rbp+3Fh+var_48]
0x18000934e  mov     [r14], eax
0x180009351  mov     eax, edi
0x180009353  jmp     short loc_18000935A
0x180009355  mov     eax, 57h ; 'W'
0x18000935a  add     rsp, 0B8h
0x180009361  pop     r15
0x180009363  pop     r14
0x180009365  pop     r13
0x180009367  pop     r12
0x180009369  pop     rdi
0x18000936a  pop     rsi
0x18000936b  pop     rbx
0x18000936c  pop     rbp
0x18000936d  retn
```
