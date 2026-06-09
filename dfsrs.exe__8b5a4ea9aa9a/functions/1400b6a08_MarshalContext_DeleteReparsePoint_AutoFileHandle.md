# MarshalContext::DeleteReparsePoint(AutoFileHandle &)

- ea: `0x1400b6a08`
- end: `0x1400b6c97`
- name: `?DeleteReparsePoint@MarshalContext@@IEAAPEAVFrsStatus@@AEAVAutoFileHandle@@@Z`
- size: `655`
- prototype: `struct FrsStatus *__fastcall(MarshalContext *__hidden this, struct AutoFileHandle *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1400b92bc`

## callees

- `0x14000cb00`
- `0x14000cdc0`
- `0x14002c548`
- `0x1400b6a08`
- `0x1401af7b0`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1400b6a62`
- `KERNEL32!DeviceIoControl` at `0x1400b6b93`
- `KERNEL32!DeviceIoControl` at `0x1400b6a62`
- `KERNEL32!DeviceIoControl` at `0x1400b6b93`
- `KERNEL32!GetLastError` at `0x1400b6a84`
- `KERNEL32!GetLastError` at `0x1400b6bb5`
- `KERNEL32!GetLastError` at `0x1400b6a84`
- `KERNEL32!GetLastError` at `0x1400b6bb5`
- `KERNEL32!GetCurrentThreadId` at `0x1400b6a76`
- `KERNEL32!GetCurrentThreadId` at `0x1400b6ba7`
- `KERNEL32!GetCurrentThreadId` at `0x1400b6c42`
- `KERNEL32!GetCurrentThreadId` at `0x1400b6a76`
- `KERNEL32!GetCurrentThreadId` at `0x1400b6ba7`
- `KERNEL32!GetCurrentThreadId` at `0x1400b6c42`

## string_xrefs

- `0x1400b6aed`: `MarshalContext::DeleteReparsePoint`
- `0x1400b6b13`: `MarshalContext::DeleteReparsePoint`
- `0x1400b6aa1`: `MarshalContext::DeleteReparsePoint`
- `0x1400b6bd2`: `MarshalContext::DeleteReparsePoint`
- `0x1400b6b52`: `DeleteReparsePoint. Tag:0x%x`
- `0x1400b6b02`: `FSCTL_GET_REPARSE_POINT failed. Error:%?`
- `0x1400b6c1b`: `FSCTL_DELETE_REPARSE_POINT failed. Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall MarshalContext::DeleteReparsePoint(MarshalContext *this, HANDLE *a2)
{
  __int64 v3; // rdi
  _WORD *lpOutBuffer; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v7; // rcx
  unsigned int *v8; // rbx
  const wchar_t *v9; // rdx
  int v10; // ecx
  DWORD v11; // ebx
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD v14; // eax
  __int64 v15; // rcx
  const wchar_t *v17; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+58h] [rbp-18h]
  int v19; // [rsp+5Ch] [rbp-14h]
  const wchar_t *v20; // [rsp+60h] [rbp-10h]
  MarshalContext *v21; // [rsp+B0h] [rbp+40h] BYREF
  DWORD BytesReturned; // [rsp+C0h] [rbp+50h] BYREF
  _WORD *v23; // [rsp+C8h] [rbp+58h] BYREF

  v21 = this;
  v3 = 0;
  BytesReturned = 0;
  v23 = 0;
  lpOutBuffer = operator_new(0x4000u);
  v23 = lpOutBuffer;
  if ( !DeviceIoControl(*a2, 0x900A8u, 0, 0, lpOutBuffer, 0x4000u, &BytesReturned, 0) )
  {
    CurrentThreadId = GetCurrentThreadId();
    LastError = GetLastError();
    v8 = (unsigned int *)FrsStatusList::PushNewError(
                           v7,
                           LastError,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\fs\\marshaller.cpp",
                           "MarshalContext::DeleteReparsePoint",
                           2966,
                           CurrentThreadId,
                           0);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v18 = 2967;
      v9 = L"FSCTL_GET_REPARSE_POINT failed. Error:%?";
LABEL_15:
      v17 = L"MarshalContext::DeleteReparsePoint";
      v19 = 2;
      v20 = L"MRSH";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(&v17, v9, v8);
      goto LABEL_16;
    }
    goto LABEL_16;
  }
  v10 = *(_DWORD *)lpOutBuffer;
  LODWORD(v21) = *(_DWORD *)lpOutBuffer;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
  {
    v17 = L"MarshalContext::DeleteReparsePoint";
    v18 = 2975;
    v19 = 4;
    v20 = L"MRSH";
    dbgobj::DbgPrint<unsigned short,unsigned int>(&v17, L"DeleteReparsePoint. Tag:0x%x", &v21);
    v10 = (int)v21;
  }
  *(_DWORD *)lpOutBuffer = v10;
  lpOutBuffer[2] = 0;
  if ( !DeviceIoControl(*a2, 0x900ACu, lpOutBuffer, 8u, 0, 0, &BytesReturned, 0) )
  {
    v11 = GetCurrentThreadId();
    v12 = GetLastError();
    v8 = (unsigned int *)FrsStatusList::PushNewError(
                           v13,
                           v12,
                           0,
                           1,
                           "base\\fs\\remotefs\\frs\\src\\fs\\marshaller.cpp",
                           "MarshalContext::DeleteReparsePoint",
                           2992,
                           v11,
                           0);
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v18 = 2993;
      v9 = L"FSCTL_DELETE_REPARSE_POINT failed. Error:%?";
      goto LABEL_15;
    }
