# wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)

- ea: `0x1800085b0`
- end: `0x180008611`
- name: `??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details::ThreadFailureCallbackHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007cd0`
- `0x180015cd0`

## callees

- `0x1800085b0`
- `0x18000eb14`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800085bf`
- `KERNEL32!GetCurrentThreadId` at `0x1800085bf`

## pseudocode

```c
void __fastcall wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(
        wil::details::ThreadFailureCallbackHolder *this)
{
  void *v2; // rdx
  unsigned int v3; // r8d
  wil::details::ThreadFailureCallbackHolder **v4; // rcx
  wil::details::ThreadFailureCallbackHolder *v5; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_DWORD *)this + 6) )
  {
    if ( *((_DWORD *)this + 6) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v2, v3, (const char *)0x8007029CLL, v6);
    *((_DWORD *)this + 6) = 0;
    v4 = *(wil::details::ThreadFailureCallbackHolder ***)this;
    while ( 1 )
    {
      v5 = *v4;
      if ( !*v4 )
        break;
      if ( v5 == this )
      {
        *v4 = (wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)this + 2);
        break;
      }
      v4 = (wil::details::ThreadFailureCallbackHolder **)((char *)v5 + 16);
      *(_QWORD *)this = (char *)v5 + 16;
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800085b0  push    rbx; int
0x1800085b2  sub     rsp, 20h
0x1800085b6  cmp     dword ptr [rcx+18h], 0
0x1800085ba  mov     rbx, rcx
0x1800085bd  jz      short loc_18000860A
0x1800085bf  call    cs:__imp_GetCurrentThreadId
0x1800085c6  nop     dword ptr [rax+rax+00h]
0x1800085cb  cmp     [rbx+18h], eax
0x1800085ce  jz      short loc_1800085E0
0x1800085d0  mov     rcx, [rsp+28h]; this
0x1800085d5  mov     r9d, 8007029Ch; char *
0x1800085db  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800085e0  and     dword ptr [rbx+18h], 0
0x1800085e4  mov     rcx, [rbx]
0x1800085e7  jmp     short loc_1800085F5
0x1800085e9  cmp     rax, rbx
0x1800085ec  jz      short loc_1800085FF
0x1800085ee  lea     rcx, [rax+10h]
0x1800085f2  mov     [rbx], rcx
0x1800085f5  mov     rax, [rcx]
0x1800085f8  test    rax, rax
0x1800085fb  jnz     short loc_1800085E9
0x1800085fd  jmp     short loc_180008606
0x1800085ff  mov     rax, [rbx+10h]
0x180008603  mov     [rcx], rax
0x180008606  and     qword ptr [rbx], 0
0x18000860a  add     rsp, 20h
0x18000860e  pop     rbx
0x18000860f  retn
```
