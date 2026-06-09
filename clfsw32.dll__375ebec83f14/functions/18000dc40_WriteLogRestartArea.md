# WriteLogRestartArea

- ea: `0x18000dc40`
- end: `0x18000dd5b`
- name: `WriteLogRestartArea`
- size: `283`
- prototype: `BOOL __stdcall(PVOID pvMarshal, PVOID pvRestartBuffer, ULONG cbRestartBuffer, PCLFS_LSN plsnBase, ULONG fFlags, PULONG pcbWritten, PCLFS_LSN plsnNext, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dc40`
- `0x180014328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dd46`

## pseudocode

```c
BOOL __stdcall WriteLogRestartArea(
        PVOID pvMarshal,
        PVOID pvRestartBuffer,
        ULONG cbRestartBuffer,
        PCLFS_LSN plsnBase,
        ULONG fFlags,
        PULONG pcbWritten,
        PCLFS_LSN plsnNext,
        LPOVERLAPPED pOverlapped)
{
  DWORD v8; // ecx
  DWORD v9; // edx
  BOOL v10; // ebx
  struct _OVERLAPPED *v12; // [rsp+38h] [rbp-20h]
  union _CLS_LSN v13; // [rsp+40h] [rbp-18h] BYREF
  union _CLS_LSN v14; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+60h] [rbp+8h] BYREF

  v13 = CLFS_LSN_INVALID;
  v14 = CLFS_LSN_NULL;
  v15 = 0;
  if ( !pvMarshal )
    goto LABEL_20;
  if ( plsnBase )
  {
    if ( CLFS_LSN_INVALID.ullOffset == plsnBase->ullOffset )
      goto LABEL_20;
    v13 = *plsnBase;
  }
  if ( (fFlags & 0xFFFFFFFB) != 0 || !cbRestartBuffer )
    goto LABEL_20;
  if ( !pvRestartBuffer )
  {
    v8 = 1784;
LABEL_21:
    SetLastError(v8);
    return 0;
  }
  if ( *(_DWORD *)pvMarshal != -1040322550 || *((_DWORD *)pvMarshal + 1) != 368 )
  {
LABEL_20:
    v8 = 87;
    goto LABEL_21;
  }
  v9 = CClfsMarshallingContext::WriteRestartArea(
         (CClfsMarshallingContext *)pvMarshal,
         pvRestartBuffer,
         cbRestartBuffer,
         &v13,
         fFlags,
         &v15,
         &v14,
         v12);
  if ( pcbWritten && (!v9 || v9 == 997) )
    *pcbWritten = v15;
  if ( plsnNext && (!v9 || v9 == 997) )
    *plsnNext = v14;
  v10 = v9 == 0;
  SetLastError(v9);
  return v10;
}

```

## disassembly

```asm
0x18000dc40  push    rbx
0x18000dc42  sub     rsp, 50h
0x18000dc46  mov     r10, qword ptr cs:CLFS_LSN_INVALID
0x18000dc4d  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x18000dc54  mov     qword ptr [rsp+58h+var_18], r10
0x18000dc59  mov     qword ptr [rsp+58h+var_10], rax
0x18000dc5e  mov     [rsp+58h+arg_0], 0
0x18000dc66  test    rcx, rcx
0x18000dc69  jz      loc_18000DD41
0x18000dc6f  test    r9, r9
0x18000dc72  jz      short loc_18000DC85
0x18000dc74  mov     rax, [r9]
0x18000dc77  cmp     r10, rax
0x18000dc7a  jz      loc_18000DD41
0x18000dc80  mov     qword ptr [rsp+58h+var_18], rax
0x18000dc85  mov     eax, [rsp+58h+fFlags]
0x18000dc8c  test    eax, 0FFFFFFFBh
0x18000dc91  jnz     loc_18000DD41
0x18000dc97  test    r8d, r8d
0x18000dc9a  jz      loc_18000DD41
0x18000dca0  test    rdx, rdx
0x18000dca3  jnz     short loc_18000DCAF
0x18000dca5  mov     ecx, 6F8h; this
0x18000dcaa  jmp     loc_18000DD46
0x18000dcaf  cmp     dword ptr [rcx], 0C1FDF00Ah
0x18000dcb5  jnz     loc_18000DD41
0x18000dcbb  cmp     dword ptr [rcx+4], 170h
0x18000dcc2  jnz     short loc_18000DD41
0x18000dcc4  lea     r9, [rsp+58h+var_10]
0x18000dcc9  mov     [rsp+58h+var_28], r9; union _CLS_LSN *
0x18000dcce  lea     r9, [rsp+58h+arg_0]
0x18000dcd3  mov     [rsp+58h+var_30], r9; unsigned int *
0x18000dcd8  lea     r9, [rsp+58h+var_18]; union _CLS_LSN *
0x18000dcdd  mov     dword ptr [rsp+58h+var_38], eax; char
0x18000dce1  call    ?WriteRestartArea@CClfsMarshallingContext@@QEAAKPEAXKAEBT_CLS_LSN@@KAEAKAEAT2@PEAU_OVERLAPPED@@@Z; CClfsMarshallingContext::WriteRestartArea(void *,ulong,_CLS_LSN const &,ulong,ulong &,_CLS_LSN &,_OVERLAPPED *)
0x18000dce6  mov     edx, eax
0x18000dce8  mov     r8d, 3E5h
0x18000dcee  mov     rax, [rsp+58h+pcbWritten]
0x18000dcf6  test    rax, rax
0x18000dcf9  jz      short loc_18000DD0A
0x18000dcfb  test    edx, edx
0x18000dcfd  jz      short loc_18000DD04
0x18000dcff  cmp     edx, r8d
0x18000dd02  jnz     short loc_18000DD0A
0x18000dd04  mov     ecx, [rsp+58h+arg_0]
0x18000dd08  mov     [rax], ecx
0x18000dd0a  mov     rcx, [rsp+58h+plsnNext]
0x18000dd12  test    rcx, rcx
0x18000dd15  jz      short loc_18000DD28
0x18000dd17  test    edx, edx
0x18000dd19  jz      short loc_18000DD20
0x18000dd1b  cmp     edx, r8d
0x18000dd1e  jnz     short loc_18000DD28
0x18000dd20  mov     rax, qword ptr [rsp+58h+var_10]
0x18000dd25  mov     [rcx], rax
0x18000dd28  xor     ebx, ebx
0x18000dd2a  mov     ecx, edx; dwErrCode
0x18000dd2c  test    edx, edx
0x18000dd2e  setz    bl
0x18000dd31  call    cs:__imp_SetLastError
0x18000dd38  nop     dword ptr [rax+rax+00h]
0x18000dd3d  mov     eax, ebx
0x18000dd3f  jmp     short loc_18000DD54
0x18000dd41  mov     ecx, 57h ; 'W'; dwErrCode
0x18000dd46  call    cs:__imp_SetLastError
0x18000dd4d  nop     dword ptr [rax+rax+00h]
0x18000dd52  xor     eax, eax
0x18000dd54  add     rsp, 50h
0x18000dd58  pop     rbx
0x18000dd59  retn
```
