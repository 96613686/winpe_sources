# StopFaxServiceProviders(void)

- ea: `0x140048fac`
- end: `0x140049161`
- name: `?StopFaxServiceProviders@@YAHXZ`
- size: `437`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140023d20`
- `0x140046a7c`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140025194`
- `0x140048fac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140049046`
- `KERNEL32!GetLastError` at `0x1400490dc`
- `KERNEL32!GetLastError` at `0x140049112`
- `KERNEL32!GetLastError` at `0x140049046`
- `KERNEL32!GetLastError` at `0x1400490dc`
- `KERNEL32!GetLastError` at `0x140049112`
- `KERNEL32!SetLastError` at `0x140049142`
- `KERNEL32!SetLastError` at `0x140049142`
- `KERNEL32!CloseHandle` at `0x14004914b`
- `KERNEL32!CloseHandle` at `0x14004914b`
- `KERNEL32!WaitForSingleObject` at `0x140049084`
- `KERNEL32!WaitForSingleObject` at `0x140049084`
- `KERNEL32!GetExitCodeThread` at `0x1400490f1`
- `KERNEL32!GetExitCodeThread` at `0x1400490f1`
- `KERNEL32!CreateThread` at `0x140049021`
- `KERNEL32!CreateThread` at `0x140049021`

## pseudocode

