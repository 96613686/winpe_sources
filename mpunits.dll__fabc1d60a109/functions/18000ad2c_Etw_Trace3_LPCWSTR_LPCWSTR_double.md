# Etw_Trace3_LPCWSTR_LPCWSTR_double

- ea: `0x18000ad2c`
- end: `0x18000adf6`
- name: `Etw_Trace3_LPCWSTR_LPCWSTR_double`
- size: `202`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800237a0`
- `0x180023970`

## callees

- `0x18000ad2c`
- `0x18000babc`
- `0x180044880`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000add4`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000add4`

## pseudocode

```c
ULONG __fastcall Etw_Trace3_LPCWSTR_LPCWSTR_double(
        PCEVENT_DESCRIPTOR EventDescriptor,
        ULONGLONG a2,
        __int64 a3,
        double a4)
{
  __int64 v7; // rax
  __int64 v8; // rcx
  ULONG v9; // ecx
  int v10; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-40h] BYREF
  __int64 v13; // [rsp+30h] [rbp-30h]
  int v14; // [rsp+38h] [rbp-28h]
  int v15; // [rsp+3Ch] [rbp-24h]
  double *v16; // [rsp+40h] [rbp-20h]
  __int64 v17; // [rsp+48h] [rbp-18h]
  double v18; // [rsp+98h] [rbp+38h] BYREF

  v18 = a4;
  EtwInitProvider();
  v7 = -1;
  UserData.Ptr = a2;
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a2 + 2 * v8) );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 0;
  }
  UserData.Size = v9;
  UserData.Reserved = 0;
  v13 = a3;
  if ( a3 )
  {
    do
      ++v7;
    while ( *(_WORD *)(a3 + 2 * v7) );
    v10 = 2 * v7 + 2;
  }
  else
  {
    v10 = 0;
  }
  v14 = v10;
  v15 = 0;
  v16 = &v18;
  v17 = 8;
  return EventWrite(RegistrationHandle, EventDescriptor, 3u, &UserData);
}

```

## disassembly

```asm
0x18000ad2c  mov     [rsp-18h+arg_8], rbx
0x18000ad31  movsd   [rsp-18h+arg_18], xmm3
0x18000ad37  push    rbp
0x18000ad38  push    rsi
0x18000ad39  push    rdi
0x18000ad3a  mov     rbp, rsp
0x18000ad3d  sub     rsp, 60h
0x18000ad41  mov     rax, cs:__security_cookie
0x18000ad48  xor     rax, rsp
0x18000ad4b  mov     [rbp+var_10], rax
0x18000ad4f  mov     rbx, r8
0x18000ad52  mov     rdi, rdx
0x18000ad55  mov     rsi, rcx
0x18000ad58  call    EtwInitProvider
0x18000ad5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ad61  mov     [rbp+UserData.Ptr], rdi
0x18000ad65  xor     edx, edx
0x18000ad67  test    rdi, rdi
0x18000ad6a  jz      short loc_18000AD82
0x18000ad6c  mov     rcx, rax
0x18000ad6f  inc     rcx
0x18000ad72  cmp     [rdi+rcx*2], dx
0x18000ad76  jnz     short loc_18000AD6F
0x18000ad78  lea     rcx, ds:2[rcx*2]
0x18000ad80  jmp     short loc_18000AD85
0x18000ad82  mov     rcx, rdx
0x18000ad85  mov     [rbp+UserData.Size], ecx
0x18000ad88  mov     dword ptr [rbp+UserData.0Ch], edx
0x18000ad8b  mov     [rbp+var_30], rbx
0x18000ad8f  test    rbx, rbx
0x18000ad92  jz      short loc_18000ADA7
0x18000ad94  inc     rax
0x18000ad97  cmp     [rbx+rax*2], dx
0x18000ad9b  jnz     short loc_18000AD94
0x18000ad9d  lea     rax, ds:2[rax*2]
0x18000ada5  jmp     short loc_18000ADAA
0x18000ada7  mov     rax, rdx
0x18000adaa  mov     rcx, cs:RegistrationHandle; RegHandle
0x18000adb1  lea     r9, [rbp+UserData]; UserData
0x18000adb5  mov     [rbp+var_28], eax
0x18000adb8  mov     r8d, 3; UserDataCount
0x18000adbe  lea     rax, [rbp+arg_18]
0x18000adc2  mov     [rbp+var_24], edx
0x18000adc5  mov     rdx, rsi; EventDescriptor
0x18000adc8  mov     [rbp+var_20], rax
0x18000adcc  mov     [rbp+var_18], 8
0x18000add4  call    cs:__imp_EventWrite
0x18000adda  mov     rcx, [rbp+var_10]
0x18000adde  xor     rcx, rsp; StackCookie
0x18000ade1  call    __security_check_cookie
0x18000ade6  mov     rbx, [rsp+60h+arg_8]
0x18000adee  add     rsp, 60h
0x18000adf2  pop     rdi
0x18000adf3  pop     rsi
0x18000adf4  pop     rbp
0x18000adf5  retn
```
