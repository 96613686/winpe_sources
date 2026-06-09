# CAsyncReflectionDump::Reflect(ulong,ulong,ulong,ulong,wchar_t const *)

- ea: `0x180047990`
- end: `0x180047ad4`
- name: `?Reflect@CAsyncReflectionDump@@UEAAJKKKKPEB_W@Z`
- size: `324`
- prototype: `__int64 __usercall@<rax>(CAsyncReflectionDump *__hidden this@<rcx>, DWORD dwProcessId@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180045148`

## callees

- `0x180009f00`
- `0x180046d8c`
- `0x18004752c`
- `0x180047990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180047a43`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180047a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047a5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047a5b`

## pseudocode

```c
__int64 __fastcall CAsyncReflectionDump::Reflect(
        CAsyncReflectionDump *this,
        DWORD dwProcessId,
        int a3,
        int a4,
        unsigned int a5,
        const wchar_t *a6)
{
  unsigned int ReflectionObjectForPid; // ebx
  HANDLE Thread; // rax
  void *v12; // rcx
  signed int LastError; // eax

  CAsyncReflectionDump::Cleanup(this, 0xFFFFFFFF);
  *((_DWORD *)this + 8) = -2147483638;
  ReflectionObjectForPid = CReflectedDump::GetReflectionObjectForPid(dwProcessId);
  if ( (ReflectionObjectForPid & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
        ReflectionObjectForPid);
LABEL_14:
    CAsyncReflectionDump::Cleanup(this, 0xFFFFFFFF);
    return ReflectionObjectForPid;
  }
  *((_DWORD *)this + 5) = a5;
  *((_QWORD *)this + 3) = a6;
  *((_DWORD *)this + 2) = dwProcessId;
  *((_DWORD *)this + 3) = a3;
  *((_DWORD *)this + 4) = a4;
  Thread = CreateThread(0, 0, CAsyncReflectionDump::static_ReflectionThreadProc, this, 0, 0);
  v12 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = Thread;
  if ( (unsigned __int64)v12 + 1 > 1 )
    CloseHandle(v12);
  if ( *((_QWORD *)this + 5) != -1 && *((_QWORD *)this + 5) != 0 )
    return 0;
  LastError = GetLastError();
  ReflectionObjectForPid = LastError;
  if ( LastError > 0 )
    ReflectionObjectForPid = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      90,
      &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
      ReflectionObjectForPid);
  if ( (ReflectionObjectForPid & 0x80000000) != 0 )
    goto LABEL_14;
  return ReflectionObjectForPid;
}

```

## disassembly

```asm
0x180047990  push    rbx
0x180047992  push    rbp
0x180047993  push    rsi
0x180047994  push    rdi
0x180047995  push    r14
0x180047997  sub     rsp, 30h
0x18004799b  mov     esi, edx
0x18004799d  mov     ebp, r9d
0x1800479a0  or      edx, 0FFFFFFFFh; unsigned int
0x1800479a3  mov     r14d, r8d
0x1800479a6  mov     rdi, rcx
0x1800479a9  call    ?Cleanup@CAsyncReflectionDump@@QEAAXK@Z; CAsyncReflectionDump::Cleanup(ulong)
0x1800479ae  lea     rdx, [rdi+30h]
0x1800479b2  mov     dword ptr [rdi+20h], 8000000Ah
0x1800479b9  mov     ecx, esi; dwProcessId
0x1800479bb  call    ?GetReflectionObjectForPid@CReflectedDump@@SAJKPEAV?$unique_ptr@VIReflectedDump@@U?$default_delete@VIReflectedDump@@@utl@@@utl@@@Z; CReflectedDump::GetReflectionObjectForPid(ulong,utl::unique_ptr<IReflectedDump,utl::default_delete<IReflectedDump>> *)
0x1800479c0  mov     ebx, eax
0x1800479c2  test    eax, eax
0x1800479c4  jns     short loc_180047A04
0x1800479c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800479cd  lea     rax, WPP_GLOBAL_Control
0x1800479d4  cmp     rcx, rax
0x1800479d7  jz      loc_180047AB8
0x1800479dd  test    byte ptr [rcx+1Ch], 1
0x1800479e1  jz      loc_180047AB8
0x1800479e7  mov     rcx, [rcx+10h]
0x1800479eb  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1800479f2  mov     edx, 59h ; 'Y'
0x1800479f7  mov     r9d, ebx
0x1800479fa  call    WPP_SF_d
0x1800479ff  jmp     loc_180047AB8
0x180047a04  mov     eax, [rsp+58h+arg_20]
0x180047a0b  lea     r8, ?static_ReflectionThreadProc@CAsyncReflectionDump@@KAKPEAX@Z; lpStartAddress
0x180047a12  mov     [rdi+14h], eax
0x180047a15  mov     r9, rdi; lpParameter
0x180047a18  mov     rax, [rsp+58h+arg_28]
0x180047a20  xor     edx, edx; dwStackSize
0x180047a22  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180047a2b  xor     ecx, ecx; lpThreadAttributes
0x180047a2d  mov     [rdi+18h], rax
0x180047a31  mov     [rdi+8], esi
0x180047a34  mov     [rdi+0Ch], r14d
0x180047a38  mov     [rdi+10h], ebp
0x180047a3b  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180047a43  call    cs:__imp_CreateThread
0x180047a49  mov     rcx, [rdi+28h]; hObject
0x180047a4d  mov     [rdi+28h], rax
0x180047a51  lea     rax, [rcx+1]
0x180047a55  cmp     rax, 1
0x180047a59  jbe     short loc_180047A61
0x180047a5b  call    cs:__imp_CloseHandle
0x180047a61  mov     rax, [rdi+28h]
0x180047a65  inc     rax
0x180047a68  cmp     rax, 1
0x180047a6c  ja      short loc_180047AC5
0x180047a6e  call    cs:__imp_GetLastError
0x180047a74  mov     ebx, eax
0x180047a76  test    eax, eax
0x180047a78  jle     short loc_180047A83
0x180047a7a  movzx   ebx, ax
0x180047a7d  or      ebx, 80070000h
0x180047a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180047a8a  lea     rax, WPP_GLOBAL_Control
0x180047a91  cmp     rcx, rax
0x180047a94  jz      short loc_180047AB4
0x180047a96  test    byte ptr [rcx+1Ch], 1
0x180047a9a  jz      short loc_180047AB4
0x180047a9c  mov     rcx, [rcx+10h]
0x180047aa0  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x180047aa7  mov     edx, 5Ah ; 'Z'
0x180047aac  mov     r9d, ebx
0x180047aaf  call    WPP_SF_d
0x180047ab4  test    ebx, ebx
0x180047ab6  jns     short loc_180047AC7
0x180047ab8  or      edx, 0FFFFFFFFh; unsigned int
0x180047abb  mov     rcx, rdi; this
0x180047abe  call    ?Cleanup@CAsyncReflectionDump@@QEAAXK@Z; CAsyncReflectionDump::Cleanup(ulong)
0x180047ac3  jmp     short loc_180047AC7
0x180047ac5  xor     ebx, ebx
0x180047ac7  mov     eax, ebx
0x180047ac9  add     rsp, 30h
0x180047acd  pop     r14
0x180047acf  pop     rdi
0x180047ad0  pop     rsi
0x180047ad1  pop     rbp
0x180047ad2  pop     rbx
0x180047ad3  retn
```
