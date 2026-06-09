# ATL::CDacl::CAccessAce::GetACE(void)

- ea: `0x18000bee0`
- end: `0x18000bf92`
- name: `?GetACE@CAccessAce@CDacl@ATL@@UEBAPEAXXZ`
- size: `178`
- prototype: `char *__fastcall(ATL::CDacl::CAccessAce *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180005bcc`
- `0x180005c18`
- `0x18000bee0`
- `0x18002c802`
- `0x18002f010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000bf72`
- `msvcrt!memcpy_s` at `0x18000bf72`
- `msvcrt!malloc` at `0x18000bf0c`
- `msvcrt!malloc` at `0x18000bf0c`
- `ADVAPI32!GetLengthSid` at `0x18000bf5d`
- `ADVAPI32!GetLengthSid` at `0x18000bf5d`

## pseudocode

```c
char *__fastcall ATL::CDacl::CAccessAce::GetACE(ATL::CDacl::CAccessAce *this)
{
  char *v1; // rdi
  size_t v3; // rbx
  char *v4; // rax
  __int64 v5; // rax
  DWORD LengthSid; // eax
  errno_t v7; // eax

  v1 = (char *)*((_QWORD *)this + 17);
  if ( !v1 )
  {
    v3 = (*(unsigned int (__fastcall **)(ATL::CDacl::CAccessAce *))(*(_QWORD *)this + 16LL))(this);
    v4 = (char *)malloc(v3);
    v1 = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(-2147024882);
    memset_0(v4, 0, v3);
    v1[1] = *((_BYTE *)this + 132);
    v5 = *(_QWORD *)this;
    *((_WORD *)v1 + 1) = v3;
    *v1 = (*(__int64 (__fastcall **)(ATL::CDacl::CAccessAce *))(v5 + 24))(this);
    *((_DWORD *)v1 + 1) = *((_DWORD *)this + 32);
    LengthSid = GetLengthSid((char *)this + 16);
    v7 = memcpy_s(v1 + 8, v3 - 8, (char *)this + 16, LengthSid);
    ATL::AtlCrtErrorCheck(v7);
    *((_QWORD *)this + 17) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x18000bee0  push    rbx
0x18000bee2  push    rbp
0x18000bee3  push    rsi
0x18000bee4  push    rdi
0x18000bee5  sub     rsp, 28h
0x18000bee9  mov     rdi, [rcx+88h]
0x18000bef0  mov     rsi, rcx
0x18000bef3  test    rdi, rdi
0x18000bef6  jnz     loc_18000BF86
0x18000befc  mov     rax, [rcx]
0x18000beff  mov     rax, [rax+10h]
0x18000bf03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf08  mov     ecx, eax; Size
0x18000bf0a  mov     ebx, eax
0x18000bf0c  call    cs:__imp_malloc
0x18000bf12  mov     rdi, rax
0x18000bf15  test    rax, rax
0x18000bf18  jnz     short loc_18000BF25
0x18000bf1a  mov     ecx, 8007000Eh; int
0x18000bf1f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000bf25  mov     r8, rbx; Size
0x18000bf28  xor     edx, edx; Val
0x18000bf2a  mov     rcx, rdi; void *
0x18000bf2d  call    memset_0
0x18000bf32  mov     al, [rsi+84h]
0x18000bf38  mov     rcx, rsi
0x18000bf3b  mov     [rdi+1], al
0x18000bf3e  mov     rax, [rsi]
0x18000bf41  mov     [rdi+2], bx
0x18000bf45  mov     rax, [rax+18h]
0x18000bf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf4e  mov     [rdi], al
0x18000bf50  lea     rcx, [rsi+10h]; pSid
0x18000bf54  mov     eax, [rsi+80h]
0x18000bf5a  mov     [rdi+4], eax
0x18000bf5d  call    cs:__imp_GetLengthSid
0x18000bf63  mov     r9d, eax; SourceSize
0x18000bf66  lea     rdx, [rbx-8]; DestinationSize
0x18000bf6a  lea     rcx, [rdi+8]; Destination
0x18000bf6e  lea     r8, [rsi+10h]; Source
0x18000bf72  call    cs:__imp_memcpy_s
0x18000bf78  mov     ecx, eax; int
0x18000bf7a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bf7f  mov     [rsi+88h], rdi
0x18000bf86  mov     rax, rdi
0x18000bf89  add     rsp, 28h
0x18000bf8d  pop     rdi
0x18000bf8e  pop     rsi
0x18000bf8f  pop     rbp
0x18000bf90  pop     rbx
0x18000bf91  retn
```
