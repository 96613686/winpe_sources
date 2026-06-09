# CNotificationMap::ExtNotificationThread(void *)

- ea: `0x1400598e0`
- end: `0x140059aef`
- name: `?ExtNotificationThread@CNotificationMap@@CAKPEAX@Z`
- size: `527`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b58`
- `0x14004eedc`
- `0x1400598e0`
- `0x14005b3f8`
- `0x140065dbc`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140059966`
- `KERNEL32!GetLastError` at `0x140059a68`
- `KERNEL32!GetLastError` at `0x140059abf`
- `KERNEL32!GetLastError` at `0x140059966`
- `KERNEL32!GetLastError` at `0x140059a68`
- `KERNEL32!GetLastError` at `0x140059abf`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140059a5e`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140059a5e`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14005995c`
- `KERNEL32!GetQueuedCompletionStatus` at `0x14005995c`

## pseudocode

```c
__int64 __fastcall CNotificationMap::ExtNotificationThread(void *a1)
{
  int v1; // edx
  int v2; // r8d
  DWORD LastError; // eax
  LPVOID *v4; // rbx
  DWORD v5; // eax
  DWORD v6; // eax
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+78h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids);
  }
  while ( 1 )
  {
    while ( 1 )
    {
      NumberOfBytesTransferred = 0;
      CompletionKey = 0;
      Overlapped = 0;
      if ( GetQueuedCompletionStatus(
             *((HANDLE *)g_pNotificationMap + 1),
             &NumberOfBytesTransferred,
             &CompletionKey,
             &Overlapped,
             0xFFFFFFFF) )
      {
        break;
      }
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, LastError);
      }
      v4 = (LPVOID *)Overlapped;
      if ( Overlapped )
        goto LABEL_18;
    }
    if ( CompletionKey == 0xFFFFFFFF )
      break;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qlSql(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v1,
        v2,
        Overlapped[1].Internal,
        Overlapped->Internal,
        Overlapped->InternalHigh,
        (char)Overlapped->Pointer,
        (char)Overlapped->hEvent);
    }
    ((void (__fastcall *)(_QWORD, ULONG_PTR, PVOID, _QWORD))Overlapped[1].Internal)(
      LODWORD(Overlapped->Internal),
      Overlapped->InternalHigh,
      Overlapped->Pointer,
      LODWORD(Overlapped->hEvent));
    v4 = (LPVOID *)Overlapped;
