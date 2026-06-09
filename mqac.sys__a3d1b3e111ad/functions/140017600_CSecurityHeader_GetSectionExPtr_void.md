# CSecurityHeader::GetSectionExPtr(void)

- ea: `0x140017600`
- end: `0x14001768c`
- name: `?GetSectionExPtr@CSecurityHeader@@AEBAPEBEXZ`
- size: `140`
- prototype: `const unsigned __int8 *__fastcall(CSecurityHeader *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012dc4`

## callees

- `0x140017600`

## pseudocode

```c
const unsigned __int8 *__fastcall CSecurityHeader::GetSectionExPtr(CSecurityHeader *this)
{
  const unsigned __int8 *result; // rax
  int v2; // edx
  const unsigned __int8 *v3; // rdx
  unsigned __int64 i; // rax

  if ( (*(_WORD *)this & 0x80u) == 0 )
    return 0;
  v2 = *((unsigned __int16 *)this + 3);
  result = (const unsigned __int8 *)this
         + ((v2 + 3) & 0xFFFFFFFC)
         + ((*((unsigned __int16 *)this + 1) + 3) & 0xFFFFFFFC)
         + ((*((unsigned __int16 *)this + 2) + 3) & 0xFFFFFFFC)
         + ((*((_DWORD *)this + 2) + 3) & 0xFFFFFFFC)
         + 16;
  if ( (_WORD)v2 && (*(_WORD *)this & 0x40) == 0 )
  {
    v3 = result + 4;
    for ( i = 0; i < (unsigned __int64)(unsigned int)(*((_DWORD *)this + 3) - 4) >> 1; ++i )
    {
      if ( !*(_WORD *)&v3[2 * i] )
        break;
    }
    return (const unsigned __int8 *)((unsigned __int64)&v3[2 * i + 5] & 0xFFFFFFFFFFFFFFFCuLL);
  }
  return result;
}

```

## disassembly

```asm
0x140017600  movzx   r9d, word ptr [rcx]
0x140017604  mov     r8, rcx
0x140017607  test    r9b, r9b
0x14001760a  js      short loc_140017610
0x14001760c  xor     eax, eax
0x14001760e  retn
0x140017610  movzx   edx, word ptr [rcx+6]
0x140017614  mov     r10d, 0FFFFFFFCh
0x14001761a  movzx   ecx, word ptr [rcx+4]
0x14001761e  movzx   eax, word ptr [r8+2]
0x140017623  add     ecx, 3
0x140017626  add     eax, 3
0x140017629  and     ecx, r10d
0x14001762c  and     eax, r10d
0x14001762f  add     ecx, eax
0x140017631  lea     eax, [rdx+3]
0x140017634  and     eax, r10d
0x140017637  add     ecx, eax
0x140017639  mov     eax, [r8+8]
0x14001763d  add     eax, 3
0x140017640  and     eax, r10d
0x140017643  xor     r10d, r10d
0x140017646  add     eax, ecx
0x140017648  add     rax, 10h
0x14001764c  add     rax, r8
0x14001764f  test    dx, dx
0x140017652  jz      short locret_14001768B
0x140017654  test    r9b, 40h
0x140017658  jnz     short locret_14001768B
0x14001765a  mov     ecx, [r8+0Ch]
0x14001765e  lea     rdx, [rax+4]
0x140017662  sub     ecx, 4
0x140017665  mov     eax, r10d
0x140017668  shr     rcx, 1
0x14001766b  jz      short loc_14001767C
0x14001766d  cmp     [rdx+rax*2], r10w
0x140017672  jz      short loc_14001767C
0x140017674  inc     rax
0x140017677  cmp     rax, rcx
0x14001767a  jb      short loc_14001766D
0x14001767c  lea     rax, ds:5[rax*2]
0x140017684  add     rax, rdx
0x140017687  and     rax, 0FFFFFFFFFFFFFFFCh
0x14001768b  retn
```
