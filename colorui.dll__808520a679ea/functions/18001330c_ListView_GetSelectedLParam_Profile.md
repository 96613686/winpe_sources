# ListView::GetSelectedLParam(Profile * *)

- ea: `0x18001330c`
- end: `0x180013369`
- name: `?GetSelectedLParam@ListView@@QEBAJPEAPEAUProfile@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(HWND *this, struct Profile **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dcdc`
- `0x18000dfe4`
- `0x18000ef00`
- `0x18000f654`

## callees

- `0x1800131ec`
- `0x18001327c`
- `0x18001330c`

## pseudocode

```c
__int64 __fastcall ListView::GetSelectedLParam(HWND *this, struct Profile **a2)
{
  __int64 result; // rax
  int v5; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v5 = 0;
  result = ListView::GetSelectedItemIndex(this, (unsigned int *)&v5);
  if ( (int)result >= 0 )
  {
    if ( v5 == -1 )
      return 1;
    else
      return ListView::GetItemLParam(this, v5, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18001330c  mov     [rsp+arg_0], rbx
0x180013311  push    rdi
0x180013312  sub     rsp, 20h
0x180013316  mov     rbx, rdx
0x180013319  mov     rdi, rcx
0x18001331c  test    rdx, rdx
0x18001331f  jnz     short loc_180013328
0x180013321  mov     eax, 80070057h
0x180013326  jmp     short loc_18001335E
0x180013328  mov     qword ptr [rdx], 0
0x18001332f  lea     rdx, [rsp+28h+arg_8]; int *
0x180013334  mov     [rsp+28h+arg_8], 0
0x18001333c  call    ?GetSelectedItemIndex@ListView@@QEBAJPEAH@Z; ListView::GetSelectedItemIndex(int *)
0x180013341  test    eax, eax
0x180013343  js      short loc_18001335E
0x180013345  mov     edx, [rsp+28h+arg_8]; int
0x180013349  cmp     edx, 0FFFFFFFFh
0x18001334c  jnz     short loc_180013353
0x18001334e  lea     eax, [rdx+2]
0x180013351  jmp     short loc_18001335E
0x180013353  mov     r8, rbx; struct Profile **
0x180013356  mov     rcx, rdi; this
0x180013359  call    ?GetItemLParam@ListView@@QEBAJHPEAPEAUProfile@@@Z; ListView::GetItemLParam(int,Profile * *)
0x18001335e  mov     rbx, [rsp+28h+arg_0]
0x180013363  add     rsp, 20h
0x180013367  pop     rdi
0x180013368  retn
```
