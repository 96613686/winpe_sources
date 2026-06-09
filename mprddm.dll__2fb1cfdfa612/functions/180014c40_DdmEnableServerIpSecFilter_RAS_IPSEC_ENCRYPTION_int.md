# DdmEnableServerIpSecFilter(_RAS_IPSEC_ENCRYPTION,int)

- ea: `0x180014c40`
- end: `0x18001506c`
- name: `?DdmEnableServerIpSecFilter@@YAKW4_RAS_IPSEC_ENCRYPTION@@H@Z`
- size: `1068`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008540`
- `0x18000b3c0`
- `0x1800144d0`

## callees

- `0x180007b7c`
- `0x180014c40`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjectsEx` at `0x180014e90`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180014e90`
- `KERNEL32!HeapAlloc` at `0x180014ce5`
- `KERNEL32!HeapAlloc` at `0x180014ce5`
- `KERNEL32!CloseHandle` at `0x180014fb5`
- `KERNEL32!CloseHandle` at `0x180014fb5`
- `KERNEL32!GetLastError` at `0x180014d54`
- `KERNEL32!GetLastError` at `0x180014ea6`
- `KERNEL32!GetLastError` at `0x180014d54`
- `KERNEL32!GetLastError` at `0x180014ea6`
- `KERNEL32!CreateEventW` at `0x180014d45`
- `KERNEL32!CreateEventW` at `0x180014d45`
- `KERNEL32!HeapFree` at `0x180014fcb`
- `KERNEL32!HeapFree` at `0x180014fcb`
- `rtutils!RouterLogEventW` at `0x180014d24`
- `rtutils!RouterLogEventW` at `0x180014d24`

## string_xrefs

- `0x180014d72`: `DdmEnableServerIpSecFilter: CreateEvent failed with 0x%x`
- `0x180014f43`: `DdmEnableServerIpSecFilterEx completed async with return code 0x%x`

## pseudocode

```c
__int64 __fastcall DdmEnableServerIpSecFilter(int a1, int a2)
{
  __int64 v4; // r8
  _OWORD *v5; // rax
  __int64 v6; // rsi
  void *v7; // rdi
  unsigned int v8; // ebx
  HANDLE EventW; // rax
  __int64 v10; // r8
  DWORD LastError; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned int v14; // eax
  DWORD v15; // eax
  DWORD v16; // r14d
  DWORD v17; // eax
  __int64 *v18; // rdx
  void *v19; // rcx
  HANDLE Handles[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[16]; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v25 = 0;
  *(_OWORD *)Handles = 0;
  memset_0(v26, 0, sizeof(v26));
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v24 = 66;
    v23 = L"DdmEnableServerIpSecFilter Enter";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v4, 2, v22);
  }
  v5 = HeapAlloc(hHeap, 8u, 0x18u);
  v6 = -1;
  v7 = v5;
  if ( !v5 )
  {
    v8 = 8;
    if ( dword_1800C84E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, 8u);
    goto LABEL_39;
  }
  *v5 = 0;
  *((_QWORD *)v5 + 2) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v7 + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_36;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DdmEnableServerIpSecFilter: CreateEvent failed with 0x%x", LastError);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_36;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v26[2 * v13 - 4] );
    goto LABEL_33;
  }
  *(_DWORD *)v7 = a1;
  *((_DWORD *)v7 + 1) = a2;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v24 = 98;
    v23 = L"queue work item for DdmEnableServerIpSecFilterEx";
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v10, 2, v22);
  }
  v14 = (*(__int64 (__fastcall **)(DdmThreadPool *, void (__fastcall *)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *), void *, _QWORD))(*(_QWORD *)qword_1800C8678 + 16LL))(
          qword_1800C8678,
          DdmEnableServerIpSecFilterCallback,
          v7,
          0);
  v8 = v14;
  if ( v14 )
  {
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_36;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DdmEnableServerIpSecFilter: QueueWorkItem failed with 0x%x", v14);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_36;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v26[2 * v13 - 4] );
    goto LABEL_33;
  }
  Handles[0] = *((HANDLE *)v7 + 1);
  Handles[1] = *((HANDLE *)qword_1800C8678 + 13);
  v15 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 1);
  v16 = v15;
  if ( !v15 )
  {
    v8 = *((_DWORD *)v7 + 4);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_36;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DdmEnableServerIpSecFilterEx completed async with return code 0x%x", v8);
    if ( (byte_1800C8404 & 8) == 0 )
      goto LABEL_36;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v26[2 * v13 - 4] );
