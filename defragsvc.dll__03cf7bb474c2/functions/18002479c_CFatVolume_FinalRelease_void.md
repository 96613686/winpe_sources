# CFatVolume::FinalRelease(void)

- ea: `0x18002479c`
- end: `0x1800249f3`
- name: `?FinalRelease@CFatVolume@@QEAAJXZ`
- size: `599`
- prototype: `__int64 __fastcall(CFatVolume *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800625b4`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001fed8`
- `0x18002479c`
- `0x180024afc`
- `0x1800253bc`

## import_xrefs

- `ntdll!RtlFindSetBits` at `0x180024860`
- `ntdll!RtlFindSetBits` at `0x180024948`
- `ntdll!RtlFindSetBits` at `0x180024860`
- `ntdll!RtlFindSetBits` at `0x180024948`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024805`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024805`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFatVolume::FinalRelease(CFatVolume *this)
{
  CFatVolume *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 i; // rbx
  struct _RTL_BITMAP *v6; // rcx
  ULONG SetBits; // eax
  int Element; // eax
  unsigned int v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // rdi
  ULONG v12; // r14d
  unsigned int j; // ebx
  struct _RTL_BITMAP *v14; // rcx
  ULONG v15; // eax
  int v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-40h] BYREF
  __int16 v19; // [rsp+24h] [rbp-3Ch]
  __int16 v20; // [rsp+26h] [rbp-3Ah]
  struct _QUEUED_DIR *v21; // [rsp+90h] [rbp+30h] BYREF
  __int64 v22; // [rsp+98h] [rbp+38h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v18, "CFatVolume::FinalRelease", 302, 1);
  while ( 1 )
  {
    v3 = *((_QWORD *)this + 49);
    if ( !v3 )
      break;
    v21 = (struct _QUEUED_DIR *)*((_QWORD *)this + 49);
    *((_QWORD *)this + 49) = *(_QWORD *)(v3 + 8);
    CFatVolume::FreeDir(v2, &v21);
  }
  CoTaskMemFree(*((LPVOID *)this + 132));
  *((_QWORD *)this + 132) = 0;
  CVolume::_DestroyVars(this);
  v4 = *((_QWORD *)this + 135);
  *(_QWORD *)(v4 + 40) = 0;
  v22 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0x10000 )
    {
      v9 = 1;
      goto LABEL_17;
    }
    v6 = *(struct _RTL_BITMAP **)(*(_QWORD *)(v4 + 8) + 8 * i);
    if ( v6 )
    {
      if ( v6[2].SizeOfBitMap )
      {
        SetBits = RtlFindSetBits(v6 + 1, 1u, 0);
        if ( SetBits != -1 && SetBits < *(_DWORD *)(v4 + 20) )
          break;
      }
    }
  }
  LODWORD(v21) = *(_DWORD *)(v4 + 28) | ((i & 0xFFF) << 16) | (*(_DWORD *)(v4 + 28) | (SetBits + 1)) & 0xFFFFFFF;
  if ( SetBits + 1 >= *(_DWORD *)(v4 + 20) )
    LODWORD(i) = i + 1;
  *(_DWORD *)(v4 + 40) = i;
  *(_DWORD *)(v4 + 44) = SetBits + 1 < *(_DWORD *)(v4 + 20) ? SetBits + 1 : 0;
  Element = CBulkAllocator<CFatFile>::GetElement(v4, &v21, &v22);
  v9 = Element;
  if ( Element < 0 )
  {
    v18 = Element;
    v20 = 321;
    goto LABEL_36;
  }
  v9 = 0;
LABEL_17:
  v19 = 321;
  while ( 2 )
  {
    v18 = v9;
    if ( v9 == 1 )
      goto LABEL_36;
    v10 = v22;
    CoTaskMemFree(*(LPVOID *)(v22 + 16));
    *(_QWORD *)(v10 + 16) = 0;
    v11 = *((_QWORD *)this + 135);
    v12 = *(_DWORD *)(v11 + 44);
    v22 = 0;
    for ( j = *(_DWORD *)(v11 + 40); ; ++j )
    {
      if ( j >= 0x10000 )
      {
        v9 = 1;
        goto LABEL_34;
      }
      v14 = *(struct _RTL_BITMAP **)(*(_QWORD *)(v11 + 8) + 8LL * j);
      if ( v14 )
      {
        if ( v14[2].SizeOfBitMap )
        {
          v15 = RtlFindSetBits(v14 + 1, 1u, v12);
          if ( v15 )
          {
            if ( v15 == -1 )
              goto LABEL_28;
          }
          else if ( v12 )
          {
            goto LABEL_28;
          }
          if ( v15 < *(_DWORD *)(v11 + 20) )
            break;
        }
      }
LABEL_28:
      v12 = 0;
    }
    LODWORD(v21) = *(_DWORD *)(v11 + 28) | ((j & 0xFFF) << 16) | (*(_DWORD *)(v11 + 28) | (v15 + 1)) & 0xFFFFFFF;
    if ( v15 + 1 >= *(_DWORD *)(v11 + 20) )
      ++j;
    *(_DWORD *)(v11 + 40) = j;
    *(_DWORD *)(v11 + 44) = v15 + 1 < *(_DWORD *)(v11 + 20) ? v15 + 1 : 0;
    v16 = CBulkAllocator<CFatFile>::GetElement(v11, &v21, &v22);
    v9 = v16;
    if ( v16 >= 0 )
    {
      v9 = 0;
LABEL_34:
      v19 = 326;
      continue;
    }
    break;
  }
  v18 = v16;
  v20 = 326;
LABEL_36:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v18);
  return v9;
}

```

