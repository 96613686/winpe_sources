# CRAHelperClass::ReconfirmLowHealth(ulong,tagHypothesisResult *,ushort * *,tagDIAGNOSIS_STATUS *)

- ea: `0x18000e9b0`
- end: `0x18000ebcd`
- name: `?ReconfirmLowHealth@CRAHelperClass@@UEAAJKPEAUtagHypothesisResult@@PEAPEAGPEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(CRAHelperClass *this, const struct _EVENT_DESCRIPTOR *, struct tagHypothesisResult *, unsigned __int16 **, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cb0c`
- `0x18000e9b0`
- `0x18001223c`
- `0x180014660`
- `0x18001a5a2`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eaa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ea8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eaa0`

## string_xrefs

- `0x18000ea40`: `RemoteAccessibilityIssue`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::ReconfirmLowHealth(
        CRAHelperClass *this,
        const struct _EVENT_DESCRIPTOR *a2,
        struct tagHypothesisResult *a3,
        unsigned __int16 **a4,
        enum tagDIAGNOSIS_STATUS *a5)
{
  enum tagDIAGNOSIS_STATUS *v5; // rdi
  unsigned int v8; // r15d
  unsigned int v10; // r9d
  BOOL v12; // r14d
  __int64 i; // rdx
  unsigned int v14; // ebx
  bool v15; // zf
  signed int v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  unsigned int v19; // r9d
  LPVOID pv; // [rsp+30h] [rbp-81h] BYREF
  int v21; // [rsp+38h] [rbp-79h]
  LPVOID v22; // [rsp+40h] [rbp-71h]
  LPVOID v23; // [rsp+48h] [rbp-69h]

  v5 = a5;
  v8 = (unsigned int)a2;
  if ( !a5 )
  {
    v10 = 722;
LABEL_3:
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      v10,
      L"CRAHelperClass::ReconfirmLowHealth",
      0x80070057);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    v10 = 723;
    goto LABEL_3;
  }
  LODWORD(a5) = 0;
  memset_0(&pv, 0, 0x90u);
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, LPVOID *))(**((_QWORD **)this + 16) + 32LL))(
         *((_QWORD *)this + 16),
         L"RemoteAccessibilityIssue",
         &pv) < 0 )
    goto LABEL_12;
  v12 = (_DWORD)v22 == 1;
  CoTaskMemFree(pv);
  pv = 0;
  if ( v21 == 10 )
  {
    CoTaskMemFree(v22);
    v22 = 0;
  }
  else if ( v21 == 14 )
  {
    CoTaskMemFree(v23);
    v23 = 0;
  }
  v21 = 0;
  if ( !v12 )
  {
LABEL_12:
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      if ( a3[i].pathStatus == DS_CONFIRMED )
        return (unsigned int)-2147467263;
    }
  }
  *v5 = DS_REJECTED;
  *a4 = 0;
  if ( *((_DWORD *)this + 26) == 2 )
  {
    v16 = CRAHelperClass::CheckForGlobalAddresses((CRAHelperClass *)((char *)this - 56), 0, a4, v5, (int *)&a5);
    v14 = v16;
    if ( v16 < 0 )
    {
      v19 = 823;
      goto LABEL_24;
    }
    if ( (_DWORD)a5 != 1 )
      goto LABEL_30;
  }
  else
  {
    if ( *((_DWORD *)this + 26) != 3 && (unsigned int)(*((_DWORD *)this + 26) - 5) >= 2 )
    {
      v14 = 0;
LABEL_30:
      *v5 = DS_REJECTED;
      return v14;
    }
    *v5 = DS_CONFIRMED;
    v15 = *((_DWORD *)this + 26) == 3;
    *((_OWORD *)this + 14) = RCG_RADIAG_EXPERT_FAQ;
    *((_DWORD *)this + 66) = 1;
    if ( !v15 )
    {
      v16 = StringCchCopyWithAlloc(a4, i, 808);
      v14 = v16;
      if ( v16 >= 0 )
        return v14;
      v19 = 808;
      goto LABEL_24;
    }
    v16 = StringCchCopyWithAlloc(a4, i, 801);
    v14 = v16;
    if ( v16 < 0 )
    {
      v19 = 802;
LABEL_24:
      CEventLogger::LogError(
        v18,
        v17,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        v19,
        L"CRAHelperClass::ReconfirmLowHealth",
        v16);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18000e9b0  push    rbp
0x18000e9b2  push    rbx
0x18000e9b3  push    rsi
0x18000e9b4  push    rdi
0x18000e9b5  push    r12
0x18000e9b7  push    r13
0x18000e9b9  push    r14
0x18000e9bb  push    r15
0x18000e9bd  lea     rbp, [rsp-17h]
0x18000e9c2  sub     rsp, 0C8h
0x18000e9c9  mov     rdi, [rbp+4Fh+arg_20]
0x18000e9cd  mov     rsi, r9
0x18000e9d0  mov     r12, r8
0x18000e9d3  mov     r15d, edx
0x18000e9d6  mov     rbx, rcx
0x18000e9d9  test    rdi, rdi
0x18000e9dc  jnz     short loc_18000EA0E
0x18000e9de  mov     r9d, 2D2h; unsigned int
0x18000e9e4  lea     rax, aCrahelperclass_0; "CRAHelperClass::ReconfirmLowHealth"
0x18000e9eb  mov     [rsp+100h+var_D8], 80070057h; unsigned int
0x18000e9f3  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e9fa  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x18000e9ff  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000ea04  mov     eax, 80070057h
0x18000ea09  jmp     loc_18000EBB9
0x18000ea0e  test    rsi, rsi
0x18000ea11  jnz     short loc_18000EA1B
0x18000ea13  mov     r9d, 2D3h
0x18000ea19  jmp     short loc_18000E9E4
0x18000ea1b  xor     edx, edx; Val
0x18000ea1d  mov     dword ptr [rbp+4Fh+arg_20], 0
0x18000ea24  mov     r8d, 90h; Size
0x18000ea2a  lea     rcx, [rsp+100h+pv]; void *
0x18000ea2f  call    memset_0
0x18000ea34  mov     rcx, [rbx+80h]
0x18000ea3b  lea     r8, [rsp+100h+pv]
0x18000ea40  lea     rdx, aRemoteaccessib; "RemoteAccessibilityIssue"
0x18000ea47  mov     rax, [rcx]
0x18000ea4a  mov     rax, [rax+20h]
0x18000ea4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea53  mov     r8d, 1
0x18000ea59  test    eax, eax
0x18000ea5b  js      short loc_18000EABE
0x18000ea5d  mov     rcx, [rsp+100h+pv]; pv
0x18000ea62  xor     r14d, r14d
0x18000ea65  cmp     dword ptr [rbp+4Fh+var_C0], r8d
0x18000ea69  cmovz   r14d, r8d
0x18000ea6d  call    cs:__imp_CoTaskMemFree
0x18000ea73  cmp     [rbp+4Fh+var_C8], 0Ah
0x18000ea77  mov     [rsp+100h+pv], 0
0x18000ea80  jz      short loc_18000EA9C
0x18000ea82  cmp     [rbp+4Fh+var_C8], 0Eh
0x18000ea86  jnz     short loc_18000EAAE
0x18000ea88  mov     rcx, [rbp+4Fh+var_B8]; pv
0x18000ea8c  call    cs:__imp_CoTaskMemFree
0x18000ea92  mov     [rbp+4Fh+var_B8], 0
0x18000ea9a  jmp     short loc_18000EAAE
0x18000ea9c  mov     rcx, [rbp+4Fh+var_C0]; pv
0x18000eaa0  call    cs:__imp_CoTaskMemFree
0x18000eaa6  mov     [rbp+4Fh+var_C0], 0
0x18000eaae  mov     [rbp+4Fh+var_C8], 0
0x18000eab5  test    r14d, r14d
0x18000eab8  jnz     short loc_18000EADF
0x18000eaba  lea     r8d, [r14+1]
0x18000eabe  xor     edx, edx
0x18000eac0  cmp     edx, r15d
0x18000eac3  jnb     short loc_18000EADF
0x18000eac5  lea     rcx, [rdx+rdx*4]
0x18000eac9  cmp     [r12+rcx*8+20h], r8d
0x18000eace  jz      short loc_18000EAD5
0x18000ead0  add     edx, r8d
0x18000ead3  jmp     short loc_18000EAC0
0x18000ead5  mov     ebx, 80004001h
0x18000eada  jmp     loc_18000EBB7
0x18000eadf  mov     r14d, 2
0x18000eae5  mov     [rdi], r14d
0x18000eae8  mov     qword ptr [rsi], 0
0x18000eaef  mov     ecx, [rbx+68h]
0x18000eaf2  sub     ecx, r14d
0x18000eaf5  jz      loc_18000EB86
0x18000eafb  sub     ecx, 1
0x18000eafe  jz      short loc_18000EB11
0x18000eb00  sub     ecx, r14d
0x18000eb03  jz      short loc_18000EB11
0x18000eb05  cmp     ecx, 1
0x18000eb08  jz      short loc_18000EB11
0x18000eb0a  xor     ebx, ebx
0x18000eb0c  jmp     loc_18000EBB4
0x18000eb11  movups  xmm0, cs:RCG_RADIAG_EXPERT_FAQ
0x18000eb18  mov     dword ptr [rdi], 1
0x18000eb1e  mov     rcx, rsi; unsigned __int16 **
0x18000eb21  cmp     dword ptr [rbx+68h], 3
0x18000eb25  movdqu  xmmword ptr [rbx+0E0h], xmm0
0x18000eb2d  mov     dword ptr [rbx+108h], 1
0x18000eb37  jnz     short loc_18000EB6E
0x18000eb39  mov     r8d, 321h; int
0x18000eb3f  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000eb44  mov     ebx, eax
0x18000eb46  test    eax, eax
0x18000eb48  jns     short loc_18000EBB7
0x18000eb4a  mov     r9d, 322h; unsigned int
0x18000eb50  mov     [rsp+100h+var_D8], eax; unsigned int
0x18000eb54  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000eb5b  lea     rax, aCrahelperclass_0; "CRAHelperClass::ReconfirmLowHealth"
0x18000eb62  mov     [rsp+100h+var_E0], rax; unsigned __int16 *
0x18000eb67  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000eb6c  jmp     short loc_18000EBB7
0x18000eb6e  mov     edi, 328h
0x18000eb73  mov     r8d, edi; int
0x18000eb76  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000eb7b  mov     ebx, eax
0x18000eb7d  test    eax, eax
0x18000eb7f  jns     short loc_18000EBB7
0x18000eb81  mov     r9d, edi
0x18000eb84  jmp     short loc_18000EB50
0x18000eb86  lea     rax, [rbp+4Fh+arg_20]
0x18000eb8a  mov     r9, rdi; enum tagDIAGNOSIS_STATUS *
0x18000eb8d  mov     r8, rsi; unsigned __int16 **
0x18000eb90  mov     [rsp+100h+var_E0], rax; int *
0x18000eb95  xor     edx, edx; unsigned __int16 *
0x18000eb97  lea     rcx, [rbx-38h]; this
0x18000eb9b  call    ?CheckForGlobalAddresses@CRAHelperClass@@AEAAJPEAGPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckForGlobalAddresses(ushort *,ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000eba0  mov     ebx, eax
0x18000eba2  test    eax, eax
0x18000eba4  jns     short loc_18000EBAE
0x18000eba6  mov     r9d, 337h
0x18000ebac  jmp     short loc_18000EB50
0x18000ebae  cmp     dword ptr [rbp+4Fh+arg_20], 1
0x18000ebb2  jz      short loc_18000EBB7
0x18000ebb4  mov     [rdi], r14d
0x18000ebb7  mov     eax, ebx
0x18000ebb9  add     rsp, 0C8h
0x18000ebc0  pop     r15
0x18000ebc2  pop     r14
0x18000ebc4  pop     r13
0x18000ebc6  pop     r12
0x18000ebc8  pop     rdi
0x18000ebc9  pop     rsi
0x18000ebca  pop     rbx
0x18000ebcb  pop     rbp
0x18000ebcc  retn
```
