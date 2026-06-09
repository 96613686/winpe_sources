# BfsExpandDirectory

- ea: `0x1400115f0`
- end: `0x140011832`
- name: `BfsExpandDirectory`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140011ea8`

## callees

- `0x140001008`
- `0x140010754`
- `0x1400115f0`
- `0x14001193c`
- `0x140012c40`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001164a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001164a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400117f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400117f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117db`
- `ntoskrnl!ExAllocatePool2` at `0x14001167d`
- `ntoskrnl!ExAllocatePool2` at `0x1400116c1`
- `ntoskrnl!ExAllocatePool2` at `0x14001167d`
- `ntoskrnl!ExAllocatePool2` at `0x1400116c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011639`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011639`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011803`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011803`

## pseudocode

```c
__int64 __fastcall BfsExpandDirectory(__int64 a1, _DWORD *a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  _DWORD *v5; // rdi
  __int64 v8; // rbx
  NTSTATUS v9; // ebx
  __int64 Pool2; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // r15d
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  bool v16; // cc
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rcx
  NTSTATUS v20; // eax
  __int64 v21; // rdx
  void *v22; // r8
  int v24; // [rsp+20h] [rbp-51h]
  int v25; // [rsp+30h] [rbp-41h] BYREF
  _DWORD *v26; // [rsp+38h] [rbp-39h]
  __int64 v27; // [rsp+40h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+48h] [rbp-29h] BYREF
  int *v29; // [rsp+68h] [rbp-9h]
  __int64 v30; // [rsp+70h] [rbp-1h]

  v5 = 0;
  *a4 = 0;
  v27 = a3;
  v26 = a2;
  *a5 = 0;
  v8 = *(_QWORD *)(a1 + 8);
  v25 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v8, 0);
  v9 = BfsAllocateBlock(*(_QWORD *)(a1 + 8), &v25);
  if ( v9 < 0 )
    goto LABEL_23;
  Pool2 = ExAllocatePool2(256, 32, 1282631234);
  v13 = v25;
  v14 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v15 = (unsigned int)dword_140019000;
    v16 = (unsigned int)dword_140019000 <= 3;
    goto LABEL_4;
  }
  v17 = ExAllocatePool2(256, 0x4000, 1651729986);
  v5 = (_DWORD *)v17;
  if ( !v17 )
  {
    v16 = (unsigned int)dword_140019000 <= 3;
LABEL_4:
    v9 = -1073741801;
    if ( !v16 )
    {
      v25 = -1073741801;
LABEL_17:
      v30 = 4;
      v29 = &v25;
      tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v11, v12, v24, &v28);
      goto LABEL_18;
    }
    goto LABEL_18;
  }
  v14[2] = v17;
  *((_DWORD *)v14 + 6) = v13;
  v18 = *(_QWORD *)(a1 + 16);
  v19 = *(_QWORD **)(v18 + 8);
  if ( *v19 != v18 )
    __fastfail(3u);
  v14[1] = v19;
  *v14 = v18;
  *v19 = v14;
  *(_QWORD *)(v18 + 8) = v14;
  memset(v5 + 1, 0, 0x3FFCu);
  *v5 = 1148413506;
  v20 = BfsWriteBlock(*(_QWORD *)(a1 + 8), v13, v5);
  v9 = v20;
  if ( v20 >= 0 )
  {
    v9 = BfsWriteBlock(*(_QWORD *)(a1 + 8), 0, *(void **)(*(_QWORD *)(a1 + 8) + 16LL));
    if ( v9 >= 0 )
    {
      v21 = v27;
      v22 = v26;
      v26[1] = v13;
      v9 = BfsWriteBlock(*(_QWORD *)(a1 + 8), *(_DWORD *)(v21 + 24), v22);
      if ( v9 >= 0 )
      {
        *a5 = v14;
        *a4 = v5;
        goto LABEL_23;
      }
    }
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_18;
    v25 = v9;
    goto LABEL_17;
  }
  v15 = (unsigned int)dword_140019000;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v25 = v20;
    goto LABEL_17;
  }
