# NetpAllocFtinfoEntry2

- ea: `0x180037768`
- end: `0x18003796e`
- name: `NetpAllocFtinfoEntry2`
- size: `518`
- prototype: ``
- caller_count: `12`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025340`
- `0x180028c84`
- `0x18003759c`
- `0x180037688`
- `0x180038670`
- `0x1800391b8`
- `0x1800399dc`
- `0x180039ca4`
- `0x180039fe0`
- `0x18003a1f8`
- `0x18003a3ac`
- `0x18003a768`

## callees

- `0x180001fb8`
- `0x180037768`
- `0x180037b40`
- `0x180038af0`
- `0x180039ec0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800377cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800377cf`
- `ntdll!RtlAllocateHeap` at `0x1800378de`
- `ntdll!RtlAllocateHeap` at `0x1800378de`
- `ntdll!RtlLengthSid` at `0x180037828`
- `ntdll!RtlLengthSid` at `0x180037864`
- `ntdll!RtlLengthSid` at `0x180037828`
- `ntdll!RtlLengthSid` at `0x180037864`

## pseudocode

```c
char *__fastcall NetpAllocFtinfoEntry2(_DWORD *a1, unsigned int *a2)
{
  unsigned int *v2; // rbx
  bool v3; // zf
  ULONG v5; // edi
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int *v9; // rsi
  int v10; // ebx
  HLOCAL v11; // rcx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  void *v16; // rcx
  ULONG v17; // edx
  void *v18; // rcx
  unsigned int v19; // ebp
  _DWORD *Heap; // rax
  _DWORD *v21; // rsi
  __int64 v22; // rax
  char *result; // rax
  char *v24; // [rsp+68h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+18h] BYREF

  v2 = a2;
  v3 = a2[1] == 3;
  v5 = 0;
  LODWORD(v24) = 0;
  if ( v3 )
  {
    v6 = a2[4];
    v7 = *((_QWORD *)a2 + 3);
    v8 = *a2;
    v9 = 0;
    hMem = 0;
    v10 = NetpBuildRecordFromBinary(v8, a2 + 2, v7, v6, &hMem);
    if ( v10 < 0 )
    {
      v11 = hMem;
    }
    else
    {
      v9 = (unsigned int *)hMem;
      v11 = 0;
      v10 = 0;
    }
    LocalFree(v11);
    if ( v10 < 0 )
      return 0;
    v2 = v9;
  }
  v12 = v2[1];
  if ( !v12 || (v13 = v12 - 1) == 0 )
  {
    v17 = 0;
    if ( !*((_WORD *)v2 + 8) )
      goto LABEL_29;
    v5 = *((unsigned __int16 *)v2 + 8) + 2;
LABEL_28:
    v17 = v5;
    goto LABEL_29;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    v18 = (void *)*((_QWORD *)v2 + 2);
    if ( v18 )
      v5 = RtlLengthSid(v18);
    if ( *((_WORD *)v2 + 12) )
      v5 += *((unsigned __int16 *)v2 + 12) + 2;
    if ( *((_WORD *)v2 + 20) )
      v5 += *((unsigned __int16 *)v2 + 20) + 2;
    goto LABEL_28;
  }
  v15 = v14 - 1;
  if ( !v15 )
  {
    v5 = v2[4];
    goto LABEL_28;
  }
  if ( v15 != 1 || (int)NetpSizeScannerInfoRecord(v2, &v24) < 0 )
    return 0;
  v16 = (void *)*((_QWORD *)v2 + 2);
  v17 = 0;
  if ( v16 )
    v17 = RtlLengthSid(v16);
  if ( *((_WORD *)v2 + 12) )
    v17 += *((unsigned __int16 *)v2 + 12) + 2;
  v5 = (unsigned int)v24;
  if ( *((_WORD *)v2 + 20) )
    v17 += *((unsigned __int16 *)v2 + 20) + 2;
LABEL_29:
  if ( v5 + 8 < v5 )
    return 0;
  if ( v17 + 8 < v17 )
    return 0;
  v19 = (v17 + 7) & 0xFFFFFFF8;
  if ( v19 >= 0xFFFFFFA8 )
    return 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19 + 88);
  v21 = Heap;
  if ( !Heap )
    return 0;
  memset_0(Heap, 0, v19 + 88);
  v21[5] = v19;
  v21[4] = (v5 + 7) & 0xFFFFFFF8;
  v24 = (char *)(v21 + 22);
  NetpMarshalFtinfoEntry2(v2, v21 + 8, &v24);
  v22 = *(_QWORD *)a1;
  if ( *(_DWORD **)(*(_QWORD *)a1 + 8LL) != a1 )
    __fastfail(3u);
  *(_QWORD *)v21 = v22;
  *((_QWORD *)v21 + 1) = a1;
  *(_QWORD *)(v22 + 8) = v21;
  result = (char *)(v21 + 8);
  *(_QWORD *)a1 = v21;
  a1[4] += v21[4];
  a1[5] += v21[5];
  ++a1[6];
  return result;
}

