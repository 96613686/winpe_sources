# RxpFindOrCreateParentFcb

- ea: `0x14000d7c0`
- end: `0x14000da90`
- name: `RxpFindOrCreateParentFcb`
- size: `720`
- prototype: `__int64 __fastcall(PVOID Instance)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140055950`
- `0x140069a20`

## callees

- `0x140009b80`
- `0x14000d7c0`
- `0x1400169b0`
- `0x140016e20`
- `0x14001e3b0`
- `0x140055fc0`
- `0x140057660`
- `0x140058540`
- `0x14005cae0`
- `0x140062d40`
- `0x140065690`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14000d9ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d9ad`

## pseudocode

```c
__int64 __fastcall RxpFindOrCreateParentFcb(char *Instance)
{
  __int64 v1; // rsi
  unsigned int v2; // edi
  __int64 v5; // rax
  char *v6; // r14
  UNICODE_STRING *p_Path; // rbp
  PFCB v8; // rax
  PFCB v9; // r14
  UNICODE_STRING *v10; // r8
  UNICODE_STRING *v11; // r9
  PFCB NetFcb; // rax
  unsigned __int8 v13; // si
  ULONG v14; // r8d
  const CHAR *v15; // r9
  ULONG v16; // r8d
  const CHAR *v17; // r9
  const CHAR *FileName; // [rsp+20h] [rbp-78h]
  ULONG FileNamea; // [rsp+20h] [rbp-78h]
  int SerialNumber; // [rsp+28h] [rbp-70h]
  __int128 v21; // [rsp+50h] [rbp-48h] BYREF
  __int128 v22; // [rsp+60h] [rbp-38h] BYREF
  UNICODE_STRING Path; // [rsp+70h] [rbp-28h] BYREF

  v1 = *((_QWORD *)Instance + 15);
  v2 = 0;
  v21 = 0;
  Path = 0;
  v22 = 0;
  if ( *(_BYTE *)(v1 + 77)
    || (*(_DWORD *)(*(_QWORD *)(v1 + 32) + 96LL) & 0x4000) == 0
    || (*(_DWORD *)(*((_QWORD *)Instance + 50) + 336LL) & 0x20000) != 0
    || dbgForceNewFcb )
  {
    return v2;
  }
  v5 = *((_QWORD *)Instance + 16);
  if ( v5 )
  {
    v6 = Instance + 336;
    if ( *((_WORD *)Instance + 168) <= **(_WORD **)(v5 + 56) )
      return v2;
  }
  else
  {
    if ( !*((_WORD *)Instance + 180) )
      return v2;
    v6 = Instance + 336;
  }
  *((_QWORD *)&v22 + 1) = *((_QWORD *)Instance + 46);
  LOWORD(v22) = *((_WORD *)Instance + 180);
  WORD1(v22) = v22;
  RxCrackPathName(&v22, &v21, 0, 0);
  if ( (_WORD)v21 == 2 && **((_WORD **)&v21 + 1) == 92 )
    LOWORD(v21) = 0;
  if ( *((_QWORD *)Instance + 16) )
  {
    RxCrackPathName(v6, &Path, 0, 0);
    p_Path = &Path;
  }
  else
  {
    p_Path = (UNICODE_STRING *)&v21;
  }
  v8 = RxFcbTableLookupFcb((PRX_FCB_TABLE)(v1 + 296), p_Path);
  v9 = v8;
  if ( !v8 )
  {
    v10 = &Path;
    v11 = (UNICODE_STRING *)*((_QWORD *)Instance + 16);
    if ( !v11 )
      v10 = 0;
    SerialNumber = *((_DWORD *)Instance + 39) & 0x20000;
    LOWORD(FileName) = *((_WORD *)Instance + 140);
    NetFcb = RxCreateNetFcb((PRX_CONTEXT)v1, (PIRP)&v21, (PV_NET_ROOT)v10, v11);
    v9 = NetFcb;
    if ( !NetFcb )
      return (unsigned int)-1073741670;
    NetFcb->Header.NodeTypeCode = -5087;
    goto LABEL_16;
  }
  if ( v8->Header.NodeTypeCode == -5087 )
  {
LABEL_16:
    _RxAcquireFcb((PFCB)Instance, 0, 1u, 0, FileName, SerialNumber);
    *((_QWORD *)Instance + 36) = v9;
    v13 = *(_BYTE *)(*((_QWORD *)Instance + 1) + 26LL) & 0x80;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v13);
    }
    if ( v13
      && *(_DWORD *)(*((_QWORD *)Instance + 38) + 296LL)
      && (*((_DWORD *)Instance + 39) & 0x80000) == 0
      && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(0, Instance) )
    {
      RxProcessFcbChangeBufferingStateRequestInternal(Instance);
    }
    ExReleaseResourceLite(*((PERESOURCE *)Instance + 1));
    return v2;
  }
  _RxAcquireFcb(v8, 0, 1u, 0, FileName, SerialNumber);
  if ( v9->Header.NodeTypeCode == -5087 )
  {
LABEL_44:
    _RxReleaseFcb(0, (PMRX_FCB)&v9->Header, v14, v15, FileNamea);
    goto LABEL_16;
  }
  if ( LODWORD(v9->ScavengerFinalizationList.Flink) + HIDWORD(v9->ScavengerFinalizationList.Flink) <= 0 )
  {
    v9->Header.NodeTypeCode = -5087;
    goto LABEL_44;
  }
  if ( !RxpDereferenceAndFinalizeNetFcb(v9, 0, 0, 0) )
    _RxReleaseFcb(0, (PMRX_FCB)&v9->Header, v16, v17, FileNamea);
  v2 = -1073741766;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qZD(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      (unsigned int)&WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
      (_DWORD)v9,
      (__int64)p_Path,
      58);
  }
  return v2;
}

