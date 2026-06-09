# NcaEvCollProbesUpdateEvidenceSummary(NCA_PROBE_TEST_TYPE_,int,ulong,NCA_EVCOLL_USER_PROBES_ *)

- ea: `0x180001c70`
- end: `0x180001e87`
- name: `?NcaEvCollProbesUpdateEvidenceSummary@@YAXW4NCA_PROBE_TEST_TYPE_@@HKPEAUNCA_EVCOLL_USER_PROBES_@@@Z`
- size: `535`
- prototype: `void __fastcall(int, int, unsigned int, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180001400`
- `0x180001ee0`
- `0x180003720`
- `0x180011f80`

## callees

- `0x180001c70`
- `0x180016678`
- `0x180016798`

## pseudocode

```c
void __fastcall NcaEvCollProbesUpdateEvidenceSummary(int a1, int a2, unsigned int a3, __int64 a4)
{
  unsigned int v5; // r9d
  unsigned int v6; // ebp
  int v9; // r14d
  unsigned int v10; // esi
  unsigned int v11; // r15d
  unsigned int v12; // edi
  unsigned int v13; // r11d
  __int64 v14; // r13
  __int64 v15; // rcx
  int v16; // r8d
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v21; // eax

  v5 = *(_DWORD *)(a4 + 16);
  v6 = 1;
  v9 = 0;
  v10 = 1;
  v11 = 1;
  v12 = 1;
  if ( v5 )
  {
    v13 = 0;
    v14 = *(_QWORD *)(a4 + 24);
    do
    {
      v15 = 392LL * v13;
      v16 = *(_DWORD *)(v15 + v14);
      if ( !v16 || *(_DWORD *)(v15 + v14 + 16) == 2 )
        goto LABEL_30;
      v17 = *(_DWORD *)(v15 + v14 + 224);
      if ( v17 )
      {
        if ( v17 == 1 )
        {
          v18 = *(_DWORD *)(v15 + v14 + 24);
          if ( !v18 )
          {
            v11 = 0;
            if ( v16 != 4 )
            {
              LOBYTE(v18) = v6 != 0;
              v6 = v18;
            }
            v20 = 0;
            if ( v16 != 2 )
              v20 = v10;
            v10 = v20;
            goto LABEL_30;
          }
LABEL_19:
          if ( v18 == 1 )
            v12 = 0;
          goto LABEL_30;
        }
        if ( v17 == 2 )
        {
          v21 = *(_DWORD *)(v15 + v14 + 24);
          if ( v21 )
          {
            if ( v21 == 1 )
              v12 = v12 != 0;
            goto LABEL_30;
          }
          v11 = v11 != 0;
          if ( v16 == 4 )
          {
LABEL_27:
            v9 = 1;
            goto LABEL_30;
          }
          v6 = v6 != 0;
          if ( v16 == 2 )
          {
            v10 = v10 != 0;
          }
          else if ( (unsigned int)(v16 - 3) <= 1 )
          {
            goto LABEL_27;
          }
        }
      }
      else
      {
        v18 = *(_DWORD *)(v15 + v14 + 24);
        if ( v18 )
          goto LABEL_19;
        v11 = 0;
        if ( v16 == 4 )
          v18 = v6;
        v6 = v18;
        v19 = 0;
        if ( v16 != 2 )
          v19 = v10;
        v10 = v19;
      }
LABEL_30:
      ++v13;
    }
    while ( v13 < v5 );
  }
  if ( *(_DWORD *)(a4 + 36) != v11 )
  {
    NcaDAPEvidenceSnapshotSetUserState(1, v11, a3);
    *(_DWORD *)(a4 + 36) = v11;
    if ( v11 != 1 )
      goto LABEL_38;
    goto LABEL_37;
  }
  if ( a2 == 1 && a1 == 2 && v11 == 1 )
  {
    *(_DWORD *)(a4 + 36) = 1;
LABEL_37:
    NcaDAPEvidenceSnapshotSetUserState(5, 0, a3);
    NcaDAPEvidenceSnapshotSetGlobalState(6, 0);
  }
LABEL_38:
  if ( v9 == 1 )
  {
    NcaDAPEvidenceSnapshotSetUserState(5, 0, a3);
    NcaDAPEvidenceSnapshotSetGlobalState(6, 0);
  }
  if ( *(_DWORD *)(a4 + 40) != v6 )
  {
    *(_DWORD *)(a4 + 40) = v6;
    NcaDAPEvidenceSnapshotSetUserState(9, v6, a3);
  }
  if ( *(_DWORD *)(a4 + 44) != v10 )
  {
    *(_DWORD *)(a4 + 44) = v10;
    NcaDAPEvidenceSnapshotSetUserState(2, v10, a3);
  }
  if ( *(_DWORD *)(a4 + 48) != v12 )
  {
    *(_DWORD *)(a4 + 48) = v12;
    NcaDAPEvidenceSnapshotSetUserState(18, v12, a3);
  }
}

```

