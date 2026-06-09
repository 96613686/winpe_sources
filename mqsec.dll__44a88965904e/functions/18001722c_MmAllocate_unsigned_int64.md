# MmAllocate(unsigned __int64)

- ea: `0x18001722c`
- end: `0x180017270`
- name: `?MmAllocate@@YAPEAX_K@Z`
- size: `68`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `116`
- callee_count: `4`
- tags: ``

## callers

- `0x180001038`
- `0x180003820`
- `0x18000396c`
- `0x1800039cc`
- `0x180003a58`
- `0x180003e7c`
- `0x180003ecc`
- `0x180003f34`
- `0x180004440`
- `0x180004620`
- `0x180008c68`
- `0x18000bfe0`
- `0x18000c598`
- `0x18000c6b8`
- `0x18000cfe4`
- `0x18000d5c0`
- `0x18000d650`
- `0x18000da54`
- `0x18000e380`
- `0x18000e65c`
- `0x18000e8d4`
- `0x18000f520`
- `0x180010334`
- `0x1800104a0`
- `0x1800109cc`
- `0x180010aac`
- `0x180011218`
- `0x180011638`
- `0x1800117bc`
- `0x18001182c`
- `0x180011dfc`
- `0x180013b18`
- `0x180014350`
- `0x180014730`
- `0x180014930`
- `0x180014a10`
- `0x180014c50`
- `0x1800151d0`
- `0x180015780`
- `0x180016250`
- `0x1800162d0`
- `0x180016360`
- `0x180016470`
- `0x180016510`
- `0x1800165d0`
- `0x180016740`
- `0x1800168c0`
- `0x180016980`
- `0x180016d00`
- `0x180016ee0`

## callees

- `0x180017208`
- `0x18001722c`
- `0x180017278`
- `0x1800172b0`

## pseudocode

```c
void *__fastcall MmAllocate(unsigned __int64 a1, const char *a2, int a3)
{
  void *result; // rax
  __int64 v5; // rdx
  __int64 v6; // r8

  result = Allocate(a1, a2, a3);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, a1);
    MmThrowBadAlloc();
  }
  return result;
}

```

## disassembly

```asm
0x18001722c  push    rbx
0x18001722e  sub     rsp, 20h
0x180017232  mov     rbx, rcx
0x180017235  call    ?Allocate@@YAPEAX_KPEBDH@Z; Allocate(unsigned __int64,char const *,int)
0x18001723a  test    rax, rax
0x18001723d  jnz     short loc_18001726A
0x18001723f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017246  lea     rax, WPP_GLOBAL_Control
0x18001724d  cmp     rcx, rax
0x180017250  jz      short loc_180017264
0x180017252  test    byte ptr [rcx+1Ch], 1
0x180017256  jz      short loc_180017264
0x180017258  mov     rcx, [rcx+10h]
0x18001725c  mov     r9, rbx
0x18001725f  call    WPP_SF_P
0x180017264  call    ?MmThrowBadAlloc@@YAXXZ; MmThrowBadAlloc(void)
0x18001726a  add     rsp, 20h
0x18001726e  pop     rbx
0x18001726f  retn
```
