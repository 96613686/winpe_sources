# NcaApiSrvImplIsEngineValid(NCA_INTSERVER_ENGINE_HANDLE_ *)

- ea: `0x180007088`
- end: `0x180007110`
- name: `?NcaApiSrvImplIsEngineValid@@YAKPEAUNCA_INTSERVER_ENGINE_HANDLE_@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(struct NCA_INTSERVER_ENGINE_HANDLE_ *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180007560`
- `0x180007954`
- `0x180007b58`
- `0x180007f10`
- `0x18000833c`
- `0x180008be4`

## callees

- `0x180004f34`
- `0x180007088`

## pseudocode

```c
__int64 __fastcall NcaApiSrvImplIsEngineValid(struct NCA_INTSERVER_ENGINE_HANDLE_ *a1)
{
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  struct NCA_INTSERVER_ENGINE_HANDLE_ *v4; // rax

  if ( a1 )
  {
    v4 = (struct NCA_INTSERVER_ENGINE_HANDLE_ *)qword_180028C80;
    v1 = 0;
    while ( v4 != (struct NCA_INTSERVER_ENGINE_HANDLE_ *)&qword_180028C80 )
    {
      if ( a1 == v4 )
        return v1;
      v4 = *(struct NCA_INTSERVER_ENGINE_HANDLE_ **)v4;
    }
    v1 = 6;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 23;
      goto LABEL_12;
    }
  }
  else
  {
    v1 = 87;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v3 = 22;
LABEL_12:
      WPP_SF_d(v2[2], v3, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids, v1);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180007088  push    rbx
0x18000708a  sub     rsp, 20h
0x18000708e  test    rcx, rcx
0x180007091  jnz     short loc_1800070B4
0x180007093  lea     ebx, [rcx+57h]
0x180007096  mov     rcx, cs:WPP_GLOBAL_Control
0x18000709d  lea     rax, WPP_GLOBAL_Control
0x1800070a4  cmp     rcx, rax
0x1800070a7  jz      short loc_180007107
0x1800070a9  test    byte ptr [rcx+1Ch], 1
0x1800070ad  jz      short loc_180007107
0x1800070af  lea     edx, [rbx-41h]
0x1800070b2  jmp     short loc_1800070F4
0x1800070b4  mov     rax, cs:qword_180028C80
0x1800070bb  xor     ebx, ebx
0x1800070bd  lea     rdx, qword_180028C80
0x1800070c4  cmp     rax, rdx
0x1800070c7  jz      short loc_1800070D3
0x1800070c9  cmp     rcx, rax
0x1800070cc  jz      short loc_180007107
0x1800070ce  mov     rax, [rax]
0x1800070d1  jmp     short loc_1800070BD
0x1800070d3  mov     ebx, 6
0x1800070d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070df  lea     rax, WPP_GLOBAL_Control
0x1800070e6  cmp     rcx, rax
0x1800070e9  jz      short loc_180007107
0x1800070eb  test    byte ptr [rcx+1Ch], 1
0x1800070ef  jz      short loc_180007107
0x1800070f1  lea     edx, [rbx+11h]
0x1800070f4  mov     rcx, [rcx+10h]
0x1800070f8  lea     r8, WPP_155de82f2b7a38d65fdac8bb2f3716fe_Traceguids
0x1800070ff  mov     r9d, ebx
0x180007102  call    WPP_SF_d
0x180007107  mov     eax, ebx
0x180007109  add     rsp, 20h
0x18000710d  pop     rbx
0x18000710e  retn
```
