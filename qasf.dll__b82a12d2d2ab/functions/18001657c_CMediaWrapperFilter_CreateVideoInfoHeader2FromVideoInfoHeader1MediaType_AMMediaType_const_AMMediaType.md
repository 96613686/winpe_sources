# CMediaWrapperFilter::CreateVideoInfoHeader2FromVideoInfoHeader1MediaType(_AMMediaType const *,_AMMediaType * *)

- ea: `0x18001657c`
- end: `0x1800165e2`
- name: `?CreateVideoInfoHeader2FromVideoInfoHeader1MediaType@CMediaWrapperFilter@@KAJPEBU_AMMediaType@@PEAPEAU2@@Z`
- size: `102`
- prototype: `__int64 __fastcall(const struct _AMMediaType *, struct _AMMediaType **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016020`

## callees

- `0x180007194`
- `0x1800071e8`
- `0x180007300`
- `0x18001657c`
- `0x18001be68`

## pseudocode

```c
__int64 __fastcall CMediaWrapperFilter::CreateVideoInfoHeader2FromVideoInfoHeader1MediaType(
        const struct _AMMediaType *a1,
        struct _AMMediaType **a2)
{
  int v4; // ebx
  struct _AMMediaType *MediaType; // rax
  struct _AMMediaType *v6; // rdi

  v4 = CheckVideoInfoType((__int64)a1);
  if ( v4 < 0 )
    return (unsigned int)v4;
  MediaType = CreateMediaType(a1);
  v6 = MediaType;
  if ( !MediaType )
    return (unsigned int)-2147024882;
  v4 = ConvertVideoInfoToVideoInfo2((__int64)MediaType);
  if ( v4 < 0 )
  {
    DeleteMediaType(v6);
    return (unsigned int)v4;
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x18001657c  mov     [rsp+arg_0], rbx
0x180016581  mov     [rsp+arg_8], rsi
0x180016586  push    rdi
0x180016587  sub     rsp, 20h
0x18001658b  mov     rsi, rdx
0x18001658e  mov     rdi, rcx
0x180016591  call    CheckVideoInfoType
0x180016596  mov     ebx, eax
0x180016598  test    eax, eax
0x18001659a  js      short loc_1800165B1
0x18001659c  mov     rcx, rdi; struct _AMMediaType *
0x18001659f  call    ?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z; CreateMediaType(_AMMediaType const *)
0x1800165a4  mov     rdi, rax
0x1800165a7  test    rax, rax
0x1800165aa  jnz     short loc_1800165C3
0x1800165ac  mov     ebx, 8007000Eh
0x1800165b1  mov     eax, ebx
0x1800165b3  mov     rbx, [rsp+28h+arg_0]
0x1800165b8  mov     rsi, [rsp+28h+arg_8]
0x1800165bd  add     rsp, 20h
0x1800165c1  pop     rdi
0x1800165c2  retn
0x1800165c3  mov     rcx, rdi
0x1800165c6  call    ConvertVideoInfoToVideoInfo2
0x1800165cb  mov     ebx, eax
0x1800165cd  test    eax, eax
0x1800165cf  jns     short loc_1800165DB
0x1800165d1  mov     rcx, rdi; pv
0x1800165d4  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800165d9  jmp     short loc_1800165B1
0x1800165db  mov     [rsi], rdi
0x1800165de  xor     eax, eax
0x1800165e0  jmp     short loc_1800165B3
```
