# GetCredentialsFromVan

- ea: `0x180084d10`
- end: `0x18008517e`
- name: `GetCredentialsFromVan`
- size: `1134`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParameter@<rcx>, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180087230`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x180084d10`
- `0x180085c1c`
- `0x18008d31c`
- `0x18008d66c`
- `0x18008ec1c`
- `0x18008fc44`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180084e28`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180084f42`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180084e28`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180084f42`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180084e70`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180084f8d`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180084e70`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180084f8d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180084db8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180084eec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180084db8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180084eec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f98`

## pseudocode

```c
__int64 __fastcall GetCredentialsFromVan(char *lpParameter, __int64 a2, __int64 a3, unsigned int a4, unsigned int a5)
{
  unsigned int v8; // esi
  HANDLE Thread; // rax
  DWORD LastError; // eax
  DWORD v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HANDLE *v14; // rbx
  HANDLE v15; // rax
  DWORD v16; // eax
  __int64 v17; // rdx
  int v19; // [rsp+80h] [rbp+18h] BYREF

  v19 = a3;
  v8 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qDdd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, 0, a4, a5);
  }
  v19 = 0;
  UpdateAutoTriggerConnectionStatus(a2, lpParameter, a4, v8);
  Thread = CreateThread(0, 0, WaitAndRedialTriggerConnection, lpParameter, 4u, (LPDWORD)lpParameter + 2642);
  *((_QWORD *)lpParameter + 1333) = Thread;
  if ( Thread )
  {
    if ( !SetThreadToken((PHANDLE)lpParameter + 1333, *((HANDLE *)lpParameter + 1330)) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( !LastError )
        goto LABEL_69;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_70;
      v13 = 677;
      goto LABEL_11;
    }
    if ( ResumeThread(*((HANDLE *)lpParameter + 1333)) == -1 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( !LastError )
        goto LABEL_69;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_70;
      v13 = 678;
      goto LABEL_11;
    }
    v14 = (HANDLE *)(lpParameter + 10672);
    if ( !*((_QWORD *)lpParameter + 1334) )
    {
      v15 = CreateThread(0, 0, WaitForVanCancelEvent, lpParameter, 4u, (LPDWORD)lpParameter + 2643);
      *v14 = v15;
      if ( !v15 )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( !LastError )
          goto LABEL_69;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v11;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_70;
        v13 = 679;
        goto LABEL_11;
      }
      if ( !SetThreadToken((PHANDLE)lpParameter + 1334, *((HANDLE *)lpParameter + 1330)) )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( !LastError )
          goto LABEL_69;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v11;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_70;
        v13 = 680;
        goto LABEL_11;
      }
      if ( ResumeThread(*v14) == -1 )
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( !LastError )
          goto LABEL_69;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v11;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_70;
        v13 = 681;
        goto LABEL_11;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 682, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v8);
    }
    LogRasDialEvent(8, 0, lpParameter);
    LastError = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))g_pRasSignalActionRequired)(
                  a2,
                  a4,
                  0,
                  *((_QWORD *)lpParameter + 1331),
                  *((_QWORD *)lpParameter + 1332),
                  0);
    v11 = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_70;
      v13 = 683;
      goto LABEL_11;
    }
    SignalVanActionRequiredEvent(lpParameter, &v19);
    if ( v19 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        goto LABEL_70;
      v17 = 686;
    }
    else
    {
      if ( *((_DWORD *)lpParameter + 1794) == 2 )
      {
        v16 = ShowToastNotification(lpParameter, v8);
        v11 = v16;
        if ( v16 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 684, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v16);
            v12 = WPP_GLOBAL_Control;
          }
          v11 = 0;
          goto LABEL_70;
        }
        goto LABEL_69;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        goto LABEL_70;
      v17 = 685;
    }
    WPP_SF_(v12[2], v17, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
LABEL_69:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_70;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( !LastError )
    goto LABEL_69;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v11;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 676;
LABEL_11:
    WPP_SF_d(v12[2], v13, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, LastError);
    goto LABEL_69;
  }
LABEL_70:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_d(v12[2], 687, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180084d10  mov     rax, rsp
0x180084d13  mov     [rax+8], rbx
0x180084d17  mov     [rax+10h], rbp
0x180084d1b  mov     [rax+18h], r8d
0x180084d1f  push    rsi
0x180084d20  push    rdi
0x180084d21  push    r12
0x180084d23  push    r13
0x180084d25  push    r14
0x180084d27  sub     rsp, 40h
0x180084d2b  mov     ebp, r9d
0x180084d2e  mov     r14, rdx
0x180084d31  mov     rdi, rcx
0x180084d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180084d3b  lea     r13, WPP_GLOBAL_Control
0x180084d42  mov     esi, [rsp+68h+arg_20]
0x180084d49  mov     r12d, 800h
0x180084d4f  cmp     rcx, r13
0x180084d52  jz      short loc_180084D7A
0x180084d54  test    [rcx+1Ch], r12d
0x180084d58  jz      short loc_180084D7A
0x180084d5a  cmp     byte ptr [rcx+19h], 6
0x180084d5e  jb      short loc_180084D7A
0x180084d60  mov     rcx, [rcx+10h]
0x180084d64  mov     [rax-38h], esi
0x180084d67  mov     [rax-40h], r9d
0x180084d6b  mov     r9, rdx
0x180084d6e  mov     dword ptr [rax-48h], 0
0x180084d75  call    WPP_SF_qDdd
0x180084d7a  mov     r9d, esi
0x180084d7d  mov     [rsp+68h+arg_10], 0
0x180084d88  mov     r8d, ebp
0x180084d8b  mov     rdx, rdi
0x180084d8e  mov     rcx, r14
0x180084d91  call    UpdateAutoTriggerConnectionStatus
0x180084d96  lea     rax, [rdi+2948h]
0x180084d9d  mov     r9, rdi; lpParameter
0x180084da0  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180084da5  lea     r8, WaitAndRedialTriggerConnection; lpStartAddress
0x180084dac  xor     edx, edx; dwStackSize
0x180084dae  mov     [rsp+68h+dwCreationFlags], 4; dwCreationFlags
0x180084db6  xor     ecx, ecx; lpThreadAttributes
0x180084db8  call    cs:__imp_CreateThread
0x180084dbe  lea     rbx, [rdi+29A8h]
0x180084dc5  mov     [rbx], rax
0x180084dc8  test    rax, rax
0x180084dcb  jnz     short loc_180084E1E
0x180084dcd  call    cs:__imp_GetLastError
0x180084dd3  mov     ebx, eax
0x180084dd5  test    eax, eax
0x180084dd7  jz      loc_180085135
0x180084ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x180084de4  cmp     rcx, r13
0x180084de7  jz      loc_180085165
0x180084ded  test    [rcx+1Ch], r12d
0x180084df1  jz      loc_18008513C
0x180084df7  cmp     byte ptr [rcx+19h], 2
0x180084dfb  jb      loc_18008513C
0x180084e01  mov     edx, 2A4h
0x180084e06  mov     rcx, [rcx+10h]
0x180084e0a  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180084e11  mov     r9d, eax
0x180084e14  call    WPP_SF_d
0x180084e19  jmp     loc_180085135
0x180084e1e  mov     rdx, [rdi+2990h]; Token
0x180084e25  mov     rcx, rbx; Thread
0x180084e28  call    cs:__imp_SetThreadToken
0x180084e2e  test    eax, eax
0x180084e30  jnz     short loc_180084E6D
0x180084e32  call    cs:__imp_GetLastError
0x180084e38  mov     ebx, eax
0x180084e3a  test    eax, eax
0x180084e3c  jz      loc_180085135
0x180084e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180084e49  cmp     rcx, r13
0x180084e4c  jz      loc_180085165
0x180084e52  test    [rcx+1Ch], r12d
0x180084e56  jz      loc_18008513C
0x180084e5c  cmp     byte ptr [rcx+19h], 2
0x180084e60  jb      loc_18008513C
0x180084e66  mov     edx, 2A5h
0x180084e6b  jmp     short loc_180084E06
0x180084e6d  mov     rcx, [rbx]; hThread
0x180084e70  call    cs:__imp_ResumeThread
0x180084e76  cmp     eax, 0FFFFFFFFh
0x180084e79  jnz     short loc_180084EB9
0x180084e7b  call    cs:__imp_GetLastError
0x180084e81  mov     ebx, eax
0x180084e83  test    eax, eax
0x180084e85  jz      loc_180085135
0x180084e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180084e92  cmp     rcx, r13
0x180084e95  jz      loc_180085165
0x180084e9b  test    [rcx+1Ch], r12d
0x180084e9f  jz      loc_18008513C
0x180084ea5  cmp     byte ptr [rcx+19h], 2
0x180084ea9  jb      loc_18008513C
0x180084eaf  mov     edx, 2A6h
0x180084eb4  jmp     loc_180084E06
0x180084eb9  lea     rbx, [rdi+29B0h]
0x180084ec0  cmp     qword ptr [rbx], 0
0x180084ec4  jnz     loc_180084FD6
0x180084eca  lea     rax, [rdi+294Ch]
0x180084ed1  mov     r9, rdi; lpParameter
0x180084ed4  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x180084ed9  lea     r8, WaitForVanCancelEvent; lpStartAddress
0x180084ee0  xor     edx, edx; dwStackSize
0x180084ee2  mov     [rsp+68h+dwCreationFlags], 4; dwCreationFlags
0x180084eea  xor     ecx, ecx; lpThreadAttributes
0x180084eec  call    cs:__imp_CreateThread
0x180084ef2  mov     [rbx], rax
0x180084ef5  test    rax, rax
0x180084ef8  jnz     short loc_180084F38
0x180084efa  call    cs:__imp_GetLastError
0x180084f00  mov     ebx, eax
0x180084f02  test    eax, eax
0x180084f04  jz      loc_180085135
0x180084f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180084f11  cmp     rcx, r13
0x180084f14  jz      loc_180085165
0x180084f1a  test    [rcx+1Ch], r12d
0x180084f1e  jz      loc_18008513C
0x180084f24  cmp     byte ptr [rcx+19h], 2
0x180084f28  jb      loc_18008513C
0x180084f2e  mov     edx, 2A7h
0x180084f33  jmp     loc_180084E06
0x180084f38  mov     rdx, [rdi+2990h]; Token
0x180084f3f  mov     rcx, rbx; Thread
0x180084f42  call    cs:__imp_SetThreadToken
0x180084f48  test    eax, eax
0x180084f4a  jnz     short loc_180084F8A
0x180084f4c  call    cs:__imp_GetLastError
0x180084f52  mov     ebx, eax
0x180084f54  test    eax, eax
0x180084f56  jz      loc_180085135
0x180084f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180084f63  cmp     rcx, r13
0x180084f66  jz      loc_180085165
0x180084f6c  test    [rcx+1Ch], r12d
0x180084f70  jz      loc_18008513C
0x180084f76  cmp     byte ptr [rcx+19h], 2
0x180084f7a  jb      loc_18008513C
0x180084f80  mov     edx, 2A8h
0x180084f85  jmp     loc_180084E06
0x180084f8a  mov     rcx, [rbx]; hThread
0x180084f8d  call    cs:__imp_ResumeThread
0x180084f93  cmp     eax, 0FFFFFFFFh
0x180084f96  jnz     short loc_180084FD6
0x180084f98  call    cs:__imp_GetLastError
0x180084f9e  mov     ebx, eax
0x180084fa0  test    eax, eax
0x180084fa2  jz      loc_180085135
0x180084fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180084faf  cmp     rcx, r13
0x180084fb2  jz      loc_180085165
0x180084fb8  test    [rcx+1Ch], r12d
0x180084fbc  jz      loc_18008513C
0x180084fc2  cmp     byte ptr [rcx+19h], 2
0x180084fc6  jb      loc_18008513C
0x180084fcc  mov     edx, 2A9h
0x180084fd1  jmp     loc_180084E06
0x180084fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180084fdd  cmp     rcx, r13
0x180084fe0  jz      short loc_180085006
0x180084fe2  test    [rcx+1Ch], r12d
0x180084fe6  jz      short loc_180085006
0x180084fe8  cmp     byte ptr [rcx+19h], 5
0x180084fec  jb      short loc_180085006
0x180084fee  mov     rcx, [rcx+10h]
0x180084ff2  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180084ff9  mov     edx, 2AAh
0x180084ffe  mov     r9d, esi
0x180085001  call    WPP_SF_d
0x180085006  xor     edx, edx
0x180085008  mov     r8, rdi
0x18008500b  lea     ecx, [rdx+8]
0x18008500e  call    LogRasDialEvent
0x180085013  mov     rcx, [rdi+29A0h]
0x18008501a  xor     r8d, r8d
0x18008501d  mov     r9, [rdi+2998h]
0x180085024  mov     edx, ebp
0x180085026  mov     rax, cs:g_pRasSignalActionRequired
0x18008502d  mov     [rsp+68h+lpThreadId], 0
0x180085036  mov     qword ptr [rsp+68h+dwCreationFlags], rcx
0x18008503b  mov     rcx, r14
0x18008503e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085043  mov     ebx, eax
0x180085045  test    eax, eax
0x180085047  jz      short loc_180085077
0x180085049  mov     rcx, cs:WPP_GLOBAL_Control
0x180085050  cmp     rcx, r13
0x180085053  jz      loc_180085165
0x180085059  test    [rcx+1Ch], r12d
0x18008505d  jz      loc_18008513C
0x180085063  cmp     byte ptr [rcx+19h], 2
0x180085067  jb      loc_18008513C
0x18008506d  mov     edx, 2ABh
0x180085072  jmp     loc_180084E06
0x180085077  lea     rdx, [rsp+68h+arg_10]
0x18008507f  mov     rcx, rdi
0x180085082  call    SignalVanActionRequiredEvent
0x180085087  cmp     [rsp+68h+arg_10], 0
0x18008508f  jnz     short loc_180085108
0x180085091  cmp     dword ptr [rdi+1C08h], 2
0x180085098  jnz     short loc_1800850E9
0x18008509a  mov     edx, esi
0x18008509c  mov     rcx, rdi
0x18008509f  call    ShowToastNotification
0x1800850a4  mov     ebx, eax
0x1800850a6  test    eax, eax
0x1800850a8  jz      loc_180085135
0x1800850ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800850b5  cmp     rcx, r13
0x1800850b8  jz      short loc_1800850E5
0x1800850ba  test    [rcx+1Ch], r12d
0x1800850be  jz      short loc_1800850E5
0x1800850c0  cmp     byte ptr [rcx+19h], 2
0x1800850c4  jb      short loc_1800850E5
0x1800850c6  mov     rcx, [rcx+10h]
0x1800850ca  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x1800850d1  mov     edx, 2ACh
0x1800850d6  mov     r9d, eax
0x1800850d9  call    WPP_SF_d
0x1800850de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800850e5  xor     ebx, ebx
0x1800850e7  jmp     short loc_18008513C
0x1800850e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800850f0  cmp     rcx, r13
0x1800850f3  jz      short loc_180085165
0x1800850f5  test    [rcx+1Ch], r12d
0x1800850f9  jz      short loc_18008513C
0x1800850fb  cmp     byte ptr [rcx+19h], 5
0x1800850ff  jb      short loc_18008513C
0x180085101  mov     edx, 2ADh
0x180085106  jmp     short loc_180085125
0x180085108  mov     rcx, cs:WPP_GLOBAL_Control
0x18008510f  cmp     rcx, r13
0x180085112  jz      short loc_180085165
0x180085114  test    [rcx+1Ch], r12d
0x180085118  jz      short loc_18008513C
0x18008511a  cmp     byte ptr [rcx+19h], 5
0x18008511e  jb      short loc_18008513C
0x180085120  mov     edx, 2AEh
0x180085125  mov     rcx, [rcx+10h]
0x180085129  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180085130  call    WPP_SF_
0x180085135  mov     rcx, cs:WPP_GLOBAL_Control
0x18008513c  cmp     rcx, r13
0x18008513f  jz      short loc_180085165
0x180085141  test    [rcx+1Ch], r12d
0x180085145  jz      short loc_180085165
0x180085147  cmp     byte ptr [rcx+19h], 6
0x18008514b  jb      short loc_180085165
0x18008514d  mov     rcx, [rcx+10h]
0x180085151  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180085158  mov     edx, 2AFh
0x18008515d  mov     r9d, ebx
0x180085160  call    WPP_SF_d
0x180085165  mov     rbp, [rsp+68h+arg_8]
0x18008516a  mov     eax, ebx
0x18008516c  mov     rbx, [rsp+68h+arg_0]
0x180085171  add     rsp, 40h
0x180085175  pop     r14
0x180085177  pop     r13
0x180085179  pop     r12
0x18008517b  pop     rdi
0x18008517c  pop     rsi
0x18008517d  retn
```
