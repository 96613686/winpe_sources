# NcaTriggerRearm

- ea: `0x180003610`
- end: `0x18000370e`
- name: `NcaTriggerRearm`
- size: `254`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b7e0`
- `0x18000f5a8`
- `0x180015f20`

## callees

- `0x180003610`
- `0x180004f04`
- `0x180004f34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800036cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800036cc`

## pseudocode

```c
void __fastcall NcaTriggerRearm(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  struct _TP_WAIT *v5; // rax
  void *v6; // rdx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 == &WPP_GLOBAL_Control )
      return;
    v3 = 87;
    if ( (*((_BYTE *)v2 + 28) & 1) == 0 )
      goto LABEL_19;
    v4 = 20;
    goto LABEL_8;
  }
  v5 = *(struct _TP_WAIT **)a1;
  if ( !*(_QWORD *)a1 )
  {
    if ( v2 == &WPP_GLOBAL_Control )
      return;
    v3 = 87;
    if ( (*((_BYTE *)v2 + 28) & 1) == 0 )
      goto LABEL_19;
    v4 = 21;
    goto LABEL_8;
  }
  v6 = *(void **)(a1 + 8);
  if ( v6 )
  {
    v3 = 0;
    SetThreadpoolWait(v5, v6, 0);
    goto LABEL_18;
  }
  if ( v2 == &WPP_GLOBAL_Control )
    return;
  v3 = 87;
  if ( (*((_BYTE *)v2 + 28) & 1) != 0 )
  {
    v4 = 22;
LABEL_8:
    WPP_SF_d(v2[2], v4, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, 87);
LABEL_18:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_19:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(v2[2], 23, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v3);
}

```

## disassembly

```asm
0x180003610  mov     [rsp+arg_0], rbx
0x180003615  push    rdi
0x180003616  sub     rsp, 20h
0x18000361a  mov     rbx, rcx
0x18000361d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003624  lea     rdi, WPP_GLOBAL_Control
0x18000362b  cmp     rcx, rdi
0x18000362e  jz      short loc_180003652
0x180003630  test    byte ptr [rcx+1Ch], 8
0x180003634  jz      short loc_180003652
0x180003636  mov     rcx, [rcx+10h]
0x18000363a  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x180003641  mov     edx, 13h
0x180003646  call    WPP_SF_
0x18000364b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003652  test    rbx, rbx
0x180003655  jnz     short loc_180003685
0x180003657  cmp     rcx, rdi
0x18000365a  jz      loc_180003702
0x180003660  test    byte ptr [rcx+1Ch], 1
0x180003664  mov     ebx, 57h ; 'W'
0x180003669  jz      short loc_1800036DF
0x18000366b  mov     edx, 14h
0x180003670  mov     rcx, [rcx+10h]
0x180003674  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000367b  mov     r9d, ebx
0x18000367e  call    WPP_SF_d
0x180003683  jmp     short loc_1800036D8
0x180003685  mov     rax, [rbx]
0x180003688  test    rax, rax
0x18000368b  jnz     short loc_1800036A4
0x18000368d  cmp     rcx, rdi
0x180003690  jz      short loc_180003702
0x180003692  test    byte ptr [rcx+1Ch], 1
0x180003696  mov     ebx, 57h ; 'W'
0x18000369b  jz      short loc_1800036DF
0x18000369d  mov     edx, 15h
0x1800036a2  jmp     short loc_180003670
0x1800036a4  mov     rdx, [rbx+8]; h
0x1800036a8  test    rdx, rdx
0x1800036ab  jnz     short loc_1800036C4
0x1800036ad  cmp     rcx, rdi
0x1800036b0  jz      short loc_180003702
0x1800036b2  test    byte ptr [rcx+1Ch], 1
0x1800036b6  mov     ebx, 57h ; 'W'
0x1800036bb  jz      short loc_1800036DF
0x1800036bd  mov     edx, 16h
0x1800036c2  jmp     short loc_180003670
0x1800036c4  xor     ebx, ebx
0x1800036c6  xor     r8d, r8d; pftTimeout
0x1800036c9  mov     rcx, rax; pwa
0x1800036cc  call    cs:__imp_SetThreadpoolWait
0x1800036d3  nop     dword ptr [rax+rax+00h]
0x1800036d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036df  cmp     rcx, rdi
0x1800036e2  jz      short loc_180003702
0x1800036e4  test    byte ptr [rcx+1Ch], 8
0x1800036e8  jz      short loc_180003702
0x1800036ea  mov     rcx, [rcx+10h]
0x1800036ee  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x1800036f5  mov     edx, 17h
0x1800036fa  mov     r9d, ebx
0x1800036fd  call    WPP_SF_d
0x180003702  mov     rbx, [rsp+28h+arg_0]
0x180003707  add     rsp, 20h
0x18000370b  pop     rdi
0x18000370c  retn
```