LABEL_18:
    if ( v4 )
    {
      pMemFree(v4[1]);
      pMemFree(v4[2]);
      operator delete(v4);
    }
  }
  if ( !PostQueuedCompletionStatus(*((HANDLE *)g_pNotificationMap + 1), 0, 0xFFFFFFFF, 0) )
  {
    v5 = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, v5);
    }
  }
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1400598e0  push    rbx
0x1400598e2  push    rbp
0x1400598e3  push    r12
0x1400598e5  sub     rsp, 40h
0x1400598e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400598f0  lea     rbp, WPP_GLOBAL_Control
0x1400598f7  cmp     rcx, rbp
0x1400598fa  jz      short loc_14005991D
0x1400598fc  test    byte ptr [rcx+1Ch], 4
0x140059900  jz      short loc_14005991D
0x140059902  cmp     byte ptr [rcx+19h], 5
0x140059906  jb      short loc_14005991D
0x140059908  mov     rcx, [rcx+10h]
0x14005990c  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x140059913  mov     edx, 22h ; '"'
0x140059918  call    WPP_SF_
0x14005991d  mov     r12d, 0FFFFFFFFh
0x140059923  mov     rcx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x14005992a  lea     r9, [rsp+58h+Overlapped]; lpOverlapped
0x14005992f  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x140059937  lea     r8, [rsp+58h+CompletionKey]; lpCompletionKey
0x14005993c  mov     [rsp+58h+CompletionKey], 0
0x140059945  lea     rdx, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14005994a  mov     [rsp+58h+Overlapped], 0
0x140059953  mov     rcx, [rcx+8]; CompletionPort
0x140059957  mov     [rsp+58h+dwMilliseconds], r12d; dwMilliseconds
0x14005995c  call    cs:__imp_GetQueuedCompletionStatus
0x140059962  test    eax, eax
0x140059964  jnz     short loc_1400599AC
0x140059966  call    cs:__imp_GetLastError
0x14005996c  mov     rcx, cs:WPP_GLOBAL_Control
0x140059973  cmp     rcx, rbp
0x140059976  jz      short loc_14005999C
0x140059978  test    byte ptr [rcx+1Ch], 4
0x14005997c  jz      short loc_14005999C
0x14005997e  cmp     byte ptr [rcx+19h], 2
0x140059982  jb      short loc_14005999C
0x140059984  mov     rcx, [rcx+10h]
0x140059988  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x14005998f  mov     edx, 23h ; '#'
0x140059994  mov     r9d, eax
0x140059997  call    WPP_SF_d
0x14005999c  mov     rbx, [rsp+58h+Overlapped]
0x1400599a1  test    rbx, rbx
0x1400599a4  jz      loc_140059923
0x1400599aa  jmp     short loc_140059A23
0x1400599ac  cmp     [rsp+58h+CompletionKey], r12
0x1400599b1  jz      loc_140059A4B
0x1400599b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400599be  cmp     rcx, rbp
0x1400599c1  jz      short loc_140059A02
0x1400599c3  test    byte ptr [rcx+1Ch], 4
0x1400599c7  jz      short loc_140059A02
0x1400599c9  cmp     byte ptr [rcx+19h], 5
0x1400599cd  jb      short loc_140059A02
0x1400599cf  mov     r9, [rsp+58h+Overlapped]
0x1400599d4  mov     rcx, [rcx+10h]
0x1400599d8  mov     eax, [r9+18h]
0x1400599dc  mov     [rsp+58h+var_20], eax
0x1400599e0  mov     rax, [r9+10h]
0x1400599e4  mov     [rsp+58h+var_28], rax
0x1400599e9  mov     rax, [r9+8]
0x1400599ed  mov     [rsp+58h+var_30], rax
0x1400599f2  mov     eax, [r9]
0x1400599f5  mov     r9, [r9+20h]
0x1400599f9  mov     [rsp+58h+dwMilliseconds], eax
0x1400599fd  call    WPP_SF_qlSql
0x140059a02  mov     rcx, [rsp+58h+Overlapped]
0x140059a07  mov     rax, [rcx+20h]
0x140059a0b  mov     r9d, [rcx+18h]
0x140059a0f  mov     r8, [rcx+10h]
0x140059a13  mov     rdx, [rcx+8]
0x140059a17  mov     ecx, [rcx]
0x140059a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059a1e  mov     rbx, [rsp+58h+Overlapped]
0x140059a23  test    rbx, rbx
0x140059a26  jz      loc_140059923
0x140059a2c  mov     rcx, [rbx+8]; lpMem
0x140059a30  call    pMemFree
0x140059a35  mov     rcx, [rbx+10h]; lpMem
0x140059a39  call    pMemFree
0x140059a3e  mov     rcx, rbx; Block
0x140059a41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140059a46  jmp     loc_140059923
0x140059a4b  mov     rcx, cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA; CNotificationMap * g_pNotificationMap
0x140059a52  xor     r9d, r9d; lpOverlapped
0x140059a55  mov     r8, r12; dwCompletionKey
0x140059a58  xor     edx, edx; dwNumberOfBytesTransferred
0x140059a5a  mov     rcx, [rcx+8]; CompletionPort
0x140059a5e  call    cs:__imp_PostQueuedCompletionStatus
0x140059a64  test    eax, eax
0x140059a66  jnz     short loc_140059A9E
0x140059a68  call    cs:__imp_GetLastError
0x140059a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059a75  cmp     rcx, rbp
0x140059a78  jz      short loc_140059A9E
0x140059a7a  test    byte ptr [rcx+1Ch], 4
0x140059a7e  jz      short loc_140059A9E
0x140059a80  cmp     byte ptr [rcx+19h], 2
0x140059a84  jb      short loc_140059A9E
0x140059a86  mov     rcx, [rcx+10h]
0x140059a8a  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x140059a91  mov     edx, 24h ; '$'
0x140059a96  mov     r9d, eax
0x140059a99  call    WPP_SF_d
0x140059a9e  call    ?DecreaseServiceThreadsCount@@YAHXZ; DecreaseServiceThreadsCount(void)
0x140059aa3  test    eax, eax
0x140059aa5  jnz     short loc_140059AE4
0x140059aa7  mov     rax, cs:WPP_GLOBAL_Control
0x140059aae  cmp     rax, rbp
0x140059ab1  jz      short loc_140059AE4
0x140059ab3  test    byte ptr [rax+1Ch], 4
0x140059ab7  jz      short loc_140059AE4
0x140059ab9  cmp     byte ptr [rax+19h], 2
0x140059abd  jb      short loc_140059AE4
0x140059abf  call    cs:__imp_GetLastError
0x140059ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x140059acc  lea     r8, WPP_0a6138d6ffbf316398f3c44c06e0bba3_Traceguids
0x140059ad3  mov     edx, 25h ; '%'
0x140059ad8  mov     r9d, eax
0x140059adb  mov     rcx, [rcx+10h]
0x140059adf  call    WPP_SF_d
0x140059ae4  xor     eax, eax
0x140059ae6  add     rsp, 40h
0x140059aea  pop     r12
0x140059aec  pop     rbp
0x140059aed  pop     rbx
0x140059aee  retn
```
