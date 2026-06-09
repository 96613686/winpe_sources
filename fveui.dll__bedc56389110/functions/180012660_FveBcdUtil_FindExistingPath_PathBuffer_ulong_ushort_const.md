# FveBcdUtil::FindExistingPath(PathBuffer *,ulong,ushort const *)

- ea: `0x180012660`
- end: `0x1800126b2`
- name: `?FindExistingPath@FveBcdUtil@@SA_NPEAVPathBuffer@@KPEBG@Z`
- size: `82`
- prototype: `char __fastcall(LPCWCH *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007360`
- `0x1800132c8`

## callees

- `0x180012660`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180012692`
- `KERNEL32!CompareStringOrdinal` at `0x180012692`

## pseudocode

```c
char __fastcall FveBcdUtil::FindExistingPath(LPCWCH *a1, unsigned int a2, const unsigned __int16 *a3)
{
  char v3; // di
  __int64 i; // rbx

  v3 = 0;
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    if ( CompareStringOrdinal(a1[i], -1, a3, -1, 1) == 2 )
      return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x180012660  push    rbx
0x180012662  push    rbp
0x180012663  push    rsi
0x180012664  push    rdi
0x180012665  push    r14
0x180012667  sub     rsp, 30h
0x18001266b  xor     dil, dil
0x18001266e  mov     rbp, r8
0x180012671  xor     ebx, ebx
0x180012673  mov     esi, edx
0x180012675  mov     r14, rcx
0x180012678  cmp     ebx, esi
0x18001267a  jnb     short loc_1800126A4
0x18001267c  mov     rcx, [r14+rbx*8]; lpString1
0x180012680  or      r9d, 0FFFFFFFFh; cchCount2
0x180012684  or      edx, r9d; cchCount1
0x180012687  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18001268f  mov     r8, rbp; lpString2
0x180012692  call    cs:__imp_CompareStringOrdinal
0x180012698  cmp     eax, 2
0x18001269b  jz      short loc_1800126A1
0x18001269d  inc     ebx
0x18001269f  jmp     short loc_180012678
0x1800126a1  mov     dil, 1
0x1800126a4  mov     al, dil
0x1800126a7  add     rsp, 30h
0x1800126ab  pop     r14
0x1800126ad  pop     rdi
0x1800126ae  pop     rsi
0x1800126af  pop     rbp
0x1800126b0  pop     rbx
0x1800126b1  retn
```
