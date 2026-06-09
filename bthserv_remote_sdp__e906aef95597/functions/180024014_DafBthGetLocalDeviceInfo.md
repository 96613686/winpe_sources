# DafBthGetLocalDeviceInfo

- ea: `0x180024014`
- end: `0x180024243`
- name: `DafBthGetLocalDeviceInfo`
- size: `559`
- prototype: `__int64 __fastcall(HANDLE hFile, LPVOID lpOutBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022a74`

## callees

- `0x18000270c`
- `0x18002354c`
- `0x180023628`
- `0x180024014`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002408c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002408c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024160`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800240a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024160`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800241e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800241e0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024113`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024113`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180024150`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180024150`

## pseudocode

```c
__int64 __fastcall DafBthGetLocalDeviceInfo(HANDLE hFile, LPVOID lpOutBuffer)
{
  unsigned int v2; // ebx
  signed int v5; // eax
  int v6; // r9d
  _QWORD *v7; // rcx
  int v8; // edx
  signed int LastError; // eax
  signed int v10; // eax
  int v11; // eax
  bool v12; // cf
  struct _OVERLAPPED Overlapped; // [rsp+40h] [rbp-38h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+18h] BYREF

  v2 = 0;
  BytesReturned = 0;
  memset(&Overlapped, 0, 24);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
  memset_0(lpOutBuffer, 0, 0x124u);
  Overlapped.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(hFile, 0x410000u, 0, 0, lpOutBuffer, 0x124u, &BytesReturned, &Overlapped) )
      goto LABEL_25;
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      else
        v2 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v8 = 19;
        goto LABEL_24;
      }
      goto LABEL_26;
    }
    if ( GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
    {
LABEL_25:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    v10 = GetLastError();
    v2 = v10;
    if ( v10 > 0 )
      v2 = (unsigned __int16)v10 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v8 = 18;
      goto LABEL_24;
    }
  }
  else
  {
    v5 = GetLastError();
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 17;
LABEL_24:
      WPP_SF_sd(v7[2], v8, (unsigned int)WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids, v6, v2);
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( Overlapped.hEvent )
  {
    CloseHandle(Overlapped.hEvent);
    Overlapped.hEvent = 0;
    v7 = WPP_GLOBAL_Control;
  }
  v11 = 0;
  if ( v2 )
    v12 = *((_BYTE *)v7 + 25) < 2u;
  else
    v12 = *((_BYTE *)v7 + 25) < 5u;
  if ( v7 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v11) = !v12;
    if ( v11 )
      WPP_SF_sd(v7[2], 20, (unsigned int)WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids, v6, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x180024014  mov     rax, rsp
0x180024017  mov     [rax+8], rbx
0x18002401b  mov     [rax+10h], rsi
0x18002401f  push    rdi
0x180024020  push    r14
0x180024022  push    r15
0x180024024  sub     rsp, 60h
0x180024028  xor     ebx, ebx
0x18002402a  xorps   xmm0, xmm0
0x18002402d  and     [rax+18h], ebx
0x180024030  mov     rsi, rdx
0x180024033  and     [rax-38h], rbx
0x180024037  mov     rdi, rcx
0x18002403a  movdqu  xmmword ptr [rax-30h], xmm0
0x18002403f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024046  lea     r14, WPP_GLOBAL_Control
0x18002404d  lea     r15, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids
0x180024054  cmp     rcx, r14
0x180024057  jz      short loc_18002406E
0x180024059  cmp     byte ptr [rcx+19h], 5
0x18002405d  jb      short loc_18002406E
0x18002405f  mov     rcx, [rcx+10h]
0x180024063  lea     edx, [rbx+10h]
0x180024066  mov     r8, r15
0x180024069  call    WPP_SF_s
0x18002406e  xor     edx, edx; Val
0x180024070  mov     r8d, 124h; Size
0x180024076  mov     rcx, rsi; void *
0x180024079  call    memset_0
0x18002407e  xor     edx, edx; lpName
0x180024080  xor     ecx, ecx; lpEventAttributes
0x180024082  mov     r9d, 1F0003h; dwDesiredAccess
0x180024088  lea     r8d, [rdx+1]; dwFlags
0x18002408c  call    cs:__imp_CreateEventExW
0x180024093  nop     dword ptr [rax+rax+00h]
0x180024098  mov     [rsp+78h+Overlapped.hEvent], rax
0x18002409d  test    rax, rax
0x1800240a0  jnz     short loc_1800240E1
0x1800240a2  call    cs:__imp_GetLastError
0x1800240a9  nop     dword ptr [rax+rax+00h]
0x1800240ae  mov     ebx, eax
0x1800240b0  test    eax, eax
0x1800240b2  jle     short loc_1800240BD
0x1800240b4  movzx   ebx, ax
0x1800240b7  or      ebx, 80070000h
0x1800240bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800240c4  cmp     rcx, r14
0x1800240c7  jz      loc_1800241D3
0x1800240cd  cmp     byte ptr [rcx+19h], 2
0x1800240d1  jb      loc_1800241D3
0x1800240d7  mov     edx, 11h
0x1800240dc  jmp     loc_1800241BC
0x1800240e1  lea     rax, [rsp+78h+Overlapped]
0x1800240e6  xor     r9d, r9d; nInBufferSize
0x1800240e9  mov     [rsp+78h+lpOverlapped], rax; lpOverlapped
0x1800240ee  xor     r8d, r8d; lpInBuffer
0x1800240f1  lea     rax, [rsp+78h+BytesReturned]
0x1800240f9  mov     edx, 410000h; dwIoControlCode
0x1800240fe  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x180024103  mov     rcx, rdi; hDevice
0x180024106  mov     [rsp+78h+nOutBufferSize], 124h; nOutBufferSize
0x18002410e  mov     [rsp+78h+lpOutBuffer], rsi; lpOutBuffer
0x180024113  call    cs:__imp_DeviceIoControl
0x18002411a  nop     dword ptr [rax+rax+00h]
0x18002411f  test    eax, eax
0x180024121  jnz     loc_1800241CC
0x180024127  call    cs:__imp_GetLastError
0x18002412e  nop     dword ptr [rax+rax+00h]
0x180024133  cmp     eax, 3E5h
0x180024138  jnz     short loc_180024194
0x18002413a  mov     r9d, 1; bWait
0x180024140  lea     r8, [rsp+78h+BytesReturned]; lpNumberOfBytesTransferred
0x180024148  lea     rdx, [rsp+78h+Overlapped]; lpOverlapped
0x18002414d  mov     rcx, rdi; hFile
0x180024150  call    cs:__imp_GetOverlappedResult
0x180024157  nop     dword ptr [rax+rax+00h]
0x18002415c  test    eax, eax
0x18002415e  jnz     short loc_1800241CC
0x180024160  call    cs:__imp_GetLastError
0x180024167  nop     dword ptr [rax+rax+00h]
0x18002416c  mov     ebx, eax
0x18002416e  test    eax, eax
0x180024170  jle     short loc_18002417B
0x180024172  movzx   ebx, ax
0x180024175  or      ebx, 80070000h
0x18002417b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024182  cmp     rcx, r14
0x180024185  jz      short loc_1800241D3
0x180024187  cmp     byte ptr [rcx+19h], 3
0x18002418b  jb      short loc_1800241D3
0x18002418d  mov     edx, 12h
0x180024192  jmp     short loc_1800241BC
0x180024194  test    eax, eax
0x180024196  jg      short loc_18002419C
0x180024198  mov     ebx, eax
0x18002419a  jmp     short loc_1800241A5
0x18002419c  movzx   ebx, ax
0x18002419f  or      ebx, 80070000h
0x1800241a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241ac  cmp     rcx, r14
0x1800241af  jz      short loc_1800241D3
0x1800241b1  cmp     byte ptr [rcx+19h], 3
0x1800241b5  jb      short loc_1800241D3
0x1800241b7  mov     edx, 13h
0x1800241bc  mov     rcx, [rcx+10h]
0x1800241c0  mov     r8, r15
0x1800241c3  mov     dword ptr [rsp+78h+lpOutBuffer], ebx
0x1800241c7  call    WPP_SF_sd
0x1800241cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241d3  mov     rax, [rsp+78h+Overlapped.hEvent]
0x1800241d8  test    rax, rax
0x1800241db  jz      short loc_1800241F9
0x1800241dd  mov     rcx, rax; hObject
0x1800241e0  call    cs:__imp_CloseHandle
0x1800241e7  nop     dword ptr [rax+rax+00h]
0x1800241ec  and     [rsp+78h+Overlapped.hEvent], 0
0x1800241f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241f9  xor     eax, eax
0x1800241fb  test    ebx, ebx
0x1800241fd  jnz     short loc_180024205
0x1800241ff  cmp     byte ptr [rcx+19h], 5
0x180024203  jmp     short loc_180024209
0x180024205  cmp     byte ptr [rcx+19h], 2
0x180024209  setnb   al
0x18002420c  cmp     rcx, r14
0x18002420f  jz      short loc_18002422A
0x180024211  test    eax, eax
0x180024213  jz      short loc_18002422A
0x180024215  mov     rcx, [rcx+10h]
0x180024219  mov     edx, 14h
0x18002421e  mov     r8, r15
0x180024221  mov     dword ptr [rsp+78h+lpOutBuffer], ebx
0x180024225  call    WPP_SF_sd
0x18002422a  lea     r11, [rsp+78h+var_18]
0x18002422f  mov     eax, ebx
0x180024231  mov     rbx, [r11+20h]
0x180024235  mov     rsi, [r11+28h]
0x180024239  mov     rsp, r11
0x18002423c  pop     r15
0x18002423e  pop     r14
0x180024240  pop     rdi
0x180024241  retn
```
