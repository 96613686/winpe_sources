# EtwpAdvanceToNewEvent(_TRACE_STREAM_CONTEXT *)

- ea: `0x180014b10`
- end: `0x180014e82`
- name: `?EtwpAdvanceToNewEvent@@YAKPEAU_TRACE_STREAM_CONTEXT@@@Z`
- size: `882`
- prototype: `__int64 __fastcall(struct _TRACE_STREAM_CONTEXT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001eb2`
- `0x1800060b4`
- `0x180010b38`
- `0x180010ba0`
- `0x180010d44`
- `0x1800110b0`
- `0x180012cc0`
- `0x180012e10`
- `0x180014b10`
- `0x18001526c`
- `0x180015328`
- `0x180015578`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180014db1`
- `ntdll!NtSetEvent` at `0x180014db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014d9b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014d8e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180014d8e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180014be5`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180014be5`

## pseudocode

```c
__int64 __fastcall EtwpAdvanceToNewEvent(struct _TRACE_STREAM_CONTEXT *a1)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  unsigned int *v4; // r8
  struct _WMI_BUFFER_HEADER *v5; // rbp
  DWORD v6; // r9d
  __int64 v7; // rax
  _DWORD *v8; // r8
  unsigned int v9; // r10d
  signed int v10; // edx
  __int64 v11; // rbx
  struct _WMI_BUFFER_HEADER *v12; // r15
  struct _WMI_BUFFER_HEADER *v13; // rdx
  struct _TRACELOG_CONTEXT *v14; // rcx
  _DWORD *v15; // rax
  int v16; // ebx
  unsigned int v17; // r15d
  unsigned int v18; // ebx
  struct _WMI_BUFFER_HEADER *FreeBuffer; // rax
  __int64 v20; // rdx
  __int64 result; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  void *v25; // rcx
  DWORD v26; // r12d
  BOOL v27; // r13d
  _DWORD *v28; // rcx
  __int64 v29; // r15
  struct _WMI_BUFFER_HEADER *v30; // rdx
  struct _TRACELOG_CONTEXT *v31; // rcx
  struct _TRACE_BUFFER_LIST_ENTRY *v32; // rdx
  struct _WMI_BUFFER_HEADER *CurrentBuffer; // rax
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+8h] BYREF

  v1 = *((_QWORD *)a1 + 8);
  v3 = *(_QWORD *)(v1 + 792);
  if ( v3 )
    *(_QWORD *)(v1 + 792) = *(_QWORD *)v3;
  v4 = (unsigned int *)(v3 + 12);
  v5 = (struct _WMI_BUFFER_HEADER *)*((_QWORD *)a1 + 9);
  if ( (*(_QWORD *)(v1 + 504) || *v4 == 72)
    && EtwpGetNextEvent(
         *((struct _WMI_BUFFER_HEADER **)a1 + 9),
         (struct _TRACELOG_CONTEXT *)v1,
         v4,
         (struct _ETW_EVENT_INFO *)(v3 + 40)) )
  {
    if ( (*(_DWORD *)(v1 + 32) & 0x10000000) != 0 )
      EtwpUpdateBufferEntryQpcDelta((struct _TRACELOG_CONTEXT *)v1, (struct _TRACE_BUFFER_LIST_ENTRY *)v3);
    EtwpInsertBuffer((struct _TRACELOG_CONTEXT *)v1, (struct _TRACE_BUFFER_LIST_ENTRY *)v3);
    goto LABEL_42;
  }
  if ( *(_QWORD *)(v1 + 480) )
  {
    *(_DWORD *)(v1 + 160) = *(_DWORD *)(v3 + 8);
    if ( !EtwpDoBufferCallback((struct _TRACELOG_CONTEXT *)v1, v5) )
      goto LABEL_11;
    return 1223;
  }
  if ( *(_QWORD *)(v1 + 528) )
  {
    v17 = EtwpDoBufferCallback2((struct _TRACELOG_CONTEXT *)v1, v5);
    if ( (int)EtwpRemovePlaybackEngineBufferReference((struct _TRACELOG_CONTEXT *)v1, v5) > 0 )
    {
      v18 = *(_DWORD *)(v3 + 8) % **(_DWORD **)(v1 + 816);
      FreeBuffer = EtwpGetFreeBuffer((struct _TRACELOG_CONTEXT *)v1);
      v20 = 2LL * v18;
      *(_QWORD *)(*(_QWORD *)(v1 + 816) + 8 * v20 + 16) = FreeBuffer;
      *(_DWORD *)(*(_QWORD *)(v1 + 816) + 8 * v20 + 8) = -1;
      *((_QWORD *)a1 + 9) = 0;
      v5 = *(struct _WMI_BUFFER_HEADER **)(*(_QWORD *)(v1 + 816) + 16LL * v18 + 16);
      if ( !v5 )
        return 1223;
    }
    if ( v17 )
      return 1223;
  }
LABEL_11:
  v6 = 0;
  NumberOfBytesTransferred = 0;
  if ( *(_DWORD *)(v1 + 584) != -1 )
  {
    if ( !GetOverlappedResult(*(HANDLE *)(v1 + 624), (LPOVERLAPPED)(v1 + 592), &NumberOfBytesTransferred, 0) )
      goto LABEL_42;
    v6 = NumberOfBytesTransferred;
  }
  v7 = *(int *)(v1 + 584);
  if ( (_DWORD)v7 != -1 )
  {
    v8 = *(_DWORD **)(v1 + 816);
    v9 = *(_DWORD *)(432 * v7 + *(_QWORD *)(v1 + 800) + 24);
    v10 = (unsigned int)v7 % *v8;
    v11 = 2LL * v10;
    v12 = *(struct _WMI_BUFFER_HEADER **)&v8[4 * v10 + 4];
    if ( v9 > v6 )
      memset_0((char *)v12 + v6, 0, v9 - v6);
    if ( !EtwpValidateBuffer((struct _TRACELOG_CONTEXT *)v1, v12) || EtwpDecompressBufferInPlace(v14, v13) )
      *(_DWORD *)(*(_QWORD *)(v1 + 816) + 8 * v11 + 8) = -1;
    *(_DWORD *)(v1 + 584) = -1;
  }
  v15 = *(_DWORD **)(v1 + 816);
  if ( (*(_DWORD *)(v1 + 232) & 0x400) != 0 )
    v16 = *(_DWORD *)(v3 + 8) - *v15;
  else
    v16 = *(_DWORD *)(v3 + 8) + *v15;
  if ( v16 >= 0 && (unsigned int)v16 < *(_DWORD *)(v1 + 772) )
  {
    v22 = *(_QWORD *)(v1 + 800);
    v23 = 432LL * v16;
    v24 = *(_QWORD *)(v23 + v22 + 16);
    *(_DWORD *)(v1 + 608) = v24;
    v25 = *(void **)(v1 + 624);
    *(_DWORD *)(v1 + 612) = HIDWORD(v24);
    v26 = *(_DWORD *)(v23 + v22 + 24);
    NumberOfBytesTransferred = 0;
    v27 = ReadFile(v25, v5, v26, &NumberOfBytesTransferred, (LPOVERLAPPED)(v1 + 592));
    if ( !v27 && GetLastError() != 997 )
    {
      NtSetEvent(*(HANDLE *)(v1 + 616), 0);
LABEL_40:
      *(_DWORD *)(v1 + 584) = -1;
      goto LABEL_42;
    }
    v28 = *(_DWORD **)(v1 + 816);
    v29 = (unsigned int)v16 % *v28;
    if ( !v27 )
    {
      *(_DWORD *)(v1 + 584) = v16;
      v28[4 * v29 + 2] = v16;
      goto LABEL_42;
    }
    if ( v26 > NumberOfBytesTransferred )
      memset_0((char *)v5 + NumberOfBytesTransferred, 0, v26 - NumberOfBytesTransferred);
    if ( !EtwpValidateBuffer((struct _TRACELOG_CONTEXT *)v1, v5) || EtwpDecompressBufferInPlace(v31, v30) )
    {
      *(_DWORD *)(*(_QWORD *)(v1 + 816) + 16 * v29 + 8) = -1;
      goto LABEL_40;
    }
  }
LABEL_42:
  v32 = *(struct _TRACE_BUFFER_LIST_ENTRY **)(v1 + 792);
  if ( !v32 )
  {
    result = 38;
LABEL_47:
    *((_BYTE *)a1 + 116) = 0;
    return result;
  }
  if ( v32 != (struct _TRACE_BUFFER_LIST_ENTRY *)v3 )
  {
    *((_QWORD *)a1 + 7) = (char *)v32 + 40;
    CurrentBuffer = EtwpGetCurrentBuffer((struct _TRACELOG_CONTEXT *)v1, v32);
    *((_QWORD *)a1 + 9) = CurrentBuffer;
    if ( !CurrentBuffer )
    {
      result = 32;
      goto LABEL_47;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014b10  push    rbx
0x180014b12  push    rbp
0x180014b13  push    rsi
0x180014b14  push    rdi
0x180014b15  push    r12
0x180014b17  push    r13
0x180014b19  push    r14
0x180014b1b  push    r15
0x180014b1d  sub     rsp, 38h
0x180014b21  mov     rdi, [rcx+40h]
0x180014b25  mov     r14, rcx
0x180014b28  mov     rsi, [rdi+318h]
0x180014b2f  test    rsi, rsi
0x180014b32  jz      short loc_180014B3E
0x180014b34  mov     rax, [rsi]
0x180014b37  mov     [rdi+318h], rax
0x180014b3e  cmp     qword ptr [rdi+1F8h], 0
0x180014b46  lea     r8, [rsi+0Ch]; unsigned int *
0x180014b4a  mov     rbp, [rcx+48h]
0x180014b4e  jnz     short loc_180014B56
0x180014b50  cmp     dword ptr [r8], 48h ; 'H'
0x180014b54  jnz     short loc_180014B8D
0x180014b56  lea     r9, [rsi+28h]; struct _ETW_EVENT_INFO *
0x180014b5a  mov     rdx, rdi; struct _TRACELOG_CONTEXT *
0x180014b5d  mov     rcx, rbp; struct _WMI_BUFFER_HEADER *
0x180014b60  call    ?EtwpGetNextEvent@@YAEPEAU_WMI_BUFFER_HEADER@@PEAU_TRACELOG_CONTEXT@@PEAKPEAU_ETW_EVENT_INFO@@@Z; EtwpGetNextEvent(_WMI_BUFFER_HEADER *,_TRACELOG_CONTEXT *,ulong *,_ETW_EVENT_INFO *)
0x180014b65  test    al, al
0x180014b67  jz      short loc_180014B8D
0x180014b69  test    dword ptr [rdi+20h], 10000000h
0x180014b70  jz      short loc_180014B7D
0x180014b72  mov     rdx, rsi; struct _TRACE_BUFFER_LIST_ENTRY *
0x180014b75  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014b78  call    ?EtwpUpdateBufferEntryQpcDelta@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_TRACE_BUFFER_LIST_ENTRY@@@Z; EtwpUpdateBufferEntryQpcDelta(_TRACELOG_CONTEXT *,_TRACE_BUFFER_LIST_ENTRY *)
0x180014b7d  mov     rdx, rsi; struct _TRACE_BUFFER_LIST_ENTRY *
0x180014b80  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014b83  call    ?EtwpInsertBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_TRACE_BUFFER_LIST_ENTRY@@@Z; EtwpInsertBuffer(_TRACELOG_CONTEXT *,_TRACE_BUFFER_LIST_ENTRY *)
0x180014b88  jmp     loc_180014E34
0x180014b8d  or      r12d, 0FFFFFFFFh
0x180014b91  cmp     qword ptr [rdi+1E0h], 0
0x180014b99  jz      loc_180014C95
0x180014b9f  mov     eax, [rsi+8]
0x180014ba2  mov     rdx, rbp; struct _WMI_BUFFER_HEADER *
0x180014ba5  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014ba8  mov     [rdi+0A0h], eax
0x180014bae  call    ?EtwpDoBufferCallback@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpDoBufferCallback(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180014bb3  test    eax, eax
0x180014bb5  jnz     loc_180014D17
0x180014bbb  xor     r9d, r9d; bWait
0x180014bbe  mov     [rsp+78h+NumberOfBytesTransferred], r9d
0x180014bc6  cmp     [rdi+248h], r12d
0x180014bcd  jz      short loc_180014BFB
0x180014bcf  mov     rcx, [rdi+270h]; hFile
0x180014bd6  lea     rdx, [rdi+250h]; lpOverlapped
0x180014bdd  lea     r8, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180014be5  call    cs:__imp_GetOverlappedResult
0x180014beb  test    eax, eax
0x180014bed  jz      loc_180014E34
0x180014bf3  mov     r9d, [rsp+78h+NumberOfBytesTransferred]
0x180014bfb  movsxd  rax, dword ptr [rdi+248h]
0x180014c02  cmp     eax, r12d
0x180014c05  jz      short loc_180014C74
0x180014c07  mov     r8, [rdi+330h]
0x180014c0e  mov     rcx, [rdi+320h]
0x180014c15  imul    rdx, rax, 1B0h
0x180014c1c  mov     r10d, [rdx+rcx+18h]
0x180014c21  xor     edx, edx
0x180014c23  div     dword ptr [r8]
0x180014c26  movsxd  rbx, edx
0x180014c29  add     rbx, rbx
0x180014c2c  mov     r15, [r8+rbx*8+10h]
0x180014c31  cmp     r10d, r9d
0x180014c34  jbe     short loc_180014C49
0x180014c36  sub     r10d, r9d
0x180014c39  mov     ecx, r9d
0x180014c3c  mov     r8d, r10d; Size
0x180014c3f  add     rcx, r15; void *
0x180014c42  xor     edx, edx; Val
0x180014c44  call    memset_0
0x180014c49  mov     rdx, r15; struct _WMI_BUFFER_HEADER *
0x180014c4c  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014c4f  call    ?EtwpValidateBuffer@@YAEPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpValidateBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180014c54  test    al, al
0x180014c56  jz      short loc_180014C61
0x180014c58  call    ?EtwpDecompressBufferInPlace@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpDecompressBufferInPlace(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180014c5d  test    eax, eax
0x180014c5f  jz      short loc_180014C6D
0x180014c61  mov     rax, [rdi+330h]
0x180014c68  mov     [rax+rbx*8+8], r12d
0x180014c6d  mov     [rdi+248h], r12d
0x180014c74  test    dword ptr [rdi+0E8h], 400h
0x180014c7e  mov     rax, [rdi+330h]
0x180014c85  jnz     loc_180014D21
0x180014c8b  mov     ebx, [rax]
0x180014c8d  add     ebx, [rsi+8]
0x180014c90  jmp     loc_180014D26
0x180014c95  cmp     qword ptr [rdi+210h], 0
0x180014c9d  jz      loc_180014BBB
0x180014ca3  mov     rdx, rbp; struct _WMI_BUFFER_HEADER *
0x180014ca6  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014ca9  call    ?EtwpDoBufferCallback2@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpDoBufferCallback2(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180014cae  mov     rdx, rbp; struct _WMI_BUFFER_HEADER *
0x180014cb1  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014cb4  mov     r15d, eax
0x180014cb7  call    ?EtwpRemovePlaybackEngineBufferReference@@YAJPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpRemovePlaybackEngineBufferReference(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180014cbc  test    eax, eax
0x180014cbe  jle     short loc_180014D0E
0x180014cc0  mov     rcx, [rdi+330h]
0x180014cc7  xor     edx, edx
0x180014cc9  mov     eax, [rsi+8]
0x180014ccc  div     dword ptr [rcx]
0x180014cce  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014cd1  mov     ebx, edx
0x180014cd3  call    ?EtwpGetFreeBuffer@@YAPEAU_WMI_BUFFER_HEADER@@PEAU_TRACELOG_CONTEXT@@@Z; EtwpGetFreeBuffer(_TRACELOG_CONTEXT *)
0x180014cd8  mov     rcx, [rdi+330h]
0x180014cdf  mov     edx, ebx
0x180014ce1  add     rdx, rdx
0x180014ce4  mov     [rcx+rdx*8+10h], rax
0x180014ce9  mov     rax, [rdi+330h]
0x180014cf0  mov     [rax+rdx*8+8], r12d
0x180014cf5  mov     qword ptr [r14+48h], 0
0x180014cfd  mov     rax, [rdi+330h]
0x180014d04  mov     rbp, [rax+rdx*8+10h]
0x180014d09  test    rbp, rbp
0x180014d0c  jz      short loc_180014D17
0x180014d0e  test    r15d, r15d
0x180014d11  jz      loc_180014BBB
0x180014d17  mov     eax, 4C7h
0x180014d1c  jmp     loc_180014E71
0x180014d21  mov     ebx, [rsi+8]
0x180014d24  sub     ebx, [rax]
0x180014d26  test    ebx, ebx
0x180014d28  js      loc_180014E34
0x180014d2e  cmp     ebx, [rdi+304h]
0x180014d34  jnb     loc_180014E34
0x180014d3a  mov     rdx, [rdi+320h]
0x180014d41  lea     rcx, [rdi+250h]
0x180014d48  movsxd  rax, ebx
0x180014d4b  lea     r9, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesRead
0x180014d53  imul    r8, rax, 1B0h
0x180014d5a  mov     [rsp+78h+lpOverlapped], rcx; lpOverlapped
0x180014d5f  mov     rax, [r8+rdx+10h]
0x180014d64  mov     [rcx+10h], eax
0x180014d67  mov     rcx, [rdi+270h]; hFile
0x180014d6e  shr     rax, 20h
0x180014d72  mov     [rdi+264h], eax
0x180014d78  mov     r12d, [r8+rdx+18h]
0x180014d7d  mov     r8d, r12d; nNumberOfBytesToRead
0x180014d80  mov     rdx, rbp; lpBuffer
0x180014d83  mov     [rsp+78h+NumberOfBytesTransferred], 0
0x180014d8e  call    cs:__imp_ReadFile
0x180014d94  mov     r13d, eax
0x180014d97  test    eax, eax
0x180014d99  jnz     short loc_180014DB9
0x180014d9b  call    cs:__imp_GetLastError
0x180014da1  cmp     eax, 3E5h
0x180014da6  jz      short loc_180014DB9
0x180014da8  mov     rcx, [rdi+268h]; EventHandle
0x180014daf  xor     edx, edx; PreviousState
0x180014db1  call    cs:__imp_NtSetEvent
0x180014db7  jmp     short loc_180014E18
0x180014db9  mov     rcx, [rdi+330h]
0x180014dc0  xor     edx, edx
0x180014dc2  mov     eax, ebx
0x180014dc4  div     dword ptr [rcx]
0x180014dc6  mov     r15d, edx
0x180014dc9  test    r13d, r13d
0x180014dcc  jz      short loc_180014E24
0x180014dce  mov     eax, [rsp+78h+NumberOfBytesTransferred]
0x180014dd5  cmp     r12d, eax
0x180014dd8  jbe     short loc_180014DEB
0x180014dda  sub     r12d, eax
0x180014ddd  lea     rcx, [rax+rbp]; void *
0x180014de1  mov     r8d, r12d; Size
0x180014de4  xor     edx, edx; Val
0x180014de6  call    memset_0
0x180014deb  mov     rdx, rbp; struct _WMI_BUFFER_HEADER *
0x180014dee  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014df1  call    ?EtwpValidateBuffer@@YAEPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpValidateBuffer(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180014df6  test    al, al
0x180014df8  jz      short loc_180014E03
0x180014dfa  call    ?EtwpDecompressBufferInPlace@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z; EtwpDecompressBufferInPlace(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)
0x180014dff  test    eax, eax
0x180014e01  jz      short loc_180014E34
0x180014e03  mov     rax, [rdi+330h]
0x180014e0a  mov     rcx, r15
0x180014e0d  add     rcx, rcx
0x180014e10  mov     dword ptr [rax+rcx*8+8], 0FFFFFFFFh
0x180014e18  mov     dword ptr [rdi+248h], 0FFFFFFFFh
0x180014e22  jmp     short loc_180014E34
0x180014e24  mov     rax, r15
0x180014e27  mov     [rdi+248h], ebx
0x180014e2d  add     rax, rax
0x180014e30  mov     [rcx+rax*8+8], ebx
0x180014e34  mov     rdx, [rdi+318h]; struct _TRACE_BUFFER_LIST_ENTRY *
0x180014e3b  test    rdx, rdx
0x180014e3e  jnz     short loc_180014E45
0x180014e40  lea     eax, [rdx+26h]
0x180014e43  jmp     short loc_180014E68
0x180014e45  cmp     rdx, rsi
0x180014e48  jz      short loc_180014E6F
0x180014e4a  lea     rax, [rdx+28h]
0x180014e4e  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180014e51  mov     [r14+38h], rax
0x180014e55  call    ?EtwpGetCurrentBuffer@@YAPEAU_WMI_BUFFER_HEADER@@PEAU_TRACELOG_CONTEXT@@PEAU_TRACE_BUFFER_LIST_ENTRY@@@Z; EtwpGetCurrentBuffer(_TRACELOG_CONTEXT *,_TRACE_BUFFER_LIST_ENTRY *)
0x180014e5a  mov     [r14+48h], rax
0x180014e5e  test    rax, rax
0x180014e61  jnz     short loc_180014E6F
0x180014e63  mov     eax, 20h ; ' '
0x180014e68  mov     byte ptr [r14+74h], 0
0x180014e6d  jmp     short loc_180014E71
0x180014e6f  xor     eax, eax
0x180014e71  add     rsp, 38h
0x180014e75  pop     r15
0x180014e77  pop     r14
0x180014e79  pop     r13
0x180014e7b  pop     r12
0x180014e7d  pop     rdi
0x180014e7e  pop     rsi
0x180014e7f  pop     rbp
0x180014e80  pop     rbx
0x180014e81  retn
```
