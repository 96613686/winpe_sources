# SockCloseSocket

- ea: `0x180014e38`
- end: `0x18001525e`
- name: `SockCloseSocket`
- size: `1062`
- prototype: ``
- caller_count: `9`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18000a2a0`
- `0x180014c00`
- `0x1800238d0`
- `0x180025530`
- `0x180027140`
- `0x18003d540`
- `0x18003dbe4`
- `0x18004abd0`
- `0x18005284c`

## callees

- `0x180006d00`
- `0x180008250`
- `0x18000f4c8`
- `0x18000f970`
- `0x18000f9f0`
- `0x180014e38`
- `0x18001be40`
- `0x1800222f0`
- `0x180024df4`
- `0x180038118`
- `0x180038a20`
- `0x180038f54`
- `0x18005284c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180014e85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180014e85`
- `ntdll!NtClose` at `0x180015131`
- `ntdll!NtClose` at `0x180015156`
- `ntdll!NtClose` at `0x180015192`
- `ntdll!NtClose` at `0x180015131`
- `ntdll!NtClose` at `0x180015156`
- `ntdll!NtClose` at `0x180015192`
- `ntdll!NtDeviceIoControlFile` at `0x1800150ac`
- `ntdll!NtDeviceIoControlFile` at `0x1800150ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ef7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001503f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800151de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001521b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ef7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014f70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001503f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800151de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001521b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ea3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001502c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800150f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ea3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014f5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001502c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800150f8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015000`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015000`
- `WS2_32!WahRemoveHandleContext` at `0x180015173`
- `WS2_32!WahRemoveHandleContext` at `0x180015173`

## pseudocode

