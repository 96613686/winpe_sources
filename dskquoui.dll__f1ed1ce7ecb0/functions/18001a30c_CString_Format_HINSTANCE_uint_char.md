# CString::Format(HINSTANCE__ *,uint,char * *)

- ea: `0x18001a30c`
- end: `0x18001a461`
- name: `?Format@CString@@QEAAHPEAUHINSTANCE__@@IPEAPEAD@Z`
- size: `341`
- prototype: `__int64 __fastcall(CString *__hidden this, HINSTANCE, unsigned int, char **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180019d24`
- `0x18001a468`

## callees

- `0x180001510`
- `0x180001534`
- `0x180006ec0`
- `0x180019d04`
- `0x180019e80`
- `0x18001a30c`
- `0x18001a49c`
- `0x18001cde0`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a34c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001a34c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a431`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a431`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a3b2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a3b2`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001a386`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18001a386`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a3e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CString::Format(CString *this, HINSTANCE a2, DWORD a3, char **a4)
{
  unsigned int v8; // ebx
  unsigned __int16 ThreadLocale; // ax
  __int64 v11; // rcx
  HLOCAL *v12; // rdi
  CString::StringValue *v13; // rax
  __int64 v14; // rdx
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-2060h] BYREF
  WCHAR Buffer[4104]; // [rsp+60h] [rbp-2048h] BYREF

  if ( LoadStringW(a2, a3, Buffer, 4097) <= 0 )
  {
    ThreadLocale = GetThreadLocale();
    if ( (int)FormatMessageW(0x1800u, a2, a3, ThreadLocale, Buffer, 0x1001u, a4) <= 0 )
    {
      v8 = 0;
      if ( GetLastError() )
      {
        CResourceException::CResourceException(pExceptionObject, v14, a2, a3);
        throw (CResourceException *)pExceptionObject;
      }
    }
    else
    {
      v11 = *((_QWORD *)this + 1);
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 12), 0xFFFFFFFF) == 1 )
        {
          v12 = (HLOCAL *)*((_QWORD *)this + 1);
          if ( v12 )
          {
            if ( *v12 )
              LocalFree(*v12);
            operator delete(v12, 0x18u);
          }
        }
      }
      *((_QWORD *)this + 1) = 0;
      v13 = (CString::StringValue *)operator new(0x18u);
      if ( v13 )
        v13 = (CString::StringValue *)CString::StringValue::StringValue(v13, Buffer);
      *((_QWORD *)this + 1) = v13;
      return 1;
    }
  }
  else
  {
    return (unsigned int)CString::Format(this, Buffer, a4);
  }
  return v8;
}

```

## disassembly

