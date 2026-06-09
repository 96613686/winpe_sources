# BiCreateBootEntry

- ea: `0x180035f38`
- end: `0x18003635e`
- name: `BiCreateBootEntry`
- size: `1062`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180036364`

## callees

- `0x1800033d4`
- `0x180003bb5`
- `0x18002d588`
- `0x1800330d0`
- `0x180034254`
- `0x180035f38`
- `0x180037e68`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003628f`
- `ntdll!RtlFreeHeap` at `0x1800362b2`
- `ntdll!RtlFreeHeap` at `0x1800362d5`
- `ntdll!RtlFreeHeap` at `0x1800362f8`
- `ntdll!RtlFreeHeap` at `0x18003631b`
- `ntdll!RtlFreeHeap` at `0x18003633e`
- `ntdll!RtlFreeHeap` at `0x18003628f`
- `ntdll!RtlFreeHeap` at `0x1800362b2`
- `ntdll!RtlFreeHeap` at `0x1800362d5`
- `ntdll!RtlFreeHeap` at `0x1800362f8`
- `ntdll!RtlFreeHeap` at `0x18003631b`
- `ntdll!RtlFreeHeap` at `0x18003633e`
- `ntdll!RtlAllocateHeap` at `0x18003609a`
- `ntdll!RtlAllocateHeap` at `0x180036190`
- `ntdll!RtlAllocateHeap` at `0x18003609a`
- `ntdll!RtlAllocateHeap` at `0x180036190`

## string_xrefs

- `0x180035fd2`: `BiCreateBootEntry: Could not retrieve BCD Object application device. Status: %x`
- `0x180035f9f`: `BiCreateBootEntry: Could not retrieve BCD Object application description. Status: %x`
- `0x18003600a`: `BiCreateBootEntry: Could not retrieve BCD Object application path. Status: %x`

## pseudocode

