# CClfsBaseFile::FindSharedSecurityDescriptor(void * const,uchar,uchar &,void * &)

- ea: `0x1400389ac`
- end: `0x140038b11`
- name: `?FindSharedSecurityDescriptor@CClfsBaseFile@@QEAAJQEAXEAEAEAEAPEAX@Z`
- size: `357`
- prototype: `__int64 __usercall@<rax>(CClfsBaseFile *__hidden this@<rcx>, void *const Src@<rdx>, unsigned __int8@<r8b>, unsigned __int8 *@<r9>, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140037c74`
- `0x140038fac`

## callees

- `0x14000b6b0`
- `0x140011d58`
- `0x140017f80`
- `0x140034558`
- `0x1400389ac`
- `0x140062688`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400389fb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400389fb`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140038a14`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140038a14`

## pseudocode

```c
__int64 __fastcall CClfsBaseFile::FindSharedSecurityDescriptor(
        PERESOURCE *this,
        void *const Src,
        unsigned __int8 a3,
        bool *a4,
        void **a5)
{
  BOOLEAN v9; // r13
  size_t v10; // r14
  int v11; // edi
  int Symbol; // eax
  struct _CLFSHASHSYM *v13; // rdx
  char *v14; // rax
  volatile signed __int32 *v15; // rbx
  struct _CLFSHASHSYM *v17; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING v18; // [rsp+40h] [rbp-38h] BYREF

  *(_QWORD *)&v18.Length = 0;
  v18.Buffer = 0;
  v17 = 0;
  *a4 = 1;
  *a5 = (void *)-1LL;
  v9 = ExAcquireResourceExclusiveLite(this[4], 1u);
  v10 = RtlLengthSecurityDescriptor(Src);
  v11 = ClfsConvertSecurityDescriptorToUnicodeString(&v18, Src, v10);
  if ( v11 >= 0 )
  {
    Symbol = CClfsBaseFile::FindSymbol(&v18, (struct _CLFSHASHTBL *)(this + 14), a3, (int)v10 + 28, &v17);
    v11 = Symbol;
    if ( Symbol == -1073741635 )
    {
      *a4 = 1;
    }
    else
    {
      if ( Symbol )
        goto LABEL_11;
      *a4 = a3 == 0;
    }
    v13 = v17;
    *a5 = (void *)*((int *)v17 + 9);
    v14 = (char *)CClfsBaseFile::OffsetToAddr((CClfsBaseFile *)this, *((_DWORD *)v13 + 9));
    v15 = (volatile signed __int32 *)v14;
    if ( v14 )
    {
      if ( !*a4 )
      {
        *(_DWORD *)v14 = -1040322547;
        *(_QWORD *)(v14 + 4) = 28;
        *((_DWORD *)v14 + 3) = 0;
        *((_DWORD *)v14 + 4) = 24;
        *((_DWORD *)v14 + 5) = v10;
        memmove(v14 + 24, Src, v10);
      }
      _InterlockedIncrement(v15 + 2);
    }
    else
    {
      v11 = -1072037875;
    }
  }
LABEL_11:
  if ( v9 )
    CClfsBaseFile::UnlockImage((CClfsBaseFile *)this);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400389ac  mov     r11, rsp
0x1400389af  mov     [r11+10h], rbx
0x1400389b3  mov     [r11+18h], rsi
0x1400389b7  mov     [r11+8], rcx
0x1400389bb  push    rdi
0x1400389bc  push    r12
0x1400389be  push    r13
0x1400389c0  push    r14
0x1400389c2  push    r15
0x1400389c4  sub     rsp, 50h
0x1400389c8  mov     rsi, r9
0x1400389cb  mov     bl, r8b
0x1400389ce  mov     r12, rdx
0x1400389d1  mov     r15, rcx
0x1400389d4  xor     eax, eax
0x1400389d6  mov     [r11-38h], rax
0x1400389da  mov     [r11-30h], rax
0x1400389de  mov     [r11-40h], rax
0x1400389e2  mov     byte ptr [r9], 1
0x1400389e6  mov     rax, [rsp+78h+arg_20]
0x1400389ee  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1400389f5  mov     dl, 1; Wait
0x1400389f7  mov     rcx, [rcx+20h]; Resource
0x1400389fb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140038a02  nop     dword ptr [rax+rax+00h]
0x140038a07  mov     r13b, al
0x140038a0a  mov     [rsp+78h+arg_18], al
0x140038a11  mov     rcx, r12; SecurityDescriptor
0x140038a14  call    cs:__imp_RtlLengthSecurityDescriptor
0x140038a1b  nop     dword ptr [rax+rax+00h]
0x140038a20  mov     r14d, eax
0x140038a23  mov     r8d, eax
0x140038a26  mov     rdx, r12
0x140038a29  lea     rcx, [rsp+78h+var_38]
0x140038a2e  call    ClfsConvertSecurityDescriptorToUnicodeString
0x140038a33  mov     edi, eax
0x140038a35  mov     [rsp+78h+var_48], eax
0x140038a39  test    eax, eax
0x140038a3b  js      loc_140038AE7
0x140038a41  lea     r9d, [r14+1Ch]; unsigned int
0x140038a45  lea     rdx, [r15+70h]; struct _CLFSHASHTBL *
0x140038a49  lea     rax, [rsp+78h+var_40]
0x140038a4e  mov     [rsp+78h+var_58], rax; struct _CLFSHASHSYM **
0x140038a53  mov     r8b, bl; unsigned __int8
0x140038a56  lea     rcx, [rsp+78h+var_38]; struct _UNICODE_STRING *
0x140038a5b  call    ?FindSymbol@CClfsBaseFile@@KAJPEAU_UNICODE_STRING@@PEAU_CLFSHASHTBL@@EKPEAPEAU_CLFSHASHSYM@@@Z; CClfsBaseFile::FindSymbol(_UNICODE_STRING *,_CLFSHASHTBL *,uchar,ulong,_CLFSHASHSYM * *)
0x140038a60  mov     edi, eax
0x140038a62  mov     [rsp+78h+var_48], eax
0x140038a66  cmp     eax, 0C00000BDh
0x140038a6b  jz      short loc_140038A7A
0x140038a6d  test    eax, eax
0x140038a6f  jnz     short loc_140038AE7
0x140038a71  test    bl, bl
0x140038a73  setz    al
0x140038a76  mov     [rsi], al
0x140038a78  jmp     short loc_140038A7D
0x140038a7a  mov     byte ptr [rsi], 1
0x140038a7d  mov     rdx, [rsp+78h+var_40]
0x140038a82  movsxd  rax, dword ptr [rdx+24h]
0x140038a86  mov     rcx, [rsp+78h+arg_20]
0x140038a8e  mov     [rcx], rax
0x140038a91  mov     edx, [rdx+24h]; unsigned int
0x140038a94  mov     rcx, r15; this
0x140038a97  call    ?OffsetToAddr@CClfsBaseFile@@IEAAPEAXK@Z; CClfsBaseFile::OffsetToAddr(ulong)
0x140038a9c  mov     rbx, rax
0x140038a9f  test    rax, rax
0x140038aa2  jnz     short loc_140038AAF
0x140038aa4  mov     edi, 0C01A000Dh
0x140038aa9  mov     [rsp+78h+var_48], edi
0x140038aad  jmp     short loc_140038AE7
0x140038aaf  cmp     byte ptr [rsi], 0
0x140038ab2  jnz     short loc_140038AE3
0x140038ab4  mov     dword ptr [rax], 0C1FDF00Dh
0x140038aba  mov     qword ptr [rax+4], 1Ch
0x140038ac2  mov     dword ptr [rax+0Ch], 0
0x140038ac9  mov     dword ptr [rax+10h], 18h
0x140038ad0  mov     [rax+14h], r14d
0x140038ad4  mov     r8, r14; Size
0x140038ad7  lea     rcx, [rax+18h]; void *
0x140038adb  mov     rdx, r12; Src
0x140038ade  call    memmove
0x140038ae3  lock inc dword ptr [rbx+8]
0x140038ae7  test    r13b, r13b
0x140038aea  jz      short loc_140038AF4
0x140038aec  mov     rcx, r15; this
0x140038aef  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x140038af4  mov     eax, edi
0x140038af6  lea     r11, [rsp+78h+var_28]
0x140038afb  mov     rbx, [r11+38h]
0x140038aff  mov     rsi, [r11+40h]
0x140038b03  mov     rsp, r11
0x140038b06  pop     r15
0x140038b08  pop     r14
0x140038b0a  pop     r13
0x140038b0c  pop     r12
0x140038b0e  pop     rdi
0x140038b0f  retn
0x14007d545  push    rbp
0x14007d547  sub     rsp, 30h
0x14007d54b  mov     rbp, rdx
0x14007d54e  cmp     byte ptr [rbp+98h], 0
0x14007d555  jz      short loc_14007D564
0x14007d557  mov     rcx, [rbp+80h]; this
0x14007d55e  call    ?UnlockImage@CClfsBaseFile@@QEAAXXZ; CClfsBaseFile::UnlockImage(void)
0x14007d563  nop
0x14007d564  add     rsp, 30h
0x14007d568  pop     rbp
0x14007d569  retn
```
