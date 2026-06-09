# BookKeeping::UnregisterThread(int,ulong)

- ea: `0x18000e3f0`
- end: `0x18000e481`
- name: `?UnregisterThread@BookKeeping@@SAJHK@Z`
- size: `145`
- prototype: `__int64 __fastcall(int, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f90`
- `0x180008630`
- `0x18000e3f0`
- `0x18000f9d8`

## pseudocode

```c
__int64 __fastcall BookKeeping::UnregisterThread(int a1, unsigned int a2)
{
  CSnapinThreadTable *v4; // rcx
  int inited; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx

  inited = BookKeeping::InitInstance();
  if ( inited >= 0 )
  {
    inited = CSnapinThreadTable::UnregisterThread(v4, a1, a2);
    if ( inited < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v7 = 42;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v7 = 41;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids, (unsigned int)inited);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000e3f0  mov     [rsp+arg_0], rbx
0x18000e3f5  mov     [rsp+arg_8], rsi
0x18000e3fa  push    rdi
0x18000e3fb  sub     rsp, 20h
0x18000e3ff  mov     edi, edx
0x18000e401  mov     esi, ecx
0x18000e403  call    ?InitInstance@BookKeeping@@SAJXZ; BookKeeping::InitInstance(void)
0x18000e408  mov     ebx, eax
0x18000e40a  test    eax, eax
0x18000e40c  jns     short loc_18000E42E
0x18000e40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e415  lea     rax, WPP_GLOBAL_Control
0x18000e41c  cmp     rcx, rax
0x18000e41f  jz      short loc_18000E46F
0x18000e421  cmp     byte ptr [rcx+19h], 2
0x18000e425  jb      short loc_18000E46F
0x18000e427  mov     edx, 29h ; ')'
0x18000e42c  jmp     short loc_18000E45C
0x18000e42e  mov     r8d, edi; unsigned int
0x18000e431  mov     edx, esi; int
0x18000e433  call    ?UnregisterThread@CSnapinThreadTable@@QEAAJHK@Z; CSnapinThreadTable::UnregisterThread(int,ulong)
0x18000e438  mov     ebx, eax
0x18000e43a  test    eax, eax
0x18000e43c  jns     short loc_18000E46F
0x18000e43e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e445  lea     rax, WPP_GLOBAL_Control
0x18000e44c  cmp     rcx, rax
0x18000e44f  jz      short loc_18000E46F
0x18000e451  cmp     byte ptr [rcx+19h], 2
0x18000e455  jb      short loc_18000E46F
0x18000e457  mov     edx, 2Ah ; '*'
0x18000e45c  mov     rcx, [rcx+10h]
0x18000e460  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x18000e467  mov     r9d, ebx
0x18000e46a  call    WPP_SF_d
0x18000e46f  mov     rsi, [rsp+28h+arg_8]
0x18000e474  mov     eax, ebx
0x18000e476  mov     rbx, [rsp+28h+arg_0]
0x18000e47b  add     rsp, 20h
0x18000e47f  pop     rdi
0x18000e480  retn
```
