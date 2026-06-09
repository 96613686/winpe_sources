# FatFlushDirectory

- ea: `0x14003e028`
- end: `0x14003e406`
- name: `FatFlushDirectory`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x14003e94c`

## callees

- `0x140005288`
- `0x140023ad4`
- `0x14002486c`
- `0x1400319bc`
- `0x14003805c`
- `0x14003e028`
- `0x14003e870`
- `0x1400465f4`
- `0x1400487b8`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005ead3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005eb55`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005eb7f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005ead3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005eb55`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005eb7f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003e2dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005eb2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003e2dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005eb2d`
- `ntoskrnl!CcUnpinData` at `0x14003e27f`
- `ntoskrnl!CcUnpinData` at `0x14003e2b6`
- `ntoskrnl!CcUnpinData` at `0x14005eb01`
- `ntoskrnl!CcUnpinData` at `0x14003e27f`
- `ntoskrnl!CcUnpinData` at `0x14003e2b6`
- `ntoskrnl!CcUnpinData` at `0x14005eb01`

## pseudocode

```c
__int64 __fastcall FatFlushDirectory(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // rsi
  int *v5; // r14
  int v6; // eax
  __int64 v7; // r13
  __int64 i; // rdi
  _DWORD *v9; // r12
  unsigned int v10; // ecx
  int *v11; // rdx
  PVOID v12; // rcx
  int v13; // eax
  __int64 j; // rdi
  __int64 v15; // r12
  int v16; // eax
  char v18; // [rsp+30h] [rbp-88h]
  unsigned int v19; // [rsp+34h] [rbp-84h]
  __int64 v20; // [rsp+38h] [rbp-80h] BYREF
  PVOID Bcb; // [rsp+40h] [rbp-78h] BYREF
  __int64 v22; // [rsp+48h] [rbp-70h]
  int *v23; // [rsp+50h] [rbp-68h]
  __int64 v24; // [rsp+58h] [rbp-60h]
  __int64 v25; // [rsp+60h] [rbp-58h]
  __int64 NextFcbTopDown; // [rsp+68h] [rbp-50h]
  __int64 v27; // [rsp+70h] [rbp-48h]
  char v29; // [rsp+D8h] [rbp+20h]

  v4 = a1;
  v20 = 0;
  Bcb = 0;
  v19 = 0;
  v18 = 0;
  v5 = (int *)(a1 + 68);
  v24 = a1 + 68;
  v6 = *(_DWORD *)(a1 + 68);
  if ( (v6 & 4) != 0 )
  {
    v29 = 0;
  }
  else
  {
    v29 = 1;
    v6 |= 4u;
    *v5 = v6;
  }
  if ( (v6 & 2) == 0 )
  {
    v18 = 1;
    *v5 = v6 | 2;
  }
  v7 = *(_QWORD *)(a2 + 184);
  v25 = v7;
  for ( i = a2; ; i = NextFcbTopDown )
  {
    v22 = i;
    if ( !i )
      break;
    NextFcbTopDown = FatGetNextFcbTopDown(a1, i, a2);
    if ( *(_WORD *)i == 1282 && *(_QWORD *)(v7 + 784) != i )
    {
      v27 = i;
      v9 = (_DWORD *)(i + 192);
      v23 = (int *)(i + 192);
      if ( (*(_DWORD *)(i + 192) & 1) == 0 || *(_DWORD *)(i + 228) )
      {
        FatAcquireExclusiveFcb(v4, i);
        _InterlockedAnd((volatile signed __int32 *)(v7 + 200), 0xFFFFFEFF);
        FatVerifyFcb(v4, i);
        if ( *(_DWORD *)(i + 196) == 1 )
        {
          if ( (*v9 & 2) != 0 )
          {
            v23 = (int *)(i + 132);
            FatTruncateFileAllocation(v4, i, (unsigned int)(*(_DWORD *)(i + 132) + *(_DWORD *)(i + 32)));
          }
          else
          {
            v23 = (int *)(v27 + 132);
          }
          FatGetDirentFromFcbOrDcb(v4, i, 0, (unsigned int)&v20, (__int64)&Bcb);
          v10 = *(_DWORD *)(i + 32);
          v11 = v23;
          if ( (*(_DWORD *)(i + 192) & 0x60000) != 0 )
            v10 = *v23 + ((v10 + 15) & 0xFFFFFFF0);
          if ( *(_DWORD *)(v20 + 28) != v10 )
          {
            *(_DWORD *)(v20 + 28) = v10;
            if ( (*(_DWORD *)(v7 + 200) & 0x400000) != 0 && (*v9 & 0x8000) != 0 )
            {
              FatUpdateFileHeader(v4, i, *v11, *(unsigned int *)(v20 + 28));
              *(_BYTE *)(i + 136) = ((*(_BYTE *)(v20 + 28) + 15) & 0xF0) - *(_BYTE *)(v20 + 28);
              *(_DWORD *)(v20 + 28) = (*(_DWORD *)(v20 + 28) + 15) & 0xFFFFFFF0;
              *(_DWORD *)(v20 + 28) += *v23;
              *(_BYTE *)(v20 + 12) = *(_BYTE *)(v20 + 12) & 0x1B
                                   | (4 * (*(_BYTE *)(i + 136) & 1 | (4 * (*(_BYTE *)(i + 136) & 0xFE))));
            }
          }
          v12 = Bcb;
          if ( Bcb )
          {
            CcUnpinData(Bcb);
            Bcb = 0;
          }
          v13 = FatFlushFile((__int64)v12, i, a3);
          if ( v13 < 0 )
            v19 = v13;
        }
        a1 = (__int64)Bcb;
        if ( Bcb )
        {
          CcUnpinData(Bcb);
          Bcb = 0;
        }
        if ( (*(_DWORD *)(v7 + 200) & 0x100) == 0 )
          ExReleaseResourceLite(*(PERESOURCE *)(i + 8));
      }
    }
  }
  for ( j = a2; ; j = v15 )
  {
    v22 = j;
    if ( !j )
      break;
    v15 = FatGetNextFcbTopDown(a1, j, a2);
    NextFcbTopDown = v15;
    if ( *(_WORD *)j != 1282 )
    {
      a1 = *(unsigned int *)(j + 192);
      if ( (a1 & 1) == 0 || *(_DWORD *)(j + 228) )
      {
        FatVerifyFcb(v4, j);
        if ( *(_DWORD *)(j + 196) == 1 )
        {
          v16 = FatFlushFile(a1, j, a3);
          a1 = v19;
          if ( v16 < 0 )
            a1 = (unsigned int)v16;
          v19 = a1;
        }
      }
    }
  }
  FatUnpinRepinnedBcbs(v4);
  if ( v29 )
    *v5 &= ~4u;
  if ( v18 )
    *v5 &= ~2u;
  return v19;
}

```

