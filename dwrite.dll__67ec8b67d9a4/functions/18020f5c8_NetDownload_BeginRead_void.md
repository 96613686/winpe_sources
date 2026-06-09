# NetDownload::BeginRead(void)

- ea: `0x18020f5c8`
- end: `0x18020f6f3`
- name: `?BeginRead@NetDownload@@AEAAXXZ`
- size: `299`
- prototype: `void __fastcall(NetDownload *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18020e028`
- `0x18020f4b8`
- `0x18020f5c8`

## callees

- `0x18012a85c`
- `0x1801537f8`
- `0x18016975c`
- `0x1801bae58`
- `0x18020f5c8`
- `0x18021e1b6`
- `0x1802547e0`

## import_xrefs

- `kernel32!GetLastError` at `0x18020f6e0`
- `kernel32!GetLastError` at `0x18020f6e0`
- `WININET!InternetReadFile` at `0x18020f6ae`
- `WININET!InternetReadFile` at `0x18020f6ae`

## pseudocode

```c
void __fastcall NetDownload::BeginRead(NetDownload *this)
{
  unsigned int v1; // eax
  char *v3; // rbx
  size_t v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rcx
  _DWORD *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // [rsp+40h] [rbp+20h] BYREF
  int v10; // [rsp+48h] [rbp+28h] BYREF
  __int64 v11; // [rsp+50h] [rbp+30h] BYREF

  v1 = *((_DWORD *)this + 22);
  if ( v1 )
  {
    if ( *((_DWORD *)this + 23) >= v1 )
      goto LABEL_15;
    v3 = (char *)this + 80;
  }
  else
  {
    v3 = (char *)this + 80;
    if ( *(unsigned int *)(*((_QWORD *)this + 10) + 4LL) - (unsigned __int64)*((unsigned int *)this + 23) < 0x10000 )
    {
      v11 = *(unsigned int *)(*((_QWORD *)this + 10) + 4LL);
      LODWORD(v9) = 0;
      v10 = 2;
      MultiplicationHelper<unsigned int,unsigned __int64,8>::MultiplyThrow<SafeIntExceptionHandler<Exception>>(
        &v10,
        &v11,
        &v9);
      v4 = *(unsigned int *)(*(_QWORD *)v3 + 4LL);
      if ( (unsigned int)v9 >= (unsigned int)v4 )
      {
        if ( (unsigned int)v9 > (unsigned int)v4 )
        {
          RefCountedArrayImpl::RefCountedArrayImpl((RefCountedArrayImpl *)&v9, v9, 1u);
          if ( (_DWORD)v4 )
            memcpy_0((void *)(v9 + 8), (const void *)(*(_QWORD *)v3 + 8LL), v4);
          v5 = v9;
          v9 = *(_QWORD *)v3;
          *(_QWORD *)v3 = v5;
          RefCountedArrayImpl::~RefCountedArrayImpl((RefCountedArrayImpl *)&v9);
        }
      }
      else
      {
        *(_DWORD *)(*(_QWORD *)v3 + 4LL) = v9;
      }
    }
  }
  v6 = *((unsigned int *)this + 23);
  v7 = (_DWORD *)((char *)this + 96);
  v8 = *(_QWORD *)v3;
  *((_DWORD *)this + 24) = 0;
  if ( InternetReadFile(*((HINTERNET *)this + 18), (LPVOID)(v8 + v6 + 8), *(_DWORD *)(v8 + 4) - v6, (LPDWORD)this + 24) )
  {
    if ( *v7 )
    {
      *((_DWORD *)this + 23) += *v7;
      NetDownload::BeginRead(this);
      return;
    }
LABEL_15:
    NetDownload::Finalize(this);
    return;
  }
  if ( GetLastError() != 997 )
    OSException::ThrowLastError();
}

```

## disassembly

