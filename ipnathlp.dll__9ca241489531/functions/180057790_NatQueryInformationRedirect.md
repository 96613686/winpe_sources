# NatQueryInformationRedirect

- ea: `0x180057790`
- end: `0x180057a30`
- name: `NatQueryInformationRedirect`
- size: `672`
- prototype: `ULONG __fastcall(HANDLE FileHandle, char, int, __int16, int, __int16, int, __int16, int, __int16, __int64, _DWORD *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18004e0c0`
- `0x180057790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057828`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180057828`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057957`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057964`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057964`
- `ntdll!NtDeviceIoControlFile` at `0x180057941`
- `ntdll!NtDeviceIoControlFile` at `0x180057941`
- `ntdll!RtlNtStatusToDosError` at `0x180057972`
- `ntdll!RtlNtStatusToDosError` at `0x180057972`

## pseudocode

```c
ULONG __fastcall NatQueryInformationRedirect(
        HANDLE FileHandle,
        char a2,
        int a3,
        __int16 a4,
        int a5,
        __int16 a6,
        int a7,
        __int16 a8,
        int a9,
        __int16 a10,
        __int64 a11,
        _DWORD *a12,
        int a13)
{
  HANDLE EventW; // r15
  NTSTATUS v18; // eax
  int Status; // r14d
  int v20; // edx
  __int16 v21; // ax
  __int128 InputBuffer; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h]
  __int128 v25; // [rsp+78h] [rbp-88h]
  int v26; // [rsp+88h] [rbp-78h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  __int128 OutputBuffer; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v29; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v30[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v31; // [rsp+E0h] [rbp-20h]

  v26 = 0;
  IoStatusBlock = 0;
  InputBuffer = 0;
  v24 = 0;
  v25 = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v29 = 0;
  OutputBuffer = 0;
  if ( a12 && a13 < 5 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
      return 8;
    LOWORD(v25) = a4;
    DWORD1(v24) = a5;
    WORD4(v24) = a6;
    HIDWORD(v25) = a7;
    LOWORD(v26) = a8;
    DWORD1(v25) = a9;
    LOBYTE(v24) = a2;
    WORD4(v25) = a10;
    LODWORD(InputBuffer) = 0;
    *((_QWORD *)&InputBuffer + 1) = 0;
    HIDWORD(v24) = a3;
    if ( a13 == 4 )
    {
      v18 = NtDeviceIoControlFile(
              FileHandle,
              EventW,
              0,
              0,
              &IoStatusBlock,
              0x128054u,
              &InputBuffer,
              0x38u,
              &OutputBuffer,
              0x10u);
    }
    else if ( a13 == 3 )
    {
      v18 = NtDeviceIoControlFile(FileHandle, EventW, 0, 0, &IoStatusBlock, 0x128048u, &InputBuffer, 0x38u, &v29, 0x10u);
    }
    else
    {
      v18 = NtDeviceIoControlFile(FileHandle, EventW, 0, 0, &IoStatusBlock, 0x12803Cu, &InputBuffer, 0x38u, v30, 0x30u);
    }
    Status = v18;
    if ( v18 == 259 )
    {
      WaitForSingleObject(EventW, 0xFFFFFFFF);
      Status = IoStatusBlock.Status;
    }
    CloseHandle(EventW);
    if ( Status < 0 )
      return RtlNtStatusToDosError(Status);
    v20 = 0;
    switch ( a13 )
    {
      case 1:
        if ( *a12 >= 0x10u )
        {
          *(_OWORD *)a11 = v30[0];
          goto LABEL_28;
        }
        goto LABEL_26;
      case 2:
        if ( *a12 >= 0x10u )
        {
          *(_OWORD *)a11 = v31;
          goto LABEL_28;
        }
        goto LABEL_26;
      case 3:
        if ( *a12 >= 0x10u )
        {
          *(_DWORD *)a11 = v29;
          *(_WORD *)(a11 + 4) = WORD2(v29);
          *(_DWORD *)(a11 + 8) = DWORD2(v29);
          v21 = WORD6(v29);
          goto LABEL_20;
        }
LABEL_26:
        v20 = 122;
        goto LABEL_28;
      case 4:
        if ( *a12 >= 0x10u )
        {
          *(_DWORD *)a11 = OutputBuffer;
          *(_WORD *)(a11 + 4) = WORD2(OutputBuffer);
          *(_DWORD *)(a11 + 8) = DWORD2(OutputBuffer);
          v21 = WORD6(OutputBuffer);
LABEL_20:
          *(_WORD *)(a11 + 12) = v21;
LABEL_28:
          *a12 = 16;
          return v20;
        }
        goto LABEL_26;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180057790  push    rbp
0x180057792  push    rbx
0x180057793  push    rsi
0x180057794  push    rdi
0x180057795  push    r12
0x180057797  push    r13
0x180057799  push    r14
0x18005779b  push    r15
0x18005779d  lea     rbp, [rsp-8]
0x1800577a2  sub     rsp, 108h
0x1800577a9  mov     rax, cs:__security_cookie
0x1800577b0  xor     rax, rsp
0x1800577b3  mov     [rbp+40h+var_50], rax
0x1800577b7  mov     rsi, [rbp+40h+arg_58]
0x1800577be  xorps   xmm0, xmm0
0x1800577c1  mov     rdi, [rbp+40h+arg_50]
0x1800577c8  xor     eax, eax
0x1800577ca  mov     [rsp+140h+var_F0], r9w
0x1800577d0  xorps   xmm1, xmm1
0x1800577d3  mov     [rbp+40h+var_B8], eax
0x1800577d6  mov     r13d, r8d
0x1800577d9  mov     r12b, dl
0x1800577dc  mov     r14, rcx
0x1800577df  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x1800577e3  movups  [rsp+140h+var_E8], xmm0
0x1800577e8  movups  [rsp+140h+var_D8], xmm0
0x1800577ed  movups  [rsp+140h+var_C8], xmm0
0x1800577f2  movups  [rbp+40h+var_80], xmm0
0x1800577f6  movups  [rbp+40h+var_70], xmm0
0x1800577fa  movups  [rbp+40h+var_60], xmm0
0x1800577fe  movups  [rbp+40h+var_90], xmm0
0x180057802  movups  [rbp+40h+var_A0], xmm1
0x180057806  test    rsi, rsi
0x180057809  jz      loc_180057A0B
0x18005780f  mov     ebx, [rbp+40h+arg_60]
0x180057815  cmp     ebx, 5
0x180057818  jge     loc_180057A0B
0x18005781e  xor     r9d, r9d; lpName
0x180057821  xor     r8d, r8d; bInitialState
0x180057824  xor     edx, edx; bManualReset
0x180057826  xor     ecx, ecx; lpEventAttributes
0x180057828  call    cs:__imp_CreateEventW
0x18005782e  mov     r15, rax
0x180057831  test    rax, rax
0x180057834  jnz     short loc_18005783F
0x180057836  lea     eax, [r15+8]
0x18005783a  jmp     loc_180057A10
0x18005783f  movzx   eax, [rsp+140h+var_F0]
0x180057844  mov     word ptr [rsp+140h+var_C8], ax
0x180057849  mov     eax, [rbp+40h+arg_20]
0x18005784c  mov     dword ptr [rsp+140h+var_D8+4], eax
0x180057850  movzx   eax, [rbp+40h+arg_28]
0x180057854  mov     word ptr [rsp+140h+var_D8+8], ax
0x180057859  mov     eax, [rbp+40h+arg_30]
0x18005785f  mov     dword ptr [rbp+40h+var_C8+0Ch], eax
0x180057862  movzx   eax, [rbp+40h+arg_38]
0x180057869  mov     word ptr [rbp+40h+var_B8], ax
0x18005786d  mov     eax, [rbp+40h+arg_40]
0x180057873  mov     dword ptr [rsp+140h+var_C8+4], eax
0x180057877  movzx   eax, [rbp+40h+arg_48]
0x18005787e  mov     byte ptr [rsp+140h+var_D8], r12b
0x180057883  mov     r12d, 10h
0x180057889  mov     word ptr [rbp+40h+var_C8+8], ax
0x18005788d  mov     dword ptr [rsp+140h+var_E8], 0
0x180057895  mov     qword ptr [rsp+140h+var_E8+8], 0
0x18005789e  mov     dword ptr [rsp+140h+var_D8+0Ch], r13d
0x1800578a3  cmp     ebx, 4
0x1800578a6  jnz     short loc_1800578D2
0x1800578a8  mov     [rsp+140h+OutputBufferLength], r12d
0x1800578ad  lea     rax, [rbp+40h+var_A0]
0x1800578b1  mov     [rsp+140h+OutputBuffer], rax
0x1800578b6  lea     rax, [rsp+140h+var_E8]
0x1800578bb  mov     [rsp+140h+InputBufferLength], 38h ; '8'
0x1800578c3  mov     [rsp+140h+InputBuffer], rax
0x1800578c8  mov     [rsp+140h+IoControlCode], 128054h
0x1800578d0  jmp     short loc_18005792C
0x1800578d2  cmp     ebx, 3
0x1800578d5  jnz     short loc_180057901
0x1800578d7  mov     [rsp+140h+OutputBufferLength], r12d
0x1800578dc  lea     rax, [rbp+40h+var_90]
0x1800578e0  mov     [rsp+140h+OutputBuffer], rax
0x1800578e5  lea     rax, [rsp+140h+var_E8]
0x1800578ea  mov     [rsp+140h+InputBufferLength], 38h ; '8'
0x1800578f2  mov     [rsp+140h+InputBuffer], rax
0x1800578f7  mov     [rsp+140h+IoControlCode], 128048h
0x1800578ff  jmp     short loc_18005792C
0x180057901  mov     [rsp+140h+OutputBufferLength], 30h ; '0'; OutputBufferLength
0x180057909  lea     rax, [rbp+40h+var_80]
0x18005790d  mov     [rsp+140h+OutputBuffer], rax; OutputBuffer
0x180057912  lea     rax, [rsp+140h+var_E8]
0x180057917  mov     [rsp+140h+InputBufferLength], 38h ; '8'; InputBufferLength
0x18005791f  mov     [rsp+140h+InputBuffer], rax; InputBuffer
0x180057924  mov     [rsp+140h+IoControlCode], 12803Ch; IoControlCode
0x18005792c  lea     rax, [rbp+40h+var_B0]
0x180057930  xor     r9d, r9d; ApcContext
0x180057933  xor     r8d, r8d; ApcRoutine
0x180057936  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x18005793b  mov     rdx, r15; Event
0x18005793e  mov     rcx, r14; FileHandle
0x180057941  call    cs:__imp_NtDeviceIoControlFile
0x180057947  mov     r14d, eax
0x18005794a  cmp     eax, 103h
0x18005794f  jnz     short loc_180057961
0x180057951  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180057954  mov     rcx, r15; hHandle
0x180057957  call    cs:__imp_WaitForSingleObject
0x18005795d  mov     r14d, dword ptr [rbp+40h+var_B0]
0x180057961  mov     rcx, r15; hObject
0x180057964  call    cs:__imp_CloseHandle
0x18005796a  test    r14d, r14d
0x18005796d  jns     short loc_18005797D
0x18005796f  mov     ecx, r14d; Status
0x180057972  call    cs:__imp_RtlNtStatusToDosError
0x180057978  jmp     loc_180057A10
0x18005797d  xor     edx, edx
0x18005797f  sub     ebx, 1
0x180057982  jz      short loc_1800579E9
0x180057984  sub     ebx, 1
0x180057987  jz      short loc_1800579D3
0x180057989  sub     ebx, 1
0x18005798c  jz      short loc_1800579B5
0x18005798e  cmp     ebx, 1
0x180057991  jnz     short loc_180057A0B
0x180057993  cmp     [rsi], r12d
0x180057996  jb      short loc_1800579EE
0x180057998  mov     eax, dword ptr [rbp+40h+var_A0]
0x18005799b  mov     [rdi], eax
0x18005799d  movzx   eax, word ptr [rbp+40h+var_A0+4]
0x1800579a1  mov     [rdi+4], ax
0x1800579a5  mov     eax, dword ptr [rbp+40h+var_A0+8]
0x1800579a8  mov     [rdi+8], eax
0x1800579ab  movzx   eax, word ptr [rbp+40h+var_A0+0Ch]
0x1800579af  mov     [rdi+0Ch], ax
0x1800579b3  jmp     short loc_180057A04
0x1800579b5  cmp     [rsi], r12d
0x1800579b8  jb      short loc_1800579EE
0x1800579ba  mov     eax, dword ptr [rbp+40h+var_90]
0x1800579bd  mov     [rdi], eax
0x1800579bf  movzx   eax, word ptr [rbp+40h+var_90+4]
0x1800579c3  mov     [rdi+4], ax
0x1800579c7  mov     eax, dword ptr [rbp+40h+var_90+8]
0x1800579ca  mov     [rdi+8], eax
0x1800579cd  movzx   eax, word ptr [rbp+40h+var_90+0Ch]
0x1800579d1  jmp     short loc_1800579AF
0x1800579d3  cmp     [rsi], r12d
0x1800579d6  jb      short loc_1800579EE
0x1800579d8  mov     rax, qword ptr [rbp+40h+var_60]
0x1800579dc  mov     [rdi], rax
0x1800579df  mov     rax, qword ptr [rbp+40h+var_60+8]
0x1800579e3  mov     [rdi+8], rax
0x1800579e7  jmp     short loc_180057A04
0x1800579e9  cmp     [rsi], r12d
0x1800579ec  jnb     short loc_1800579F5
0x1800579ee  mov     edx, 7Ah ; 'z'
0x1800579f3  jmp     short loc_180057A04
0x1800579f5  mov     rcx, qword ptr [rbp+40h+var_80]
0x1800579f9  mov     [rdi], rcx
0x1800579fc  mov     rcx, qword ptr [rbp+40h+var_80+8]
0x180057a00  mov     [rdi+8], rcx
0x180057a04  mov     [rsi], r12d
0x180057a07  mov     eax, edx
0x180057a09  jmp     short loc_180057A10
0x180057a0b  mov     eax, 57h ; 'W'
0x180057a10  mov     rcx, [rbp+40h+var_50]
0x180057a14  xor     rcx, rsp; StackCookie
0x180057a17  call    __security_check_cookie
0x180057a1c  add     rsp, 108h
0x180057a23  pop     r15
0x180057a25  pop     r14
0x180057a27  pop     r13
0x180057a29  pop     r12
0x180057a2b  pop     rdi
0x180057a2c  pop     rsi
0x180057a2d  pop     rbx
0x180057a2e  pop     rbp
0x180057a2f  retn
```
