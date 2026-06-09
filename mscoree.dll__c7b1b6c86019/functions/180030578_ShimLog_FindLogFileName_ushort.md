# ShimLog::FindLogFileName(ushort *)

- ea: `0x180030578`
- end: `0x180030750`
- name: `?FindLogFileName@ShimLog@@AEAAHPEAG@Z`
- size: `472`
- prototype: `int(ShimLog *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180030798`

## callees

- `0x180003070`
- `0x180003740`
- `0x18000c1a8`
- `0x18000d614`
- `0x18000da9c`
- `0x18002a7c8`
- `0x180030578`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180030608`
- `KERNEL32!GetFullPathNameW` at `0x180030608`
- `KERNEL32!GetModuleFileNameW` at `0x1800305b7`
- `KERNEL32!GetModuleFileNameW` at `0x1800305b7`
- `KERNEL32!GetFileAttributesW` at `0x1800306ea`
- `KERNEL32!GetFileAttributesW` at `0x1800306ea`

## pseudocode

```c
__int64 __fastcall ShimLog::FindLogFileName(ShimLog *this, unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  size_t v8; // rsi
  unsigned __int128 v9; // rax
  unsigned __int64 v10; // kr00_8
  wchar_t *v11; // rdi
  int i; // ebx
  __int64 v14; // [rsp+20h] [rbp-E0h]
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+38h] [rbp-C8h]
  wchar_t Filename[272]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[272]; // [rsp+260h] [rbp+160h] BYREF

  if ( !GetModuleFileNameW(0, Filename, 0x10Cu) )
    return 0;
  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    if ( v4 )
    {
      FilePart = 0;
      if ( GetFullPathNameW(Filename, 0x10Du, Buffer, &FilePart) - 1 > 0x10C )
        return 0;
      v5 = -1;
      do
        ++v5;
      while ( FilePart[v5] );
      v6 = -1;
      do
        ++v6;
      while ( a2[v6] );
      if ( (unsigned __int64)(v6 + v5 + 2) > 0x10D )
        return 0;
      wcscpy_s(Filename, 0x10Du, a2);
      wcscat_s(Filename, 0x10Du, L"\\");
      wcscat_s(Filename, 0x10Du, FilePart);
    }
  }
  v7 = -1;
  do
    ++v7;
  while ( Filename[v7] );
  v8 = v7 + 14;
  v10 = v7 + 14;
  v9 = (unsigned __int64)(v7 + 14) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v10, 2u) )
    *(_QWORD *)&v9 = -1;
  FilePart = (LPWSTR)operator new(v9, *((const struct NoThrow **)&v9 + 1));
  v11 = FilePart;
  v16 = 0;
  if ( FilePart )
  {
    v16 = 1;
    for ( i = 0; i < 10; ++i )
    {
      LODWORD(v14) = i;
      swprintf_s(v11, v8, L"%s.CLRLoad%d.log", Filename, v14);
      if ( GetFileAttributesW(v11) == -1 && (unsigned int)HRESULT_FROM_GetLastError() == -2147024894 )
      {
        *(_QWORD *)this = v11;
        v16 = 0;
        Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&FilePart);
        return 1;
      }
    }
  }
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&FilePart);
  return 0;
}

