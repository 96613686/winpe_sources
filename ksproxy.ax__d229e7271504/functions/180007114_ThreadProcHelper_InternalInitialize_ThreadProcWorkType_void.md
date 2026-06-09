# ThreadProcHelper::InternalInitialize(ThreadProcWorkType,void *)

- ea: `0x180007114`
- end: `0x180007292`
- name: `?InternalInitialize@ThreadProcHelper@@IEAAJW4ThreadProcWorkType@@PEAX@Z`
- size: `382`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180007b38`

## callees

- `0x180007114`
- `0x180007298`
- `0x1800072a8`
- `0x180007318`
- `0x1800081e4`
- `0x18001b6d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800071f6`
- `KERNEL32!GetLastError` at `0x18000724e`
- `KERNEL32!GetLastError` at `0x1800071f6`
- `KERNEL32!GetLastError` at `0x18000724e`
- `KERNEL32!CloseHandle` at `0x180007207`
- `KERNEL32!CloseHandle` at `0x180007207`
- `KERNEL32!CreateThread` at `0x1800071d9`
- `KERNEL32!CreateThread` at `0x1800071d9`
- `KERNEL32!GetCurrentProcess` at `0x180007151`
- `KERNEL32!GetCurrentProcess` at `0x180007160`
- `KERNEL32!GetCurrentProcess` at `0x180007151`
- `KERNEL32!GetCurrentProcess` at `0x180007160`
- `KERNEL32!SetLastError` at `0x180007215`
- `KERNEL32!SetLastError` at `0x180007215`
- `KERNEL32!DuplicateHandle` at `0x180007191`
- `KERNEL32!DuplicateHandle` at `0x180007191`

## string_xrefs

- `0x1800071a6`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x180007277`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
__int64 __fastcall ThreadProcHelper::InternalInitialize(__int64 a1, __int64 a2, void *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  const char *v9; // r9
  char *Thread; // rax
  char *v12; // rbp
  char *v13; // rdi
  DWORD LastError; // ebx
  signed int v15; // eax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (unsigned __int64)(*(_QWORD *)(a1 + 24) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v5 = -2147418113;
    v6 = 90;
    goto LABEL_15;
  }
  *(_DWORD *)(a1 + 92) = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1 + 40,
    0);
  CurrentProcess = GetCurrentProcess();
  v8 = GetCurrentProcess();
  if ( !DuplicateHandle(v8, a3, CurrentProcess, (LPHANDLE)(a1 + 40), 0, 0, 2u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x64,
             (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
             v9);
  Thread = (char *)CreateThread(0, 0, ThreadProcHelper::ThreadProc, (LPVOID)a1, 0, 0);
  v12 = *(char **)(a1 + 24);
  v13 = Thread;
  if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v12);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 24) = v13;
  if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v15 = GetLastError();
    v5 = v15;
    if ( v15 > 0 )
      v5 = (unsigned __int16)v15 | 0x80070000;
    if ( (v5 & 0x80000000) == 0 )
      return v5;
    v6 = 108;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (const char *)v5,
      dwDesiredAccess);
    return v5;
  }
  while ( !(unsigned __int8)wil::slim_event_t<1>::TryAcquireEvent(a1 + 12)
       && (unsigned __int8)wil::slim_event_t<1>::WaitForSignal(a1 + 12) )
    ;
  return *(unsigned int *)(a1 + 32);
}

