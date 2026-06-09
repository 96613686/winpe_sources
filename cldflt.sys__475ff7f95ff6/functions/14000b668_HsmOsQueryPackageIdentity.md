# HsmOsQueryPackageIdentity

- ea: `0x14000b668`
- end: `0x14000b7df`
- name: `HsmOsQueryPackageIdentity`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140013f88`
- `0x140076948`

## callees

- `0x140001560`
- `0x140001578`
- `0x14000b668`
- `0x140014c84`
- `0x14001e300`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000b7c3`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000b7c3`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14000b7b2`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14000b7b2`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000b779`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000b779`

## pseudocode

```c
__int64 __fastcall HsmOsQueryPackageIdentity(__int64 a1, void *a2, ULONGLONG *a3, void *a4, ULONGLONG *a5)
{
  __int64 EcpFromAttributionInfo; // rax
  ULONGLONG v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned __int16 *v12; // rdi
  __int64 result; // rax
  ULONGLONG v14; // rcx
  ULONGLONG v15; // rdx
  ULONGLONG v16; // rbx
  ULONGLONG v17; // rbx
  ULONGLONG v18; // rax
  struct _KPROCESS *ProcessFromAttributionInfo; // rax
  PACCESS_TOKEN v20; // rdi
  unsigned int PackageIdentity; // ebx
  ULONGLONG Size; // [rsp+30h] [rbp-48h] BYREF
  ULONGLONG pullResult[8]; // [rsp+38h] [rbp-40h] BYREF

  EcpFromAttributionInfo = HsmOsGetEcpFromAttributionInfo();
  v12 = (unsigned __int16 *)EcpFromAttributionInfo;
  if ( EcpFromAttributionInfo )
  {
    if ( !*(_WORD *)(EcpFromAttributionInfo + 72) && !*(_WORD *)(EcpFromAttributionInfo + 68) )
      return 3221226021LL;
    v14 = *(unsigned __int16 *)(EcpFromAttributionInfo + 68);
    pullResult[0] = 0;
    Size = 0;
    if ( RtlULongLongMult(v14, v9, pullResult) >= 0 && RtlULongLongMult(v12[36], v15, &Size) >= 0 )
    {
      v16 = pullResult[0];
      if ( *a3 < pullResult[0] )
      {
        if ( pullResult[0] )
        {
          v18 = Size;
          *a3 = pullResult[0];
          *a5 = v18;
          return 3221225507LL;
        }
      }
      else if ( pullResult[0] )
      {
        memmove(a2, &v12[v12[33] + 37], pullResult[0]);
      }
      *a3 = v16;
      v17 = Size;
      if ( *a5 < Size )
      {
        result = 3221225507LL;
        if ( Size )
        {
LABEL_17:
          *a5 = v17;
          return result;
        }
      }
      else if ( Size )
      {
        memmove(a4, &v12[v12[35] + 37], Size);
      }
      result = 0;
      goto LABEL_17;
    }
    return 3221225621LL;
  }
  else
  {
    ProcessFromAttributionInfo = (struct _KPROCESS *)HsmOsGetProcessFromAttributionInfo(v10, v9, v11);
    v20 = PsReferencePrimaryToken(ProcessFromAttributionInfo);
    if ( v20 )
    {
      PackageIdentity = RtlQueryPackageIdentity(v20, a2, a3, a4, a5, 0, Size);
      PsDereferencePrimaryToken(v20);
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return PackageIdentity;
  }
}

```

## disassembly

```asm
0x14000b668  push    rbx
0x14000b66a  push    rbp
0x14000b66b  push    rsi
0x14000b66c  push    rdi
0x14000b66d  push    r14
0x14000b66f  push    r15
0x14000b671  sub     rsp, 48h
0x14000b675  mov     r14, r9
0x14000b678  mov     rsi, r8
0x14000b67b  mov     rbp, rdx
0x14000b67e  call    HsmOsGetEcpFromAttributionInfo
0x14000b683  xor     r15d, r15d
0x14000b686  mov     rdi, rax
0x14000b689  test    rax, rax
0x14000b68c  jz      loc_14000B771
0x14000b692  cmp     [rax+48h], r15w
0x14000b697  jnz     short loc_14000B6AA
0x14000b699  cmp     [rax+44h], r15w
0x14000b69e  jnz     short loc_14000B6AA
0x14000b6a0  mov     eax, 0C0000225h
0x14000b6a5  jmp     loc_14000B7D1
0x14000b6aa  movzx   ecx, word ptr [rax+44h]; ullMultiplicand
0x14000b6ae  lea     r8, [rsp+78h+pullResult]; pullResult
0x14000b6b3  mov     [rsp+78h+pullResult], r15
0x14000b6b8  mov     [rsp+78h+Size], r15
0x14000b6bd  call    RtlULongLongMult
0x14000b6c2  test    eax, eax
0x14000b6c4  js      loc_14000B76A
0x14000b6ca  movzx   ecx, word ptr [rdi+48h]; ullMultiplicand
0x14000b6ce  lea     r8, [rsp+78h+Size]; pullResult
0x14000b6d3  call    RtlULongLongMult
0x14000b6d8  test    eax, eax
0x14000b6da  js      loc_14000B76A
0x14000b6e0  mov     rbx, [rsp+78h+pullResult]
0x14000b6e5  cmp     [rsi], rbx
0x14000b6e8  jb      short loc_14000B739
0x14000b6ea  test    rbx, rbx
0x14000b6ed  jz      short loc_14000B706
0x14000b6ef  movzx   eax, word ptr [rdi+42h]
0x14000b6f3  mov     r8, rbx; Size
0x14000b6f6  add     rax, 25h ; '%'
0x14000b6fa  mov     rcx, rbp; void *
0x14000b6fd  lea     rdx, [rdi+rax*2]; Src
0x14000b701  call    memmove
0x14000b706  mov     [rsi], rbx
0x14000b709  mov     rsi, [rsp+78h+arg_20]
0x14000b711  mov     rbx, [rsp+78h+Size]
0x14000b716  cmp     [rsi], rbx
0x14000b719  jb      short loc_14000B758
0x14000b71b  test    rbx, rbx
0x14000b71e  jz      short loc_14000B762
0x14000b720  movzx   eax, word ptr [rdi+46h]
0x14000b724  mov     r8, rbx; Size
0x14000b727  add     rax, 25h ; '%'
0x14000b72b  mov     rcx, r14; void *
0x14000b72e  lea     rdx, [rdi+rax*2]; Src
0x14000b732  call    memmove
0x14000b737  jmp     short loc_14000B762
0x14000b739  test    rbx, rbx
0x14000b73c  jz      short loc_14000B706
0x14000b73e  mov     rax, [rsp+78h+Size]
0x14000b743  mov     rcx, [rsp+78h+arg_20]
0x14000b74b  mov     [rsi], rbx
0x14000b74e  mov     [rcx], rax
0x14000b751  mov     eax, 0C0000023h
0x14000b756  jmp     short loc_14000B7D1
0x14000b758  mov     eax, 0C0000023h
0x14000b75d  test    rbx, rbx
0x14000b760  jnz     short loc_14000B765
0x14000b762  mov     eax, r15d
0x14000b765  mov     [rsi], rbx
0x14000b768  jmp     short loc_14000B7D1
0x14000b76a  mov     eax, 0C0000095h
0x14000b76f  jmp     short loc_14000B7D1
0x14000b771  call    HsmOsGetProcessFromAttributionInfo
0x14000b776  mov     rcx, rax; Process
0x14000b779  call    cs:__imp_PsReferencePrimaryToken
0x14000b780  nop     dword ptr [rax+rax+00h]
0x14000b785  mov     rdi, rax
0x14000b788  test    rax, rax
0x14000b78b  jnz     short loc_14000B794
0x14000b78d  mov     ebx, 0C0000001h
0x14000b792  jmp     short loc_14000B7CF
0x14000b794  mov     rax, [rsp+78h+arg_20]
0x14000b79c  mov     r9, r14
0x14000b79f  mov     [rsp+78h+var_50], r15
0x14000b7a4  mov     r8, rsi
0x14000b7a7  mov     rdx, rbp
0x14000b7aa  mov     [rsp+78h+var_58], rax
0x14000b7af  mov     rcx, rdi
0x14000b7b2  call    cs:__imp_RtlQueryPackageIdentity
0x14000b7b9  nop     dword ptr [rax+rax+00h]
0x14000b7be  mov     rcx, rdi; PrimaryToken
0x14000b7c1  mov     ebx, eax
0x14000b7c3  call    cs:__imp_PsDereferencePrimaryToken
0x14000b7ca  nop     dword ptr [rax+rax+00h]
0x14000b7cf  mov     eax, ebx
0x14000b7d1  add     rsp, 48h
0x14000b7d5  pop     r15
0x14000b7d7  pop     r14
0x14000b7d9  pop     rdi
0x14000b7da  pop     rsi
0x14000b7db  pop     rbp
0x14000b7dc  pop     rbx
0x14000b7dd  retn
```
