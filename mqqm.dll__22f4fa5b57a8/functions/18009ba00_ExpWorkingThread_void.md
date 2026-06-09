# ExpWorkingThread(void *)

- ea: `0x18009ba00`
- end: `0x18009baed`
- name: `?ExpWorkingThread@@YAKPEAX@Z`
- size: `237`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000f35c`
- `0x18009ba00`
- `0x18009bcdc`

## import_xrefs

- `KERNEL32!GetQueuedCompletionStatus` at `0x18009ba45`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18009ba45`
- `KERNEL32!GetLastError` at `0x18009ba6f`
- `KERNEL32!GetLastError` at `0x18009bab3`
- `KERNEL32!GetLastError` at `0x18009ba6f`
- `KERNEL32!GetLastError` at `0x18009bab3`
- `KERNEL32!Sleep` at `0x18009ba96`
- `KERNEL32!Sleep` at `0x18009ba96`

## pseudocode

```c
void __fastcall __noreturn ExpWorkingThread(PVOID Parameter)
{
  EXOVERLAPPED *v1; // rcx
  DWORD LastError; // eax
  DWORD v3; // eax
  const exception *v4; // [rsp+30h] [rbp-18h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+58h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+68h] [rbp+20h] BYREF

  while ( 1 )
  {
    try
    {
      while ( 1 )
      {
        CompletionKey = 0;
        Overlapped = 0;
        NumberOfBytesTransferred = 0;
        if ( GetQueuedCompletionStatus(
               CompletionPort,
               &NumberOfBytesTransferred,
               &CompletionKey,
               &Overlapped,
               0xFFFFFFFF) )
        {
          goto LABEL_11;
        }
        v1 = (EXOVERLAPPED *)Overlapped;
        if ( Overlapped )
          break;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5044ce7d522c39f28b6ef29e222952de_Traceguids, LastError);
        }
        Sleep(0);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v3 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_5044ce7d522c39f28b6ef29e222952de_Traceguids, v3);
LABEL_11:
        v1 = (EXOVERLAPPED *)Overlapped;
      }
      EXOVERLAPPED::CompleteRequest(v1);
    }
    catch ( const exception *v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        (*(void (__fastcall **)(const exception *))(*(_QWORD *)v4 + 8LL))(v4);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2));
      }
      continue;
    }
  }
}

```

## disassembly

```asm
0x18009ba00  push    rbx
0x18009ba02  sub     rsp, 40h
0x18009ba06  lea     rbx, WPP_GLOBAL_Control
0x18009ba0d  mov     [rsp+48h+CompletionKey], 0
0x18009ba16  mov     [rsp+48h+Overlapped], 0
0x18009ba1f  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x18009ba27  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18009ba2f  lea     r9, [rsp+48h+Overlapped]; lpOverlapped
0x18009ba34  lea     r8, [rsp+48h+CompletionKey]; lpCompletionKey
0x18009ba39  lea     rdx, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18009ba3e  mov     rcx, cs:CompletionPort; CompletionPort
0x18009ba45  call    cs:__imp_GetQueuedCompletionStatus
0x18009ba4b  test    eax, eax
0x18009ba4d  jnz     loc_18009BAD8
0x18009ba53  mov     rcx, [rsp+48h+Overlapped]
0x18009ba58  test    rcx, rcx
0x18009ba5b  jnz     short loc_18009BAA1
0x18009ba5d  mov     rax, cs:WPP_GLOBAL_Control
0x18009ba64  cmp     rax, rbx
0x18009ba67  jz      short loc_18009BA94
0x18009ba69  test    byte ptr [rax+1Ch], 1
0x18009ba6d  jz      short loc_18009BA94
0x18009ba6f  call    cs:__imp_GetLastError
0x18009ba75  mov     edx, 0Dh
0x18009ba7a  mov     r9d, eax
0x18009ba7d  lea     r8, WPP_5044ce7d522c39f28b6ef29e222952de_Traceguids
0x18009ba84  mov     rcx, cs:WPP_GLOBAL_Control
0x18009ba8b  mov     rcx, [rcx+10h]
0x18009ba8f  call    WPP_SF_d
0x18009ba94  xor     ecx, ecx; dwMilliseconds
0x18009ba96  call    cs:__imp_Sleep
0x18009ba9c  jmp     loc_18009BA0D
0x18009baa1  mov     rax, cs:WPP_GLOBAL_Control
0x18009baa8  cmp     rax, rbx
0x18009baab  jz      short loc_18009BADD
0x18009baad  test    byte ptr [rax+1Ch], 1
0x18009bab1  jz      short loc_18009BADD
0x18009bab3  call    cs:__imp_GetLastError
0x18009bab9  mov     edx, 0Eh
0x18009babe  mov     r9d, eax
0x18009bac1  lea     r8, WPP_5044ce7d522c39f28b6ef29e222952de_Traceguids
0x18009bac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009bacf  mov     rcx, [rcx+10h]
0x18009bad3  call    WPP_SF_d
0x18009bad8  mov     rcx, [rsp+48h+Overlapped]; this
0x18009badd  call    ?CompleteRequest@EXOVERLAPPED@@QEAAXXZ; EXOVERLAPPED::CompleteRequest(void)
0x18009bae2  nop
0x18009bae3  jmp     loc_18009BA0D
0x18009bae8  jmp     loc_18009BA06
```
