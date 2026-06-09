# common_ftell_translated_utf8_nolock(__crt_stdio_stream,__int64,__crt_cached_ptd_host &)

- ea: `0x140140910`
- end: `0x140140a96`
- name: `?common_ftell_translated_utf8_nolock@@YA_JV__crt_stdio_stream@@_JAEAV__crt_cached_ptd_host@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140140bf4`

## callees

- `0x14012fc30`
- `0x14012fc90`
- `0x140140434`
- `0x140140910`
- `0x140142604`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1401409df`
- `KERNEL32!ReadFile` at `0x1401409df`

## pseudocode

```c
__int64 __fastcall common_ftell_translated_utf8_nolock(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // eax
  __int64 v7; // rdi
  unsigned int v8; // r14d
  __int64 v10; // kr00_8
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int64 v13; // r13
  __int64 v14; // rcx
  unsigned __int8 *v15; // rdx
  unsigned __int8 *v16; // rcx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-1058h] BYREF
  _BYTE Buffer[4096]; // [rsp+40h] [rbp-1048h] BYREF

  v6 = fileno((FILE *)a1);
  v7 = 0;
  v8 = v6;
  if ( !*(_DWORD *)(a1 + 16) )
    return a2;
  v10 = *(_QWORD *)a1 - *(_QWORD *)(a1 + 8);
  v11 = (__int64)v6 >> 6;
  v12 = v10 / 2;
  v13 = common_lseek<__int64>((unsigned int)v6, *(_QWORD *)(qword_14038C5D0[v11] + 72LL * (v6 & 0x3F) + 48), 0, a3);
  v14 = qword_14038C5D0[v11];
  if ( v13 != *(_QWORD *)(v14 + 72LL * (v8 & 0x3F) + 48) )
    return -1;
  NumberOfBytesRead = 0;
  if ( !ReadFile(*(HANDLE *)(v14 + 72LL * (v8 & 0x3F) + 40), Buffer, 0x1000u, &NumberOfBytesRead, 0)
    || common_lseek<__int64>(v8, a2, 0, a3) < 0
    || v12 > NumberOfBytesRead )
  {
    return -1;
  }
  v15 = &Buffer[NumberOfBytesRead];
  v16 = Buffer;
  if ( v12 )
  {
    do
    {
      if ( v16 >= v15 )
        break;
      if ( *v16 == 13 )
      {
        if ( v16 < v15 - 1 && v16[1] == 10 )
          ++v16;
      }
      else
      {
        v16 += *((char *)qword_14037A370 + *v16);
      }
      ++v7;
      ++v16;
    }
    while ( v7 != v12 );
  }
  return v16 - Buffer + v13;
}

