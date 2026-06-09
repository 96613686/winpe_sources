# DfscCopyTargetAccessStatus

- ea: `0x14002184c`
- end: `0x1400219b4`
- name: `DfscCopyTargetAccessStatus`
- size: `360`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140023120`

## callees

- `0x1400025a0`
- `0x140002fcc`
- `0x1400119f8`
- `0x140020fd0`
- `0x140021820`
- `0x14002184c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002193a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002193a`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall DfscCopyTargetAccessStatus(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  PDEVICE_OBJECT v6; // rcx
  PDEVICE_OBJECT *result; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 CurrentTarget; // rsi
  __int64 v14; // rcx
  __int64 v15; // rbp

  v4 = *(_QWORD *)(a1 + 16);
  v5 = *(_QWORD *)(a2 + 16);
  if ( v5 == v4 )
  {
    v6 = WPP_GLOBAL_Control;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      v8 = 34;
      return (PDEVICE_OBJECT *)WPP_SF_qq(
                                 v6->AttachedDevice,
                                 v8,
                                 WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
                                 a2,
                                 a1);
    }
  }
  else if ( *(_DWORD *)(v5 + 8) == *(_DWORD *)(v4 + 8) )
  {
    if ( *(_WORD *)(v5 + 24) && *(_WORD *)(v4 + 24) )
    {
      DfscReferralIterateInitialize(a1);
      while ( !(unsigned int)DfscReferralIterate(v10, v9, v11, v12) )
      {
        CurrentTarget = DfscReferralGetCurrentTarget(a1);
        if ( *(_DWORD *)(CurrentTarget + 8) != -1 )
        {
          DfscReferralIterateInitialize(a2);
          while ( !(unsigned int)DfscReferralIterate(v14, v9, v11, v12) )
          {
            v15 = DfscReferralGetCurrentTarget(a2);
            if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(CurrentTarget + 80), (PCUNICODE_STRING)(v15 + 80), 1u) )
            {
              *(_DWORD *)(v15 + 8) = *(_DWORD *)(CurrentTarget + 8);
              break;
            }
            v14 = a2;
          }
        }
        v10 = a1;
      }
      return (PDEVICE_OBJECT *)DfscReferralIterateInitialize(a2);
    }
    else
    {
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
      {
        return (PDEVICE_OBJECT *)WPP_SF_dd(
                                   WPP_GLOBAL_Control->AttachedDevice,
                                   36,
                                   WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
                                   *(unsigned __int16 *)(v5 + 24),
                                   *(unsigned __int16 *)(v4 + 24));
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      v8 = 35;
      return (PDEVICE_OBJECT *)WPP_SF_qq(
                                 v6->AttachedDevice,
                                 v8,
                                 WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
                                 a2,
                                 a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002184c  push    rbx
0x14002184e  push    rbp
0x14002184f  push    rsi
0x140021850  push    rdi
0x140021851  push    r14
0x140021853  sub     rsp, 30h
0x140021857  mov     rbx, rdx
0x14002185a  mov     rdi, rcx
0x14002185d  mov     rcx, [rcx+10h]
0x140021861  mov     rdx, [rdx+10h]
0x140021865  cmp     rdx, rcx
0x140021868  jnz     short loc_1400218B0
0x14002186a  mov     rcx, cs:WPP_GLOBAL_Control
0x140021871  lea     rax, WPP_GLOBAL_Control
0x140021878  cmp     rcx, rax
0x14002187b  jz      loc_1400219A8
0x140021881  test    dword ptr [rcx+2Ch], 200000h
0x140021888  jz      loc_1400219A8
0x14002188e  mov     edx, 22h ; '"'
0x140021893  mov     rcx, [rcx+18h]
0x140021897  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14002189e  mov     r9, rbx
0x1400218a1  mov     [rsp+58h+var_38], rdi
0x1400218a6  call    WPP_SF_qq
0x1400218ab  jmp     loc_1400219A8
0x1400218b0  mov     eax, [rcx+8]
0x1400218b3  cmp     [rdx+8], eax
0x1400218b6  jz      short loc_1400218E3
0x1400218b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400218bf  lea     rax, WPP_GLOBAL_Control
0x1400218c6  cmp     rcx, rax
0x1400218c9  jz      loc_1400219A8
0x1400218cf  test    dword ptr [rcx+2Ch], 100000h
0x1400218d6  jz      loc_1400219A8
0x1400218dc  mov     edx, 23h ; '#'
0x1400218e1  jmp     short loc_140021893
0x1400218e3  movzx   r8d, word ptr [rdx+18h]
0x1400218e8  xor     r14d, r14d
0x1400218eb  test    r8w, r8w
0x1400218ef  jz      short loc_14002196B
0x1400218f1  cmp     [rcx+18h], r14w
0x1400218f6  jz      short loc_14002196B
0x1400218f8  mov     rcx, rdi
0x1400218fb  call    DfscReferralIterateInitialize
0x140021900  jmp     short loc_140021958
0x140021902  mov     rcx, rdi
0x140021905  call    DfscReferralGetCurrentTarget
0x14002190a  mov     rsi, rax
0x14002190d  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x140021911  jz      short loc_140021955
0x140021913  mov     rcx, rbx
0x140021916  call    DfscReferralIterateInitialize
0x14002191b  call    DfscReferralIterate
0x140021920  test    eax, eax
0x140021922  jnz     short loc_140021955
0x140021924  mov     rcx, rbx
0x140021927  call    DfscReferralGetCurrentTarget
0x14002192c  lea     rcx, [rsi+50h]; String1
0x140021930  mov     r8b, 1; CaseInSensitive
0x140021933  mov     rbp, rax
0x140021936  lea     rdx, [rax+50h]; String2
0x14002193a  call    cs:__imp_RtlCompareUnicodeString
0x140021941  nop     dword ptr [rax+rax+00h]
0x140021946  test    eax, eax
0x140021948  jz      short loc_14002194F
0x14002194a  mov     rcx, rbx
0x14002194d  jmp     short loc_14002191B
0x14002194f  mov     eax, [rsi+8]
0x140021952  mov     [rbp+8], eax
0x140021955  mov     rcx, rdi
0x140021958  call    DfscReferralIterate
0x14002195d  test    eax, eax
0x14002195f  jz      short loc_140021902
0x140021961  mov     rcx, rbx
0x140021964  call    DfscReferralIterateInitialize
0x140021969  jmp     short loc_1400219A8
0x14002196b  mov     r10, cs:WPP_GLOBAL_Control
0x140021972  lea     rax, WPP_GLOBAL_Control
0x140021979  cmp     r10, rax
0x14002197c  jz      short loc_1400219A8
0x14002197e  test    dword ptr [r10+2Ch], 200000h
0x140021986  jz      short loc_1400219A8
0x140021988  movzx   eax, word ptr [rcx+18h]
0x14002198c  mov     r9d, r8d
0x14002198f  mov     rcx, [r10+18h]
0x140021993  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x14002199a  mov     edx, 24h ; '$'
0x14002199f  mov     dword ptr [rsp+58h+var_38], eax
0x1400219a3  call    WPP_SF_dd
0x1400219a8  add     rsp, 30h
0x1400219ac  pop     r14
0x1400219ae  pop     rdi
0x1400219af  pop     rsi
0x1400219b0  pop     rbp
0x1400219b1  pop     rbx
0x1400219b2  retn
```
