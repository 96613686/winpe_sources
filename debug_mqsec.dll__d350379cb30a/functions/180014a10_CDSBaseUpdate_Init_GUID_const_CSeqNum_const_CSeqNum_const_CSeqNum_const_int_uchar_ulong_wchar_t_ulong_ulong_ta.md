# CDSBaseUpdate::Init(_GUID const *,CSeqNum const &,CSeqNum const &,CSeqNum const &,int,uchar,ulong,wchar_t *,ulong,ulong *,tagPROPVARIANT *)

- ea: `0x180014a10`
- end: `0x180014c40`
- name: `?Init@CDSBaseUpdate@@QEAAJPEBU_GUID@@AEBVCSeqNum@@11HEKPEA_WKPEAKPEAUtagPROPVARIANT@@@Z`
- size: `560`
- prototype: `__int64 __usercall@<rax>(CDSBaseUpdate *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct CSeqNum *@<r8>, const struct CSeqNum *@<r9>, const struct CSeqNum *, int, char, unsigned int, wchar_t *, unsigned int, unsigned int *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180014930`

## callees

- `0x180004074`
- `0x180014350`
- `0x180014a10`
- `0x18001722c`
- `0x18002f0a2`

## import_xrefs

- `msvcrt!free` at `0x180014b9f`
- `msvcrt!free` at `0x180014ba9`
- `msvcrt!free` at `0x180014bb3`
- `msvcrt!free` at `0x180014bcc`
- `msvcrt!free` at `0x180014c18`
- `msvcrt!free` at `0x180014c21`
- `msvcrt!free` at `0x180014b9f`
- `msvcrt!free` at `0x180014ba9`
- `msvcrt!free` at `0x180014bb3`
- `msvcrt!free` at `0x180014bcc`
- `msvcrt!free` at `0x180014c18`
- `msvcrt!free` at `0x180014c21`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDSBaseUpdate::Init(
        CDSBaseUpdate *this,
        const struct _GUID *a2,
        const struct CSeqNum *a3,
        const struct CSeqNum *a4,
        const struct CSeqNum *a5,
        int a6,
        char a7,
        unsigned int a8,
        wchar_t *a9,
        unsigned int a10,
        unsigned int *Src,
        struct tagPROPVARIANT *a12)
{
  void *v13; // r12
  struct tagPROPVARIANT *v14; // rdi
  void *v15; // rbx
  unsigned __int64 v16; // rsi
  __int64 i; // rsi
  int v18; // ebp

  if ( a10 > 0x100 || !Src || !a12 )
    return 3222142977LL;
  *(_BYTE *)this = a7;
  *(struct _GUID *)((char *)this + 4) = *a2;
  *(_QWORD *)((char *)this + 20) = *(_QWORD *)a4;
  *((_QWORD *)this + 4) = *(_QWORD *)a3;
  *((_QWORD *)this + 5) = *(_QWORD *)a5;
  *((_DWORD *)this + 7) = a6;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 56) = a10;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  v13 = MmAllocate(saturated_mul((unsigned __int8)a10, 4u));
  memcpy_0(v13, Src, 4LL * *((unsigned __int8 *)this + 56));
  v14 = (struct tagPROPVARIANT *)MmAllocate(saturated_mul(*((unsigned __int8 *)this + 56), 0x18u));
  if ( a8 )
  {
    *((_QWORD *)this + 6) = a9;
    memcpy_0(v14, a12, 24LL * *((unsigned __int8 *)this + 56));
    *((_DWORD *)this + 23) = a8 != 2;
  }
  else
  {
    v15 = 0;
    if ( a9 )
    {
      v16 = mqwcslen(a9) + 1;
      v15 = MmAllocate(saturated_mul(v16, 2u));
      memcpy_0(v15, a9, 2 * v16);
    }
    for ( i = 0; (unsigned int)i < *((unsigned __int8 *)this + 56); i = (unsigned int)(i + 1) )
    {
      v18 = CDSBaseUpdate::CopyProperty(this, &a12[i], &v14[i]);
      if ( v18 < 0 )
      {
        free(v15);
        free(v14);
        free(v13);
        return (unsigned int)v18;
      }
    }
    *((_DWORD *)this + 23) = 1;
    *((_QWORD *)this + 6) = v15;
    free(0);
  }
  *((_QWORD *)this + 8) = v13;
  *((_QWORD *)this + 9) = v14;
  free(0);
  free(0);
  return 0;
}

