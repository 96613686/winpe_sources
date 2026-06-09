# PuDeleteBcdObjects(PU_PARTITION_PROPERTIES *)

- ea: `0x1801ab708`
- end: `0x1801ab8a0`
- name: `?PuDeleteBcdObjects@@YAJPEAVPU_PARTITION_PROPERTIES@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(struct PU_PARTITION_PROPERTIES *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18019ec54`

## callees

- `0x1800298d0`
- `0x1801ab658`
- `0x1801ab708`
- `0x1801ab8a8`
- `0x1801abb14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ab860`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ab860`
- `bcd!BcdCloseStore` at `0x1801ab880`
- `bcd!BcdCloseStore` at `0x1801ab880`
- `bcd!BcdDeleteObject` at `0x1801ab7ea`
- `bcd!BcdDeleteObject` at `0x1801ab7ea`
- `bcd!BcdOpenObject` at `0x1801ab7b8`
- `bcd!BcdOpenObject` at `0x1801ab7b8`
- `bcd!BcdCloseObject` at `0x1801ab799`
- `bcd!BcdCloseObject` at `0x1801ab84f`
- `bcd!BcdCloseObject` at `0x1801ab799`
- `bcd!BcdCloseObject` at `0x1801ab84f`
- `bcd!BcdOpenSystemStore` at `0x1801ab73a`
- `bcd!BcdOpenSystemStore` at `0x1801ab73a`

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
  unsigned int v9; // edx
  void *v11; // [rsp+20h] [rbp-10h] BYREF
  struct _BCD_OBJECT *v12; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v13; // [rsp+68h] [rbp+38h] BYREF
  int v14; // [rsp+70h] [rbp+40h] BYREF
  void *v15; // [rsp+78h] [rbp+48h] BYREF

  v1 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  v3 = BcdOpenSystemStore(&v11);
  v4 = v3;
  if ( v3 == -1073741809 )
  {
    v4 = 0;
  }
  else if ( v3 >= 0 )
  {
    v4 = PuEnumerateBcdObjects(v11, &v12, &v13);
    if ( v4 >= 0 && (v5 = 0, v13) )
    {
      v1 = v12;
      do
      {
        v6 = (_QWORD *)((char *)v1 + 24 * v5);
        if ( v15 )
        {
          BcdCloseObject();
          v15 = 0;
        }
        v4 = BcdOpenObject(v11, (char *)v1 + 24 * v5, &v15);
        if ( v4 < 0 )
          break;
        v4 = PuBcdObjectMatchesPartition(v15, a1, &v14);
        if ( v4 < 0 )
          break;
        if ( v14 )
        {
          v4 = BcdDeleteObject(v15);
          if ( v4 < 0 )
            break;
          v15 = 0;
          v7 = *v6 - *(_QWORD *)&GUID_WINDOWS_BOOTMGR.Data1;
          if ( *v6 == *(_QWORD *)&GUID_WINDOWS_BOOTMGR.Data1 )
            v7 = v6[1] - *(_QWORD *)GUID_WINDOWS_BOOTMGR.Data4;
          if ( v7 )
          {
            v4 = PuDeleteDataFromDisplayOrder(v11, (const struct _GUID *)((char *)v1 + 24 * v5));
            if ( v4 < 0 )
              v4 = 0;
          }
        }
        v5 = (unsigned int)(v5 + 1);
      }
      while ( (unsigned int)v5 < v13 );
    }
    else
    {
      v1 = v12;
    }
  }
  if ( v15 )
    BcdCloseObject();
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    PmHeapFree(ProcessHeap, v9, v1);
  }
  if ( v11 )
    BcdCloseStore();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801ab708  mov     [rsp-28h+arg_0], rbx
0x1801ab70d  push    rbp
0x1801ab70e  push    rsi
0x1801ab70f  push    rdi
0x1801ab710  push    r12
0x1801ab712  push    r14
0x1801ab714  mov     rbp, rsp
0x1801ab717  sub     rsp, 30h
0x1801ab71b  xor     edi, edi
0x1801ab71d  mov     [rbp+var_10], 0
0x1801ab725  mov     r12, rcx
0x1801ab728  mov     [rbp+var_8], rdi
0x1801ab72c  lea     rcx, [rbp+var_10]
0x1801ab730  mov     [rbp+arg_8], edi
0x1801ab733  mov     [rbp+arg_18], rdi
0x1801ab737  mov     [rbp+arg_10], edi
0x1801ab73a  call    cs:__imp_BcdOpenSystemStore
0x1801ab741  nop     dword ptr [rax+rax+00h]
0x1801ab746  mov     ebx, eax
0x1801ab748  cmp     eax, 0C000000Fh
0x1801ab74d  jnz     short loc_1801AB756
0x1801ab74f  xor     ebx, ebx
0x1801ab751  jmp     loc_1801AB846
0x1801ab756  test    eax, eax
0x1801ab758  js      loc_1801AB846
0x1801ab75e  mov     rcx, [rbp+var_10]; void *
0x1801ab762  lea     r8, [rbp+arg_8]; unsigned int *
0x1801ab766  lea     rdx, [rbp+var_8]; struct _BCD_OBJECT **
0x1801ab76a  call    ?PuEnumerateBcdObjects@@YAJPEAXPEAPEAU_BCD_OBJECT@@PEAK@Z; PuEnumerateBcdObjects(void *,_BCD_OBJECT * *,ulong *)
0x1801ab76f  mov     ebx, eax
0x1801ab771  test    eax, eax
0x1801ab773  js      loc_1801AB842
0x1801ab779  xor     esi, esi
0x1801ab77b  cmp     [rbp+arg_8], esi
0x1801ab77e  jbe     loc_1801AB842
0x1801ab784  mov     rdi, [rbp+var_8]
0x1801ab788  lea     rcx, [rsi+rsi*2]
0x1801ab78c  lea     r14, [rdi+rcx*8]
0x1801ab790  mov     rcx, [rbp+arg_18]
0x1801ab794  test    rcx, rcx
0x1801ab797  jz      short loc_1801AB7AD
0x1801ab799  call    cs:__imp_BcdCloseObject
0x1801ab7a0  nop     dword ptr [rax+rax+00h]
0x1801ab7a5  mov     [rbp+arg_18], 0
0x1801ab7ad  mov     rcx, [rbp+var_10]
0x1801ab7b1  lea     r8, [rbp+arg_18]
0x1801ab7b5  mov     rdx, r14
0x1801ab7b8  call    cs:__imp_BcdOpenObject
0x1801ab7bf  nop     dword ptr [rax+rax+00h]
0x1801ab7c4  mov     ebx, eax
0x1801ab7c6  test    eax, eax
0x1801ab7c8  js      short loc_1801AB846
0x1801ab7ca  mov     rcx, [rbp+arg_18]; void *
0x1801ab7ce  lea     r8, [rbp+arg_10]; int *
0x1801ab7d2  mov     rdx, r12; struct PU_PARTITION_PROPERTIES *
0x1801ab7d5  call    ?PuBcdObjectMatchesPartition@@YAJPEAXPEAVPU_PARTITION_PROPERTIES@@PEAH@Z; PuBcdObjectMatchesPartition(void *,PU_PARTITION_PROPERTIES *,int *)
0x1801ab7da  mov     ebx, eax
0x1801ab7dc  test    eax, eax
0x1801ab7de  js      short loc_1801AB846
0x1801ab7e0  cmp     [rbp+arg_10], 0
0x1801ab7e4  jz      short loc_1801AB835
0x1801ab7e6  mov     rcx, [rbp+arg_18]
0x1801ab7ea  call    cs:__imp_BcdDeleteObject
0x1801ab7f1  nop     dword ptr [rax+rax+00h]
0x1801ab7f6  mov     ebx, eax
0x1801ab7f8  test    eax, eax
0x1801ab7fa  js      short loc_1801AB846
0x1801ab7fc  mov     [rbp+arg_18], 0
0x1801ab804  mov     rax, [r14]
0x1801ab807  sub     rax, qword ptr cs:GUID_WINDOWS_BOOTMGR.Data1
0x1801ab80e  jnz     short loc_1801AB81B
0x1801ab810  mov     rax, [r14+8]
0x1801ab814  sub     rax, qword ptr cs:GUID_WINDOWS_BOOTMGR.Data4
0x1801ab81b  test    rax, rax
0x1801ab81e  jz      short loc_1801AB835
0x1801ab820  mov     rcx, [rbp+var_10]; void *
0x1801ab824  mov     rdx, r14; struct _GUID *
0x1801ab827  call    ?PuDeleteDataFromDisplayOrder@@YAJPEAXPEBU_GUID@@@Z; PuDeleteDataFromDisplayOrder(void *,_GUID const *)
0x1801ab82c  mov     ebx, eax
0x1801ab82e  xor     eax, eax
0x1801ab830  test    ebx, ebx
0x1801ab832  cmovs   ebx, eax
0x1801ab835  inc     esi
0x1801ab837  cmp     esi, [rbp+arg_8]
0x1801ab83a  jb      loc_1801AB788
0x1801ab840  jmp     short loc_1801AB846
0x1801ab842  mov     rdi, [rbp+var_8]
0x1801ab846  mov     rcx, [rbp+arg_18]
0x1801ab84a  test    rcx, rcx
0x1801ab84d  jz      short loc_1801AB85B
0x1801ab84f  call    cs:__imp_BcdCloseObject
0x1801ab856  nop     dword ptr [rax+rax+00h]
0x1801ab85b  test    rdi, rdi
0x1801ab85e  jz      short loc_1801AB877
0x1801ab860  call    cs:__imp_GetProcessHeap
0x1801ab867  nop     dword ptr [rax+rax+00h]
0x1801ab86c  mov     rcx, rax; void *
0x1801ab86f  mov     r8, rdi; void *
0x1801ab872  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801ab877  mov     rcx, [rbp+var_10]
0x1801ab87b  test    rcx, rcx
0x1801ab87e  jz      short loc_1801AB88C
0x1801ab880  call    cs:__imp_BcdCloseStore
0x1801ab887  nop     dword ptr [rax+rax+00h]
0x1801ab88c  mov     eax, ebx
0x1801ab88e  mov     rbx, [rsp+30h+arg_0]
0x1801ab893  add     rsp, 30h
0x1801ab897  pop     r14
0x1801ab899  pop     r12
0x1801ab89b  pop     rdi
0x1801ab89c  pop     rsi
0x1801ab89d  pop     rbp
0x1801ab89e  retn
```
