# WriteMasterKey(void *,MASTERKEY_STORED *)

- ea: `0x180003908`
- end: `0x180003b92`
- name: `?WriteMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@@Z`
- size: `650`
- prototype: `__int64 __fastcall(_QWORD *, struct MASTERKEY_STORED *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800048a4`
- `0x18002ea4c`

## callees

- `0x180003908`
- `0x180004780`
- `0x1800048e4`
- `0x1800060e0`
- `0x180012f00`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003984`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003984`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b37`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b0a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b0a`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180003b1f`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180003b1f`

## pseudocode

```c
__int64 __fastcall WriteMasterKey(_QWORD *a1, struct MASTERKEY_STORED *a2)
{
  bool v3; // cc
  unsigned int v5; // edx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  __int64 v8; // r14
  char *v9; // rax
  struct MASTERKEY_STORED_ON_DISK *v10; // rdi
  char *v11; // r12
  unsigned int v12; // ebp
  void *v13; // r15
  const void *v14; // rdx
  char *v15; // rsi
  const void *v16; // rdx
  const void *v17; // rdx
  const void *v18; // rdx
  HANDLE v19; // rbx
  struct MASTERKEY_STORED_ON_DISK *i; // rax
  HANDLE hFile; // [rsp+30h] [rbp-48h] BYREF
  int v23; // [rsp+88h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+18h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+98h] [rbp+20h]

  v3 = *(_DWORD *)a2 <= 2u;
  hFile = 0;
  if ( !v3 )
    return 0;
  v5 = *((_DWORD *)a2 + 25);
  if ( v5 > 0xFFFF )
    return 0;
  if ( *((_DWORD *)a2 + 28) > 0xFFFFu )
    return 0;
  v6 = *((_DWORD *)a2 + 32);
  if ( v6 > 0xFFFF )
    return 0;
  v7 = *((_DWORD *)a2 + 36);
  if ( v7 > 0xFFFF )
    return 0;
  nNumberOfBytesToWrite = v5 + 128 + *((_DWORD *)a2 + 28) + v7 + v6;
  v8 = nNumberOfBytesToWrite;
  v9 = (char *)LocalAlloc(0, nNumberOfBytesToWrite);
  v10 = (struct MASTERKEY_STORED_ON_DISK *)v9;
  if ( !v9 )
    return 0;
  v11 = v9 + 128;
  *(_DWORD *)v9 = *(_DWORD *)a2;
  v12 = 0;
  v13 = 0;
  *(_OWORD *)(v9 + 12) = *((_OWORD *)a2 + 1);
  *(_OWORD *)(v9 + 28) = *((_OWORD *)a2 + 2);
  *(_OWORD *)(v9 + 44) = *((_OWORD *)a2 + 3);
  *(_OWORD *)(v9 + 60) = *((_OWORD *)a2 + 4);
  *(_OWORD *)(v9 + 76) = *((_OWORD *)a2 + 5);
  *((_DWORD *)v9 + 23) = *((_DWORD *)a2 + 24);
  *((_DWORD *)v9 + 24) = *((_DWORD *)a2 + 25);
  *((_DWORD *)v9 + 26) = *((_DWORD *)a2 + 28);
  *((_DWORD *)v9 + 28) = *((_DWORD *)a2 + 32);
  *((_DWORD *)v9 + 30) = *((_DWORD *)a2 + 36);
  *(_QWORD *)(v9 + 4) = 0;
  *((_DWORD *)v9 + 25) = 0;
  *((_DWORD *)v9 + 27) = 0;
  *((_DWORD *)v9 + 29) = 0;
  *((_DWORD *)v9 + 31) = 0;
  v14 = (const void *)*((_QWORD *)a2 + 13);
  if ( v14 )
  {
    memcpy_0(v9 + 128, v14, *((unsigned int *)a2 + 25));
    v15 = &v11[*((unsigned int *)a2 + 25)];
  }
  else
  {
    v15 = v9 + 128;
  }
  v16 = (const void *)*((_QWORD *)a2 + 15);
  if ( v16 )
  {
    memcpy_0(v15, v16, *((unsigned int *)a2 + 28));
    v15 += *((unsigned int *)a2 + 28);
  }
  v17 = (const void *)*((_QWORD *)a2 + 17);
  if ( v17 )
  {
    memcpy_0(v15, v17, *((unsigned int *)a2 + 32));
    v15 += *((unsigned int *)a2 + 32);
  }
  v18 = (const void *)*((_QWORD *)a2 + 19);
  if ( v18 )
    memcpy_0(v15, v18, *((unsigned int *)a2 + 36));
  if ( a1 )
  {
    v13 = (void *)a1[9];
    AcquireExclusiveLockForUser(v13);
  }
  if ( !(unsigned int)OpenFileInStorageArea(
                        a1,
                        0xC0000000,
                        *((const unsigned __int16 **)a2 + 1),
                        (const unsigned __int16 *)a2 + 8,
                        &hFile) )
  {
    v19 = hFile;
    v23 = 0;
    NumberOfBytesWritten = 0;
    CheckToStompMasterKey(v10, hFile, &v23);
    if ( v23 )
    {
      v12 = WriteFile(v19, v10, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
      if ( v12 )
        v12 = FlushFileBuffers(v19);
    }
    else
    {
      v12 = 1;
    }
    CloseHandle(v19);
  }
  if ( v13 )
    ReleaseExclusiveLockForUser(v13);
  for ( i = v10; v8; --v8 )
  {
    *(_BYTE *)i = 0;
    i = (struct MASTERKEY_STORED_ON_DISK *)((char *)i + 1);
  }
  LocalFree(v10);
  return v12;
}

```

