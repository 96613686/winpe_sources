# CopyTxMatchDefaults

- ea: `0x18001f740`
- end: `0x18001f91d`
- name: `CopyTxMatchDefaults`
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
- `0x18001e278`
- `0x18001f4b4`
- `0x18001f740`

## pseudocode

```c
__int64 __fastcall CopyTxMatchDefaults(char a1, _QWORD *a2, _QWORD *a3, _DWORD *a4)
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, 13015);
    goto LABEL_24;
  }
  v8 = SPDApiBufferAllocate(0xB8u);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v10 = 71;
    goto LABEL_23;
  }
  v8 = SPDApiBufferAllocate(0x30u);
  if ( v8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v12 = 72;
    goto LABEL_13;
  }
  v8 = CopyDefaultTxFilter(0);
  if ( v8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v12 = 73;
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
    v10 = 74;
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
0x18001f740  push    rbx
0x18001f742  push    rbp
0x18001f743  push    rsi
0x18001f744  push    rdi
0x18001f745  push    r12
0x18001f747  push    r13
0x18001f749  push    r14
0x18001f74b  push    r15
0x18001f74d  sub     rsp, 38h
0x18001f751  xor     esi, esi
0x18001f753  mov     r15, r9
0x18001f756  cmp     cs:gpIniDefaultQMPolicy, rsi
0x18001f75d  mov     ebx, esi
0x18001f75f  mov     [rsp+78h+var_58], rbx
0x18001f764  mov     r12, r8
0x18001f767  mov     r13, rdx
0x18001f76a  mov     [rsp+78h+var_50], rsi
0x18001f76f  mov     r14d, ecx
0x18001f772  jnz     short loc_18001F7B5
0x18001f774  mov     edi, 32D7h
0x18001f779  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f780  lea     rax, WPP_GLOBAL_Control
0x18001f787  cmp     rcx, rax
0x18001f78a  jz      loc_18001F8E8
0x18001f790  test    byte ptr [rcx+1Ch], 10h
0x18001f794  jz      loc_18001F8E8
0x18001f79a  mov     rcx, [rcx+10h]
0x18001f79e  lea     edx, [rsi+46h]
0x18001f7a1  mov     r9d, edi
0x18001f7a4  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001f7ab  call    WPP_SF_d
0x18001f7b0  jmp     loc_18001F8E8
0x18001f7b5  lea     rdx, [rsp+78h+var_50]
0x18001f7ba  mov     ecx, 0B8h; Size
0x18001f7bf  mov     ebp, esi
0x18001f7c1  call    SPDApiBufferAllocate
0x18001f7c6  mov     rsi, [rsp+78h+var_50]
0x18001f7cb  mov     edi, eax
0x18001f7cd  test    eax, eax
0x18001f7cf  jz      short loc_18001F7FC
0x18001f7d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7d8  lea     rax, WPP_GLOBAL_Control
0x18001f7df  cmp     rcx, rax
0x18001f7e2  jz      loc_18001F8C8
0x18001f7e8  test    byte ptr [rcx+1Ch], 10h
0x18001f7ec  jz      loc_18001F8C8
0x18001f7f2  mov     edx, 47h ; 'G'
0x18001f7f7  jmp     loc_18001F8B5
0x18001f7fc  lea     rdx, [rsp+78h+var_58]
0x18001f801  mov     ecx, 30h ; '0'; Size
0x18001f806  call    SPDApiBufferAllocate
0x18001f80b  mov     edi, eax
0x18001f80d  test    eax, eax
0x18001f80f  jz      short loc_18001F849
0x18001f811  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f818  lea     rax, WPP_GLOBAL_Control
0x18001f81f  cmp     rcx, rax
0x18001f822  jz      short loc_18001F842
0x18001f824  test    byte ptr [rcx+1Ch], 10h
0x18001f828  jz      short loc_18001F842
0x18001f82a  mov     edx, 48h ; 'H'
0x18001f82f  mov     rcx, [rcx+10h]
0x18001f833  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001f83a  mov     r9d, edi
0x18001f83d  call    WPP_SF_d
0x18001f842  mov     rbx, [rsp+78h+var_58]
0x18001f847  jmp     short loc_18001F8C8
0x18001f849  mov     rcx, rsi
0x18001f84c  call    CopyDefaultTxFilter
0x18001f851  mov     edi, eax
0x18001f853  test    eax, eax
0x18001f855  jz      short loc_18001F877
0x18001f857  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f85e  lea     rax, WPP_GLOBAL_Control
0x18001f865  cmp     rcx, rax
0x18001f868  jz      short loc_18001F842
0x18001f86a  test    byte ptr [rcx+1Ch], 10h
0x18001f86e  jz      short loc_18001F842
0x18001f870  mov     edx, 49h ; 'I'
0x18001f875  jmp     short loc_18001F82F
0x18001f877  mov     rbx, [rsp+78h+var_58]
0x18001f87c  mov     ecx, r14d
0x18001f87f  mov     rdx, cs:gpIniDefaultQMPolicy
0x18001f886  mov     r8, rbx
0x18001f889  call    CopyQMPolicy
0x18001f88e  mov     edi, eax
0x18001f890  test    eax, eax
0x18001f892  jz      short loc_18001F8F7
0x18001f894  mov     ebp, 1
0x18001f899  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8a0  lea     rax, WPP_GLOBAL_Control
0x18001f8a7  cmp     rcx, rax
0x18001f8aa  jz      short loc_18001F8C8
0x18001f8ac  test    byte ptr [rcx+1Ch], 10h
0x18001f8b0  jz      short loc_18001F8C8
0x18001f8b2  lea     edx, [rbp+49h]
0x18001f8b5  mov     rcx, [rcx+10h]
0x18001f8b9  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001f8c0  mov     r9d, edi
0x18001f8c3  call    WPP_SF_d
0x18001f8c8  test    rsi, rsi
0x18001f8cb  jz      short loc_18001F8D7
0x18001f8cd  mov     rdx, rsi
0x18001f8d0  mov     ecx, ebp
0x18001f8d2  call    FreeTxFilters
0x18001f8d7  xor     esi, esi
0x18001f8d9  test    rbx, rbx
0x18001f8dc  jz      short loc_18001F8E8
0x18001f8de  mov     rdx, rbx
0x18001f8e1  xor     ecx, ecx
0x18001f8e3  call    FreeMMPolicies
0x18001f8e8  mov     [r13+0], rsi
0x18001f8ec  mov     eax, edi
0x18001f8ee  mov     [r12], rsi
0x18001f8f2  mov     [r15], esi
0x18001f8f5  jmp     short loc_18001F90C
0x18001f8f7  or      dword ptr [rbx+18h], 8
0x18001f8fb  mov     [r13+0], rsi
0x18001f8ff  xor     eax, eax
0x18001f901  mov     [r12], rbx
0x18001f905  mov     dword ptr [r15], 1
0x18001f90c  add     rsp, 38h
0x18001f910  pop     r15
0x18001f912  pop     r14
0x18001f914  pop     r13
0x18001f916  pop     r12
0x18001f918  pop     rdi
0x18001f919  pop     rsi
0x18001f91a  pop     rbp
0x18001f91b  pop     rbx
0x18001f91c  retn
```
