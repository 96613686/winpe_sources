# SmbCeUpdateServerAvailability

- ea: `0x140094fe0`
- end: `0x140095278`
- name: `SmbCeUpdateServerAvailability`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002d150`
- `0x14003acec`

## callees

- `0x14004c48c`
- `0x14004c538`
- `0x140094fe0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14009504e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14009504e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140095139`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140095139`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400950c8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400950c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009525a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009525a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140095034`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140095034`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009524e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14009524e`
- `ntoskrnl!ExAllocatePool2` at `0x14009510a`
- `ntoskrnl!ExAllocatePool2` at `0x14009510a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400950ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009519d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400950ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009519d`

## pseudocode

```c
void __fastcall SmbCeUpdateServerAvailability(__int64 *a1, const UNICODE_STRING *a2, int a3, int a4)
{
  __int64 *v4; // r14
  int v5; // r12d
  __int64 v8; // r13
  __int64 v9; // rsi
  __int64 v10; // rbx
  UNICODE_STRING *v11; // rdi
  __int64 v12; // rax
  UNICODE_STRING *Buffer; // rsi
  wchar_t *v14; // rsi
  UNICODE_STRING *Pool2; // rax
  UNICODE_STRING *v16; // rbx
  int v17; // edx
  int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // rax
  wchar_t *v21; // rcx
  int v22; // r8d
  __int64 v23; // [rsp+A0h] [rbp+8h]

  v4 = a1;
  v5 = a4;
  if ( !a1 )
    v4 = MRxSmbHostUnavailableServers;
  if ( !a4 )
    v5 = 1;
  v8 = MEMORY[0xFFFFF78000000320];
  v9 = 30 * SmbCeTicksPerSecond;
  v23 = 30 * SmbCeTicksPerSecond;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 2), 1u);
  v10 = MEMORY[0xFFFFF78000000320];
  v11 = (UNICODE_STRING *)*v4;
  if ( (__int64 *)*v4 == v4 )
  {
LABEL_13:
    v14 = (wchar_t *)(v8 + v9);
    goto LABEL_14;
  }
  while ( 1 )
  {
    if ( v10 > (__int64)&v11[2].Buffer[300 * SmbCeTicksPerSecond] )
    {
      v12 = *(_QWORD *)&v11->Length;
      if ( *(UNICODE_STRING **)(*(_QWORD *)&v11->Length + 8LL) != v11 )
        goto LABEL_17;
      Buffer = (UNICODE_STRING *)v11->Buffer;
      if ( *(UNICODE_STRING **)&Buffer->Length != v11 )
        goto LABEL_17;
      *(_QWORD *)&Buffer->Length = v12;
      *(_QWORD *)(v12 + 8) = Buffer;
      ExFreePoolWithTag(v11, 0x6D537355u);
      v11 = Buffer;
      goto LABEL_11;
    }
    if ( !RtlCompareUnicodeString(v11 + 1, a2, 1u) )
      break;
LABEL_11:
    v11 = *(UNICODE_STRING **)&v11->Length;
    if ( v11 == (UNICODE_STRING *)v4 )
    {
      v9 = v23;
      goto LABEL_13;
    }
  }
  v14 = (wchar_t *)(v8 + v23);
  if ( v11 )
  {
    if ( a3 >= 0 )
    {
      v20 = *(_QWORD *)&v11->Length;
      if ( *(UNICODE_STRING **)(*(_QWORD *)&v11->Length + 8LL) == v11 )
      {
        v21 = v11->Buffer;
        if ( *(UNICODE_STRING **)v21 == v11 )
        {
          *(_QWORD *)v21 = v20;
          *(_QWORD *)(v20 + 8) = v21;
          ExFreePoolWithTag(v11, 0x6D537355u);
          goto LABEL_31;
        }
      }
LABEL_17:
      __fastfail(3u);
    }
    *(_DWORD *)(&v11[2].MaximumLength + 1) += v5;
    v22 = *(_DWORD *)(&v11[2].MaximumLength + 1);
    v11[2].Buffer = v14;
    *(_DWORD *)&v11[2].Length = a3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_ZdPD(WPP_GLOBAL_Control->AttachedDevice, 11, v22, (_DWORD)a2, v22, v4[15], a3);
    }
    goto LABEL_31;
  }
