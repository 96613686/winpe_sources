# CClfsLogFcbPhysical::QueryLogFileInfo(_FILE_OBJECT *,_CLS_LOG_INFORMATION_CLASS,void *,ulong,void *,ulong &)

- ea: `0x140069450`
- end: `0x1400699c2`
- name: `?QueryLogFileInfo@CClfsLogFcbPhysical@@UEAAJPEAU_FILE_OBJECT@@W4_CLS_LOG_INFORMATION_CLASS@@PEAXK2AEAK@Z`
- size: `1394`
- prototype: `__int64 __usercall@<rax>(CClfsLogFcbPhysical *__hidden this@<rcx>, struct _FILE_OBJECT *@<rdx>, enum _CLS_LOG_INFORMATION_CLASS@<r8d>, void *@<r9>, unsigned int, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140015f10`

## callees

- `0x140017f20`
- `0x140017f80`
- `0x140018280`
- `0x140046f94`
- `0x140069450`

## import_xrefs

- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400695a3`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14006966a`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400696cd`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140069788`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140069997`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007b273`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400695a3`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14006966a`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x1400696cd`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140069788`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140069997`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x14007b273`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006948e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140069546`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400695cf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400696ad`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400696ea`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14006948e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140069546`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400695cf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400696ad`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400696ea`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::QueryLogFileInfo(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        unsigned int a3,
        struct _CLFS_PHYSICAL_LSN_INFORMATION *a4,
        unsigned int a5,
        struct _CLFS_PHYSICAL_LSN_INFORMATION *a6,
        unsigned int *a7)
{
  unsigned int PhysicalLsn; // r15d
  BOOLEAN v12; // r12
  __int64 v13; // rdi
  unsigned __int8 v14; // si
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // edx
  __int64 v19; // rax
  __int64 v20; // rdi
  struct _ERESOURCE *v21; // rcx
  CLFS_RECORD_INDEX v22; // esi
  __int16 v23; // r10
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned int v27; // r8d
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r8
  unsigned int v32; // edx
  __int64 v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rdi
  __int64 v36; // rdi
  __int16 v37; // r10
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r9
  unsigned int v41; // r8d
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // r8
  unsigned int v46; // edx
  __int64 v47; // rax
  int v48; // ecx
  int v49; // eax
  int v50; // edx
  unsigned int v51; // edi
  __int16 v52; // dx
  unsigned int v53; // ecx
  unsigned int v54; // edi
  unsigned int v55; // edi

  PhysicalLsn = 0;
  v12 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
  if ( a3 > 1 )
  {
    v51 = a3 - 2;
    if ( v51 )
    {
      v54 = v51 - 1;
      if ( v54 )
      {
        v55 = v54 - 1;
        if ( v55 )
        {
          if ( v55 == 1 )
          {
            if ( a4 )
              PhysicalLsn = CClfsLogFcbPhysical::QueryPhysicalLsn(this, a2, a4, a5 / 0x18, a6, a7);
            else
              PhysicalLsn = -1073741811;
          }
          else
          {
            PhysicalLsn = -1073741821;
          }
        }
        else if ( *a7 >= 4 )
        {
          memset(a6, 0, *a7);
          *(_DWORD *)&a6->StreamIdentifier = *((_DWORD *)this + 332);
          *a7 = 4;
        }
        else
        {
          *a7 = 4;
          PhysicalLsn = -2147483643;
        }
      }
      else if ( *a7 )
      {
        a6->StreamIdentifier = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 304LL))(this);
      }
      else
      {
        *a7 = 1;
        PhysicalLsn = -2147483643;
      }
    }
    else
    {
      v52 = *((_WORD *)this + 160);
      v53 = (unsigned __int16)(v52 + 4);
      if ( *a7 >= v53 )
      {
        *(_WORD *)&a6->StreamIdentifier = v52;
        memmove(&a6->StreamIdentifier + 2, *((const void **)this + 41), *((unsigned __int16 *)this + 160));
      }
      else
      {
        *a7 = v53;
        PhysicalLsn = -2147483643;
      }
    }
  }
  else if ( *a7 < 0x78 )
  {
    *a7 = 120;
    PhysicalLsn = -2147483643;
  }
  else
  {
    memset(a6, 0, *a7);
    *(_QWORD *)&a6[3].StreamIdentifier = *((_QWORD *)this + 61);
    a6[3].VirtualLsn.ullOffset = *((_QWORD *)this + 60);
    a6[3].PhysicalLsn.ullOffset = *((_QWORD *)this + 63);
    a6[2].PhysicalLsn.ullOffset = *((_QWORD *)this + 62);
    *(_QWORD *)&a6[4].StreamIdentifier = *((_QWORD *)this + 64);
    *(_QWORD *)&a6->StreamIdentifier = *((_QWORD *)this + 57);
    a6->PhysicalLsn.ullOffset = *((_QWORD *)this + 59);
    a6->VirtualLsn.ullOffset = *((_QWORD *)this + 58);
    a6[1].VirtualLsn.ullOffset = *((_QWORD *)this + 87);
    v13 = *((_QWORD *)this + 89);
    v14 = 0;
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v13 + 32), 1u);
    if ( *(_WORD *)(v13 + 40)
      && (v15 = *(_QWORD *)(v13 + 48), (v16 = *(_QWORD *)(v15 + 48)) != 0)
      && (v17 = *(unsigned int *)(v16 + 40), v18 = *(_DWORD *)(v15 + 56), (unsigned int)v17 < v18)
      && (unsigned int)v17 >= 0x70
      && v18 - (unsigned int)v17 >= 0x1338 )
    {
      v19 = v16 + v17;
    }
    else
    {
      v19 = 0;
    }
    if ( v19 )
      v14 = *(_BYTE *)(v19 + 4916);
    ExReleaseResourceForThreadLite(*(PERESOURCE *)(v13 + 32), (ERESOURCE_THREAD)KeGetCurrentThread());
    *(_DWORD *)&a6[2].StreamIdentifier = v14;
    v20 = *((_QWORD *)this + 89);
    v21 = *(struct _ERESOURCE **)(v20 + 32);
    v22 = 0;
    if ( v21 )
    {
      ExAcquireResourceSharedLite(v21, 1u);
      v23 = *(_WORD *)(v20 + 40);
      if ( v23
        && (v24 = *(_QWORD *)(v20 + 48), (v25 = *(_QWORD *)(v24 + 48)) != 0)
        && (v26 = *(unsigned int *)(v25 + 40), v27 = *(_DWORD *)(v24 + 56), (unsigned int)v26 < v27)
        && (unsigned int)v26 >= 0x70
        && v27 - (unsigned int)v26 >= 0x1338 )
      {
        v28 = v25 + v26;
      }
      else
      {
        v28 = 0;
      }
      if ( v28 )
      {
        if ( v23
          && (v29 = *(_QWORD *)(v20 + 48), (v30 = *(_QWORD *)(v29 + 48)) != 0)
          && (v31 = *(unsigned int *)(v30 + 40), v32 = *(_DWORD *)(v29 + 56), (unsigned int)v31 < v32)
          && (unsigned int)v31 >= 0x70
          && v32 - (unsigned int)v31 >= 0x1338 )
        {
          v33 = v30 + v31;
        }
        else
        {
          v33 = 0;
        }
        v22 = *(_DWORD *)(v33 + 300);
      }
      ExReleaseResourceForThreadLite(*(PERESOURCE *)(v20 + 32), (ERESOURCE_THREAD)KeGetCurrentThread());
    }
    a6[1].PhysicalLsn.offset.idxRecord = v22;
    *((_DWORD *)&a6[2].StreamIdentifier + 1) = *((unsigned __int16 *)this + 188);
    a6[2].VirtualLsn.offset.idxRecord = *((_DWORD *)this + 329);
    a6[2].VirtualLsn.offset.cidContainer = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
    v34 = *((_QWORD *)this + 89);
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v34 + 32), 1u);
    v35 = *(_QWORD *)(v34 + 136);
    ExReleaseResourceForThreadLite(*(PERESOURCE *)(v34 + 32), (ERESOURCE_THREAD)KeGetCurrentThread());
    *(_QWORD *)&a6[1].StreamIdentifier = v35;
    v36 = *((_QWORD *)this + 89);
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v36 + 32), 1u);
    v37 = *(_WORD *)(v36 + 40);
    if ( v37
      && (v38 = *(_QWORD *)(v36 + 48), (v39 = *(_QWORD *)(v38 + 48)) != 0)
      && (v40 = *(unsigned int *)(v39 + 40), v41 = *(_DWORD *)(v38 + 56), (unsigned int)v40 < v41)
      && (unsigned int)v40 >= 0x70
      && v41 - (unsigned int)v40 >= 0x1338 )
    {
      v42 = v39 + v40;
    }
    else
    {
      v42 = 0;
    }
    if ( v42 )
    {
      if ( v37
        && (v43 = *(_QWORD *)(v36 + 48), (v44 = *(_QWORD *)(v43 + 48)) != 0)
        && (v45 = *(unsigned int *)(v44 + 40), v46 = *(_DWORD *)(v43 + 56), (unsigned int)v45 < v46)
        && (unsigned int)v45 >= 0x70
        && v46 - (unsigned int)v45 >= 0x1338 )
      {
        v47 = v44 + v45;
      }
      else
      {
        v47 = 0;
      }
      *(_OWORD *)&a6[4].VirtualLsn.offset.idxRecord = *(_OWORD *)(v47 + 8);
    }
    ExReleaseResourceForThreadLite(*(PERESOURCE *)(v36 + 32), (ERESOURCE_THREAD)KeGetCurrentThread());
    v48 = *((_DWORD *)this + 354);
    if ( !v48 )
      goto LABEL_49;
    LOWORD(v49) = -1;
    LOWORD(v50) = -1;
    if ( this != (CClfsLogFcbPhysical *)-504LL )
      v50 = *((_DWORD *)this + 127);
    if ( (v50 & 0x3FF) == v48 )
    {
LABEL_49:
      a6[1].PhysicalLsn.offset.cidContainer = 0;
    }
    else
    {
      if ( this != (CClfsLogFcbPhysical *)-504LL )
        v49 = *((_DWORD *)this + 127);
      a6[1].PhysicalLsn.offset.cidContainer = v48 + ~(v49 & 0x3FF);
    }
    *a7 = 120;
    PhysicalLsn = 0;
  }
  if ( v12 )
    ExReleaseResourceForThreadLite((PERESOURCE)((char *)this + 200), (ERESOURCE_THREAD)KeGetCurrentThread());
  return PhysicalLsn;
}

