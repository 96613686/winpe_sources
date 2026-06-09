# GetBuffer(ulong,ulong,uchar * *,ulong *)

- ea: `0x180034570`
- end: `0x1800345b2`
- name: `?GetBuffer@@YAJKKPEAPEAEPEAK@Z`
- size: `66`
- prototype: `int(unsigned int, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009da0`
- `0x180041970`
- `0x18005bd84`
- `0x180060ef0`
- `0x18006107c`

## callees

- `0x180034570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034585`

## pseudocode

```c
__int64 __fastcall GetBuffer(unsigned int a1, unsigned int a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned __int8 *v8; // rax

  while ( 1 )
  {
    v8 = (unsigned __int8 *)CoTaskMemAlloc(a2);
    if ( v8 )
      break;
    a2 >>= 1;
    if ( a2 < a1 )
      goto LABEL_3;
  }
  *a4 = a2;
LABEL_3:
  *a3 = v8;
  return v8 == 0 ? 0x80030008 : 0;
}

```

## disassembly

```asm
0x180034570  push    rbx
0x180034572  push    rbp
0x180034573  push    rsi
0x180034574  push    rdi
0x180034575  sub     rsp, 28h
0x180034579  mov     rsi, r9
0x18003457c  mov     rdi, r8
0x18003457f  mov     ebx, edx
0x180034581  mov     ebp, ecx
0x180034583  mov     ecx, ebx; cb
0x180034585  call    cs:__imp_CoTaskMemAlloc
0x18003458b  test    rax, rax
0x18003458e  jz      short loc_1800345AA
0x180034590  mov     [rsi], ebx
0x180034592  mov     [rdi], rax
0x180034595  neg     rax
0x180034598  sbb     eax, eax
0x18003459a  not     eax
0x18003459c  and     eax, 80030008h
0x1800345a1  add     rsp, 28h
0x1800345a5  pop     rdi
0x1800345a6  pop     rsi
0x1800345a7  pop     rbp
0x1800345a8  pop     rbx
0x1800345a9  retn
0x1800345aa  shr     ebx, 1
0x1800345ac  cmp     ebx, ebp
0x1800345ae  jnb     short loc_180034583
0x1800345b0  jmp     short loc_180034592
```
