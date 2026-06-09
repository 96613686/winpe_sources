# CopyMMMatchDefaults

- ea: `0x180025320`
- end: `0x1800255d2`
- name: `CopyMMMatchDefaults`
- size: `690`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800269a0`

## callees

- `0x18000e510`
- `0x180017534`
- `0x180018fdc`
- `0x18001a1ac`
- `0x18001b750`
- `0x18001bf48`
- `0x180023674`
- `0x1800250ec`
- `0x180025320`

## pseudocode

```c
__int64 __fastcall CopyMMMatchDefaults(_QWORD *a1, _QWORD *a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 result; // rax

  if ( !gpIniDefaultMMPolicy )
  {
    v7 = 13013;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 54;
LABEL_33:
    WPP_SF_d(v8[2], v9, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids, v7);
LABEL_34:
    *a1 = 0;
    result = v7;
    *a3 = 0;
    *a2 = 0;
    *a4 = 0;
    return result;
  }
  if ( !gpIniDefaultMMAuthMethods )
  {
    v7 = 13014;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 55;
    goto LABEL_33;
  }
  v7 = SPDApiBufferAllocate(0xA8u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 56;
    goto LABEL_33;
  }
  v7 = SPDApiBufferAllocate(0x30u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 57;
    goto LABEL_33;
  }
  v7 = SPDApiBufferAllocate(0x20u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 58;
    goto LABEL_33;
  }
  v7 = CopyDefaultMMFilter(0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 59;
    goto LABEL_33;
  }
  v7 = CopyMMPolicy(gpIniDefaultMMPolicy, 0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 60;
    goto LABEL_33;
  }
  MEMORY[0x18] |= 4u;
  v7 = CopyMMAuthMethods(gpIniDefaultMMAuthMethods, 0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 61;
    goto LABEL_33;
  }
  MEMORY[0x10] |= 2u;
  *a1 = 0;
  *a3 = 0;
  result = 0;
  *a2 = 0;
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x180025320  mov     [rsp-40h+arg_0], rcx
0x180025325  push    rbp
0x180025326  push    rbx
0x180025327  push    rsi
0x180025328  push    rdi
0x180025329  push    r12
0x18002532b  push    r13
0x18002532d  push    r14
0x18002532f  push    r15
0x180025331  mov     rbp, rsp
0x180025334  sub     rsp, 48h
0x180025338  xor     edi, edi
0x18002533a  mov     r15, r9
0x18002533d  cmp     cs:gpIniDefaultMMPolicy, rdi
0x180025344  mov     r12, r8
0x180025347  mov     r13, rdx
0x18002534a  mov     [rbp+var_18], rdi
0x18002534e  mov     [rbp+var_20], rdi
0x180025352  mov     [rbp+var_28], rdi
0x180025356  jnz     short loc_180025399
0x180025358  mov     ebx, 32D5h
0x18002535d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025364  lea     rax, WPP_GLOBAL_Control
0x18002536b  cmp     rcx, rax
0x18002536e  jz      loc_18002558B
0x180025374  test    byte ptr [rcx+1Ch], 10h
0x180025378  jz      loc_18002558B
0x18002537e  lea     edx, [rdi+36h]
0x180025381  mov     rcx, [rcx+10h]
0x180025385  lea     r8, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids
0x18002538c  mov     r9d, ebx
0x18002538f  call    WPP_SF_d
0x180025394  jmp     loc_18002558B
0x180025399  cmp     cs:gpIniDefaultMMAuthMethods, rdi
0x1800253a0  jnz     short loc_1800253CF
0x1800253a2  mov     ebx, 32D6h
0x1800253a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253ae  lea     rax, WPP_GLOBAL_Control
0x1800253b5  cmp     rcx, rax
0x1800253b8  jz      loc_18002558B
0x1800253be  test    byte ptr [rcx+1Ch], 10h
0x1800253c2  jz      loc_18002558B
0x1800253c8  mov     edx, 37h ; '7'
0x1800253cd  jmp     short loc_180025381
0x1800253cf  lea     rdx, [rbp+var_18]
0x1800253d3  mov     ecx, 0A8h; Size
0x1800253d8  mov     esi, edi
0x1800253da  mov     r14d, edi
0x1800253dd  call    SPDApiBufferAllocate
0x1800253e2  mov     rdi, [rbp+var_18]
0x1800253e6  mov     ebx, eax
0x1800253e8  test    eax, eax
0x1800253ea  jz      short loc_180025417
0x1800253ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253f3  lea     rax, WPP_GLOBAL_Control
0x1800253fa  cmp     rcx, rax
0x1800253fd  jz      loc_180025556
0x180025403  test    byte ptr [rcx+1Ch], 10h
0x180025407  jz      loc_180025556
0x18002540d  mov     edx, 38h ; '8'
0x180025412  jmp     loc_180025543
0x180025417  lea     rdx, [rbp+var_28]
0x18002541b  mov     ecx, 30h ; '0'; Size
0x180025420  call    SPDApiBufferAllocate
0x180025425  mov     ebx, eax
0x180025427  test    eax, eax
0x180025429  jz      short loc_180025456
0x18002542b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025432  lea     rax, WPP_GLOBAL_Control
0x180025439  cmp     rcx, rax
0x18002543c  jz      loc_180025556
0x180025442  test    byte ptr [rcx+1Ch], 10h
0x180025446  jz      loc_180025556
0x18002544c  mov     edx, 39h ; '9'
0x180025451  jmp     loc_180025543
0x180025456  lea     rdx, [rbp+var_20]
0x18002545a  mov     ecx, 20h ; ' '; Size
0x18002545f  call    SPDApiBufferAllocate
0x180025464  mov     ebx, eax
0x180025466  test    eax, eax
0x180025468  jz      short loc_180025495
0x18002546a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025471  lea     rax, WPP_GLOBAL_Control
0x180025478  cmp     rcx, rax
0x18002547b  jz      loc_180025556
0x180025481  test    byte ptr [rcx+1Ch], 10h
0x180025485  jz      loc_180025556
0x18002548b  mov     edx, 3Ah ; ':'
0x180025490  jmp     loc_180025543
0x180025495  mov     rcx, rdi
0x180025498  call    CopyDefaultMMFilter
0x18002549d  mov     ebx, eax
0x18002549f  test    eax, eax
0x1800254a1  jz      short loc_1800254CB
0x1800254a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254aa  lea     rax, WPP_GLOBAL_Control
0x1800254b1  cmp     rcx, rax
0x1800254b4  jz      loc_180025556
0x1800254ba  test    byte ptr [rcx+1Ch], 10h
0x1800254be  jz      loc_180025556
0x1800254c4  mov     edx, 3Bh ; ';'
0x1800254c9  jmp     short loc_180025543
0x1800254cb  mov     rdx, [rbp+var_28]
0x1800254cf  mov     esi, 1
0x1800254d4  mov     rcx, cs:gpIniDefaultMMPolicy
0x1800254db  call    CopyMMPolicy
0x1800254e0  mov     ebx, eax
0x1800254e2  test    eax, eax
0x1800254e4  jz      short loc_180025504
0x1800254e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254ed  lea     rax, WPP_GLOBAL_Control
0x1800254f4  cmp     rcx, rax
0x1800254f7  jz      short loc_180025556
0x1800254f9  test    byte ptr [rcx+1Ch], 10h
0x1800254fd  jz      short loc_180025556
0x1800254ff  lea     edx, [rsi+3Bh]
0x180025502  jmp     short loc_180025543
0x180025504  mov     rax, [rbp+var_28]
0x180025508  mov     rdx, [rbp+var_20]
0x18002550c  mov     rcx, cs:gpIniDefaultMMAuthMethods
0x180025513  or      dword ptr [rax+18h], 4
0x180025517  call    CopyMMAuthMethods
0x18002551c  mov     ebx, eax
0x18002551e  test    eax, eax
0x180025520  jz      short loc_1800255A1
0x180025522  mov     r14d, esi
0x180025525  mov     rcx, cs:WPP_GLOBAL_Control
0x18002552c  lea     rax, WPP_GLOBAL_Control
0x180025533  cmp     rcx, rax
0x180025536  jz      short loc_180025556
0x180025538  test    byte ptr [rcx+1Ch], 10h
0x18002553c  jz      short loc_180025556
0x18002553e  mov     edx, 3Dh ; '='
0x180025543  mov     rcx, [rcx+10h]
0x180025547  lea     r8, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids
0x18002554e  mov     r9d, ebx
0x180025551  call    WPP_SF_d
0x180025556  test    rdi, rdi
0x180025559  jz      short loc_180025565
0x18002555b  mov     rdx, rdi
0x18002555e  mov     ecx, esi
0x180025560  call    FreeMMFilters
0x180025565  mov     rdx, [rbp+var_28]
0x180025569  xor     edi, edi
0x18002556b  test    rdx, rdx
0x18002556e  jz      short loc_180025578
0x180025570  mov     ecx, r14d
0x180025573  call    FreeMMPolicies
0x180025578  mov     rcx, [rbp+var_20]
0x18002557c  test    rcx, rcx
0x18002557f  jz      short loc_18002558B
0x180025581  mov     rdx, rcx
0x180025584  xor     ecx, ecx
0x180025586  call    FreeMMAuthMethods
0x18002558b  mov     rax, [rbp+arg_0]
0x18002558f  mov     [rax], rdi
0x180025592  mov     eax, ebx
0x180025594  mov     [r12], rdi
0x180025598  mov     [r13+0], rdi
0x18002559c  mov     [r15], edi
0x18002559f  jmp     short loc_1800255C1
0x1800255a1  mov     rcx, [rbp+var_20]
0x1800255a5  mov     rax, [rbp+arg_0]
0x1800255a9  or      dword ptr [rcx+10h], 2
0x1800255ad  mov     [rax], rdi
0x1800255b0  mov     rax, [rbp+var_28]
0x1800255b4  mov     [r12], rax
0x1800255b8  xor     eax, eax
0x1800255ba  mov     [r13+0], rcx
0x1800255be  mov     [r15], esi
0x1800255c1  add     rsp, 48h
0x1800255c5  pop     r15
0x1800255c7  pop     r14
0x1800255c9  pop     r13
0x1800255cb  pop     r12
0x1800255cd  pop     rdi
0x1800255ce  pop     rsi
0x1800255cf  pop     rbx
0x1800255d0  pop     rbp
0x1800255d1  retn
```
