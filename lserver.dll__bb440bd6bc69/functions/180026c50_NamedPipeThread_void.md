# NamedPipeThread(void *)

- ea: `0x180026c50`
- end: `0x180026fdb`
- name: `?NamedPipeThread@@YAIPEAX@Z`
- size: `907`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180005665`
- `0x18001ad48`
- `0x180026be0`
- `0x180026c50`
- `0x1800a0fb0`

## import_xrefs

- `msvcrt!_endthreadex` at `0x180026fa0`
- `msvcrt!_endthreadex` at `0x180026fa0`
- `msvcrt!swprintf_s` at `0x180026ccc`
- `msvcrt!swprintf_s` at `0x180026ccc`
- `KERNEL32!DisconnectNamedPipe` at `0x180026ec6`
- `KERNEL32!DisconnectNamedPipe` at `0x180026ec6`
- `KERNEL32!ReadFile` at `0x180026e8e`
- `KERNEL32!ReadFile` at `0x180026e8e`
- `KERNEL32!GetOverlappedResult` at `0x180026e61`
- `KERNEL32!GetOverlappedResult` at `0x180026e61`
- `KERNEL32!CreateNamedPipeW` at `0x180026d62`
- `KERNEL32!CreateNamedPipeW` at `0x180026d62`
- `KERNEL32!WaitForMultipleObjects` at `0x180026e19`
- `KERNEL32!WaitForMultipleObjects` at `0x180026e19`
- `KERNEL32!CreateEventW` at `0x180026d13`
- `KERNEL32!CreateEventW` at `0x180026d13`
- `KERNEL32!GetLastError` at `0x180026da2`
- `KERNEL32!GetLastError` at `0x180026eaa`
- `KERNEL32!GetLastError` at `0x180026da2`
- `KERNEL32!GetLastError` at `0x180026eaa`
- `KERNEL32!SetEvent` at `0x180026db8`
- `KERNEL32!SetEvent` at `0x180026db8`
- `KERNEL32!SetLastError` at `0x180026eeb`
- `KERNEL32!SetLastError` at `0x180026f52`
- `KERNEL32!SetLastError` at `0x180026eeb`
- `KERNEL32!SetLastError` at `0x180026f52`
- `KERNEL32!CloseHandle` at `0x180026f70`
- `KERNEL32!CloseHandle` at `0x180026f84`
- `KERNEL32!CloseHandle` at `0x180026f70`
- `KERNEL32!CloseHandle` at `0x180026f84`

## pseudocode

```c
__int64 __fastcall NamedPipeThread(void *a1)
{
  __int64 v2; // r14
  HANDLE *v3; // rax
  __int64 v4; // rcx
  int v5; // ebx
  HANDLE *v6; // rdi
  DWORD *v7; // rsi
  HANDLE EventW; // rax
  HANDLE NamedPipeW; // rax
  DWORD LastError; // ebx
  DWORD v11; // eax
  __int64 v12; // rax
  __int64 v13; // rbx
  struct _OVERLAPPED *lpOverlapped; // rdi
  HANDLE *v15; // rdi
  HANDLE *v16; // rsi
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp-C0h] BYREF
  DWORD NumberOfBytesTransferred_4; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD NumberOfBytesTransferred_8[4]; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE v21[4]; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE hFile[6]; // [rsp+88h] [rbp-80h] BYREF
  HANDLE Handles[4]; // [rsp+B8h] [rbp-50h] BYREF
  wchar_t Buffer[264]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v25[528]; // [rsp+2E8h] [rbp+1E0h] BYREF

  NumberOfBytesTransferred = 0;
  NumberOfBytesTransferred_4 = 0;
  memset(Handles, 0, 24);
  memset_0(v21, 0, 0x50u);
  *(_OWORD *)NumberOfBytesTransferred_8 = 0;
  swprintf_s(Buffer, 0x105u, L"\\\\.\\pipe\\%s", L"TermServLicensing");
  v2 = 2;
  v3 = hFile;
  v4 = 2;
  do
  {
    *v3 = (HANDLE)-1LL;
    v3 += 5;
    --v4;
  }
  while ( v4 );
  v5 = 0;
  v6 = hFile;
  v7 = NumberOfBytesTransferred_8;
  while ( v5 < 2 )
  {
    EventW = CreateEventW(0, 1, 1, 0);
    *(_QWORD *)v7 = EventW;
    if ( !EventW
      || (*(v6 - 1) = EventW,
          NamedPipeW = CreateNamedPipeW(Buffer, v5 != 0 ? 1073741825 : 1074266113, 6u, 2u, 0, 0x200u, 0, 0),
          *v6 = NamedPipeW,
          NamedPipeW == (HANDLE)-1LL)
      || !(unsigned int)ConnectToNewClient(NamedPipeW, (struct _OVERLAPPED *)&v21[5 * v5]) )
    {
      LastError = GetLastError();
      goto LABEL_30;
    }
    ++v5;
    v7 += 2;
    v6 += 5;
  }
  SetEvent(a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f8d6e851cc35328591a43dcf77c71880_Traceguids);
  Handles[0] = hHandle;
  *(_OWORD *)&Handles[1] = *(_OWORD *)NumberOfBytesTransferred_8;
  while ( 1 )
  {
    v11 = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
    if ( v11 == -1 )
    {
      LastError = 4096;
      SetLastError(0x1000u);
      goto LABEL_30;
    }
    if ( !v11 )
      break;
    v12 = v11 - 1;
    if ( (unsigned int)v12 > 1 )
    {
      LastError = 4096;
      SetLastError(0x1000u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f8d6e851cc35328591a43dcf77c71880_Traceguids);
      goto LABEL_30;
    }
    v13 = 5 * v12;
    lpOverlapped = (struct _OVERLAPPED *)&v21[5 * v12];
    if ( !GetOverlappedResult(hFile[5 * v12], lpOverlapped, &NumberOfBytesTransferred_4, 1)
      || (!ReadFile(hFile[v13], v25, 0x201u, &NumberOfBytesTransferred, lpOverlapped) || !NumberOfBytesTransferred)
      && GetLastError() != 997 )
    {
      DisconnectNamedPipe(hFile[v13]);
      ConnectToNewClient(hFile[v13], lpOverlapped);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f8d6e851cc35328591a43dcf77c71880_Traceguids);
  LastError = 0;
LABEL_30:
  v15 = (HANDLE *)NumberOfBytesTransferred_8;
  v16 = hFile;
  do
  {
    if ( *v16 != (HANDLE)-1LL )
      CloseHandle(*v16);
    if ( *v15 )
      CloseHandle(*v15);
    v16 += 5;
    ++v15;
    --v2;
  }
  while ( v2 );
  _endthreadex(LastError);
  return LastError;
}