LABEL_16:
    if ( v8 )
    {
      v14 = GetCurrentThreadId();
      v3 = FrsStatusList::PushNewError(
             v15,
             v8[1],
             v8[2],
             *v8,
             "base\\fs\\remotefs\\frs\\src\\fs\\marshaller.cpp",
             "MarshalContext::DeleteReparsePoint",
             2997,
             v14,
             v8);
    }
  }
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v23);
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x1400b6a08  mov     [rsp-38h+arg_0], rcx
0x1400b6a0d  push    rbp
0x1400b6a0e  push    rbx
0x1400b6a0f  push    rsi
0x1400b6a10  push    rdi
0x1400b6a11  push    r12
0x1400b6a13  push    r14
0x1400b6a15  push    r15
0x1400b6a17  mov     rbp, rsp
0x1400b6a1a  sub     rsp, 70h
0x1400b6a1e  mov     r15, rdx
0x1400b6a21  xor     edi, edi
0x1400b6a23  mov     [rbp+BytesReturned], edi
0x1400b6a26  mov     [rbp+arg_18], rdi
0x1400b6a2a  mov     esi, 4000h
0x1400b6a2f  mov     ecx, esi; unsigned __int64
0x1400b6a31  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1400b6a36  mov     rbx, rax
0x1400b6a39  mov     [rbp+arg_18], rax
0x1400b6a3d  mov     [rsp+70h+lpOverlapped], rdi; lpOverlapped
0x1400b6a42  lea     rax, [rbp+BytesReturned]
0x1400b6a46  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x1400b6a4b  mov     [rsp+70h+nOutBufferSize], esi; nOutBufferSize
0x1400b6a4f  mov     [rsp+70h+lpOutBuffer], rbx; lpOutBuffer
0x1400b6a54  xor     r9d, r9d; nInBufferSize
0x1400b6a57  xor     r8d, r8d; lpInBuffer
0x1400b6a5a  mov     edx, 900A8h; dwIoControlCode
0x1400b6a5f  mov     rcx, [r15]; hDevice
0x1400b6a62  call    cs:__imp_DeviceIoControl
0x1400b6a69  nop     dword ptr [rax+rax+00h]
0x1400b6a6e  test    eax, eax
0x1400b6a70  jnz     loc_1400B6B0E
0x1400b6a76  call    cs:__imp_GetCurrentThreadId
0x1400b6a7d  nop     dword ptr [rax+rax+00h]
0x1400b6a82  mov     ebx, eax
0x1400b6a84  call    cs:__imp_GetLastError
0x1400b6a8b  nop     dword ptr [rax+rax+00h]
0x1400b6a90  mov     [rsp+70h+var_30], rdi
0x1400b6a95  mov     dword ptr [rsp+70h+lpOverlapped], ebx
0x1400b6a99  mov     dword ptr [rsp+70h+lpBytesReturned], 0B96h
0x1400b6aa1  lea     r15, aMarshalcontext_8; "MarshalContext::DeleteReparsePoint"
0x1400b6aa8  mov     qword ptr [rsp+70h+nOutBufferSize], r15
0x1400b6aad  lea     r12, dwCreationFlags; "base\\fs\\remotefs\\frs\\src\\fs\\marsh"...
0x1400b6ab4  mov     [rsp+70h+lpOutBuffer], r12
0x1400b6ab9  lea     r9d, [rdi+1]
0x1400b6abd  xor     r8d, r8d
0x1400b6ac0  mov     edx, eax
0x1400b6ac2  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b6ac7  mov     rbx, rax
0x1400b6aca  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400b6ad1  test    rax, rax
0x1400b6ad4  jz      loc_1400B6C3D
0x1400b6ada  cmp     [rax+40h], edi
0x1400b6add  jz      loc_1400B6C3D
0x1400b6ae3  cmp     dword ptr [rax+38h], 2
0x1400b6ae7  jl      loc_1400B6C3D
0x1400b6aed  lea     rsi, aMarshalcontext_15; "MarshalContext::DeleteReparsePoint"
0x1400b6af4  mov     [rbp+var_18], 0B97h
0x1400b6afb  lea     r14, aMrsh; "MRSH"
0x1400b6b02  lea     rdx, aFsctlGetRepars; "FSCTL_GET_REPARSE_POINT failed. Error:%"...
0x1400b6b09  jmp     loc_1400B6C22
0x1400b6b0e  mov     ecx, [rbx]
0x1400b6b10  mov     dword ptr [rbp+arg_0], ecx
0x1400b6b13  lea     rsi, aMarshalcontext_15; "MarshalContext::DeleteReparsePoint"
0x1400b6b1a  lea     r14, aMrsh; "MRSH"
0x1400b6b21  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400b6b28  test    rax, rax
0x1400b6b2b  jz      short loc_1400B6B65
0x1400b6b2d  cmp     [rax+40h], edi
0x1400b6b30  jz      short loc_1400B6B65
0x1400b6b32  cmp     dword ptr [rax+38h], 4
0x1400b6b36  jl      short loc_1400B6B65
0x1400b6b38  mov     [rbp+var_20], rsi
0x1400b6b3c  mov     [rbp+var_18], 0B9Fh
0x1400b6b43  mov     [rbp+var_14], 4
0x1400b6b4a  mov     [rbp+var_10], r14
0x1400b6b4e  lea     r8, [rbp+arg_0]
0x1400b6b52  lea     rdx, aDeletereparsep; "DeleteReparsePoint. Tag:0x%x"
0x1400b6b59  lea     rcx, [rbp+var_20]
0x1400b6b5d  call    ??$DbgPrint@GI@dbgobj@@QEAA_KPEBGAEBI@Z; dbgobj::DbgPrint<ushort,uint>(ushort const *,uint const &)
0x1400b6b62  mov     ecx, dword ptr [rbp+arg_0]
0x1400b6b65  mov     [rbx], ecx
0x1400b6b67  mov     [rbx+4], di
0x1400b6b6b  mov     [rsp+70h+lpOverlapped], rdi; lpOverlapped
0x1400b6b70  lea     rax, [rbp+BytesReturned]
0x1400b6b74  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x1400b6b79  mov     [rsp+70h+nOutBufferSize], edi; nOutBufferSize
0x1400b6b7d  mov     [rsp+70h+lpOutBuffer], rdi; lpOutBuffer
0x1400b6b82  mov     r9d, 8; nInBufferSize
0x1400b6b88  mov     r8, rbx; lpInBuffer
0x1400b6b8b  mov     edx, 900ACh; dwIoControlCode
0x1400b6b90  mov     rcx, [r15]; hDevice
0x1400b6b93  call    cs:__imp_DeviceIoControl
0x1400b6b9a  nop     dword ptr [rax+rax+00h]
0x1400b6b9f  test    eax, eax
0x1400b6ba1  jnz     loc_1400B6C7B
0x1400b6ba7  call    cs:__imp_GetCurrentThreadId
0x1400b6bae  nop     dword ptr [rax+rax+00h]
0x1400b6bb3  mov     ebx, eax
0x1400b6bb5  call    cs:__imp_GetLastError
0x1400b6bbc  nop     dword ptr [rax+rax+00h]
0x1400b6bc1  mov     [rsp+70h+var_30], rdi
0x1400b6bc6  mov     dword ptr [rsp+70h+lpOverlapped], ebx
0x1400b6bca  mov     dword ptr [rsp+70h+lpBytesReturned], 0BB0h
0x1400b6bd2  lea     r15, aMarshalcontext_8; "MarshalContext::DeleteReparsePoint"
0x1400b6bd9  mov     qword ptr [rsp+70h+nOutBufferSize], r15
0x1400b6bde  lea     r12, dwCreationFlags; "base\\fs\\remotefs\\frs\\src\\fs\\marsh"...
0x1400b6be5  mov     [rsp+70h+lpOutBuffer], r12
0x1400b6bea  mov     r9d, 1
0x1400b6bf0  xor     r8d, r8d
0x1400b6bf3  mov     edx, eax
0x1400b6bf5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b6bfa  mov     rbx, rax
0x1400b6bfd  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400b6c04  test    rax, rax
0x1400b6c07  jz      short loc_1400B6C3D
0x1400b6c09  cmp     [rax+40h], edi
0x1400b6c0c  jz      short loc_1400B6C3D
0x1400b6c0e  cmp     dword ptr [rax+38h], 2
0x1400b6c12  jl      short loc_1400B6C3D
0x1400b6c14  mov     [rbp+var_18], 0BB1h
0x1400b6c1b  lea     rdx, aFsctlDeleteRep; "FSCTL_DELETE_REPARSE_POINT failed. Erro"...
0x1400b6c22  mov     [rbp+var_20], rsi
0x1400b6c26  mov     [rbp+var_14], 2
0x1400b6c2d  mov     [rbp+var_10], r14
0x1400b6c31  mov     r8, rbx
0x1400b6c34  lea     rcx, [rbp+var_20]
0x1400b6c38  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400b6c3d  test    rbx, rbx
0x1400b6c40  jz      short loc_1400B6C7B
0x1400b6c42  call    cs:__imp_GetCurrentThreadId
0x1400b6c49  nop     dword ptr [rax+rax+00h]
0x1400b6c4e  mov     [rsp+70h+var_30], rbx
0x1400b6c53  mov     dword ptr [rsp+70h+lpOverlapped], eax
0x1400b6c57  mov     dword ptr [rsp+70h+lpBytesReturned], 0BB5h
0x1400b6c5f  mov     qword ptr [rsp+70h+nOutBufferSize], r15
0x1400b6c64  mov     [rsp+70h+lpOutBuffer], r12
0x1400b6c69  mov     r9d, [rbx]
0x1400b6c6c  mov     r8d, [rbx+8]
0x1400b6c70  mov     edx, [rbx+4]
0x1400b6c73  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b6c78  mov     rdi, rax
0x1400b6c7b  lea     rcx, [rbp+arg_18]
0x1400b6c7f  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1400b6c84  mov     rax, rdi
0x1400b6c87  add     rsp, 70h
0x1400b6c8b  pop     r15
0x1400b6c8d  pop     r14
0x1400b6c8f  pop     r12
0x1400b6c91  pop     rdi
0x1400b6c92  pop     rsi
0x1400b6c93  pop     rbx
0x1400b6c94  pop     rbp
0x1400b6c95  retn
```
