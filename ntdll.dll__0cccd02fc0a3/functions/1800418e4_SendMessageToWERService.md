# SendMessageToWERService

- ea: `0x1800418e4`
- end: `0x180041b41`
- name: `SendMessageToWERService`
- size: `605`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task`

## callers

- `0x180042de4`
- `0x1800439b0`

## callees

- `0x1800418e4`
- `0x180041b48`
- `0x180041bf4`
- `0x180041cf0`
- `0x18012076c`
- `0x18012c830`
- `0x18015e4b0`
- `0x18015e990`
- `0x18015f220`
- `0x18015f480`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1800419ae`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
__int64 __fastcall SendMessageToWERService(__int64 a1, __int64 a2)
{
  NTSTATUS started; // ebx
  int v5; // eax
  size_t v6; // rax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  __int64 v11; // rdi
  char v12; // dl
  __int64 *v13; // rsi
  int v14; // eax
  int v15; // eax
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v18; // [rsp+64h] [rbp-9Ch]
  __int64 SystemInformation; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21; // [rsp+78h] [rbp-88h]
  __int64 v22; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h] BYREF
  __int128 v24; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v25[48]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v26[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-20h]

  Handle = 0;
  v23 = 0;
  v24 = 0;
  memset(v25, 0, 44);
  memset_thunk_772440563353939046(v26, 0, 0x48u);
  v21 = 0;
  v17 = 0;
  v18 = 1280;
  v22 = 0;
  SystemInformation = 0;
  started = SignalStartWerSvc();
  if ( started >= 0 )
  {
    started = NtQuerySystemInformation(SystemErrorPortTimeouts, &SystemInformation, 8u, 0);
    if ( started >= 0 )
    {
      v5 = WaitForWerSvc((unsigned int)SystemInformation);
      started = v5;
      if ( v5 >= 0 && v5 != 258 )
      {
        *(_QWORD *)&v24 = 0;
        *((_QWORD *)&v24 + 1) = L"\\WindowsErrorReportingServicePort";
        v6 = 2 * wcslen(L"\\WindowsErrorReportingServicePort");
        if ( v6 >= 0xFFFE )
          LOWORD(v6) = -4;
        LOWORD(v24) = v6;
        WORD1(v24) = v6 + 2;
        memset_thunk_772440563353939046(v26, 0, 0x48u);
        v27 = 1400;
        v10 = WerpAllocateAndInitializeSid((unsigned int)&v17, v7, v8, v9);
        v11 = v21;
        started = v10;
        if ( v10 >= 0 )
        {
          *(_OWORD *)&v25[32] = 0;
          *(_DWORD *)v25 = 48;
          memset(&v25[8], 0, 20);
          if ( HIDWORD(SystemInformation) == -1 )
          {
            v12 = 1;
          }
          else
          {
            v12 = 0;
            v22 = -10000LL * SHIDWORD(SystemInformation);
          }
          v13 = &v22;
          if ( v12 )
            v13 = 0;
          v14 = NtAlpcConnectPort(&Handle, &v24, v25, v26, 0x20000, v21, 0, 0, 0, 0, v13);
          started = v14;
          if ( v14 >= 0 && v14 != 258 )
          {
            v23 = 1400;
            v15 = ZwAlpcSendWaitReceivePort(Handle, 0x20000, a1, 0, a2, &v23, 0, v13);
            started = v15;
            if ( v15 >= 0 && v15 != 258 )
            {
              started = 0;
              if ( *(int *)(a2 + 44) < 0 )
                started = *(_DWORD *)(a2 + 44);
            }
          }
        }
        if ( v11 )
          WerpFreeSid(v11);
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
0x1800418e4  mov     [rsp-8+arg_10], rbx
0x1800418e9  mov     [rsp-8+arg_18], rsi
0x1800418ee  push    rbp
0x1800418ef  push    rdi
0x1800418f0  push    r12
0x1800418f2  push    r14
0x1800418f4  push    r15
0x1800418f6  lea     rbp, [rsp-30h]
0x1800418fb  sub     rsp, 130h
0x180041902  mov     rax, cs:__security_cookie
0x180041909  xor     rax, rsp
0x18004190c  mov     [rbp+50h+var_30], rax
0x180041910  xorps   xmm0, xmm0
0x180041913  xor     eax, eax
0x180041915  mov     r14, rdx
0x180041918  mov     r15, rcx
0x18004191b  xor     r12d, r12d
0x18004191e  lea     rcx, [rbp+50h+var_80]; void *
0x180041922  movups  [rbp+50h+var_A0], xmm0
0x180041926  lea     edi, [rax+48h]
0x180041929  mov     [rsp+150h+Handle], r12
0x18004192e  mov     r8d, edi; Size
0x180041931  mov     [rbp+50h+var_C8], r12
0x180041935  xor     edx, edx; Val
0x180041937  movups  [rbp+50h+var_C0], xmm0
0x18004193b  movups  [rbp+50h+var_B0], xmm0
0x18004193f  movups  [rbp+50h+var_A0+0Ch], xmm0
0x180041943  call    memset$thunk$772440563353939046
0x180041948  mov     [rsp+150h+var_D8], r12
0x18004194d  mov     [rsp+150h+var_F0], r12d
0x180041952  mov     [rsp+150h+var_EC], 500h
0x180041959  mov     [rbp+50h+var_D0], r12
0x18004195d  mov     [rsp+150h+SystemInformation], r12
0x180041962  call    SignalStartWerSvc
0x180041967  mov     ebx, eax
0x180041969  test    eax, eax
0x18004196b  js      loc_180041B00
0x180041971  xor     r9d, r9d; ReturnLength
0x180041974  lea     r8d, [r12+8]; SystemInformationLength
0x180041979  lea     rdx, [rsp+150h+SystemInformation]; SystemInformation
0x18004197e  lea     ecx, [rdi+2Bh]; SystemInformationClass
0x180041981  call    NtQuerySystemInformation
0x180041986  mov     ebx, eax
0x180041988  test    eax, eax
0x18004198a  js      loc_180041B00
0x180041990  mov     ecx, dword ptr [rsp+150h+SystemInformation]
0x180041994  call    WaitForWerSvc
0x180041999  mov     ebx, eax
0x18004199b  test    eax, eax
0x18004199d  js      loc_180041B00
0x1800419a3  cmp     eax, 102h
0x1800419a8  jz      loc_180041B00
0x1800419ae  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x1800419b5  mov     qword ptr [rbp+50h+var_C0], r12
0x1800419b9  mov     qword ptr [rbp+50h+var_C0+8], rcx
0x1800419bd  call    wcslen
0x1800419c2  add     rax, rax
0x1800419c5  mov     ecx, 0FFFCh
0x1800419ca  cmp     rax, 0FFFEh
0x1800419d0  mov     r8d, edi; Size
0x1800419d3  cmovnb  rax, rcx
0x1800419d7  xor     edx, edx; Val
0x1800419d9  mov     word ptr [rbp+50h+var_C0], ax
0x1800419dd  lea     rcx, [rbp+50h+var_80]; void *
0x1800419e1  add     ax, 2
0x1800419e5  mov     word ptr [rbp+50h+var_C0+2], ax
0x1800419e9  call    memset$thunk$772440563353939046
0x1800419ee  lea     rax, [rsp+150h+var_D8]
0x1800419f3  mov     [rbp+50h+var_70], 578h
0x1800419fb  lea     rcx, [rsp+150h+var_F0]
0x180041a00  mov     [rsp+150h+var_100], rax
0x180041a05  call    WerpAllocateAndInitializeSid
0x180041a0a  mov     rdi, [rsp+150h+var_D8]
0x180041a0f  mov     ebx, eax
0x180041a11  test    eax, eax
0x180041a13  js      loc_180041AF3
0x180041a19  cmp     dword ptr [rsp+150h+SystemInformation+4], 0FFFFFFFFh
0x180041a1e  xorps   xmm0, xmm0
0x180041a21  movdqu  [rbp+50h+var_90], xmm0
0x180041a26  mov     dword ptr [rbp+50h+var_B0], 30h ; '0'
0x180041a2d  mov     qword ptr [rbp+50h+var_B0+8], r12
0x180041a31  mov     dword ptr [rbp+50h+var_A0+8], r12d
0x180041a35  mov     qword ptr [rbp+50h+var_A0], r12
0x180041a39  jz      loc_180041B3A
0x180041a3f  movsxd  rax, dword ptr [rsp+150h+SystemInformation+4]
0x180041a44  mov     dl, r12b
0x180041a47  imul    rcx, rax, 0FFFFFFFFFFFFD8F0h
0x180041a4e  mov     [rbp+50h+var_D0], rcx
0x180041a52  test    dl, dl
0x180041a54  lea     rsi, [rbp+50h+var_D0]
0x180041a58  lea     r9, [rbp+50h+var_80]
0x180041a5c  cmovnz  rsi, r12
0x180041a60  lea     r8, [rbp+50h+var_B0]
0x180041a64  mov     [rsp+150h+var_100], rsi
0x180041a69  lea     rdx, [rbp+50h+var_C0]
0x180041a6d  mov     [rsp+150h+var_108], r12
0x180041a72  lea     rcx, [rsp+150h+Handle]
0x180041a77  mov     [rsp+150h+var_110], r12
0x180041a7c  mov     [rsp+150h+var_118], r12
0x180041a81  mov     [rsp+150h+var_120], r12
0x180041a86  mov     [rsp+150h+var_128], rdi
0x180041a8b  mov     dword ptr [rsp+150h+var_130], 20000h
0x180041a93  call    NtAlpcConnectPort
0x180041a98  mov     ebx, eax
0x180041a9a  test    eax, eax
0x180041a9c  js      short loc_180041AF3
0x180041a9e  cmp     eax, 102h
0x180041aa3  jz      short loc_180041AF3
0x180041aa5  mov     rcx, [rsp+150h+Handle]
0x180041aaa  lea     rax, [rbp+50h+var_C8]
0x180041aae  mov     [rsp+150h+var_118], rsi
0x180041ab3  xor     r9d, r9d
0x180041ab6  mov     [rsp+150h+var_120], r12
0x180041abb  mov     r8, r15
0x180041abe  mov     [rsp+150h+var_128], rax
0x180041ac3  mov     edx, 20000h
0x180041ac8  mov     [rsp+150h+var_130], r14
0x180041acd  mov     [rbp+50h+var_C8], 578h
0x180041ad5  call    ZwAlpcSendWaitReceivePort
0x180041ada  mov     ebx, eax
0x180041adc  test    eax, eax
0x180041ade  js      short loc_180041AF3
0x180041ae0  cmp     eax, 102h
0x180041ae5  jz      short loc_180041AF3
0x180041ae7  cmp     [r14+2Ch], r12d
0x180041aeb  mov     ebx, r12d
0x180041aee  cmovl   ebx, [r14+2Ch]
0x180041af3  test    rdi, rdi
0x180041af6  jz      short loc_180041B00
0x180041af8  mov     rcx, rdi
0x180041afb  call    WerpFreeSid
0x180041b00  mov     rcx, [rsp+150h+Handle]; Handle
0x180041b05  test    rcx, rcx
0x180041b08  jz      short loc_180041B0F
0x180041b0a  call    NtClose
0x180041b0f  mov     eax, ebx
0x180041b11  mov     rcx, [rbp+50h+var_30]
0x180041b15  xor     rcx, rsp; StackCookie
0x180041b18  call    __security_check_cookie
0x180041b1d  lea     r11, [rsp+150h+var_20]
0x180041b25  mov     rbx, [r11+40h]
0x180041b29  mov     rsi, [r11+48h]
0x180041b2d  mov     rsp, r11
0x180041b30  pop     r15
0x180041b32  pop     r14
0x180041b34  pop     r12
0x180041b36  pop     rdi
0x180041b37  pop     rbp
0x180041b38  retn
0x180041b3a  mov     dl, 1
0x180041b3c  jmp     loc_180041A52
```
