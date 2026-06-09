# W3_REQUEST::CopyBasics(W3_REQUEST *)

- ea: `0x180029244`
- end: `0x1800293b5`
- name: `?CopyBasics@W3_REQUEST@@QEAAJPEAV1@@Z`
- size: `369`
- prototype: `__int64 __fastcall(W3_REQUEST *__hidden this, struct W3_REQUEST *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002910c`

## callees

- `0x180029244`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180029376`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180029376`

## pseudocode

```c
int __fastcall W3_REQUEST::CopyBasics(W3_REQUEST *this, struct W3_REQUEST *a2)
{
  __int64 v4; // rdx
  int result; // eax
  __int64 v6; // rcx

  if ( a2 )
  {
    ++*((_DWORD *)a2 + 12);
    v4 = *((_QWORD *)a2 + 5);
    *(_DWORD *)(*((_QWORD *)this + 5) + 36LL) = *(_DWORD *)(v4 + 36);
    *(_WORD *)(*((_QWORD *)this + 5) + 40LL) = *(_WORD *)(v4 + 40);
    *(_QWORD *)(*((_QWORD *)this + 5) + 48LL) = *(_QWORD *)(v4 + 48);
    *(_WORD *)(*((_QWORD *)this + 5) + 42LL) = *(_WORD *)(v4 + 42);
    *(_QWORD *)(*((_QWORD *)this + 5) + 56LL) = *(_QWORD *)(v4 + 56);
    *(_WORD *)(*((_QWORD *)this + 5) + 64LL) = *(_WORD *)(v4 + 64);
    *(_QWORD *)(*((_QWORD *)this + 5) + 72LL) = *(_QWORD *)(v4 + 72);
    *(_WORD *)(*((_QWORD *)this + 5) + 66LL) = *(_WORD *)(v4 + 66);
    *(_QWORD *)(*((_QWORD *)this + 5) + 80LL) = *(_QWORD *)(v4 + 80);
    *(_WORD *)(*((_QWORD *)this + 5) + 68LL) = *(_WORD *)(v4 + 68);
    *(_QWORD *)(*((_QWORD *)this + 5) + 88LL) = *(_QWORD *)(v4 + 88);
    *(_WORD *)(*((_QWORD *)this + 5) + 70LL) = *(_WORD *)(v4 + 70);
    *(_QWORD *)(*((_QWORD *)this + 5) + 96LL) = *(_QWORD *)(v4 + 96);
    result = STRU::Copy((W3_REQUEST *)((char *)this + 56), (struct W3_REQUEST *)((char *)a2 + 56));
    if ( result < 0 )
      return result;
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)this + 5) + 36LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 40LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 48LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 42LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 56LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 64LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 72LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 66LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 80LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 68LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 88LL) = 0;
    *(_WORD *)(*((_QWORD *)this + 5) + 70LL) = 0;
    *(_QWORD *)(*((_QWORD *)this + 5) + 96LL) = 0;
  }
  v6 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 28) = *(_QWORD *)(v6 + 72);
  *((_QWORD *)this + 29) = *(_QWORD *)(v6 + 88);
  *((_DWORD *)this + 60) = *(unsigned __int16 *)(v6 + 64) >> 1;
  return 0;
}

```

## disassembly

