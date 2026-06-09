# HelperAttributeList::GetAttribute(ushort const *,tagHELPER_ATTRIBUTE * *)

- ea: `0x18001a668`
- end: `0x18001a6ff`
- name: `?GetAttribute@HelperAttributeList@@QEAAJPEBGPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(HelperAttributeList *__hidden this, const unsigned __int16 *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x180009f54`
- `0x18001a668`
- `0x18001a83c`
- `0x18002c802`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a6a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a6a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a6e7`

## pseudocode

```c
__int64 __fastcall HelperAttributeList::GetAttribute(
        HelperAttributeList *this,
        const unsigned __int16 *a2,
        struct tagHELPER_ATTRIBUTE **a3)
{
  int Item; // edi
  struct tagHELPER_ATTRIBUTE *v5; // rax
  struct tagHELPER_ATTRIBUTE *v6; // rbx
  const struct tagHELPER_ATTRIBUTE **v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  Item = HelperAttributeList::GetItem(
           this,
           L"NDFSQMCallerApplication",
           (struct HelperAttributeList::HelperAttributeListItem **)&v8,
           0);
  if ( Item >= 0 )
  {
    v5 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
    v6 = v5;
    if ( v5 )
    {
      memset_0(v5, 0, sizeof(struct tagHELPER_ATTRIBUTE));
      Item = CopyHelperAttribute(v6, *v8);
      if ( Item < 0 )
        CoTaskMemFree(v6);
      else
        *a3 = v6;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x18001a668  mov     rax, rsp
0x18001a66b  mov     [rax+8], rbx
0x18001a66f  mov     [rax+18h], rsi
0x18001a673  mov     [rax+10h], rdx
0x18001a677  push    rdi
0x18001a678  sub     rsp, 20h
0x18001a67c  mov     rsi, r8
0x18001a67f  mov     qword ptr [rax+10h], 0
0x18001a687  lea     r8, [rax+10h]; struct HelperAttributeList::HelperAttributeListItem **
0x18001a68b  xor     r9d, r9d; struct HelperAttributeList::HelperAttributeListItem **
0x18001a68e  lea     rdx, aNdfsqmcallerap; "NDFSQMCallerApplication"
0x18001a695  call    ?GetItem@HelperAttributeList@@AEAAJPEBGPEAPEAUHelperAttributeListItem@1@1@Z; HelperAttributeList::GetItem(ushort const *,HelperAttributeList::HelperAttributeListItem * *,HelperAttributeList::HelperAttributeListItem * *)
0x18001a69a  mov     edi, eax
0x18001a69c  test    eax, eax
0x18001a69e  js      short loc_18001A6ED
0x18001a6a0  mov     edi, 90h
0x18001a6a5  mov     ecx, edi; cb
0x18001a6a7  call    cs:__imp_CoTaskMemAlloc
0x18001a6ad  mov     rbx, rax
0x18001a6b0  test    rax, rax
0x18001a6b3  jnz     short loc_18001A6BC
0x18001a6b5  mov     edi, 8007000Eh
0x18001a6ba  jmp     short loc_18001A6ED
0x18001a6bc  mov     r8, rdi; Size
0x18001a6bf  xor     edx, edx; Val
0x18001a6c1  mov     rcx, rbx; void *
0x18001a6c4  call    memset_0
0x18001a6c9  mov     rdx, [rsp+28h+arg_8]
0x18001a6ce  mov     rcx, rbx; struct tagHELPER_ATTRIBUTE *
0x18001a6d1  mov     rdx, [rdx]; struct tagHELPER_ATTRIBUTE *
0x18001a6d4  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x18001a6d9  mov     edi, eax
0x18001a6db  test    eax, eax
0x18001a6dd  js      short loc_18001A6E4
0x18001a6df  mov     [rsi], rbx
0x18001a6e2  jmp     short loc_18001A6ED
0x18001a6e4  mov     rcx, rbx; pv
0x18001a6e7  call    cs:__imp_CoTaskMemFree
0x18001a6ed  mov     rbx, [rsp+28h+arg_0]
0x18001a6f2  mov     eax, edi
0x18001a6f4  mov     rsi, [rsp+28h+arg_10]
0x18001a6f9  add     rsp, 20h
0x18001a6fd  pop     rdi
0x18001a6fe  retn
```
