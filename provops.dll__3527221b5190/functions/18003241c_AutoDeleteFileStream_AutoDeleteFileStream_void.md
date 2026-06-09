# AutoDeleteFileStream::~AutoDeleteFileStream(void)

- ea: `0x18003241c`
- end: `0x1800324e1`
- name: `??1AutoDeleteFileStream@@UEAA@XZ`
- size: `197`
- prototype: `void __fastcall(AutoDeleteFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800324f0`

## callees

- `0x1800017ec`
- `0x18003241c`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800324b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800324b4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180032446`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180032446`

## pseudocode

```c
void __fastcall AutoDeleteFileStream::~AutoDeleteFileStream(AutoDeleteFileStream *this)
{
  char *v2; // rbx
  const WCHAR *v3; // rcx
  __int64 v4; // r9
  char *v5; // rax
  __int64 v6; // rcx
  char *v7; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &AutoDeleteFileStream::`vftable';
  v2 = (char *)this + 16;
  if ( *((_QWORD *)this + 5) < 8u )
    v3 = (const WCHAR *)((char *)this + 16);
  else
    v3 = *(const WCHAR **)v2;
  if ( !DeleteFileW(v3) && *(_DWORD *)g_hProvTraceProvider > 2u )
  {
    if ( *((_QWORD *)v2 + 3) < 8u )
      v5 = v2;
    else
      v5 = *(char **)v2;
    v7 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      g_hProvTraceProvider,
      (__int64)&byte_180041DB7,
      0,
      v4,
      &v7);
  }
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
  {
    *((_QWORD *)this + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
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
0x18003241c  mov     [rsp+arg_8], rbx
0x180032421  push    rdi
0x180032422  sub     rsp, 30h
0x180032426  mov     rdi, rcx
0x180032429  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x180032430  mov     [rcx], rax
0x180032433  lea     rbx, [rcx+10h]
0x180032437  cmp     qword ptr [rbx+18h], 8
0x18003243c  jb      short loc_180032443
0x18003243e  mov     rcx, [rbx]
0x180032441  jmp     short loc_180032446
0x180032443  mov     rcx, rbx; lpFileName
0x180032446  call    cs:__imp_DeleteFileW
0x18003244c  test    eax, eax
0x18003244e  jnz     short loc_18003248C
0x180032450  mov     rcx, cs:g_hProvTraceProvider
0x180032457  mov     eax, [rcx]
0x180032459  cmp     eax, 2
0x18003245c  jbe     short loc_18003248C
0x18003245e  cmp     qword ptr [rbx+18h], 8
0x180032463  jb      short loc_18003246A
0x180032465  mov     rax, [rbx]
0x180032468  jmp     short loc_18003246D
0x18003246a  mov     rax, rbx
0x18003246d  mov     [rsp+38h+arg_0], rax
0x180032472  lea     rax, [rsp+38h+arg_0]
0x180032477  mov     [rsp+38h+var_18], rax
0x18003247c  xor     r8d, r8d
0x18003247f  lea     rdx, byte_180041DB7
0x180032486  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003248b  nop
0x18003248c  mov     rcx, [rdi+30h]
0x180032490  test    rcx, rcx
0x180032493  jz      short loc_1800324AA
0x180032495  mov     qword ptr [rdi+30h], 0
0x18003249d  mov     rax, [rcx]
0x1800324a0  mov     rax, [rax+10h]
0x1800324a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324a9  nop
0x1800324aa  cmp     qword ptr [rbx+18h], 8
0x1800324af  jb      short loc_1800324BA
0x1800324b1  mov     rcx, [rbx]
0x1800324b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800324ba  mov     qword ptr [rbx+18h], 7
0x1800324c2  mov     qword ptr [rbx+10h], 0
0x1800324ca  xor     eax, eax
0x1800324cc  mov     [rbx], ax
0x1800324cf  mov     dword ptr [rdi+0Ch], 0C0000001h
0x1800324d6  mov     rbx, [rsp+38h+arg_8]
0x1800324db  add     rsp, 30h
0x1800324df  pop     rdi
0x1800324e0  retn
```
