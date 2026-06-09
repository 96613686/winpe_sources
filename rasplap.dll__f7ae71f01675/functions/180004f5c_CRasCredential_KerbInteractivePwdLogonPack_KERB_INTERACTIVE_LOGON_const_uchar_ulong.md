# CRasCredential::_KerbInteractivePwdLogonPack(_KERB_INTERACTIVE_LOGON const &,uchar * *,ulong *)

- ea: `0x180004f5c`
- end: `0x180005061`
- name: `?_KerbInteractivePwdLogonPack@CRasCredential@@AEAAJAEBU_KERB_INTERACTIVE_LOGON@@PEAPEAEPEAK@Z`
- size: `261`
- prototype: `__int64 __fastcall(CRasCredential *__hidden this, const struct _KERB_INTERACTIVE_LOGON *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004bd8`

## callees

- `0x180004f5c`
- `0x18000b0c2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180004f87`
- `ole32!CoTaskMemAlloc` at `0x180004f87`

## pseudocode

```c
__int64 __fastcall CRasCredential::_KerbInteractivePwdLogonPack(
        CRasCredential *this,
        const struct _KERB_INTERACTIVE_LOGON *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  unsigned int v7; // ebp
  _OWORD *v8; // rax
  _OWORD *v9; // rdi
  char *v10; // rbx
  unsigned int Length; // ecx
  __int64 v12; // rax
  char *v13; // rbx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  char *v16; // rbx
  __int64 result; // rax

  v7 = a2->Password.Length + a2->LogonDomainName.Length + a2->UserName.Length + 56;
  v8 = CoTaskMemAlloc(v7);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v10 = (char *)v8 + 56;
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  *((_QWORD *)v8 + 6) = 0;
  *(_DWORD *)v8 = a2->MessageType;
  Length = a2->LogonDomainName.Length;
  *((_WORD *)v8 + 4) = Length;
  *((_WORD *)v8 + 5) = a2->LogonDomainName.Length;
  *((_QWORD *)v8 + 2) = (char *)v8 + 56;
  memcpy_0((char *)v8 + 56, a2->LogonDomainName.Buffer, Length);
  v12 = *((unsigned __int16 *)v9 + 4);
  *((_QWORD *)v9 + 2) = 56;
  v13 = &v10[v12];
  v14 = a2->UserName.Length;
  *((_WORD *)v9 + 12) = v14;
  *((_WORD *)v9 + 13) = a2->UserName.Length;
  *((_QWORD *)v9 + 4) = v13;
  memcpy_0(v13, a2->UserName.Buffer, v14);
  *((_QWORD *)v9 + 4) = v13 - (char *)v9;
  v15 = a2->Password.Length;
  v16 = &v13[*((unsigned __int16 *)v9 + 12)];
  *((_WORD *)v9 + 20) = v15;
  *((_WORD *)v9 + 21) = a2->Password.Length;
  *((_QWORD *)v9 + 6) = v16;
  memcpy_0(v16, a2->Password.Buffer, v15);
  *a3 = (unsigned __int8 *)v9;
  *((_QWORD *)v9 + 6) = v16 - (char *)v9;
  result = 0;
  *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x180004f5c  push    rbx
0x180004f5e  push    rbp
0x180004f5f  push    rsi
0x180004f60  push    rdi
0x180004f61  push    r14
0x180004f63  push    r15
0x180004f65  sub     rsp, 28h
0x180004f69  movzx   ecx, word ptr [rdx+8]
0x180004f6d  mov     r14, r9
0x180004f70  movzx   eax, word ptr [rdx+28h]
0x180004f74  mov     r15, r8
0x180004f77  movzx   ebp, word ptr [rdx+18h]
0x180004f7b  add     ecx, eax
0x180004f7d  add     ebp, 38h ; '8'
0x180004f80  mov     rsi, rdx
0x180004f83  add     ebp, ecx
0x180004f85  mov     ecx, ebp; cb
0x180004f87  call    cs:__imp_CoTaskMemAlloc
0x180004f8d  mov     rdi, rax
0x180004f90  test    rax, rax
0x180004f93  jz      loc_18000504F
0x180004f99  xorps   xmm0, xmm0
0x180004f9c  lea     rbx, [rdi+38h]
0x180004fa0  movups  xmmword ptr [rdi], xmm0
0x180004fa3  xor     eax, eax
0x180004fa5  movups  xmmword ptr [rdi+10h], xmm0
0x180004fa9  movups  xmmword ptr [rdi+20h], xmm0
0x180004fad  mov     [rdi+30h], rax
0x180004fb1  mov     ecx, [rsi]
0x180004fb3  mov     [rdi], ecx
0x180004fb5  movzx   ecx, word ptr [rsi+8]
0x180004fb9  mov     [rdi+8], cx
0x180004fbd  mov     r8d, ecx; Size
0x180004fc0  movzx   eax, word ptr [rsi+8]
0x180004fc4  mov     rcx, rbx; void *
0x180004fc7  mov     [rdi+0Ah], ax
0x180004fcb  mov     [rdi+10h], rbx
0x180004fcf  mov     rdx, [rsi+10h]; Src
0x180004fd3  call    memcpy_0
0x180004fd8  movzx   eax, word ptr [rdi+8]
0x180004fdc  mov     qword ptr [rdi+10h], 38h ; '8'
0x180004fe4  add     rbx, rax
0x180004fe7  movzx   ecx, word ptr [rsi+18h]
0x180004feb  mov     [rdi+18h], cx
0x180004fef  mov     r8d, ecx; Size
0x180004ff2  movzx   eax, word ptr [rsi+18h]
0x180004ff6  mov     rcx, rbx; void *
0x180004ff9  mov     [rdi+1Ah], ax
0x180004ffd  mov     [rdi+20h], rbx
0x180005001  mov     rdx, [rsi+20h]; Src
0x180005005  call    memcpy_0
0x18000500a  mov     rax, rbx
0x18000500d  sub     rax, rdi
0x180005010  mov     [rdi+20h], rax
0x180005014  movzx   eax, word ptr [rdi+18h]
0x180005018  movzx   ecx, word ptr [rsi+28h]
0x18000501c  add     rbx, rax
0x18000501f  mov     [rdi+28h], cx
0x180005023  mov     r8d, ecx; Size
0x180005026  movzx   eax, word ptr [rsi+28h]
0x18000502a  mov     rcx, rbx; void *
0x18000502d  mov     [rdi+2Ah], ax
0x180005031  mov     [rdi+30h], rbx
0x180005035  mov     rdx, [rsi+30h]; Src
0x180005039  call    memcpy_0
0x18000503e  sub     rbx, rdi
0x180005041  mov     [r15], rdi
0x180005044  mov     [rdi+30h], rbx
0x180005048  xor     eax, eax
0x18000504a  mov     [r14], ebp
0x18000504d  jmp     short loc_180005054
0x18000504f  mov     eax, 8007000Eh
0x180005054  add     rsp, 28h
0x180005058  pop     r15
0x18000505a  pop     r14
0x18000505c  pop     rdi
0x18000505d  pop     rsi
0x18000505e  pop     rbp
0x18000505f  pop     rbx
0x180005060  retn
```
