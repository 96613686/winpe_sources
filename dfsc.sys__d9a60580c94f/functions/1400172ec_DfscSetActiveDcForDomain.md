# DfscSetActiveDcForDomain

- ea: `0x1400172ec`
- end: `0x14001744f`
- name: `DfscSetActiveDcForDomain`
- size: `355`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140016b80`

## callees

- `0x140001df8`
- `0x140005a70`
- `0x1400172ec`
- `0x14001c270`
- `0x14001c2e4`
- `0x14001d090`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400173b8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400173b8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001737e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001737e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017372`
- `ntoskrnl!ExReleaseResourceLite` at `0x140017372`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001734a`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001734a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017335`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140017335`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001731e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001731e`

## pseudocode

```c
__int64 __fastcall DfscSetActiveDcForDomain(__int64 a1, const UNICODE_STRING *a2, UNICODE_STRING *a3)
{
  volatile signed __int32 *p_RightChild; // rdi
  __int64 DomainCache; // rbx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  unsigned __int16 i; // bx
  int IsDomainController; // ebx
  volatile signed __int32 *v12; // rax
  struct _UNICODE_STRING *v13; // [rsp+30h] [rbp-38h] BYREF
  char v14; // [rsp+88h] [rbp+20h] BYREF

  p_RightChild = 0;
  v13 = 0;
  v14 = 0;
  DomainCache = DfscGetDomainCache(a1);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(DomainCache + 56), 1u);
  UnicodePrefix = RtlFindUnicodePrefix((PUNICODE_PREFIX_TABLE)DomainCache, a2, 0);
  if ( UnicodePrefix )
  {
    p_RightChild = (volatile signed __int32 *)&UnicodePrefix[-2].Links.RightChild;
    if ( (BYTE4(UnicodePrefix[-2].Prefix) & 1) != 0 )
      _InterlockedAdd(p_RightChild + 1, 1u);
    else
      p_RightChild = 0;
  }
  ExReleaseResourceLite((PERESOURCE)(DomainCache + 56));
  KeLeaveCriticalRegion();
  if ( !p_RightChild )
    return 3221226021LL;
  for ( i = 0; i < *((_WORD *)p_RightChild + 12); ++i )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)&p_RightChild[28 * i + 64], a3, 1u) )
    {
      *((_WORD *)p_RightChild + 13) = i;
      IsDomainController = 0;
      *((_BYTE *)p_RightChild + 14) = 1;
      goto LABEL_16;
    }
  }
  IsDomainController = DfscIsDomainController(a2, a3, &v14);
  if ( IsDomainController >= 0 && v14 )
  {
    IsDomainController = DfscRmGenerateDomainDcReferralFromDCName(a2, (const void **)a3, &v13, 1, 1);
    if ( IsDomainController >= 0 )
    {
      v12 = (volatile signed __int32 *)DfscDomainCacheStore(a1, (ULONG_PTR)v13);
      DfscRmDereferenceReferral(v12);
    }
  }
LABEL_16:
  DfscRmDereferenceReferral(p_RightChild);
  return (unsigned int)IsDomainController;
}

```

## disassembly

