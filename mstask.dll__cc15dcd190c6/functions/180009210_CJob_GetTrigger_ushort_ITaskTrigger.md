# CJob::GetTrigger(ushort,ITaskTrigger * *)

- ea: `0x180009210`
- end: `0x18000929f`
- name: `?GetTrigger@CJob@@UEAAJGPEAPEAUITaskTrigger@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(CJob *__hidden this, unsigned __int16, struct ITaskTrigger **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180009210`
- `0x180009ef8`
- `0x18000e4a4`

## pseudocode

```c
__int64 __fastcall CJob::GetTrigger(CJob *this, unsigned __int16 a2, struct ITaskTrigger **a3)
{
  unsigned __int16 i; // r9
  __int64 v7; // rdx
  CTrigger *v8; // rax
  struct ITaskTrigger *v9; // rax

  *a3 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_WORD *)this + 16) )
      return 2147750665LL;
    v7 = *((_QWORD *)this + 3) + 48LL * i;
    if ( *(_WORD *)(v7 + 2) == a2 )
      break;
  }
  if ( !v7 )
    return 2147750665LL;
  v8 = (CTrigger *)operator new(0x18u);
  if ( !v8 )
    return 2147942414LL;
  v9 = (struct ITaskTrigger *)CTrigger::CTrigger(v8, a2, this);
  if ( !v9 )
    return 2147942414LL;
  *a3 = v9;
  return 0;
}

```

## disassembly

```asm
0x180009210  mov     [rsp+arg_0], rbx
0x180009215  mov     [rsp+arg_8], rsi
0x18000921a  push    rdi
0x18000921b  sub     rsp, 20h
0x18000921f  mov     rbx, r8
0x180009222  mov     qword ptr [r8], 0
0x180009229  movzx   esi, dx
0x18000922c  mov     rdi, rcx
0x18000922f  xor     r9d, r9d
0x180009232  cmp     r9w, [rcx+20h]
0x180009237  jnb     short loc_18000928A
0x180009239  movzx   eax, r9w
0x18000923d  lea     rdx, [rax+rax*2]
0x180009241  shl     rdx, 4
0x180009245  add     rdx, [rcx+18h]
0x180009249  cmp     [rdx+2], si
0x18000924d  jz      short loc_180009255
0x18000924f  inc     r9w
0x180009253  jmp     short loc_180009232
0x180009255  test    rdx, rdx
0x180009258  jz      short loc_18000928A
0x18000925a  mov     ecx, 18h; Size
0x18000925f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009264  test    rax, rax
0x180009267  jz      short loc_180009283
0x180009269  mov     r8, rdi; struct CJob *
0x18000926c  movzx   edx, si; unsigned __int16
0x18000926f  mov     rcx, rax; this
0x180009272  call    ??0CTrigger@@QEAA@GPEAVCJob@@@Z; CTrigger::CTrigger(ushort,CJob *)
0x180009277  test    rax, rax
0x18000927a  jz      short loc_180009283
0x18000927c  mov     [rbx], rax
0x18000927f  xor     eax, eax
0x180009281  jmp     short loc_18000928F
0x180009283  mov     eax, 8007000Eh
0x180009288  jmp     short loc_18000928F
0x18000928a  mov     eax, 80041309h
0x18000928f  mov     rbx, [rsp+28h+arg_0]
0x180009294  mov     rsi, [rsp+28h+arg_8]
0x180009299  add     rsp, 20h
0x18000929d  pop     rdi
0x18000929e  retn
```
