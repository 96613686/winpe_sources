# EfspAuditProtectionRemoved

- ea: `0x1800184c8`
- end: `0x180018736`
- name: `EfspAuditProtectionRemoved`
- size: `622`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180013c68`
- `0x18001441c`
- `0x18004e17c`

## callees

- `0x180010920`
- `0x1800184c8`
- `0x180061164`
- `0x180061188`
- `0x1800612fc`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800185bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800186a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800185bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800186a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800185cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800186db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800186f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018712`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800186db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800186f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018712`
- `ntdll!RtlInitUnicodeString` at `0x18001863b`
- `ntdll!RtlInitUnicodeString` at `0x18001863b`
- `edpauditapi!EdpAuditLogProtectionRemoved` at `0x180018649`
- `edpauditapi!EdpAuditLogProtectionRemoved` at `0x180018649`

## string_xrefs

- `0x180018628`: `Protection removed`

## pseudocode

```c
__int64 __fastcall EfspAuditProtectionRemoved(__int64 a1)
{
  WCHAR *v1; // rbx
  unsigned int v3; // eax
  unsigned int v4; // r14d
  int v5; // eax
  __int64 i; // rdi
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v10; // eax
  int v11; // eax
  HANDLE v12; // rax
  __int64 j; // rbx
  __int64 v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  PCWSTR SourceString; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v19[56]; // [rsp+38h] [rbp-38h] BYREF
  bool v20; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v21; // [rsp+C0h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp+58h] BYREF

  v21 = 0;
  hMem = 0;
  v1 = 0;
  SourceString = 0;
  memset(v19, 0, sizeof(v19));
  v3 = EfsDllQueryProtectorsSrv(a1, &v21, &hMem);
  v4 = v3;
  if ( v3 )
  {
    v5 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v3, 10, 188);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v5, 10, 188);
  }
  else
  {
    for ( i = 0; (unsigned int)i < v21; i = (unsigned int)(i + 1) )
    {
      v7 = *((_QWORD *)hMem + i);
      v8 = *(const unsigned __int16 **)(v7 + 16);
      if ( v8
        && *(_QWORD *)(v7 + 8)
        && (EfsCheckIsDpapiNgEntId(v8) || EfsCheckIsRmsEntId(*(const unsigned __int16 **)(*((_QWORD *)hMem + i) + 16LL))) )
      {
        if ( v1 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v1);
          SourceString = 0;
        }
        v20 = 0;
        if ( (int)EfsConvertProtectorToExternalId(
                    *(const unsigned __int16 **)(*((_QWORD *)hMem + i) + 16LL),
                    (unsigned __int16 **)&SourceString,
                    &v20) >= 0
          && v20 )
        {
          v1 = (WCHAR *)SourceString;
          *(_WORD *)v19 = 1;
          *(_QWORD *)&v19[8] = *(_QWORD *)(*((_QWORD *)hMem + i) + 8LL);
          *(_QWORD *)&v19[16] = L"Protection removed";
          *(_QWORD *)&v19[24] = 0;
          RtlInitUnicodeString((PUNICODE_STRING)&v19[32], SourceString);
          *(_QWORD *)&v19[48] = a1;
          v10 = EdpAuditLogProtectionRemoved(v19);
          v4 = v10;
          if ( v10 )
          {
            v11 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v10, 10, 244);
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 10, 244);
            break;
          }
        }
        else
        {
          v1 = (WCHAR *)SourceString;
        }
      }
    }
    if ( v1 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v1);
    }
  }
  if ( hMem )
  {
    for ( j = 0; (unsigned int)j < v21; j = (unsigned int)(j + 1) )
    {
      v14 = *((_QWORD *)hMem + j);
      if ( v14 )
      {
        v15 = *(void **)(v14 + 16);
        if ( v15 )
          LocalFree(v15);
        v16 = *(void **)(*((_QWORD *)hMem + j) + 8LL);
        if ( v16 )
          LocalFree(v16);
        LocalFree(*((HLOCAL *)hMem + j));
      }
    }
    LocalFree(hMem);
  }
  return v4;
}

