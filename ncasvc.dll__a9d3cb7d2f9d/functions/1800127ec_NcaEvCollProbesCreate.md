# NcaEvCollProbesCreate

- ea: `0x1800127ec`
- end: `0x18001293d`
- name: `NcaEvCollProbesCreate`
- size: `337`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180017bc8`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180004f34`
- `0x180011d54`
- `0x180011f10`
- `0x1800127ec`
- `0x18001abd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012832`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012832`

## pseudocode

```c
__int64 __fastcall NcaEvCollProbesCreate(unsigned int a1)
{
  struct NCA_EVCOLL_USER_PROBES_ *v2; // rax
  __int64 v3; // rbx
  unsigned int v4; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  unsigned int v8; // eax
  __int64 *v9; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids);
  EnterCriticalSection(&CriticalSection);
  v2 = (struct NCA_EVCOLL_USER_PROBES_ *)NcaAlloc(0x38u);
  v3 = (__int64)v2;
  if ( v2 )
  {
    v8 = NcaEvCollProbesInnerCreate(v2, a1);
    v4 = v8;
    if ( v8 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 49;
        v7 = v8;
        goto LABEL_8;
      }
    }
    else
    {
      v9 = (__int64 *)qword_180029088;
      if ( *(struct NCA_EVCOLL_USER_PROBES_ ***)qword_180029088 != &gNcaEvCollProbes )
        __fastfail(3u);
      *(_QWORD *)v3 = &gNcaEvCollProbes;
      *(_QWORD *)(v3 + 8) = v9;
      *v9 = v3;
      qword_180029088 = v3;
    }
  }
  else
  {
    v4 = 14;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 48;
      v7 = 14;
LABEL_8:
      WPP_SF_d(v5[2], v6, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, v7);
    }
  }
  LeaveCriticalSection(&CriticalSection);
  if ( v4 && v3 )
  {
    NcaEvCollProbesInnerDelete((struct NCA_EVCOLL_USER_PROBES_ *)v3);
    NcaFree((LPVOID)v3);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x1800127ec  mov     [rsp+arg_0], rbx
0x1800127f1  mov     [rsp+arg_8], rsi
0x1800127f6  push    rdi
0x1800127f7  sub     rsp, 20h
0x1800127fb  mov     edi, ecx
0x1800127fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012804  lea     rsi, WPP_GLOBAL_Control
0x18001280b  cmp     rcx, rsi
0x18001280e  jz      short loc_18001282B
0x180012810  test    byte ptr [rcx+1Ch], 8
0x180012814  jz      short loc_18001282B
0x180012816  mov     rcx, [rcx+10h]
0x18001281a  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180012821  mov     edx, 2Fh ; '/'
0x180012826  call    WPP_SF_
0x18001282b  lea     rcx, CriticalSection; lpCriticalSection
0x180012832  call    cs:__imp_EnterCriticalSection
0x180012839  nop     dword ptr [rax+rax+00h]
0x18001283e  mov     ecx, 38h ; '8'
0x180012843  call    NcaAlloc
0x180012848  mov     rbx, rax
0x18001284b  test    rax, rax
0x18001284e  jnz     short loc_18001287D
0x180012850  lea     edi, [rax+0Eh]
0x180012853  mov     rcx, cs:WPP_GLOBAL_Control
0x18001285a  cmp     rcx, rsi
0x18001285d  jz      short loc_1800128D4
0x18001285f  test    byte ptr [rcx+1Ch], 1
0x180012863  jz      short loc_1800128D4
0x180012865  lea     edx, [rax+30h]
0x180012868  mov     r9d, edi
0x18001286b  mov     rcx, [rcx+10h]
0x18001286f  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x180012876  call    WPP_SF_d
0x18001287b  jmp     short loc_1800128D4
0x18001287d  mov     edx, edi; unsigned int
0x18001287f  mov     rcx, rbx; struct NCA_EVCOLL_USER_PROBES_ *
0x180012882  call    ?NcaEvCollProbesInnerCreate@@YAKPEAUNCA_EVCOLL_USER_PROBES_@@K@Z; NcaEvCollProbesInnerCreate(NCA_EVCOLL_USER_PROBES_ *,ulong)
0x180012887  mov     edi, eax
0x180012889  test    eax, eax
0x18001288b  jz      short loc_1800128A9
0x18001288d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012894  cmp     rcx, rsi
0x180012897  jz      short loc_1800128D4
0x180012899  test    byte ptr [rcx+1Ch], 1
0x18001289d  jz      short loc_1800128D4
0x18001289f  mov     edx, 31h ; '1'
0x1800128a4  mov     r9d, eax
0x1800128a7  jmp     short loc_18001286B
0x1800128a9  mov     rax, cs:qword_180029088
0x1800128b0  lea     rcx, ?gNcaEvCollProbes@@3UNCA_EVCOLL_PROBES_COMPONENT_@@A; NCA_EVCOLL_PROBES_COMPONENT_ gNcaEvCollProbes
0x1800128b7  cmp     [rax], rcx
0x1800128ba  jz      short loc_1800128C3
0x1800128bc  mov     ecx, 3
0x1800128c1  int     29h; Win8: RtlFailFast(ecx)
0x1800128c3  mov     [rbx], rcx
0x1800128c6  mov     [rbx+8], rax
0x1800128ca  mov     [rax], rbx
0x1800128cd  mov     cs:qword_180029088, rbx
0x1800128d4  lea     rcx, CriticalSection; lpCriticalSection
0x1800128db  call    cs:__imp_LeaveCriticalSection
0x1800128e2  nop     dword ptr [rax+rax+00h]
0x1800128e7  test    edi, edi
0x1800128e9  jz      short loc_180012900
0x1800128eb  test    rbx, rbx
0x1800128ee  jz      short loc_180012900
0x1800128f0  mov     rcx, rbx; struct NCA_EVCOLL_USER_PROBES_ *
0x1800128f3  call    ?NcaEvCollProbesInnerDelete@@YAXPEAUNCA_EVCOLL_USER_PROBES_@@@Z; NcaEvCollProbesInnerDelete(NCA_EVCOLL_USER_PROBES_ *)
0x1800128f8  mov     rcx, rbx; lpMem
0x1800128fb  call    NcaFree
0x180012900  mov     rcx, cs:WPP_GLOBAL_Control
0x180012907  cmp     rcx, rsi
0x18001290a  jz      short loc_18001292A
0x18001290c  test    byte ptr [rcx+1Ch], 8
0x180012910  jz      short loc_18001292A
0x180012912  mov     rcx, [rcx+10h]
0x180012916  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x18001291d  mov     edx, 32h ; '2'
0x180012922  mov     r9d, edi
0x180012925  call    WPP_SF_d
0x18001292a  mov     rbx, [rsp+28h+arg_0]
0x18001292f  mov     eax, edi
0x180012931  mov     rsi, [rsp+28h+arg_8]
0x180012936  add     rsp, 20h
0x18001293a  pop     rdi
0x18001293b  retn
```
