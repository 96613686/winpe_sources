# RepoMan::FileStream::Read(void *,ulong,ulong *)

- ea: `0x18018c690`
- end: `0x18018c786`
- name: `?Read@FileStream@RepoMan@@UEAAJPEAXKPEAK@Z`
- size: `246`
- prototype: `int(RepoMan::FileStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180013b14`
- `0x18018aed8`
- `0x18018c690`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18018c6db`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x18018c6db`
- `api-ms-win-crt-stdio-l1-1-0!feof` at `0x18018c6ed`
- `api-ms-win-crt-stdio-l1-1-0!feof` at `0x18018c6ed`
- `api-ms-win-crt-stdio-l1-1-0!ftell` at `0x18018c6fb`
- `api-ms-win-crt-stdio-l1-1-0!ftell` at `0x18018c6fb`

## string_xrefs

- `0x18018c76c`: `read failed`

## pseudocode

```c
__int64 __fastcall RepoMan::FileStream::Read(FILE **this, void *a2, unsigned int a3, unsigned int *a4)
{
  __int64 result; // rax
  unsigned int v8; // eax
  unsigned int v9; // esi
  int v10; // r8d
  FILE *v11; // rcx
  RepoMan *v12; // rcx
  const char *v13; // r9

  if ( !a2 )
    return 2147680265LL;
  if ( a4 )
    *a4 = 0;
  v8 = fread(a2, 1u, a3, this[8]);
  try
  {
    v9 = v8;
    if ( v8 != a3 && !feof(this[8]) )
      RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
        135,
        (unsigned int)"src\\repoman\\src\\inc\\FileSystem.hpp",
        (unsigned int)"read failed",
        -1941503469,
        8);
    this[2] = (FILE *)ftell(this[8]);
    if ( a4 )
      *a4 = v9;
    v11 = this[9];
    if ( v11 )
    {
      v12 = (RepoMan *)(*((unsigned int (__fastcall **)(FILE *, __int64, _QWORD))v11->_ptr + 6))(v11, 4, v9);
      RepoMan::RaiseExceptionIfFailed(v12, 143, (int)"src\\repoman\\src\\inc\\FileSystem.hpp", v13);
    }
    result = 0;
  }
  catch ( ... )
  {
    RepoMan::Lippincott((RepoMan *)"src\\repoman\\src\\inc\\FileSystem.hpp", (const char *)0x93, v10);
  }
  return result;
}

```

## disassembly

```asm
0x18018c690  mov     [rsp+arg_0], rbx
0x18018c695  mov     [rsp+arg_10], rsi
0x18018c69a  mov     [rsp+arg_18], rdi
0x18018c69f  push    r14
0x18018c6a1  sub     rsp, 30h
0x18018c6a5  mov     rbx, r9
0x18018c6a8  mov     r14d, r8d
0x18018c6ab  mov     rax, rdx
0x18018c6ae  mov     rdi, rcx
0x18018c6b1  test    rax, rax
0x18018c6b4  jnz     short loc_18018C6C0
0x18018c6b6  mov     eax, 80030009h
0x18018c6bb  jmp     loc_18018C748
0x18018c6c0  test    rbx, rbx
0x18018c6c3  jz      short loc_18018C6CC
0x18018c6c5  mov     dword ptr [r9], 0
0x18018c6cc  mov     r8, r14; ElementCount
0x18018c6cf  mov     r9, [rcx+40h]; Stream
0x18018c6d3  mov     edx, 1; ElementSize
0x18018c6d8  mov     rcx, rax; Buffer
0x18018c6db  call    cs:__imp_fread
0x18018c6e1  mov     rsi, rax
0x18018c6e4  cmp     eax, r14d
0x18018c6e7  jz      short loc_18018C6F7
0x18018c6e9  mov     rcx, [rdi+40h]; Stream
0x18018c6ed  call    cs:__imp_feof
0x18018c6f3  test    eax, eax
0x18018c6f5  jz      short loc_18018C75E
0x18018c6f7  mov     rcx, [rdi+40h]; Stream
0x18018c6fb  call    cs:__imp_ftell
0x18018c701  movsxd  rcx, eax
0x18018c704  mov     [rdi+10h], rcx
0x18018c708  test    rbx, rbx
0x18018c70b  jz      short loc_18018C70F
0x18018c70d  mov     [rbx], esi
0x18018c70f  mov     rcx, [rdi+48h]
0x18018c713  test    rcx, rcx
0x18018c716  jz      short loc_18018C740
0x18018c718  mov     rax, [rcx]
0x18018c71b  mov     r8d, esi
0x18018c71e  mov     edx, 4
0x18018c723  mov     rax, [rax+30h]
0x18018c727  call    cs:__guard_dispatch_icall_fptr
0x18018c72d  mov     ecx, eax; this
0x18018c72f  lea     r8, aSrcRepomanSrcI_17; "src\\repoman\\src\\inc\\FileSystem.hpp"
0x18018c736  mov     edx, 8Fh; int
0x18018c73b  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18018c740  xor     eax, eax
0x18018c742  jmp     short loc_18018C748
0x18018c744  mov     eax, [rsp+38h+arg_8]
0x18018c748  mov     rbx, [rsp+38h+arg_0]
0x18018c74d  mov     rsi, [rsp+38h+arg_10]
0x18018c752  mov     rdi, [rsp+38h+arg_18]
0x18018c757  add     rsp, 30h
0x18018c75b  pop     r14
0x18018c75d  retn
0x18018c75e  mov     [rsp+38h+var_18], 8
0x18018c766  mov     r9d, 8C470213h
0x18018c76c  lea     r8, aReadFailed; "read failed"
0x18018c773  lea     rdx, aSrcRepomanSrcI_17; "src\\repoman\\src\\inc\\FileSystem.hpp"
0x18018c77a  mov     ecx, 87h
0x18018c77f  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
```
