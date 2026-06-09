# CFveApiEnum::EnumNextVolume(void)

- ea: `0x180006040`
- end: `0x18000646b`
- name: `?EnumNextVolume@CFveApiEnum@@AEAAJXZ`
- size: `1067`
- prototype: `__int64 __fastcall(CFveApiEnum *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005f74`

## callees

- `0x180005410`
- `0x180006040`
- `0x18000ba30`
- `0x18011f010`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800062c7`
- `msvcrt!wcstoul` at `0x1800062c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006424`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006424`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006170`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006121`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006374`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006374`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000610d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800061be`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000610d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800061be`

## pseudocode

```c
__int64 __fastcall CFveApiEnum::EnumNextVolume(HANDLE *this)
{
  unsigned int *lpOutBuffer; // r14
  int v3; // ebx
  unsigned int v4; // esi
  signed int LastError; // eax
  signed int LastHresultError; // edi
  SIZE_T v7; // r8
  unsigned int v8; // r15d
  unsigned int v9; // r12d
  unsigned int *v10; // rbx
  unsigned __int64 v11; // rcx
  wchar_t *v12; // r8
  __int64 v13; // rdx
  wchar_t *v14; // r9
  __int64 v15; // r10
  wchar_t v16; // ax
  unsigned int v17; // eax
  unsigned int v18; // ecx
  __int64 v19; // rax
  HANDLE FileW; // rax
  DWORD OutBuffer; // [rsp+90h] [rbp-68h] BYREF
  wchar_t *EndPtr; // [rsp+98h] [rbp-60h] BYREF
  DWORD BytesReturned; // [rsp+A0h] [rbp-58h] BYREF
  wchar_t String[12]; // [rsp+A8h] [rbp-50h] BYREF

  lpOutBuffer = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  v3 = 0;
  memset(String, 0, 22);
  EndPtr = 0;
  v4 = -1;
  if ( *((_DWORD *)this + 20) > 2u )
  {
LABEL_41:
    LastHresultError = -2147418113;
  }
  else if ( this[11] == (HANDLE)-1LL
         && (FileW = CreateFileW(off_18012A180[*((int *)this + 20)], 0, 3u, 0, 3u, 0, 0),
             this[11] = FileW,
             FileW == (HANDLE)-1LL) )
  {
    LastHresultError = GetLastHresultError();
  }
  else
  {
    while ( 1 )
    {
      if ( lpOutBuffer )
      {
        CFveApiBase::FastFree(lpOutBuffer);
        lpOutBuffer = 0;
      }
      if ( (unsigned int)++v3 > 5 )
      {
        LastHresultError = -2147418113;
        goto LABEL_48;
      }
      if ( DeviceIoControl(this[11], 0x4C4210CCu, 0, 0, &OutBuffer, 4u, &BytesReturned, 0) )
      {
        LastHresultError = -2147024809;
        goto LABEL_48;
      }
      LastError = GetLastError();
      LastHresultError = LastError;
      if ( LastError > 0 )
        LastHresultError = (unsigned __int16)LastError | 0x80070000;
      if ( LastHresultError >= 0 )
        LastHresultError = -2147418113;
      if ( LastHresultError != -2147024662 )
        goto LABEL_48;
      LastHresultError = 0;
      v7 = OutBuffer;
      if ( !OutBuffer )
        v7 = 1;
      lpOutBuffer = (unsigned int *)HeapAlloc(CFveApiBase::_ProcessHeap, 0, v7);
      if ( !lpOutBuffer )
      {
        LastHresultError = -2147024882;
        goto LABEL_48;
      }
      if ( DeviceIoControl(this[11], 0x4C4210CCu, 0, 0, lpOutBuffer, OutBuffer, &BytesReturned, 0) )
        break;
      LastHresultError = GetLastHresultError();
      if ( LastHresultError != -2147024662 )
        goto LABEL_48;
    }
    v8 = 8;
    v9 = 0;
    v10 = lpOutBuffer + 2;
    while ( v9 < lpOutBuffer[1] && v8 < *lpOutBuffer )
    {
      v11 = (unsigned __int64)v10[3] >> 1;
      if ( v11 > 0x7FFFFFFE )
      {
        LastHresultError = -2147024809;
        String[0] = 0;
      }
      else
      {
        v12 = (wchar_t *)((char *)v10 + v10[2]);
        v13 = 11;
        v14 = String;
        LastHresultError = 0;
        v15 = 0;
        while ( v13 )
        {
          if ( !v11 )
            goto LABEL_25;
          v16 = *v12;
          if ( !*v12 )
            goto LABEL_25;
          ++v12;
          *v14++ = v16;
          --v13;
          --v11;
          ++v15;
        }
        --v14;
        LastHresultError = -2147024774;
LABEL_25:
        *v14 = 0;
      }
      if ( LastHresultError < 0 )
        goto LABEL_48;
      v17 = wcstoul(String, &EndPtr, 10);
      if ( v17 == -1 || EndPtr != (wchar_t *)((char *)String + (v10[3] & 0xFFFFFFFE)) )
        goto LABEL_41;
      v18 = *((_DWORD *)this + 21);
      if ( (v17 > v18 || v18 == -1) && v17 < v4 )
        v4 = v17;
      v19 = *v10;
      v8 += v19;
      ++v9;
      v10 = (unsigned int *)((char *)v10 + v19);
    }
    if ( v4 == -1 )
    {
      *((_DWORD *)this + 21) = -1;
      LastHresultError = -2147024878;
    }
    else
    {
      *((_DWORD *)this + 21) = v4;
    }
  }
LABEL_48:
  if ( lpOutBuffer && !HeapFree(CFveApiBase::_ProcessHeap, 0, lpOutBuffer) )
    GetLastHresultError();
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x180006040  mov     r11, rsp
0x180006043  mov     [r11+10h], rbx
0x180006047  mov     [r11+18h], rsi
0x18000604b  push    rdi
0x18000604c  push    r12
0x18000604e  push    r13
0x180006050  push    r14
0x180006052  push    r15
0x180006054  sub     rsp, 0D0h
0x18000605b  mov     rax, cs:__security_cookie
0x180006062  xor     rax, rsp
0x180006065  mov     [rsp+0F8h+var_38], rax
0x18000606d  mov     r13, rcx
0x180006070  xor     edi, edi
0x180006072  mov     r14d, edi
0x180006075  mov     [rsp+0F8h+var_B0], rdi
0x18000607a  mov     [r11-68h], edi
0x18000607e  mov     [r11-58h], edi
0x180006082  mov     ebx, edi
0x180006084  xorps   xmm0, xmm0
0x180006087  xor     eax, eax
0x180006089  movups  xmmword ptr [r11-50h], xmm0
0x18000608e  mov     [r11-42h], rax
0x180006092  mov     [r11-60h], rdi
0x180006096  mov     esi, 0FFFFFFFFh
0x18000609b  movsxd  rax, dword ptr [rcx+50h]
0x18000609f  cmp     eax, 2
0x1800060a2  ja      loc_1800063AE
0x1800060a8  cmp     qword ptr [rcx+58h], 0FFFFFFFFFFFFFFFFh
0x1800060ad  jz      loc_18000634A
0x1800060b3  mov     r15d, 8000FFFFh
0x1800060b9  mov     r12d, 1
0x1800060bf  test    r14, r14
0x1800060c2  jnz     loc_1800063E6
0x1800060c8  inc     ebx
0x1800060ca  mov     [rsp+0F8h+var_90], ebx
0x1800060ce  cmp     ebx, 5
0x1800060d1  ja      loc_1800063FB
0x1800060d7  mov     [rsp+0F8h+lpOverlapped], rdi; lpOverlapped
0x1800060dc  lea     rax, [rsp+0F8h+BytesReturned]
0x1800060e4  mov     [rsp+0F8h+lpBytesReturned], rax; lpBytesReturned
0x1800060e9  mov     [rsp+0F8h+nOutBufferSize], 4; nOutBufferSize
0x1800060f1  lea     rax, [rsp+0F8h+OutBuffer]
0x1800060f9  mov     [rsp+0F8h+lpOutBuffer], rax; lpOutBuffer
0x1800060fe  xor     r9d, r9d; nInBufferSize
0x180006101  xor     r8d, r8d; lpInBuffer
0x180006104  mov     edx, 4C4210CCh; dwIoControlCode
0x180006109  mov     rcx, [r13+58h]; hDevice
0x18000610d  call    cs:__imp_DeviceIoControl
0x180006114  nop     dword ptr [rax+rax+00h]
0x180006119  test    eax, eax
0x18000611b  jnz     loc_180006405
0x180006121  call    cs:__imp_GetLastError
0x180006128  nop     dword ptr [rax+rax+00h]
0x18000612d  mov     edi, eax
0x18000612f  test    eax, eax
0x180006131  jle     short loc_18000613C
0x180006133  movzx   edi, ax
0x180006136  or      edi, 80070000h
0x18000613c  test    edi, edi
0x18000613e  cmovns  edi, r15d
0x180006142  mov     [rsp+0F8h+var_B8], edi
0x180006146  cmp     edi, 800700EAh
0x18000614c  jnz     loc_180006413
0x180006152  xor     edi, edi
0x180006154  mov     [rsp+0F8h+var_B8], edi
0x180006158  mov     r8d, [rsp+0F8h+OutBuffer]
0x180006160  test    r8, r8
0x180006163  cmovz   r8, r12; dwBytes
0x180006167  xor     edx, edx; dwFlags
0x180006169  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180006170  call    cs:__imp_HeapAlloc
0x180006177  nop     dword ptr [rax+rax+00h]
0x18000617c  mov     r14, rax
0x18000617f  mov     [rsp+0F8h+var_B0], rax
0x180006184  test    rax, rax
0x180006187  jz      loc_18000640C
0x18000618d  mov     [rsp+0F8h+lpOverlapped], rdi; lpOverlapped
0x180006192  lea     rax, [rsp+0F8h+BytesReturned]
0x18000619a  mov     [rsp+0F8h+lpBytesReturned], rax; lpBytesReturned
0x18000619f  mov     eax, [rsp+0F8h+OutBuffer]
0x1800061a6  mov     [rsp+0F8h+nOutBufferSize], eax; nOutBufferSize
0x1800061aa  mov     [rsp+0F8h+lpOutBuffer], r14; lpOutBuffer
0x1800061af  xor     r9d, r9d; nInBufferSize
0x1800061b2  xor     r8d, r8d; lpInBuffer
0x1800061b5  mov     edx, 4C4210CCh; dwIoControlCode
0x1800061ba  mov     rcx, [r13+58h]; hDevice
0x1800061be  call    cs:__imp_DeviceIoControl
0x1800061c5  nop     dword ptr [rax+rax+00h]
0x1800061ca  test    eax, eax
0x1800061cc  jz      loc_1800063B5
0x1800061d2  mov     r15d, 8
0x1800061d8  xor     r12d, r12d
0x1800061db  lea     rbx, [r14+8]
0x1800061df  mov     [rsp+0F8h+var_A8], r15d
0x1800061e4  mov     [rsp+0F8h+var_A4], r12d
0x1800061e9  mov     [rsp+0F8h+var_70], rbx
0x1800061f1  cmp     r12d, [r14+4]
0x1800061f5  jnb     loc_18000633C
0x1800061fb  cmp     r15d, [r14]
0x1800061fe  jnb     loc_18000633C
0x180006204  mov     ecx, [rbx+0Ch]
0x180006207  shr     rcx, 1
0x18000620a  cmp     rcx, 7FFFFFFEh
0x180006211  ja      loc_1800063D2
0x180006217  mov     eax, [rbx+8]
0x18000621a  lea     r8, [rax+rbx]
0x18000621e  mov     [rsp+0F8h+var_78], rcx
0x180006226  mov     [rsp+0F8h+var_88], r8
0x18000622b  mov     edx, 0Bh
0x180006230  mov     [rsp+0F8h+var_80], rdx
0x180006235  lea     r9, [rsp+0F8h+String]
0x18000623d  mov     [rsp+0F8h+var_A0], r9
0x180006242  xor     edi, edi
0x180006244  xor     r10d, r10d
0x180006247  mov     [rsp+0F8h+var_98], r10
0x18000624c  nop     dword ptr [rax+00h]
0x180006250  test    rdx, rdx
0x180006253  jz      loc_180006316
0x180006259  test    rcx, rcx
0x18000625c  jz      short loc_18000629A
0x18000625e  movzx   eax, word ptr [r8]
0x180006262  test    ax, ax
0x180006265  jz      short loc_18000629A
0x180006267  add     r8, 2
0x18000626b  mov     [rsp+0F8h+var_88], r8
0x180006270  mov     [r9], ax
0x180006274  add     r9, 2
0x180006278  mov     [rsp+0F8h+var_A0], r9
0x18000627d  dec     rdx
0x180006280  mov     [rsp+0F8h+var_80], rdx
0x180006285  dec     rcx
0x180006288  mov     [rsp+0F8h+var_78], rcx
0x180006290  inc     r10
0x180006293  mov     [rsp+0F8h+var_98], r10
0x180006298  jmp     short loc_180006250
0x18000629a  test    rdx, rdx
0x18000629d  jz      short loc_180006316
0x18000629f  xor     eax, eax
0x1800062a1  mov     [r9], ax
0x1800062a5  mov     [rsp+0F8h+var_B8], edi
0x1800062a9  test    edi, edi
0x1800062ab  js      loc_180006413
0x1800062b1  mov     r8d, 0Ah; Radix
0x1800062b7  lea     rdx, [rsp+0F8h+EndPtr]; EndPtr
0x1800062bf  lea     rcx, [rsp+0F8h+String]; String
0x1800062c7  call    cs:__imp_wcstoul
0x1800062ce  nop     dword ptr [rax+rax+00h]
0x1800062d3  cmp     eax, 0FFFFFFFFh
0x1800062d6  jz      loc_1800063AE
0x1800062dc  mov     ecx, [rbx+0Ch]
0x1800062df  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800062e3  lea     rcx, [rsp+rcx+0F8h+String]
0x1800062eb  cmp     [rsp+0F8h+EndPtr], rcx
0x1800062f3  jnz     loc_1800063AE
0x1800062f9  mov     ecx, [r13+54h]
0x1800062fd  cmp     eax, ecx
0x1800062ff  ja      short loc_180006331
0x180006301  cmp     ecx, 0FFFFFFFFh
0x180006304  jz      short loc_180006331
0x180006306  mov     eax, [rbx]
0x180006308  add     r15d, eax
0x18000630b  inc     r12d
0x18000630e  add     rbx, rax
0x180006311  jmp     loc_1800061DF
0x180006316  sub     r9, 2
0x18000631a  mov     [rsp+0F8h+var_A0], r9
0x18000631f  dec     r10
0x180006322  mov     [rsp+0F8h+var_98], r10
0x180006327  mov     edi, 8007007Ah
0x18000632c  jmp     loc_18000629F
0x180006331  cmp     eax, esi
0x180006333  cmovb   esi, eax
0x180006336  mov     [rsp+0F8h+var_8C], esi
0x18000633a  jmp     short loc_180006306
0x18000633c  cmp     esi, 0FFFFFFFFh
0x18000633f  jz      short loc_18000639B
0x180006341  mov     [r13+54h], esi
0x180006345  jmp     loc_180006413
0x18000634a  mov     rcx, rax
0x18000634d  lea     rax, off_18012A180; "\\\\.\\BitLocker\\Unsupported"
0x180006354  mov     [rsp+0F8h+lpBytesReturned], rdi; hTemplateFile
0x180006359  mov     [rsp+0F8h+nOutBufferSize], edi; dwFlagsAndAttributes
0x18000635d  mov     dword ptr [rsp+0F8h+lpOutBuffer], 3; dwCreationDisposition
0x180006365  xor     r9d, r9d; lpSecurityAttributes
0x180006368  xor     edx, edx; dwDesiredAccess
0x18000636a  mov     r8d, 3; dwShareMode
0x180006370  mov     rcx, [rax+rcx*8]; lpFileName
0x180006374  call    cs:__imp_CreateFileW
0x18000637b  nop     dword ptr [rax+rax+00h]
0x180006380  mov     [r13+58h], rax
0x180006384  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006388  jnz     loc_1800060B3
0x18000638e  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180006393  mov     edi, eax
0x180006395  mov     [rsp+0F8h+var_B8], eax
0x180006399  jmp     short loc_180006413
0x18000639b  mov     dword ptr [r13+54h], 0FFFFFFFFh
0x1800063a3  mov     edi, 80070012h
0x1800063a8  mov     [rsp+0F8h+var_B8], edi
0x1800063ac  jmp     short loc_180006413
0x1800063ae  mov     edi, 8000FFFFh
0x1800063b3  jmp     short loc_1800063A8
0x1800063b5  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800063ba  mov     edi, eax
0x1800063bc  mov     [rsp+0F8h+var_B8], eax
0x1800063c0  cmp     eax, 800700EAh
0x1800063c5  jnz     short loc_180006413
0x1800063c7  xor     edi, edi
0x1800063c9  mov     [rsp+0F8h+var_B8], edi
0x1800063cd  jmp     loc_1800060BF
0x1800063d2  mov     edi, 80070057h
0x1800063d7  xor     eax, eax
0x1800063d9  mov     [rsp+0F8h+String], ax
0x1800063e1  jmp     loc_1800062A5
0x1800063e6  mov     rcx, r14; lpMem
0x1800063e9  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1800063ee  mov     r14, rdi
0x1800063f1  mov     [rsp+0F8h+var_B0], rdi
0x1800063f6  jmp     loc_1800060C8
0x1800063fb  mov     edi, r15d
0x1800063fe  mov     [rsp+0F8h+var_B8], r15d
0x180006403  jmp     short loc_180006413
0x180006405  mov     edi, 80070057h
0x18000640a  jmp     short loc_1800063A8
0x18000640c  mov     edi, 8007000Eh
0x180006411  jmp     short loc_1800063A8
0x180006413  test    r14, r14
0x180006416  jz      short loc_180006434
0x180006418  mov     r8, r14; lpMem
0x18000641b  xor     edx, edx; dwFlags
0x18000641d  mov     rcx, cs:?_ProcessHeap@CFveApiBase@@1PEAXEA; hHeap
0x180006424  call    cs:__imp_HeapFree
0x18000642b  nop     dword ptr [rax+rax+00h]
0x180006430  test    eax, eax
0x180006432  jz      short loc_180006464
0x180006434  mov     eax, edi
0x180006436  mov     rcx, [rsp+0F8h+var_38]
0x18000643e  xor     rcx, rsp; StackCookie
0x180006441  call    __security_check_cookie
0x180006446  lea     r11, [rsp+0F8h+var_28]
0x18000644e  mov     rbx, [r11+38h]
0x180006452  mov     rsi, [r11+40h]
0x180006456  mov     rsp, r11
0x180006459  pop     r15
0x18000645b  pop     r14
0x18000645d  pop     r13
0x18000645f  pop     r12
0x180006461  pop     rdi
0x180006462  retn
0x180006464  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x180006469  jmp     short loc_180006434
0x18011f2c0  push    rbp
0x18011f2c2  sub     rsp, 40h
0x18011f2c6  mov     rbp, rdx
0x18011f2c9  mov     rcx, [rbp+48h]; lpMem
0x18011f2cd  test    rcx, rcx
0x18011f2d0  jz      short loc_18011F2DF
0x18011f2d2  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18011f2d7  mov     qword ptr [rbp+48h], 0
0x18011f2df  add     rsp, 40h
0x18011f2e3  pop     rbp
0x18011f2e4  retn
```
