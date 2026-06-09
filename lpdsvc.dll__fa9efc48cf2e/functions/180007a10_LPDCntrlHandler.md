# LPDCntrlHandler

- ea: `0x180007a10`
- end: `0x180007c06`
- name: `LPDCntrlHandler`
- size: `502`
- prototype: `void __fastcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x180007a10`
- `0x1800082e8`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180007a28`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180007a28`
- `api-ms-win-crt-time-l1-1-0!_ctime64` at `0x180007a4c`
- `api-ms-win-crt-time-l1-1-0!_ctime64` at `0x180007a4c`
- `KERNEL32!SetEvent` at `0x180007ba9`
- `KERNEL32!SetEvent` at `0x180007ba9`
- `ADVAPI32!SetServiceStatus` at `0x180007b8e`
- `ADVAPI32!SetServiceStatus` at `0x180007b8e`

## pseudocode

```c
void __fastcall LPDCntrlHandler(DWORD dwControl)
{
  int v2; // edi
  _QWORD *v3; // rcx
  char *v4; // rax
  int v5; // edx
  int v6; // r8d
  DWORD v7; // ebx
  DWORD v8; // ebx
  DWORD v9; // ebx
  int v10; // ebx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __time64_t Time; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  Time = 0;
  _time64(&Time);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v4 = _ctime64(&Time);
    WPP_SF_ds(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, dwControl, (__int64)v4);
    v3 = WPP_GLOBAL_Control;
  }
  v7 = dwControl - 1;
  if ( !v7 )
  {
    if ( v3 == &WPP_GLOBAL_Control )
    {
LABEL_30:
      ssSvcStatusGLB.dwCheckPoint = 0;
      v2 = 1;
      ssSvcStatusGLB.dwCurrentState = 3;
      goto LABEL_31;
    }
    if ( (*((_BYTE *)v3 + 28) & 2) != 0 )
    {
      WPP_SF_(v3[2], 25, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
LABEL_27:
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
      WPP_SF_(v3[2], 26, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
    goto LABEL_30;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
      WPP_SF_(v3[2], 27, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
    ssSvcStatusGLB.dwCurrentState = 7;
    goto LABEL_31;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
      WPP_SF_(v3[2], 28, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
    ssSvcStatusGLB.dwCurrentState = 4;
    goto LABEL_31;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    if ( v10 != 1 )
    {
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
      {
        v11 = 30;
LABEL_12:
        WPP_SF_(v3[2], v11, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
        goto LABEL_31;
      }
      goto LABEL_31;
    }
    goto LABEL_27;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
  {
    v11 = 29;
    goto LABEL_12;
  }
LABEL_31:
  SetServiceStatus(hSvcHandleGLB, &ssSvcStatusGLB);
  if ( !v2 )
  {
LABEL_35:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_36;
  }
  fShuttingDownGLB = 1;
  SetEvent(hEventShutdownGLB);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids,
      (unsigned int)fShuttingDownGLB);
    goto LABEL_35;
  }
LABEL_36:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_(v12[2], 32, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids);
}

```

## disassembly

