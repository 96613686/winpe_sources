# HacAcquireLock

- ea: `0x140008140`
- end: `0x1400081dc`
- name: `HacAcquireLock`
- size: `156`
- prototype: `int __fastcall(__int64)`
- caller_count: `61`
- callee_count: `1`
- tags: ``

## callers

- `0x140001100`
- `0x1400029d0`
- `0x140003bd0`
- `0x140004530`
- `0x140005de0`
- `0x1400070a0`
- `0x1400081f0`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x140012c40`
- `0x1400132cc`
- `0x140013dc0`
- `0x140014300`
- `0x1400145f0`
- `0x140014650`
- `0x1400146a0`
- `0x140017d40`
- `0x1400184b8`
- `0x140018804`
- `0x140018a7c`
- `0x140019044`
- `0x1400196a8`
- `0x14001a160`
- `0x14001a478`
- `0x14001a580`
- `0x14001a708`
- `0x14001a820`
- `0x14001add0`
- `0x14001b1c4`
- `0x14001bbbc`
- `0x14001c694`
- `0x14001d6b0`
- `0x14001ea54`
- `0x14001f178`
- `0x14001f9cc`
- `0x1400200d0`
- `0x140020114`
- `0x140020154`
- `0x140020488`
- `0x1400204c0`

## callees

- `0x140008140`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140008160`
- `ntoskrnl!KeWaitForSingleObject` at `0x140008160`

## pseudocode

```c
int __fastcall HacAcquireLock(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx

  LODWORD(v2) = KeWaitForSingleObject(*(PVOID *)(a1 + 40), Executive, 0, 0, 0);
  v3 = *(_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(v3 + 88) )
  {
    if ( *(_QWORD *)(v3 + 96) != a1 )
    {
      v4 = *(_QWORD *)(a1 + 16);
      if ( v4 )
      {
        v5 = *(_QWORD *)(a1 + 24);
        if ( v5 )
        {
          *(_QWORD *)(v5 + 16) = v4;
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = *(_QWORD *)(a1 + 24);
        }
        else
        {
          *(_QWORD *)(v3 + 88) = v4;
          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) = 0;
        }
      }
      *(_QWORD *)(*(_QWORD *)(v3 + 96) + 16LL) = a1;
      v2 = *(_QWORD *)(v3 + 96);
      *(_QWORD *)(a1 + 24) = v2;
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(v3 + 96) = a1;
    }
  }
  else
  {
    *(_QWORD *)(v3 + 88) = a1;
    *(_QWORD *)(v3 + 96) = a1;
  }
  return v2;
}

```

## disassembly

```asm
0x140008140  mov     [rsp+arg_0], rbx
0x140008145  push    rdi
0x140008146  sub     rsp, 30h
0x14000814a  mov     rbx, rcx
0x14000814d  xor     edi, edi
0x14000814f  mov     rcx, [rcx+28h]; Object
0x140008153  xor     r9d, r9d; Alertable
0x140008156  xor     r8d, r8d; WaitMode
0x140008159  mov     [rsp+38h+Timeout], rdi; Timeout
0x14000815e  xor     edx, edx; WaitReason
0x140008160  call    cs:__imp_KeWaitForSingleObject
0x140008167  nop     dword ptr [rax+rax+00h]
0x14000816c  mov     rdx, [rbx+28h]
0x140008170  cmp     [rdx+58h], rdi
0x140008174  jz      short loc_140008188
0x140008176  cmp     [rdx+60h], rbx
0x14000817a  jnz     short loc_140008192
0x14000817c  mov     rbx, [rsp+38h+arg_0]
0x140008181  add     rsp, 30h
0x140008185  pop     rdi
0x140008186  retn
0x140008188  mov     [rdx+58h], rbx
0x14000818c  mov     [rdx+60h], rbx
0x140008190  jmp     short loc_14000817C
0x140008192  mov     rax, [rbx+10h]
0x140008196  test    rax, rax
0x140008199  jz      short loc_1400081B4
0x14000819b  mov     rcx, [rbx+18h]
0x14000819f  test    rcx, rcx
0x1400081a2  jz      short loc_1400081CE
0x1400081a4  mov     [rcx+10h], rax
0x1400081a8  mov     rcx, [rbx+10h]
0x1400081ac  mov     rax, [rbx+18h]
0x1400081b0  mov     [rcx+18h], rax
0x1400081b4  mov     rax, [rdx+60h]
0x1400081b8  mov     [rax+10h], rbx
0x1400081bc  mov     rax, [rdx+60h]
0x1400081c0  mov     [rbx+18h], rax
0x1400081c4  mov     [rbx+10h], rdi
0x1400081c8  mov     [rdx+60h], rbx
0x1400081cc  jmp     short loc_14000817C
0x1400081ce  mov     [rdx+58h], rax
0x1400081d2  mov     rax, [rbx+10h]
0x1400081d6  mov     [rax+18h], rdi
0x1400081da  jmp     short loc_1400081B4
```
