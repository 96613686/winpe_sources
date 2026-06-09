# CreateDropWrapper(IDataObject *,IDataObject * *)

- ea: `0x1800ce0e8`
- end: `0x1800ce1b4`
- name: `?CreateDropWrapper@@YAJPEAUIDataObject@@PEAPEAU1@@Z`
- size: `204`
- prototype: `HRESULT __fastcall(IDataObject *pDataObject, IDataObject **ppWrappedDataObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026480`

## callees

- `0x18008c268`
- `0x18008f834`
- `0x1800ce0e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ce124`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ce124`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ce10d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ce10d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce195`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800ce141`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800ce141`

## pseudocode

```c
__int64 __fastcall CreateDropWrapper(IDataObject *pDataObject, IDataObject **ppWrappedDataObject)
{
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  void *hPrimaryToken; // [rsp+48h] [rbp+10h] BYREF
  void *hImpersonationToken; // [rsp+50h] [rbp+18h] BYREF

  *ppWrappedDataObject = 0;
  Error = 0;
  hPrimaryToken = 0;
  hImpersonationToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, &hPrimaryToken)
    || !DuplicateToken(hPrimaryToken, SecurityImpersonation, &hImpersonationToken) )
  {
    Error = ResultFromKnownLastError();
  }
  if ( hPrimaryToken )
    CloseHandle(hPrimaryToken);
  if ( Error >= 0 )
    Error = CBrokeredClipDataObject::Create(pDataObject, 0, 0, &hImpersonationToken, ppWrappedDataObject);
  if ( hImpersonationToken )
    CloseHandle(hImpersonationToken);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800ce0e8  mov     rax, rsp
0x1800ce0eb  mov     [rax+8], rbx
0x1800ce0ef  mov     [rax+20h], rsi
0x1800ce0f3  push    rdi
0x1800ce0f4  sub     rsp, 30h
0x1800ce0f8  and     qword ptr [ppWrappedDataObject], 0
0x1800ce0fc  xor     ebx, ebx
0x1800ce0fe  and     [rax+10h], rbx
0x1800ce102  mov     rdi, ppWrappedDataObject
0x1800ce105  and     qword ptr [rax+18h], 0
0x1800ce10a  mov     rsi, pDataObject
0x1800ce10d  call    cs:__imp_GetCurrentProcess
0x1800ce114  nop     dword ptr [rax+rax+00h]
0x1800ce119  mov     pDataObject, rax; ProcessHandle
0x1800ce11c  lea     r8, [rsp+38h+hPrimaryToken]; TokenHandle
0x1800ce121  lea     edx, [rbx+0Eh]; DesiredAccess
0x1800ce124  call    cs:__imp_OpenProcessToken
0x1800ce12b  nop     dword ptr [rax+rax+00h]
0x1800ce130  test    eax, eax
0x1800ce132  jz      short loc_1800CE151
0x1800ce134  mov     pDataObject, [rsp+38h+hPrimaryToken]; ExistingTokenHandle
0x1800ce139  lea     r8, [rsp+38h+hImpersonationToken]; DuplicateTokenHandle
0x1800ce13e  lea     edx, [rbx+2]; ImpersonationLevel
0x1800ce141  call    cs:__imp_DuplicateToken
0x1800ce148  nop     dword ptr [rax+rax+00h]
0x1800ce14d  test    eax, eax
0x1800ce14f  jnz     short loc_1800CE158
0x1800ce151  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800ce156  mov     ebx, eax
0x1800ce158  mov     pDataObject, [rsp+38h+hPrimaryToken]; hObject
0x1800ce15d  test    pDataObject, pDataObject
0x1800ce160  jz      short loc_1800CE16E
0x1800ce162  call    cs:__imp_CloseHandle
0x1800ce169  nop     dword ptr [rax+rax+00h]
0x1800ce16e  test    ebx, ebx
0x1800ce170  js      short loc_1800CE18B
0x1800ce172  lea     r9, [rsp+38h+hImpersonationToken]; phObjectOwnerToken
0x1800ce177  mov     [rsp+38h+ppDataObj], rdi; ppDataObj
0x1800ce17c  xor     r8d, r8d; fOwnerIsPlmManaged
0x1800ce17f  xor     edx, edx; dwSourceProcessId
0x1800ce181  mov     pDataObject, rsi; pInnerDataObject
0x1800ce184  call    ?Create@CBrokeredClipDataObject@@SAJPEAUIDataObject@@K_NPEAPEAXPEAPEAU2@@Z; CBrokeredClipDataObject::Create(IDataObject *,ulong,bool,void * *,IDataObject * *)
0x1800ce189  mov     ebx, eax
0x1800ce18b  mov     pDataObject, [rsp+38h+hImpersonationToken]; hObject
0x1800ce190  test    pDataObject, pDataObject
0x1800ce193  jz      short loc_1800CE1A1
0x1800ce195  call    cs:__imp_CloseHandle
0x1800ce19c  nop     dword ptr [rax+rax+00h]
0x1800ce1a1  mov     rsi, [rsp+38h+arg_18]
0x1800ce1a6  mov     eax, ebx
0x1800ce1a8  mov     rbx, [rsp+38h+arg_0]
0x1800ce1ad  add     rsp, 30h
0x1800ce1b1  pop     rdi
0x1800ce1b2  retn
```
