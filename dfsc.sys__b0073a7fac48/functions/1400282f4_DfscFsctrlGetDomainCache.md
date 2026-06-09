# DfscFsctrlGetDomainCache

- ea: `0x1400282f4`
- end: `0x14002848d`
- name: `DfscFsctrlGetDomainCache`
- size: `409`
- prototype: `__int64 __fastcall(__int64, WCHAR *, unsigned int, __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x140016c84`
- `0x140016de8`
- `0x14001c2e4`
- `0x1400282f4`
- `0x140028f7c`

## pseudocode

```c
__int64 __fastcall DfscFsctrlGetDomainCache(
        __int64 a1,
        WCHAR *a2,
        unsigned int a3,
        __int16 *a4,
        unsigned int a5,
        int a6)
{
  unsigned int v9; // ecx
  unsigned int i; // edx
  __int64 v11; // rcx
  WCHAR *v12; // rax
  __int64 result; // rax
  struct _UNICODE_PREFIX_TABLE *v14; // rax
  struct _UNICODE_PREFIX_TABLE *DomainCache; // rax
  __int64 v16; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING FullName; // [rsp+38h] [rbp-18h] BYREF

  *(_DWORD *)(&FullName.MaximumLength + 1) = 0;
  v16 = 0;
  if ( a3 > 0xFFFE || (a3 & 1) != 0 || !a2 || !a3 || a5 < 2 || !a4 )
    return 3221225485LL;
  if ( a3 > 2 )
  {
    v9 = 0;
    for ( i = a3 >> 1; v9 < i; ++v9 )
    {
      if ( !a2[v9] )
        break;
    }
    if ( v9 >= i )
      return 3221225485LL;
  }
  if ( a3 != 4096 )
    goto LABEL_18;
  v11 = 0x7FFF;
  v12 = a2;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  if ( !v11 )
    return 3221225485LL;
  LOWORD(a3) = v11 != 0 ? -2 - 2 * v11 + 2 : 2;
LABEL_18:
  FullName.Buffer = a2;
  FullName.MaximumLength = a3;
  FullName.Length = a3;
  if ( (unsigned __int16)a3 > 2u && !a2[((unsigned __int64)(unsigned __int16)a3 >> 1) - 1] )
    FullName.Length = a3 - 2;
  result = DfscGetContainerContextFromIrp(a1, &v16);
  if ( (int)result >= 0 )
  {
    if ( *a2 )
    {
      if ( *FullName.Buffer == 42 && (FullName.Length == 2 || !FullName.Buffer[1]) )
      {
        return DfscGetActiveDcInfo(a1, a4, a5, v16);
      }
      else
      {
        DomainCache = (struct _UNICODE_PREFIX_TABLE *)DfscGetDomainCache(v16);
        return DfscGetDcListForDomain(DomainCache, &FullName, a1, a4, a5, a6);
      }
    }
    else
    {
      v14 = (struct _UNICODE_PREFIX_TABLE *)DfscGetDomainCache(v16);
      return DfscGetDomainCacheNames(v14, a1, (unsigned int *)a4, a5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400282f4  push    rbp
0x1400282f6  push    rbx
0x1400282f7  push    rsi
0x1400282f8  push    rdi
0x1400282f9  push    r12
0x1400282fb  push    r14
0x1400282fd  push    r15
0x1400282ff  mov     rbp, rsp
0x140028302  sub     rsp, 50h
0x140028306  xor     r15d, r15d
0x140028309  mov     r10d, 0FFFEh
0x14002830f  mov     dword ptr [rbp+FullName+4], r15d
0x140028313  mov     rsi, r9
0x140028316  mov     [rbp+var_20], r15
0x14002831a  mov     rbx, rdx
0x14002831d  mov     r14, rcx
0x140028320  cmp     r8d, r10d
0x140028323  ja      loc_140028478
0x140028329  test    r8b, 1
0x14002832d  jnz     loc_140028478
0x140028333  test    rdx, rdx
0x140028336  jz      loc_140028478
0x14002833c  test    r8d, r8d
0x14002833f  jz      loc_140028478
0x140028345  mov     edi, [rbp+arg_20]
0x140028348  lea     r12d, [r15+2]
0x14002834c  cmp     edi, r12d
0x14002834f  jb      loc_140028478
0x140028355  test    r9, r9
0x140028358  jz      loc_140028478
0x14002835e  cmp     r8d, r12d
0x140028361  jbe     short loc_140028384
0x140028363  mov     edx, r8d
0x140028366  mov     ecx, r15d
0x140028369  shr     edx, 1
0x14002836b  jz      short loc_14002837C
0x14002836d  mov     eax, ecx
0x14002836f  cmp     [rbx+rax*2], r15w
0x140028374  jz      short loc_14002837C
0x140028376  inc     ecx
0x140028378  cmp     ecx, edx
0x14002837a  jb      short loc_14002836D
0x14002837c  cmp     ecx, edx
0x14002837e  jnb     loc_140028478
0x140028384  cmp     r8d, 1000h
0x14002838b  jnz     short loc_1400283C6
0x14002838d  mov     ecx, 7FFFh
0x140028392  mov     rax, rbx
0x140028395  cmp     [rax], r15w
0x140028399  jz      short loc_1400283A4
0x14002839b  add     rax, r12
0x14002839e  sub     rcx, 1
0x1400283a2  jnz     short loc_140028395
0x1400283a4  test    rcx, rcx
0x1400283a7  jz      loc_140028478
0x1400283ad  movzx   eax, cx
0x1400283b0  add     ax, ax
0x1400283b3  sub     r10w, ax
0x1400283b7  neg     rcx
0x1400283ba  sbb     r8w, r8w
0x1400283be  and     r8w, r10w
0x1400283c2  add     r8w, r12w
0x1400283c6  mov     [rbp+FullName.Buffer], rbx
0x1400283ca  mov     [rbp+FullName.MaximumLength], r8w
0x1400283cf  mov     [rbp+FullName.Length], r8w
0x1400283d4  cmp     r8w, r12w
0x1400283d8  jbe     short loc_1400283F2
0x1400283da  movzx   eax, r8w
0x1400283de  shr     rax, 1
0x1400283e1  cmp     [rbx+rax*2-2], r15w
0x1400283e7  jnz     short loc_1400283F2
0x1400283e9  sub     r8w, r12w
0x1400283ed  mov     [rbp+FullName.Length], r8w
0x1400283f2  lea     rdx, [rbp+var_20]
0x1400283f6  mov     rcx, r14
0x1400283f9  call    DfscGetContainerContextFromIrp
0x1400283fe  test    eax, eax
0x140028400  js      short loc_14002847D
0x140028402  cmp     [rbx], r15w
0x140028406  jnz     short loc_140028424
0x140028408  mov     rcx, [rbp+var_20]
0x14002840c  call    DfscGetDomainCache
0x140028411  mov     rcx, rax; PrefixTable
0x140028414  mov     r9d, edi
0x140028417  mov     r8, rsi
0x14002841a  mov     rdx, r14
0x14002841d  call    DfscGetDomainCacheNames
0x140028422  jmp     short loc_14002847D
0x140028424  mov     rax, [rbp+FullName.Buffer]
0x140028428  cmp     word ptr [rax], 2Ah ; '*'
0x14002842c  jnz     short loc_140028450
0x14002842e  cmp     [rbp+FullName.Length], r12w
0x140028433  jz      short loc_14002843C
0x140028435  cmp     [rax+2], r15w
0x14002843a  jnz     short loc_140028450
0x14002843c  mov     r9, [rbp+var_20]
0x140028440  mov     r8d, edi
0x140028443  mov     rdx, rsi
0x140028446  mov     rcx, r14
0x140028449  call    DfscGetActiveDcInfo
0x14002844e  jmp     short loc_14002847D
0x140028450  mov     rcx, [rbp+var_20]
0x140028454  call    DfscGetDomainCache
0x140028459  mov     rcx, rax; PrefixTable
0x14002845c  lea     rdx, [rbp+FullName]; FullName
0x140028460  mov     eax, [rbp+arg_28]
0x140028463  mov     r9, rsi
0x140028466  mov     [rsp+50h+var_28], eax; int
0x14002846a  mov     r8, r14
0x14002846d  mov     [rsp+50h+var_30], edi; int
0x140028471  call    DfscGetDcListForDomain
0x140028476  jmp     short loc_14002847D
0x140028478  mov     eax, 0C000000Dh
0x14002847d  add     rsp, 50h
0x140028481  pop     r15
0x140028483  pop     r14
0x140028485  pop     r12
0x140028487  pop     rdi
0x140028488  pop     rsi
0x140028489  pop     rbx
0x14002848a  pop     rbp
0x14002848b  retn
```
