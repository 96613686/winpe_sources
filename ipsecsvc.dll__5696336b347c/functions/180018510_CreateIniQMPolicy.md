# CreateIniQMPolicy

- ea: `0x180018510`
- end: `0x180018661`
- name: `CreateIniQMPolicy`
- size: `337`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017ef0`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x18001832c`
- `0x180018510`
- `0x180018f78`

## pseudocode

```c
__int64 __fastcall CreateIniQMPolicy(__int64 a1, _QWORD *a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  __int64 v6; // r9
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 result; // rax

  v4 = (_OWORD *)IpsecAllocMem(72);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_20:
      *a2 = 0;
      return v7;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_15;
    v9 = 39;
    goto LABEL_14;
  }
  *v4 = *(_OWORD *)a1;
  v10 = IpsecAllocStr(*(unsigned __int16 **)(a1 + 16));
  *((_QWORD *)v5 + 2) = v10;
  if ( !v10 )
  {
    v6 = 8;
    v7 = 8;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v9 = 40;
      goto LABEL_14;
    }
    goto LABEL_19;
  }
  *((_QWORD *)v5 + 3) = 0;
  *((_DWORD *)v5 + 8) = *(_DWORD *)(a1 + 24);
  *((_DWORD *)v5 + 9) = *(_DWORD *)(a1 + 28);
  *((_QWORD *)v5 + 8) = 0;
  result = CreateIniQMOffers(*(_DWORD *)(a1 + 32), *(_QWORD *)(a1 + 40), (unsigned int *)v5 + 10, (__int64 *)v5 + 6);
  v7 = result;
  if ( (_DWORD)result != 13025 && (_DWORD)result )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_15;
      v9 = 41;
      v6 = (unsigned int)result;
LABEL_14:
      WPP_SF_d(v8[2], v9, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids, v6);
      v8 = WPP_GLOBAL_Control;
LABEL_15:
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
        WPP_SF_d(v8[2], 42, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids, v7);
      if ( !v5 )
        goto LABEL_20;
    }
LABEL_19:
    FreeIniQMPolicy(v5);
    goto LABEL_20;
  }
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180018510  push    rbx
0x180018512  push    rsi
0x180018513  push    rdi
0x180018514  push    r14
0x180018516  sub     rsp, 28h
0x18001851a  mov     rdi, rcx
0x18001851d  mov     r14, rdx
0x180018520  mov     ecx, 48h ; 'H'
0x180018525  call    IpsecAllocMem
0x18001852a  mov     rbx, rax
0x18001852d  test    rax, rax
0x180018530  jnz     short loc_180018562
0x180018532  lea     r9d, [rax+8]
0x180018536  mov     edi, r9d
0x180018539  mov     rcx, cs:WPP_GLOBAL_Control
0x180018540  lea     rsi, WPP_GLOBAL_Control
0x180018547  cmp     rcx, rsi
0x18001854a  jz      loc_180018649
0x180018550  test    byte ptr [rcx+1Ch], 10h
0x180018554  jz      loc_180018619
0x18001855a  lea     edx, [rax+27h]
0x18001855d  jmp     loc_180018602
0x180018562  movups  xmm0, xmmword ptr [rdi]
0x180018565  movdqu  xmmword ptr [rax], xmm0
0x180018569  mov     rcx, [rdi+10h]; unsigned __int16 *
0x18001856d  call    IpsecAllocStr
0x180018572  mov     [rbx+10h], rax
0x180018576  test    rax, rax
0x180018579  jnz     short loc_1800185A4
0x18001857b  lea     r9d, [rax+8]
0x18001857f  mov     edi, r9d
0x180018582  mov     rcx, cs:WPP_GLOBAL_Control
0x180018589  lea     rsi, WPP_GLOBAL_Control
0x180018590  cmp     rcx, rsi
0x180018593  jz      loc_180018641
0x180018599  test    byte ptr [rcx+1Ch], 10h
0x18001859d  jz      short loc_180018619
0x18001859f  lea     edx, [rax+28h]
0x1800185a2  jmp     short loc_180018602
0x1800185a4  mov     qword ptr [rbx+18h], 0
0x1800185ac  lea     r9, [rbx+30h]
0x1800185b0  mov     eax, [rdi+18h]
0x1800185b3  lea     r8, [rbx+28h]
0x1800185b7  mov     [rbx+20h], eax
0x1800185ba  mov     eax, [rdi+1Ch]
0x1800185bd  mov     [rbx+24h], eax
0x1800185c0  mov     qword ptr [rbx+40h], 0
0x1800185c8  mov     rdx, [rdi+28h]
0x1800185cc  mov     ecx, [rdi+20h]
0x1800185cf  call    CreateIniQMOffers
0x1800185d4  mov     edi, eax
0x1800185d6  cmp     eax, 32E1h
0x1800185db  jz      short loc_180018654
0x1800185dd  test    eax, eax
0x1800185df  jz      short loc_180018654
0x1800185e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185e8  lea     rsi, WPP_GLOBAL_Control
0x1800185ef  cmp     rcx, rsi
0x1800185f2  jz      short loc_180018641
0x1800185f4  test    byte ptr [rcx+1Ch], 10h
0x1800185f8  jz      short loc_180018619
0x1800185fa  mov     edx, 29h ; ')'
0x1800185ff  mov     r9d, eax
0x180018602  mov     rcx, [rcx+10h]
0x180018606  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x18001860d  call    WPP_SF_d
0x180018612  mov     rcx, cs:WPP_GLOBAL_Control
0x180018619  cmp     rcx, rsi
0x18001861c  jz      short loc_18001863C
0x18001861e  test    byte ptr [rcx+1Ch], 10h
0x180018622  jz      short loc_18001863C
0x180018624  mov     rcx, [rcx+10h]
0x180018628  lea     r8, WPP_b879685112533572aee45ba5e3c29dd7_Traceguids
0x18001862f  mov     edx, 2Ah ; '*'
0x180018634  mov     r9d, edi
0x180018637  call    WPP_SF_d
0x18001863c  test    rbx, rbx
0x18001863f  jz      short loc_180018649
0x180018641  mov     rcx, rbx; lpMem
0x180018644  call    FreeIniQMPolicy
0x180018649  mov     qword ptr [r14], 0
0x180018650  mov     eax, edi
0x180018652  jmp     short loc_180018657
0x180018654  mov     [r14], rbx
0x180018657  add     rsp, 28h
0x18001865b  pop     r14
0x18001865d  pop     rdi
0x18001865e  pop     rsi
0x18001865f  pop     rbx
0x180018660  retn
```