```

## disassembly

```asm
0x180037768  mov     r11, rsp
0x18003776b  mov     [r11+8], rbx
0x18003776f  mov     [r11+20h], rbp
0x180037773  push    rsi
0x180037774  push    rdi
0x180037775  push    r12
0x180037777  push    r14
0x180037779  push    r15
0x18003777b  sub     rsp, 30h
0x18003777f  xor     r12d, r12d
0x180037782  mov     rbx, rdx
0x180037785  cmp     dword ptr [rdx+4], 3
0x180037789  mov     r14, rcx
0x18003778c  mov     edi, r12d
0x18003778f  mov     [r11+10h], r12d
0x180037793  jnz     short loc_1800377E0
0x180037795  mov     r9d, [rbx+10h]
0x180037799  lea     rax, [r11+18h]
0x18003779d  mov     r8, [rbx+18h]
0x1800377a1  add     rdx, 8
0x1800377a5  mov     ecx, [rbx]
0x1800377a7  mov     esi, r12d
0x1800377aa  mov     [r11-38h], rax
0x1800377ae  mov     [r11+18h], r12
0x1800377b2  call    NetpBuildRecordFromBinary
0x1800377b7  mov     ebx, eax
0x1800377b9  test    eax, eax
0x1800377bb  js      short loc_1800377CA
0x1800377bd  mov     rsi, [rsp+58h+hMem]
0x1800377c2  mov     ecx, r12d
0x1800377c5  mov     ebx, r12d
0x1800377c8  jmp     short loc_1800377CF
0x1800377ca  mov     rcx, [rsp+58h+hMem]; hMem
0x1800377cf  call    cs:__imp_LocalFree
0x1800377d5  test    ebx, ebx
0x1800377d7  js      loc_180037955
0x1800377dd  mov     rbx, rsi
0x1800377e0  mov     ecx, [rbx+4]
0x1800377e3  test    ecx, ecx
0x1800377e5  jz      loc_18003788E
0x1800377eb  sub     ecx, 1
0x1800377ee  jz      loc_18003788E
0x1800377f4  sub     ecx, 1
0x1800377f7  jz      short loc_18003785B
0x1800377f9  sub     ecx, 1
0x1800377fc  jz      short loc_180037856
0x1800377fe  cmp     ecx, 1
0x180037801  jnz     loc_180037955
0x180037807  lea     rdx, [rsp+58h+arg_8]
0x18003780c  mov     rcx, rbx
0x18003780f  call    NetpSizeScannerInfoRecord
0x180037814  test    eax, eax
0x180037816  js      loc_180037955
0x18003781c  mov     rcx, [rbx+10h]; Sid
0x180037820  mov     edx, r12d
0x180037823  test    rcx, rcx
0x180037826  jz      short loc_180037830
0x180037828  call    cs:__imp_RtlLengthSid
0x18003782e  mov     edx, eax
0x180037830  cmp     [rbx+18h], r12w
0x180037835  jz      short loc_180037840
0x180037837  movzx   ecx, word ptr [rbx+18h]
0x18003783b  add     edx, 2
0x18003783e  add     edx, ecx
0x180037840  mov     edi, dword ptr [rsp+58h+arg_8]
0x180037844  cmp     [rbx+28h], r12w
0x180037849  jz      short loc_1800378A1
0x18003784b  movzx   eax, word ptr [rbx+28h]
0x18003784f  add     edx, 2
0x180037852  add     edx, eax
0x180037854  jmp     short loc_1800378A1
0x180037856  mov     edi, [rbx+10h]
0x180037859  jmp     short loc_18003789F
0x18003785b  mov     rcx, [rbx+10h]; Sid
0x18003785f  test    rcx, rcx
0x180037862  jz      short loc_18003786C
0x180037864  call    cs:__imp_RtlLengthSid
0x18003786a  mov     edi, eax
0x18003786c  cmp     [rbx+18h], r12w
0x180037871  jz      short loc_18003787C
0x180037873  movzx   ecx, word ptr [rbx+18h]
0x180037877  add     edi, 2
0x18003787a  add     edi, ecx
0x18003787c  cmp     [rbx+28h], r12w
0x180037881  jz      short loc_18003789F
0x180037883  movzx   eax, word ptr [rbx+28h]
0x180037887  add     edi, 2
0x18003788a  add     edi, eax
0x18003788c  jmp     short loc_18003789F
0x18003788e  mov     edx, r12d
0x180037891  cmp     [rbx+10h], r12w
0x180037896  jz      short loc_1800378A1
0x180037898  movzx   edi, word ptr [rbx+10h]
0x18003789c  add     edi, 2
0x18003789f  mov     edx, edi
0x1800378a1  lea     eax, [rdi+8]
0x1800378a4  cmp     eax, edi
0x1800378a6  jbe     loc_180037955
0x1800378ac  lea     eax, [rdx+8]
0x1800378af  cmp     eax, edx
0x1800378b1  jbe     loc_180037955
0x1800378b7  lea     ebp, [rdx+7]
0x1800378ba  and     ebp, 0FFFFFFF8h
0x1800378bd  lea     eax, [rbp+58h]
0x1800378c0  cmp     eax, 58h ; 'X'
0x1800378c3  jb      loc_180037955
0x1800378c9  mov     rcx, gs:60h
0x1800378d2  xor     edx, edx; Flags
0x1800378d4  mov     r8d, eax; Size
0x1800378d7  mov     r15d, eax
0x1800378da  mov     rcx, [rcx+30h]; HeapHandle
0x1800378de  call    cs:__imp_RtlAllocateHeap
0x1800378e4  mov     rsi, rax
0x1800378e7  test    rax, rax
0x1800378ea  jz      short loc_180037955
0x1800378ec  mov     r8d, r15d; Size
0x1800378ef  xor     edx, edx; Val
0x1800378f1  mov     rcx, rax; void *
0x1800378f4  call    memset_0
0x1800378f9  lea     edx, [rdi+7]
0x1800378fc  mov     [rsi+14h], ebp
0x1800378ff  and     edx, 0FFFFFFF8h
0x180037902  lea     rcx, [rsi+58h]
0x180037906  mov     [rsi+10h], edx
0x180037909  lea     r8, [rsp+58h+arg_8]
0x18003790e  mov     [rsp+58h+arg_8], rcx
0x180037913  lea     rdx, [rsi+20h]
0x180037917  mov     rcx, rbx
0x18003791a  call    NetpMarshalFtinfoEntry2
0x18003791f  mov     rax, [r14]
0x180037922  cmp     [rax+8], r14
0x180037926  jz      short loc_18003792F
0x180037928  mov     ecx, 3
0x18003792d  int     29h; Win8: RtlFailFast(ecx)
0x18003792f  mov     [rsi], rax
0x180037932  mov     [rsi+8], r14
0x180037936  mov     [rax+8], rsi
0x18003793a  lea     rax, [rsi+20h]
0x18003793e  mov     [r14], rsi
0x180037941  mov     ecx, [rsi+10h]
0x180037944  add     [r14+10h], ecx
0x180037948  mov     ecx, [rsi+14h]
0x18003794b  add     [r14+14h], ecx
0x18003794f  inc     dword ptr [r14+18h]
0x180037953  jmp     short loc_180037957
0x180037955  xor     eax, eax
0x180037957  mov     rbx, [rsp+58h+arg_0]
0x18003795c  mov     rbp, [rsp+58h+arg_18]
0x180037961  add     rsp, 30h
0x180037965  pop     r15
0x180037967  pop     r14
0x180037969  pop     r12
0x18003796b  pop     rdi
0x18003796c  pop     rsi
0x18003796d  retn
```
