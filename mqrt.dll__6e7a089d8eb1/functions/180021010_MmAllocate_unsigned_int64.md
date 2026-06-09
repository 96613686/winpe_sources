# MmAllocate(unsigned __int64)

- ea: `0x180021010`
- end: `0x180021059`
- name: `?MmAllocate@@YAPEAX_K@Z`
- size: `73`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `58`
- callee_count: `4`
- tags: ``

## callers

- `0x180008480`
- `0x180008550`
- `0x1800091bc`
- `0x1800094b4`
- `0x180009874`
- `0x180009b20`
- `0x18000a120`
- `0x18000c764`
- `0x18000d164`
- `0x18000fcf0`
- `0x180011c14`
- `0x1800120b0`
- `0x180012ed4`
- `0x1800138d4`
- `0x180013e88`
- `0x1800141a8`
- `0x180014388`
- `0x180014870`
- `0x180016348`
- `0x1800163ec`
- `0x1800164a8`
- `0x180016500`
- `0x1800165d0`
- `0x1800166dc`
- `0x180016944`
- `0x180017728`
- `0x180017a6c`
- `0x180017edc`
- `0x180018220`
- `0x180018800`
- `0x180018bd8`
- `0x180018f4c`
- `0x180019450`
- `0x180019a84`
- `0x18001a1b8`
- `0x18001b088`
- `0x18001b290`
- `0x18001c188`
- `0x18001d684`
- `0x18001e988`
- `0x18001ef18`
- `0x18001f104`
- `0x18001f460`
- `0x18001f568`
- `0x180020130`
- `0x180020488`
- `0x180020550`
- `0x180020610`
- `0x18002067c`
- `0x180020fe0`

## callees

- `0x180020fec`
- `0x180021010`
- `0x180021078`
- `0x1800210b0`

## pseudocode

```c
void *__fastcall MmAllocate(unsigned __int64 a1, const char *a2, int a3)
{
  void *result; // rax
  __int64 v5; // r8

  result = Allocate(a1, a2, a3);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v5, a1);
    MmThrowBadAlloc();
  }
  return result;
}

```

## disassembly

```asm
0x180021010  push    rbx
0x180021012  sub     rsp, 20h
0x180021016  mov     rbx, rcx
0x180021019  call    ?Allocate@@YAPEAX_KPEBDH@Z; Allocate(unsigned __int64,char const *,int)
0x18002101e  test    rax, rax
0x180021021  jnz     short loc_180021053
0x180021023  mov     rcx, cs:WPP_GLOBAL_Control
0x18002102a  lea     rax, WPP_GLOBAL_Control
0x180021031  cmp     rcx, rax
0x180021034  jz      short loc_18002104D
0x180021036  test    byte ptr [rcx+1Ch], 1
0x18002103a  jz      short loc_18002104D
0x18002103c  mov     rcx, [rcx+10h]
0x180021040  mov     edx, 0Bh
0x180021045  mov     r9, rbx
0x180021048  call    WPP_SF_P
0x18002104d  call    ?MmThrowBadAlloc@@YAXXZ; MmThrowBadAlloc(void)
0x180021053  add     rsp, 20h
0x180021057  pop     rbx
0x180021058  retn
```
