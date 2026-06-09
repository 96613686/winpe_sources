# FatOpenTargetDirectory

- ea: `0x14002c080`
- end: `0x14002c22e`
- name: `FatOpenTargetDirectory`
- size: `430`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400268c0`

## callees

- `0x14000c380`
- `0x14002c080`
- `0x14003db44`
- `0x1400465f4`
- `0x1400475e8`
- `0x14004814c`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x14005ca15`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005ca15`
- `ntoskrnl!IoCheckShareAccess` at `0x14002c0ef`
- `ntoskrnl!IoCheckShareAccess` at `0x14002c0ef`
- `ntoskrnl!IoSetShareAccess` at `0x14002c107`
- `ntoskrnl!IoSetShareAccess` at `0x14002c107`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c208`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ca2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c208`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ca2a`

## pseudocode

```c
__int64 __fastcall FatOpenTargetDirectory(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK *a5,
        unsigned __int16 a6,
        char a7,
        char a8)
{
  struct _SHARE_ACCESS *v11; // r9
  ACCESS_MASK v12; // ecx
  NTSTATUS v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // edx
  _WORD *v18; // r9
  unsigned int v19; // ecx
  __int64 Ccb; // [rsp+38h] [rbp-20h]

  *(_OWORD *)a1 = 0;
  FatAcquireExclusiveFcb(a2, a4);
  v11 = (struct _SHARE_ACCESS *)(a4 + 200);
  v12 = *a5;
  if ( *(_DWORD *)(a4 + 232) )
  {
    v13 = IoCheckShareAccess(v12, a6, (PFILE_OBJECT)a3, v11, 1u);
    *(_DWORD *)a1 = v13;
    if ( v13 < 0 )
      goto LABEL_18;
  }
  else
  {
    IoSetShareAccess(v12, a6, (PFILE_OBJECT)a3, v11);
  }
  Ccb = FatCreateCcb(v15, v14);
  FatSetFileObject(a3, v16, a4, Ccb);
  ++*(_DWORD *)(a4 + 228);
  ++*(_DWORD *)(a4 + 232);
  ++*(_DWORD *)(*(_QWORD *)(a4 + 184) + 272LL);
  if ( !*(_WORD *)(a3 + 75) )
    ++*(_DWORD *)(*(_QWORD *)(a4 + 184) + 276LL);
  v17 = (*(unsigned __int16 *)(a3 + 88) >> 1) - 1;
  v18 = *(_WORD **)(a3 + 96);
  if ( v18[v17] == 92 )
  {
    *(_WORD *)(a3 + 88) -= 2;
    v19 = v17 - 1;
    LOWORD(v17) = v17 - 1;
  }
  else
  {
    v19 = (*(unsigned __int16 *)(a3 + 88) >> 1) - 1;
  }
  while ( v18[v19] != 92 )
  {
    if ( !v19 )
      goto LABEL_13;
    LOWORD(v17) = --v19;
  }
  LOWORD(v17) = ++v19;
LABEL_13:
  if ( v19 )
  {
    *(_WORD *)(a3 + 88) += -2 * v17;
    memmove(v18, &v18[v19], *(unsigned __int16 *)(a3 + 88));
  }
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 5LL - (a7 != 0);
  if ( a7 && a8 )
    *(_DWORD *)(*(_QWORD *)(a3 + 32) + 4LL) |= 0x800u;
LABEL_18:
  ExReleaseResourceLite(*(PERESOURCE *)(a4 + 8));
  return a1;
}

```

## disassembly

