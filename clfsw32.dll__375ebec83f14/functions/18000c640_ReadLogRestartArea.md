# ReadLogRestartArea

- ea: `0x18000c640`
- end: `0x18000c6e1`
- name: `ReadLogRestartArea`
- size: `161`
- prototype: `BOOL __stdcall(PVOID pvMarshal, PVOID *ppvRestartBuffer, PULONG pcbRestartBuffer, PCLFS_LSN plsn, PVOID *ppvContext, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c640`
- `0x180012e18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6cc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6cc`

## pseudocode

```c
BOOL __stdcall ReadLogRestartArea(
        PVOID pvMarshal,
        PVOID *ppvRestartBuffer,
        PULONG pcbRestartBuffer,
        PCLFS_LSN plsn,
        PVOID *ppvContext,
        LPOVERLAPPED pOverlapped)
{
  DWORD RestartArea; // eax
  BOOL v7; // ebx

  if ( pvMarshal
    && ppvRestartBuffer
    && pcbRestartBuffer
    && plsn
    && ppvContext
    && (*ppvRestartBuffer = 0,
        *pcbRestartBuffer = 0,
        *plsn = CLFS_LSN_NULL,
        *ppvContext = 0,
        *(_QWORD *)pvMarshal == 0x170C1FDF00ALL) )
  {
    RestartArea = CClfsMarshallingContext::ReadRestartArea(
                    (CClfsMarshallingContext *)pvMarshal,
                    ppvRestartBuffer,
                    pcbRestartBuffer,
                    plsn,
                    ppvContext,
                    pOverlapped);
    v7 = RestartArea == 0;
    SetLastError(RestartArea);
    return v7;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18000c640  push    rbx
0x18000c642  sub     rsp, 30h
0x18000c646  mov     r10, rdx
0x18000c649  test    rcx, rcx
0x18000c64c  jz      short loc_18000C6C7
0x18000c64e  test    rdx, rdx
0x18000c651  jz      short loc_18000C6C7
0x18000c653  test    r8, r8
0x18000c656  jz      short loc_18000C6C7
0x18000c658  test    r9, r9
0x18000c65b  jz      short loc_18000C6C7
0x18000c65d  mov     rdx, [rsp+38h+ppvContext]
0x18000c662  test    rdx, rdx
0x18000c665  jz      short loc_18000C6C7
0x18000c667  mov     qword ptr [r10], 0
0x18000c66e  mov     dword ptr [r8], 0
0x18000c675  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000c67c  mov     [r9], rax
0x18000c67f  mov     qword ptr [rdx], 0
0x18000c686  cmp     dword ptr [rcx], 0C1FDF00Ah
0x18000c68c  jnz     short loc_18000C6C7
0x18000c68e  cmp     dword ptr [rcx+4], 170h
0x18000c695  jnz     short loc_18000C6C7
0x18000c697  mov     rax, [rsp+38h+pOverlapped]
0x18000c69c  mov     [rsp+38h+var_10], rax; struct _OVERLAPPED *
0x18000c6a1  mov     [rsp+38h+var_18], rdx; void **
0x18000c6a6  mov     rdx, r10; void **
0x18000c6a9  call    ?ReadRestartArea@CClfsMarshallingContext@@QEAAKAEAPEAXAEAKAEAT_CLS_LSN@@0PEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::ReadRestartArea(void * &,ulong &,_CLS_LSN &,void * &,_OVERLAPPED *)
0x18000c6ae  xor     ebx, ebx
0x18000c6b0  mov     ecx, eax; dwErrCode
0x18000c6b2  test    eax, eax
0x18000c6b4  setz    bl
0x18000c6b7  call    cs:__imp_SetLastError
0x18000c6be  nop     dword ptr [rax+rax+00h]
0x18000c6c3  mov     eax, ebx
0x18000c6c5  jmp     short loc_18000C6DA
0x18000c6c7  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c6cc  call    cs:__imp_SetLastError
0x18000c6d3  nop     dword ptr [rax+rax+00h]
0x18000c6d8  xor     eax, eax
0x18000c6da  add     rsp, 30h
0x18000c6de  pop     rbx
0x18000c6df  retn
```
