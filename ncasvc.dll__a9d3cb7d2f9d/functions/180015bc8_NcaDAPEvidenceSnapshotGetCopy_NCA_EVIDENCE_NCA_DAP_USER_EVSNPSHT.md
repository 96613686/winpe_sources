# NcaDAPEvidenceSnapshotGetCopy(NCA_EVIDENCE_ *,NCA_DAP_USER_EVSNPSHT_ *)

- ea: `0x180015bc8`
- end: `0x180015ce8`
- name: `?NcaDAPEvidenceSnapshotGetCopy@@YAXPEAUNCA_EVIDENCE_@@PEAUNCA_DAP_USER_EVSNPSHT_@@@Z`
- size: `288`
- prototype: `void __fastcall(struct NCA_EVIDENCE_ *, struct NCA_DAP_USER_EVSNPSHT_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015f20`

## callees

- `0x180004f04`
- `0x180015bc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015cab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015c09`

## pseudocode

```c
void __fastcall NcaDAPEvidenceSnapshotGetCopy(struct NCA_EVIDENCE_ *a1, struct NCA_DAP_USER_EVSNPSHT_ *a2)
{
  __int64 v4; // rcx
  _OWORD *v5; // rax
  __int128 v6; // xmm1

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_618387925699392817eae358b6323a44_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 64));
  v4 = 3;
  v5 = (_OWORD *)((char *)a2 + 112);
  do
  {
    *(_OWORD *)a1 = *v5;
    *((_OWORD *)a1 + 1) = v5[1];
    *((_OWORD *)a1 + 2) = v5[2];
    *((_OWORD *)a1 + 3) = v5[3];
    *((_OWORD *)a1 + 4) = v5[4];
    *((_OWORD *)a1 + 5) = v5[5];
    *((_OWORD *)a1 + 6) = v5[6];
    v6 = v5[7];
    v5 += 8;
    *((_OWORD *)a1 + 7) = v6;
    a1 = (struct NCA_EVIDENCE_ *)((char *)a1 + 128);
    --v4;
  }
  while ( v4 );
  *(_OWORD *)a1 = *v5;
  *((_OWORD *)a1 + 1) = v5[1];
  *((_OWORD *)a1 + 2) = v5[2];
  *((_OWORD *)a1 + 3) = v5[3];
  *((_OWORD *)a1 + 4) = v5[4];
  *((_OWORD *)a1 + 5) = v5[5];
  *((_OWORD *)a1 + 6) = v5[6];
  *((_DWORD *)a1 + 28) = *((_DWORD *)v5 + 28);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 64));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_618387925699392817eae358b6323a44_Traceguids);
}

```

## disassembly

```asm
0x180015bc8  push    rbx
0x180015bca  push    rbp
0x180015bcb  push    rsi
0x180015bcc  push    rdi
0x180015bcd  sub     rsp, 28h
0x180015bd1  mov     rdi, rdx
0x180015bd4  mov     rbx, rcx
0x180015bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bde  lea     rbp, WPP_GLOBAL_Control
0x180015be5  cmp     rcx, rbp
0x180015be8  jz      short loc_180015C05
0x180015bea  test    byte ptr [rcx+1Ch], 8
0x180015bee  jz      short loc_180015C05
0x180015bf0  mov     rcx, [rcx+10h]
0x180015bf4  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x180015bfb  mov     edx, 23h ; '#'
0x180015c00  call    WPP_SF_
0x180015c05  lea     rcx, [rdi+40h]; lpCriticalSection
0x180015c09  call    cs:__imp_EnterCriticalSection
0x180015c10  nop     dword ptr [rax+rax+00h]
0x180015c15  mov     ecx, 3
0x180015c1a  lea     rax, [rdi+70h]
0x180015c1e  lea     edx, [rcx+7Dh]
0x180015c21  movups  xmm0, xmmword ptr [rax]
0x180015c24  movups  xmmword ptr [rbx], xmm0
0x180015c27  movups  xmm1, xmmword ptr [rax+10h]
0x180015c2b  movups  xmmword ptr [rbx+10h], xmm1
0x180015c2f  movups  xmm0, xmmword ptr [rax+20h]
0x180015c33  movups  xmmword ptr [rbx+20h], xmm0
0x180015c37  movups  xmm1, xmmword ptr [rax+30h]
0x180015c3b  movups  xmmword ptr [rbx+30h], xmm1
0x180015c3f  movups  xmm0, xmmword ptr [rax+40h]
0x180015c43  movups  xmmword ptr [rbx+40h], xmm0
0x180015c47  movups  xmm1, xmmword ptr [rax+50h]
0x180015c4b  movups  xmmword ptr [rbx+50h], xmm1
0x180015c4f  movups  xmm0, xmmword ptr [rax+60h]
0x180015c53  movups  xmmword ptr [rbx+60h], xmm0
0x180015c57  movups  xmm1, xmmword ptr [rax+70h]
0x180015c5b  add     rax, rdx
0x180015c5e  movups  xmmword ptr [rbx+70h], xmm1
0x180015c62  add     rbx, rdx
0x180015c65  sub     rcx, 1
0x180015c69  jnz     short loc_180015C21
0x180015c6b  movups  xmm0, xmmword ptr [rax]
0x180015c6e  lea     rcx, [rdi+40h]; lpCriticalSection
0x180015c72  movups  xmmword ptr [rbx], xmm0
0x180015c75  movups  xmm1, xmmword ptr [rax+10h]
0x180015c79  movups  xmmword ptr [rbx+10h], xmm1
0x180015c7d  movups  xmm0, xmmword ptr [rax+20h]
0x180015c81  movups  xmmword ptr [rbx+20h], xmm0
0x180015c85  movups  xmm1, xmmword ptr [rax+30h]
0x180015c89  movups  xmmword ptr [rbx+30h], xmm1
0x180015c8d  movups  xmm0, xmmword ptr [rax+40h]
0x180015c91  movups  xmmword ptr [rbx+40h], xmm0
0x180015c95  movups  xmm1, xmmword ptr [rax+50h]
0x180015c99  movups  xmmword ptr [rbx+50h], xmm1
0x180015c9d  movups  xmm0, xmmword ptr [rax+60h]
0x180015ca1  movups  xmmword ptr [rbx+60h], xmm0
0x180015ca5  mov     eax, [rax+70h]
0x180015ca8  mov     [rbx+70h], eax
0x180015cab  call    cs:__imp_LeaveCriticalSection
0x180015cb2  nop     dword ptr [rax+rax+00h]
0x180015cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cbe  cmp     rcx, rbp
0x180015cc1  jz      short loc_180015CDE
0x180015cc3  test    byte ptr [rcx+1Ch], 8
0x180015cc7  jz      short loc_180015CDE
0x180015cc9  mov     rcx, [rcx+10h]
0x180015ccd  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x180015cd4  mov     edx, 24h ; '$'
0x180015cd9  call    WPP_SF_
0x180015cde  add     rsp, 28h
0x180015ce2  pop     rdi
0x180015ce3  pop     rsi
0x180015ce4  pop     rbp
0x180015ce5  pop     rbx
0x180015ce6  retn
```
