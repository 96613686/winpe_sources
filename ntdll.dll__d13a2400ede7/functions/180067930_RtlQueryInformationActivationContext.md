# RtlQueryInformationActivationContext

- ea: `0x180067930`
- end: `0x180067f59`
- name: `RtlQueryInformationActivationContext`
- size: `1577`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800036ec`
- `0x180067570`
- `0x1800685a0`
- `0x1800e7e20`

## callees

- `0x18001a080`
- `0x1800254d0`
- `0x1800259ec`
- `0x180067930`
- `0x1800681b0`
- `0x18006dea0`
- `0x1800709e0`
- `0x1800c0568`
- `0x1800e2624`
- `0x1800e50d8`
- `0x180100bac`
- `0x180106de8`
- `0x1801108cc`
- `0x1801115b4`

## string_xrefs

- `0x180067d21`: `SXS: %s() - Caller passed meaningless flags/class combination (0x%08lx/0x%08lx)\n`
- `0x180067db3`: `SXS: %s() - Caller asked to use activation context from address in .dll but passed NULL\n`
- `0x180067de2`: `SXS: %s() - Caller passed invalid address, not in any .dll (%p)\n`

## pseudocode

```c
__int64 __fastcall RtlQueryInformationActivationContext(
        int a1,
        struct _ACTIVATION_CONTEXT *a2,
        unsigned int *a3,
        int a4,
        __int64 a5,
        unsigned __int64 a6,
        _QWORD *a7)
{
  unsigned int *v8; // r11
  struct _ACTIVATION_CONTEXT *ActivationContext; // rdi
  int LoadedDllByHandle; // ebx
  _RTL_ACTIVATION_CONTEXT_STACK_FRAME *ActiveFrame; // rax
  const char *v13; // r10
  __int64 v14; // rcx
  const char *v15; // rdx
  const char *v16; // rax
  int v17; // ecx
  int InformationActivationContextBasicInformation; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // ecx
  PVOID v23; // rax
  const char *v25; // [rsp+48h] [rbp-70h] BYREF
  __int64 v26; // [rsp+50h] [rbp-68h]
  __int64 v27; // [rsp+58h] [rbp-60h] BYREF
  int v28; // [rsp+60h] [rbp-58h]
  PVOID BaseOfImage; // [rsp+68h] [rbp-50h] BYREF
  __int128 v30; // [rsp+70h] [rbp-48h] BYREF
  __int128 v31; // [rsp+80h] [rbp-38h]

  v8 = a3;
  ActivationContext = a2;
  v30 = 0;
  v31 = 0;
  LODWORD(v25) = 0;
  v27 = 0;
  DWORD2(v31) = 4;
  if ( a7 )
    *a7 = 0;
  if ( (a1 & 0x3FFFFFF8) != 0 )
    goto LABEL_70;
  if ( a1 < 0 && (((a4 - 1) & 0xFFFFFFFA) != 0 || a4 == 2) )
  {
    DbgPrintEx(
      51,
      0,
      "SXS: %s() - Caller passed meaningless flags/class combination (0x%08lx/0x%08lx)\n",
      "RtlQueryInformationActivationContext",
      a1,
      a4);
    goto LABEL_72;
  }
  if ( (unsigned int)(a4 - 1) > 6 )
  {
    DbgPrintEx(
      51,
      0,
      "SXS: %s() - caller asked for unknown information class %lu\n",
      "RtlQueryInformationActivationContext",
      a4);
    LoadedDllByHandle = -1073741583;
    goto LABEL_101;
  }
  if ( a6 )
  {
    if ( !a5 )
    {
      DbgPrintEx(
        51,
        0,
        "SXS: %s() - caller passed nonzero buffer length but NULL buffer pointer\n",
        "RtlQueryInformationActivationContext");
      LoadedDllByHandle = -1073741582;
      goto LABEL_101;
    }
  }
  else if ( !a7 )
  {
    DbgPrintEx(
      51,
      0,
      "SXS: %s() - caller supplied no buffer to populate and no place to return required byte count\n",
      "RtlQueryInformationActivationContext");
    LoadedDllByHandle = -1073741580;
    goto LABEL_101;
  }
  if ( (a1 & 7) == 0 )
    goto LABEL_15;
  if ( (a1 & 7) == 1 )
  {
    if ( !a2 )
    {
      ActiveFrame = NtCurrentTeb()->ActivationContextStackPointer->ActiveFrame;
      if ( ActiveFrame )
        ActivationContext = ActiveFrame->ActivationContext;
      goto LABEL_15;
    }
    DbgPrintEx(
      51,
      0,
      "SXS: %s() - caller asked to use active activation context but passed %p\n",
      "RtlQueryInformationActivationContext",
      a2);
LABEL_46:
    LoadedDllByHandle = -1073741584;
    goto LABEL_101;
  }
  if ( (a1 & 7) != 2 )
  {
    if ( (a1 & 7) == 4 )
    {
      BaseOfImage = 0;
      if ( !a2 )
      {
        DbgPrintEx(
          51,
          0,
          "SXS: %s() - Caller asked to use activation context from address in .dll but passed NULL\n",
          "RtlQueryInformationActivationContext");
        goto LABEL_46;
      }
      v23 = RtlPcToFileHeader(a2, &BaseOfImage);
      BaseOfImage = v23;
      if ( !v23 )
      {
        DbgPrintEx(
          51,
          0,
          "SXS: %s() - Caller passed invalid address, not in any .dll (%p)\n",
          "RtlQueryInformationActivationContext",
          ActivationContext);
        LoadedDllByHandle = -1073741515;
        goto LABEL_101;
      }
      ActivationContext = (struct _ACTIVATION_CONTEXT *)v23;
      goto LABEL_44;
    }
LABEL_70:
    DbgPrintEx(51, 0, "SXS: %s() - Caller passed invalid flags (0x%08lx)\n", "RtlQueryInformationActivationContext", a1);
LABEL_72:
    LoadedDllByHandle = -1073741585;
    goto LABEL_101;
  }
LABEL_44:
  if ( !ActivationContext )
  {
    DbgPrintEx(
      51,
      0,
      "SXS: %s() - Caller asked to use activation context from hmodule but passed NULL\n",
      "RtlQueryInformationActivationContext");
    goto LABEL_46;
  }
  LoadedDllByHandle = LdrpFindLoadedDllByHandle(ActivationContext, &v27, &v25);
  if ( LoadedDllByHandle >= 0 && (int)v25 < 5 && (NtCurrentTeb()->SameTebFlags & 0x1000) == 0 )
  {
    LdrpDrainWorkQueue(0);
    v22 = LoadedDllByHandle;
    if ( *(_DWORD *)(*(_QWORD *)(v27 + 152) + 56LL) != 9 )
      v22 = -1073741515;
    LoadedDllByHandle = v22;
    LdrpDropLastInProgressCount();
  }
  if ( LoadedDllByHandle < 0 )
  {
    DbgPrintEx(
      51,
      0,
      "SXS: %s() - Caller passed invalid hmodule (%p)\n",
      "RtlQueryInformationActivationContext",
      ActivationContext);
    goto LABEL_101;
  }
  ActivationContext = *(struct _ACTIVATION_CONTEXT **)(v27 + 136);
  v8 = a3;
LABEL_15:
  v13 = 0;
  v25 = 0;
  v14 = 0;
  v26 = 0;
  if ( ActivationContext )
  {
    if ( ActivationContext != (struct _ACTIVATION_CONTEXT *)-4LL )
    {
      v15 = "Actx ";
      if ( ActivationContext == (struct _ACTIVATION_CONTEXT *)-3LL )
      {
        v13 = "Actx ";
        v25 = "Actx ";
        v16 = "Actx ";
      }
      else
      {
        v13 = (const char *)*((_QWORD *)ActivationContext + 3);
        v25 = v13;
        v16 = v13;
      }
LABEL_41:
      if ( !v14 )
        goto LABEL_20;
      goto LABEL_19;
    }
    goto LABEL_85;
  }
  if ( ((unsigned __int64)&v30 & -(__int64)((a1 & 0x40000000) != 0)) != 0 )
  {
    v19 = *(_DWORD *)(((unsigned __int64)&v30 & -(__int64)((a1 & 0x40000000) != 0)) + 0x18) & 7;
    if ( !v19 || (v20 = v19 - 1) == 0 )
    {
      v14 = 760;
      v26 = 760;
LABEL_61:
      v15 = "Actx ";
      v16 = 0;
      goto LABEL_41;
    }
    v21 = v20 - 1;
    if ( v21 )
    {
      if ( v21 != 2 )
      {
        LoadedDllByHandle = -1073741584;
        v15 = 0;
        goto LABEL_23;
      }
      goto LABEL_61;
    }
LABEL_85:
    v14 = 776;
    goto LABEL_18;
  }
  v14 = 760;
LABEL_18:
  v26 = v14;
  v15 = "Actx ";
LABEL_19:
  v13 = *(const char **)(&NtCurrentPeb()->InheritedAddressSpace + v14);
  v25 = v13;
  v16 = v13;
LABEL_20:
  if ( v16 )
  {
    v15 = v16;
  }
  else
  {
    v13 = "Actx ";
    v25 = "Actx ";
  }
  LoadedDllByHandle = 0;
LABEL_23:
  if ( LoadedDllByHandle < 0 )
    goto LABEL_101;
  if ( !v15 && (a4 == 2 || a4 == 3 || a4 == 4 || a4 == 5 || (unsigned int)(a4 - 6) <= 1) )
    goto LABEL_72;
  v17 = a4 - 1;
  switch ( a4 )
  {
    case 1:
      v28 = 0;
      if ( a1 < 0 )
        v17 = a4;
      v28 = v17;
      InformationActivationContextBasicInformation = RtlpQueryInformationActivationContextBasicInformation(
                                                       v17,
                                                       (_DWORD)ActivationContext,
                                                       (_DWORD)v13,
                                                       a4,
                                                       a5,
                                                       a6,
                                                       (__int64)a7);
LABEL_29:
      LoadedDllByHandle = InformationActivationContextBasicInformation;
      if ( InformationActivationContextBasicInformation < 0 )
        break;
      goto LABEL_30;
    case 2:
      InformationActivationContextBasicInformation = RtlpQueryInformationActivationContextDetailedInformation(
                                                       v13,
                                                       v15,
                                                       a5,
                                                       a6,
                                                       a7);
      goto LABEL_29;
    case 3:
      if ( v8 )
      {
        InformationActivationContextBasicInformation = RtlpQueryAssemblyInformationActivationContextDetailedInformation(
                                                         v13,
                                                         *v8,
                                                         a5,
                                                         a6,
                                                         a7);
        goto LABEL_29;
      }
      goto LABEL_97;
    case 4:
      if ( v8 )
      {
        InformationActivationContextBasicInformation = RtlpQueryFilesInAssemblyInformationActivationContextDetailedInformation(
                                                         (_DWORD)v13,
                                                         (_DWORD)v8,
                                                         a5,
                                                         a6,
                                                         (__int64)a7);
        goto LABEL_29;
      }
LABEL_97:
      LoadedDllByHandle = -1073741811;
      break;
    case 5:
      if ( a6 >= 0xC )
      {
        *(_QWORD *)a5 = 0;
        *(_DWORD *)(a5 + 8) = 0;
        LoadedDllByHandle = RtlpQueryRunLevel((unsigned int)(a4 - 5), v13, a5);
        if ( LoadedDllByHandle >= 0 )
        {
          if ( a7 )
            *a7 = 12;
LABEL_30:
          LoadedDllByHandle = 0;
        }
      }
      else
      {
        LoadedDllByHandle = -1073741789;
        if ( a7 )
          *a7 = 12;
      }
      break;
    case 6:
      InformationActivationContextBasicInformation = RtlpQueryInformationActivationContextCompatibilityInformation(
                                                       v13,
                                                       a5,
                                                       a6,
                                                       a7);
      goto LABEL_29;
    case 7:
      InformationActivationContextBasicInformation = RtlpQueryInformationActivationContextManifestResourceName(
                                                       v13,
                                                       a5,
                                                       a6,
                                                       a7);
      goto LABEL_29;
    default:
      DbgPrintEx(
        51,
        0,
        "SXS: %s() - internal coding error; missing switch statement branch for InfoClass == %lu\n",
        "RtlQueryInformationActivationContext",
        a4);
      LoadedDllByHandle = -1073741595;
      break;
  }
LABEL_101:
  if ( v27 )
    LdrpDereferenceModule(v27);
  return (unsigned int)LoadedDllByHandle;
}