```

## disassembly

```asm
0x1800184c8  push    rbp
0x1800184ca  push    rbx
0x1800184cb  push    rsi
0x1800184cc  push    rdi
0x1800184cd  push    r13
0x1800184cf  push    r14
0x1800184d1  push    r15
0x1800184d3  mov     rbp, rsp
0x1800184d6  sub     rsp, 70h
0x1800184da  xorps   xmm0, xmm0
0x1800184dd  mov     [rbp+arg_10], 0
0x1800184e4  xor     eax, eax
0x1800184e6  mov     [rbp+hMem], 0
0x1800184ee  movups  xmmword ptr [rbp+var_16], xmm0
0x1800184f2  xor     ebx, ebx
0x1800184f4  mov     qword ptr [rbp+var_16+0Eh], rax
0x1800184f8  lea     r8, [rbp+hMem]
0x1800184fc  mov     [rbp+SourceString], rbx
0x180018500  lea     rdx, [rbp+arg_10]
0x180018504  mov     [rbp+var_38], ax
0x180018508  mov     r15, rcx
0x18001850b  movups  [rbp+var_36], xmm0
0x18001850f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180018513  call    EfsDllQueryProtectorsSrv
0x180018518  lea     r13d, [rbx+1]
0x18001851c  mov     r14d, eax
0x18001851f  test    eax, eax
0x180018521  jz      short loc_18001856B
0x180018523  mov     rcx, cs:g_hPublisher
0x18001852a  lea     edi, [r13+9]
0x18001852e  mov     ebx, 17BCh
0x180018533  lea     rdx, EFS_API_ERROR
0x18001853a  mov     r9d, edi
0x18001853d  mov     [rsp+70h+var_50], ebx
0x180018541  mov     r8d, eax
0x180018544  call    fnEfsLogTrace1
0x180018549  mov     rcx, cs:g_hPublisher
0x180018550  lea     rdx, EFS_TRACE_ERROR
0x180018557  mov     r9d, edi
0x18001855a  mov     [rsp+70h+var_50], ebx
0x18001855e  mov     r8d, eax
0x180018561  call    fnEfsLogTrace1
0x180018566  jmp     loc_1800186B7
0x18001856b  xor     edi, edi
0x18001856d  cmp     edi, [rbp+arg_10]
0x180018570  jnb     loc_18001869E
0x180018576  mov     rax, [rbp+hMem]
0x18001857a  mov     rdx, [rax+rdi*8]
0x18001857e  mov     rcx, [rdx+10h]; unsigned __int16 *
0x180018582  test    rcx, rcx
0x180018585  jz      loc_18001872E
0x18001858b  cmp     qword ptr [rdx+8], 0
0x180018590  jz      loc_18001872E
0x180018596  call    ?EfsCheckIsDpapiNgEntId@@YA_NPEBG@Z; EfsCheckIsDpapiNgEntId(ushort const *)
0x18001859b  test    al, al
0x18001859d  jnz     short loc_1800185B8
0x18001859f  mov     rax, [rbp+hMem]
0x1800185a3  mov     rcx, [rax+rdi*8]
0x1800185a7  mov     rcx, [rcx+10h]; unsigned __int16 *
0x1800185ab  call    ?EfsCheckIsRmsEntId@@YA_NPEBG@Z; EfsCheckIsRmsEntId(ushort const *)
0x1800185b0  test    al, al
0x1800185b2  jz      loc_18001872E
0x1800185b8  test    rbx, rbx
0x1800185bb  jz      short loc_1800185D9
0x1800185bd  call    cs:__imp_GetProcessHeap
0x1800185c3  mov     r8, rbx; lpMem
0x1800185c6  xor     edx, edx; dwFlags
0x1800185c8  mov     rcx, rax; hHeap
0x1800185cb  call    cs:__imp_HeapFree
0x1800185d1  mov     [rbp+SourceString], 0
0x1800185d9  mov     rax, [rbp+hMem]
0x1800185dd  lea     r8, [rbp+arg_8]; bool *
0x1800185e1  lea     rdx, [rbp+SourceString]; unsigned __int16 **
0x1800185e5  mov     [rbp+arg_8], 0
0x1800185e9  mov     rcx, [rax+rdi*8]
0x1800185ed  mov     rcx, [rcx+10h]; unsigned __int16 *
0x1800185f1  call    ?EfsConvertProtectorToExternalId@@YAJPEBGPEAPEAGPEA_N@Z; EfsConvertProtectorToExternalId(ushort const *,ushort * *,bool *)
0x1800185f6  test    eax, eax
0x1800185f8  js      loc_18001872A
0x1800185fe  cmp     [rbp+arg_8], 0
0x180018602  jz      loc_18001872A
0x180018608  mov     rax, [rbp+hMem]
0x18001860c  mov     rbx, [rbp+SourceString]
0x180018610  mov     [rbp+var_38], r13w
0x180018615  mov     rdx, rbx; SourceString
0x180018618  mov     rcx, [rax+rdi*8]
0x18001861c  mov     rax, [rcx+8]
0x180018620  lea     rcx, [rbp+DestinationString.Buffer+6]; DestinationString
0x180018624  mov     qword ptr [rbp+var_36+6], rax
0x180018628  lea     rax, EDP_AUDIT_POLICY_PROTECTION_REMOVED; "Protection removed"
0x18001862f  mov     qword ptr [rbp+var_36+0Eh], rax
0x180018633  mov     qword ptr [rbp+DestinationString+6], 0
0x18001863b  call    cs:__imp_RtlInitUnicodeString
0x180018641  lea     rcx, [rbp+var_38]
0x180018645  mov     qword ptr [rbp+var_16+0Eh], r15
0x180018649  call    cs:__imp_EdpAuditLogProtectionRemoved
0x18001864f  mov     r14d, eax
0x180018652  test    eax, eax
0x180018654  jz      loc_18001872E
0x18001865a  mov     rcx, cs:g_hPublisher
0x180018661  lea     rdx, EFS_API_ERROR
0x180018668  mov     edi, 0Ah
0x18001866d  mov     esi, 17F4h
0x180018672  mov     r9d, edi
0x180018675  mov     [rsp+70h+var_50], esi
0x180018679  mov     r8d, eax
0x18001867c  call    fnEfsLogTrace1
0x180018681  mov     rcx, cs:g_hPublisher
0x180018688  lea     rdx, EFS_TRACE_ERROR
0x18001868f  mov     r9d, edi
0x180018692  mov     [rsp+70h+var_50], esi
0x180018696  mov     r8d, eax
0x180018699  call    fnEfsLogTrace1
0x18001869e  test    rbx, rbx
0x1800186a1  jz      short loc_1800186B7
0x1800186a3  call    cs:__imp_GetProcessHeap
0x1800186a9  mov     r8, rbx; lpMem
0x1800186ac  xor     edx, edx; dwFlags
0x1800186ae  mov     rcx, rax; hHeap
0x1800186b1  call    cs:__imp_HeapFree
0x1800186b7  cmp     [rbp+hMem], 0
0x1800186bc  jz      short loc_180018718
0x1800186be  xor     ebx, ebx
0x1800186c0  cmp     [rbp+arg_10], ebx
0x1800186c3  jbe     short loc_18001870E
0x1800186c5  mov     rax, [rbp+hMem]
0x1800186c9  mov     rcx, [rax+rbx*8]
0x1800186cd  test    rcx, rcx
0x1800186d0  jz      short loc_180018706
0x1800186d2  mov     rcx, [rcx+10h]; hMem
0x1800186d6  test    rcx, rcx
0x1800186d9  jz      short loc_1800186E1
0x1800186db  call    cs:__imp_LocalFree
0x1800186e1  mov     rax, [rbp+hMem]
0x1800186e5  mov     rcx, [rax+rbx*8]
0x1800186e9  mov     rcx, [rcx+8]; hMem
0x1800186ed  test    rcx, rcx
0x1800186f0  jz      short loc_1800186F8
0x1800186f2  call    cs:__imp_LocalFree
0x1800186f8  mov     rcx, [rbp+hMem]
0x1800186fc  mov     rcx, [rcx+rbx*8]; hMem
0x180018700  call    cs:__imp_LocalFree
0x180018706  add     ebx, r13d
0x180018709  cmp     ebx, [rbp+arg_10]
0x18001870c  jb      short loc_1800186C5
0x18001870e  mov     rcx, [rbp+hMem]; hMem
0x180018712  call    cs:__imp_LocalFree
0x180018718  mov     eax, r14d
0x18001871b  add     rsp, 70h
0x18001871f  pop     r15
0x180018721  pop     r14
0x180018723  pop     r13
0x180018725  pop     rdi
0x180018726  pop     rsi
0x180018727  pop     rbx
0x180018728  pop     rbp
0x180018729  retn
0x18001872a  mov     rbx, [rbp+SourceString]
0x18001872e  add     edi, r13d
0x180018731  jmp     loc_18001856D
```