```

## disassembly

```asm
0x180014a10  push    rbx
0x180014a12  push    rbp
0x180014a13  push    rsi
0x180014a14  push    rdi
0x180014a15  push    r12
0x180014a17  push    r14
0x180014a19  push    r15
0x180014a1b  sub     rsp, 40h
0x180014a1f  mov     r14, rcx
0x180014a22  cmp     [rsp+78h+arg_48], 100h
0x180014a2d  ja      loc_180014C2C
0x180014a33  mov     rbx, [rsp+78h+Src]
0x180014a3b  test    rbx, rbx
0x180014a3e  jz      loc_180014C2C
0x180014a44  mov     r15, [rsp+78h+arg_58]
0x180014a4c  test    r15, r15
0x180014a4f  jz      loc_180014C2C
0x180014a55  mov     al, [rsp+78h+arg_30]
0x180014a5c  mov     [rcx], al
0x180014a5e  movups  xmm0, xmmword ptr [rdx]
0x180014a61  movdqu  xmmword ptr [rcx+4], xmm0
0x180014a66  mov     rax, [r9]
0x180014a69  mov     [rcx+14h], rax
0x180014a6d  mov     rax, [r8]
0x180014a70  mov     [rcx+20h], rax
0x180014a74  mov     rax, [rsp+78h+arg_20]
0x180014a7c  mov     rcx, [rax]
0x180014a7f  mov     [r14+28h], rcx
0x180014a83  mov     eax, [rsp+78h+arg_28]
0x180014a8a  mov     [r14+1Ch], eax
0x180014a8e  mov     qword ptr [r14+30h], 0
0x180014a96  mov     qword ptr [r14+40h], 0
0x180014a9e  mov     qword ptr [r14+48h], 0
0x180014aa6  movzx   ecx, byte ptr [rsp+78h+arg_48]
0x180014aae  mov     [r14+38h], cl
0x180014ab2  mov     qword ptr [r14+50h], 0
0x180014aba  mov     dword ptr [r14+58h], 0
0x180014ac2  mov     eax, 4
0x180014ac7  mul     rcx
0x180014aca  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180014ad1  cmovb   rax, rdi
0x180014ad5  mov     rcx, rax; unsigned __int64
0x180014ad8  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014add  mov     r12, rax
0x180014ae0  mov     [rsp+78h+var_50], rax
0x180014ae5  movzx   r8d, byte ptr [r14+38h]
0x180014aea  shl     r8, 2; Size
0x180014aee  mov     rdx, rbx; Src
0x180014af1  mov     rcx, rax; void *
0x180014af4  call    memcpy_0
0x180014af9  movzx   ecx, byte ptr [r14+38h]
0x180014afe  lea     eax, [rdi+19h]
0x180014b01  mul     rcx
0x180014b04  cmovb   rax, rdi
0x180014b08  mov     rcx, rax; unsigned __int64
0x180014b0b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014b10  mov     rdi, rax
0x180014b13  mov     [rsp+78h+var_48], rax
0x180014b18  mov     ebx, [rsp+78h+arg_38]
0x180014b1f  test    ebx, ebx
0x180014b21  jnz     loc_180014BD5
0x180014b27  xor     ebx, ebx
0x180014b29  mov     [rsp+78h+var_58], rbx
0x180014b2e  mov     rbp, [rsp+78h+arg_40]
0x180014b36  test    rbp, rbp
0x180014b39  jz      short loc_180014B73
0x180014b3b  mov     rcx, rbp; wchar_t *
0x180014b3e  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180014b43  lea     esi, [rax+1]
0x180014b46  lea     eax, [rbx+2]
0x180014b49  mul     rsi
0x180014b4c  lea     rcx, [rbx-1]
0x180014b50  cmovb   rax, rcx
0x180014b54  mov     rcx, rax; unsigned __int64
0x180014b57  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014b5c  mov     rbx, rax
0x180014b5f  mov     [rsp+78h+var_58], rax
0x180014b64  lea     r8, [rsi+rsi]; Size
0x180014b68  mov     rdx, rbp; Src
0x180014b6b  mov     rcx, rax; void *
0x180014b6e  call    memcpy_0
0x180014b73  xor     esi, esi
0x180014b75  movzx   eax, byte ptr [r14+38h]
0x180014b7a  cmp     esi, eax
0x180014b7c  jnb     short loc_180014BBE
0x180014b7e  lea     rcx, [rsi+rsi*2]
0x180014b82  lea     r8, [rdi+rcx*8]; struct tagPROPVARIANT *
0x180014b86  lea     rdx, [r15+rcx*8]; struct tagPROPVARIANT *
0x180014b8a  mov     rcx, r14; this
0x180014b8d  call    ?CopyProperty@CDSBaseUpdate@@AEAAJAEAUtagPROPVARIANT@@PEAU2@@Z; CDSBaseUpdate::CopyProperty(tagPROPVARIANT &,tagPROPVARIANT *)
0x180014b92  mov     ebp, eax
0x180014b94  test    eax, eax
0x180014b96  js      short loc_180014B9C
0x180014b98  inc     esi
0x180014b9a  jmp     short loc_180014B75
0x180014b9c  mov     rcx, rbx; Block
0x180014b9f  call    cs:__imp_free
0x180014ba5  nop
0x180014ba6  mov     rcx, rdi; Block
0x180014ba9  call    cs:__imp_free
0x180014baf  nop
0x180014bb0  mov     rcx, r12; Block
0x180014bb3  call    cs:__imp_free
0x180014bb9  nop
0x180014bba  mov     eax, ebp
0x180014bbc  jmp     short loc_180014C31
0x180014bbe  mov     dword ptr [r14+5Ch], 1
0x180014bc6  mov     [r14+30h], rbx
0x180014bca  xor     ecx, ecx; Block
0x180014bcc  call    cs:__imp_free
0x180014bd2  nop
0x180014bd3  jmp     short loc_180014C05
0x180014bd5  mov     rax, [rsp+78h+arg_40]
0x180014bdd  mov     [r14+30h], rax
0x180014be1  movzx   eax, byte ptr [r14+38h]
0x180014be6  lea     r8, [rax+rax*2]
0x180014bea  shl     r8, 3; Size
0x180014bee  mov     rdx, r15; Src
0x180014bf1  mov     rcx, rdi; void *
0x180014bf4  call    memcpy_0
0x180014bf9  xor     eax, eax
0x180014bfb  cmp     ebx, 2
0x180014bfe  setnz   al
0x180014c01  mov     [r14+5Ch], eax
0x180014c05  mov     [rsp+78h+var_50], 0
0x180014c0e  mov     [r14+40h], r12
0x180014c12  mov     [r14+48h], rdi
0x180014c16  xor     ecx, ecx; Block
0x180014c18  call    cs:__imp_free
0x180014c1e  nop
0x180014c1f  xor     ecx, ecx; Block
0x180014c21  call    cs:__imp_free
0x180014c27  nop
0x180014c28  xor     eax, eax
0x180014c2a  jmp     short loc_180014C31
0x180014c2c  mov     eax, 0C00E0001h
0x180014c31  add     rsp, 40h
0x180014c35  pop     r15
0x180014c37  pop     r14
0x180014c39  pop     r12
0x180014c3b  pop     rdi
0x180014c3c  pop     rsi
0x180014c3d  pop     rbp
0x180014c3e  pop     rbx
0x180014c3f  retn
```
