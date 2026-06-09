# _CmGetInstallerClassMappedPropertyFromRegProp

- ea: `0x180076630`
- end: `0x180076a16`
- name: `_CmGetInstallerClassMappedPropertyFromRegProp`
- size: `998`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800757d4`
- `0x1800759a8`
- `0x180075fc4`
- `0x180076ef4`

## callees

- `0x18001df70`
- `0x180067168`
- `0x18006723c`
- `0x18006cc90`
- `0x180071258`
- `0x180076630`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18007683b`
- `ntdll!RtlFreeHeap` at `0x180076989`
- `ntdll!RtlFreeHeap` at `0x18007683b`
- `ntdll!RtlFreeHeap` at `0x180076989`
- `ntdll!RtlAllocateHeap` at `0x1800767b0`
- `ntdll!RtlAllocateHeap` at `0x180076902`
- `ntdll!RtlAllocateHeap` at `0x1800767b0`
- `ntdll!RtlAllocateHeap` at `0x180076902`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18007696f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18007696f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800769ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800769ef`

## pseudocode

```c
__int64 __fastcall CmGetInstallerClassMappedPropertyFromRegProp(
        int a1,
        int a2,
        int a3,
        __int64 a4,
        _DWORD *a5,
        __int64 a6,
        unsigned int a7,
        unsigned int *a8)
{
  _BYTE *v8; // rdi
  unsigned int v11; // r15d
  unsigned int i; // edx
  DEVPROPKEY **v13; // rsi
  DEVPROPKEY *v14; // rcx
  __int64 v15; // rax
  unsigned int InstallerClassRegProp; // ebx
  int v17; // r13d
  unsigned int v18; // eax
  int v19; // eax
  SIZE_T v20; // rax
  PVOID v21; // rsi
  int v22; // eax
  void *v23; // r8
  PVOID Heap; // r13
  bool v25; // bl
  LPWSTR v26; // r9
  unsigned int v27; // eax
  int StringSecurityDescriptorLen; // [rsp+20h] [rbp-50h]
  unsigned int Size; // [rsp+40h] [rbp-30h] BYREF
  int Size_4; // [rsp+44h] [rbp-2Ch] BYREF
  int v32; // [rsp+48h] [rbp-28h] BYREF
  ULONG v33; // [rsp+4Ch] [rbp-24h] BYREF
  int v34; // [rsp+50h] [rbp-20h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+58h] [rbp-18h] BYREF
  __int64 v36; // [rsp+60h] [rbp-10h] BYREF

  v8 = (_BYTE *)a6;
  Size_4 = 0;
  *a5 = 0;
  *a8 = 0;
  v34 = 0;
  Size = 0;
  v32 = 0;
  StringSecurityDescriptor = 0;
  v33 = 0;
  v36 = 0;
  if ( a6 )
  {
    v11 = a7;
    v8 = (_BYTE *)(-(__int64)(a7 != 0) & a6);
  }
  else
  {
    v11 = 0;
  }
  for ( i = 0; i < 9; ++i )
  {
    v13 = &CmClassRegPropMap + 3 * i;
    v14 = *v13;
    if ( *(_DWORD *)(a4 + 16) == (*v13)->pid )
    {
      v15 = *(_QWORD *)a4 - *(_QWORD *)&v14->fmtid.Data1;
      if ( *(_QWORD *)a4 == *(_QWORD *)&v14->fmtid.Data1 )
        v15 = *(_QWORD *)(a4 + 8) - *(_QWORD *)v14->fmtid.Data4;
      if ( !v15 )
        break;
    }
    v13 = 0;
  }
  if ( !v13 )
    return (unsigned int)-1073741264;
  v17 = *((_DWORD *)v13 + 3);
  if ( v17 == 25 )
  {
    InstallerClassRegProp = CmGetInstallerClassRegProp(a1, a2, a3, 24, (__int64)&Size_4, 0, (__int64)&Size);
    if ( InstallerClassRegProp != -1073741789 )
      return InstallerClassRegProp;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
    if ( Heap )
    {
      InstallerClassRegProp = CmGetInstallerClassRegProp(
                                a1,
                                a2,
                                a3,
                                24,
                                (__int64)&Size_4,
                                (__int64)Heap,
                                (__int64)&Size);
      if ( (InstallerClassRegProp & 0x80000000) != 0 )
      {
        v23 = Heap;
        goto LABEL_33;
      }
      v25 = ConvertSecurityDescriptorToStringSecurityDescriptorW(Heap, 1u, 0xFu, &StringSecurityDescriptor, &v33);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      if ( v25 )
      {
        InstallerClassRegProp = RtlUnalignedStringCchLengthW(StringSecurityDescriptor, 0x7FFFFFFF, &v36);
        if ( (InstallerClassRegProp & 0x80000000) == 0 )
        {
          v33 = v36 + 1;
          *a8 = 2 * (v36 + 1);
          *a5 = *((_DWORD *)v13 + 2);
          if ( v11 >= *a8 )
          {
            v27 = RtlStringCbCopyExW((_DWORD)v8, v11, (_DWORD)v26, (_DWORD)v26, StringSecurityDescriptorLen, 2048);
            v26 = StringSecurityDescriptor;
            InstallerClassRegProp = v27;
          }
          else
          {
            InstallerClassRegProp = -1073741789;
          }
        }
        LocalFree(v26);
      }
      else
      {
        return (unsigned int)-1073741823;
      }
      return InstallerClassRegProp;
    }
    return (unsigned int)-1073741801;
  }
  if ( v17 == 27 )
  {
    Size = 4;
    InstallerClassRegProp = CmGetInstallerClassRegProp(a1, a2, a3, 27, (__int64)&Size_4, (__int64)&v32, (__int64)&Size);
    if ( (InstallerClassRegProp & 0x80000000) != 0 )
      return InstallerClassRegProp;
    if ( Size_4 == *((_DWORD *)v13 + 4) )
    {
      *a8 = 1;
      *a5 = *((_DWORD *)v13 + 2);
      if ( v11 >= *a8 )
        *v8 = -(v32 != 0);
      else
        return (unsigned int)-1073741789;
      return InstallerClassRegProp;
    }
    return (unsigned int)-1073741811;
  }
  *a8 = v11;
  v18 = CmGetInstallerClassRegProp(a1, a2, a3, v17, (__int64)&Size_4, (__int64)v8, (__int64)a8);
  InstallerClassRegProp = v18;
  if ( v18 && v18 != -1073741789 )
    return InstallerClassRegProp;
  if ( Size_4 != *((_DWORD *)v13 + 4) )
    return (unsigned int)-1073741811;
  v19 = *((_DWORD *)v13 + 2);
  *a5 = v19;
  if ( v19 != 18 )
    return InstallerClassRegProp;
  v20 = *a8;
  Size = *a8;
  if ( !InstallerClassRegProp )
  {
    if ( v11 < 2 || !v8 )
      return InstallerClassRegProp;
    v21 = 0;
    goto LABEL_28;
  }
  if ( InstallerClassRegProp != -1073741789 )
    return InstallerClassRegProp;
  v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v20);
  if ( !v21 )
    return (unsigned int)-1073741801;
  v22 = CmGetInstallerClassRegProp(a1, a2, a3, v17, (__int64)&v34, (__int64)v21, (__int64)&Size);
  if ( v22 < 0 )
  {
    InstallerClassRegProp = v22;
LABEL_32:
    v23 = v21;
LABEL_33:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
    return InstallerClassRegProp;
  }
  if ( Size < 2 )
    goto LABEL_32;
  v8 = v21;
