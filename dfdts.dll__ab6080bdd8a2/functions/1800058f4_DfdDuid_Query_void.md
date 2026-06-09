# DfdDuid::Query(void)

- ea: `0x1800058f4`
- end: `0x180005b92`
- name: `?Query@DfdDuid@@QEAAKXZ`
- size: `670`
- prototype: `__int64 __fastcall(DfdDuid *this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002ed8`

## callees

- `0x180002c68`
- `0x180002c90`
- `0x1800058f4`
- `0x180005cac`
- `0x180005d14`
- `0x180008370`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180005972`
- `KERNEL32!DeviceIoControl` at `0x180005a95`
- `KERNEL32!DeviceIoControl` at `0x180005972`
- `KERNEL32!DeviceIoControl` at `0x180005a95`
- `KERNEL32!HeapAlloc` at `0x180005a0d`
- `KERNEL32!HeapAlloc` at `0x180005a0d`
- `KERNEL32!GetProcessHeap` at `0x1800059fc`
- `KERNEL32!GetProcessHeap` at `0x180005b25`
- `KERNEL32!GetProcessHeap` at `0x1800059fc`
- `KERNEL32!GetProcessHeap` at `0x180005b25`
- `KERNEL32!HeapFree` at `0x180005b33`
- `KERNEL32!HeapFree` at `0x180005b33`
- `KERNEL32!GetLastError` at `0x18000597e`
- `KERNEL32!GetLastError` at `0x180005a9f`
- `KERNEL32!GetLastError` at `0x18000597e`
- `KERNEL32!GetLastError` at `0x180005a9f`

## pseudocode

```c
__int64 __fastcall DfdDuid::Query(DfdDuid *this)
{
  unsigned int v1; // edi
  void *v3; // rcx
  __int64 v4; // r8
  void *v5; // rbx
  DWORD LastError; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  DWORD nOutBufferSize; // r14d
  HANDLE ProcessHeap; // rax
  void *lpOutBuffer; // rax
  void *v12; // rcx
  __int64 v13; // r8
  DWORD v14; // eax
  HANDLE v15; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-30h] BYREF
  SIZE_T dwBytes; // [rsp+48h] [rbp-28h] BYREF
  int InBuffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 InBuffer_4; // [rsp+54h] [rbp-1Ch]

  v1 = 0;
  if ( *((_BYTE *)this + 8) )
    return v1;
  *((_BYTE *)this + 8) = 1;
  v3 = *(void **)this;
  InBuffer_4 = 0;
  dwBytes = 0;
  BytesReturned = 0;
  InBuffer = 3;
  if ( !DeviceIoControl(v3, 0x2D1400u, &InBuffer, 0xCu, &dwBytes, 8u, &BytesReturned, 0) )
  {
    v5 = 0;
    LastError = GetLastError();
    v1 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 10;
LABEL_18:
      WPP_SF_d(v7[2], v8, &WPP_3fe3f72127b734931da4de68e0accc84_Traceguids, LastError);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  if ( BytesReturned != 8 )
  {
    v1 = 13;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v4, BytesReturned, 8);
    return v1;
  }
  nOutBufferSize = HIDWORD(dwBytes);
  ProcessHeap = GetProcessHeap();
  lpOutBuffer = HeapAlloc(ProcessHeap, 8u, nOutBufferSize);
  v5 = lpOutBuffer;
  if ( !lpOutBuffer )
  {
    v1 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_3fe3f72127b734931da4de68e0accc84_Traceguids);
    return v1;
  }
  v12 = *(void **)this;
  InBuffer_4 = 0;
  InBuffer = 3;
  if ( !DeviceIoControl(v12, 0x2D1400u, &InBuffer, 0xCu, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 13;
      goto LABEL_18;
    }
LABEL_19:
    if ( v1 && v5 )
    {
LABEL_26:
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v5);
      return v1;
    }
    return v1;
  }
  v14 = BytesReturned;
  if ( BytesReturned != nOutBufferSize )
  {
    v1 = 13;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v13, BytesReturned, nOutBufferSize);
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v13, BytesReturned, nOutBufferSize);
    v14 = BytesReturned;
  }
  *((_QWORD *)this + 2) = v5;
  *((_DWORD *)this + 6) = v14;
  return v1;
}

