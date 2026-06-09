# BookKeeping::FindAllSnapinUIThreads(ulong * *,ulong *)

- ea: `0x18000d5f0`
- end: `0x18000d68f`
- name: `?FindAllSnapinUIThreads@BookKeeping@@SAJPEAPEAKPEAK@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned int **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f90`
- `0x180008630`
- `0x18000d5f0`
- `0x18000f43c`

## pseudocode

```c
__int64 __fastcall BookKeeping::FindAllSnapinUIThreads(unsigned int **a1, unsigned int *a2)
{
  int inited; // ebx
  __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // rdx

  inited = BookKeeping::InitInstance();
  if ( inited >= 0 )
  {
    inited = CSnapinThreadTable::FindThreads((__int64)BookKeeping::s_pSnapinThreadTable, 0, v5, a1, a2);
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v7 = 46;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v7 = 45;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids, (unsigned int)inited);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000d5f0  mov     [rsp+arg_0], rbx
0x18000d5f5  mov     [rsp+arg_8], rsi
0x18000d5fa  push    rdi
0x18000d5fb  sub     rsp, 30h
0x18000d5ff  mov     rdi, rdx
0x18000d602  mov     rsi, rcx
0x18000d605  call    ?InitInstance@BookKeeping@@SAJXZ; BookKeeping::InitInstance(void)
0x18000d60a  mov     ebx, eax
0x18000d60c  test    eax, eax
0x18000d60e  jns     short loc_18000D630
0x18000d610  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d617  lea     rax, WPP_GLOBAL_Control
0x18000d61e  cmp     rcx, rax
0x18000d621  jz      short loc_18000D67D
0x18000d623  cmp     byte ptr [rcx+19h], 2
0x18000d627  jb      short loc_18000D67D
0x18000d629  mov     edx, 2Dh ; '-'
0x18000d62e  jmp     short loc_18000D66A
0x18000d630  mov     rcx, cs:?s_pSnapinThreadTable@BookKeeping@@0PEAVCSnapinThreadTable@@EA; CSnapinThreadTable * BookKeeping::s_pSnapinThreadTable
0x18000d637  mov     r9, rsi
0x18000d63a  xor     edx, edx
0x18000d63c  mov     [rsp+38h+var_18], rdi
0x18000d641  call    ?FindThreads@CSnapinThreadTable@@AEAAJHW4SnapinThreadFlags@BookKeeping@@PEAPEAKPEAK@Z; CSnapinThreadTable::FindThreads(int,BookKeeping::SnapinThreadFlags,ulong * *,ulong *)
0x18000d646  mov     ebx, eax
0x18000d648  test    eax, eax
0x18000d64a  jns     short loc_18000D67D
0x18000d64c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d653  lea     rax, WPP_GLOBAL_Control
0x18000d65a  cmp     rcx, rax
0x18000d65d  jz      short loc_18000D67D
0x18000d65f  cmp     byte ptr [rcx+19h], 2
0x18000d663  jb      short loc_18000D67D
0x18000d665  mov     edx, 2Eh ; '.'
0x18000d66a  mov     rcx, [rcx+10h]
0x18000d66e  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x18000d675  mov     r9d, ebx
0x18000d678  call    WPP_SF_d
0x18000d67d  mov     rsi, [rsp+38h+arg_8]
0x18000d682  mov     eax, ebx
0x18000d684  mov     rbx, [rsp+38h+arg_0]
0x18000d689  add     rsp, 30h
0x18000d68d  pop     rdi
0x18000d68e  retn
```
