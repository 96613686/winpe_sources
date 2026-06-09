# DiscpRemoveTargetsByTag

- ea: `0x180007bb4`
- end: `0x180007c3b`
- name: `DiscpRemoveTargetsByTag`
- size: `135`
- prototype: `NTSTATUS __fastcall(int)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002cbc`
- `0x180004380`
- `0x180005098`
- `0x180007900`
- `0x180009358`
- `0x18000bfc4`
- `0x18000c03c`
- `0x180011df0`

## callees

- `0x1800079ac`
- `0x180007bb4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180007c34`
- `ntdll!RtlEnterCriticalSection` at `0x180007bca`
- `ntdll!RtlEnterCriticalSection` at `0x180007bca`

## pseudocode

```c
NTSTATUS __fastcall DiscpRemoveTargetsByTag(int a1)
{
  __int64 *v2; // rdi
  __int64 *v3; // rbp
  __int64 *v4; // rbx
  __int64 *v5; // rcx

  RtlEnterCriticalSection(&DiscpCritSection);
  v2 = (__int64 *)DiscpTargetsList;
  while ( v2 != (__int64 *)&DiscpTargetsList )
  {
    v3 = v2;
    v2 = (__int64 *)*v2;
    v4 = (__int64 *)v3[2];
    while ( v4 != v3 + 2 )
    {
      v5 = v4 - 2;
      v4 = (__int64 *)*v4;
      if ( a1 == 1 || a1 == *((_DWORD *)v5 + 11) )
        DiscpRemoveTarget(v5);
    }
    if ( a1 == 1 || a1 == *((_DWORD *)v3 + 11) )
      DiscpRemoveTarget(v3);
  }
  return RtlLeaveCriticalSection(&DiscpCritSection);
}

```

## disassembly

```asm
0x180007bb4  push    rbx
0x180007bb6  push    rbp
0x180007bb7  push    rsi
0x180007bb8  push    rdi
0x180007bb9  push    r14
0x180007bbb  push    r15
0x180007bbd  sub     rsp, 28h
0x180007bc1  mov     esi, ecx
0x180007bc3  lea     rcx, DiscpCritSection; CriticalSection
0x180007bca  call    cs:__imp_RtlEnterCriticalSection
0x180007bd0  mov     rdi, cs:DiscpTargetsList
0x180007bd7  lea     r15, DiscpTargetsList
0x180007bde  jmp     short loc_180007C1C
0x180007be0  mov     rbp, rdi
0x180007be3  mov     rdi, [rdi]
0x180007be6  lea     r14, [rbp+10h]
0x180007bea  mov     rbx, [r14]
0x180007bed  jmp     short loc_180007C05
0x180007bef  lea     rcx, [rbx-10h]
0x180007bf3  mov     rbx, [rbx]
0x180007bf6  cmp     esi, 1
0x180007bf9  jz      short loc_180007C00
0x180007bfb  cmp     esi, [rcx+2Ch]
0x180007bfe  jnz     short loc_180007C05
0x180007c00  call    DiscpRemoveTarget
0x180007c05  cmp     rbx, r14
0x180007c08  jnz     short loc_180007BEF
0x180007c0a  cmp     esi, 1
0x180007c0d  jz      short loc_180007C14
0x180007c0f  cmp     esi, [rbp+2Ch]
0x180007c12  jnz     short loc_180007C1C
0x180007c14  mov     rcx, rbp
0x180007c17  call    DiscpRemoveTarget
0x180007c1c  cmp     rdi, r15
0x180007c1f  jnz     short loc_180007BE0
0x180007c21  lea     rcx, DiscpCritSection
0x180007c28  add     rsp, 28h
0x180007c2c  pop     r15
0x180007c2e  pop     r14
0x180007c30  pop     rdi
0x180007c31  pop     rsi
0x180007c32  pop     rbp
0x180007c33  pop     rbx
0x180007c34  jmp     cs:__imp_RtlLeaveCriticalSection
```
