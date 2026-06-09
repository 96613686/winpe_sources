# CKeyInSeq::LoadSrmpStream(void *)

- ea: `0x18006787c`
- end: `0x180067983`
- name: `?LoadSrmpStream@CKeyInSeq@@AEAAHPEAX@Z`
- size: `263`
- prototype: `int(CKeyInSeq *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006753c`

## callees

- `0x18000f430`
- `0x18000faec`
- `0x18006787c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18006795c`
- `msvcrt!free` at `0x18006796d`
- `msvcrt!free` at `0x18006795c`
- `msvcrt!free` at `0x18006796d`
- `KERNEL32!ReadFile` at `0x1800678b9`
- `KERNEL32!ReadFile` at `0x1800678ff`
- `KERNEL32!ReadFile` at `0x1800678b9`
- `KERNEL32!ReadFile` at `0x1800678ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CKeyInSeq::LoadSrmpStream(CKeyInSeq *this, void *a2)
{
  _DWORD *v4; // rbx
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  _DWORD *v8; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+30h] BYREF
  DWORD Buffer; // [rsp+78h] [rbp+38h] BYREF

  NumberOfBytesRead = 0;
  Buffer = 0;
  if ( !ReadFile(a2, &Buffer, 4u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 4 )
    return 0;
  v4 = MmAllocate(Buffer);
  v8 = v4;
  if ( !ReadFile(a2, v4, Buffer, &NumberOfBytesRead, 0) || Buffer != NumberOfBytesRead )
  {
    free(v4);
    return 0;
  }
  v5 = MmAllocate(0x18u);
  v6 = v5;
  v8 = v5;
  if ( v5 )
  {
    v5[2] = 1;
    *(_QWORD *)v5 = &CQueueSecurityDescriptor::`vftable';
    *((_QWORD *)v5 + 2) = v4;
  }
  else
  {
    v6 = 0;
  }
  v8 = v6;
  R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=((char *)this + 48, &v8);
  SafeRelease<CSockTransport>(v6);
  free(0);
  return 1;
}

```

## disassembly

```asm
0x18006787c  mov     [rsp-18h+arg_0], rbx
0x180067881  push    rbp
0x180067882  push    rsi
0x180067883  push    rdi
0x180067884  mov     rbp, rsp
0x180067887  sub     rsp, 40h
0x18006788b  mov     rdi, rdx
0x18006788e  mov     rsi, rcx
0x180067891  mov     [rbp+NumberOfBytesRead], 0
0x180067898  mov     [rbp+Buffer], 0
0x18006789f  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x1800678a8  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800678ac  mov     r8d, 4; nNumberOfBytesToRead
0x1800678b2  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800678b6  mov     rcx, rdi; hFile
0x1800678b9  call    cs:__imp_ReadFile
0x1800678bf  test    eax, eax
0x1800678c1  jz      loc_180067974
0x1800678c7  cmp     [rbp+NumberOfBytesRead], 4
0x1800678cb  jnz     loc_180067974
0x1800678d1  mov     [rbp+var_10], 0
0x1800678d9  mov     ecx, [rbp+Buffer]; unsigned __int64
0x1800678dc  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800678e1  mov     rbx, rax
0x1800678e4  mov     [rbp+var_10], rax
0x1800678e8  mov     [rsp+40h+lpOverlapped], 0; lpOverlapped
0x1800678f1  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800678f5  mov     r8d, [rbp+Buffer]; nNumberOfBytesToRead
0x1800678f9  mov     rdx, rax; lpBuffer
0x1800678fc  mov     rcx, rdi; hFile
0x1800678ff  call    cs:__imp_ReadFile
0x180067905  test    eax, eax
0x180067907  jz      short loc_18006796A
0x180067909  mov     eax, [rbp+NumberOfBytesRead]
0x18006790c  cmp     [rbp+Buffer], eax
0x18006790f  jnz     short loc_18006796A
0x180067911  mov     ecx, 18h; unsigned __int64
0x180067916  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18006791b  mov     rdi, rax
0x18006791e  mov     [rbp+var_10], rax
0x180067922  test    rax, rax
0x180067925  jz      short loc_18006793E
0x180067927  mov     dword ptr [rax+8], 1
0x18006792e  lea     rax, ??_7CQueueSecurityDescriptor@@6B@; const CQueueSecurityDescriptor::`vftable'
0x180067935  mov     [rdi], rax
0x180067938  mov     [rdi+10h], rbx
0x18006793c  jmp     short loc_180067940
0x18006793e  xor     edi, edi
0x180067940  mov     [rbp+var_10], rdi
0x180067944  lea     rcx, [rsi+30h]
0x180067948  lea     rdx, [rbp+var_10]
0x18006794c  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x180067951  mov     rcx, rdi
0x180067954  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180067959  nop
0x18006795a  xor     ecx, ecx; Block
0x18006795c  call    cs:__imp_free
0x180067962  nop
0x180067963  mov     eax, 1
0x180067968  jmp     short loc_180067976
0x18006796a  mov     rcx, rbx; Block
0x18006796d  call    cs:__imp_free
0x180067973  nop
0x180067974  xor     eax, eax
0x180067976  mov     rbx, [rsp+40h+arg_0]
0x18006797b  add     rsp, 40h
0x18006797f  pop     rdi
0x180067980  pop     rsi
0x180067981  pop     rbp
0x180067982  retn
```
