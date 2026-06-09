# IsValidMonthlyDateTrigger(_TASK_TRIGGER *)

- ea: `0x18000d470`
- end: `0x18000d4f7`
- name: `?IsValidMonthlyDateTrigger@@YAHPEAU_TASK_TRIGGER@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct _TASK_TRIGGER *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000e2ac`
- `0x180015bb0`

## callees

- `0x18000d470`

## pseudocode

```c
_BOOL8 __fastcall IsValidMonthlyDateTrigger(struct _TASK_TRIGGER *a1)
{
  DWORD rgfDays; // r9d
  int rgfMonths; // r10d
  bool v3; // cl

  rgfDays = a1->Type.MonthlyDate.rgfDays;
  if ( rgfDays > 0x7FFFFFFF )
    return 0;
  rgfMonths = a1->Type.MonthlyDate.rgfMonths;
  if ( (unsigned __int16)(rgfMonths - 1) > 0xFFEu || !rgfDays )
    return 0;
  v3 = 0;
  if ( (rgfMonths & 0xFFFFFAD5) == 0 )
    v3 = (rgfDays & 0x40000000) != 0 && (rgfMonths & 0x52A) != 0;
  return !v3 && ((rgfMonths & 2) == 0 || (rgfMonths & 0xFFFFFFFD) != 0 || (rgfDays & 0x20000000) == 0);
}

```

## disassembly

```asm
0x18000d470  mov     [rsp+arg_0], rbx
0x18000d475  mov     r9d, [rcx+24h]
0x18000d479  cmp     r9d, 7FFFFFFFh
0x18000d480  ja      short loc_18000D4EF
0x18000d482  movzx   r10d, word ptr [rcx+28h]
0x18000d487  mov     ebx, 1
0x18000d48c  movzx   eax, r10w
0x18000d490  mov     ecx, 0FFEh
0x18000d495  sub     ax, bx
0x18000d498  cmp     ax, cx
0x18000d49b  ja      short loc_18000D4EF
0x18000d49d  test    r9d, r9d
0x18000d4a0  jz      short loc_18000D4EF
0x18000d4a2  mov     eax, 52Ah
0x18000d4a7  test    ax, r10w
0x18000d4ab  setnz   dl
0x18000d4ae  bt      r9d, 1Eh
0x18000d4b3  setb    al
0x18000d4b6  xor     ecx, ecx
0x18000d4b8  and     dl, al
0x18000d4ba  test    r10d, 0FFFFFAD5h
0x18000d4c1  movzx   eax, dl
0x18000d4c4  cmovz   ecx, eax
0x18000d4c7  test    cl, cl
0x18000d4c9  jnz     short loc_18000D4EF
0x18000d4cb  test    r10d, 0FFFFFFFDh
0x18000d4d2  setz    dl
0x18000d4d5  bt      r10w, bx
0x18000d4da  setb    cl
0x18000d4dd  and     dl, cl
0x18000d4df  bt      r9d, 1Dh
0x18000d4e4  setb    cl
0x18000d4e7  test    cl, dl
0x18000d4e9  jnz     short loc_18000D4EF
0x18000d4eb  mov     eax, ebx
0x18000d4ed  jmp     short loc_18000D4F1
0x18000d4ef  xor     eax, eax
0x18000d4f1  mov     rbx, [rsp+arg_0]
0x18000d4f6  retn
```
