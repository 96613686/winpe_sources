# CHtmlElement::SkipRemainingValueAndGotoNextChunk(tagSTAT_CHUNK *)

- ea: `0x180011b4c`
- end: `0x180011bc0`
- name: `?SkipRemainingValueAndGotoNextChunk@CHtmlElement@@IEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `116`
- prototype: `__int64 __fastcall(CHtmlElement *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011a90`

## callees

- `0x180011b4c`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011b9d`

## pseudocode

```c
__int64 __fastcall CHtmlElement::SkipRemainingValueAndGotoNextChunk(CHtmlElement *this, struct tagSTAT_CHUNK *a2)
{
  __int64 v2; // rax
  void *v5; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this;
  pv = 0;
  if ( (*(int (__fastcall **)(CHtmlElement *, LPVOID *))(v2 + 24))(this, &pv) >= 0 )
  {
    v5 = pv;
    if ( pv )
    {
      if ( *(_WORD *)pv == 31 )
      {
        CoTaskMemFree(*((LPVOID *)pv + 1));
        v5 = pv;
      }
      CoTaskMemFree(v5);
    }
  }
  return (*(__int64 (__fastcall **)(CHtmlElement *, struct tagSTAT_CHUNK *))(*(_QWORD *)this + 8LL))(this, a2);
}

```

## disassembly

```asm
0x180011b4c  mov     [rsp+arg_8], rbx
0x180011b51  push    rdi
0x180011b52  sub     rsp, 20h
0x180011b56  mov     rax, [rcx]
0x180011b59  mov     rdi, rdx
0x180011b5c  lea     rdx, [rsp+28h+pv]
0x180011b61  mov     [rsp+28h+pv], 0
0x180011b6a  mov     rbx, rcx
0x180011b6d  mov     rax, [rax+18h]
0x180011b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b76  test    eax, eax
0x180011b78  js      short loc_180011BA3
0x180011b7a  mov     rcx, [rsp+28h+pv]
0x180011b7f  test    rcx, rcx
0x180011b82  jz      short loc_180011BA3
0x180011b84  mov     eax, 1Fh
0x180011b89  cmp     ax, [rcx]
0x180011b8c  jnz     short loc_180011B9D
0x180011b8e  mov     rcx, [rcx+8]; pv
0x180011b92  call    cs:__imp_CoTaskMemFree
0x180011b98  mov     rcx, [rsp+28h+pv]; pv
0x180011b9d  call    cs:__imp_CoTaskMemFree
0x180011ba3  mov     rax, [rbx]
0x180011ba6  mov     rdx, rdi
0x180011ba9  mov     rcx, rbx
0x180011bac  mov     rax, [rax+8]
0x180011bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bb5  mov     rbx, [rsp+28h+arg_8]
0x180011bba  add     rsp, 20h
0x180011bbe  pop     rdi
0x180011bbf  retn
```
