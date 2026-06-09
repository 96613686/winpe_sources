# CRasCredential::_KerbInteractiveSCLogonPack(_KERB_CERTIFICATE_LOGON const &,uchar * *,ulong *)

- ea: `0x180005244`
- end: `0x180005377`
- name: `?_KerbInteractiveSCLogonPack@CRasCredential@@AEAAJAEBU_KERB_CERTIFICATE_LOGON@@PEAPEAEPEAK@Z`
- size: `307`
- prototype: `__int64 __fastcall(CRasCredential *__hidden this, const struct _KERB_CERTIFICATE_LOGON *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004bd8`

## callees

- `0x180005244`
- `0x18000b0c2`
- `0x18000b0ce`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180005276`
- `ole32!CoTaskMemAlloc` at `0x180005276`

## pseudocode

```c
__int64 __fastcall CRasCredential::_KerbInteractiveSCLogonPack(
        CRasCredential *this,
        const struct _KERB_CERTIFICATE_LOGON *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  ULONG v7; // ebp
  _WORD *v8; // rax
  _WORD *v9; // rsi
  unsigned int Length; // ecx
  __int64 v11; // rax
  char *v12; // rbx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  char *v15; // rbx
  char *v16; // rbx
  __int64 result; // rax

  v7 = a2->UserName.Length + a2->Pin.Length + a2->DomainName.Length + a2->CspDataLength + 72;
  v8 = CoTaskMemAlloc(v7);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  memset_0(v8, 0, v7);
  *(_DWORD *)v9 = a2->MessageType;
  Length = a2->DomainName.Length;
  v9[4] = Length;
  v9[5] = a2->DomainName.Length;
  *((_QWORD *)v9 + 2) = v9 + 36;
  memcpy_0(v9 + 36, a2->DomainName.Buffer, Length);
  v11 = (unsigned __int16)v9[4];
  *((_QWORD *)v9 + 2) = 72;
  v12 = (char *)v9 + v11 + 72;
  v13 = a2->UserName.Length;
  v9[12] = v13;
  v9[13] = a2->UserName.Length;
  *((_QWORD *)v9 + 4) = v12;
  memcpy_0(v12, a2->UserName.Buffer, v13);
  *((_QWORD *)v9 + 4) = v12 - (char *)v9;
  v14 = a2->Pin.Length;
  v15 = &v12[(unsigned __int16)v9[12]];
  v9[20] = v14;
  v9[21] = a2->Pin.Length;
  *((_QWORD *)v9 + 6) = v15;
  memcpy_0(v15, a2->Pin.Buffer, v14);
  *((_DWORD *)v9 + 14) = 0;
  *((_QWORD *)v9 + 6) = v15 - (char *)v9;
  v16 = &v15[(unsigned __int16)v9[20]];
  *((_DWORD *)v9 + 15) = a2->CspDataLength;
  memcpy_0(v16, a2->CspData, a2->CspDataLength);
  *a3 = (unsigned __int8 *)v9;
  *((_QWORD *)v9 + 8) = v16 - (char *)v9;
  result = 0;
  *a4 = v7;
  return result;
}