LABEL_18:
  BfsFreeBlock(*(_QWORD *)(a1 + 8), v13);
  if ( v14 )
    ExFreePoolWithTag(v14, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
LABEL_23:
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a1 + 8), 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400115f0  push    rbp
0x1400115f2  push    rbx
0x1400115f3  push    rsi
0x1400115f4  push    rdi
0x1400115f5  push    r12
0x1400115f7  push    r13
0x1400115f9  push    r14
0x1400115fb  push    r15
0x1400115fd  lea     rbp, [rsp-17h]
0x140011602  sub     rsp, 88h
0x140011609  mov     rax, cs:__security_cookie
0x140011610  xor     rax, rsp
0x140011613  mov     [rbp+4Fh+var_48], rax
0x140011617  mov     r13, [rbp+4Fh+arg_20]
0x14001161b  xor     edi, edi
0x14001161d  mov     [r9], rdi
0x140011620  mov     r12, r9
0x140011623  mov     [rbp+4Fh+var_80], r8
0x140011627  mov     r14, rcx
0x14001162a  mov     [rbp+4Fh+var_88], rdx
0x14001162e  mov     [r13+0], rdi
0x140011632  mov     rbx, [rcx+8]
0x140011636  mov     [rbp+4Fh+var_90], edi
0x140011639  call    cs:__imp_KeEnterCriticalRegion
0x140011640  nop     dword ptr [rax+rax+00h]
0x140011645  xor     edx, edx
0x140011647  mov     rcx, rbx
0x14001164a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140011651  nop     dword ptr [rax+rax+00h]
0x140011656  mov     rcx, [r14+8]
0x14001165a  lea     rdx, [rbp+4Fh+var_90]
0x14001165e  call    BfsAllocateBlock
0x140011663  mov     ebx, eax
0x140011665  test    eax, eax
0x140011667  js      loc_1400117F1
0x14001166d  mov     ebx, 100h
0x140011672  lea     edx, [rdi+20h]
0x140011675  mov     ecx, ebx
0x140011677  mov     r8d, 4C736642h
0x14001167d  call    cs:__imp_ExAllocatePool2
0x140011684  nop     dword ptr [rax+rax+00h]
0x140011689  mov     r15d, [rbp+4Fh+var_90]
0x14001168d  mov     rsi, rax
0x140011690  test    rax, rax
0x140011693  jnz     short loc_1400116B3
0x140011695  mov     ecx, cs:dword_140019000
0x14001169b  cmp     ecx, 3
0x14001169e  mov     edx, 0C0000017h
0x1400116a3  mov     ebx, edx
0x1400116a5  jbe     loc_1400117AF
0x1400116ab  mov     [rbp+4Fh+var_90], edx
0x1400116ae  jmp     loc_14001178A
0x1400116b3  mov     edx, 4000h
0x1400116b8  mov     r8d, 62736642h
0x1400116be  mov     rcx, rbx
0x1400116c1  call    cs:__imp_ExAllocatePool2
0x1400116c8  nop     dword ptr [rax+rax+00h]
0x1400116cd  mov     rdi, rax
0x1400116d0  test    rax, rax
0x1400116d3  jnz     short loc_1400116E0
0x1400116d5  mov     eax, cs:dword_140019000
0x1400116db  cmp     eax, 3
0x1400116de  jmp     short loc_14001169E
0x1400116e0  mov     [rsi+10h], rdi
0x1400116e4  mov     [rsi+18h], r15d
0x1400116e8  mov     rax, [r14+10h]
0x1400116ec  mov     rcx, [rax+8]
0x1400116f0  cmp     [rcx], rax
0x1400116f3  jz      short loc_1400116FC
0x1400116f5  mov     ecx, 3
0x1400116fa  int     29h; Win8: RtlFailFast(ecx)
0x1400116fc  mov     [rsi+8], rcx
0x140011700  xor     edx, edx; Val
0x140011702  mov     [rsi], rax
0x140011705  mov     r8d, 3FFCh; Size
0x14001170b  mov     [rcx], rsi
0x14001170e  lea     rcx, [rdi+4]; void *
0x140011712  mov     [rax+8], rsi
0x140011716  call    memset
0x14001171b  mov     dword ptr [rdi], 44736642h
0x140011721  mov     r8, rdi
0x140011724  mov     rcx, [r14+8]
0x140011728  mov     edx, r15d
0x14001172b  call    BfsWriteBlock
0x140011730  mov     ebx, eax
0x140011732  test    eax, eax
0x140011734  jns     short loc_140011746
0x140011736  mov     ecx, cs:dword_140019000
0x14001173c  cmp     ecx, 3
0x14001173f  jbe     short loc_1400117AF
0x140011741  mov     [rbp+4Fh+var_90], eax
0x140011744  jmp     short loc_14001178A
0x140011746  mov     rcx, [r14+8]
0x14001174a  xor     edx, edx
0x14001174c  mov     r8, [rcx+10h]
0x140011750  call    BfsWriteBlock
0x140011755  mov     ebx, eax
0x140011757  test    eax, eax
0x140011759  js      short loc_14001177C
0x14001175b  mov     rax, [rbp+4Fh+var_88]
0x14001175f  mov     rdx, [rbp+4Fh+var_80]
0x140011763  mov     r8, rax
0x140011766  mov     [rax+4], r15d
0x14001176a  mov     edx, [rdx+18h]
0x14001176d  mov     rcx, [r14+8]
0x140011771  call    BfsWriteBlock
0x140011776  mov     ebx, eax
0x140011778  test    eax, eax
0x14001177a  jns     short loc_1400117E9
0x14001177c  mov     eax, cs:dword_140019000
0x140011782  cmp     eax, 3
0x140011785  jbe     short loc_1400117AF
0x140011787  mov     [rbp+4Fh+var_90], ebx
0x14001178a  lea     rax, [rbp+4Fh+var_90]
0x14001178e  mov     [rbp+4Fh+var_50], 4
0x140011796  mov     [rbp+4Fh+var_58], rax
0x14001179a  lea     rdx, byte_140016D91; int
0x1400117a1  lea     rax, [rbp+4Fh+var_78]
0x1400117a5  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x1400117aa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400117af  mov     rcx, [r14+8]
0x1400117b3  mov     edx, r15d
0x1400117b6  call    BfsFreeBlock
0x1400117bb  test    rsi, rsi
0x1400117be  jz      short loc_1400117D1
0x1400117c0  xor     edx, edx; Tag
0x1400117c2  mov     rcx, rsi; P
0x1400117c5  call    cs:__imp_ExFreePoolWithTag
0x1400117cc  nop     dword ptr [rax+rax+00h]
0x1400117d1  test    rdi, rdi
0x1400117d4  jz      short loc_1400117F1
0x1400117d6  xor     edx, edx; Tag
0x1400117d8  mov     rcx, rdi; P
0x1400117db  call    cs:__imp_ExFreePoolWithTag
0x1400117e2  nop     dword ptr [rax+rax+00h]
0x1400117e7  jmp     short loc_1400117F1
0x1400117e9  mov     [r13+0], rsi
0x1400117ed  mov     [r12], rdi
0x1400117f1  mov     rcx, [r14+8]
0x1400117f5  xor     edx, edx
0x1400117f7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400117fe  nop     dword ptr [rax+rax+00h]
0x140011803  call    cs:__imp_KeLeaveCriticalRegion
0x14001180a  nop     dword ptr [rax+rax+00h]
0x14001180f  mov     eax, ebx
0x140011811  mov     rcx, [rbp+4Fh+var_48]
0x140011815  xor     rcx, rsp; StackCookie
0x140011818  call    __security_check_cookie
0x14001181d  add     rsp, 88h
0x140011824  pop     r15
0x140011826  pop     r14
0x140011828  pop     r13
0x14001182a  pop     r12
0x14001182c  pop     rdi
0x14001182d  pop     rsi
0x14001182e  pop     rbx
0x14001182f  pop     rbp
0x140011830  retn
```
