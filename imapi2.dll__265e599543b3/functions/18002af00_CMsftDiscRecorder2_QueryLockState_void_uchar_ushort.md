# CMsftDiscRecorder2::QueryLockState(void *,uchar *,ushort * *)

- ea: `0x18002af00`
- end: `0x18002b295`
- name: `?QueryLockState@CMsftDiscRecorder2@@AEAAJPEAXPEAEPEAPEAG@Z`
- size: `917`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, void *, unsigned __int8 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005100`
- `0x18002c400`

## callees

- `0x18000908c`
- `0x18000f740`
- `0x1800140f4`
- `0x180016778`
- `0x18002af00`
- `0x18004984a`
- `0x180049880`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b228`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b228`
- `OLEAUT32!__imp_SysFreeString` at `0x18002af61`
- `OLEAUT32!__imp_SysFreeString` at `0x18002af61`
- `KERNEL32!LocalAlloc` at `0x18002afb1`
- `KERNEL32!LocalAlloc` at `0x18002afb1`
- `KERNEL32!LocalFree` at `0x18002af6f`
- `KERNEL32!LocalFree` at `0x18002af6f`
- `KERNEL32!GetLastError` at `0x18002b042`
- `KERNEL32!GetLastError` at `0x18002b0aa`
- `KERNEL32!GetLastError` at `0x18002b042`
- `KERNEL32!GetLastError` at `0x18002b0aa`
- `KERNEL32!CreateEventW` at `0x18002afdd`
- `KERNEL32!CreateEventW` at `0x18002afdd`
- `KERNEL32!DeviceIoControl` at `0x18002b032`
- `KERNEL32!DeviceIoControl` at `0x18002b032`
- `KERNEL32!GetOverlappedResult` at `0x18002b09c`
- `KERNEL32!GetOverlappedResult` at `0x18002b09c`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::QueryLockState(
        CMsftDiscRecorder2 *this,
        void *a2,
        unsigned __int8 *a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v7; // r14
  _WORD *v8; // rdi
  int v9; // ebx
  void **v10; // rdx
  DWORD LastError; // eax
  int v13; // edx
  Imapi2Utility *v14; // rcx
  unsigned int LastErrorAsHresultForceFailure; // eax
  unsigned __int8 v16; // al
  _WORD *v17; // rdx
  char *i; // rcx
  __int16 v19; // ax
  DWORD BytesReturned; // [rsp+40h] [rbp-69h] BYREF
  __int64 InBuffer; // [rsp+48h] [rbp-61h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int8 OutBuffer; // [rsp+70h] [rbp-39h] BYREF
  char v24; // [rsp+71h] [rbp-38h] BYREF

  BytesReturned = 0;
  memset_0(&OutBuffer, 0, 0x41u);
  v7 = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( !a3 )
  {
    v8 = 0;
    v9 = -2147467261;
    goto LABEL_3;
  }
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = -2147024882;
  v8 = LocalAlloc(0x40u, 0x82u);
  *(_OWORD *)&Overlapped.Internal = 0;
  if ( v8 )
    v9 = 0;
  Overlapped.Pointer = 0;
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( !Overlapped.hEvent )
    goto LABEL_55;
  if ( !v8 )
    goto LABEL_3;
  InBuffer = 0;
  if ( DeviceIoControl(a2, 0x2C05Cu, &InBuffer, 8u, &OutBuffer, 0x41u, &BytesReturned, &Overlapped) )
    goto LABEL_43;
  if ( GetLastError() == 997 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 255, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    if ( GetOverlappedResult(a2, &Overlapped, &BytesReturned, 1) )
    {
LABEL_43:
      v9 = 0;
      goto LABEL_44;
    }
  }
  LastError = GetLastError();
  switch ( LastError )
  {
    case 0x79u:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 256, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      }
      v9 = -1062600179;
      goto LABEL_3;
    case 6u:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 257, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      }
      v9 = -2147024890;
      goto LABEL_3;
    case 0x37u:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 258, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
      }
      v9 = -2147024841;
      goto LABEL_3;
  }
  LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(v14, v13);
  v9 = LastErrorAsHresultForceFailure;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      259,
      &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
      LastErrorAsHresultForceFailure);
  }
  if ( v9 >= 0 )
  {
LABEL_44:
    v16 = OutBuffer;
    if ( OutBuffer && a4 && v24 )
    {
      v17 = v8;
      for ( i = &v24; *i; ++i )
      {
        v19 = (unsigned __int8)*i;
        *v17++ = v19;
      }
      v8[64] = 0;
      v7 = SysAllocString(v8);
      if ( !v7 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 260, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        }
LABEL_55:
        v9 = -2147024882;
        goto LABEL_3;
      }
      v16 = OutBuffer;
    }
    *a3 = v16;
    if ( v16 && a4 )
      *a4 = v7;
    goto LABEL_4;
  }
LABEL_3:
  SysFreeString(0);
  if ( v8 )
LABEL_4:
    LocalFree(v8);
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)&Overlapped.hEvent, v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002af00  push    rbp
0x18002af02  push    rbx
0x18002af03  push    rsi
0x18002af04  push    rdi
0x18002af05  push    r12
0x18002af07  push    r14
0x18002af09  push    r15
0x18002af0b  lea     rbp, [rsp-27h]
0x18002af10  sub     rsp, 0D0h
0x18002af17  mov     rax, cs:__security_cookie
0x18002af1e  xor     rax, rsp
0x18002af21  mov     [rbp+57h+var_40], rax
0x18002af25  mov     r12, rdx
0x18002af28  mov     [rbp+57h+BytesReturned], 0
0x18002af2f  xor     edx, edx; Val
0x18002af31  lea     rcx, [rbp+57h+OutBuffer]; void *
0x18002af35  mov     r15, r8
0x18002af38  mov     rsi, r9
0x18002af3b  lea     r8d, [rdx+41h]; Size
0x18002af3f  call    memset_0
0x18002af44  xorps   xmm0, xmm0
0x18002af47  xor     r14d, r14d
0x18002af4a  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002af4e  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002af52  test    r15, r15
0x18002af55  jnz     short loc_18002AF9E
0x18002af57  xor     edi, edi
0x18002af59  mov     ebx, 80004003h
0x18002af5e  mov     rcx, r14; bstrString
0x18002af61  call    cs:__imp_SysFreeString
0x18002af67  test    rdi, rdi
0x18002af6a  jz      short loc_18002AF75
0x18002af6c  mov     rcx, rdi; hMem
0x18002af6f  call    cs:__imp_LocalFree
0x18002af75  lea     rcx, [rbp+57h+Overlapped.hEvent]; this
0x18002af79  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x18002af7e  mov     eax, ebx
0x18002af80  mov     rcx, [rbp+57h+var_40]
0x18002af84  xor     rcx, rsp; StackCookie
0x18002af87  call    __security_check_cookie
0x18002af8c  add     rsp, 0D0h
0x18002af93  pop     r15
0x18002af95  pop     r14
0x18002af97  pop     r12
0x18002af99  pop     rdi
0x18002af9a  pop     rsi
0x18002af9b  pop     rbx
0x18002af9c  pop     rbp
0x18002af9d  retn
0x18002af9e  mov     [r15], r14b
0x18002afa1  test    rsi, rsi
0x18002afa4  jz      short loc_18002AFA9
0x18002afa6  mov     [rsi], r14
0x18002afa9  mov     edx, 82h; uBytes
0x18002afae  lea     ecx, [rdx-42h]; uFlags
0x18002afb1  call    cs:__imp_LocalAlloc
0x18002afb7  xorps   xmm0, xmm0
0x18002afba  mov     ebx, 8007000Eh
0x18002afbf  mov     rdi, rax
0x18002afc2  xor     eax, eax
0x18002afc4  test    rdi, rdi
0x18002afc7  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18002afcb  cmovnz  ebx, eax
0x18002afce  xor     r9d, r9d; lpName
0x18002afd1  xor     r8d, r8d; bInitialState
0x18002afd4  lea     edx, [rax+1]; bManualReset
0x18002afd7  xor     ecx, ecx; lpEventAttributes
0x18002afd9  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18002afdd  call    cs:__imp_CreateEventW
0x18002afe3  mov     [rbp+57h+Overlapped.hEvent], rax
0x18002afe7  test    rax, rax
0x18002afea  jz      loc_18002B26C
0x18002aff0  test    rdi, rdi
0x18002aff3  jz      loc_18002AF5E
0x18002aff9  lea     rax, [rbp+57h+Overlapped]
0x18002affd  mov     [rbp+57h+InBuffer], r14
0x18002b001  mov     [rsp+100h+lpOverlapped], rax; lpOverlapped
0x18002b006  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18002b00a  lea     rax, [rbp+57h+BytesReturned]
0x18002b00e  mov     r9d, 8; nInBufferSize
0x18002b014  mov     [rsp+100h+lpBytesReturned], rax; lpBytesReturned
0x18002b019  mov     edx, 2C05Ch; dwIoControlCode
0x18002b01e  lea     rax, [rbp+57h+OutBuffer]
0x18002b022  mov     [rsp+100h+nOutBufferSize], 41h ; 'A'; nOutBufferSize
0x18002b02a  mov     rcx, r12; hDevice
0x18002b02d  mov     [rsp+100h+lpOutBuffer], rax; lpOutBuffer
0x18002b032  call    cs:__imp_DeviceIoControl
0x18002b038  mov     bl, 3
0x18002b03a  test    eax, eax
0x18002b03c  jnz     loc_18002B1E2
0x18002b042  call    cs:__imp_GetLastError
0x18002b048  cmp     eax, 3E5h
0x18002b04d  jnz     short loc_18002B0AA
0x18002b04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b056  lea     rax, WPP_GLOBAL_Control
0x18002b05d  cmp     rcx, rax
0x18002b060  jz      short loc_18002B08B
0x18002b062  test    byte ptr [rcx+0BCh], 4
0x18002b069  jz      short loc_18002B08B
0x18002b06b  cmp     [rcx+0B9h], bl
0x18002b071  jb      short loc_18002B08B
0x18002b073  mov     rcx, [rcx+0B0h]
0x18002b07a  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b081  mov     edx, 0FFh
0x18002b086  call    WPP_SF_
0x18002b08b  mov     r9d, 1; bWait
0x18002b091  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x18002b095  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18002b099  mov     rcx, r12; hFile
0x18002b09c  call    cs:__imp_GetOverlappedResult
0x18002b0a2  test    eax, eax
0x18002b0a4  jnz     loc_18002B1E2
0x18002b0aa  call    cs:__imp_GetLastError
0x18002b0b0  cmp     eax, 79h ; 'y'
0x18002b0b3  jnz     short loc_18002B0FB
0x18002b0b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0bc  lea     rax, WPP_GLOBAL_Control
0x18002b0c3  cmp     rcx, rax
0x18002b0c6  jz      short loc_18002B0F1
0x18002b0c8  test    byte ptr [rcx+0BCh], 4
0x18002b0cf  jz      short loc_18002B0F1
0x18002b0d1  cmp     [rcx+0B9h], bl
0x18002b0d7  jb      short loc_18002B0F1
0x18002b0d9  mov     rcx, [rcx+0B0h]
0x18002b0e0  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b0e7  mov     edx, 100h
0x18002b0ec  call    WPP_SF_
0x18002b0f1  mov     ebx, 0C0AA020Dh
0x18002b0f6  jmp     loc_18002AF5E
0x18002b0fb  cmp     eax, 6
0x18002b0fe  jnz     short loc_18002B146
0x18002b100  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b107  lea     rax, WPP_GLOBAL_Control
0x18002b10e  cmp     rcx, rax
0x18002b111  jz      short loc_18002B13C
0x18002b113  test    byte ptr [rcx+0BCh], 4
0x18002b11a  jz      short loc_18002B13C
0x18002b11c  cmp     [rcx+0B9h], bl
0x18002b122  jb      short loc_18002B13C
0x18002b124  mov     rcx, [rcx+0B0h]
0x18002b12b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b132  mov     edx, 101h
0x18002b137  call    WPP_SF_
0x18002b13c  mov     ebx, 80070006h
0x18002b141  jmp     loc_18002AF5E
0x18002b146  cmp     eax, 37h ; '7'
0x18002b149  jnz     short loc_18002B191
0x18002b14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b152  lea     rax, WPP_GLOBAL_Control
0x18002b159  cmp     rcx, rax
0x18002b15c  jz      short loc_18002B187
0x18002b15e  test    byte ptr [rcx+0BCh], 4
0x18002b165  jz      short loc_18002B187
0x18002b167  cmp     [rcx+0B9h], bl
0x18002b16d  jb      short loc_18002B187
0x18002b16f  mov     rcx, [rcx+0B0h]
0x18002b176  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b17d  mov     edx, 102h
0x18002b182  call    WPP_SF_
0x18002b187  mov     ebx, 80070037h
0x18002b18c  jmp     loc_18002AF5E
0x18002b191  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x18002b196  mov     ebx, eax
0x18002b198  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b19f  lea     r12, WPP_GLOBAL_Control
0x18002b1a6  cmp     rcx, r12
0x18002b1a9  jz      short loc_18002B1D8
0x18002b1ab  test    byte ptr [rcx+0BCh], 4
0x18002b1b2  jz      short loc_18002B1D8
0x18002b1b4  cmp     byte ptr [rcx+0B9h], 3
0x18002b1bb  jb      short loc_18002B1D8
0x18002b1bd  mov     rcx, [rcx+0B0h]
0x18002b1c4  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b1cb  mov     edx, 103h
0x18002b1d0  mov     r9d, eax
0x18002b1d3  call    WPP_SF_d
0x18002b1d8  test    ebx, ebx
0x18002b1da  js      loc_18002AF5E
0x18002b1e0  jmp     short loc_18002B1EB
0x18002b1e2  xor     ebx, ebx
0x18002b1e4  lea     r12, WPP_GLOBAL_Control
0x18002b1eb  mov     al, [rbp+57h+OutBuffer]
0x18002b1ee  test    al, al
0x18002b1f0  jz      loc_18002B279
0x18002b1f6  test    rsi, rsi
0x18002b1f9  jz      short loc_18002B279
0x18002b1fb  cmp     [rbp+57h+var_8F], r14b
0x18002b1ff  jz      short loc_18002B279
0x18002b201  mov     rdx, rdi
0x18002b204  lea     rcx, [rbp+57h+var_8F]
0x18002b208  cmp     [rcx], r14b
0x18002b20b  jz      short loc_18002B21C
0x18002b20d  movzx   eax, byte ptr [rcx]
0x18002b210  inc     rcx
0x18002b213  mov     [rdx], ax
0x18002b216  add     rdx, 2
0x18002b21a  jmp     short loc_18002B208
0x18002b21c  xor     eax, eax
0x18002b21e  mov     rcx, rdi; psz
0x18002b221  mov     [rdi+80h], ax
0x18002b228  call    cs:__imp_SysAllocString
0x18002b22e  mov     r14, rax
0x18002b231  test    rax, rax
0x18002b234  jnz     short loc_18002B276
0x18002b236  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b23d  cmp     rcx, r12
0x18002b240  jz      short loc_18002B26C
0x18002b242  test    byte ptr [rcx+0BCh], 4
0x18002b249  jz      short loc_18002B26C
0x18002b24b  cmp     byte ptr [rcx+0B9h], 3
0x18002b252  jb      short loc_18002B26C
0x18002b254  mov     rcx, [rcx+0B0h]
0x18002b25b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x18002b262  mov     edx, 104h
0x18002b267  call    WPP_SF_
0x18002b26c  mov     ebx, 8007000Eh
0x18002b271  jmp     loc_18002AF5E
0x18002b276  mov     al, [rbp+57h+OutBuffer]
0x18002b279  mov     [r15], al
0x18002b27c  test    al, al
0x18002b27e  jz      loc_18002AF6C
0x18002b284  test    rsi, rsi
0x18002b287  jz      loc_18002AF6C
0x18002b28d  mov     [rsi], r14
0x18002b290  jmp     loc_18002AF6C
```
