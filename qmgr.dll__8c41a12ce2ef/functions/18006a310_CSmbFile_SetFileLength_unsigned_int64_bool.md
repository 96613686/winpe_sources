# CSmbFile::SetFileLength(unsigned __int64,bool)

- ea: `0x18006a310`
- end: `0x18006a575`
- name: `?SetFileLength@CSmbFile@@IEAAX_K_N@Z`
- size: `613`
- prototype: `void(CSmbFile *__hidden this, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180062f88`

## callees

- `0x180033480`
- `0x18006a310`
- `0x18009a9d0`
- `0x1800ab7fc`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a468`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a4e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a36e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006a36e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a561`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a561`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006a3e9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006a4c7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006a3e9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006a4c7`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006a454`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18006a454`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSmbFile::SetFileLength(CSmbFile *this, LARGE_INTEGER a2, char a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  __int64 v7; // r9
  unsigned int LastError; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  char v11[8]; // [rsp+30h] [rbp-98h] BYREF
  char *v12; // [rsp+38h] [rbp-90h]
  void **pExceptionObject; // [rsp+40h] [rbp-88h] BYREF
  __int128 v14; // [rsp+48h] [rbp-80h]
  unsigned int v15; // [rsp+58h] [rbp-70h]
  int v16; // [rsp+5Ch] [rbp-6Ch]
  int v17; // [rsp+60h] [rbp-68h]

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v12 = (char *)this + 8;
  if ( *((_BYTE *)this + 48)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v6);
  }
  EnterCriticalSection(v6);
  v11[0] = 1;
  v7 = *((_QWORD *)this + 19);
  if ( v7 != a2.QuadPart || a3 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        &WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
        v7,
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
        v14 = 0;
        pExceptionObject = &ComError::`vftable';
        v15 = LastError;
        v16 = 1362;
        v17 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( !SetEndOfFile(*((HANDLE *)this + 40)) )
      {
        if ( (int)GetLastError() > 0 )
          v9 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v9 = GetLastError();
        v14 = 0;
        pExceptionObject = &ComError::`vftable';
        v15 = v9;
        v16 = 1367;
        v17 = 1;
        throw (ComError *)&pExceptionObject;
      }
      if ( !SetFilePointerEx(*((HANDLE *)this + 40), 0, 0, 0) )
      {
        if ( (int)GetLastError() > 0 )
          v10 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v10 = GetLastError();
        v14 = 0;
        pExceptionObject = &ComError::`vftable';
        v15 = v10;
        v16 = 1376;
        v17 = 1;
        throw (ComError *)&pExceptionObject;
      }
    }
    if ( LOBYTE(v6[1].DebugInfo)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v6);
    }
    LeaveCriticalSection(v6);
  }
  else
  {
    HoldCritSec::~HoldCritSec((HoldCritSec *)v11);
  }
}

```

## disassembly

```asm
0x18006a310  push    rbx
0x18006a312  push    rbp
0x18006a313  push    rsi
0x18006a314  push    rdi
0x18006a315  push    r14
0x18006a317  sub     rsp, 0A0h
0x18006a31e  movzx   ebp, r8b
0x18006a322  mov     rsi, rdx
0x18006a325  mov     rdi, rcx
0x18006a328  lea     rbx, [rcx+8]
0x18006a32c  mov     [rsp+0C8h+var_90], rbx
0x18006a331  lea     r14, WPP_GLOBAL_Control
0x18006a338  cmp     byte ptr [rbx+28h], 0
0x18006a33c  jz      short loc_18006A36B
0x18006a33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a345  cmp     rcx, r14
0x18006a348  jz      short loc_18006A36B
0x18006a34a  test    dword ptr [rcx+1Ch], 100h
0x18006a351  jz      short loc_18006A36B
0x18006a353  mov     edx, 0Fh
0x18006a358  mov     r9, rbx
0x18006a35b  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18006a362  mov     rcx, [rcx+10h]
0x18006a366  call    WPP_SF_q
0x18006a36b  mov     rcx, rbx; lpCriticalSection
0x18006a36e  call    cs:__imp_EnterCriticalSection
0x18006a374  mov     [rsp+0C8h+var_98], 1
0x18006a379  mov     r9, [rdi+98h]
0x18006a380  cmp     r9, rsi
0x18006a383  jnz     short loc_18006A399
0x18006a385  test    bpl, bpl
0x18006a388  jnz     short loc_18006A399
0x18006a38a  lea     rcx, [rsp+0C8h+var_98]; this
0x18006a38f  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x18006a394  jmp     loc_18006A567
0x18006a399  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3a0  cmp     rcx, r14
0x18006a3a3  jz      short loc_18006A3C8
0x18006a3a5  test    dword ptr [rcx+1Ch], 800h
0x18006a3ac  jz      short loc_18006A3C8
0x18006a3ae  mov     edx, 26h ; '&'
0x18006a3b3  mov     [rsp+0C8h+var_A8], rsi
0x18006a3b8  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x18006a3bf  mov     rcx, [rcx+10h]
0x18006a3c3  call    WPP_SF_qq
0x18006a3c8  mov     [rdi+98h], rsi
0x18006a3cf  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18006a3d3  jz      loc_18006A52B
0x18006a3d9  xor     r9d, r9d; dwMoveMethod
0x18006a3dc  xor     r8d, r8d; lpNewFilePointer
0x18006a3df  mov     rdx, rsi; liDistanceToMove
0x18006a3e2  mov     rcx, [rdi+140h]; hFile
0x18006a3e9  call    cs:__imp_SetFilePointerEx
0x18006a3ef  test    eax, eax
0x18006a3f1  jnz     short loc_18006A44D
0x18006a3f3  call    cs:__imp_GetLastError
0x18006a3f9  test    eax, eax
0x18006a3fb  jg      short loc_18006A405
0x18006a3fd  call    cs:__imp_GetLastError
0x18006a403  jmp     short loc_18006A413
0x18006a405  call    cs:__imp_GetLastError
0x18006a40b  movzx   eax, ax
0x18006a40e  or      eax, 80070000h
0x18006a413  xorps   xmm0, xmm0
0x18006a416  movups  [rsp+0C8h+var_80], xmm0
0x18006a41b  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006a422  mov     [rsp+0C8h+pExceptionObject], rcx
0x18006a427  mov     [rsp+0C8h+var_70], eax
0x18006a42b  mov     [rsp+0C8h+var_6C], 552h
0x18006a433  mov     [rsp+0C8h+var_68], 1
0x18006a43b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006a442  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18006a447  call    _CxxThrowException_0
0x18006a44d  mov     rcx, [rdi+140h]; hFile
0x18006a454  call    cs:__imp_SetEndOfFile
0x18006a45a  test    eax, eax
0x18006a45c  jnz     short loc_18006A4B8
0x18006a45e  call    cs:__imp_GetLastError
0x18006a464  test    eax, eax
0x18006a466  jg      short loc_18006A470
0x18006a468  call    cs:__imp_GetLastError
0x18006a46e  jmp     short loc_18006A47E
0x18006a470  call    cs:__imp_GetLastError
0x18006a476  movzx   eax, ax
0x18006a479  or      eax, 80070000h
0x18006a47e  xorps   xmm0, xmm0
0x18006a481  movups  [rsp+0C8h+var_80], xmm0
0x18006a486  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006a48d  mov     [rsp+0C8h+pExceptionObject], rcx
0x18006a492  mov     [rsp+0C8h+var_70], eax
0x18006a496  mov     [rsp+0C8h+var_6C], 557h
0x18006a49e  mov     [rsp+0C8h+var_68], 1
0x18006a4a6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006a4ad  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18006a4b2  call    _CxxThrowException_0
0x18006a4b8  xor     r9d, r9d; dwMoveMethod
0x18006a4bb  xor     r8d, r8d; lpNewFilePointer
0x18006a4be  xor     edx, edx; liDistanceToMove
0x18006a4c0  mov     rcx, [rdi+140h]; hFile
0x18006a4c7  call    cs:__imp_SetFilePointerEx
0x18006a4cd  test    eax, eax
0x18006a4cf  jnz     short loc_18006A52B
0x18006a4d1  call    cs:__imp_GetLastError
0x18006a4d7  test    eax, eax
0x18006a4d9  jg      short loc_18006A4E3
0x18006a4db  call    cs:__imp_GetLastError
0x18006a4e1  jmp     short loc_18006A4F1
0x18006a4e3  call    cs:__imp_GetLastError
0x18006a4e9  movzx   eax, ax
0x18006a4ec  or      eax, 80070000h
0x18006a4f1  xorps   xmm0, xmm0
0x18006a4f4  movups  [rsp+0C8h+var_80], xmm0
0x18006a4f9  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006a500  mov     [rsp+0C8h+pExceptionObject], rcx
0x18006a505  mov     [rsp+0C8h+var_70], eax
0x18006a509  mov     [rsp+0C8h+var_6C], 560h
0x18006a511  mov     [rsp+0C8h+var_68], 1
0x18006a519  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006a520  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18006a525  call    _CxxThrowException_0
0x18006a52b  cmp     byte ptr [rbx+28h], 0
0x18006a52f  jz      short loc_18006A55E
0x18006a531  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a538  cmp     rcx, r14
0x18006a53b  jz      short loc_18006A55E
0x18006a53d  test    dword ptr [rcx+1Ch], 100h
0x18006a544  jz      short loc_18006A55E
0x18006a546  mov     edx, 10h
0x18006a54b  mov     r9, rbx
0x18006a54e  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18006a555  mov     rcx, [rcx+10h]
0x18006a559  call    WPP_SF_q
0x18006a55e  mov     rcx, rbx; lpCriticalSection
0x18006a561  call    cs:__imp_LeaveCriticalSection
0x18006a567  add     rsp, 0A0h
0x18006a56e  pop     r14
0x18006a570  pop     rdi
0x18006a571  pop     rsi
0x18006a572  pop     rbp
0x18006a573  pop     rbx
0x18006a574  retn
```
