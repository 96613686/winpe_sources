# CNtfsStream::Rename(ushort const *,int)

- ea: `0x1800583b0`
- end: `0x180058542`
- name: `?Rename@CNtfsStream@@AEAAJPEBGH@Z`
- size: `402`
- prototype: `int(CNtfsStream *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054720`
- `0x18005a150`

## callees

- `0x18001e2f0`
- `0x180033b54`
- `0x1800341f4`
- `0x180042800`
- `0x1800583b0`
- `0x1800613b0`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x1800584f2`
- `api-ms-win-crt-private-l1-1-0!_o__resetstkoflw` at `0x1800584f2`
- `ntdll!NtSetInformationFile` at `0x180058491`
- `ntdll!NtSetInformationFile` at `0x180058491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800584c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800584c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800584ac`

## pseudocode

```c
__int64 __fastcall CNtfsStream::Rename(CNtfsStream *this, const unsigned __int16 *a2, char a3)
{
  __int64 v6; // rdi
  signed int v7; // r15d
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  NTSTATUS v12; // eax
  int v13; // ebx
  SIZE_T v14; // rbx
  unsigned __int16 *v15; // rax
  _QWORD FileInformation[2]; // [rsp+30h] [rbp+0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp+10h] BYREF
  __int64 v19; // [rsp+50h] [rbp+20h] BYREF
  _BYTE Src[520]; // [rsp+58h] [rbp+28h] BYREF

  IoStatusBlock = 0;
  CNtfsStreamName::CNtfsStreamName((CNtfsStreamName *)&v19, a2);
  FileInformation[0] = (char *)this + 104;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), 0xFFFFFFFFLL);
  v6 = -1;
  if ( *((_QWORD *)this + 12) == -1 )
  {
    v13 = -2147286782;
  }
  else
  {
    v7 = 2 * v19 + 22;
    v8 = v7 + 15LL;
    if ( v8 <= v7 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    LOBYTE(FileInformation[0]) = a3;
    FileInformation[1] = 0;
    IoStatusBlock.Status = 2 * v19;
    memcpy_0((char *)&IoStatusBlock.Pointer + 4, Src, (unsigned int)(2 * v19));
    v12 = NtSetInformationFile(*((HANDLE *)this + 12), &IoStatusBlock, FileInformation, v7, FileRenameInformation);
    if ( v12 >= 0 || (v13 = NtStatusToScode(v12), v13 >= 0) )
    {
      CoTaskMemFree(*((LPVOID *)this + 2));
      do
        ++v6;
      while ( a2[v6] );
      v14 = 2 * (int)v6 + 2;
      v15 = (unsigned __int16 *)CoTaskMemAlloc(v14);
      *((_QWORD *)this + 2) = v15;
      if ( v15 )
      {
        StringCbCopyW(v15, v14, a2);
        v13 = 0;
      }
      else
      {
        v13 = -2147287032;
      }
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 32LL))(*((_QWORD *)this + 13));
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800583b0  push    rbp
0x1800583b2  push    rsi
0x1800583b3  push    rdi
0x1800583b4  push    r12
0x1800583b6  push    r13
0x1800583b8  push    r14
0x1800583ba  push    r15
0x1800583bc  sub     rsp, 270h
0x1800583c3  lea     rbp, [rsp+30h]
0x1800583c8  mov     [rbp+270h+arg_10], rbx
0x1800583cf  mov     rax, cs:__security_cookie
0x1800583d6  xor     rax, rbp
0x1800583d9  mov     [rbp+270h+var_40], rax
0x1800583e0  mov     r13d, r8d
0x1800583e3  mov     r12, rdx
0x1800583e6  mov     r14, rcx
0x1800583e9  xorps   xmm0, xmm0
0x1800583ec  movups  xmmword ptr [rbp+270h+IoStatusBlock], xmm0
0x1800583f0  lea     rcx, [rbp+270h+var_250]; this
0x1800583f4  call    ??0CNtfsStreamName@@QEAA@PEBG@Z; CNtfsStreamName::CNtfsStreamName(ushort const *)
0x1800583f9  lea     rsi, [r14+68h]
0x1800583fd  mov     [rbp+270h+FileInformation], rsi
0x180058401  mov     rcx, [rsi]
0x180058404  mov     rax, [rcx]
0x180058407  or      edx, 0FFFFFFFFh
0x18005840a  mov     rax, [rax+18h]
0x18005840e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058413  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180058417  cmp     [r14+60h], rdi
0x18005841b  jz      loc_180058503
0x180058421  mov     rdx, [rbp+270h+var_250]
0x180058425  lea     r15d, ds:16h[rdx*2]
0x18005842d  movsxd  rax, r15d
0x180058430  lea     rcx, [rax+0Fh]
0x180058434  cmp     rcx, rax
0x180058437  ja      short loc_180058443
0x180058439  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180058443  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180058447  mov     rax, rcx
0x18005844a  call    _alloca_probe
0x18005844f  sub     rsp, rcx
0x180058452  lea     rbx, [rsp+2A0h+FileInformation]
0x180058457  mov     [rbp+270h+var_268], rbx
0x18005845b  mov     [rbx], r13b
0x18005845e  xor     r13d, r13d
0x180058461  mov     [rbx+8], r13
0x180058465  lea     eax, [rdx+rdx]
0x180058468  mov     [rbx+10h], eax
0x18005846b  mov     r8d, eax; Size
0x18005846e  lea     rcx, [rbx+14h]; void *
0x180058472  lea     rdx, [rbp+270h+Src]; Src
0x180058476  call    memcpy_0
0x18005847b  mov     [rsp+2A0h+FileInformationClass], 0Ah; FileInformationClass
0x180058483  mov     r9d, r15d; Length
0x180058486  mov     r8, rbx; FileInformation
0x180058489  lea     rdx, [rbp+270h+IoStatusBlock]; IoStatusBlock
0x18005848d  mov     rcx, [r14+60h]; FileHandle
0x180058491  call    cs:__imp_NtSetInformationFile
0x180058497  test    eax, eax
0x180058499  jns     short loc_1800584A8
0x18005849b  mov     ecx, eax; int
0x18005849d  call    ?NtStatusToScode@@YAJJ@Z; NtStatusToScode(long)
0x1800584a2  mov     ebx, eax
0x1800584a4  test    eax, eax
0x1800584a6  js      short loc_180058508
0x1800584a8  mov     rcx, [r14+10h]; pv
0x1800584ac  call    cs:__imp_CoTaskMemFree
0x1800584b2  inc     rdi
0x1800584b5  cmp     [r12+rdi*2], r13w
0x1800584ba  jnz     short loc_1800584B2
0x1800584bc  lea     eax, ds:2[rdi*2]
0x1800584c3  movsxd  rbx, eax
0x1800584c6  mov     rcx, rbx; cb
0x1800584c9  call    cs:__imp_CoTaskMemAlloc
0x1800584cf  mov     [r14+10h], rax
0x1800584d3  test    rax, rax
0x1800584d6  jnz     short loc_1800584DF
0x1800584d8  mov     ebx, 80030008h
0x1800584dd  jmp     short loc_180058508
0x1800584df  mov     r8, r12; unsigned __int16 *
0x1800584e2  mov     rdx, rbx; unsigned __int64
0x1800584e5  mov     rcx, rax; unsigned __int16 *
0x1800584e8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800584ed  mov     ebx, r13d
0x1800584f0  jmp     short loc_180058508
0x1800584f2  call    cs:__imp__o__resetstkoflw
0x1800584f8  mov     ebx, 80030008h
0x1800584fd  mov     rsi, [rbp+270h+FileInformation]
0x180058501  jmp     short loc_180058508
0x180058503  mov     ebx, 80030102h
0x180058508  mov     rcx, [rsi]
0x18005850b  mov     rax, [rcx]
0x18005850e  mov     rax, [rax+20h]
0x180058512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058517  mov     eax, ebx
0x180058519  mov     rcx, [rbp+270h+var_40]
0x180058520  xor     rcx, rbp; StackCookie
0x180058523  call    __security_check_cookie
0x180058528  mov     rbx, [rbp+270h+arg_10]
0x18005852f  lea     rsp, [rbp+240h]
0x180058536  pop     r15
0x180058538  pop     r14
0x18005853a  pop     r13
0x18005853c  pop     r12
0x18005853e  pop     rdi
0x18005853f  pop     rsi
0x180058540  pop     rbp
0x180058541  retn
```
