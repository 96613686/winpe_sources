# CIPropertyStorageWrapper::ReadMultiple(ulong,tagPROPSPEC const * const,tagPROPVARIANT * const)

- ea: `0x180011840`
- end: `0x18001195d`
- name: `?ReadMultiple@CIPropertyStorageWrapper@@UEAAJKQEBUtagPROPSPEC@@QEAUtagPROPVARIANT@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CIPropertyStorageWrapper *__hidden this, unsigned int, const struct tagPROPSPEC *const, struct tagPROPVARIANT *const)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011330`
- `0x180011840`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18001193d`
- `KERNEL32!ReleaseMutex` at `0x18001193d`
- `KERNEL32!WaitForSingleObject` at `0x180011885`
- `KERNEL32!WaitForSingleObject` at `0x180011885`
- `KERNEL32!lstrcmpiW` at `0x1800118be`
- `KERNEL32!lstrcmpiW` at `0x1800118be`

## pseudocode

```c
__int64 __fastcall CIPropertyStorageWrapper::ReadMultiple(
        CIPropertyStorageWrapper *this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        struct tagPROPVARIANT *const a4)
{
  void *v8; // rcx
  unsigned int v10; // r12d
  __int64 v11; // rdi
  const WCHAR *lpwstr; // r15
  __int64 *j; // rbx
  CIPropertyStorageWrapper *v14; // rcx
  __int64 *i; // rdx

  if ( !a3 || !a4 )
    return 2147944180LL;
  v8 = (void *)*((_QWORD *)this + 5);
  if ( !v8 )
    return 2147680264LL;
  WaitForSingleObject(v8, 0xFFFFFFFF);
  v10 = 0;
  if ( a2 )
  {
    v11 = 0;
    do
    {
      if ( a3[v11].ulKind )
      {
        if ( a3[v11].ulKind != 1 )
        {
          a4[v11].vt = 0;
          goto LABEL_23;
        }
        for ( i = (__int64 *)*((_QWORD *)this + 2); i; i = (__int64 *)*i )
        {
          if ( *((_DWORD *)i + 5) == LODWORD(a3[v11].propid) )
            break;
        }
        v14 = (CIPropertyStorageWrapper *)&a4[v11];
        if ( !i )
        {
LABEL_21:
          *(_WORD *)v14 = 0;
          goto LABEL_23;
        }
      }
      else
      {
        lpwstr = a3[v11].lpwstr;
        for ( j = (__int64 *)*((_QWORD *)this + 2);
              j && (*((_DWORD *)j + 4) || lstrcmpiW((LPCWSTR)j[3], lpwstr));
              j = (__int64 *)*j )
        {
          ;
        }
        v14 = (CIPropertyStorageWrapper *)&a4[v11];
        if ( !j )
          goto LABEL_21;
        i = j;
      }
      CIPropertyStorageWrapper::GetPropNodeData(v14, (struct _propertyNodeDef *)i, (struct tagPROPVARIANT *)v14);
LABEL_23:
      ++v10;
      ++v11;
    }
    while ( v10 < a2 );
  }
  ReleaseMutex(*((HANDLE *)this + 5));
  return 0;
}

