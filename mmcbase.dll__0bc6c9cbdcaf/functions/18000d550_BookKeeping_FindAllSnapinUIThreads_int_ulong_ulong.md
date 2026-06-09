# BookKeeping::FindAllSnapinUIThreads(int,ulong * *,ulong *)

- ea: `0x18000d550`
- end: `0x18000d5e4`
- name: `?FindAllSnapinUIThreads@BookKeeping@@SAJHPEAPEAKPEAK@Z`
- size: `148`
- prototype: `__int64 __fastcall(int, unsigned int **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f90`
- `0x180008630`
- `0x18000d550`
- `0x18000f43c`

## pseudocode

```c
__int64 __fastcall BookKeeping::FindAllSnapinUIThreads(int a1, unsigned int **a2, unsigned int *a3)
{
  int inited; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rdx

  inited = BookKeeping::InitInstance();
  if ( inited >= 0 )
  {
    inited = CSnapinThreadTable::FindThreads((__int64)BookKeeping::s_pSnapinThreadTable, a1, v7, a2, a3);
    if ( inited < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v9 = 48;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v9 = 47;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids, (unsigned int)inited);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000d550  push    rbx
0x18000d552  push    rbp
0x18000d553  push    rsi
0x18000d554  push    rdi
0x18000d555  sub     rsp, 38h
0x18000d559  mov     rdi, r8
0x18000d55c  mov     rsi, rdx
0x18000d55f  mov     ebp, ecx
0x18000d561  call    ?InitInstance@BookKeeping@@SAJXZ; BookKeeping::InitInstance(void)
0x18000d566  mov     ebx, eax
0x18000d568  test    eax, eax
0x18000d56a  jns     short loc_18000D58C
0x18000d56c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d573  lea     rax, WPP_GLOBAL_Control
0x18000d57a  cmp     rcx, rax
0x18000d57d  jz      short loc_18000D5D9
0x18000d57f  cmp     byte ptr [rcx+19h], 2
0x18000d583  jb      short loc_18000D5D9
0x18000d585  mov     edx, 2Fh ; '/'
0x18000d58a  jmp     short loc_18000D5C6
0x18000d58c  mov     rcx, cs:?s_pSnapinThreadTable@BookKeeping@@0PEAVCSnapinThreadTable@@EA; CSnapinThreadTable * BookKeeping::s_pSnapinThreadTable
0x18000d593  mov     r9, rsi
0x18000d596  mov     edx, ebp
0x18000d598  mov     [rsp+58h+var_38], rdi
0x18000d59d  call    ?FindThreads@CSnapinThreadTable@@AEAAJHW4SnapinThreadFlags@BookKeeping@@PEAPEAKPEAK@Z; CSnapinThreadTable::FindThreads(int,BookKeeping::SnapinThreadFlags,ulong * *,ulong *)
0x18000d5a2  mov     ebx, eax
0x18000d5a4  test    eax, eax
0x18000d5a6  jns     short loc_18000D5D9
0x18000d5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5af  lea     rax, WPP_GLOBAL_Control
0x18000d5b6  cmp     rcx, rax
0x18000d5b9  jz      short loc_18000D5D9
0x18000d5bb  cmp     byte ptr [rcx+19h], 2
0x18000d5bf  jb      short loc_18000D5D9
0x18000d5c1  mov     edx, 30h ; '0'
0x18000d5c6  mov     rcx, [rcx+10h]
0x18000d5ca  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x18000d5d1  mov     r9d, ebx
0x18000d5d4  call    WPP_SF_d
0x18000d5d9  mov     eax, ebx
0x18000d5db  add     rsp, 38h
0x18000d5df  pop     rdi
0x18000d5e0  pop     rsi
0x18000d5e1  pop     rbp
0x18000d5e2  pop     rbx
0x18000d5e3  retn
```
