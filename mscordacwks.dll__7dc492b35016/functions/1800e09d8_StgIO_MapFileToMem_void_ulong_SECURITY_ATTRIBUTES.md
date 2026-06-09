# StgIO::MapFileToMem(void * &,ulong *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800e09d8`
- end: `0x1800e0d2c`
- name: `?MapFileToMem@StgIO@@QEAAJAEAPEAXPEAKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `852`
- prototype: `__int64 __fastcall(StgIO *__hidden this, void **, unsigned int *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ddd8c`
- `0x1800dfdc0`
- `0x1800e1528`

## callees

- `0x18007262c`
- `0x180072664`
- `0x1800727b8`
- `0x1800e06ac`
- `0x1800e0928`
- `0x1800e09d8`
- `0x1800f0490`
- `0x1800f0d20`
- `0x1800f3020`
- `0x180106100`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1800e0be4`
- `KERNEL32!MapViewOfFile` at `0x1800e0be4`
- `KERNEL32!CreateFileMappingW` at `0x1800e0b79`
- `KERNEL32!CreateFileMappingW` at `0x1800e0b79`
- `KERNEL32!GetLastError` at `0x1800e0b88`
- `KERNEL32!GetLastError` at `0x1800e0bb0`
- `KERNEL32!GetLastError` at `0x1800e0bfb`
- `KERNEL32!GetLastError` at `0x1800e0b88`
- `KERNEL32!GetLastError` at `0x1800e0bb0`
- `KERNEL32!GetLastError` at `0x1800e0bfb`
- `KERNEL32!CloseHandle` at `0x1800e0ad1`
- `KERNEL32!CloseHandle` at `0x1800e0b24`
- `KERNEL32!CloseHandle` at `0x1800e0ad1`
- `KERNEL32!CloseHandle` at `0x1800e0b24`

## pseudocode

```c
__int64 __fastcall StgIO::MapFileToMem(StgIO *this, void **a2, unsigned int *a3, struct _SECURITY_ATTRIBUTES *a4)
{
  const struct NoThrow *v7; // rdx
  unsigned __int64 v8; // r8
  __int16 v9; // cx
  void *v10; // rax
  unsigned int v11; // r8d
  int v12; // edi
  unsigned int v13; // r8d
  void *v14; // rcx
  int v15; // edx
  __int64 v16; // rcx
  int v17; // eax
  void *v18; // rcx
  void *v19; // rax
  HANDLE FileMappingW; // rax
  signed int v21; // eax
  __int64 v22; // rcx
  LPVOID v24; // rax
  signed int LastError; // eax
  __int64 v26; // rcx
  unsigned int v27; // r8d
  unsigned int v28; // ecx
  unsigned int v29; // esi
  void *v30; // rax
  void *v31; // rax
  unsigned int v32; // [rsp+30h] [rbp-58h] BYREF

  if ( !*((_QWORD *)this + 20) && !*((_QWORD *)this + 12) && !*((_QWORD *)this + 13) )
  {
    v7 = (const struct NoThrow *)*((unsigned int *)this + 34);
    if ( (unsigned int)((_DWORD)v7 - 4) > 2 )
    {
      v8 = (unsigned __int64)this + 4;
      v9 = *((_WORD *)this + 2);
      if ( v9 || *((_DWORD *)this + 32) > 0x10000u )
      {
        if ( (*((_BYTE *)this + 132) & 2) != 0 || (_DWORD)v7 == 3 )
        {
          v27 = StgIO::m_iPageSize;
          v28 = *((_DWORD *)this + 32);
          v29 = StgIO::m_iPageSize + ((v28 - 1) & ~(StgIO::m_iPageSize - 1));
          if ( v29 < v28 )
          {
            v12 = PostError(2148734230LL);
            if ( v12 < 0 )
              goto LABEL_22;
            v27 = StgIO::m_iPageSize;
          }
          v30 = operator new(v29 / v27, (const struct NoThrow *)(v29 % v27));
          *((_QWORD *)this + 20) = v30;
          if ( v30 )
          {
            memset(v30, 0, v29 / StgIO::m_iPageSize);
            v31 = ClrVirtualAlloc(0, v29, 0x2000u, 1u);
            *((_QWORD *)this + 15) = v31;
            *((_QWORD *)this + 14) = v31;
            if ( !v31 )
            {
              v17 = PostError(2147942414LL);
              goto LABEL_20;
            }
            goto LABEL_19;
          }
          v22 = 2147942414LL;
        }
        else
        {
          FileMappingW = CreateFileMappingW(*((HANDLE *)this + 11), 0, 2u, 0, 0, (LPCWSTR)(v8 & -(__int64)(v9 != 0)));
          *((_QWORD *)this + 12) = FileMappingW;
          if ( FileMappingW )
          {
            *((_DWORD *)this + 35) = 1;
            if ( GetLastError() == 183 )
            {
              v17 = PostError(2148733194LL);
              goto LABEL_20;
            }
            v24 = MapViewOfFile(*((HANDLE *)this + 12), 4u, 0, 0, 0);
            *((_QWORD *)this + 15) = v24;
            *((_QWORD *)this + 14) = v24;
            if ( !v24 )
            {
              LastError = GetLastError();
              v26 = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                v26 = (unsigned int)LastError;
              v12 = PostError(v26);
              if ( v12 >= 0 )
                v12 = PostError(2148733198LL);
              *((_QWORD *)this + 15) = 0;
              *((_QWORD *)this + 14) = 0;
LABEL_21:
              if ( v12 >= 0 )
              {
                v19 = (void *)*((_QWORD *)this + 15);
LABEL_47:
                *a2 = v19;
                if ( a3 )
                  *a3 = *((_DWORD *)this + 32);
                return (unsigned int)v12;
              }
LABEL_22:
              v18 = (void *)*((_QWORD *)this + 12);
              if ( v18 )
                CloseHandle(v18);
              *((_QWORD *)this + 12) = 0;
              v19 = 0;
              *((_QWORD *)this + 15) = 0;
              *((_QWORD *)this + 14) = 0;
              *((_DWORD *)this + 32) = 0;
              goto LABEL_47;
            }
LABEL_19:
            v17 = StgIO::Seek(this, 0, v13);
LABEL_20:
            v12 = v17;
            goto LABEL_21;
          }
          v21 = GetLastError();
          v22 = (unsigned __int16)v21 | 0x80070000;
          if ( v21 <= 0 )
            v22 = (unsigned int)v21;
        }
        return PostError(v22);
      }
      v32 = *((_DWORD *)this + 32);
      v10 = operator new((int)v32, v7);
      *((_QWORD *)this + 15) = v10;
      *((_QWORD *)this + 14) = v10;
      if ( !v10 )
      {
        v12 = -2147024882;
        goto LABEL_22;
      }
      v12 = StgIO::Seek(this, 0, v11);
      if ( v12 < 0 )
        goto LABEL_22;
      v12 = StgIO::Read(this, *((void **)this + 15), v32, &v32);
      if ( v12 < 0 )
      {
        operator delete(*((void **)this + 15));
        *((_QWORD *)this + 15) = 0;
        goto LABEL_22;
      }
      v14 = (void *)*((_QWORD *)this + 11);
      if ( v14 == (void *)-1LL )
      {
        v16 = *((_QWORD *)this + 10);
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          *((_QWORD *)this + 10) = 0;
        }
      }
      else
      {
        v15 = 6;
        if ( (*((_BYTE *)this + 132) & 6) != 0 )
        {
LABEL_18:
          *((_DWORD *)this + 34) = v15;
          *((_BYTE *)this + 72) |= 8u;
          goto LABEL_19;
        }
        CloseHandle(v14);
        *((_QWORD *)this + 11) = -1;
      }
      v15 = 4;
      goto LABEL_18;
    }
  }
  *a2 = (void *)*((_QWORD *)this + 15);
  if ( a3 )
    *a3 = *((_DWORD *)this + 32);
  return 0;
}

```

## disassembly

```asm
0x1800e09d8  mov     [rsp+arg_18], rbx
0x1800e09dd  push    rbp
0x1800e09de  push    rsi
0x1800e09df  push    rdi
0x1800e09e0  push    r14
0x1800e09e2  push    r15
0x1800e09e4  sub     rsp, 60h
0x1800e09e8  mov     rax, cs:__security_cookie
0x1800e09ef  xor     rax, rsp
0x1800e09f2  mov     [rsp+88h+var_30], rax
0x1800e09f7  xor     ebp, ebp
0x1800e09f9  mov     r14, r8
0x1800e09fc  mov     r15, rdx
0x1800e09ff  mov     rbx, rcx
0x1800e0a02  cmp     [rcx+0A0h], rbp
0x1800e0a09  jnz     loc_1800E0CF4
0x1800e0a0f  cmp     [rcx+60h], rbp
0x1800e0a13  jnz     loc_1800E0CF4
0x1800e0a19  cmp     [rcx+68h], rbp
0x1800e0a1d  jnz     loc_1800E0CF4
0x1800e0a23  mov     edx, [rcx+88h]; struct NoThrow *
0x1800e0a29  lea     eax, [rdx-4]
0x1800e0a2c  cmp     eax, 2
0x1800e0a2f  jbe     loc_1800E0CF4
0x1800e0a35  lea     r8, [rcx+4]
0x1800e0a39  movzx   ecx, word ptr [r8]
0x1800e0a3d  test    cx, cx
0x1800e0a40  jnz     loc_1800E0B44
0x1800e0a46  movsxd  rax, dword ptr [rbx+80h]
0x1800e0a4d  cmp     eax, 10000h
0x1800e0a52  ja      loc_1800E0B44
0x1800e0a58  mov     rcx, rax; dwBytes
0x1800e0a5b  mov     [rsp+88h+var_58], eax
0x1800e0a5f  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800e0a64  mov     [rbx+78h], rax
0x1800e0a68  mov     [rbx+70h], rax
0x1800e0a6c  test    rax, rax
0x1800e0a6f  jnz     short loc_1800E0A7B
0x1800e0a71  mov     edi, 8007000Eh
0x1800e0a76  jmp     loc_1800E0B1B
0x1800e0a7b  xor     edx, edx; int
0x1800e0a7d  mov     rcx, rbx; this
0x1800e0a80  call    ?Seek@StgIO@@QEAAJJK@Z; StgIO::Seek(long,ulong)
0x1800e0a85  mov     edi, eax
0x1800e0a87  test    eax, eax
0x1800e0a89  js      loc_1800E0B1B
0x1800e0a8f  mov     r8d, [rsp+88h+var_58]; unsigned int
0x1800e0a94  lea     r9, [rsp+88h+var_58]; unsigned int *
0x1800e0a99  mov     rdx, [rbx+78h]; void *
0x1800e0a9d  mov     rcx, rbx; this
0x1800e0aa0  call    ?Read@StgIO@@QEAAJPEAXKPEAK@Z; StgIO::Read(void *,ulong,ulong *)
0x1800e0aa5  mov     edi, eax
0x1800e0aa7  test    eax, eax
0x1800e0aa9  jns     short loc_1800E0ABA
0x1800e0aab  mov     rcx, [rbx+78h]; lpMem
0x1800e0aaf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e0ab4  mov     [rbx+78h], rbp
0x1800e0ab8  jmp     short loc_1800E0B1B
0x1800e0aba  mov     rcx, [rbx+58h]; hObject
0x1800e0abe  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e0ac2  jz      short loc_1800E0ADE
0x1800e0ac4  mov     edx, 6
0x1800e0ac9  test    [rbx+84h], dl
0x1800e0acf  jnz     short loc_1800E0AFD
0x1800e0ad1  call    cs:__imp_CloseHandle
0x1800e0ad7  or      qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x1800e0adc  jmp     short loc_1800E0AF8
0x1800e0ade  mov     rcx, [rbx+50h]
0x1800e0ae2  test    rcx, rcx
0x1800e0ae5  jz      short loc_1800E0AF8
0x1800e0ae7  mov     rax, [rcx]
0x1800e0aea  mov     rax, [rax+10h]
0x1800e0aee  call    cs:__guard_dispatch_icall_fptr
0x1800e0af4  mov     [rbx+50h], rbp
0x1800e0af8  mov     edx, 4
0x1800e0afd  mov     [rbx+88h], edx
0x1800e0b03  or      byte ptr [rbx+48h], 8
0x1800e0b07  xor     edx, edx; int
0x1800e0b09  mov     rcx, rbx; this
0x1800e0b0c  call    ?Seek@StgIO@@QEAAJJK@Z; StgIO::Seek(long,ulong)
0x1800e0b11  mov     edi, eax
0x1800e0b13  test    edi, edi
0x1800e0b15  jns     loc_1800E0CDB
0x1800e0b1b  mov     rcx, [rbx+60h]; hObject
0x1800e0b1f  test    rcx, rcx
0x1800e0b22  jz      short loc_1800E0B2A
0x1800e0b24  call    cs:__imp_CloseHandle
0x1800e0b2a  mov     [rbx+60h], rbp
0x1800e0b2e  mov     rax, rbp
0x1800e0b31  mov     [rbx+78h], rbp
0x1800e0b35  mov     [rbx+70h], rbp
0x1800e0b39  mov     [rbx+80h], ebp
0x1800e0b3f  jmp     loc_1800E0CDF
0x1800e0b44  test    byte ptr [rbx+84h], 2
0x1800e0b4b  jnz     loc_1800E0C33
0x1800e0b51  cmp     edx, 3
0x1800e0b54  jz      loc_1800E0C33
0x1800e0b5a  neg     cx
0x1800e0b5d  mov     rcx, [rbx+58h]; hFile
0x1800e0b61  sbb     rax, rax
0x1800e0b64  xor     r9d, r9d; dwMaximumSizeHigh
0x1800e0b67  and     rax, r8
0x1800e0b6a  xor     edx, edx; lpFileMappingAttributes
0x1800e0b6c  mov     [rsp+88h+lpName], rax; lpName
0x1800e0b71  mov     [rsp+88h+dwMaximumSizeLow], ebp; dwMaximumSizeLow
0x1800e0b75  lea     r8d, [r9+2]; flProtect
0x1800e0b79  call    cs:__imp_CreateFileMappingW
0x1800e0b7f  mov     [rbx+60h], rax
0x1800e0b83  test    rax, rax
0x1800e0b86  jnz     short loc_1800E0BA6
0x1800e0b88  call    cs:__imp_GetLastError
0x1800e0b8e  movzx   ecx, ax
0x1800e0b91  or      ecx, 80070000h
0x1800e0b97  test    eax, eax
0x1800e0b99  cmovle  ecx, eax
0x1800e0b9c  call    PostError
0x1800e0ba1  jmp     loc_1800E0D0B
0x1800e0ba6  mov     dword ptr [rbx+8Ch], 1
0x1800e0bb0  call    cs:__imp_GetLastError
0x1800e0bb6  cmp     eax, 0B7h
0x1800e0bbb  jnz     short loc_1800E0BD1
0x1800e0bbd  lea     rdx, [rsp+88h+var_50]
0x1800e0bc2  mov     ecx, 8013110Ah
0x1800e0bc7  call    PostError
0x1800e0bcc  jmp     loc_1800E0B11
0x1800e0bd1  mov     rcx, [rbx+60h]; hFileMappingObject
0x1800e0bd5  xor     r9d, r9d; dwFileOffsetLow
0x1800e0bd8  xor     r8d, r8d; dwFileOffsetHigh
0x1800e0bdb  mov     qword ptr [rsp+88h+dwMaximumSizeLow], rbp; dwNumberOfBytesToMap
0x1800e0be0  lea     edx, [r9+4]; dwDesiredAccess
0x1800e0be4  call    cs:__imp_MapViewOfFile
0x1800e0bea  mov     [rbx+78h], rax
0x1800e0bee  mov     [rbx+70h], rax
0x1800e0bf2  test    rax, rax
0x1800e0bf5  jnz     loc_1800E0B07
0x1800e0bfb  call    cs:__imp_GetLastError
0x1800e0c01  movzx   ecx, ax
0x1800e0c04  or      ecx, 80070000h
0x1800e0c0a  test    eax, eax
0x1800e0c0c  cmovle  ecx, eax
0x1800e0c0f  call    PostError
0x1800e0c14  mov     edi, eax
0x1800e0c16  test    eax, eax
0x1800e0c18  js      short loc_1800E0C26
0x1800e0c1a  mov     ecx, 8013110Eh
0x1800e0c1f  call    PostError
0x1800e0c24  mov     edi, eax
0x1800e0c26  mov     [rbx+78h], rbp
0x1800e0c2a  mov     [rbx+70h], rbp
0x1800e0c2e  jmp     loc_1800E0B13
0x1800e0c33  mov     r8d, cs:?m_iPageSize@StgIO@@0HA; int StgIO::m_iPageSize
0x1800e0c3a  mov     ecx, [rbx+80h]
0x1800e0c40  lea     esi, [r8-1]
0x1800e0c44  not     esi
0x1800e0c46  lea     eax, [rcx-1]
0x1800e0c49  and     esi, eax
0x1800e0c4b  add     esi, r8d
0x1800e0c4e  cmp     esi, ecx
0x1800e0c50  jnb     short loc_1800E0C6D
0x1800e0c52  mov     ecx, 80131516h
0x1800e0c57  call    PostError
0x1800e0c5c  mov     edi, eax
0x1800e0c5e  test    eax, eax
0x1800e0c60  js      loc_1800E0B1B
0x1800e0c66  mov     r8d, cs:?m_iPageSize@StgIO@@0HA; int StgIO::m_iPageSize
0x1800e0c6d  xor     edx, edx; struct NoThrow *
0x1800e0c6f  mov     eax, esi
0x1800e0c71  div     r8d
0x1800e0c74  mov     ecx, eax; dwBytes
0x1800e0c76  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800e0c7b  mov     [rbx+0A0h], rax
0x1800e0c82  mov     rcx, rax; void *
0x1800e0c85  test    rax, rax
0x1800e0c88  jnz     short loc_1800E0C94
0x1800e0c8a  mov     ecx, 8007000Eh
0x1800e0c8f  jmp     loc_1800E0B9C
0x1800e0c94  xor     edx, edx
0x1800e0c96  mov     eax, esi
0x1800e0c98  div     cs:?m_iPageSize@StgIO@@0HA; int StgIO::m_iPageSize
0x1800e0c9e  xor     edx, edx; Val
0x1800e0ca0  mov     r8d, eax; Size
0x1800e0ca3  call    memset
0x1800e0ca8  xor     ecx, ecx; void *
0x1800e0caa  mov     edx, esi; unsigned __int64
0x1800e0cac  mov     r8d, 2000h; unsigned int
0x1800e0cb2  lea     r9d, [rcx+1]; unsigned int
0x1800e0cb6  call    ?ClrVirtualAlloc@@YAPEAXPEAX_KKK@Z; ClrVirtualAlloc(void *,unsigned __int64,ulong,ulong)
0x1800e0cbb  mov     [rbx+78h], rax
0x1800e0cbf  mov     [rbx+70h], rax
0x1800e0cc3  test    rax, rax
0x1800e0cc6  jnz     loc_1800E0B07
0x1800e0ccc  mov     ecx, 8007000Eh
0x1800e0cd1  call    PostError
0x1800e0cd6  jmp     loc_1800E0B11
0x1800e0cdb  mov     rax, [rbx+78h]
0x1800e0cdf  mov     [r15], rax
0x1800e0ce2  test    r14, r14
0x1800e0ce5  jz      short loc_1800E0CF0
0x1800e0ce7  mov     eax, [rbx+80h]
0x1800e0ced  mov     [r14], eax
0x1800e0cf0  mov     eax, edi
0x1800e0cf2  jmp     short loc_1800E0D0B
0x1800e0cf4  mov     rax, [rcx+78h]
0x1800e0cf8  mov     [r15], rax
0x1800e0cfb  test    r14, r14
0x1800e0cfe  jz      short loc_1800E0D09
0x1800e0d00  mov     eax, [rcx+80h]
0x1800e0d06  mov     [r8], eax
0x1800e0d09  xor     eax, eax
0x1800e0d0b  mov     rcx, [rsp+88h+var_30]
0x1800e0d10  xor     rcx, rsp; StackCookie
0x1800e0d13  call    __security_check_cookie
0x1800e0d18  mov     rbx, [rsp+88h+arg_18]
0x1800e0d20  add     rsp, 60h
0x1800e0d24  pop     r15
0x1800e0d26  pop     r14
0x1800e0d28  pop     rdi
0x1800e0d29  pop     rsi
0x1800e0d2a  pop     rbp
0x1800e0d2b  retn
```