## disassembly

```asm
0x180003908  mov     [rsp+arg_0], rbx
0x18000390d  push    rbp
0x18000390e  push    rsi
0x18000390f  push    rdi
0x180003910  push    r12
0x180003912  push    r13
0x180003914  push    r14
0x180003916  push    r15
0x180003918  sub     rsp, 40h
0x18000391c  xor     esi, esi
0x18000391e  mov     rbx, rdx
0x180003921  cmp     dword ptr [rdx], 2
0x180003924  mov     r13, rcx
0x180003927  mov     [rsp+78h+hFile], rsi
0x18000392c  ja      loc_180003B77
0x180003932  mov     edx, [rdx+64h]
0x180003935  mov     r8d, 0FFFFh
0x18000393b  cmp     edx, r8d
0x18000393e  ja      loc_180003B77
0x180003944  cmp     [rbx+70h], r8d
0x180003948  ja      loc_180003B77
0x18000394e  mov     eax, [rbx+80h]
0x180003954  cmp     eax, r8d
0x180003957  ja      loc_180003B77
0x18000395d  mov     ecx, [rbx+90h]
0x180003963  cmp     ecx, r8d
0x180003966  ja      loc_180003B77
0x18000396c  add     eax, ecx
0x18000396e  sub     edx, 0FFFFFF80h
0x180003971  add     eax, [rbx+70h]
0x180003974  xor     ecx, ecx; uFlags
0x180003976  add     eax, edx
0x180003978  mov     edx, eax; uBytes
0x18000397a  mov     [rsp+78h+nNumberOfBytesToWrite], eax
0x180003981  mov     r14d, eax
0x180003984  call    cs:__imp_LocalAlloc
0x18000398b  nop     dword ptr [rax+rax+00h]
0x180003990  mov     rdi, rax
0x180003993  test    rax, rax
0x180003996  jz      loc_180003B77
0x18000399c  mov     eax, [rbx]
0x18000399e  lea     r12, [rdi+80h]
0x1800039a5  mov     [rdi], eax
0x1800039a7  mov     ebp, esi
0x1800039a9  movups  xmm0, xmmword ptr [rbx+10h]
0x1800039ad  mov     r15d, esi
0x1800039b0  movups  xmmword ptr [rdi+0Ch], xmm0
0x1800039b4  movups  xmm1, xmmword ptr [rbx+20h]
0x1800039b8  movups  xmmword ptr [rdi+1Ch], xmm1
0x1800039bc  movups  xmm0, xmmword ptr [rbx+30h]
0x1800039c0  movups  xmmword ptr [rdi+2Ch], xmm0
0x1800039c4  movups  xmm1, xmmword ptr [rbx+40h]
0x1800039c8  movups  xmmword ptr [rdi+3Ch], xmm1
0x1800039cc  movups  xmm0, xmmword ptr [rbx+50h]
0x1800039d0  movups  xmmword ptr [rdi+4Ch], xmm0
0x1800039d4  mov     eax, [rbx+60h]
0x1800039d7  mov     [rdi+5Ch], eax
0x1800039da  mov     eax, [rbx+64h]
0x1800039dd  mov     [rdi+60h], eax
0x1800039e0  mov     eax, [rbx+70h]
0x1800039e3  mov     [rdi+68h], eax
0x1800039e6  mov     eax, [rbx+80h]
0x1800039ec  mov     [rdi+70h], eax
0x1800039ef  mov     eax, [rbx+90h]
0x1800039f5  mov     [rdi+78h], eax
0x1800039f8  mov     [rdi+4], rsi
0x1800039fc  mov     [rdi+64h], esi
0x1800039ff  mov     [rdi+6Ch], esi
0x180003a02  mov     [rdi+74h], esi
0x180003a05  mov     [rdi+7Ch], esi
0x180003a08  mov     rdx, [rbx+68h]; Src
0x180003a0c  test    rdx, rdx
0x180003a0f  jz      short loc_180003A25
0x180003a11  mov     r8d, [rbx+64h]; Size
0x180003a15  mov     rcx, r12; void *
0x180003a18  call    memcpy_0
0x180003a1d  mov     esi, [rbx+64h]
0x180003a20  add     rsi, r12
0x180003a23  jmp     short loc_180003A28
0x180003a25  mov     rsi, r12
0x180003a28  mov     rdx, [rbx+78h]; Src
0x180003a2c  xor     r12d, r12d
0x180003a2f  test    rdx, rdx
0x180003a32  jz      short loc_180003A46
0x180003a34  mov     r8d, [rbx+70h]; Size
0x180003a38  mov     rcx, rsi; void *
0x180003a3b  call    memcpy_0
0x180003a40  mov     eax, [rbx+70h]
0x180003a43  add     rsi, rax
0x180003a46  mov     rdx, [rbx+88h]; Src
0x180003a4d  test    rdx, rdx
0x180003a50  jz      short loc_180003A6A
0x180003a52  mov     r8d, [rbx+80h]; Size
0x180003a59  mov     rcx, rsi; void *
0x180003a5c  call    memcpy_0
0x180003a61  mov     eax, [rbx+80h]
0x180003a67  add     rsi, rax
0x180003a6a  mov     rdx, [rbx+98h]; Src
0x180003a71  test    rdx, rdx
0x180003a74  jz      short loc_180003A85
0x180003a76  mov     r8d, [rbx+90h]; Size
0x180003a7d  mov     rcx, rsi; void *
0x180003a80  call    memcpy_0
0x180003a85  test    r13, r13
0x180003a88  jz      short loc_180003A96
0x180003a8a  mov     r15, [r13+48h]
0x180003a8e  mov     rcx, r15; void *
0x180003a91  call    ?AcquireExclusiveLockForUser@@YAXPEAX@Z; AcquireExclusiveLockForUser(void *)
0x180003a96  mov     r8, [rbx+8]; unsigned __int16 *
0x180003a9a  lea     rax, [rsp+78h+hFile]
0x180003a9f  lea     r9, [rbx+10h]; unsigned __int16 *
0x180003aa3  mov     [rsp+78h+lpOverlapped], rax; void **
0x180003aa8  mov     edx, 0C0000000h; unsigned int
0x180003aad  mov     rcx, r13; void *
0x180003ab0  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x180003ab5  test    eax, eax
0x180003ab7  jnz     loc_180003B43
0x180003abd  mov     rbx, [rsp+78h+hFile]
0x180003ac2  lea     r8, [rsp+78h+arg_8]; int *
0x180003aca  mov     rdx, rbx; void *
0x180003acd  mov     [rsp+78h+arg_8], r12d
0x180003ad5  mov     rcx, rdi; struct MASTERKEY_STORED_ON_DISK *
0x180003ad8  mov     [rsp+78h+NumberOfBytesWritten], r12d
0x180003ae0  call    ?CheckToStompMasterKey@@YAHPEAUMASTERKEY_STORED_ON_DISK@@PEAXPEAH@Z; CheckToStompMasterKey(MASTERKEY_STORED_ON_DISK *,void *,int *)
0x180003ae5  cmp     [rsp+78h+arg_8], r12d
0x180003aed  jz      short loc_180003B2F
0x180003aef  mov     r8d, [rsp+78h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180003af7  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180003aff  mov     rdx, rdi; lpBuffer
0x180003b02  mov     [rsp+78h+lpOverlapped], r12; lpOverlapped
0x180003b07  mov     rcx, rbx; hFile
0x180003b0a  call    cs:__imp_WriteFile
0x180003b11  nop     dword ptr [rax+rax+00h]
0x180003b16  mov     ebp, eax
0x180003b18  test    eax, eax
0x180003b1a  jz      short loc_180003B34
0x180003b1c  mov     rcx, rbx; hFile
0x180003b1f  call    cs:__imp_FlushFileBuffers
0x180003b26  nop     dword ptr [rax+rax+00h]
0x180003b2b  mov     ebp, eax
0x180003b2d  jmp     short loc_180003B34
0x180003b2f  mov     ebp, 1
0x180003b34  mov     rcx, rbx; hObject
0x180003b37  call    cs:__imp_CloseHandle
0x180003b3e  nop     dword ptr [rax+rax+00h]
0x180003b43  test    r15, r15
0x180003b46  jz      short loc_180003B50
0x180003b48  mov     rcx, r15; pSid2
0x180003b4b  call    ?ReleaseExclusiveLockForUser@@YAXPEAX@Z; ReleaseExclusiveLockForUser(void *)
0x180003b50  mov     rax, rdi
0x180003b53  test    r14, r14
0x180003b56  jz      short loc_180003B64
0x180003b58  mov     [rax], r12b
0x180003b5b  inc     rax
0x180003b5e  sub     r14, 1
0x180003b62  jnz     short loc_180003B58
0x180003b64  mov     rcx, rdi; hMem
0x180003b67  call    cs:__imp_LocalFree
0x180003b6e  nop     dword ptr [rax+rax+00h]
0x180003b73  mov     eax, ebp
0x180003b75  jmp     short loc_180003B79
0x180003b77  xor     eax, eax
0x180003b79  mov     rbx, [rsp+78h+arg_0]
0x180003b81  add     rsp, 40h
0x180003b85  pop     r15
0x180003b87  pop     r14
0x180003b89  pop     r13
0x180003b8b  pop     r12
0x180003b8d  pop     rdi
0x180003b8e  pop     rsi
0x180003b8f  pop     rbp
0x180003b90  retn
```
