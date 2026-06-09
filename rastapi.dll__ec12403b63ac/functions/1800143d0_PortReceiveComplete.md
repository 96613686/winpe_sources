# PortReceiveComplete

- ea: `0x1800143d0`
- end: `0x1800144ce`
- name: `PortReceiveComplete`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d92c`
- `0x180012340`
- `0x1800143d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800144ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800144ac`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800143fe`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800143fe`
- `api-ms-win-core-comm-l1-1-0!PurgeComm` at `0x18001442f`
- `api-ms-win-core-comm-l1-1-0!PurgeComm` at `0x18001442f`

## string_xrefs

- `0x180014415`: `PortReceiveComplete: GetOverlappedResult Failed.%s, %d`

## pseudocode

```c
__int64 __fastcall PortReceiveComplete(__int64 a1, DWORD *a2, __int64 a3, __int64 a4)
{
  DWORD LastError; // edi
  unsigned int v7; // r10d
  __int64 v8; // r9
  __int64 v9; // r11
  _DWORD *i; // r8
  int v11; // eax

  GetMutex(a1, a2, a3, a4);
  if ( GetOverlappedResult(*(HANDLE *)(a1 + 888), (LPOVERLAPPED)(a1 + 896), a2, 0) )
  {
    LastError = 0;
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 216) + 32LL) )
    {
      v7 = *(_DWORD *)(a1 + 1160);
      v8 = 0;
      v9 = *(_QWORD *)(a1 + 1152);
      for ( i = *(_DWORD **)(a1 + 1168); (unsigned int)v8 < v7; i[2] = (unsigned int)(v11 + 1) % i[3] )
      {
        if ( !*i )
          break;
        *(_BYTE *)(v8 + v9) = *((_BYTE *)i + (unsigned int)i[2] + 16);
        v8 = (unsigned int)(v8 + 1);
        v11 = i[2];
        --*i;
      }
      *a2 = v8;
      *(_QWORD *)(a1 + 1152) = 0;
      *(_DWORD *)(a1 + 1160) = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    RasTapiTrace("PortReceiveComplete: GetOverlappedResult Failed.%s, %d");
    PurgeComm(*(HANDLE *)(a1 + 888), 2u);
    *a2 = 0;
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return LastError;
}

```

## disassembly

```asm
0x1800143d0  mov     [rsp+arg_0], rbx
0x1800143d5  mov     [rsp+arg_8], rsi
0x1800143da  push    rdi
0x1800143db  sub     rsp, 20h
0x1800143df  mov     rsi, rdx
0x1800143e2  mov     rbx, rcx
0x1800143e5  call    GetMutex
0x1800143ea  mov     rcx, [rbx+378h]; hFile
0x1800143f1  lea     rdx, [rbx+380h]; lpOverlapped
0x1800143f8  xor     r9d, r9d; bWait
0x1800143fb  mov     r8, rsi; lpNumberOfBytesTransferred
0x1800143fe  call    cs:__imp_GetOverlappedResult
0x180014404  test    eax, eax
0x180014406  jnz     short loc_18001443D
0x180014408  call    cs:__imp_GetLastError
0x18001440e  mov     r8d, eax
0x180014411  lea     rdx, [rbx+18h]
0x180014415  lea     rcx, aPortreceivecom_0; "PortReceiveComplete: GetOverlappedResul"...
0x18001441c  mov     edi, eax
0x18001441e  call    RasTapiTrace
0x180014423  mov     rcx, [rbx+378h]; hFile
0x18001442a  mov     edx, 2; dwFlags
0x18001442f  call    cs:__imp_PurgeComm
0x180014435  mov     dword ptr [rsi], 0
0x18001443b  jmp     short loc_1800144A5
0x18001443d  mov     rax, [rbx+0D8h]
0x180014444  xor     edi, edi
0x180014446  cmp     [rax+20h], edi
0x180014449  jz      short loc_1800144A5
0x18001444b  mov     r10d, [rbx+488h]
0x180014452  xor     r9d, r9d
0x180014455  mov     r11, [rbx+480h]
0x18001445c  mov     r8, [rbx+490h]
0x180014463  test    r10d, r10d
0x180014466  jz      short loc_180014495
0x180014468  cmp     [r8], edi
0x18001446b  jz      short loc_180014495
0x18001446d  mov     eax, [r8+8]
0x180014471  xor     edx, edx
0x180014473  mov     al, [rax+r8+10h]
0x180014478  mov     [r9+r11], al
0x18001447c  inc     r9d
0x18001447f  mov     eax, [r8+8]
0x180014483  dec     dword ptr [r8]
0x180014486  inc     eax
0x180014488  div     dword ptr [r8+0Ch]
0x18001448c  mov     [r8+8], edx
0x180014490  cmp     r9d, r10d
0x180014493  jb      short loc_180014468
0x180014495  mov     [rsi], r9d
0x180014498  mov     [rbx+480h], rdi
0x18001449f  mov     [rbx+488h], edi
0x1800144a5  mov     rcx, cs:RasTapiMutex; hMutex
0x1800144ac  call    cs:__imp_ReleaseMutex
0x1800144b2  test    eax, eax
0x1800144b4  jnz     short loc_1800144BC
0x1800144b6  call    cs:__imp_GetLastError
0x1800144bc  mov     rbx, [rsp+28h+arg_0]
0x1800144c1  mov     eax, edi
0x1800144c3  mov     rsi, [rsp+28h+arg_8]
0x1800144c8  add     rsp, 20h
0x1800144cc  pop     rdi
0x1800144cd  retn
```
