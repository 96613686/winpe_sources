# MupiTriggerStartProvider

- ea: `0x14001e368`
- end: `0x14001e5a1`
- name: `MupiTriggerStartProvider`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14001e11c`

## callees

- `0x140013330`
- `0x140013de0`
- `0x140013e10`
- `0x14001e368`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001e585`
- `ntoskrnl!KeSetEvent` at `0x14001e585`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001e466`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001e466`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14001e569`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14001e569`
- `ntoskrnl!ZwQueryWnfStateData` at `0x14001e50e`
- `ntoskrnl!ZwQueryWnfStateData` at `0x14001e50e`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14001e53e`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14001e53e`

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
0x14001e368  mov     [rsp-38h+arg_8], rbx
0x14001e36d  push    rbp
0x14001e36e  push    rsi
0x14001e36f  push    rdi
0x14001e370  push    r12
0x14001e372  push    r13
0x14001e374  push    r14
0x14001e376  push    r15
0x14001e378  mov     rbp, rsp
0x14001e37b  sub     rsp, 60h
0x14001e37f  movzx   r14d, word ptr [rcx+48h]
0x14001e384  xor     r13d, r13d
0x14001e387  mov     rbx, [rcx+50h]
0x14001e38b  xorps   xmm0, xmm0
0x14001e38e  xorps   xmm1, xmm1
0x14001e391  mov     [rbp+arg_18], r13d
0x14001e395  mov     r12, r8
0x14001e398  mov     [rbp+arg_0], r13d
0x14001e39c  lea     esi, [r13+1]
0x14001e3a0  mov     r15, rdx
0x14001e3a3  mov     rdi, rcx
0x14001e3a6  movups  xmmword ptr [rbp+String2.Length], xmm0
0x14001e3aa  movups  xmmword ptr [rbp+String1.Length], xmm1
0x14001e3ae  test    r14w, r14w
0x14001e3b2  jz      loc_14001E4BF
0x14001e3b8  test    rbx, rbx
0x14001e3bb  jz      loc_14001E4BF
0x14001e3c1  movzx   edx, r14w
0x14001e3c5  mov     rcx, rbx
0x14001e3c8  mov     eax, edx
0x14001e3ca  shr     rax, 1
0x14001e3cd  mov     r8, rax
0x14001e3d0  jz      short loc_14001E3E1
0x14001e3d2  cmp     [rcx], r13w
0x14001e3d6  jz      short loc_14001E3E6
0x14001e3d8  add     rcx, 2
0x14001e3dc  sub     rax, rsi
0x14001e3df  jnz     short loc_14001E3D2
0x14001e3e1  mov     r8, r13
0x14001e3e4  jmp     short loc_14001E3E9
0x14001e3e6  sub     r8, rax
0x14001e3e9  test    rax, rax
0x14001e3ec  jz      loc_14001E4BF
0x14001e3f2  add     r8, r8
0x14001e3f5  mov     [rbp+String1.Buffer], rbx
0x14001e3f9  cmp     r8, rdx
0x14001e3fc  mov     [rbp+String1.Length], r8w
0x14001e401  mov     [rbp+String1.MaximumLength], r8w
0x14001e406  lea     rax, [r8+2]
0x14001e40a  cmovnb  rax, r8
0x14001e40e  add     rbx, rax
0x14001e411  sub     r14w, ax
0x14001e415  test    r8w, r8w
0x14001e419  jz      short loc_14001E3AE
0x14001e41b  movzx   eax, word ptr [r15]
0x14001e41f  movzx   edx, r8w
0x14001e423  lea     rcx, [rdx+4]
0x14001e427  cmp     rcx, rax
0x14001e42a  ja      short loc_14001E3AE
0x14001e42c  mov     rax, [r15+8]
0x14001e430  cmp     word ptr [rax], 5Ch ; '\'
0x14001e434  jnz     loc_14001E3AE
0x14001e43a  shr     rdx, 1
0x14001e43d  cmp     word ptr [rax+rdx*2+2], 5Ch ; '\'
0x14001e443  jnz     loc_14001E3AE
0x14001e449  add     rax, 2
0x14001e44d  mov     [rbp+String2.Length], r8w
0x14001e452  mov     [rbp+String2.MaximumLength], r8w
0x14001e457  lea     rdx, [rbp+String2]; String2
0x14001e45b  mov     r8b, sil; CaseInSensitive
0x14001e45e  mov     [rbp+String2.Buffer], rax
0x14001e462  lea     rcx, [rbp+String1]; String1
0x14001e466  call    cs:__imp_RtlEqualUnicodeString
0x14001e46d  nop     dword ptr [rax+rax+00h]
0x14001e472  test    al, al
0x14001e474  jz      loc_14001E3AE
0x14001e47a  mov     rcx, rdi
0x14001e47d  call    MupiLockProviderTriggerStartExclusive
0x14001e482  cmp     [rdi+70h], r13
0x14001e486  jnz     short loc_14001E48E
0x14001e488  cmp     dword ptr [rdi+44h], 3
0x14001e48c  jz      short loc_14001E4B2
0x14001e48e  mov     rcx, [rdi+80h]
0x14001e495  test    rcx, rcx
0x14001e498  jz      short loc_14001E4DA
0x14001e49a  mov     rax, ds:0FFFFF78000000008h
0x14001e4a4  sub     rax, rcx
0x14001e4a7  cmp     rax, 11E1A300h
0x14001e4ad  jnb     short loc_14001E4DA
0x14001e4af  mov     sil, r13b
0x14001e4b2  mov     rcx, rdi
0x14001e4b5  call    MupiUnlockProviderTriggerStartExclusive
0x14001e4ba  mov     al, sil
0x14001e4bd  jmp     short loc_14001E4C1
0x14001e4bf  xor     al, al
0x14001e4c1  mov     rbx, [rsp+60h+arg_8]
0x14001e4c9  add     rsp, 60h
0x14001e4cd  pop     r15
0x14001e4cf  pop     r14
0x14001e4d1  pop     r13
0x14001e4d3  pop     r12
0x14001e4d5  pop     rdi
0x14001e4d6  pop     rsi
0x14001e4d7  pop     rbp
0x14001e4d8  retn
0x14001e4da  add     [rdi+70h], rsi
0x14001e4de  mov     rcx, rdi
0x14001e4e1  mov     rbx, [rdi+70h]
0x14001e4e5  call    MupiUnlockProviderTriggerStartExclusive
0x14001e4ea  cmp     rbx, rsi
0x14001e4ed  jnz     loc_14001E591
0x14001e4f3  lea     rax, [rbp+arg_18]
0x14001e4f7  xor     r8d, r8d
0x14001e4fa  mov     [rsp+60h+var_38], rax
0x14001e4ff  lea     r9, [rbp+arg_0]
0x14001e503  xor     edx, edx
0x14001e505  mov     [rsp+60h+var_40], r13
0x14001e50a  lea     rcx, [rdi+60h]
0x14001e50e  call    cs:__imp_ZwQueryWnfStateData
0x14001e515  nop     dword ptr [rax+rax+00h]
0x14001e51a  test    eax, eax
0x14001e51c  js      short loc_14001E579
0x14001e51e  mov     r9d, [rbp+arg_0]
0x14001e522  lea     rax, MupiTriggerStartWnfCallback
0x14001e529  lea     rcx, [rdi+78h]
0x14001e52d  mov     [rsp+60h+var_38], rdi
0x14001e532  mov     r8d, esi
0x14001e535  mov     [rsp+60h+var_40], rax
0x14001e53a  lea     rdx, [rdi+60h]
0x14001e53e  call    cs:__imp_ExSubscribeWnfStateChange
0x14001e545  nop     dword ptr [rax+rax+00h]
0x14001e54a  test    eax, eax
0x14001e54c  js      short loc_14001E579
0x14001e54e  mov     [rsp+60h+var_30], r13d
0x14001e553  lea     rcx, [rdi+58h]
0x14001e557  mov     dword ptr [rsp+60h+var_38], r13d
0x14001e55c  xor     r9d, r9d
0x14001e55f  xor     r8d, r8d
0x14001e562  mov     [rsp+60h+var_40], r13
0x14001e567  xor     edx, edx
0x14001e569  call    cs:__imp_ZwUpdateWnfStateData
0x14001e570  nop     dword ptr [rax+rax+00h]
0x14001e575  test    eax, eax
0x14001e577  jns     short loc_14001E591
0x14001e579  mov     rcx, [rdi+88h]; Event
0x14001e580  xor     r8d, r8d; Wait
0x14001e583  xor     edx, edx; Increment
0x14001e585  call    cs:__imp_KeSetEvent
0x14001e58c  nop     dword ptr [rax+rax+00h]
0x14001e591  mov     rdx, r12
0x14001e594  mov     rcx, rdi
0x14001e597  call    MupiWaitForProviderTriggerStart
0x14001e59c  jmp     loc_14001E4C1
```