```

## disassembly

```asm
0x1800058f4  mov     r11, rsp
0x1800058f7  mov     [r11+10h], rbx
0x1800058fb  mov     [r11+18h], rsi
0x1800058ff  push    rbp
0x180005900  push    rdi
0x180005901  push    r14
0x180005903  mov     rbp, rsp
0x180005906  sub     rsp, 70h
0x18000590a  mov     rax, cs:__security_cookie
0x180005911  xor     rax, rsp
0x180005914  mov     [rbp+var_10], rax
0x180005918  xor     edi, edi
0x18000591a  mov     rsi, rcx
0x18000591d  cmp     [rcx+8], dil
0x180005921  jnz     loc_180005B6F
0x180005927  xor     eax, eax
0x180005929  mov     byte ptr [rcx+8], 1
0x18000592d  mov     rcx, [rcx]; hDevice
0x180005930  lea     r9d, [rdi+0Ch]; nInBufferSize
0x180005934  mov     [r11-50h], rax
0x180005938  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000593c  mov     [rbp+InBuffer], rax
0x180005940  mov     edx, 2D1400h; dwIoControlCode
0x180005945  mov     [rbp+InBuffer+4], rax
0x180005949  mov     [rbp+var_18], al
0x18000594c  mov     [rbp+dwBytes], rax
0x180005950  lea     rax, [rbp+BytesReturned]
0x180005954  mov     [r11-58h], rax
0x180005958  lea     rax, [rbp+dwBytes]
0x18000595c  mov     [rsp+70h+nOutBufferSize], 8; nOutBufferSize
0x180005964  mov     [r11-68h], rax
0x180005968  mov     [rbp+BytesReturned], edi
0x18000596b  mov     dword ptr [rbp+InBuffer], 3
0x180005972  call    cs:__imp_DeviceIoControl
0x180005978  test    eax, eax
0x18000597a  jnz     short loc_1800059AF
0x18000597c  xor     ebx, ebx
0x18000597e  call    cs:__imp_GetLastError
0x180005984  mov     edi, eax
0x180005986  mov     rcx, cs:WPP_GLOBAL_Control
0x18000598d  lea     rdx, WPP_GLOBAL_Control
0x180005994  cmp     rcx, rdx
0x180005997  jz      loc_180005AD8
0x18000599d  test    byte ptr [rcx+1Ch], 1
0x1800059a1  jz      loc_180005AD8
0x1800059a7  lea     edx, [rbx+0Ah]
0x1800059aa  jmp     loc_180005AC5
0x1800059af  mov     r9d, [rbp+BytesReturned]
0x1800059b3  cmp     r9d, 8
0x1800059b7  jz      short loc_1800059F8
0x1800059b9  mov     edi, 0Dh
0x1800059be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059c5  lea     rdx, WPP_GLOBAL_Control
0x1800059cc  cmp     rcx, rdx
0x1800059cf  jz      loc_180005B6F
0x1800059d5  test    byte ptr [rcx+1Ch], 1
0x1800059d9  jz      loc_180005B6F
0x1800059df  mov     rcx, [rcx+10h]
0x1800059e3  lea     edx, [rdi-2]
0x1800059e6  mov     dword ptr [rsp+70h+lpOutBuffer], 8
0x1800059ee  call    WPP_SF_DDD
0x1800059f3  jmp     loc_180005B6F
0x1800059f8  mov     r14d, dword ptr [rbp+dwBytes+4]
0x1800059fc  call    cs:__imp_GetProcessHeap
0x180005a02  mov     r8d, r14d; dwBytes
0x180005a05  mov     edx, 8; dwFlags
0x180005a0a  mov     rcx, rax; hHeap
0x180005a0d  call    cs:__imp_HeapAlloc
0x180005a13  mov     rbx, rax
0x180005a16  test    rax, rax
0x180005a19  jnz     short loc_180005A57
0x180005a1b  lea     edi, [rax+8]
0x180005a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a25  lea     rdx, WPP_GLOBAL_Control
0x180005a2c  cmp     rcx, rdx
0x180005a2f  jz      loc_180005B6F
0x180005a35  test    byte ptr [rcx+1Ch], 1
0x180005a39  jz      loc_180005B6F
0x180005a3f  mov     rcx, [rcx+10h]
0x180005a43  lea     edx, [rax+0Ch]
0x180005a46  lea     r8, WPP_3fe3f72127b734931da4de68e0accc84_Traceguids
0x180005a4d  call    WPP_SF_
0x180005a52  jmp     loc_180005B6F
0x180005a57  mov     rcx, [rsi]; hDevice
0x180005a5a  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180005a5e  xor     eax, eax
0x180005a60  mov     r9d, 0Ch; nInBufferSize
0x180005a66  mov     [rsp+70h+lpOverlapped], rax; lpOverlapped
0x180005a6b  mov     edx, 2D1400h; dwIoControlCode
0x180005a70  mov     [rbp+InBuffer], rax
0x180005a74  mov     [rbp+InBuffer+4], rax
0x180005a78  mov     [rbp+var_18], al
0x180005a7b  lea     rax, [rbp+BytesReturned]
0x180005a7f  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x180005a84  mov     [rsp+70h+nOutBufferSize], r14d; nOutBufferSize
0x180005a89  mov     [rsp+70h+lpOutBuffer], rbx; lpOutBuffer
0x180005a8e  mov     dword ptr [rbp+InBuffer], 3
0x180005a95  call    cs:__imp_DeviceIoControl
0x180005a9b  test    eax, eax
0x180005a9d  jnz     short loc_180005AEB
0x180005a9f  call    cs:__imp_GetLastError
0x180005aa5  mov     edi, eax
0x180005aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aae  lea     rdx, WPP_GLOBAL_Control
0x180005ab5  cmp     rcx, rdx
0x180005ab8  jz      short loc_180005AD8
0x180005aba  test    byte ptr [rcx+1Ch], 1
0x180005abe  jz      short loc_180005AD8
0x180005ac0  mov     edx, 0Dh
0x180005ac5  mov     rcx, [rcx+10h]
0x180005ac9  lea     r8, WPP_3fe3f72127b734931da4de68e0accc84_Traceguids
0x180005ad0  mov     r9d, eax
0x180005ad3  call    WPP_SF_d
0x180005ad8  test    edi, edi
0x180005ada  jz      loc_180005B6F
0x180005ae0  test    rbx, rbx
0x180005ae3  jz      loc_180005B6F
0x180005ae9  jmp     short loc_180005B25
0x180005aeb  mov     eax, [rbp+BytesReturned]
0x180005aee  cmp     eax, r14d
0x180005af1  jz      short loc_180005B3B
0x180005af3  mov     edi, 0Dh
0x180005af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aff  lea     rdx, WPP_GLOBAL_Control
0x180005b06  cmp     rcx, rdx
0x180005b09  jz      short loc_180005B25
0x180005b0b  test    byte ptr [rcx+1Ch], 1
0x180005b0f  jz      short loc_180005B25
0x180005b11  mov     rcx, [rcx+10h]
0x180005b15  lea     edx, [rdi+1]
0x180005b18  mov     r9d, eax
0x180005b1b  mov     dword ptr [rsp+70h+lpOutBuffer], r14d
0x180005b20  call    WPP_SF_DDD
0x180005b25  call    cs:__imp_GetProcessHeap
0x180005b2b  mov     r8, rbx; lpMem
0x180005b2e  xor     edx, edx; dwFlags
0x180005b30  mov     rcx, rax; hHeap
0x180005b33  call    cs:__imp_HeapFree
0x180005b39  jmp     short loc_180005B6F
0x180005b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b42  lea     rdx, WPP_GLOBAL_Control
0x180005b49  cmp     rcx, rdx
0x180005b4c  jz      short loc_180005B68
0x180005b4e  test    byte ptr [rcx+1Ch], 4
0x180005b52  jz      short loc_180005B68
0x180005b54  mov     rcx, [rcx+10h]
0x180005b58  mov     r9d, eax
0x180005b5b  mov     dword ptr [rsp+70h+lpOutBuffer], r14d
0x180005b60  call    WPP_SF_dd
0x180005b65  mov     eax, [rbp+BytesReturned]
0x180005b68  mov     [rsi+10h], rbx
0x180005b6c  mov     [rsi+18h], eax
0x180005b6f  mov     eax, edi
0x180005b71  mov     rcx, [rbp+var_10]
0x180005b75  xor     rcx, rsp; StackCookie
0x180005b78  call    __security_check_cookie
0x180005b7d  lea     r11, [rsp+70h+var_s0]
0x180005b82  mov     rbx, [r11+28h]
0x180005b86  mov     rsi, [r11+30h]
0x180005b8a  mov     rsp, r11
0x180005b8d  pop     r14
0x180005b8f  pop     rdi
0x180005b90  pop     rbp
0x180005b91  retn
```
