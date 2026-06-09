# CMsftDiscRecorder2::SaferDeviceIoControl(void * const,ulong,void *,ulong,void *,ulong,ulong *)

- ea: `0x180005100`
- end: `0x1800053e1`
- name: `?SaferDeviceIoControl@CMsftDiscRecorder2@@AEAA?BJQEAXKPEAXK1KPEAK@Z`
- size: `737`
- prototype: `int(CMsftDiscRecorder2 *__hidden this, void *const, unsigned int, void *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1800036f0`
- `0x180003b00`
- `0x180004af0`
- `0x18000f970`
- `0x180028d20`
- `0x1800292e0`
- `0x180029530`
- `0x18002ad98`

## callees

- `0x180005100`
- `0x18000f740`
- `0x1800140f4`
- `0x180016778`
- `0x18002af00`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800051ce`
- `KERNEL32!CloseHandle` at `0x1800051ce`
- `KERNEL32!GetLastError` at `0x1800051de`
- `KERNEL32!GetLastError` at `0x180005208`
- `KERNEL32!GetLastError` at `0x180005271`
- `KERNEL32!GetLastError` at `0x1800051de`
- `KERNEL32!GetLastError` at `0x180005208`
- `KERNEL32!GetLastError` at `0x180005271`
- `KERNEL32!CreateEventW` at `0x18000512f`
- `KERNEL32!CreateEventW` at `0x18000512f`
- `KERNEL32!DeviceIoControl` at `0x180005192`
- `KERNEL32!DeviceIoControl` at `0x180005192`
- `KERNEL32!GetOverlappedResult` at `0x1800052c9`
- `KERNEL32!GetOverlappedResult` at `0x1800052c9`

## pseudocode

```c
__int64 __fastcall CMsftDiscRecorder2::SaferDeviceIoControl(
        CMsftDiscRecorder2 *this,
        void *const a2,
        DWORD a3,
        void *a4,
        DWORD nInBufferSize,
        void *lpOutBuffer,
        DWORD nOutBufferSize,
        unsigned int *lpNumberOfBytesTransferred)
{
  DWORD *v11; // rbp
  BOOL OverlappedResult; // edi
  unsigned int LastErrorAsHresultForceFailure; // ebx
  DWORD LastError; // eax
  CMsftDiscRecorder2 *v16; // rcx
  signed int v17; // eax
  int v18; // edx
  Imapi2Utility *v19; // rcx
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-38h] BYREF
  CMsftDiscRecorder2 *v21; // [rsp+80h] [rbp+8h] BYREF

  v21 = this;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( !Overlapped.hEvent )
    return 2147942414LL;
  v11 = lpNumberOfBytesTransferred;
  OverlappedResult = DeviceIoControl(
                       a2,
                       a3,
                       a4,
                       nInBufferSize,
                       lpOutBuffer,
                       nOutBufferSize,
                       lpNumberOfBytesTransferred,
                       &Overlapped);
  if ( !OverlappedResult && GetLastError() == 997 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 44, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
    }
    OverlappedResult = GetOverlappedResult(a2, &Overlapped, v11, 1);
  }
  LastErrorAsHresultForceFailure = 0;
  if ( !OverlappedResult )
  {
    LastError = GetLastError();
    switch ( LastError )
    {
      case 0x79u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 45, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        }
        LastErrorAsHresultForceFailure = -1062600179;
        break;
      case 6u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 46, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        }
        LastErrorAsHresultForceFailure = -2147024890;
        break;
      case 0x37u:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 22), 47, &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids);
        }
        LastErrorAsHresultForceFailure = -2147024841;
        break;
      case 5u:
        LOBYTE(v21) = 0;
        if ( CMsftDiscRecorder2::QueryLockState(v16, a2, (unsigned __int8 *)&v21, 0) >= 0 && (_BYTE)v21 )
          LastErrorAsHresultForceFailure = -1062600176;
        else
          LastErrorAsHresultForceFailure = Imapi2Utility::GetLastErrorAsHresultForceFailure(v19, v18);
        break;
      default:
        v17 = GetLastError();
        LastErrorAsHresultForceFailure = v17;
        if ( v17 > 0 )
          LastErrorAsHresultForceFailure = (unsigned __int16)v17 | 0x80070000;
        if ( (LastErrorAsHresultForceFailure & 0x80000000) == 0 )
          LastErrorAsHresultForceFailure = -2147467259;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 22),
            48,
            &WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids,
            LastErrorAsHresultForceFailure);
        }
        break;
    }
  }
  if ( (unsigned __int64)Overlapped.hEvent - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(Overlapped.hEvent);
  return LastErrorAsHresultForceFailure;
}

