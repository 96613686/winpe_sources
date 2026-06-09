# HTTP_COMPRESSION::CompressAndWriteData(COMPRESSION_SCHEME *,void *,uchar const *,ulong,__int64 *,void *)

- ea: `0x180002670`
- end: `0x1800027e2`
- name: `?CompressAndWriteData@HTTP_COMPRESSION@@CAJPEAVCOMPRESSION_SCHEME@@PEAXPEBEKPEA_J1@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct COMPRESSION_SCHEME *, void *, const unsigned __int8 *, unsigned int, __int64 *, HANDLE hFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002090`

## callees

- `0x180002670`
- `0x180005f90`
- `0x180006020`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027a4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002779`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002779`

## pseudocode

```c
signed int __fastcall HTTP_COMPRESSION::CompressAndWriteData(
        struct COMPRESSION_SCHEME *a1,
        void *a2,
        const unsigned __int8 *a3,
        unsigned int a4,
        __int64 *a5,
        HANDLE hFile)
{
  int v7; // r13d
  unsigned int v8; // edi
  __int64 (__fastcall *v11)(void *, const unsigned __int8 *, _QWORD, _BYTE *, int, unsigned int *, DWORD *, int, int); // rax
  int v12; // ecx
  signed int result; // eax
  signed int v14; // ebx
  DWORD nNumberOfBytesToWrite; // [rsp+50h] [rbp-1068h] BYREF
  unsigned int v16; // [rsp+54h] [rbp-1064h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp-1060h] BYREF
  _BYTE Buffer[4096]; // [rsp+60h] [rbp-1058h] BYREF

  NumberOfBytesWritten = 0;
  v7 = 0;
  if ( !a4 )
    v7 = 2;
  v8 = a4;
  while ( 1 )
  {
    v11 = (__int64 (__fastcall *)(void *, const unsigned __int8 *, _QWORD, _BYTE *, int, unsigned int *, DWORD *, int, int))*((_QWORD *)a1 + 26);
    v16 = 0;
    nNumberOfBytesToWrite = 0;
    v12 = *((_DWORD *)a1 + 57);
    result = v11
           ? v11(a2, a3, v8, Buffer, 4096, &v16, &nNumberOfBytesToWrite, v12, v7)
           : (*((unsigned __int64 (__fastcall **)(void *, const unsigned __int8 *, _QWORD, _BYTE *, int, unsigned int *, DWORD *, int))a1
              + 25))(
               a2,
               a3,
               v8,
               Buffer,
               4096,
               &v16,
               &nNumberOfBytesToWrite,
               v12);
    v14 = result;
    if ( result < 0 )
      break;
    if ( nNumberOfBytesToWrite )
    {
      if ( !WriteFile(hFile, Buffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
        return result;
      }
      *a5 += NumberOfBytesWritten;
    }
    v8 -= v16;
    if ( !v8 && v16 || v14 )
      return 0;
    a3 += v16;
  }
  return result;
}

```

## disassembly

