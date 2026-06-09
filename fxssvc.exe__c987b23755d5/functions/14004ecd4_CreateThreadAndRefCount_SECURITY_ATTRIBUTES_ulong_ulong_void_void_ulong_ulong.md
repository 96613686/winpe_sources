# CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)

- ea: `0x14004ecd4`
- end: `0x14004edec`
- name: `?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z`
- size: `280`
- prototype: `void *(struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int (*)(void *), void *, unsigned int, unsigned int *)`
- caller_count: `8`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b544`
- `0x14002e978`
- `0x14002ea30`
- `0x140032ce8`
- `0x14003392c`
- `0x140041a98`
- `0x1400569ec`
- `0x14005a080`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14004ecd4`
- `0x14004fca8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004ed54`
- `KERNEL32!GetLastError` at `0x14004ed9c`
- `KERNEL32!GetLastError` at `0x14004ed54`
- `KERNEL32!GetLastError` at `0x14004ed9c`
- `KERNEL32!SetLastError` at `0x14004edd3`
- `KERNEL32!SetLastError` at `0x14004edd3`
- `KERNEL32!EnterCriticalSection` at `0x14004ed24`
- `KERNEL32!EnterCriticalSection` at `0x14004ed24`
- `KERNEL32!LeaveCriticalSection` at `0x14004edc6`
- `KERNEL32!LeaveCriticalSection` at `0x14004edc6`
- `KERNEL32!CreateThread` at `0x14004ed46`
- `KERNEL32!CreateThread` at `0x14004ed46`

## pseudocode

```c
HANDLE __fastcall CreateThreadAndRefCount(
        struct _SECURITY_ATTRIBUTES *a1,
        __int64 a2,
        unsigned int (*a3)(void *),
        void *a4,
        unsigned int a5,
        unsigned int *lpThreadId)
{
  HANDLE Thread; // rdi
  DWORD LastError; // eax
  DWORD v10; // ebx
  CMapDeviceId *v11; // rcx
  __int64 v12; // rdx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids);
  }
  EnterCriticalSection(&g_CsServiceThreads);
  Thread = CreateThread(0, 0, a3, a4, 0, lpThreadId);
  if ( Thread )
  {
    v10 = 0;
    if ( !(unsigned int)IncreaseServiceThreadsCount()
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      v12 = 50;
      goto LABEL_15;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 49;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids, LastError);
    }
  }
  LeaveCriticalSection(&g_CsServiceThreads);
  if ( !Thread )
    SetLastError(v10);
  return Thread;
}

```

## disassembly

```asm
0x14004ecd4  mov     [rsp+arg_0], rbx
0x14004ecd9  mov     [rsp+arg_8], rbp
0x14004ecde  push    rdi
0x14004ecdf  sub     rsp, 30h
0x14004ece3  mov     rbx, r9
0x14004ece6  mov     rdi, r8
0x14004ece9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ecf0  lea     rbp, WPP_GLOBAL_Control
0x14004ecf7  cmp     rcx, rbp
0x14004ecfa  jz      short loc_14004ED1D
0x14004ecfc  test    byte ptr [rcx+1Ch], 4
0x14004ed00  jz      short loc_14004ED1D
0x14004ed02  cmp     byte ptr [rcx+19h], 5
0x14004ed06  jb      short loc_14004ED1D
0x14004ed08  mov     rcx, [rcx+10h]
0x14004ed0c  lea     r8, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids
0x14004ed13  mov     edx, 30h ; '0'
0x14004ed18  call    WPP_SF_
0x14004ed1d  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004ed24  call    cs:__imp_EnterCriticalSection
0x14004ed2a  mov     rax, [rsp+38h+arg_28]
0x14004ed2f  mov     r9, rbx; lpParameter
0x14004ed32  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14004ed37  mov     r8, rdi; lpStartAddress
0x14004ed3a  xor     edx, edx; dwStackSize
0x14004ed3c  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14004ed44  xor     ecx, ecx; lpThreadAttributes
0x14004ed46  call    cs:__imp_CreateThread
0x14004ed4c  mov     rdi, rax
0x14004ed4f  test    rax, rax
0x14004ed52  jnz     short loc_14004ED79
0x14004ed54  call    cs:__imp_GetLastError
0x14004ed5a  mov     ebx, eax
0x14004ed5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ed63  cmp     rcx, rbp
0x14004ed66  jz      short loc_14004EDBF
0x14004ed68  test    byte ptr [rcx+1Ch], 4
0x14004ed6c  jz      short loc_14004EDBF
0x14004ed6e  cmp     byte ptr [rcx+19h], 2
0x14004ed72  jb      short loc_14004EDBF
0x14004ed74  lea     edx, [rdi+31h]
0x14004ed77  jmp     short loc_14004EDAC
0x14004ed79  xor     ebx, ebx
0x14004ed7b  call    ?IncreaseServiceThreadsCount@@YAHXZ; IncreaseServiceThreadsCount(void)
0x14004ed80  test    eax, eax
0x14004ed82  jnz     short loc_14004EDBF
0x14004ed84  mov     rax, cs:WPP_GLOBAL_Control
0x14004ed8b  cmp     rax, rbp
0x14004ed8e  jz      short loc_14004EDBF
0x14004ed90  test    byte ptr [rax+1Ch], 4
0x14004ed94  jz      short loc_14004EDBF
0x14004ed96  cmp     byte ptr [rax+19h], 2
0x14004ed9a  jb      short loc_14004EDBF
0x14004ed9c  call    cs:__imp_GetLastError
0x14004eda2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eda9  lea     edx, [rbx+32h]
0x14004edac  mov     rcx, [rcx+10h]
0x14004edb0  lea     r8, WPP_0362f8d91b5731b150afbfbe9b7fce65_Traceguids
0x14004edb7  mov     r9d, eax
0x14004edba  call    WPP_SF_d
0x14004edbf  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14004edc6  call    cs:__imp_LeaveCriticalSection
0x14004edcc  test    rdi, rdi
0x14004edcf  jnz     short loc_14004EDD9
0x14004edd1  mov     ecx, ebx; dwErrCode
0x14004edd3  call    cs:__imp_SetLastError
0x14004edd9  mov     rbx, [rsp+38h+arg_0]
0x14004edde  mov     rax, rdi
0x14004ede1  mov     rbp, [rsp+38h+arg_8]
0x14004ede6  add     rsp, 30h
0x14004edea  pop     rdi
0x14004edeb  retn
```