LABEL_33:
    v18 = RasDdmTraceError;
LABEL_34:
    v24 = (unsigned int)(2 * v13 + 2);
    v23 = (const wchar_t *)&v25;
    goto LABEL_35;
  }
  if ( v15 != 1 )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_36;
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"WaitForMultipleObjectsEx returned %d, GetLastError=%d", v16, v17);
    if ( (byte_1800C8404 & 0x10) == 0 )
      goto LABEL_36;
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)&v26[2 * v13 - 4] );
    v18 = RasDdmTraceInfo;
    goto LABEL_34;
  }
  v8 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v24 = 154;
    v23 = L"TP uninitialized -- DdmEnableServerIpSecFilterEx work may have been canceled";
    v18 = RasDdmTraceInfo;
LABEL_35:
    McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v18, v12, 2, v22);
  }
LABEL_36:
  v19 = (void *)*((_QWORD *)v7 + 1);
  if ( v19 )
  {
    CloseHandle(v19);
    *((_QWORD *)v7 + 1) = 0;
  }
  HeapFree(hHeap, 0, v7);
LABEL_39:
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(&v25, L"DdmEnableServerIpSecFilter Return 0x%x", v8);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      do
        ++v6;
      while ( *(_WORD *)&v26[2 * v6 - 4] );
      v24 = (unsigned int)(2 * v6 + 2);
      v23 = (const wchar_t *)&v25;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, &v25, 2, v22);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180014c40  push    rbp
