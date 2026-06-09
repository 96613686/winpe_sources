# IsDiskMbrBootable(void *,int *)

- ea: `0x180006b34`
- end: `0x180006e3c`
- name: `?IsDiskMbrBootable@@YAHPEAXPEAH@Z`
- size: `776`
- prototype: `__int64 __fastcall(HANDLE hDevice, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006814`

## callees

- `0x180005528`
- `0x180006b34`
- `0x180008ac8`
- `0x180008af0`
- `0x180008cf0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180006c65`
- `KERNEL32!GetProcessHeap` at `0x180006c79`
- `KERNEL32!GetProcessHeap` at `0x180006dc5`
- `KERNEL32!GetProcessHeap` at `0x180006c65`
- `KERNEL32!GetProcessHeap` at `0x180006c79`
- `KERNEL32!GetProcessHeap` at `0x180006dc5`
- `KERNEL32!HeapAlloc` at `0x180006c87`
- `KERNEL32!HeapAlloc` at `0x180006c87`
- `KERNEL32!GetLastError` at `0x180006bf2`
- `KERNEL32!GetLastError` at `0x180006cc9`
- `KERNEL32!GetLastError` at `0x180006cd8`
- `KERNEL32!GetLastError` at `0x180006bf2`
- `KERNEL32!GetLastError` at `0x180006cc9`
- `KERNEL32!GetLastError` at `0x180006cd8`
- `KERNEL32!HeapFree` at `0x180006c73`
- `KERNEL32!HeapFree` at `0x180006dd3`
- `KERNEL32!HeapFree` at `0x180006c73`
- `KERNEL32!HeapFree` at `0x180006dd3`
- `KERNEL32!SetLastError` at `0x180006bda`
- `KERNEL32!SetLastError` at `0x180006bda`
- `KERNEL32!DeviceIoControl` at `0x180006cbf`
- `KERNEL32!DeviceIoControl` at `0x180006cbf`

## string_xrefs

- `0x180006bb6`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180006d05`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x180006e13`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall IsDiskMbrBootable(HANDLE hDevice, int *a2)
{
  unsigned int v2; // esi
  _QWORD *v5; // rcx
  DWORD v6; // edi
  int v7; // r8d
  int v8; // r9d
  const char *v9; // rcx
  unsigned int *lpOutBuffer; // rbx
  int v12; // r14d
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  DWORD LastError; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  HANDLE v18; // rax
  char lpBytesReturned; // [rsp+30h] [rbp-38h]
  DWORD BytesReturned; // [rsp+78h] [rbp+10h] BYREF

  v2 = 0;
  BytesReturned = 0;
  v5 = WPP_GLOBAL_Control;
  v6 = 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    lpOutBuffer = 0;
    v12 = 0;
    while ( 1 )
    {
      v12 += 16;
      if ( lpOutBuffer )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, lpOutBuffer);
      }
      v14 = GetProcessHeap();
      lpOutBuffer = (unsigned int *)HeapAlloc(v14, 8u, (unsigned int)(144 * v12 + 48));
      if ( !lpOutBuffer )
        break;
      if ( DeviceIoControl(hDevice, 0x70050u, 0, 0, lpOutBuffer, 144 * v12 + 48, &BytesReturned, 0) )
      {
        v16 = *lpOutBuffer;
        v6 = 0;
        if ( (_DWORD)v16 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids, v16);
          goto LABEL_35;
        }
        v17 = 0;
        if ( lpOutBuffer[1] )
        {
          while ( lpOutBuffer[36 * v17 + 12]
               || !LOBYTE(lpOutBuffer[36 * v17 + 20])
               || !BYTE1(lpOutBuffer[36 * v17 + 20]) )
          {
            v17 = (unsigned int)(v17 + 1);
            if ( (unsigned int)v17 >= lpOutBuffer[1] )
              goto LABEL_32;
          }
          *a2 = 1;
        }
        else
        {
LABEL_32:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
LABEL_35:
          *a2 = 0;
        }
        v2 = 1;
LABEL_37:
        v18 = GetProcessHeap();
        HeapFree(v18, 0, lpOutBuffer);
        goto LABEL_8;
      }
      if ( GetLastError() != 122 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            70,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            151,
            LastError);
        goto LABEL_37;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        139,
        8);
  }
  else
  {
    v6 = 87;
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v5[2],
        68,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        113,
        87);
  }
LABEL_8:
  SetLastError(v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    lpBytesReturned = GetLastError();
    v9 = "Success";
    if ( !v2 )
      v9 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, v7, v8, 191, (__int64)v9, lpBytesReturned);
  }
  return v2;
}

