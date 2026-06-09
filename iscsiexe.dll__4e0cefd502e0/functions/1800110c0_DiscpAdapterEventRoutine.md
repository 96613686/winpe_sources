# DiscpAdapterEventRoutine

- ea: `0x1800110c0`
- end: `0x180011182`
- name: `DiscpAdapterEventRoutine`
- size: `194`
- prototype: `void __fastcall(unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005098`
- `0x1800110c0`

## import_xrefs

- `ISCSIUM!DiscpParseSingleInstance` at `0x180011117`
- `ISCSIUM!DiscpParseSingleInstance` at `0x180011117`
- `ISCSIUM!DiscpCopyString` at `0x180011155`
- `ISCSIUM!DiscpCopyString` at `0x180011155`
- `ISCSIUM!DiscpFreeMemory` at `0x180011176`
- `ISCSIUM!DiscpFreeMemory` at `0x180011176`

## pseudocode

```c
void __fastcall DiscpAdapterEventRoutine(unsigned int *a1)
{
  bool v1; // zf
  int v2; // eax
  unsigned __int16 *v3; // [rsp+30h] [rbp-10h] BYREF
  __int64 v4; // [rsp+38h] [rbp-8h] BYREF
  int v5; // [rsp+50h] [rbp+10h] BYREF
  int v6; // [rsp+60h] [rbp+20h] BYREF
  __int64 v7; // [rsp+68h] [rbp+28h] BYREF

  v1 = (a1[11] & 2) == 0;
  v4 = 0;
  v3 = 0;
  v7 = 0;
  v5 = 0;
  v6 = 0;
  if ( !v1 && !(unsigned int)DiscpParseSingleInstance(a1, *a1, 16, &v3, &v4, 0) )
  {
    v2 = *v3 + 2;
    v7 = 0;
    v5 = v2;
    if ( !(unsigned int)DiscpCopyString(&v7, &v6, &v3, (*v3 >> 1) + 1, &v5) )
    {
      if ( *(_DWORD *)(v4 + 8) == 3 )
        DiscpRefreshAdapterTargets(v7);
      DiscpFreeMemory(v7);
    }
  }
}

```

## disassembly

```asm
0x1800110c0  push    rbp
0x1800110c2  mov     rbp, rsp
0x1800110c5  sub     rsp, 40h
0x1800110c9  test    byte ptr [rcx+2Ch], 2
0x1800110cd  mov     [rbp+var_8], 0
0x1800110d5  mov     [rbp+var_10], 0
0x1800110dd  mov     [rbp+arg_18], 0
0x1800110e5  mov     [rbp+arg_0], 0
0x1800110ec  mov     [rbp+arg_10], 0
0x1800110f3  jz      loc_18001117C
0x1800110f9  mov     edx, [rcx]
0x1800110fb  lea     rax, [rbp+var_8]
0x1800110ff  mov     [rsp+40h+var_18], 0
0x180011108  lea     r9, [rbp+var_10]
0x18001110c  mov     r8d, 10h
0x180011112  mov     [rsp+40h+var_20], rax
0x180011117  call    cs:__imp_DiscpParseSingleInstance
0x18001111d  test    eax, eax
0x18001111f  jnz     short loc_18001117C
0x180011121  mov     rcx, [rbp+var_10]
0x180011125  lea     r8, [rbp+var_10]
0x180011129  lea     rdx, [rbp+arg_10]
0x18001112d  movzx   eax, word ptr [rcx]
0x180011130  add     eax, 2
0x180011133  mov     [rbp+arg_18], 0
0x18001113b  mov     [rbp+arg_0], eax
0x18001113e  lea     rax, [rbp+arg_0]
0x180011142  movzx   r9d, word ptr [rcx]
0x180011146  lea     rcx, [rbp+arg_18]
0x18001114a  shr     r9d, 1
0x18001114d  inc     r9d
0x180011150  mov     [rsp+40h+var_20], rax
0x180011155  call    cs:__imp_DiscpCopyString
0x18001115b  test    eax, eax
0x18001115d  jnz     short loc_18001117C
0x18001115f  mov     rax, [rbp+var_8]
0x180011163  cmp     dword ptr [rax+8], 3
0x180011167  jnz     short loc_180011172
0x180011169  mov     rcx, [rbp+arg_18]
0x18001116d  call    DiscpRefreshAdapterTargets
0x180011172  mov     rcx, [rbp+arg_18]
0x180011176  call    cs:__imp_DiscpFreeMemory
0x18001117c  add     rsp, 40h
0x180011180  pop     rbp
0x180011181  retn
```