## disassembly

```asm
0x14003e028  mov     rax, rsp
0x14003e02b  mov     [rax+18h], r8d
0x14003e02f  mov     [rax+10h], rdx
0x14003e033  mov     [rax+8], rcx
0x14003e037  push    rsi
0x14003e038  push    rdi
0x14003e039  push    r12
0x14003e03b  push    r13
0x14003e03d  push    r14
0x14003e03f  push    r15
0x14003e041  sub     rsp, 88h
0x14003e048  mov     r15, rdx
0x14003e04b  mov     rsi, rcx
0x14003e04e  mov     qword ptr [rax-80h], 0
0x14003e056  mov     qword ptr [rax-78h], 0
0x14003e05e  mov     [rsp+0B8h+var_84], 0
0x14003e066  mov     [rsp+0B8h+var_88], 0
0x14003e06b  lea     r14, [rcx+44h]
0x14003e06f  mov     [rsp+0B8h+var_60], r14
0x14003e074  mov     eax, [r14]
0x14003e077  test    al, 4
0x14003e079  jnz     short loc_14003E08B
0x14003e07b  mov     [rsp+0B8h+arg_18], 1
0x14003e083  or      eax, 4
0x14003e086  mov     [r14], eax
0x14003e089  jmp     short loc_14003E093
0x14003e08b  mov     [rsp+0B8h+arg_18], 0
0x14003e093  test    al, 2
0x14003e095  jnz     short loc_14003E0A2
0x14003e097  mov     [rsp+0B8h+var_88], 1
0x14003e09c  or      eax, 2
0x14003e09f  mov     [r14], eax
0x14003e0a2  mov     r13, [rdx+0B8h]
0x14003e0a9  mov     [rsp+0B8h+var_58], r13
0x14003e0ae  mov     rdi, rdx
0x14003e0b1  mov     [rsp+0B8h+var_70], rdi
0x14003e0b6  test    rdi, rdi
0x14003e0b9  jz      loc_14003E315
0x14003e0bf  mov     r8, r15
0x14003e0c2  mov     rdx, rdi
0x14003e0c5  call    FatGetNextFcbTopDown
0x14003e0ca  mov     [rsp+0B8h+var_50], rax
0x14003e0cf  mov     eax, 502h
0x14003e0d4  cmp     [rdi], ax
0x14003e0d7  jnz     loc_14003E30B
0x14003e0dd  cmp     [r13+310h], rdi
0x14003e0e4  jz      loc_14003E30B
0x14003e0ea  mov     [rsp+0B8h+var_48], rdi
0x14003e0ef  lea     r12, [rdi+0C0h]
0x14003e0f6  mov     [rsp+0B8h+var_68], r12
0x14003e0fb  mov     eax, [r12]
0x14003e0ff  test    al, 1
0x14003e101  jz      short loc_14003E110
0x14003e103  cmp     dword ptr [rdi+0E4h], 0
0x14003e10a  jz      loc_14003E30B
0x14003e110  mov     rdx, rdi
0x14003e113  mov     rcx, rsi
0x14003e116  call    FatAcquireExclusiveFcb
0x14003e11b  lock and dword ptr [r13+0C8h], 0FFFFFEFFh
0x14003e127  mov     rdx, rdi
0x14003e12a  mov     rcx, rsi
0x14003e12d  call    FatVerifyFcb
0x14003e132  jmp     short loc_14003E15F
0x14003e134  mov     rsi, [rsp+0B8h+arg_0]
0x14003e13c  mov     dword ptr [rsi+48h], 0
0x14003e143  mov     r15, [rsp+0B8h+arg_8]
0x14003e14b  mov     rdi, [rsp+0B8h+var_70]
0x14003e150  mov     r13, [rsp+0B8h+var_58]
0x14003e155  mov     r12, [rsp+0B8h+var_68]
0x14003e15a  mov     r14, [rsp+0B8h+var_60]
0x14003e15f  cmp     dword ptr [rdi+0C4h], 1
0x14003e166  jnz     loc_14003E2AC
0x14003e16c  mov     eax, [r12]
0x14003e170  test    al, 2
0x14003e172  jz      short loc_14003E194
0x14003e174  lea     rax, [rdi+84h]
0x14003e17b  mov     [rsp+0B8h+var_68], rax
0x14003e180  mov     r8d, [rdi+20h]
0x14003e184  add     r8d, [rax]
0x14003e187  mov     rdx, rdi
0x14003e18a  mov     rcx, rsi
0x14003e18d  call    FatTruncateFileAllocation
0x14003e192  jmp     short loc_14003E1A4
0x14003e194  mov     rax, [rsp+0B8h+var_48]
0x14003e199  add     rax, 84h
0x14003e19f  mov     [rsp+0B8h+var_68], rax
0x14003e1a4  lea     rax, [rsp+0B8h+Bcb]
0x14003e1a9  mov     [rsp+0B8h+var_98], rax
0x14003e1ae  lea     r9, [rsp+0B8h+var_80]
0x14003e1b3  xor     r8d, r8d
0x14003e1b6  mov     rdx, rdi
0x14003e1b9  mov     rcx, rsi
0x14003e1bc  call    FatGetDirentFromFcbOrDcb
0x14003e1c1  mov     ecx, [rdi+20h]
0x14003e1c4  mov     rdx, [rsp+0B8h+var_68]
0x14003e1c9  test    dword ptr [rdi+0C0h], 60000h
0x14003e1d3  jz      short loc_14003E1DD
0x14003e1d5  add     ecx, 0Fh
0x14003e1d8  and     ecx, 0FFFFFFF0h
0x14003e1db  add     ecx, [rdx]
0x14003e1dd  mov     rax, [rsp+0B8h+var_80]
0x14003e1e2  cmp     [rax+1Ch], ecx
0x14003e1e5  jz      loc_14003E275
0x14003e1eb  mov     [rax+1Ch], ecx
0x14003e1ee  mov     eax, [r13+0C8h]
0x14003e1f5  bt      eax, 16h
0x14003e1f9  jnb     short loc_14003E275
0x14003e1fb  test    dword ptr [r12], 8000h
0x14003e203  jz      short loc_14003E275
0x14003e205  mov     rax, [rsp+0B8h+var_80]
0x14003e20a  mov     r9d, [rax+1Ch]
0x14003e20e  mov     r8d, [rdx]
0x14003e211  mov     rdx, rdi
0x14003e214  mov     rcx, rsi
0x14003e217  call    FatUpdateFileHeader
0x14003e21c  mov     rax, [rsp+0B8h+var_80]
0x14003e221  mov     cl, [rax+1Ch]
0x14003e224  lea     eax, [rcx+0Fh]
0x14003e227  and     al, 0F0h
0x14003e229  sub     al, cl
0x14003e22b  mov     [rdi+88h], al
0x14003e231  mov     rcx, [rsp+0B8h+var_80]
0x14003e236  mov     eax, [rcx+1Ch]
0x14003e239  add     eax, 0Fh
0x14003e23c  and     eax, 0FFFFFFF0h
0x14003e23f  mov     [rcx+1Ch], eax
0x14003e242  mov     rcx, [rsp+0B8h+var_80]
0x14003e247  mov     rax, [rsp+0B8h+var_68]
0x14003e24c  mov     eax, [rax]
0x14003e24e  add     [rcx+1Ch], eax
0x14003e251  mov     al, [rdi+88h]
0x14003e257  mov     rdx, [rsp+0B8h+var_80]
0x14003e25c  mov     cl, al
0x14003e25e  and     cl, 0FEh
0x14003e261  shl     cl, 2
0x14003e264  and     al, 1
0x14003e266  or      cl, al
0x14003e268  shl     cl, 2
0x14003e26b  mov     al, [rdx+0Ch]
0x14003e26e  and     al, 1Bh
0x14003e270  or      cl, al
0x14003e272  mov     [rdx+0Ch], cl
0x14003e275  mov     rcx, [rsp+0B8h+Bcb]; Bcb
0x14003e27a  test    rcx, rcx
0x14003e27d  jz      short loc_14003E294
0x14003e27f  call    cs:__imp_CcUnpinData
0x14003e286  nop     dword ptr [rax+rax+00h]
0x14003e28b  mov     [rsp+0B8h+Bcb], 0
0x14003e294  mov     r8d, [rsp+0B8h+arg_10]
0x14003e29c  mov     rdx, rdi
0x14003e29f  call    FatFlushFile
0x14003e2a4  test    eax, eax
0x14003e2a6  jns     short loc_14003E2AC
0x14003e2a8  mov     [rsp+0B8h+var_84], eax
0x14003e2ac  mov     rcx, [rsp+0B8h+Bcb]; Bcb
0x14003e2b1  test    rcx, rcx
0x14003e2b4  jz      short loc_14003E2CB
0x14003e2b6  call    cs:__imp_CcUnpinData
0x14003e2bd  nop     dword ptr [rax+rax+00h]
0x14003e2c2  mov     [rsp+0B8h+Bcb], 0
0x14003e2cb  mov     eax, [r13+0C8h]
0x14003e2d2  bt      eax, 8
0x14003e2d6  jb      short loc_14003E2E8
0x14003e2d8  mov     rcx, [rdi+8]; Resource
0x14003e2dc  call    cs:__imp_ExReleaseResourceLite
0x14003e2e3  nop     dword ptr [rax+rax+00h]
0x14003e2e8  jmp     short loc_14003E30B
0x14003e2ea  mov     rsi, [rsp+0B8h+arg_0]
0x14003e2f2  mov     dword ptr [rsi+48h], 0
0x14003e2f9  mov     r15, [rsp+0B8h+arg_8]
0x14003e301  mov     r13, [rsp+0B8h+var_58]
0x14003e306  mov     r14, [rsp+0B8h+var_60]
0x14003e30b  mov     rdi, [rsp+0B8h+var_50]
0x14003e310  jmp     loc_14003E0B1
0x14003e315  mov     rdi, r15
0x14003e318  mov     [rsp+0B8h+var_70], rdi
0x14003e31d  test    rdi, rdi
0x14003e320  jz      loc_14003E3B8
0x14003e326  mov     r8, r15
0x14003e329  mov     rdx, rdi
0x14003e32c  call    FatGetNextFcbTopDown
0x14003e331  mov     r12, rax
0x14003e334  mov     [rsp+0B8h+var_50], rax
0x14003e339  mov     eax, 502h
0x14003e33e  cmp     [rdi], ax
0x14003e341  jz      short loc_14003E3B0
0x14003e343  mov     ecx, [rdi+0C0h]
0x14003e349  test    cl, 1
0x14003e34c  jz      short loc_14003E357
0x14003e34e  cmp     dword ptr [rdi+0E4h], 0
0x14003e355  jz      short loc_14003E3B0
0x14003e357  mov     rdx, rdi
0x14003e35a  mov     rcx, rsi
0x14003e35d  call    FatVerifyFcb
0x14003e362  jmp     short loc_14003E38A
0x14003e364  mov     rsi, [rsp+0B8h+arg_0]
0x14003e36c  mov     dword ptr [rsi+48h], 0
0x14003e373  mov     r15, [rsp+0B8h+arg_8]
0x14003e37b  mov     rdi, [rsp+0B8h+var_70]
0x14003e380  mov     r12, [rsp+0B8h+var_50]
0x14003e385  mov     r14, [rsp+0B8h+var_60]
0x14003e38a  cmp     dword ptr [rdi+0C4h], 1
0x14003e391  jnz     short loc_14003E3B0
0x14003e393  mov     r8d, [rsp+0B8h+arg_10]
0x14003e39b  mov     rdx, rdi
0x14003e39e  call    FatFlushFile
0x14003e3a3  mov     ecx, [rsp+0B8h+var_84]
0x14003e3a7  test    eax, eax
0x14003e3a9  cmovs   ecx, eax
0x14003e3ac  mov     [rsp+0B8h+var_84], ecx
0x14003e3b0  mov     rdi, r12
0x14003e3b3  jmp     loc_14003E318
0x14003e3b8  mov     rcx, rsi
0x14003e3bb  call    FatUnpinRepinnedBcbs
0x14003e3c0  jmp     short loc_14003E3D6
0x14003e3c2  mov     rax, [rsp+0B8h+arg_0]
0x14003e3ca  mov     ecx, [rax+48h]
0x14003e3cd  mov     [rsp+0B8h+var_84], ecx
0x14003e3d1  mov     r14, [rsp+0B8h+var_60]
0x14003e3d6  cmp     [rsp+0B8h+arg_18], 0
0x14003e3de  jz      short loc_14003E3E4
0x14003e3e0  and     dword ptr [r14], 0FFFFFFFBh
0x14003e3e4  cmp     [rsp+0B8h+var_88], 0
0x14003e3e9  jz      short loc_14003E3EF
0x14003e3eb  and     dword ptr [r14], 0FFFFFFFDh
0x14003e3ef  mov     eax, [rsp+0B8h+var_84]
0x14003e3f3  add     rsp, 88h
0x14003e3fa  pop     r15
0x14003e3fc  pop     r14
0x14003e3fe  pop     r13
0x14003e400  pop     r12
0x14003e402  pop     rdi
0x14003e403  pop     rsi
0x14003e404  retn
0x14005eac5  push    rbp
0x14005eac7  sub     rsp, 30h
0x14005eacb  mov     rbp, rdx
0x14005eace  mov     rcx, [rcx]
0x14005ead1  mov     ecx, [rcx]; Exception
0x14005ead3  call    cs:__imp_FsRtlIsNtstatusExpected
0x14005eada  nop     dword ptr [rax+rax+00h]
0x14005eadf  xor     ecx, ecx
0x14005eae1  test    al, al
0x14005eae3  setnz   cl
0x14005eae6  mov     eax, ecx
0x14005eae8  add     rsp, 30h
0x14005eaec  pop     rbp
0x14005eaed  retn
0x14005eaef  push    rbp
0x14005eaf1  sub     rsp, 30h
0x14005eaf5  mov     rbp, rdx
0x14005eaf8  mov     rcx, [rbp+40h]; Bcb
0x14005eafc  test    rcx, rcx
0x14005eaff  jz      short loc_14005EB15
0x14005eb01  call    cs:__imp_CcUnpinData
0x14005eb08  nop     dword ptr [rax+rax+00h]
0x14005eb0d  mov     qword ptr [rbp+40h], 0
0x14005eb15  mov     rax, [rbp+60h]
0x14005eb19  mov     ecx, [rax+0C8h]
0x14005eb1f  bt      ecx, 8
0x14005eb23  jb      short loc_14005EB3A
0x14005eb25  mov     rcx, [rbp+48h]
0x14005eb29  mov     rcx, [rcx+8]; Resource
0x14005eb2d  call    cs:__imp_ExReleaseResourceLite
0x14005eb34  nop     dword ptr [rax+rax+00h]
0x14005eb39  nop
0x14005eb3a  add     rsp, 30h
0x14005eb3e  pop     rbp
0x14005eb3f  retn
0x14005eb41  push    rbp
0x14005eb43  sub     rsp, 30h
0x14005eb47  mov     rbp, rdx
0x14005eb4a  mov     rax, [rcx]
0x14005eb4d  mov     ecx, [rax]
0x14005eb4f  mov     [rbp+34h], ecx
0x14005eb52  mov     ecx, [rbp+34h]; Exception
0x14005eb55  call    cs:__imp_FsRtlIsNtstatusExpected
0x14005eb5c  nop     dword ptr [rax+rax+00h]
0x14005eb61  xor     ecx, ecx
0x14005eb63  test    al, al
0x14005eb65  setnz   cl
0x14005eb68  mov     eax, ecx
0x14005eb6a  add     rsp, 30h
0x14005eb6e  pop     rbp
0x14005eb6f  retn
0x14005eb71  push    rbp
0x14005eb73  sub     rsp, 30h
0x14005eb77  mov     rbp, rdx
0x14005eb7a  mov     rcx, [rcx]
0x14005eb7d  mov     ecx, [rcx]; Exception
0x14005eb7f  call    cs:__imp_FsRtlIsNtstatusExpected
0x14005eb86  nop     dword ptr [rax+rax+00h]
0x14005eb8b  xor     ecx, ecx
0x14005eb8d  test    al, al
0x14005eb8f  setnz   cl
0x14005eb92  mov     eax, ecx
0x14005eb94  add     rsp, 30h
0x14005eb98  pop     rbp
0x14005eb99  retn
0x14005eb9b  push    rbp
  ... truncated ...
```
