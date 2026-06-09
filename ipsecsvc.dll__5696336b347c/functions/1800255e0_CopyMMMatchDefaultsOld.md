# CopyMMMatchDefaultsOld

- ea: `0x1800255e0`
- end: `0x180025892`
- name: `CopyMMMatchDefaultsOld`
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
- `0x180023718`
- `0x1800251f8`
- `0x1800255e0`

## pseudocode

```c
__int64 __fastcall CopyMMMatchDefaultsOld(_QWORD *a1, _QWORD *a2, _QWORD *a3, _DWORD *a4)
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
    v9 = 62;
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
    v9 = 63;
    goto LABEL_33;
  }
  v7 = SPDApiBufferAllocate(0xA8u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 64;
    goto LABEL_33;
  }
  v7 = SPDApiBufferAllocate(0x30u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 65;
    goto LABEL_33;
  }
  v7 = SPDApiBufferAllocate(0x20u);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 66;
    goto LABEL_33;
  }
  v7 = CopyDefaultMMFilterOld(0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 67;
    goto LABEL_33;
  }
  v7 = CopyMMPolicy(gpIniDefaultMMPolicy, 0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 68;
    goto LABEL_33;
  }
  MEMORY[0x18] |= 4u;
  v7 = CopyMMAuthMethods(gpIniDefaultMMAuthMethods, 0);
  if ( v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_34;
    v9 = 69;
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
0x1800255e0  mov     [rsp-40h+arg_0], rcx
0x1800255e5  push    rbp
0x1800255e6  push    rbx
0x1800255e7  push    rsi
0x1800255e8  push    rdi
0x1800255e9  push    r12
0x1800255eb  push    r13
0x1800255ed  push    r14
0x1800255ef  push    r15
0x1800255f1  mov     rbp, rsp
0x1800255f4  sub     rsp, 48h
0x1800255f8  xor     edi, edi
0x1800255fa  mov     r15, r9
0x1800255fd  cmp     cs:gpIniDefaultMMPolicy, rdi
0x180025604  mov     r12, r8
0x180025607  mov     r13, rdx
0x18002560a  mov     [rbp+var_18], rdi
0x18002560e  mov     [rbp+var_20], rdi
0x180025612  mov     [rbp+var_28], rdi
0x180025616  jnz     short loc_180025659
0x180025618  mov     ebx, 32D5h
0x18002561d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025624  lea     rax, WPP_GLOBAL_Control
0x18002562b  cmp     rcx, rax
0x18002562e  jz      loc_18002584B
0x180025634  test    byte ptr [rcx+1Ch], 10h
0x180025638  jz      loc_18002584B
0x18002563e  lea     edx, [rdi+3Eh]
0x180025641  mov     rcx, [rcx+10h]
0x180025645  lea     r8, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids
0x18002564c  mov     r9d, ebx
0x18002564f  call    WPP_SF_d
0x180025654  jmp     loc_18002584B
0x180025659  cmp     cs:gpIniDefaultMMAuthMethods, rdi
0x180025660  jnz     short loc_18002568F
0x180025662  mov     ebx, 32D6h
0x180025667  mov     rcx, cs:WPP_GLOBAL_Control
0x18002566e  lea     rax, WPP_GLOBAL_Control
0x180025675  cmp     rcx, rax
0x180025678  jz      loc_18002584B
0x18002567e  test    byte ptr [rcx+1Ch], 10h
0x180025682  jz      loc_18002584B
0x180025688  mov     edx, 3Fh ; '?'
0x18002568d  jmp     short loc_180025641
0x18002568f  lea     rdx, [rbp+var_18]
0x180025693  mov     ecx, 0A8h; Size
0x180025698  mov     esi, edi
0x18002569a  mov     r14d, edi
0x18002569d  call    SPDApiBufferAllocate
0x1800256a2  mov     rdi, [rbp+var_18]
0x1800256a6  mov     ebx, eax
0x1800256a8  test    eax, eax
0x1800256aa  jz      short loc_1800256D7
0x1800256ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256b3  lea     rax, WPP_GLOBAL_Control
0x1800256ba  cmp     rcx, rax
0x1800256bd  jz      loc_180025816
0x1800256c3  test    byte ptr [rcx+1Ch], 10h
0x1800256c7  jz      loc_180025816
0x1800256cd  mov     edx, 40h ; '@'
0x1800256d2  jmp     loc_180025803
0x1800256d7  lea     rdx, [rbp+var_28]
0x1800256db  mov     ecx, 30h ; '0'; Size
0x1800256e0  call    SPDApiBufferAllocate
0x1800256e5  mov     ebx, eax
0x1800256e7  test    eax, eax
0x1800256e9  jz      short loc_180025716
0x1800256eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800256f2  lea     rax, WPP_GLOBAL_Control
0x1800256f9  cmp     rcx, rax
0x1800256fc  jz      loc_180025816
0x180025702  test    byte ptr [rcx+1Ch], 10h
0x180025706  jz      loc_180025816
0x18002570c  mov     edx, 41h ; 'A'
0x180025711  jmp     loc_180025803
0x180025716  lea     rdx, [rbp+var_20]
0x18002571a  mov     ecx, 20h ; ' '; Size
0x18002571f  call    SPDApiBufferAllocate
0x180025724  mov     ebx, eax
0x180025726  test    eax, eax
0x180025728  jz      short loc_180025755
0x18002572a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025731  lea     rax, WPP_GLOBAL_Control
0x180025738  cmp     rcx, rax
0x18002573b  jz      loc_180025816
0x180025741  test    byte ptr [rcx+1Ch], 10h
0x180025745  jz      loc_180025816
0x18002574b  mov     edx, 42h ; 'B'
0x180025750  jmp     loc_180025803
0x180025755  mov     rcx, rdi
0x180025758  call    CopyDefaultMMFilterOld
0x18002575d  mov     ebx, eax
0x18002575f  test    eax, eax
0x180025761  jz      short loc_18002578B
0x180025763  mov     rcx, cs:WPP_GLOBAL_Control
0x18002576a  lea     rax, WPP_GLOBAL_Control
0x180025771  cmp     rcx, rax
0x180025774  jz      loc_180025816
0x18002577a  test    byte ptr [rcx+1Ch], 10h
0x18002577e  jz      loc_180025816
0x180025784  mov     edx, 43h ; 'C'
0x180025789  jmp     short loc_180025803
0x18002578b  mov     rdx, [rbp+var_28]
0x18002578f  mov     esi, 1
0x180025794  mov     rcx, cs:gpIniDefaultMMPolicy
0x18002579b  call    CopyMMPolicy
0x1800257a0  mov     ebx, eax
0x1800257a2  test    eax, eax
0x1800257a4  jz      short loc_1800257C4
0x1800257a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257ad  lea     rax, WPP_GLOBAL_Control
0x1800257b4  cmp     rcx, rax
0x1800257b7  jz      short loc_180025816
0x1800257b9  test    byte ptr [rcx+1Ch], 10h
0x1800257bd  jz      short loc_180025816
0x1800257bf  lea     edx, [rsi+43h]
0x1800257c2  jmp     short loc_180025803
0x1800257c4  mov     rax, [rbp+var_28]
0x1800257c8  mov     rdx, [rbp+var_20]
0x1800257cc  mov     rcx, cs:gpIniDefaultMMAuthMethods
0x1800257d3  or      dword ptr [rax+18h], 4
0x1800257d7  call    CopyMMAuthMethods
0x1800257dc  mov     ebx, eax
0x1800257de  test    eax, eax
0x1800257e0  jz      short loc_180025861
0x1800257e2  mov     r14d, esi
0x1800257e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257ec  lea     rax, WPP_GLOBAL_Control
0x1800257f3  cmp     rcx, rax
0x1800257f6  jz      short loc_180025816
0x1800257f8  test    byte ptr [rcx+1Ch], 10h
0x1800257fc  jz      short loc_180025816
0x1800257fe  mov     edx, 45h ; 'E'
0x180025803  mov     rcx, [rcx+10h]
0x180025807  lea     r8, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids
0x18002580e  mov     r9d, ebx
0x180025811  call    WPP_SF_d
0x180025816  test    rdi, rdi
0x180025819  jz      short loc_180025825
0x18002581b  mov     rdx, rdi
0x18002581e  mov     ecx, esi
0x180025820  call    FreeMMFiltersOld
0x180025825  mov     rdx, [rbp+var_28]
0x180025829  xor     edi, edi
0x18002582b  test    rdx, rdx
0x18002582e  jz      short loc_180025838
0x180025830  mov     ecx, r14d
0x180025833  call    FreeMMPolicies
0x180025838  mov     rcx, [rbp+var_20]
0x18002583c  test    rcx, rcx
0x18002583f  jz      short loc_18002584B
0x180025841  mov     rdx, rcx
0x180025844  xor     ecx, ecx
0x180025846  call    FreeMMAuthMethods
0x18002584b  mov     rax, [rbp+arg_0]
0x18002584f  mov     [rax], rdi
0x180025852  mov     eax, ebx
0x180025854  mov     [r12], rdi
0x180025858  mov     [r13+0], rdi
0x18002585c  mov     [r15], edi
0x18002585f  jmp     short loc_180025881
0x180025861  mov     rcx, [rbp+var_20]
0x180025865  mov     rax, [rbp+arg_0]
0x180025869  or      dword ptr [rcx+10h], 2
0x18002586d  mov     [rax], rdi
0x180025870  mov     rax, [rbp+var_28]
0x180025874  mov     [r12], rax
0x180025878  xor     eax, eax
0x18002587a  mov     [r13+0], rcx
0x18002587e  mov     [r15], esi
0x180025881  add     rsp, 48h
0x180025885  pop     r15
0x180025887  pop     r14
0x180025889  pop     r13
0x18002588b  pop     r12
0x18002588d  pop     rdi
0x18002588e  pop     rsi
0x18002588f  pop     rbx
0x180025890  pop     rbp
0x180025891  retn
```