## disassembly

```asm
0x180001c70  push    rbx
0x180001c72  push    rdi
0x180001c73  push    r12
0x180001c75  sub     rsp, 30h
0x180001c79  mov     [rsp+48h+arg_0], rbp
0x180001c7e  mov     rbx, r9
0x180001c81  mov     r9d, [r9+10h]
0x180001c85  mov     ebp, 1
0x180001c8a  mov     [rsp+48h+arg_8], rsi
0x180001c8f  mov     r12d, r8d
0x180001c92  mov     [rsp+48h+var_20], r14
0x180001c97  mov     r10d, ecx
0x180001c9a  xor     r14d, r14d
0x180001c9d  mov     [rsp+48h+var_28], r15
0x180001ca2  mov     esi, ebp
0x180001ca4  mov     r15d, ebp
0x180001ca7  mov     edi, ebp
0x180001ca9  test    r9d, r9d
0x180001cac  jz      loc_180001DB2
0x180001cb2  mov     [rsp+48h+arg_10], r13
0x180001cb7  xor     r11d, r11d
0x180001cba  mov     r13, [rbx+18h]
0x180001cbe  mov     eax, r11d
0x180001cc1  imul    rcx, rax, 188h
0x180001cc8  mov     r8d, [rcx+r13]
0x180001ccc  test    r8d, r8d
0x180001ccf  jz      loc_180001DA1
0x180001cd5  cmp     dword ptr [rcx+r13+10h], 2
0x180001cdb  jz      loc_180001DA1
0x180001ce1  mov     eax, [rcx+r13+0E0h]
0x180001ce9  test    eax, eax
0x180001ceb  jnz     short loc_180001D12
0x180001ced  mov     eax, [rcx+r13+18h]
0x180001cf2  test    eax, eax
0x180001cf4  jnz     short loc_180001D3D
0x180001cf6  xor     r15d, r15d
0x180001cf9  cmp     r8d, 4
0x180001cfd  cmovz   eax, ebp
0x180001d00  mov     ebp, eax
0x180001d02  xor     eax, eax
0x180001d04  cmp     r8d, 2
0x180001d08  cmovnz  eax, esi
0x180001d0b  mov     esi, eax
0x180001d0d  jmp     loc_180001DA1
0x180001d12  cmp     eax, 1
0x180001d15  jnz     short loc_180001D46
0x180001d17  mov     eax, [rcx+r13+18h]
0x180001d1c  test    eax, eax
0x180001d1e  jnz     short loc_180001D3D
0x180001d20  xor     r15d, r15d
0x180001d23  cmp     r8d, 4
0x180001d27  jz      short loc_180001D30
0x180001d29  test    ebp, ebp
0x180001d2b  setnz   al
0x180001d2e  mov     ebp, eax
0x180001d30  xor     eax, eax
0x180001d32  cmp     r8d, 2
0x180001d36  cmovnz  eax, esi
0x180001d39  mov     esi, eax
0x180001d3b  jmp     short loc_180001DA1
0x180001d3d  cmp     eax, 1
0x180001d40  jnz     short loc_180001DA1
0x180001d42  xor     edi, edi
0x180001d44  jmp     short loc_180001DA1
0x180001d46  cmp     eax, 2
0x180001d49  jnz     short loc_180001DA1
0x180001d4b  mov     eax, [rcx+r13+18h]
0x180001d50  test    eax, eax
0x180001d52  jnz     short loc_180001D93
0x180001d54  test    r15d, r15d
0x180001d57  mov     ecx, ebp
0x180001d59  setnz   al
0x180001d5c  mov     r15d, eax
0x180001d5f  cmp     r8d, 4
0x180001d63  jz      short loc_180001D8B
0x180001d65  xor     ebp, ebp
0x180001d67  test    ecx, ecx
0x180001d69  setnz   bpl
0x180001d6d  cmp     r8d, 2
0x180001d71  jnz     short loc_180001D82
0x180001d73  test    esi, esi
0x180001d75  jz      short loc_180001D7E
0x180001d77  mov     esi, 1
0x180001d7c  jmp     short loc_180001DA1
0x180001d7e  xor     esi, esi
0x180001d80  jmp     short loc_180001DA1
0x180001d82  lea     eax, [r8-3]
0x180001d86  cmp     eax, 1
0x180001d89  ja      short loc_180001DA1
0x180001d8b  mov     r14d, 1
0x180001d91  jmp     short loc_180001DA1
0x180001d93  cmp     eax, 1
0x180001d96  jnz     short loc_180001DA1
0x180001d98  xor     eax, eax
0x180001d9a  test    edi, edi
0x180001d9c  setnz   al
0x180001d9f  mov     edi, eax
0x180001da1  inc     r11d
0x180001da4  cmp     r11d, r9d
0x180001da7  jb      loc_180001CBE
0x180001dad  mov     r13, [rsp+48h+arg_10]
0x180001db2  cmp     [rbx+24h], r15d
0x180001db6  jnz     short loc_180001DCE
0x180001db8  cmp     edx, 1
0x180001dbb  jnz     short loc_180001E03
0x180001dbd  cmp     r10d, 2
0x180001dc1  jnz     short loc_180001E03
0x180001dc3  cmp     r15d, edx
0x180001dc6  jnz     short loc_180001E03
0x180001dc8  mov     [rbx+24h], r15d
0x180001dcc  jmp     short loc_180001DE8
0x180001dce  mov     r8d, r12d
0x180001dd1  mov     edx, r15d
0x180001dd4  mov     ecx, 1
0x180001dd9  call    NcaDAPEvidenceSnapshotSetUserState
0x180001dde  mov     [rbx+24h], r15d
0x180001de2  cmp     r15d, 1
0x180001de6  jnz     short loc_180001E03
0x180001de8  mov     r8d, r12d
0x180001deb  xor     edx, edx
0x180001ded  mov     ecx, 5
0x180001df2  call    NcaDAPEvidenceSnapshotSetUserState
0x180001df7  xor     edx, edx
0x180001df9  mov     ecx, 6
0x180001dfe  call    NcaDAPEvidenceSnapshotSetGlobalState
0x180001e03  mov     r15, [rsp+48h+var_28]
0x180001e08  cmp     r14d, 1
0x180001e0c  mov     r14, [rsp+48h+var_20]
0x180001e11  jnz     short loc_180001E2E
0x180001e13  mov     r8d, r12d
0x180001e16  xor     edx, edx
0x180001e18  mov     ecx, 5
0x180001e1d  call    NcaDAPEvidenceSnapshotSetUserState
0x180001e22  xor     edx, edx
0x180001e24  mov     ecx, 6
0x180001e29  call    NcaDAPEvidenceSnapshotSetGlobalState
0x180001e2e  cmp     [rbx+28h], ebp
0x180001e31  jz      short loc_180001E45
0x180001e33  mov     r8d, r12d
0x180001e36  mov     [rbx+28h], ebp
0x180001e39  mov     edx, ebp
0x180001e3b  mov     ecx, 9
0x180001e40  call    NcaDAPEvidenceSnapshotSetUserState
0x180001e45  mov     rbp, [rsp+48h+arg_0]
0x180001e4a  cmp     [rbx+2Ch], esi
0x180001e4d  jz      short loc_180001E61
0x180001e4f  mov     r8d, r12d
0x180001e52  mov     [rbx+2Ch], esi
0x180001e55  mov     edx, esi
0x180001e57  mov     ecx, 2
0x180001e5c  call    NcaDAPEvidenceSnapshotSetUserState
0x180001e61  mov     rsi, [rsp+48h+arg_8]
0x180001e66  cmp     [rbx+30h], edi
0x180001e69  jz      short loc_180001E7D
0x180001e6b  mov     r8d, r12d
0x180001e6e  mov     [rbx+30h], edi
0x180001e71  mov     edx, edi
0x180001e73  mov     ecx, 12h
0x180001e78  call    NcaDAPEvidenceSnapshotSetUserState
0x180001e7d  add     rsp, 30h
0x180001e81  pop     r12
0x180001e83  pop     rdi
0x180001e84  pop     rbx
0x180001e85  retn
```
