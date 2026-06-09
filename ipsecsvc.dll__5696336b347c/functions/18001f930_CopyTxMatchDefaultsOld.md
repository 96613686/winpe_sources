# CopyTxMatchDefaultsOld

- ea: `0x18001f930`
- end: `0x18001fb0d`
- name: `CopyTxMatchDefaultsOld`
- size: `477`
- prototype: `__int64 __fastcall(char, _QWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800209bc`

## callees

- `0x18000e510`
- `0x180017534`
- `0x180018194`
- `0x180018fdc`
- `0x18001e318`
- `0x18001f5e8`
- `0x18001f930`

## pseudocode

```c
__int64 __fastcall CopyTxMatchDefaultsOld(char a1, _QWORD *a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 result; // rax

  if ( !gpIniDefaultQMPolicy )
  {
    v8 = 13015;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, 13015);
    goto LABEL_24;
  }
  v8 = SPDApiBufferAllocate(0xB8u);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v10 = 76;
    goto LABEL_23;
  }
  v8 = SPDApiBufferAllocate(0x30u);
  if ( v8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v12 = 77;
    goto LABEL_13;
  }
  v8 = CopyDefaultTxFilterOld(0);
  if ( v8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v12 = 78;
LABEL_13:
    WPP_SF_d(v11[2], v12, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, v8);
    goto LABEL_24;
  }
  v8 = CopyQMPolicy(a1, (__int128 *)gpIniDefaultQMPolicy, 0);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v10 = 79;
LABEL_23:
    WPP_SF_d(v9[2], v10, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, v8);
LABEL_24:
    *a2 = 0;
    result = v8;
    *a3 = 0;
    *a4 = 0;
    return result;
  }
  MEMORY[0x18] |= 8u;
  *a2 = 0;
  result = 0;
  *a3 = 0;
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x18001f930  push    rbx
0x18001f932  push    rbp
0x18001f933  push    rsi
0x18001f934  push    rdi
0x18001f935  push    r12
0x18001f937  push    r13
0x18001f939  push    r14
0x18001f93b  push    r15
0x18001f93d  sub     rsp, 38h
0x18001f941  xor     esi, esi
0x18001f943  mov     r15, r9
0x18001f946  cmp     cs:gpIniDefaultQMPolicy, rsi
0x18001f94d  mov     ebx, esi
0x18001f94f  mov     [rsp+78h+var_58], rbx
0x18001f954  mov     r12, r8
0x18001f957  mov     r13, rdx
0x18001f95a  mov     [rsp+78h+var_50], rsi
0x18001f95f  mov     r14d, ecx
0x18001f962  jnz     short loc_18001F9A5
0x18001f964  mov     edi, 32D7h
0x18001f969  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f970  lea     rax, WPP_GLOBAL_Control
0x18001f977  cmp     rcx, rax
0x18001f97a  jz      loc_18001FAD8
0x18001f980  test    byte ptr [rcx+1Ch], 10h
0x18001f984  jz      loc_18001FAD8
0x18001f98a  mov     rcx, [rcx+10h]
0x18001f98e  lea     edx, [rsi+4Bh]
0x18001f991  mov     r9d, edi
0x18001f994  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001f99b  call    WPP_SF_d
0x18001f9a0  jmp     loc_18001FAD8
0x18001f9a5  lea     rdx, [rsp+78h+var_50]
0x18001f9aa  mov     ecx, 0B8h; Size
0x18001f9af  mov     ebp, esi
0x18001f9b1  call    SPDApiBufferAllocate
0x18001f9b6  mov     rsi, [rsp+78h+var_50]
0x18001f9bb  mov     edi, eax
0x18001f9bd  test    eax, eax
0x18001f9bf  jz      short loc_18001F9EC
0x18001f9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9c8  lea     rax, WPP_GLOBAL_Control
0x18001f9cf  cmp     rcx, rax
0x18001f9d2  jz      loc_18001FAB8
0x18001f9d8  test    byte ptr [rcx+1Ch], 10h
0x18001f9dc  jz      loc_18001FAB8
0x18001f9e2  mov     edx, 4Ch ; 'L'
0x18001f9e7  jmp     loc_18001FAA5
0x18001f9ec  lea     rdx, [rsp+78h+var_58]
0x18001f9f1  mov     ecx, 30h ; '0'; Size
0x18001f9f6  call    SPDApiBufferAllocate
0x18001f9fb  mov     edi, eax
0x18001f9fd  test    eax, eax
0x18001f9ff  jz      short loc_18001FA39
0x18001fa01  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa08  lea     rax, WPP_GLOBAL_Control
0x18001fa0f  cmp     rcx, rax
0x18001fa12  jz      short loc_18001FA32
0x18001fa14  test    byte ptr [rcx+1Ch], 10h
0x18001fa18  jz      short loc_18001FA32
0x18001fa1a  mov     edx, 4Dh ; 'M'
0x18001fa1f  mov     rcx, [rcx+10h]
0x18001fa23  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001fa2a  mov     r9d, edi
0x18001fa2d  call    WPP_SF_d
0x18001fa32  mov     rbx, [rsp+78h+var_58]
0x18001fa37  jmp     short loc_18001FAB8
0x18001fa39  mov     rcx, rsi
0x18001fa3c  call    CopyDefaultTxFilterOld
0x18001fa41  mov     edi, eax
0x18001fa43  test    eax, eax
0x18001fa45  jz      short loc_18001FA67
0x18001fa47  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa4e  lea     rax, WPP_GLOBAL_Control
0x18001fa55  cmp     rcx, rax
0x18001fa58  jz      short loc_18001FA32
0x18001fa5a  test    byte ptr [rcx+1Ch], 10h
0x18001fa5e  jz      short loc_18001FA32
0x18001fa60  mov     edx, 4Eh ; 'N'
0x18001fa65  jmp     short loc_18001FA1F
0x18001fa67  mov     rbx, [rsp+78h+var_58]
0x18001fa6c  mov     ecx, r14d
0x18001fa6f  mov     rdx, cs:gpIniDefaultQMPolicy
0x18001fa76  mov     r8, rbx
0x18001fa79  call    CopyQMPolicy
0x18001fa7e  mov     edi, eax
0x18001fa80  test    eax, eax
0x18001fa82  jz      short loc_18001FAE7
0x18001fa84  mov     ebp, 1
0x18001fa89  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa90  lea     rax, WPP_GLOBAL_Control
0x18001fa97  cmp     rcx, rax
0x18001fa9a  jz      short loc_18001FAB8
0x18001fa9c  test    byte ptr [rcx+1Ch], 10h
0x18001faa0  jz      short loc_18001FAB8
0x18001faa2  lea     edx, [rbp+4Eh]
0x18001faa5  mov     rcx, [rcx+10h]
0x18001faa9  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001fab0  mov     r9d, edi
0x18001fab3  call    WPP_SF_d
0x18001fab8  test    rsi, rsi
0x18001fabb  jz      short loc_18001FAC7
0x18001fabd  mov     rdx, rsi
0x18001fac0  mov     ecx, ebp
0x18001fac2  call    FreeTxFiltersOld
0x18001fac7  xor     esi, esi
0x18001fac9  test    rbx, rbx
0x18001facc  jz      short loc_18001FAD8
0x18001face  mov     rdx, rbx
0x18001fad1  xor     ecx, ecx
0x18001fad3  call    FreeMMPolicies
0x18001fad8  mov     [r13+0], rsi
0x18001fadc  mov     eax, edi
0x18001fade  mov     [r12], rsi
0x18001fae2  mov     [r15], esi
0x18001fae5  jmp     short loc_18001FAFC
0x18001fae7  or      dword ptr [rbx+18h], 8
0x18001faeb  mov     [r13+0], rsi
0x18001faef  xor     eax, eax
0x18001faf1  mov     [r12], rbx
0x18001faf5  mov     dword ptr [r15], 1
0x18001fafc  add     rsp, 38h
0x18001fb00  pop     r15
0x18001fb02  pop     r14
0x18001fb04  pop     r13
0x18001fb06  pop     r12
0x18001fb08  pop     rdi
0x18001fb09  pop     rsi
0x18001fb0a  pop     rbp
0x18001fb0b  pop     rbx
0x18001fb0c  retn
```
