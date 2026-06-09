# BfsVerifyAce

- ea: `0x140004614`
- end: `0x1400046cf`
- name: `BfsVerifyAce`
- size: `187`
- prototype: `__int64 __usercall@<rax>(PACL Acl@<rcx>, PSID Sid1, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000b0d0`
- `0x14000e6f0`
- `0x14001e1a0`

## callees

- `0x140004614`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14000469b`
- `ntoskrnl!RtlEqualSid` at `0x14000469b`
- `ntoskrnl!RtlGetAce` at `0x14000465f`
- `ntoskrnl!RtlGetAce` at `0x14000465f`

## pseudocode

```c
__int64 __fastcall BfsVerifyAce(PACL Acl, char a2, char a3, int a4, PSID Sid1, _BYTE *a6)
{
  _BYTE *v6; // r14
  NTSTATUS v11; // esi
  ULONG v12; // edi
  char v13; // cl
  int v14; // ebx
  PVOID Ace; // [rsp+70h] [rbp+8h] BYREF

  v6 = a6;
  Ace = 0;
  v11 = -1073741275;
  v12 = 0;
  *a6 = 0;
  while ( v12 < Acl->AceCount )
  {
    v11 = RtlGetAce(Acl, v12, &Ace);
    if ( v11 < 0 )
      break;
    v13 = *(_BYTE *)Ace;
    if ( *(_BYTE *)Ace == a2 && *((_BYTE *)Ace + 1) == a3 && (!v13 || v13 == 17) )
    {
      v14 = *((_DWORD *)Ace + 1);
      if ( RtlEqualSid(Sid1, (char *)Ace + 8) )
      {
        if ( (a4 & v14) == a4 )
        {
          *v6 = 1;
          return (unsigned int)v11;
        }
      }
    }
    ++v12;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140004614  push    rbx
0x140004616  push    rbp
0x140004617  push    rsi
0x140004618  push    rdi
0x140004619  push    r12
0x14000461b  push    r13
0x14000461d  push    r14
0x14000461f  push    r15
0x140004621  sub     rsp, 28h
0x140004625  mov     r14, [rsp+68h+arg_28]
0x14000462d  mov     r15d, r9d
0x140004630  mov     r12b, r8b
0x140004633  mov     [rsp+68h+Ace], 0
0x14000463c  mov     r13b, dl
0x14000463f  mov     rbp, rcx
0x140004642  mov     esi, 0C0000225h
0x140004647  xor     edi, edi
0x140004649  mov     byte ptr [r14], 0
0x14000464d  movzx   eax, word ptr [rbp+4]
0x140004651  cmp     edi, eax
0x140004653  jnb     short loc_1400046BB
0x140004655  lea     r8, [rsp+68h+Ace]; Ace
0x14000465a  mov     edx, edi; AceIndex
0x14000465c  mov     rcx, rbp; Acl
0x14000465f  call    cs:__imp_RtlGetAce
0x140004666  nop     dword ptr [rax+rax+00h]
0x14000466b  mov     esi, eax
0x14000466d  test    eax, eax
0x14000466f  js      short loc_1400046BB
0x140004671  mov     rdx, [rsp+68h+Ace]
0x140004676  mov     cl, [rdx]
0x140004678  cmp     cl, r13b
0x14000467b  jnz     short loc_1400046B3
0x14000467d  cmp     [rdx+1], r12b
0x140004681  jnz     short loc_1400046B3
0x140004683  test    cl, cl
0x140004685  jz      short loc_14000468C
0x140004687  cmp     cl, 11h
0x14000468a  jnz     short loc_1400046B3
0x14000468c  mov     ebx, [rdx+4]
0x14000468f  add     rdx, 8; Sid2
0x140004693  mov     rcx, [rsp+68h+Sid1]; Sid1
0x14000469b  call    cs:__imp_RtlEqualSid
0x1400046a2  nop     dword ptr [rax+rax+00h]
0x1400046a7  test    al, al
0x1400046a9  jz      short loc_1400046B3
0x1400046ab  and     ebx, r15d
0x1400046ae  cmp     ebx, r15d
0x1400046b1  jz      short loc_1400046B7
0x1400046b3  inc     edi
0x1400046b5  jmp     short loc_14000464D
0x1400046b7  mov     byte ptr [r14], 1
0x1400046bb  mov     eax, esi
0x1400046bd  add     rsp, 28h
0x1400046c1  pop     r15
0x1400046c3  pop     r14
0x1400046c5  pop     r13
0x1400046c7  pop     r12
0x1400046c9  pop     rdi
0x1400046ca  pop     rsi
0x1400046cb  pop     rbp
0x1400046cc  pop     rbx
0x1400046cd  retn
```