```asm
0x180007a10  push    rbx
0x180007a12  push    rsi
0x180007a13  push    rdi
0x180007a14  push    r14
0x180007a16  sub     rsp, 38h
0x180007a1a  mov     ebx, ecx
0x180007a1c  xor     edi, edi
0x180007a1e  lea     rcx, [rsp+58h+Time]; Time
0x180007a23  mov     [rsp+58h+Time], rdi
0x180007a28  call    cs:__imp__time64
0x180007a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a35  lea     rsi, WPP_GLOBAL_Control
0x180007a3c  cmp     rcx, rsi
0x180007a3f  jz      short loc_180007A71
0x180007a41  test    byte ptr [rcx+1Ch], 2
0x180007a45  jz      short loc_180007A71
0x180007a47  lea     rcx, [rsp+58h+Time]; Time
0x180007a4c  call    cs:__imp__ctime64
0x180007a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a59  mov     r9d, ebx
0x180007a5c  mov     [rsp+58h+var_38], rax
0x180007a61  mov     rcx, [rcx+10h]
0x180007a65  call    WPP_SF_ds
0x180007a6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a71  lea     r14, WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids
0x180007a78  sub     ebx, 1
0x180007a7b  jz      loc_180007B2C
0x180007a81  sub     ebx, 1
0x180007a84  jz      short loc_180007B04
0x180007a86  sub     ebx, 1
0x180007a89  jz      short loc_180007ADC
0x180007a8b  sub     ebx, 1
0x180007a8e  jz      short loc_180007AC2
0x180007a90  cmp     ebx, 1
0x180007a93  jz      loc_180007B4F
0x180007a99  cmp     rcx, rsi
0x180007a9c  jz      loc_180007B80
0x180007aa2  test    byte ptr [rcx+1Ch], 2
0x180007aa6  jz      loc_180007B80
0x180007aac  mov     edx, 1Eh
0x180007ab1  mov     rcx, [rcx+10h]
0x180007ab5  mov     r8, r14
0x180007ab8  call    WPP_SF_
0x180007abd  jmp     loc_180007B80
0x180007ac2  cmp     rcx, rsi
0x180007ac5  jz      loc_180007B80
0x180007acb  test    byte ptr [rcx+1Ch], 2
0x180007acf  jz      loc_180007B80
0x180007ad5  mov     edx, 1Dh
0x180007ada  jmp     short loc_180007AB1
0x180007adc  cmp     rcx, rsi
0x180007adf  jz      short loc_180007AF8
0x180007ae1  test    byte ptr [rcx+1Ch], 2
0x180007ae5  jz      short loc_180007AF8
0x180007ae7  mov     rcx, [rcx+10h]
0x180007aeb  mov     edx, 1Ch
0x180007af0  mov     r8, r14
0x180007af3  call    WPP_SF_
0x180007af8  mov     cs:ssSvcStatusGLB.dwCurrentState, 4
0x180007b02  jmp     short loc_180007B80
0x180007b04  cmp     rcx, rsi
0x180007b07  jz      short loc_180007B20
0x180007b09  test    byte ptr [rcx+1Ch], 2
0x180007b0d  jz      short loc_180007B20
0x180007b0f  mov     rcx, [rcx+10h]
0x180007b13  mov     edx, 1Bh
0x180007b18  mov     r8, r14
0x180007b1b  call    WPP_SF_
0x180007b20  mov     cs:ssSvcStatusGLB.dwCurrentState, 7
0x180007b2a  jmp     short loc_180007B80
0x180007b2c  cmp     rcx, rsi
0x180007b2f  jz      short loc_180007B6B
0x180007b31  test    byte ptr [rcx+1Ch], 2
0x180007b35  jz      short loc_180007B4F
0x180007b37  mov     rcx, [rcx+10h]
0x180007b3b  mov     edx, 19h
0x180007b40  mov     r8, r14
0x180007b43  call    WPP_SF_
0x180007b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b4f  cmp     rcx, rsi
0x180007b52  jz      short loc_180007B6B
0x180007b54  test    byte ptr [rcx+1Ch], 2
0x180007b58  jz      short loc_180007B6B
0x180007b5a  mov     rcx, [rcx+10h]
0x180007b5e  mov     edx, 1Ah
0x180007b63  mov     r8, r14
0x180007b66  call    WPP_SF_
0x180007b6b  mov     cs:ssSvcStatusGLB.dwCheckPoint, edi
0x180007b71  mov     edi, 1
0x180007b76  mov     cs:ssSvcStatusGLB.dwCurrentState, 3
0x180007b80  mov     rcx, cs:hSvcHandleGLB; hServiceStatus
0x180007b87  lea     rdx, ssSvcStatusGLB; lpServiceStatus
0x180007b8e  call    cs:__imp_SetServiceStatus
0x180007b94  test    edi, edi
0x180007b96  jz      short loc_180007BD9
0x180007b98  mov     rcx, cs:hEventShutdownGLB; hEvent
0x180007b9f  mov     cs:fShuttingDownGLB, 1
0x180007ba9  call    cs:__imp_SetEvent
0x180007baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bb6  cmp     rcx, rsi
0x180007bb9  jz      short loc_180007BFC
0x180007bbb  test    byte ptr [rcx+1Ch], 2
0x180007bbf  jz      short loc_180007BE0
0x180007bc1  mov     r9d, cs:fShuttingDownGLB
0x180007bc8  mov     edx, 1Fh
0x180007bcd  mov     rcx, [rcx+10h]
0x180007bd1  mov     r8, r14
0x180007bd4  call    WPP_SF_d
0x180007bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007be0  cmp     rcx, rsi
0x180007be3  jz      short loc_180007BFC
0x180007be5  test    byte ptr [rcx+1Ch], 1
0x180007be9  jz      short loc_180007BFC
0x180007beb  mov     rcx, [rcx+10h]
0x180007bef  mov     edx, 20h ; ' '
0x180007bf4  mov     r8, r14
0x180007bf7  call    WPP_SF_
0x180007bfc  add     rsp, 38h
0x180007c00  pop     r14
0x180007c02  pop     rdi
0x180007c03  pop     rsi
0x180007c04  pop     rbx
0x180007c05  retn
```
