# CFileListener::MergeRemainingProperties(CLocationWriter *,ISimpleTableRead2 *,int,ulong *,ulong)

- ea: `0x18000ccc0`
- end: `0x18000cf62`
- name: `?MergeRemainingProperties@CFileListener@@AEAAJPEAVCLocationWriter@@PEAUISimpleTableRead2@@HPEAKK@Z`
- size: `674`
- prototype: `__int64 __fastcall(CFileListener *__hidden this, struct CLocationWriter *, struct ISimpleTableRead2 *, int, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c374`
- `0x18000c680`

## callees

- `0x18000ccc0`
- `0x18002e130`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000ce63`
- `IisRTL!PuDbgPrintW` at `0x18000cebe`
- `IisRTL!PuDbgPrintW` at `0x18000cf16`
- `IisRTL!PuDbgPrintW` at `0x18000ce63`
- `IisRTL!PuDbgPrintW` at `0x18000cebe`
- `IisRTL!PuDbgPrintW` at `0x18000cf16`

## string_xrefs

- `0x18000cefd`: `[CFileListener::MergeRemainingProperties] GetColumnValues/GetWriteColumnValues on row %d from table %s failed with hr = 0x%x. Location = %s, Property ID: %d.\n`
- `0x18000ceae`: `[CFileListener::MergeRemainingProperties] CLocationWriter::AddProperty failed with hr = 0x%x. Location = %s, Property ID: %d.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::MergeRemainingProperties(
        CFileListener *this,
        struct CLocationWriter *a2,
        struct ISimpleTableRead2 *a3,
        int a4,
        unsigned int *a5,
        unsigned int a6)
{
  __int64 v6; // rbx
  __int64 result; // rax
  unsigned int v10; // r12d
  unsigned int *v11; // r15
  void **v12; // rdi
  const wchar_t *v13; // r13
  unsigned int i; // esi
  int v15; // eax
  __int64 v16; // rdx
  int v17; // ebx
  _DWORD *v18; // rcx
  __int64 v19; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h]
  struct ISimpleTableRead2 *v22; // [rsp+60h] [rbp-A0h]
  CLocationWriter *v23; // [rsp+68h] [rbp-98h]
  char v24; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[80]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v26; // [rsp+F0h] [rbp-10h] BYREF
  void *v27[10]; // [rsp+120h] [rbp+20h] BYREF

  v6 = 0;
  v22 = a3;
  v23 = a2;
  v21 = a4;
  v20 = 0;
  memset_0(v27, 0, sizeof(v27));
  memset_0(v25, 0, 0x48u);
  if ( a4 )
  {
    v10 = 9;
    v11 = (unsigned int *)&v24;
    v12 = (void **)v25;
    v13 = L"MBProperty";
  }
  else
  {
    result = (**(__int64 (__fastcall ***)(struct ISimpleTableRead2 *, GUID *, __int64 *))a3)(
               a3,
               &IID_ISimpleTableWrite2,
               &v20);
    if ( (int)result < 0 )
      return result;
    v6 = v20;
    v10 = 10;
    v11 = &v26;
    v12 = v27;
    v13 = L"MBPropertyDiff";
  }
  for ( i = *a5; ; ++i )
  {
    if ( v6 )
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, void **))(*(_QWORD *)v6 + 96LL))(
              v6,
              i,
              v10,
              0,
              0,
              v11,
              v12);
    else
      v15 = (*(__int64 (__fastcall **)(struct ISimpleTableRead2 *, _QWORD, _QWORD, _QWORD, unsigned int *, void **))(*(_QWORD *)v22 + 32LL))(
              v22,
              i,
              v10,
              0,
              v11,
              v12);
    v17 = v15;
    if ( v15 == -2145318890 )
    {
LABEL_23:
      v17 = 0;
      *a5 = i;
LABEL_24:
      if ( v20 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 16LL))(v20, v16);
      return (unsigned int)v17;
    }
    if ( v15 < 0 )
      break;
    if ( *(_DWORD *)v12[7] != a6 )
      goto LABEL_23;
    if ( v20 )
    {
      v18 = v12[8];
      if ( *v18 != 1 )
      {
        v16 = (unsigned int)(*v18 - 2);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            4386,
            "CFileListener::MergeRemainingProperties",
            L"[CFileListener::MergeRemainingProperties] Incorrect directive.\n");
        v17 = -2147024883;
        goto LABEL_24;
      }
    }
    v17 = CLocationWriter::AddProperty(v23, v21, v12, v11);
    if ( v17 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        LODWORD(v19) = v17;
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          4401,
          "CFileListener::MergeRemainingProperties",
          L"[CFileListener::MergeRemainingProperties] CLocationWriter::AddProperty failed with hr = 0x%x. Location = %s, P"
           "roperty ID: %d.\n",
          v19,
          v12[4],
          *(_DWORD *)v12[5]);
      }
      goto LABEL_24;
    }
    v6 = v20;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(v19) = i;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      4362,
      "CFileListener::MergeRemainingProperties",
      L"[CFileListener::MergeRemainingProperties] GetColumnValues/GetWriteColumnValues on row %d from table %s failed with"
       " hr = 0x%x. Location = %s, Property ID: %d.\n",
      v19,
      v13,
      v15,
      v12[4],
      *(_DWORD *)v12[5]);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000ccc0  mov     [rsp-8+arg_0], rbx
