# pwszAllocNtMultiplePath

- ea: `0x180039150`
- end: `0x1800394d4`
- name: `pwszAllocNtMultiplePath`
- size: `900`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x180038d10`
- `0x180038ef0`
- `0x180038fc0`

## callees

- `0x180039150`
- `0x1800394e0`
- `0x180039770`
- `0x180039f54`
- `0x18007ac50`
- `0x18007ba24`
- `0x1800a3514`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800393c9`
- `ntdll!RtlFreeHeap` at `0x180039457`
- `ntdll!RtlFreeHeap` at `0x1800393c9`
- `ntdll!RtlFreeHeap` at `0x180039457`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180039340`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180039340`
- `ntdll!RtlAllocateHeap` at `0x1800391f1`
- `ntdll!RtlAllocateHeap` at `0x1800391f1`

## pseudocode

```c
void *__fastcall pwszAllocNtMultiplePath(_WORD *a1, int *a2, _DWORD *a3, unsigned int *a4, int a5, __int64 a6, int a7)
{
  _WORD *v8; // r12
  unsigned int v9; // r14d
  int v10; // ebx
  __int16 v11; // cx
  _WORD *v12; // rdx
  bool v13; // zf
  unsigned int v14; // eax
  PVOID Heap; // rax
  void *v16; // r15
  int v17; // edi
  int v18; // r13d
  unsigned int i; // eax
  WCHAR *v20; // rcx
  WCHAR v21; // ax
  __int64 v22; // r13
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // ebx
  int v26; // ebx
  int v28; // eax
  int v29; // eax
  int v30; // [rsp+40h] [rbp-C0h]
  unsigned int v31; // [rsp+44h] [rbp-BCh]
  int v32; // [rsp+48h] [rbp-B8h]
  _DWORD v33[3]; // [rsp+4Ch] [rbp-B4h] BYREF
  _DWORD *v34; // [rsp+58h] [rbp-A8h]
  unsigned int *v35; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING NtPathName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  unsigned int v38; // [rsp+80h] [rbp-80h]
  WCHAR FileName[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR DosPathName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR Buffer[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v35 = a4;
  v34 = a3;
  v8 = a1;
  v37 = a6;
  v9 = 1;
  if ( a2 )
    v10 = *a2;
  else
    LOBYTE(v10) = 0;
  v11 = *a1;
  v33[0] = 0;
  if ( v11 )
  {
    v12 = v8;
    do
    {
      v13 = v11 == 124;
      v14 = v9 + 1;
      v11 = *++v12;
      if ( !v13 )
        v14 = v9;
      v9 = v14;
    }
    while ( v11 );
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 520 * v9);
  v16 = Heap;
  if ( Heap )
  {
    v17 = 0;
    v32 = 0;
    v18 = 1;
    *(_QWORD *)&v33[1] = Heap;
    v30 = 1;
    for ( i = 0; ; i = v31 + 1 )
    {
      v31 = i;
      if ( i >= v9 )
        break;
      memset_0(FileName, 0, 0x208u);
      memset_0(Buffer, 0, 0x208u);
      memset_0(DosPathName, 0, 0x208u);
      v20 = FileName;
      v18 = 0;
      while ( 1 )
      {
        v21 = *v8;
        if ( !*v8 || v21 == 124 )
          break;
        *v20++ = v21;
        if ( (__int64)(((char *)v20 - (char *)FileName) & 0xFFFFFFFFFFFFFFFEuLL) >= 520 )
          goto LABEL_34;
        ++v8;
      }
      *v20 = 0;
      if ( !bMakePathNameW(Buffer, FileName, 0, 0) || !(unsigned int)cGetTTFFromFOT(Buffer, (__int64)v33, v37, a7) )
        goto LABEL_34;
      NtPathName = 0;
      if ( a5 )
      {
        if ( (unsigned int)bFileIsOnTheHardDrive(DosPathName) )
          v17 |= 1u;
        else
          v17 |= 2u;
      }
      if ( RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) && NtPathName.Buffer )
      {
        v38 = NtPathName.Length >> 1;
        v22 = v38 + 1;
        if ( (unsigned int)v22 > 0x104 )
        {
          v18 = 0;
          v30 = 0;
        }
        else
        {
          v32 += v22;
          memcpy_0(*(void **)&v33[1], NtPathName.Buffer, NtPathName.Length);
          v23 = *(_QWORD *)&v33[1];
          *(_WORD *)(*(_QWORD *)&v33[1] + 2LL * v38) = v31 < v9 - 1 ? 0x7C : 0;
          v24 = v23 + 2 * v22;
          v18 = v30;
          *(_QWORD *)&v33[1] = v24;
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
      }
      else
      {
        v30 = 0;
      }
      if ( !v18 )
        goto LABEL_34;
      ++v8;
    }
    if ( !a5 )
      goto LABEL_32;
    v25 = (v10 & 3) - 1;
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        if ( v26 != 1 )
        {
          v28 = *a2;
          if ( (v17 & 2) != 0 )
            v29 = v28 | 2;
          else
            v29 = v28 | 1;
          *a2 = v29;
          goto LABEL_32;
        }
      }
      else if ( ((v17 & 2) != 0 ? v18 : 0) != 0 )
      {
LABEL_32:
        *v34 = v32;
        *v35 = v9;
        *a2 |= v33[0];
        return v16;
      }
    }
    else if ( (v17 & 2) == 0 )
    {
      goto LABEL_32;
    }
  }
LABEL_34:
  *v34 = 0;
  *v35 = 0;
  if ( v16 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
    return 0;
  }
  return v16;
}

```

