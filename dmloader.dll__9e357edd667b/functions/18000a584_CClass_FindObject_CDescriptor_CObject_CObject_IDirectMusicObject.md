# CClass::FindObject(CDescriptor *,CObject * *,CObject *,IDirectMusicObject *)

- ea: `0x18000a584`
- end: `0x18000a80a`
- name: `?FindObject@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@PEAV3@PEAUIDirectMusicObject@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(CClass *__hidden this, struct CDescriptor *, struct CObject **, struct CObject *, struct IDirectMusicObject *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800080f0`
- `0x180008710`
- `0x18000a958`
- `0x18000ad04`
- `0x18000bbc4`

## callees

- `0x18000a584`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a69c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a6e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a6f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a726`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a7a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a69c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a6e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a6f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a726`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a7a3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000a77c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000a78a`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000a77c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000a78a`

## pseudocode

```c
__int64 __fastcall CClass::FindObject(
        CClass *this,
        struct CDescriptor *a2,
        struct IDirectMusicObject ***a3,
        struct IDirectMusicObject **a4,
        struct IDirectMusicObject *a5)
{
  int v10; // r12d
  struct IDirectMusicObject **i; // rcx
  struct IDirectMusicObject *v12; // rdx
  struct IDirectMusicObject **j; // rcx
  struct IDirectMusicObject **k; // rbx
  wchar_t *v15; // rdx
  wchar_t *v16; // rcx
  wchar_t *v17; // r14
  wchar_t *v18; // rbp
  struct IDirectMusicObject **m; // rax

  if ( !a2 )
    return 2147500035LL;
  v10 = *((_DWORD *)a2 + 2);
  if ( (v10 & 1) != 0 )
  {
    for ( i = (struct IDirectMusicObject **)*((_QWORD *)this + 25); ; i = (struct IDirectMusicObject **)*i )
    {
      if ( !i )
        goto LABEL_11;
      if ( i != a4
        && ((_BYTE)i[2] & 1) != 0
        && *(struct IDirectMusicObject **)((char *)i + 20) == *(struct IDirectMusicObject **)((char *)a2 + 12)
        && *(struct IDirectMusicObject **)((char *)i + 28) == *(struct IDirectMusicObject **)((char *)a2 + 20) )
      {
        break;
      }
    }
LABEL_13:
    *a3 = i;
    return 0;
  }
LABEL_11:
  if ( (v10 & 0x400) != 0 )
  {
    for ( i = (struct IDirectMusicObject **)*((_QWORD *)this + 25); i; i = (struct IDirectMusicObject **)*i )
    {
      if ( i != a4 && ((_DWORD)i[2] & 0x400) != 0 && i[13] == *((struct IDirectMusicObject **)a2 + 12) )
        goto LABEL_13;
    }
  }
  if ( (v10 & 0x800) != 0 )
  {
    v12 = (struct IDirectMusicObject *)*((_QWORD *)a2 + 14);
    if ( v12 )
    {
      for ( j = (struct IDirectMusicObject **)*((_QWORD *)this + 25); ; j = (struct IDirectMusicObject **)*j )
      {
        if ( !j )
          goto LABEL_29;
        if ( j != a4 && ((_DWORD)j[2] & 0x800) != 0 && j[15] == v12 && j[16] == *((struct IDirectMusicObject **)a2 + 15) )
          break;
      }
      *a3 = j;
      return 0;
    }
  }
LABEL_29:
  if ( (v10 & 0x10) != 0 && (v10 & 0x20) != 0 )
  {
    for ( k = (struct IDirectMusicObject **)*((_QWORD *)this + 25); ; k = (struct IDirectMusicObject **)*k )
    {
      if ( !k )
        goto LABEL_38;
      if ( k != a4 && ((_BYTE)k[2] & 0x30) == 0x30 && !(unsigned int)_o__wcsicmp(k[11], *((_QWORD *)a2 + 10)) )
        break;
    }
LABEL_41:
    *a3 = k;
    return 0;
  }
LABEL_38:
  if ( (v10 & 4) != 0 )
  {
    if ( (v10 & 8) != 0 )
    {
      for ( k = (struct IDirectMusicObject **)*((_QWORD *)this + 25); k; k = (struct IDirectMusicObject **)*k )
      {
        if ( k != a4
          && ((_BYTE)k[2] & 0xC) == 0xC
          && !(unsigned int)_o__wcsicmp(k[10], *((_QWORD *)a2 + 9))
          && !(unsigned int)_o__wcsicmp(k[9], *((_QWORD *)a2 + 8)) )
        {
          goto LABEL_41;
        }
      }
    }
    for ( k = (struct IDirectMusicObject **)*((_QWORD *)this + 25); k; k = (struct IDirectMusicObject **)*k )
    {
      if ( k != a4 && ((_BYTE)k[2] & 4) != 0 && !(unsigned int)_o__wcsicmp(k[9], *((_QWORD *)a2 + 8)) )
        goto LABEL_41;
    }
  }
  if ( (v10 & 0x10) != 0 )
  {
    for ( k = (struct IDirectMusicObject **)*((_QWORD *)this + 25); k; k = (struct IDirectMusicObject **)*k )
    {
      if ( k != a4 && ((_DWORD)k[2] & 0x10) != 0 )
      {
        if ( (v10 & 0x20) == ((_DWORD)k[2] & 0x20) )
        {
          v15 = (wchar_t *)*((_QWORD *)a2 + 10);
          v16 = (wchar_t *)k[11];
        }
        else
        {
          v17 = (wchar_t *)k[11];
          v18 = (wchar_t *)*((_QWORD *)a2 + 10);
          if ( (v10 & 0x20) != 0 )
            v17 = wcsrchr((const wchar_t *)k[11], 0x5Cu);
          else
            v18 = wcsrchr(*((const wchar_t **)a2 + 10), 0x5Cu);
          if ( !v17 || !v18 )
            continue;
          v15 = v18;
          v16 = v17;
        }
        if ( !(unsigned int)_o__wcsicmp(v16, v15) )
          goto LABEL_41;
      }
    }
  }
  if ( a5 )
  {
    for ( m = (struct IDirectMusicObject **)*((_QWORD *)this + 25); m; m = (struct IDirectMusicObject **)*m )
    {
      if ( m != a4 && m[23] == a5 )
      {
        *a3 = m;
        return 0;
      }
    }
  }
  *a3 = 0;
  return 2289570181LL;
}

```