```

## disassembly

```asm
0x180067930  mov     rax, rsp
0x180067933  mov     [rax+8], rbx
0x180067937  mov     [rax+10h], rsi
0x18006793b  mov     [rax+18h], r8
0x18006793f  push    rdi
0x180067940  push    r12
0x180067942  push    r13
0x180067944  push    r14
0x180067946  push    r15
0x180067948  sub     rsp, 90h
0x18006794f  mov     r14d, r9d
0x180067952  mov     r11, r8
0x180067955  mov     rdi, rdx
0x180067958  mov     r13d, ecx
0x18006795b  xorps   xmm0, xmm0
0x18006795e  movups  xmmword ptr [rax-48h], xmm0
0x180067962  movups  xmmword ptr [rax-38h], xmm0
0x180067966  mov     dword ptr [rax-70h], 0
0x18006796d  mov     qword ptr [rax-60h], 0
0x180067975  mov     dword ptr [rax-30h], 4
0x18006797c  mov     rsi, [rsp+0B8h+arg_30]
0x180067984  test    rsi, rsi
0x180067987  jz      short loc_180067990
0x180067989  mov     qword ptr [rsi], 0
0x180067990  test    r13d, 3FFFFFF8h
0x180067997  jnz     loc_180067CF1
0x18006799d  test    r13d, r13d
0x1800679a0  js      loc_180067D3C
0x1800679a6  lea     eax, [r9-1]
0x1800679aa  cmp     eax, 6
0x1800679ad  ja      loc_180067D53
0x1800679b3  mov     r12, [rsp+0B8h+arg_28]
0x1800679bb  mov     r15, [rsp+0B8h+arg_20]
0x1800679c3  test    r12, r12
0x1800679c6  jnz     short loc_1800679EF
0x1800679c8  test    rsi, rsi
0x1800679cb  jnz     short loc_1800679FD
0x1800679cd  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x1800679d4  lea     r8, aSxsSCallerSupp; "SXS: %s() - caller supplied no buffer t"...
0x1800679db  xor     edx, edx
0x1800679dd  lea     ecx, [rsi+33h]
0x1800679e0  call    DbgPrintEx
0x1800679e5  mov     ebx, 0C00000F4h
0x1800679ea  jmp     loc_180067AFA
0x1800679ef  test    r15, r15
0x1800679f2  jz      loc_180067D7A
0x1800679f8  test    r12, r12
0x1800679fb  jz      short loc_1800679C8
0x1800679fd  mov     eax, r13d
0x180067a00  and     eax, 7
0x180067a03  jz      short loc_180067A33
0x180067a05  sub     eax, 1
0x180067a08  jnz     loc_180067B87
0x180067a0e  test    rdi, rdi
0x180067a11  jnz     loc_180067E05
0x180067a17  mov     rax, gs:30h
0x180067a20  mov     rcx, [rax+2C8h]
0x180067a27  mov     rax, [rcx]
0x180067a2a  test    rax, rax
0x180067a2d  jnz     loc_180067B4D
0x180067a33  mov     eax, r13d
0x180067a36  and     eax, 40000000h
0x180067a3b  neg     eax
0x180067a3d  sbb     rax, rax
0x180067a40  lea     rcx, [rsp+0B8h+var_48]
0x180067a45  and     rax, rcx
0x180067a48  mov     [rsp+0B8h+var_68], 0
0x180067a51  xor     r10d, r10d
0x180067a54  mov     [rsp+0B8h+var_70], r10
0x180067a59  xor     ecx, ecx
0x180067a5b  mov     [rsp+0B8h+var_68], rcx
0x180067a60  test    rdi, rdi
0x180067a63  jnz     loc_180067B56
0x180067a69  test    rax, rax
0x180067a6c  jnz     loc_180067C4B
0x180067a72  mov     ecx, 2F8h
0x180067a77  mov     [rsp+0B8h+var_68], rcx
0x180067a7c  lea     rdx, RtlpTheEmptyActivationContextData; "Actx "
0x180067a83  mov     rax, gs:60h
0x180067a8c  mov     r10, [rax+rcx]
0x180067a90  mov     [rsp+0B8h+var_70], r10
0x180067a95  mov     rax, r10
0x180067a98  test    rax, rax
0x180067a9b  jz      short loc_180067B03
0x180067a9d  mov     rdx, rax
0x180067aa0  xor     ebx, ebx
0x180067aa2  mov     [rsp+0B8h+var_78], ebx
0x180067aa6  test    ebx, ebx
0x180067aa8  js      loc_180067F28
0x180067aae  test    rdx, rdx
0x180067ab1  jz      loc_180067BC4
0x180067ab7  mov     ecx, r14d
0x180067aba  sub     ecx, 1
0x180067abd  jnz     short loc_180067B0D
0x180067abf  mov     [rsp+0B8h+var_58], ecx
0x180067ac3  lea     eax, [rcx+1]
0x180067ac6  test    r13d, r13d
0x180067ac9  cmovs   ecx, eax
0x180067acc  mov     [rsp+0B8h+var_58], ecx
0x180067ad0  mov     [rsp+0B8h+var_88], rsi
0x180067ad5  mov     [rsp+0B8h+var_90], r12
0x180067ada  mov     [rsp+0B8h+var_98], r15
0x180067adf  mov     r8, r10
0x180067ae2  mov     rdx, rdi
0x180067ae5  call    RtlpQueryInformationActivationContextBasicInformation
0x180067aea  test    eax, eax
0x180067aec  mov     [rsp+0B8h+var_78], eax
0x180067af0  mov     ebx, eax
0x180067af2  js      loc_180067F28
0x180067af8  xor     ebx, ebx
0x180067afa  mov     [rsp+0B8h+var_78], ebx
0x180067afe  jmp     loc_180067F28
0x180067b03  mov     r10, rdx
0x180067b06  mov     [rsp+0B8h+var_70], rdx
0x180067b0b  jmp     short loc_180067AA0
0x180067b0d  sub     ecx, 1
0x180067b10  jz      loc_180067F10
0x180067b16  sub     ecx, 1
0x180067b19  jz      loc_180067EF0
0x180067b1f  sub     ecx, 1
0x180067b22  jz      loc_180067EC6
0x180067b28  sub     ecx, 1
0x180067b2b  jz      loc_180067E73
0x180067b31  sub     ecx, 1
0x180067b34  jnz     loc_180067E31
0x180067b3a  mov     r9, rsi
0x180067b3d  mov     r8, r12
0x180067b40  mov     rdx, r15
0x180067b43  mov     rcx, r10
0x180067b46  call    RtlpQueryInformationActivationContextCompatibilityInformation
0x180067b4b  jmp     short loc_180067AEA
0x180067b4d  mov     rdi, [rax+8]
0x180067b51  jmp     loc_180067A33
0x180067b56  cmp     rdi, 0FFFFFFFFFFFFFFFCh
0x180067b5a  jz      loc_180067E27
0x180067b60  lea     rdx, RtlpTheEmptyActivationContextData; "Actx "
0x180067b67  cmp     rdi, 0FFFFFFFFFFFFFFFDh
0x180067b6b  jz      short loc_180067BB7
0x180067b6d  mov     r10, [rdi+18h]
0x180067b71  mov     [rsp+0B8h+var_70], r10
0x180067b76  mov     rax, r10
0x180067b79  test    rcx, rcx
0x180067b7c  jnz     loc_180067A83
0x180067b82  jmp     loc_180067A98
0x180067b87  sub     eax, 1
0x180067b8a  jnz     loc_180067D9C
0x180067b90  test    rdi, rdi
0x180067b93  jnz     short loc_180067C02
0x180067b95  lea     r8, aSxsSCallerAske_0; "SXS: %s() - Caller asked to use activat"...
0x180067b9c  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067ba3  xor     edx, edx
0x180067ba5  lea     ecx, [rdx+33h]
0x180067ba8  call    DbgPrintEx
0x180067bad  mov     ebx, 0C00000F0h
0x180067bb2  jmp     loc_180067AFA
0x180067bb7  mov     r10, rdx
0x180067bba  mov     [rsp+0B8h+var_70], rdx
0x180067bbf  mov     rax, rdx
0x180067bc2  jmp     short loc_180067B79
0x180067bc4  mov     ecx, r14d
0x180067bc7  sub     ecx, 2
0x180067bca  jz      loc_180067D32
0x180067bd0  sub     ecx, 1
0x180067bd3  jz      loc_180067D32
0x180067bd9  sub     ecx, 1
0x180067bdc  jz      loc_180067D32
0x180067be2  sub     ecx, 1
0x180067be5  jz      loc_180067D32
0x180067beb  sub     ecx, 1
0x180067bee  jz      loc_180067D32
0x180067bf4  cmp     ecx, 1
0x180067bf7  jnz     loc_180067AB7
0x180067bfd  jmp     loc_180067D32
0x180067c02  lea     r8, [rsp+0B8h+var_70]
0x180067c07  lea     rdx, [rsp+0B8h+var_60]
0x180067c0c  mov     rcx, rdi
0x180067c0f  call    LdrpFindLoadedDllByHandle
0x180067c14  mov     ebx, eax
0x180067c16  mov     [rsp+0B8h+var_78], eax
0x180067c1a  test    eax, eax
0x180067c1c  js      short loc_180067C25
0x180067c1e  cmp     dword ptr [rsp+0B8h+var_70], 5
0x180067c23  jl      short loc_180067CA3
0x180067c25  test    ebx, ebx
0x180067c27  jns     short loc_180067C70
0x180067c29  mov     [rsp+0B8h+var_98], rdi
0x180067c2e  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067c35  lea     r8, aSxsSCallerPass_1; "SXS: %s() - Caller passed invalid hmodu"...
0x180067c3c  xor     edx, edx
0x180067c3e  lea     ecx, [rdx+33h]
0x180067c41  call    DbgPrintEx
0x180067c46  jmp     loc_180067F28
0x180067c4b  mov     eax, [rax+18h]
0x180067c4e  and     eax, 7
0x180067c51  jz      short loc_180067C58
0x180067c53  sub     eax, 1
0x180067c56  jnz     short loc_180067C89
0x180067c58  mov     ecx, 2F8h
0x180067c5d  mov     [rsp+0B8h+var_68], rcx
0x180067c62  lea     rdx, RtlpTheEmptyActivationContextData; "Actx "
0x180067c69  xor     eax, eax
0x180067c6b  jmp     loc_180067B79
0x180067c70  mov     rax, [rsp+0B8h+var_60]
0x180067c75  mov     rdi, [rax+88h]
0x180067c7c  mov     r11, [rsp+0B8h+arg_10]
0x180067c84  jmp     loc_180067A33
0x180067c89  sub     eax, 1
0x180067c8c  jz      loc_180067E27
0x180067c92  sub     eax, 2
0x180067c95  jz      short loc_180067C62
0x180067c97  mov     ebx, 0C00000F0h
0x180067c9c  xor     edx, edx
0x180067c9e  jmp     loc_180067AA2
0x180067ca3  mov     rcx, gs:30h
0x180067cac  mov     eax, 1000h
0x180067cb1  test    [rcx+17EEh], ax
0x180067cb8  jnz     loc_180067C25
0x180067cbe  xor     ecx, ecx
0x180067cc0  call    LdrpDrainWorkQueue
0x180067cc5  mov     rax, [rsp+0B8h+var_60]
0x180067cca  mov     rcx, [rax+98h]
0x180067cd1  mov     eax, [rcx+38h]
0x180067cd4  mov     ecx, ebx
0x180067cd6  mov     ebx, 0C0000135h
0x180067cdb  cmp     eax, 9
0x180067cde  cmovnz  ecx, ebx
0x180067ce1  mov     ebx, ecx
0x180067ce3  mov     [rsp+0B8h+var_78], ecx
0x180067ce7  call    LdrpDropLastInProgressCount
0x180067cec  jmp     loc_180067C25
0x180067cf1  mov     dword ptr [rsp+0B8h+var_98], r13d
0x180067cf6  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067cfd  lea     r8, aSxsSCallerPass_2; "SXS: %s() - Caller passed invalid flags"...
0x180067d04  xor     edx, edx
0x180067d06  lea     ecx, [rdx+33h]
0x180067d09  call    DbgPrintEx
0x180067d0e  jmp     short loc_180067D32
0x180067d10  mov     dword ptr [rsp+0B8h+var_90], r14d
0x180067d15  mov     dword ptr [rsp+0B8h+var_98], r13d
0x180067d1a  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067d21  lea     r8, aSxsSCallerPass; "SXS: %s() - Caller passed meaningless f"...
0x180067d28  xor     edx, edx
0x180067d2a  lea     ecx, [rdx+33h]
0x180067d2d  call    DbgPrintEx
0x180067d32  mov     ebx, 0C00000EFh
0x180067d37  jmp     loc_180067AFA
0x180067d3c  lea     eax, [r9-1]
0x180067d40  test    eax, 0FFFFFFFAh
0x180067d45  jnz     short loc_180067D10
0x180067d47  cmp     r14d, 2
0x180067d4b  jnz     loc_1800679A6
0x180067d51  jmp     short loc_180067D10
0x180067d53  mov     dword ptr [rsp+0B8h+var_98], r14d
0x180067d58  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067d5f  lea     r8, aSxsSCallerAske; "SXS: %s() - caller asked for unknown in"...
0x180067d66  xor     edx, edx
0x180067d68  lea     ecx, [rdx+33h]
0x180067d6b  call    DbgPrintEx
0x180067d70  mov     ebx, 0C00000F1h
0x180067d75  jmp     loc_180067AFA
0x180067d7a  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067d81  lea     r8, aSxsSCallerPass_3; "SXS: %s() - caller passed nonzero buffe"...
0x180067d88  xor     edx, edx
0x180067d8a  lea     ecx, [rdx+33h]
0x180067d8d  call    DbgPrintEx
0x180067d92  mov     ebx, 0C00000F2h
0x180067d97  jmp     loc_180067AFA
0x180067d9c  sub     eax, 2
0x180067d9f  jnz     loc_180067CF1
0x180067da5  mov     [rsp+0B8h+BaseOfImage], 0
0x180067dae  test    rdi, rdi
0x180067db1  jnz     short loc_180067DBF
0x180067db3  lea     r8, aSxsSCallerAske_1; "SXS: %s() - Caller asked to use activat"...
0x180067dba  jmp     loc_180067B9C
0x180067dbf  lea     rdx, [rsp+0B8h+BaseOfImage]; BaseOfImage
0x180067dc4  mov     rcx, rdi; PcValue
0x180067dc7  call    RtlPcToFileHeader
0x180067dcc  mov     [rsp+0B8h+BaseOfImage], rax
0x180067dd1  test    rax, rax
0x180067dd4  jnz     short loc_180067DFD
0x180067dd6  mov     [rsp+0B8h+var_98], rdi
0x180067ddb  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067de2  lea     r8, aSxsSCallerPass_0; "SXS: %s() - Caller passed invalid addre"...
0x180067de9  xor     edx, edx
0x180067deb  lea     ecx, [rax+33h]
0x180067dee  call    DbgPrintEx
0x180067df3  mov     ebx, 0C0000135h
0x180067df8  jmp     loc_180067AFA
0x180067dfd  mov     rdi, rax
0x180067e00  jmp     loc_180067B90
0x180067e05  mov     [rsp+0B8h+var_98], rdi
0x180067e0a  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x180067e11  lea     r8, aSxsSCallerAske_2; "SXS: %s() - caller asked to use active "...
0x180067e18  xor     edx, edx
0x180067e1a  lea     ecx, [rdx+33h]
0x180067e1d  call    DbgPrintEx
0x180067e22  jmp     loc_180067BAD
0x180067e27  mov     ecx, 308h
0x180067e2c  jmp     loc_180067A77
0x180067e31  cmp     ecx, 1
  ... truncated ...
```