```c
__int64 __fastcall SockCloseSocket(__int64 a1)
{
  HANDLE *Value; // r13
  int v3; // r15d
  unsigned int v4; // r14d
  __int64 v5; // r12
  unsigned int v6; // eax
  int v7; // r14d
  DWORD v8; // r12d
  int v9; // eax
  NTSTATUS Status; // eax
  __int64 v12; // r8
  void *v13; // rcx
  void *v14; // rcx
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  _DWORD *IoControlCode; // [rsp+28h] [rbp-90h]
  PVOID InputBuffer; // [rsp+30h] [rbp-88h]
  _DWORD v21[2]; // [rsp+50h] [rbp-68h] BYREF
  __int64 v22; // [rsp+58h] [rbp-60h]
  __int64 v23; // [rsp+60h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-50h] BYREF
  __int64 v25; // [rsp+78h] [rbp-40h] BYREF
  __int64 v26; // [rsp+80h] [rbp-38h]

  v22 = a1;
  LODWORD(v26) = 0;
  v25 = 0;
  IoStatusBlock = 0;
  Value = (HANDLE *)TlsGetValue(MSAFD_SockTlsSlot);
  v23 = a1 + 224;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
  v3 = *(_DWORD *)(a1 + 24);
  if ( v3 == 4 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 19, WPP_0fa42c8809bf3117963d5a958f6beeb2_Traceguids, *(_QWORD *)(a1 + 8));
    v4 = 10038;
LABEL_13:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
    return v4;
  }
  v5 = *(_QWORD *)(a1 + 200);
  *(_DWORD *)(a1 + 24) = 4;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
  if ( SockSanEnabled )
  {
    if ( (*(_BYTE *)(a1 + 68) & 1) != 0 )
      SockSanRemoveListenSockTracker(a1);
    if ( *(_QWORD *)(a1 + 264) )
    {
      v6 = SockSanCloseSocket(a1);
      v4 = v6;
      if ( v6 )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_qD(1025, 20, WPP_0fa42c8809bf3117963d5a958f6beeb2_Traceguids, *(_QWORD *)(a1 + 8), v6);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
        *(_DWORD *)(a1 + 24) = v3;
        goto LABEL_13;
      }
    }
  }
  if ( (v3 == 3 || v5) && (*(_BYTE *)(a1 + 69) & 2) == 0 && (*(_BYTE *)(a1 + 80) & 1) == 0 && *(_WORD *)(a1 + 48) )
  {
    v7 = 1000 * *(unsigned __int16 *)(a1 + 50);
    v8 = 110;
    v21[0] = 0;
    while ( v7 > 0 )
    {
      InputBuffer = 0;
      IoControlCode = v21;
      if ( (unsigned int)SockGetInformation(a1, 4, 0, 0) )
        break;
      if ( !v21[0] )
        goto LABEL_34;
      if ( (*(_BYTE *)(a1 + 68) & 0x40) != 0 )
        goto LABEL_29;
      Sleep(v8);
      v7 -= v8;
      v9 = 2 * v8;
      if ( (int)(2 * v8) > 1000 )
        v9 = 1000;
      v8 = v7;
      if ( v9 <= v7 )
        v8 = v9;
    }
    v26 = 0;
    LODWORD(v25) = 4;
    Status = NtDeviceIoControlFile(*(HANDLE *)(a1 + 8), Value[2], 0, 0, &IoStatusBlock, 0x1202Bu, &v25, 0x10u, 0, 0);
    if ( Status == 259 )
    {
      SockWaitForSingleObject(Value[2]);
      Status = IoStatusBlock.Status;
    }
    if ( Status == -1073741661 )
    {
LABEL_29:
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
      *(_DWORD *)(a1 + 24) = v3;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
      return 10035;
    }
  }
LABEL_34:
  SockAcquireRwLockShared();
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
  SockNotifyHelperDll(a1, 128, v12);
  *(_QWORD *)(a1 + 160) = 0;
  *(_DWORD *)(a1 + 124) = -1;
  v13 = *(void **)(a1 + 184);
  if ( v13 )
  {
    if ( v13 != (void *)-1LL )
      NtClose(v13);
    *(_QWORD *)(a1 + 184) = 0;
  }
  v14 = *(void **)(a1 + 192);
  if ( v14 )
  {
    if ( v14 != (void *)-1LL )
      NtClose(v14);
    *(_QWORD *)(a1 + 192) = 0;
  }
  v4 = WahRemoveHandleContext(SockContextTable, a1);
  v21[0] = v4;
  if ( v4 )
  {
    SockReleaseRwLockShared();
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
    return 10038;
  }
  else
  {
    v15 = NtClose(*(HANDLE *)(a1 + 8));
    v21[1] = v15;
    if ( v15 < 0 && (xmmword_180063D60 & 2) != 0 )
    {
      LODWORD(IoControlCode) = v15;
      WPP_SF_iqL(v17, v16, v18, *(_QWORD *)(a1 + 8), a1, IoControlCode, InputBuffer);
    }
    SockReleaseRwLockShared();
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 224));
    if ( (*(_BYTE *)(a1 + 68) & 1) != 0 && (*(_BYTE *)(a1 + 69) & 0x10) != 0 )
      _InterlockedDecrement(&SockTLNPIListenerCount);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) == 1 )
      SockDestroySocket(a1);
  }
  return v4;
}

```

## disassembly

