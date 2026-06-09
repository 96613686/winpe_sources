# UnmarshalSharedMemory(SDfMarshalPacket const *,ulong,ulong,CPerContext *)

- ea: `0x18004cdec`
- end: `0x18004cf1f`
- name: `?UnmarshalSharedMemory@@YAJPEBUSDfMarshalPacket@@KKPEAVCPerContext@@@Z`
- size: `307`
- prototype: `int(const struct SDfMarshalPacket *, unsigned int, unsigned int, struct CPerContext *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18003b588`
- `0x1800405dc`

## callees

- `0x180018680`
- `0x18001f5cc`
- `0x18002db70`
- `0x18002dfc0`
- `0x180035320`
- `0x18003686c`
- `0x18004ba24`
- `0x18004cdec`
- `0x18005d728`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ceaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ceaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ce2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ce2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ce98`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ce98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ce7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ce7c`

## pseudocode

```c
__int64 __fastcall UnmarshalSharedMemory(const struct SDfMarshalPacket *a1, __int64 a2, int a3, struct CPerContext *a4)
{
  unsigned int v4; // r15d
  unsigned int v6; // ebp
  int v9; // ebx
  CProcessSecret *v10; // rcx
  struct CPerContext **v11; // rdx
  struct CSmAllocator *TlsSmAllocator; // rsi
  HANDLE CurrentThread; // rax
  CSmAllocator *v14; // rcx
  struct CPerContext **v15; // rdx
  struct _GUID v17; // [rsp+30h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+8h] BYREF

  v4 = *((_DWORD *)a1 + 18);
  v6 = *((_DWORD *)a1 + 19);
  if ( IsSharedMemoryModeDisabledForCurrentProcess() )
  {
    return (unsigned int)-2147287039;
  }
  else if ( !a3 || v6 == a3 )
  {
    if ( GetCurrentProcessId() == v6
      && (v17 = (struct _GUID)*((_OWORD *)a1 + 5), CProcessSecret::VerifyMatchingSecret(v10, &v17) >= 0) )
    {
      CPerContext::SetThreadAllocatorState(*((CPerContext **)a1 + 12), v11);
      return 0;
    }
    else
    {
      v9 = 0;
      TlsSmAllocator = GetTlsSmAllocator();
      if ( *((_DWORD *)TlsSmAllocator + 9) == v4 )
        goto LABEL_14;
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        CloseHandle(TokenHandle);
        return (unsigned int)-2147287035;
      }
      CSmAllocator::SetState(TlsSmAllocator, 0, 0, 0, 0, 0);
      v9 = CSmAllocator::Init(v14, *((void **)a1 + 13), v6, v4, 1);
      if ( v9 >= 0 )
      {
        v9 = CSmAllocator::Sync(TlsSmAllocator);
        if ( v9 >= 0 )
        {
LABEL_14:
          CPerContext::GetThreadAllocatorState(a4);
          CPerContext::SetThreadAllocatorState(a4, v15);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024891;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004cdec  push    rbx
0x18004cdee  push    rbp
0x18004cdef  push    rsi
0x18004cdf0  push    rdi
0x18004cdf1  push    r14
0x18004cdf3  push    r15
0x18004cdf5  sub     rsp, 48h
0x18004cdf9  mov     r15d, [rcx+48h]
0x18004cdfd  mov     r14, r9
0x18004ce00  mov     ebp, [rcx+4Ch]
0x18004ce03  mov     ebx, r8d
0x18004ce06  mov     rdi, rcx
0x18004ce09  call    ?IsSharedMemoryModeDisabledForCurrentProcess@@YA_NXZ; IsSharedMemoryModeDisabledForCurrentProcess(void)
0x18004ce0e  test    al, al
0x18004ce10  jz      short loc_18004CE1C
0x18004ce12  mov     ebx, 80030001h
0x18004ce17  jmp     loc_18004CF10
0x18004ce1c  test    ebx, ebx
0x18004ce1e  jz      short loc_18004CE2E
0x18004ce20  cmp     ebp, ebx
0x18004ce22  jz      short loc_18004CE2E
0x18004ce24  mov     ebx, 80070005h
0x18004ce29  jmp     loc_18004CF10
0x18004ce2e  call    cs:__imp_GetCurrentProcessId
0x18004ce34  cmp     eax, ebp
0x18004ce36  jnz     short loc_18004CE60
0x18004ce38  movups  xmm0, xmmword ptr [rdi+50h]
0x18004ce3c  lea     rdx, [rsp+78h+var_48]; struct _GUID
0x18004ce41  movdqu  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x18004ce47  call    ?VerifyMatchingSecret@CProcessSecret@@QEAAJU_GUID@@@Z; CProcessSecret::VerifyMatchingSecret(_GUID)
0x18004ce4c  test    eax, eax
0x18004ce4e  js      short loc_18004CE60
0x18004ce50  mov     rcx, [rdi+60h]; this
0x18004ce54  call    ?SetThreadAllocatorState@CPerContext@@QEAAPEAVCSmAllocator@@PEAPEAV1@@Z; CPerContext::SetThreadAllocatorState(CPerContext * *)
0x18004ce59  xor     ebx, ebx
0x18004ce5b  jmp     loc_18004CF10
0x18004ce60  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18004ce65  xor     ebx, ebx
0x18004ce67  mov     rsi, rax
0x18004ce6a  cmp     [rax+24h], r15d
0x18004ce6e  jz      loc_18004CF00
0x18004ce74  mov     [rsp+78h+TokenHandle], rbx
0x18004ce7c  call    cs:__imp_GetCurrentThread
0x18004ce82  mov     ebx, 1
0x18004ce87  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x18004ce8f  mov     rcx, rax; ThreadHandle
0x18004ce92  mov     r8d, ebx; OpenAsSelf
0x18004ce95  lea     edx, [rbx+7]; DesiredAccess
0x18004ce98  call    cs:__imp_OpenThreadToken
0x18004ce9e  test    eax, eax
0x18004cea0  jz      short loc_18004CEB7
0x18004cea2  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x18004ceaa  call    cs:__imp_CloseHandle
0x18004ceb0  mov     ebx, 80030005h
0x18004ceb5  jmp     short loc_18004CF10
0x18004ceb7  mov     [rsp+78h+var_50], 0; struct CPerContext *
0x18004cec0  xor     r9d, r9d; unsigned int
0x18004cec3  xor     r8d, r8d; unsigned __int8 *
0x18004cec6  mov     [rsp+78h+var_58], 0; struct CPerContext **
0x18004cecf  xor     edx, edx; struct CSharedMemoryBlock *
0x18004ced1  mov     rcx, rsi; this
0x18004ced4  call    ?SetState@CSmAllocator@@QEAAXPEAVCSharedMemoryBlock@@PEAEKPEAPEAVCPerContext@@PEAV3@@Z; CSmAllocator::SetState(CSharedMemoryBlock *,uchar *,ulong,CPerContext * *,CPerContext *)
0x18004ced9  mov     rdx, [rdi+68h]; void *
0x18004cedd  mov     r9d, r15d; unsigned int
0x18004cee0  mov     r8d, ebp; unsigned int
0x18004cee3  mov     dword ptr [rsp+78h+var_58], ebx; int
0x18004cee7  call    ?Init@CSmAllocator@@QEAAJPEAXKKH@Z; CSmAllocator::Init(void *,ulong,ulong,int)
0x18004ceec  mov     ebx, eax
0x18004ceee  test    eax, eax
0x18004cef0  js      short loc_18004CF10
0x18004cef2  mov     rcx, rsi; this
0x18004cef5  call    ?Sync@CSmAllocator@@QEAAJXZ; CSmAllocator::Sync(void)
0x18004cefa  mov     ebx, eax
0x18004cefc  test    eax, eax
0x18004cefe  js      short loc_18004CF10
0x18004cf00  mov     rcx, r14; this
0x18004cf03  call    ?GetThreadAllocatorState@CPerContext@@QEAAJXZ; CPerContext::GetThreadAllocatorState(void)
0x18004cf08  mov     rcx, r14; this
0x18004cf0b  call    ?SetThreadAllocatorState@CPerContext@@QEAAPEAVCSmAllocator@@PEAPEAV1@@Z; CPerContext::SetThreadAllocatorState(CPerContext * *)
0x18004cf10  mov     eax, ebx
0x18004cf12  add     rsp, 48h
0x18004cf16  pop     r15
0x18004cf18  pop     r14
0x18004cf1a  pop     rdi
0x18004cf1b  pop     rsi
0x18004cf1c  pop     rbp
0x18004cf1d  pop     rbx
0x18004cf1e  retn
```
