# BookKeeping::RegisterThread(int,int,ulong,BookKeeping::SnapinThreadFlags)

- ea: `0x18000dd40`
- end: `0x18000ddd7`
- name: `?RegisterThread@BookKeeping@@SAJHHKW4SnapinThreadFlags@1@@Z`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f90`
- `0x180008630`
- `0x18000dd40`
- `0x18000f6d8`

## pseudocode

```c
__int64 __fastcall BookKeeping::RegisterThread(int a1, int a2, unsigned int a3, int a4)
{
  __int64 v8; // rcx
  int inited; // ebx
  __int64 v10; // rcx
  __int64 v11; // rdx

  inited = BookKeeping::InitInstance();
  if ( inited >= 0 )
  {
    inited = CSnapinThreadTable::RegisterThread(v8, a1, a2, a3, a4);
    if ( inited < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v11 = 40;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v11 = 39;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids, (unsigned int)inited);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000dd40  push    rbx
0x18000dd42  push    rbp
0x18000dd43  push    rsi
0x18000dd44  push    rdi
0x18000dd45  push    r14
0x18000dd47  sub     rsp, 30h
0x18000dd4b  mov     edi, r9d
0x18000dd4e  mov     esi, r8d
0x18000dd51  mov     ebp, edx
0x18000dd53  mov     r14d, ecx
0x18000dd56  call    ?InitInstance@BookKeeping@@SAJXZ; BookKeeping::InitInstance(void)
0x18000dd5b  mov     ebx, eax
0x18000dd5d  test    eax, eax
0x18000dd5f  jns     short loc_18000DD81
0x18000dd61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd68  lea     rax, WPP_GLOBAL_Control
0x18000dd6f  cmp     rcx, rax
0x18000dd72  jz      short loc_18000DDCA
0x18000dd74  cmp     byte ptr [rcx+19h], 2
0x18000dd78  jb      short loc_18000DDCA
0x18000dd7a  mov     edx, 27h ; '''
0x18000dd7f  jmp     short loc_18000DDB7
0x18000dd81  mov     r9d, esi
0x18000dd84  mov     [rsp+58h+var_38], edi
0x18000dd88  mov     r8d, ebp
0x18000dd8b  mov     edx, r14d
0x18000dd8e  call    ?RegisterThread@CSnapinThreadTable@@QEAAJHHKW4SnapinThreadFlags@BookKeeping@@@Z; CSnapinThreadTable::RegisterThread(int,int,ulong,BookKeeping::SnapinThreadFlags)
0x18000dd93  mov     ebx, eax
0x18000dd95  test    eax, eax
0x18000dd97  jns     short loc_18000DDCA
0x18000dd99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dda0  lea     rax, WPP_GLOBAL_Control
0x18000dda7  cmp     rcx, rax
0x18000ddaa  jz      short loc_18000DDCA
0x18000ddac  cmp     byte ptr [rcx+19h], 2
0x18000ddb0  jb      short loc_18000DDCA
0x18000ddb2  mov     edx, 28h ; '('
0x18000ddb7  mov     rcx, [rcx+10h]
0x18000ddbb  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x18000ddc2  mov     r9d, ebx
0x18000ddc5  call    WPP_SF_d
0x18000ddca  mov     eax, ebx
0x18000ddcc  add     rsp, 30h
0x18000ddd0  pop     r14
0x18000ddd2  pop     rdi
0x18000ddd3  pop     rsi
0x18000ddd4  pop     rbp
0x18000ddd5  pop     rbx
0x18000ddd6  retn
```
