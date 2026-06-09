# ParseTransactResponse

- ea: `0x14000a700`
- end: `0x14000af3d`
- name: `ParseTransactResponse`
- size: `2109`
- prototype: `__int64 __fastcall(__int64, char *, unsigned int, __int64, unsigned int *, __int64, struct _MDL **, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140006af0`

## callees

- `0x14000a700`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x140012fb4`
- `0x1400148c4`
- `0x14001492c`
- `0x14001499c`
- `0x1400166c0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a80f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a97a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a80f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000a97a`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000acfb`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000ae17`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000acfb`
- `ntoskrnl!IoBuildPartialMdl` at `0x14000ae17`
- `ntoskrnl!IoFreeMdl` at `0x14000ae56`
- `ntoskrnl!IoFreeMdl` at `0x14000ae56`
- `rdbss!RxAllocateMdl2` at `0x14000acd5`
- `rdbss!RxAllocateMdl2` at `0x14000adf3`
- `rdbss!RxAllocateMdl2` at `0x14000acd5`
- `rdbss!RxAllocateMdl2` at `0x14000adf3`

## pseudocode

```c
__int64 __fastcall ParseTransactResponse(
        __int64 a1,
        char *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int *a5,
        __int64 a6,
        struct _MDL **a7,
        _DWORD *a8)
{
  char *v10; // rbx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  unsigned int *v16; // r14
  ULONG v17; // esi
  ULONG v18; // r12d
  __int64 v19; // rcx
  unsigned int v20; // r9d
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  char *v23; // rax
  unsigned int v24; // ebp
  __int64 v25; // rcx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  unsigned int v29; // r9d
  unsigned int v30; // r8d
  unsigned int v31; // r9d
  char *v32; // rax
  __int64 v33; // rcx
  char *v34; // r13
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  PDEVICE_OBJECT *v37; // r8
  struct _MDL *v38; // r11
  __int64 v39; // rdx
  unsigned int v40; // ebx
  ULONG v41; // r12d
  char *v42; // rcx
  unsigned int v43; // r10d
  size_t v44; // rbx
  struct _MDL *Mdl2; // rax
  struct _MDL *v46; // rbx
  unsigned int v47; // r14d
  struct _MDL *v48; // rax
  struct _MDL *v49; // rbp
  unsigned int v50; // eax
  ULONG Size; // [rsp+40h] [rbp-68h]
  char *VirtualAddress; // [rsp+48h] [rbp-60h]
  char *v53; // [rsp+50h] [rbp-58h]
  char *v54; // [rsp+58h] [rbp-50h]
  struct _MDL *v55; // [rsp+60h] [rbp-48h]
  unsigned int v57; // [rsp+C8h] [rbp+20h]
  unsigned int v58; // [rsp+D8h] [rbp+30h]

  v10 = a2;
  v11 = *(unsigned __int8 *)(a6 + 4);
  if ( v11 != 51 && (v12 = v11 - 37) != 0 && (v13 = v12 - 1) != 0 && (v14 = v13 - 12) != 0 )
  {
    if ( (unsigned int)(v14 - 110) >= 2 )
      return 3221225667LL;
    v16 = a5;
    *a5 += 38;
  }
  else
  {
    v16 = a5;
    *a5 += 22;
  }
  v17 = *((_DWORD *)a2 + 3);
  v18 = *((_DWORD *)a2 + 6);
  v57 = *((_DWORD *)a2 + 4);
  Size = v18;
  v58 = *((_DWORD *)a2 + 7);
  if ( !v17 )
  {
    v53 = 0;
    VirtualAddress = 0;
LABEL_33:
    if ( !v18 )
    {
      v54 = 0;
      v34 = 0;
      goto LABEL_57;
    }
    v28 = *(_QWORD *)(a1 + 384);
    if ( v28 )
    {
      v29 = *((_DWORD *)v10 + 8);
      if ( v29 + v18 < v29 || (v30 = *(_DWORD *)(a1 + 392), v29 + v18 > v30) )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          v36 = 81;
          goto LABEL_51;
        }
      }
      else
      {
        v31 = *(_DWORD *)(a1 + 396);
        if ( v31 + v18 >= v31 && v31 + v18 <= v30 )
        {
          if ( (*(_BYTE *)(v28 + 10) & 5) != 0 )
            v32 = *(char **)(v28 + 24);
          else
            v32 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000000u);
          if ( !v32 )
            return (unsigned int)-1073741670;
          v33 = *((unsigned int *)v10 + 8);
          a2 = &v32[v33];
          v54 = &v32[v33];
          v34 = (char *)(v33
                       + *(_QWORD *)(*(_QWORD *)(a1 + 384) + 32LL)
                       + *(unsigned int *)(*(_QWORD *)(a1 + 384) + 44LL));
LABEL_57:
          v37 = &WPP_GLOBAL_Control;
          v38 = 0;
          v24 = 0;
          v55 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_llll(WPP_GLOBAL_Control->AttachedDevice, a2, &WPP_GLOBAL_Control, v17, v57, v18, v58);
            v37 = &WPP_GLOBAL_Control;
            v38 = 0;
          }
          v39 = v57;
          v40 = a3;
          if ( v57 <= a3 && (*v16 = v57, v17) )
          {
            v41 = a3 - v57;
            if ( v17 < a3 - v57 )
              v41 = v17;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v41);
              v39 = v57;
            }
            memmove(v53, (const void *)(a6 + v39), v41);
            *v16 += v41;
            v37 = &WPP_GLOBAL_Control;
            v17 -= v41;
            v42 = &VirtualAddress[v41];
            *(_DWORD *)(a1 + 436) += v41;
            v39 = v41 + v57;
            v18 = Size;
            v38 = 0;
            v40 = a3;
            VirtualAddress = v42;
            v57 = v39;
          }
          else
          {
            v42 = VirtualAddress;
          }
          v43 = v58;
          if ( v58 <= v40 )
          {
            if ( v58 )
            {
              *v16 = v58;
              if ( v18 )
              {
                v44 = v40 - v58;
                if ( v18 < (unsigned int)v44 )
                  v44 = v18;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    86,
                    WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids,
                    (unsigned int)v44);
                  v43 = v58;
                }
                memmove(v54, (const void *)(a6 + v43), v44);
                v37 = &WPP_GLOBAL_Control;
                v34 += v44;
                *v16 += v44;
                v43 = v44 + v58;
                *(_DWORD *)(a1 + 396) += v44;
                v18 -= v44;
                v42 = VirtualAddress;
                v38 = 0;
                v39 = v57;
                v58 += v44;
              }
            }
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
            v42 = VirtualAddress;
            v37 = &WPP_GLOBAL_Control;
            v39 = v57;
            v38 = 0;
            v43 = v58;
          }
          if ( v17 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v17);
              v42 = VirtualAddress;
            }
            Mdl2 = (struct _MDL *)RxAllocateMdl2(v42, v17, 0, 0, 0);
            v46 = Mdl2;
            if ( !Mdl2 )
            {
              *(_DWORD *)(a1 + 436) += v17;
              return (unsigned int)-1073741670;
            }
            IoBuildPartialMdl(*(PMDL *)(a1 + 424), Mdl2, VirtualAddress, v17);
            *(_DWORD *)(a1 + 436) += v17;
            v37 = &WPP_GLOBAL_Control;
            v39 = v57;
            v38 = v46;
            v43 = v58;
            v55 = v46;
          }
          else
          {
            v46 = 0;
          }
          if ( v18 )
          {
            v47 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v18);
              LODWORD(v39) = v57;
              v43 = v58;
            }
            if ( v17 )
            {
              v47 = v43 - v39 - v17;
              if ( v43 - (_DWORD)v39 != v17 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                {
                  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v47);
                }
                goto LABEL_98;
              }
            }
            if ( *(_DWORD *)(*(_QWORD *)(a1 + 384) + 40LL) < v18 )
            {
              v24 = -1073741629;
LABEL_106:
              if ( v46 )
                IoFreeMdl(v46);
              return v24;
            }
            v48 = (struct _MDL *)RxAllocateMdl2(v34, v18, 0, 0, 0);
            v49 = v48;
            if ( !v48 )
            {
LABEL_98:
              v24 = -1073741670;
              goto LABEL_106;
            }
            IoBuildPartialMdl(*(PMDL *)(a1 + 384), v48, v34, v18);
            v38 = v55;
            if ( v55 )
              v55->Next = v49;
            else
              v38 = v49;
            *(_DWORD *)(a1 + 396) += v18;
            v37 = &WPP_GLOBAL_Control;
          }
          else
          {
            if ( !v38 )
            {
LABEL_114:
              if ( *(_DWORD *)(a1 + 436) < *(_DWORD *)(a1 + 432) || *(_DWORD *)(a1 + 396) < *(_DWORD *)(a1 + 392) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
                }
                v50 = SmbCeReceive(a1, v39, v37);
                if ( v50 )
                  return v50;
              }
              return v24;
            }
            v47 = 0;
          }
          v39 = v17 + v47 + v18;
          *a7 = v38;
          *a8 = v39;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_qLl(
              WPP_GLOBAL_Control->AttachedDevice,
              v39,
              &WPP_GLOBAL_Control,
              v38,
              v17 + v47 + v18,
              v17 + v47 + v18);
            v37 = &WPP_GLOBAL_Control;
          }
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 504));
          v24 = -1073741802;
          goto LABEL_114;
        }
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          v36 = 82;
LABEL_51:
          WPP_SF_lll(v35->AttachedDevice, v36);
          return (unsigned int)-1073741629;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
    }
    return (unsigned int)-1073741629;
  }
  v19 = *(_QWORD *)(a1 + 424);
  if ( !v19 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
    return (unsigned int)-1073741629;
  }
  v20 = *((_DWORD *)a2 + 5);
  if ( v20 + v17 < v20 || (v21 = *(_DWORD *)(a1 + 432), v20 + v17 > v21) )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      return (unsigned int)-1073741629;
    v27 = 78;
    goto LABEL_27;
  }
  v22 = *(_DWORD *)(a1 + 436);
  if ( v22 + v17 < v22 || v22 + v17 > v21 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0 )
      return (unsigned int)-1073741629;
    v27 = 79;
LABEL_27:
    WPP_SF_lll(v26->AttachedDevice, v27);
    return (unsigned int)-1073741629;
  }
  if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
    v23 = *(char **)(v19 + 24);
  else
    v23 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000000u);
  if ( v23 )
  {
    v25 = *((unsigned int *)v10 + 5);
    v53 = &v23[v25];
    a2 = (char *)(v25 + *(_QWORD *)(*(_QWORD *)(a1 + 424) + 32LL) + *(unsigned int *)(*(_QWORD *)(a1 + 424) + 44LL));
    VirtualAddress = a2;
    goto LABEL_33;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x14000a700  mov     [rsp+arg_18], r9d
0x14000a705  mov     [rsp+arg_10], r8d
0x14000a70a  push    rbx
0x14000a70b  push    rbp
0x14000a70c  push    rdi
0x14000a70d  push    r14
0x14000a70f  push    r15
0x14000a711  sub     rsp, 80h
0x14000a718  mov     r15, [rsp+0A8h+arg_28]
0x14000a720  mov     rdi, rcx
0x14000a723  mov     rbx, rdx
0x14000a726  movzx   ecx, byte ptr [r15+4]
0x14000a72b  cmp     ecx, 33h ; '3'
0x14000a72e  jz      short loc_14000A761
0x14000a730  sub     ecx, 25h ; '%'
0x14000a733  jz      short loc_14000A761
0x14000a735  sub     ecx, 1
0x14000a738  jz      short loc_14000A761
0x14000a73a  sub     ecx, 0Ch
0x14000a73d  jz      short loc_14000A761
0x14000a73f  sub     ecx, 6Eh ; 'n'
0x14000a742  jz      short loc_14000A753
0x14000a744  cmp     ecx, 1
0x14000a747  jz      short loc_14000A753
0x14000a749  mov     eax, 0C00000C3h
0x14000a74e  jmp     loc_14000AF2D
0x14000a753  mov     r14, [rsp+0A8h+arg_20]
0x14000a75b  add     dword ptr [r14], 26h ; '&'
0x14000a75f  jmp     short loc_14000A76D
0x14000a761  mov     r14, [rsp+0A8h+arg_20]
0x14000a769  add     dword ptr [r14], 16h
0x14000a76d  mov     eax, [rdx+10h]
0x14000a770  mov     [rsp+0A8h+arg_0], rsi
0x14000a778  mov     esi, [rdx+0Ch]
0x14000a77b  mov     [rsp+0A8h+var_30], r12
0x14000a780  mov     r12d, [rdx+18h]
0x14000a784  mov     [rsp+0A8h+arg_18], eax
0x14000a78b  mov     eax, [rdx+1Ch]
0x14000a78e  mov     dword ptr [rsp+0A8h+Size], r12d
0x14000a793  mov     dword ptr [rsp+0A8h+arg_28], eax
0x14000a79a  test    esi, esi
0x14000a79c  jz      loc_14000A8EE
0x14000a7a2  mov     rcx, [rdi+1A8h]; MemoryDescriptorList
0x14000a7a9  test    rcx, rcx
0x14000a7ac  jz      loc_14000A8BB
0x14000a7b2  mov     r9d, [rdx+14h]
0x14000a7b6  lea     eax, [r9+rsi]
0x14000a7ba  cmp     eax, r9d
0x14000a7bd  jb      loc_14000A879
0x14000a7c3  mov     r8d, [rdi+1B0h]
0x14000a7ca  cmp     eax, r8d
0x14000a7cd  ja      loc_14000A879
0x14000a7d3  mov     r9d, [rdi+1B4h]
0x14000a7da  lea     eax, [r9+rsi]
0x14000a7de  cmp     eax, r9d
0x14000a7e1  jb      short loc_14000A851
0x14000a7e3  cmp     eax, r8d
0x14000a7e6  ja      short loc_14000A851
0x14000a7e8  test    byte ptr [rcx+0Ah], 5
0x14000a7ec  jz      short loc_14000A7F4
0x14000a7ee  mov     rax, [rcx+18h]
0x14000a7f2  jmp     short loc_14000A81B
0x14000a7f4  mov     [rsp+0A8h+Priority], 40000000h; Priority
0x14000a7fc  xor     r9d, r9d; RequestedAddress
0x14000a7ff  xor     edx, edx; AccessMode
0x14000a801  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000a809  mov     r8d, 1; CacheType
0x14000a80f  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a816  nop     dword ptr [rax+rax+00h]
0x14000a81b  test    rax, rax
0x14000a81e  jnz     short loc_14000A82A
0x14000a820  mov     ebp, 0C000009Ah
0x14000a825  jmp     loc_14000AF1E
0x14000a82a  mov     ecx, [rbx+14h]
0x14000a82d  lea     r9, [rcx+rax]
0x14000a831  mov     rax, [rdi+1A8h]
0x14000a838  mov     [rsp+0A8h+var_58], r9
0x14000a83d  mov     edx, [rax+2Ch]
0x14000a840  add     rdx, [rax+20h]
0x14000a844  add     rdx, rcx
0x14000a847  mov     [rsp+0A8h+VirtualAddress], rdx
0x14000a84c  jmp     loc_14000A8FF
0x14000a851  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a858  lea     rax, WPP_GLOBAL_Control
0x14000a85f  cmp     rcx, rax
0x14000a862  jz      short loc_14000A8B1
0x14000a864  test    dword ptr [rcx+2Ch], 400h
0x14000a86b  jz      short loc_14000A8B1
0x14000a86d  mov     edx, 4Fh ; 'O'
0x14000a872  mov     [rsp+0A8h+Priority], r8d
0x14000a877  jmp     short loc_14000A8A4
0x14000a879  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a880  lea     rax, WPP_GLOBAL_Control
0x14000a887  cmp     rcx, rax
0x14000a88a  jz      short loc_14000A8B1
0x14000a88c  test    dword ptr [rcx+2Ch], 400h
0x14000a893  jz      short loc_14000A8B1
0x14000a895  mov     eax, [rdi+1B0h]
0x14000a89b  mov     edx, 4Eh ; 'N'
0x14000a8a0  mov     [rsp+0A8h+Priority], eax
0x14000a8a4  mov     rcx, [rcx+18h]
0x14000a8a8  mov     [rsp+0A8h+BugCheckOnFailure], esi
0x14000a8ac  call    WPP_SF_lll
0x14000a8b1  mov     ebp, 0C00000C3h
0x14000a8b6  jmp     loc_14000AF1E
0x14000a8bb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a8c2  lea     rax, WPP_GLOBAL_Control
0x14000a8c9  cmp     rcx, rax
0x14000a8cc  jz      short loc_14000A8B1
0x14000a8ce  test    dword ptr [rcx+2Ch], 400h
0x14000a8d5  jz      short loc_14000A8B1
0x14000a8d7  mov     rcx, [rcx+18h]
0x14000a8db  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14000a8e2  mov     edx, 50h ; 'P'
0x14000a8e7  call    WPP_SF_
0x14000a8ec  jmp     short loc_14000A8B1
0x14000a8ee  xor     r8d, r8d
0x14000a8f1  mov     [rsp+0A8h+var_58], 0
0x14000a8fa  mov     [rsp+0A8h+VirtualAddress], r8
0x14000a8ff  mov     [rsp+0A8h+var_38], r13
0x14000a904  test    r12d, r12d
0x14000a907  jz      loc_14000AA66
0x14000a90d  mov     rcx, [rdi+180h]; MemoryDescriptorList
0x14000a914  test    rcx, rcx
0x14000a917  jz      loc_14000AA2B
0x14000a91d  mov     r9d, [rbx+20h]
0x14000a921  lea     eax, [r9+r12]
0x14000a925  cmp     eax, r9d
0x14000a928  jb      loc_14000A9E8
0x14000a92e  mov     r8d, [rdi+188h]
0x14000a935  cmp     eax, r8d
0x14000a938  ja      loc_14000A9E8
0x14000a93e  mov     r9d, [rdi+18Ch]
0x14000a945  lea     eax, [r9+r12]
0x14000a949  cmp     eax, r9d
0x14000a94c  jb      short loc_14000A9B8
0x14000a94e  cmp     eax, r8d
0x14000a951  ja      short loc_14000A9B8
0x14000a953  test    byte ptr [rcx+0Ah], 5
0x14000a957  jz      short loc_14000A95F
0x14000a959  mov     rax, [rcx+18h]
0x14000a95d  jmp     short loc_14000A986
0x14000a95f  mov     [rsp+0A8h+Priority], 40000000h; Priority
0x14000a967  xor     r9d, r9d; RequestedAddress
0x14000a96a  xor     edx, edx; AccessMode
0x14000a96c  mov     [rsp+0A8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000a974  mov     r8d, 1; CacheType
0x14000a97a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000a981  nop     dword ptr [rax+rax+00h]
0x14000a986  test    rax, rax
0x14000a989  jnz     short loc_14000A995
0x14000a98b  mov     ebp, 0C000009Ah
0x14000a990  jmp     loc_14000AF19
0x14000a995  mov     ecx, [rbx+20h]
0x14000a998  lea     rdx, [rcx+rax]
0x14000a99c  mov     rax, [rdi+180h]
0x14000a9a3  mov     [rsp+0A8h+var_50], rdx
0x14000a9a8  mov     r13d, [rax+2Ch]
0x14000a9ac  add     r13, [rax+20h]
0x14000a9b0  add     r13, rcx
0x14000a9b3  jmp     loc_14000AA72
0x14000a9b8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a9bf  lea     rax, WPP_GLOBAL_Control
0x14000a9c6  cmp     rcx, rax
0x14000a9c9  jz      loc_14000AA5C
0x14000a9cf  test    dword ptr [rcx+2Ch], 400h
0x14000a9d6  jz      loc_14000AA5C
0x14000a9dc  mov     edx, 52h ; 'R'
0x14000a9e1  mov     [rsp+0A8h+Priority], r8d
0x14000a9e6  jmp     short loc_14000AA13
0x14000a9e8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000a9ef  lea     rax, WPP_GLOBAL_Control
0x14000a9f6  cmp     rcx, rax
0x14000a9f9  jz      short loc_14000AA5C
0x14000a9fb  test    dword ptr [rcx+2Ch], 400h
0x14000aa02  jz      short loc_14000AA5C
0x14000aa04  mov     eax, [rdi+188h]
0x14000aa0a  mov     edx, 51h ; 'Q'
0x14000aa0f  mov     [rsp+0A8h+Priority], eax
0x14000aa13  mov     rcx, [rcx+18h]
0x14000aa17  mov     [rsp+0A8h+BugCheckOnFailure], r12d
0x14000aa1c  call    WPP_SF_lll
0x14000aa21  mov     ebp, 0C00000C3h
0x14000aa26  jmp     loc_14000AF19
0x14000aa2b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000aa32  lea     rax, WPP_GLOBAL_Control
0x14000aa39  cmp     rcx, rax
0x14000aa3c  jz      short loc_14000AA5C
0x14000aa3e  test    dword ptr [rcx+2Ch], 400h
0x14000aa45  jz      short loc_14000AA5C
0x14000aa47  mov     rcx, [rcx+18h]
0x14000aa4b  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14000aa52  mov     edx, 53h ; 'S'
0x14000aa57  call    WPP_SF_
0x14000aa5c  mov     ebp, 0C00000C3h
0x14000aa61  jmp     loc_14000AF19
0x14000aa66  mov     [rsp+0A8h+var_50], 0
0x14000aa6f  xor     r13d, r13d
0x14000aa72  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000aa79  lea     r8, WPP_GLOBAL_Control
0x14000aa80  xor     r11d, r11d
0x14000aa83  xor     ebp, ebp
0x14000aa85  mov     [rsp+0A8h+var_48], r11
0x14000aa8a  cmp     rcx, r8
0x14000aa8d  jz      short loc_14000AAC9
0x14000aa8f  test    dword ptr [rcx+2Ch], 400h
0x14000aa96  jz      short loc_14000AAC9
0x14000aa98  mov     eax, dword ptr [rsp+0A8h+arg_28]
0x14000aa9f  mov     r9d, esi
0x14000aaa2  mov     rcx, [rcx+18h]
0x14000aaa6  mov     [rsp+0A8h+var_78], eax
0x14000aaaa  mov     eax, [rsp+0A8h+arg_18]
0x14000aab1  mov     [rsp+0A8h+Priority], r12d
0x14000aab6  mov     [rsp+0A8h+BugCheckOnFailure], eax
0x14000aaba  call    WPP_SF_llll
0x14000aabf  lea     r8, WPP_GLOBAL_Control
0x14000aac6  xor     r11d, r11d
0x14000aac9  mov     edx, [rsp+0A8h+arg_18]
0x14000aad0  mov     ebx, [rsp+0A8h+arg_10]
0x14000aad7  cmp     edx, ebx
0x14000aad9  ja      loc_14000AB81
0x14000aadf  mov     [r14], edx
0x14000aae2  test    esi, esi
0x14000aae4  jz      loc_14000AB81
0x14000aaea  mov     r12d, ebx
0x14000aaed  sub     r12d, edx
0x14000aaf0  cmp     esi, r12d
0x14000aaf3  cmovb   r12d, esi
0x14000aaf7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000aafe  cmp     rcx, r8
0x14000ab01  jz      short loc_14000AB2B
0x14000ab03  test    dword ptr [rcx+2Ch], 400h
0x14000ab0a  jz      short loc_14000AB2B
0x14000ab0c  mov     rcx, [rcx+18h]
0x14000ab10  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14000ab17  mov     edx, 55h ; 'U'
0x14000ab1c  mov     r9d, r12d
0x14000ab1f  call    WPP_SF_d
0x14000ab24  mov     edx, [rsp+0A8h+arg_18]
0x14000ab2b  mov     rcx, [rsp+0A8h+var_58]; void *
0x14000ab30  add     rdx, r15; Src
0x14000ab33  mov     r8d, r12d; Size
0x14000ab36  mov     ebx, r12d
0x14000ab39  call    memmove
0x14000ab3e  add     [r14], r12d
0x14000ab41  lea     r8, WPP_GLOBAL_Control
0x14000ab48  mov     rcx, [rsp+0A8h+VirtualAddress]
0x14000ab4d  sub     esi, r12d
0x14000ab50  mov     edx, [rsp+0A8h+arg_18]
0x14000ab57  add     rcx, rbx
0x14000ab5a  add     [rdi+1B4h], r12d
0x14000ab61  add     edx, r12d
0x14000ab64  mov     r12d, dword ptr [rsp+0A8h+Size]
0x14000ab69  xor     r11d, r11d
0x14000ab6c  mov     ebx, [rsp+0A8h+arg_10]
0x14000ab73  mov     [rsp+0A8h+VirtualAddress], rcx
0x14000ab78  mov     [rsp+0A8h+arg_18], edx
0x14000ab7f  jmp     short loc_14000AB86
0x14000ab81  mov     rcx, [rsp+0A8h+VirtualAddress]
0x14000ab86  mov     r10d, dword ptr [rsp+0A8h+arg_28]
0x14000ab8e  cmp     r10d, ebx
0x14000ab91  ja      loc_14000AC44
0x14000ab97  test    r10d, r10d
0x14000ab9a  jz      loc_14000AC44
0x14000aba0  mov     [r14], r10d
0x14000aba3  test    r12d, r12d
0x14000aba6  jz      loc_14000AC44
0x14000abac  sub     ebx, r10d
0x14000abaf  cmp     r12d, ebx
0x14000abb2  cmovb   ebx, r12d
0x14000abb6  mov     [rsp+0A8h+arg_10], ebx
0x14000abbd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000abc4  cmp     rcx, r8
0x14000abc7  jz      short loc_14000ABF2
0x14000abc9  test    dword ptr [rcx+2Ch], 400h
0x14000abd0  jz      short loc_14000ABF2
0x14000abd2  mov     rcx, [rcx+18h]
0x14000abd6  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14000abdd  mov     edx, 56h ; 'V'
0x14000abe2  mov     r9d, ebx
0x14000abe5  call    WPP_SF_d
0x14000abea  mov     r10d, dword ptr [rsp+0A8h+arg_28]
0x14000abf2  mov     rcx, [rsp+0A8h+var_50]; void *
0x14000abf7  mov     r8, rbx; Size
0x14000abfa  mov     edx, r10d
0x14000abfd  add     rdx, r15; Src
0x14000ac00  call    memmove
0x14000ac05  mov     eax, [rsp+0A8h+arg_10]
0x14000ac0c  lea     r8, WPP_GLOBAL_Control
0x14000ac13  mov     r10d, dword ptr [rsp+0A8h+arg_28]
0x14000ac1b  add     r13, rbx
0x14000ac1e  add     [r14], eax
0x14000ac21  add     r10d, eax
0x14000ac24  add     [rdi+18Ch], eax
0x14000ac2a  sub     r12d, eax
0x14000ac2d  mov     rcx, [rsp+0A8h+VirtualAddress]
0x14000ac32  xor     r11d, r11d
0x14000ac35  mov     edx, [rsp+0A8h+arg_18]
0x14000ac3c  mov     dword ptr [rsp+0A8h+arg_28], r10d
0x14000ac44  mov     r9, cs:WPP_GLOBAL_Control; __annotation("TMF:",
  ... truncated ...
```
