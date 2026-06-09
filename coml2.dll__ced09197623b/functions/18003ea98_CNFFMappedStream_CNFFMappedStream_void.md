# CNFFMappedStream::~CNFFMappedStream(void)

- ea: `0x18003ea98`
- end: `0x18003eaea`
- name: `??1CNFFMappedStream@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(CNFFMappedStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003b4d4`

## callees

- `0x18003ea98`
- `0x180059b70`
- `0x18005a150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ead1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ead1`

## pseudocode

```c
void __fastcall CNFFMappedStream::~CNFFMappedStream(CNFFMappedStream *this)
{
  bool v1; // zf

  v1 = *((_QWORD *)this + 7) == 0;
  *(_QWORD *)this = &CNFFMappedStream::`vftable';
  if ( !v1 )
  {
    CNFFMappedStream::ReplaceOriginalWithUpdate(this, 2, 1);
    RELEASE_INTERFACE<CNtfsUpdateStreamForPropStg>((char *)this + 56);
  }
  CoTaskMemFree(*((LPVOID *)this + 3));
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18003ea98  mov     [rsp+arg_0], rbx
0x18003ea9d  push    rdi
0x18003ea9e  sub     rsp, 20h
0x18003eaa2  cmp     qword ptr [rcx+38h], 0
0x18003eaa7  lea     rax, ??_7CNFFMappedStream@@6B@; const CNFFMappedStream::`vftable'
0x18003eaae  mov     [rcx], rax
0x18003eab1  mov     rbx, rcx
0x18003eab4  jz      short loc_18003EACD
0x18003eab6  mov     edx, 2
0x18003eabb  lea     r8d, [rdx-1]
0x18003eabf  call    ?ReplaceOriginalWithUpdate@CNFFMappedStream@@AEAAJW4enumCREATE_NEW_UPDATE_STREAM@1@H@Z; CNFFMappedStream::ReplaceOriginalWithUpdate(CNFFMappedStream::enumCREATE_NEW_UPDATE_STREAM,int)
0x18003eac4  lea     rcx, [rbx+38h]
0x18003eac8  call    ??$RELEASE_INTERFACE@VCNtfsUpdateStreamForPropStg@@@@YAKAEAPEAVCNtfsUpdateStreamForPropStg@@@Z; RELEASE_INTERFACE<CNtfsUpdateStreamForPropStg>(CNtfsUpdateStreamForPropStg * &)
0x18003eacd  mov     rcx, [rbx+18h]; pv
0x18003ead1  call    cs:__imp_CoTaskMemFree
0x18003ead7  mov     qword ptr [rbx+18h], 0
0x18003eadf  mov     rbx, [rsp+28h+arg_0]
0x18003eae4  add     rsp, 20h
0x18003eae8  pop     rdi
0x18003eae9  retn
```
