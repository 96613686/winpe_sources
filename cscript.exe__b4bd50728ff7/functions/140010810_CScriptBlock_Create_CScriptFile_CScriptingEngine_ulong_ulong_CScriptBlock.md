# CScriptBlock::Create(CScriptFile *,CScriptingEngine *,ulong,ulong,CScriptBlock * *)

- ea: `0x140010810`
- end: `0x1400108e7`
- name: `?Create@CScriptBlock@@SAJPEAVCScriptFile@@PEAVCScriptingEngine@@KKPEAPEAV1@@Z`
- size: `215`
- prototype: `__int64 __fastcall(struct CScriptFile *, struct CScriptingEngine *, unsigned int, unsigned int, struct CScriptBlock **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011bc`
- `0x14000e740`
- `0x14000fe80`

## callees

- `0x140009c70`
- `0x140010810`

## pseudocode

```c
__int64 __fastcall CScriptBlock::Create(
        struct CScriptFile *a1,
        struct CScriptingEngine *a2,
        int a3,
        int a4,
        struct CScriptBlock **a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rdx
  __int64 result; // rax

  if ( !a1 || !a2 || !a5 )
    return 2147500035LL;
  v9 = operator new(0x58u);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  v9[1] = &IPrivateDocumentContext::`vftable';
  v9[2] = &CUnknown::`vftable';
  v9[5] = &CUnknown::InnerUnknown::`vftable';
  *((_DWORD *)v9 + 12) = 1;
  v9[3] = v9 + 5;
  v9[4] = v9;
  _InterlockedIncrement(&Global::g_cObjects);
  *v9 = &CScriptBlock::`vftable'{for `IDebugDocumentContext'};
  v9[1] = &CScriptBlock::`vftable'{for `IPrivateDocumentContext'};
  v9[2] = &CScriptBlock::`vftable'{for `CUnknown'};
  *((_DWORD *)v9 + 20) = a3 + a4;
  result = 0;
  v10[7] = a1;
  v10[8] = a2;
  *((_DWORD *)v10 + 18) = a3;
  *((_DWORD *)v10 + 19) = a4;
  *a5 = (struct CScriptBlock *)v10;
  return result;
}

```

## disassembly

```asm
0x140010810  push    rbx
0x140010812  push    rbp
0x140010813  push    rsi
0x140010814  push    rdi
0x140010815  push    r14
0x140010817  sub     rsp, 20h
0x14001081b  mov     ebp, r9d
0x14001081e  mov     r14d, r8d
0x140010821  mov     rdi, rdx
0x140010824  mov     rsi, rcx
0x140010827  test    rcx, rcx
0x14001082a  jz      loc_1400108D7
0x140010830  test    rdx, rdx
0x140010833  jz      loc_1400108D7
0x140010839  mov     rbx, [rsp+48h+arg_20]
0x14001083e  test    rbx, rbx
0x140010841  jz      loc_1400108D7
0x140010847  mov     ecx, 58h ; 'X'; Size
0x14001084c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010851  mov     rdx, rax
0x140010854  test    rax, rax
0x140010857  jz      short loc_1400108D0
0x140010859  lea     rcx, [rdx+28h]
0x14001085d  lea     rax, ??_7IPrivateDocumentContext@@6B@; const IPrivateDocumentContext::`vftable'
0x140010864  mov     [rdx+8], rax
0x140010868  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x14001086f  mov     [rdx+10h], rax
0x140010873  lea     rax, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x14001087a  mov     [rcx], rax
0x14001087d  mov     dword ptr [rcx+8], 1
0x140010884  mov     [rdx+18h], rcx
0x140010888  mov     [rdx+20h], rdx
0x14001088c  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x140010893  lea     rax, ??_7CScriptBlock@@6BIDebugDocumentContext@@@; const CScriptBlock::`vftable'{for `IDebugDocumentContext'}
0x14001089a  mov     [rdx], rax
0x14001089d  lea     rax, ??_7CScriptBlock@@6BIPrivateDocumentContext@@@; const CScriptBlock::`vftable'{for `IPrivateDocumentContext'}
0x1400108a4  mov     [rdx+8], rax
0x1400108a8  lea     rax, ??_7CScriptBlock@@6BCUnknown@@@; const CScriptBlock::`vftable'{for `CUnknown'}
0x1400108af  mov     [rdx+10h], rax
0x1400108b3  lea     eax, [r14+rbp]
0x1400108b7  mov     [rdx+50h], eax
0x1400108ba  xor     eax, eax
0x1400108bc  mov     [rdx+38h], rsi
0x1400108c0  mov     [rdx+40h], rdi
0x1400108c4  mov     [rdx+48h], r14d
0x1400108c8  mov     [rdx+4Ch], ebp
0x1400108cb  mov     [rbx], rdx
0x1400108ce  jmp     short loc_1400108DC
0x1400108d0  mov     eax, 8007000Eh
0x1400108d5  jmp     short loc_1400108DC
0x1400108d7  mov     eax, 80004003h
0x1400108dc  add     rsp, 20h
0x1400108e0  pop     r14
0x1400108e2  pop     rdi
0x1400108e3  pop     rsi
0x1400108e4  pop     rbp
0x1400108e5  pop     rbx
0x1400108e6  retn
```
