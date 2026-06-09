# CWMWriter::GetCurFile(ushort * *,_AMMediaType *)

- ea: `0x18000fae0`
- end: `0x18000fb70`
- name: `?GetCurFile@CWMWriter@@UEAAJPEAPEAGPEAU_AMMediaType@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, unsigned __int16 **, struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002660`
- `0x18000fae0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18000fb12`
- `KERNEL32!lstrlenW` at `0x18000fb12`
- `ole32!CoTaskMemAlloc` at `0x18000fb21`
- `ole32!CoTaskMemAlloc` at `0x18000fb21`

## pseudocode

```c
__int64 __fastcall CWMWriter::GetCurFile(CWMWriter *this, unsigned __int16 **a2, struct _AMMediaType *a3)
{
  const WCHAR *v7; // rcx
  __int64 v8; // r14
  unsigned __int16 *v9; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v7 = (const WCHAR *)*((_QWORD *)this + 19);
  if ( v7 )
  {
    v8 = (unsigned int)(lstrlenW(v7) + 1);
    v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8);
    *a2 = v9;
    if ( !v9 )
      return 2147942414LL;
    StringCchCopyW(v9, (unsigned int)v8, *((const unsigned __int16 **)this + 19));
  }
  if ( a3 )
  {
    a3->majortype = GUID_NULL;
    a3->subtype = GUID_NULL;
  }
  return 0;
}

```

## disassembly

```asm
0x18000fae0  push    rbx
0x18000fae2  push    rsi
0x18000fae3  push    rdi
0x18000fae4  push    r14
0x18000fae6  sub     rsp, 28h
0x18000faea  mov     rbx, r8
0x18000faed  mov     rdi, rdx
0x18000faf0  mov     rsi, rcx
0x18000faf3  test    rdx, rdx
0x18000faf6  jnz     short loc_18000FAFF
0x18000faf8  mov     eax, 80004003h
0x18000fafd  jmp     short loc_18000FB5F
0x18000faff  mov     qword ptr [rdx], 0
0x18000fb06  mov     rcx, [rcx+98h]; lpString
0x18000fb0d  test    rcx, rcx
0x18000fb10  jz      short loc_18000FB41
0x18000fb12  call    cs:__imp_lstrlenW
0x18000fb18  inc     eax
0x18000fb1a  mov     r14d, eax
0x18000fb1d  lea     rcx, [rax+rax]; cb
0x18000fb21  call    cs:__imp_CoTaskMemAlloc
0x18000fb27  mov     [rdi], rax
0x18000fb2a  test    rax, rax
0x18000fb2d  jz      short loc_18000FB69
0x18000fb2f  mov     r8, [rsi+98h]; unsigned __int16 *
0x18000fb36  mov     edx, r14d; unsigned __int64
0x18000fb39  mov     rcx, rax; unsigned __int16 *
0x18000fb3c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fb41  test    rbx, rbx
0x18000fb44  jz      short loc_18000FB5D
0x18000fb46  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000fb4d  movdqu  xmmword ptr [rbx], xmm0
0x18000fb51  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18000fb58  movdqu  xmmword ptr [rbx+10h], xmm1
0x18000fb5d  xor     eax, eax
0x18000fb5f  add     rsp, 28h
0x18000fb63  pop     r14
0x18000fb65  pop     rdi
0x18000fb66  pop     rsi
0x18000fb67  pop     rbx
0x18000fb68  retn
0x18000fb69  mov     eax, 8007000Eh
0x18000fb6e  jmp     short loc_18000FB5F
```
