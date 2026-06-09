# AutoDeleteFileStream::~AutoDeleteFileStream(void)

- ea: `0x180034dd0`
- end: `0x180034e9c`
- name: `??1AutoDeleteFileStream@@UEAA@XZ`
- size: `204`
- prototype: `void __fastcall(AutoDeleteFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180034eb0`

## callees

- `0x180001b14`
- `0x180034dd0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180034e68`
- `msvcrt!??3@YAXPEAX@Z` at `0x180034e68`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180034dfa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180034dfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AutoDeleteFileStream::~AutoDeleteFileStream(AutoDeleteFileStream *this)
{
  char *v2; // rbx
  const WCHAR *v3; // rcx
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  char *v7; // rax
  __int64 v8; // rcx
  char *v9; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &AutoDeleteFileStream::`vftable';
  v2 = (char *)this + 16;
  if ( *((_QWORD *)this + 5) < 8u )
    v3 = (const WCHAR *)((char *)this + 16);
  else
    v3 = *(const WCHAR **)v2;
  if ( !DeleteFileW(v3) && (unsigned int)dword_1800495B0 > 2 )
  {
    if ( *((_QWORD *)v2 + 3) < 8u )
      v7 = v2;
    else
      v7 = *(char **)v2;
    v9 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v4,
      (unsigned int)&unk_180041D98,
      v5,
      v6,
      (__int64)&v9);
  }
  v8 = *((_QWORD *)this + 6);
  if ( v8 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( *((_QWORD *)v2 + 3) >= 8u )
    operator delete(*(void **)v2);
  *((_QWORD *)v2 + 3) = 7;
  *((_QWORD *)v2 + 2) = 0;
  *(_WORD *)v2 = 0;
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180034dd0  mov     [rsp+arg_8], rbx
0x180034dd5  push    rdi
0x180034dd6  sub     rsp, 30h
0x180034dda  mov     rdi, rcx
0x180034ddd  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x180034de4  mov     [rcx], rax
0x180034de7  lea     rbx, [rcx+10h]
0x180034deb  cmp     qword ptr [rbx+18h], 8
0x180034df0  jb      short loc_180034DF7
0x180034df2  mov     rcx, [rbx]
0x180034df5  jmp     short loc_180034DFA
0x180034df7  mov     rcx, rbx; lpFileName
0x180034dfa  call    cs:__imp_DeleteFileW
0x180034e01  nop     dword ptr [rax+rax+00h]
0x180034e06  test    eax, eax
0x180034e08  jnz     short loc_180034E40
0x180034e0a  mov     eax, cs:dword_1800495B0
0x180034e10  cmp     eax, 2
0x180034e13  jbe     short loc_180034E40
0x180034e15  cmp     qword ptr [rbx+18h], 8
0x180034e1a  jb      short loc_180034E21
0x180034e1c  mov     rax, [rbx]
0x180034e1f  jmp     short loc_180034E24
0x180034e21  mov     rax, rbx
0x180034e24  mov     [rsp+38h+arg_0], rax
0x180034e29  lea     rax, [rsp+38h+arg_0]
0x180034e2e  mov     [rsp+38h+var_18], rax
0x180034e33  lea     rdx, unk_180041D98
0x180034e3a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180034e3f  nop
0x180034e40  mov     rcx, [rdi+30h]
0x180034e44  test    rcx, rcx
0x180034e47  jz      short loc_180034E5E
0x180034e49  mov     qword ptr [rdi+30h], 0
0x180034e51  mov     rax, [rcx]
0x180034e54  mov     rax, [rax+10h]
0x180034e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e5d  nop
0x180034e5e  cmp     qword ptr [rbx+18h], 8
0x180034e63  jb      short loc_180034E74
0x180034e65  mov     rcx, [rbx]
0x180034e68  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180034e6f  nop     dword ptr [rax+rax+00h]
0x180034e74  mov     qword ptr [rbx+18h], 7
0x180034e7c  mov     qword ptr [rbx+10h], 0
0x180034e84  xor     eax, eax
0x180034e86  mov     [rbx], ax
0x180034e89  mov     dword ptr [rdi+0Ch], 0C0000001h
0x180034e90  mov     rbx, [rsp+38h+arg_8]
0x180034e95  add     rsp, 30h
0x180034e99  pop     rdi
0x180034e9a  retn
```
