# HsmIBitmapVOLATILEMarkRangeEx

- ea: `0x1400448bc`
- end: `0x140044a4a`
- name: `HsmIBitmapVOLATILEMarkRangeEx`
- size: `398`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140065284`
- `0x1400652e4`

## callees

- `0x140003c50`
- `0x14000ac28`
- `0x1400448bc`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14004498e`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14004498e`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400449a8`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400449a8`
- `FLTMGR!FltReleasePushLockEx` at `0x1400449ca`
- `FLTMGR!FltReleasePushLockEx` at `0x1400449ca`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140044968`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140044968`

## pseudocode

```c
__int64 __fastcall HsmIBitmapVOLATILEMarkRangeEx(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 v4; // r15
  __int64 v5; // rbp
  unsigned int v6; // r8d
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rcx
  int v10; // esi
  LONGLONG v11; // r13
  LONGLONG v12; // r8
  LONGLONG v13; // rbx

  if ( !a2 )
    a2 = (__int64 *)(a1 + 32);
  v4 = *a2;
  if ( !a3 )
    a3 = (__int64 *)(a1 + 8);
  v5 = *a3;
  if ( v4 >= *a3 )
    goto LABEL_19;
  v6 = *(_DWORD *)(a1 + 16);
  v7 = *(_QWORD *)(a1 + 8);
  v8 = (unsigned int)(1 << ((v6 >> 6) & 0x3F));
  v9 = ~(v8 - 1);
  if ( v5 > (v9 & (v7 + v8 - 1)) )
    goto LABEL_19;
  if ( v5 == v7 )
    v5 = v9 & (v8 + v5 - 1);
  if ( (((_DWORD)v8 - 1) & (unsigned int)v4) != 0 || (((_DWORD)v8 - 1) & (unsigned int)v5) != 0 || (v6 & 0x20) != 0 )
  {
LABEL_19:
    v10 = -1073741595;
    HsmDbgBreakOnStatus(-1073741595);
  }
  else
  {
    v10 = 0;
    v11 = (v5 - v4) / v8;
    FltAcquirePushLockExclusiveEx(a1 + 40, 0);
    if ( v11 > 0 )
    {
      v12 = (v5 - v4) / v8;
      v13 = v4 / v8;
      FsRtlRemoveBaseMcbEntry((PBASE_MCB)(a1 + 48), v13, v12);
      if ( !FsRtlAddBaseMcbEntry((PBASE_MCB)(a1 + 48), v13, v13 + 1, v11) )
      {
        v10 = -1073741670;
        HsmDbgBreakOnStatus(-1073741670);
      }
    }
    FltReleasePushLockEx(a1 + 40, 0);
    if ( v10 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqiqd(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
        a1,
        *(_QWORD *)a1,
        v4,
        v5,
        v10);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400448bc  push    rbx
0x1400448be  push    rbp
0x1400448bf  push    rsi
0x1400448c0  push    rdi
0x1400448c1  push    r12
0x1400448c3  push    r13
0x1400448c5  push    r14
0x1400448c7  push    r15
0x1400448c9  sub     rsp, 48h
0x1400448cd  mov     r14, rcx
0x1400448d0  test    rdx, rdx
0x1400448d3  jnz     short loc_1400448D9
0x1400448d5  lea     rdx, [rcx+20h]
0x1400448d9  mov     r15, [rdx]
0x1400448dc  test    r8, r8
0x1400448df  jnz     short loc_1400448E5
0x1400448e1  lea     r8, [rcx+8]
0x1400448e5  mov     rbp, [r8]
0x1400448e8  cmp     r15, rbp
0x1400448eb  jge     loc_140044A2A
0x1400448f1  mov     r8d, [rcx+10h]
0x1400448f5  mov     eax, 1
0x1400448fa  mov     rdx, [r14+8]
0x1400448fe  mov     ecx, r8d
0x140044901  shr     ecx, 6
0x140044904  and     ecx, 3Fh
0x140044907  shl     eax, cl
0x140044909  mov     ebx, eax
0x14004490b  dec     rax
0x14004490e  mov     rcx, rax
0x140044911  add     rax, rdx
0x140044914  not     rcx
0x140044917  and     rax, rcx
0x14004491a  cmp     rbp, rax
0x14004491d  jg      loc_140044A2A
0x140044923  cmp     rbp, rdx
0x140044926  jnz     short loc_140044931
0x140044928  dec     rbp
0x14004492b  add     rbp, rbx
0x14004492e  and     rbp, rcx
0x140044931  lea     edx, [rbx-1]
0x140044934  test    r15, rdx
0x140044937  setz    cl
0x14004493a  test    rbp, rdx
0x14004493d  setz    al
0x140044940  test    al, cl
0x140044942  jz      loc_140044A2A
0x140044948  test    r8b, 20h
0x14004494c  jnz     loc_140044A2A
0x140044952  mov     rax, rbp
0x140044955  lea     rcx, [r14+28h]
0x140044959  sub     rax, r15
0x14004495c  xor     esi, esi
0x14004495e  cqo
0x140044960  idiv    rbx
0x140044963  xor     edx, edx
0x140044965  mov     r13, rax
0x140044968  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14004496f  nop     dword ptr [rax+rax+00h]
0x140044974  test    r13, r13
0x140044977  jle     short loc_1400449C4
0x140044979  mov     rax, r15
0x14004497c  lea     rcx, [r14+30h]; Mcb
0x140044980  cqo
0x140044982  mov     r8, r13; SectorCount
0x140044985  idiv    rbx
0x140044988  mov     rdx, rax; Vbn
0x14004498b  mov     rbx, rax
0x14004498e  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x140044995  nop     dword ptr [rax+rax+00h]
0x14004499a  lea     r8, [rbx+1]; Lbn
0x14004499e  mov     r9, r13; SectorCount
0x1400449a1  mov     rdx, rbx; Vbn
0x1400449a4  lea     rcx, [r14+30h]; Mcb
0x1400449a8  call    cs:__imp_FsRtlAddBaseMcbEntry
0x1400449af  nop     dword ptr [rax+rax+00h]
0x1400449b4  test    al, al
0x1400449b6  jnz     short loc_1400449C4
0x1400449b8  mov     esi, 0C000009Ah
0x1400449bd  mov     ecx, esi
0x1400449bf  call    HsmDbgBreakOnStatus
0x1400449c4  xor     edx, edx
0x1400449c6  lea     rcx, [r14+28h]
0x1400449ca  call    cs:__imp_FltReleasePushLockEx
0x1400449d1  nop     dword ptr [rax+rax+00h]
0x1400449d6  test    esi, esi
0x1400449d8  jns     short loc_140044A36
0x1400449da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400449e1  lea     rax, WPP_GLOBAL_Control
0x1400449e8  cmp     rcx, rax
0x1400449eb  jz      short loc_140044A36
0x1400449ed  mov     eax, [rcx+2Ch]
0x1400449f0  test    al, 1
0x1400449f2  jz      short loc_140044A36
0x1400449f4  cmp     byte ptr [rcx+29h], 2
0x1400449f8  jb      short loc_140044A36
0x1400449fa  mov     rax, [r14]
0x1400449fd  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x140044a04  mov     rcx, [rcx+18h]
0x140044a08  mov     edx, 18h
0x140044a0d  mov     [rsp+88h+var_50], esi
0x140044a11  mov     r9, r14
0x140044a14  mov     [rsp+88h+var_58], rbp
0x140044a19  mov     [rsp+88h+var_60], r15
0x140044a1e  mov     [rsp+88h+var_68], rax
0x140044a23  call    WPP_SF_qqiqd
0x140044a28  jmp     short loc_140044A36
0x140044a2a  mov     ecx, 0C00000E5h
0x140044a2f  mov     esi, ecx
0x140044a31  call    HsmDbgBreakOnStatus
0x140044a36  mov     eax, esi
0x140044a38  add     rsp, 48h
0x140044a3c  pop     r15
0x140044a3e  pop     r14
0x140044a40  pop     r13
0x140044a42  pop     r12
0x140044a44  pop     rdi
0x140044a45  pop     rsi
0x140044a46  pop     rbp
0x140044a47  pop     rbx
0x140044a48  retn
```
