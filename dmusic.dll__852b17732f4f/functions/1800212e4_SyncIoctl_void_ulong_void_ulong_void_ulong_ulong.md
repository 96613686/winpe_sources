# SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x1800212e4`
- end: `0x180021597`
- name: `?SyncIoctl@@YAJPEAXK0K0KPEAK@Z`
- size: `691`
- prototype: `__int64 __fastcall(void *, unsigned int, void *, unsigned int, void *, DWORD, LPDWORD lpNumberOfBytesTransferred)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180016080`
- `0x18001e2b0`
- `0x18001f238`
- `0x18001feb0`
- `0x18001ff20`
- `0x18001ff90`
- `0x180020148`
- `0x180021254`
- `0x1800212e4`

## callees

- `0x180007664`
- `0x180007684`
- `0x1800212e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180021333`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180021333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800213e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002150d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002157e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002150d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002157e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800213ad`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800213ad`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800213de`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800213de`

## pseudocode

```c
__int64 __fastcall SyncIoctl(
        void *a1,
        DWORD a2,
        void *a3,
        unsigned int a4,
        void *a5,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred)
{
  DWORD *lpBytesReturned; // rdi
  unsigned __int64 EventA; // rax
  const char *v13; // r9
  char *v14; // rsi
  signed int v15; // ebx
  DWORD LastError; // eax
  bool v17; // sf
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  int lpOutBuffer; // [rsp+20h] [rbp-58h]
  DWORD v23; // [rsp+40h] [rbp-38h] BYREF
  int v24; // [rsp+44h] [rbp-34h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v24 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  lpBytesReturned = (DWORD *)&v24;
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  EventA = (unsigned __int64)CreateEventA(0, 0, 0, 0);
  v14 = (char *)EventA;
  if ( ((EventA + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    Overlapped.hEvent = (HANDLE)(EventA | 1);
    if ( !DeviceIoControl(a1, a2, a3, a4, a5, nOutBufferSize, lpBytesReturned, &Overlapped) )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError == 997 )
      {
        v15 = 0;
        if ( GetOverlappedResult(a1, &Overlapped, lpBytesReturned, 1) )
          goto LABEL_12;
        v15 = GetLastError();
LABEL_10:
        v17 = v15 < 0;
        if ( v15 <= 0 )
          goto LABEL_13;
        v15 = (unsigned __int16)v15 | 0x80070000;
LABEL_12:
        v17 = v15 < 0;
LABEL_13:
        if ( v17 )
        {
          if ( v15 == -2147024846 )
            goto LABEL_42;
          v18 = (unsigned int)(v15 + 2147023779);
          if ( (unsigned int)v18 <= 0x35 )
          {
            v19 = 0x28000000000001LL;
            if ( _bittest64(&v19, v18) )
              goto LABEL_42;
          }
          if ( v15 == -2147024875 || v15 == -2147024774 || v15 == -2147023279 || v15 == -2147024809 )
            goto LABEL_42;
          v20 = 216;
          goto LABEL_41;
        }
LABEL_35:
        CloseHandle(v14);
        return 0;
      }
      if ( LastError != 122 && LastError != 234 || a2 != 3080195 || nOutBufferSize )
        goto LABEL_10;
      if ( !*lpBytesReturned )
      {
        v23 = 0;
        if ( (int)SyncIoctl(a1, 0x2F0003u, a3, a4, &v23, 4u, lpBytesReturned) < 0 )
          goto LABEL_10;
        *lpBytesReturned = v23;
      }
      v15 = 0;
      goto LABEL_12;
    }
    if ( Overlapped.Internal != 258 )
    {
      if ( Overlapped.Internal == 261 )
      {
        v15 = -2147024662;
      }
      else
      {
        if ( Overlapped.Internal != 3221225659 )
        {
          if ( Overlapped.Internal == 3221225680 )
          {
            v15 = -2147024825;
            v20 = 238;
          }
          else
          {
            if ( Overlapped.Internal != 3221226048 )
              goto LABEL_35;
            v15 = -2147023661;
            v20 = 246;
          }
LABEL_41:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"avcore\\audiocore\\lib\\kslib\\kslib.cpp",
            (const char *)(unsigned int)v15,
            lpOutBuffer);
          goto LABEL_42;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"avcore\\audiocore\\lib\\kslib\\kslib.cpp",
          (const char *)0x80070032LL,
          lpOutBuffer);
        v15 = -2147024846;
      }
LABEL_42:
      *lpBytesReturned = 0;
LABEL_43:
      CloseHandle(v14);
      return (unsigned int)v15;
    }
    v15 = -2147023436;
    v20 = 234;
    goto LABEL_41;
  }
  v15 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x89,
          (unsigned int)"avcore\\audiocore\\lib\\kslib\\kslib.cpp",
          v13);
  *lpBytesReturned = 0;
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_43;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800212e4  mov     [rsp-40h+lpInBuffer], r8
0x1800212e9  push    rbp
0x1800212ea  push    rbx
0x1800212eb  push    rsi
0x1800212ec  push    rdi
0x1800212ed  push    r12
0x1800212ef  push    r13
0x1800212f1  push    r14
0x1800212f3  push    r15
0x1800212f5  mov     rbp, rsp
0x1800212f8  sub     rsp, 78h
0x1800212fc  mov     r13d, r9d
0x1800212ff  mov     rbx, r8
0x180021302  mov     r12d, edx
0x180021305  mov     r14, rcx
0x180021308  mov     [rbp+var_34], 0
0x18002130f  xorps   xmm0, xmm0
0x180021312  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x180021316  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x18002131a  lea     rdi, [rbp+var_34]
0x18002131e  mov     rax, [rbp+lpNumberOfBytesTransferred]
0x180021322  test    rax, rax
0x180021325  cmovnz  rdi, rax
0x180021329  xor     r9d, r9d; lpName
0x18002132c  xor     r8d, r8d; bInitialState
0x18002132f  xor     edx, edx; bManualReset
0x180021331  xor     ecx, ecx; lpEventAttributes
0x180021333  call    cs:__imp_CreateEventA
0x180021339  mov     rsi, rax
0x18002133c  lea     rcx, [rax+1]
0x180021340  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180021347  jnz     short loc_180021379
0x180021349  mov     rcx, [rbp+40h]; this
0x18002134d  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\lib\\kslib\\kslib.cp"...
0x180021354  mov     edx, 89h; void *
0x180021359  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002135e  mov     ebx, eax
0x180021360  mov     dword ptr [rdi], 0
0x180021366  lea     rcx, [rsi-1]
0x18002136a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002136e  ja      loc_180021584
0x180021374  jmp     loc_18002157B
0x180021379  or      rax, 1
0x18002137d  mov     [rbp+Overlapped.hEvent], rax
0x180021381  lea     rax, [rbp+Overlapped]
0x180021385  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x18002138a  mov     [rsp+78h+lpBytesReturned], rdi; lpBytesReturned
0x18002138f  mov     r15d, [rbp+arg_28]
0x180021393  mov     [rsp+78h+nOutBufferSize], r15d; nOutBufferSize
0x180021398  mov     rax, [rbp+arg_20]
0x18002139c  mov     [rsp+78h+lpOutBuffer], rax; int
0x1800213a1  mov     r9d, r13d; nInBufferSize
0x1800213a4  mov     r8, rbx; lpInBuffer
0x1800213a7  mov     edx, r12d; dwIoControlCode
0x1800213aa  mov     rcx, r14; hDevice
0x1800213ad  call    cs:__imp_DeviceIoControl
0x1800213b3  test    eax, eax
0x1800213b5  jnz     loc_1800214D8
0x1800213bb  call    cs:__imp_GetLastError
0x1800213c1  mov     ebx, eax
0x1800213c3  cmp     eax, 3E5h
0x1800213c8  jnz     loc_18002146A
0x1800213ce  xor     ebx, ebx
0x1800213d0  lea     r9d, [rbx+1]; bWait
0x1800213d4  mov     r8, rdi; lpNumberOfBytesTransferred
0x1800213d7  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1800213db  mov     rcx, r14; hFile
0x1800213de  call    cs:__imp_GetOverlappedResult
0x1800213e4  test    eax, eax
0x1800213e6  jnz     short loc_1800213FD
0x1800213e8  call    cs:__imp_GetLastError
0x1800213ee  mov     ebx, eax
0x1800213f0  test    ebx, ebx
0x1800213f2  jle     short loc_1800213FF
0x1800213f4  movzx   ebx, bx
0x1800213f7  or      ebx, 80070000h
0x1800213fd  test    ebx, ebx
0x1800213ff  jns     loc_18002150A
0x180021405  cmp     ebx, 80070032h
0x18002140b  jz      loc_180021575
0x180021411  lea     eax, [rbx+7FF8FBA3h]
0x180021417  cmp     eax, 35h ; '5'
0x18002141a  ja      short loc_180021430
0x18002141c  mov     rcx, 28000000000001h
0x180021426  bt      rcx, rax
0x18002142a  jb      loc_180021575
0x180021430  cmp     ebx, 80070015h
0x180021436  jz      loc_180021575
0x18002143c  cmp     ebx, 8007007Ah
0x180021442  jz      loc_180021575
0x180021448  cmp     ebx, 80070651h
0x18002144e  jz      loc_180021575
0x180021454  cmp     ebx, 80070057h
0x18002145a  jz      loc_180021575
0x180021460  mov     edx, 0D8h
0x180021465  jmp     loc_180021562
0x18002146a  cmp     eax, 7Ah ; 'z'
0x18002146d  jz      short loc_18002147A
0x18002146f  cmp     eax, 0EAh
0x180021474  jnz     loc_1800213F0
0x18002147a  mov     edx, 2F0003h; unsigned int
0x18002147f  cmp     r12d, edx
0x180021482  jnz     loc_1800213F0
0x180021488  test    r15d, r15d
0x18002148b  jnz     loc_1800213F0
0x180021491  cmp     [rdi], r15d
0x180021494  jbe     short loc_18002149D
0x180021496  xor     ebx, ebx
0x180021498  jmp     loc_1800213FD
0x18002149d  mov     [rbp+var_38], 0
0x1800214a4  mov     [rsp+78h+lpBytesReturned], rdi; lpNumberOfBytesTransferred
0x1800214a9  mov     [rsp+78h+nOutBufferSize], 4; DWORD
0x1800214b1  lea     rax, [rbp+var_38]
0x1800214b5  mov     [rsp+78h+lpOutBuffer], rax; void *
0x1800214ba  mov     r9d, r13d; unsigned int
0x1800214bd  mov     r8, [rbp+lpInBuffer]; void *
0x1800214c1  mov     rcx, r14; void *
0x1800214c4  call    ?SyncIoctl@@YAJPEAXK0K0KPEAK@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x1800214c9  test    eax, eax
0x1800214cb  js      loc_1800213F0
0x1800214d1  mov     eax, [rbp+var_38]
0x1800214d4  mov     [rdi], eax
0x1800214d6  jmp     short loc_180021496
0x1800214d8  mov     rax, [rbp+Overlapped.Internal]
0x1800214dc  cmp     rax, 102h
0x1800214e2  jz      short loc_180021558
0x1800214e4  cmp     rax, 105h
0x1800214ea  jz      short loc_180021551
0x1800214ec  mov     ecx, 0C00000BBh
0x1800214f1  cmp     rax, rcx
0x1800214f4  jz      short loc_18002152F
0x1800214f6  mov     ecx, 0C00000D0h
0x1800214fb  cmp     rax, rcx
0x1800214fe  jz      short loc_180021523
0x180021500  mov     ecx, 0C0000240h
0x180021505  cmp     rax, rcx
0x180021508  jz      short loc_180021517
0x18002150a  mov     rcx, rsi; hObject
0x18002150d  call    cs:__imp_CloseHandle
0x180021513  xor     eax, eax
0x180021515  jmp     short loc_180021586
0x180021517  mov     ebx, 800704D3h
0x18002151c  mov     edx, 0F6h
0x180021521  jmp     short loc_180021562
0x180021523  mov     ebx, 80070047h
0x180021528  mov     edx, 0EEh
0x18002152d  jmp     short loc_180021562
0x18002152f  mov     rcx, [rbp+40h]; this
0x180021533  mov     r9d, 80070032h; char *
0x180021539  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\lib\\kslib\\kslib.cp"...
0x180021540  mov     edx, 0F2h; void *
0x180021545  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002154a  mov     ebx, 80070032h
0x18002154f  jmp     short loc_180021575
0x180021551  mov     ebx, 800700EAh
0x180021556  jmp     short loc_180021575
0x180021558  mov     ebx, 800705B4h
0x18002155d  mov     edx, 0EAh; void *
0x180021562  mov     r9d, ebx; char *
0x180021565  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\lib\\kslib\\kslib.cp"...
0x18002156c  mov     rcx, [rbp+40h]; this
0x180021570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021575  mov     dword ptr [rdi], 0
0x18002157b  mov     rcx, rsi; hObject
0x18002157e  call    cs:__imp_CloseHandle
0x180021584  mov     eax, ebx
0x180021586  add     rsp, 78h
0x18002158a  pop     r15
0x18002158c  pop     r14
0x18002158e  pop     r13
0x180021590  pop     r12
0x180021592  pop     rdi
0x180021593  pop     rsi
0x180021594  pop     rbx
0x180021595  pop     rbp
0x180021596  retn
```
