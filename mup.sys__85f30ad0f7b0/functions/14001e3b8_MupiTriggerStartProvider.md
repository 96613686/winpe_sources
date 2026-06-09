# MupiTriggerStartProvider

- ea: `0x14001e3b8`
- end: `0x14001e5f1`
- name: `MupiTriggerStartProvider`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14001e16c`

## callees

- `0x140013380`
- `0x140013e30`
- `0x140013e60`
- `0x14001e3b8`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001e5d5`
- `ntoskrnl!KeSetEvent` at `0x14001e5d5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001e4b6`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001e4b6`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14001e5b9`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14001e5b9`
- `ntoskrnl!ZwQueryWnfStateData` at `0x14001e55e`
- `ntoskrnl!ZwQueryWnfStateData` at `0x14001e55e`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14001e58e`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14001e58e`

## pseudocode

```c
char __fastcall MupiTriggerStartProvider(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  unsigned __int16 v3; // r14
  WCHAR *v4; // rbx
  char v6; // si
  WCHAR *v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rax
  _WORD *v14; // rax
  __int64 v15; // rcx
  __int64 v17; // rbx
  UNICODE_STRING String2; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+40h] BYREF
  int v21; // [rsp+B8h] [rbp+58h] BYREF

  v3 = *(_WORD *)(a1 + 72);
  v4 = *(WCHAR **)(a1 + 80);
  v21 = 0;
  v20 = 0;
  v6 = 1;
  String2 = 0;
  String1 = 0;
  while ( 1 )
  {
    if ( !v3 || !v4 )
      return 0;
    v9 = v4;
    v10 = (unsigned __int64)v3 >> 1;
    if ( v10 )
    {
      while ( *v9 )
      {
        ++v9;
        if ( !--v10 )
          goto LABEL_7;
      }
      v11 = ((unsigned __int64)v3 >> 1) - v10;
    }
    else
    {
LABEL_7:
      v11 = 0;
    }
    if ( !v10 )
      return 0;
    v12 = 2 * v11;
    String1.Buffer = v4;
    String1.Length = v12;
    String1.MaximumLength = v12;
    v13 = v12 + 2;
    if ( v12 >= v3 )
      v13 = v12;
    v4 = (WCHAR *)((char *)v4 + v13);
    v3 -= v13;
    if ( (_WORD)v12 )
    {
      if ( (unsigned __int64)(unsigned __int16)v12 + 4 <= *a2 )
      {
        v14 = (_WORD *)*((_QWORD *)a2 + 1);
        if ( *v14 == 92 && v14[((unsigned __int64)(unsigned __int16)v12 >> 1) + 1] == 92 )
        {
          String2.Length = v12;
          String2.MaximumLength = v12;
          String2.Buffer = v14 + 1;
          if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
            break;
        }
      }
    }
  }
  MupiLockProviderTriggerStartExclusive(a1);
  if ( !*(_QWORD *)(a1 + 112) && *(_DWORD *)(a1 + 68) == 3 )
    goto LABEL_22;
  v15 = *(_QWORD *)(a1 + 128);
  if ( v15 && (unsigned __int64)(MEMORY[0xFFFFF78000000008] - v15) < 0x11E1A300 )
  {
    v6 = 0;
LABEL_22:
    MupiUnlockProviderTriggerStartExclusive(a1);
    return v6;
  }
  v17 = ++*(_QWORD *)(a1 + 112);
  MupiUnlockProviderTriggerStartExclusive(a1);
  if ( v17 == 1
    && ((int)ZwQueryWnfStateData(a1 + 96, 0, 0, &v20, 0, &v21) < 0
     || (int)ExSubscribeWnfStateChange(a1 + 120, a1 + 96, 1, v20, MupiTriggerStartWnfCallback, a1) < 0
     || (int)ZwUpdateWnfStateData(a1 + 88, 0, 0, 0, 0, 0, 0) < 0) )
  {
    KeSetEvent(*(PRKEVENT *)(a1 + 136), 0, 0);
  }
  return MupiWaitForProviderTriggerStart(a1, a3);
}

