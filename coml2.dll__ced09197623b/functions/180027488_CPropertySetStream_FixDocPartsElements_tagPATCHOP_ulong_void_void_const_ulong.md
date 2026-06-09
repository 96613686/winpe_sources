# CPropertySetStream::_FixDocPartsElements(tagPATCHOP,ulong,void *,void const *,ulong *)

- ea: `0x180027488`
- end: `0x180027620`
- name: `?_FixDocPartsElements@CPropertySetStream@@AEAAEW4tagPATCHOP@@KPEAXPEFBXPEAK@Z`
- size: `408`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180029f04`
- `0x180038d54`

## callees

- `0x180027488`
- `0x180029040`
- `0x180043100`
- `0x180061428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800274fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800274fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800275f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800275f5`

## pseudocode

```c
char __fastcall CPropertySetStream::_FixDocPartsElements(
        CPropertySetStream *a1,
        int a2,
        unsigned int a3,
        unsigned int *a4,
        _DWORD *a5,
        unsigned int *a6)
{
  int v7; // ebx
  __int64 v8; // rdi
  unsigned int v10; // ebp
  unsigned __int64 v11; // rax
  _DWORD *v13; // r15
  unsigned int v15; // r8d
  char v16; // si
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // ecx
  int v20; // ebx
  struct tagPROPERTYSECTIONHEADER *v21; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+18h]
  unsigned int v24; // [rsp+98h] [rbp+30h]

  v7 = a2;
  v8 = a3;
  v21 = 0;
  v10 = *a6;
  if ( (int)CPropertySetStream::_GetAndValidateSectionHeader(a1, &v21) < 0 )
    return 0;
  if ( !(_DWORD)v8 )
  {
    *a6 = 0;
    return 1;
  }
  v11 = 4LL * (unsigned int)v8;
  if ( v11 > 0xFFFFFFFF )
    return 0;
  v13 = CoTaskMemAlloc((unsigned int)v11);
  if ( !v13 )
    return 0;
  v15 = v8;
  v24 = v8;
  v16 = 1;
  while ( 1 )
  {
    if ( !(_DWORD)v8 )
    {
      v10 = 0;
      while ( 1 )
      {
        v18 = v13[v8];
        v23 = v18;
        v19 = (v18 + 3) & 0xFFFFFFFC;
        v10 += v19;
        a4 = (unsigned int *)((char *)a4 - v19);
        a5 = (_DWORD *)((char *)a5 - v18);
        if ( v7 == 2 )
          break;
        if ( v7 )
          goto LABEL_17;
LABEL_18:
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= v15 )
          goto LABEL_21;
      }
      v20 = v13[v8];
      memmove_0(a4, a5, v18);
      memset_0((char *)a4 + (int)v23, 0, -v20 & 3);
      v15 = v24;
      v7 = a2;
LABEL_17:
      *a4 = (*a4 + 3) & 0xFFFFFFFC;
      goto LABEL_18;
    }
    if ( v10 < 4 )
      break;
    v17 = *a5 + 4;
    if ( v10 < v17 )
      break;
    v10 -= v17;
    if ( v7 == 1 )
      v17 = (*a5 + 7) & 0xFFFFFFFC;
    v8 = (unsigned int)(v8 - 1);
    a4 = (unsigned int *)((char *)a4 + ((int)(v17 + 3) & 0xFFFFFFFFFFFFFFFCuLL));
    a5 = (_DWORD *)((char *)a5 + (int)v17);
    v13[v8] = v17;
  }
  v16 = 0;
LABEL_21:
  *a6 = v10;
  CoTaskMemFree(v13);
  return v16;
}

