# PmDeinit(void)

- ea: `0x18000c608`
- end: `0x18000c6e3`
- name: `?PmDeinit@@YAKXZ`
- size: `219`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b9fc`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000c608`
- `0x18000dc98`
- `0x18003386c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c69b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c69b`

## pseudocode

```c
__int64 PmDeinit(void)
{
  struct _PM_PCB_LIST *v0; // rcx
  struct _PM_PCB_LIST **v1; // rbx

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 39, WPP_935883eb83d333df730e157613565e66_Traceguids);
  }
  PmpFreePcbList((struct _PM_PCB_LIST *)Mem, 0);
  PmpFreePcbList((struct _PM_PCB_LIST *)qword_180052DA0, 0);
  v0 = qword_180052DD8;
  if ( qword_180052DD8 != (struct _PM_PCB_LIST *)&qword_180052DD8 )
  {
    do
    {
      v1 = *(struct _PM_PCB_LIST ***)v0;
      PmpFreePcbList(v0, 1);
      v0 = (struct _PM_PCB_LIST *)v1;
    }
    while ( v1 != &qword_180052DD8 );
  }
  LpReleaseProfileSchemaCollection();
  DeleteCriticalSection(&stru_180052D40);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 40, WPP_935883eb83d333df730e157613565e66_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c608  mov     [rsp+arg_0], rbx
0x18000c60d  mov     [rsp+arg_8], rsi
0x18000c612  push    rdi
0x18000c613  sub     rsp, 20h
0x18000c617  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c61e  lea     rdi, WPP_GLOBAL_Control
0x18000c625  cmp     rcx, rdi
0x18000c628  jz      short loc_18000C64B
0x18000c62a  cmp     byte ptr [rcx+19h], 4
0x18000c62e  jb      short loc_18000C64B
0x18000c630  test    byte ptr [rcx+1Ch], 1
0x18000c634  jz      short loc_18000C64B
0x18000c636  mov     rcx, [rcx+10h]
0x18000c63a  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000c641  mov     edx, 27h ; '''
0x18000c646  call    WPP_SF_
0x18000c64b  xor     edx, edx; int
0x18000c64d  lea     rcx, Mem; lpMem
0x18000c654  call    ?PmpFreePcbList@@YAXPEAU_PM_PCB_LIST@@H@Z; PmpFreePcbList(_PM_PCB_LIST *,int)
0x18000c659  xor     edx, edx; int
0x18000c65b  lea     rcx, qword_180052DA0; lpMem
0x18000c662  call    ?PmpFreePcbList@@YAXPEAU_PM_PCB_LIST@@H@Z; PmpFreePcbList(_PM_PCB_LIST *,int)
0x18000c667  mov     rcx, cs:qword_180052DD8; lpMem
0x18000c66e  lea     rsi, qword_180052DD8
0x18000c675  cmp     rcx, rsi
0x18000c678  jz      short loc_18000C68F
0x18000c67a  mov     rbx, [rcx]
0x18000c67d  mov     edx, 1; int
0x18000c682  call    ?PmpFreePcbList@@YAXPEAU_PM_PCB_LIST@@H@Z; PmpFreePcbList(_PM_PCB_LIST *,int)
0x18000c687  mov     rcx, rbx
0x18000c68a  cmp     rbx, rsi
0x18000c68d  jnz     short loc_18000C67A
0x18000c68f  call    LpReleaseProfileSchemaCollection
0x18000c694  lea     rcx, stru_180052D40; lpCriticalSection
0x18000c69b  call    cs:__imp_DeleteCriticalSection
0x18000c6a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6a8  cmp     rcx, rdi
0x18000c6ab  jz      short loc_18000C6D1
0x18000c6ad  cmp     byte ptr [rcx+19h], 4
0x18000c6b1  jb      short loc_18000C6D1
0x18000c6b3  test    byte ptr [rcx+1Ch], 1
0x18000c6b7  jz      short loc_18000C6D1
0x18000c6b9  mov     rcx, [rcx+10h]
0x18000c6bd  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000c6c4  mov     edx, 28h ; '('
0x18000c6c9  xor     r9d, r9d
0x18000c6cc  call    WPP_SF_d
0x18000c6d1  mov     rbx, [rsp+28h+arg_0]
0x18000c6d6  xor     eax, eax
0x18000c6d8  mov     rsi, [rsp+28h+arg_8]
0x18000c6dd  add     rsp, 20h
0x18000c6e1  pop     rdi
0x18000c6e2  retn
```