## disassembly

```asm
0x18002479c  mov     [rsp-28h+arg_10], rbx
0x1800247a1  mov     [rsp-28h+arg_18], rsi
0x1800247a6  push    rbp
0x1800247a7  push    rdi
0x1800247a8  push    r12
0x1800247aa  push    r13
0x1800247ac  push    r14
0x1800247ae  mov     rbp, rsp
0x1800247b1  sub     rsp, 60h
0x1800247b5  mov     rsi, rcx
0x1800247b8  mov     r12d, 1
0x1800247be  mov     r9d, r12d; unsigned __int16
0x1800247c1  mov     r8d, 12Eh; unsigned __int16
0x1800247c7  lea     rdx, aCfatvolumeFina; "CFatVolume::FinalRelease"
0x1800247ce  lea     rcx, [rbp+var_40]; this
0x1800247d2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800247d7  nop
0x1800247d8  jmp     short loc_1800247F2
0x1800247da  mov     [rbp+arg_0], rax
0x1800247de  mov     rax, [rax+8]
0x1800247e2  mov     [rsi+188h], rax
0x1800247e9  lea     rdx, [rbp+arg_0]; struct _QUEUED_DIR **
0x1800247ed  call    ?FreeDir@CFatVolume@@AEAAXPEAPEAU_QUEUED_DIR@@@Z; CFatVolume::FreeDir(_QUEUED_DIR * *)
0x1800247f2  mov     rax, [rsi+188h]
0x1800247f9  test    rax, rax
0x1800247fc  jnz     short loc_1800247DA
0x1800247fe  mov     rcx, [rsi+420h]; pv
0x180024805  call    cs:__imp_CoTaskMemFree
0x18002480b  mov     qword ptr [rsi+420h], 0
0x180024816  mov     rcx, rsi; this
0x180024819  call    ?_DestroyVars@CVolume@@IEAAJXZ; CVolume::_DestroyVars(void)
0x18002481e  mov     rdi, [rsi+438h]
0x180024825  mov     qword ptr [rdi+28h], 0
0x18002482d  mov     [rbp+arg_8], 0
0x180024835  xor     ebx, ebx
0x180024837  cmp     ebx, 10000h
0x18002483d  jnb     loc_1800248D5
0x180024843  mov     rax, [rdi+8]
0x180024847  mov     rcx, [rax+rbx*8]
0x18002484b  test    rcx, rcx
0x18002484e  jz      short loc_180024870
0x180024850  cmp     dword ptr [rcx+20h], 0
0x180024854  jbe     short loc_180024870
0x180024856  add     rcx, 10h; BitMapHeader
0x18002485a  xor     r8d, r8d; HintIndex
0x18002485d  mov     edx, r12d; NumberToFind
0x180024860  call    cs:__imp_RtlFindSetBits
0x180024866  cmp     eax, 0FFFFFFFEh
0x180024869  ja      short loc_180024870
0x18002486b  cmp     eax, [rdi+14h]
0x18002486e  jb      short loc_180024875
0x180024870  add     ebx, r12d
0x180024873  jmp     short loc_180024837
0x180024875  lea     ecx, [rax+1]
0x180024878  mov     edx, ecx
0x18002487a  or      edx, [rdi+1Ch]
0x18002487d  and     edx, 0FFFFFFFh
0x180024883  mov     eax, ebx
0x180024885  and     eax, 0FFFh
0x18002488a  shl     eax, 10h
0x18002488d  or      edx, eax
0x18002488f  or      edx, [rdi+1Ch]
0x180024892  mov     dword ptr [rbp+arg_0], edx
0x180024895  cmp     ecx, [rdi+14h]
0x180024898  jb      short loc_18002489D
0x18002489a  add     ebx, r12d
0x18002489d  mov     [rdi+28h], ebx
0x1800248a0  cmp     ecx, [rdi+14h]
0x1800248a3  sbb     eax, eax
0x1800248a5  and     eax, ecx
0x1800248a7  mov     [rdi+2Ch], eax
0x1800248aa  lea     r8, [rbp+arg_8]
0x1800248ae  lea     rdx, [rbp+arg_0]
0x1800248b2  mov     rcx, rdi
0x1800248b5  call    ?GetElement@?$CBulkAllocator@VCFatFile@@@@QEAAJPEAKPEAPEAVCFatFile@@@Z; CBulkAllocator<CFatFile>::GetElement(ulong *,CFatFile * *)
0x1800248ba  mov     ebx, eax
0x1800248bc  test    eax, eax
0x1800248be  js      short loc_1800248C4
0x1800248c0  xor     ebx, ebx
0x1800248c2  jmp     short loc_1800248D8
0x1800248c4  mov     [rbp+var_40], eax
0x1800248c7  mov     eax, 141h
0x1800248cc  mov     [rbp+var_3A], ax
0x1800248d0  jmp     loc_1800249CF
0x1800248d5  mov     ebx, r12d
0x1800248d8  mov     eax, 141h
0x1800248dd  mov     [rbp+var_3C], ax
0x1800248e1  lea     r13d, [rax+5]
0x1800248e5  mov     [rbp+var_40], ebx
0x1800248e8  cmp     ebx, r12d
0x1800248eb  jz      loc_1800249CF
0x1800248f1  mov     rbx, [rbp+arg_8]
0x1800248f5  mov     rcx, [rbx+10h]; pv
0x1800248f9  call    cs:__imp_CoTaskMemFree
0x1800248ff  mov     qword ptr [rbx+10h], 0
0x180024907  mov     rdi, [rsi+438h]
0x18002490e  mov     r14d, [rdi+2Ch]
0x180024912  mov     [rbp+arg_8], 0
0x18002491a  mov     ebx, [rdi+28h]
0x18002491d  cmp     ebx, 10000h
0x180024923  jnb     loc_1800249BA
0x180024929  mov     ecx, ebx
0x18002492b  mov     rax, [rdi+8]
0x18002492f  mov     rcx, [rax+rcx*8]
0x180024933  test    rcx, rcx
0x180024936  jz      short loc_180024963
0x180024938  cmp     dword ptr [rcx+20h], 0
0x18002493c  jbe     short loc_180024963
0x18002493e  add     rcx, 10h; BitMapHeader
0x180024942  mov     r8d, r14d; HintIndex
0x180024945  mov     edx, r12d; NumberToFind
0x180024948  call    cs:__imp_RtlFindSetBits
0x18002494e  test    eax, eax
0x180024950  jnz     short loc_180024959
0x180024952  test    r14d, r14d
0x180024955  jnz     short loc_180024963
0x180024957  jmp     short loc_18002495E
0x180024959  cmp     eax, 0FFFFFFFFh
0x18002495c  jz      short loc_180024963
0x18002495e  cmp     eax, [rdi+14h]
0x180024961  jb      short loc_18002496B
0x180024963  xor     r14d, r14d
0x180024966  add     ebx, r12d
0x180024969  jmp     short loc_18002491D
0x18002496b  lea     ecx, [rax+1]
0x18002496e  mov     edx, ecx
0x180024970  or      edx, [rdi+1Ch]
0x180024973  and     edx, 0FFFFFFFh
0x180024979  mov     eax, ebx
0x18002497b  and     eax, 0FFFh
0x180024980  shl     eax, 10h
0x180024983  or      edx, eax
0x180024985  or      edx, [rdi+1Ch]
0x180024988  mov     dword ptr [rbp+arg_0], edx
0x18002498b  cmp     ecx, [rdi+14h]
0x18002498e  jb      short loc_180024993
0x180024990  add     ebx, r12d
0x180024993  mov     [rdi+28h], ebx
0x180024996  cmp     ecx, [rdi+14h]
0x180024999  sbb     eax, eax
0x18002499b  and     eax, ecx
0x18002499d  mov     [rdi+2Ch], eax
0x1800249a0  lea     r8, [rbp+arg_8]
0x1800249a4  lea     rdx, [rbp+arg_0]
0x1800249a8  mov     rcx, rdi
0x1800249ab  call    ?GetElement@?$CBulkAllocator@VCFatFile@@@@QEAAJPEAKPEAPEAVCFatFile@@@Z; CBulkAllocator<CFatFile>::GetElement(ulong *,CFatFile * *)
0x1800249b0  mov     ebx, eax
0x1800249b2  test    eax, eax
0x1800249b4  js      short loc_1800249C7
0x1800249b6  xor     ebx, ebx
0x1800249b8  jmp     short loc_1800249BD
0x1800249ba  mov     ebx, r12d
0x1800249bd  mov     [rbp+var_3C], r13w
0x1800249c2  jmp     loc_1800248E5
0x1800249c7  mov     [rbp+var_40], eax
0x1800249ca  mov     [rbp+var_3A], r13w
0x1800249cf  lea     rcx, [rbp+var_40]; this
0x1800249d3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800249d8  mov     eax, ebx
0x1800249da  lea     r11, [rsp+60h+var_s0]
0x1800249df  mov     rbx, [r11+40h]
0x1800249e3  mov     rsi, [r11+48h]
0x1800249e7  mov     rsp, r11
0x1800249ea  pop     r14
0x1800249ec  pop     r13
0x1800249ee  pop     r12
0x1800249f0  pop     rdi
0x1800249f1  pop     rbp
0x1800249f2  retn
```
