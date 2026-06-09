# RtlQueryInformationActivationContext

- ea: `0x18004ad30`
- end: `0x18004b359`
- name: `RtlQueryInformationActivationContext`
- size: `1577`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800036ec`
- `0x18004a970`
- `0x18004b9a0`
- `0x1800e7aa0`

## callees

- `0x18001a080`
- `0x1800254e0`
- `0x1800259fc`
- `0x18004ad30`
- `0x18004b5b0`
- `0x1800514c0`
- `0x180054000`
- `0x1800bc288`
- `0x1800e2014`
- `0x1800e4d58`
- `0x18010058c`
- `0x180105fb8`
- `0x18010f56c`
- `0x180110254`

## string_xrefs

- `0x18004b121`: `SXS: %s() - Caller passed meaningless flags/class combination (0x%08lx/0x%08lx)\n`
- `0x18004b1b3`: `SXS: %s() - Caller asked to use activation context from address in .dll but passed NULL\n`
- `0x18004b1e2`: `SXS: %s() - Caller passed invalid address, not in any .dll (%p)\n`

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
0x18004ad30  mov     rax, rsp
0x18004ad33  mov     [rax+8], rbx
0x18004ad37  mov     [rax+10h], rsi
0x18004ad3b  mov     [rax+18h], r8
0x18004ad3f  push    rdi
0x18004ad40  push    r12
0x18004ad42  push    r13
0x18004ad44  push    r14
0x18004ad46  push    r15
0x18004ad48  sub     rsp, 90h
0x18004ad4f  mov     r14d, r9d
0x18004ad52  mov     r11, r8
0x18004ad55  mov     rdi, rdx
0x18004ad58  mov     r13d, ecx
0x18004ad5b  xorps   xmm0, xmm0
0x18004ad5e  movups  xmmword ptr [rax-48h], xmm0
0x18004ad62  movups  xmmword ptr [rax-38h], xmm0
0x18004ad66  mov     dword ptr [rax-70h], 0
0x18004ad6d  mov     qword ptr [rax-60h], 0
0x18004ad75  mov     dword ptr [rax-30h], 4
0x18004ad7c  mov     rsi, [rsp+0B8h+arg_30]
0x18004ad84  test    rsi, rsi
0x18004ad87  jz      short loc_18004AD90
0x18004ad89  mov     qword ptr [rsi], 0
0x18004ad90  test    r13d, 3FFFFFF8h
0x18004ad97  jnz     loc_18004B0F1
0x18004ad9d  test    r13d, r13d
0x18004ada0  js      loc_18004B13C
0x18004ada6  lea     eax, [r9-1]
0x18004adaa  cmp     eax, 6
0x18004adad  ja      loc_18004B153
0x18004adb3  mov     r12, [rsp+0B8h+arg_28]
0x18004adbb  mov     r15, [rsp+0B8h+arg_20]
0x18004adc3  test    r12, r12
0x18004adc6  jnz     short loc_18004ADEF
0x18004adc8  test    rsi, rsi
0x18004adcb  jnz     short loc_18004ADFD
0x18004adcd  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004add4  lea     r8, aSxsSCallerSupp; "SXS: %s() - caller supplied no buffer t"...
0x18004addb  xor     edx, edx
0x18004addd  lea     ecx, [rsi+33h]
0x18004ade0  call    DbgPrintEx
0x18004ade5  mov     ebx, 0C00000F4h
0x18004adea  jmp     loc_18004AEFA
0x18004adef  test    r15, r15
0x18004adf2  jz      loc_18004B17A
0x18004adf8  test    r12, r12
0x18004adfb  jz      short loc_18004ADC8
0x18004adfd  mov     eax, r13d
0x18004ae00  and     eax, 7
0x18004ae03  jz      short loc_18004AE33
0x18004ae05  sub     eax, 1
0x18004ae08  jnz     loc_18004AF87
0x18004ae0e  test    rdi, rdi
0x18004ae11  jnz     loc_18004B205
0x18004ae17  mov     rax, gs:30h
0x18004ae20  mov     rcx, [rax+2C8h]
0x18004ae27  mov     rax, [rcx]
0x18004ae2a  test    rax, rax
0x18004ae2d  jnz     loc_18004AF4D
0x18004ae33  mov     eax, r13d
0x18004ae36  and     eax, 40000000h
0x18004ae3b  neg     eax
0x18004ae3d  sbb     rax, rax
0x18004ae40  lea     rcx, [rsp+0B8h+var_48]
0x18004ae45  and     rax, rcx
0x18004ae48  mov     [rsp+0B8h+var_68], 0
0x18004ae51  xor     r10d, r10d
0x18004ae54  mov     [rsp+0B8h+var_70], r10
0x18004ae59  xor     ecx, ecx
0x18004ae5b  mov     [rsp+0B8h+var_68], rcx
0x18004ae60  test    rdi, rdi
0x18004ae63  jnz     loc_18004AF56
0x18004ae69  test    rax, rax
0x18004ae6c  jnz     loc_18004B04B
0x18004ae72  mov     ecx, 2F8h
0x18004ae77  mov     [rsp+0B8h+var_68], rcx
0x18004ae7c  lea     rdx, RtlpTheEmptyActivationContextData; "Actx "
0x18004ae83  mov     rax, gs:60h
0x18004ae8c  mov     r10, [rax+rcx]
0x18004ae90  mov     [rsp+0B8h+var_70], r10
0x18004ae95  mov     rax, r10
0x18004ae98  test    rax, rax
0x18004ae9b  jz      short loc_18004AF03
0x18004ae9d  mov     rdx, rax
0x18004aea0  xor     ebx, ebx
0x18004aea2  mov     [rsp+0B8h+var_78], ebx
0x18004aea6  test    ebx, ebx
0x18004aea8  js      loc_18004B328
0x18004aeae  test    rdx, rdx
0x18004aeb1  jz      loc_18004AFC4
0x18004aeb7  mov     ecx, r14d
0x18004aeba  sub     ecx, 1
0x18004aebd  jnz     short loc_18004AF0D
0x18004aebf  mov     [rsp+0B8h+var_58], ecx
0x18004aec3  lea     eax, [rcx+1]
0x18004aec6  test    r13d, r13d
0x18004aec9  cmovs   ecx, eax
0x18004aecc  mov     [rsp+0B8h+var_58], ecx
0x18004aed0  mov     [rsp+0B8h+var_88], rsi
0x18004aed5  mov     [rsp+0B8h+var_90], r12
0x18004aeda  mov     [rsp+0B8h+var_98], r15
0x18004aedf  mov     r8, r10
0x18004aee2  mov     rdx, rdi
0x18004aee5  call    RtlpQueryInformationActivationContextBasicInformation
0x18004aeea  test    eax, eax
0x18004aeec  mov     [rsp+0B8h+var_78], eax
0x18004aef0  mov     ebx, eax
0x18004aef2  js      loc_18004B328
0x18004aef8  xor     ebx, ebx
0x18004aefa  mov     [rsp+0B8h+var_78], ebx
0x18004aefe  jmp     loc_18004B328
0x18004af03  mov     r10, rdx
0x18004af06  mov     [rsp+0B8h+var_70], rdx
0x18004af0b  jmp     short loc_18004AEA0
0x18004af0d  sub     ecx, 1
0x18004af10  jz      loc_18004B310
0x18004af16  sub     ecx, 1
0x18004af19  jz      loc_18004B2F0
0x18004af1f  sub     ecx, 1
0x18004af22  jz      loc_18004B2C6
0x18004af28  sub     ecx, 1
0x18004af2b  jz      loc_18004B273
0x18004af31  sub     ecx, 1
0x18004af34  jnz     loc_18004B231
0x18004af3a  mov     r9, rsi
0x18004af3d  mov     r8, r12
0x18004af40  mov     rdx, r15
0x18004af43  mov     rcx, r10
0x18004af46  call    RtlpQueryInformationActivationContextCompatibilityInformation
0x18004af4b  jmp     short loc_18004AEEA
0x18004af4d  mov     rdi, [rax+8]
0x18004af51  jmp     loc_18004AE33
0x18004af56  cmp     rdi, 0FFFFFFFFFFFFFFFCh
0x18004af5a  jz      loc_18004B227
0x18004af60  lea     rdx, RtlpTheEmptyActivationContextData; "Actx "
0x18004af67  cmp     rdi, 0FFFFFFFFFFFFFFFDh
0x18004af6b  jz      short loc_18004AFB7
0x18004af6d  mov     r10, [rdi+18h]
0x18004af71  mov     [rsp+0B8h+var_70], r10
0x18004af76  mov     rax, r10
0x18004af79  test    rcx, rcx
0x18004af7c  jnz     loc_18004AE83
0x18004af82  jmp     loc_18004AE98
0x18004af87  sub     eax, 1
0x18004af8a  jnz     loc_18004B19C
0x18004af90  test    rdi, rdi
0x18004af93  jnz     short loc_18004B002
0x18004af95  lea     r8, aSxsSCallerAske_0; "SXS: %s() - Caller asked to use activat"...
0x18004af9c  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004afa3  xor     edx, edx
0x18004afa5  lea     ecx, [rdx+33h]
0x18004afa8  call    DbgPrintEx
0x18004afad  mov     ebx, 0C00000F0h
0x18004afb2  jmp     loc_18004AEFA
0x18004afb7  mov     r10, rdx
0x18004afba  mov     [rsp+0B8h+var_70], rdx
0x18004afbf  mov     rax, rdx
0x18004afc2  jmp     short loc_18004AF79
0x18004afc4  mov     ecx, r14d
0x18004afc7  sub     ecx, 2
0x18004afca  jz      loc_18004B132
0x18004afd0  sub     ecx, 1
0x18004afd3  jz      loc_18004B132
0x18004afd9  sub     ecx, 1
0x18004afdc  jz      loc_18004B132
0x18004afe2  sub     ecx, 1
0x18004afe5  jz      loc_18004B132
0x18004afeb  sub     ecx, 1
0x18004afee  jz      loc_18004B132
0x18004aff4  cmp     ecx, 1
0x18004aff7  jnz     loc_18004AEB7
0x18004affd  jmp     loc_18004B132
0x18004b002  lea     r8, [rsp+0B8h+var_70]
0x18004b007  lea     rdx, [rsp+0B8h+var_60]
0x18004b00c  mov     rcx, rdi
0x18004b00f  call    LdrpFindLoadedDllByHandle
0x18004b014  mov     ebx, eax
0x18004b016  mov     [rsp+0B8h+var_78], eax
0x18004b01a  test    eax, eax
0x18004b01c  js      short loc_18004B025
0x18004b01e  cmp     dword ptr [rsp+0B8h+var_70], 5
0x18004b023  jl      short loc_18004B0A3
0x18004b025  test    ebx, ebx
0x18004b027  jns     short loc_18004B070
0x18004b029  mov     [rsp+0B8h+var_98], rdi
0x18004b02e  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004b035  lea     r8, aSxsSCallerPass_1; "SXS: %s() - Caller passed invalid hmodu"...
0x18004b03c  xor     edx, edx
0x18004b03e  lea     ecx, [rdx+33h]
0x18004b041  call    DbgPrintEx
0x18004b046  jmp     loc_18004B328
0x18004b04b  mov     eax, [rax+18h]
0x18004b04e  and     eax, 7
0x18004b051  jz      short loc_18004B058
0x18004b053  sub     eax, 1
0x18004b056  jnz     short loc_18004B089
0x18004b058  mov     ecx, 2F8h
0x18004b05d  mov     [rsp+0B8h+var_68], rcx
0x18004b062  lea     rdx, RtlpTheEmptyActivationContextData; "Actx "
0x18004b069  xor     eax, eax
0x18004b06b  jmp     loc_18004AF79
0x18004b070  mov     rax, [rsp+0B8h+var_60]
0x18004b075  mov     rdi, [rax+88h]
0x18004b07c  mov     r11, [rsp+0B8h+arg_10]
0x18004b084  jmp     loc_18004AE33
0x18004b089  sub     eax, 1
0x18004b08c  jz      loc_18004B227
0x18004b092  sub     eax, 2
0x18004b095  jz      short loc_18004B062
0x18004b097  mov     ebx, 0C00000F0h
0x18004b09c  xor     edx, edx
0x18004b09e  jmp     loc_18004AEA2
0x18004b0a3  mov     rcx, gs:30h
0x18004b0ac  mov     eax, 1000h
0x18004b0b1  test    [rcx+17EEh], ax
0x18004b0b8  jnz     loc_18004B025
0x18004b0be  xor     ecx, ecx
0x18004b0c0  call    LdrpDrainWorkQueue
0x18004b0c5  mov     rax, [rsp+0B8h+var_60]
0x18004b0ca  mov     rcx, [rax+98h]
0x18004b0d1  mov     eax, [rcx+38h]
0x18004b0d4  mov     ecx, ebx
0x18004b0d6  mov     ebx, 0C0000135h
0x18004b0db  cmp     eax, 9
0x18004b0de  cmovnz  ecx, ebx
0x18004b0e1  mov     ebx, ecx
0x18004b0e3  mov     [rsp+0B8h+var_78], ecx
0x18004b0e7  call    LdrpDropLastInProgressCount
0x18004b0ec  jmp     loc_18004B025
0x18004b0f1  mov     dword ptr [rsp+0B8h+var_98], r13d
0x18004b0f6  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004b0fd  lea     r8, aSxsSCallerPass_2; "SXS: %s() - Caller passed invalid flags"...
0x18004b104  xor     edx, edx
0x18004b106  lea     ecx, [rdx+33h]
0x18004b109  call    DbgPrintEx
0x18004b10e  jmp     short loc_18004B132
0x18004b110  mov     dword ptr [rsp+0B8h+var_90], r14d
0x18004b115  mov     dword ptr [rsp+0B8h+var_98], r13d
0x18004b11a  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004b121  lea     r8, aSxsSCallerPass; "SXS: %s() - Caller passed meaningless f"...
0x18004b128  xor     edx, edx
0x18004b12a  lea     ecx, [rdx+33h]
0x18004b12d  call    DbgPrintEx
0x18004b132  mov     ebx, 0C00000EFh
0x18004b137  jmp     loc_18004AEFA
0x18004b13c  lea     eax, [r9-1]
0x18004b140  test    eax, 0FFFFFFFAh
0x18004b145  jnz     short loc_18004B110
0x18004b147  cmp     r14d, 2
0x18004b14b  jnz     loc_18004ADA6
0x18004b151  jmp     short loc_18004B110
0x18004b153  mov     dword ptr [rsp+0B8h+var_98], r14d
0x18004b158  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004b15f  lea     r8, aSxsSCallerAske; "SXS: %s() - caller asked for unknown in"...
0x18004b166  xor     edx, edx
0x18004b168  lea     ecx, [rdx+33h]
0x18004b16b  call    DbgPrintEx
0x18004b170  mov     ebx, 0C00000F1h
0x18004b175  jmp     loc_18004AEFA
0x18004b17a  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004b181  lea     r8, aSxsSCallerPass_3; "SXS: %s() - caller passed nonzero buffe"...
0x18004b188  xor     edx, edx
0x18004b18a  lea     ecx, [rdx+33h]
0x18004b18d  call    DbgPrintEx
0x18004b192  mov     ebx, 0C00000F2h
0x18004b197  jmp     loc_18004AEFA
0x18004b19c  sub     eax, 2
0x18004b19f  jnz     loc_18004B0F1
0x18004b1a5  mov     [rsp+0B8h+BaseOfImage], 0
0x18004b1ae  test    rdi, rdi
0x18004b1b1  jnz     short loc_18004B1BF
0x18004b1b3  lea     r8, aSxsSCallerAske_1; "SXS: %s() - Caller asked to use activat"...
0x18004b1ba  jmp     loc_18004AF9C
0x18004b1bf  lea     rdx, [rsp+0B8h+BaseOfImage]; BaseOfImage
0x18004b1c4  mov     rcx, rdi; PcValue
0x18004b1c7  call    RtlPcToFileHeader
0x18004b1cc  mov     [rsp+0B8h+BaseOfImage], rax
0x18004b1d1  test    rax, rax
0x18004b1d4  jnz     short loc_18004B1FD
0x18004b1d6  mov     [rsp+0B8h+var_98], rdi
0x18004b1db  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004b1e2  lea     r8, aSxsSCallerPass_0; "SXS: %s() - Caller passed invalid addre"...
0x18004b1e9  xor     edx, edx
0x18004b1eb  lea     ecx, [rax+33h]
0x18004b1ee  call    DbgPrintEx
0x18004b1f3  mov     ebx, 0C0000135h
0x18004b1f8  jmp     loc_18004AEFA
0x18004b1fd  mov     rdi, rax
0x18004b200  jmp     loc_18004AF90
0x18004b205  mov     [rsp+0B8h+var_98], rdi
0x18004b20a  lea     r9, aRtlqueryinform_2; "RtlQueryInformationActivationContext"
0x18004b211  lea     r8, aSxsSCallerAske_2; "SXS: %s() - caller asked to use active "...
0x18004b218  xor     edx, edx
0x18004b21a  lea     ecx, [rdx+33h]
0x18004b21d  call    DbgPrintEx
0x18004b222  jmp     loc_18004AFAD
0x18004b227  mov     ecx, 308h
0x18004b22c  jmp     loc_18004AE77
0x18004b231  cmp     ecx, 1
  ... truncated ...
```
