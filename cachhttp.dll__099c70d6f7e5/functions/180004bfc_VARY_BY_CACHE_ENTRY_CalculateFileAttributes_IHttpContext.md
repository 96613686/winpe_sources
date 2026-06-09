# VARY_BY_CACHE_ENTRY::CalculateFileAttributes(IHttpContext *)

- ea: `0x180004bfc`
- end: `0x180004d12`
- name: `?CalculateFileAttributes@VARY_BY_CACHE_ENTRY@@QEAAXPEAVIHttpContext@@@Z`
- size: `278`
- prototype: `void __fastcall(VARY_BY_CACHE_ENTRY *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004220`

## callees

- `0x180004bfc`
- `0x180008bf0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004cee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004cee`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180004cba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180004cba`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180004caa`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180004caa`

## pseudocode

```c
void __fastcall VARY_BY_CACHE_ENTRY::CalculateFileAttributes(VARY_BY_CACHE_ENTRY *this, struct IHttpContext *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  const WCHAR *Str; // rax
  __int128 FileInformation; // [rsp+20h] [rbp-38h] BYREF
  __int128 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+40h] [rbp-18h]

  if ( !*((_QWORD *)this + 85) && !*((_DWORD *)this + 162) )
  {
    v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 208LL))(a2);
    v4 = v3;
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v3 + 64LL))(v3, (char *)this + 656);
      *((_DWORD *)this + 166) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4);
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v4 + 104LL))(v4, (char *)this + 672);
    }
    else
    {
      FileInformation = 0;
      v8 = 0;
      v7 = 0;
      Str = STRU::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)this + 336));
      if ( !GetFileAttributesExW(Str, GetFileExInfoStandard, &FileInformation) )
        return;
      *((_DWORD *)this + 164) = v8;
      *((_DWORD *)this + 165) = HIDWORD(v7);
      *((_DWORD *)this + 166) = FileInformation;
      *((_QWORD *)this + 84) = *(_QWORD *)((char *)&v7 + 4);
    }
    *((_DWORD *)this + 162) = GetTickCount();
  }
}

```

## disassembly

```asm
0x180004bfc  mov     [rsp+arg_10], rbx
0x180004c01  push    rdi
0x180004c02  sub     rsp, 50h
0x180004c06  mov     rax, cs:__security_cookie
0x180004c0d  xor     rax, rsp
0x180004c10  mov     [rsp+58h+var_10], rax
0x180004c15  cmp     qword ptr [rcx+2A8h], 0
0x180004c1d  mov     rbx, rcx
0x180004c20  jnz     loc_180004CFA
0x180004c26  cmp     dword ptr [rcx+288h], 0
0x180004c2d  jnz     loc_180004CFA
0x180004c33  mov     rax, [rdx]
0x180004c36  mov     rcx, rdx
0x180004c39  mov     rax, [rax+0D0h]
0x180004c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c45  mov     rdi, rax
0x180004c48  test    rax, rax
0x180004c4b  jz      short loc_180004C90
0x180004c4d  mov     rcx, [rax]
0x180004c50  lea     rdx, [rbx+290h]
0x180004c57  mov     rax, [rcx+40h]
0x180004c5b  mov     rcx, rdi
0x180004c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c63  mov     rcx, [rdi]
0x180004c66  mov     rax, [rcx+38h]
0x180004c6a  mov     rcx, rdi
0x180004c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c72  mov     [rbx+298h], eax
0x180004c78  lea     rdx, [rbx+2A0h]
0x180004c7f  mov     rax, [rdi]
0x180004c82  mov     rcx, rdi
0x180004c85  mov     rax, [rax+68h]
0x180004c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c8e  jmp     short loc_180004CEE
0x180004c90  xorps   xmm0, xmm0
0x180004c93  lea     rcx, [rbx+150h]
0x180004c9a  xor     eax, eax
0x180004c9c  movups  [rsp+58h+FileInformation], xmm0
0x180004ca1  mov     [rsp+58h+var_18], eax
0x180004ca5  movups  [rsp+58h+var_28], xmm0
0x180004caa  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180004cb0  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180004cb5  xor     edx, edx; fInfoLevelId
0x180004cb7  mov     rcx, rax; lpFileName
0x180004cba  call    cs:__imp_GetFileAttributesExW
0x180004cc0  test    eax, eax
0x180004cc2  jz      short loc_180004CFA
0x180004cc4  mov     eax, [rsp+58h+var_18]
0x180004cc8  mov     [rbx+290h], eax
0x180004cce  mov     eax, dword ptr [rsp+58h+var_28+0Ch]
0x180004cd2  mov     [rbx+294h], eax
0x180004cd8  mov     eax, dword ptr [rsp+58h+FileInformation]
0x180004cdc  mov     [rbx+298h], eax
0x180004ce2  mov     rax, qword ptr [rsp+58h+var_28+4]
0x180004ce7  mov     [rbx+2A0h], rax
0x180004cee  call    cs:__imp_GetTickCount
0x180004cf4  mov     [rbx+288h], eax
0x180004cfa  mov     rcx, [rsp+58h+var_10]
0x180004cff  xor     rcx, rsp; StackCookie
0x180004d02  call    __security_check_cookie
0x180004d07  mov     rbx, [rsp+58h+arg_10]
0x180004d0c  add     rsp, 50h
0x180004d10  pop     rdi
0x180004d11  retn
```
