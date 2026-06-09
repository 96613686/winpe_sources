# CSmbFile::SubmitReadOrWrite(unsigned __int64)

- ea: `0x18005d0e0`
- end: `0x18005d315`
- name: `?SubmitReadOrWrite@CSmbFile@@IEAAX_K@Z`
- size: `565`
- prototype: `void __fastcall(CSmbFile *this, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005d0d0`

## callees

- `0x18005d0e0`
- `0x1800ab7b0`
- `0x1800b1980`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2ae`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18005d261`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18005d2c8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18005d261`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18005d2c8`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18005d167`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18005d167`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005d239`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18005d239`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005d193`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18005d193`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSmbFile::SubmitReadOrWrite(CSmbFile *this, __int64 a2)
{
  unsigned __int64 v4; // r9
  struct _TP_IO *v5; // rcx
  void *v6; // rdx
  void *v7; // rcx
  signed int LastError; // edi
  signed int v9; // edi
  struct _OVERLAPPED *lpOverlapped; // [rsp+20h] [rbp-78h]
  void **pExceptionObject; // [rsp+30h] [rbp-68h] BYREF
  __int128 v12; // [rsp+38h] [rbp-60h]
  signed int v13; // [rsp+48h] [rbp-50h]
  int v14; // [rsp+4Ch] [rbp-4Ch]
  int v15; // [rsp+50h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_DDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
      *((unsigned __int8 *)this + 376),
      a2,
      *((_DWORD *)this + 40));
  v4 = *((unsigned int *)this + 36);
  if ( v4 >= *((_QWORD *)this + 22) - *((_QWORD *)this + 23) )
    v4 = *((_QWORD *)this + 22) - *((_QWORD *)this + 23);
  if ( a2 != v4 )
  {
    *((_DWORD *)this + 102) = a2 - v4;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_544ed435ee403dfadff71ae516532c05_Traceguids, v4, a2 - v4);
  }
  v5 = (struct _TP_IO *)*((_QWORD *)this + 52);
  *((_QWORD *)this + 45) = *((_QWORD *)this + 20);
  *((_QWORD *)this + 46) = 0;
  StartThreadpoolIo(v5);
  v6 = (void *)*((_QWORD *)this + 17);
  v7 = (void *)*((_QWORD *)this + 40);
  lpOverlapped = (struct _OVERLAPPED *)((char *)this + 344);
  if ( *((_BYTE *)this + 376) )
  {
    if ( !ReadFile(v7, v6, a2, 0, lpOverlapped) )
    {
      LastError = GetLastError();
      if ( LastError != 997 )
      {
        CancelThreadpoolIo(*((PTP_IO *)this + 52));
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v13 = LastError;
        v14 = 1702;
        pExceptionObject = &ComError::`vftable';
        v15 = 1;
        v12 = 0;
        throw (ComError *)&pExceptionObject;
      }
    }
  }
  else if ( !WriteFile(v7, v6, a2, 0, lpOverlapped) )
  {
    v9 = GetLastError();
    if ( v9 != 997 )
    {
      CancelThreadpoolIo(*((PTP_IO *)this + 52));
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v13 = v9;
      v14 = 1718;
      pExceptionObject = &ComError::`vftable';
      v15 = 1;
      v12 = 0;
      throw (ComError *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18005d0e0  mov     [rsp+arg_0], rbx
0x18005d0e5  mov     [rsp+arg_8], rsi
0x18005d0ea  push    rdi
0x18005d0eb  sub     rsp, 90h
0x18005d0f2  mov     rsi, rdx
0x18005d0f5  mov     rbx, rcx
0x18005d0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0ff  lea     rdi, WPP_GLOBAL_Control
0x18005d106  cmp     rcx, rdi
0x18005d109  jnz     loc_18005D1B6
0x18005d10f  mov     r9d, [rbx+90h]
0x18005d116  mov     rax, [rbx+0B0h]
0x18005d11d  sub     rax, [rbx+0B8h]
0x18005d124  cmp     r9, rax
0x18005d127  cmovnb  r9, rax
0x18005d12b  cmp     rsi, r9
0x18005d12e  jnz     loc_18005D1F3
0x18005d134  mov     eax, [rbx+0A0h]
0x18005d13a  lea     rdi, [rbx+158h]
0x18005d141  mov     rcx, [rbx+1A0h]; pio
0x18005d148  mov     [rdi+10h], eax
0x18005d14b  mov     rax, [rbx+0A0h]
0x18005d152  shr     rax, 20h
0x18005d156  mov     [rbx+16Ch], eax
0x18005d15c  mov     qword ptr [rbx+170h], 0
0x18005d167  call    cs:__imp_StartThreadpoolIo
0x18005d16d  mov     rdx, [rbx+88h]; lpBuffer
0x18005d174  xor     r9d, r9d; lpNumberOfBytesRead
0x18005d177  mov     r8d, esi; nNumberOfBytesToRead
0x18005d17a  mov     rcx, [rbx+140h]; hFile
0x18005d181  mov     [rsp+98h+lpOverlapped], rdi; lpOverlapped
0x18005d186  cmp     [rbx+178h], r9b
0x18005d18d  jnz     loc_18005D239
0x18005d193  call    cs:__imp_WriteFile
0x18005d199  test    eax, eax
0x18005d19b  jz      loc_18005D2AE
0x18005d1a1  lea     r11, [rsp+98h+var_8]
0x18005d1a9  mov     rbx, [r11+10h]
0x18005d1ad  mov     rsi, [r11+18h]
0x18005d1b1  mov     rsp, r11
0x18005d1b4  pop     rdi
0x18005d1b5  retn
0x18005d1b6  test    dword ptr [rcx+1Ch], 800h
0x18005d1bd  jz      loc_18005D10F
0x18005d1c3  mov     eax, [rbx+0A0h]
0x18005d1c9  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x18005d1d0  movzx   r9d, byte ptr [rbx+178h]
0x18005d1d8  mov     edx, 2Dh ; '-'
0x18005d1dd  mov     rcx, [rcx+10h]
0x18005d1e1  mov     [rsp+98h+var_70], eax
0x18005d1e5  mov     dword ptr [rsp+98h+lpOverlapped], esi
0x18005d1e9  call    WPP_SF_DDD
0x18005d1ee  jmp     loc_18005D10F
0x18005d1f3  mov     eax, esi
0x18005d1f5  sub     eax, r9d
0x18005d1f8  mov     [rbx+198h], eax
0x18005d1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d205  cmp     rcx, rdi
0x18005d208  jz      loc_18005D134
0x18005d20e  test    dword ptr [rcx+1Ch], 800h
0x18005d215  jz      loc_18005D134
0x18005d21b  mov     rcx, [rcx+10h]
0x18005d21f  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x18005d226  mov     edx, 2Eh ; '.'
0x18005d22b  mov     dword ptr [rsp+98h+lpOverlapped], eax
0x18005d22f  call    WPP_SF_Dd
0x18005d234  jmp     loc_18005D134
0x18005d239  call    cs:__imp_ReadFile
0x18005d23f  test    eax, eax
0x18005d241  jnz     loc_18005D1A1
0x18005d247  call    cs:__imp_GetLastError
0x18005d24d  mov     edi, eax
0x18005d24f  cmp     eax, 3E5h
0x18005d254  jz      loc_18005D1A1
0x18005d25a  mov     rcx, [rbx+1A0h]; pio
0x18005d261  call    cs:__imp_CancelThreadpoolIo
0x18005d267  test    edi, edi
0x18005d269  jle     short loc_18005D274
0x18005d26b  movzx   edi, di
0x18005d26e  or      edi, 80070000h
0x18005d274  xorps   xmm0, xmm0
0x18005d277  mov     [rsp+98h+var_50], edi
0x18005d27b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005d282  mov     [rsp+98h+var_4C], 6A6h
0x18005d28a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005d291  mov     [rsp+98h+pExceptionObject], rax
0x18005d296  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18005d29b  mov     [rsp+98h+var_48], 1
0x18005d2a3  movups  [rsp+98h+var_60], xmm0
0x18005d2a8  call    _CxxThrowException_0
0x18005d2ae  call    cs:__imp_GetLastError
0x18005d2b4  mov     edi, eax
0x18005d2b6  cmp     eax, 3E5h
0x18005d2bb  jz      loc_18005D1A1
0x18005d2c1  mov     rcx, [rbx+1A0h]; pio
0x18005d2c8  call    cs:__imp_CancelThreadpoolIo
0x18005d2ce  test    edi, edi
0x18005d2d0  jle     short loc_18005D2DB
0x18005d2d2  movzx   edi, di
0x18005d2d5  or      edi, 80070000h
0x18005d2db  xorps   xmm0, xmm0
0x18005d2de  mov     [rsp+98h+var_50], edi
0x18005d2e2  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005d2e9  mov     [rsp+98h+var_4C], 6B6h
0x18005d2f1  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005d2f8  mov     [rsp+98h+pExceptionObject], rax
0x18005d2fd  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18005d302  mov     [rsp+98h+var_48], 1
0x18005d30a  movups  [rsp+98h+var_60], xmm0
0x18005d30f  call    _CxxThrowException_0
```
