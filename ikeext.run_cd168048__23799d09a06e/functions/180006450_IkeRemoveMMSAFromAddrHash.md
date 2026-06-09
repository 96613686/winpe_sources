# IkeRemoveMMSAFromAddrHash

- ea: `0x180006450`
- end: `0x180006865`
- name: `IkeRemoveMMSAFromAddrHash`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000b940`

## callees

- `0x1800061ec`
- `0x180006450`
- `0x180008310`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x18005e8f0`
- `0x180117f9c`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180006678`
- `ntdll!RtlRemoveEntryHashTable` at `0x180006678`
- `ntdll!RtlLookupEntryHashTable` at `0x18000670d`
- `ntdll!RtlLookupEntryHashTable` at `0x18000670d`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000651d`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000651d`
- `ntdll!RtlExpandHashTable` at `0x18000683a`
- `ntdll!RtlExpandHashTable` at `0x18000683a`
- `ntdll!RtlContractHashTable` at `0x1800066b0`
- `ntdll!RtlContractHashTable` at `0x1800066b0`

## string_xrefs

- `0x180006495`: `IkeRemoveMMSAFromAddrHash`
- `0x1800066c0`: `IkeRemoveMMSAFromAddrHash`
- `0x1800066cc`: `IkeRemoveMMSAFromAddrHash`
- `0x18000681d`: `IkeRemoveMMSAFromAddrHash`

## pseudocode

```c
__int64 __fastcall IkeRemoveMMSAFromAddrHash(__int64 a1, __int64 *a2)
{
  __int64 v3; // r13
  __int64 v4; // r15
  __int64 v5; // rcx
  __int64 v6; // rbx
  _BYTE *v7; // r12
  __int64 v8; // r14
  LONG *p_LockCount; // rcx
  __int64 NextEntryHashTable; // rax
  __int64 v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rsi
  LONG *v16; // rbx
  unsigned int OwningThread; // ecx
  unsigned int LockSemaphore_high; // edi
  __int64 v20; // rdx
  __int64 i; // rax
  __int64 v22; // rdx
  __int64 j; // rdx
  __int64 v24; // rcx
  size_t Size; // [rsp+20h] [rbp-50h] BYREF
  void *Buf2; // [rsp+28h] [rbp-48h] BYREF
  void *Buf1; // [rsp+30h] [rbp-40h] BYREF
  int v28; // [rsp+38h] [rbp-38h]
  __int64 v29; // [rsp+40h] [rbp-30h]
  __int64 *v30; // [rsp+48h] [rbp-28h]
  __int128 v31; // [rsp+50h] [rbp-20h] BYREF
  __int64 v32; // [rsp+60h] [rbp-10h]

  v30 = a2;
  v29 = a1;
  v28 = 1;
  v32 = 0;
  v3 = 0;
  v31 = 0;
  TraceLogHelper("IkeRemoveMMSAFromAddrHash", 1);
  v4 = a1 + 376;
  Buf2 = 0;
  v5 = a1 + 376;
  LODWORD(Size) = 0;
  v6 = 0;
  IkeAddrGetAddrBytes(v5, &Buf2, &Size);
  if ( Buf2 )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)Size; v6 = v22 + 37 * v6 )
    {
      v22 = *((unsigned __int8 *)Buf2 + i);
      i = (unsigned int)(i + 1);
    }
  }
  v7 = (_BYTE *)(v4 + 60);
  IkeAddrGetAddrBytes(v4 + 60, &Buf2, &Size);
  if ( Buf2 )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)Size; v6 = v24 + 37 * v6 )
    {
      v24 = *((unsigned __int8 *)Buf2 + j);
      j = (unsigned int)(j + 1);
    }
  }
  while ( 1 )
  {
    v8 = 0;
    while ( 1 )
    {
      p_LockCount = &gIkeExtGlobals[55].LockCount;
      if ( v28 )
      {
        v20 = v6;
        if ( !v6 )
          v20 = -1;
        NextEntryHashTable = RtlLookupEntryHashTable(p_LockCount, v20, &v31);
        v28 = 0;
      }
      else
      {
        NextEntryHashTable = RtlGetNextEntryHashTable(p_LockCount, &v31);
      }
      v11 = NextEntryHashTable;
      if ( !NextEntryHashTable )
        break;
      v12 = *(_QWORD *)(NextEntryHashTable + 24) + 376LL;
      LODWORD(Size) = 0;
      Buf1 = 0;
      Buf2 = 0;
      if ( *v7 == *(_BYTE *)(v12 + 60) )
      {
        IkeAddrGetAddrBytes(v7, &Buf1, &Size);
        IkeAddrGetAddrBytes(v12 + 60, &Buf2, &Size);
        if ( !memcmp_0(Buf1, Buf2, (unsigned int)Size) )
        {
          if ( (unsigned __int8)(*v7 - 7) > 1u
            || (IkeAddrGetAddrBytesHigh(v7, &Buf1, &Size),
                IkeAddrGetAddrBytesHigh(v12 + 60, &Buf2, &Size),
                !memcmp_0(Buf1, Buf2, (unsigned int)Size)) )
          {
            v13 = v29;
            LODWORD(Size) = 0;
            Buf2 = 0;
            Buf1 = 0;
            if ( *(_BYTE *)(v29 + 376) == *(_BYTE *)v12 )
            {
              IkeAddrGetAddrBytes(v29 + 376, &Buf2, &Size);
              IkeAddrGetAddrBytes(v12, &Buf1, &Size);
              if ( !memcmp_0(Buf2, Buf1, (unsigned int)Size) )
              {
                if ( (unsigned __int8)(*(_BYTE *)(v13 + 376) - 7) > 1u
                  || (IkeAddrGetAddrBytesHigh(v13 + 376, &Buf2, &Size),
                      IkeAddrGetAddrBytesHigh(v12, &Buf1, &Size),
                      !memcmp_0(Buf2, Buf1, (unsigned int)Size)) )
                {
                  if ( *(_QWORD *)(v13 + 496) == *(_QWORD *)(v12 + 120) )
                  {
                    v8 = *(_QWORD *)(v11 + 24);
                    v3 = v11;
                    break;
                  }
                }
              }
            }
          }
        }
      }
    }
    v15 = IkeReturnError(0, "IkeNextFindAddrMatch");
    if ( v15 )
      break;
    if ( v8 == v29 )
    {
      RtlRemoveEntryHashTable(&gIkeExtGlobals[55].LockCount, v3, 0);
      if ( v30 )
        *v30 = v3;
      v16 = &gIkeExtGlobals[55].LockCount;
      OwningThread = (unsigned int)gIkeExtGlobals[55].OwningThread;
      LockSemaphore_high = HIDWORD(gIkeExtGlobals[55].LockSemaphore);
      if ( LockSemaphore_high > 3 * OwningThread )
      {
        while ( (unsigned __int8)RtlExpandHashTable(v16) && LockSemaphore_high > 3 * v16[2] )
          ;
      }
      else if ( LockSemaphore_high < OwningThread )
      {
        while ( (unsigned __int8)RtlContractHashTable(v16) && LockSemaphore_high < v16[2] )
          ;
      }
      break;
    }
    if ( !v8 )
    {
      v15 = WfpReportSysErrorAsWinError(v14, "IkeRemoveMMSAFromAddrHash", 1168, 1);
      break;
    }
  }
  TraceLogHelper("IkeRemoveMMSAFromAddrHash", 0);
  return IkeReturnError(v15, "IkeRemoveMMSAFromAddrHash");
}

