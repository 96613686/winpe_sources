# CSynth::StealVoice(ulong)

- ea: `0x1800075f0`
- end: `0x1800076cc`
- name: `?StealVoice@CSynth@@AEAAPEAVCVoice@@K@Z`
- size: `220`
- prototype: `struct CVoice *__fastcall(CSynth *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004120`
- `0x180004c90`

## callees

- `0x1800075f0`
- `0x18000b0f0`

## pseudocode

```c
struct CVoice *__fastcall CSynth::StealVoice(CSynth *this, unsigned int a2)
{
  __int64 *v2; // r8
  __int64 *v3; // rbx
  __int64 *v5; // rcx
  __int64 *v6; // r8
  __int64 *v7; // rax
  __int64 v8; // rdx

  v2 = (__int64 *)*((_QWORD *)this + 8);
  v3 = 0;
  if ( v2 )
  {
    do
    {
      if ( *((_DWORD *)v2 + 145) <= a2 )
      {
        if ( v3 )
        {
          if ( *((_DWORD *)v2 + 137) )
          {
            if ( v3[65] > v2[65] )
              v3 = v2;
          }
          else if ( *((_DWORD *)v3 + 137) == 1 || *((_DWORD *)v3 + 139) > *((_DWORD *)v2 + 139) )
          {
            v3 = v2;
          }
        }
        else
        {
          v3 = v2;
        }
      }
      v2 = (__int64 *)*v2;
    }
    while ( v2 );
    if ( v3 )
    {
      CVoice::ClearVoice((CVoice *)v3);
      *((_DWORD *)v3 + 136) = 0;
      v5 = (__int64 *)*((_QWORD *)this + 8);
      if ( v3 == v5 )
      {
        v5 = (__int64 *)*v5;
      }
      else
      {
        v6 = 0;
        v7 = (__int64 *)*((_QWORD *)this + 8);
        if ( v5 )
        {
          while ( 1 )
          {
            v8 = *v7;
            if ( v7 == v3 )
              break;
            v6 = v7;
            v7 = (__int64 *)*v7;
            if ( !v8 )
              goto LABEL_20;
          }
          *v6 = v8;
          *v7 = 0;
        }
      }
LABEL_20:
      *((_QWORD *)this + 8) = v5;
      *v3 = 0;
    }
  }
  return (struct CVoice *)v3;
}

```

## disassembly

```asm
0x1800075f0  mov     [rsp+arg_0], rbx
0x1800075f5  push    rdi
0x1800075f6  sub     rsp, 20h
0x1800075fa  mov     r8, [rcx+40h]
0x1800075fe  xor     ebx, ebx
0x180007600  mov     rdi, rcx
0x180007603  test    r8, r8
0x180007606  jz      loc_1800076BE
0x18000760c  nop     dword ptr [rax+00h]
0x180007610  cmp     [r8+244h], edx
0x180007617  ja      short loc_18000765C
0x180007619  test    rbx, rbx
0x18000761c  jnz     short loc_180007623
0x18000761e  mov     rbx, r8
0x180007621  jmp     short loc_18000765C
0x180007623  cmp     dword ptr [r8+224h], 0
0x18000762b  jnz     short loc_18000764A
0x18000762d  cmp     dword ptr [rbx+224h], 1
0x180007634  jz      short loc_180007645
0x180007636  mov     eax, [r8+22Ch]
0x18000763d  cmp     [rbx+22Ch], eax
0x180007643  jle     short loc_18000765C
0x180007645  mov     rbx, r8
0x180007648  jmp     short loc_18000765C
0x18000764a  mov     rax, [r8+208h]
0x180007651  cmp     [rbx+208h], rax
0x180007658  cmovg   rbx, r8
0x18000765c  mov     r8, [r8]
0x18000765f  test    r8, r8
0x180007662  jnz     short loc_180007610
0x180007664  test    rbx, rbx
0x180007667  jz      short loc_1800076BE
0x180007669  mov     rcx, rbx; this
0x18000766c  call    ?ClearVoice@CVoice@@QEAAXXZ; CVoice::ClearVoice(void)
0x180007671  mov     dword ptr [rbx+220h], 0
0x18000767b  mov     rcx, [rdi+40h]
0x18000767f  cmp     rbx, rcx
0x180007682  jnz     short loc_180007689
0x180007684  mov     rcx, [rcx]
0x180007687  jmp     short loc_1800076B3
0x180007689  xor     r8d, r8d
0x18000768c  mov     rax, rcx
0x18000768f  test    rcx, rcx
0x180007692  jz      short loc_1800076B3
0x180007694  mov     rdx, [rax]
0x180007697  cmp     rax, rbx
0x18000769a  jz      short loc_1800076A9
0x18000769c  mov     r8, rax
0x18000769f  mov     rax, rdx
0x1800076a2  test    rdx, rdx
0x1800076a5  jnz     short loc_180007694
0x1800076a7  jmp     short loc_1800076B3
0x1800076a9  mov     [r8], rdx
0x1800076ac  mov     qword ptr [rax], 0
0x1800076b3  mov     [rdi+40h], rcx
0x1800076b7  mov     qword ptr [rbx], 0
0x1800076be  mov     rax, rbx
0x1800076c1  mov     rbx, [rsp+28h+arg_0]
0x1800076c6  add     rsp, 20h
0x1800076ca  pop     rdi
0x1800076cb  retn
```