```

## disassembly

```asm
0x180005244  push    rbx
0x180005246  push    rbp
0x180005247  push    rsi
0x180005248  push    rdi
0x180005249  push    r14
0x18000524b  push    r15
0x18000524d  sub     rsp, 28h
0x180005251  movzx   ecx, word ptr [rdx+8]
0x180005255  mov     r14, r9
0x180005258  movzx   eax, word ptr [rdx+28h]
0x18000525c  mov     r15, r8
0x18000525f  mov     ebp, [rdx+3Ch]
0x180005262  add     ecx, eax
0x180005264  movzx   eax, word ptr [rdx+18h]
0x180005268  add     ebp, 48h ; 'H'
0x18000526b  add     ecx, eax
0x18000526d  mov     rdi, rdx
0x180005270  add     ebp, ecx
0x180005272  mov     ecx, ebp; cb
0x180005274  mov     ebx, ebp
0x180005276  call    cs:__imp_CoTaskMemAlloc
0x18000527c  mov     rsi, rax
0x18000527f  test    rax, rax
0x180005282  jz      loc_180005365
0x180005288  mov     r8d, ebx; Size
0x18000528b  xor     edx, edx; Val
0x18000528d  mov     rcx, rax; void *
0x180005290  call    memset_0
0x180005295  mov     ecx, [rdi]
0x180005297  lea     rbx, [rsi+48h]
0x18000529b  mov     [rsi], ecx
0x18000529d  movzx   ecx, word ptr [rdi+8]
0x1800052a1  mov     [rsi+8], cx
0x1800052a5  mov     r8d, ecx; Size
0x1800052a8  movzx   eax, word ptr [rdi+8]
0x1800052ac  mov     rcx, rbx; void *
0x1800052af  mov     [rsi+0Ah], ax
0x1800052b3  mov     [rsi+10h], rbx
0x1800052b7  mov     rdx, [rdi+10h]; Src
0x1800052bb  call    memcpy_0
0x1800052c0  movzx   eax, word ptr [rsi+8]
0x1800052c4  mov     qword ptr [rsi+10h], 48h ; 'H'
0x1800052cc  add     rbx, rax
0x1800052cf  movzx   ecx, word ptr [rdi+18h]
0x1800052d3  mov     [rsi+18h], cx
0x1800052d7  mov     r8d, ecx; Size
0x1800052da  movzx   eax, word ptr [rdi+18h]
0x1800052de  mov     rcx, rbx; void *
0x1800052e1  mov     [rsi+1Ah], ax
0x1800052e5  mov     [rsi+20h], rbx
0x1800052e9  mov     rdx, [rdi+20h]; Src
0x1800052ed  call    memcpy_0
0x1800052f2  mov     rax, rbx
0x1800052f5  sub     rax, rsi
0x1800052f8  mov     [rsi+20h], rax
0x1800052fc  movzx   eax, word ptr [rsi+18h]
0x180005300  movzx   ecx, word ptr [rdi+28h]
0x180005304  add     rbx, rax
0x180005307  mov     [rsi+28h], cx
0x18000530b  mov     r8d, ecx; Size
0x18000530e  movzx   eax, word ptr [rdi+28h]
0x180005312  mov     rcx, rbx; void *
0x180005315  mov     [rsi+2Ah], ax
0x180005319  mov     [rsi+30h], rbx
0x18000531d  mov     rdx, [rdi+30h]; Src
0x180005321  call    memcpy_0
0x180005326  mov     dword ptr [rsi+38h], 0
0x18000532d  mov     rax, rbx
0x180005330  sub     rax, rsi
0x180005333  mov     [rsi+30h], rax
0x180005337  movzx   eax, word ptr [rsi+28h]
0x18000533b  add     rbx, rax
0x18000533e  mov     eax, [rdi+3Ch]
0x180005341  mov     [rsi+3Ch], eax
0x180005344  mov     rcx, rbx; void *
0x180005347  mov     r8d, [rdi+3Ch]; Size
0x18000534b  mov     rdx, [rdi+40h]; Src
0x18000534f  call    memcpy_0
0x180005354  sub     rbx, rsi
0x180005357  mov     [r15], rsi
0x18000535a  mov     [rsi+40h], rbx
0x18000535e  xor     eax, eax
0x180005360  mov     [r14], ebp
0x180005363  jmp     short loc_18000536A
0x180005365  mov     eax, 8007000Eh
0x18000536a  add     rsp, 28h
0x18000536e  pop     r15
0x180005370  pop     r14
0x180005372  pop     rdi
0x180005373  pop     rsi
0x180005374  pop     rbp
0x180005375  pop     rbx
0x180005376  retn
```