```asm
0x14002c080  mov     [rsp+arg_18], r9
0x14002c085  mov     [rsp+arg_10], r8
0x14002c08a  push    rbx
0x14002c08b  push    rsi
0x14002c08c  push    rdi
0x14002c08d  sub     rsp, 40h
0x14002c091  mov     rbx, r9
0x14002c094  mov     rdi, r8
0x14002c097  mov     rax, rdx
0x14002c09a  mov     rsi, rcx
0x14002c09d  xorps   xmm0, xmm0
0x14002c0a0  movups  xmmword ptr [rcx], xmm0
0x14002c0a3  mov     [rsp+58h+var_28], 0
0x14002c0a8  mov     [rsp+58h+var_20], 0
0x14002c0b1  mov     rdx, r9
0x14002c0b4  mov     rcx, rax
0x14002c0b7  call    FatAcquireExclusiveFcb
0x14002c0bc  nop
0x14002c0bd  mov     [rsp+58h+var_24], 0
0x14002c0c5  lea     r9, [rbx+0C8h]; ShareAccess
0x14002c0cc  movzx   edx, [rsp+58h+arg_28]; DesiredShareAccess
0x14002c0d4  mov     rax, [rsp+58h+arg_20]
0x14002c0dc  mov     ecx, [rax]; DesiredAccess
0x14002c0de  mov     r8, rdi; FileObject
0x14002c0e1  cmp     dword ptr [rbx+0E8h], 0
0x14002c0e8  jbe     short loc_14002C107
0x14002c0ea  mov     [rsp+58h+Update], 1; Update
0x14002c0ef  call    cs:__imp_IoCheckShareAccess
0x14002c0f6  nop     dword ptr [rax+rax+00h]
0x14002c0fb  mov     [rsi], eax
0x14002c0fd  test    eax, eax
0x14002c0ff  js      loc_14002C204
0x14002c105  jmp     short loc_14002C113
0x14002c107  call    cs:__imp_IoSetShareAccess
0x14002c10e  nop     dword ptr [rax+rax+00h]
0x14002c113  mov     [rsp+58h+var_28], 1
0x14002c118  call    FatCreateCcb
0x14002c11d  mov     [rsp+58h+var_20], rax
0x14002c122  mov     r9, rax
0x14002c125  mov     r8, rbx
0x14002c128  mov     rcx, rdi
0x14002c12b  call    FatSetFileObject
0x14002c130  inc     dword ptr [rbx+0E4h]
0x14002c136  inc     dword ptr [rbx+0E8h]
0x14002c13c  mov     rax, [rbx+0B8h]
0x14002c143  inc     dword ptr [rax+110h]
0x14002c149  mov     al, [rdi+4Ch]
0x14002c14c  or      al, [rdi+4Bh]
0x14002c14f  jnz     short loc_14002C15E
0x14002c151  mov     rax, [rbx+0B8h]
0x14002c158  inc     dword ptr [rax+114h]
0x14002c15e  movzx   ecx, word ptr [rdi+58h]
0x14002c162  mov     eax, ecx
0x14002c164  shr     eax, 1
0x14002c166  dec     eax
0x14002c168  mov     edx, eax
0x14002c16a  mov     [rsp+58h+var_24], edx
0x14002c16e  mov     r9, [rdi+60h]
0x14002c172  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14002c178  jnz     short loc_14002C18D
0x14002c17a  sub     cx, 2
0x14002c17e  mov     [rdi+58h], cx
0x14002c182  lea     ecx, [rax-1]
0x14002c185  mov     edx, ecx
0x14002c187  mov     [rsp+58h+var_24], ecx
0x14002c18b  jmp     short loc_14002C18F
0x14002c18d  mov     ecx, edx
0x14002c18f  mov     eax, ecx
0x14002c191  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14002c197  jnz     short loc_14002C1A3
0x14002c199  inc     ecx
0x14002c19b  mov     edx, ecx
0x14002c19d  mov     [rsp+58h+var_24], ecx
0x14002c1a1  jmp     short loc_14002C1A7
0x14002c1a3  test    ecx, ecx
0x14002c1a5  jnz     short loc_14002C220
0x14002c1a7  test    ecx, ecx
0x14002c1a9  jz      short loc_14002C1CD
0x14002c1ab  mov     eax, 0FFFEh
0x14002c1b0  movzx   edx, dx
0x14002c1b3  imul    edx, eax
0x14002c1b6  add     [rdi+58h], dx
0x14002c1ba  movzx   r8d, word ptr [rdi+58h]; Size
0x14002c1bf  mov     eax, ecx
0x14002c1c1  lea     rdx, [r9+rax*2]; Src
0x14002c1c5  mov     rcx, r9; void *
0x14002c1c8  call    memmove
0x14002c1cd  mov     dword ptr [rsi], 0
0x14002c1d3  mov     al, [rsp+58h+arg_30]
0x14002c1da  neg     al
0x14002c1dc  sbb     rcx, rcx
0x14002c1df  add     rcx, 5
0x14002c1e3  mov     [rsi+8], rcx
0x14002c1e7  cmp     [rsp+58h+arg_30], 0
0x14002c1ef  jz      short loc_14002C204
0x14002c1f1  cmp     [rsp+58h+arg_38], 0
0x14002c1f9  jz      short loc_14002C204
0x14002c1fb  mov     rax, [rdi+20h]
0x14002c1ff  bts     dword ptr [rax+4], 0Bh
0x14002c204  mov     rcx, [rbx+8]; Resource
0x14002c208  call    cs:__imp_ExReleaseResourceLite
0x14002c20f  nop     dword ptr [rax+rax+00h]
0x14002c214  mov     rax, rsi
0x14002c217  add     rsp, 40h
0x14002c21b  pop     rdi
0x14002c21c  pop     rsi
0x14002c21d  pop     rbx
0x14002c21e  retn
0x14002c220  dec     ecx
0x14002c222  mov     edx, ecx
0x14002c224  mov     [rsp+58h+var_24], ecx
0x14002c228  jmp     loc_14002C18F
0x14005c9df  push    rbp
0x14005c9e1  sub     rsp, 30h
0x14005c9e5  mov     rbp, rdx
0x14005c9e8  movzx   eax, cl
0x14005c9eb  test    cl, cl
0x14005c9ed  jz      short loc_14005CA22
0x14005c9ef  cmp     qword ptr [rbp+38h], 0
0x14005c9f4  jz      short loc_14005CA00
0x14005c9f6  lea     rdx, [rbp+38h]
0x14005c9fa  call    FatDeleteCcb
0x14005c9ff  nop
0x14005ca00  cmp     byte ptr [rbp+30h], 0
0x14005ca04  jz      short loc_14005CA22
0x14005ca06  mov     rdx, [rbp+78h]
0x14005ca0a  add     rdx, 0C8h; ShareAccess
0x14005ca11  mov     rcx, [rbp+70h]; FileObject
0x14005ca15  call    cs:__imp_IoRemoveShareAccess
0x14005ca1c  nop     dword ptr [rax+rax+00h]
0x14005ca21  nop
0x14005ca22  mov     rcx, [rbp+78h]
0x14005ca26  mov     rcx, [rcx+8]; Resource
0x14005ca2a  call    cs:__imp_ExReleaseResourceLite
0x14005ca31  nop     dword ptr [rax+rax+00h]
0x14005ca36  nop
0x14005ca37  add     rsp, 30h
0x14005ca3b  pop     rbp
0x14005ca3c  retn
```