```

## disassembly

```asm
0x180027488  mov     rax, rsp
0x18002748b  mov     [rax+8], rbx
0x18002748f  mov     [rax+10h], edx
0x180027492  push    rbp
0x180027493  push    rsi
0x180027494  push    rdi
0x180027495  push    r12
0x180027497  push    r13
0x180027499  push    r14
0x18002749b  push    r15
0x18002749d  sub     rsp, 30h
0x1800274a1  mov     r13, [rsp+68h+arg_28]
0x1800274a9  mov     ebx, edx
0x1800274ab  lea     rdx, [rax-48h]; struct tagPROPERTYSECTIONHEADER **
0x1800274af  mov     edi, r8d
0x1800274b2  mov     r14, r9
0x1800274b5  mov     qword ptr [rax-48h], 0
0x1800274bd  mov     ebp, [r13+0]
0x1800274c1  call    ?_GetAndValidateSectionHeader@CPropertySetStream@@AEAAJPEAPEAUtagPROPERTYSECTIONHEADER@@@Z; CPropertySetStream::_GetAndValidateSectionHeader(tagPROPERTYSECTIONHEADER * *)
0x1800274c6  test    eax, eax
0x1800274c8  js      short loc_1800274E2
0x1800274ca  test    edi, edi
0x1800274cc  jz      loc_180027603
0x1800274d2  mov     eax, edi
0x1800274d4  mov     ecx, 0FFFFFFFFh
0x1800274d9  shl     rax, 2
0x1800274dd  cmp     rax, rcx
0x1800274e0  jbe     short loc_1800274F9
0x1800274e2  xor     al, al
0x1800274e4  mov     rbx, [rsp+68h+arg_0]
0x1800274e9  add     rsp, 30h
0x1800274ed  pop     r15
0x1800274ef  pop     r14
0x1800274f1  pop     r13
0x1800274f3  pop     r12
0x1800274f5  pop     rdi
0x1800274f6  pop     rsi
0x1800274f7  pop     rbp
0x1800274f8  retn
0x1800274f9  mov     ecx, eax; cb
0x1800274fb  call    cs:__imp_CoTaskMemAlloc
0x180027501  mov     r15, rax
0x180027504  test    rax, rax
0x180027507  jz      short loc_1800274E2
0x180027509  mov     r12, [rsp+68h+arg_20]
0x180027511  mov     r8d, edi
0x180027514  mov     dword ptr [rsp+68h+arg_28], edi
0x18002751b  mov     esi, 1
0x180027520  mov     r9d, 0FFFFFFFFh
0x180027526  test    edi, edi
0x180027528  jz      short loc_180027568
0x18002752a  cmp     ebp, 4
0x18002752d  jb      loc_1800275EB
0x180027533  mov     edx, [r12]
0x180027537  add     edx, 4
0x18002753a  cmp     ebp, edx
0x18002753c  jb      loc_1800275EB
0x180027542  sub     ebp, edx
0x180027544  cmp     ebx, esi
0x180027546  jz      loc_180027615
0x18002754c  lea     eax, [rdx+3]
0x18002754f  add     edi, r9d
0x180027552  movsxd  rcx, eax
0x180027555  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180027559  movsxd  rax, edx
0x18002755c  add     r14, rcx
0x18002755f  add     r12, rax
0x180027562  mov     [r15+rdi*4], edx
0x180027566  jmp     short loc_180027526
0x180027568  xor     ebp, ebp
0x18002756a  test    r8d, r8d
0x18002756d  jz      short loc_1800275EE
0x18002756f  mov     edx, [r15+rdi*4]
0x180027573  mov     [rsp+68h+arg_10], edx
0x18002757a  lea     ecx, [rdx+3]
0x18002757d  and     ecx, 0FFFFFFFCh
0x180027580  mov     eax, ecx
0x180027582  add     ebp, ecx
0x180027584  neg     eax
0x180027586  cdqe
0x180027588  add     r14, rax
0x18002758b  mov     eax, edx
0x18002758d  neg     eax
0x18002758f  cdqe
0x180027591  add     r12, rax
0x180027594  cmp     ebx, 2
0x180027597  jnz     short loc_1800275D2
0x180027599  mov     ebx, edx
0x18002759b  mov     r8d, edx; Size
0x18002759e  mov     rdx, r12; Src
0x1800275a1  mov     rcx, r14; void *
0x1800275a4  call    memmove_0
0x1800275a9  movsxd  rcx, [rsp+68h+arg_10]
0x1800275b1  neg     rbx
0x1800275b4  and     ebx, 3
0x1800275b7  add     rcx, r14; void *
0x1800275ba  mov     r8d, ebx; Size
0x1800275bd  xor     edx, edx; Val
0x1800275bf  call    memset_0
0x1800275c4  mov     r8d, dword ptr [rsp+68h+arg_28]
0x1800275cc  mov     ebx, [rsp+68h+arg_8]
0x1800275d0  jmp     short loc_1800275D6
0x1800275d2  test    ebx, ebx
0x1800275d4  jz      short loc_1800275E2
0x1800275d6  mov     eax, [r14]
0x1800275d9  add     eax, 3
0x1800275dc  and     eax, 0FFFFFFFCh
0x1800275df  mov     [r14], eax
0x1800275e2  add     edi, esi
0x1800275e4  cmp     edi, r8d
0x1800275e7  jb      short loc_18002756F
0x1800275e9  jmp     short loc_1800275EE
0x1800275eb  xor     sil, sil
0x1800275ee  mov     rcx, r15; pv
0x1800275f1  mov     [r13+0], ebp
0x1800275f5  call    cs:__imp_CoTaskMemFree
0x1800275fb  mov     al, sil
0x1800275fe  jmp     loc_1800274E4
0x180027603  mov     dword ptr [r13+0], 0
0x18002760b  mov     eax, 1
0x180027610  jmp     loc_1800274E4
0x180027615  add     edx, 3
0x180027618  and     edx, 0FFFFFFFCh
0x18002761b  jmp     loc_18002754C
```