```

## disassembly

```asm
0x14001e3b8  mov     [rsp-38h+arg_8], rbx
0x14001e3bd  push    rbp
0x14001e3be  push    rsi
0x14001e3bf  push    rdi
0x14001e3c0  push    r12
0x14001e3c2  push    r13
0x14001e3c4  push    r14
0x14001e3c6  push    r15
0x14001e3c8  mov     rbp, rsp
0x14001e3cb  sub     rsp, 60h
0x14001e3cf  movzx   r14d, word ptr [rcx+48h]
0x14001e3d4  xor     r13d, r13d
0x14001e3d7  mov     rbx, [rcx+50h]
0x14001e3db  xorps   xmm0, xmm0
0x14001e3de  xorps   xmm1, xmm1
0x14001e3e1  mov     [rbp+arg_18], r13d
0x14001e3e5  mov     r12, r8
0x14001e3e8  mov     [rbp+arg_0], r13d
0x14001e3ec  lea     esi, [r13+1]
0x14001e3f0  mov     r15, rdx
0x14001e3f3  mov     rdi, rcx
0x14001e3f6  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001e3fa  movups  xmmword ptr [rbp+String1.Length], xmm1
0x14001e3fe  test    r14w, r14w
0x14001e402  jz      loc_14001E50F
0x14001e408  test    rbx, rbx
0x14001e40b  jz      loc_14001E50F
0x14001e411  movzx   edx, r14w
0x14001e415  mov     rcx, rbx
0x14001e418  mov     eax, edx
0x14001e41a  shr     rax, 1
0x14001e41d  mov     r8, rax
0x14001e420  jz      short loc_14001E431
0x14001e422  cmp     [rcx], r13w
0x14001e426  jz      short loc_14001E436
0x14001e428  add     rcx, 2
0x14001e42c  sub     rax, rsi
0x14001e42f  jnz     short loc_14001E422
0x14001e431  mov     r8, r13
0x14001e434  jmp     short loc_14001E439
0x14001e436  sub     r8, rax
0x14001e439  test    rax, rax
0x14001e43c  jz      loc_14001E50F
0x14001e442  add     r8, r8
0x14001e445  mov     [rbp+String1.Buffer], rbx
0x14001e449  cmp     r8, rdx
0x14001e44c  mov     [rbp+String1.Length], r8w
0x14001e451  mov     [rbp+String1.MaximumLength], r8w
0x14001e456  lea     rax, [r8+2]
0x14001e45a  cmovnb  rax, r8
0x14001e45e  add     rbx, rax
0x14001e461  sub     r14w, ax
0x14001e465  test    r8w, r8w
0x14001e469  jz      short loc_14001E3FE
0x14001e46b  movzx   eax, word ptr [r15]
0x14001e46f  movzx   edx, r8w
0x14001e473  lea     rcx, [rdx+4]
0x14001e477  cmp     rcx, rax
0x14001e47a  ja      short loc_14001E3FE
0x14001e47c  mov     rax, [r15+8]
0x14001e480  cmp     word ptr [rax], 5Ch ; '\'
0x14001e484  jnz     loc_14001E3FE
0x14001e48a  shr     rdx, 1
0x14001e48d  cmp     word ptr [rax+rdx*2+2], 5Ch ; '\'
0x14001e493  jnz     loc_14001E3FE
0x14001e499  add     rax, 2
0x14001e49d  mov     [rbp+String2.Length], r8w
0x14001e4a2  mov     [rbp+String2.MaximumLength], r8w
0x14001e4a7  lea     rdx, [rbp+String2]; String2
0x14001e4ab  mov     r8b, sil; CaseInSensitive
0x14001e4ae  mov     [rbp+String2.Buffer], rax
0x14001e4b2  lea     rcx, [rbp+String1]; String1
0x14001e4b6  call    cs:__imp_RtlEqualUnicodeString
0x14001e4bd  nop     dword ptr [rax+rax+00h]
0x14001e4c2  test    al, al
0x14001e4c4  jz      loc_14001E3FE
0x14001e4ca  mov     rcx, rdi
0x14001e4cd  call    MupiLockProviderTriggerStartExclusive
0x14001e4d2  cmp     [rdi+70h], r13
0x14001e4d6  jnz     short loc_14001E4DE
0x14001e4d8  cmp     dword ptr [rdi+44h], 3
0x14001e4dc  jz      short loc_14001E502
0x14001e4de  mov     rcx, [rdi+80h]
0x14001e4e5  test    rcx, rcx
0x14001e4e8  jz      short loc_14001E52A
0x14001e4ea  mov     rax, ds:0FFFFF78000000008h
0x14001e4f4  sub     rax, rcx
0x14001e4f7  cmp     rax, 11E1A300h
0x14001e4fd  jnb     short loc_14001E52A
0x14001e4ff  mov     sil, r13b
0x14001e502  mov     rcx, rdi
0x14001e505  call    MupiUnlockProviderTriggerStartExclusive
0x14001e50a  mov     al, sil
0x14001e50d  jmp     short loc_14001E511
0x14001e50f  xor     al, al
0x14001e511  mov     rbx, [rsp+60h+arg_8]
0x14001e519  add     rsp, 60h
0x14001e51d  pop     r15
0x14001e51f  pop     r14
0x14001e521  pop     r13
0x14001e523  pop     r12
0x14001e525  pop     rdi
0x14001e526  pop     rsi
0x14001e527  pop     rbp
0x14001e528  retn
0x14001e52a  add     [rdi+70h], rsi
0x14001e52e  mov     rcx, rdi
0x14001e531  mov     rbx, [rdi+70h]
0x14001e535  call    MupiUnlockProviderTriggerStartExclusive
0x14001e53a  cmp     rbx, rsi
0x14001e53d  jnz     loc_14001E5E1
0x14001e543  lea     rax, [rbp+arg_18]
0x14001e547  xor     r8d, r8d
0x14001e54a  mov     [rsp+60h+var_38], rax
0x14001e54f  lea     r9, [rbp+arg_0]
0x14001e553  xor     edx, edx
0x14001e555  mov     [rsp+60h+var_40], r13
0x14001e55a  lea     rcx, [rdi+60h]
0x14001e55e  call    cs:__imp_ZwQueryWnfStateData
0x14001e565  nop     dword ptr [rax+rax+00h]
0x14001e56a  test    eax, eax
0x14001e56c  js      short loc_14001E5C9
0x14001e56e  mov     r9d, [rbp+arg_0]
0x14001e572  lea     rax, MupiTriggerStartWnfCallback
0x14001e579  lea     rcx, [rdi+78h]
0x14001e57d  mov     [rsp+60h+var_38], rdi
0x14001e582  mov     r8d, esi
0x14001e585  mov     [rsp+60h+var_40], rax
0x14001e58a  lea     rdx, [rdi+60h]
0x14001e58e  call    cs:__imp_ExSubscribeWnfStateChange
0x14001e595  nop     dword ptr [rax+rax+00h]
0x14001e59a  test    eax, eax
0x14001e59c  js      short loc_14001E5C9
0x14001e59e  mov     [rsp+60h+var_30], r13d
0x14001e5a3  lea     rcx, [rdi+58h]
0x14001e5a7  mov     dword ptr [rsp+60h+var_38], r13d
0x14001e5ac  xor     r9d, r9d
0x14001e5af  xor     r8d, r8d
0x14001e5b2  mov     [rsp+60h+var_40], r13
0x14001e5b7  xor     edx, edx
0x14001e5b9  call    cs:__imp_ZwUpdateWnfStateData
0x14001e5c0  nop     dword ptr [rax+rax+00h]
0x14001e5c5  test    eax, eax
0x14001e5c7  jns     short loc_14001E5E1
0x14001e5c9  mov     rcx, [rdi+88h]; Event
0x14001e5d0  xor     r8d, r8d; Wait
0x14001e5d3  xor     edx, edx; Increment
0x14001e5d5  call    cs:__imp_KeSetEvent
0x14001e5dc  nop     dword ptr [rax+rax+00h]
0x14001e5e1  mov     rdx, r12
0x14001e5e4  mov     rcx, rdi
0x14001e5e7  call    MupiWaitForProviderTriggerStart
0x14001e5ec  jmp     loc_14001E511
```