```

## disassembly

```asm
0x180007114  push    rbx
0x180007116  push    rbp
0x180007117  push    rsi
0x180007118  push    rdi
0x180007119  sub     rsp, 48h
0x18000711d  mov     rax, [rcx+18h]
0x180007121  mov     rbp, r8
0x180007124  dec     rax
0x180007127  mov     rsi, rcx
0x18000712a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000712e  ja      short loc_18000713F
0x180007130  mov     ebx, 8000FFFFh
0x180007135  mov     edx, 5Ah ; 'Z'
0x18000713a  jmp     loc_180007272
0x18000713f  mov     dword ptr [rcx+5Ch], 0
0x180007146  xor     edx, edx
0x180007148  add     rcx, 28h ; '('
0x18000714c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180007151  call    cs:__imp_GetCurrentProcess
0x180007158  nop     dword ptr [rax+rax+00h]
0x18000715d  mov     rbx, rax
0x180007160  call    cs:__imp_GetCurrentProcess
0x180007167  nop     dword ptr [rax+rax+00h]
0x18000716c  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180007174  lea     r9, [rsi+28h]; lpTargetHandle
0x180007178  mov     rcx, rax; hSourceProcessHandle
0x18000717b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180007183  mov     r8, rbx; hTargetProcessHandle
0x180007186  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18000718e  mov     rdx, rbp; hSourceHandle
0x180007191  call    cs:__imp_DuplicateHandle
0x180007198  nop     dword ptr [rax+rax+00h]
0x18000719d  test    eax, eax
0x18000719f  jnz     short loc_1800071BA
0x1800071a1  mov     rcx, [rsp+68h]; this
0x1800071a6  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1800071ad  lea     edx, [rax+64h]; void *
0x1800071b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800071b5  jmp     loc_180007288
0x1800071ba  mov     qword ptr [rsp+68h+bInheritHandle], 0; lpThreadId
0x1800071c3  lea     r8, ?ThreadProc@ThreadProcHelper@@CAKPEAX@Z; lpStartAddress
0x1800071ca  mov     r9, rsi; lpParameter
0x1800071cd  mov     [rsp+68h+dwDesiredAccess], 0; int
0x1800071d5  xor     edx, edx; dwStackSize
0x1800071d7  xor     ecx, ecx; lpThreadAttributes
0x1800071d9  call    cs:__imp_CreateThread
0x1800071e0  nop     dword ptr [rax+rax+00h]
0x1800071e5  mov     rbp, [rsi+18h]
0x1800071e9  mov     rdi, rax
0x1800071ec  lea     rdx, [rbp-1]
0x1800071f0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800071f4  ja      short loc_180007221
0x1800071f6  call    cs:__imp_GetLastError
0x1800071fd  nop     dword ptr [rax+rax+00h]
0x180007202  mov     rcx, rbp; hObject
0x180007205  mov     ebx, eax
0x180007207  call    cs:__imp_CloseHandle
0x18000720e  nop     dword ptr [rax+rax+00h]
0x180007213  mov     ecx, ebx; dwErrCode
0x180007215  call    cs:__imp_SetLastError
0x18000721c  nop     dword ptr [rax+rax+00h]
0x180007221  lea     rax, [rdi-1]
0x180007225  mov     [rsi+18h], rdi
0x180007229  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000722d  ja      short loc_18000724E
0x18000722f  lea     rcx, [rsi+0Ch]
0x180007233  call    ?TryAcquireEvent@?$slim_event_t@$00@wil@@AEAA_NXZ; wil::slim_event_t<1>::TryAcquireEvent(void)
0x180007238  test    al, al
0x18000723a  jnz     short loc_180007249
0x18000723c  lea     rcx, [rsi+0Ch]
0x180007240  call    ?WaitForSignal@?$slim_event_t@$00@wil@@AEAA_NK@Z; wil::slim_event_t<1>::WaitForSignal(ulong)
0x180007245  test    al, al
0x180007247  jnz     short loc_18000722F
0x180007249  mov     eax, [rsi+20h]
0x18000724c  jmp     short loc_180007288
0x18000724e  call    cs:__imp_GetLastError
0x180007255  nop     dword ptr [rax+rax+00h]
0x18000725a  mov     ebx, eax
0x18000725c  test    eax, eax
0x18000725e  jle     short loc_180007269
0x180007260  movzx   ebx, ax
0x180007263  or      ebx, 80070000h
0x180007269  test    ebx, ebx
0x18000726b  jns     short loc_180007286
0x18000726d  mov     edx, 6Ch ; 'l'; void *
0x180007272  mov     rcx, [rsp+68h]; this
0x180007277  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18000727e  mov     r9d, ebx; char *
0x180007281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007286  mov     eax, ebx
0x180007288  add     rsp, 48h
0x18000728c  pop     rdi
0x18000728d  pop     rsi
0x18000728e  pop     rbp
0x18000728f  pop     rbx
0x180007290  retn
```