LABEL_14:
  if ( a3 < 0 )
  {
    Pool2 = (UNICODE_STRING *)ExAllocatePool2(258, a2->Length + 48LL, 1834185557);
    v16 = Pool2;
    if ( Pool2 )
    {
      Pool2[1].Buffer = &Pool2[3].Length;
      Pool2[1].MaximumLength = a2->Length;
      RtlCopyUnicodeString(Pool2 + 1, a2);
      *(_DWORD *)(&v16[2].MaximumLength + 1) = v5;
      *(_DWORD *)&v16[2].Length = a3;
      v16[2].Buffer = v14;
      v19 = *v4;
      if ( *(__int64 **)(*v4 + 8) != v4 )
        goto LABEL_17;
      *(_QWORD *)&v16->Length = v19;
      v16->Buffer = (wchar_t *)v4;
      *(_QWORD *)(v19 + 8) = v16;
      *v4 = (__int64)v16;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_ZPD(WPP_GLOBAL_Control->AttachedDevice, v17, v18, (_DWORD)a2, v4[15], a3);
      }
    }
  }
LABEL_31:
  ExReleaseResourceLite((PERESOURCE)(v4 + 2));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140094fe0  push    rbx
0x140094fe2  push    rbp
0x140094fe3  push    rsi
0x140094fe4  push    rdi
0x140094fe5  push    r12
0x140094fe7  push    r13
0x140094fe9  push    r14
0x140094feb  push    r15
0x140094fed  sub     rsp, 58h
0x140094ff1  test    rcx, rcx
0x140094ff4  lea     rax, MRxSmbHostUnavailableServers
0x140094ffb  mov     r14, rcx
0x140094ffe  mov     r12d, r9d
0x140095001  cmovz   r14, rax
0x140095005  mov     rbx, 0FFFFF78000000320h
0x14009500f  test    r9d, r9d
0x140095012  mov     eax, 1
0x140095017  mov     ebp, r8d
0x14009501a  mov     r15, rdx
0x14009501d  cmovz   r12d, eax
0x140095021  mov     r13, [rbx]
0x140095024  imul    rsi, cs:SmbCeTicksPerSecond, 1Eh
0x14009502c  mov     [rsp+98h+arg_0], rsi
0x140095034  call    cs:__imp_KeEnterCriticalRegion
0x14009503b  nop     dword ptr [rax+rax+00h]
0x140095040  lea     rax, [r14+10h]
0x140095044  mov     dl, 1; Wait
0x140095046  mov     rcx, rax; Resource
0x140095049  mov     [rsp+98h+Resource], rax
0x14009504e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140095055  nop     dword ptr [rax+rax+00h]
0x14009505a  mov     rbx, [rbx]
0x14009505d  mov     rdi, [r14]
0x140095060  cmp     rdi, r14
0x140095063  jz      loc_1400950EC
0x140095069  nop     dword ptr [rax+00000000h]
0x140095070  imul    rax, cs:SmbCeTicksPerSecond, 258h
0x14009507b  add     rax, [rdi+28h]
0x14009507f  cmp     rbx, rax
0x140095082  jle     short loc_1400950BE
0x140095084  mov     rax, [rdi]
0x140095087  cmp     [rax+8], rdi
0x14009508b  jnz     loc_14009515D
0x140095091  mov     rsi, [rdi+8]
0x140095095  cmp     [rsi], rdi
0x140095098  jnz     loc_14009515D
0x14009509e  mov     [rsi], rax
0x1400950a1  mov     edx, 6D537355h; Tag
0x1400950a6  mov     rcx, rdi; P
0x1400950a9  mov     [rax+8], rsi
0x1400950ad  call    cs:__imp_ExFreePoolWithTag
0x1400950b4  nop     dword ptr [rax+rax+00h]
0x1400950b9  mov     rdi, rsi
0x1400950bc  jmp     short loc_1400950DC
0x1400950be  lea     rcx, [rdi+10h]; String1
0x1400950c2  mov     r8b, 1; CaseInSensitive
0x1400950c5  mov     rdx, r15; String2
0x1400950c8  call    cs:__imp_RtlCompareUnicodeString
0x1400950cf  nop     dword ptr [rax+rax+00h]
0x1400950d4  test    eax, eax
0x1400950d6  jz      loc_140095164
0x1400950dc  mov     rdi, [rdi]
0x1400950df  cmp     rdi, r14
0x1400950e2  jnz     short loc_140095070
0x1400950e4  mov     rsi, [rsp+98h+arg_0]
0x1400950ec  add     rsi, r13
0x1400950ef  test    ebp, ebp
0x1400950f1  jns     loc_140095249
0x1400950f7  movzx   edx, word ptr [r15]
0x1400950fb  mov     ecx, 102h
0x140095100  add     rdx, 30h ; '0'
0x140095104  mov     r8d, 6D537355h
0x14009510a  call    cs:__imp_ExAllocatePool2
0x140095111  nop     dword ptr [rax+rax+00h]
0x140095116  mov     rbx, rax
0x140095119  test    rax, rax
0x14009511c  jz      loc_140095249
0x140095122  lea     rcx, [rax+30h]
0x140095126  mov     rdx, r15; SourceString
0x140095129  mov     [rax+18h], rcx
0x14009512d  movzx   ecx, word ptr [r15]
0x140095131  mov     [rax+12h], cx
0x140095135  lea     rcx, [rax+10h]; DestinationString
0x140095139  call    cs:__imp_RtlCopyUnicodeString
0x140095140  nop     dword ptr [rax+rax+00h]
0x140095145  mov     [rbx+24h], r12d
0x140095149  mov     [rbx+20h], ebp
0x14009514c  mov     [rbx+28h], rsi
0x140095150  mov     rax, [r14]
0x140095153  cmp     [rax+8], r14
0x140095157  jz      loc_140095202
0x14009515d  mov     ecx, 3
0x140095162  int     29h; Win8: RtlFailFast(ecx)
0x140095164  mov     rsi, [rsp+98h+arg_0]
0x14009516c  add     rsi, r13
0x14009516f  test    rdi, rdi
0x140095172  jz      loc_1400950EF
0x140095178  test    ebp, ebp
0x14009517a  js      short loc_1400951AE
0x14009517c  mov     rax, [rdi]
0x14009517f  cmp     [rax+8], rdi
0x140095183  jnz     short loc_14009515D
0x140095185  mov     rcx, [rdi+8]
0x140095189  cmp     [rcx], rdi
0x14009518c  jnz     short loc_14009515D
0x14009518e  mov     [rcx], rax
0x140095191  mov     edx, 6D537355h; Tag
0x140095196  mov     [rax+8], rcx
0x14009519a  mov     rcx, rdi; P
0x14009519d  call    cs:__imp_ExFreePoolWithTag
0x1400951a4  nop     dword ptr [rax+rax+00h]
0x1400951a9  jmp     loc_140095249
0x1400951ae  add     [rdi+24h], r12d
0x1400951b2  mov     r8d, [rdi+24h]
0x1400951b6  mov     [rdi+28h], rsi
0x1400951ba  mov     [rdi+20h], ebp
0x1400951bd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400951c4  lea     rax, WPP_GLOBAL_Control
0x1400951cb  cmp     rcx, rax
0x1400951ce  jz      short loc_140095249
0x1400951d0  mov     eax, [rcx+2Ch]
0x1400951d3  test    al, 1
0x1400951d5  jz      short loc_140095249
0x1400951d7  cmp     byte ptr [rcx+29h], 1
0x1400951db  jb      short loc_140095249
0x1400951dd  mov     rax, [r14+78h]
0x1400951e1  mov     edx, 0Bh
0x1400951e6  mov     rcx, [rcx+18h]
0x1400951ea  mov     r9, r15
0x1400951ed  mov     [rsp+98h+var_68], ebp
0x1400951f1  mov     [rsp+98h+var_70], rax
0x1400951f6  mov     dword ptr [rsp+98h+var_78], r8d
0x1400951fb  call    WPP_SF_ZdPD
0x140095200  jmp     short loc_140095249
0x140095202  mov     [rbx], rax
0x140095205  mov     [rbx+8], r14
0x140095209  mov     [rax+8], rbx
0x14009520d  mov     [r14], rbx
0x140095210  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140095217  lea     rax, WPP_GLOBAL_Control
0x14009521e  cmp     rcx, rax
0x140095221  jz      short loc_140095249
0x140095223  mov     eax, [rcx+2Ch]
0x140095226  test    al, 1
0x140095228  jz      short loc_140095249
0x14009522a  cmp     byte ptr [rcx+29h], 1
0x14009522e  jb      short loc_140095249
0x140095230  mov     rax, [r14+78h]
0x140095234  mov     r9, r15
0x140095237  mov     rcx, [rcx+18h]
0x14009523b  mov     dword ptr [rsp+98h+var_70], ebp
0x14009523f  mov     [rsp+98h+var_78], rax
0x140095244  call    WPP_SF_ZPD
0x140095249  mov     rcx, [rsp+98h+Resource]; Resource
0x14009524e  call    cs:__imp_ExReleaseResourceLite
0x140095255  nop     dword ptr [rax+rax+00h]
0x14009525a  call    cs:__imp_KeLeaveCriticalRegion
0x140095261  nop     dword ptr [rax+rax+00h]
0x140095266  add     rsp, 58h
0x14009526a  pop     r15
0x14009526c  pop     r14
0x14009526e  pop     r13
0x140095270  pop     r12
0x140095272  pop     rdi
0x140095273  pop     rsi
0x140095274  pop     rbp
0x140095275  pop     rbx
0x140095276  retn
```