LABEL_28:
  if ( (unsigned __int8)PnpParseIndirectInfString(v8) || (unsigned __int8)PnpParseIndirectResourceString(v8) )
    *a5 = 25;
  if ( v21 )
    goto LABEL_32;
  return InstallerClassRegProp;
}

```

## disassembly

```asm
0x180076630  mov     rax, rsp
0x180076633  mov     [rax+20h], rbx
0x180076637  mov     [rax+18h], r8
0x18007663b  mov     [rax+10h], rdx
0x18007663f  mov     [rax+8], rcx
0x180076643  push    rbp
0x180076644  push    rsi
0x180076645  push    rdi
0x180076646  push    r12
0x180076648  push    r13
0x18007664a  push    r14
0x18007664c  push    r15
0x18007664e  mov     rbp, rsp
0x180076651  sub     rsp, 70h
0x180076655  mov     r14, [rbp+arg_20]
0x180076659  xor     r13d, r13d
0x18007665c  mov     r12, [rbp+arg_38]
0x180076660  mov     r10, r8
0x180076663  mov     rdi, [rbp+arg_28]
0x180076667  mov     r11, rdx
0x18007666a  mov     dword ptr [rbp+Size+4], r13d
0x18007666e  mov     rbx, rcx
0x180076671  mov     [r14], r13d
0x180076674  mov     [r12], r13d
0x180076678  mov     [rbp+var_20], r13d
0x18007667c  mov     dword ptr [rbp+Size], r13d
0x180076680  mov     [rbp+var_28], r13d
0x180076684  mov     [rbp+StringSecurityDescriptor], r13
0x180076688  mov     [rbp+var_24], r13d
0x18007668c  mov     [rbp+var_10], r13
0x180076690  test    rdi, rdi
0x180076693  jnz     short loc_18007669A
0x180076695  mov     r15d, r13d
0x180076698  jmp     short loc_1800766A9
0x18007669a  mov     r15d, [rbp+arg_30]
0x18007669e  mov     eax, r15d
0x1800766a1  neg     eax
0x1800766a3  sbb     rcx, rcx
0x1800766a6  and     rdi, rcx
0x1800766a9  mov     r8d, [r9+10h]
0x1800766ad  mov     edx, r13d
0x1800766b0  mov     eax, edx
0x1800766b2  lea     rcx, [rax+rax*2]
0x1800766b6  lea     rax, _CmClassRegPropMap
0x1800766bd  lea     rsi, [rax+rcx*8]
0x1800766c1  mov     rcx, [rsi]
0x1800766c4  cmp     r8d, [rcx+10h]
0x1800766c8  jnz     short loc_1800766DF
0x1800766ca  mov     rax, [r9]
0x1800766cd  sub     rax, [rcx]
0x1800766d0  jnz     short loc_1800766DA
0x1800766d2  mov     rax, [r9+8]
0x1800766d6  sub     rax, [rcx+8]
0x1800766da  test    rax, rax
0x1800766dd  jz      short loc_1800766E9
0x1800766df  inc     edx
0x1800766e1  mov     rsi, r13
0x1800766e4  cmp     edx, 9
0x1800766e7  jb      short loc_1800766B0
0x1800766e9  test    rsi, rsi
0x1800766ec  jnz     short loc_1800766F8
0x1800766ee  mov     ebx, 0C0000230h
0x1800766f3  jmp     loc_1800769FC
0x1800766f8  mov     r13d, [rsi+0Ch]
0x1800766fc  mov     r8, r10
0x1800766ff  mov     rdx, r11
0x180076702  mov     rcx, rbx
0x180076705  cmp     r13d, 19h
0x180076709  jz      loc_1800768B5
0x18007670f  mov     r9d, 1Bh
0x180076715  cmp     r13d, r9d
0x180076718  jz      loc_180076846
0x18007671e  mov     [rsp+70h+var_40], r12
0x180076723  lea     rax, [rbp+Size+4]
0x180076727  mov     [rsp+70h+var_48], rdi
0x18007672c  mov     r9d, r13d
0x18007672f  mov     [rsp+70h+StringSecurityDescriptorLen], rax
0x180076734  mov     [r12], r15d
0x180076738  call    _CmGetInstallerClassRegProp
0x18007673d  mov     ebx, eax
0x18007673f  mov     r14d, 0C0000023h
0x180076745  test    eax, eax
0x180076747  jz      short loc_180076752
0x180076749  cmp     eax, r14d
0x18007674c  jnz     loc_1800769FC
0x180076752  mov     ecx, [rsi+10h]
0x180076755  cmp     dword ptr [rbp+Size+4], ecx
0x180076758  jnz     loc_18007687F
0x18007675e  mov     eax, [rsi+8]
0x180076761  mov     rcx, [rbp+arg_20]
0x180076765  mov     [rcx], eax
0x180076767  cmp     eax, 12h
0x18007676a  jnz     loc_1800769FC
0x180076770  mov     eax, [r12]
0x180076774  mov     dword ptr [rbp+Size], eax
0x180076777  test    ebx, ebx
0x180076779  jnz     short loc_180076792
0x18007677b  cmp     r15d, 2
0x18007677f  jb      loc_1800769FC
0x180076785  test    rdi, rdi
0x180076788  jz      loc_1800769FC
0x18007678e  xor     esi, esi
0x180076790  jmp     short loc_1800767FE
0x180076792  cmp     ebx, r14d
0x180076795  jnz     loc_1800769FC
0x18007679b  mov     rcx, gs:60h
0x1800767a4  mov     r8, rax; Size
0x1800767a7  mov     edx, 8; Flags
0x1800767ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800767b0  call    cs:__imp_RtlAllocateHeap
0x1800767b6  mov     rsi, rax
0x1800767b9  test    rax, rax
0x1800767bc  jz      loc_180076910
0x1800767c2  mov     r8, [rbp+arg_10]
0x1800767c6  lea     rax, [rbp+Size]
0x1800767ca  mov     rdx, [rbp+arg_8]
0x1800767ce  mov     r9d, r13d
0x1800767d1  mov     rcx, [rbp+arg_0]
0x1800767d5  mov     [rsp+70h+var_40], rax
0x1800767da  lea     rax, [rbp+var_20]
0x1800767de  mov     [rsp+70h+var_48], rsi
0x1800767e3  mov     [rsp+70h+StringSecurityDescriptorLen], rax
0x1800767e8  call    _CmGetInstallerClassRegProp
0x1800767ed  test    eax, eax
0x1800767ef  jns     short loc_1800767F5
0x1800767f1  mov     ebx, eax
0x1800767f3  jmp     short loc_180076829
0x1800767f5  cmp     dword ptr [rbp+Size], 2
0x1800767f9  jb      short loc_180076829
0x1800767fb  mov     rdi, rsi
0x1800767fe  mov     rcx, rdi
0x180076801  call    _PnpParseIndirectInfString
0x180076806  test    al, al
0x180076808  jnz     short loc_180076816
0x18007680a  mov     rcx, rdi
0x18007680d  call    _PnpParseIndirectResourceString
0x180076812  test    al, al
0x180076814  jz      short loc_180076820
0x180076816  mov     rax, [rbp+arg_20]
0x18007681a  mov     dword ptr [rax], 19h
0x180076820  test    rsi, rsi
0x180076823  jz      loc_1800769FC
0x180076829  mov     r8, rsi; P
0x18007682c  mov     rcx, gs:60h
0x180076835  xor     edx, edx; Flags
0x180076837  mov     rcx, [rcx+30h]; HeapHandle
0x18007683b  call    cs:__imp_RtlFreeHeap
0x180076841  jmp     loc_1800769FC
0x180076846  lea     rax, [rbp+Size]
0x18007684a  mov     dword ptr [rbp+Size], 4
0x180076851  mov     [rsp+70h+var_40], rax
0x180076856  lea     rax, [rbp+var_28]
0x18007685a  mov     [rsp+70h+var_48], rax
0x18007685f  lea     rax, [rbp+Size+4]
0x180076863  mov     [rsp+70h+StringSecurityDescriptorLen], rax
0x180076868  call    _CmGetInstallerClassRegProp
0x18007686d  mov     ebx, eax
0x18007686f  test    eax, eax
0x180076871  js      loc_1800769FC
0x180076877  mov     eax, [rsi+10h]
0x18007687a  cmp     dword ptr [rbp+Size+4], eax
0x18007687d  jz      short loc_180076889
0x18007687f  mov     ebx, 0C000000Dh
0x180076884  jmp     loc_1800769FC
0x180076889  mov     dword ptr [r12], 1
0x180076891  mov     eax, [rsi+8]
0x180076894  mov     [r14], eax
0x180076897  cmp     r15d, [r12]
0x18007689b  jnb     short loc_1800768A7
0x18007689d  mov     ebx, 0C0000023h
0x1800768a2  jmp     loc_1800769FC
0x1800768a7  mov     eax, [rbp+var_28]
0x1800768aa  neg     eax
0x1800768ac  sbb     cl, cl
0x1800768ae  mov     [rdi], cl
0x1800768b0  jmp     loc_1800769FC
0x1800768b5  lea     rax, [rbp+Size]
0x1800768b9  mov     r9d, 18h
0x1800768bf  mov     [rsp+70h+var_40], rax
0x1800768c4  lea     rax, [rbp+Size+4]
0x1800768c8  mov     [rsp+70h+var_48], 0
0x1800768d1  mov     [rsp+70h+StringSecurityDescriptorLen], rax
0x1800768d6  call    _CmGetInstallerClassRegProp
0x1800768db  mov     r14d, 0C0000023h
0x1800768e1  mov     ebx, eax
0x1800768e3  cmp     eax, r14d
0x1800768e6  jnz     loc_1800769FC
0x1800768ec  mov     rcx, gs:60h
0x1800768f5  mov     edx, 8; Flags
0x1800768fa  mov     r8d, dword ptr [rbp+Size]; Size
0x1800768fe  mov     rcx, [rcx+30h]; HeapHandle
0x180076902  call    cs:__imp_RtlAllocateHeap
0x180076908  mov     r13, rax
0x18007690b  test    rax, rax
0x18007690e  jnz     short loc_18007691A
0x180076910  mov     ebx, 0C0000017h
0x180076915  jmp     loc_1800769FC
0x18007691a  mov     r8, [rbp+arg_10]
0x18007691e  lea     rax, [rbp+Size]
0x180076922  mov     rdx, [rbp+arg_8]
0x180076926  mov     r9d, 18h
0x18007692c  mov     rcx, [rbp+arg_0]
0x180076930  mov     [rsp+70h+var_40], rax
0x180076935  lea     rax, [rbp+Size+4]
0x180076939  mov     [rsp+70h+var_48], r13
0x18007693e  mov     [rsp+70h+StringSecurityDescriptorLen], rax
0x180076943  call    _CmGetInstallerClassRegProp
0x180076948  mov     ebx, eax
0x18007694a  test    eax, eax
0x18007694c  jns     short loc_180076956
0x18007694e  mov     r8, r13
0x180076951  jmp     loc_18007682C
0x180076956  mov     edx, 1; RequestedStringSDRevision
0x18007695b  lea     rax, [rbp+var_24]
0x18007695f  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180076963  mov     [rsp+70h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x180076968  mov     rcx, r13; SecurityDescriptor
0x18007696b  lea     r8d, [rdx+0Eh]; SecurityInformation
0x18007696f  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180076975  mov     rcx, gs:60h
0x18007697e  mov     r8, r13; P
0x180076981  xor     edx, edx; Flags
0x180076983  mov     ebx, eax
0x180076985  mov     rcx, [rcx+30h]; HeapHandle
0x180076989  call    cs:__imp_RtlFreeHeap
0x18007698f  test    bl, bl
0x180076991  jz      short loc_1800769F7
0x180076993  mov     r9, [rbp+StringSecurityDescriptor]
0x180076997  lea     r8, [rbp+var_10]
0x18007699b  mov     rcx, r9
0x18007699e  mov     edx, 7FFFFFFFh
0x1800769a3  call    RtlUnalignedStringCchLengthW
0x1800769a8  mov     ebx, eax
0x1800769aa  test    eax, eax
0x1800769ac  js      short loc_1800769EC
0x1800769ae  mov     eax, dword ptr [rbp+var_10]
0x1800769b1  mov     rcx, [rbp+arg_20]
0x1800769b5  inc     eax
0x1800769b7  mov     [rbp+var_24], eax
0x1800769ba  add     eax, eax
0x1800769bc  mov     [r12], eax
0x1800769c0  mov     eax, [rsi+8]
0x1800769c3  mov     [rcx], eax
0x1800769c5  cmp     r15d, [r12]
0x1800769c9  jnb     short loc_1800769D0
0x1800769cb  mov     ebx, r14d
0x1800769ce  jmp     short loc_1800769EC
0x1800769d0  mov     edx, r15d
0x1800769d3  mov     r8, r9
0x1800769d6  mov     rcx, rdi
0x1800769d9  mov     dword ptr [rsp+70h+var_48], 800h
0x1800769e1  call    RtlStringCbCopyExW
0x1800769e6  mov     r9, [rbp+StringSecurityDescriptor]
0x1800769ea  mov     ebx, eax
0x1800769ec  mov     rcx, r9; hMem
0x1800769ef  call    cs:__imp_LocalFree
0x1800769f5  jmp     short loc_1800769FC
0x1800769f7  mov     ebx, 0C0000001h
0x1800769fc  mov     eax, ebx
0x1800769fe  mov     rbx, [rsp+70h+arg_18]
0x180076a06  add     rsp, 70h
0x180076a0a  pop     r15
0x180076a0c  pop     r14
0x180076a0e  pop     r13
0x180076a10  pop     r12
0x180076a12  pop     rdi
0x180076a13  pop     rsi
0x180076a14  pop     rbp
0x180076a15  retn
```