```asm
0x1400172ec  mov     rax, rsp
0x1400172ef  mov     [rax+8], rbx
0x1400172f3  mov     [rax+10h], rbp
0x1400172f7  push    rsi
0x1400172f8  push    rdi
0x1400172f9  push    r13
0x1400172fb  push    r14
0x1400172fd  push    r15
0x1400172ff  sub     rsp, 40h
0x140017303  xor     edi, edi
0x140017305  mov     rsi, r8
0x140017308  mov     [rax-38h], rdi
0x14001730c  mov     rbp, rdx
0x14001730f  mov     [rax+20h], dil
0x140017313  mov     r15, rcx
0x140017316  call    DfscGetDomainCache
0x14001731b  mov     rbx, rax
0x14001731e  call    cs:__imp_KeEnterCriticalRegion
0x140017325  nop     dword ptr [rax+rax+00h]
0x14001732a  lea     r13d, [rdi+1]
0x14001732e  mov     dl, r13b; Wait
0x140017331  lea     rcx, [rbx+38h]; Resource
0x140017335  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001733c  nop     dword ptr [rax+rax+00h]
0x140017341  xor     r8d, r8d; CaseInsensitiveIndex
0x140017344  mov     rdx, rbp; FullName
0x140017347  mov     rcx, rbx; PrefixTable
0x14001734a  call    cs:__imp_RtlFindUnicodePrefix
0x140017351  nop     dword ptr [rax+rax+00h]
0x140017356  test    rax, rax
0x140017359  jz      short loc_14001736E
0x14001735b  lea     rdi, [rax-48h]
0x14001735f  test    [rdi+0Ch], r13b
0x140017363  jz      short loc_14001736C
0x140017365  lock add [rdi+4], r13d
0x14001736a  jmp     short loc_14001736E
0x14001736c  xor     edi, edi
0x14001736e  lea     rcx, [rbx+38h]; Resource
0x140017372  call    cs:__imp_ExReleaseResourceLite
0x140017379  nop     dword ptr [rax+rax+00h]
0x14001737e  call    cs:__imp_KeLeaveCriticalRegion
0x140017385  nop     dword ptr [rax+rax+00h]
0x14001738a  test    rdi, rdi
0x14001738d  jnz     short loc_140017399
0x14001738f  mov     eax, 0C0000225h
0x140017394  jmp     loc_140017437
0x140017399  xor     ebx, ebx
0x14001739b  mov     rdx, rsi; String2
0x14001739e  cmp     bx, [rdi+18h]
0x1400173a2  jnb     short loc_1400173DA
0x1400173a4  movzx   eax, bx
0x1400173a7  mov     r8b, r13b; CaseInSensitive
0x1400173aa  imul    rcx, rax, 70h ; 'p'
0x1400173ae  add     rcx, 100h
0x1400173b5  add     rcx, rdi; String1
0x1400173b8  call    cs:__imp_RtlCompareUnicodeString
0x1400173bf  nop     dword ptr [rax+rax+00h]
0x1400173c4  test    eax, eax
0x1400173c6  jz      short loc_1400173CE
0x1400173c8  add     bx, r13w
0x1400173cc  jmp     short loc_14001739B
0x1400173ce  mov     [rdi+1Ah], bx
0x1400173d2  xor     ebx, ebx
0x1400173d4  mov     [rdi+0Eh], r13b
0x1400173d8  jmp     short loc_14001742D
0x1400173da  lea     r8, [rsp+68h+arg_18]
0x1400173e2  mov     rcx, rbp
0x1400173e5  call    DfscIsDomainController
0x1400173ea  mov     ebx, eax
0x1400173ec  test    eax, eax
0x1400173ee  js      short loc_14001742D
0x1400173f0  cmp     [rsp+68h+arg_18], 0
0x1400173f8  jz      short loc_14001742D
0x1400173fa  mov     r9b, r13b
0x1400173fd  mov     [rsp+68h+var_48], r13b; char
0x140017402  lea     r8, [rsp+68h+var_38]
0x140017407  mov     rdx, rsi
0x14001740a  mov     rcx, rbp; SourceString
0x14001740d  call    DfscRmGenerateDomainDcReferralFromDCName
0x140017412  mov     ebx, eax
0x140017414  test    eax, eax
0x140017416  js      short loc_14001742D
0x140017418  mov     rdx, [rsp+68h+var_38]
0x14001741d  mov     rcx, r15
0x140017420  call    DfscDomainCacheStore
0x140017425  mov     rcx, rax; P
0x140017428  call    DfscRmDereferenceReferral
0x14001742d  mov     rcx, rdi; P
0x140017430  call    DfscRmDereferenceReferral
0x140017435  mov     eax, ebx
0x140017437  mov     rbx, [rsp+68h+arg_0]
0x14001743c  mov     rbp, [rsp+68h+arg_8]
0x140017441  add     rsp, 40h
0x140017445  pop     r15
0x140017447  pop     r14
0x140017449  pop     r13
0x14001744b  pop     rdi
0x14001744c  pop     rsi
0x14001744d  retn
```