```

## disassembly

```asm
0x180006450  mov     [rsp-38h+arg_10], rbx
0x180006455  push    rbp
0x180006456  push    rsi
0x180006457  push    rdi
0x180006458  push    r12
0x18000645a  push    r13
0x18000645c  push    r14
0x18000645e  push    r15
0x180006460  mov     rbp, rsp
0x180006463  sub     rsp, 70h
0x180006467  mov     rax, cs:__security_cookie
0x18000646e  xor     rax, rsp
0x180006471  mov     [rbp+var_8], rax
0x180006475  mov     [rbp+var_28], rdx
0x180006479  mov     rbx, rcx
0x18000647c  mov     [rbp+var_30], rcx
0x180006480  xorps   xmm0, xmm0
0x180006483  xor     eax, eax
0x180006485  mov     [rbp+var_38], 1
0x18000648c  mov     edx, 1
0x180006491  mov     [rbp+var_10], rax
0x180006495  lea     rcx, aIkeremovemmsaf_0; "IkeRemoveMMSAFromAddrHash"
0x18000649c  xor     r13d, r13d
0x18000649f  movups  [rbp+var_20], xmm0
0x1800064a3  call    TraceLogHelper
0x1800064a8  lea     r15, [rbx+178h]
0x1800064af  mov     [rbp+Buf2], r13
0x1800064b3  mov     rcx, r15
0x1800064b6  mov     dword ptr [rbp+Size], r13d
0x1800064ba  lea     r8, [rbp+Size]
0x1800064be  xor     ebx, ebx
0x1800064c0  lea     rdx, [rbp+Buf2]
0x1800064c4  call    IkeAddrGetAddrBytes
0x1800064c9  mov     r8, [rbp+Buf2]
0x1800064cd  test    r8, r8
0x1800064d0  jnz     loc_18000671C
0x1800064d6  lea     r12, [r15+3Ch]
0x1800064da  mov     rcx, r12
0x1800064dd  lea     r8, [rbp+Size]
0x1800064e1  lea     rdx, [rbp+Buf2]
0x1800064e5  call    IkeAddrGetAddrBytes
0x1800064ea  mov     r8, [rbp+Buf2]
0x1800064ee  test    r8, r8
0x1800064f1  jnz     loc_180006748
0x1800064f7  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800064fe  xor     r14d, r14d
0x180006501  mov     rcx, cs:gIkeExtGlobals
0x180006508  add     rcx, 8A0h
0x18000650f  cmp     [rbp+var_38], r14d
0x180006513  jnz     loc_1800066FF
0x180006519  lea     rdx, [rbp+var_20]
0x18000651d  call    cs:__imp_RtlGetNextEntryHashTable
0x180006523  mov     rdi, rax
0x180006526  test    rax, rax
0x180006529  jz      loc_180006644
0x18000652f  mov     rsi, [rax+18h]
0x180006533  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000653a  add     rsi, 178h
0x180006541  mov     dword ptr [rbp+Size], r14d
0x180006545  mov     [rbp+Buf1], r14
0x180006549  mov     [rbp+Buf2], r14
0x18000654d  movzx   eax, byte ptr [rsi+3Ch]
0x180006551  cmp     [r12], al
0x180006555  jnz     short loc_180006501
0x180006557  lea     r8, [rbp+Size]
0x18000655b  mov     rcx, r12
0x18000655e  lea     rdx, [rbp+Buf1]
0x180006562  call    IkeAddrGetAddrBytes
0x180006567  lea     rcx, [rsi+3Ch]
0x18000656b  lea     r8, [rbp+Size]
0x18000656f  lea     rdx, [rbp+Buf2]
0x180006573  call    IkeAddrGetAddrBytes
0x180006578  mov     rcx, [rbp+Buf1]; Buf1
0x18000657c  mov     r8d, dword ptr [rbp+Size]; Size
0x180006580  mov     rdx, [rbp+Buf2]; Buf2
0x180006584  call    memcmp_0
0x180006589  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180006590  test    eax, eax
0x180006592  jnz     loc_180006501
0x180006598  movzx   eax, byte ptr [r12]
0x18000659d  sub     al, 7
0x18000659f  cmp     al, 1
0x1800065a1  jbe     loc_180006778
0x1800065a7  mov     r15, [rbp+var_30]
0x1800065ab  xor     eax, eax
0x1800065ad  mov     dword ptr [rbp+Size], eax
0x1800065b0  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800065b7  mov     [rbp+Buf2], rax
0x1800065bb  mov     [rbp+Buf1], rax
0x1800065bf  movzx   eax, byte ptr [rsi]
0x1800065c2  cmp     [r15+178h], al
0x1800065c9  jnz     loc_180006501
0x1800065cf  lea     r8, [rbp+Size]
0x1800065d3  lea     rdx, [rbp+Buf2]
0x1800065d7  lea     rcx, [r15+178h]
0x1800065de  call    IkeAddrGetAddrBytes
0x1800065e3  mov     rcx, rsi
0x1800065e6  lea     r8, [rbp+Size]
0x1800065ea  lea     rdx, [rbp+Buf1]
0x1800065ee  call    IkeAddrGetAddrBytes
0x1800065f3  mov     rcx, [rbp+Buf2]; Buf1
0x1800065f7  mov     r8d, dword ptr [rbp+Size]; Size
0x1800065fb  mov     rdx, [rbp+Buf1]; Buf2
0x1800065ff  call    memcmp_0
0x180006604  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000660b  test    eax, eax
0x18000660d  jnz     loc_180006501
0x180006613  movzx   eax, byte ptr [r15+178h]
0x18000661b  sub     al, 7
0x18000661d  cmp     al, 1
0x18000661f  jbe     loc_1800067BE
0x180006625  mov     rax, [rsi+78h]
0x180006629  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180006630  cmp     [r15+1F0h], rax
0x180006637  jnz     loc_180006501
0x18000663d  mov     r14, [rdi+18h]
0x180006641  mov     r13, rdi
0x180006644  lea     rdx, aIkenextfindadd; "IkeNextFindAddrMatch"
0x18000664b  xor     ecx, ecx
0x18000664d  call    IkeReturnError
0x180006652  mov     rsi, rax
0x180006655  test    rax, rax
0x180006658  jnz     short loc_1800066BE
0x18000665a  cmp     r14, [rbp+var_30]
0x18000665e  jnz     loc_180006807
0x180006664  mov     rcx, cs:gIkeExtGlobals
0x18000666b  xor     r8d, r8d
0x18000666e  add     rcx, 8A0h
0x180006675  mov     rdx, r13
0x180006678  call    cs:__imp_RtlRemoveEntryHashTable
0x18000667e  mov     rax, [rbp+var_28]
0x180006682  test    rax, rax
0x180006685  jz      short loc_18000668A
0x180006687  mov     [rax], r13
0x18000668a  mov     rbx, cs:gIkeExtGlobals
0x180006691  add     rbx, 8A0h
0x180006698  mov     ecx, [rbx+8]
0x18000669b  mov     edi, [rbx+14h]
0x18000669e  lea     eax, [rcx+rcx*2]
0x1800066a1  cmp     edi, eax
0x1800066a3  ja      loc_180006837
0x1800066a9  cmp     edi, ecx
0x1800066ab  jnb     short loc_1800066BE
0x1800066ad  mov     rcx, rbx
0x1800066b0  call    cs:__imp_RtlContractHashTable
0x1800066b6  test    al, al
0x1800066b8  jnz     loc_180006857
0x1800066be  xor     edx, edx
0x1800066c0  lea     rcx, aIkeremovemmsaf_0; "IkeRemoveMMSAFromAddrHash"
0x1800066c7  call    TraceLogHelper
0x1800066cc  lea     rdx, aIkeremovemmsaf_0; "IkeRemoveMMSAFromAddrHash"
0x1800066d3  mov     rcx, rsi
0x1800066d6  call    IkeReturnError
0x1800066db  mov     rcx, [rbp+var_8]
0x1800066df  xor     rcx, rsp; StackCookie
0x1800066e2  call    __security_check_cookie
0x1800066e7  mov     rbx, [rsp+70h+arg_10]
0x1800066ef  add     rsp, 70h
0x1800066f3  pop     r15
0x1800066f5  pop     r14
0x1800066f7  pop     r13
0x1800066f9  pop     r12
0x1800066fb  pop     rdi
0x1800066fc  pop     rsi
0x1800066fd  pop     rbp
0x1800066fe  retn
0x1800066ff  test    rbx, rbx
0x180006702  mov     rdx, rbx
0x180006705  cmovz   rdx, r8
0x180006709  lea     r8, [rbp+var_20]
0x18000670d  call    cs:__imp_RtlLookupEntryHashTable
0x180006713  mov     [rbp+var_38], r14d
0x180006717  jmp     loc_180006523
0x18000671c  mov     r9d, dword ptr [rbp+Size]
0x180006720  xor     eax, eax
0x180006722  test    r9d, r9d
0x180006725  jz      loc_1800064D6
0x18000672b  nop     dword ptr [rax+rax+00h]
0x180006730  movzx   edx, byte ptr [rax+r8]
0x180006735  inc     eax
0x180006737  imul    rbx, 25h ; '%'
0x18000673b  add     rbx, rdx
0x18000673e  cmp     eax, r9d
0x180006741  jb      short loc_180006730
0x180006743  jmp     loc_1800064D6
0x180006748  mov     r9d, dword ptr [rbp+Size]
0x18000674c  xor     edx, edx
0x18000674e  test    r9d, r9d
0x180006751  jz      loc_1800064F7
0x180006757  nop     word ptr [rax+rax+00000000h]
0x180006760  movzx   ecx, byte ptr [rdx+r8]
0x180006765  inc     edx
0x180006767  imul    rbx, 25h ; '%'
0x18000676b  add     rbx, rcx
0x18000676e  cmp     edx, r9d
0x180006771  jb      short loc_180006760
0x180006773  jmp     loc_1800064F7
0x180006778  lea     r8, [rbp+Size]
0x18000677c  mov     rcx, r12
0x18000677f  lea     rdx, [rbp+Buf1]
0x180006783  call    IkeAddrGetAddrBytesHigh
0x180006788  lea     rcx, [rsi+3Ch]
0x18000678c  lea     r8, [rbp+Size]
0x180006790  lea     rdx, [rbp+Buf2]
0x180006794  call    IkeAddrGetAddrBytesHigh
0x180006799  mov     rcx, [rbp+Buf1]; Buf1
0x18000679d  mov     r8d, dword ptr [rbp+Size]; Size
0x1800067a1  mov     rdx, [rbp+Buf2]; Buf2
0x1800067a5  call    memcmp_0
0x1800067aa  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800067b1  test    eax, eax
0x1800067b3  jnz     loc_180006501
0x1800067b9  jmp     loc_1800065A7
0x1800067be  lea     r8, [rbp+Size]
0x1800067c2  lea     rdx, [rbp+Buf2]
0x1800067c6  lea     rcx, [r15+178h]
0x1800067cd  call    IkeAddrGetAddrBytesHigh
0x1800067d2  mov     rcx, rsi
0x1800067d5  lea     r8, [rbp+Size]
0x1800067d9  lea     rdx, [rbp+Buf1]
0x1800067dd  call    IkeAddrGetAddrBytesHigh
0x1800067e2  mov     rcx, [rbp+Buf2]; Buf1
0x1800067e6  mov     r8d, dword ptr [rbp+Size]; Size
0x1800067ea  mov     rdx, [rbp+Buf1]; Buf2
0x1800067ee  call    memcmp_0
0x1800067f3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800067fa  test    eax, eax
0x1800067fc  jnz     loc_180006501
0x180006802  jmp     loc_180006625
0x180006807  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000680e  test    r14, r14
0x180006811  jnz     loc_1800064FE
0x180006817  mov     r9d, 1
0x18000681d  lea     rdx, aIkeremovemmsaf_0; "IkeRemoveMMSAFromAddrHash"
0x180006824  mov     r8d, 490h
0x18000682a  call    WfpReportSysErrorAsWinError
0x18000682f  mov     rsi, rax
0x180006832  jmp     loc_1800066BE
0x180006837  mov     rcx, rbx
0x18000683a  call    cs:__imp_RtlExpandHashTable
0x180006840  test    al, al
0x180006842  jz      loc_1800066BE
0x180006848  mov     eax, [rbx+8]
0x18000684b  lea     ecx, [rax+rax*2]
0x18000684e  cmp     edi, ecx
0x180006850  ja      short loc_180006837
0x180006852  jmp     loc_1800066BE
0x180006857  cmp     edi, [rbx+8]
0x18000685a  jb      loc_1800066AD
0x180006860  jmp     loc_1800066BE
```
