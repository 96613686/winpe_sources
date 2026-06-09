# CCrashReport::SuspendProcess(void)

- ea: `0x180015e5c`
- end: `0x18001609c`
- name: `?SuspendProcess@CCrashReport@@AEAAXXZ`
- size: `576`
- prototype: `void __fastcall(CCrashReport *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800143a8`
- `0x180014c34`

## callees

- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x180015e5c`
- `0x180016964`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180015eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180015eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001606d`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18001606d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016013`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180016013`
- `ntdll!NtResumeThread` at `0x180016041`
- `ntdll!NtResumeThread` at `0x180016041`
- `ntdll!NtSuspendProcess` at `0x180015fcb`
- `ntdll!NtSuspendProcess` at `0x180015fcb`

## pseudocode

```c
void __fastcall CCrashReport::SuspendProcess(CCrashReport *this)
{
  void *v2; // rcx
  DWORD ProcessId; // esi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v6; // ecx
  NTSTATUS v7; // eax
  int v8; // ebp
  DWORD TickCount; // eax
  bool v10; // zf
  void *v11; // rcx
  NTSTATUS v12; // esi
  ULONG v13; // ebx
  DWORD ThreadId; // eax
  __int64 v15; // r8
  ULONG SuspendCount; // [rsp+60h] [rbp+8h] BYREF

  v2 = (void *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)v2 + 1 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids);
    return;
  }
  ProcessId = GetProcessId(v2);
  if ( *((_DWORD *)this + 5) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return;
    v5 = 112;
    goto LABEL_9;
  }
  if ( *(_DWORD *)this )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return;
    v5 = 113;
    goto LABEL_9;
  }
  if ( *((_DWORD *)this + 1) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return;
    v5 = 114;
    goto LABEL_9;
  }
  if ( (*((_BYTE *)this + 28) & 4) != 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return;
    v5 = 115;
    goto LABEL_9;
  }
  v6 = *(_DWORD *)(*((_QWORD *)this + 5) + 236LL);
  if ( v6 < 0 && (v6 & 4) != 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return;
    v5 = 116;
LABEL_9:
    WPP_SF_d(v4[2], v5, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, ProcessId);
    return;
  }
  v7 = NtSuspendProcess(*((HANDLE *)this + 6));
  v8 = v7;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, ProcessId, v7);
  if ( v8 < 0 )
  {
    *((_DWORD *)this + 5) = 0;
    TickCount = 0;
  }
  else
  {
    *((_DWORD *)this + 5) = 1;
    TickCount = GetTickCount();
  }
  v10 = *((_DWORD *)this + 5) == 0;
  *((_DWORD *)this + 1218) = TickCount;
  if ( !v10 )
  {
    v11 = (void *)*((_QWORD *)this + 7);
    SuspendCount = 0;
    v12 = NtResumeThread(v11, &SuspendCount);
    *((_DWORD *)this + 6) = v12 >= 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v13 = SuspendCount;
      ThreadId = GetThreadId(*((HANDLE *)this + 7));
      WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, v15, ThreadId, v12, v13);
    }
  }
}

```

## disassembly

