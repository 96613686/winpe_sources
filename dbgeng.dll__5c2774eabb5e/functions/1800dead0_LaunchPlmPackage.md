# LaunchPlmPackage

- ea: `0x1800dead0`
- end: `0x1800ded49`
- name: `LaunchPlmPackage`
- size: `633`
- prototype: `__int64 __usercall@<rax>(DWORD dwMilliseconds@<ecx>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180428fc8`
- `0x18042af60`

## callees

- `0x18007daa4`
- `0x1800b94c4`
- `0x1800dead0`
- `0x1800ded50`
- `0x1800f1750`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800dec74`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800dec74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800debf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800decd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800debf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800decd2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800decb1`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800decb1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800debe0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800debe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dec2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800decff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dec2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800decff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LaunchPlmPackage(__int64 dwMilliseconds, void *a2, __int64 a3, __int64 a4, __int64 a5)
{
  DWORD v8; // r15d
  _QWORD *v9; // rbx
  HANDLE Thread; // rax
  void *v11; // rbx
  signed int v12; // eax
  signed int v13; // edi
  DWORD v14; // esi
  char v15; // r14
  DWORD v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  signed int LastError; // eax
  HANDLE Handles[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+40h] BYREF
  _QWORD *v25; // [rsp+98h] [rbp+48h] BYREF

  v8 = dwMilliseconds;
  if ( ((_DWORD)dwMilliseconds != 0) != (a2 != 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(dwMilliseconds, a2, a3, a4);
  v9 = operator new(0x48u);
  memset(v9, 0, 0x48u);
  *v9 = 0;
  v9[1] = 0;
  *((_WORD *)v9 + 8) = 256;
  *((_DWORD *)v9 + 5) = 64;
  v9[3] = 0;
  v9[4] = 0;
  *((_WORD *)v9 + 20) = 256;
  *((_DWORD *)v9 + 11) = 64;
  v9[6] = 0;
  v9[7] = 0;
  *((_WORD *)v9 + 32) = 256;
  *((_DWORD *)v9 + 17) = 64;
  v25 = v9;
  if ( DbsDynamicString<unsigned short>::CopyStr(v9, a3, 0xFFFFFFFFLL)
    && DbsDynamicString<unsigned short>::CopyStr(v9 + 3, a4, 0xFFFFFFFFLL)
    && (!a5 || DbsDynamicString<unsigned short>::CopyStr(v9 + 6, a5, 0xFFFFFFFFLL)) )
  {
    Thread = CreateThread(0, 0, LaunchPlmPackageThreadProc, v9, 0, 0);
    v11 = Thread;
    if ( Thread )
    {
      v25 = 0;
      if ( v8 )
      {
        Handles[0] = a2;
        Handles[1] = Thread;
        v14 = 2;
        v15 = 1;
LABEL_16:
        v13 = 0;
        while ( v15 )
        {
          v15 = 0;
          v16 = WaitForMultipleObjectsEx(v14, Handles, 0, v8, 0);
          switch ( v16 )
          {
            case 0u:
              goto LABEL_16;
            case 1u:
              if ( v14 != 2 )
                MicrosoftTelemetryAssertTriggeredNoArgs(v18, v17, v19, v20);
              ExitCode = 0;
              if ( GetExitCodeThread(v11, &ExitCode) )
              {
                v13 = ExitCode;
                if ( (ExitCode & 0x80000000) != 0 )
                  goto LABEL_30;
                v14 = 1;
                v15 = 1;
              }
              else
              {
                LastError = GetLastError();
                v13 = LastError;
                if ( LastError > 0 )
                  v13 = (unsigned __int16)LastError | 0x80070000;
              }
              break;
            case 0x102u:
              v13 = -2147024638;
              break;
            default:
              v13 = -2147467259;
              break;
          }
        }
        if ( v13 >= 1 )
          v13 = -2147467259;
LABEL_30:
        if ( v11 != (void *)-1LL )
          CloseHandle(v11);
      }
      else
      {
        if ( Thread != (HANDLE)-1LL )
          CloseHandle(Thread);
        v13 = 0;
      }
    }
    else
    {
      v12 = GetLastError();
      v13 = v12;
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
    }
    DbsDeletePtr<LaunchPackageThreadData>::~DbsDeletePtr<LaunchPackageThreadData>(&v25);
    return (unsigned int)v13;
  }
  else
  {
    DbsDeletePtr<LaunchPackageThreadData>::~DbsDeletePtr<LaunchPackageThreadData>(&v25);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800dead0  mov     rax, rsp
0x1800dead3  push    rbp
0x1800dead4  push    rsi
0x1800dead5  push    rdi
0x1800dead6  push    r12
0x1800dead8  push    r13
0x1800deada  push    r14
0x1800deadc  push    r15
0x1800deade  mov     rbp, rsp
0x1800deae1  sub     rsp, 50h
0x1800deae5  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1800deaed  mov     [rax+18h], rbx
0x1800deaf1  mov     r12, r9
0x1800deaf4  mov     r13, r8
0x1800deaf7  mov     r14, rdx
0x1800deafa  mov     r15d, ecx
0x1800deafd  xor     esi, esi
0x1800deaff  mov     r10d, esi
0x1800deb02  test    ecx, ecx
0x1800deb04  setnz   r10b
0x1800deb08  mov     eax, esi
0x1800deb0a  test    rdx, rdx
0x1800deb0d  setnz   al
0x1800deb10  cmp     r10d, eax
0x1800deb13  jz      short loc_1800DEB1A
0x1800deb15  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800deb1a  mov     edi, 48h ; 'H'
0x1800deb1f  mov     ecx, edi; Size
0x1800deb21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800deb26  mov     rbx, rax
0x1800deb29  mov     [rbp+arg_8], rax
0x1800deb2d  mov     r8d, edi; Size
0x1800deb30  xor     edx, edx; Val
0x1800deb32  mov     rcx, rax; void *
0x1800deb35  call    memset
0x1800deb3a  mov     [rbx], rsi
0x1800deb3d  mov     [rbx+8], rsi
0x1800deb41  mov     word ptr [rbx+10h], 100h
0x1800deb47  lea     eax, [rdi-8]
0x1800deb4a  mov     [rbx+14h], eax
0x1800deb4d  mov     [rbx+18h], rsi
0x1800deb51  mov     [rbx+20h], rsi
0x1800deb55  mov     word ptr [rbx+28h], 100h
0x1800deb5b  mov     [rbx+2Ch], eax
0x1800deb5e  xor     ecx, ecx
0x1800deb60  mov     [rbx+30h], rcx
0x1800deb64  mov     [rbx+38h], rcx
0x1800deb68  mov     word ptr [rbx+40h], 100h
0x1800deb6e  mov     [rbx+44h], eax
0x1800deb71  mov     [rbp+arg_8], rbx
0x1800deb75  or      r8d, 0FFFFFFFFh
0x1800deb79  mov     rdx, r13
0x1800deb7c  mov     rcx, rbx
0x1800deb7f  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1800deb84  xor     r13d, r13d
0x1800deb87  test    rax, rax
0x1800deb8a  jz      loc_1800DED22
0x1800deb90  or      r8d, 0FFFFFFFFh
0x1800deb94  mov     rdx, r12
0x1800deb97  lea     rcx, [rbx+18h]
0x1800deb9b  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1800deba0  test    rax, rax
0x1800deba3  jz      loc_1800DED22
0x1800deba9  mov     rdx, [rbp+arg_20]
0x1800debad  test    rdx, rdx
0x1800debb0  jz      short loc_1800DEBC8
0x1800debb2  or      r8d, 0FFFFFFFFh
0x1800debb6  lea     rcx, [rbx+30h]
0x1800debba  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1800debbf  test    rax, rax
0x1800debc2  jz      loc_1800DED22
0x1800debc8  mov     [rsp+50h+lpThreadId], r13; lpThreadId
0x1800debcd  mov     [rsp+50h+dwCreationFlags], r13d; dwCreationFlags
0x1800debd2  mov     r9, rbx; lpParameter
0x1800debd5  lea     r8, LaunchPlmPackageThreadProc; lpStartAddress
0x1800debdc  xor     edx, edx; dwStackSize
0x1800debde  xor     ecx, ecx; lpThreadAttributes
0x1800debe0  call    cs:__imp_CreateThread
0x1800debe7  nop     dword ptr [rax+rax+00h]
0x1800debec  mov     rbx, rax
0x1800debef  mov     [rbp+var_18], rax
0x1800debf3  test    rax, rax
0x1800debf6  jnz     short loc_1800DEC18
0x1800debf8  call    cs:__imp_GetLastError
0x1800debff  nop     dword ptr [rax+rax+00h]
0x1800dec04  mov     edi, eax
0x1800dec06  test    eax, eax
0x1800dec08  jle     short loc_1800DEC13
0x1800dec0a  movzx   edi, ax
0x1800dec0d  or      edi, 80070000h
0x1800dec13  jmp     loc_1800DED0C
0x1800dec18  mov     [rbp+arg_8], r13
0x1800dec1c  test    r15d, r15d
0x1800dec1f  jnz     short loc_1800DEC3E
0x1800dec21  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800dec25  jz      short loc_1800DEC36
0x1800dec27  mov     rcx, rbx; hObject
0x1800dec2a  call    cs:__imp_CloseHandle
0x1800dec31  nop     dword ptr [rax+rax+00h]
0x1800dec36  mov     edi, r13d
0x1800dec39  jmp     loc_1800DED0C
0x1800dec3e  mov     [rbp+Handles], r14
0x1800dec42  mov     [rbp+var_8], rbx
0x1800dec46  mov     esi, 2
0x1800dec4b  mov     r14b, 1
0x1800dec4e  mov     r12d, 80004005h
0x1800dec54  mov     edi, r13d
0x1800dec57  test    r14b, r14b
0x1800dec5a  jz      loc_1800DED19
0x1800dec60  mov     r14b, r13b
0x1800dec63  mov     [rsp+50h+dwCreationFlags], r13d; bAlertable
0x1800dec68  mov     r9d, r15d; dwMilliseconds
0x1800dec6b  xor     r8d, r8d; bWaitAll
0x1800dec6e  lea     rdx, [rbp+Handles]; lpHandles
0x1800dec72  mov     ecx, esi; nCount
0x1800dec74  call    cs:__imp_WaitForMultipleObjectsEx
0x1800dec7b  nop     dword ptr [rax+rax+00h]
0x1800dec80  test    eax, eax
0x1800dec82  jz      short loc_1800DEC54
0x1800dec84  cmp     eax, 1
0x1800dec87  jz      short loc_1800DEC9C
0x1800dec89  cmp     eax, 102h
0x1800dec8e  jz      short loc_1800DEC95
0x1800dec90  mov     edi, r12d
0x1800dec93  jmp     short loc_1800DEC57
0x1800dec95  mov     edi, 80070102h
0x1800dec9a  jmp     short loc_1800DEC57
0x1800dec9c  cmp     esi, 2
0x1800dec9f  jz      short loc_1800DECA6
0x1800deca1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800deca6  mov     [rbp+ExitCode], r13d
0x1800decaa  lea     rdx, [rbp+ExitCode]; lpExitCode
0x1800decae  mov     rcx, rbx; hThread
0x1800decb1  call    cs:__imp_GetExitCodeThread
0x1800decb8  nop     dword ptr [rax+rax+00h]
0x1800decbd  test    eax, eax
0x1800decbf  jz      short loc_1800DECD2
0x1800decc1  mov     edi, [rbp+ExitCode]
0x1800decc4  test    edi, edi
0x1800decc6  js      short loc_1800DECF6
0x1800decc8  mov     esi, 1
0x1800deccd  mov     r14b, sil
0x1800decd0  jmp     short loc_1800DEC57
0x1800decd2  call    cs:__imp_GetLastError
0x1800decd9  nop     dword ptr [rax+rax+00h]
0x1800decde  mov     edi, eax
0x1800dece0  test    eax, eax
0x1800dece2  jle     loc_1800DEC57
0x1800dece8  movzx   edi, ax
0x1800deceb  or      edi, 80070000h
0x1800decf1  jmp     loc_1800DEC57
0x1800decf6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800decfa  jz      short loc_1800DED0C
0x1800decfc  mov     rcx, rbx; hObject
0x1800decff  call    cs:__imp_CloseHandle
0x1800ded06  nop     dword ptr [rax+rax+00h]
0x1800ded0b  nop
0x1800ded0c  lea     rcx, [rbp+arg_8]
0x1800ded10  call    ??1?$DbsDeletePtr@ULaunchPackageThreadData@@@@QEAA@XZ; DbsDeletePtr<LaunchPackageThreadData>::~DbsDeletePtr<LaunchPackageThreadData>(void)
0x1800ded15  mov     eax, edi
0x1800ded17  jmp     short loc_1800DED30
0x1800ded19  cmp     edi, 1
0x1800ded1c  cmovge  edi, r12d
0x1800ded20  jmp     short loc_1800DECF6
0x1800ded22  lea     rcx, [rbp+arg_8]
0x1800ded26  call    ??1?$DbsDeletePtr@ULaunchPackageThreadData@@@@QEAA@XZ; DbsDeletePtr<LaunchPackageThreadData>::~DbsDeletePtr<LaunchPackageThreadData>(void)
0x1800ded2b  mov     eax, 8007000Eh
0x1800ded30  mov     rbx, [rsp+50h+arg_10]
0x1800ded38  add     rsp, 50h
0x1800ded3c  pop     r15
0x1800ded3e  pop     r14
0x1800ded40  pop     r13
0x1800ded42  pop     r12
0x1800ded44  pop     rdi
0x1800ded45  pop     rsi
0x1800ded46  pop     rbp
0x1800ded47  retn
```