```

## disassembly

```asm
0x140069450  mov     [rsp+arg_8], rbx
0x140069455  mov     [rsp+arg_10], rsi
0x14006945a  mov     [rsp+arg_0], rcx
0x14006945f  push    rdi
0x140069460  push    r12
0x140069462  push    r13
0x140069464  push    r14
0x140069466  push    r15
0x140069468  sub     rsp, 40h
0x14006946c  mov     rsi, r9
0x14006946f  mov     edi, r8d
0x140069472  mov     r14, rdx
0x140069475  mov     rbx, rcx
0x140069478  xor     r15d, r15d
0x14006947b  mov     [rsp+68h+var_34], r15d
0x140069480  mov     [rsp+68h+var_38], r15b
0x140069485  mov     dl, 1; Wait
0x140069487  add     rcx, 0C8h; Resource
0x14006948e  call    cs:__imp_ExAcquireResourceSharedLite
0x140069495  nop     dword ptr [rax+rax+00h]
0x14006949a  movzx   r12d, al
0x14006949e  mov     [rsp+68h+var_38], al
0x1400694a2  cmp     edi, 1
0x1400694a5  jnz     loc_140069802
0x1400694ab  mov     r15, [rsp+68h+arg_30]
0x1400694b3  mov     eax, [r15]
0x1400694b6  cmp     eax, 78h ; 'x'
0x1400694b9  jb      loc_1400697F0
0x1400694bf  mov     r8d, eax; Size
0x1400694c2  xor     edx, edx; Val
0x1400694c4  mov     r14, [rsp+68h+arg_28]
0x1400694cc  mov     rcx, r14; void *
0x1400694cf  call    memset
0x1400694d4  mov     rax, [rbx+1E8h]
0x1400694db  mov     [r14+48h], rax
0x1400694df  mov     rax, [rbx+1E0h]
0x1400694e6  mov     [r14+50h], rax
0x1400694ea  mov     rax, [rbx+1F8h]
0x1400694f1  mov     [r14+58h], rax
0x1400694f5  mov     rax, [rbx+1F0h]
0x1400694fc  mov     [r14+40h], rax
0x140069500  mov     rax, [rbx+200h]
0x140069507  mov     [r14+60h], rax
0x14006950b  mov     rax, [rbx+1C8h]
0x140069512  mov     [r14], rax
0x140069515  mov     rax, [rbx+1D8h]
0x14006951c  mov     [r14+10h], rax
0x140069520  mov     rax, [rbx+1D0h]
0x140069527  mov     [r14+8], rax
0x14006952b  mov     rax, [rbx+2B8h]
0x140069532  mov     [r14+20h], rax
0x140069536  mov     rdi, [rbx+2C8h]
0x14006953d  xor     sil, sil
0x140069540  mov     dl, 1; Wait
0x140069542  mov     rcx, [rdi+20h]; Resource
0x140069546  call    cs:__imp_ExAcquireResourceSharedLite
0x14006954d  nop     dword ptr [rax+rax+00h]
0x140069552  xor     eax, eax
0x140069554  cmp     ax, [rdi+28h]
0x140069558  jz      short loc_140069588
0x14006955a  mov     rax, [rdi+30h]
0x14006955e  mov     rcx, [rax+30h]
0x140069562  test    rcx, rcx
0x140069565  jz      short loc_140069588
0x140069567  mov     r8d, [rcx+28h]
0x14006956b  mov     edx, [rax+38h]
0x14006956e  cmp     r8d, edx
0x140069571  jnb     short loc_140069588
0x140069573  cmp     r8d, 70h ; 'p'
0x140069577  jb      short loc_140069588
0x140069579  sub     edx, r8d
0x14006957c  cmp     edx, 1338h
0x140069582  jnb     loc_140069955
0x140069588  xor     eax, eax
0x14006958a  test    rax, rax
0x14006958d  jz      short loc_140069596
0x14006958f  movzx   esi, byte ptr [rax+1334h]
0x140069596  mov     rdx, gs:188h; ResourceThreadId
0x14006959f  mov     rcx, [rdi+20h]; Resource
0x1400695a3  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400695aa  nop     dword ptr [rax+rax+00h]
0x1400695af  movzx   eax, sil
0x1400695b3  mov     [r14+30h], eax
0x1400695b7  mov     rdi, [rbx+2C8h]
0x1400695be  mov     rcx, [rdi+20h]; Resource
0x1400695c2  xor     esi, esi
0x1400695c4  test    rcx, rcx
0x1400695c7  jz      loc_140069676
0x1400695cd  mov     dl, 1; Wait
0x1400695cf  call    cs:__imp_ExAcquireResourceSharedLite
0x1400695d6  nop     dword ptr [rax+rax+00h]
0x1400695db  movzx   r10d, word ptr [rdi+28h]
0x1400695e0  xor     eax, eax
0x1400695e2  cmp     ax, r10w
0x1400695e6  jz      short loc_140069618
0x1400695e8  mov     rax, [rdi+30h]
0x1400695ec  mov     rdx, [rax+30h]
0x1400695f0  test    rdx, rdx
0x1400695f3  jz      short loc_140069618
0x1400695f5  mov     r9d, [rdx+28h]
0x1400695f9  mov     r8d, [rax+38h]
0x1400695fd  cmp     r9d, r8d
0x140069600  jnb     short loc_140069618
0x140069602  cmp     r9d, 70h ; 'p'
0x140069606  jb      short loc_140069618
0x140069608  sub     r8d, r9d
0x14006960b  cmp     r8d, 1338h
0x140069612  jnb     loc_14006995E
0x140069618  xor     eax, eax
0x14006961a  test    rax, rax
0x14006961d  jz      short loc_14006965D
0x14006961f  xor     eax, eax
0x140069621  cmp     ax, r10w
0x140069625  jz      short loc_140069655
0x140069627  mov     rax, [rdi+30h]
0x14006962b  mov     rcx, [rax+30h]
0x14006962f  test    rcx, rcx
0x140069632  jz      short loc_140069655
0x140069634  mov     r8d, [rcx+28h]
0x140069638  mov     edx, [rax+38h]
0x14006963b  cmp     r8d, edx
0x14006963e  jnb     short loc_140069655
0x140069640  cmp     r8d, 70h ; 'p'
0x140069644  jb      short loc_140069655
0x140069646  sub     edx, r8d
0x140069649  cmp     edx, 1338h
0x14006964f  jnb     loc_140069967
0x140069655  xor     eax, eax
0x140069657  mov     esi, [rax+12Ch]
0x14006965d  mov     rdx, gs:188h; ResourceThreadId
0x140069666  mov     rcx, [rdi+20h]; Resource
0x14006966a  call    cs:__imp_ExReleaseResourceForThreadLite
0x140069671  nop     dword ptr [rax+rax+00h]
0x140069676  mov     [r14+28h], esi
0x14006967a  movzx   eax, word ptr [rbx+178h]
0x140069681  mov     [r14+34h], eax
0x140069685  mov     eax, [rbx+524h]
0x14006968b  mov     [r14+38h], eax
0x14006968f  mov     rax, [rbx+2C8h]
0x140069696  mov     ecx, [rax+90h]
0x14006969c  mov     [r14+3Ch], ecx
0x1400696a0  mov     rsi, [rbx+2C8h]
0x1400696a7  mov     dl, 1; Wait
0x1400696a9  mov     rcx, [rsi+20h]; Resource
0x1400696ad  call    cs:__imp_ExAcquireResourceSharedLite
0x1400696b4  nop     dword ptr [rax+rax+00h]
0x1400696b9  mov     rdi, [rsi+88h]
0x1400696c0  mov     rdx, gs:188h; ResourceThreadId
0x1400696c9  mov     rcx, [rsi+20h]; Resource
0x1400696cd  call    cs:__imp_ExReleaseResourceForThreadLite
0x1400696d4  nop     dword ptr [rax+rax+00h]
0x1400696d9  mov     [r14+18h], rdi
0x1400696dd  mov     rdi, [rbx+2C8h]
0x1400696e4  mov     dl, 1; Wait
0x1400696e6  mov     rcx, [rdi+20h]; Resource
0x1400696ea  call    cs:__imp_ExAcquireResourceSharedLite
0x1400696f1  nop     dword ptr [rax+rax+00h]
0x1400696f6  movzx   r10d, word ptr [rdi+28h]
0x1400696fb  xor     eax, eax
0x1400696fd  cmp     ax, r10w
0x140069701  jz      short loc_140069733
0x140069703  mov     rax, [rdi+30h]
0x140069707  mov     rdx, [rax+30h]
0x14006970b  test    rdx, rdx
0x14006970e  jz      short loc_140069733
0x140069710  mov     r9d, [rdx+28h]
0x140069714  mov     r8d, [rax+38h]
0x140069718  cmp     r9d, r8d
0x14006971b  jnb     short loc_140069733
0x14006971d  cmp     r9d, 70h ; 'p'
0x140069721  jb      short loc_140069733
0x140069723  sub     r8d, r9d
0x140069726  cmp     r8d, 1338h
0x14006972d  jnb     loc_140069970
0x140069733  xor     eax, eax
0x140069735  test    rax, rax
0x140069738  jz      short loc_14006977B
0x14006973a  xor     eax, eax
0x14006973c  cmp     ax, r10w
0x140069740  jz      short loc_140069770
0x140069742  mov     rax, [rdi+30h]
0x140069746  mov     rcx, [rax+30h]
0x14006974a  test    rcx, rcx
0x14006974d  jz      short loc_140069770
0x14006974f  mov     r8d, [rcx+28h]
0x140069753  mov     edx, [rax+38h]
0x140069756  cmp     r8d, edx
0x140069759  jnb     short loc_140069770
0x14006975b  cmp     r8d, 70h ; 'p'
0x14006975f  jb      short loc_140069770
0x140069761  sub     edx, r8d
0x140069764  cmp     edx, 1338h
0x14006976a  jnb     loc_140069979
0x140069770  xor     eax, eax
0x140069772  movups  xmm0, xmmword ptr [rax+8]
0x140069776  movups  xmmword ptr [r14+68h], xmm0
0x14006977b  mov     rdx, gs:188h; ResourceThreadId
0x140069784  mov     rcx, [rdi+20h]; Resource
0x140069788  call    cs:__imp_ExReleaseResourceForThreadLite
0x14006978f  nop     dword ptr [rax+rax+00h]
0x140069794  mov     ecx, [rbx+588h]
0x14006979a  test    ecx, ecx
0x14006979c  jz      short loc_1400697E6
0x14006979e  mov     eax, 0FFFFFFFFh
0x1400697a3  mov     edx, eax
0x1400697a5  lea     r8, [rbx+1F8h]
0x1400697ac  test    r8, r8
0x1400697af  jz      short loc_1400697B5
0x1400697b1  mov     edx, [r8+4]
0x1400697b5  and     edx, 3FFh
0x1400697bb  cmp     edx, ecx
0x1400697bd  jz      short loc_1400697E6
0x1400697bf  test    r8, r8
0x1400697c2  jz      short loc_1400697C8
0x1400697c4  mov     eax, [r8+4]
0x1400697c8  and     eax, 3FFh
0x1400697cd  not     eax
0x1400697cf  add     eax, ecx
0x1400697d1  mov     [r14+2Ch], eax
0x1400697d5  mov     dword ptr [r15], 78h ; 'x'
0x1400697dc  mov     r15d, [rsp+68h+var_34]
0x1400697e1  jmp     loc_140069982
0x1400697e6  mov     dword ptr [r14+2Ch], 0
0x1400697ee  jmp     short loc_1400697D5
0x1400697f0  mov     dword ptr [r15], 78h ; 'x'
0x1400697f7  mov     r15d, 80000005h
0x1400697fd  jmp     loc_140069982
0x140069802  test    edi, edi
0x140069804  jz      loc_1400694AB
0x14006980a  sub     edi, 2
0x14006980d  jnz     short loc_140069835
0x14006980f  movzx   edx, word ptr [rbx+140h]
0x140069816  lea     eax, [rdx+4]
0x140069819  movzx   ecx, ax
0x14006981c  mov     rax, [rsp+68h+arg_30]
0x140069824  cmp     [rax], ecx
0x140069826  jnb     short loc_140069853
0x140069828  mov     [rax], ecx
0x14006982a  mov     r15d, 80000005h
0x140069830  jmp     loc_140069982
0x140069835  sub     edi, 1
0x140069838  jz      short loc_14006987B
0x14006983a  sub     edi, 1
0x14006983d  jz      loc_140069905
0x140069843  cmp     edi, 1
0x140069846  jz      short loc_1400698AD
0x140069848  mov     r15d, 0C0000003h
0x14006984e  jmp     loc_140069982
0x140069853  mov     rcx, [rsp+68h+arg_28]
0x14006985b  mov     [rcx], dx
0x14006985e  movzx   r8d, word ptr [rbx+140h]; Size
0x140069866  add     rcx, 2; void *
0x14006986a  mov     rdx, [rbx+148h]; Src
0x140069871  call    memmove
0x140069876  jmp     loc_140069982
0x14006987b  mov     rax, [rsp+68h+arg_30]
0x140069883  cmp     dword ptr [rax], 1
0x140069886  jb      loc_140069947
0x14006988c  mov     rax, [rbx]
0x14006988f  mov     rax, [rax+130h]
0x140069896  mov     rcx, rbx
0x140069899  call    _guard_dispatch_icall
0x14006989e  mov     rcx, [rsp+68h+arg_28]
0x1400698a6  mov     [rcx], al
0x1400698a8  jmp     loc_140069982
0x1400698ad  test    rsi, rsi
0x1400698b0  jnz     short loc_1400698BD
0x1400698b2  mov     r15d, 0C000000Dh
0x1400698b8  jmp     loc_140069982
0x1400698bd  mov     ecx, [rsp+68h+arg_20]
0x1400698c4  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400698ce  mul     rcx
0x1400698d1  shr     rdx, 4
0x1400698d5  mov     rax, [rsp+68h+arg_30]
0x1400698dd  mov     [rsp+68h+var_40], rax; unsigned int *
0x1400698e2  mov     rax, [rsp+68h+arg_28]
0x1400698ea  mov     [rsp+68h+var_48], rax; struct _CLFS_PHYSICAL_LSN_INFORMATION *
0x1400698ef  mov     r9d, edx; unsigned int
0x1400698f2  mov     r8, rsi; struct _CLFS_PHYSICAL_LSN_INFORMATION *
0x1400698f5  mov     rdx, r14; struct _FILE_OBJECT *
0x1400698f8  mov     rcx, rbx; this
0x1400698fb  call    ?QueryPhysicalLsn@CClfsLogFcbPhysical@@QEAAJPEAU_FILE_OBJECT@@PEAU_CLFS_PHYSICAL_LSN_INFORMATION@@K1AEAK@Z; CClfsLogFcbPhysical::QueryPhysicalLsn(_FILE_OBJECT *,_CLFS_PHYSICAL_LSN_INFORMATION *,ulong,_CLFS_PHYSICAL_LSN_INFORMATION *,ulong &)
0x140069900  mov     r15d, eax
0x140069903  jmp     short loc_140069982
0x140069905  mov     rsi, [rsp+68h+arg_30]
0x14006990d  mov     eax, [rsi]
0x14006990f  cmp     eax, 4
0x140069912  jnb     short loc_140069922
0x140069914  mov     dword ptr [rsi], 4
0x14006991a  mov     r15d, 80000005h
0x140069920  jmp     short loc_140069982
0x140069922  mov     r8, rax; Size
0x140069925  xor     edx, edx; Val
0x140069927  mov     rdi, [rsp+68h+arg_28]
0x14006992f  mov     rcx, rdi; void *
0x140069932  call    memset
0x140069937  mov     eax, [rbx+530h]
0x14006993d  mov     [rdi], eax
0x14006993f  mov     dword ptr [rsi], 4
0x140069945  jmp     short loc_140069982
  ... truncated ...
```
