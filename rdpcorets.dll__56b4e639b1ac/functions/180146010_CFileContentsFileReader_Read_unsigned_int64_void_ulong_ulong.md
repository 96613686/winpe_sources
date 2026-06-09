# CFileContentsFileReader::Read(unsigned __int64,void *,ulong,ulong *)

- ea: `0x180146010`
- end: `0x18014620c`
- name: `?Read@CFileContentsFileReader@@UEAAJ_KPEAXKPEAK@Z`
- size: `508`
- prototype: `__int64 __fastcall(CFileContentsFileReader *this, LARGE_INTEGER, void *, DWORD, unsigned int *lpNumberOfBytesRead)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800091a8`
- `0x180032f60`
- `0x180059838`
- `0x180146010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801461f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801461f3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801460e6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801460e6`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180146059`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180146059`

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
0x180146010  push    rbx
0x180146012  push    rbp
0x180146013  push    rsi
0x180146014  push    rdi
0x180146015  sub     rsp, 38h
0x180146019  mov     rsi, rcx
0x18014601c  mov     ebp, r9d
0x18014601f  mov     rcx, [rcx+20h]; hFile
0x180146023  mov     rdi, r8
0x180146026  lea     rax, [rcx-1]
0x18014602a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18014602e  ja      loc_1801461A2
0x180146034  test    r8, r8
0x180146037  jz      loc_180146158
0x18014603d  mov     rbx, [rsp+58h+lpNumberOfBytesRead]
0x180146045  test    rbx, rbx
0x180146048  jz      loc_180146158
0x18014604e  test    rdx, rdx
0x180146051  jz      short loc_1801460D0
0x180146053  xor     r9d, r9d; dwMoveMethod
0x180146056  xor     r8d, r8d; lpNewFilePointer
0x180146059  call    cs:__imp_SetFilePointerEx
0x18014605f  test    eax, eax
0x180146061  jnz     short loc_1801460D0
0x180146063  call    cs:__imp_GetLastError
0x180146069  mov     ebx, eax
0x18014606b  test    eax, eax
0x18014606d  jle     short loc_180146078
0x18014606f  movzx   ebx, ax
0x180146072  or      ebx, 80070000h
0x180146078  mov     rcx, cs:WPP_GLOBAL_Control
0x18014607f  lea     rax, WPP_GLOBAL_Control
0x180146086  cmp     rcx, rax
0x180146089  jz      loc_1801461EA
0x18014608f  test    byte ptr [rcx+1Ch], 1
0x180146093  jz      loc_1801461EA
0x180146099  cmp     byte ptr [rcx+19h], 2
0x18014609d  jb      loc_1801461EA
0x1801460a3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801460a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801460af  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x1801460b6  mov     edx, 45h ; 'E'
0x1801460bb  mov     dword ptr [rsp+58h+lpOverlapped], ebx
0x1801460bf  mov     r9d, eax
0x1801460c2  mov     rcx, [rcx+10h]
0x1801460c6  call    WPP_SF_Dd
0x1801460cb  jmp     loc_1801461EA
0x1801460d0  mov     rcx, [rsi+20h]; hFile
0x1801460d4  mov     r9, rbx; lpNumberOfBytesRead
0x1801460d7  mov     r8d, ebp; nNumberOfBytesToRead
0x1801460da  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x1801460e3  mov     rdx, rdi; lpBuffer
0x1801460e6  call    cs:__imp_ReadFile
0x1801460ec  test    eax, eax
0x1801460ee  jnz     short loc_180146151
0x1801460f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801460f7  lea     rax, WPP_GLOBAL_Control
0x1801460fe  cmp     rcx, rax
0x180146101  jz      short loc_180146133
0x180146103  test    byte ptr [rcx+1Ch], 1
0x180146107  jz      short loc_180146133
0x180146109  cmp     byte ptr [rcx+19h], 2
0x18014610d  jb      short loc_180146133
0x18014610f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180146114  mov     rcx, cs:WPP_GLOBAL_Control
0x18014611b  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x180146122  mov     edx, 46h ; 'F'
0x180146127  mov     r9d, eax
0x18014612a  mov     rcx, [rcx+10h]
0x18014612e  call    WPP_SF_d
0x180146133  call    cs:__imp_GetLastError
0x180146139  mov     ebx, eax
0x18014613b  test    eax, eax
0x18014613d  jle     loc_1801461EA
0x180146143  movzx   ebx, ax
0x180146146  or      ebx, 80070000h
0x18014614c  jmp     loc_1801461EA
0x180146151  xor     ebx, ebx
0x180146153  jmp     loc_1801461EA
0x180146158  mov     rcx, cs:WPP_GLOBAL_Control
0x18014615f  lea     rax, WPP_GLOBAL_Control
0x180146166  cmp     rcx, rax
0x180146169  jz      short loc_18014619B
0x18014616b  test    byte ptr [rcx+1Ch], 1
0x18014616f  jz      short loc_18014619B
0x180146171  cmp     byte ptr [rcx+19h], 2
0x180146175  jb      short loc_18014619B
0x180146177  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014617c  mov     rcx, cs:WPP_GLOBAL_Control
0x180146183  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x18014618a  mov     edx, 44h ; 'D'
0x18014618f  mov     r9d, eax
0x180146192  mov     rcx, [rcx+10h]
0x180146196  call    WPP_SF_d
0x18014619b  mov     ebx, 80070057h
0x1801461a0  jmp     short loc_1801461EA
0x1801461a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1801461a9  lea     rax, WPP_GLOBAL_Control
0x1801461b0  cmp     rcx, rax
0x1801461b3  jz      short loc_1801461E5
0x1801461b5  test    byte ptr [rcx+1Ch], 1
0x1801461b9  jz      short loc_1801461E5
0x1801461bb  cmp     byte ptr [rcx+19h], 2
0x1801461bf  jb      short loc_1801461E5
0x1801461c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1801461c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801461cd  lea     r8, WPP_bfac144fbe6e397db7c639d4b063c735_Traceguids
0x1801461d4  mov     edx, 43h ; 'C'
0x1801461d9  mov     r9d, eax
0x1801461dc  mov     rcx, [rcx+10h]
0x1801461e0  call    WPP_SF_d
0x1801461e5  mov     ebx, 8000FFFFh
0x1801461ea  mov     rcx, [rsi+20h]; hObject
0x1801461ee  test    rcx, rcx
0x1801461f1  jz      short loc_180146201
0x1801461f3  call    cs:__imp_CloseHandle
0x1801461f9  mov     qword ptr [rsi+20h], 0
0x180146201  mov     eax, ebx
0x180146203  add     rsp, 38h
0x180146207  pop     rdi
0x180146208  pop     rsi
0x180146209  pop     rbp
0x18014620a  pop     rbx
0x18014620b  retn
```
