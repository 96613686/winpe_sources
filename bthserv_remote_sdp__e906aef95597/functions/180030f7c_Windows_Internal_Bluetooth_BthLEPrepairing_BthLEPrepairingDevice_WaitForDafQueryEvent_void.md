# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)

- ea: `0x180030f7c`
- end: `0x180031200`
- name: `?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ`
- size: `644`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002e77c`
- `0x18002ff10`
- `0x180030270`

## callees

- `0x1800120b8`
- `0x180012384`
- `0x18001268c`
- `0x18002c9b8`
- `0x180030f7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031053`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180031027`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180031027`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(
        HANDLE *this)
{
  char v2; // di
  bool v3; // dl
  DWORD v4; // eax
  int v5; // edx
  int v6; // r8d
  signed int LastError; // eax
  signed int v8; // ebx
  _BYTE *v9; // rcx
  int v10; // eax
  bool v11; // cf
  int v13; // [rsp+20h] [rbp-68h]
  HANDLE Handles[2]; // [rsp+60h] [rbp-28h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  Handles[0] = this[257];
  Handles[1] = this[256];
  while ( 1 )
  {
    v4 = WaitForMultipleObjects(2u, Handles, 0, 0x7530u);
    switch ( v4 )
    {
      case 0u:
        v8 = -2147467260;
        goto LABEL_42;
      case 1u:
        v8 = *((_DWORD *)this + 38);
        v9 = WPP_GLOBAL_Control;
LABEL_39:
        if ( !v8 )
        {
          v10 = 0;
          v11 = v9[25] < 5u;
          goto LABEL_44;
        }
        goto LABEL_43;
      case 0x102u:
        v8 = -2147023436;
        v9 = WPP_GLOBAL_Control;
        LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
        LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !(_BYTE)v5 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_43;
LABEL_30:
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v9 + 2), v5, v6, *((_QWORD *)v9 + 5));
LABEL_42:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_43;
    }
    if ( v4 != -1 )
      break;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v13);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v8 < 0 )
      goto LABEL_39;
  }
  v8 = -2147418113;
  v9 = WPP_GLOBAL_Control;
  LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_30;
LABEL_43:
  v10 = 0;
  v11 = v9[25] < 2u;
LABEL_44:
  if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v10) = !v11, !v10) )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = v2;
    LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v9 + 2), v5, v6, *((_QWORD *)v9 + 5));
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030f7c  mov     [rsp+arg_0], rbx
0x180030f81  mov     [rsp+arg_8], rsi
0x180030f86  mov     [rsp+arg_10], rdi
0x180030f8b  push    r13
0x180030f8d  push    r14
0x180030f8f  push    r15
0x180030f91  sub     rsp, 70h
0x180030f95  mov     rsi, rcx
0x180030f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f9f  lea     r14, WPP_GLOBAL_Control
0x180030fa6  mov     edi, 1
0x180030fab  cmp     rcx, r14
0x180030fae  jz      short loc_180030FBB
0x180030fb0  cmp     byte ptr [rcx+19h], 5
0x180030fb4  jb      short loc_180030FBB
0x180030fb6  mov     dl, dil
0x180030fb9  jmp     short loc_180030FBD
0x180030fbb  xor     dl, dl
0x180030fbd  lea     r15, WPP_RECORDER_INITIALIZED
0x180030fc4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180030fcb  lea     r13, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180030fd2  setnz   r8b
0x180030fd6  test    dl, dl
0x180030fd8  jnz     short loc_180030FDF
0x180030fda  test    r8b, r8b
0x180030fdd  jz      short loc_180030FFD
0x180030fdf  mov     r9, [rcx+28h]
0x180030fe3  mov     rcx, [rcx+10h]
0x180030fe7  mov     [rsp+88h+var_40], rsi
0x180030fec  mov     [rsp+88h+var_50], r13
0x180030ff1  mov     [rsp+88h+var_58], 55h ; 'U'
0x180030ff8  call    WPP_RECORDER_AND_TRACE_SF_si
0x180030ffd  mov     rax, [rsi+808h]
0x180031004  mov     [rsp+88h+Handles], rax
0x180031009  mov     rax, [rsi+800h]
0x180031010  mov     [rsp+88h+var_20], rax
0x180031015  xor     r8d, r8d; bWaitAll
0x180031018  lea     rdx, [rsp+88h+Handles]; lpHandles
0x18003101d  mov     r9d, 7530h; dwMilliseconds
0x180031023  lea     ecx, [r8+2]; nCount
0x180031027  call    cs:__imp_WaitForMultipleObjects
0x18003102e  nop     dword ptr [rax+rax+00h]
0x180031033  test    eax, eax
0x180031035  jz      loc_180031187
0x18003103b  cmp     eax, edi
0x18003103d  jz      loc_18003116E
0x180031043  cmp     eax, 102h
0x180031048  jz      loc_180031126
0x18003104e  cmp     eax, 0FFFFFFFFh
0x180031051  jnz     short loc_1800310D1
0x180031053  call    cs:__imp_GetLastError
0x18003105a  nop     dword ptr [rax+rax+00h]
0x18003105f  mov     ebx, eax
0x180031061  test    eax, eax
0x180031063  jle     short loc_18003106E
0x180031065  movzx   ebx, ax
0x180031068  or      ebx, 80070000h
0x18003106e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031075  cmp     rcx, r14
0x180031078  jz      short loc_180031085
0x18003107a  cmp     byte ptr [rcx+19h], 2
0x18003107e  jb      short loc_180031085
0x180031080  mov     dl, dil
0x180031083  jmp     short loc_180031087
0x180031085  xor     dl, dl
0x180031087  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003108e  setnz   r8b
0x180031092  test    dl, dl
0x180031094  jnz     short loc_18003109B
0x180031096  test    r8b, r8b
0x180031099  jz      short loc_1800310C4
0x18003109b  mov     r9, [rcx+28h]
0x18003109f  mov     rcx, [rcx+10h]
0x1800310a3  mov     [rsp+88h+var_38], ebx
0x1800310a7  or      dword ptr [rsp+88h+var_40], 0FFFFFFFFh
0x1800310ac  mov     [rsp+88h+var_50], r13
0x1800310b1  mov     [rsp+88h+var_58], 58h ; 'X'
0x1800310b8  call    WPP_RECORDER_AND_TRACE_SF_sdd
0x1800310bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310c4  test    ebx, ebx
0x1800310c6  jns     loc_180031015
0x1800310cc  jmp     loc_18003117B
0x1800310d1  mov     ebx, 8000FFFFh
0x1800310d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800310dd  cmp     rcx, r14
0x1800310e0  jz      short loc_1800310ED
0x1800310e2  cmp     byte ptr [rcx+19h], 2
0x1800310e6  jb      short loc_1800310ED
0x1800310e8  mov     dl, dil
0x1800310eb  jmp     short loc_1800310EF
0x1800310ed  xor     dl, dl
0x1800310ef  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800310f6  setnz   r8b
0x1800310fa  test    dl, dl
0x1800310fc  jnz     short loc_180031107
0x1800310fe  test    r8b, r8b
0x180031101  jz      loc_180031193
0x180031107  mov     dword ptr [rsp+88h+var_40], eax
0x18003110b  mov     [rsp+88h+var_50], r13
0x180031110  mov     [rsp+88h+var_58], 59h ; 'Y'
0x180031117  mov     r9, [rcx+28h]
0x18003111b  mov     rcx, [rcx+10h]
0x18003111f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180031124  jmp     short loc_18003118C
0x180031126  mov     ebx, 800705B4h
0x18003112b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031132  cmp     rcx, r14
0x180031135  jz      short loc_180031142
0x180031137  cmp     byte ptr [rcx+19h], 2
0x18003113b  jb      short loc_180031142
0x18003113d  mov     dl, dil
0x180031140  jmp     short loc_180031144
0x180031142  xor     dl, dl
0x180031144  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003114b  setnz   r8b
0x18003114f  test    dl, dl
0x180031151  jnz     short loc_180031158
0x180031153  test    r8b, r8b
0x180031156  jz      short loc_180031193
0x180031158  mov     dword ptr [rsp+88h+var_40], 102h
0x180031160  mov     [rsp+88h+var_50], r13
0x180031165  mov     [rsp+88h+var_58], 57h ; 'W'
0x18003116c  jmp     short loc_180031117
0x18003116e  mov     ebx, [rsi+98h]
0x180031174  mov     rcx, cs:WPP_GLOBAL_Control
0x18003117b  test    ebx, ebx
0x18003117d  jnz     short loc_180031193
0x18003117f  xor     eax, eax
0x180031181  cmp     byte ptr [rcx+19h], 5
0x180031185  jmp     short loc_180031199
0x180031187  mov     ebx, 80004004h
0x18003118c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031193  xor     eax, eax
0x180031195  cmp     byte ptr [rcx+19h], 2
0x180031199  setnb   al
0x18003119c  cmp     rcx, r14
0x18003119f  jz      short loc_1800311A5
0x1800311a1  test    eax, eax
0x1800311a3  jnz     short loc_1800311A8
0x1800311a5  xor     dil, dil
0x1800311a8  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800311af  setnz   r8b
0x1800311b3  test    dil, dil
0x1800311b6  jnz     short loc_1800311BD
0x1800311b8  test    r8b, r8b
0x1800311bb  jz      short loc_1800311E2
0x1800311bd  mov     r9, [rcx+28h]
0x1800311c1  mov     dl, dil
0x1800311c4  mov     rcx, [rcx+10h]
0x1800311c8  mov     [rsp+88h+var_38], ebx
0x1800311cc  mov     [rsp+88h+var_40], rsi
0x1800311d1  mov     [rsp+88h+var_50], r13
0x1800311d6  mov     [rsp+88h+var_58], 5Ah ; 'Z'
0x1800311dd  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x1800311e2  lea     r11, [rsp+88h+var_18]
0x1800311e7  mov     eax, ebx
0x1800311e9  mov     rbx, [r11+20h]
0x1800311ed  mov     rsi, [r11+28h]
0x1800311f1  mov     rdi, [r11+30h]
0x1800311f5  mov     rsp, r11
0x1800311f8  pop     r15
0x1800311fa  pop     r14
0x1800311fc  pop     r13
0x1800311fe  retn
```