```

## disassembly

```asm
0x180006b34  mov     [rsp+arg_0], rbx
0x180006b39  mov     [rsp+arg_10], rbp
0x180006b3e  push    rsi
0x180006b3f  push    rdi
0x180006b40  push    r12
0x180006b42  push    r14
0x180006b44  push    r15
0x180006b46  sub     rsp, 40h
0x180006b4a  xor     esi, esi
0x180006b4c  mov     r15, rdx
0x180006b4f  mov     [rsp+68h+BytesReturned], esi
0x180006b53  mov     r12, rcx
0x180006b56  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b5d  lea     rax, WPP_GLOBAL_Control
0x180006b64  lea     edi, [rsi+8]
0x180006b67  cmp     rcx, rax
0x180006b6a  jz      short loc_180006B93
0x180006b6c  test    [rcx+1Ch], dil
0x180006b70  jz      short loc_180006B93
0x180006b72  mov     rcx, [rcx+10h]
0x180006b76  lea     edx, [rsi+43h]
0x180006b79  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006b80  call    WPP_SF_
0x180006b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b8c  lea     rax, WPP_GLOBAL_Control
0x180006b93  test    r15, r15
0x180006b96  jnz     loc_180006C4D
0x180006b9c  lea     edi, [r15+57h]
0x180006ba0  cmp     rcx, rax
0x180006ba3  jz      short loc_180006BD1
0x180006ba5  test    byte ptr [rcx+1Ch], 1
0x180006ba9  jz      short loc_180006BD1
0x180006bab  mov     rcx, [rcx+10h]
0x180006baf  lea     edx, [rdi-13h]
0x180006bb2  mov     [rsp+68h+nOutBufferSize], edi
0x180006bb6  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180006bbd  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006bc4  mov     dword ptr [rsp+68h+lpOutBuffer], 371h
0x180006bcc  call    WPP_SF_sdD
0x180006bd1  lea     rbp, WPP_GLOBAL_Control
0x180006bd8  mov     ecx, edi; dwErrCode
0x180006bda  call    cs:__imp_SetLastError
0x180006be0  mov     rax, cs:WPP_GLOBAL_Control
0x180006be7  cmp     rax, rbp
0x180006bea  jz      short loc_180006C32
0x180006bec  test    byte ptr [rax+1Ch], 4
0x180006bf0  jz      short loc_180006C32
0x180006bf2  call    cs:__imp_GetLastError
0x180006bf8  lea     rdx, aFailure; "Failure"
0x180006bff  mov     dword ptr [rsp+68h+lpBytesReturned], eax
0x180006c03  test    esi, esi
0x180006c05  lea     rcx, aSuccess; "Success"
0x180006c0c  cmovz   rcx, rdx
0x180006c10  mov     edx, 49h ; 'I'
0x180006c15  mov     qword ptr [rsp+68h+nOutBufferSize], rcx
0x180006c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c21  mov     dword ptr [rsp+68h+lpOutBuffer], 3BFh
0x180006c29  mov     rcx, [rcx+10h]
0x180006c2d  call    WPP_SF_sdsd
0x180006c32  lea     r11, [rsp+68h+var_28]
0x180006c37  mov     eax, esi
0x180006c39  mov     rbx, [r11+30h]
0x180006c3d  mov     rbp, [r11+40h]
0x180006c41  mov     rsp, r11
0x180006c44  pop     r15
0x180006c46  pop     r14
0x180006c48  pop     r12
0x180006c4a  pop     rdi
0x180006c4b  pop     rsi
0x180006c4c  retn
0x180006c4d  xor     ebx, ebx
0x180006c4f  xor     r14d, r14d
0x180006c52  lea     r14d, [r14+10h]
0x180006c56  lea     ebp, [r14+r14*8]
0x180006c5a  shl     ebp, 4
0x180006c5d  add     ebp, 30h ; '0'
0x180006c60  test    rbx, rbx
0x180006c63  jz      short loc_180006C79
0x180006c65  call    cs:__imp_GetProcessHeap
0x180006c6b  mov     r8, rbx; lpMem
0x180006c6e  xor     edx, edx; dwFlags
0x180006c70  mov     rcx, rax; hHeap
0x180006c73  call    cs:__imp_HeapFree
0x180006c79  call    cs:__imp_GetProcessHeap
0x180006c7f  mov     r8d, ebp; dwBytes
0x180006c82  mov     edx, edi; dwFlags
0x180006c84  mov     rcx, rax; hHeap
0x180006c87  call    cs:__imp_HeapAlloc
0x180006c8d  mov     rbx, rax
0x180006c90  test    rax, rax
0x180006c93  jz      loc_180006DEE
0x180006c99  mov     [rsp+68h+lpOverlapped], rsi; lpOverlapped
0x180006c9e  lea     rax, [rsp+68h+BytesReturned]
0x180006ca3  mov     [rsp+68h+lpBytesReturned], rax; lpBytesReturned
0x180006ca8  xor     r9d, r9d; nInBufferSize
0x180006cab  mov     [rsp+68h+nOutBufferSize], ebp; nOutBufferSize
0x180006caf  xor     r8d, r8d; lpInBuffer
0x180006cb2  mov     edx, 70050h; dwIoControlCode
0x180006cb7  mov     [rsp+68h+lpOutBuffer], rbx; lpOutBuffer
0x180006cbc  mov     rcx, r12; hDevice
0x180006cbf  call    cs:__imp_DeviceIoControl
0x180006cc5  test    eax, eax
0x180006cc7  jnz     short loc_180006D2E
0x180006cc9  call    cs:__imp_GetLastError
0x180006ccf  cmp     eax, 7Ah ; 'z'
0x180006cd2  jz      loc_180006C52
0x180006cd8  call    cs:__imp_GetLastError
0x180006cde  mov     edi, eax
0x180006ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ce7  lea     rbp, WPP_GLOBAL_Control
0x180006cee  cmp     rcx, rbp
0x180006cf1  jz      loc_180006DC5
0x180006cf7  test    byte ptr [rcx+1Ch], 1
0x180006cfb  jz      loc_180006DC5
0x180006d01  mov     rcx, [rcx+10h]
0x180006d05  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180006d0c  mov     [rsp+68h+nOutBufferSize], eax
0x180006d10  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006d17  mov     edx, 46h ; 'F'
0x180006d1c  mov     dword ptr [rsp+68h+lpOutBuffer], 397h
0x180006d24  call    WPP_SF_sdD
0x180006d29  jmp     loc_180006DC5
0x180006d2e  mov     r9d, [rbx]
0x180006d31  xor     edi, edi
0x180006d33  test    r9d, r9d
0x180006d36  jz      short loc_180006D66
0x180006d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d3f  lea     rbp, WPP_GLOBAL_Control
0x180006d46  cmp     rcx, rbp
0x180006d49  jz      short loc_180006DBD
0x180006d4b  test    byte ptr [rcx+1Ch], 4
0x180006d4f  jz      short loc_180006DBD
0x180006d51  mov     rcx, [rcx+10h]
0x180006d55  lea     edx, [rdi+47h]
0x180006d58  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006d5f  call    WPP_SF_d
0x180006d64  jmp     short loc_180006DBD
0x180006d66  xor     edx, edx
0x180006d68  cmp     [rbx+4], edx
0x180006d6b  jbe     short loc_180006D8F
0x180006d6d  lea     rcx, [rdx+rdx*8]
0x180006d71  add     rcx, rcx
0x180006d74  cmp     [rbx+rcx*8+30h], esi
0x180006d78  jnz     short loc_180006D88
0x180006d7a  cmp     [rbx+rcx*8+50h], sil
0x180006d7f  jz      short loc_180006D88
0x180006d81  cmp     [rbx+rcx*8+51h], sil
0x180006d86  jnz     short loc_180006DDE
0x180006d88  inc     edx
0x180006d8a  cmp     edx, [rbx+4]
0x180006d8d  jb      short loc_180006D6D
0x180006d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d96  lea     rbp, WPP_GLOBAL_Control
0x180006d9d  cmp     rcx, rbp
0x180006da0  jz      short loc_180006DBD
0x180006da2  test    byte ptr [rcx+1Ch], 4
0x180006da6  jz      short loc_180006DBD
0x180006da8  mov     rcx, [rcx+10h]
0x180006dac  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006db3  mov     edx, 48h ; 'H'
0x180006db8  call    WPP_SF_
0x180006dbd  mov     [r15], esi
0x180006dc0  mov     esi, 1
0x180006dc5  call    cs:__imp_GetProcessHeap
0x180006dcb  mov     r8, rbx; lpMem
0x180006dce  xor     edx, edx; dwFlags
0x180006dd0  mov     rcx, rax; hHeap
0x180006dd3  call    cs:__imp_HeapFree
0x180006dd9  jmp     loc_180006BD8
0x180006dde  mov     dword ptr [r15], 1
0x180006de5  lea     rbp, WPP_GLOBAL_Control
0x180006dec  jmp     short loc_180006DC0
0x180006dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180006df5  lea     rbp, WPP_GLOBAL_Control
0x180006dfc  cmp     rcx, rbp
0x180006dff  jz      loc_180006BD8
0x180006e05  test    byte ptr [rcx+1Ch], 1
0x180006e09  jz      loc_180006BD8
0x180006e0f  mov     rcx, [rcx+10h]
0x180006e13  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180006e1a  mov     edx, 45h ; 'E'
0x180006e1f  mov     [rsp+68h+nOutBufferSize], edi
0x180006e23  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006e2a  mov     dword ptr [rsp+68h+lpOutBuffer], 38Bh
0x180006e32  call    WPP_SF_sdD
0x180006e37  jmp     loc_180006BD8
```
