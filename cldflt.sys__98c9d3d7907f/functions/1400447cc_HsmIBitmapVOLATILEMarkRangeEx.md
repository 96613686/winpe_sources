# HsmIBitmapVOLATILEMarkRangeEx

- ea: `0x1400447cc`
- end: `0x14004495a`
- name: `HsmIBitmapVOLATILEMarkRangeEx`
- size: `398`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140065164`
- `0x1400651c4`

## callees

- `0x140003c50`
- `0x14000ac28`
- `0x1400447cc`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14004489e`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14004489e`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400448b8`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x1400448b8`
- `FLTMGR!FltReleasePushLockEx` at `0x1400448da`
- `FLTMGR!FltReleasePushLockEx` at `0x1400448da`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140044878`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140044878`

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
    HsmDbgBreakOnStatus(3221225701LL);
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
        HsmDbgBreakOnStatus(3221225626LL);
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
0x1400447cc  push    rbx
0x1400447ce  push    rbp
0x1400447cf  push    rsi
0x1400447d0  push    rdi
0x1400447d1  push    r12
0x1400447d3  push    r13
0x1400447d5  push    r14
0x1400447d7  push    r15
0x1400447d9  sub     rsp, 48h
0x1400447dd  mov     r14, rcx
0x1400447e0  test    rdx, rdx
0x1400447e3  jnz     short loc_1400447E9
0x1400447e5  lea     rdx, [rcx+20h]
0x1400447e9  mov     r15, [rdx]
0x1400447ec  test    r8, r8
0x1400447ef  jnz     short loc_1400447F5
0x1400447f1  lea     r8, [rcx+8]
0x1400447f5  mov     rbp, [r8]
0x1400447f8  cmp     r15, rbp
0x1400447fb  jge     loc_14004493A
0x140044801  mov     r8d, [rcx+10h]
0x140044805  mov     eax, 1
0x14004480a  mov     rdx, [r14+8]
0x14004480e  mov     ecx, r8d
0x140044811  shr     ecx, 6
0x140044814  and     ecx, 3Fh
0x140044817  shl     eax, cl
0x140044819  mov     ebx, eax
0x14004481b  dec     rax
0x14004481e  mov     rcx, rax
0x140044821  add     rax, rdx
0x140044824  not     rcx
0x140044827  and     rax, rcx
0x14004482a  cmp     rbp, rax
0x14004482d  jg      loc_14004493A
0x140044833  cmp     rbp, rdx
0x140044836  jnz     short loc_140044841
0x140044838  dec     rbp
0x14004483b  add     rbp, rbx
0x14004483e  and     rbp, rcx
0x140044841  lea     edx, [rbx-1]
0x140044844  test    r15, rdx
0x140044847  setz    cl
0x14004484a  test    rbp, rdx
0x14004484d  setz    al
0x140044850  test    al, cl
0x140044852  jz      loc_14004493A
0x140044858  test    r8b, 20h
0x14004485c  jnz     loc_14004493A
0x140044862  mov     rax, rbp
0x140044865  lea     rcx, [r14+28h]
0x140044869  sub     rax, r15
0x14004486c  xor     esi, esi
0x14004486e  cqo
0x140044870  idiv    rbx
0x140044873  xor     edx, edx
0x140044875  mov     r13, rax
0x140044878  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14004487f  nop     dword ptr [rax+rax+00h]
0x140044884  test    r13, r13
0x140044887  jle     short loc_1400448D4
0x140044889  mov     rax, r15
0x14004488c  lea     rcx, [r14+30h]; Mcb
0x140044890  cqo
0x140044892  mov     r8, r13; SectorCount
0x140044895  idiv    rbx
0x140044898  mov     rdx, rax; Vbn
0x14004489b  mov     rbx, rax
0x14004489e  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x1400448a5  nop     dword ptr [rax+rax+00h]
0x1400448aa  lea     r8, [rbx+1]; Lbn
0x1400448ae  mov     r9, r13; SectorCount
0x1400448b1  mov     rdx, rbx; Vbn
0x1400448b4  lea     rcx, [r14+30h]; Mcb
0x1400448b8  call    cs:__imp_FsRtlAddBaseMcbEntry
0x1400448bf  nop     dword ptr [rax+rax+00h]
0x1400448c4  test    al, al
0x1400448c6  jnz     short loc_1400448D4
0x1400448c8  mov     esi, 0C000009Ah
0x1400448cd  mov     ecx, esi
0x1400448cf  call    HsmDbgBreakOnStatus
0x1400448d4  xor     edx, edx
0x1400448d6  lea     rcx, [r14+28h]
0x1400448da  call    cs:__imp_FltReleasePushLockEx
0x1400448e1  nop     dword ptr [rax+rax+00h]
0x1400448e6  test    esi, esi
0x1400448e8  jns     short loc_140044946
0x1400448ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400448f1  lea     rax, WPP_GLOBAL_Control
0x1400448f8  cmp     rcx, rax
0x1400448fb  jz      short loc_140044946
0x1400448fd  mov     eax, [rcx+2Ch]
0x140044900  test    al, 1
0x140044902  jz      short loc_140044946
0x140044904  cmp     byte ptr [rcx+29h], 2
0x140044908  jb      short loc_140044946
0x14004490a  mov     rax, [r14]
0x14004490d  lea     r8, WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids
0x140044914  mov     rcx, [rcx+18h]
0x140044918  mov     edx, 18h
0x14004491d  mov     [rsp+88h+var_50], esi
0x140044921  mov     r9, r14
0x140044924  mov     [rsp+88h+var_58], rbp
0x140044929  mov     [rsp+88h+var_60], r15
0x14004492e  mov     [rsp+88h+var_68], rax
0x140044933  call    WPP_SF_qqiqd
0x140044938  jmp     short loc_140044946
0x14004493a  mov     ecx, 0C00000E5h
0x14004493f  mov     esi, ecx
0x140044941  call    HsmDbgBreakOnStatus
0x140044946  mov     eax, esi
0x140044948  add     rsp, 48h
0x14004494c  pop     r15
0x14004494e  pop     r14
0x140044950  pop     r13
0x140044952  pop     r12
0x140044954  pop     rdi
0x140044955  pop     rsi
0x140044956  pop     rbp
0x140044957  pop     rbx
0x140044958  retn
```
