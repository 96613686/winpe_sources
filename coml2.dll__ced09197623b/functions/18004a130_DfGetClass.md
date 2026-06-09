# DfGetClass

- ea: `0x18004a130`
- end: `0x18004a382`
- name: `DfGetClass`
- size: `594`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x18000cdd8`
- `0x18001d820`
- `0x18001d8d8`
- `0x18001daa0`
- `0x18001db94`
- `0x180026bc4`
- `0x180030c08`
- `0x1800325d4`
- `0x1800391b4`
- `0x18003ab9c`
- `0x180042800`
- `0x180043100`
- `0x18004a130`
- `0x18004c020`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1aa`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004a1dc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004a1dc`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004a1a0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18004a1a0`

## pseudocode

```c
__int64 __fastcall DfGetClass(HANDLE hFile, _OWORD *a2)
{
  DWORD LastError; // eax
  signed int inited; // ebx
  struct IMalloc *v6; // rdx
  CFileStream *v7; // rax
  struct IMalloc *v8; // rsi
  CFileStream *v9; // rax
  CFileStream *v10; // rdi
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v13; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v14; // [rsp+38h] [rbp-C8h] BYREF
  struct IMalloc *v15; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Buffer[48]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+80h] [rbp-80h]
  char v18; // [rsp+92h] [rbp-6Eh]
  __int128 v19; // [rsp+A0h] [rbp-60h]

  NumberOfBytesRead = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  memset_0(Buffer, 0, 0x204u);
  if ( SetFilePointer(hFile, 0, 0, 0) || !ReadFile(hFile, Buffer, 0x200u, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    return (unsigned int)Win32ErrorToScode(LastError);
  }
  else if ( NumberOfBytesRead == 512 )
  {
    inited = CMSFHeader::Validate((CMSFHeader *)Buffer);
    if ( inited >= 0 )
    {
      inited = DfCreateSharedAllocator(&v15, 1);
      if ( inited >= 0 )
      {
        v7 = (CFileStream *)CMallocBased::operator new(0x78u, v6);
        v8 = v15;
        if ( v7 && (v9 = CFileStream::CFileStream(v7, v15), (v10 = v9) != 0) )
        {
          inited = CFileStream::InitGlobal(v9, 0, 0);
          if ( inited >= 0 )
          {
            inited = CFileStream::InitFromHandle(v10, hFile);
            if ( inited >= 0 )
            {
              inited = StgpAcquireOpenLocks((struct ILockBytes *)v10, 0x40u, 1, &v14);
              if ( inited >= 0 )
              {
                inited = StgpAcquireAccessLocks((struct ILockBytes *)v10, 0x40u, &v13);
                if ( inited >= 0 )
                {
                  inited = (*(__int64 (__fastcall **)(CFileStream *, unsigned __int64, _BYTE *, __int64, DWORD *))(*(_QWORD *)v10 + 24LL))(
                             v10,
                             (unsigned __int64)(unsigned int)(v17 + 1) << Buffer[30],
                             Buffer,
                             128,
                             &NumberOfBytesRead);
                  if ( inited >= 0 )
                  {
                    if ( NumberOfBytesRead == 128 )
                    {
                      if ( v18 == 5 )
                      {
                        inited = 0;
                        *a2 = v19;
                      }
                      else
                      {
                        inited = -2147286775;
                      }
                    }
                    else
                    {
                      inited = -2147287010;
                    }
                  }
                  StgpReleaseAccessLocks((struct ILockBytes *)v10, 0x40u, v13);
                }
                StgpReleaseOpenLocks((struct ILockBytes *)v10, 0x40u, v14);
              }
            }
          }
          (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v10 + 16LL))(v10);
        }
        else
        {
          inited = -2147287032;
        }
        ((void (__fastcall *)(struct IMalloc *))v8->lpVtbl->Release)(v8);
      }
    }
  }
  else
  {
    return (unsigned int)-2147286789;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18004a130  mov     [rsp-8+arg_10], rbx
0x18004a135  push    rbp
0x18004a136  push    rsi
0x18004a137  push    rdi
0x18004a138  push    r14
0x18004a13a  push    r15
0x18004a13c  lea     rbp, [rsp-170h]
0x18004a144  sub     rsp, 270h
0x18004a14b  mov     rax, cs:__security_cookie
0x18004a152  xor     rax, rsp
0x18004a155  mov     [rbp+190h+var_30], rax
0x18004a15c  mov     r15, rdx
0x18004a15f  mov     [rsp+290h+NumberOfBytesRead], 0
0x18004a167  mov     r14, rcx
0x18004a16a  mov     [rsp+290h+var_250], 0
0x18004a173  xor     edx, edx; Val
0x18004a175  mov     [rsp+290h+var_258], 0
0x18004a17d  lea     rcx, [rsp+290h+Buffer]; void *
0x18004a182  mov     [rsp+290h+var_25C], 0
0x18004a18a  mov     r8d, 204h; Size
0x18004a190  call    memset_0
0x18004a195  xor     r9d, r9d; dwMoveMethod
0x18004a198  xor     r8d, r8d; lpDistanceToMoveHigh
0x18004a19b  xor     edx, edx; lDistanceToMove
0x18004a19d  mov     rcx, r14; hFile
0x18004a1a0  call    cs:__imp_SetFilePointer
0x18004a1a6  test    eax, eax
0x18004a1a8  jz      short loc_18004A1BE
0x18004a1aa  call    cs:__imp_GetLastError
0x18004a1b0  mov     ecx, eax; unsigned int
0x18004a1b2  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004a1b7  mov     ebx, eax
0x18004a1b9  jmp     loc_18004A35A
0x18004a1be  mov     ebx, 200h
0x18004a1c3  mov     [rsp+290h+lpOverlapped], 0; lpOverlapped
0x18004a1cc  mov     r8d, ebx; nNumberOfBytesToRead
0x18004a1cf  lea     r9, [rsp+290h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004a1d4  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x18004a1d9  mov     rcx, r14; hFile
0x18004a1dc  call    cs:__imp_ReadFile
0x18004a1e2  test    eax, eax
0x18004a1e4  jz      short loc_18004A1AA
0x18004a1e6  cmp     [rsp+290h+NumberOfBytesRead], ebx
0x18004a1ea  jz      short loc_18004A1F6
0x18004a1ec  mov     ebx, 800300FBh
0x18004a1f1  jmp     loc_18004A35A
0x18004a1f6  lea     rcx, [rsp+290h+Buffer]; this
0x18004a1fb  call    ?Validate@CMSFHeader@@QEBAJXZ; CMSFHeader::Validate(void)
0x18004a200  mov     ebx, eax
0x18004a202  test    eax, eax
0x18004a204  js      loc_18004A35A
0x18004a20a  mov     edx, 1; int
0x18004a20f  lea     rcx, [rsp+290h+var_250]; struct IMalloc **
0x18004a214  call    ?DfCreateSharedAllocator@@YAJPEAPEAUIMalloc@@H@Z; DfCreateSharedAllocator(IMalloc * *,int)
0x18004a219  mov     ebx, eax
0x18004a21b  test    eax, eax
0x18004a21d  js      loc_18004A35A
0x18004a223  mov     ecx, 78h ; 'x'; unsigned __int64
0x18004a228  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18004a22d  mov     rsi, [rsp+290h+var_250]
0x18004a232  test    rax, rax
0x18004a235  jz      loc_18004A346
0x18004a23b  mov     rdx, rsi; struct IMalloc *
0x18004a23e  mov     rcx, rax; this
0x18004a241  call    ??0CFileStream@@QEAA@QEAUIMalloc@@@Z; CFileStream::CFileStream(IMalloc * const)
0x18004a246  mov     rdi, rax
0x18004a249  test    rax, rax
0x18004a24c  jz      loc_18004A346
0x18004a252  xor     r8d, r8d; unsigned int
0x18004a255  xor     edx, edx; unsigned int
0x18004a257  mov     rcx, rax; this
0x18004a25a  call    ?InitGlobal@CFileStream@@QEAAJKK@Z; CFileStream::InitGlobal(ulong,ulong)
0x18004a25f  mov     ebx, eax
0x18004a261  test    eax, eax
0x18004a263  js      loc_18004A335
0x18004a269  mov     rdx, r14; void *
0x18004a26c  mov     rcx, rdi; this
0x18004a26f  call    ?InitFromHandle@CFileStream@@QEAAJPEAX@Z; CFileStream::InitFromHandle(void *)
0x18004a274  mov     ebx, eax
0x18004a276  test    eax, eax
0x18004a278  js      loc_18004A335
0x18004a27e  mov     r8d, 1; int
0x18004a284  lea     r9, [rsp+290h+var_258]; unsigned int *
0x18004a289  mov     rcx, rdi; struct ILockBytes *
0x18004a28c  lea     r14d, [r8+3Fh]
0x18004a290  mov     edx, r14d; unsigned int
0x18004a293  call    ?StgpAcquireOpenLocks@@YAJPEAUILockBytes@@KHPEAK@Z; StgpAcquireOpenLocks(ILockBytes *,ulong,int,ulong *)
0x18004a298  mov     ebx, eax
0x18004a29a  test    eax, eax
0x18004a29c  js      loc_18004A335
0x18004a2a2  lea     r8, [rsp+290h+var_25C]; unsigned int *
0x18004a2a7  mov     edx, r14d; unsigned int
0x18004a2aa  mov     rcx, rdi; struct ILockBytes *
0x18004a2ad  call    ?StgpAcquireAccessLocks@@YAJPEAUILockBytes@@KPEAK@Z; StgpAcquireAccessLocks(ILockBytes *,ulong,ulong *)
0x18004a2b2  mov     ebx, eax
0x18004a2b4  test    eax, eax
0x18004a2b6  js      short loc_18004A325
0x18004a2b8  mov     edx, [rbp+190h+var_210]
0x18004a2bb  lea     r9d, [r14+40h]
0x18004a2bf  mov     cl, [rsp+290h+var_222]
0x18004a2c3  lea     r8, [rsp+290h+Buffer]
0x18004a2c8  mov     rax, [rdi]
0x18004a2cb  inc     edx
0x18004a2cd  shl     rdx, cl
0x18004a2d0  lea     rcx, [rsp+290h+NumberOfBytesRead]
0x18004a2d5  mov     [rsp+290h+lpOverlapped], rcx
0x18004a2da  mov     rcx, rdi
0x18004a2dd  mov     rax, [rax+18h]
0x18004a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2e6  mov     ebx, eax
0x18004a2e8  test    eax, eax
0x18004a2ea  js      short loc_18004A315
0x18004a2ec  cmp     [rsp+290h+NumberOfBytesRead], 80h
0x18004a2f4  jz      short loc_18004A2FD
0x18004a2f6  mov     ebx, 8003001Eh
0x18004a2fb  jmp     short loc_18004A315
0x18004a2fd  cmp     [rbp+190h+var_1FE], 5
0x18004a301  jz      short loc_18004A30A
0x18004a303  mov     ebx, 80030109h
0x18004a308  jmp     short loc_18004A315
0x18004a30a  movaps  xmm0, [rbp+190h+var_1F0]
0x18004a30e  xor     ebx, ebx
0x18004a310  movdqu  xmmword ptr [r15], xmm0
0x18004a315  mov     r8d, [rsp+290h+var_25C]; unsigned int
0x18004a31a  mov     edx, r14d; unsigned int
0x18004a31d  mov     rcx, rdi; struct ILockBytes *
0x18004a320  call    ?StgpReleaseAccessLocks@@YAXPEAUILockBytes@@KK@Z; StgpReleaseAccessLocks(ILockBytes *,ulong,ulong)
0x18004a325  mov     r8d, [rsp+290h+var_258]; unsigned int
0x18004a32a  mov     edx, r14d; unsigned int
0x18004a32d  mov     rcx, rdi; struct ILockBytes *
0x18004a330  call    ?StgpReleaseOpenLocks@@YAXPEAUILockBytes@@KK@Z; StgpReleaseOpenLocks(ILockBytes *,ulong,ulong)
0x18004a335  mov     rax, [rdi]
0x18004a338  mov     rcx, rdi
0x18004a33b  mov     rax, [rax+10h]
0x18004a33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a344  jmp     short loc_18004A34B
0x18004a346  mov     ebx, 80030008h
0x18004a34b  mov     rax, [rsi]
0x18004a34e  mov     rcx, rsi
0x18004a351  mov     rax, [rax+10h]
0x18004a355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a35a  mov     eax, ebx
0x18004a35c  mov     rcx, [rbp+190h+var_30]
0x18004a363  xor     rcx, rsp; StackCookie
0x18004a366  call    __security_check_cookie
0x18004a36b  mov     rbx, [rsp+290h+arg_10]
0x18004a373  add     rsp, 270h
0x18004a37a  pop     r15
0x18004a37c  pop     r14
0x18004a37e  pop     rdi
0x18004a37f  pop     rsi
0x18004a380  pop     rbp
0x18004a381  retn
```
