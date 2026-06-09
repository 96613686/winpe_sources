# SendMessageToWERService

- ea: `0x18004ec14`
- end: `0x18004ee71`
- name: `SendMessageToWERService`
- size: `605`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task`

## callers

- `0x18005f9d4`
- `0x1800605a0`

## callees

- `0x18004ec14`
- `0x18004ee78`
- `0x18004ef24`
- `0x18004f020`
- `0x18012125c`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015f1a0`
- `0x18015fa30`
- `0x18015fc90`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x18004ecde`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
__int64 __fastcall SendMessageToWERService(__int64 a1, __int64 a2)
{
  NTSTATUS started; // ebx
  int v4; // eax
  size_t v5; // rax
  int v6; // edx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  __int64 v10; // rdi
  int v11; // eax
  int v12; // eax
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v15; // [rsp+64h] [rbp-9Ch]
  __int64 SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  __int64 v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  __int128 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+A0h] [rbp-60h]
  __m256i v23; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-20h]

  memset(&v23, 0, 28);
  Handle = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  memset_thunk_772440563353939046(v24, 0, 0x48u);
  v18 = 0;
  v14 = 0;
  v15 = 1280;
  v19 = 0;
  SystemInformation = 0;
  started = SignalStartWerSvc();
  if ( started >= 0 )
  {
    started = NtQuerySystemInformation(SystemErrorPortTimeouts, &SystemInformation, 8u, 0);
    if ( started >= 0 )
    {
      v4 = WaitForWerSvc((unsigned int)SystemInformation);
      started = v4;
      if ( v4 >= 0 && v4 != 258 )
      {
        *(_QWORD *)&v21 = 0;
        *((_QWORD *)&v21 + 1) = L"\\WindowsErrorReportingServicePort";
        v5 = 2 * wcslen(L"\\WindowsErrorReportingServicePort");
        if ( v5 >= 0xFFFE )
          LOWORD(v5) = -4;
        LOWORD(v21) = v5;
        WORD1(v21) = v5 + 2;
        memset_thunk_772440563353939046(v24, 0, 0x48u);
        v25 = 1400;
        v9 = WerpAllocateAndInitializeSid((unsigned int)&v14, v6, v7, v8);
        v10 = v18;
        started = v9;
        if ( v9 >= 0 )
        {
          *(_OWORD *)&v23.m256i_u64[2] = 0;
          LODWORD(v22) = 48;
          *((_QWORD *)&v22 + 1) = 0;
          v23.m256i_i32[2] = 0;
          v23.m256i_i64[0] = 0;
          if ( HIDWORD(SystemInformation) != -1 )
            v19 = -10000LL * SHIDWORD(SystemInformation);
          v11 = NtAlpcConnectPort();
          started = v11;
          if ( v11 >= 0 && v11 != 258 )
          {
            v20 = 1400;
            v12 = ZwAlpcSendWaitReceivePort();
            started = v12;
            if ( v12 >= 0 && v12 != 258 )
            {
              started = 0;
              if ( *(int *)(a2 + 44) < 0 )
                started = *(_DWORD *)(a2 + 44);
            }
          }
        }
        if ( v10 )
          WerpFreeSid(v10);
      }
    }
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18004ec14  mov     [rsp-8+arg_10], rbx
0x18004ec19  mov     [rsp-8+arg_18], rsi
0x18004ec1e  push    rbp
0x18004ec1f  push    rdi
0x18004ec20  push    r12
0x18004ec22  push    r14
0x18004ec24  push    r15
0x18004ec26  lea     rbp, [rsp-30h]
0x18004ec2b  sub     rsp, 130h
0x18004ec32  mov     rax, cs:__security_cookie
0x18004ec39  xor     rax, rsp
0x18004ec3c  mov     [rbp+50h+var_30], rax
0x18004ec40  xorps   xmm0, xmm0
0x18004ec43  xor     eax, eax
0x18004ec45  mov     r14, rdx
0x18004ec48  mov     r15, rcx
0x18004ec4b  xor     r12d, r12d
0x18004ec4e  lea     rcx, [rbp+50h+var_80]; void *
0x18004ec52  movups  [rbp+50h+var_A0], xmm0
0x18004ec56  lea     edi, [rax+48h]
0x18004ec59  mov     [rsp+150h+Handle], r12
0x18004ec5e  mov     r8d, edi; Size
0x18004ec61  mov     [rbp+50h+var_C8], r12
0x18004ec65  xor     edx, edx; Val
0x18004ec67  movups  [rbp+50h+var_C0], xmm0
0x18004ec6b  movups  [rbp+50h+var_B0], xmm0
0x18004ec6f  movups  [rbp+50h+var_A0+0Ch], xmm0
0x18004ec73  call    memset$thunk$772440563353939046
0x18004ec78  mov     [rsp+150h+var_D8], r12
0x18004ec7d  mov     [rsp+150h+var_F0], r12d
0x18004ec82  mov     [rsp+150h+var_EC], 500h
0x18004ec89  mov     [rbp+50h+var_D0], r12
0x18004ec8d  mov     [rsp+150h+SystemInformation], r12
0x18004ec92  call    SignalStartWerSvc
0x18004ec97  mov     ebx, eax
0x18004ec99  test    eax, eax
0x18004ec9b  js      loc_18004EE30
0x18004eca1  xor     r9d, r9d; ReturnLength
0x18004eca4  lea     r8d, [r12+8]; SystemInformationLength
0x18004eca9  lea     rdx, [rsp+150h+SystemInformation]; SystemInformation
0x18004ecae  lea     ecx, [rdi+2Bh]; SystemInformationClass
0x18004ecb1  call    NtQuerySystemInformation
0x18004ecb6  mov     ebx, eax
0x18004ecb8  test    eax, eax
0x18004ecba  js      loc_18004EE30
0x18004ecc0  mov     ecx, dword ptr [rsp+150h+SystemInformation]
0x18004ecc4  call    WaitForWerSvc
0x18004ecc9  mov     ebx, eax
0x18004eccb  test    eax, eax
0x18004eccd  js      loc_18004EE30
0x18004ecd3  cmp     eax, 102h
0x18004ecd8  jz      loc_18004EE30
0x18004ecde  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x18004ece5  mov     qword ptr [rbp+50h+var_C0], r12
0x18004ece9  mov     qword ptr [rbp+50h+var_C0+8], rcx
0x18004eced  call    wcslen
0x18004ecf2  add     rax, rax
0x18004ecf5  mov     ecx, 0FFFCh
0x18004ecfa  cmp     rax, 0FFFEh
0x18004ed00  mov     r8d, edi; Size
0x18004ed03  cmovnb  rax, rcx
0x18004ed07  xor     edx, edx; Val
0x18004ed09  mov     word ptr [rbp+50h+var_C0], ax
0x18004ed0d  lea     rcx, [rbp+50h+var_80]; void *
0x18004ed11  add     ax, 2
0x18004ed15  mov     word ptr [rbp+50h+var_C0+2], ax
0x18004ed19  call    memset$thunk$772440563353939046
0x18004ed1e  lea     rax, [rsp+150h+var_D8]
0x18004ed23  mov     [rbp+50h+var_70], 578h
0x18004ed2b  lea     rcx, [rsp+150h+var_F0]
0x18004ed30  mov     [rsp+150h+var_100], rax
0x18004ed35  call    WerpAllocateAndInitializeSid
0x18004ed3a  mov     rdi, [rsp+150h+var_D8]
0x18004ed3f  mov     ebx, eax
0x18004ed41  test    eax, eax
0x18004ed43  js      loc_18004EE23
0x18004ed49  cmp     dword ptr [rsp+150h+SystemInformation+4], 0FFFFFFFFh
0x18004ed4e  xorps   xmm0, xmm0
0x18004ed51  movdqu  [rbp+50h+var_90], xmm0
0x18004ed56  mov     dword ptr [rbp+50h+var_B0], 30h ; '0'
0x18004ed5d  mov     qword ptr [rbp+50h+var_B0+8], r12
0x18004ed61  mov     dword ptr [rbp+50h+var_A0+8], r12d
0x18004ed65  mov     qword ptr [rbp+50h+var_A0], r12
0x18004ed69  jz      loc_18004EE6A
0x18004ed6f  movsxd  rax, dword ptr [rsp+150h+SystemInformation+4]
0x18004ed74  mov     dl, r12b
0x18004ed77  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x18004ed7e  mov     [rbp+50h+var_D0], rcx
0x18004ed82  test    dl, dl
0x18004ed84  lea     rsi, [rbp+50h+var_D0]
0x18004ed88  lea     r9, [rbp+50h+var_80]
0x18004ed8c  cmovnz  rsi, r12
0x18004ed90  lea     r8, [rbp+50h+var_B0]
0x18004ed94  mov     [rsp+150h+var_100], rsi
0x18004ed99  lea     rdx, [rbp+50h+var_C0]
0x18004ed9d  mov     [rsp+150h+var_108], r12
0x18004eda2  lea     rcx, [rsp+150h+Handle]
0x18004eda7  mov     [rsp+150h+var_110], r12
0x18004edac  mov     [rsp+150h+var_118], r12
0x18004edb1  mov     [rsp+150h+var_120], r12
0x18004edb6  mov     [rsp+150h+var_128], rdi
0x18004edbb  mov     dword ptr [rsp+150h+var_130], 20000h
0x18004edc3  call    NtAlpcConnectPort
0x18004edc8  mov     ebx, eax
0x18004edca  test    eax, eax
0x18004edcc  js      short loc_18004EE23
0x18004edce  cmp     eax, 102h
0x18004edd3  jz      short loc_18004EE23
0x18004edd5  mov     rcx, [rsp+150h+Handle]
0x18004edda  lea     rax, [rbp+50h+var_C8]
0x18004edde  mov     [rsp+150h+var_118], rsi
0x18004ede3  xor     r9d, r9d
0x18004ede6  mov     [rsp+150h+var_120], r12
0x18004edeb  mov     r8, r15
0x18004edee  mov     [rsp+150h+var_128], rax
0x18004edf3  mov     edx, 20000h
0x18004edf8  mov     [rsp+150h+var_130], r14
0x18004edfd  mov     [rbp+50h+var_C8], 578h
0x18004ee05  call    ZwAlpcSendWaitReceivePort
0x18004ee0a  mov     ebx, eax
0x18004ee0c  test    eax, eax
0x18004ee0e  js      short loc_18004EE23
0x18004ee10  cmp     eax, 102h
0x18004ee15  jz      short loc_18004EE23
0x18004ee17  cmp     [r14+2Ch], r12d
0x18004ee1b  mov     ebx, r12d
0x18004ee1e  cmovl   ebx, [r14+2Ch]
0x18004ee23  test    rdi, rdi
0x18004ee26  jz      short loc_18004EE30
0x18004ee28  mov     rcx, rdi
0x18004ee2b  call    WerpFreeSid
0x18004ee30  mov     rcx, [rsp+150h+Handle]; Handle
0x18004ee35  test    rcx, rcx
0x18004ee38  jz      short loc_18004EE3F
0x18004ee3a  call    NtClose
0x18004ee3f  mov     eax, ebx
0x18004ee41  mov     rcx, [rbp+50h+var_30]
0x18004ee45  xor     rcx, rsp; StackCookie
0x18004ee48  call    __security_check_cookie
0x18004ee4d  lea     r11, [rsp+150h+var_20]
0x18004ee55  mov     rbx, [r11+40h]
0x18004ee59  mov     rsi, [r11+48h]
0x18004ee5d  mov     rsp, r11
0x18004ee60  pop     r15
0x18004ee62  pop     r14
0x18004ee64  pop     r12
0x18004ee66  pop     rdi
0x18004ee67  pop     rbp
0x18004ee68  retn
0x18004ee6a  mov     dl, 1
0x18004ee6c  jmp     loc_18004ED82
```