```

## disassembly

```asm
0x140140910  mov     [rsp+arg_0], rbx
0x140140915  push    rbp
0x140140916  push    rsi
0x140140917  push    rdi
0x140140918  push    r12
0x14014091a  push    r13
0x14014091c  push    r14
0x14014091e  push    r15
0x140140920  mov     eax, 1050h
0x140140925  call    __alloca_probe
0x14014092a  sub     rsp, rax
0x14014092d  mov     rax, cs:__security_cookie
0x140140934  xor     rax, rsp
0x140140937  mov     [rsp+1088h+var_48], rax
0x14014093f  mov     r15, r8
0x140140942  mov     rbp, rdx
0x140140945  mov     rbx, rcx
0x140140948  call    _fileno
0x14014094d  xor     edi, edi
0x14014094f  movsxd  r14, eax
0x140140952  cmp     [rbx+10h], edi
0x140140955  jnz     short loc_14014095F
0x140140957  mov     rax, rbp
0x14014095a  jmp     loc_140140A6B
0x14014095f  mov     rax, [rbx]
0x140140962  mov     rcx, r14
0x140140965  sub     rax, [rbx+8]
0x140140969  and     ecx, 3Fh
0x14014096c  cqo
0x14014096e  mov     rbx, r14
0x140140971  sub     rax, rdx
0x140140974  sar     rbx, 6
0x140140978  sar     rax, 1
0x14014097b  mov     r9, r15
0x14014097e  lea     r12, [rcx+rcx*8]
0x140140982  mov     rsi, rax
0x140140985  lea     rax, __ImageBase
0x14014098c  xor     r8d, r8d
0x14014098f  mov     rdx, rva qword_14038C5D0[rax+rbx*8]
0x140140997  mov     ecx, r14d
0x14014099a  mov     rdx, [rdx+r12*8+30h]
0x14014099f  call    j_??$common_lseek@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z
0x1401409a4  mov     r13, rax
0x1401409a7  lea     rax, __ImageBase
0x1401409ae  mov     rcx, rva qword_14038C5D0[rax+rbx*8]
0x1401409b6  cmp     r13, [rcx+r12*8+30h]
0x1401409bb  jnz     loc_140140A67
0x1401409c1  mov     [rsp+1088h+NumberOfBytesRead], edi
0x1401409c5  lea     r9, [rsp+1088h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1401409ca  mov     rcx, [rcx+r12*8+28h]; hFile
0x1401409cf  lea     rdx, [rsp+1088h+Buffer]; lpBuffer
0x1401409d4  mov     r8d, 1000h; nNumberOfBytesToRead
0x1401409da  mov     [rsp+1088h+lpOverlapped], rdi; lpOverlapped
0x1401409df  call    cs:ReadFile
0x1401409e5  test    eax, eax
0x1401409e7  jz      short loc_140140A67
0x1401409e9  mov     r9, r15
0x1401409ec  xor     r8d, r8d
0x1401409ef  mov     rdx, rbp
0x1401409f2  mov     ecx, r14d
0x1401409f5  call    j_??$common_lseek@_J@@YA_JH_JHAEAV__crt_cached_ptd_host@@@Z
0x1401409fa  test    rax, rax
0x1401409fd  js      short loc_140140A67
0x1401409ff  mov     eax, [rsp+1088h+NumberOfBytesRead]
0x140140a03  cmp     rsi, rax
0x140140a06  jg      short loc_140140A67
0x140140a08  lea     rdx, [rsp+1088h+Buffer]
0x140140a0d  add     rdx, rax
0x140140a10  lea     rcx, [rsp+1088h+Buffer]
0x140140a15  test    rsi, rsi
0x140140a18  jz      short loc_140140A59
0x140140a1a  lea     r8, __ImageBase
0x140140a21  cmp     rcx, rdx
0x140140a24  jnb     short loc_140140A59
0x140140a26  cmp     byte ptr [rcx], 0Dh
0x140140a29  jnz     short loc_140140A3F
0x140140a2b  lea     rax, [rdx-1]
0x140140a2f  cmp     rcx, rax
0x140140a32  jnb     short loc_140140A4E
0x140140a34  cmp     byte ptr [rcx+1], 0Ah
0x140140a38  jnz     short loc_140140A4E
0x140140a3a  inc     rcx
0x140140a3d  jmp     short loc_140140A4E
0x140140a3f  movzx   eax, byte ptr [rcx]
0x140140a42  movsx   rax, byte ptr [rax+r8+37A370h]
0x140140a4b  add     rcx, rax
0x140140a4e  inc     rdi
0x140140a51  inc     rcx
0x140140a54  cmp     rdi, rsi
0x140140a57  jnz     short loc_140140A21
0x140140a59  lea     rax, [rsp+1088h+Buffer]
0x140140a5e  sub     rcx, rax
0x140140a61  lea     rax, [rcx+r13]
0x140140a65  jmp     short loc_140140A6B
0x140140a67  or      rax, 0FFFFFFFFFFFFFFFFh
0x140140a6b  mov     rcx, [rsp+1088h+var_48]
0x140140a73  xor     rcx, rsp; StackCookie
0x140140a76  call    __security_check_cookie
0x140140a7b  mov     rbx, [rsp+1088h+arg_0]
0x140140a83  add     rsp, 1050h
0x140140a8a  pop     r15
0x140140a8c  pop     r14
0x140140a8e  pop     r13
0x140140a90  pop     r12
0x140140a92  pop     rdi
0x140140a93  pop     rsi
0x140140a94  pop     rbp
0x140140a95  retn
```
