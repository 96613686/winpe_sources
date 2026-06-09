# CNotificationMap::Init(void)

- ea: `0x14005a080`
- end: `0x14005a1b8`
- name: `?Init@CNotificationMap@@QEAAKXZ`
- size: `312`
- prototype: `unsigned int __fastcall(CNotificationMap *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400480f0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14004ecd4`
- `0x14005a080`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005a0f6`
- `KERNEL32!GetLastError` at `0x14005a14f`
- `KERNEL32!GetLastError` at `0x14005a0f6`
- `KERNEL32!GetLastError` at `0x14005a14f`
- `KERNEL32!CloseHandle` at `0x14005a18b`
- `KERNEL32!CloseHandle` at `0x14005a1a0`
- `KERNEL32!CloseHandle` at `0x14005a18b`
- `KERNEL32!CloseHandle` at `0x14005a1a0`
- `KERNEL32!InitializeCriticalSection` at `0x14005a0ce`
- `KERNEL32!InitializeCriticalSection` at `0x14005a0ce`
- `KERNEL32!CreateIoCompletionPort` at `0x14005a0e7`
- `KERNEL32!CreateIoCompletionPort` at `0x14005a0e7`

## pseudocode

```c
__int64 __fastcall CNotificationMap::Init(CNotificationMap *this)
{
  struct CNotificationMap *v1; // rbx
  HANDLE IoCompletionPort; // rax
  __int64 v3; // rdx
  struct _SECURITY_ATTRIBUTES *v4; // rcx
  DWORD v5; // eax
  DWORD v6; // ebx
  __int64 result; // rax
  HANDLE ThreadAndRefCount; // rax
  DWORD LastError; // eax
  DWORD v10; // edi
  unsigned int v11; // [rsp+20h] [rbp-18h]

  v1 = g_pNotificationMap;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids);
  }
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 16));
  *((_BYTE *)v1 + 56) = 1;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  *((_QWORD *)v1 + 1) = IoCompletionPort;
  if ( IoCompletionPort )
  {
    ThreadAndRefCount = CreateThreadAndRefCount(
                          v4,
                          v3,
                          (unsigned int (*)(void *))CNotificationMap::ExtNotificationThread,
                          0,
                          v11,
                          0);
    if ( ThreadAndRefCount )
    {
      CloseHandle(ThreadAndRefCount);
      return 0;
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, LastError);
      }
      CloseHandle(*((HANDLE *)v1 + 1));
      result = v10;
      *((_QWORD *)v1 + 1) = 0;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, v5);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14005a080  mov     [rsp+arg_0], rbx
0x14005a085  mov     [rsp+arg_8], rbp
0x14005a08a  push    rdi
0x14005a08b  sub     rsp, 30h
0x14005a08f  mov     rbx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14005a096  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a09d  lea     rbp, WPP_GLOBAL_Control
0x14005a0a4  cmp     rcx, rbp
0x14005a0a7  jz      short loc_14005A0CA
0x14005a0a9  test    byte ptr [rcx+1Ch], 4
0x14005a0ad  jz      short loc_14005A0CA
0x14005a0af  cmp     byte ptr [rcx+19h], 5
0x14005a0b3  jb      short loc_14005A0CA
0x14005a0b5  mov     rcx, [rcx+10h]
0x14005a0b9  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005a0c0  mov     edx, 27h ; '''
0x14005a0c5  call    WPP_SF_
0x14005a0ca  lea     rcx, [rbx+10h]; lpCriticalSection
0x14005a0ce  call    cs:__imp_InitializeCriticalSection
0x14005a0d4  mov     r9d, 1; NumberOfConcurrentThreads
0x14005a0da  mov     byte ptr [rbx+38h], 1
0x14005a0de  xor     r8d, r8d; CompletionKey
0x14005a0e1  xor     edx, edx; ExistingCompletionPort
0x14005a0e3  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x14005a0e7  call    cs:__imp_CreateIoCompletionPort
0x14005a0ed  mov     [rbx+8], rax
0x14005a0f1  test    rax, rax
0x14005a0f4  jnz     short loc_14005A132
0x14005a0f6  call    cs:__imp_GetLastError
0x14005a0fc  mov     ebx, eax
0x14005a0fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a105  cmp     rcx, rbp
0x14005a108  jz      short loc_14005A12E
0x14005a10a  test    byte ptr [rcx+1Ch], 4
0x14005a10e  jz      short loc_14005A12E
0x14005a110  cmp     byte ptr [rcx+19h], 2
0x14005a114  jb      short loc_14005A12E
0x14005a116  mov     rcx, [rcx+10h]
0x14005a11a  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005a121  mov     edx, 28h ; '('
0x14005a126  mov     r9d, eax
0x14005a129  call    WPP_SF_d
0x14005a12e  mov     eax, ebx
0x14005a130  jmp     short loc_14005A1A8
0x14005a132  xor     r9d, r9d; void *
0x14005a135  mov     [rsp+38h+var_10], 0; unsigned int *
0x14005a13e  lea     r8, ?ExtNotificationThread@CNotificationMap@@CAKPEAX@Z; unsigned int (*)(void *)
0x14005a145  call    ?CreateThreadAndRefCount@@YAPEAXPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KPEAK@Z; CreateThreadAndRefCount(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,ulong *)
0x14005a14a  test    rax, rax
0x14005a14d  jnz     short loc_14005A19D
0x14005a14f  call    cs:__imp_GetLastError
0x14005a155  mov     edi, eax
0x14005a157  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a15e  cmp     rcx, rbp
0x14005a161  jz      short loc_14005A187
0x14005a163  test    byte ptr [rcx+1Ch], 4
0x14005a167  jz      short loc_14005A187
0x14005a169  cmp     byte ptr [rcx+19h], 2
0x14005a16d  jb      short loc_14005A187
0x14005a16f  mov     rcx, [rcx+10h]
0x14005a173  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005a17a  mov     edx, 29h ; ')'
0x14005a17f  mov     r9d, eax
0x14005a182  call    WPP_SF_d
0x14005a187  mov     rcx, [rbx+8]; hObject
0x14005a18b  call    cs:__imp_CloseHandle
0x14005a191  mov     eax, edi
0x14005a193  mov     qword ptr [rbx+8], 0
0x14005a19b  jmp     short loc_14005A1A8
0x14005a19d  mov     rcx, rax; hObject
0x14005a1a0  call    cs:__imp_CloseHandle
0x14005a1a6  xor     eax, eax
0x14005a1a8  mov     rbx, [rsp+38h+arg_0]
0x14005a1ad  mov     rbp, [rsp+38h+arg_8]
0x14005a1b2  add     rsp, 30h
0x14005a1b6  pop     rdi
0x14005a1b7  retn
```
