# CPropertySetStream::_FixHeadingPairElements(tagPATCHOP,ulong,tagSERIALIZEDPROPERTYVALUE *,tagSERIALIZEDPROPERTYVALUE const *,ulong *)

- ea: `0x180034fdc`
- end: `0x1800351ab`
- name: `?_FixHeadingPairElements@CPropertySetStream@@AEAAEW4tagPATCHOP@@KPEAUtagSERIALIZEDPROPERTYVALUE@@PEFBU3@PEAK@Z`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180034f64`

## callees

- `0x180034fdc`
- `0x180043100`
- `0x180061428`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035163`

## pseudocode

```c
char __fastcall CPropertySetStream::_FixHeadingPairElements(
        __int64 a1,
        int a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5,
        unsigned int *a6)
{
  __int64 v6; // rbp
  int v8; // ebx
  unsigned __int64 v9; // rax
  unsigned int v10; // r14d
  _DWORD *v11; // r12
  unsigned int v13; // r8d
  char v14; // si
  unsigned int v15; // edx
  signed int v16; // edx
  int v17; // edx
  unsigned int v18; // ecx
  unsigned int v19; // edx
  __int64 v20; // rdi
  unsigned int v21; // ebx
  unsigned int v24; // [rsp+70h] [rbp+18h]

  v6 = a3;
  v8 = a2;
  if ( !a3 )
  {
    *a6 = 0;
    return 1;
  }
  v9 = 4LL * a3;
  if ( v9 > 0xFFFFFFFF )
    return 0;
  v10 = *a6;
  v11 = CoTaskMemAlloc((unsigned int)v9);
  if ( !v11 )
    return 0;
  v13 = v6;
  v24 = v6;
  v14 = 1;
  while ( 1 )
  {
    if ( !(_DWORD)v6 )
    {
      v10 = 0;
      if ( !v13 )
        goto LABEL_21;
      while ( 1 )
      {
        v17 = v11[v6];
        v18 = (v17 + 3) & 0xFFFFFFFC;
        v10 += v18;
        a4 = (_DWORD *)((char *)a4 - v18);
        a5 = (_DWORD *)((char *)a5 - v17);
        if ( v8 == 2 )
        {
          v19 = v17 - 8;
          v20 = (int)v19;
          v21 = v19;
          *(_QWORD *)((char *)a4 + ((int)(v19 + 3) & 0xFFFFFFFFFFFFFFFCuLL)) = *(_QWORD *)((char *)a5 + (int)v19);
          memmove_0(a4, a5, v19);
          memset_0((char *)a4 + v20, 0, -v21 & 3);
          v13 = v24;
          v8 = a2;
        }
        else if ( !v8 )
        {
          goto LABEL_18;
        }
        a4[1] = (a4[1] + 3) & 0xFFFFFFFC;
LABEL_18:
        v6 = (unsigned int)(v6 + 1);
        if ( (unsigned int)v6 >= v13 )
          goto LABEL_21;
      }
    }
    if ( v10 < 8 )
      break;
    if ( *a5 != 30 )
      break;
    v15 = a5[1] + 8;
    if ( v10 < v15 )
      break;
    if ( v8 == 1 )
      v15 = (a5[1] + 11) & 0xFFFFFFFC;
    if ( v10 < (unsigned __int64)(v15 + 4) + 4 || *(_DWORD *)((char *)a5 + (int)v15) != 3 )
      break;
    v16 = v15 + 8;
    v6 = (unsigned int)(v6 - 1);
    v10 -= v16;
    v11[v6] = v16;
    a4 = (_DWORD *)((char *)a4 + ((v16 + 3) & 0xFFFFFFFFFFFFFFFCuLL));
    a5 = (_DWORD *)((char *)a5 + v16);
  }
  v14 = 0;
LABEL_21:
  *a6 = v10;
  CoTaskMemFree(v11);
  return v14;
}

```

## disassembly

