# CVoice::QuickStopVoice(__int64)

- ea: `0x18000d220`
- end: `0x18000d312`
- name: `?QuickStopVoice@CVoice@@QEAAX_J@Z`
- size: `242`
- prototype: `void(CVoice *__hidden this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004120`
- `0x180006420`

## callees

- `0x18000b4b0`
- `0x18000d220`
- `0x18000d320`

## pseudocode

```c
void __fastcall CVoice::QuickStopVoice(CVoice *this, __int64 a2)
{
  bool v2; // zf
  __int64 v3; // rdi
  __int64 v5; // rax

  v2 = *((_DWORD *)this + 137) == 0;
  v3 = a2;
  *((_DWORD *)this + 138) = 1;
  if ( !v2 || *((_DWORD *)this + 140) )
  {
    v5 = *((_QWORD *)this + 65);
    if ( a2 <= v5 )
      v3 = v5 + 1;
    if ( *((_DWORD *)this + 40) )
      *((_QWORD *)this + 13) = *((_QWORD *)this + 13)
                             * (int)CVoiceEG::GetLevel((CVoice *)((char *)this + 88), v3, (__int64 *)this + 19, 1)
                             / 1000LL;
    *((_QWORD *)this + 19) = v3;
    CVoiceEG::QuickStopVoice((CVoice *)((char *)this + 168), v3, *(_DWORD *)(*((_QWORD *)this + 60) + 208LL));
    *((_QWORD *)this + 66) = v3;
    *((_DWORD *)this + 137) = 0;
    *((_DWORD *)this + 140) = 0;
  }
  else
  {
    CVoiceEG::QuickStopVoice(
      (CVoice *)((char *)this + 168),
      *((_QWORD *)this + 66),
      *(_DWORD *)(*((_QWORD *)this + 60) + 208LL));
  }
}

```

## disassembly

```asm
0x18000d220  push    rbx
0x18000d222  push    rsi
0x18000d223  push    rdi
0x18000d224  push    r14
0x18000d226  sub     rsp, 28h
0x18000d22a  cmp     dword ptr [rcx+224h], 0
0x18000d231  mov     rdi, rdx
0x18000d234  mov     rbx, rcx
0x18000d237  mov     dword ptr [rcx+228h], 1
0x18000d241  jnz     short loc_18000D276
0x18000d243  cmp     dword ptr [rcx+230h], 0
0x18000d24a  jnz     short loc_18000D276
0x18000d24c  mov     r8, [rcx+1E0h]
0x18000d253  add     rcx, 0A8h; this
0x18000d25a  mov     rdx, [rbx+210h]; __int64
0x18000d261  mov     r8d, [r8+0D0h]; unsigned int
0x18000d268  add     rsp, 28h
0x18000d26c  pop     r14
0x18000d26e  pop     rdi
0x18000d26f  pop     rsi
0x18000d270  pop     rbx
0x18000d271  jmp     ?QuickStopVoice@CVoiceEG@@QEAAX_JK@Z; CVoiceEG::QuickStopVoice(__int64,ulong)
0x18000d276  mov     rax, [rcx+208h]
0x18000d27d  cmp     rdx, rax
0x18000d280  jg      short loc_18000D286
0x18000d282  lea     rdi, [rax+1]
0x18000d286  cmp     dword ptr [rcx+0A0h], 0
0x18000d28d  jz      short loc_18000D2CF
0x18000d28f  lea     r8, [rcx+98h]; __int64 *
0x18000d296  mov     r9d, 1; int
0x18000d29c  add     rcx, 58h ; 'X'; this
0x18000d2a0  mov     rdx, rdi; __int64
0x18000d2a3  call    ?GetLevel@CVoiceEG@@AEAAJ_JPEA_JH@Z; CVoiceEG::GetLevel(__int64,__int64 *,int)
0x18000d2a8  movsxd  rcx, eax
0x18000d2ab  mov     rax, 20C49BA5E353F7CFh
0x18000d2b5  imul    rcx, [rbx+68h]
0x18000d2ba  imul    rcx
0x18000d2bd  sar     rdx, 7
0x18000d2c1  mov     rax, rdx
0x18000d2c4  shr     rax, 3Fh
0x18000d2c8  add     rdx, rax
0x18000d2cb  mov     [rbx+68h], rdx
0x18000d2cf  mov     [rbx+98h], rdi
0x18000d2d6  lea     rcx, [rbx+0A8h]; this
0x18000d2dd  mov     r8, [rbx+1E0h]
0x18000d2e4  mov     rdx, rdi; __int64
0x18000d2e7  mov     r8d, [r8+0D0h]; unsigned int
0x18000d2ee  call    ?QuickStopVoice@CVoiceEG@@QEAAX_JK@Z; CVoiceEG::QuickStopVoice(__int64,ulong)
0x18000d2f3  xor     eax, eax
0x18000d2f5  mov     [rbx+210h], rdi
0x18000d2fc  mov     [rbx+224h], eax
0x18000d302  mov     [rbx+230h], eax
0x18000d308  add     rsp, 28h
0x18000d30c  pop     r14
0x18000d30e  pop     rdi
0x18000d30f  pop     rsi
0x18000d310  pop     rbx
0x18000d311  retn
```