```asm
0x180015e5c  push    rbx
0x180015e5e  push    rbp
0x180015e5f  push    rsi
0x180015e60  push    rdi
0x180015e61  sub     rsp, 38h
0x180015e65  mov     rdi, rcx
0x180015e68  mov     rcx, [rcx+30h]; Process
0x180015e6c  lea     rax, [rcx+1]
0x180015e70  cmp     rax, 1
0x180015e74  ja      short loc_180015EB1
0x180015e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e7d  lea     rbx, WPP_GLOBAL_Control
0x180015e84  cmp     rcx, rbx
0x180015e87  jz      loc_180016093
0x180015e8d  test    byte ptr [rcx+1Ch], 4
0x180015e91  jz      loc_180016093
0x180015e97  mov     rcx, [rcx+10h]
0x180015e9b  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180015ea2  mov     edx, 6Fh ; 'o'
0x180015ea7  call    WPP_SF_
0x180015eac  jmp     loc_180016093
0x180015eb1  call    cs:__imp_GetProcessId
0x180015eb7  cmp     dword ptr [rdi+14h], 0
0x180015ebb  mov     esi, eax
0x180015ebd  jz      short loc_180015EFD
0x180015ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ec6  lea     rbx, WPP_GLOBAL_Control
0x180015ecd  cmp     rcx, rbx
0x180015ed0  jz      loc_180016093
0x180015ed6  test    byte ptr [rcx+1Ch], 4
0x180015eda  jz      loc_180016093
0x180015ee0  mov     edx, 70h ; 'p'
0x180015ee5  mov     rcx, [rcx+10h]
0x180015ee9  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180015ef0  mov     r9d, esi
0x180015ef3  call    WPP_SF_d
0x180015ef8  jmp     loc_180016093
0x180015efd  cmp     dword ptr [rdi], 0
0x180015f00  jz      short loc_180015F2A
0x180015f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f09  lea     rbx, WPP_GLOBAL_Control
0x180015f10  cmp     rcx, rbx
0x180015f13  jz      loc_180016093
0x180015f19  test    byte ptr [rcx+1Ch], 4
0x180015f1d  jz      loc_180016093
0x180015f23  mov     edx, 71h ; 'q'
0x180015f28  jmp     short loc_180015EE5
0x180015f2a  cmp     dword ptr [rdi+4], 0
0x180015f2e  jz      short loc_180015F58
0x180015f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f37  lea     rbx, WPP_GLOBAL_Control
0x180015f3e  cmp     rcx, rbx
0x180015f41  jz      loc_180016093
0x180015f47  test    byte ptr [rcx+1Ch], 4
0x180015f4b  jz      loc_180016093
0x180015f51  mov     edx, 72h ; 'r'
0x180015f56  jmp     short loc_180015EE5
0x180015f58  test    byte ptr [rdi+1Ch], 4
0x180015f5c  jz      short loc_180015F89
0x180015f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f65  lea     rbx, WPP_GLOBAL_Control
0x180015f6c  cmp     rcx, rbx
0x180015f6f  jz      loc_180016093
0x180015f75  test    byte ptr [rcx+1Ch], 4
0x180015f79  jz      loc_180016093
0x180015f7f  mov     edx, 73h ; 's'
0x180015f84  jmp     loc_180015EE5
0x180015f89  mov     rax, [rdi+28h]
0x180015f8d  mov     ecx, [rax+0ECh]
0x180015f93  test    ecx, ecx
0x180015f95  jns     short loc_180015FC7
0x180015f97  test    cl, 4
0x180015f9a  jz      short loc_180015FC7
0x180015f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fa3  lea     rbx, WPP_GLOBAL_Control
0x180015faa  cmp     rcx, rbx
0x180015fad  jz      loc_180016093
0x180015fb3  test    byte ptr [rcx+1Ch], 4
0x180015fb7  jz      loc_180016093
0x180015fbd  mov     edx, 74h ; 't'
0x180015fc2  jmp     loc_180015EE5
0x180015fc7  mov     rcx, [rdi+30h]; ProcessHandle
0x180015fcb  call    cs:__imp_NtSuspendProcess
0x180015fd1  mov     ebp, eax
0x180015fd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fda  lea     rbx, WPP_GLOBAL_Control
0x180015fe1  cmp     rcx, rbx
0x180015fe4  jz      short loc_180016008
0x180015fe6  test    byte ptr [rcx+1Ch], 4
0x180015fea  jz      short loc_180016008
0x180015fec  mov     rcx, [rcx+10h]
0x180015ff0  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x180015ff7  mov     edx, 75h ; 'u'
0x180015ffc  mov     [rsp+58h+var_38], eax
0x180016000  mov     r9d, esi
0x180016003  call    WPP_SF_Dd
0x180016008  test    ebp, ebp
0x18001600a  js      short loc_18001601B
0x18001600c  mov     dword ptr [rdi+14h], 1
0x180016013  call    cs:__imp_GetTickCount
0x180016019  jmp     short loc_180016024
0x18001601b  mov     dword ptr [rdi+14h], 0
0x180016022  xor     eax, eax
0x180016024  cmp     dword ptr [rdi+14h], 0
0x180016028  mov     [rdi+1308h], eax
0x18001602e  jz      short loc_180016093
0x180016030  mov     rcx, [rdi+38h]; ThreadHandle
0x180016034  lea     rdx, [rsp+58h+SuspendCount]; SuspendCount
0x180016039  mov     [rsp+58h+SuspendCount], 0
0x180016041  call    cs:__imp_NtResumeThread
0x180016047  mov     ecx, eax
0x180016049  mov     esi, eax
0x18001604b  not     ecx
0x18001604d  shr     ecx, 1Fh
0x180016050  mov     [rdi+18h], ecx
0x180016053  mov     rcx, cs:WPP_GLOBAL_Control
0x18001605a  cmp     rcx, rbx
0x18001605d  jz      short loc_180016093
0x18001605f  test    byte ptr [rcx+1Ch], 4
0x180016063  jz      short loc_180016093
0x180016065  mov     rcx, [rdi+38h]; Thread
0x180016069  mov     ebx, [rsp+58h+SuspendCount]
0x18001606d  call    cs:__imp_GetThreadId
0x180016073  mov     rcx, cs:WPP_GLOBAL_Control
0x18001607a  mov     edx, 76h ; 'v'
0x18001607f  mov     [rsp+58h+var_30], ebx
0x180016083  mov     r9d, eax
0x180016086  mov     [rsp+58h+var_38], esi
0x18001608a  mov     rcx, [rcx+10h]
0x18001608e  call    WPP_SF_DdD
0x180016093  add     rsp, 38h
0x180016097  pop     rdi
0x180016098  pop     rsi
0x180016099  pop     rbp
0x18001609a  pop     rbx
0x18001609b  retn
```
