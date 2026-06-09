# BookKeeping::UnregisterAllSnapinInstanceThreads(int)

- ea: `0x18000e360`
- end: `0x18000e3e2`
- name: `?UnregisterAllSnapinInstanceThreads@BookKeeping@@SAJH@Z`
- size: `130`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001f90`
- `0x180008630`
- `0x18000e360`
- `0x18000f8dc`

## pseudocode

```c
__int64 __fastcall BookKeeping::UnregisterAllSnapinInstanceThreads(int a1)
{
  CSnapinThreadTable *v2; // rcx
  int inited; // ebx
  __int64 v4; // rcx
  __int64 v5; // rdx

  inited = BookKeeping::InitInstance();
  if ( inited >= 0 )
  {
    inited = CSnapinThreadTable::UnregisterAllSnapinInstanceThreads(v2, a1);
    if ( inited < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v5 = 44;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      v5 = 43;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v4 + 16), v5, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids, (unsigned int)inited);
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000e360  mov     [rsp+arg_0], rbx
0x18000e365  push    rdi
0x18000e366  sub     rsp, 20h
0x18000e36a  mov     edi, ecx
0x18000e36c  call    ?InitInstance@BookKeeping@@SAJXZ; BookKeeping::InitInstance(void)
0x18000e371  mov     ebx, eax
0x18000e373  test    eax, eax
0x18000e375  jns     short loc_18000E397
0x18000e377  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e37e  lea     rax, WPP_GLOBAL_Control
0x18000e385  cmp     rcx, rax
0x18000e388  jz      short loc_18000E3D5
0x18000e38a  cmp     byte ptr [rcx+19h], 2
0x18000e38e  jb      short loc_18000E3D5
0x18000e390  mov     edx, 2Bh ; '+'
0x18000e395  jmp     short loc_18000E3C2
0x18000e397  mov     edx, edi; int
0x18000e399  call    ?UnregisterAllSnapinInstanceThreads@CSnapinThreadTable@@QEAAJH@Z; CSnapinThreadTable::UnregisterAllSnapinInstanceThreads(int)
0x18000e39e  mov     ebx, eax
0x18000e3a0  test    eax, eax
0x18000e3a2  jns     short loc_18000E3D5
0x18000e3a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3ab  lea     rax, WPP_GLOBAL_Control
0x18000e3b2  cmp     rcx, rax
0x18000e3b5  jz      short loc_18000E3D5
0x18000e3b7  cmp     byte ptr [rcx+19h], 2
0x18000e3bb  jb      short loc_18000E3D5
0x18000e3bd  mov     edx, 2Ch ; ','
0x18000e3c2  mov     rcx, [rcx+10h]
0x18000e3c6  lea     r8, WPP_b1fef5ebbfd2305bddc8c1215ae5a760_Traceguids
0x18000e3cd  mov     r9d, ebx
0x18000e3d0  call    WPP_SF_d
0x18000e3d5  mov     eax, ebx
0x18000e3d7  mov     rbx, [rsp+28h+arg_0]
0x18000e3dc  add     rsp, 20h
0x18000e3e0  pop     rdi
0x18000e3e1  retn
```