```asm
0x18020f5c8  mov     [rsp-18h+arg_18], rbx
0x18020f5cd  push    rbp
0x18020f5ce  push    rsi
0x18020f5cf  push    rdi
0x18020f5d0  mov     rbp, rsp
0x18020f5d3  sub     rsp, 20h
0x18020f5d7  mov     eax, [rcx+58h]
0x18020f5da  mov     rdi, rcx
0x18020f5dd  test    eax, eax
0x18020f5df  jz      short loc_18020F5F3
0x18020f5e1  cmp     [rcx+5Ch], eax
0x18020f5e4  jnb     loc_18020F6D6
0x18020f5ea  lea     rbx, [rcx+50h]
0x18020f5ee  jmp     loc_18020F686
0x18020f5f3  lea     rbx, [rcx+50h]
0x18020f5f7  mov     rax, [rbx]
0x18020f5fa  mov     edx, [rax+4]
0x18020f5fd  mov     eax, [rcx+5Ch]
0x18020f600  mov     ecx, edx
0x18020f602  sub     rcx, rax
0x18020f605  cmp     rcx, 10000h
0x18020f60c  jnb     short loc_18020F686
0x18020f60e  mov     [rbp+arg_10], rdx
0x18020f612  lea     r8, [rbp+arg_0]
0x18020f616  lea     rdx, [rbp+arg_10]
0x18020f61a  mov     dword ptr [rbp+arg_0], 0
0x18020f621  lea     rcx, [rbp+arg_8]
0x18020f625  mov     [rbp+arg_8], 2
0x18020f62c  call    ??$MultiplyThrow@V?$SafeIntExceptionHandler@VException@@@@@?$MultiplicationHelper@I_K$07@@SAXAEBIAEB_KAEAI@Z; MultiplicationHelper<uint,unsigned __int64,8>::MultiplyThrow<SafeIntExceptionHandler<Exception>>(uint const &,unsigned __int64 const &,uint &)
0x18020f631  mov     rax, [rbx]
0x18020f634  mov     edx, dword ptr [rbp+arg_0]; unsigned int
0x18020f637  mov     esi, [rax+4]
0x18020f63a  cmp     edx, esi
0x18020f63c  jnb     short loc_18020F643
0x18020f63e  mov     [rax+4], edx
0x18020f641  jmp     short loc_18020F686
0x18020f643  jbe     short loc_18020F686
0x18020f645  mov     r8d, 1; unsigned int
0x18020f64b  lea     rcx, [rbp+arg_0]; this
0x18020f64f  call    ??0RefCountedArrayImpl@@IEAA@II@Z; RefCountedArrayImpl::RefCountedArrayImpl(uint,uint)
0x18020f654  test    esi, esi
0x18020f656  jz      short loc_18020F66F
0x18020f658  mov     rdx, [rbx]
0x18020f65b  mov     r8, rsi; Size
0x18020f65e  mov     rcx, [rbp+arg_0]
0x18020f662  add     rdx, 8; Src
0x18020f666  add     rcx, 8; void *
0x18020f66a  call    memcpy_0
0x18020f66f  mov     rcx, [rbx]
0x18020f672  mov     rax, [rbp+arg_0]
0x18020f676  mov     [rbp+arg_0], rcx
0x18020f67a  lea     rcx, [rbp+arg_0]; this
0x18020f67e  mov     [rbx], rax
0x18020f681  call    ??1RefCountedArrayImpl@@QEAA@XZ; RefCountedArrayImpl::~RefCountedArrayImpl(void)
0x18020f686  mov     ecx, [rdi+5Ch]
0x18020f689  lea     rsi, [rdi+60h]
0x18020f68d  mov     rax, [rbx]
0x18020f690  mov     r9, rsi; lpdwNumberOfBytesRead
0x18020f693  mov     dword ptr [rsi], 0
0x18020f699  lea     rdx, [rcx+8]
0x18020f69d  mov     r8d, [rax+4]
0x18020f6a1  add     rdx, rax; lpBuffer
0x18020f6a4  sub     r8d, ecx; dwNumberOfBytesToRead
0x18020f6a7  mov     rcx, [rdi+90h]; hFile
0x18020f6ae  call    cs:__imp_InternetReadFile
0x18020f6b4  test    eax, eax
0x18020f6b6  jz      short loc_18020F6E0
0x18020f6b8  mov     eax, [rsi]
0x18020f6ba  test    eax, eax
0x18020f6bc  jz      short loc_18020F6D6
0x18020f6be  add     [rdi+5Ch], eax
0x18020f6c1  mov     rcx, rdi; this
0x18020f6c4  call    ?BeginRead@NetDownload@@AEAAXXZ; NetDownload::BeginRead(void)
0x18020f6c9  mov     rbx, [rsp+20h+arg_18]
0x18020f6ce  add     rsp, 20h
0x18020f6d2  pop     rdi
0x18020f6d3  pop     rsi
0x18020f6d4  pop     rbp
0x18020f6d5  retn
0x18020f6d6  mov     rcx, rdi; this
0x18020f6d9  call    ?Finalize@NetDownload@@AEAAXXZ; NetDownload::Finalize(void)
0x18020f6de  jmp     short loc_18020F6C9
0x18020f6e0  call    cs:__imp_GetLastError
0x18020f6e6  cmp     eax, 3E5h
0x18020f6eb  jz      short loc_18020F6C9
0x18020f6ed  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