0x180014c42  push    rbx
0x180014c43  push    rsi
0x180014c44  push    rdi
0x180014c45  push    r12
0x180014c47  push    r14
0x180014c49  push    r15
0x180014c4b  lea     rbp, [rsp-780h]
0x180014c53  sub     rsp, 880h
0x180014c5a  mov     rax, cs:__security_cookie
0x180014c61  xor     rax, rsp
0x180014c64  mov     [rbp+7B0h+var_40], rax
0x180014c6b  mov     ebx, edx
0x180014c6d  mov     r14d, ecx
0x180014c70  xorps   xmm0, xmm0
0x180014c73  lea     rcx, [rsp+8B0h+var_83C]; void *
0x180014c78  xor     r15d, r15d
0x180014c7b  xor     edx, edx; Val
0x180014c7d  mov     r8d, 7FCh; Size
0x180014c83  mov     [rsp+8B0h+var_840], r15d
0x180014c88  movups  xmmword ptr [rsp+8B0h+Handles], xmm0
0x180014c8d  call    memset_0
0x180014c92  test    cs:byte_1800C8404, 10h
0x180014c99  jz      short loc_180014CD1
0x180014c9b  lea     rax, aDdmenableserve_2; "DdmEnableServerIpSecFilter Enter"
0x180014ca2  mov     [rsp+8B0h+var_850], 42h ; 'B'
0x180014cab  mov     [rsp+8B0h+var_858], rax
0x180014cb0  lea     r9d, [r15+2]
0x180014cb4  lea     rax, [rsp+8B0h+var_868]
0x180014cb9  lea     rdx, RasDdmTraceInfo
0x180014cc0  mov     [rsp+8B0h+plpszSubStringArray], rax
0x180014cc5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014ccc  call    McGenEventWrite_EventWriteTransfer
0x180014cd1  mov     rcx, cs:hHeap; hHeap
0x180014cd8  mov     r8d, 18h; dwBytes
0x180014cde  lea     r12d, [r8-10h]
0x180014ce2  mov     edx, r12d; dwFlags
0x180014ce5  call    cs:__imp_HeapAlloc
0x180014ceb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180014cef  mov     rdi, rax
0x180014cf2  test    rax, rax
0x180014cf5  jnz     short loc_180014D2F
0x180014cf7  cmp     cs:dword_1800C84E4, r15d
0x180014cfe  mov     ebx, r12d
0x180014d01  jbe     loc_180014FD1
0x180014d07  mov     rcx, cs:hLogHandle; hLogHandle
0x180014d0e  lea     edx, [rax+1]; dwEventType
0x180014d11  mov     [rsp+8B0h+dwErrorCode], r12d; dwErrorCode
0x180014d16  xor     r9d, r9d; dwSubStringCount
0x180014d19  mov     r8d, 4E88h; dwMessageId
0x180014d1f  mov     [rsp+8B0h+plpszSubStringArray], r15; plpszSubStringArray
0x180014d24  call    cs:__imp_RouterLogEventW
0x180014d2a  jmp     loc_180014FD1
0x180014d2f  xorps   xmm0, xmm0
0x180014d32  xor     eax, eax
0x180014d34  movups  xmmword ptr [rdi], xmm0
0x180014d37  xor     r9d, r9d; lpName
0x180014d3a  mov     [rdi+10h], rax
0x180014d3e  xor     r8d, r8d; bInitialState
0x180014d41  xor     edx, edx; bManualReset
0x180014d43  xor     ecx, ecx; lpEventAttributes
0x180014d45  call    cs:__imp_CreateEventW
0x180014d4b  mov     [rdi+8], rax
0x180014d4f  test    rax, rax
0x180014d52  jnz     short loc_180014DA7
0x180014d54  call    cs:__imp_GetLastError
0x180014d5a  test    cs:byte_1800C8404, r12b
0x180014d61  mov     ebx, eax
0x180014d63  jz      loc_180014FAC
0x180014d69  mov     r8d, eax
0x180014d6c  mov     word ptr [rsp+8B0h+var_840], r15w
0x180014d72  lea     rdx, aDdmenableserve; "DdmEnableServerIpSecFilter: CreateEvent"...
0x180014d79  lea     rcx, [rsp+8B0h+var_840]
0x180014d7e  call    FormatRRASErrorString
0x180014d83  test    cs:byte_1800C8404, r12b
0x180014d8a  jz      loc_180014FAC
0x180014d90  lea     rcx, [rsp+8B0h+var_840]
0x180014d95  mov     rax, rsi
0x180014d98  inc     rax
0x180014d9b  cmp     [rcx+rax*2], r15w
0x180014da0  jnz     short loc_180014D98
0x180014da2  jmp     loc_180014F6F
0x180014da7  mov     [rdi], r14d
0x180014daa  mov     [rdi+4], ebx
0x180014dad  test    cs:byte_1800C8404, 10h
0x180014db4  jz      short loc_180014DEE
0x180014db6  lea     rax, aQueueWorkItemF; "queue work item for DdmEnableServerIpSe"...
0x180014dbd  mov     [rsp+8B0h+var_850], 62h ; 'b'
0x180014dc6  mov     [rsp+8B0h+var_858], rax
0x180014dcb  lea     rdx, RasDdmTraceInfo
0x180014dd2  lea     rax, [rsp+8B0h+var_868]
0x180014dd7  mov     r9d, 2
0x180014ddd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014de4  mov     [rsp+8B0h+plpszSubStringArray], rax
0x180014de9  call    McGenEventWrite_EventWriteTransfer
0x180014dee  mov     rcx, cs:qword_1800C8678
0x180014df5  lea     rdx, ?DdmEnableServerIpSecFilterCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; DdmEnableServerIpSecFilterCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x180014dfc  xor     r9d, r9d
0x180014dff  mov     r8, rdi
0x180014e02  mov     rax, [rcx]
0x180014e05  mov     rax, [rax+10h]
0x180014e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e0e  mov     ebx, eax
0x180014e10  test    eax, eax
0x180014e12  jz      short loc_180014E5F
0x180014e14  test    cs:byte_1800C8404, r12b
0x180014e1b  jz      loc_180014FAC
0x180014e21  mov     r8d, eax
0x180014e24  mov     word ptr [rsp+8B0h+var_840], r15w
0x180014e2a  lea     rdx, aDdmenableserve_5; "DdmEnableServerIpSecFilter: QueueWorkIt"...
0x180014e31  lea     rcx, [rsp+8B0h+var_840]
0x180014e36  call    FormatRRASErrorString
0x180014e3b  test    cs:byte_1800C8404, r12b
0x180014e42  jz      loc_180014FAC
0x180014e48  lea     rcx, [rsp+8B0h+var_840]
0x180014e4d  mov     rax, rsi
0x180014e50  inc     rax
0x180014e53  cmp     [rcx+rax*2], r15w
0x180014e58  jnz     short loc_180014E50
0x180014e5a  jmp     loc_180014F6F
0x180014e5f  mov     rax, [rdi+8]
0x180014e63  lea     rdx, [rsp+8B0h+Handles]; lpHandles
0x180014e68  mov     [rsp+8B0h+Handles], rax
0x180014e6d  xor     r8d, r8d; bWaitAll
0x180014e70  mov     rax, cs:qword_1800C8678
0x180014e77  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180014e7b  mov     dword ptr [rsp+8B0h+plpszSubStringArray], 1; bAlertable
0x180014e83  mov     rcx, [rax+68h]
0x180014e87  mov     [rsp+8B0h+Handles+8], rcx
0x180014e8c  lea     ecx, [r8+2]; nCount
0x180014e90  call    cs:__imp_WaitForMultipleObjectsEx
0x180014e96  mov     r14d, eax
0x180014e99  test    eax, eax
0x180014e9b  jz      loc_180014F2E
0x180014ea1  cmp     eax, 1
0x180014ea4  jz      short loc_180014F00
0x180014ea6  call    cs:__imp_GetLastError
0x180014eac  test    cs:byte_1800C8404, 10h
0x180014eb3  mov     ebx, eax
0x180014eb5  jz      loc_180014FAC
0x180014ebb  mov     r9d, eax
0x180014ebe  mov     word ptr [rsp+8B0h+var_840], r15w
0x180014ec4  mov     r8d, r14d
0x180014ec7  lea     rdx, aWaitformultipl; "WaitForMultipleObjectsEx returned %d, G"...
0x180014ece  lea     rcx, [rsp+8B0h+var_840]
0x180014ed3  call    FormatRRASErrorString
0x180014ed8  test    cs:byte_1800C8404, 10h
0x180014edf  jz      loc_180014FAC
0x180014ee5  lea     rcx, [rsp+8B0h+var_840]
0x180014eea  mov     rax, rsi
0x180014eed  inc     rax
0x180014ef0  cmp     [rcx+rax*2], r15w
0x180014ef5  jnz     short loc_180014EED
0x180014ef7  lea     rdx, RasDdmTraceInfo
0x180014efe  jmp     short loc_180014F76
0x180014f00  test    cs:byte_1800C8404, 10h
0x180014f07  mov     ebx, r15d
0x180014f0a  jz      loc_180014FAC
0x180014f10  lea     rax, aTpUninitialize; "TP uninitialized -- DdmEnableServerIpSe"...
0x180014f17  mov     [rsp+8B0h+var_850], 9Ah
0x180014f20  mov     [rsp+8B0h+var_858], rax
0x180014f25  lea     rdx, RasDdmTraceInfo
0x180014f2c  jmp     short loc_180014F90
0x180014f2e  test    cs:byte_1800C8404, r12b
0x180014f35  mov     ebx, [rdi+10h]
0x180014f38  jz      short loc_180014FAC
0x180014f3a  mov     r8d, ebx
0x180014f3d  mov     word ptr [rsp+8B0h+var_840], r15w
0x180014f43  lea     rdx, aDdmenableserve_1; "DdmEnableServerIpSecFilterEx completed "...
0x180014f4a  lea     rcx, [rsp+8B0h+var_840]
0x180014f4f  call    FormatRRASErrorString
0x180014f54  test    cs:byte_1800C8404, r12b
0x180014f5b  jz      short loc_180014FAC
0x180014f5d  lea     rcx, [rsp+8B0h+var_840]
0x180014f62  mov     rax, rsi
0x180014f65  inc     rax
0x180014f68  cmp     [rcx+rax*2], r15w
0x180014f6d  jnz     short loc_180014F65
0x180014f6f  lea     rdx, RasDdmTraceError
0x180014f76  lea     eax, ds:2[rax*2]
0x180014f7d  mov     dword ptr [rsp+8B0h+var_850+4], r15d
0x180014f82  lea     rcx, [rsp+8B0h+var_840]
0x180014f87  mov     dword ptr [rsp+8B0h+var_850], eax
0x180014f8b  mov     [rsp+8B0h+var_858], rcx
0x180014f90  lea     rax, [rsp+8B0h+var_868]
0x180014f95  mov     r9d, 2
0x180014f9b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014fa2  mov     [rsp+8B0h+plpszSubStringArray], rax
0x180014fa7  call    McGenEventWrite_EventWriteTransfer
0x180014fac  mov     rcx, [rdi+8]; hObject
0x180014fb0  test    rcx, rcx
0x180014fb3  jz      short loc_180014FBF
0x180014fb5  call    cs:__imp_CloseHandle
0x180014fbb  mov     [rdi+8], r15
0x180014fbf  mov     rcx, cs:hHeap; hHeap
0x180014fc6  mov     r8, rdi; lpMem
0x180014fc9  xor     edx, edx; dwFlags
0x180014fcb  call    cs:__imp_HeapFree
0x180014fd1  test    cs:byte_1800C8404, 10h
0x180014fd8  jz      short loc_180015049
0x180014fda  mov     r8d, ebx
0x180014fdd  mov     word ptr [rsp+8B0h+var_840], r15w
0x180014fe3  lea     rdx, aDdmenableserve_7; "DdmEnableServerIpSecFilter Return 0x%x"
0x180014fea  lea     rcx, [rsp+8B0h+var_840]
0x180014fef  call    FormatRRASErrorString
0x180014ff4  test    cs:byte_1800C8404, 10h
0x180014ffb  jz      short loc_180015049
0x180014ffd  lea     rax, [rsp+8B0h+var_840]
0x180015002  inc     rsi
0x180015005  cmp     [rax+rsi*2], r15w
0x18001500a  jnz     short loc_180015002
0x18001500c  lea     eax, ds:2[rsi*2]
0x180015013  mov     dword ptr [rsp+8B0h+var_850+4], r15d
0x180015018  mov     dword ptr [rsp+8B0h+var_850], eax
0x18001501c  lea     r8, [rsp+8B0h+var_840]
0x180015021  lea     rax, [rsp+8B0h+var_868]
0x180015026  mov     [rsp+8B0h+var_858], r8
0x18001502b  mov     r9d, 2
0x180015031  mov     [rsp+8B0h+plpszSubStringArray], rax
0x180015036  lea     rdx, RasDdmTraceInfo
0x18001503d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015044  call    McGenEventWrite_EventWriteTransfer
0x180015049  mov     eax, ebx
0x18001504b  mov     rcx, [rbp+7B0h+var_40]
0x180015052  xor     rcx, rsp; StackCookie
0x180015055  call    __security_check_cookie
0x18001505a  add     rsp, 880h
0x180015061  pop     r15
0x180015063  pop     r14
0x180015065  pop     r12
0x180015067  pop     rdi
0x180015068  pop     rsi
0x180015069  pop     rbx
0x18001506a  pop     rbp
0x18001506b  retn
```
