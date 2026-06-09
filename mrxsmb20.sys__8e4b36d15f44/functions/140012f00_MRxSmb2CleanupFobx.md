# MRxSmb2CleanupFobx

- ea: `0x140012f00`
- end: `0x1400131fd`
- name: `MRxSmb2CleanupFobx`
- size: `765`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140004d30`
- `0x140012f00`
- `0x140013210`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140013080`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140013080`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140013002`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140013002`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140013011`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140013011`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012fdf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140012fdf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012fb9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140012fb9`
- `mrxsmb!SmbCeResumeSuspendedExchangesLite` at `0x14001305f`
- `mrxsmb!SmbCeResumeSuspendedExchangesLite` at `0x14001305f`

## pseudocode

```c
__int64 __fastcall MRxSmb2CleanupFobx(_QWORD *a1)
{
  unsigned __int16 *v1; // rdi
  __int64 v2; // rsi
  __int64 v3; // rax
  __int64 v4; // rbp
  __int64 v5; // rbx
  __int64 v6; // rbx
  char *v7; // rcx
  int v8; // r8d
  __int64 v10; // rax
  __int64 v11; // r15
  __int64 *v12; // rcx
  unsigned int v13; // esi
  KIRQL v14; // bl
  int v15; // eax
  unsigned __int16 *v16; // rdx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rcx
  unsigned __int16 *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 **v22; // rdx
  __int64 **v23; // rdx
  _OWORD v24[4]; // [rsp+30h] [rbp-48h] BYREF

  v1 = (unsigned __int16 *)a1[7];
  v2 = a1[9];
  v3 = *((_QWORD *)v1 + 15);
  v4 = *(_QWORD *)(v2 + 48);
  if ( !*(_BYTE *)(v3 + 77) )
  {
    if ( *v1 == 60449 )
    {
      v5 = a1[8];
      if ( v5 )
      {
        v6 = *(_QWORD *)(v5 + 56);
        if ( v6 )
        {
          v7 = *(char **)(v6 + 16);
          if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          {
            Smb2DereferenceDirCacheObject(v7);
            *(_QWORD *)(v6 + 16) = -1;
          }
        }
      }
      v8 = *(_DWORD *)(v2 + 72);
      if ( (v8 & 0x200) == 0 )
      {
        v15 = *((_DWORD *)v1 + 41);
        if ( ((v15 & 0x10) != 0 || (v15 & 0x20) != 0) && (*(_DWORD *)(v4 + 8) & 0x20) == 0 )
        {
          v16 = v1 + 132;
          v17 = v1 + 132;
          do
          {
            v17 = *(unsigned __int16 **)v17;
            if ( v17 == v16 )
              goto LABEL_34;
            v18 = v17 - 68;
          }
          while ( *(v17 - 68) == 0xEBAA );
LABEL_22:
          while ( v18 )
          {
            if ( v18 != (unsigned __int16 *)v2
              && (*((_DWORD *)v18 + 18) & 8) != 0
              && *(_QWORD *)(*((_QWORD *)v18 + 5) + 40LL) == *(_QWORD *)(*(_QWORD *)(v2 + 40) + 40LL) )
            {
              goto LABEL_30;
            }
            v19 = v18 + 68;
            while ( 1 )
            {
              v19 = *(unsigned __int16 **)v19;
              if ( v19 == v16 )
                break;
              v18 = v19 - 68;
              if ( *(v19 - 68) != 0xEBAA )
                goto LABEL_22;
            }
LABEL_34:
            v18 = 0;
          }
        }
        else
        {
LABEL_30:
          *(_DWORD *)(v2 + 72) = v8 | 0x1000;
        }
      }
      return 0;
    }
    if ( *v1 == 60450 )
    {
      v10 = *(_QWORD *)(v2 + 40);
      v24[0] = 0;
      v11 = *(_QWORD *)(*(_QWORD *)(v10 + 40) + 24LL);
      *((_QWORD *)&v24[0] + 1) = v24;
      *(_QWORD *)&v24[0] = v24;
      ExAcquirePushLockExclusiveEx(v4 + 16, 0);
      v12 = *(__int64 **)(v4 + 56);
      if ( v12 != (__int64 *)(v4 + 56) )
      {
        do
        {
          v20 = *(v12 - 10);
          v21 = *v12;
          if ( v20 && *(_QWORD *)(v20 + 40) && *(_BYTE *)(v20 + 32) == 13 && *(_DWORD *)(v20 + 540) == 1311180 )
          {
            if ( *(__int64 **)(v21 + 8) != v12
              || (v22 = (__int64 **)v12[1], *v22 != v12)
              || (*v22 = (__int64 *)v21,
                  *(_QWORD *)(v21 + 8) = v22,
                  v23 = (__int64 **)*((_QWORD *)&v24[0] + 1),
                  **((_OWORD ***)&v24[0] + 1) != v24) )
            {
              __fastfail(3u);
            }
            v12[1] = *((_QWORD *)&v24[0] + 1);
            *v12 = (__int64)v24;
            *v23 = v12;
            *((_QWORD *)&v24[0] + 1) = v12;
          }
          v12 = (__int64 *)v21;
        }
        while ( v21 != v4 + 56 );
      }
      v13 = *(_DWORD *)(v4 + 44);
      ExReleasePushLockExclusiveEx(v4 + 16, 0);
      if ( *(_OWORD **)&v24[0] != v24 )
      {
        v14 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920));
        *(_DWORD *)(v11 + 2352) = (unsigned int)PsGetCurrentThreadId();
        SmbCeResumeSuspendedExchangesLite(v24, 1, 3, v13, 0x13C0000128LL, 0);
        *(_DWORD *)(v11 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920), v14);
        return 0;
      }
    }
    return 0;
  }
  if ( *(_BYTE *)(v3 + 77) != 1 || (*(_DWORD *)(v4 + 8) & 1) != 0 )
    return 0;
  return MRxSmb2Close((__int64)a1);
}

```

