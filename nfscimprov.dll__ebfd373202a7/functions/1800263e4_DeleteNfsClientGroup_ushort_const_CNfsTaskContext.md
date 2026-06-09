# DeleteNfsClientGroup(ushort const *,CNfsTaskContext *)

- ea: `0x1800263e4`
- end: `0x1800264b5`
- name: `?DeleteNfsClientGroup@@YAKPEBGPEAVCNfsTaskContext@@@Z`
- size: `209`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct CNfsTaskContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180014968`

## callees

- `0x1800263e4`
- `0x1800264bc`
- `0x180026970`
- `0x1800269d4`
- `0x180026ac4`
- `0x1800272a0`
- `0x180037010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002649a`
- `KERNEL32!HeapFree` at `0x18002649a`
- `KERNEL32!GetProcessHeap` at `0x18002648c`
- `KERNEL32!GetProcessHeap` at `0x18002648c`

## pseudocode

```c
__int64 __fastcall DeleteNfsClientGroup(const unsigned __int16 *a1, struct CNfsTaskContext *a2)
{
  unsigned int v4; // ebx
  struct _NFS_GROUP_ENTRY *ClientGroup; // rax
  struct _NFS_GROUP_ENTRY *v6; // rbx
  __int64 v8; // rax
  struct _NFS_GROUP_ENTRY **v9; // rcx
  HANDLE ProcessHeap; // rax
  struct _LIST_ENTRY v11; // [rsp+30h] [rbp-18h] BYREF

  v11.Blink = &v11;
  v11.Flink = &v11;
  v4 = LoadCliGrpData(&v11, 0);
  if ( !v4 )
  {
    ClientGroup = FindClientGroup(&v11, a1);
    v6 = ClientGroup;
    if ( ClientGroup )
    {
      v8 = *(_QWORD *)ClientGroup;
      if ( *(struct _NFS_GROUP_ENTRY **)(v8 + 8) != v6
        || (v9 = (struct _NFS_GROUP_ENTRY **)*((_QWORD *)v6 + 1), *v9 != v6) )
      {
        __fastfail(3u);
      }
      *v9 = (struct _NFS_GROUP_ENTRY *)v8;
      *(_QWORD *)(v8 + 8) = v9;
      FreeGroupMemberList(v6);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
      v4 = SaveSettings(&v11);
    }
    else
    {
      v4 = 1168;
      (*(void (__fastcall **)(struct CNfsTaskContext *, __int64, __int64, const unsigned __int16 *))(*(_QWORD *)a2 + 40LL))(
        a2,
        1168,
        3221229608LL,
        a1);
    }
  }
  FreeGroupList(&v11);
  return v4;
}

```

## disassembly

```asm
0x1800263e4  mov     r11, rsp
0x1800263e7  mov     [r11+8], rbx
0x1800263eb  mov     [r11+10h], rsi
0x1800263ef  push    rdi
0x1800263f0  sub     rsp, 40h
0x1800263f4  lea     rax, [r11-18h]
0x1800263f8  mov     rsi, rdx
0x1800263fb  mov     [r11-10h], rax
0x1800263ff  mov     rdi, rcx
0x180026402  lea     rax, [r11-18h]
0x180026406  xor     edx, edx; unsigned int *
0x180026408  lea     rcx, [r11-18h]; struct _LIST_ENTRY *
0x18002640c  mov     [r11-18h], rax
0x180026410  call    ?LoadCliGrpData@@YAKPEAU_LIST_ENTRY@@PEAK@Z; LoadCliGrpData(_LIST_ENTRY *,ulong *)
0x180026415  mov     ebx, eax
0x180026417  test    eax, eax
0x180026419  jnz     short loc_18002644F
0x18002641b  mov     rdx, rdi; unsigned __int16 *
0x18002641e  lea     rcx, [rsp+48h+var_18]; struct _LIST_ENTRY *
0x180026423  call    ?FindClientGroup@@YAPEAU_NFS_GROUP_ENTRY@@PEAU_LIST_ENTRY@@PEBG@Z; FindClientGroup(_LIST_ENTRY *,ushort const *)
0x180026428  mov     rbx, rax
0x18002642b  test    rax, rax
0x18002642e  jnz     short loc_18002646B
0x180026430  mov     rax, [rsi]
0x180026433  mov     ebx, 490h
0x180026438  mov     r9, rdi
0x18002643b  mov     r8d, 0C0001028h
0x180026441  mov     edx, ebx
0x180026443  mov     rcx, rsi
0x180026446  mov     rax, [rax+28h]
0x18002644a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002644f  lea     rcx, [rsp+48h+var_18]; struct _LIST_ENTRY *
0x180026454  call    ?FreeGroupList@@YAXPEAU_LIST_ENTRY@@@Z; FreeGroupList(_LIST_ENTRY *)
0x180026459  mov     rsi, [rsp+48h+arg_8]
0x18002645e  mov     eax, ebx
0x180026460  mov     rbx, [rsp+48h+arg_0]
0x180026465  add     rsp, 40h
0x180026469  pop     rdi
0x18002646a  retn
0x18002646b  mov     rax, [rax]
0x18002646e  cmp     [rax+8], rbx
0x180026472  jnz     short loc_1800264AE
0x180026474  mov     rcx, [rbx+8]
0x180026478  cmp     [rcx], rbx
0x18002647b  jnz     short loc_1800264AE
0x18002647d  mov     [rcx], rax
0x180026480  mov     [rax+8], rcx
0x180026484  mov     rcx, rbx; struct _NFS_GROUP_ENTRY *
0x180026487  call    ?FreeGroupMemberList@@YAXPEAU_NFS_GROUP_ENTRY@@@Z; FreeGroupMemberList(_NFS_GROUP_ENTRY *)
0x18002648c  call    cs:__imp_GetProcessHeap
0x180026492  mov     r8, rbx; lpMem
0x180026495  xor     edx, edx; dwFlags
0x180026497  mov     rcx, rax; hHeap
0x18002649a  call    cs:__imp_HeapFree
0x1800264a0  lea     rcx, [rsp+48h+var_18]; struct _LIST_ENTRY *
0x1800264a5  call    ?SaveSettings@@YAKPEAU_LIST_ENTRY@@@Z; SaveSettings(_LIST_ENTRY *)
0x1800264aa  mov     ebx, eax
0x1800264ac  jmp     short loc_18002644F
0x1800264ae  mov     ecx, 3
0x1800264b3  int     29h; Win8: RtlFailFast(ecx)
```