```asm
0x180029244  push    rbx
0x180029246  sub     rsp, 20h
0x18002924a  mov     r8, rdx
0x18002924d  mov     rbx, rcx
0x180029250  test    rdx, rdx
0x180029253  jnz     short loc_1800292CD
0x180029255  mov     rax, [rcx+28h]
0x180029259  mov     [rax+24h], edx
0x18002925c  xor     eax, eax
0x18002925e  mov     rdx, [rcx+28h]
0x180029262  mov     [rdx+28h], ax
0x180029266  mov     rax, [rcx+28h]
0x18002926a  mov     [rax+30h], r8
0x18002926e  xor     eax, eax
0x180029270  mov     rdx, [rcx+28h]
0x180029274  mov     [rdx+2Ah], ax
0x180029278  mov     rax, [rcx+28h]
0x18002927c  mov     [rax+38h], r8
0x180029280  xor     eax, eax
0x180029282  mov     rcx, [rcx+28h]
0x180029286  mov     [rcx+40h], ax
0x18002928a  mov     rax, [rbx+28h]
0x18002928e  mov     [rax+48h], r8
0x180029292  xor     eax, eax
0x180029294  mov     rcx, [rbx+28h]
0x180029298  mov     [rcx+42h], ax
0x18002929c  mov     rax, [rbx+28h]
0x1800292a0  mov     [rax+50h], r8
0x1800292a4  xor     eax, eax
0x1800292a6  mov     rcx, [rbx+28h]
0x1800292aa  mov     [rcx+44h], ax
0x1800292ae  mov     rax, [rbx+28h]
0x1800292b2  mov     [rax+58h], r8
0x1800292b6  xor     eax, eax
0x1800292b8  mov     rcx, [rbx+28h]
0x1800292bc  mov     [rcx+46h], ax
0x1800292c0  mov     rax, [rbx+28h]
0x1800292c4  mov     [rax+60h], r8
0x1800292c8  jmp     loc_180029386
0x1800292cd  inc     dword ptr [rdx+30h]
0x1800292d0  mov     rdx, [rdx+28h]
0x1800292d4  mov     rcx, [rcx+28h]
0x1800292d8  mov     eax, [rdx+24h]
0x1800292db  mov     [rcx+24h], eax
0x1800292de  movzx   eax, word ptr [rdx+28h]
0x1800292e2  mov     rcx, [rbx+28h]
0x1800292e6  mov     [rcx+28h], ax
0x1800292ea  mov     rax, [rdx+30h]
0x1800292ee  mov     rcx, [rbx+28h]
0x1800292f2  mov     [rcx+30h], rax
0x1800292f6  movzx   eax, word ptr [rdx+2Ah]
0x1800292fa  mov     rcx, [rbx+28h]
0x1800292fe  mov     [rcx+2Ah], ax
0x180029302  mov     rax, [rdx+38h]
0x180029306  mov     rcx, [rbx+28h]
0x18002930a  mov     [rcx+38h], rax
0x18002930e  movzx   eax, word ptr [rdx+40h]
0x180029312  mov     rcx, [rbx+28h]
0x180029316  mov     [rcx+40h], ax
0x18002931a  mov     rax, [rdx+48h]
0x18002931e  mov     rcx, [rbx+28h]
0x180029322  mov     [rcx+48h], rax
0x180029326  movzx   eax, word ptr [rdx+42h]
0x18002932a  mov     rcx, [rbx+28h]
0x18002932e  mov     [rcx+42h], ax
0x180029332  mov     rax, [rdx+50h]
0x180029336  mov     rcx, [rbx+28h]
0x18002933a  mov     [rcx+50h], rax
0x18002933e  movzx   eax, word ptr [rdx+44h]
0x180029342  mov     rcx, [rbx+28h]
0x180029346  mov     [rcx+44h], ax
0x18002934a  mov     rax, [rdx+58h]
0x18002934e  mov     rcx, [rbx+28h]
0x180029352  mov     [rcx+58h], rax
0x180029356  movzx   eax, word ptr [rdx+46h]
0x18002935a  mov     rcx, [rbx+28h]
0x18002935e  mov     [rcx+46h], ax
0x180029362  mov     rcx, [rbx+28h]
0x180029366  mov     rax, [rdx+60h]
0x18002936a  lea     rdx, [r8+38h]
0x18002936e  mov     [rcx+60h], rax
0x180029372  lea     rcx, [rbx+38h]
0x180029376  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002937d  nop     dword ptr [rax+rax+00h]
0x180029382  test    eax, eax
0x180029384  js      short loc_1800293AE
0x180029386  mov     rcx, [rbx+28h]
0x18002938a  mov     rax, [rcx+48h]
0x18002938e  mov     [rbx+0E0h], rax
0x180029395  mov     rax, [rcx+58h]
0x180029399  mov     [rbx+0E8h], rax
0x1800293a0  movzx   eax, word ptr [rcx+40h]
0x1800293a4  shr     eax, 1
0x1800293a6  mov     [rbx+0F0h], eax
0x1800293ac  xor     eax, eax
0x1800293ae  add     rsp, 20h
0x1800293b2  pop     rbx
0x1800293b3  retn
```
