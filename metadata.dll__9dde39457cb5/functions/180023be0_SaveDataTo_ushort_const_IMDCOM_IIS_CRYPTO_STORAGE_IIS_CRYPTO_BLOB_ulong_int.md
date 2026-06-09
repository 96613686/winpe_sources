# SaveDataTo(ushort const *,IMDCOM *,IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ulong *,int *)

- ea: `0x180023be0`
- end: `0x180023dec`
- name: `?SaveDataTo@@YAJPEBGPEAUIMDCOM@@PEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@PEAKPEAH@Z`
- size: `524`
- prototype: `int(const unsigned __int16 *, struct IMDCOM *, struct IIS_CRYPTO_STORAGE *, struct _IIS_CRYPTO_BLOB *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000b3a0`
- `0x180018f60`

## callees

- `0x180023be0`
- `0x180023df4`
- `0x180031010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180023cf5`
- `KERNEL32!CreateFileW` at `0x180023cf5`
- `KERNEL32!CloseHandle` at `0x180023d68`
- `KERNEL32!CloseHandle` at `0x180023d68`
- `KERNEL32!WaitForSingleObject` at `0x180023ca7`
- `KERNEL32!WaitForSingleObject` at `0x180023ca7`
- `KERNEL32!ReleaseSemaphore` at `0x180023da9`
- `KERNEL32!ReleaseSemaphore` at `0x180023da9`
- `KERNEL32!DeleteFileW` at `0x180023d75`
- `KERNEL32!DeleteFileW` at `0x180023d75`
- `KERNEL32!GetLastError` at `0x180023d04`
- `KERNEL32!GetLastError` at `0x180023d04`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180023d82`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180023d82`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180023d22`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180023d22`

## pseudocode