```asm
0x180034fdc  mov     [rsp+arg_0], rbx
0x180034fe1  mov     [rsp+arg_8], edx
0x180034fe5  push    rbp
0x180034fe6  push    rsi
0x180034fe7  push    rdi
0x180034fe8  push    r12
0x180034fea  push    r13
0x180034fec  push    r14
0x180034fee  push    r15
0x180034ff0  sub     rsp, 20h
0x180034ff4  mov     ebp, r8d
0x180034ff7  mov     r13, r9
0x180034ffa  mov     ebx, edx
0x180034ffc  test    r8d, r8d
0x180034fff  jz      loc_18003518B
0x180035005  mov     eax, ebp
0x180035007  mov     edi, 0FFFFFFFFh
0x18003500c  shl     rax, 2
0x180035010  cmp     rax, rdi
0x180035013  ja      loc_180035181
0x180035019  mov     r14, [rsp+58h+arg_28]
0x180035021  mov     ecx, eax; cb
0x180035023  mov     r14d, [r14]
0x180035026  call    cs:__imp_CoTaskMemAlloc
0x18003502c  mov     r12, rax
0x18003502f  test    rax, rax
0x180035032  jz      loc_180035181
0x180035038  mov     r15, [rsp+58h+arg_20]
0x180035040  mov     r8d, ebp
0x180035043  mov     [rsp+58h+arg_10], ebp
0x180035047  mov     esi, 1
0x18003504c  test    ebp, ebp
0x18003504e  jz      short loc_1800350BE
0x180035050  cmp     r14d, 8
0x180035054  jb      loc_180035152
0x18003505a  cmp     dword ptr [r15], 1Eh
0x18003505e  jnz     loc_180035152
0x180035064  mov     edx, [r15+4]
0x180035068  add     edx, 8
0x18003506b  cmp     r14d, edx
0x18003506e  jb      loc_180035152
0x180035074  cmp     ebx, esi
0x180035076  jz      loc_1800351A0
0x18003507c  lea     ecx, [rdx+4]
0x18003507f  mov     eax, r14d
0x180035082  add     rcx, 4
0x180035086  cmp     rax, rcx
0x180035089  jb      loc_180035152
0x18003508f  movsxd  rax, edx
0x180035092  cmp     dword ptr [rax+r15], 3
0x180035097  jnz     loc_180035152
0x18003509d  add     edx, 8
0x1800350a0  add     ebp, edi
0x1800350a2  sub     r14d, edx
0x1800350a5  lea     eax, [rdx+3]
0x1800350a8  mov     [r12+rbp*4], edx
0x1800350ac  movsxd  rcx, eax
0x1800350af  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1800350b3  movsxd  rax, edx
0x1800350b6  add     r13, rcx
0x1800350b9  add     r15, rax
0x1800350bc  jmp     short loc_18003504C
0x1800350be  xor     r14d, r14d
0x1800350c1  test    r8d, r8d
0x1800350c4  jz      loc_180035155
0x1800350ca  mov     edx, [r12+rbp*4]
0x1800350ce  lea     ecx, [rdx+3]
0x1800350d1  and     ecx, 0FFFFFFFCh
0x1800350d4  mov     eax, ecx
0x1800350d6  add     r14d, ecx
0x1800350d9  neg     eax
0x1800350db  cdqe
0x1800350dd  add     r13, rax
0x1800350e0  mov     eax, edx
0x1800350e2  neg     eax
0x1800350e4  cdqe
0x1800350e6  add     r15, rax
0x1800350e9  cmp     ebx, 2
0x1800350ec  jnz     loc_180035185
0x1800350f2  add     edx, 0FFFFFFF8h
0x1800350f5  movsxd  rdi, edx
0x1800350f8  mov     ebx, edx
0x1800350fa  mov     r8d, edx; Size
0x1800350fd  lea     eax, [rdx+3]
0x180035100  mov     rdx, r15; Src
0x180035103  movsxd  rcx, eax
0x180035106  mov     rax, [rdi+r15]
0x18003510a  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18003510e  mov     [rcx+r13], rax
0x180035112  mov     rcx, r13; void *
0x180035115  call    memmove_0
0x18003511a  neg     rbx
0x18003511d  lea     rcx, [rdi+r13]; void *
0x180035121  and     ebx, 3
0x180035124  xor     edx, edx; Val
0x180035126  mov     r8d, ebx; Size
0x180035129  call    memset_0
0x18003512e  mov     r8d, [rsp+58h+arg_10]
0x180035133  mov     ebx, [rsp+58h+arg_8]
0x180035137  mov     eax, [r13+4]
0x18003513b  add     eax, 3
0x18003513e  and     eax, 0FFFFFFFCh
0x180035141  mov     [r13+4], eax
0x180035145  add     ebp, esi
0x180035147  cmp     ebp, r8d
0x18003514a  jb      loc_1800350CA
0x180035150  jmp     short loc_180035155
0x180035152  xor     sil, sil
0x180035155  mov     rax, [rsp+58h+arg_28]
0x18003515d  mov     rcx, r12; pv
0x180035160  mov     [rax], r14d
0x180035163  call    cs:__imp_CoTaskMemFree
0x180035169  mov     al, sil
0x18003516c  mov     rbx, [rsp+58h+arg_0]
0x180035171  add     rsp, 20h
0x180035175  pop     r15
0x180035177  pop     r14
0x180035179  pop     r13
0x18003517b  pop     r12
0x18003517d  pop     rdi
0x18003517e  pop     rsi
0x18003517f  pop     rbp
0x180035180  retn
0x180035181  xor     al, al
0x180035183  jmp     short loc_18003516C
0x180035185  test    ebx, ebx
0x180035187  jnz     short loc_180035137
0x180035189  jmp     short loc_180035145
0x18003518b  mov     rax, [rsp+58h+arg_28]
0x180035193  mov     dword ptr [rax], 0
0x180035199  mov     eax, 1
0x18003519e  jmp     short loc_18003516C
0x1800351a0  add     edx, 3
0x1800351a3  and     edx, 0FFFFFFFCh
0x1800351a6  jmp     loc_18003507C
```
