# CEASConsentPopup::Invoke(IPopupWindow *,IPopupCommand *)

- ea: `0x1800021c0`
- end: `0x180002223`
- name: `?Invoke@CEASConsentPopup@@UEAAJPEAUIPopupWindow@@PEAUIPopupCommand@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(CEASConsentPopup *__hidden this, struct IPopupWindow *, struct IPopupCommand *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800021c0`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CEASConsentPopup::Invoke(CEASConsentPopup *this, struct IPopupWindow *a2, struct IPopupCommand *a3)
{
  int v3; // ebx
  __int64 v5; // rax
  int v7; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  if ( a3 )
  {
    v5 = *(_QWORD *)a3;
    v7 = 0;
    v3 = (*(__int64 (__fastcall **)(struct IPopupCommand *, int *))(v5 + 32))(a3, &v7);
    if ( v3 >= 0 && v7 == 10003 )
      *((_DWORD *)this + 4) = 1;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 296LL))(*((_QWORD *)this + 3));
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800021c0  mov     [rsp+arg_0], rbx
0x1800021c5  push    rdi
0x1800021c6  sub     rsp, 20h
0x1800021ca  xor     ebx, ebx
0x1800021cc  mov     rdi, rcx
0x1800021cf  test    r8, r8
0x1800021d2  jz      short loc_180002216
0x1800021d4  mov     rax, [r8]
0x1800021d7  lea     rdx, [rsp+28h+arg_10]
0x1800021dc  mov     rcx, r8
0x1800021df  mov     [rsp+28h+arg_10], ebx
0x1800021e3  mov     rax, [rax+20h]
0x1800021e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ec  mov     ebx, eax
0x1800021ee  test    eax, eax
0x1800021f0  js      short loc_180002203
0x1800021f2  cmp     [rsp+28h+arg_10], 2713h
0x1800021fa  jnz     short loc_180002203
0x1800021fc  mov     dword ptr [rdi+10h], 1
0x180002203  mov     rcx, [rdi+18h]
0x180002207  mov     rdx, [rcx]
0x18000220a  mov     rax, [rdx+128h]
0x180002211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002216  mov     eax, ebx
0x180002218  mov     rbx, [rsp+28h+arg_0]
0x18000221d  add     rsp, 20h
0x180002221  pop     rdi
0x180002222  retn
```
