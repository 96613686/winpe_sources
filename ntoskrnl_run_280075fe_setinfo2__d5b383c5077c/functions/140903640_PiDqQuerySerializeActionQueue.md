# PiDqQuerySerializeActionQueue

- ea: `0x140903640`
- end: `0x140903952`
- name: `PiDqQuerySerializeActionQueue`
- size: `786`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x140903e80`
- `0x14090556c`

## callees

- `0x140903070`
- `0x140903640`
- `0x140903958`
- `0x140904bd0`
- `0x140904c40`
- `0x1409050d8`
- `0x14090581c`
- `0x14090585c`
- `0x140bb19f0`

## import_xrefs

- `msrpc!MesHandleFree` at `0x1409038d9`
- `msrpc!MesHandleFree` at `0x1409038d9`
- `msrpc!MesEncodeIncrementalHandleCreate` at `0x1409036df`
- `msrpc!MesEncodeIncrementalHandleCreate` at `0x1409036df`
- `msrpc!MesIncrementalHandleReset` at `0x140903718`
- `msrpc!MesIncrementalHandleReset` at `0x140903718`
- `msrpc!NdrMesTypeEncode3` at `0x1409037af`
- `msrpc!NdrMesTypeEncode3` at `0x1409037af`

## pseudocode

```c
__int64 __fastcall PiDqQuerySerializeActionQueue(__int64 a1, __int64 a2, int a3, char a4, int *a5, _DWORD *a6)
{
  int v7; // esi
  int v8; // ebx
  struct _ERESOURCE *ObjectManager; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // r15
  __int64 v12; // rcx
  int v13; // ebx
  _QWORD v15[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  int v17; // [rsp+48h] [rbp-40h]
  int v18; // [rsp+4Ch] [rbp-3Ch]
  PVOID P; // [rsp+50h] [rbp-38h]
  int v20; // [rsp+58h] [rbp-30h]
  bool v21; // [rsp+5Ch] [rbp-2Ch]
  char v22; // [rsp+5Dh] [rbp-2Bh]
  __int16 v23; // [rsp+5Eh] [rbp-2Ah]
  PVOID v24; // [rsp+98h] [rbp+10h] BYREF

  v7 = 0;
  v15[0] = 0;
  v24 = 0;
  v23 = 0;
  v16 = a2;
  v17 = a3;
  v18 = 16;
  P = 0;
  v20 = 0;
  v21 = (a4 & 3) == 3;
  v22 = 0;
  PiDqQueryLock(a1);
  v8 = *(_DWORD *)(a1 + 216);
  PiDqQueryUnlock(a1);
  if ( (v8 & 0x20) == 0 )
  {
    ObjectManager = (struct _ERESOURCE *)PiDqQueryGetObjectManager(a1);
    v7 = PiDqObjectManagerEnumerateAndRegisterQuery(ObjectManager);
  }
  if ( v7 < 0 )
  {
LABEL_18:
    *a5 = 0;
    *a6 = 0;
  }
  else
  {
    v7 = MesEncodeIncrementalHandleCreate(&v16, PiDqSerializationAlloc, &PiDqSerializationWrite, v15);
    if ( v7 >= 0 )
    {
      v7 = MesIncrementalHandleReset(v15[0], &v16, 0, 0, 0, *(_DWORD *)(a1 + 216) & 2);
      if ( v7 >= 0 )
      {
        *a5 = v18;
        *a6 = 0;
        PiDqQueryLock(a1);
        v15[1] = a1 + 184;
        v24 = *(PVOID *)(a1 + 184);
        *(_QWORD *)(a1 + 184) = 0;
        PiDqQueryUnlock(a1);
        while ( 1 )
        {
          if ( v24 )
          {
            NdrMesTypeEncode3(v15[0], "TP 3\a", &off_140004F50, &off_140E0A510, 1, &v24);
            if ( (_BYTE)v23 )
            {
              v7 = -1073741819;
              goto LABEL_18;
            }
            if ( v22 )
            {
              PiDqQueryLock(a1);
              *(_QWORD *)(a1 + 184) = v24;
              v24 = 0;
              PiDqQueryUnlock(a1);
              *a6 = v20 + 16;
              break;
            }
            *a5 = v18;
            PiDqActionDataFree(v24);
            v24 = 0;
          }
          PiDqQueryLock(a1);
          v10 = (_QWORD *)(a1 + 192);
          v11 = *(_QWORD **)(a1 + 192);
          if ( v11 == (_QWORD *)(a1 + 192) )
          {
            PiDqQueryUnlock(a1);
            break;
          }
          if ( (_QWORD *)v11[1] != v10 || (v12 = *v11, *(_QWORD **)(*v11 + 8LL) != v11) )
            __fastfail(3u);
          *v10 = v12;
          *(_QWORD *)(v12 + 8) = v10;
          --*(_DWORD *)(a1 + 208);
          PiDqQueryUnlock(a1);
          v13 = PiDqActionDataCreate(*(_QWORD *)(a1 + 24), a1 + 32, v11, &v24);
          PiDqQueryActionQueueEntryFree(v11);
          v7 = 0;
          if ( v13 != -1073741772 )
            v7 = v13;
          if ( v7 < 0 )
            goto LABEL_18;
        }
      }
    }
    if ( v7 < 0 )
      goto LABEL_18;
  }
  if ( v24 )
    PiDqActionDataFree(v24);
  if ( P )
    ExFreePoolWithTag(P, 0x58706E50u);
  if ( v15[0] )
    MesHandleFree();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140903640  mov     rax, rsp
0x140903643  mov     [rax+18h], rbx
0x140903647  mov     [rax+8], rcx
0x14090364b  push    rsi
0x14090364c  push    rdi
0x14090364d  push    r12
0x14090364f  push    r14
0x140903651  push    r15
0x140903653  sub     rsp, 60h
0x140903657  mov     r14, rcx
0x14090365a  xor     edi, edi
0x14090365c  mov     esi, edi
0x14090365e  mov     [rax-58h], rdi
0x140903662  mov     [rax+10h], rdi
0x140903666  mov     [rax-2Ah], di
0x14090366a  mov     [rax-48h], rdx
0x14090366e  mov     [rax-40h], r8d
0x140903672  mov     dword ptr [rax-3Ch], 10h
0x140903679  mov     [rax-38h], rdi
0x14090367d  mov     [rax-30h], edi
0x140903680  and     r9b, 3
0x140903684  cmp     r9b, 3
0x140903688  setz    byte ptr [rax-2Ch]
0x14090368c  mov     [rax-2Bh], dil
0x140903690  call    PiDqQueryLock
0x140903695  mov     ebx, [r14+0D8h]
0x14090369c  mov     rcx, r14
0x14090369f  call    PiDqQueryUnlock
0x1409036a4  bt      ebx, 5
0x1409036a8  jb      short loc_1409036BF
0x1409036aa  mov     rcx, r14
0x1409036ad  call    PiDqQueryGetObjectManager
0x1409036b2  mov     rcx, rax; Resource
0x1409036b5  mov     rdx, r14
0x1409036b8  call    PiDqObjectManagerEnumerateAndRegisterQuery
0x1409036bd  mov     esi, eax
0x1409036bf  test    esi, esi
0x1409036c1  js      loc_140903888
0x1409036c7  lea     r9, [rsp+88h+var_58]
0x1409036cc  lea     r8, PiDqSerializationWrite
0x1409036d3  lea     rdx, PiDqSerializationAlloc
0x1409036da  lea     rcx, [rsp+88h+var_48]
0x1409036df  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x1409036e6  nop     dword ptr [rax+rax+00h]
0x1409036eb  mov     esi, eax
0x1409036ed  test    eax, eax
0x1409036ef  js      loc_1409038A6
0x1409036f5  mov     eax, [r14+0D8h]
0x1409036fc  and     eax, 2
0x1409036ff  mov     dword ptr [rsp+88h+var_60], eax
0x140903703  mov     [rsp+88h+var_68], rdi
0x140903708  xor     r9d, r9d
0x14090370b  xor     r8d, r8d
0x14090370e  lea     rdx, [rsp+88h+var_48]
0x140903713  mov     rcx, [rsp+88h+var_58]
0x140903718  call    cs:__imp_MesIncrementalHandleReset
0x14090371f  nop     dword ptr [rax+rax+00h]
0x140903724  mov     esi, eax
0x140903726  test    eax, eax
0x140903728  js      loc_1409038A6
0x14090372e  mov     ecx, [rsp+88h+var_3C]
0x140903732  mov     rax, [rsp+88h+arg_20]
0x14090373a  mov     [rax], ecx
0x14090373c  mov     rax, [rsp+88h+arg_28]
0x140903744  mov     [rax], edi
0x140903746  mov     rcx, r14
0x140903749  call    PiDqQueryLock
0x14090374e  lea     r12, [r14+0B8h]
0x140903755  mov     [rsp+88h+var_50], r12
0x14090375a  mov     rax, [r12]
0x14090375e  mov     [rsp+88h+arg_8], rax
0x140903766  mov     [r12], rdi
0x14090376a  mov     rcx, r14
0x14090376d  call    PiDqQueryUnlock
0x140903772  cmp     [rsp+88h+arg_8], rdi
0x14090377a  jz      loc_14090380F
0x140903780  lea     rax, [rsp+88h+arg_8]
0x140903788  mov     [rsp+88h+var_60], rax
0x14090378d  mov     dword ptr [rsp+88h+var_68], 1
0x140903795  lea     r9, off_140E0A510
0x14090379c  lea     r8, off_140004F50
0x1409037a3  lea     rdx, aTp3; "TP 3\a"
0x1409037aa  mov     rcx, [rsp+88h+var_58]
0x1409037af  call    cs:__imp_NdrMesTypeEncode3
0x1409037b6  nop     dword ptr [rax+rax+00h]
0x1409037bb  jmp     short loc_1409037CE
0x1409037bd  mov     esi, eax
0x1409037bf  xor     edi, edi
0x1409037c1  mov     r14, [rsp+88h+arg_0]
0x1409037c9  mov     r12, [rsp+88h+var_50]
0x1409037ce  test    esi, esi
0x1409037d0  js      loc_140903888
0x1409037d6  cmp     byte ptr [rsp+88h+var_2A], dil
0x1409037db  jnz     loc_14090393E
0x1409037e1  cmp     [rsp+88h+var_2B], dil
0x1409037e6  jnz     loc_140903904
0x1409037ec  mov     ecx, [rsp+88h+var_3C]
0x1409037f0  mov     rax, [rsp+88h+arg_20]
0x1409037f8  mov     [rax], ecx
0x1409037fa  mov     rcx, [rsp+88h+arg_8]; P
0x140903802  call    PiDqActionDataFree
0x140903807  mov     [rsp+88h+arg_8], rdi
0x14090380f  mov     rcx, r14
0x140903812  call    PiDqQueryLock
0x140903817  lea     rax, [r14+0C0h]
0x14090381e  mov     r15, [rax]
0x140903821  cmp     r15, rax
0x140903824  jz      short loc_14090389E
0x140903826  cmp     [r15+8], rax
0x14090382a  jnz     loc_1409038FD
0x140903830  mov     rcx, [r15]
0x140903833  cmp     [rcx+8], r15
0x140903837  jnz     loc_1409038FD
0x14090383d  mov     [rax], rcx
0x140903840  mov     [rcx+8], rax
0x140903844  dec     dword ptr [r14+0D0h]
0x14090384b  mov     rcx, r14
0x14090384e  call    PiDqQueryUnlock
0x140903853  lea     rdx, [r14+20h]
0x140903857  lea     r9, [rsp+88h+arg_8]
0x14090385f  mov     r8, r15
0x140903862  mov     rcx, [r14+18h]
0x140903866  call    PiDqActionDataCreate
0x14090386b  mov     ebx, eax
0x14090386d  mov     rcx, r15; P
0x140903870  call    PiDqQueryActionQueueEntryFree
0x140903875  mov     esi, edi
0x140903877  cmp     ebx, 0C0000034h
0x14090387d  cmovnz  esi, ebx
0x140903880  test    esi, esi
0x140903882  jns     loc_140903772
0x140903888  mov     rax, [rsp+88h+arg_20]
0x140903890  mov     [rax], edi
0x140903892  mov     rax, [rsp+88h+arg_28]
0x14090389a  mov     [rax], edi
0x14090389c  jmp     short loc_1409038AA
0x14090389e  mov     rcx, r14
0x1409038a1  call    PiDqQueryUnlock
0x1409038a6  test    esi, esi
0x1409038a8  js      short loc_140903888
0x1409038aa  mov     rcx, [rsp+88h+arg_8]; P
0x1409038b2  test    rcx, rcx
0x1409038b5  jnz     loc_140903948
0x1409038bb  mov     rcx, [rsp+88h+P]; P
0x1409038c0  test    rcx, rcx
0x1409038c3  jz      short loc_1409038CF
0x1409038c5  mov     edx, 58706E50h; Tag
0x1409038ca  call    ExFreePoolWithTag
0x1409038cf  mov     rcx, [rsp+88h+var_58]
0x1409038d4  test    rcx, rcx
0x1409038d7  jz      short loc_1409038E5
0x1409038d9  call    cs:__imp_MesHandleFree
0x1409038e0  nop     dword ptr [rax+rax+00h]
0x1409038e5  mov     eax, esi
0x1409038e7  mov     rbx, [rsp+88h+arg_10]
0x1409038ef  add     rsp, 60h
0x1409038f3  pop     r15
0x1409038f5  pop     r14
0x1409038f7  pop     r12
0x1409038f9  pop     rdi
0x1409038fa  pop     rsi
0x1409038fb  retn
0x1409038fd  mov     ecx, 3
0x140903902  int     29h; Win8: RtlFailFast(ecx)
0x140903904  mov     rcx, r14
0x140903907  call    PiDqQueryLock
0x14090390c  mov     rax, [rsp+88h+arg_8]
0x140903914  mov     [r12], rax
0x140903918  mov     [rsp+88h+arg_8], rdi
0x140903920  mov     rcx, r14
0x140903923  call    PiDqQueryUnlock
0x140903928  mov     ecx, [rsp+88h+var_30]
0x14090392c  add     ecx, 10h
0x14090392f  mov     rax, [rsp+88h+arg_28]
0x140903937  mov     [rax], ecx
0x140903939  jmp     loc_1409038A6
0x14090393e  mov     esi, 0C0000005h
0x140903943  jmp     loc_140903888
0x140903948  call    PiDqActionDataFree
0x14090394d  jmp     loc_1409038BB
```
