# PuDeleteBcdObjects(PU_PARTITION_PROPERTIES *)

- ea: `0x1801a6014`
- end: `0x1801a618e`
- name: `?PuDeleteBcdObjects@@YAJPEAVPU_PARTITION_PROPERTIES@@@Z`
- size: `378`
- prototype: `__int64 __fastcall(struct PU_PARTITION_PROPERTIES *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180199f2c`

## callees

- `0x1801a5f60`
- `0x1801a6014`
- `0x1801a6194`
- `0x1801a63e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a6166`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a6166`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a614e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a614e`
- `bcd!BcdCloseStore` at `0x1801a6175`
- `bcd!BcdCloseStore` at `0x1801a6175`
- `bcd!BcdDeleteObject` at `0x1801a60e4`
- `bcd!BcdDeleteObject` at `0x1801a60e4`
- `bcd!BcdOpenObject` at `0x1801a60b8`
- `bcd!BcdOpenObject` at `0x1801a60b8`
- `bcd!BcdCloseObject` at `0x1801a609f`
- `bcd!BcdCloseObject` at `0x1801a6143`
- `bcd!BcdCloseObject` at `0x1801a609f`
- `bcd!BcdCloseObject` at `0x1801a6143`
- `bcd!BcdOpenSystemStore` at `0x1801a6046`
- `bcd!BcdOpenSystemStore` at `0x1801a6046`

## pseudocode