```c
__int64 __fastcall BiCreateBootEntry(__int64 a1, _QWORD *a2)
{
  _DWORD *v2; // rdi
  void *v3; // rsi
  unsigned int *v4; // r14
  void *v5; // r13
  char *v6; // r15
  int Element; // eax
  int v9; // ebx
  int v10; // eax
  int v11; // eax
  __int64 v12; // r12
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  char *Heap; // rax
  __int64 v20; // rbx
  size_t v21; // r8
  int KeyName; // eax
  int v23; // r8d
  unsigned int v24; // ecx
  PVOID ProcessHeap; // rcx
  _DWORD *v26; // rax
  _DWORD *v27; // rbx
  int v28; // ecx
  size_t v29; // r8
  PVOID v30; // rdx
  int v31; // eax
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  size_t v36; // [rsp+30h] [rbp-38h] BYREF
  void *v37; // [rsp+38h] [rbp-30h] BYREF
  void *Src; // [rsp+40h] [rbp-28h] BYREF
  _DWORD *v39; // [rsp+48h] [rbp-20h] BYREF
  void *v40; // [rsp+50h] [rbp-18h] BYREF
  PVOID P[2]; // [rsp+58h] [rbp-10h] BYREF
  size_t v44; // [rsp+C0h] [rbp+58h] BYREF
  size_t Size; // [rsp+C8h] [rbp+60h] BYREF

  LODWORD(v44) = 0;
  LODWORD(Size) = 0;
  LODWORD(v36) = 0;
  v2 = 0;
  P[0] = 0;
  v3 = 0;
  v39 = 0;
  v4 = 0;
  Src = 0;
  v5 = 0;
  v37 = 0;
  v6 = 0;
  v40 = 0;
  Element = BiGetElement(a1, 301989892, P, &v44);
  v9 = Element;
  if ( Element < 0 )
  {
    BiLogMessage(
      4,
      L"BiCreateBootEntry: Could not retrieve BCD Object application description. Status: %x",
      (unsigned int)Element);
    goto LABEL_25;
  }
  v10 = BiGetElement(a1, 285212673, &v39, &Size);
  v9 = v10;
  if ( v10 < 0 )
  {
    BiLogMessage(
      4,
      L"BiCreateBootEntry: Could not retrieve BCD Object application device. Status: %x",
      (unsigned int)v10);
    v2 = v39;
    goto LABEL_25;
  }
  v11 = BiGetElement(a1, 301989890, &Src, &v36);
  v9 = v11;
  if ( v11 < 0 )
  {
    BiLogMessage(4, L"BiCreateBootEntry: Could not retrieve BCD Object application path. Status: %x", (unsigned int)v11);
    v2 = v39;
    v3 = Src;
    goto LABEL_25;
  }
  v2 = v39;
  v3 = Src;
  if ( *v39 != 2 )
  {
    v9 = -1073741637;
    goto LABEL_25;
  }
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)Src + v13) );
  v14 = 2 * v13 + 2;
  v15 = -1;
  LODWORD(v36) = v14;
  do
    ++v15;
  while ( *((_WORD *)v39 + v15 + 10) );
  v16 = 2 * v15 + 2;
  v17 = v16 + v14;
  LODWORD(Size) = v16;
  if ( v16 + v14 < v16 )
    goto LABEL_24;
  v18 = v17 + 12;
  if ( v17 + 12 < v17 )
    goto LABEL_24;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
  v6 = Heap;
  if ( !Heap )
  {
LABEL_16:
    v9 = -1073741670;
    goto LABEL_25;
  }
  *((_DWORD *)Heap + 1) = v18;
  v20 = (unsigned int)Size;
  v21 = (unsigned int)Size;
  *(_DWORD *)Heap = 1;
  *((_DWORD *)Heap + 2) = 3;
  memcpy_0(Heap + 12, v2 + 5, v21);
  memcpy_0(&v6[v20 + 12], v3, (unsigned int)v36);
  v9 = BiTranslateFilePath(v6, 4, &v37);
  if ( v9 < 0 || (KeyName = BiGetKeyName(a1, &v40), v5 = v40, v9 = KeyName, KeyName < 0) )
  {
    v4 = (unsigned int *)v37;
    goto LABEL_25;
  }
  do
    ++v12;
  while ( *((_WORD *)v40 + v12) );
  v4 = (unsigned int *)v37;
  LODWORD(v39) = (2 * v12 + 45) & 0xFFFFFFFC;
  LODWORD(v36) = (_DWORD)v39 + 16;
  v23 = *((_DWORD *)v37 + 1);
  v24 = ((_DWORD)v39 + 47) & 0xFFFFFFFC;
  LODWORD(Src) = v24;
  if ( (unsigned int)v44 + v24 + v23 + 4 < (unsigned int)v44 )
  {
LABEL_24:
    v9 = -1073741675;
  }
  else
  {
    LODWORD(Size) = (v24 + v44 + 3) & 0xFFFFFFFC;
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    LODWORD(v37) = v23 + Size;
    v26 = RtlAllocateHeap(ProcessHeap, 0, (unsigned int)(v23 + Size));
    v27 = v26;
    if ( !v26 )
      goto LABEL_16;
    v28 = Size;
    v29 = (unsigned int)v44;
    v30 = P[0];
    *v26 = 1;
    v31 = (int)v37;
    v27[5] = v28;
    v32 = v36;
    v27[1] = v31;
    v33 = (unsigned int)Src;
    v27[6] = v32;
    v27[2] = -1;
    v27[3] = 5;
    v27[4] = v33;
    memcpy_0((char *)v27 + v33, v30, v29);
    memcpy_0((char *)v27 + (unsigned int)Size, v4, v4[1]);
    *(_QWORD *)(v27 + 7) = 0x53574F444E4957LL;
    v27[10] = v36;
    v27[11] = (_DWORD)v39;
    v27[9] = 1;
    swprintf_s((wchar_t *const)v27 + 24, (unsigned int)v12 + 11LL, L"%s%s", L"BCDOBJECT=", v5);
    v34 = (unsigned int)v27[11];
    *(_DWORD *)((char *)v27 + v34 + 28) = 1;
    *(_DWORD *)((char *)v27 + v34 + 32) = 16;
    *(_DWORD *)((char *)v27 + v34 + 36) = 4;
    *(_DWORD *)((char *)v27 + v34 + 40) = 327551;
    *a2 = v27;
    v9 = 0;
  }
LABEL_25:
  if ( P[0] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( v6 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180035f38  mov     [rsp-40h+arg_8], rdx
0x180035f3d  mov     [rsp-40h+arg_0], rcx
0x180035f42  push    rbp
0x180035f43  push    rbx
0x180035f44  push    rsi
0x180035f45  push    rdi
0x180035f46  push    r12
0x180035f48  push    r13
0x180035f4a  push    r14
0x180035f4c  push    r15
0x180035f4e  mov     rbp, rsp
0x180035f51  sub     rsp, 68h
0x180035f55  xor     eax, eax
0x180035f57  lea     r9, [rbp+arg_10]
0x180035f5b  lea     r8, [rbp+P]
0x180035f5f  mov     dword ptr [rbp+arg_10], eax
0x180035f62  mov     edx, 12000004h
0x180035f67  mov     dword ptr [rbp+Size], eax
0x180035f6a  mov     dword ptr [rbp+var_38], eax
0x180035f6d  mov     edi, eax
0x180035f6f  mov     [rbp+P], rax
0x180035f73  mov     esi, eax
0x180035f75  mov     [rbp+var_20], rax
0x180035f79  mov     r14d, eax
0x180035f7c  mov     [rbp+Src], rax
0x180035f80  mov     r13d, eax
0x180035f83  mov     [rbp+var_30], rax
0x180035f87  mov     r15d, eax
0x180035f8a  mov     [rbp+var_18], rax
0x180035f8e  mov     r12, rcx
0x180035f91  call    BiGetElement
0x180035f96  mov     ebx, eax
0x180035f98  test    eax, eax
0x180035f9a  jns     short loc_180035FB4
0x180035f9c  mov     r8d, eax
0x180035f9f  lea     rdx, aBicreatebooten_0; "BiCreateBootEntry: Could not retrieve B"...
0x180035fa6  lea     ecx, [r15+4]
0x180035faa  call    BiLogMessage
0x180035faf  jmp     loc_180036274
0x180035fb4  lea     r9, [rbp+Size]
0x180035fb8  mov     edx, 11000001h
0x180035fbd  lea     r8, [rbp+var_20]
0x180035fc1  mov     rcx, r12
0x180035fc4  call    BiGetElement
0x180035fc9  mov     ebx, eax
0x180035fcb  test    eax, eax
0x180035fcd  jns     short loc_180035FEC
0x180035fcf  mov     r8d, eax
0x180035fd2  lea     rdx, aBicreatebooten_1; "BiCreateBootEntry: Could not retrieve B"...
0x180035fd9  mov     ecx, 4
0x180035fde  call    BiLogMessage
0x180035fe3  mov     rdi, [rbp+var_20]
0x180035fe7  jmp     loc_180036274
0x180035fec  lea     r9, [rbp+var_38]
0x180035ff0  mov     edx, 12000002h
0x180035ff5  lea     r8, [rbp+Src]
0x180035ff9  mov     rcx, r12
0x180035ffc  call    BiGetElement
0x180036001  mov     ebx, eax
0x180036003  test    eax, eax
0x180036005  jns     short loc_180036028
0x180036007  mov     r8d, eax
0x18003600a  lea     rdx, aBicreatebooten; "BiCreateBootEntry: Could not retrieve B"...
0x180036011  mov     ecx, 4
0x180036016  call    BiLogMessage
0x18003601b  mov     rdi, [rbp+var_20]
0x18003601f  mov     rsi, [rbp+Src]
0x180036023  jmp     loc_180036274
0x180036028  mov     rdi, [rbp+var_20]
0x18003602c  mov     rsi, [rbp+Src]
0x180036030  cmp     dword ptr [rdi], 2
0x180036033  jz      short loc_18003603F
0x180036035  mov     ebx, 0C00000BBh
0x18003603a  jmp     loc_180036274
0x18003603f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180036043  mov     rax, r12
0x180036046  xor     ebx, ebx
0x180036048  inc     rax
0x18003604b  cmp     [rsi+rax*2], bx
0x18003604f  jnz     short loc_180036048
0x180036051  lea     edx, ds:2[rax*2]
0x180036058  mov     rax, r12
0x18003605b  mov     dword ptr [rbp+var_38], edx
0x18003605e  inc     rax
0x180036061  cmp     [rdi+rax*2+14h], bx
0x180036066  jnz     short loc_18003605E
0x180036068  lea     ecx, ds:2[rax*2]
0x18003606f  lea     eax, [rcx+rdx]
0x180036072  mov     dword ptr [rbp+Size], ecx
0x180036075  cmp     eax, ecx
0x180036077  jb      loc_18003626F
0x18003607d  lea     ebx, [rax+0Ch]
0x180036080  cmp     ebx, eax
0x180036082  jb      loc_18003626F
0x180036088  mov     rcx, gs:60h
0x180036091  xor     edx, edx; Flags
0x180036093  mov     r8d, ebx; Size
0x180036096  mov     rcx, [rcx+30h]; HeapHandle
0x18003609a  call    cs:__imp_RtlAllocateHeap
0x1800360a1  nop     dword ptr [rax+rax+00h]
0x1800360a6  mov     r15, rax
0x1800360a9  test    rax, rax
0x1800360ac  jnz     short loc_1800360B8
0x1800360ae  mov     ebx, 0C000009Ah
0x1800360b3  jmp     loc_180036274
0x1800360b8  mov     [rax+4], ebx
0x1800360bb  lea     rcx, [rax+0Ch]; void *
0x1800360bf  mov     ebx, dword ptr [rbp+Size]
0x1800360c2  lea     rdx, [rdi+14h]; Src
0x1800360c6  mov     r8d, ebx; Size
0x1800360c9  mov     dword ptr [rax], 1
0x1800360cf  mov     dword ptr [rax+8], 3
0x1800360d6  call    memcpy_0
0x1800360db  mov     r8d, dword ptr [rbp+var_38]; Size
0x1800360df  lea     rcx, [rbx+0Ch]
0x1800360e3  add     rcx, r15; void *
0x1800360e6  mov     rdx, rsi; Src
0x1800360e9  call    memcpy_0
0x1800360ee  lea     r8, [rbp+var_30]
0x1800360f2  mov     edx, 4
0x1800360f7  mov     rcx, r15
0x1800360fa  call    BiTranslateFilePath
0x1800360ff  mov     ebx, eax
0x180036101  test    eax, eax
0x180036103  js      loc_180036269
0x180036109  mov     rcx, [rbp+arg_0]
0x18003610d  lea     rdx, [rbp+var_18]
0x180036111  call    BiGetKeyName
0x180036116  mov     r13, [rbp+var_18]
0x18003611a  mov     ebx, eax
0x18003611c  test    eax, eax
0x18003611e  js      loc_180036269
0x180036124  inc     r12
0x180036127  cmp     [r13+r12*2+0], r14w
0x18003612d  jnz     short loc_180036124
0x18003612f  mov     edx, dword ptr [rbp+arg_10]
0x180036132  lea     eax, ds:2Dh[r12*2]
0x18003613a  mov     r14, [rbp+var_30]
0x18003613e  mov     r9d, 0FFFFFFFCh
0x180036144  and     eax, r9d
0x180036147  mov     dword ptr [rbp+var_20], eax
0x18003614a  add     eax, 10h
0x18003614d  mov     dword ptr [rbp+var_38], eax
0x180036150  mov     r8d, [r14+4]
0x180036154  lea     ecx, [rax+1Fh]
0x180036157  and     ecx, r9d
0x18003615a  lea     eax, [r8+4]
0x18003615e  mov     dword ptr [rbp+Src], ecx
0x180036161  add     eax, ecx
0x180036163  add     eax, edx
0x180036165  cmp     eax, edx
0x180036167  jb      loc_18003626F
0x18003616d  lea     eax, [rdx+3]
0x180036170  xor     edx, edx; Flags
0x180036172  add     eax, ecx
0x180036174  mov     rcx, gs:60h
0x18003617d  and     eax, r9d
0x180036180  mov     dword ptr [rbp+Size], eax
0x180036183  add     eax, r8d
0x180036186  mov     r8d, eax; Size
0x180036189  mov     rcx, [rcx+30h]; HeapHandle
0x18003618d  mov     dword ptr [rbp+var_30], eax
0x180036190  call    cs:__imp_RtlAllocateHeap
0x180036197  nop     dword ptr [rax+rax+00h]
0x18003619c  mov     rbx, rax
0x18003619f  test    rax, rax
0x1800361a2  jz      loc_1800360AE
0x1800361a8  mov     ecx, dword ptr [rbp+Size]
0x1800361ab  mov     r8d, dword ptr [rbp+arg_10]; Size
0x1800361af  mov     rdx, [rbp+P]; Src
0x1800361b3  mov     dword ptr [rax], 1
0x1800361b9  mov     eax, dword ptr [rbp+var_30]
0x1800361bc  mov     [rbx+14h], ecx
0x1800361bf  mov     ecx, dword ptr [rbp+var_38]
0x1800361c2  mov     [rbx+4], eax
0x1800361c5  mov     eax, dword ptr [rbp+Src]
0x1800361c8  mov     [rbx+18h], ecx
0x1800361cb  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x1800361d2  mov     dword ptr [rbx+0Ch], 5
0x1800361d9  lea     rcx, [rbx+rax]; void *
0x1800361dd  mov     [rbx+10h], eax
0x1800361e0  call    memcpy_0
0x1800361e5  mov     ecx, dword ptr [rbp+Size]
0x1800361e8  mov     rdx, r14; Src
0x1800361eb  mov     r8d, [r14+4]; Size
0x1800361ef  add     rcx, rbx; void *
0x1800361f2  call    memcpy_0
0x1800361f7  mov     rax, 53574F444E4957h
0x180036201  mov     edx, r12d
0x180036204  mov     [rbx+1Ch], rax
0x180036208  lea     rcx, [rbx+30h]; Buffer
0x18003620c  mov     eax, dword ptr [rbp+var_38]
0x18003620f  lea     r9, aBcdobject; "BCDOBJECT="
0x180036216  mov     [rbx+28h], eax
0x180036219  lea     r8, aSS_0; "%s%s"
0x180036220  mov     eax, dword ptr [rbp+var_20]
0x180036223  add     rdx, 0Bh; BufferCount
0x180036227  mov     [rbx+2Ch], eax
0x18003622a  mov     dword ptr [rbx+24h], 1
0x180036231  mov     [rsp+68h+var_48], r13
0x180036236  call    swprintf_s
0x18003623b  mov     eax, [rbx+2Ch]
0x18003623e  mov     dword ptr [rax+rbx+1Ch], 1
0x180036246  mov     dword ptr [rax+rbx+20h], 10h
0x18003624e  mov     dword ptr [rax+rbx+24h], 4
0x180036256  mov     dword ptr [rax+rbx+28h], 4FF7Fh
0x18003625e  mov     rax, [rbp+arg_8]
0x180036262  mov     [rax], rbx
0x180036265  xor     ebx, ebx
0x180036267  jmp     short loc_180036274
0x180036269  mov     r14, [rbp+var_30]
0x18003626d  jmp     short loc_180036274
0x18003626f  mov     ebx, 0C0000095h
0x180036274  mov     rax, [rbp+P]
0x180036278  test    rax, rax
0x18003627b  jz      short loc_18003629B
0x18003627d  mov     rcx, gs:60h
0x180036286  mov     r8, rax; P
0x180036289  xor     edx, edx; Flags
0x18003628b  mov     rcx, [rcx+30h]; HeapHandle
0x18003628f  call    cs:__imp_RtlFreeHeap
0x180036296  nop     dword ptr [rax+rax+00h]
0x18003629b  test    rdi, rdi
0x18003629e  jz      short loc_1800362BE
0x1800362a0  mov     rcx, gs:60h
0x1800362a9  mov     r8, rdi; P
0x1800362ac  xor     edx, edx; Flags
0x1800362ae  mov     rcx, [rcx+30h]; HeapHandle
0x1800362b2  call    cs:__imp_RtlFreeHeap
0x1800362b9  nop     dword ptr [rax+rax+00h]
0x1800362be  test    rsi, rsi
0x1800362c1  jz      short loc_1800362E1
0x1800362c3  mov     rcx, gs:60h
0x1800362cc  mov     r8, rsi; P
0x1800362cf  xor     edx, edx; Flags
0x1800362d1  mov     rcx, [rcx+30h]; HeapHandle
0x1800362d5  call    cs:__imp_RtlFreeHeap
0x1800362dc  nop     dword ptr [rax+rax+00h]
0x1800362e1  test    r14, r14
0x1800362e4  jz      short loc_180036304
0x1800362e6  mov     rcx, gs:60h
0x1800362ef  mov     r8, r14; P
0x1800362f2  xor     edx, edx; Flags
0x1800362f4  mov     rcx, [rcx+30h]; HeapHandle
0x1800362f8  call    cs:__imp_RtlFreeHeap
0x1800362ff  nop     dword ptr [rax+rax+00h]
0x180036304  test    r13, r13
0x180036307  jz      short loc_180036327
0x180036309  mov     rcx, gs:60h
0x180036312  mov     r8, r13; P
0x180036315  xor     edx, edx; Flags
0x180036317  mov     rcx, [rcx+30h]; HeapHandle
0x18003631b  call    cs:__imp_RtlFreeHeap
0x180036322  nop     dword ptr [rax+rax+00h]
0x180036327  test    r15, r15
0x18003632a  jz      short loc_18003634A
0x18003632c  mov     rcx, gs:60h
0x180036335  mov     r8, r15; P
0x180036338  xor     edx, edx; Flags
0x18003633a  mov     rcx, [rcx+30h]; HeapHandle
0x18003633e  call    cs:__imp_RtlFreeHeap
0x180036345  nop     dword ptr [rax+rax+00h]
0x18003634a  mov     eax, ebx
0x18003634c  add     rsp, 68h
0x180036350  pop     r15
0x180036352  pop     r14
0x180036354  pop     r13
0x180036356  pop     r12
0x180036358  pop     rdi
0x180036359  pop     rsi
0x18003635a  pop     rbx
0x18003635b  pop     rbp
0x18003635c  retn
```
