# Smb2SetInfo_Start

- ea: `0x1400565a0`
- end: `0x140056927`
- name: `Smb2SetInfo_Start`
- size: `903`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000e700`
- `0x140028cc0`
- `0x140029764`
- `0x14002f7e0`
- `0x1400372c0`
- `0x1400565a0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140056729`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140056729`
- `ntoskrnl!IoIs32bitProcess` at `0x1400566ad`
- `ntoskrnl!IoIs32bitProcess` at `0x1400566ad`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005679f`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005679f`
- `rdbss!RxFreeMdl` at `0x140056895`
- `rdbss!RxFreeMdl` at `0x140056895`
- `rdbss!RxAllocateMdl2` at `0x14005670e`
- `rdbss!RxAllocateMdl2` at `0x14005670e`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x14005660e`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x14005660e`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x1400567f7`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x1400567f7`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140056767`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x140056767`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140056904`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140056904`

## pseudocode

```c
__int64 __fastcall Smb2SetInfo_Start(__int64 a1)
{
  __int64 v1; // rsi
  struct _MDL *v2; // rbp
  __int64 v3; // r12
  __int64 v5; // r15
  int v6; // eax
  unsigned int v7; // edi
  unsigned int *v8; // r13
  int v9; // r14d
  __int64 ExchangeBuffer; // rax
  __int64 v11; // rbp
  __int128 v12; // xmm0
  _DWORD *v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  struct _MDL *Mdl2; // rax
  int v17; // esi
  ULONG v19; // eax
  __int64 v20; // r9
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  unsigned int *v23; // r15
  const void *v24; // rdx
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  unsigned int v27; // [rsp+A0h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 48);
  v2 = 0;
  v3 = *(_QWORD *)(a1 + 72);
  v5 = *(_QWORD *)(*(_QWORD *)(v1 + 72) + 48LL);
  v6 = *(_DWORD *)(a1 + 2408);
  if ( v6 == 3 )
  {
    v9 = 0;
    v19 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(v1 + 520));
    v8 = *(unsigned int **)(v1 + 520);
    v7 = v19;
  }
  else
  {
    if ( v6 == 1 && *(_DWORD *)(a1 + 2412) == 10 && *(_BYTE *)(v1 + 479) && (v8 = *(unsigned int **)(v1 + 464)) != 0 )
    {
      v20 = v8[4];
      v7 = v20 + 24;
      if ( (int)v20 + 24 < (unsigned int)v20 )
      {
        v17 = -1073741811;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || !BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          goto LABEL_35;
        }
        v22 = 10;
LABEL_44:
        WPP_SF_d(v21->AttachedDevice, v22, WPP_69214addf0f23a16977eb0c8dd6a2623_Traceguids, v20);
        goto LABEL_35;
      }
    }
    else
    {
      v7 = *(_DWORD *)(v1 + 472);
      v8 = *(unsigned int **)(v1 + 456);
    }
    v9 = 16;
  }
  if ( v9 + v7 + 128 < v7 )
  {
    v17 = -1073741811;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_35;
    }
    v22 = 11;
    v20 = v7;
    goto LABEL_44;
  }
  ExchangeBuffer = SmbCeAllocateExchangeBuffer(a1);
  if ( !ExchangeBuffer )
    goto LABEL_36;
  v11 = ExchangeBuffer + 32;
  SmbCeBuildSmb2Header(a1, ExchangeBuffer + 32, 64);
  *(_WORD *)(v11 + 12) = 17;
  *(_OWORD *)(v11 + 64) = 0;
  *(_OWORD *)(v11 + 80) = 0;
  *(_WORD *)(v11 + 64) = 33;
  *(_BYTE *)(v11 + 66) = *(_BYTE *)(a1 + 2408);
  v12 = *(_OWORD *)(v5 + 28);
  *(_WORD *)(v11 + 72) = 96;
  v13 = (_DWORD *)(a1 + 2412);
  *(_OWORD *)(v11 + 80) = v12;
  if ( *(_DWORD *)(a1 + 2408) == 1 )
  {
    if ( (unsigned int)(*v13 - 10) <= 1 )
    {
      *(_OWORD *)(v11 + 96) = *(_OWORD *)v8;
      *(_DWORD *)(v11 + 112) = v8[4];
      if ( v8[4] > 2 && *((_WORD *)v8 + 10) == 92 )
      {
        *(_DWORD *)(v11 + 112) -= 2;
        v23 = (unsigned int *)(v11 + 112);
        v24 = (char *)v8 + 22;
      }
      else
      {
        v23 = (unsigned int *)(v11 + 112);
        v24 = v8 + 5;
      }
      memmove((void *)(v11 + 116), v24, *v23);
      if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 72) + 40LL) + 32LL) + 56LL) & 2) != 0
        && (*(_DWORD *)(*(_QWORD *)(v1 + 64) + 72LL) & 0x101) == 1 )
      {
        StripDfsPrefixFromName((void *)(v11 + 116));
      }
      v25 = *v23 + 20LL;
      v26 = v25;
      if ( v25 < 0x18 )
        v26 = 24;
      if ( v7 >= v26 )
      {
        v7 = 24;
        if ( v25 >= 0x18 )
          v7 = v25;
      }
    }
    else
    {
      memmove((void *)(v11 + 96), v8, v7);
    }
    if ( *(_DWORD *)(a1 + 2412) == 4 && !(unsigned __int8)SmbCeCheckServerEntryDialect(v3, 3, 0, 0) )
      *(_DWORD *)(v11 + 128) &= 0xFFFD7FFF;
    if ( IoIs32bitProcess(*(PIRP *)(v1 + 40)) )
    {
      v15 = *(unsigned int *)(a1 + 2412);
      v27 = v9 + v7;
      Smb2ThunkFileInfo(v15, v14, v7, &v27);
      v7 = v27;
    }
    v13 = (_DWORD *)(a1 + 2412);
    *(_BYTE *)(v11 + 67) = *(_BYTE *)(a1 + 2412);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 2408) == 3 )
      *(_DWORD *)(v11 + 76) = *v13;
    else
      *(_BYTE *)(v11 + 67) = *(_BYTE *)v13;
    memmove((void *)(v11 + 96), v8, v7);
  }
  *(_DWORD *)(v11 + 68) = v7;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(v11, v7 + 96, 0, 0, 0);
  v2 = Mdl2;
  if ( !Mdl2 )
  {
LABEL_36:
    v17 = -1073741670;
LABEL_35:
    RxFreeMdl(v2);
    return (unsigned int)v17;
  }
  MmBuildMdlForNonPagedPool(Mdl2);
  v17 = SmbCseInitializeBufferContextWithMemoryRegistration(a1 + 1024, a1, v2, v7 + 96, 0, 0, 0, 0, 0, 4);
  if ( !v17 )
  {
    v2 = 0;
    *(_DWORD *)(a1 + 1888) = *v13 | (*(_DWORD *)(a1 + 2408) << 16);
    v17 = SmbCseSubmitBufferContext(a1 + 1024);
  }
  if ( v17 < 0 )
    goto LABEL_35;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400565a0  push    rbx
0x1400565a2  push    rbp
0x1400565a3  push    rsi
0x1400565a4  push    rdi
0x1400565a5  push    r12
0x1400565a7  push    r13
0x1400565a9  push    r14
0x1400565ab  push    r15
0x1400565ad  sub     rsp, 58h
0x1400565b1  mov     rsi, [rcx+30h]
0x1400565b5  xor     ebp, ebp
0x1400565b7  mov     r12, [rcx+48h]
0x1400565bb  mov     rbx, rcx
0x1400565be  mov     rax, [rsi+48h]
0x1400565c2  mov     r15, [rax+30h]
0x1400565c6  mov     eax, [rcx+968h]
0x1400565cc  cmp     eax, 3
0x1400565cf  jz      loc_140056795
0x1400565d5  cmp     eax, 1
0x1400565d8  jnz     short loc_1400565E7
0x1400565da  cmp     dword ptr [rcx+96Ch], 0Ah
0x1400565e1  jz      loc_14005684A
0x1400565e7  mov     edi, [rsi+1D8h]
0x1400565ed  mov     r13, [rsi+1C8h]
0x1400565f4  mov     r14d, 10h
0x1400565fa  lea     edx, [rdi+80h]
0x140056600  add     edx, r14d
0x140056603  cmp     edx, edi
0x140056605  jb      loc_140056869
0x14005660b  mov     rcx, rbx
0x14005660e  call    cs:__imp_SmbCeAllocateExchangeBuffer
0x140056615  nop     dword ptr [rax+rax+00h]
0x14005661a  test    rax, rax
0x14005661d  jz      loc_1400568A6
0x140056623  lea     rbp, [rax+20h]
0x140056627  mov     r8d, 40h ; '@'
0x14005662d  mov     rdx, rbp
0x140056630  mov     rcx, rbx
0x140056633  call    SmbCeBuildSmb2Header
0x140056638  mov     word ptr [rbp+0Ch], 11h
0x14005663e  xorps   xmm1, xmm1
0x140056641  movups  xmmword ptr [rbp+40h], xmm1
0x140056645  movups  xmmword ptr [rbp+50h], xmm1
0x140056649  mov     word ptr [rbp+40h], 21h ; '!'
0x14005664f  movzx   eax, byte ptr [rbx+968h]
0x140056656  mov     [rbp+42h], al
0x140056659  movups  xmm0, xmmword ptr [r15+1Ch]
0x14005665e  mov     word ptr [rbp+48h], 60h ; '`'
0x140056664  lea     r15, [rbx+96Ch]
0x14005666b  movups  xmmword ptr [rbp+50h], xmm0
0x14005666f  mov     ecx, [rbx+968h]
0x140056675  sub     ecx, 1
0x140056678  jnz     loc_1400567B9
0x14005667e  mov     eax, [r15]
0x140056681  sub     eax, 0Ah
0x140056684  cmp     eax, 1
0x140056687  jbe     loc_1400568BE
0x14005668d  mov     r8d, edi; Size
0x140056690  lea     rcx, [rbp+60h]; void *
0x140056694  mov     rdx, r13; Src
0x140056697  call    memmove
0x14005669c  cmp     dword ptr [rbx+96Ch], 4
0x1400566a3  jz      loc_1400568F6
0x1400566a9  mov     rcx, [rsi+28h]; Irp
0x1400566ad  call    cs:__imp_IoIs32bitProcess
0x1400566b4  nop     dword ptr [rax+rax+00h]
0x1400566b9  test    al, al
0x1400566bb  jz      short loc_1400566E5
0x1400566bd  mov     ecx, [rbx+96Ch]
0x1400566c3  lea     eax, [r14+rdi]
0x1400566c7  lea     r9, [rsp+98h+arg_0]
0x1400566cf  mov     [rsp+98h+arg_0], eax
0x1400566d6  mov     r8d, edi
0x1400566d9  call    Smb2ThunkFileInfo
0x1400566de  mov     edi, [rsp+98h+arg_0]
0x1400566e5  movzx   eax, byte ptr [rbx+96Ch]
0x1400566ec  lea     r15, [rbx+96Ch]
0x1400566f3  mov     [rbp+43h], al
0x1400566f6  xor     r9d, r9d
0x1400566f9  mov     [rbp+44h], edi
0x1400566fc  xor     r8d, r8d
0x1400566ff  mov     [rsp+98h+var_78], 0
0x140056708  lea     edx, [rdi+60h]
0x14005670b  mov     rcx, rbp
0x14005670e  call    cs:__imp_RxAllocateMdl2
0x140056715  nop     dword ptr [rax+rax+00h]
0x14005671a  mov     rbp, rax
0x14005671d  test    rax, rax
0x140056720  jz      loc_1400568A6
0x140056726  mov     rcx, rax; MemoryDescriptorList
0x140056729  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140056730  nop     dword ptr [rax+rax+00h]
0x140056735  xor     eax, eax
0x140056737  mov     [rsp+98h+var_50], 4
0x14005673f  mov     [rsp+98h+var_58], ax
0x140056744  lea     r9d, [rdi+60h]
0x140056748  mov     [rsp+98h+var_60], eax
0x14005674c  lea     rcx, [rbx+400h]
0x140056753  mov     [rsp+98h+var_68], rax
0x140056758  mov     r8, rbp
0x14005675b  mov     [rsp+98h+var_70], eax
0x14005675f  mov     rdx, rbx
0x140056762  mov     [rsp+98h+var_78], rax
0x140056767  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x14005676e  nop     dword ptr [rax+rax+00h]
0x140056773  mov     esi, eax
0x140056775  test    eax, eax
0x140056777  jz      short loc_1400567DC
0x140056779  test    esi, esi
0x14005677b  js      loc_140056892
0x140056781  mov     eax, esi
0x140056783  add     rsp, 58h
0x140056787  pop     r15
0x140056789  pop     r14
0x14005678b  pop     r13
0x14005678d  pop     r12
0x14005678f  pop     rdi
0x140056790  pop     rsi
0x140056791  pop     rbp
0x140056792  pop     rbx
0x140056793  retn
0x140056795  mov     rcx, [rsi+208h]; SecurityDescriptor
0x14005679c  xor     r14d, r14d
0x14005679f  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400567a6  nop     dword ptr [rax+rax+00h]
0x1400567ab  mov     r13, [rsi+208h]
0x1400567b2  mov     edi, eax
0x1400567b4  jmp     loc_1400565FA
0x1400567b9  cmp     ecx, 2
0x1400567bc  mov     r8d, edi; Size
0x1400567bf  lea     rcx, [rbp+60h]; void *
0x1400567c3  mov     rdx, r13; Src
0x1400567c6  jnz     loc_1400568AD
0x1400567cc  mov     eax, [r15]
0x1400567cf  mov     [rbp+4Ch], eax
0x1400567d2  call    memmove
0x1400567d7  jmp     loc_1400566F6
0x1400567dc  mov     eax, [rbx+968h]
0x1400567e2  lea     rcx, [rbx+400h]
0x1400567e9  shl     eax, 10h
0x1400567ec  xor     ebp, ebp
0x1400567ee  or      eax, [r15]
0x1400567f1  mov     [rbx+760h], eax
0x1400567f7  call    cs:__imp_SmbCseSubmitBufferContext
0x1400567fe  nop     dword ptr [rax+rax+00h]
0x140056803  mov     esi, eax
0x140056805  jmp     loc_140056779
0x14005680a  mov     r9d, [r13+10h]
0x14005680e  lea     edi, [r9+18h]
0x140056812  cmp     edi, r9d
0x140056815  jnb     loc_1400565F4
0x14005681b  mov     esi, 0C000000Dh
0x140056820  mov     rcx, cs:WPP_GLOBAL_Control
0x140056827  lea     rax, WPP_GLOBAL_Control
0x14005682e  cmp     rcx, rax
0x140056831  jz      short loc_140056892
0x140056833  mov     eax, [rcx+2Ch]
0x140056836  test    al, 1
0x140056838  jz      short loc_140056892
0x14005683a  cmp     byte ptr [rcx+29h], 1
0x14005683e  jb      short loc_140056892
0x140056840  mov     edx, 0Ah
0x140056845  jmp     loc_140058684
0x14005684a  cmp     [rsi+1DFh], bpl
0x140056851  jz      loc_1400565E7
0x140056857  mov     r13, [rsi+1D0h]
0x14005685e  test    r13, r13
0x140056861  jz      loc_1400565E7
0x140056867  jmp     short loc_14005680A
0x140056869  mov     esi, 0C000000Dh
0x14005686e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056875  lea     rax, WPP_GLOBAL_Control
0x14005687c  cmp     rcx, rax
0x14005687f  jz      short loc_140056892
0x140056881  mov     eax, [rcx+2Ch]
0x140056884  test    al, 1
0x140056886  jz      short loc_140056892
0x140056888  cmp     byte ptr [rcx+29h], 1
0x14005688c  jnb     loc_14005867C
0x140056892  mov     rcx, rbp
0x140056895  call    cs:__imp_RxFreeMdl
0x14005689c  nop     dword ptr [rax+rax+00h]
0x1400568a1  jmp     loc_140056781
0x1400568a6  mov     esi, 0C000009Ah
0x1400568ab  jmp     short loc_140056892
0x1400568ad  movzx   eax, byte ptr [r15]
0x1400568b1  mov     [rbp+43h], al
0x1400568b4  call    memmove
0x1400568b9  jmp     loc_1400566F6
0x1400568be  movups  xmm0, xmmword ptr [r13+0]
0x1400568c3  movups  xmmword ptr [rbp+60h], xmm0
0x1400568c7  mov     eax, [r13+10h]
0x1400568cb  mov     [rbp+70h], eax
0x1400568ce  cmp     dword ptr [r13+10h], 2
0x1400568d3  jbe     loc_14005869A
0x1400568d9  cmp     word ptr [r13+14h], 5Ch ; '\'
0x1400568df  jnz     loc_14005869A
0x1400568e5  add     dword ptr [rbp+70h], 0FFFFFFFEh
0x1400568e9  lea     r15, [rbp+70h]
0x1400568ed  lea     rdx, [r13+16h]
0x1400568f1  jmp     loc_1400586A2
0x1400568f6  xor     r9d, r9d
0x1400568f9  xor     r8d, r8d
0x1400568fc  mov     edx, 3
0x140056901  mov     rcx, r12
0x140056904  call    cs:__imp_SmbCeCheckServerEntryDialect
0x14005690b  nop     dword ptr [rax+rax+00h]
0x140056910  test    al, al
0x140056912  jnz     loc_1400566A9
0x140056918  and     dword ptr [rbp+80h], 0FFFD7FFFh
0x140056922  jmp     loc_1400566A9
0x14005867c  mov     edx, 0Bh
0x140058681  mov     r9d, edi
0x140058684  mov     rcx, [rcx+18h]
0x140058688  lea     r8, WPP_69214addf0f23a16977eb0c8dd6a2623_Traceguids
0x14005868f  call    WPP_SF_d
0x140058694  nop
0x140058695  jmp     loc_140056892
0x14005869a  lea     r15, [rbp+70h]
0x14005869e  lea     rdx, [r13+14h]; Src
0x1400586a2  mov     r8d, [r15]; Size
0x1400586a5  lea     rcx, [rbp+74h]; void *
0x1400586a9  call    memmove
0x1400586ae  mov     rax, [rsi+48h]
0x1400586b2  mov     rdx, [rax+28h]
0x1400586b6  mov     rax, [rdx+20h]
0x1400586ba  mov     edx, [rax+38h]
0x1400586bd  test    dl, 2
0x1400586c0  jz      short loc_1400586E0
0x1400586c2  mov     rax, [rsi+40h]
0x1400586c6  mov     edx, [rax+48h]
0x1400586c9  and     edx, 101h
0x1400586cf  cmp     edx, 1
0x1400586d2  jnz     short loc_1400586E0
0x1400586d4  mov     rdx, r15
0x1400586d7  lea     rcx, [rbp+74h]; void *
0x1400586db  call    StripDfsPrefixFromName
0x1400586e0  mov     edx, [r15]
0x1400586e3  mov     r8d, 18h
0x1400586e9  add     rdx, 14h
0x1400586ed  mov     eax, edi
0x1400586ef  cmp     rdx, r8
0x1400586f2  mov     rcx, rdx
0x1400586f5  cmovb   rcx, r8
0x1400586f9  cmp     rax, rcx
0x1400586fc  jb      loc_14005669C
0x140058702  mov     edi, r8d
0x140058705  cmp     rdx, r8
0x140058708  jb      loc_14005669C
0x14005870e  mov     edi, edx
0x140058710  jmp     loc_14005669C
```
