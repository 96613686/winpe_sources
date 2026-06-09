# AllocProperties(void)

- ea: `0x1800221a4`
- end: `0x1800221ec`
- name: `?AllocProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@XZ`
- size: `72`
- prototype: `struct _EVENT_TRACE_PROPERTIES *(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800223b0`
- `0x180022430`
- `0x180022540`

## callees

- `0x1800221a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800221ad`

## pseudocode

```c
struct _EVENT_TRACE_PROPERTIES *AllocProperties(void)
{
  struct _EVENT_TRACE_PROPERTIES *result; // rax
  __int64 v1; // rdx
  struct _EVENT_TRACE_PROPERTIES *v2; // rcx

  result = (struct _EVENT_TRACE_PROPERTIES *)CoTaskMemAlloc(0x488u);
  if ( result )
  {
    v1 = 1160;
    v2 = result;
    do
    {
      LOBYTE(v2->Wnode.BufferSize) = 0;
      v2 = (struct _EVENT_TRACE_PROPERTIES *)((char *)v2 + 1);
      --v1;
    }
    while ( v1 );
    result->LoggerNameOffset = 120;
    result->LogFileNameOffset = 640;
    result->Wnode.BufferSize = 1160;
    result->Wnode.Flags = 0x20000;
  }
  return result;
}

```

## disassembly

```asm
0x1800221a4  sub     rsp, 28h
0x1800221a8  mov     ecx, 488h; cb
0x1800221ad  call    cs:__imp_CoTaskMemAlloc
0x1800221b3  test    rax, rax
0x1800221b6  jz      short loc_1800221E7
0x1800221b8  mov     edx, 488h
0x1800221bd  mov     rcx, rax
0x1800221c0  mov     byte ptr [rcx], 0
0x1800221c3  inc     rcx
0x1800221c6  sub     rdx, 1
0x1800221ca  jnz     short loc_1800221C0
0x1800221cc  mov     dword ptr [rax+74h], 78h ; 'x'
0x1800221d3  mov     dword ptr [rax+70h], 280h
0x1800221da  mov     dword ptr [rax], 488h
0x1800221e0  mov     dword ptr [rax+2Ch], 20000h
0x1800221e7  add     rsp, 28h
0x1800221eb  retn
```