```asm
0x180002670  push    rbx
0x180002672  push    rbp
0x180002673  push    rsi
0x180002674  push    rdi
0x180002675  push    r12
0x180002677  push    r13
0x180002679  push    r14
0x18000267b  push    r15
0x18000267d  mov     eax, 1078h
0x180002682  call    _alloca_probe
0x180002687  sub     rsp, rax
0x18000268a  mov     rax, cs:__security_cookie
0x180002691  xor     rax, rsp
0x180002694  mov     [rsp+10B8h+var_58], rax
0x18000269c  mov     r14, [rsp+10B8h+arg_20]
0x1800026a4  mov     rbp, rcx
0x1800026a7  mov     r12, [rsp+10B8h+hFile]
0x1800026af  xor     ecx, ecx
0x1800026b1  test    r9d, r9d
0x1800026b4  mov     [rsp+10B8h+NumberOfBytesWritten], ecx
0x1800026b8  mov     r13d, ecx
0x1800026bb  mov     eax, 2
0x1800026c0  cmovz   r13d, eax
0x1800026c4  mov     edi, r9d
0x1800026c7  mov     rsi, r8
0x1800026ca  mov     r15, rdx
0x1800026cd  nop     dword ptr [rax]
0x1800026d0  mov     rax, [rbp+0D0h]
0x1800026d7  lea     r9, [rsp+10B8h+Buffer]
0x1800026dc  mov     [rsp+10B8h+var_1064], ecx
0x1800026e0  mov     r8d, edi
0x1800026e3  mov     [rsp+10B8h+nNumberOfBytesToWrite], ecx
0x1800026e7  mov     rdx, rsi
0x1800026ea  mov     ecx, [rbp+0E4h]
0x1800026f0  test    rax, rax
0x1800026f3  jz      short loc_180002724
0x1800026f5  mov     [rsp+10B8h+var_1078], r13d
0x1800026fa  mov     [rsp+10B8h+var_1080], ecx
0x1800026fe  lea     rcx, [rsp+10B8h+nNumberOfBytesToWrite]
0x180002703  mov     [rsp+10B8h+var_1088], rcx
0x180002708  lea     rcx, [rsp+10B8h+var_1064]
0x18000270d  mov     [rsp+10B8h+var_1090], rcx
0x180002712  mov     rcx, r15
0x180002715  mov     dword ptr [rsp+10B8h+lpOverlapped], 1000h
0x18000271d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002722  jmp     short loc_180002753
0x180002724  mov     [rsp+10B8h+var_1080], ecx
0x180002728  lea     rax, [rsp+10B8h+nNumberOfBytesToWrite]
0x18000272d  mov     [rsp+10B8h+var_1088], rax
0x180002732  mov     rcx, r15
0x180002735  lea     rax, [rsp+10B8h+var_1064]
0x18000273a  mov     [rsp+10B8h+var_1090], rax
0x18000273f  mov     rax, [rbp+0C8h]
0x180002746  mov     dword ptr [rsp+10B8h+lpOverlapped], 1000h
0x18000274e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002753  mov     ebx, eax
0x180002755  test    eax, eax
0x180002757  js      short loc_1800027BC
0x180002759  mov     r8d, [rsp+10B8h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18000275e  test    r8d, r8d
0x180002761  jz      short loc_18000278A
0x180002763  lea     r9, [rsp+10B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002768  mov     [rsp+10B8h+lpOverlapped], 0; lpOverlapped
0x180002771  lea     rdx, [rsp+10B8h+Buffer]; lpBuffer
0x180002776  mov     rcx, r12; hFile
0x180002779  call    cs:__imp_WriteFile
0x18000277f  test    eax, eax
0x180002781  jz      short loc_1800027A4
0x180002783  mov     eax, [rsp+10B8h+NumberOfBytesWritten]
0x180002787  add     [r14], rax
0x18000278a  mov     eax, [rsp+10B8h+var_1064]
0x18000278e  sub     edi, eax
0x180002790  jnz     short loc_180002796
0x180002792  test    eax, eax
0x180002794  jnz     short loc_1800027B8
0x180002796  test    ebx, ebx
0x180002798  jnz     short loc_1800027B8
0x18000279a  add     rsi, rax
0x18000279d  xor     ecx, ecx
0x18000279f  jmp     loc_1800026D0
0x1800027a4  call    cs:__imp_GetLastError
0x1800027aa  test    eax, eax
0x1800027ac  jle     short loc_1800027BE
0x1800027ae  movzx   eax, ax
0x1800027b1  or      eax, 80070000h
0x1800027b6  jmp     short loc_1800027BE
0x1800027b8  xor     eax, eax
0x1800027ba  jmp     short loc_1800027BE
0x1800027bc  mov     eax, ebx
0x1800027be  mov     rcx, [rsp+10B8h+var_58]
0x1800027c6  xor     rcx, rsp; StackCookie
0x1800027c9  call    __security_check_cookie
0x1800027ce  add     rsp, 1078h
0x1800027d5  pop     r15
0x1800027d7  pop     r14
0x1800027d9  pop     r13
0x1800027db  pop     r12
0x1800027dd  pop     rdi
0x1800027de  pop     rsi
0x1800027df  pop     rbp
0x1800027e0  pop     rbx
0x1800027e1  retn
```
