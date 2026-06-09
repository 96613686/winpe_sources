# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x1400281f0`
- end: `0x14002836f`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140028088`

## callees

- `0x14000bfa0`
- `0x1400281f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002826c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002826c`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 *i; // rbx
  int v1; // eax
  _QWORD *v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= wil_details_featureDescriptors_a )
      return;
    if ( *i )
      break;
  }
LABEL_20:
  if ( !i )
    return;
  v5 = 0;
  v6 = 0;
  v4 = 0;
  if ( *((_BYTE *)i + 29) || *((_BYTE *)i + 30) )
    goto LABEL_14;
  v1 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
         *((unsigned int *)i + 6),
         (unsigned __int8)(*((_BYTE *)i + 28) - 2) > 1u,
         &v4,
         &v5);
  if ( v1 != -2147483614 )
  {
    if ( v1 != -1073741275 )
    {
      if ( !v1 )
      {
        v4 = (8 * (BYTE4(v5) & 0xB0 | (4 * (BYTE4(v5) & 0x40u)))) | 0x206LL;
        goto LABEL_15;
      }
      if ( v1 == 279 )
      {
        v4 = (8 * (BYTE4(v5) & 0x80u)) | 0x206LL;
        goto LABEL_15;
      }
    }
LABEL_14:
    v4 = 518;
LABEL_15:
    v2 = (_QWORD *)*i;
    i += 7;
    *v2 = v4;
    while ( i < wil_details_featureDescriptors_a )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = (_QWORD *)*i;
  i += 7;
  *v3 = 518;
  while ( i < wil_details_featureDescriptors_a )
  {
    if ( *i )
    {
      if ( i )
        goto LABEL_23;
      return;
    }
    ++i;
  }
}

```

## disassembly

```asm
0x1400281f0  mov     [rsp+arg_0], rbx
0x1400281f5  push    rsi
0x1400281f6  sub     rsp, 40h
0x1400281fa  mov     rax, cs:__security_cookie
0x140028201  xor     rax, rsp
0x140028204  mov     [rsp+48h+var_10], rax
0x140028209  lea     rbx, wil_details_featureDescriptors_a
0x140028210  lea     rsi, wil_details_featureDescriptors_a
0x140028217  jmp     short loc_140028227
0x140028219  cmp     qword ptr [rbx], 0
0x14002821d  jnz     loc_140028313
0x140028223  add     rbx, 8
0x140028227  cmp     rbx, rsi
0x14002822a  jb      short loc_140028219
0x14002822c  jmp     loc_140028356
0x140028231  xor     eax, eax
0x140028233  mov     [rsp+48h+var_20], rax
0x140028238  mov     [rsp+48h+var_18], eax
0x14002823c  mov     [rsp+48h+var_28], rax
0x140028241  cmp     [rbx+1Dh], al
0x140028244  jnz     loc_1400282E0
0x14002824a  cmp     [rbx+1Eh], al
0x14002824d  jnz     loc_1400282E0
0x140028253  mov     al, [rbx+1Ch]
0x140028256  lea     r9, [rsp+48h+var_20]
0x14002825b  mov     ecx, [rbx+18h]
0x14002825e  lea     r8, [rsp+48h+var_28]
0x140028263  xor     edx, edx
0x140028265  sub     al, 2
0x140028267  cmp     al, 1
0x140028269  setnbe  dl
0x14002826c  call    cs:__imp_RtlQueryFeatureConfiguration
0x140028273  nop     dword ptr [rax+rax+00h]
0x140028278  cmp     eax, 80000022h
0x14002827d  jz      loc_14002831E
0x140028283  cmp     eax, 0C0000225h
0x140028288  jz      short loc_1400282E0
0x14002828a  test    eax, eax
0x14002828c  jz      short loc_1400282B5
0x14002828e  cmp     eax, 117h
0x140028293  jnz     short loc_1400282E0
0x140028295  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140028299  and     eax, 80h
0x14002829e  mov     [rsp+48h+var_28], 0
0x1400282a7  shl     eax, 3
0x1400282aa  or      eax, 206h
0x1400282af  mov     dword ptr [rsp+48h+var_28], eax
0x1400282b3  jmp     short loc_1400282F1
0x1400282b5  mov     eax, dword ptr [rsp+48h+var_20+4]
0x1400282b9  mov     ecx, eax
0x1400282bb  and     ecx, 40h
0x1400282be  mov     [rsp+48h+var_28], 0
0x1400282c7  shl     ecx, 2
0x1400282ca  and     eax, 0B0h
0x1400282cf  or      ecx, eax
0x1400282d1  shl     ecx, 3
0x1400282d4  or      ecx, 206h
0x1400282da  mov     dword ptr [rsp+48h+var_28], ecx
0x1400282de  jmp     short loc_1400282F1
0x1400282e0  mov     [rsp+48h+var_28], 0
0x1400282e9  mov     dword ptr [rsp+48h+var_28], 206h
0x1400282f1  mov     rcx, [rbx]
0x1400282f4  add     rbx, 38h ; '8'
0x1400282f8  mov     rax, [rsp+48h+var_28]
0x1400282fd  mov     [rcx], rax
0x140028300  jmp     short loc_14002830C
0x140028302  cmp     qword ptr [rbx], 0
0x140028306  jnz     short loc_140028313
0x140028308  add     rbx, 8
0x14002830c  cmp     rbx, rsi
0x14002830f  jb      short loc_140028302
0x140028311  jmp     short loc_140028356
0x140028313  test    rbx, rbx
0x140028316  jnz     loc_140028231
0x14002831c  jmp     short loc_140028356
0x14002831e  mov     [rsp+48h+var_28], 0
0x140028327  mov     dword ptr [rsp+48h+var_28], 206h
0x14002832f  mov     rax, [rsp+48h+var_28]
0x140028334  mov     rcx, [rbx]
0x140028337  add     rbx, 38h ; '8'
0x14002833b  mov     [rcx], rax
0x14002833e  jmp     short loc_14002834A
0x140028340  cmp     qword ptr [rbx], 0
0x140028344  jnz     short loc_140028351
0x140028346  add     rbx, 8
0x14002834a  cmp     rbx, rsi
0x14002834d  jb      short loc_140028340
0x14002834f  jmp     short loc_140028356
0x140028351  test    rbx, rbx
0x140028354  jnz     short loc_140028334
0x140028356  mov     rcx, [rsp+48h+var_10]
0x14002835b  xor     rcx, rsp; StackCookie
0x14002835e  call    __security_check_cookie
0x140028363  mov     rbx, [rsp+48h+arg_0]
0x140028368  add     rsp, 40h
0x14002836c  pop     rsi
0x14002836d  retn
```
