# NptrigWaitNamedPipeQueueRemove

- ea: `0x140009ec0`
- end: `0x140009ee7`
- name: `NptrigWaitNamedPipeQueueRemove`
- size: `39`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140009ec0`

## pseudocode

```c
void __fastcall NptrigWaitNamedPipeQueueRemove(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  struct _LIST_ENTRY *Flink; // rcx
  union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *p_QueueLinks; // rdx
  struct _LIST_ENTRY *Blink; // rax

  Flink = Cbd->QueueLinks.Flink;
  p_QueueLinks = (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)&Cbd->QueueLinks;
  if ( (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)Flink->Blink != p_QueueLinks
    || (Blink = p_QueueLinks->QueueLinks.Blink,
        (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)Blink->Flink != p_QueueLinks) )
  {
    __fastfail(3u);
  }
  Blink->Flink = Flink;
  Flink->Blink = Blink;
}

```

## disassembly

```asm
0x140009ec0  mov     rcx, [rdx+30h]
0x140009ec4  add     rdx, 30h ; '0'
0x140009ec8  cmp     [rcx+8], rdx
0x140009ecc  jnz     short loc_140009EE0
0x140009ece  mov     rax, [rdx+8]
0x140009ed2  cmp     [rax], rdx
0x140009ed5  jnz     short loc_140009EE0
0x140009ed7  mov     [rax], rcx
0x140009eda  mov     [rcx+8], rax
0x140009ede  retn
0x140009ee0  mov     ecx, 3
0x140009ee5  int     29h; Win8: RtlFailFast(ecx)
```