```c
_BOOL8 StopFaxServiceProviders(void)
{
  unsigned int v0; // edx
  HANDLE v1; // rdi
  DWORD v2; // eax
  BOOL v3; // ebx
  unsigned int i; // r8d
  DWORD v5; // eax
  DWORD LastError; // eax
  __int64 v7; // rdx
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF

  ThreadId = 0;
  ExitCode = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  v1 = CreateThread(0, 0, ShutdownDeviceProviders, 0, 0, &ThreadId);
  if ( v1 )
  {
    for ( i = 20000; ; i = 30000 )
    {
      ReportServiceStatus(3u, v0, i);
      v5 = WaitForSingleObject(v1, 0x2710u);
      if ( !v5 )
        break;
      if ( v5 != 258 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v7 = 56;
          goto LABEL_28;
        }
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
      }
    }
    if ( !GetExitCodeThread(v1, &ExitCode) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v7 = 54;
LABEL_28:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
      }
LABEL_29:
      v3 = 0;
      goto LABEL_31;
    }
    v3 = ExitCode == 0;
    SetLastError(ExitCode);
LABEL_31:
    CloseHandle(v1);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v2 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v2);
    }
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x140048fac  mov     [rsp+arg_10], rbx
0x140048fb1  push    rbp
0x140048fb2  push    rdi
0x140048fb3  push    r14
0x140048fb5  sub     rsp, 30h
0x140048fb9  mov     [rsp+48h+ThreadId], 0
0x140048fc1  mov     [rsp+48h+ExitCode], 0
0x140048fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140048fd0  lea     rbp, WPP_GLOBAL_Control
0x140048fd7  lea     r14, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x140048fde  mov     bl, 4
0x140048fe0  cmp     rcx, rbp
0x140048fe3  jz      short loc_140049001
0x140048fe5  test    [rcx+1Ch], bl
0x140048fe8  jz      short loc_140049001
0x140048fea  cmp     byte ptr [rcx+19h], 5
0x140048fee  jb      short loc_140049001
0x140048ff0  mov     rcx, [rcx+10h]
0x140048ff4  mov     edx, 34h ; '4'
0x140048ff9  mov     r8, r14
0x140048ffc  call    WPP_SF_
0x140049001  lea     rax, [rsp+48h+ThreadId]
0x140049006  xor     r9d, r9d; lpParameter
0x140049009  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x14004900e  lea     r8, ?ShutdownDeviceProviders@@YAKPEAX@Z; lpStartAddress
0x140049015  xor     edx, edx; dwStackSize
0x140049017  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x14004901f  xor     ecx, ecx; lpThreadAttributes
0x140049021  call    cs:__imp_CreateThread
0x140049027  mov     rdi, rax
0x14004902a  test    rax, rax
0x14004902d  jnz     short loc_14004906C
0x14004902f  mov     rax, cs:WPP_GLOBAL_Control
0x140049036  cmp     rax, rbp
0x140049039  jz      short loc_140049065
0x14004903b  test    [rax+1Ch], bl
0x14004903e  jz      short loc_140049065
0x140049040  cmp     byte ptr [rax+19h], 2
0x140049044  jb      short loc_140049065
0x140049046  call    cs:__imp_GetLastError
0x14004904c  mov     rcx, cs:WPP_GLOBAL_Control
0x140049053  lea     edx, [rdi+35h]
0x140049056  mov     r9d, eax
0x140049059  mov     r8, r14
0x14004905c  mov     rcx, [rcx+10h]
0x140049060  call    WPP_SF_d
0x140049065  xor     ebx, ebx
0x140049067  jmp     loc_140049151
0x14004906c  mov     r8d, 4E20h; unsigned int
0x140049072  mov     ecx, 3; unsigned int
0x140049077  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x14004907c  mov     edx, 2710h; dwMilliseconds
0x140049081  mov     rcx, rdi; hHandle
0x140049084  call    cs:__imp_WaitForSingleObject
0x14004908a  test    eax, eax
0x14004908c  jz      short loc_1400490E9
0x14004908e  cmp     eax, 102h
0x140049093  jnz     short loc_1400490C5
0x140049095  mov     rcx, cs:WPP_GLOBAL_Control
0x14004909c  cmp     rcx, rbp
0x14004909f  jz      short loc_1400490BD
0x1400490a1  test    [rcx+1Ch], bl
0x1400490a4  jz      short loc_1400490BD
0x1400490a6  cmp     byte ptr [rcx+19h], 5
0x1400490aa  jb      short loc_1400490BD
0x1400490ac  mov     rcx, [rcx+10h]
0x1400490b0  mov     edx, 37h ; '7'
0x1400490b5  mov     r8, r14
0x1400490b8  call    WPP_SF_
0x1400490bd  mov     r8d, 7530h
0x1400490c3  jmp     short loc_140049072
0x1400490c5  mov     rax, cs:WPP_GLOBAL_Control
0x1400490cc  cmp     rax, rbp
0x1400490cf  jz      short loc_140049133
0x1400490d1  test    [rax+1Ch], bl
0x1400490d4  jz      short loc_140049133
0x1400490d6  cmp     byte ptr [rax+19h], 2
0x1400490da  jb      short loc_140049133
0x1400490dc  call    cs:__imp_GetLastError
0x1400490e2  mov     edx, 38h ; '8'
0x1400490e7  jmp     short loc_14004911D
0x1400490e9  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x1400490ee  mov     rcx, rdi; hThread
0x1400490f1  call    cs:__imp_GetExitCodeThread
0x1400490f7  test    eax, eax
0x1400490f9  jnz     short loc_140049137
0x1400490fb  mov     rax, cs:WPP_GLOBAL_Control
0x140049102  cmp     rax, rbp
0x140049105  jz      short loc_140049133
0x140049107  test    [rax+1Ch], bl
0x14004910a  jz      short loc_140049133
0x14004910c  cmp     byte ptr [rax+19h], 2
0x140049110  jb      short loc_140049133
0x140049112  call    cs:__imp_GetLastError
0x140049118  mov     edx, 36h ; '6'
0x14004911d  mov     rcx, cs:WPP_GLOBAL_Control
0x140049124  mov     r9d, eax
0x140049127  mov     r8, r14
0x14004912a  mov     rcx, [rcx+10h]
0x14004912e  call    WPP_SF_d
0x140049133  xor     ebx, ebx
0x140049135  jmp     short loc_140049148
0x140049137  mov     ecx, [rsp+48h+ExitCode]; dwErrCode
0x14004913b  xor     ebx, ebx
0x14004913d  test    ecx, ecx
0x14004913f  setz    bl
0x140049142  call    cs:__imp_SetLastError
0x140049148  mov     rcx, rdi; hObject
0x14004914b  call    cs:__imp_CloseHandle
0x140049151  mov     eax, ebx
0x140049153  mov     rbx, [rsp+48h+arg_10]
0x140049158  add     rsp, 30h
0x14004915c  pop     r14
0x14004915e  pop     rdi
0x14004915f  pop     rbp
0x140049160  retn
```
