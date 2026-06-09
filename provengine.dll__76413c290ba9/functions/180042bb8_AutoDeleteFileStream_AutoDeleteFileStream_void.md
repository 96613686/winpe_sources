# AutoDeleteFileStream::~AutoDeleteFileStream(void)

- ea: `0x180042bb8`
- end: `0x180042c81`
- name: `??1AutoDeleteFileStream@@UEAA@XZ`
- size: `201`
- prototype: `void __fastcall(AutoDeleteFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180042c90`

## callees

- `0x1800011ac`
- `0x180042bb8`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180042c54`
- `msvcrt!??3@YAXPEAX@Z` at `0x180042c54`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042be2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180042be2`

## pseudocode

```c
void __fastcall AutoDeleteFileStream::~AutoDeleteFileStream(AutoDeleteFileStream *this)
{
  __int64 *v2; // rbx
  const WCHAR *v3; // rcx
  __int64 v4; // r9
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 *v7; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &AutoDeleteFileStream::`vftable';
  v2 = (__int64 *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) < 8u )
    v3 = (const WCHAR *)((char *)this + 16);
  else
    v3 = (const WCHAR *)*v2;
  if ( !DeleteFileW(v3) && (unsigned int)dword_18005A000 > 2 )
  {
    if ( (unsigned __int64)v2[3] < 8 )
      v5 = v2;
    else
      v5 = (__int64 *)*v2;
    v7 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_18005A000,
      (__int64)byte_180050A4D,
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
  if ( (unsigned __int64)v2[3] >= 8 )
    operator delete((void *)*v2);
  v2[3] = 7;
  v2[2] = 0;
  *(_WORD *)v2 = 0;
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180042bb8  mov     [rsp+arg_8], rbx
0x180042bbd  push    rdi
0x180042bbe  sub     rsp, 30h
0x180042bc2  mov     rdi, rcx
0x180042bc5  lea     rax, ??_7AutoDeleteFileStream@@6B@; const AutoDeleteFileStream::`vftable'
0x180042bcc  mov     [rcx], rax
0x180042bcf  lea     rbx, [rcx+10h]
0x180042bd3  cmp     qword ptr [rbx+18h], 8
0x180042bd8  jb      short loc_180042BDF
0x180042bda  mov     rcx, [rbx]
0x180042bdd  jmp     short loc_180042BE2
0x180042bdf  mov     rcx, rbx; lpFileName
0x180042be2  call    cs:__imp_DeleteFileW
0x180042be8  test    eax, eax
0x180042bea  jnz     short loc_180042C2C
0x180042bec  mov     eax, cs:dword_18005A000
0x180042bf2  cmp     eax, 2
0x180042bf5  jbe     short loc_180042C2C
0x180042bf7  cmp     qword ptr [rbx+18h], 8
0x180042bfc  jb      short loc_180042C03
0x180042bfe  mov     rax, [rbx]
0x180042c01  jmp     short loc_180042C06
0x180042c03  mov     rax, rbx
0x180042c06  mov     [rsp+38h+arg_0], rax
0x180042c0b  lea     rax, [rsp+38h+arg_0]
0x180042c10  mov     [rsp+38h+var_18], rax
0x180042c15  xor     r8d, r8d
0x180042c18  lea     rdx, byte_180050A4D
0x180042c1f  lea     rcx, dword_18005A000
0x180042c26  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180042c2b  nop
0x180042c2c  mov     rcx, [rdi+30h]
0x180042c30  test    rcx, rcx
0x180042c33  jz      short loc_180042C4A
0x180042c35  mov     qword ptr [rdi+30h], 0
0x180042c3d  mov     rax, [rcx]
0x180042c40  mov     rax, [rax+10h]
0x180042c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c49  nop
0x180042c4a  cmp     qword ptr [rbx+18h], 8
0x180042c4f  jb      short loc_180042C5A
0x180042c51  mov     rcx, [rbx]
0x180042c54  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180042c5a  mov     qword ptr [rbx+18h], 7
0x180042c62  mov     qword ptr [rbx+10h], 0
0x180042c6a  xor     eax, eax
0x180042c6c  mov     [rbx], ax
0x180042c6f  mov     dword ptr [rdi+0Ch], 0C0000001h
0x180042c76  mov     rbx, [rsp+38h+arg_8]
0x180042c7b  add     rsp, 30h
0x180042c7f  pop     rdi
0x180042c80  retn
```
