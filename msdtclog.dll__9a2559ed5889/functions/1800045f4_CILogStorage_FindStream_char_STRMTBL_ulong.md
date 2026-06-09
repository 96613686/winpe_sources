# CILogStorage::FindStream(char *,_STRMTBL * *,ulong *)

- ea: `0x1800045f4`
- end: `0x1800046b9`
- name: `?FindStream@CILogStorage@@AEAAJPEADPEAPEAU_STRMTBL@@PEAK@Z`
- size: `197`
- prototype: `__int64 __fastcall(CILogStorage *__hidden this, char *, struct _STRMTBL **, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002370`
- `0x180002400`
- `0x1800047b0`

## callees

- `0x1800045f4`

## pseudocode

```c
__int64 __fastcall CILogStorage::FindStream(CILogStorage *this, char *a2, struct _STRMTBL **a3, unsigned int *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r11
  struct _STRMTBL *v9; // rdx
  int v10; // r9d
  unsigned __int16 v11; // r10
  char *v12; // rax
  int v13; // ebx
  int v14; // ecx
  __int64 result; // rax

  if ( !a3 || !a2 )
    return 2147942487LL;
  v7 = *((_QWORD *)this + 1);
  v8 = *(_QWORD *)(v7 + 400);
  if ( v8 && (v9 = *(struct _STRMTBL **)(v7 + 296), v10 = 0, v11 = 0, *(_WORD *)(v8 + 88)) )
  {
    while ( !v10 )
    {
      v12 = a2;
      do
      {
        v13 = (unsigned __int8)v12[v9 - (struct _STRMTBL *)a2];
        v14 = (unsigned __int8)*v12 - v13;
        if ( v14 )
          break;
        ++v12;
      }
      while ( v13 );
      if ( v14 )
      {
        v9 = (struct _STRMTBL *)((char *)v9 + 44);
      }
      else
      {
        v10 = 1;
        *a4 = v11 + 1;
        *a3 = v9;
      }
      if ( ++v11 >= *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 400LL) + 88LL) )
      {
        if ( !v10 )
          goto LABEL_15;
        return 0;
      }
    }
    return 0;
  }
  else
  {
LABEL_15:
    *a3 = 0;
    result = 1;
    *a4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800045f4  push    rbx
0x1800045f6  push    rbp
0x1800045f7  push    rsi
0x1800045f8  push    rdi
0x1800045f9  push    r14
0x1800045fb  mov     rdi, r9
0x1800045fe  mov     rsi, rdx
0x180004601  mov     rbp, rcx
0x180004604  test    r8, r8
0x180004607  jz      loc_1800046AD
0x18000460d  test    rdx, rdx
0x180004610  jz      loc_1800046AD
0x180004616  mov     rdx, [rcx+8]
0x18000461a  mov     r14d, 1
0x180004620  mov     r11, [rdx+190h]
0x180004627  test    r11, r11
0x18000462a  jz      short loc_18000469B
0x18000462c  mov     rdx, [rdx+128h]
0x180004633  xor     r9d, r9d
0x180004636  xor     r10d, r10d
0x180004639  xor     eax, eax
0x18000463b  cmp     ax, [r11+58h]
0x180004640  jnb     short loc_18000469B
0x180004642  test    r9d, r9d
0x180004645  jnz     short loc_180004697
0x180004647  mov     r11, rdx
0x18000464a  mov     rax, rsi
0x18000464d  sub     r11, rsi
0x180004650  movzx   ecx, byte ptr [rax]
0x180004653  movzx   ebx, byte ptr [rax+r11]
0x180004658  sub     ecx, ebx
0x18000465a  jnz     short loc_180004663
0x18000465c  add     rax, r14
0x18000465f  test    ebx, ebx
0x180004661  jnz     short loc_180004650
0x180004663  test    ecx, ecx
0x180004665  jnz     short loc_180004678
0x180004667  movzx   eax, r10w
0x18000466b  mov     r9d, r14d
0x18000466e  add     eax, r14d
0x180004671  mov     [rdi], eax
0x180004673  mov     [r8], rdx
0x180004676  jmp     short loc_18000467C
0x180004678  add     rdx, 2Ch ; ','
0x18000467c  mov     rax, [rbp+8]
0x180004680  add     r10w, r14w
0x180004684  mov     rcx, [rax+190h]
0x18000468b  cmp     r10w, [rcx+58h]
0x180004690  jb      short loc_180004642
0x180004692  test    r9d, r9d
0x180004695  jz      short loc_18000469B
0x180004697  xor     eax, eax
0x180004699  jmp     short loc_1800046B2
0x18000469b  mov     qword ptr [r8], 0
0x1800046a2  mov     eax, r14d
0x1800046a5  mov     dword ptr [rdi], 0
0x1800046ab  jmp     short loc_1800046B2
0x1800046ad  mov     eax, 80070057h
0x1800046b2  pop     r14
0x1800046b4  pop     rdi
0x1800046b5  pop     rsi
0x1800046b6  pop     rbp
0x1800046b7  pop     rbx
0x1800046b8  retn
```
