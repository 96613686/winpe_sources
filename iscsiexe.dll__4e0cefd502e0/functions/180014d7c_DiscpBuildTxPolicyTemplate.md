# DiscpBuildTxPolicyTemplate

- ea: `0x180014d7c`
- end: `0x180014e16`
- name: `DiscpBuildTxPolicyTemplate`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016934`

## callees

- `0x180001cfe`
- `0x180014d7c`
- `0x180014e1c`
- `0x180015890`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180014d92`
- `ISCSIUM!DiscpAllocMemory` at `0x180014d92`
- `ISCSIUM!DiscpFreeMemory` at `0x180014dfd`
- `ISCSIUM!DiscpFreeMemory` at `0x180014dfd`

## pseudocode

```c
__int64 __fastcall DiscpBuildTxPolicyTemplate(_QWORD *a1, unsigned int a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rdx
  unsigned int v7; // edi
  unsigned int i; // esi

  v4 = (_QWORD *)DiscpAllocMemory(124);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x7Cu);
    v7 = DiscpFillIpsecProposals(v5 + 5, v6, a2);
    if ( v7 )
    {
      for ( i = 0; i < *(_DWORD *)v5; ++i )
        DiscpClearIpsecProposal(v5[1] + 32LL * i);
      DiscpFreeMemory(v5);
    }
    else
    {
      *((_DWORD *)v5 + 4) = 0;
      *((_DWORD *)v5 + 6) = 360;
      *((_DWORD *)v5 + 7) = 360;
      v5[1] = v5 + 5;
      *(_DWORD *)v5 = 3;
      *a1 = v5;
    }
  }
  else
  {
    return 8;
  }
  return v7;
}

```

## disassembly

```asm
0x180014d7c  push    rbx
0x180014d7e  push    rsi
0x180014d7f  push    rdi
0x180014d80  push    r14
0x180014d82  sub     rsp, 28h
0x180014d86  mov     r14, rcx
0x180014d89  mov     esi, 7Ch ; '|'
0x180014d8e  mov     ecx, esi
0x180014d90  mov     edi, edx
0x180014d92  call    cs:__imp_DiscpAllocMemory
0x180014d98  mov     rbx, rax
0x180014d9b  test    rax, rax
0x180014d9e  jz      short loc_180014E05
0x180014da0  mov     r8d, esi; Size
0x180014da3  xor     edx, edx; Val
0x180014da5  mov     rcx, rax; void *
0x180014da8  call    memset_0
0x180014dad  lea     rsi, [rbx+28h]
0x180014db1  mov     r8d, edi
0x180014db4  mov     rcx, rsi
0x180014db7  call    DiscpFillIpsecProposals
0x180014dbc  mov     edi, eax
0x180014dbe  test    eax, eax
0x180014dc0  jnz     short loc_180014DDF
0x180014dc2  mov     [rbx+10h], eax
0x180014dc5  mov     eax, 168h
0x180014dca  mov     [rbx+18h], eax
0x180014dcd  mov     [rbx+1Ch], eax
0x180014dd0  mov     [rbx+8], rsi
0x180014dd4  mov     dword ptr [rbx], 3
0x180014dda  mov     [r14], rbx
0x180014ddd  jmp     short loc_180014E0A
0x180014ddf  xor     esi, esi
0x180014de1  cmp     [rbx], esi
0x180014de3  jbe     short loc_180014DFA
0x180014de5  mov     ecx, esi
0x180014de7  shl     rcx, 5
0x180014deb  add     rcx, [rbx+8]
0x180014def  call    DiscpClearIpsecProposal
0x180014df4  inc     esi
0x180014df6  cmp     esi, [rbx]
0x180014df8  jb      short loc_180014DE5
0x180014dfa  mov     rcx, rbx
0x180014dfd  call    cs:__imp_DiscpFreeMemory
0x180014e03  jmp     short loc_180014E0A
0x180014e05  mov     edi, 8
0x180014e0a  mov     eax, edi
0x180014e0c  add     rsp, 28h
0x180014e10  pop     r14
0x180014e12  pop     rdi
0x180014e13  pop     rsi
0x180014e14  pop     rbx
0x180014e15  retn
```
