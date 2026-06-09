# CFileContentsFileReader::Read(unsigned __int64,void *,ulong,ulong *)

- ea: `0x140068100`
- end: `0x1400682fc`
- name: `?Read@CFileContentsFileReader@@UEAAJ_KPEAXKPEAK@Z`
- size: `508`
- prototype: `__int64 __fastcall(CFileContentsFileReader *this, LARGE_INTEGER, void *, DWORD, unsigned int *lpNumberOfBytesRead)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x140068100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140068223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400682e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400682e3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400681d6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1400681d6`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140068149`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140068149`

## pseudocode

```c
__int64 __fastcall CFileContentsFileReader::Read(
        CFileContentsFileReader *this,
        LARGE_INTEGER a2,
        void *a3,
        DWORD a4,
        unsigned int *lpNumberOfBytesRead)
{
  char *v7; // rcx
  signed int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  signed int LastError; // eax
  unsigned int v14; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v16; // rcx

  v7 = (char *)*((_QWORD *)this + 4);
  if ( (unsigned __int64)(v7 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    v10 = -2147418113;
  }
  else if ( a3 && lpNumberOfBytesRead )
  {
    if ( !a2.QuadPart || SetFilePointerEx(v7, a2, 0, 0) )
    {
      if ( ReadFile(*((HANDLE *)this + 4), a3, a4, lpNumberOfBytesRead, 0) )
      {
        v10 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids, v12);
        }
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v9 = GetLastError();
      v10 = v9;
      if ( v9 > 0 )
        v10 = (unsigned __int16)v9 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids, v11, v10);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids, v14);
    }
    v10 = -2147024809;
  }
  v16 = (void *)*((_QWORD *)this + 4);
  if ( v16 )
  {
    CloseHandle(v16);
    *((_QWORD *)this + 4) = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x140068100  push    rbx
0x140068102  push    rbp
0x140068103  push    rsi
0x140068104  push    rdi
0x140068105  sub     rsp, 38h
0x140068109  mov     rsi, rcx
0x14006810c  mov     ebp, r9d
0x14006810f  mov     rcx, [rcx+20h]; hFile
0x140068113  mov     rdi, r8
0x140068116  lea     rax, [rcx-1]
0x14006811a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006811e  ja      loc_140068292
0x140068124  test    r8, r8
0x140068127  jz      loc_140068248
0x14006812d  mov     rbx, [rsp+58h+lpNumberOfBytesRead]
0x140068135  test    rbx, rbx
0x140068138  jz      loc_140068248
0x14006813e  test    rdx, rdx
0x140068141  jz      short loc_1400681C0
0x140068143  xor     r9d, r9d; dwMoveMethod
0x140068146  xor     r8d, r8d; lpNewFilePointer
0x140068149  call    cs:__imp_SetFilePointerEx
0x14006814f  test    eax, eax
0x140068151  jnz     short loc_1400681C0
0x140068153  call    cs:__imp_GetLastError
0x140068159  mov     ebx, eax
0x14006815b  test    eax, eax
0x14006815d  jle     short loc_140068168
0x14006815f  movzx   ebx, ax
0x140068162  or      ebx, 80070000h
0x140068168  mov     rcx, cs:WPP_GLOBAL_Control
0x14006816f  lea     rax, WPP_GLOBAL_Control
0x140068176  cmp     rcx, rax
0x140068179  jz      loc_1400682DA
0x14006817f  test    byte ptr [rcx+1Ch], 1
0x140068183  jz      loc_1400682DA
0x140068189  cmp     byte ptr [rcx+19h], 2
0x14006818d  jb      loc_1400682DA
0x140068193  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140068198  mov     rcx, cs:WPP_GLOBAL_Control
0x14006819f  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x1400681a6  mov     edx, 45h ; 'E'
0x1400681ab  mov     dword ptr [rsp+58h+lpOverlapped], ebx
0x1400681af  mov     r9d, eax
0x1400681b2  mov     rcx, [rcx+10h]
0x1400681b6  call    WPP_SF_Dd
0x1400681bb  jmp     loc_1400682DA
0x1400681c0  mov     rcx, [rsi+20h]; hFile
0x1400681c4  mov     r9, rbx; lpNumberOfBytesRead
0x1400681c7  mov     r8d, ebp; nNumberOfBytesToRead
0x1400681ca  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1400681d3  mov     rdx, rdi; lpBuffer
0x1400681d6  call    cs:__imp_ReadFile
0x1400681dc  test    eax, eax
0x1400681de  jnz     short loc_140068241
0x1400681e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400681e7  lea     rax, WPP_GLOBAL_Control
0x1400681ee  cmp     rcx, rax
0x1400681f1  jz      short loc_140068223
0x1400681f3  test    byte ptr [rcx+1Ch], 1
0x1400681f7  jz      short loc_140068223
0x1400681f9  cmp     byte ptr [rcx+19h], 2
0x1400681fd  jb      short loc_140068223
0x1400681ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140068204  mov     rcx, cs:WPP_GLOBAL_Control
0x14006820b  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x140068212  mov     edx, 46h ; 'F'
0x140068217  mov     r9d, eax
0x14006821a  mov     rcx, [rcx+10h]
0x14006821e  call    WPP_SF_d
0x140068223  call    cs:__imp_GetLastError
0x140068229  mov     ebx, eax
0x14006822b  test    eax, eax
0x14006822d  jle     loc_1400682DA
0x140068233  movzx   ebx, ax
0x140068236  or      ebx, 80070000h
0x14006823c  jmp     loc_1400682DA
0x140068241  xor     ebx, ebx
0x140068243  jmp     loc_1400682DA
0x140068248  mov     rcx, cs:WPP_GLOBAL_Control
0x14006824f  lea     rax, WPP_GLOBAL_Control
0x140068256  cmp     rcx, rax
0x140068259  jz      short loc_14006828B
0x14006825b  test    byte ptr [rcx+1Ch], 1
0x14006825f  jz      short loc_14006828B
0x140068261  cmp     byte ptr [rcx+19h], 2
0x140068265  jb      short loc_14006828B
0x140068267  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006826c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068273  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x14006827a  mov     edx, 44h ; 'D'
0x14006827f  mov     r9d, eax
0x140068282  mov     rcx, [rcx+10h]
0x140068286  call    WPP_SF_d
0x14006828b  mov     ebx, 80070057h
0x140068290  jmp     short loc_1400682DA
0x140068292  mov     rcx, cs:WPP_GLOBAL_Control
0x140068299  lea     rax, WPP_GLOBAL_Control
0x1400682a0  cmp     rcx, rax
0x1400682a3  jz      short loc_1400682D5
0x1400682a5  test    byte ptr [rcx+1Ch], 1
0x1400682a9  jz      short loc_1400682D5
0x1400682ab  cmp     byte ptr [rcx+19h], 2
0x1400682af  jb      short loc_1400682D5
0x1400682b1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400682b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400682bd  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x1400682c4  mov     edx, 43h ; 'C'
0x1400682c9  mov     r9d, eax
0x1400682cc  mov     rcx, [rcx+10h]
0x1400682d0  call    WPP_SF_d
0x1400682d5  mov     ebx, 8000FFFFh
0x1400682da  mov     rcx, [rsi+20h]; hObject
0x1400682de  test    rcx, rcx
0x1400682e1  jz      short loc_1400682F1
0x1400682e3  call    cs:__imp_CloseHandle
0x1400682e9  mov     qword ptr [rsi+20h], 0
0x1400682f1  mov     eax, ebx
0x1400682f3  add     rsp, 38h
0x1400682f7  pop     rdi
0x1400682f8  pop     rsi
0x1400682f9  pop     rbp
0x1400682fa  pop     rbx
0x1400682fb  retn
```