```asm
0x180014e38  mov     r11, rsp
0x180014e3b  mov     [r11+10h], rbx
0x180014e3f  mov     [r11+18h], rsi
0x180014e43  push    rdi
0x180014e44  push    r12
0x180014e46  push    r13
0x180014e48  push    r14
0x180014e4a  push    r15
0x180014e4c  sub     rsp, 90h
0x180014e53  mov     rax, cs:__security_cookie
0x180014e5a  xor     rax, rsp
0x180014e5d  mov     [rsp+0B8h+var_30], rax
0x180014e65  mov     rbx, rcx
0x180014e68  mov     [rsp+0B8h+var_60], rcx
0x180014e6d  xor     eax, eax
0x180014e6f  mov     [r11-3Ch], rax
0x180014e73  mov     [r11-40h], rax
0x180014e77  xorps   xmm0, xmm0
0x180014e7a  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x180014e7f  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180014e85  call    cs:__imp_TlsGetValue
0x180014e8c  nop     dword ptr [rax+rax+00h]
0x180014e91  mov     r13, rax
0x180014e94  lea     rsi, [rbx+0E0h]
0x180014e9b  mov     [rsp+0B8h+var_58], rsi
0x180014ea0  mov     rcx, rsi; lpCriticalSection
0x180014ea3  call    cs:__imp_EnterCriticalSection
0x180014eaa  nop     dword ptr [rax+rax+00h]
0x180014eaf  mov     r15d, [rbx+18h]
0x180014eb3  cmp     r15d, 4
0x180014eb7  jnz     short loc_180014EE6
0x180014eb9  test    byte ptr cs:xmmword_180063D60, 2
0x180014ec0  jz      short loc_180014EDB
0x180014ec2  lea     edx, [r15+0Fh]
0x180014ec6  mov     ecx, 401h
0x180014ecb  mov     r9, [rbx+8]
0x180014ecf  lea     r8, WPP_0fa42c8809bf3117963d5a958f6beeb2_Traceguids
0x180014ed6  call    WPP_SF_q
0x180014edb  mov     r14d, 2736h
0x180014ee1  jmp     loc_180014F6D
0x180014ee6  mov     r12, [rbx+0C8h]
0x180014eed  mov     dword ptr [rbx+18h], 4
0x180014ef4  mov     rcx, rsi; lpCriticalSection
0x180014ef7  call    cs:__imp_LeaveCriticalSection
0x180014efe  nop     dword ptr [rax+rax+00h]
0x180014f03  xor     edi, edi
0x180014f05  cmp     cs:SockSanEnabled, edi
0x180014f0b  jz      short loc_180014F81
0x180014f0d  test    byte ptr [rbx+44h], 1
0x180014f11  jz      short loc_180014F1B
0x180014f13  mov     rcx, rbx
0x180014f16  call    SockSanRemoveListenSockTracker
0x180014f1b  cmp     [rbx+108h], rdi
0x180014f22  jz      short loc_180014F81
0x180014f24  mov     rcx, rbx
0x180014f27  call    SockSanCloseSocket
0x180014f2c  mov     r14d, eax
0x180014f2f  test    eax, eax
0x180014f31  jz      short loc_180014F81
0x180014f33  test    byte ptr cs:xmmword_180063D60, 2
0x180014f3a  jz      short loc_180014F5A
0x180014f3c  mov     edx, 14h
0x180014f41  mov     ecx, 401h
0x180014f46  mov     dword ptr [rsp+0B8h+IoStatusBlock], eax
0x180014f4a  mov     r9, [rbx+8]
0x180014f4e  lea     r8, WPP_0fa42c8809bf3117963d5a958f6beeb2_Traceguids
0x180014f55  call    WPP_SF_qD
0x180014f5a  mov     rcx, rsi; lpCriticalSection
0x180014f5d  call    cs:__imp_EnterCriticalSection
0x180014f64  nop     dword ptr [rax+rax+00h]
0x180014f69  mov     [rbx+18h], r15d
0x180014f6d  mov     rcx, rsi; lpCriticalSection
0x180014f70  call    cs:__imp_LeaveCriticalSection
0x180014f77  nop     dword ptr [rax+rax+00h]
0x180014f7c  jmp     loc_18001522D
0x180014f81  cmp     r15d, 3
0x180014f85  jz      short loc_180014F90
0x180014f87  test    r12, r12
0x180014f8a  jz      loc_1800150F0
0x180014f90  test    byte ptr [rbx+45h], 2
0x180014f94  jnz     loc_1800150F0
0x180014f9a  test    byte ptr [rbx+50h], 1
0x180014f9e  jnz     loc_1800150F0
0x180014fa4  cmp     [rbx+30h], di
0x180014fa8  jz      loc_1800150F0
0x180014fae  movzx   eax, word ptr [rbx+32h]
0x180014fb2  imul    r14d, eax, 3E8h
0x180014fb9  mov     r12d, 6Eh ; 'n'
0x180014fbf  mov     [rsp+0B8h+var_68], edi
0x180014fc3  test    r14d, r14d
0x180014fc6  jle     loc_18001505E
0x180014fcc  mov     [rsp+0B8h+InputBuffer], rdi
0x180014fd1  lea     rax, [rsp+0B8h+var_68]
0x180014fd6  mov     qword ptr [rsp+0B8h+IoControlCode], rax
0x180014fdb  xor     r9d, r9d
0x180014fde  xor     r8d, r8d
0x180014fe1  lea     edx, [r9+4]
0x180014fe5  mov     rcx, rbx
0x180014fe8  call    SockGetInformation
0x180014fed  test    eax, eax
0x180014fef  jnz     short loc_18001505E
0x180014ff1  cmp     [rsp+0B8h+var_68], edi
0x180014ff5  jz      short loc_180015055
0x180014ff7  test    byte ptr [rbx+44h], 40h
0x180014ffb  jnz     short loc_180015029
0x180014ffd  mov     ecx, r12d; dwMilliseconds
0x180015000  call    cs:__imp_Sleep
0x180015007  nop     dword ptr [rax+rax+00h]
0x18001500c  sub     r14d, r12d
0x18001500f  lea     eax, [r12+r12]
0x180015013  mov     ecx, 3E8h
0x180015018  cmp     eax, ecx
0x18001501a  cmovg   eax, ecx
0x18001501d  mov     r12d, r14d
0x180015020  cmp     eax, r14d
0x180015023  cmovle  r12d, eax
0x180015027  jmp     short loc_180014FC3
0x180015029  mov     rcx, rsi; lpCriticalSection
0x18001502c  call    cs:__imp_EnterCriticalSection
0x180015033  nop     dword ptr [rax+rax+00h]
0x180015038  mov     [rbx+18h], r15d
0x18001503c  mov     rcx, rsi; lpCriticalSection
0x18001503f  call    cs:__imp_LeaveCriticalSection
0x180015046  nop     dword ptr [rax+rax+00h]
0x18001504b  mov     eax, 2733h
0x180015050  jmp     loc_180015230
0x180015055  test    r14d, r14d
0x180015058  jg      loc_1800150F0
0x18001505e  mov     [rsp+0B8h+var_38], rdi
0x180015066  mov     r14d, 4
0x18001506c  mov     dword ptr [rsp+0B8h+var_40], r14d
0x180015071  mov     [rsp+0B8h+OutputBufferLength], edi; OutputBufferLength
0x180015075  mov     [rsp+0B8h+OutputBuffer], rdi; OutputBuffer
0x18001507a  mov     [rsp+0B8h+InputBufferLength], 10h; InputBufferLength
0x180015082  lea     rax, [rsp+0B8h+var_40]
0x180015087  mov     [rsp+0B8h+InputBuffer], rax; InputBuffer
0x18001508c  mov     [rsp+0B8h+IoControlCode], 1202Bh; IoControlCode
0x180015094  lea     rax, [rsp+0B8h+var_50]
0x180015099  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x18001509e  xor     r9d, r9d; ApcContext
0x1800150a1  xor     r8d, r8d; ApcRoutine
0x1800150a4  mov     rdx, [r13+10h]; Event
0x1800150a8  mov     rcx, [rbx+8]; FileHandle
0x1800150ac  call    cs:__imp_NtDeviceIoControlFile
0x1800150b3  nop     dword ptr [rax+rax+00h]
0x1800150b8  cmp     eax, 103h
0x1800150bd  jnz     short loc_1800150E5
0x1800150bf  movzx   eax, word ptr [rbx+30h]
0x1800150c3  neg     ax
0x1800150c6  sbb     r8d, r8d
0x1800150c9  and     r8d, 0FFFFFFFEh
0x1800150cd  add     r8d, 3
0x1800150d1  mov     r9d, r14d
0x1800150d4  mov     rdx, [rbx+8]
0x1800150d8  mov     rcx, [r13+10h]; Handle
0x1800150dc  call    SockWaitForSingleObject
0x1800150e1  mov     eax, dword ptr [rsp+0B8h+var_50]
0x1800150e5  cmp     eax, 0C00000A3h
0x1800150ea  jz      loc_180015029
0x1800150f0  call    SockAcquireRwLockShared
0x1800150f5  mov     rcx, rsi; lpCriticalSection
0x1800150f8  call    cs:__imp_EnterCriticalSection
0x1800150ff  nop     dword ptr [rax+rax+00h]
0x180015104  mov     edx, 80h
0x180015109  mov     rcx, rbx
0x18001510c  call    SockNotifyHelperDll
0x180015111  mov     [rbx+0A0h], rdi
0x180015118  mov     dword ptr [rbx+7Ch], 0FFFFFFFFh
0x18001511f  mov     rcx, [rbx+0B8h]; Handle
0x180015126  test    rcx, rcx
0x180015129  jz      short loc_180015144
0x18001512b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001512f  jz      short loc_18001513D
0x180015131  call    cs:__imp_NtClose
0x180015138  nop     dword ptr [rax+rax+00h]
0x18001513d  mov     [rbx+0B8h], rdi
0x180015144  mov     rcx, [rbx+0C0h]; Handle
0x18001514b  test    rcx, rcx
0x18001514e  jz      short loc_180015169
0x180015150  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015154  jz      short loc_180015162
0x180015156  call    cs:__imp_NtClose
0x18001515d  nop     dword ptr [rax+rax+00h]
0x180015162  mov     [rbx+0C0h], rdi
0x180015169  mov     rdx, rbx
0x18001516c  mov     rcx, cs:SockContextTable
0x180015173  call    cs:__imp_WahRemoveHandleContext
0x18001517a  nop     dword ptr [rax+rax+00h]
0x18001517f  mov     r14d, eax
0x180015182  mov     [rsp+0B8h+var_68], eax
0x180015186  test    eax, eax
0x180015188  jnz     loc_180015213
0x18001518e  mov     rcx, [rbx+8]; Handle
0x180015192  call    cs:__imp_NtClose
0x180015199  nop     dword ptr [rax+rax+00h]
0x18001519e  mov     [rsp+0B8h+var_64], eax
0x1800151a2  jmp     short loc_1800151B7
0x1800151a4  mov     [rsp+0B8h+var_64], eax
0x1800151a8  mov     r14d, [rsp+0B8h+var_68]
0x1800151ad  mov     rbx, [rsp+0B8h+var_60]
0x1800151b2  mov     rsi, [rsp+0B8h+var_58]
0x1800151b7  test    eax, eax
0x1800151b9  jns     short loc_1800151D6
0x1800151bb  test    byte ptr cs:xmmword_180063D60, 2
0x1800151c2  jz      short loc_1800151D6
0x1800151c4  mov     [rsp+0B8h+IoControlCode], eax
0x1800151c8  mov     [rsp+0B8h+IoStatusBlock], rbx
0x1800151cd  mov     r9, [rbx+8]
0x1800151d1  call    WPP_SF_iqL
0x1800151d6  call    SockReleaseRwLockShared
0x1800151db  mov     rcx, rsi; lpCriticalSection
0x1800151de  call    cs:__imp_LeaveCriticalSection
0x1800151e5  nop     dword ptr [rax+rax+00h]
0x1800151ea  test    byte ptr [rbx+44h], 1
0x1800151ee  jz      short loc_1800151FD
0x1800151f0  test    byte ptr [rbx+45h], 10h
0x1800151f4  jz      short loc_1800151FD
0x1800151f6  lock dec cs:SockTLNPIListenerCount
0x1800151fd  or      eax, 0FFFFFFFFh
0x180015200  lock xadd [rbx], eax
0x180015204  cmp     eax, 1
0x180015207  jnz     short loc_18001522D
0x180015209  mov     rcx, rbx
0x18001520c  call    SockDestroySocket
0x180015211  jmp     short loc_18001522D
0x180015213  call    SockReleaseRwLockShared
0x180015218  mov     rcx, rsi; lpCriticalSection
0x18001521b  call    cs:__imp_LeaveCriticalSection
0x180015222  nop     dword ptr [rax+rax+00h]
0x180015227  mov     r14d, 2736h
0x18001522d  mov     eax, r14d
0x180015230  mov     rcx, [rsp+0B8h+var_30]
0x180015238  xor     rcx, rsp; StackCookie
0x18001523b  call    __security_check_cookie
0x180015240  lea     r11, [rsp+0B8h+var_28]
0x180015248  mov     rbx, [r11+38h]
0x18001524c  mov     rsi, [r11+40h]
0x180015250  mov     rsp, r11
0x180015253  pop     r15
0x180015255  pop     r14
0x180015257  pop     r13
0x180015259  pop     r12
0x18001525b  pop     rdi
0x18001525c  retn
```
