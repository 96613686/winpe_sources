# CQPrivate::SetQueueProperties(wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const,ulong *,ulong * *,tagPROPVARIANT * *)

- ea: `0x18001d5e0`
- end: `0x18001d80a`
- name: `?SetQueueProperties@CQPrivate@@AEAAJPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@PEAKPEAPEAKPEAPEAU2@@Z`
- size: `554`
- prototype: `int(CQPrivate *__hidden this, const wchar_t *, void *, unsigned int, unsigned int *const, struct tagPROPVARIANT *const, unsigned int *, unsigned int **, struct tagPROPVARIANT **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bba0`
- `0x18001cdd8`

## callees

- `0x18001b3c4`
- `0x18001d5e0`
- `0x18002c61c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18001d7e5`
- `msvcrt!free` at `0x18001d7ee`
- `msvcrt!free` at `0x18001d7e5`
- `msvcrt!free` at `0x18001d7ee`
- `msvcrt!time` at `0x18001d78e`
- `msvcrt!time` at `0x18001d78e`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18001d770`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x18001d770`
- `mqsec!MQSec_ConvertSDToNT4Format` at `0x18001d72d`
- `mqsec!MQSec_ConvertSDToNT4Format` at `0x18001d72d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CQPrivate::SetQueueProperties(
        CQPrivate *this,
        const wchar_t *a2,
        struct _SECURITY_DESCRIPTOR *a3,
        unsigned int a4,
        unsigned int *const a5,
        struct tagPROPVARIANT *const a6,
        unsigned int *a7,
        unsigned int **a8,
        struct tagPROPVARIANT **a9)
{
  unsigned int *v12; // r14
  struct tagPROPVARIANT *v13; // rbx
  struct tagPROPVARIANT *v14; // rcx
  __int16 *v15; // rax
  __int64 v16; // r8
  __int64 i; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r9
  BYTE *v21; // xmm1_8
  int v22; // eax
  unsigned int v23; // ecx
  DWORD SecurityDescriptorLength; // edx
  LONG v25; // eax
  void *Block; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v28; // [rsp+78h] [rbp+20h] BYREF

  Block = this;
  v12 = a5;
  v13 = (struct tagPROPVARIANT *)MmAllocate(0x168u);
  v14 = v13;
  v15 = &word_18013BD30;
  v16 = 2;
  do
  {
    *(_OWORD *)&v14->vt = *(_OWORD *)v15;
    *((_OWORD *)&v14->decVal + 1) = *((_OWORD *)v15 + 1);
    *(_OWORD *)&v14[1].decVal.Lo32 = *((_OWORD *)v15 + 2);
    *(_OWORD *)&v14[2].vt = *((_OWORD *)v15 + 3);
    *((_OWORD *)&v14[2].decVal + 1) = *((_OWORD *)v15 + 4);
    *(_OWORD *)&v14[3].decVal.Lo32 = *((_OWORD *)v15 + 5);
    *(_OWORD *)&v14[4].vt = *((_OWORD *)v15 + 6);
    *((_OWORD *)&v14[4].decVal + 1) = *((_OWORD *)v15 + 7);
    v14 = (struct tagPROPVARIANT *)((char *)v14 + 128);
    v15 += 64;
    --v16;
  }
  while ( v16 );
  *(_OWORD *)&v14->vt = *(_OWORD *)v15;
  *((_OWORD *)&v14->decVal + 1) = *((_OWORD *)v15 + 1);
  *(_OWORD *)&v14[1].decVal.Lo32 = *((_OWORD *)v15 + 2);
  *(_OWORD *)&v14[2].vt = *((_OWORD *)v15 + 3);
  *((_OWORD *)&v14[2].decVal + 1) = *((_OWORD *)v15 + 4);
  *(_OWORD *)&v14[3].decVal.Lo32 = *((_OWORD *)v15 + 5);
  *(_QWORD *)&v14[4].vt = *((_QWORD *)v15 + 12);
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(v19 + 1) )
  {
    v18 = PROPERTY_MAP::operator[](i, v12[i], v16);
    if ( v18 != -1 )
    {
      if ( v12[v19] == 103 )
      {
        v13[v18].vt = 31;
        v13[v18].hVal.QuadPart = (LONGLONG)a2;
      }
      else
      {
        v21 = *(BYTE **)(v20 + 24 * v19 + 16);
        *(_OWORD *)&v13[v18].vt = *(_OWORD *)(v20 + 24 * v19);
        v13[v18].bstrblobVal.pData = v21;
      }
    }
  }
  v28 = 0;
  Block = 0;
  v22 = MQSec_ConvertSDToNT4Format(1u, a3, &v28, (struct _SECURITY_DESCRIPTOR **)&Block, 0xFu);
  if ( v22 >= 0 )
  {
    if ( v22 != 1074662402 )
      a3 = (struct _SECURITY_DESCRIPTOR *)Block;
  }
  else
  {
    LogMsgHR(v22, (wchar_t *)L"cqpriv", 0xC7u);
  }
  v23 = dword_18012A338;
  v13[dword_18012A338].bstrblobVal.pData = &a3->Revision;
  if ( a3 )
  {
    SecurityDescriptorLength = GetSecurityDescriptorLength(a3);
    v23 = dword_18012A338;
  }
  else
  {
    SecurityDescriptorLength = 0;
  }
  v13[v23].lVal = SecurityDescriptorLength;
  v25 = time(0);
  v13[dword_18012A33C].lVal = v25;
  v13[dword_180132348].lVal = v25;
  *a7 = 15;
  *a8 = (unsigned int *)&dword_180128670;
  *a9 = v13;
  free(Block);
  free(0);
  return 0;
}

```