```

## disassembly

```asm
0x180030578  mov     [rsp-8+arg_10], rbx
0x18003057d  push    rbp
0x18003057e  push    rsi
0x18003057f  push    rdi
0x180030580  push    r14
0x180030582  push    r15
0x180030584  lea     rbp, [rsp-390h]
0x18003058c  sub     rsp, 490h
0x180030593  mov     rax, cs:__security_cookie
0x18003059a  xor     rax, rsp
0x18003059d  mov     [rbp+3B0h+var_30], rax
0x1800305a4  mov     rbx, rdx
0x1800305a7  mov     r14, rcx
0x1800305aa  lea     rdx, [rsp+4B0h+Filename]; lpFilename
0x1800305af  xor     ecx, ecx; hModule
0x1800305b1  mov     r8d, 10Ch; nSize
0x1800305b7  call    cs:__imp_GetModuleFileNameW
0x1800305bd  xor     r15d, r15d
0x1800305c0  test    eax, eax
0x1800305c2  jz      loc_180030728
0x1800305c8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800305cc  test    rbx, rbx
0x1800305cf  jz      loc_180030680
0x1800305d5  mov     rax, rdi
0x1800305d8  inc     rax
0x1800305db  cmp     [rbx+rax*2], r15w
0x1800305e0  jnz     short loc_1800305D8
0x1800305e2  test    rax, rax
0x1800305e5  jz      loc_180030680
0x1800305eb  mov     esi, 10Dh
0x1800305f0  mov     [rsp+4B0h+FilePart], r15
0x1800305f5  mov     edx, esi; nBufferLength
0x1800305f7  lea     r9, [rsp+4B0h+FilePart]; lpFilePart
0x1800305fc  lea     r8, [rbp+3B0h+Buffer]; lpBuffer
0x180030603  lea     rcx, [rsp+4B0h+Filename]; lpFileName
0x180030608  call    cs:__imp_GetFullPathNameW
0x18003060e  dec     eax
0x180030610  cmp     eax, 10Ch
0x180030615  ja      loc_180030728
0x18003061b  mov     rcx, [rsp+4B0h+FilePart]
0x180030620  mov     rax, rdi
0x180030623  inc     rax
0x180030626  cmp     [rcx+rax*2], r15w
0x18003062b  jnz     short loc_180030623
0x18003062d  mov     rcx, rdi
0x180030630  inc     rcx
0x180030633  cmp     [rbx+rcx*2], r15w
0x180030638  jnz     short loc_180030630
0x18003063a  add     rax, 2
0x18003063e  add     rax, rcx
0x180030641  cmp     rax, rsi
0x180030644  ja      loc_180030728
0x18003064a  mov     r8, rbx; Source
0x18003064d  lea     rcx, [rsp+4B0h+Filename]; Destination
0x180030652  mov     rdx, rsi; SizeInWords
0x180030655  call    wcscpy_s
0x18003065a  lea     r8, asc_18004C8C0; "\\"
0x180030661  mov     rdx, rsi; SizeInWords
0x180030664  lea     rcx, [rsp+4B0h+Filename]; Destination
0x180030669  call    wcscat_s
0x18003066e  mov     r8, [rsp+4B0h+FilePart]; Source
0x180030673  lea     rcx, [rsp+4B0h+Filename]; Destination
0x180030678  mov     rdx, rsi; SizeInWords
0x18003067b  call    wcscat_s
0x180030680  lea     rcx, [rsp+4B0h+Filename]
0x180030685  mov     rax, rdi
0x180030688  inc     rax
0x18003068b  cmp     [rcx+rax*2], r15w
0x180030690  jnz     short loc_180030688
0x180030692  lea     rsi, [rax+0Eh]
0x180030696  mov     eax, 2
0x18003069b  mul     rsi
0x18003069e  cmovb   rax, rdi
0x1800306a2  mov     rcx, rax; unsigned __int64
0x1800306a5  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800306aa  mov     [rsp+4B0h+FilePart], rax
0x1800306af  mov     rdi, rax
0x1800306b2  mov     [rsp+4B0h+var_478], r15d
0x1800306b7  test    rax, rax
0x1800306ba  jz      short loc_18003071E
0x1800306bc  mov     [rsp+4B0h+var_478], 1
0x1800306c4  mov     ebx, r15d
0x1800306c7  cmp     ebx, 0Ah
0x1800306ca  jge     short loc_18003071E
0x1800306cc  lea     r9, [rsp+4B0h+Filename]
0x1800306d1  mov     [rsp+4B0h+var_490], ebx
0x1800306d5  lea     r8, aSClrloadDLog; "%s.CLRLoad%d.log"
0x1800306dc  mov     rdx, rsi; BufferCount
0x1800306df  mov     rcx, rdi; Buffer
0x1800306e2  call    swprintf_s
0x1800306e7  mov     rcx, rdi; lpFileName
0x1800306ea  call    cs:__imp_GetFileAttributesW
0x1800306f0  cmp     eax, 0FFFFFFFFh
0x1800306f3  jnz     short loc_180030701
0x1800306f5  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x1800306fa  cmp     eax, 80070002h
0x1800306ff  jz      short loc_180030705
0x180030701  inc     ebx
0x180030703  jmp     short loc_1800306C7
0x180030705  lea     rcx, [rsp+4B0h+FilePart]
0x18003070a  mov     [r14], rdi
0x18003070d  mov     [rsp+4B0h+var_478], r15d
0x180030712  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180030717  mov     eax, 1
0x18003071c  jmp     short loc_18003072A
0x18003071e  lea     rcx, [rsp+4B0h+FilePart]
0x180030723  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180030728  xor     eax, eax
0x18003072a  mov     rcx, [rbp+3B0h+var_30]
0x180030731  xor     rcx, rsp; StackCookie
0x180030734  call    __security_check_cookie
0x180030739  mov     rbx, [rsp+4B0h+arg_10]
0x180030741  add     rsp, 490h
0x180030748  pop     r15
0x18003074a  pop     r14
0x18003074c  pop     rdi
0x18003074d  pop     rsi
0x18003074e  pop     rbp
0x18003074f  retn
```