```

## disassembly

```asm
0x180011840  push    rbx
0x180011842  push    rbp
0x180011843  push    rsi
0x180011844  push    rdi
0x180011845  push    r12
0x180011847  push    r13
0x180011849  push    r14
0x18001184b  push    r15
0x18001184d  sub     rsp, 28h
0x180011851  mov     r14, r9
0x180011854  mov     rbp, r8
0x180011857  mov     r13d, edx
0x18001185a  mov     rsi, rcx
0x18001185d  test    r8, r8
0x180011860  jz      loc_180011947
0x180011866  test    r9, r9
0x180011869  jz      loc_180011947
0x18001186f  mov     rcx, [rcx+28h]; hHandle
0x180011873  test    rcx, rcx
0x180011876  jnz     short loc_180011882
0x180011878  mov     eax, 80030008h
0x18001187d  jmp     loc_18001194C
0x180011882  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011885  call    cs:__imp_WaitForSingleObject
0x18001188b  xor     r12d, r12d
0x18001188e  test    r13d, r13d
0x180011891  jz      loc_180011939
0x180011897  xor     edi, edi
0x180011899  mov     rax, rdi
0x18001189c  add     rax, rax
0x18001189f  cmp     dword ptr [rbp+rax*8+0], 0
0x1800118a4  jnz     short loc_1800118EA
0x1800118a6  mov     r15, [rbp+rax*8+8]
0x1800118ab  mov     rbx, [rsi+10h]
0x1800118af  jmp     short loc_1800118CB
0x1800118b1  cmp     dword ptr [rbx+10h], 0
0x1800118b5  jnz     short loc_1800118C8
0x1800118b7  mov     rcx, [rbx+18h]; lpString1
0x1800118bb  mov     rdx, r15; lpString2
0x1800118be  call    cs:__imp_lstrcmpiW
0x1800118c4  test    eax, eax
0x1800118c6  jz      short loc_1800118D0
0x1800118c8  mov     rbx, [rbx]
0x1800118cb  test    rbx, rbx
0x1800118ce  jnz     short loc_1800118B1
0x1800118d0  lea     rax, [rdi+rdi*2]
0x1800118d4  lea     rcx, [r14+rax*8]; this
0x1800118d8  test    rbx, rbx
0x1800118db  jz      short loc_180011918
0x1800118dd  mov     rdx, rbx; struct _propertyNodeDef *
0x1800118e0  mov     r8, rcx; struct tagPROPVARIANT *
0x1800118e3  call    ?GetPropNodeData@CIPropertyStorageWrapper@@QEAAJPEAU_propertyNodeDef@@PEAUtagPROPVARIANT@@@Z; CIPropertyStorageWrapper::GetPropNodeData(_propertyNodeDef *,tagPROPVARIANT *)
0x1800118e8  jmp     short loc_18001192A
0x1800118ea  cmp     dword ptr [rbp+rax*8+0], 1
0x1800118ef  jnz     short loc_18001191F
0x1800118f1  mov     rdx, [rsi+10h]
0x1800118f5  test    rdx, rdx
0x1800118f8  jz      short loc_18001190B
0x1800118fa  mov     ecx, [rbp+rax*8+8]
0x1800118fe  cmp     [rdx+14h], ecx
0x180011901  jz      short loc_18001190B
0x180011903  mov     rdx, [rdx]
0x180011906  test    rdx, rdx
0x180011909  jnz     short loc_1800118FE
0x18001190b  lea     rax, [rdi+rdi*2]
0x18001190f  lea     rcx, [r14+rax*8]
0x180011913  test    rdx, rdx
0x180011916  jnz     short loc_1800118E0
0x180011918  xor     eax, eax
0x18001191a  mov     [rcx], ax
0x18001191d  jmp     short loc_18001192A
0x18001191f  lea     rcx, [rdi+rdi*2]
0x180011923  xor     eax, eax
0x180011925  mov     [r14+rcx*8], ax
0x18001192a  inc     r12d
0x18001192d  inc     rdi
0x180011930  cmp     r12d, r13d
0x180011933  jb      loc_180011899
0x180011939  mov     rcx, [rsi+28h]; hMutex
0x18001193d  call    cs:__imp_ReleaseMutex
0x180011943  xor     eax, eax
0x180011945  jmp     short loc_18001194C
0x180011947  mov     eax, 800706F4h
0x18001194c  add     rsp, 28h
0x180011950  pop     r15
0x180011952  pop     r14
0x180011954  pop     r13
0x180011956  pop     r12
0x180011958  pop     rdi
0x180011959  pop     rsi
0x18001195a  pop     rbp
0x18001195b  pop     rbx
0x18001195c  retn
```