## disassembly

```asm
0x18001d5e0  mov     [rsp+arg_8], rbx
0x18001d5e5  mov     [rsp+arg_10], rbp
0x18001d5ea  mov     [rsp+Block], rcx
0x18001d5ef  push    rsi
0x18001d5f0  push    rdi
0x18001d5f1  push    r14
0x18001d5f3  sub     rsp, 40h
0x18001d5f7  mov     esi, r9d
0x18001d5fa  mov     rdi, r8
0x18001d5fd  mov     rbp, rdx
0x18001d600  mov     r14, [rsp+58h+arg_20]
0x18001d608  mov     ecx, 168h; unsigned __int64
0x18001d60d  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001d612  mov     rbx, rax
0x18001d615  mov     [rsp+58h+var_28], rax
0x18001d61a  mov     rcx, rax
0x18001d61d  lea     rax, word_18013BD30
0x18001d624  mov     edx, 80h
0x18001d629  lea     r8d, [rdx-7Eh]
0x18001d62d  movups  xmm0, xmmword ptr [rax]
0x18001d630  movups  xmmword ptr [rcx], xmm0
0x18001d633  movups  xmm1, xmmword ptr [rax+10h]
0x18001d637  movups  xmmword ptr [rcx+10h], xmm1
0x18001d63b  movups  xmm0, xmmword ptr [rax+20h]
0x18001d63f  movups  xmmword ptr [rcx+20h], xmm0
0x18001d643  movups  xmm1, xmmword ptr [rax+30h]
0x18001d647  movups  xmmword ptr [rcx+30h], xmm1
0x18001d64b  movups  xmm0, xmmword ptr [rax+40h]
0x18001d64f  movups  xmmword ptr [rcx+40h], xmm0
0x18001d653  movups  xmm1, xmmword ptr [rax+50h]
0x18001d657  movups  xmmword ptr [rcx+50h], xmm1
0x18001d65b  movups  xmm0, xmmword ptr [rax+60h]
0x18001d65f  movups  xmmword ptr [rcx+60h], xmm0
0x18001d663  movups  xmm1, xmmword ptr [rax+70h]
0x18001d667  movups  xmmword ptr [rcx+70h], xmm1
0x18001d66b  add     rcx, rdx
0x18001d66e  add     rax, rdx
0x18001d671  sub     r8, 1
0x18001d675  jnz     short loc_18001D62D
0x18001d677  movups  xmm0, xmmword ptr [rax]
0x18001d67a  movups  xmmword ptr [rcx], xmm0
0x18001d67d  movups  xmm1, xmmword ptr [rax+10h]
0x18001d681  movups  xmmword ptr [rcx+10h], xmm1
0x18001d685  movups  xmm0, xmmword ptr [rax+20h]
0x18001d689  movups  xmmword ptr [rcx+20h], xmm0
0x18001d68d  movups  xmm1, xmmword ptr [rax+30h]
0x18001d691  movups  xmmword ptr [rcx+30h], xmm1
0x18001d695  movups  xmm0, xmmword ptr [rax+40h]
0x18001d699  movups  xmmword ptr [rcx+40h], xmm0
0x18001d69d  movups  xmm1, xmmword ptr [rax+50h]
0x18001d6a1  movups  xmmword ptr [rcx+50h], xmm1
0x18001d6a5  mov     rax, [rax+60h]
0x18001d6a9  mov     [rcx+60h], rax
0x18001d6ad  xor     ecx, ecx
0x18001d6af  test    esi, esi
0x18001d6b1  jz      short loc_18001D703
0x18001d6b3  mov     r9, [rsp+58h+arg_28]
0x18001d6bb  mov     edx, [r14+rcx*4]
0x18001d6bf  call    ??APROPERTY_MAP@@QEAAHK@Z; PROPERTY_MAP::operator[](ulong)
0x18001d6c4  cmp     eax, 0FFFFFFFFh
0x18001d6c7  jz      short loc_18001D6FD
0x18001d6c9  cdqe
0x18001d6cb  lea     rdx, [rax+rax*2]
0x18001d6cf  cmp     dword ptr [r14+rcx*4], 67h ; 'g'
0x18001d6d4  jnz     short loc_18001D6E3
0x18001d6d6  mov     word ptr [rbx+rdx*8], 1Fh
0x18001d6dc  mov     [rbx+rdx*8+8], rbp
0x18001d6e1  jmp     short loc_18001D6FD
0x18001d6e3  lea     rax, [rcx+rcx*2]
0x18001d6e7  movups  xmm0, xmmword ptr [r9+rax*8]
0x18001d6ec  movsd   xmm1, qword ptr [r9+rax*8+10h]
0x18001d6f3  movups  xmmword ptr [rbx+rdx*8], xmm0
0x18001d6f7  movsd   qword ptr [rbx+rdx*8+10h], xmm1
0x18001d6fd  inc     ecx
0x18001d6ff  cmp     ecx, esi
0x18001d701  jb      short loc_18001D6BB
0x18001d703  mov     [rsp+58h+arg_18], 0
0x18001d70b  mov     [rsp+58h+Block], 0
0x18001d714  mov     esi, 0Fh
0x18001d719  mov     [rsp+58h+var_38], esi
0x18001d71d  lea     r9, [rsp+58h+Block]
0x18001d722  lea     r8, [rsp+58h+arg_18]
0x18001d727  mov     rdx, rdi
0x18001d72a  lea     ecx, [rsi-0Eh]
0x18001d72d  call    cs:__imp_?MQSec_ConvertSDToNT4Format@@YAJKPEAU_SECURITY_DESCRIPTOR@@PEAKPEAPEAU1@K@Z; MQSec_ConvertSDToNT4Format(ulong,_SECURITY_DESCRIPTOR *,ulong *,_SECURITY_DESCRIPTOR * *,ulong)
0x18001d733  test    eax, eax
0x18001d735  jns     short loc_18001D74D
0x18001d737  mov     r8d, 0C7h; unsigned __int16
0x18001d73d  lea     rdx, aCqpriv; "cqpriv"
0x18001d744  mov     ecx, eax; int
0x18001d746  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001d74b  jmp     short loc_18001D759
0x18001d74d  cmp     eax, 400E0C02h
0x18001d752  jz      short loc_18001D759
0x18001d754  mov     rdi, [rsp+58h+Block]
0x18001d759  mov     ecx, cs:dword_18012A338
0x18001d75f  lea     rdx, [rcx+rcx*2]
0x18001d763  mov     [rbx+rdx*8+10h], rdi
0x18001d768  test    rdi, rdi
0x18001d76b  jz      short loc_18001D780
0x18001d76d  mov     rcx, rdi; pSecurityDescriptor
0x18001d770  call    cs:__imp_GetSecurityDescriptorLength
0x18001d776  mov     edx, eax
0x18001d778  mov     ecx, cs:dword_18012A338
0x18001d77e  jmp     short loc_18001D782
0x18001d780  xor     edx, edx
0x18001d782  mov     eax, ecx
0x18001d784  lea     rcx, [rax+rax*2]
0x18001d788  mov     [rbx+rcx*8+8], edx
0x18001d78c  xor     ecx, ecx; Time
0x18001d78e  call    cs:__imp_time
0x18001d794  mov     ecx, cs:dword_18012A33C
0x18001d79a  lea     rdx, [rcx+rcx*2]
0x18001d79e  mov     [rbx+rdx*8+8], eax
0x18001d7a2  mov     ecx, cs:dword_180132348
0x18001d7a8  lea     rdx, [rcx+rcx*2]
0x18001d7ac  mov     [rbx+rdx*8+8], eax
0x18001d7b0  mov     rax, [rsp+58h+arg_30]
0x18001d7b8  mov     [rax], esi
0x18001d7ba  lea     rcx, dword_180128670
0x18001d7c1  mov     rax, [rsp+58h+arg_38]
0x18001d7c9  mov     [rax], rcx
0x18001d7cc  mov     [rsp+58h+var_28], 0
0x18001d7d5  mov     rax, [rsp+58h+arg_40]
0x18001d7dd  mov     [rax], rbx
0x18001d7e0  mov     rcx, [rsp+58h+Block]; Block
0x18001d7e5  call    cs:__imp_free
0x18001d7eb  nop
0x18001d7ec  xor     ecx, ecx; Block
0x18001d7ee  call    cs:__imp_free
0x18001d7f4  nop
0x18001d7f5  xor     eax, eax
0x18001d7f7  mov     rbx, [rsp+58h+arg_8]
0x18001d7fc  mov     rbp, [rsp+58h+arg_10]
0x18001d801  add     rsp, 40h
0x18001d805  pop     r14
0x18001d807  pop     rdi
0x18001d808  pop     rsi
0x18001d809  retn
```
