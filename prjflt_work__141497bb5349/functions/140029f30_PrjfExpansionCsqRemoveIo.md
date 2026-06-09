# PrjfExpansionCsqRemoveIo

- ea: `0x140029f30`
- end: `0x140029f56`
- name: `PrjfExpansionCsqRemoveIo`
- size: `38`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140029f30`

## pseudocode

```c
void __fastcall PrjfExpansionCsqRemoveIo(PFLT_CALLBACK_DATA_QUEUE Cbdq, PFLT_CALLBACK_DATA Cbd)
{
  union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *p_QueueLinks; // rdx
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *Blink; // rax

  p_QueueLinks = (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)&Cbd->QueueLinks;
  Flink = p_QueueLinks->QueueLinks.Flink;
  if ( (union _FLT_CALLBACK_DATA::$312C66EF40AEDAF2A3A5D4554FF51F28 *)p_QueueLinks->QueueLinks.Flink->Blink != p_QueueLinks
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
0x140029f30  add     rdx, 30h ; '0'
0x140029f34  mov     rcx, [rdx]
0x140029f37  cmp     [rcx+8], rdx
0x140029f3b  jnz     short loc_140029F4F
0x140029f3d  mov     rax, [rdx+8]
0x140029f41  cmp     [rax], rdx
0x140029f44  jnz     short loc_140029F4F
0x140029f46  mov     [rax], rcx
0x140029f49  mov     [rcx+8], rax
0x140029f4d  retn
0x140029f4f  mov     ecx, 3
0x140029f54  int     29h; Win8: RtlFailFast(ecx)
```
