# CFormatRunPtr::MergeRuns(long,IFormatCache *)

- ea: `0x18001a650`
- end: `0x18001a9c4`
- name: `?MergeRuns@CFormatRunPtr@@AEAAXJPEAUIFormatCache@@@Z`
- size: `884`
- prototype: `void __fastcall(CFormatRunPtr *__hidden this, int, struct IFormatCache *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005480`
- `0x18001d24c`
- `0x18004cbb0`
- `0x18005fabc`

## callees

- `0x18001a650`
- `0x18001a9d0`
- `0x18001aa80`
- `0x18001ab30`
- `0x180092010`

## pseudocode

```c
void __fastcall CFormatRunPtr::MergeRuns(CFormatRunPtr *this, int a2, struct IFormatCache *a3)
{
  int v3; // r10d
  __int64 *v4; // rax
  int v5; // ebx
  signed int v7; // r14d
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  _DWORD *v12; // r9
  __int64 v13; // r10
  int v14; // ecx
  int v15; // edx
  int v16; // r11d
  int v17; // r8d
  int v18; // ecx
  int *v19; // rdx
  int v20; // edx
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // edx
  int v26; // eax
  __int64 v27; // rcx
  __int64 *v28; // rdx
  int v29; // ecx
  int v30; // eax
  int v31; // esi
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // edx
  int v36; // eax
  _DWORD *v37; // rcx

  v3 = *((_DWORD *)this + 2);
  v4 = *(__int64 **)this;
  v5 = v3 - a2;
  v7 = (((a2 - v3) >> 31) & 0xFFFFFFFE) + 1;
  if ( a2 - v3 >= 0 )
    v5 = a2 - v3;
  if ( !v4 || !*((_DWORD *)v4 + 2) )
    CRunPtrBase::SetRun(this, v7 + v3, 0);
  if ( v5 )
  {
    while ( 1 )
    {
      v9 = *(_QWORD *)this;
      v10 = *((_DWORD *)this + 2);
      v11 = *(_DWORD *)(*(_QWORD *)this + 8LL);
      if ( v11 > 0 && v10 < v11 && *(_QWORD *)v9 && v10 >= 0 )
        v12 = (_DWORD *)(*(_QWORD *)v9 + *(_DWORD *)(v9 + 16) * v10);
      else
        v12 = 0;
      if ( !*v12 && !v10 && v11 - 1 > 0 )
      {
        if ( v7 > 0 )
          CRunPtrBase::PrevRun(this);
        v24 = *(_QWORD *)this;
        v25 = *(_DWORD *)(*(_QWORD *)this + 8LL);
        if ( v25 > 0 && (v26 = *((_DWORD *)this + 2), v26 < v25) && *(_QWORD *)v24 && v26 >= 0 )
          v27 = *(_QWORD *)v24 + *(_DWORD *)(v24 + 16) * v26;
        else
          v27 = 0;
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)a3 + 8LL))(
          a3,
          (unsigned int)*(__int16 *)(v27 + 4));
        CArrayBase::Remove(*(CArrayBase **)this, *((_DWORD *)this + 2), 1);
        goto LABEL_37;
      }
      if ( v11 > 0 && v10 < v11 && *(_QWORD *)v9 && v10 >= 0 )
        v13 = *(_QWORD *)v9 + *(_DWORD *)(v9 + 16) * v10;
      else
        v13 = 0;
      if ( !v9 || !v11 )
        return;
      v14 = v7 + v10;
      if ( v7 + v10 >= v11 )
      {
        v15 = 0;
        v14 = v11 - 1;
      }
      else
      {
        v15 = 1;
      }
      v16 = 0;
      *((_DWORD *)this + 3) = 0;
      if ( v14 >= 0 )
        v16 = v15;
      v17 = 0;
      if ( v14 >= 0 )
        v17 = v14;
      *((_DWORD *)this + 2) = v17;
      v18 = *(_DWORD *)(v9 + 8);
      if ( v18 > 0 && v17 < v18 && *(_QWORD *)v9 )
        v19 = (int *)(*(_QWORD *)v9 + *(_DWORD *)(v9 + 16) * v17);
      else
        v19 = 0;
      v20 = *v19;
      v21 = 0;
      if ( v20 <= 0 )
        v21 = v20;
      *((_DWORD *)this + 3) = v21;
      if ( !v16 )
        return;
      v22 = *(_DWORD *)(v9 + 8);
      if ( v22 > 0 && v17 < v22 && *(_QWORD *)v9 )
        v23 = *(_QWORD *)v9 + *(_DWORD *)(v9 + 16) * v17;
      else
        v23 = 0;
      if ( *(_WORD *)(v13 + 4) == *(_WORD *)(v23 + 4)
        && *(_BYTE *)(v13 + 6) == *(_BYTE *)(v23 + 6)
        && ((*(_BYTE *)(v13 + 7) ^ *(_BYTE *)(v23 + 7)) & 1) == 0 )
      {
        break;
      }
LABEL_37:
      if ( !--v5 )
        return;
    }
    if ( v7 > 0 )
      CRunPtrBase::PrevRun(this);
    v28 = *(__int64 **)this;
    v29 = *((_DWORD *)this + 2);
    v30 = *(_DWORD *)(*(_QWORD *)this + 8LL);
    if ( v30 > 0 && v29 < v30 && *v28 && v29 >= 0 )
    {
      v31 = *(_DWORD *)(*((_DWORD *)v28 + 4) * v29 + *v28);
      v32 = *v28;
    }
    else
    {
      v31 = MEMORY[0];
      if ( v30 <= 0 || v29 >= v30 || (v32 = *v28) == 0 || v29 < 0 )
      {
        v33 = 0;
LABEL_60:
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)a3 + 8LL))(
          a3,
          (unsigned int)*(__int16 *)(v33 + 4));
        CArrayBase::Remove(*(CArrayBase **)this, *((_DWORD *)this + 2), 1);
        v34 = *(_QWORD *)this;
        v35 = *(_DWORD *)(*(_QWORD *)this + 8LL);
        if ( v35 > 0 && (v36 = *((_DWORD *)this + 2), v36 < v35) && *(_QWORD *)v34 && v36 >= 0 )
          v37 = (_DWORD *)(*(_QWORD *)v34 + *(_DWORD *)(v34 + 16) * v36);
        else
          v37 = 0;
        *v37 += v31;
        goto LABEL_37;
      }
    }
    v33 = v32 + *((_DWORD *)v28 + 4) * v29;
    goto LABEL_60;
  }
}

```