```

## disassembly

```asm
0x180026c50  mov     rax, rsp
0x180026c53  mov     [rax+10h], rbx
0x180026c57  mov     [rax+18h], rsi
0x180026c5b  mov     [rax+20h], rdi
0x180026c5f  push    rbp
0x180026c60  push    r14
0x180026c62  push    r15
0x180026c64  lea     rbp, [rax-418h]
0x180026c6b  sub     rsp, 500h
0x180026c72  mov     rax, cs:__security_cookie
0x180026c79  xor     rax, rsp
0x180026c7c  mov     [rbp+410h+var_20], rax
0x180026c83  and     [rsp+510h+NumberOfBytesTransferred], 0
0x180026c88  xor     eax, eax
0x180026c8a  and     [rsp+510h+NumberOfBytesTransferred+4], 0
0x180026c8f  mov     r15, rcx
0x180026c92  xorps   xmm0, xmm0
0x180026c95  mov     [rbp+410h+var_450], rax
0x180026c99  xor     edx, edx; Val
0x180026c9b  lea     rcx, [rsp+510h+var_4B0]; void *
0x180026ca0  lea     r8d, [rax+50h]; Size
0x180026ca4  movups  xmmword ptr [rbp+410h+Handles], xmm0
0x180026ca8  call    memset_0
0x180026cad  xorps   xmm0, xmm0
0x180026cb0  lea     r9, ServiceName; "TermServLicensing"
0x180026cb7  lea     r8, aPipeS; "\\\\.\\pipe\\%s"
0x180026cbe  mov     edx, 105h; BufferCount
0x180026cc3  lea     rcx, [rbp+410h+Buffer]; Buffer
0x180026cc7  movups  xmmword ptr [rsp+510h+NumberOfBytesTransferred+8], xmm0
0x180026ccc  call    cs:__imp_swprintf_s
0x180026cd3  nop     dword ptr [rax+rax+00h]
0x180026cd8  mov     r14d, 2
0x180026cde  lea     rax, [rbp+410h+hFile]
0x180026ce2  mov     ecx, r14d
0x180026ce5  or      qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x180026ce9  lea     rax, [rax+28h]
0x180026ced  sub     rcx, 1
0x180026cf1  jnz     short loc_180026CE5
0x180026cf3  xor     ebx, ebx
0x180026cf5  lea     rdi, [rbp+410h+hFile]
0x180026cf9  lea     rsi, [rsp+510h+NumberOfBytesTransferred+8]
0x180026cfe  cmp     ebx, r14d
0x180026d01  jge     loc_180026DB5
0x180026d07  xor     r9d, r9d; lpName
0x180026d0a  xor     ecx, ecx; lpEventAttributes
0x180026d0c  lea     edx, [r9+1]; bManualReset
0x180026d10  mov     r8d, edx; bInitialState
0x180026d13  call    cs:__imp_CreateEventW
0x180026d1a  nop     dword ptr [rax+rax+00h]
0x180026d1f  mov     [rsi], rax
0x180026d22  test    rax, rax
0x180026d25  jz      short loc_180026DA2
0x180026d27  mov     [rdi-8], rax
0x180026d2b  lea     rcx, [rbp+410h+Buffer]; lpName
0x180026d2f  mov     eax, ebx
0x180026d31  mov     r9d, r14d; nMaxInstances
0x180026d34  neg     eax
0x180026d36  mov     r8d, 6; dwPipeMode
0x180026d3c  sbb     edx, edx
0x180026d3e  and     qword ptr [rsp+510h+var_4D8], 0
0x180026d44  and     dword ptr [rsp+510h+var_4E0], 0
0x180026d49  and     edx, 0FFF80000h
0x180026d4f  add     edx, 40080001h; dwOpenMode
0x180026d55  mov     [rsp+510h+nInBufferSize], 200h; nInBufferSize
0x180026d5d  and     dword ptr [rsp+510h+lpOverlapped], 0
0x180026d62  call    cs:__imp_CreateNamedPipeW
0x180026d69  nop     dword ptr [rax+rax+00h]
0x180026d6e  mov     [rdi], rax
0x180026d71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026d75  jz      short loc_180026DA2
0x180026d77  movsxd  rcx, ebx
0x180026d7a  lea     rdx, [rcx+rcx*4]
0x180026d7e  lea     rcx, [rsp+510h+var_4B0]
0x180026d83  lea     rdx, [rcx+rdx*8]; struct _OVERLAPPED *
0x180026d87  mov     rcx, rax; void *
0x180026d8a  call    ?ConnectToNewClient@@YAHPEAXPEAU_OVERLAPPED@@@Z; ConnectToNewClient(void *,_OVERLAPPED *)
0x180026d8f  test    eax, eax
0x180026d91  jz      short loc_180026DA2
0x180026d93  inc     ebx
0x180026d95  add     rsi, 8
0x180026d99  add     rdi, 28h ; '('
0x180026d9d  jmp     loc_180026CFE
0x180026da2  call    cs:__imp_GetLastError
0x180026da9  nop     dword ptr [rax+rax+00h]
0x180026dae  mov     ebx, eax
0x180026db0  jmp     loc_180026F5E
0x180026db5  mov     rcx, r15; hEvent
0x180026db8  call    cs:__imp_SetEvent
0x180026dbf  nop     dword ptr [rax+rax+00h]
0x180026dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dcb  lea     r15, WPP_GLOBAL_Control
0x180026dd2  mov     sil, 40h ; '@'
0x180026dd5  cmp     rcx, r15
0x180026dd8  jz      short loc_180026DF5
0x180026dda  test    [rcx+1Ch], sil
0x180026dde  jz      short loc_180026DF5
0x180026de0  mov     rcx, [rcx+10h]
0x180026de4  lea     r8, WPP_f8d6e851cc35328591a43dcf77c71880_Traceguids
0x180026deb  mov     edx, 0Ah
0x180026df0  call    WPP_SF_
0x180026df5  movups  xmm0, xmmword ptr [rsp+510h+NumberOfBytesTransferred+8]
0x180026dfa  mov     rax, cs:hHandle
0x180026e01  mov     [rbp+410h+Handles], rax
0x180026e05  movdqu  xmmword ptr [rbp+410h+Handles+8], xmm0
0x180026e0a  xor     r8d, r8d; bWaitAll
0x180026e0d  lea     rdx, [rbp+410h+Handles]; lpHandles
0x180026e11  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180026e15  lea     ecx, [r8+3]; nCount
0x180026e19  call    cs:__imp_WaitForMultipleObjects
0x180026e20  nop     dword ptr [rax+rax+00h]
0x180026e25  cmp     eax, 0FFFFFFFFh
0x180026e28  jz      loc_180026F4B
0x180026e2e  test    eax, eax
0x180026e30  jz      loc_180026F20
0x180026e36  dec     eax
0x180026e38  cmp     eax, 1
0x180026e3b  ja      loc_180026EE4
0x180026e41  lea     rbx, [rax+rax*4]
0x180026e45  mov     r9d, 1; bWait
0x180026e4b  mov     rcx, [rbp+rbx*8+410h+hFile]; hFile
0x180026e50  lea     rdi, [rsp+510h+var_4B0]
0x180026e55  lea     rdi, [rdi+rbx*8]
0x180026e59  mov     rdx, rdi; lpOverlapped
0x180026e5c  lea     r8, [rsp+510h+NumberOfBytesTransferred+4]; lpNumberOfBytesTransferred
0x180026e61  call    cs:__imp_GetOverlappedResult
0x180026e68  nop     dword ptr [rax+rax+00h]
0x180026e6d  cmp     eax, 1
0x180026e70  jnz     short loc_180026EC1
0x180026e72  mov     rcx, [rbp+rbx*8+410h+hFile]; hFile
0x180026e77  lea     r9, [rsp+510h+NumberOfBytesTransferred]; lpNumberOfBytesRead
0x180026e7c  mov     r8d, 201h; nNumberOfBytesToRead
0x180026e82  mov     [rsp+510h+lpOverlapped], rdi; lpOverlapped
0x180026e87  lea     rdx, [rbp+410h+var_230]; lpBuffer
0x180026e8e  call    cs:__imp_ReadFile
0x180026e95  nop     dword ptr [rax+rax+00h]
0x180026e9a  cmp     eax, 1
0x180026e9d  jnz     short loc_180026EAA
0x180026e9f  cmp     [rsp+510h+NumberOfBytesTransferred], 0
0x180026ea4  jnz     loc_180026E0A
0x180026eaa  call    cs:__imp_GetLastError
0x180026eb1  nop     dword ptr [rax+rax+00h]
0x180026eb6  cmp     eax, 3E5h
0x180026ebb  jz      loc_180026E0A
0x180026ec1  mov     rcx, [rbp+rbx*8+410h+hFile]; hNamedPipe
0x180026ec6  call    cs:__imp_DisconnectNamedPipe
0x180026ecd  nop     dword ptr [rax+rax+00h]
0x180026ed2  mov     rcx, [rbp+rbx*8+410h+hFile]; void *
0x180026ed7  mov     rdx, rdi; struct _OVERLAPPED *
0x180026eda  call    ?ConnectToNewClient@@YAHPEAXPEAU_OVERLAPPED@@@Z; ConnectToNewClient(void *,_OVERLAPPED *)
0x180026edf  jmp     loc_180026E0A
0x180026ee4  mov     ecx, 1000h; dwErrCode
0x180026ee9  mov     ebx, ecx
0x180026eeb  call    cs:__imp_SetLastError
0x180026ef2  nop     dword ptr [rax+rax+00h]
0x180026ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x180026efe  cmp     rcx, r15
0x180026f01  jz      short loc_180026F5E
0x180026f03  test    [rcx+1Ch], sil
0x180026f07  jz      short loc_180026F5E
0x180026f09  mov     rcx, [rcx+10h]
0x180026f0d  lea     r8, WPP_f8d6e851cc35328591a43dcf77c71880_Traceguids
0x180026f14  mov     edx, 0Ch
0x180026f19  call    WPP_SF_
0x180026f1e  jmp     short loc_180026F5E
0x180026f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f27  cmp     rcx, r15
0x180026f2a  jz      short loc_180026F47
0x180026f2c  test    [rcx+1Ch], sil
0x180026f30  jz      short loc_180026F47
0x180026f32  mov     rcx, [rcx+10h]
0x180026f36  lea     r8, WPP_f8d6e851cc35328591a43dcf77c71880_Traceguids
0x180026f3d  mov     edx, 0Bh
0x180026f42  call    WPP_SF_
0x180026f47  xor     ebx, ebx
0x180026f49  jmp     short loc_180026F5E
0x180026f4b  mov     ecx, 1000h; dwErrCode
0x180026f50  mov     ebx, ecx
0x180026f52  call    cs:__imp_SetLastError
0x180026f59  nop     dword ptr [rax+rax+00h]
0x180026f5e  lea     rdi, [rsp+510h+NumberOfBytesTransferred+8]
0x180026f63  lea     rsi, [rbp+410h+hFile]
0x180026f67  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180026f6b  jz      short loc_180026F7C
0x180026f6d  mov     rcx, [rsi]; hObject
0x180026f70  call    cs:__imp_CloseHandle
0x180026f77  nop     dword ptr [rax+rax+00h]
0x180026f7c  mov     rcx, [rdi]; hObject
0x180026f7f  test    rcx, rcx
0x180026f82  jz      short loc_180026F90
0x180026f84  call    cs:__imp_CloseHandle
0x180026f8b  nop     dword ptr [rax+rax+00h]
0x180026f90  add     rsi, 28h ; '('
0x180026f94  add     rdi, 8
0x180026f98  sub     r14, 1
0x180026f9c  jnz     short loc_180026F67
0x180026f9e  mov     ecx, ebx; ReturnCode
0x180026fa0  call    cs:__imp__endthreadex
0x180026fa7  nop     dword ptr [rax+rax+00h]
0x180026fac  mov     eax, ebx
0x180026fae  mov     rcx, [rbp+410h+var_20]
0x180026fb5  xor     rcx, rsp; StackCookie
0x180026fb8  call    __security_check_cookie
0x180026fbd  lea     r11, [rsp+510h+var_10]
0x180026fc5  mov     rbx, [r11+28h]
0x180026fc9  mov     rsi, [r11+30h]
0x180026fcd  mov     rdi, [r11+38h]
0x180026fd1  mov     rsp, r11
0x180026fd4  pop     r15
0x180026fd6  pop     r14
0x180026fd8  pop     rbp
0x180026fd9  retn
```