```asm
0x18001a30c  push    rbx
0x18001a30e  push    rbp
0x18001a30f  push    rsi
0x18001a310  push    rdi
0x18001a311  mov     eax, 2088h
0x18001a316  call    _alloca_probe
0x18001a31b  sub     rsp, rax
0x18001a31e  mov     rax, cs:__security_cookie
0x18001a325  xor     rax, rsp
0x18001a328  mov     [rsp+20A8h+var_38], rax
0x18001a330  mov     rbp, r9
0x18001a333  mov     esi, r8d
0x18001a336  mov     rdi, rdx
0x18001a339  mov     rbx, rcx
0x18001a33c  mov     r9d, 1001h; cchBufferMax
0x18001a342  lea     r8, [rsp+20A8h+Buffer]; lpBuffer
0x18001a347  mov     edx, esi; uID
0x18001a349  mov     rcx, rdi; hInstance
0x18001a34c  call    cs:__imp_LoadStringW
0x18001a352  test    eax, eax
0x18001a354  jle     short loc_18001A386
0x18001a356  mov     r8, rbp; char **
0x18001a359  lea     rdx, [rsp+20A8h+Buffer]; unsigned __int16 *
0x18001a35e  mov     rcx, rbx; this
0x18001a361  call    ?Format@CString@@QEAAHPEBGPEAPEAD@Z; CString::Format(ushort const *,char * *)
0x18001a366  mov     ebx, eax
0x18001a368  mov     eax, ebx
0x18001a36a  mov     rcx, [rsp+20A8h+var_38]
0x18001a372  xor     rcx, rsp; StackCookie
0x18001a375  call    __security_check_cookie
0x18001a37a  add     rsp, 2088h
0x18001a381  pop     rdi
0x18001a382  pop     rsi
0x18001a383  pop     rbp
0x18001a384  pop     rbx
0x18001a385  retn
0x18001a386  call    cs:__imp_GetThreadLocale
0x18001a38c  movzx   r9d, ax; dwLanguageId
0x18001a390  mov     [rsp+20A8h+Arguments], rbp; Arguments
0x18001a395  mov     [rsp+20A8h+nSize], 1001h; nSize
0x18001a39d  lea     rax, [rsp+20A8h+Buffer]
0x18001a3a2  mov     [rsp+20A8h+lpBuffer], rax; lpBuffer
0x18001a3a7  mov     r8d, esi; dwMessageId
0x18001a3aa  mov     rdx, rdi; lpSource
0x18001a3ad  mov     ecx, 1800h; dwFlags
0x18001a3b2  call    cs:__imp_FormatMessageW
0x18001a3b8  test    eax, eax
0x18001a3ba  jle     short loc_18001A42F
0x18001a3bc  mov     rcx, [rbx+8]
0x18001a3c0  mov     esi, 18h
0x18001a3c5  test    rcx, rcx
0x18001a3c8  jz      short loc_18001A3F9
0x18001a3ca  or      eax, 0FFFFFFFFh
0x18001a3cd  lock xadd [rcx+0Ch], eax
0x18001a3d2  cmp     eax, 1
0x18001a3d5  jnz     short loc_18001A3F9
0x18001a3d7  mov     rdi, [rbx+8]
0x18001a3db  test    rdi, rdi
0x18001a3de  jz      short loc_18001A3F9
0x18001a3e0  mov     rcx, [rdi]; hMem
0x18001a3e3  test    rcx, rcx
0x18001a3e6  jz      short loc_18001A3EE
0x18001a3e8  call    cs:__imp_LocalFree
0x18001a3ee  mov     rdx, rsi; unsigned __int64
0x18001a3f1  mov     rcx, rdi; void *
0x18001a3f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a3f9  mov     qword ptr [rbx+8], 0
0x18001a401  mov     rcx, rsi; uBytes
0x18001a404  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a409  mov     [rsp+20A8h+var_2068], rax
0x18001a40e  test    rax, rax
0x18001a411  jz      short loc_18001A421
0x18001a413  lea     rdx, [rsp+20A8h+Buffer]; unsigned __int16 *
0x18001a418  mov     rcx, rax; this
0x18001a41b  call    ??0StringValue@CString@@QEAA@PEBG@Z; CString::StringValue::StringValue(ushort const *)
0x18001a420  nop
0x18001a421  mov     [rbx+8], rax
0x18001a425  mov     ebx, 1
0x18001a42a  jmp     loc_18001A368
0x18001a42f  xor     ebx, ebx
0x18001a431  call    cs:__imp_GetLastError
0x18001a437  test    eax, eax
0x18001a439  jz      loc_18001A368
0x18001a43f  mov     r9d, esi
0x18001a442  mov     r8, rdi
0x18001a445  lea     rcx, [rsp+20A8h+pExceptionObject]
0x18001a44a  call    ??0CResourceException@@QEAA@W4type@0@PEAUHINSTANCE__@@I@Z; CResourceException::CResourceException(CResourceException::type,HINSTANCE__ *,uint)
0x18001a44f  lea     rdx, _TI2?AVCResourceException@@; pThrowInfo
0x18001a456  lea     rcx, [rsp+20A8h+pExceptionObject]; pExceptionObject
0x18001a45b  call    _CxxThrowException_0
```