## disassembly

```asm
0x140012f00  push    rbx
0x140012f02  push    rbp
0x140012f03  push    rsi
0x140012f04  push    rdi
0x140012f05  push    r14
0x140012f07  push    r15
0x140012f09  sub     rsp, 48h
0x140012f0d  mov     rdi, [rcx+38h]
0x140012f11  mov     rdx, rcx
0x140012f14  mov     rsi, [rcx+48h]
0x140012f18  xor     r14d, r14d
0x140012f1b  mov     rax, [rdi+78h]
0x140012f1f  mov     rbp, [rsi+30h]
0x140012f23  movzx   ecx, byte ptr [rax+4Dh]
0x140012f27  test    ecx, ecx
0x140012f29  jnz     loc_14001309D
0x140012f2f  movzx   ecx, word ptr [rdi]
0x140012f32  sub     ecx, 0EC21h
0x140012f38  jnz     short loc_140012F7E
0x140012f3a  mov     rbx, [rdx+40h]
0x140012f3e  test    rbx, rbx
0x140012f41  jz      short loc_140012F5E
0x140012f43  mov     rbx, [rbx+38h]
0x140012f47  test    rbx, rbx
0x140012f4a  jz      short loc_140012F5E
0x140012f4c  mov     rcx, [rbx+10h]; P
0x140012f50  lea     rax, [rcx-1]
0x140012f54  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140012f58  jbe     loc_140013147
0x140012f5e  mov     r8d, [rsi+48h]
0x140012f62  bt      r8d, 9
0x140012f67  jnb     loc_1400130C7
0x140012f6d  mov     eax, r14d
0x140012f70  add     rsp, 48h
0x140012f74  pop     r15
0x140012f76  pop     r14
0x140012f78  pop     rdi
0x140012f79  pop     rsi
0x140012f7a  pop     rbp
0x140012f7b  pop     rbx
0x140012f7c  retn
0x140012f7e  cmp     ecx, 1
0x140012f81  jnz     short loc_140012F6D
0x140012f83  mov     rax, [rsi+28h]
0x140012f87  xorps   xmm0, xmm0
0x140012f8a  movups  [rsp+78h+var_48], xmm0
0x140012f8f  xor     edx, edx
0x140012f91  mov     [rsp+78h+arg_0], r14
0x140012f99  mov     rcx, [rax+28h]
0x140012f9d  lea     rax, [rsp+78h+var_48]
0x140012fa2  mov     r15, [rcx+18h]
0x140012fa6  lea     rcx, [rbp+10h]
0x140012faa  mov     qword ptr [rsp+78h+var_48+8], rax
0x140012faf  lea     rax, [rsp+78h+var_48]
0x140012fb4  mov     qword ptr [rsp+78h+var_48], rax
0x140012fb9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140012fc0  nop     dword ptr [rax+rax+00h]
0x140012fc5  mov     rcx, [rbp+38h]
0x140012fc9  lea     rax, [rbp+38h]
0x140012fcd  cmp     rcx, rax
0x140012fd0  jnz     loc_140013180
0x140012fd6  mov     esi, [rbp+2Ch]
0x140012fd9  lea     rcx, [rbp+10h]
0x140012fdd  xor     edx, edx
0x140012fdf  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140012fe6  nop     dword ptr [rax+rax+00h]
0x140012feb  lea     rax, [rsp+78h+var_48]
0x140012ff0  cmp     qword ptr [rsp+78h+var_48], rax
0x140012ff5  jz      loc_140012F6D
0x140012ffb  lea     rcx, [r15+780h]; SpinLock
0x140013002  call    cs:__imp_ExAcquireSpinLockExclusive
0x140013009  nop     dword ptr [rax+rax+00h]
0x14001300e  movzx   ebx, al
0x140013011  call    cs:__imp_PsGetCurrentThreadId
0x140013018  nop     dword ptr [rax+rax+00h]
0x14001301d  mov     dword ptr [rsp+78h+arg_0], 0C0000128h
0x140013028  lea     rcx, [rsp+78h+var_48]
0x14001302d  mov     dword ptr [rsp+78h+arg_0+4], 13h
0x140013038  mov     r9d, esi
0x14001303b  mov     rdx, [rsp+78h+arg_0]
0x140013043  mov     r8d, 3
0x140013049  mov     [rsp+78h+var_50], r14
0x14001304e  mov     [rsp+78h+var_58], rdx
0x140013053  mov     edx, 1
0x140013058  mov     [r15+930h], eax
0x14001305f  call    cs:__imp_SmbCeResumeSuspendedExchangesLite
0x140013066  nop     dword ptr [rax+rax+00h]
0x14001306b  movzx   edx, bl; OldIrql
0x14001306e  mov     dword ptr [r15+930h], 0FFFFFFFFh
0x140013079  lea     rcx, [r15+780h]; SpinLock
0x140013080  call    cs:__imp_ExReleaseSpinLockExclusive
0x140013087  nop     dword ptr [rax+rax+00h]
0x14001308c  mov     eax, r14d
0x14001308f  add     rsp, 48h
0x140013093  pop     r15
0x140013095  pop     r14
0x140013097  pop     rdi
0x140013098  pop     rsi
0x140013099  pop     rbp
0x14001309a  pop     rbx
0x14001309b  retn
0x14001309d  cmp     ecx, 1
0x1400130a0  jnz     loc_140012F6D
0x1400130a6  mov     eax, [rbp+8]
0x1400130a9  test    cl, al
0x1400130ab  jnz     loc_140012F6D
0x1400130b1  mov     rcx, rdx
0x1400130b4  call    MRxSmb2Close
0x1400130b9  add     rsp, 48h
0x1400130bd  pop     r15
0x1400130bf  pop     r14
0x1400130c1  pop     rdi
0x1400130c2  pop     rsi
0x1400130c3  pop     rbp
0x1400130c4  pop     rbx
0x1400130c5  retn
0x1400130c7  mov     eax, [rdi+0A4h]
0x1400130cd  test    al, 10h
0x1400130cf  jnz     short loc_1400130D9
0x1400130d1  test    al, 20h
0x1400130d3  jz      loc_14001316A
0x1400130d9  mov     eax, [rbp+8]
0x1400130dc  test    al, 20h
0x1400130de  jnz     loc_14001316A
0x1400130e4  mov     rax, [rsi+28h]
0x1400130e8  lea     rdx, [rdi+108h]
0x1400130ef  mov     r10d, 0EBAAh
0x1400130f5  mov     r9, [rax+28h]
0x1400130f9  mov     rax, rdx
0x1400130fc  nop     dword ptr [rax+00h]
0x140013100  mov     rax, [rax]
0x140013103  cmp     rax, rdx
0x140013106  jz      loc_14001319A
0x14001310c  lea     rcx, [rax-88h]
0x140013113  cmp     [rcx], r10w
0x140013117  jz      short loc_140013100
0x140013119  test    rcx, rcx
0x14001311c  jz      loc_140012F6D
0x140013122  cmp     rcx, rsi
0x140013125  jnz     short loc_140013159
0x140013127  lea     rax, [rcx+88h]
0x14001312e  xchg    ax, ax
0x140013130  mov     rax, [rax]
0x140013133  cmp     rax, rdx
0x140013136  jz      short loc_14001319A
0x140013138  lea     rcx, [rax-88h]
0x14001313f  cmp     [rcx], r10w
0x140013143  jz      short loc_140013130
0x140013145  jmp     short loc_140013119
0x140013147  call    Smb2DereferenceDirCacheObject
0x14001314c  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x140013154  jmp     loc_140012F5E
0x140013159  mov     eax, [rcx+48h]
0x14001315c  test    al, 8
0x14001315e  jz      short loc_140013127
0x140013160  mov     rax, [rcx+28h]
0x140013164  cmp     [rax+28h], r9
0x140013168  jnz     short loc_140013127
0x14001316a  bts     r8d, 0Ch
0x14001316f  mov     [rsi+48h], r8d
0x140013173  jmp     loc_140012F6D
0x140013180  mov     rdx, [rcx-50h]
0x140013184  mov     r8, [rcx]
0x140013187  test    rdx, rdx
0x14001318a  jnz     short loc_1400131B7
0x14001318c  mov     rcx, r8
0x14001318f  cmp     r8, rax
0x140013192  jz      loc_140012FD6
0x140013198  jmp     short loc_140013180
0x14001319a  xor     ecx, ecx
0x14001319c  jmp     loc_140013119
0x1400131a1  cmp     [r8+8], rcx
0x1400131a5  jnz     short loc_1400131B0
0x1400131a7  mov     rdx, [rcx+8]
0x1400131ab  cmp     [rdx], rcx
0x1400131ae  jz      short loc_1400131D1
0x1400131b0  mov     ecx, 3
0x1400131b5  int     29h; Win8: RtlFailFast(ecx)
0x1400131b7  cmp     [rdx+28h], r14
0x1400131bb  jz      short loc_14001318C
0x1400131bd  cmp     byte ptr [rdx+20h], 0Dh
0x1400131c1  jnz     short loc_14001318C
0x1400131c3  cmp     dword ptr [rdx+21Ch], 1401CCh
0x1400131cd  jnz     short loc_14001318C
0x1400131cf  jmp     short loc_1400131A1
0x1400131d1  mov     [rdx], r8
0x1400131d4  lea     r9, [rsp+78h+var_48]
0x1400131d9  mov     [r8+8], rdx
0x1400131dd  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x1400131e2  cmp     [rdx], r9
0x1400131e5  jnz     short loc_1400131B0
0x1400131e7  mov     [rcx+8], rdx
0x1400131eb  lea     r9, [rsp+78h+var_48]
0x1400131f0  mov     [rcx], r9
0x1400131f3  mov     [rdx], rcx
0x1400131f6  mov     qword ptr [rsp+78h+var_48+8], rcx
0x1400131fb  jmp     short loc_14001318C
```