## disassembly

```asm
0x18001a650  push    rbx
0x18001a652  push    rdi
0x18001a653  push    r14
0x18001a655  push    r15
0x18001a657  sub     rsp, 28h
0x18001a65b  mov     r10d, [rcx+8]
0x18001a65f  mov     r9d, edx
0x18001a662  mov     rax, [rcx]
0x18001a665  sub     r9d, r10d
0x18001a668  mov     r14d, r9d
0x18001a66b  mov     ebx, r10d
0x18001a66e  sar     r14d, 1Fh
0x18001a672  sub     ebx, edx
0x18001a674  and     r14d, 0FFFFFFFEh
0x18001a678  mov     r15, r8
0x18001a67b  inc     r14d
0x18001a67e  mov     rdi, rcx
0x18001a681  test    r9d, r9d
0x18001a684  cmovns  ebx, r9d
0x18001a688  test    rax, rax
0x18001a68b  jz      loc_18001A804
0x18001a691  cmp     dword ptr [rax+8], 0
0x18001a695  jz      loc_18001A804
0x18001a69b  test    ebx, ebx
0x18001a69d  jz      loc_18001A7F9
0x18001a6a3  mov     [rsp+48h+arg_0], rsi
0x18001a6a8  mov     rax, [rdi]
0x18001a6ab  mov     edx, [rdi+8]
0x18001a6ae  mov     r8d, [rax+8]
0x18001a6b2  test    r8d, r8d
0x18001a6b5  jle     loc_18001A950
0x18001a6bb  cmp     edx, r8d
0x18001a6be  jge     loc_18001A950
0x18001a6c4  mov     r10, [rax]
0x18001a6c7  test    r10, r10
0x18001a6ca  jz      loc_18001A950
0x18001a6d0  test    edx, edx
0x18001a6d2  js      loc_18001A950
0x18001a6d8  mov     ecx, edx
0x18001a6da  imul    ecx, [rax+10h]
0x18001a6de  movsxd  r9, ecx
0x18001a6e1  add     r9, r10
0x18001a6e4  cmp     dword ptr [r9], 0
0x18001a6e8  jz      loc_18001A815
0x18001a6ee  test    r8d, r8d
0x18001a6f1  jle     loc_18001A958
0x18001a6f7  cmp     edx, r8d
0x18001a6fa  jge     loc_18001A958
0x18001a700  mov     r9, [rax]
0x18001a703  test    r9, r9
0x18001a706  jz      loc_18001A958
0x18001a70c  test    edx, edx
0x18001a70e  js      loc_18001A958
0x18001a714  mov     ecx, edx
0x18001a716  imul    ecx, [rax+10h]
0x18001a71a  movsxd  r10, ecx
0x18001a71d  add     r10, r9
0x18001a720  test    rax, rax
0x18001a723  jz      loc_18001A7F4
0x18001a729  test    r8d, r8d
0x18001a72c  jz      loc_18001A7F4
0x18001a732  lea     ecx, [r14+rdx]
0x18001a736  cmp     ecx, r8d
0x18001a739  jge     loc_18001A9AC
0x18001a73f  mov     edx, 1
0x18001a744  xor     r11d, r11d
0x18001a747  mov     dword ptr [rdi+0Ch], 0
0x18001a74e  test    ecx, ecx
0x18001a750  cmovns  r11d, edx
0x18001a754  xor     r8d, r8d
0x18001a757  test    ecx, ecx
0x18001a759  cmovns  r8d, ecx
0x18001a75d  mov     [rdi+8], r8d
0x18001a761  mov     ecx, [rax+8]
0x18001a764  test    ecx, ecx
0x18001a766  jle     loc_18001A960
0x18001a76c  cmp     r8d, ecx
0x18001a76f  jge     loc_18001A960
0x18001a775  mov     r9, [rax]
0x18001a778  test    r9, r9
0x18001a77b  jz      loc_18001A960
0x18001a781  test    r8d, r8d
0x18001a784  js      loc_18001A960
0x18001a78a  mov     ecx, r8d
0x18001a78d  imul    ecx, [rax+10h]
0x18001a791  movsxd  rdx, ecx
0x18001a794  add     rdx, r9
0x18001a797  mov     edx, [rdx]
0x18001a799  xor     ecx, ecx
0x18001a79b  test    edx, edx
0x18001a79d  cmovle  ecx, edx
0x18001a7a0  mov     [rdi+0Ch], ecx
0x18001a7a3  test    r11d, r11d
0x18001a7a6  jz      short loc_18001A7F4
0x18001a7a8  mov     ecx, [rax+8]
0x18001a7ab  test    ecx, ecx
0x18001a7ad  jle     loc_18001A967
0x18001a7b3  cmp     r8d, ecx
0x18001a7b6  jge     loc_18001A967
0x18001a7bc  mov     rdx, [rax]
0x18001a7bf  test    rdx, rdx
0x18001a7c2  jz      loc_18001A967
0x18001a7c8  test    r8d, r8d
0x18001a7cb  js      loc_18001A967
0x18001a7d1  imul    r8d, [rax+10h]
0x18001a7d6  movsxd  rcx, r8d
0x18001a7d9  add     rcx, rdx; this
0x18001a7dc  movzx   eax, word ptr [rcx+4]
0x18001a7e0  cmp     [r10+4], ax
0x18001a7e5  jz      loc_18001A892
0x18001a7eb  sub     ebx, 1
0x18001a7ee  jnz     loc_18001A6A8
0x18001a7f4  mov     rsi, [rsp+48h+arg_0]
0x18001a7f9  add     rsp, 28h
0x18001a7fd  pop     r15
0x18001a7ff  pop     r14
0x18001a801  pop     rdi
0x18001a802  pop     rbx
0x18001a803  retn
0x18001a804  lea     edx, [r14+r10]; int
0x18001a808  xor     r8d, r8d; int
0x18001a80b  call    ?SetRun@CRunPtrBase@@QEAAHJJ@Z; CRunPtrBase::SetRun(long,long)
0x18001a810  jmp     loc_18001A69B
0x18001a815  test    edx, edx
0x18001a817  jnz     loc_18001A6EE
0x18001a81d  lea     ecx, [r8-1]
0x18001a821  test    ecx, ecx
0x18001a823  jle     loc_18001A6EE
0x18001a829  test    r14d, r14d
0x18001a82c  jg      loc_18001A99F
0x18001a832  mov     rcx, [rdi]
0x18001a835  mov     edx, [rcx+8]
0x18001a838  test    edx, edx
0x18001a83a  jle     loc_18001A994
0x18001a840  mov     eax, [rdi+8]
0x18001a843  cmp     eax, edx
0x18001a845  jge     loc_18001A994
0x18001a84b  mov     rdx, [rcx]
0x18001a84e  test    rdx, rdx
0x18001a851  jz      loc_18001A994
0x18001a857  test    eax, eax
0x18001a859  js      loc_18001A994
0x18001a85f  imul    eax, [rcx+10h]
0x18001a863  movsxd  rcx, eax
0x18001a866  add     rcx, rdx
0x18001a869  mov     rax, [r15]
0x18001a86c  movsx   edx, word ptr [rcx+4]
0x18001a870  mov     rcx, r15
0x18001a873  mov     rax, [rax+8]
0x18001a877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a87c  mov     edx, [rdi+8]; int
0x18001a87f  mov     r8d, 1; int
0x18001a885  mov     rcx, [rdi]; this
0x18001a888  call    ?Remove@CArrayBase@@QEAAXJJ@Z; CArrayBase::Remove(long,long)
0x18001a88d  jmp     loc_18001A7EB
0x18001a892  movzx   eax, byte ptr [rcx+6]
0x18001a896  cmp     [r10+6], al
0x18001a89a  jnz     loc_18001A7EB
0x18001a8a0  movzx   eax, byte ptr [rcx+7]
0x18001a8a4  xor     al, [r10+7]
0x18001a8a8  test    al, 1
0x18001a8aa  jnz     loc_18001A7EB
0x18001a8b0  test    r14d, r14d
0x18001a8b3  jg      loc_18001A9B7
0x18001a8b9  mov     rdx, [rdi]
0x18001a8bc  mov     ecx, [rdi+8]
0x18001a8bf  mov     eax, [rdx+8]
0x18001a8c2  test    eax, eax
0x18001a8c4  jle     loc_18001A96E
0x18001a8ca  cmp     ecx, eax
0x18001a8cc  jge     loc_18001A96E
0x18001a8d2  mov     rsi, [rdx]
0x18001a8d5  test    rsi, rsi
0x18001a8d8  jz      loc_18001A96E
0x18001a8de  test    ecx, ecx
0x18001a8e0  js      loc_18001A96E
0x18001a8e6  mov     eax, ecx
0x18001a8e8  imul    eax, [rdx+10h]
0x18001a8ec  cdqe
0x18001a8ee  mov     esi, [rax+rsi]
0x18001a8f1  mov     rax, [rdx]
0x18001a8f4  imul    ecx, [rdx+10h]
0x18001a8f8  movsxd  rdx, ecx
0x18001a8fb  add     rdx, rax
0x18001a8fe  mov     rax, [r15]
0x18001a901  mov     rcx, r15
0x18001a904  movsx   edx, word ptr [rdx+4]
0x18001a908  mov     rax, [rax+8]
0x18001a90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a911  mov     edx, [rdi+8]; int
0x18001a914  mov     r8d, 1; int
0x18001a91a  mov     rcx, [rdi]; this
0x18001a91d  call    ?Remove@CArrayBase@@QEAAXJJ@Z; CArrayBase::Remove(long,long)
0x18001a922  mov     rcx, [rdi]
0x18001a925  mov     edx, [rcx+8]
0x18001a928  test    edx, edx
0x18001a92a  jle     short loc_18001A99B
0x18001a92c  mov     eax, [rdi+8]
0x18001a92f  cmp     eax, edx
0x18001a931  jge     short loc_18001A99B
0x18001a933  mov     rdx, [rcx]
0x18001a936  test    rdx, rdx
0x18001a939  jz      short loc_18001A99B
0x18001a93b  test    eax, eax
0x18001a93d  js      short loc_18001A99B
0x18001a93f  imul    eax, [rcx+10h]
0x18001a943  movsxd  rcx, eax
0x18001a946  add     rcx, rdx
0x18001a949  add     [rcx], esi
0x18001a94b  jmp     loc_18001A7EB
0x18001a950  xor     r9d, r9d
0x18001a953  jmp     loc_18001A6E4
0x18001a958  xor     r10d, r10d
0x18001a95b  jmp     loc_18001A720
0x18001a960  xor     edx, edx
0x18001a962  jmp     loc_18001A797
0x18001a967  xor     ecx, ecx
0x18001a969  jmp     loc_18001A7DC
0x18001a96e  mov     esi, ds:0
0x18001a975  test    eax, eax
0x18001a977  jle     short loc_18001A98D
0x18001a979  cmp     ecx, eax
0x18001a97b  jge     short loc_18001A98D
0x18001a97d  mov     rax, [rdx]
0x18001a980  test    rax, rax
0x18001a983  jz      short loc_18001A98D
0x18001a985  test    ecx, ecx
0x18001a987  jns     loc_18001A8F4
0x18001a98d  xor     edx, edx
0x18001a98f  jmp     loc_18001A8FE
0x18001a994  xor     ecx, ecx
0x18001a996  jmp     loc_18001A869
0x18001a99b  xor     ecx, ecx
0x18001a99d  jmp     short loc_18001A949
0x18001a99f  mov     rcx, rdi; this
0x18001a9a2  call    ?PrevRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::PrevRun(void)
0x18001a9a7  jmp     loc_18001A832
0x18001a9ac  xor     edx, edx
0x18001a9ae  lea     ecx, [r8-1]
0x18001a9b2  jmp     loc_18001A744
0x18001a9b7  mov     rcx, rdi; this
0x18001a9ba  call    ?PrevRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::PrevRun(void)
0x18001a9bf  jmp     loc_18001A8B9
```
