# CMsmqVssWriter::~CMsmqVssWriter(void)

- ea: `0x18008d900`
- end: `0x18008d991`
- name: `??1CMsmqVssWriter@@UEAA@XZ`
- size: `145`
- prototype: `void __fastcall(CMsmqVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18008da10`

## callees

- `0x18002c61c`
- `0x18008d900`
- `0x18008d9b8`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x18008d967`
- `msvcrt!free` at `0x18008d972`
- `msvcrt!free` at `0x18008d97d`
- `msvcrt!free` at `0x18008d967`
- `msvcrt!free` at `0x18008d972`
- `msvcrt!free` at `0x18008d97d`
- `KERNEL32!DeleteCriticalSection` at `0x18008d95c`
- `KERNEL32!DeleteCriticalSection` at `0x18008d95c`

## string_xrefs

- `0x18008d94b`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMsmqVssWriter::~CMsmqVssWriter(CMsmqVssWriter *this)
{
  __int64 v2; // rcx
  int v3; // ecx

  *(_QWORD *)this = &CMsmqVssWriter::`vftable';
  if ( *((_DWORD *)this + 14) )
  {
    v2 = *((_QWORD *)this + 1);
    if ( v2 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
      v3 = 0;
    }
    else
    {
      v3 = -2147467259;
    }
    *((_DWORD *)this + 14) = v3 != 0;
    if ( v3 < 0 )
      LogMsgHR(v3, (wchar_t *)L"writer/mqwriter", 0x2BCu);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  free(*((void **)this + 4));
  free(*((void **)this + 3));
  free(*((void **)this + 2));
  CVssWriter::~CVssWriter(this);
}

```

## disassembly

```asm
0x18008d900  push    rbx
0x18008d902  sub     rsp, 20h
0x18008d906  mov     rbx, rcx
0x18008d909  lea     rax, ??_7CMsmqVssWriter@@6B@; const CMsmqVssWriter::`vftable'
0x18008d910  mov     [rcx], rax
0x18008d913  cmp     dword ptr [rcx+38h], 0
0x18008d917  jz      short loc_18008D958
0x18008d919  mov     rcx, [rcx+8]
0x18008d91d  test    rcx, rcx
0x18008d920  jnz     short loc_18008D929
0x18008d922  mov     ecx, 80004005h
0x18008d927  jmp     short loc_18008D937
0x18008d929  mov     rax, [rcx]
0x18008d92c  mov     rax, [rax+28h]
0x18008d930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008d935  xor     ecx, ecx; int
0x18008d937  xor     eax, eax
0x18008d939  test    ecx, ecx
0x18008d93b  setnz   al
0x18008d93e  mov     [rbx+38h], eax
0x18008d941  test    ecx, ecx
0x18008d943  jns     short loc_18008D958
0x18008d945  mov     r8d, 2BCh; unsigned __int16
0x18008d94b  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008d952  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008d957  nop
0x18008d958  lea     rcx, [rbx+40h]; lpCriticalSection
0x18008d95c  call    cs:__imp_DeleteCriticalSection
0x18008d962  nop
0x18008d963  mov     rcx, [rbx+20h]; Block
0x18008d967  call    cs:__imp_free
0x18008d96d  nop
0x18008d96e  mov     rcx, [rbx+18h]; Block
0x18008d972  call    cs:__imp_free
0x18008d978  nop
0x18008d979  mov     rcx, [rbx+10h]; Block
0x18008d97d  call    cs:__imp_free
0x18008d983  nop
0x18008d984  mov     rcx, rbx; this
0x18008d987  add     rsp, 20h
0x18008d98b  pop     rbx
0x18008d98c  jmp     ??1CVssWriter@@UEAA@XZ; CVssWriter::~CVssWriter(void)
```