```

## disassembly

```asm
0x14000d7c0  push    rbx
0x14000d7c2  push    rsi
0x14000d7c3  push    rdi
0x14000d7c4  sub     rsp, 80h
0x14000d7cb  mov     rsi, [rcx+78h]
0x14000d7cf  xorps   xmm0, xmm0
0x14000d7d2  xorps   xmm1, xmm1
0x14000d7d5  xor     edi, edi
0x14000d7d7  movups  [rsp+98h+var_48], xmm1
0x14000d7dc  mov     rbx, rcx
0x14000d7df  movups  xmmword ptr [rsp+98h+Path.Length], xmm0
0x14000d7e4  movups  [rsp+98h+var_38], xmm0
0x14000d7e9  cmp     [rsi+4Dh], dil
0x14000d7ed  jz      short loc_14000D7FD
0x14000d7ef  mov     eax, edi
0x14000d7f1  add     rsp, 80h
0x14000d7f8  pop     rdi
0x14000d7f9  pop     rsi
0x14000d7fa  pop     rbx
0x14000d7fb  retn
0x14000d7fd  mov     rax, [rsi+20h]
0x14000d801  test    dword ptr [rax+60h], 4000h
0x14000d808  jz      short loc_14000D7EF
0x14000d80a  mov     rax, [rcx+190h]
0x14000d811  test    dword ptr [rax+150h], 20000h
0x14000d81b  jnz     short loc_14000D7EF
0x14000d81d  movzx   eax, cs:dbgForceNewFcb
0x14000d824  test    al, al
0x14000d826  jnz     short loc_14000D7EF
0x14000d828  mov     rax, [rcx+80h]
0x14000d82f  mov     [rsp+98h+arg_8], r14
0x14000d837  test    rax, rax
0x14000d83a  jz      loc_14000DA45
0x14000d840  mov     rax, [rax+38h]
0x14000d844  lea     r14, [rcx+150h]
0x14000d84b  movzx   edx, word ptr [r14]
0x14000d84f  cmp     dx, [rax]
0x14000d852  jbe     loc_14000D9C9
0x14000d858  mov     rax, [rcx+170h]
0x14000d85f  lea     rdx, [rsp+98h+var_48]
0x14000d864  mov     qword ptr [rsp+98h+var_38+8], rax
0x14000d869  xor     r9d, r9d
0x14000d86c  movzx   eax, word ptr [rcx+168h]
0x14000d873  xor     r8d, r8d
0x14000d876  lea     rcx, [rsp+98h+var_38]
0x14000d87b  mov     word ptr [rsp+98h+var_38], ax
0x14000d880  mov     word ptr [rsp+98h+var_38+2], ax
0x14000d885  mov     [rsp+98h+arg_0], rbp
0x14000d88d  call    RxCrackPathName
0x14000d892  cmp     word ptr [rsp+98h+var_48], 2
0x14000d898  jz      loc_14000DA2A
0x14000d89e  cmp     [rbx+80h], rdi
0x14000d8a5  jz      loc_14000DA20
0x14000d8ab  xor     r9d, r9d
0x14000d8ae  lea     rdx, [rsp+98h+Path]
0x14000d8b3  xor     r8d, r8d
0x14000d8b6  mov     rcx, r14
0x14000d8b9  call    RxCrackPathName
0x14000d8be  lea     rbp, [rsp+98h+Path]
0x14000d8c3  cmp     [rbx+80h], rdi
0x14000d8ca  lea     rcx, [rsi+128h]; FcbTable
0x14000d8d1  mov     rdx, rbp; Path
0x14000d8d4  mov     [rsp+98h+arg_10], r15
0x14000d8dc  setnz   r8b
0x14000d8e0  xor     r9d, r9d
0x14000d8e3  call    RxFcbTableLookupFcb
0x14000d8e8  mov     r14, rax
0x14000d8eb  test    rax, rax
0x14000d8ee  jnz     loc_14000D9D6
0x14000d8f4  mov     edx, [rbx+9Ch]
0x14000d8fa  lea     r8, [rsp+98h+Path]
0x14000d8ff  mov     r9, [rbx+80h]; Name
0x14000d906  and     edx, 20000h
0x14000d90c  mov     [rsp+98h+var_58], 1
0x14000d911  test    r9, r9
0x14000d914  mov     [rsp+98h+var_60], 0EC21h
0x14000d91b  mov     rcx, rsi; RxContext
0x14000d91e  cmovz   r8, rax; VNetRoot
0x14000d922  mov     [rsp+98h+var_68], 100h
0x14000d92b  movzx   eax, word ptr [rbx+118h]
0x14000d932  mov     [rsp+98h+SerialNumber], edx; SerialNumber
0x14000d936  lea     rdx, [rsp+98h+var_48]; Irp
0x14000d93b  mov     word ptr [rsp+98h+FileName], ax; FileName
0x14000d940  call    RxCreateNetFcb
0x14000d945  mov     r14, rax
0x14000d948  test    rax, rax
0x14000d94b  jz      loc_14000DA5E
0x14000d951  mov     word ptr [rax], 0EC21h
0x14000d956  xor     r9d, r9d; LineNumber
0x14000d959  xor     edx, edx; RxContext
0x14000d95b  mov     r8d, 1; Mode
0x14000d961  mov     rcx, rbx; Fcb
0x14000d964  call    __RxAcquireFcb
0x14000d969  mov     rax, [rbx+8]
0x14000d96d  mov     [rbx+120h], r14
0x14000d974  movzx   ecx, byte ptr [rax+1Ah]
0x14000d978  mov     rax, [rbx+8]
0x14000d97c  movzx   esi, byte ptr [rax+1Ah]
0x14000d980  and     sil, 80h
0x14000d984  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d98b  lea     rax, WPP_GLOBAL_Control
0x14000d992  cmp     rcx, rax
0x14000d995  jz      short loc_14000D9A4
0x14000d997  test    dword ptr [rcx+2Ch], 100h
0x14000d99e  jnz     loc_14000DA68
0x14000d9a4  test    sil, sil
0x14000d9a7  jnz     short loc_14000D9EB
0x14000d9a9  mov     rcx, [rbx+8]; Resource
0x14000d9ad  call    cs:__imp_ExReleaseResourceLite
0x14000d9b4  nop     dword ptr [rax+rax+00h]
0x14000d9b9  mov     r15, [rsp+98h+arg_10]
0x14000d9c1  mov     rbp, [rsp+98h+arg_0]
0x14000d9c9  mov     r14, [rsp+98h+arg_8]
0x14000d9d1  jmp     loc_14000D7EF
0x14000d9d6  mov     r15d, 0EC21h
0x14000d9dc  cmp     [rax], r15w
0x14000d9e0  jz      loc_14000D956
0x14000d9e6  jmp     loc_1400277F0
0x14000d9eb  mov     rax, [rbx+130h]
0x14000d9f2  cmp     [rax+128h], edi
0x14000d9f8  jz      short loc_14000D9A9
0x14000d9fa  test    dword ptr [rbx+9Ch], 80000h
0x14000da04  jnz     short loc_14000D9A9
0x14000da06  mov     rdx, rbx
0x14000da09  xor     ecx, ecx
0x14000da0b  call    RxIsSafeToProcessBufferingStateChange
0x14000da10  test    al, al
0x14000da12  jz      short loc_14000D9A9
0x14000da14  xor     edx, edx
0x14000da16  mov     rcx, rbx; Instance
0x14000da19  call    RxProcessFcbChangeBufferingStateRequestInternal
0x14000da1e  jmp     short loc_14000D9A9
0x14000da20  lea     rbp, [rsp+98h+var_48]
0x14000da25  jmp     loc_14000D8C3
0x14000da2a  mov     rax, qword ptr [rsp+98h+var_48+8]
0x14000da2f  cmp     word ptr [rax], 5Ch ; '\'
0x14000da33  jnz     loc_14000D89E
0x14000da39  xor     eax, eax
0x14000da3b  mov     word ptr [rsp+98h+var_48], ax
0x14000da40  jmp     loc_14000D89E
0x14000da45  cmp     [rcx+168h], di
0x14000da4c  jbe     loc_14000D9C9
0x14000da52  lea     r14, [rcx+150h]
0x14000da59  jmp     loc_14000D858
0x14000da5e  mov     edi, 0C000009Ah
0x14000da63  jmp     loc_14000D9B9
0x14000da68  cmp     byte ptr [rcx+29h], 4
0x14000da6c  jb      loc_14000D9A4
0x14000da72  mov     rcx, [rcx+18h]
0x14000da76  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14000da7d  movzx   r9d, sil
0x14000da81  mov     edx, 0Dh
0x14000da86  call    WPP_SF_d
0x14000da8b  jmp     loc_14000D9A4
0x1400277f0  xor     r9d, r9d; LineNumber
0x1400277f3  xor     edx, edx; RxContext
0x1400277f5  mov     r8d, 1; Mode
0x1400277fb  mov     rcx, r14; Fcb
0x1400277fe  call    __RxAcquireFcb
0x140027803  cmp     [r14], r15w
0x140027807  jz      loc_14002789F
0x14002780d  mov     eax, [r14+0C4h]
0x140027814  add     eax, [r14+0C0h]
0x14002781b  test    eax, eax
0x14002781d  jle     short loc_140027899
0x14002781f  xor     r9d, r9d; ForceFinalize
0x140027822  xor     r8d, r8d; RecursiveFinalize
0x140027825  xor     edx, edx; RxContext
0x140027827  mov     rcx, r14; ThisFcb
0x14002782a  call    RxpDereferenceAndFinalizeNetFcb
0x14002782f  test    al, al
0x140027831  jnz     short loc_14002783D
0x140027833  mov     rdx, r14; MrxFcb
0x140027836  xor     ecx, ecx; RxContext
0x140027838  call    __RxReleaseFcb
0x14002783d  mov     edi, 0C000003Ah
0x140027842  mov     rcx, cs:WPP_GLOBAL_Control
0x140027849  lea     rax, WPP_GLOBAL_Control
0x140027850  cmp     rcx, rax
0x140027853  jz      loc_14000D9B9
0x140027859  mov     eax, [rcx+2Ch]
0x14002785c  test    al, 1
0x14002785e  jz      loc_14000D9B9
0x140027864  cmp     byte ptr [rcx+29h], 1
0x140027868  jb      loc_14000D9B9
0x14002786e  mov     rcx, [rcx+18h]
0x140027872  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140027879  mov     edx, 14h
0x14002787e  mov     [rsp+98h+SerialNumber], 0C000003Ah
0x140027886  mov     r9, r14
0x140027889  mov     [rsp+98h+FileName], rbp
0x14002788e  call    WPP_SF_qZD
0x140027893  nop
0x140027894  jmp     loc_14000D9B9
0x140027899  mov     word ptr [r14], 0EC21h
0x14002789f  mov     rdx, r14; MrxFcb
0x1400278a2  xor     ecx, ecx; RxContext
0x1400278a4  call    __RxReleaseFcb
0x1400278a9  nop
0x1400278aa  jmp     loc_14000D956
```
