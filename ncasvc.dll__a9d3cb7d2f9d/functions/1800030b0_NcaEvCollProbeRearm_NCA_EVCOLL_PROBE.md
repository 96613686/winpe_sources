# NcaEvCollProbeRearm(NCA_EVCOLL_PROBE_ *)

- ea: `0x1800030b0`
- end: `0x1800031e2`
- name: `?NcaEvCollProbeRearm@@YAXPEAUNCA_EVCOLL_PROBE_@@@Z`
- size: `306`
- prototype: `void __fastcall(struct NCA_EVCOLL_PROBE_ *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ee0`
- `0x180011f80`

## callees

- `0x180002310`
- `0x1800030b0`
- `0x180004f04`
- `0x180004f34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800031a0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800031a0`

## pseudocode

```c
void __fastcall NcaEvCollProbeRearm(struct NCA_EVCOLL_PROBE_ *a1)
{
  __int64 v2; // rbx
  PVOID *v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  struct _TP_WAIT *v6; // rax
  void *v7; // rdx

  if ( *((_DWORD *)a1 + 54) == 1 )
  {
    NcaSrcLnkdTriggerRearm(*((_QWORD *)a1 + 23));
    NcaSrcLnkdTriggerRearm(*((_QWORD *)a1 + 24));
    NcaSrcLnkdTriggerRearm(*((_QWORD *)a1 + 25));
  }
  v2 = *((_QWORD *)a1 + 22);
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v2 )
  {
    if ( v3 == &WPP_GLOBAL_Control )
      return;
    v4 = 87;
    if ( (*((_BYTE *)v3 + 28) & 1) == 0 )
      goto LABEL_21;
    v5 = 20;
    goto LABEL_10;
  }
  v6 = *(struct _TP_WAIT **)v2;
  if ( !*(_QWORD *)v2 )
  {
    if ( v3 == &WPP_GLOBAL_Control )
      return;
    v4 = 87;
    if ( (*((_BYTE *)v3 + 28) & 1) == 0 )
      goto LABEL_21;
    v5 = 21;
    goto LABEL_10;
  }
  v7 = *(void **)(v2 + 8);
  if ( v7 )
  {
    v4 = 0;
    SetThreadpoolWait(v6, v7, 0);
    goto LABEL_20;
  }
  if ( v3 == &WPP_GLOBAL_Control )
    return;
  v4 = 87;
  if ( (*((_BYTE *)v3 + 28) & 1) != 0 )
  {
    v5 = 22;
LABEL_10:
    WPP_SF_d(v3[2], v5, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, 87);
LABEL_20:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    WPP_SF_d(v3[2], 23, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids, v4);
}

```

## disassembly

```asm
0x1800030b0  mov     [rsp+arg_0], rbx
0x1800030b5  push    rdi
0x1800030b6  sub     rsp, 20h
0x1800030ba  cmp     dword ptr [rcx+0D8h], 1
0x1800030c1  mov     rbx, rcx
0x1800030c4  jnz     short loc_1800030EA
0x1800030c6  mov     rcx, [rcx+0B8h]
0x1800030cd  call    NcaSrcLnkdTriggerRearm
0x1800030d2  mov     rcx, [rbx+0C0h]
0x1800030d9  call    NcaSrcLnkdTriggerRearm
0x1800030de  mov     rcx, [rbx+0C8h]
0x1800030e5  call    NcaSrcLnkdTriggerRearm
0x1800030ea  mov     rbx, [rbx+0B0h]
0x1800030f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030f8  lea     rdi, WPP_GLOBAL_Control
0x1800030ff  cmp     rcx, rdi
0x180003102  jz      short loc_180003126
0x180003104  test    byte ptr [rcx+1Ch], 8
0x180003108  jz      short loc_180003126
0x18000310a  mov     rcx, [rcx+10h]
0x18000310e  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x180003115  mov     edx, 13h
0x18000311a  call    WPP_SF_
0x18000311f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003126  test    rbx, rbx
0x180003129  jnz     short loc_180003159
0x18000312b  cmp     rcx, rdi
0x18000312e  jz      loc_1800031D6
0x180003134  test    byte ptr [rcx+1Ch], 1
0x180003138  mov     ebx, 57h ; 'W'
0x18000313d  jz      short loc_1800031B3
0x18000313f  mov     edx, 14h
0x180003144  mov     rcx, [rcx+10h]
0x180003148  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x18000314f  mov     r9d, ebx
0x180003152  call    WPP_SF_d
0x180003157  jmp     short loc_1800031AC
0x180003159  mov     rax, [rbx]
0x18000315c  test    rax, rax
0x18000315f  jnz     short loc_180003178
0x180003161  cmp     rcx, rdi
0x180003164  jz      short loc_1800031D6
0x180003166  test    byte ptr [rcx+1Ch], 1
0x18000316a  mov     ebx, 57h ; 'W'
0x18000316f  jz      short loc_1800031B3
0x180003171  mov     edx, 15h
0x180003176  jmp     short loc_180003144
0x180003178  mov     rdx, [rbx+8]; h
0x18000317c  test    rdx, rdx
0x18000317f  jnz     short loc_180003198
0x180003181  cmp     rcx, rdi
0x180003184  jz      short loc_1800031D6
0x180003186  test    byte ptr [rcx+1Ch], 1
0x18000318a  mov     ebx, 57h ; 'W'
0x18000318f  jz      short loc_1800031B3
0x180003191  mov     edx, 16h
0x180003196  jmp     short loc_180003144
0x180003198  xor     ebx, ebx
0x18000319a  xor     r8d, r8d; pftTimeout
0x18000319d  mov     rcx, rax; pwa
0x1800031a0  call    cs:__imp_SetThreadpoolWait
0x1800031a7  nop     dword ptr [rax+rax+00h]
0x1800031ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031b3  cmp     rcx, rdi
0x1800031b6  jz      short loc_1800031D6
0x1800031b8  test    byte ptr [rcx+1Ch], 8
0x1800031bc  jz      short loc_1800031D6
0x1800031be  mov     rcx, [rcx+10h]
0x1800031c2  lea     r8, WPP_3bebb8bd632b3e04288e9ea9721fbba3_Traceguids
0x1800031c9  mov     edx, 17h
0x1800031ce  mov     r9d, ebx
0x1800031d1  call    WPP_SF_d
0x1800031d6  mov     rbx, [rsp+28h+arg_0]
0x1800031db  add     rsp, 20h
0x1800031df  pop     rdi
0x1800031e0  retn
```
