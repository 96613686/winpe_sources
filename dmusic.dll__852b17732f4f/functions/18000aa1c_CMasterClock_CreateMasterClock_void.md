# CMasterClock::CreateMasterClock(void)

- ea: `0x18000aa1c`
- end: `0x18000aac7`
- name: `?CreateMasterClock@CMasterClock@@AEAAJXZ`
- size: `171`
- prototype: `__int64 __fastcall(CMasterClock *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b170`
- `0x180013850`

## callees

- `0x18000aa1c`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CMasterClock::CreateMasterClock(CMasterClock *this)
{
  int v2; // edi
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  __int64 v5; // r8

  v2 = -2147024809;
  v3 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 4) + 40LL))((char *)this + 32);
  if ( v3 )
  {
    v4 = (_QWORD *)*((_QWORD *)this + 14);
    while ( 1 )
    {
      v5 = *(_QWORD *)(v3 + 16);
      if ( *v4 == *(_QWORD *)(v5 + 12) && v4[1] == *(_QWORD *)(v5 + 20) )
        break;
      v3 = *(_QWORD *)(v3 + 8);
      if ( !v3 )
        return (unsigned int)v2;
    }
    if ( v5 )
    {
      v2 = (*(__int64 (__fastcall **)(char *, CMasterClock *))(v5 + 288))((char *)this + 80, this);
      if ( v2 >= 0
        && (***((int (__fastcall ****)(_QWORD, GUID *, char *))this + 10))(
             *((_QWORD *)this + 10),
             &IID_IDirectSoundSinkSync,
             (char *)this + 88) < 0 )
      {
        *((_QWORD *)this + 11) = 0;
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000aa1c  mov     [rsp+arg_0], rbx
0x18000aa21  mov     [rsp+arg_8], rsi
0x18000aa26  push    rdi
0x18000aa27  sub     rsp, 20h
0x18000aa2b  mov     rbx, rcx
0x18000aa2e  mov     edi, 80070057h
0x18000aa33  add     rcx, 20h ; ' '
0x18000aa37  mov     rax, [rcx]
0x18000aa3a  mov     rax, [rax+28h]
0x18000aa3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa43  mov     rdx, rax
0x18000aa46  test    rax, rax
0x18000aa49  jz      short loc_18000AAB5
0x18000aa4b  mov     rcx, [rbx+70h]
0x18000aa4f  mov     r8, [rdx+10h]
0x18000aa53  mov     rax, [rcx]
0x18000aa56  cmp     rax, [r8+0Ch]
0x18000aa5a  jnz     short loc_18000AA66
0x18000aa5c  mov     rax, [rcx+8]
0x18000aa60  cmp     rax, [r8+14h]
0x18000aa64  jz      short loc_18000AA71
0x18000aa66  mov     rdx, [rdx+8]
0x18000aa6a  test    rdx, rdx
0x18000aa6d  jnz     short loc_18000AA4F
0x18000aa6f  jmp     short loc_18000AAB5
0x18000aa71  test    r8, r8
0x18000aa74  jz      short loc_18000AAB5
0x18000aa76  mov     rax, [r8+120h]
0x18000aa7d  lea     rcx, [rbx+50h]
0x18000aa81  mov     rdx, rbx
0x18000aa84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa89  mov     edi, eax
0x18000aa8b  test    eax, eax
0x18000aa8d  js      short loc_18000AAB5
0x18000aa8f  mov     rcx, [rbx+50h]
0x18000aa93  lea     r8, [rbx+58h]
0x18000aa97  mov     rdx, [rcx]
0x18000aa9a  mov     rax, [rdx]
0x18000aa9d  lea     rdx, IID_IDirectSoundSinkSync
0x18000aaa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaa9  test    eax, eax
0x18000aaab  jns     short loc_18000AAB5
0x18000aaad  mov     qword ptr [rbx+58h], 0
0x18000aab5  mov     rbx, [rsp+28h+arg_0]
0x18000aaba  mov     eax, edi
0x18000aabc  mov     rsi, [rsp+28h+arg_8]
0x18000aac1  add     rsp, 20h
0x18000aac5  pop     rdi
0x18000aac6  retn
```