0x18000ccc5  push    rbp
0x18000ccc6  push    rsi
0x18000ccc7  push    rdi
0x18000ccc8  push    r12
0x18000ccca  push    r13
0x18000cccc  push    r14
0x18000ccce  push    r15
0x18000ccd0  lea     rbp, [rsp-80h]
0x18000ccd5  sub     rsp, 180h
0x18000ccdc  mov     rax, cs:__security_cookie
0x18000cce3  xor     rax, rsp
0x18000cce6  mov     [rbp+0B0h+var_40], rax
0x18000ccea  mov     r14, [rbp+0B0h+arg_20]
0x18000ccf1  lea     rcx, [rbp+0B0h+var_90]; void *
0x18000ccf5  xor     ebx, ebx
0x18000ccf7  mov     [rsp+1B0h+var_150], r8
0x18000ccfc  mov     rdi, r8
0x18000ccff  mov     [rsp+1B0h+var_148], rdx
0x18000cd04  xor     edx, edx; Val
0x18000cd06  mov     [rsp+1B0h+var_158], r9d
0x18000cd0b  mov     esi, r9d
0x18000cd0e  mov     [rsp+1B0h+var_160], rbx
0x18000cd13  lea     r8d, [rbx+50h]; Size
0x18000cd17  call    memset_0
0x18000cd1c  xor     edx, edx; Val
0x18000cd1e  lea     r8d, [rbx+48h]; Size
0x18000cd22  lea     rcx, [rbp+0B0h+var_110]; void *
0x18000cd26  call    memset_0
0x18000cd2b  test    esi, esi
0x18000cd2d  jnz     short loc_18000CD6B
0x18000cd2f  mov     rax, [rdi]
0x18000cd32  lea     r8, [rsp+1B0h+var_160]
0x18000cd37  lea     rdx, IID_ISimpleTableWrite2
0x18000cd3e  mov     rcx, rdi
0x18000cd41  mov     rax, [rax]
0x18000cd44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd49  test    eax, eax
0x18000cd4b  js      loc_18000CF3B
0x18000cd51  mov     rbx, [rsp+1B0h+var_160]
0x18000cd56  lea     r12d, [rsi+0Ah]
0x18000cd5a  lea     r15, [rbp+0B0h+var_C0]
0x18000cd5e  lea     rdi, [rbp+0B0h+var_90]
0x18000cd62  lea     r13, aMbpropertydiff; "MBPropertyDiff"
0x18000cd69  jmp     short loc_18000CD81
0x18000cd6b  mov     r12d, 9
0x18000cd71  lea     r15, [rsp+1B0h+var_140]
0x18000cd76  lea     rdi, [rbp+0B0h+var_110]
0x18000cd7a  lea     r13, aMbproperty_0; "MBProperty"
0x18000cd81  mov     esi, [r14]
0x18000cd84  xor     r9d, r9d
0x18000cd87  mov     r8d, r12d
0x18000cd8a  mov     edx, esi
0x18000cd8c  test    rbx, rbx
0x18000cd8f  jnz     short loc_18000CDAE
0x18000cd91  mov     rcx, [rsp+1B0h+var_150]
0x18000cd96  mov     [rsp+1B0h+var_188], rdi
0x18000cd9b  mov     [rsp+1B0h+var_190], r15
0x18000cda0  mov     rax, [rcx]
0x18000cda3  mov     rax, [rax+20h]
0x18000cda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdac  jmp     short loc_18000CDD0
0x18000cdae  mov     rax, [rbx]
0x18000cdb1  mov     rcx, rbx
0x18000cdb4  mov     [rsp+1B0h+var_180], rdi
0x18000cdb9  mov     [rsp+1B0h+var_188], r15
0x18000cdbe  mov     [rsp+1B0h+var_190], 0
0x18000cdc7  mov     rax, [rax+60h]
0x18000cdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd0  mov     ebx, eax
0x18000cdd2  cmp     eax, 80210816h
0x18000cdd7  jz      loc_18000CF1E
0x18000cddd  test    eax, eax
0x18000cddf  js      loc_18000CEC6
0x18000cde5  mov     rax, [rdi+38h]
0x18000cde9  mov     ecx, [rbp+0B0h+arg_28]
0x18000cdef  cmp     [rax], ecx
0x18000cdf1  jnz     loc_18000CF1E
0x18000cdf7  cmp     [rsp+1B0h+var_160], 0
0x18000cdfd  jz      short loc_18000CE0A
0x18000cdff  mov     rcx, [rdi+40h]
0x18000ce03  mov     edx, [rcx]
0x18000ce05  sub     edx, 1
0x18000ce08  jnz     short loc_18000CE30
0x18000ce0a  mov     edx, [rsp+1B0h+var_158]; int
0x18000ce0e  mov     r9, r15; unsigned int *
0x18000ce11  mov     rcx, [rsp+1B0h+var_148]; this
0x18000ce16  mov     r8, rdi; void **
0x18000ce19  call    ?AddProperty@CLocationWriter@@QEAAJHPEAPEAXPEAK@Z; CLocationWriter::AddProperty(int,void * *,ulong *)
0x18000ce1e  mov     ebx, eax
0x18000ce20  test    eax, eax
0x18000ce22  js      short loc_18000CE73
0x18000ce24  mov     rbx, [rsp+1B0h+var_160]
0x18000ce29  inc     esi
0x18000ce2b  jmp     loc_18000CD84
0x18000ce30  sub     edx, 1
0x18000ce33  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ce3a  jz      short loc_18000CE69
0x18000ce3c  mov     rcx, cs:g_pDebug
0x18000ce43  lea     rax, aCfilelistenerM_3; "[CFileListener::MergeRemainingPropertie"...
0x18000ce4a  lea     r9, aCfilelistenerM_10; "CFileListener::MergeRemainingProperties"
0x18000ce51  mov     [rsp+1B0h+var_190], rax
0x18000ce56  mov     r8d, 1122h
0x18000ce5c  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000ce63  call    cs:__imp_PuDbgPrintW
0x18000ce69  mov     ebx, 8007000Dh
0x18000ce6e  jmp     loc_18000CF23
0x18000ce73  test    byte ptr cs:g_dwDebugFlags, 3
0x18000ce7a  jz      loc_18000CF23
0x18000ce80  mov     rax, [rdi+28h]
0x18000ce84  lea     r9, aCfilelistenerM_10; "CFileListener::MergeRemainingProperties"
0x18000ce8b  mov     r8d, 1131h
0x18000ce91  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000ce98  mov     ecx, [rax]
0x18000ce9a  mov     rax, [rdi+20h]
0x18000ce9e  mov     [rsp+1B0h+var_178], ecx
0x18000cea2  mov     rcx, cs:g_pDebug
0x18000cea9  mov     [rsp+1B0h+var_180], rax
0x18000ceae  lea     rax, aCfilelistenerM; "[CFileListener::MergeRemainingPropertie"...
0x18000ceb5  mov     dword ptr [rsp+1B0h+var_188], ebx
0x18000ceb9  mov     [rsp+1B0h+var_190], rax
0x18000cebe  call    cs:__imp_PuDbgPrintW
0x18000cec4  jmp     short loc_18000CF23
0x18000cec6  test    byte ptr cs:g_dwDebugFlags, 3
0x18000cecd  jz      short loc_18000CF39
0x18000cecf  mov     rax, [rdi+28h]
0x18000ced3  lea     r9, aCfilelistenerM_10; "CFileListener::MergeRemainingProperties"
0x18000ceda  mov     r8d, 110Ah
0x18000cee0  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000cee7  mov     ecx, [rax]
0x18000cee9  mov     rax, [rdi+20h]
0x18000ceed  mov     [rsp+1B0h+var_168], ecx
0x18000cef1  mov     rcx, cs:g_pDebug
0x18000cef8  mov     [rsp+1B0h+var_170], rax
0x18000cefd  lea     rax, aCfilelistenerM_0; "[CFileListener::MergeRemainingPropertie"...
0x18000cf04  mov     [rsp+1B0h+var_178], ebx
0x18000cf08  mov     [rsp+1B0h+var_180], r13
0x18000cf0d  mov     dword ptr [rsp+1B0h+var_188], esi
0x18000cf11  mov     [rsp+1B0h+var_190], rax
0x18000cf16  call    cs:__imp_PuDbgPrintW
0x18000cf1c  jmp     short loc_18000CF39
0x18000cf1e  xor     ebx, ebx
0x18000cf20  mov     [r14], esi
0x18000cf23  mov     rcx, [rsp+1B0h+var_160]
0x18000cf28  test    rcx, rcx
0x18000cf2b  jz      short loc_18000CF39
0x18000cf2d  mov     rax, [rcx]
0x18000cf30  mov     rax, [rax+10h]
0x18000cf34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf39  mov     eax, ebx
0x18000cf3b  mov     rcx, [rbp+0B0h+var_40]
0x18000cf3f  xor     rcx, rsp; StackCookie
0x18000cf42  call    __security_check_cookie
0x18000cf47  mov     rbx, [rsp+1B0h+arg_0]
0x18000cf4f  add     rsp, 180h
0x18000cf56  pop     r15
0x18000cf58  pop     r14
0x18000cf5a  pop     r13
0x18000cf5c  pop     r12
0x18000cf5e  pop     rdi
0x18000cf5f  pop     rsi
0x18000cf60  pop     rbp
0x18000cf61  retn
```
