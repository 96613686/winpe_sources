# NfsLookupDirCache

- ea: `0x1400186ac`
- end: `0x1400187fb`
- name: `NfsLookupDirCache`
- size: `335`
- prototype: `__int64 __fastcall(int, int, int, int, STRING *String1, BOOLEAN CaseInSensitive)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004530`
- `0x14002a9e0`

## callees

- `0x1400186ac`

## import_xrefs

- `ntoskrnl!RtlCompareString` at `0x14001874e`
- `ntoskrnl!RtlCompareString` at `0x14001874e`

## pseudocode

```c
__int64 __fastcall NfsLookupDirCache(
        __int64 a1,
        __int64 a2,
        char a3,
        _QWORD *a4,
        STRING *String1,
        BOOLEAN CaseInSensitive)
{
  int *v10; // rsi
  unsigned __int64 v11; // rdi
  USHORT *v12; // r14
  bool v13; // zf
  _DWORD *v14; // rcx
  int v15; // eax
  STRING String2; // [rsp+20h] [rbp-48h] BYREF

  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  if ( !a1 )
    return 261;
  *(_DWORD *)(a2 + 20) = *(_DWORD *)a1;
  v10 = **(int ***)(a1 + 8);
  *(_QWORD *)(a2 + 24) = v10;
  *(_WORD *)(a2 + 16) = 0;
  v11 = (unsigned __int64)(v10 + 10);
  *(_QWORD *)(a2 + 32) = v10 + 10;
  *(_QWORD *)(a2 + 40) = v10 + 10;
  if ( !v10 )
    return 261;
  while ( 1 )
  {
    if ( v10[6] > 0 )
    {
      while ( 1 )
      {
        v12 = (USHORT *)(v11 + 16);
        if ( a3 )
        {
          v13 = *a4 == *(_QWORD *)v11;
        }
        else
        {
          String2.Length = *v12;
          String2.MaximumLength = String2.Length;
          String2.Buffer = (PCHAR)(v11 + 184);
          v13 = RtlCompareString(String1, &String2, CaseInSensitive) == 0;
        }
        if ( v13 )
          break;
        ++*(_WORD *)(a2 + 16);
        v11 = (*(_DWORD *)v12 + 184 + v11 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        if ( *(unsigned __int16 *)(a2 + 16) >= v10[6] )
          goto LABEL_9;
      }
      *(_QWORD *)(a2 + 24) = v10;
      *(_DWORD *)(a2 + 20) = *(_DWORD *)a1;
      v15 = *(_DWORD *)v12 + 184;
      *(_QWORD *)(a2 + 40) = v11;
      *(_QWORD *)(a2 + 32) = (v11 + v15 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL;
      return 0;
    }
LABEL_9:
    *(_WORD *)(a2 + 16) = 0;
    v14 = *(_DWORD **)(a1 + 8);
    v10 = *(int **)v10;
    if ( v10 == *(int **)v14 )
      break;
    v11 = (unsigned __int64)(v10 + 10);
  }
  if ( (*(_DWORD *)(*(_QWORD *)v14 + 8LL) & 2) == 0 )
    return 261;
  return (v14[2] & 1) != 0 ? -1073741809 : 261;
}

```

## disassembly

