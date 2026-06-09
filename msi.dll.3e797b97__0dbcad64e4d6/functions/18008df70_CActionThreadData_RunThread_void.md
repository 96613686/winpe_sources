# CActionThreadData::RunThread(void)

- ea: `0x18008df70`
- end: `0x18008e1fd`
- name: `?RunThread@CActionThreadData@@QEAA?AW4iesEnum@@XZ`
- size: `653`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18008d67c`
- `0x1800a7b14`
- `0x1801ce694`
- `0x1801ce7e4`

## callees

- `0x1800200a4`
- `0x1800202e4`
- `0x18008df70`
- `0x18009ca0c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008e0e6`
- `KERNEL32!CloseHandle` at `0x18008e0e6`
- `KERNEL32!GetExitCodeThread` at `0x18008e0d6`
- `KERNEL32!GetExitCodeThread` at `0x18008e0d6`
- `KERNEL32!GetCurrentThreadId` at `0x18008df9d`
- `KERNEL32!GetCurrentThreadId` at `0x18008df9d`
- `KERNEL32!WaitForSingleObject` at `0x18008e013`
- `KERNEL32!WaitForSingleObject` at `0x18008e013`
- `KERNEL32!CreateThread` at `0x18008dfd4`
- `KERNEL32!CreateThread` at `0x18008dfd4`
- `USER32!MsgWaitForMultipleObjects` at `0x18008e0b8`
- `USER32!MsgWaitForMultipleObjects` at `0x18008e0b8`
- `USER32!PeekMessageW` at `0x18008e096`
- `USER32!PeekMessageW` at `0x18008e096`
- `USER32!TranslateMessage` at `0x18008e069`
- `USER32!TranslateMessage` at `0x18008e069`
- `USER32!DispatchMessageW` at `0x18008e079`
- `USER32!DispatchMessageW` at `0x18008e079`

## pseudocode

```c
__int64 __fastcall CActionThreadData::RunThread(__int64 a1)
{
  int v1; // esi
  int v3; // edi
  HANDLE Thread; // rax
  DWORD v5; // ecx
  DWORD v6; // ebx
  MsiUIMessageContext *v7; // rcx
  __int64 result; // rax
  DWORD v9; // ecx
  DWORD v10; // ecx
  DWORD v11; // ecx
  DWORD v12; // ecx
  DWORD v13; // ecx
  DWORD v14; // ecx
  MSG Msg; // [rsp+30h] [rbp-30h] BYREF
  DWORD ExitCode; // [rsp+80h] [rbp+20h] BYREF
  HANDLE hHandle; // [rsp+88h] [rbp+28h] BYREF

  v1 = *(_DWORD *)(a1 + 8);
  if ( (v1 & 0x80u) == 0 )
  {
    v3 = 0;
    if ( GetCurrentThreadId() == (_DWORD)qword_180313658 )
      *(_BYTE *)(a1 + 124) = 1;
  }
  else
  {
    v3 = 1;
  }
  Thread = CreateThread(0, 0xA000u, *(LPTHREAD_START_ROUTINE *)(a1 + 112), (LPVOID)a1, 0, (LPDWORD)(a1 + 36));
  *(_QWORD *)(a1 + 16) = Thread;
  hHandle = Thread;
  if ( !Thread )
    return 3;
  v5 = 0;
  ExitCode = 0;
  if ( !v3 )
  {
    if ( GetTestFlag(84) )
    {
      do
      {
        v6 = WaitForSingleObject(hHandle, 0x14u);
        MsiUIMessageContext::Invoke(&g_MessageContext, 167772160, &off_18030FDB0);
      }
      while ( v6 == 258 );
    }
    else
    {
      ++HIDWORD(qword_1803136AC);
      while ( MsgWaitForMultipleObjects(1u, &hHandle, 0, 0xFFFFFFFF, 0x1CFFu) == 1 )
      {
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      MsiUIMessageContext::EnableTimeout(v7);
    }
    GetExitCodeThread(hHandle, &ExitCode);
    CloseHandle(hHandle);
    v5 = ExitCode;
  }
  if ( (v1 & 0x20000) != 0 )
    return v5;
  if ( v5 <= 0x643 )
  {
    if ( v5 != 1603 )
    {
      if ( !v5 )
        return 2 * (v3 ^ 1u) - 1;
      result = 7;
      v9 = v5 - 7;
      if ( v9 )
      {
        v10 = v9 - 227;
        if ( v10 && (v11 = v10 - 25) != 0 )
        {
          v12 = v11 - 895;
          if ( v12 && (v13 = v12 - 3) != 0 )
          {
            v14 = v13 - 444;
            if ( v14 )
            {
              if ( v14 == 1 )
                return 2;
              else
                return 3;
            }
            else
            {
              return 4294967290LL;
            }
          }
          else
          {
            return 4294967291LL;
          }
        }
        else
        {
          return 5;
        }
      }
      return result;
    }
    return 3;
  }
  switch ( v5 )
  {
    case 0x644u:
      return 4;
    case 0x649u:
      return 6;
    case 0x65Au:
      return 0;
    case 0x65Fu:
      return 4294967293LL;
    case 0xBC2u:
      return 4294967292LL;
    case 0xFFFFFFFE:
      return 4294967294LL;
  }
  result = 0xFFFFFFFFLL;
  if ( v5 != -1 )
    return 3;
  return result;
}

```

## disassembly

```asm
0x18008df70  mov     [rsp-18h+arg_10], rbx
0x18008df75  mov     [rsp-18h+arg_18], rsi
0x18008df7a  push    rbp
0x18008df7b  push    rdi
0x18008df7c  push    r14
0x18008df7e  mov     rbp, rsp
0x18008df81  sub     rsp, 60h
0x18008df85  mov     esi, [rcx+8]
0x18008df88  mov     rbx, rcx
0x18008df8b  mov     r14d, 1
0x18008df91  test    sil, sil
0x18008df94  jns     short loc_18008DF9B
0x18008df96  mov     edi, r14d
0x18008df99  jmp     short loc_18008DFB5
0x18008df9b  xor     edi, edi
0x18008df9d  call    cs:__imp_GetCurrentThreadId
0x18008dfa4  nop     dword ptr [rax+rax+00h]
0x18008dfa9  cmp     eax, dword ptr cs:qword_180313658
0x18008dfaf  jnz     short loc_18008DFB5
0x18008dfb1  mov     [rbx+7Ch], r14b
0x18008dfb5  mov     r8, [rbx+70h]; lpStartAddress
0x18008dfb9  lea     rax, [rbx+24h]
0x18008dfbd  mov     [rsp+60h+lpThreadId], rax; lpThreadId
0x18008dfc2  mov     r9, rbx; lpParameter
0x18008dfc5  mov     edx, 0A000h; dwStackSize
0x18008dfca  mov     [rsp+60h+dwCreationFlags], 0; dwCreationFlags
0x18008dfd2  xor     ecx, ecx; lpThreadAttributes
0x18008dfd4  call    cs:__imp_CreateThread
0x18008dfdb  nop     dword ptr [rax+rax+00h]
0x18008dfe0  mov     [rbx+10h], rax
0x18008dfe4  mov     [rbp+hHandle], rax
0x18008dfe8  test    rax, rax
0x18008dfeb  jz      loc_18008E1E2
0x18008dff1  xor     ecx, ecx
0x18008dff3  mov     [rbp+ExitCode], ecx
0x18008dff6  test    edi, edi
0x18008dff8  jnz     loc_18008E0F5
0x18008dffe  lea     ecx, [rdi+54h]; int
0x18008e001  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x18008e006  test    al, al
0x18008e008  jz      short loc_18008E046
0x18008e00a  mov     rcx, [rbp+hHandle]; hHandle
0x18008e00e  mov     edx, 14h; dwMilliseconds
0x18008e013  call    cs:__imp_WaitForSingleObject
0x18008e01a  nop     dword ptr [rax+rax+00h]
0x18008e01f  lea     r8, off_18030FDB0
0x18008e026  mov     edx, 0A000000h
0x18008e02b  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x18008e032  mov     ebx, eax
0x18008e034  call    ?Invoke@MsiUIMessageContext@@QEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::Invoke(imtEnum,IMsiRecord *)
0x18008e039  cmp     ebx, 102h
0x18008e03f  jz      short loc_18008E00A
0x18008e041  jmp     loc_18008E0CE
0x18008e046  add     dword ptr cs:qword_1803136AC+4, r14d
0x18008e04d  mov     ebx, 1CFFh
0x18008e052  jmp     short loc_18008E0A6
0x18008e054  xorps   xmm0, xmm0
0x18008e057  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18008e05b  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18008e05f  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18008e063  jmp     short loc_18008E085
0x18008e065  lea     rcx, [rbp+Msg]; lpMsg
0x18008e069  call    cs:__imp_TranslateMessage
0x18008e070  nop     dword ptr [rax+rax+00h]
0x18008e075  lea     rcx, [rbp+Msg]; lpMsg
0x18008e079  call    cs:__imp_DispatchMessageW
0x18008e080  nop     dword ptr [rax+rax+00h]
0x18008e085  xor     r9d, r9d; wMsgFilterMax
0x18008e088  mov     [rsp+60h+dwCreationFlags], r14d; wRemoveMsg
0x18008e08d  xor     r8d, r8d; wMsgFilterMin
0x18008e090  lea     rcx, [rbp+Msg]; lpMsg
0x18008e094  xor     edx, edx; hWnd
0x18008e096  call    cs:__imp_PeekMessageW
0x18008e09d  nop     dword ptr [rax+rax+00h]
0x18008e0a2  test    eax, eax
0x18008e0a4  jnz     short loc_18008E065
0x18008e0a6  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18008e0aa  mov     [rsp+60h+dwCreationFlags], ebx; dwWakeMask
0x18008e0ae  xor     r8d, r8d; fWaitAll
0x18008e0b1  lea     rdx, [rbp+hHandle]; pHandles
0x18008e0b5  mov     ecx, r14d; nCount
0x18008e0b8  call    cs:__imp_MsgWaitForMultipleObjects
0x18008e0bf  nop     dword ptr [rax+rax+00h]
0x18008e0c4  cmp     eax, r14d
0x18008e0c7  jz      short loc_18008E054
0x18008e0c9  call    ?EnableTimeout@MsiUIMessageContext@@QEAAXXZ; MsiUIMessageContext::EnableTimeout(void)
0x18008e0ce  mov     rcx, [rbp+hHandle]; hThread
0x18008e0d2  lea     rdx, [rbp+ExitCode]; lpExitCode
0x18008e0d6  call    cs:__imp_GetExitCodeThread
0x18008e0dd  nop     dword ptr [rax+rax+00h]
0x18008e0e2  mov     rcx, [rbp+hHandle]; hObject
0x18008e0e6  call    cs:__imp_CloseHandle
0x18008e0ed  nop     dword ptr [rax+rax+00h]
0x18008e0f2  mov     ecx, [rbp+ExitCode]
0x18008e0f5  bt      esi, 11h
0x18008e0f9  jnb     short loc_18008E102
0x18008e0fb  mov     eax, ecx
0x18008e0fd  jmp     loc_18008E1E7
0x18008e102  mov     eax, 643h
0x18008e107  cmp     ecx, eax
0x18008e109  ja      short loc_18008E180
0x18008e10b  jz      loc_18008E1E2
0x18008e111  test    ecx, ecx
0x18008e113  jz      short loc_18008E174
0x18008e115  mov     eax, 7
0x18008e11a  sub     ecx, eax
0x18008e11c  jz      loc_18008E1E7
0x18008e122  sub     ecx, 0E3h
0x18008e128  jz      short loc_18008E16D
0x18008e12a  sub     ecx, 19h
0x18008e12d  jz      short loc_18008E16D
0x18008e12f  sub     ecx, 37Fh
0x18008e135  jz      short loc_18008E166
0x18008e137  lea     edx, [rax-4]
0x18008e13a  sub     ecx, edx
0x18008e13c  jz      short loc_18008E166
0x18008e13e  sub     ecx, 1BCh
0x18008e144  jz      short loc_18008E15C
0x18008e146  cmp     ecx, r14d
0x18008e149  jz      short loc_18008E152
0x18008e14b  mov     eax, edx
0x18008e14d  jmp     loc_18008E1E7
0x18008e152  mov     eax, 2
0x18008e157  jmp     loc_18008E1E7
0x18008e15c  mov     eax, 0FFFFFFFAh
0x18008e161  jmp     loc_18008E1E7
0x18008e166  mov     eax, 0FFFFFFFBh
0x18008e16b  jmp     short loc_18008E1E7
0x18008e16d  mov     eax, 5
0x18008e172  jmp     short loc_18008E1E7
0x18008e174  xor     edi, r14d
0x18008e177  lea     eax, ds:0FFFFFFFFFFFFFFFFh[rdi*2]
0x18008e17e  jmp     short loc_18008E1E7
0x18008e180  cmp     ecx, 644h
0x18008e186  jz      short loc_18008E1DB
0x18008e188  cmp     ecx, 649h
0x18008e18e  jz      short loc_18008E1D4
0x18008e190  cmp     ecx, 65Ah
0x18008e196  jz      short loc_18008E1D0
0x18008e198  cmp     ecx, 65Fh
0x18008e19e  jz      short loc_18008E1C9
0x18008e1a0  cmp     ecx, 0BC2h
0x18008e1a6  jz      short loc_18008E1C2
0x18008e1a8  cmp     ecx, 0FFFFFFFEh
0x18008e1ab  jz      short loc_18008E1BB
0x18008e1ad  or      eax, 0FFFFFFFFh
0x18008e1b0  cmp     ecx, 0FFFFFFFFh
0x18008e1b3  lea     edx, [rax+4]
0x18008e1b6  cmovnz  eax, edx
0x18008e1b9  jmp     short loc_18008E1E7
0x18008e1bb  mov     eax, 0FFFFFFFEh
0x18008e1c0  jmp     short loc_18008E1E7
0x18008e1c2  mov     eax, 0FFFFFFFCh
0x18008e1c7  jmp     short loc_18008E1E7
0x18008e1c9  mov     eax, 0FFFFFFFDh
0x18008e1ce  jmp     short loc_18008E1E7
0x18008e1d0  xor     eax, eax
0x18008e1d2  jmp     short loc_18008E1E7
0x18008e1d4  mov     eax, 6
0x18008e1d9  jmp     short loc_18008E1E7
0x18008e1db  mov     eax, 4
0x18008e1e0  jmp     short loc_18008E1E7
0x18008e1e2  mov     eax, 3
0x18008e1e7  lea     r11, [rsp+60h+var_s0]
0x18008e1ec  mov     rbx, [r11+30h]
0x18008e1f0  mov     rsi, [r11+38h]
0x18008e1f4  mov     rsp, r11
0x18008e1f7  pop     r14
0x18008e1f9  pop     rdi
0x18008e1fa  pop     rbp
0x18008e1fb  retn
```