```c
__int64 __fastcall PuDeleteBcdObjects(struct PU_PARTITION_PROPERTIES *a1)
{
  struct _BCD_OBJECT *v1; // rdi
  int v3; // eax
  int v4; // ebx
  __int64 v5; // rsi
  _QWORD *v6; // r14
  __int64 v7; // rax
  HANDLE ProcessHeap; // rax
  void *v10; // [rsp+20h] [rbp-10h] BYREF
  struct _BCD_OBJECT *v11; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+38h] BYREF
  int v13; // [rsp+70h] [rbp+40h] BYREF
  void *v14; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v3 = BcdOpenSystemStore(&v10);
  v4 = v3;
  if ( v3 == -1073741809 )
  {
    v4 = 0;
  }
  else if ( v3 >= 0 )
  {
    v4 = PuEnumerateBcdObjects(v10, &v11, &v12);
    if ( v4 >= 0 && (v5 = 0, v12) )
    {
      v1 = v11;
      do
      {
        v6 = (_QWORD *)((char *)v1 + 24 * v5);
        if ( v14 )
        {
          BcdCloseObject();
          v14 = 0;
        }
        v4 = BcdOpenObject(v10, (char *)v1 + 24 * v5, &v14);
        if ( v4 < 0 )
          break;
        v4 = PuBcdObjectMatchesPartition(v14, a1, &v13);
        if ( v4 < 0 )
          break;
        if ( v13 )
        {
          v4 = BcdDeleteObject(v14);
          if ( v4 < 0 )
            break;
          v14 = 0;
          v7 = *v6 - *(_QWORD *)&GUID_WINDOWS_BOOTMGR.Data1;
          if ( *v6 == *(_QWORD *)&GUID_WINDOWS_BOOTMGR.Data1 )
            v7 = v6[1] - *(_QWORD *)GUID_WINDOWS_BOOTMGR.Data4;
          if ( v7 )
          {
            v4 = PuDeleteDataFromDisplayOrder(v10, (const struct _GUID *)((char *)v1 + 24 * v5));
            if ( v4 < 0 )
              v4 = 0;
          }
        }
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < v12 );
    }
    else
    {
      v1 = v11;
    }
  }
  if ( v14 )
    BcdCloseObject();
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
      HeapFree(ProcessHeap, 0, v1);
  }
  if ( v10 )
    BcdCloseStore();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801a6014  mov     [rsp-28h+arg_0], rbx
0x1801a6019  push    rbp
0x1801a601a  push    rsi
0x1801a601b  push    rdi
0x1801a601c  push    r12
0x1801a601e  push    r14
0x1801a6020  mov     rbp, rsp
0x1801a6023  sub     rsp, 30h
0x1801a6027  xor     edi, edi
0x1801a6029  mov     [rbp+var_10], 0
0x1801a6031  mov     r12, rcx
0x1801a6034  mov     [rbp+var_8], rdi
0x1801a6038  lea     rcx, [rbp+var_10]
0x1801a603c  mov     [rbp+arg_8], edi
0x1801a603f  mov     [rbp+arg_18], rdi
0x1801a6043  mov     [rbp+arg_10], edi
0x1801a6046  call    cs:__imp_BcdOpenSystemStore
0x1801a604c  mov     ebx, eax
0x1801a604e  cmp     eax, 0C000000Fh
0x1801a6053  jnz     short loc_1801A605C
0x1801a6055  xor     ebx, ebx
0x1801a6057  jmp     loc_1801A613A
0x1801a605c  test    eax, eax
0x1801a605e  js      loc_1801A613A
0x1801a6064  mov     rcx, [rbp+var_10]; void *
0x1801a6068  lea     r8, [rbp+arg_8]; unsigned int *
0x1801a606c  lea     rdx, [rbp+var_8]; struct _BCD_OBJECT **
0x1801a6070  call    ?PuEnumerateBcdObjects@@YAJPEAXPEAPEAU_BCD_OBJECT@@PEAK@Z; PuEnumerateBcdObjects(void *,_BCD_OBJECT * *,ulong *)
0x1801a6075  mov     ebx, eax
0x1801a6077  test    eax, eax
0x1801a6079  js      loc_1801A6136
0x1801a607f  xor     esi, esi
0x1801a6081  cmp     [rbp+arg_8], esi
0x1801a6084  jbe     loc_1801A6136
0x1801a608a  mov     rdi, [rbp+var_8]
0x1801a608e  lea     rcx, [rsi+rsi*2]
0x1801a6092  lea     r14, [rdi+rcx*8]
0x1801a6096  mov     rcx, [rbp+arg_18]
0x1801a609a  test    rcx, rcx
0x1801a609d  jz      short loc_1801A60AD
0x1801a609f  call    cs:__imp_BcdCloseObject
0x1801a60a5  mov     [rbp+arg_18], 0
0x1801a60ad  mov     rcx, [rbp+var_10]
0x1801a60b1  lea     r8, [rbp+arg_18]
0x1801a60b5  mov     rdx, r14
0x1801a60b8  call    cs:__imp_BcdOpenObject
0x1801a60be  mov     ebx, eax
0x1801a60c0  test    eax, eax
0x1801a60c2  js      short loc_1801A613A
0x1801a60c4  mov     rcx, [rbp+arg_18]; void *
0x1801a60c8  lea     r8, [rbp+arg_10]; int *
0x1801a60cc  mov     rdx, r12; struct PU_PARTITION_PROPERTIES *
0x1801a60cf  call    ?PuBcdObjectMatchesPartition@@YAJPEAXPEAVPU_PARTITION_PROPERTIES@@PEAH@Z; PuBcdObjectMatchesPartition(void *,PU_PARTITION_PROPERTIES *,int *)
0x1801a60d4  mov     ebx, eax
0x1801a60d6  test    eax, eax
0x1801a60d8  js      short loc_1801A613A
0x1801a60da  cmp     [rbp+arg_10], 0
0x1801a60de  jz      short loc_1801A6129
0x1801a60e0  mov     rcx, [rbp+arg_18]
0x1801a60e4  call    cs:__imp_BcdDeleteObject
0x1801a60ea  mov     ebx, eax
0x1801a60ec  test    eax, eax
0x1801a60ee  js      short loc_1801A613A
0x1801a60f0  mov     [rbp+arg_18], 0
0x1801a60f8  mov     rax, [r14]
0x1801a60fb  sub     rax, qword ptr cs:GUID_WINDOWS_BOOTMGR.Data1
0x1801a6102  jnz     short loc_1801A610F
0x1801a6104  mov     rax, [r14+8]
0x1801a6108  sub     rax, qword ptr cs:GUID_WINDOWS_BOOTMGR.Data4
0x1801a610f  test    rax, rax
0x1801a6112  jz      short loc_1801A6129
0x1801a6114  mov     rcx, [rbp+var_10]; void *
0x1801a6118  mov     rdx, r14; struct _GUID *
0x1801a611b  call    ?PuDeleteDataFromDisplayOrder@@YAJPEAXPEBU_GUID@@@Z; PuDeleteDataFromDisplayOrder(void *,_GUID const *)
0x1801a6120  mov     ebx, eax
0x1801a6122  xor     eax, eax
0x1801a6124  test    ebx, ebx
0x1801a6126  cmovs   ebx, eax
0x1801a6129  inc     esi
0x1801a612b  cmp     esi, [rbp+arg_8]
0x1801a612e  jb      loc_1801A608E
0x1801a6134  jmp     short loc_1801A613A
0x1801a6136  mov     rdi, [rbp+var_8]
0x1801a613a  mov     rcx, [rbp+arg_18]
0x1801a613e  test    rcx, rcx
0x1801a6141  jz      short loc_1801A6149
0x1801a6143  call    cs:__imp_BcdCloseObject
0x1801a6149  test    rdi, rdi
0x1801a614c  jz      short loc_1801A616C
0x1801a614e  call    cs:__imp_GetProcessHeap
0x1801a6154  test    rax, rax
0x1801a6157  jz      short loc_1801A616C
0x1801a6159  test    rdi, rdi
0x1801a615c  jz      short loc_1801A616C
0x1801a615e  mov     r8, rdi; lpMem
0x1801a6161  xor     edx, edx; dwFlags
0x1801a6163  mov     rcx, rax; hHeap
0x1801a6166  call    cs:__imp_HeapFree
0x1801a616c  mov     rcx, [rbp+var_10]
0x1801a6170  test    rcx, rcx
0x1801a6173  jz      short loc_1801A617B
0x1801a6175  call    cs:__imp_BcdCloseStore
0x1801a617b  mov     eax, ebx
0x1801a617d  mov     rbx, [rsp+30h+arg_0]
0x1801a6182  add     rsp, 30h
0x1801a6186  pop     r14
0x1801a6188  pop     r12
0x1801a618a  pop     rdi
0x1801a618b  pop     rsi
0x1801a618c  pop     rbp
0x1801a618d  retn
```
