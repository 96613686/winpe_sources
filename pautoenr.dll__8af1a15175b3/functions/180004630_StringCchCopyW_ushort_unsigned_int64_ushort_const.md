# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004630`
- end: `0x18000469d`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `109`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ed0`
- `0x180004270`
- `0x1800074b0`

## callees

- `0x180004630`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r9
  __int64 v4; // rcx
  unsigned __int16 *v5; // rax
  __int64 result; // rax

  v3 = a1;
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v4;
      --a2;
    }
    while ( a2 );
    v5 = v3 - 1;
    if ( a2 )
      v5 = v3;
    *v5 = 0;
    result = 2147942522LL;
    if ( a2 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004630  mov     r9, rcx
0x180004633  test    rdx, rdx
0x180004636  jz      short loc_18000468C
0x180004638  cmp     rdx, 7FFFFFFFh
0x18000463f  ja      short loc_180004685
0x180004641  mov     ecx, 7FFFFFFEh
0x180004646  test    rcx, rcx
0x180004649  jz      short loc_180004669
0x18000464b  movzx   eax, word ptr [r8]
0x18000464f  test    ax, ax
0x180004652  jz      short loc_180004669
0x180004654  mov     [r9], ax
0x180004658  add     r8, 2
0x18000465c  add     r9, 2
0x180004660  dec     rcx
0x180004663  sub     rdx, 1
0x180004667  jnz     short loc_180004646
0x180004669  test    rdx, rdx
0x18000466c  lea     rax, [r9-2]
0x180004670  cmovnz  rax, r9
0x180004674  xor     ecx, ecx
0x180004676  test    rdx, rdx
0x180004679  mov     [rax], cx
0x18000467c  mov     eax, 8007007Ah
0x180004681  cmovnz  eax, ecx
0x180004684  retn
0x180004685  mov     eax, 80070057h
0x18000468a  jmp     short loc_180004696
0x18000468c  mov     eax, 80070057h
0x180004691  test    rdx, rdx
0x180004694  jz      short locret_180004684
0x180004696  xor     ecx, ecx
0x180004698  mov     [r9], cx
0x18000469c  retn
```
