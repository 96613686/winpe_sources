# GetLogReservationInfo

- ea: `0x18000bb40`
- end: `0x18000bba6`
- name: `GetLogReservationInfo`
- size: `102`
- prototype: `BOOL __stdcall(PVOID pvMarshal, PULONG pcbRecordNumber, PLONGLONG pcbUserReservation, PLONGLONG pcbCommitReservation)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bb40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bb92`

## pseudocode

```c
BOOL __stdcall GetLogReservationInfo(
        PVOID pvMarshal,
        PULONG pcbRecordNumber,
        PLONGLONG pcbUserReservation,
        PLONGLONG pcbCommitReservation)
{
  *pcbRecordNumber = -1;
  *pcbUserReservation = -1;
  *pcbCommitReservation = -1;
  if ( pvMarshal && *(_DWORD *)pvMarshal == -1040322550 && *((_DWORD *)pvMarshal + 1) == 368 )
  {
    *pcbRecordNumber = *((_DWORD *)pvMarshal + 38);
    *pcbUserReservation = *((_QWORD *)pvMarshal + 22);
    *pcbCommitReservation = *((_QWORD *)pvMarshal + 23);
    return 1;
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
0x18000bb40  sub     rsp, 28h
0x18000bb44  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb48  mov     dword ptr [rdx], 0FFFFFFFFh
0x18000bb4e  mov     [r8], rax
0x18000bb51  mov     [r9], rax
0x18000bb54  test    rcx, rcx
0x18000bb57  jz      short loc_18000BB8D
0x18000bb59  cmp     dword ptr [rcx], 0C1FDF00Ah
0x18000bb5f  jnz     short loc_18000BB8D
0x18000bb61  cmp     dword ptr [rcx+4], 170h
0x18000bb68  jnz     short loc_18000BB8D
0x18000bb6a  mov     eax, [rcx+98h]
0x18000bb70  mov     [rdx], eax
0x18000bb72  mov     rax, [rcx+0B0h]
0x18000bb79  mov     [r8], rax
0x18000bb7c  mov     rax, [rcx+0B8h]
0x18000bb83  mov     [r9], rax
0x18000bb86  mov     eax, 1
0x18000bb8b  jmp     short loc_18000BBA0
0x18000bb8d  mov     ecx, 57h ; 'W'; dwErrCode
0x18000bb92  call    cs:__imp_SetLastError
0x18000bb99  nop     dword ptr [rax+rax+00h]
0x18000bb9e  xor     eax, eax
0x18000bba0  add     rsp, 28h
0x18000bba4  retn
```