## disassembly

```asm
0x180039150  mov     [rsp-8+arg_0], rbx
0x180039155  push    rbp
0x180039156  push    rsi
0x180039157  push    rdi
0x180039158  push    r12
0x18003915a  push    r13
0x18003915c  push    r14
0x18003915e  push    r15
0x180039160  lea     rbp, [rsp-5D0h]
0x180039168  sub     rsp, 6D0h
0x18003916f  mov     rax, cs:__security_cookie
0x180039176  xor     rax, rsp
0x180039179  mov     [rbp+600h+var_40], rax
0x180039180  mov     rax, [rbp+600h+arg_28]
0x180039187  xor     r13d, r13d
0x18003918a  mov     [rsp+700h+var_6A0], r9
0x18003918f  mov     rsi, rdx
0x180039192  mov     [rsp+700h+var_6A8], r8
0x180039197  mov     r12, rcx
0x18003919a  mov     [rsp+700h+var_688], rax
0x18003919f  mov     r14d, 1
0x1800391a5  test    rdx, rdx
0x1800391a8  jz      loc_18003949A
0x1800391ae  mov     ebx, [rdx]
0x1800391b0  movzx   ecx, word ptr [rcx]
0x1800391b3  mov     dword ptr [rsp+700h+var_6B4], r13d
0x1800391b8  test    cx, cx
0x1800391bb  jz      short loc_1800391DB
0x1800391bd  mov     rdx, r12
0x1800391c0  cmp     cx, 7Ch ; '|'
0x1800391c4  lea     eax, [r14+1]
0x1800391c8  lea     rdx, [rdx+2]
0x1800391cc  movzx   ecx, word ptr [rdx]
0x1800391cf  cmovnz  eax, r14d
0x1800391d3  mov     r14d, eax
0x1800391d6  test    cx, cx
0x1800391d9  jnz     short loc_1800391C0
0x1800391db  mov     rcx, gs:60h
0x1800391e4  xor     edx, edx; Flags
0x1800391e6  imul    r8d, r14d, 208h; Size
0x1800391ed  mov     rcx, [rcx+30h]; HeapHandle
0x1800391f1  call    cs:__imp_RtlAllocateHeap
0x1800391f7  mov     r15, rax
0x1800391fa  test    rax, rax
0x1800391fd  jz      loc_180039430
0x180039203  mov     edi, r13d
0x180039206  mov     [rsp+700h+var_6B8], r13d
0x18003920b  mov     r13d, 1
0x180039211  mov     qword ptr [rsp+700h+var_6B4+4], rax
0x180039216  xor     ecx, ecx
0x180039218  mov     [rsp+700h+var_6C0], r13d
0x18003921d  mov     eax, ecx
0x18003921f  mov     [rsp+700h+var_6BC], eax
0x180039223  cmp     eax, r14d
0x180039226  jnb     loc_1800393E5
0x18003922c  xor     edx, edx; Val
0x18003922e  lea     rcx, [rbp+600h+FileName]; void *
0x180039232  mov     r8d, 208h; Size
0x180039238  call    memset_0
0x18003923d  mov     r13d, 208h
0x180039243  lea     rcx, [rbp+600h+Buffer]; void *
0x18003924a  mov     r8d, r13d; Size
0x18003924d  xor     edx, edx; Val
0x18003924f  call    memset_0
0x180039254  mov     r8d, r13d; Size
0x180039257  lea     rcx, [rbp+600h+DosPathName]; void *
0x18003925e  xor     edx, edx; Val
0x180039260  call    memset_0
0x180039265  lea     rcx, [rbp+600h+FileName]
0x180039269  xor     r13d, r13d
0x18003926c  movzx   eax, word ptr [r12]
0x180039271  test    ax, ax
0x180039274  jz      short loc_1800392A3
0x180039276  cmp     ax, 7Ch ; '|'
0x18003927a  jz      short loc_1800392A3
0x18003927c  mov     [rcx], ax
0x18003927f  lea     rdx, [rbp+600h+FileName]
0x180039283  add     rcx, 2
0x180039287  mov     rax, rcx
0x18003928a  sub     rax, rdx
0x18003928d  and     rax, 0FFFFFFFFFFFFFFFEh
0x180039291  cmp     rax, 208h
0x180039297  jge     loc_180039430
0x18003929d  add     r12, 2
0x1800392a1  jmp     short loc_18003926C
0x1800392a3  mov     [rcx], r13w
0x1800392a7  lea     rdx, [rbp+600h+FileName]; lpFileName
0x1800392ab  lea     rcx, [rbp+600h+Buffer]; lpBuffer
0x1800392b2  xor     r9d, r9d
0x1800392b5  xor     r8d, r8d; lpFilePart
0x1800392b8  call    bMakePathNameW
0x1800392bd  test    eax, eax
0x1800392bf  jz      loc_180039430
0x1800392c5  mov     eax, [rbp+600h+arg_30]
0x1800392cb  lea     r8, [rbp+600h+DosPathName]
0x1800392d2  mov     [rsp+700h+var_6D0], eax; int
0x1800392d6  lea     rcx, [rbp+600h+Buffer]; SourceString
0x1800392dd  mov     rax, [rsp+700h+var_688]
0x1800392e2  xor     r9d, r9d
0x1800392e5  mov     [rsp+700h+var_6D8], rax; __int64
0x1800392ea  mov     edx, 104h
0x1800392ef  lea     rax, [rsp+700h+var_6B4]
0x1800392f4  mov     [rsp+700h+var_6E0], rax; __int64
0x1800392f9  call    cGetTTFFromFOT
0x1800392fe  test    eax, eax
0x180039300  jz      loc_180039430
0x180039306  xorps   xmm0, xmm0
0x180039309  movups  xmmword ptr [rsp+700h+NtPathName.Length], xmm0
0x18003930e  cmp     [rbp+600h+arg_20], r13d
0x180039315  jz      short loc_18003932E
0x180039317  lea     rcx, [rbp+600h+DosPathName]
0x18003931e  call    bFileIsOnTheHardDrive
0x180039323  test    eax, eax
0x180039325  jz      loc_1800394C7
0x18003932b  or      edi, 1
0x18003932e  xor     r9d, r9d; DirectoryInfo
0x180039331  lea     rdx, [rsp+700h+NtPathName]; NtPathName
0x180039336  xor     r8d, r8d; NtFileNamePart
0x180039339  lea     rcx, [rbp+600h+DosPathName]; DosPathName
0x180039340  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180039346  test    al, al
0x180039348  jz      loc_1800394A2
0x18003934e  mov     rdx, [rsp+700h+NtPathName.Buffer]; Src
0x180039353  test    rdx, rdx
0x180039356  jz      loc_1800394A2
0x18003935c  movzx   eax, [rsp+700h+NtPathName.Length]
0x180039361  shr     eax, 1
0x180039363  mov     [rbp+600h+var_680], eax
0x180039366  lea     r13d, [rax+1]
0x18003936a  cmp     r13d, 104h
0x180039371  ja      loc_18003948D
0x180039377  movzx   r8d, [rsp+700h+NtPathName.Length]; Size
0x18003937d  mov     rcx, qword ptr [rsp+700h+var_6B4+4]; void *
0x180039382  add     [rsp+700h+var_6B8], r13d
0x180039387  call    memcpy_0
0x18003938c  mov     rdx, qword ptr [rsp+700h+var_6B4+4]
0x180039391  lea     eax, [r14-1]
0x180039395  cmp     [rsp+700h+var_6BC], eax
0x180039399  mov     eax, [rbp+600h+var_680]
0x18003939c  sbb     cx, cx
0x18003939f  and     cx, 7Ch
0x1800393a3  mov     [rdx+rax*2], cx
0x1800393a7  lea     rdx, [rdx+r13*2]
0x1800393ab  mov     r13d, [rsp+700h+var_6C0]
0x1800393b0  mov     qword ptr [rsp+700h+var_6B4+4], rdx
0x1800393b5  mov     rcx, gs:60h
0x1800393be  xor     edx, edx; Flags
0x1800393c0  mov     r8, [rsp+700h+NtPathName.Buffer]; P
0x1800393c5  mov     rcx, [rcx+30h]; HeapHandle
0x1800393c9  call    cs:__imp_RtlFreeHeap
0x1800393cf  xor     ecx, ecx
0x1800393d1  test    r13d, r13d
0x1800393d4  jz      short loc_18003942D
0x1800393d6  mov     eax, [rsp+700h+var_6BC]
0x1800393da  add     r12, 2
0x1800393de  inc     eax
0x1800393e0  jmp     loc_18003921F
0x1800393e5  cmp     [rbp+600h+arg_20], ecx
0x1800393eb  jz      short loc_18003940C
0x1800393ed  and     ebx, 3
0x1800393f0  sub     ebx, 1
0x1800393f3  jz      short loc_180039427
0x1800393f5  sub     ebx, 1
0x1800393f8  jnz     loc_1800394AC
0x1800393fe  and     dil, 2
0x180039402  neg     dil
0x180039405  sbb     eax, eax
0x180039407  test    r13d, eax
0x18003940a  jz      short loc_18003942D
0x18003940c  mov     rax, [rsp+700h+var_6A8]
0x180039411  mov     ecx, [rsp+700h+var_6B8]
0x180039415  mov     [rax], ecx
0x180039417  mov     rax, [rsp+700h+var_6A0]
0x18003941c  mov     [rax], r14d
0x18003941f  mov     eax, dword ptr [rsp+700h+var_6B4]
0x180039423  or      [rsi], eax
0x180039425  jmp     short loc_180039460
0x180039427  test    dil, 2
0x18003942b  jz      short loc_18003940C
0x18003942d  xor     r13d, r13d
0x180039430  mov     rax, [rsp+700h+var_6A8]
0x180039435  mov     [rax], r13d
0x180039438  mov     rax, [rsp+700h+var_6A0]
0x18003943d  mov     [rax], r13d
0x180039440  test    r15, r15
0x180039443  jz      short loc_180039460
0x180039445  mov     rcx, gs:60h
0x18003944e  mov     r8, r15; P
0x180039451  xor     edx, edx; Flags
0x180039453  mov     rcx, [rcx+30h]; HeapHandle
0x180039457  call    cs:__imp_RtlFreeHeap
0x18003945d  mov     r15, r13
0x180039460  mov     rax, r15
0x180039463  mov     rcx, [rbp+600h+var_40]
0x18003946a  xor     rcx, rsp; StackCookie
0x18003946d  call    __security_check_cookie
0x180039472  mov     rbx, [rsp+700h+arg_0]
0x18003947a  add     rsp, 6D0h
0x180039481  pop     r15
0x180039483  pop     r14
0x180039485  pop     r13
0x180039487  pop     r12
0x180039489  pop     rdi
0x18003948a  pop     rsi
0x18003948b  pop     rbp
0x18003948c  retn
0x18003948d  xor     r13d, r13d
0x180039490  mov     [rsp+700h+var_6C0], r13d
0x180039495  jmp     loc_1800393B5
0x18003949a  mov     ebx, r13d
0x18003949d  jmp     loc_1800391B0
0x1800394a2  mov     [rsp+700h+var_6C0], r13d
0x1800394a7  jmp     loc_1800393CF
0x1800394ac  cmp     ebx, 1
0x1800394af  jz      loc_18003942D
0x1800394b5  mov     eax, [rsi]
0x1800394b7  test    dil, 2
0x1800394bb  jnz     short loc_1800394CF
0x1800394bd  or      eax, 1
0x1800394c0  mov     [rsi], eax
0x1800394c2  jmp     loc_18003940C
0x1800394c7  or      edi, 2
0x1800394ca  jmp     loc_18003932E
0x1800394cf  or      eax, 2
0x1800394d2  jmp     short loc_1800394C0
```
