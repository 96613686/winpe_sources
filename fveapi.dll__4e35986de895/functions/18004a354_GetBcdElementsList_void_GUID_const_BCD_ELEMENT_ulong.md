# GetBcdElementsList(void *,_GUID const *,_BCD_ELEMENT * *,ulong *)

- ea: `0x18004a354`
- end: `0x18004a47c`
- name: `?GetBcdElementsList@@YAJPEAXPEBU_GUID@@PEAPEAU_BCD_ELEMENT@@PEAK@Z`
- size: `296`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, struct _BCD_ELEMENT **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18009e740`

## callees

- `0x18000ba30`
- `0x18000ca50`
- `0x18004a354`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18004a454`
- `bcd!BcdCloseObject` at `0x18004a454`
- `bcd!BcdOpenObject` at `0x18004a395`
- `bcd!BcdOpenObject` at `0x18004a395`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18004a3cb`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18004a424`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18004a3cb`
- `bcd!BcdEnumerateAndUnpackElements` at `0x18004a424`

## pseudocode

```c
__int64 __fastcall GetBcdElementsList(void *a1, const struct _GUID *a2, struct _BCD_ELEMENT **a3, unsigned int *a4)
{
  int v7; // ebx
  int v8; // eax
  void *v9; // rdi
  unsigned int v10; // eax
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+40h] [rbp-18h]

  v12 = 0;
  v13 = 0;
  v7 = BcdOpenObject(a1, a2, &v12);
  if ( v7 >= 0 )
  {
    v8 = BcdEnumerateAndUnpackElements(a1, v12, 30);
    v7 = v8;
    if ( v8 == -1073741789 )
    {
      v9 = CFveApiBase::FastAlloc(0);
      if ( v9 )
      {
        v7 = BcdEnumerateAndUnpackElements(a1, v12, 30);
        if ( v7 < 0 )
        {
          CFveApiBase::FastFree(v9);
        }
        else
        {
          v10 = v13;
          v7 = 0;
          *a3 = (struct _BCD_ELEMENT *)v9;
          *a4 = v10;
        }
      }
      else
      {
        v7 = -1073741801;
      }
    }
    else if ( v8 >= 0 )
    {
      v7 = -1073741811;
    }
  }
  if ( v12 )
    BcdCloseObject(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004a354  push    rbp
0x18004a356  push    rbx
0x18004a357  push    rsi
0x18004a358  push    rdi
0x18004a359  push    r14
0x18004a35b  push    r15
0x18004a35d  mov     rbp, rsp
0x18004a360  sub     rsp, 58h
0x18004a364  mov     rax, cs:__security_cookie
0x18004a36b  xor     rax, rsp
0x18004a36e  mov     [rbp+var_10], rax
0x18004a372  mov     r14, r8
0x18004a375  mov     dword ptr [rbp+var_28], 0
0x18004a37c  lea     r8, [rbp+var_20]
0x18004a380  mov     [rbp+var_20], 0
0x18004a388  mov     r15, r9
0x18004a38b  mov     [rbp+var_18], 0
0x18004a392  mov     rsi, rcx
0x18004a395  call    cs:__imp_BcdOpenObject
0x18004a39c  nop     dword ptr [rax+rax+00h]
0x18004a3a1  mov     ebx, eax
0x18004a3a3  test    eax, eax
0x18004a3a5  js      loc_18004A44B
0x18004a3ab  mov     rdx, [rbp+var_20]
0x18004a3af  lea     rax, [rbp+var_18]
0x18004a3b3  mov     [rsp+58h+var_30], rax
0x18004a3b8  xor     r9d, r9d
0x18004a3bb  lea     rax, [rbp+var_28]
0x18004a3bf  mov     rcx, rsi
0x18004a3c2  mov     [rsp+58h+var_38], rax
0x18004a3c7  lea     r8d, [r9+1Eh]
0x18004a3cb  call    cs:__imp_BcdEnumerateAndUnpackElements
0x18004a3d2  nop     dword ptr [rax+rax+00h]
0x18004a3d7  mov     ebx, eax
0x18004a3d9  cmp     eax, 0C0000023h
0x18004a3de  jz      short loc_18004A3EB
0x18004a3e0  test    eax, eax
0x18004a3e2  js      short loc_18004A44B
0x18004a3e4  mov     ebx, 0C000000Dh
0x18004a3e9  jmp     short loc_18004A44B
0x18004a3eb  mov     ecx, dword ptr [rbp+var_28]; unsigned __int64
0x18004a3ee  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x18004a3f3  mov     rdi, rax
0x18004a3f6  test    rax, rax
0x18004a3f9  jnz     short loc_18004A402
0x18004a3fb  mov     ebx, 0C0000017h
0x18004a400  jmp     short loc_18004A44B
0x18004a402  mov     rdx, [rbp+var_20]
0x18004a406  lea     rax, [rbp+var_18]
0x18004a40a  mov     [rsp+58h+var_30], rax
0x18004a40f  mov     r9, rdi
0x18004a412  lea     rax, [rbp+var_28]
0x18004a416  mov     r8d, 1Eh
0x18004a41c  mov     rcx, rsi
0x18004a41f  mov     [rsp+58h+var_38], rax
0x18004a424  call    cs:__imp_BcdEnumerateAndUnpackElements
0x18004a42b  nop     dword ptr [rax+rax+00h]
0x18004a430  mov     ebx, eax
0x18004a432  test    eax, eax
0x18004a434  js      short loc_18004A443
0x18004a436  mov     eax, [rbp+var_18]
0x18004a439  xor     ebx, ebx
0x18004a43b  mov     [r14], rdi
0x18004a43e  mov     [r15], eax
0x18004a441  jmp     short loc_18004A44B
0x18004a443  mov     rcx, rdi; lpMem
0x18004a446  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18004a44b  mov     rcx, [rbp+var_20]
0x18004a44f  test    rcx, rcx
0x18004a452  jz      short loc_18004A460
0x18004a454  call    cs:__imp_BcdCloseObject
0x18004a45b  nop     dword ptr [rax+rax+00h]
0x18004a460  mov     eax, ebx
0x18004a462  mov     rcx, [rbp+var_10]
0x18004a466  xor     rcx, rsp; StackCookie
0x18004a469  call    __security_check_cookie
0x18004a46e  add     rsp, 58h
0x18004a472  pop     r15
0x18004a474  pop     r14
0x18004a476  pop     rdi
0x18004a477  pop     rsi
0x18004a478  pop     rbx
0x18004a479  pop     rbp
0x18004a47a  retn
```
