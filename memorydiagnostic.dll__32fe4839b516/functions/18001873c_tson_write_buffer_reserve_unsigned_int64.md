# tson::write_buffer::reserve(unsigned __int64)

- ea: `0x18001873c`
- end: `0x18001881d`
- name: `?reserve@write_buffer@tson@@AEAA_N_K@Z`
- size: `225`
- prototype: `bool __fastcall(tson::write_buffer *__hidden this, unsigned __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800038f0`
- `0x180003990`
- `0x1800065b4`
- `0x18000664c`
- `0x180007494`
- `0x18001758c`
- `0x180018458`
- `0x1800189d0`
- `0x180018a6c`
- `0x180019060`
- `0x18001a160`
- `0x18001a380`

## callees

- `0x18001873c`
- `0x18001a6ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800187ae`
- `KERNEL32!GetLastError` at `0x1800187ae`
- `KERNEL32!SetLastError` at `0x1800187cd`
- `KERNEL32!SetLastError` at `0x1800187cd`
- `ole32!CoTaskMemFree` at `0x1800187bf`
- `ole32!CoTaskMemFree` at `0x1800187bf`
- `ole32!CoTaskMemAlloc` at `0x180018773`
- `ole32!CoTaskMemAlloc` at `0x180018773`

## pseudocode

```c
bool __fastcall tson::write_buffer::reserve(tson::write_buffer *this, unsigned __int64 a2)
{
  rsize_t v3; // rbp
  char *v4; // rax
  char *v5; // rsi
  const void *v6; // r8
  rsize_t v7; // r14
  void *v8; // r15
  DWORD LastError; // ebx
  bool result; // al

  if ( *((_QWORD *)this + 260) - *((_QWORD *)this + 258) > a2 )
    a2 = *((_QWORD *)this + 260) - *((_QWORD *)this + 258);
  v3 = 2 * a2;
  v4 = (char *)CoTaskMemAlloc(2 * a2);
  v5 = v4;
  if ( v4 )
  {
    v6 = (const void *)*((_QWORD *)this + 258);
    v7 = *((_QWORD *)this + 259) - (_QWORD)v6;
    memcpy_s(v4, v3, v6, v7);
    v8 = *(void **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      CoTaskMemFree(v8);
      SetLastError(LastError);
    }
    *(_QWORD *)this = v5;
    *((_QWORD *)this + 259) = &v5[v7];
    *((_QWORD *)this + 260) = &v5[v3];
    result = 1;
    *((_QWORD *)this + 258) = v5;
  }
  else
  {
    *((_BYTE *)this + 8) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001873c  mov     [rsp+arg_0], rbx
0x180018741  mov     [rsp+arg_8], rbp
0x180018746  mov     [rsp+arg_10], rsi
0x18001874b  push    rdi
0x18001874c  push    r14
0x18001874e  push    r15
0x180018750  sub     rsp, 20h
0x180018754  mov     rax, [rcx+820h]
0x18001875b  mov     rdi, rcx
0x18001875e  sub     rax, [rcx+810h]
0x180018765  cmp     rax, rdx
0x180018768  cmova   rdx, rax
0x18001876c  lea     rbp, [rdx+rdx]
0x180018770  mov     rcx, rbp; cb
0x180018773  call    cs:__imp_CoTaskMemAlloc
0x18001877a  nop     dword ptr [rax+rax+00h]
0x18001877f  mov     rsi, rax
0x180018782  test    rax, rax
0x180018785  jz      short loc_1800187FD
0x180018787  mov     r8, [rdi+810h]; Source
0x18001878e  mov     rdx, rbp; DestinationSize
0x180018791  mov     r14, [rdi+818h]
0x180018798  mov     rcx, rax; Destination
0x18001879b  sub     r14, r8
0x18001879e  mov     r9, r14; SourceSize
0x1800187a1  call    memcpy_s
0x1800187a6  mov     r15, [rdi]
0x1800187a9  test    r15, r15
0x1800187ac  jz      short loc_1800187D9
0x1800187ae  call    cs:__imp_GetLastError
0x1800187b5  nop     dword ptr [rax+rax+00h]
0x1800187ba  mov     rcx, r15; pv
0x1800187bd  mov     ebx, eax
0x1800187bf  call    cs:__imp_CoTaskMemFree
0x1800187c6  nop     dword ptr [rax+rax+00h]
0x1800187cb  mov     ecx, ebx; dwErrCode
0x1800187cd  call    cs:__imp_SetLastError
0x1800187d4  nop     dword ptr [rax+rax+00h]
0x1800187d9  mov     [rdi], rsi
0x1800187dc  lea     rax, [r14+rsi]
0x1800187e0  mov     [rdi+818h], rax
0x1800187e7  lea     rax, [rsi+rbp]
0x1800187eb  mov     [rdi+820h], rax
0x1800187f2  mov     al, 1
0x1800187f4  mov     [rdi+810h], rsi
0x1800187fb  jmp     short loc_180018803
0x1800187fd  mov     byte ptr [rdi+8], 1
0x180018801  xor     al, al
0x180018803  mov     rbx, [rsp+38h+arg_0]
0x180018808  mov     rbp, [rsp+38h+arg_8]
0x18001880d  mov     rsi, [rsp+38h+arg_10]
0x180018812  add     rsp, 20h
0x180018816  pop     r15
0x180018818  pop     r14
0x18001881a  pop     rdi
0x18001881b  retn
```
