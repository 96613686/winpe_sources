# FCpEncStreamCleanup

- ea: `0x14000d13c`
- end: `0x14000d1a1`
- name: `FCpEncStreamCleanup`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d010`
- `0x14000d1a8`

## callees

- `0x14000d13c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d186`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d186`
- `ksecdd!BCryptDestroyKey` at `0x14000d14d`
- `ksecdd!BCryptDestroyKey` at `0x14000d14d`

## pseudocode

```c
void __fastcall FCpEncStreamCleanup(__int64 a1)
{
  void *v2; // rcx
  _BYTE *v3; // rax
  __int64 v4; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    BCryptDestroyKey(v2);
    *(_QWORD *)a1 = 0;
  }
  v3 = *(_BYTE **)(a1 + 8);
  if ( v3 )
  {
    v4 = *(unsigned int *)(a1 + 16);
    if ( *(_DWORD *)(a1 + 16) )
    {
      do
      {
        *v3++ = 0;
        --v4;
      }
      while ( v4 );
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 8), 0x72434346u);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x14000d13c  push    rbx
0x14000d13e  sub     rsp, 20h
0x14000d142  mov     rbx, rcx
0x14000d145  mov     rcx, [rcx]; hKey
0x14000d148  test    rcx, rcx
0x14000d14b  jz      short loc_14000D160
0x14000d14d  call    cs:__imp_BCryptDestroyKey
0x14000d154  nop     dword ptr [rax+rax+00h]
0x14000d159  mov     qword ptr [rbx], 0
0x14000d160  mov     rax, [rbx+8]
0x14000d164  test    rax, rax
0x14000d167  jz      short loc_14000D19A
0x14000d169  mov     ecx, [rbx+10h]
0x14000d16c  test    rcx, rcx
0x14000d16f  jz      short loc_14000D17D
0x14000d171  mov     byte ptr [rax], 0
0x14000d174  inc     rax
0x14000d177  sub     rcx, 1
0x14000d17b  jnz     short loc_14000D171
0x14000d17d  mov     rcx, [rbx+8]; P
0x14000d181  mov     edx, 72434346h; Tag
0x14000d186  call    cs:__imp_ExFreePoolWithTag
0x14000d18d  nop     dword ptr [rax+rax+00h]
0x14000d192  mov     qword ptr [rbx+8], 0
0x14000d19a  add     rsp, 20h
0x14000d19e  pop     rbx
0x14000d19f  retn
```