```c
__int64 __fastcall SaveDataTo(
        const unsigned __int16 *a1,
        struct IMDCOM *a2,
        struct IIS_CRYPTO_STORAGE *a3,
        struct _IIS_CRYPTO_BLOB *a4,
        unsigned int *a5,
        int *a6)
{
  const WCHAR *v6; // rbp
  int *v7; // rdi
  unsigned int *v11; // r14
  signed int v12; // ebx
  HANDLE v13; // r15
  signed int LastError; // eax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-68h] BYREF
  int v17; // [rsp+B0h] [rbp+8h] BYREF
  int v18; // [rsp+B4h] [rbp+Ch]

  v18 = HIDWORD(a1);
  v6 = g_wszTempFileName;
  v7 = a6;
  v17 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !g_wszTempFileName || !a2 || !a3 || !a4 || (v11 = a5) == 0 || !a6 )
  {
    v12 = -2147024809;
    goto LABEL_17;
  }
  *a6 = 0;
  v12 = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, _QWORD, __int64, int, int *))(*(_QWORD *)a2 + 280LL))(
          a2,
          0,
          0,
          1,
          30000,
          &v17);
  if ( v12 < 0 )
  {
LABEL_18:
    if ( *v7 == 1 )
    {
      ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
      *v7 = 0;
    }
    goto LABEL_20;
  }
  WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  SecurityAttributes.lpSecurityDescriptor = qword_180048AE8;
  *v7 = 1;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  v13 = CreateFileW(v6, 0xC0000000, 0, &SecurityAttributes, 4u, 0x8000080u, 0);
  if ( v13 == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockMasterResource);
    v12 = SaveEntireTree(a3, a4, 0, 0, g_wszSchemaFileName, &SecurityAttributes, v13);
    if ( v12 >= 0 )
    {
      v12 = 0;
      *v11 = g_ulHistoryMajorVersionNumber;
    }
    CloseHandle(v13);
    if ( v12 < 0 )
      DeleteFileW(v6);
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  }
  if ( v12 < 0 )
  {
LABEL_17:
    if ( !v7 )
      goto LABEL_20;
    goto LABEL_18;
  }
LABEL_20:
  if ( v17 )
    (*(void (__fastcall **)(struct IMDCOM *))(*(_QWORD *)a2 + 288LL))(a2);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180023be0  mov     r11, rsp
0x180023be3  mov     [r11+8], rcx
0x180023be7  push    rbx
0x180023be8  push    rbp
0x180023be9  push    rsi
0x180023bea  push    rdi
0x180023beb  push    r12
0x180023bed  push    r13
0x180023bef  push    r14
0x180023bf1  push    r15
0x180023bf3  sub     rsp, 68h
0x180023bf7  mov     rbp, cs:?g_wszTempFileName@@3PEAGEA; ushort * g_wszTempFileName
0x180023bfe  xor     eax, eax
0x180023c00  mov     rdi, [rsp+0A8h+arg_28]
0x180023c08  xorps   xmm0, xmm0
0x180023c0b  mov     dword ptr [r11+8], 0
0x180023c13  mov     r12, r9
0x180023c16  mov     r13, r8
0x180023c19  mov     rsi, rdx
0x180023c1c  lea     r15d, [rax+1]
0x180023c20  movups  xmmword ptr [rsp+0A8h+SecurityAttributes.nLength], xmm0
0x180023c25  mov     [r11-58h], rax
0x180023c29  test    rbp, rbp
0x180023c2c  jz      loc_180023DE5
0x180023c32  test    rdx, rdx
0x180023c35  jz      loc_180023DE5
0x180023c3b  test    r8, r8
0x180023c3e  jz      loc_180023DE5
0x180023c44  test    r9, r9
0x180023c47  jz      loc_180023DE5
0x180023c4d  mov     r14, [rsp+0A8h+arg_20]
0x180023c55  test    r14, r14
0x180023c58  jz      loc_180023DE5
0x180023c5e  test    rdi, rdi
0x180023c61  jz      loc_180023DE5
0x180023c67  mov     [rdi], eax
0x180023c69  lea     rcx, [r11+8]
0x180023c6d  mov     rax, [rdx]
0x180023c70  mov     r9d, r15d
0x180023c73  mov     [r11-80h], rcx
0x180023c77  xor     r8d, r8d
0x180023c7a  xor     edx, edx
0x180023c7c  mov     [rsp+0A8h+dwCreationDisposition], 7530h
0x180023c84  mov     rcx, rsi
0x180023c87  mov     rax, [rax+118h]
0x180023c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c93  mov     ebx, eax
0x180023c95  test    eax, eax
0x180023c97  js      loc_180023D97
0x180023c9d  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x180023ca4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023ca7  call    cs:__imp_WaitForSingleObject
0x180023cad  lea     rax, qword_180048AE8
0x180023cb4  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x180023cbd  mov     [rsp+0A8h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180023cc5  lea     r9, [rsp+0A8h+SecurityAttributes]; lpSecurityAttributes
0x180023cca  xor     r8d, r8d; dwShareMode
0x180023ccd  mov     [rsp+0A8h+SecurityAttributes.lpSecurityDescriptor], rax
0x180023cd2  mov     edx, 0C0000000h; dwDesiredAccess
0x180023cd7  mov     [rdi], r15d
0x180023cda  mov     rcx, rbp; lpFileName
0x180023cdd  mov     [rsp+0A8h+SecurityAttributes.nLength], 18h
0x180023ce5  mov     [rsp+0A8h+SecurityAttributes.bInheritHandle], 0
0x180023ced  mov     [rsp+0A8h+dwCreationDisposition], 4; dwCreationDisposition
0x180023cf5  call    cs:__imp_CreateFileW
0x180023cfb  mov     r15, rax
0x180023cfe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023d02  jnz     short loc_180023D1B
0x180023d04  call    cs:__imp_GetLastError
0x180023d0a  mov     ebx, eax
0x180023d0c  test    eax, eax
0x180023d0e  jle     short loc_180023D88
0x180023d10  movzx   ebx, ax
0x180023d13  or      ebx, 80070000h
0x180023d19  jmp     short loc_180023D88
0x180023d1b  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180023d22  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180023d28  lea     rax, [rsp+0A8h+SecurityAttributes]
0x180023d2d  mov     [rsp+0A8h+hTemplateFile], r15; void *
0x180023d32  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], rax; struct _SECURITY_ATTRIBUTES *
0x180023d37  xor     r9d, r9d; unsigned __int16 *
0x180023d3a  mov     rax, cs:?g_wszSchemaFileName@@3PEAGEA; ushort * g_wszSchemaFileName
0x180023d41  xor     r8d, r8d; unsigned int
0x180023d44  mov     rdx, r12; struct _IIS_CRYPTO_BLOB *
0x180023d47  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rax; unsigned __int16 *
0x180023d4c  mov     rcx, r13; struct IIS_CRYPTO_STORAGE *
0x180023d4f  call    ?SaveEntireTree@@YAJPEAVIIS_CRYPTO_STORAGE@@PEFAU_IIS_CRYPTO_BLOB@@KPEAG2PEAU_SECURITY_ATTRIBUTES@@PEAX@Z; SaveEntireTree(IIS_CRYPTO_STORAGE *,_IIS_CRYPTO_BLOB *,ulong,ushort *,ushort *,_SECURITY_ATTRIBUTES *,void *)
0x180023d54  mov     ebx, eax
0x180023d56  test    eax, eax
0x180023d58  js      short loc_180023D65
0x180023d5a  mov     eax, cs:?g_ulHistoryMajorVersionNumber@@3KA; ulong g_ulHistoryMajorVersionNumber
0x180023d60  xor     ebx, ebx
0x180023d62  mov     [r14], eax
0x180023d65  mov     rcx, r15; hObject
0x180023d68  call    cs:__imp_CloseHandle
0x180023d6e  test    ebx, ebx
0x180023d70  jns     short loc_180023D7B
0x180023d72  mov     rcx, rbp; lpFileName
0x180023d75  call    cs:__imp_DeleteFileW
0x180023d7b  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180023d82  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180023d88  test    ebx, ebx
0x180023d8a  jns     short loc_180023DB5
0x180023d8c  mov     r15d, 1
0x180023d92  test    rdi, rdi
0x180023d95  jz      short loc_180023DB5
0x180023d97  cmp     [rdi], r15d
0x180023d9a  jnz     short loc_180023DB5
0x180023d9c  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x180023da3  xor     r8d, r8d; lpPreviousCount
0x180023da6  mov     edx, r15d; lReleaseCount
0x180023da9  call    cs:__imp_ReleaseSemaphore
0x180023daf  mov     dword ptr [rdi], 0
0x180023db5  mov     edx, [rsp+0A8h+arg_0]
0x180023dbc  test    edx, edx
0x180023dbe  jz      short loc_180023DD2
0x180023dc0  mov     rax, [rsi]
0x180023dc3  mov     rcx, rsi
0x180023dc6  mov     rax, [rax+120h]
0x180023dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dd2  mov     eax, ebx
0x180023dd4  add     rsp, 68h
0x180023dd8  pop     r15
0x180023dda  pop     r14
0x180023ddc  pop     r13
0x180023dde  pop     r12
0x180023de0  pop     rdi
0x180023de1  pop     rsi
0x180023de2  pop     rbp
0x180023de3  pop     rbx
0x180023de4  retn
0x180023de5  mov     ebx, 80070057h
0x180023dea  jmp     short loc_180023D92
```