## disassembly

```asm
0x18000a584  push    rbx
0x18000a586  push    rbp
0x18000a587  push    rsi
0x18000a588  push    rdi
0x18000a589  push    r12
0x18000a58b  push    r13
0x18000a58d  push    r14
0x18000a58f  push    r15
0x18000a591  sub     rsp, 28h
0x18000a595  mov     r13, r9
0x18000a598  mov     rdi, r8
0x18000a59b  mov     rsi, rdx
0x18000a59e  mov     r15, rcx
0x18000a5a1  test    rdx, rdx
0x18000a5a4  jnz     short loc_18000A5B0
0x18000a5a6  mov     eax, 80004003h
0x18000a5ab  jmp     loc_18000A7F1
0x18000a5b0  mov     r12d, [rdx+8]
0x18000a5b4  test    r12b, 1
0x18000a5b8  jz      short loc_18000A5EA
0x18000a5ba  mov     rcx, [rcx+0C8h]
0x18000a5c1  jmp     short loc_18000A5E5
0x18000a5c3  cmp     rcx, r13
0x18000a5c6  jz      short loc_18000A5E2
0x18000a5c8  test    byte ptr [rcx+10h], 1
0x18000a5cc  jz      short loc_18000A5E2
0x18000a5ce  mov     rax, [rcx+14h]
0x18000a5d2  cmp     rax, [rdx+0Ch]
0x18000a5d6  jnz     short loc_18000A5E2
0x18000a5d8  mov     rax, [rcx+1Ch]
0x18000a5dc  cmp     rax, [rdx+14h]
0x18000a5e0  jz      short loc_18000A5FD
0x18000a5e2  mov     rcx, [rcx]
0x18000a5e5  test    rcx, rcx
0x18000a5e8  jnz     short loc_18000A5C3
0x18000a5ea  mov     edx, 400h
0x18000a5ef  test    edx, r12d
0x18000a5f2  jz      short loc_18000A623
0x18000a5f4  mov     rcx, [r15+0C8h]
0x18000a5fb  jmp     short loc_18000A61E
0x18000a5fd  mov     [r8], rcx
0x18000a600  xor     eax, eax
0x18000a602  jmp     loc_18000A7F1
0x18000a607  cmp     rcx, r13
0x18000a60a  jz      short loc_18000A61B
0x18000a60c  test    [rcx+10h], edx
0x18000a60f  jz      short loc_18000A61B
0x18000a611  mov     rax, [rsi+60h]
0x18000a615  cmp     [rcx+68h], rax
0x18000a619  jz      short loc_18000A5FD
0x18000a61b  mov     rcx, [rcx]
0x18000a61e  test    rcx, rcx
0x18000a621  jnz     short loc_18000A607
0x18000a623  mov     r8d, 800h
0x18000a629  test    r8d, r12d
0x18000a62c  jz      short loc_18000A666
0x18000a62e  mov     rdx, [rsi+70h]
0x18000a632  test    rdx, rdx
0x18000a635  jz      short loc_18000A666
0x18000a637  mov     rcx, [r15+0C8h]
0x18000a63e  jmp     short loc_18000A661
0x18000a640  cmp     rcx, r13
0x18000a643  jz      short loc_18000A65E
0x18000a645  test    [rcx+10h], r8d
0x18000a649  jz      short loc_18000A65E
0x18000a64b  cmp     [rcx+78h], rdx
0x18000a64f  jnz     short loc_18000A65E
0x18000a651  mov     rax, [rsi+78h]
0x18000a655  cmp     [rcx+80h], rax
0x18000a65c  jz      short loc_18000A67D
0x18000a65e  mov     rcx, [rcx]
0x18000a661  test    rcx, rcx
0x18000a664  jnz     short loc_18000A640
0x18000a666  mov     ebp, r12d
0x18000a669  and     ebp, 10h
0x18000a66c  jz      short loc_18000A6AE
0x18000a66e  test    r12b, 20h
0x18000a672  jz      short loc_18000A6AE
0x18000a674  mov     rbx, [r15+0C8h]
0x18000a67b  jmp     short loc_18000A6A9
0x18000a67d  mov     [rdi], rcx
0x18000a680  jmp     loc_18000A600
0x18000a685  cmp     rbx, r13
0x18000a688  jz      short loc_18000A6A6
0x18000a68a  mov     eax, [rbx+10h]
0x18000a68d  and     eax, 30h
0x18000a690  cmp     al, 30h ; '0'
0x18000a692  jnz     short loc_18000A6A6
0x18000a694  mov     rdx, [rsi+50h]
0x18000a698  mov     rcx, [rbx+58h]
0x18000a69c  call    cs:__imp__o__wcsicmp
0x18000a6a2  test    eax, eax
0x18000a6a4  jz      short loc_18000A6C7
0x18000a6a6  mov     rbx, [rbx]
0x18000a6a9  test    rbx, rbx
0x18000a6ac  jnz     short loc_18000A685
0x18000a6ae  test    r12b, 4
0x18000a6b2  jz      loc_18000A738
0x18000a6b8  test    r12b, 8
0x18000a6bc  jz      short loc_18000A70A
0x18000a6be  mov     rbx, [r15+0C8h]
0x18000a6c5  jmp     short loc_18000A705
0x18000a6c7  mov     [rdi], rbx
0x18000a6ca  jmp     loc_18000A600
0x18000a6cf  cmp     rbx, r13
0x18000a6d2  jz      short loc_18000A702
0x18000a6d4  mov     eax, [rbx+10h]
0x18000a6d7  and     eax, 0Ch
0x18000a6da  cmp     al, 0Ch
0x18000a6dc  jnz     short loc_18000A702
0x18000a6de  mov     rdx, [rsi+48h]
0x18000a6e2  mov     rcx, [rbx+50h]
0x18000a6e6  call    cs:__imp__o__wcsicmp
0x18000a6ec  test    eax, eax
0x18000a6ee  jnz     short loc_18000A702
0x18000a6f0  mov     rdx, [rsi+40h]
0x18000a6f4  mov     rcx, [rbx+48h]
0x18000a6f8  call    cs:__imp__o__wcsicmp
0x18000a6fe  test    eax, eax
0x18000a700  jz      short loc_18000A6C7
0x18000a702  mov     rbx, [rbx]
0x18000a705  test    rbx, rbx
0x18000a708  jnz     short loc_18000A6CF
0x18000a70a  mov     rbx, [r15+0C8h]
0x18000a711  jmp     short loc_18000A733
0x18000a713  cmp     rbx, r13
0x18000a716  jz      short loc_18000A730
0x18000a718  test    byte ptr [rbx+10h], 4
0x18000a71c  jz      short loc_18000A730
0x18000a71e  mov     rdx, [rsi+40h]
0x18000a722  mov     rcx, [rbx+48h]
0x18000a726  call    cs:__imp__o__wcsicmp
0x18000a72c  test    eax, eax
0x18000a72e  jz      short loc_18000A6C7
0x18000a730  mov     rbx, [rbx]
0x18000a733  test    rbx, rbx
0x18000a736  jnz     short loc_18000A713
0x18000a738  test    ebp, ebp
0x18000a73a  jz      short loc_18000A7B9
0x18000a73c  mov     rbx, [r15+0C8h]
0x18000a743  jmp     short loc_18000A7B4
0x18000a745  cmp     rbx, r13
0x18000a748  jz      short loc_18000A7B1
0x18000a74a  mov     eax, [rbx+10h]
0x18000a74d  test    al, 10h
0x18000a74f  jz      short loc_18000A7B1
0x18000a751  mov     ecx, r12d
0x18000a754  and     eax, 20h
0x18000a757  and     ecx, 20h
0x18000a75a  cmp     ecx, eax
0x18000a75c  jnz     short loc_18000A768
0x18000a75e  mov     rdx, [rsi+50h]
0x18000a762  mov     rcx, [rbx+58h]
0x18000a766  jmp     short loc_18000A7A3
0x18000a768  mov     r14, [rbx+58h]
0x18000a76c  mov     edx, 5Ch ; '\'; Ch
0x18000a771  mov     rbp, [rsi+50h]
0x18000a775  test    ecx, ecx
0x18000a777  jz      short loc_18000A787
0x18000a779  mov     rcx, r14; Str
0x18000a77c  call    cs:__imp_wcsrchr
0x18000a782  mov     r14, rax
0x18000a785  jmp     short loc_18000A793
0x18000a787  mov     rcx, rbp; Str
0x18000a78a  call    cs:__imp_wcsrchr
0x18000a790  mov     rbp, rax
0x18000a793  test    r14, r14
0x18000a796  jz      short loc_18000A7B1
0x18000a798  test    rbp, rbp
0x18000a79b  jz      short loc_18000A7B1
0x18000a79d  mov     rdx, rbp
0x18000a7a0  mov     rcx, r14
0x18000a7a3  call    cs:__imp__o__wcsicmp
0x18000a7a9  test    eax, eax
0x18000a7ab  jz      loc_18000A6C7
0x18000a7b1  mov     rbx, [rbx]
0x18000a7b4  test    rbx, rbx
0x18000a7b7  jnz     short loc_18000A745
0x18000a7b9  mov     rcx, [rsp+68h+arg_20]
0x18000a7c1  test    rcx, rcx
0x18000a7c4  jz      short loc_18000A7E5
0x18000a7c6  mov     rax, [r15+0C8h]
0x18000a7cd  jmp     short loc_18000A7E0
0x18000a7cf  cmp     rax, r13
0x18000a7d2  jz      short loc_18000A7DD
0x18000a7d4  cmp     [rax+0B8h], rcx
0x18000a7db  jz      short loc_18000A802
0x18000a7dd  mov     rax, [rax]
0x18000a7e0  test    rax, rax
0x18000a7e3  jnz     short loc_18000A7CF
0x18000a7e5  mov     qword ptr [rdi], 0
0x18000a7ec  mov     eax, 88781185h
0x18000a7f1  add     rsp, 28h
0x18000a7f5  pop     r15
0x18000a7f7  pop     r14
0x18000a7f9  pop     r13
0x18000a7fb  pop     r12
0x18000a7fd  pop     rdi
0x18000a7fe  pop     rsi
0x18000a7ff  pop     rbp
0x18000a800  pop     rbx
0x18000a801  retn
0x18000a802  mov     [rdi], rax
0x18000a805  jmp     loc_18000A600
```
