# QueryDirCache::CleanupCache(void)

- ea: `0x1400167f4`
- end: `0x140016867`
- name: `?CleanupCache@QueryDirCache@@QEAAXXZ`
- size: `115`
- prototype: `void __fastcall(QueryDirCache *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001665c`
- `0x140016870`
- `0x1400169f0`

## callees

- `0x140001e30`
- `0x140003870`
- `0x1400167f4`

## pseudocode

```c
void __fastcall QueryDirCache::CleanupCache(QueryDirCache *this, __int64 a2, __int64 a3)
{
  if ( *((_QWORD *)this + 1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_Ddd(
        WPP_GLOBAL_Control->AttachedDevice,
        a2,
        a3,
        *((unsigned int *)this + 4),
        *((_DWORD *)this + 9),
        *((_DWORD *)this + 8));
    operator delete(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x1400167f4  push    rbx
0x1400167f6  sub     rsp, 30h
0x1400167fa  cmp     qword ptr [rcx+8], 0
0x1400167ff  mov     rbx, rcx
0x140016802  jz      short loc_140016849
0x140016804  mov     rcx, cs:WPP_GLOBAL_Control
0x14001680b  lea     rax, WPP_GLOBAL_Control
0x140016812  cmp     rcx, rax
0x140016815  jz      short loc_140016838
0x140016817  cmp     byte ptr [rcx+29h], 5
0x14001681b  jb      short loc_140016838
0x14001681d  mov     eax, [rbx+20h]
0x140016820  mov     r9d, [rbx+10h]
0x140016824  mov     rcx, [rcx+18h]
0x140016828  mov     [rsp+38h+var_10], eax
0x14001682c  mov     eax, [rbx+24h]
0x14001682f  mov     [rsp+38h+var_18], eax
0x140016833  call    WPP_SF_Ddd
0x140016838  mov     rcx, [rbx+8]; void *
0x14001683c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140016841  mov     qword ptr [rbx+8], 0
0x140016849  mov     dword ptr [rbx+10h], 0
0x140016850  mov     qword ptr [rbx+18h], 0
0x140016858  mov     qword ptr [rbx+20h], 0
0x140016860  add     rsp, 30h
0x140016864  pop     rbx
0x140016865  retn
```