```asm
0x1400186ac  push    rbx
0x1400186ae  push    rbp
0x1400186af  push    rsi
0x1400186b0  push    rdi
0x1400186b1  push    r12
0x1400186b3  push    r14
0x1400186b5  push    r15
0x1400186b7  sub     rsp, 30h
0x1400186bb  xor     eax, eax
0x1400186bd  mov     r12, r9
0x1400186c0  mov     qword ptr [rsp+68h+String2.Length], rax
0x1400186c5  mov     bpl, r8b
0x1400186c8  mov     [rsp+68h+String2.Buffer], rax
0x1400186cd  mov     rbx, rdx
0x1400186d0  mov     r15, rcx
0x1400186d3  test    rcx, rcx
0x1400186d6  jz      loc_1400187E6
0x1400186dc  mov     eax, [rcx]
0x1400186de  mov     [rdx+14h], eax
0x1400186e1  mov     rax, [rcx+8]
0x1400186e5  mov     rsi, [rax]
0x1400186e8  xor     eax, eax
0x1400186ea  mov     [rdx+18h], rsi
0x1400186ee  mov     [rdx+10h], ax
0x1400186f2  lea     rdi, [rsi+28h]
0x1400186f6  mov     [rdx+20h], rdi
0x1400186fa  mov     [rdx+28h], rdi
0x1400186fe  test    rsi, rsi
0x140018701  jz      loc_1400187E6
0x140018707  cmp     dword ptr [rsi+18h], 0
0x14001870b  jle     short loc_140018780
0x14001870d  lea     r14, [rdi+10h]
0x140018711  test    bpl, bpl
0x140018714  jz      short loc_14001871F
0x140018716  mov     rax, [rdi]
0x140018719  cmp     [r12], rax
0x14001871d  jmp     short loc_14001875C
0x14001871f  movzx   eax, word ptr [r14]
0x140018723  lea     rdx, [rsp+68h+String2]; String2
0x140018728  mov     r8b, [rsp+68h+CaseInSensitive]; CaseInSensitive
0x140018730  mov     rcx, [rsp+68h+String1]; String1
0x140018738  mov     [rsp+68h+String2.Length], ax
0x14001873d  mov     [rsp+68h+String2.MaximumLength], ax
0x140018742  lea     rax, [rdi+0B8h]
0x140018749  mov     [rsp+68h+String2.Buffer], rax
0x14001874e  call    cs:__imp_RtlCompareString
0x140018755  nop     dword ptr [rax+rax+00h]
0x14001875a  test    eax, eax
0x14001875c  jz      short loc_14001879E
0x14001875e  inc     word ptr [rbx+10h]
0x140018762  add     rdi, 7
0x140018766  mov     eax, [r14]
0x140018769  movzx   ecx, word ptr [rbx+10h]
0x14001876d  add     eax, 0B8h
0x140018772  cdqe
0x140018774  add     rdi, rax
0x140018777  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14001877b  cmp     ecx, [rsi+18h]
0x14001877e  jl      short loc_14001870D
0x140018780  xor     eax, eax
0x140018782  mov     [rbx+10h], ax
0x140018786  mov     rcx, [r15+8]
0x14001878a  mov     rsi, [rsi]
0x14001878d  mov     rax, [rcx]
0x140018790  cmp     rsi, rax
0x140018793  jz      short loc_1400187CA
0x140018795  lea     rdi, [rsi+28h]
0x140018799  jmp     loc_140018707
0x14001879e  mov     [rbx+18h], rsi
0x1400187a2  mov     eax, [r15]
0x1400187a5  mov     [rbx+14h], eax
0x1400187a8  mov     eax, [r14]
0x1400187ab  add     eax, 0B8h
0x1400187b0  mov     [rbx+28h], rdi
0x1400187b4  movsxd  rcx, eax
0x1400187b7  add     rcx, 7
0x1400187bb  add     rcx, rdi
0x1400187be  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1400187c2  mov     [rbx+20h], rcx
0x1400187c6  xor     eax, eax
0x1400187c8  jmp     short loc_1400187EB
0x1400187ca  mov     eax, [rax+8]
0x1400187cd  test    al, 2
0x1400187cf  jz      short loc_1400187E6
0x1400187d1  mov     eax, [rcx+8]
0x1400187d4  and     al, 1
0x1400187d6  neg     al
0x1400187d8  sbb     eax, eax
0x1400187da  and     eax, 0BFFFFF0Ah
0x1400187df  add     eax, 105h
0x1400187e4  jmp     short loc_1400187EB
0x1400187e6  mov     eax, 105h
0x1400187eb  add     rsp, 30h
0x1400187ef  pop     r15
0x1400187f1  pop     r14
0x1400187f3  pop     r12
0x1400187f5  pop     rdi
0x1400187f6  pop     rsi
0x1400187f7  pop     rbp
0x1400187f8  pop     rbx
0x1400187f9  retn
```
