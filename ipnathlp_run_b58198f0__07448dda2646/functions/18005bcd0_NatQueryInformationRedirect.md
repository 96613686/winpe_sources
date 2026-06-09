# NatQueryInformationRedirect

- ea: `0x18005bcd0`
- end: `0x18005bf8f`
- name: `NatQueryInformationRedirect`
- size: `703`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int, __int16, int, __int16, int, __int16, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180051f30`
- `0x18005bcd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005bd68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005bd68`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005bea3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005bea3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005beb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005beb6`
- `ntdll!NtDeviceIoControlFile` at `0x18005be87`
- `ntdll!NtDeviceIoControlFile` at `0x18005be87`
- `ntdll!RtlNtStatusToDosError` at `0x18005beca`
- `ntdll!RtlNtStatusToDosError` at `0x18005beca`

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
0x18005bcd0  push    rbp
0x18005bcd2  push    rbx
0x18005bcd3  push    rsi
0x18005bcd4  push    rdi
0x18005bcd5  push    r12
0x18005bcd7  push    r13
0x18005bcd9  push    r14
0x18005bcdb  push    r15
0x18005bcdd  lea     rbp, [rsp-8]
0x18005bce2  sub     rsp, 108h
0x18005bce9  mov     rax, cs:__security_cookie
0x18005bcf0  xor     rax, rsp
0x18005bcf3  mov     [rbp+40h+var_50], rax
0x18005bcf7  mov     rsi, [rbp+40h+arg_58]
0x18005bcfe  xorps   xmm0, xmm0
0x18005bd01  mov     rdi, [rbp+40h+arg_50]
0x18005bd08  xor     eax, eax
0x18005bd0a  mov     [rsp+140h+var_F0], r9w
0x18005bd10  xorps   xmm1, xmm1
0x18005bd13  mov     [rbp+40h+var_B8], eax
0x18005bd16  mov     r13d, r8d
0x18005bd19  mov     r12b, dl
0x18005bd1c  mov     r14, rcx
0x18005bd1f  movups  xmmword ptr [rbp+40h+var_B0], xmm0
0x18005bd23  movups  [rsp+140h+var_E8], xmm0
0x18005bd28  movups  [rsp+140h+var_D8], xmm0
0x18005bd2d  movups  [rsp+140h+var_C8], xmm0
0x18005bd32  movups  [rbp+40h+var_80], xmm0
0x18005bd36  movups  [rbp+40h+var_70], xmm0
0x18005bd3a  movups  [rbp+40h+var_60], xmm0
0x18005bd3e  movups  [rbp+40h+var_90], xmm0
0x18005bd42  movups  [rbp+40h+var_A0], xmm1
0x18005bd46  test    rsi, rsi
0x18005bd49  jz      loc_18005BF69
0x18005bd4f  mov     ebx, [rbp+40h+arg_60]
0x18005bd55  cmp     ebx, 5
0x18005bd58  jge     loc_18005BF69
0x18005bd5e  xor     r9d, r9d; lpName
0x18005bd61  xor     r8d, r8d; bInitialState
0x18005bd64  xor     edx, edx; bManualReset
0x18005bd66  xor     ecx, ecx; lpEventAttributes
0x18005bd68  call    cs:__imp_CreateEventW
0x18005bd6f  nop     dword ptr [rax+rax+00h]
0x18005bd74  mov     r15, rax
0x18005bd77  test    rax, rax
0x18005bd7a  jnz     short loc_18005BD85
0x18005bd7c  lea     eax, [r15+8]
0x18005bd80  jmp     loc_18005BF6E
0x18005bd85  movzx   eax, [rsp+140h+var_F0]
0x18005bd8a  mov     word ptr [rsp+140h+var_C8], ax
0x18005bd8f  mov     eax, [rbp+40h+arg_20]
0x18005bd92  mov     dword ptr [rsp+140h+var_D8+4], eax
0x18005bd96  movzx   eax, [rbp+40h+arg_28]
0x18005bd9a  mov     word ptr [rsp+140h+var_D8+8], ax
0x18005bd9f  mov     eax, [rbp+40h+arg_30]
0x18005bda5  mov     dword ptr [rbp+40h+var_C8+0Ch], eax
0x18005bda8  movzx   eax, [rbp+40h+arg_38]
0x18005bdaf  mov     word ptr [rbp+40h+var_B8], ax
0x18005bdb3  mov     eax, [rbp+40h+arg_40]
0x18005bdb9  mov     dword ptr [rsp+140h+var_C8+4], eax
0x18005bdbd  movzx   eax, [rbp+40h+arg_48]
0x18005bdc4  mov     byte ptr [rsp+140h+var_D8], r12b
0x18005bdc9  mov     r12d, 10h
0x18005bdcf  mov     word ptr [rbp+40h+var_C8+8], ax
0x18005bdd3  mov     dword ptr [rsp+140h+var_E8], 0
0x18005bddb  mov     qword ptr [rsp+140h+var_E8+8], 0
0x18005bde4  mov     dword ptr [rsp+140h+var_D8+0Ch], r13d
0x18005bde9  cmp     ebx, 4
0x18005bdec  jnz     short loc_18005BE18
0x18005bdee  mov     [rsp+140h+OutputBufferLength], r12d
0x18005bdf3  lea     rax, [rbp+40h+var_A0]
0x18005bdf7  mov     [rsp+140h+OutputBuffer], rax
0x18005bdfc  lea     rax, [rsp+140h+var_E8]
0x18005be01  mov     [rsp+140h+InputBufferLength], 38h ; '8'
0x18005be09  mov     [rsp+140h+InputBuffer], rax
0x18005be0e  mov     [rsp+140h+IoControlCode], 128054h
0x18005be16  jmp     short loc_18005BE72
0x18005be18  cmp     ebx, 3
0x18005be1b  jnz     short loc_18005BE47
0x18005be1d  mov     [rsp+140h+OutputBufferLength], r12d
0x18005be22  lea     rax, [rbp+40h+var_90]
0x18005be26  mov     [rsp+140h+OutputBuffer], rax
0x18005be2b  lea     rax, [rsp+140h+var_E8]
0x18005be30  mov     [rsp+140h+InputBufferLength], 38h ; '8'
0x18005be38  mov     [rsp+140h+InputBuffer], rax
0x18005be3d  mov     [rsp+140h+IoControlCode], 128048h
0x18005be45  jmp     short loc_18005BE72
0x18005be47  mov     [rsp+140h+OutputBufferLength], 30h ; '0'; OutputBufferLength
0x18005be4f  lea     rax, [rbp+40h+var_80]
0x18005be53  mov     [rsp+140h+OutputBuffer], rax; OutputBuffer
0x18005be58  lea     rax, [rsp+140h+var_E8]
0x18005be5d  mov     [rsp+140h+InputBufferLength], 38h ; '8'; InputBufferLength
0x18005be65  mov     [rsp+140h+InputBuffer], rax; InputBuffer
0x18005be6a  mov     [rsp+140h+IoControlCode], 12803Ch; IoControlCode
0x18005be72  lea     rax, [rbp+40h+var_B0]
0x18005be76  xor     r9d, r9d; ApcContext
0x18005be79  xor     r8d, r8d; ApcRoutine
0x18005be7c  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x18005be81  mov     rdx, r15; Event
0x18005be84  mov     rcx, r14; FileHandle
0x18005be87  call    cs:__imp_NtDeviceIoControlFile
0x18005be8e  nop     dword ptr [rax+rax+00h]
0x18005be93  mov     r14d, eax
0x18005be96  cmp     eax, 103h
0x18005be9b  jnz     short loc_18005BEB3
0x18005be9d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005bea0  mov     rcx, r15; hHandle
0x18005bea3  call    cs:__imp_WaitForSingleObject
0x18005beaa  nop     dword ptr [rax+rax+00h]
0x18005beaf  mov     r14d, dword ptr [rbp+40h+var_B0]
0x18005beb3  mov     rcx, r15; hObject
0x18005beb6  call    cs:__imp_CloseHandle
0x18005bebd  nop     dword ptr [rax+rax+00h]
0x18005bec2  test    r14d, r14d
0x18005bec5  jns     short loc_18005BEDB
0x18005bec7  mov     ecx, r14d; Status
0x18005beca  call    cs:__imp_RtlNtStatusToDosError
0x18005bed1  nop     dword ptr [rax+rax+00h]
0x18005bed6  jmp     loc_18005BF6E
0x18005bedb  xor     edx, edx
0x18005bedd  sub     ebx, 1
0x18005bee0  jz      short loc_18005BF47
0x18005bee2  sub     ebx, 1
0x18005bee5  jz      short loc_18005BF31
0x18005bee7  sub     ebx, 1
0x18005beea  jz      short loc_18005BF13
0x18005beec  cmp     ebx, 1
0x18005beef  jnz     short loc_18005BF69
0x18005bef1  cmp     [rsi], r12d
0x18005bef4  jb      short loc_18005BF4C
0x18005bef6  mov     eax, dword ptr [rbp+40h+var_A0]
0x18005bef9  mov     [rdi], eax
0x18005befb  movzx   eax, word ptr [rbp+40h+var_A0+4]
0x18005beff  mov     [rdi+4], ax
0x18005bf03  mov     eax, dword ptr [rbp+40h+var_A0+8]
0x18005bf06  mov     [rdi+8], eax
0x18005bf09  movzx   eax, word ptr [rbp+40h+var_A0+0Ch]
0x18005bf0d  mov     [rdi+0Ch], ax
0x18005bf11  jmp     short loc_18005BF62
0x18005bf13  cmp     [rsi], r12d
0x18005bf16  jb      short loc_18005BF4C
0x18005bf18  mov     eax, dword ptr [rbp+40h+var_90]
0x18005bf1b  mov     [rdi], eax
0x18005bf1d  movzx   eax, word ptr [rbp+40h+var_90+4]
0x18005bf21  mov     [rdi+4], ax
0x18005bf25  mov     eax, dword ptr [rbp+40h+var_90+8]
0x18005bf28  mov     [rdi+8], eax
0x18005bf2b  movzx   eax, word ptr [rbp+40h+var_90+0Ch]
0x18005bf2f  jmp     short loc_18005BF0D
0x18005bf31  cmp     [rsi], r12d
0x18005bf34  jb      short loc_18005BF4C
0x18005bf36  mov     rax, qword ptr [rbp+40h+var_60]
0x18005bf3a  mov     [rdi], rax
0x18005bf3d  mov     rax, qword ptr [rbp+40h+var_60+8]
0x18005bf41  mov     [rdi+8], rax
0x18005bf45  jmp     short loc_18005BF62
0x18005bf47  cmp     [rsi], r12d
0x18005bf4a  jnb     short loc_18005BF53
0x18005bf4c  mov     edx, 7Ah ; 'z'
0x18005bf51  jmp     short loc_18005BF62
0x18005bf53  mov     rcx, qword ptr [rbp+40h+var_80]
0x18005bf57  mov     [rdi], rcx
0x18005bf5a  mov     rcx, qword ptr [rbp+40h+var_80+8]
0x18005bf5e  mov     [rdi+8], rcx
0x18005bf62  mov     [rsi], r12d
0x18005bf65  mov     eax, edx
0x18005bf67  jmp     short loc_18005BF6E
0x18005bf69  mov     eax, 57h ; 'W'
0x18005bf6e  mov     rcx, [rbp+40h+var_50]
0x18005bf72  xor     rcx, rsp; StackCookie
0x18005bf75  call    __security_check_cookie
0x18005bf7a  add     rsp, 108h
0x18005bf81  pop     r15
0x18005bf83  pop     r14
0x18005bf85  pop     r13
0x18005bf87  pop     r12
0x18005bf89  pop     rdi
0x18005bf8a  pop     rsi
0x18005bf8b  pop     rbx
0x18005bf8c  pop     rbp
0x18005bf8d  retn
```
