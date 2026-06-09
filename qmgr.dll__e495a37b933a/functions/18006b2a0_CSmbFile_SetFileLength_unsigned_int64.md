# CSmbFile::SetFileLength(unsigned __int64)

- ea: `0x18006b2a0`
- end: `0x18006b4f5`
- name: `?SetFileLength@CSmbFile@@UEAAX_K@Z`
- size: `597`
- prototype: `void(CSmbFile *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180033480`
- `0x18006b2a0`
- `0x18009a9d0`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b454`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b468`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b2fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b2fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b4e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b4e1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006b372`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006b44a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006b372`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006b44a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006b3da`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006b3da`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSmbFile::SetFileLength(CSmbFile *this, LARGE_INTEGER a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // r9
  unsigned int LastError; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  char v9[8]; // [rsp+30h] [rbp-39h] BYREF
  char *v10; // [rsp+38h] [rbp-31h]
  void **pExceptionObject; // [rsp+40h] [rbp-29h] BYREF
  __int128 v12; // [rsp+48h] [rbp-21h]
  unsigned int v13; // [rsp+58h] [rbp-11h]
  int v14; // [rsp+5Ch] [rbp-Dh]
  int v15; // [rsp+60h] [rbp-9h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v10 = (char *)this + 8;
  if ( *((_BYTE *)this + 48)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v4);
  }
  EnterCriticalSection(v4);
  v9[0] = 1;
  v5 = *((_QWORD *)this + 19);
  if ( v5 == a2.QuadPart )
  {
    HoldCritSec::~HoldCritSec((HoldCritSec *)v9);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
        v5,
        (LARGE_INTEGER)a2.QuadPart);
    *((LARGE_INTEGER *)this + 19) = a2;
    if ( a2.QuadPart != -1 )
    {
      if ( !SetFilePointerEx(*((HANDLE *)this + 40), a2, 0, 0) )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0x80070000;
        else
          LastError = GetLastError();
        v12 = 0;
        pExceptionObject = &ComError::`vftable';
        v13 = LastError;
        v14 = 1362;
        v15 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( !SetEndOfFile(*((HANDLE *)this + 40)) )
      {
        if ( (int)GetLastError() > 0 )
          v7 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v7 = GetLastError();
        v12 = 0;
        pExceptionObject = &ComError::`vftable';
        v13 = v7;
        v14 = 1367;
        v15 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( !SetFilePointerEx(*((HANDLE *)this + 40), 0, 0, 0) )
      {
        if ( (int)GetLastError() > 0 )
          v8 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v8 = GetLastError();
        v12 = 0;
        pExceptionObject = &ComError::`vftable';
        v13 = v8;
        v14 = 1376;
        v15 = 1;
        throw (ComError *)&pExceptionObject;
      }
    }
    if ( LOBYTE(v4[1].DebugInfo)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v4);
    }
    LeaveCriticalSection(v4);
  }
}

```

## disassembly

```asm
0x18006b2a0  push    rbp
0x18006b2a2  push    rbx
0x18006b2a3  push    rsi
0x18006b2a4  push    rdi
0x18006b2a5  push    r15
0x18006b2a7  lea     rbp, [rsp-37h]
0x18006b2ac  sub     rsp, 0A0h
0x18006b2b3  mov     rsi, rdx
0x18006b2b6  mov     rdi, rcx
0x18006b2b9  lea     rbx, [rcx+8]
0x18006b2bd  mov     [rbp+57h+var_88], rbx
0x18006b2c1  lea     r15, WPP_GLOBAL_Control
0x18006b2c8  cmp     byte ptr [rbx+28h], 0
0x18006b2cc  jz      short loc_18006B2FB
0x18006b2ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b2d5  cmp     rcx, r15
0x18006b2d8  jz      short loc_18006B2FB
0x18006b2da  test    dword ptr [rcx+1Ch], 100h
0x18006b2e1  jz      short loc_18006B2FB
0x18006b2e3  mov     edx, 0Fh
0x18006b2e8  mov     r9, rbx
0x18006b2eb  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18006b2f2  mov     rcx, [rcx+10h]
0x18006b2f6  call    WPP_SF_q
0x18006b2fb  mov     rcx, rbx; lpCriticalSection
0x18006b2fe  call    cs:__imp_EnterCriticalSection
0x18006b304  mov     [rbp+57h+var_90], 1
0x18006b308  mov     r9, [rdi+98h]
0x18006b30f  cmp     r9, rsi
0x18006b312  jnz     short loc_18006B322
0x18006b314  lea     rcx, [rbp+57h+var_90]; this
0x18006b318  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x18006b31d  jmp     loc_18006B4E7
0x18006b322  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b329  cmp     rcx, r15
0x18006b32c  jz      short loc_18006B351
0x18006b32e  test    dword ptr [rcx+1Ch], 800h
0x18006b335  jz      short loc_18006B351
0x18006b337  mov     edx, 26h ; '&'
0x18006b33c  mov     [rsp+0C0h+var_A0], rsi
0x18006b341  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x18006b348  mov     rcx, [rcx+10h]
0x18006b34c  call    WPP_SF_qq
0x18006b351  mov     [rdi+98h], rsi
0x18006b358  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18006b35c  jz      loc_18006B4AB
0x18006b362  xor     r9d, r9d; dwMoveMethod
0x18006b365  xor     r8d, r8d; lpNewFilePointer
0x18006b368  mov     rdx, rsi; liDistanceToMove
0x18006b36b  mov     rcx, [rdi+140h]; hFile
0x18006b372  call    cs:__imp_SetFilePointerEx
0x18006b378  test    eax, eax
0x18006b37a  jnz     short loc_18006B3D3
0x18006b37c  call    cs:__imp_GetLastError
0x18006b382  test    eax, eax
0x18006b384  jg      short loc_18006B390
0x18006b386  call    cs:__imp_GetLastError
0x18006b38c  mov     ecx, eax
0x18006b38e  jmp     short loc_18006B39F
0x18006b390  call    cs:__imp_GetLastError
0x18006b396  movzx   ecx, ax
0x18006b399  or      ecx, 80070000h
0x18006b39f  xorps   xmm0, xmm0
0x18006b3a2  movups  [rbp+57h+var_78], xmm0
0x18006b3a6  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006b3ad  mov     [rbp+57h+pExceptionObject], rax
0x18006b3b1  mov     [rbp+57h+var_68], ecx
0x18006b3b4  mov     [rbp+57h+var_64], 552h
0x18006b3bb  mov     [rbp+57h+var_60], 1
0x18006b3c2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006b3c9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006b3cd  call    _CxxThrowException_0
0x18006b3d3  mov     rcx, [rdi+140h]; hFile
0x18006b3da  call    cs:__imp_SetEndOfFile
0x18006b3e0  test    eax, eax
0x18006b3e2  jnz     short loc_18006B43B
0x18006b3e4  call    cs:__imp_GetLastError
0x18006b3ea  test    eax, eax
0x18006b3ec  jg      short loc_18006B3F8
0x18006b3ee  call    cs:__imp_GetLastError
0x18006b3f4  mov     ecx, eax
0x18006b3f6  jmp     short loc_18006B407
0x18006b3f8  call    cs:__imp_GetLastError
0x18006b3fe  movzx   ecx, ax
0x18006b401  or      ecx, 80070000h
0x18006b407  xorps   xmm0, xmm0
0x18006b40a  movups  [rbp+57h+var_78], xmm0
0x18006b40e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006b415  mov     [rbp+57h+pExceptionObject], rax
0x18006b419  mov     [rbp+57h+var_68], ecx
0x18006b41c  mov     [rbp+57h+var_64], 557h
0x18006b423  mov     [rbp+57h+var_60], 1
0x18006b42a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006b431  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006b435  call    _CxxThrowException_0
0x18006b43b  xor     edx, edx; liDistanceToMove
0x18006b43d  xor     r9d, r9d; dwMoveMethod
0x18006b440  xor     r8d, r8d; lpNewFilePointer
0x18006b443  mov     rcx, [rdi+140h]; hFile
0x18006b44a  call    cs:__imp_SetFilePointerEx
0x18006b450  test    eax, eax
0x18006b452  jnz     short loc_18006B4AB
0x18006b454  call    cs:__imp_GetLastError
0x18006b45a  test    eax, eax
0x18006b45c  jg      short loc_18006B468
0x18006b45e  call    cs:__imp_GetLastError
0x18006b464  mov     ecx, eax
0x18006b466  jmp     short loc_18006B477
0x18006b468  call    cs:__imp_GetLastError
0x18006b46e  movzx   ecx, ax
0x18006b471  or      ecx, 80070000h
0x18006b477  xorps   xmm0, xmm0
0x18006b47a  movups  [rbp+57h+var_78], xmm0
0x18006b47e  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18006b485  mov     [rbp+57h+pExceptionObject], rax
0x18006b489  mov     [rbp+57h+var_68], ecx
0x18006b48c  mov     [rbp+57h+var_64], 560h
0x18006b493  mov     [rbp+57h+var_60], 1
0x18006b49a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006b4a1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006b4a5  call    _CxxThrowException_0
0x18006b4ab  cmp     byte ptr [rbx+28h], 0
0x18006b4af  jz      short loc_18006B4DE
0x18006b4b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b4b8  cmp     rcx, r15
0x18006b4bb  jz      short loc_18006B4DE
0x18006b4bd  test    dword ptr [rcx+1Ch], 100h
0x18006b4c4  jz      short loc_18006B4DE
0x18006b4c6  mov     edx, 10h
0x18006b4cb  mov     r9, rbx
0x18006b4ce  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18006b4d5  mov     rcx, [rcx+10h]
0x18006b4d9  call    WPP_SF_q
0x18006b4de  mov     rcx, rbx; lpCriticalSection
0x18006b4e1  call    cs:__imp_LeaveCriticalSection
0x18006b4e7  add     rsp, 0A0h
0x18006b4ee  pop     r15
0x18006b4f0  pop     rdi
0x18006b4f1  pop     rsi
0x18006b4f2  pop     rbx
0x18006b4f3  pop     rbp
0x18006b4f4  retn
```
