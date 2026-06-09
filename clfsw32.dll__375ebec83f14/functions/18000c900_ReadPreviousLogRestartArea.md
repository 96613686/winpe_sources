# ReadPreviousLogRestartArea

- ea: `0x18000c900`
- end: `0x18000c9f9`
- name: `ReadPreviousLogRestartArea`
- size: `249`
- prototype: `BOOL __stdcall(PVOID pvReadContext, PVOID *ppvRestartBuffer, PULONG pcbRestartBuffer, PCLFS_LSN plsnRestart, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c900`
- `0x1800124f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9da`

## pseudocode

```c
BOOL __stdcall ReadPreviousLogRestartArea(
        PVOID pvReadContext,
        PVOID *ppvRestartBuffer,
        PULONG pcbRestartBuffer,
        PCLFS_LSN plsnRestart,
        LPOVERLAPPED pOverlapped)
{
  CClfsMarshallingContext *v8; // r10
  int v9; // eax
  DWORD v10; // ecx
  struct _CLFS_RECORD_HEADER *v11; // rdx
  struct _CLFS_RECORD_HEADER *v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = 0;
  if ( pvReadContext
    && ppvRestartBuffer
    && pcbRestartBuffer
    && plsnRestart
    && *((_DWORD *)pvReadContext + 4) == -1040322545
    && *((_DWORD *)pvReadContext + 5) == 224
    && (*((_BYTE *)pvReadContext + 28) & 0x10) != 0
    && (v8 = (CClfsMarshallingContext *)*((_QWORD *)pvReadContext + 24)) != 0 )
  {
    v9 = CClfsMarshallingContext::ReadNextLogRecord(v8, (char *)pvReadContext, 2u, 0, &v13, pOverlapped);
    if ( v9 )
    {
      v10 = v9;
    }
    else
    {
      v11 = v13;
      if ( v13 )
      {
        *ppvRestartBuffer = (char *)v13 + *((unsigned __int16 *)v13 + 17);
        *pcbRestartBuffer = *((_DWORD *)v11 + 6) - *((unsigned __int16 *)v11 + 17);
        *plsnRestart = *(PCLFS_LSN)v11;
        SetLastError(0);
        return 1;
      }
      v10 = 0;
    }
  }
  else
  {
    v10 = 87;
  }
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x18000c900  mov     r11, rsp
0x18000c903  mov     [r11+10h], rbx
0x18000c907  mov     [r11+18h], rsi
0x18000c90b  push    rdi
0x18000c90c  sub     rsp, 30h
0x18000c910  mov     qword ptr [r11+8], 0
0x18000c918  mov     rbx, r9
0x18000c91b  mov     rdi, r8
0x18000c91e  mov     rsi, rdx
0x18000c921  test    rcx, rcx
0x18000c924  jz      loc_18000C9D5
0x18000c92a  test    rdx, rdx
0x18000c92d  jz      loc_18000C9D5
0x18000c933  test    r8, r8
0x18000c936  jz      loc_18000C9D5
0x18000c93c  test    rbx, rbx
0x18000c93f  jz      loc_18000C9D5
0x18000c945  cmp     dword ptr [rcx+10h], 0C1FDF00Fh
0x18000c94c  jnz     loc_18000C9D5
0x18000c952  cmp     dword ptr [rcx+14h], 0E0h
0x18000c959  jnz     short loc_18000C9D5
0x18000c95b  test    byte ptr [rcx+1Ch], 10h
0x18000c95f  jz      short loc_18000C9D5
0x18000c961  mov     r10, [rcx+0C0h]
0x18000c968  test    r10, r10
0x18000c96b  jz      short loc_18000C9D5
0x18000c96d  mov     rax, [rsp+38h+pOverlapped]
0x18000c972  mov     rdx, rcx; void *
0x18000c975  mov     [r11-10h], rax
0x18000c979  xor     r9d, r9d; union _CLS_LSN *
0x18000c97c  lea     rax, [r11+8]
0x18000c980  mov     r8b, 2; unsigned __int8
0x18000c983  mov     rcx, r10; this
0x18000c986  mov     [r11-18h], rax
0x18000c98a  call    ?ReadNextLogRecord@CClfsMarshallingContext@@QEAAKQEAXEQEAT_CLS_LSN@@AEAPEAU_CLFS_RECORD_HEADER@@PEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::ReadNextLogRecord(void * const,uchar,_CLS_LSN * const,_CLFS_RECORD_HEADER * &,_OVERLAPPED *)
0x18000c98f  test    eax, eax
0x18000c991  jz      short loc_18000C997
0x18000c993  mov     ecx, eax
0x18000c995  jmp     short loc_18000C9DA
0x18000c997  mov     rdx, [rsp+38h+arg_0]
0x18000c99c  test    rdx, rdx
0x18000c99f  jnz     short loc_18000C9A5
0x18000c9a1  xor     ecx, ecx
0x18000c9a3  jmp     short loc_18000C9DA
0x18000c9a5  movzx   eax, word ptr [rdx+22h]
0x18000c9a9  add     rax, rdx
0x18000c9ac  mov     [rsi], rax
0x18000c9af  movzx   eax, word ptr [rdx+22h]
0x18000c9b3  mov     ecx, [rdx+18h]
0x18000c9b6  sub     ecx, eax
0x18000c9b8  mov     [rdi], ecx
0x18000c9ba  xor     ecx, ecx; dwErrCode
0x18000c9bc  mov     rax, [rdx]
0x18000c9bf  mov     [rbx], rax
0x18000c9c2  call    cs:__imp_SetLastError
0x18000c9c9  nop     dword ptr [rax+rax+00h]
0x18000c9ce  mov     eax, 1
0x18000c9d3  jmp     short loc_18000C9E8
0x18000c9d5  mov     ecx, 57h ; 'W'; dwErrCode
0x18000c9da  call    cs:__imp_SetLastError
0x18000c9e1  nop     dword ptr [rax+rax+00h]
0x18000c9e6  xor     eax, eax
0x18000c9e8  mov     rbx, [rsp+38h+arg_8]
0x18000c9ed  mov     rsi, [rsp+38h+arg_10]
0x18000c9f2  add     rsp, 30h
0x18000c9f6  pop     rdi
0x18000c9f7  retn
```