```

## disassembly

```asm
0x180005100  mov     [rsp+arg_0], rcx
0x180005105  push    rbx
0x180005106  push    rsi
0x180005107  push    rdi
0x180005108  sub     rsp, 60h
0x18000510c  xorps   xmm0, xmm0
0x18000510f  mov     rbx, r9
0x180005112  mov     edi, r8d
0x180005115  mov     rsi, rdx
0x180005118  xor     r9d, r9d; lpName
0x18000511b  xor     r8d, r8d; bInitialState
0x18000511e  mov     edx, 1; bManualReset
0x180005123  xor     ecx, ecx; lpEventAttributes
0x180005125  movups  xmmword ptr [rsp+78h+Overlapped.Internal], xmm0
0x18000512a  movups  xmmword ptr [rsp+78h+Overlapped.10h], xmm0
0x18000512f  call    cs:__imp_CreateEventW
0x180005135  mov     [rsp+78h+Overlapped.hEvent], rax
0x18000513a  test    rax, rax
0x18000513d  jz      loc_180005264
0x180005143  mov     r9d, [rsp+78h+nInBufferSize]; nInBufferSize
0x18000514b  lea     rax, [rsp+78h+Overlapped]
0x180005150  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x180005155  mov     r8, rbx; lpInBuffer
0x180005158  mov     eax, [rsp+78h+arg_30]
0x18000515f  mov     edx, edi; dwIoControlCode
0x180005161  mov     [rsp+78h+arg_8], rbp
0x180005169  mov     rcx, rsi; hDevice
0x18000516c  mov     rbp, [rsp+78h+lpNumberOfBytesTransferred]
0x180005174  mov     [rsp+78h+lpBytesReturned], rbp; lpBytesReturned
0x180005179  mov     [rsp+78h+nOutBufferSize], eax; nOutBufferSize
0x18000517d  mov     rax, [rsp+78h+arg_28]
0x180005185  mov     [rsp+78h+lpOutBuffer], rax; lpOutBuffer
0x18000518a  mov     [rsp+78h+arg_10], r14
0x180005192  call    cs:__imp_DeviceIoControl
0x180005198  lea     r14, WPP_GLOBAL_Control
0x18000519f  mov     edi, eax
0x1800051a1  test    eax, eax
0x1800051a3  jz      loc_180005271
0x1800051a9  mov     rbp, [rsp+78h+arg_8]
0x1800051b1  xor     ebx, ebx
0x1800051b3  test    edi, edi
0x1800051b5  jz      short loc_1800051DE
0x1800051b7  mov     rcx, [rsp+78h+Overlapped.hEvent]; hObject
0x1800051bc  mov     r14, [rsp+78h+arg_10]
0x1800051c4  lea     rax, [rcx-1]
0x1800051c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800051cc  ja      short loc_1800051D4
0x1800051ce  call    cs:__imp_CloseHandle
0x1800051d4  mov     eax, ebx
0x1800051d6  add     rsp, 60h
0x1800051da  pop     rdi
0x1800051db  pop     rsi
0x1800051dc  pop     rbx
0x1800051dd  retn
0x1800051de  call    cs:__imp_GetLastError
0x1800051e4  cmp     eax, 79h ; 'y'
0x1800051e7  jz      loc_1800052D6
0x1800051ed  cmp     eax, 6
0x1800051f0  jz      loc_180005316
0x1800051f6  cmp     eax, 37h ; '7'
0x1800051f9  jz      loc_180005356
0x1800051ff  cmp     eax, 5
0x180005202  jz      loc_180005396
0x180005208  call    cs:__imp_GetLastError
0x18000520e  mov     ebx, eax
0x180005210  test    eax, eax
0x180005212  jg      loc_1800053D3
0x180005218  test    ebx, ebx
0x18000521a  mov     eax, 80004005h
0x18000521f  cmovns  ebx, eax
0x180005222  mov     rcx, cs:WPP_GLOBAL_Control
0x180005229  cmp     rcx, r14
0x18000522c  jz      short loc_1800051B7
0x18000522e  test    byte ptr [rcx+0BCh], 4
0x180005235  jz      short loc_1800051B7
0x180005237  cmp     byte ptr [rcx+0B9h], 3
0x18000523e  jb      loc_1800051B7
0x180005244  mov     rcx, [rcx+0B0h]
0x18000524b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180005252  mov     edx, 30h ; '0'
0x180005257  mov     r9d, ebx
0x18000525a  call    WPP_SF_d
0x18000525f  jmp     loc_1800051B7
0x180005264  mov     eax, 8007000Eh
0x180005269  add     rsp, 60h
0x18000526d  pop     rdi
0x18000526e  pop     rsi
0x18000526f  pop     rbx
0x180005270  retn
0x180005271  call    cs:__imp_GetLastError
0x180005277  cmp     eax, 3E5h
0x18000527c  jnz     loc_1800051A9
0x180005282  mov     rcx, cs:WPP_GLOBAL_Control
0x180005289  cmp     rcx, r14
0x18000528c  jz      short loc_1800052B8
0x18000528e  test    byte ptr [rcx+0BCh], 4
0x180005295  jz      short loc_1800052B8
0x180005297  cmp     byte ptr [rcx+0B9h], 3
0x18000529e  jb      short loc_1800052B8
0x1800052a0  mov     rcx, [rcx+0B0h]
0x1800052a7  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x1800052ae  mov     edx, 2Ch ; ','
0x1800052b3  call    WPP_SF_
0x1800052b8  mov     r9d, 1; bWait
0x1800052be  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x1800052c3  mov     r8, rbp; lpNumberOfBytesTransferred
0x1800052c6  mov     rcx, rsi; hFile
0x1800052c9  call    cs:__imp_GetOverlappedResult
0x1800052cf  mov     edi, eax
0x1800052d1  jmp     loc_1800051A9
0x1800052d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052dd  cmp     rcx, r14
0x1800052e0  jz      short loc_18000530C
0x1800052e2  test    byte ptr [rcx+0BCh], 4
0x1800052e9  jz      short loc_18000530C
0x1800052eb  cmp     byte ptr [rcx+0B9h], 3
0x1800052f2  jb      short loc_18000530C
0x1800052f4  mov     rcx, [rcx+0B0h]
0x1800052fb  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180005302  mov     edx, 2Dh ; '-'
0x180005307  call    WPP_SF_
0x18000530c  mov     ebx, 0C0AA020Dh
0x180005311  jmp     loc_1800051B7
0x180005316  mov     rcx, cs:WPP_GLOBAL_Control
0x18000531d  cmp     rcx, r14
0x180005320  jz      short loc_18000534C
0x180005322  test    byte ptr [rcx+0BCh], 4
0x180005329  jz      short loc_18000534C
0x18000532b  cmp     byte ptr [rcx+0B9h], 3
0x180005332  jb      short loc_18000534C
0x180005334  mov     rcx, [rcx+0B0h]
0x18000533b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180005342  mov     edx, 2Eh ; '.'
0x180005347  call    WPP_SF_
0x18000534c  mov     ebx, 80070006h
0x180005351  jmp     loc_1800051B7
0x180005356  mov     rcx, cs:WPP_GLOBAL_Control
0x18000535d  cmp     rcx, r14
0x180005360  jz      short loc_18000538C
0x180005362  test    byte ptr [rcx+0BCh], 4
0x180005369  jz      short loc_18000538C
0x18000536b  cmp     byte ptr [rcx+0B9h], 3
0x180005372  jb      short loc_18000538C
0x180005374  mov     rcx, [rcx+0B0h]
0x18000537b  lea     r8, WPP_fefec3ffd04a3513b6b0bfc2ca7f8bf3_Traceguids
0x180005382  mov     edx, 2Fh ; '/'
0x180005387  call    WPP_SF_
0x18000538c  mov     ebx, 80070037h
0x180005391  jmp     loc_1800051B7
0x180005396  xor     r9d, r9d; unsigned __int16 **
0x180005399  mov     byte ptr [rsp+78h+arg_0], bl
0x1800053a0  lea     r8, [rsp+78h+arg_0]; unsigned __int8 *
0x1800053a8  mov     rdx, rsi; void *
0x1800053ab  call    ?QueryLockState@CMsftDiscRecorder2@@AEAAJPEAXPEAEPEAPEAG@Z; CMsftDiscRecorder2::QueryLockState(void *,uchar *,ushort * *)
0x1800053b0  test    eax, eax
0x1800053b2  js      short loc_1800053C7
0x1800053b4  cmp     byte ptr [rsp+78h+arg_0], bl
0x1800053bb  jz      short loc_1800053C7
0x1800053bd  mov     ebx, 0C0AA0210h
0x1800053c2  jmp     loc_1800051B7
0x1800053c7  call    ?GetLastErrorAsHresultForceFailure@Imapi2Utility@@YAJJ@Z; Imapi2Utility::GetLastErrorAsHresultForceFailure(long)
0x1800053cc  mov     ebx, eax
0x1800053ce  jmp     loc_1800051B7
0x1800053d3  movzx   ebx, ax
0x1800053d6  or      ebx, 80070000h
0x1800053dc  jmp     loc_180005218
```
