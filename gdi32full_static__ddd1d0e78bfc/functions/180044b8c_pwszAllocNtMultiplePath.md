# pwszAllocNtMultiplePath

- ea: `0x180044b8c`
- end: `0x180044f29`
- name: `pwszAllocNtMultiplePath`
- size: `925`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x180044700`
- `0x180044900`
- `0x1800449e0`

## callees

- `0x180044b8c`
- `0x180044f30`
- `0x1800451f0`
- `0x180045a00`
- `0x18007f800`
- `0x180080604`
- `0x1800a68d4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180044e11`
- `ntdll!RtlFreeHeap` at `0x180044ea5`
- `ntdll!RtlFreeHeap` at `0x180044e11`
- `ntdll!RtlFreeHeap` at `0x180044ea5`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180044d82`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180044d82`
- `ntdll!RtlAllocateHeap` at `0x180044c2d`
- `ntdll!RtlAllocateHeap` at `0x180044c2d`

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
0x180044b8c  mov     [rsp-8+arg_0], rbx
0x180044b91  push    rbp
0x180044b92  push    rsi
0x180044b93  push    rdi
0x180044b94  push    r12
0x180044b96  push    r13
0x180044b98  push    r14
0x180044b9a  push    r15
0x180044b9c  lea     rbp, [rsp-5D0h]
0x180044ba4  sub     rsp, 6D0h
0x180044bab  mov     rax, cs:__security_cookie
0x180044bb2  xor     rax, rsp
0x180044bb5  mov     [rbp+600h+var_40], rax
0x180044bbc  mov     rax, [rbp+600h+arg_28]
0x180044bc3  xor     r13d, r13d
0x180044bc6  mov     [rsp+700h+var_6A0], r9
0x180044bcb  mov     rsi, rdx
0x180044bce  mov     [rsp+700h+var_6A8], r8
0x180044bd3  mov     r12, rcx
0x180044bd6  mov     [rsp+700h+var_688], rax
0x180044bdb  mov     r14d, 1
0x180044be1  test    rdx, rdx
0x180044be4  jz      loc_180044EEF
0x180044bea  mov     ebx, [rdx]
0x180044bec  movzx   ecx, word ptr [rcx]
0x180044bef  mov     dword ptr [rsp+700h+var_6B4], r13d
0x180044bf4  test    cx, cx
0x180044bf7  jz      short loc_180044C17
0x180044bf9  mov     rdx, r12
0x180044bfc  cmp     cx, 7Ch ; '|'
0x180044c00  lea     eax, [r14+1]
0x180044c04  lea     rdx, [rdx+2]
0x180044c08  movzx   ecx, word ptr [rdx]
0x180044c0b  cmovnz  eax, r14d
0x180044c0f  mov     r14d, eax
0x180044c12  test    cx, cx
0x180044c15  jnz     short loc_180044BFC
0x180044c17  mov     rcx, gs:60h
0x180044c20  xor     edx, edx; Flags
0x180044c22  imul    r8d, r14d, 208h; Size
0x180044c29  mov     rcx, [rcx+30h]; HeapHandle
0x180044c2d  call    cs:__imp_RtlAllocateHeap
0x180044c34  nop     dword ptr [rax+rax+00h]
0x180044c39  mov     r15, rax
0x180044c3c  test    rax, rax
0x180044c3f  jz      loc_180044E7E
0x180044c45  mov     edi, r13d
0x180044c48  mov     [rsp+700h+var_6B8], r13d
0x180044c4d  mov     r13d, 1
0x180044c53  mov     qword ptr [rsp+700h+var_6B4+4], rax
0x180044c58  xor     ecx, ecx
0x180044c5a  mov     [rsp+700h+var_6C0], r13d
0x180044c5f  mov     eax, ecx
0x180044c61  mov     [rsp+700h+var_6BC], eax
0x180044c65  cmp     eax, r14d
0x180044c68  jnb     loc_180044E33
0x180044c6e  xor     edx, edx; Val
0x180044c70  lea     rcx, [rbp+600h+FileName]; void *
0x180044c74  mov     r8d, 208h; Size
0x180044c7a  call    memset_0
0x180044c7f  mov     r13d, 208h
0x180044c85  lea     rcx, [rbp+600h+Buffer]; void *
0x180044c8c  mov     r8d, r13d; Size
0x180044c8f  xor     edx, edx; Val
0x180044c91  call    memset_0
0x180044c96  mov     r8d, r13d; Size
0x180044c99  lea     rcx, [rbp+600h+DosPathName]; void *
0x180044ca0  xor     edx, edx; Val
0x180044ca2  call    memset_0
0x180044ca7  lea     rcx, [rbp+600h+FileName]
0x180044cab  xor     r13d, r13d
0x180044cae  movzx   eax, word ptr [r12]
0x180044cb3  test    ax, ax
0x180044cb6  jz      short loc_180044CE5
0x180044cb8  cmp     ax, 7Ch ; '|'
0x180044cbc  jz      short loc_180044CE5
0x180044cbe  mov     [rcx], ax
0x180044cc1  lea     rdx, [rbp+600h+FileName]
0x180044cc5  add     rcx, 2
0x180044cc9  mov     rax, rcx
0x180044ccc  sub     rax, rdx
0x180044ccf  and     rax, 0FFFFFFFFFFFFFFFEh
0x180044cd3  cmp     rax, 208h
0x180044cd9  jge     loc_180044E7E
0x180044cdf  add     r12, 2
0x180044ce3  jmp     short loc_180044CAE
0x180044ce5  mov     [rcx], r13w
0x180044ce9  lea     rdx, [rbp+600h+FileName]; lpFileName
0x180044ced  lea     rcx, [rbp+600h+Buffer]; lpBuffer
0x180044cf4  xor     r9d, r9d
0x180044cf7  xor     r8d, r8d; lpFilePart
0x180044cfa  call    bMakePathNameW
0x180044cff  test    eax, eax
0x180044d01  jz      loc_180044E7E
0x180044d07  mov     eax, [rbp+600h+arg_30]
0x180044d0d  lea     r8, [rbp+600h+DosPathName]
0x180044d14  mov     [rsp+700h+var_6D0], eax; int
0x180044d18  lea     rcx, [rbp+600h+Buffer]; SourceString
0x180044d1f  mov     rax, [rsp+700h+var_688]
0x180044d24  xor     r9d, r9d
0x180044d27  mov     [rsp+700h+var_6D8], rax; __int64
0x180044d2c  mov     edx, 104h
0x180044d31  lea     rax, [rsp+700h+var_6B4]
0x180044d36  mov     [rsp+700h+var_6E0], rax; __int64
0x180044d3b  call    cGetTTFFromFOT
0x180044d40  test    eax, eax
0x180044d42  jz      loc_180044E7E
0x180044d48  xorps   xmm0, xmm0
0x180044d4b  movups  xmmword ptr [rsp+700h+NtPathName.Length], xmm0
0x180044d50  cmp     [rbp+600h+arg_20], r13d
0x180044d57  jz      short loc_180044D70
0x180044d59  lea     rcx, [rbp+600h+DosPathName]
0x180044d60  call    bFileIsOnTheHardDrive
0x180044d65  test    eax, eax
0x180044d67  jz      loc_180044F1C
0x180044d6d  or      edi, 1
0x180044d70  xor     r9d, r9d; DirectoryInfo
0x180044d73  lea     rdx, [rsp+700h+NtPathName]; NtPathName
0x180044d78  xor     r8d, r8d; NtFileNamePart
0x180044d7b  lea     rcx, [rbp+600h+DosPathName]; DosPathName
0x180044d82  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180044d89  nop     dword ptr [rax+rax+00h]
0x180044d8e  test    al, al
0x180044d90  jz      loc_180044EF7
0x180044d96  mov     rdx, [rsp+700h+NtPathName.Buffer]; Src
0x180044d9b  test    rdx, rdx
0x180044d9e  jz      loc_180044EF7
0x180044da4  movzx   eax, [rsp+700h+NtPathName.Length]
0x180044da9  shr     eax, 1
0x180044dab  mov     [rbp+600h+var_680], eax
0x180044dae  lea     r13d, [rax+1]
0x180044db2  cmp     r13d, 104h
0x180044db9  ja      loc_180044EE2
0x180044dbf  movzx   r8d, [rsp+700h+NtPathName.Length]; Size
0x180044dc5  mov     rcx, qword ptr [rsp+700h+var_6B4+4]; void *
0x180044dca  add     [rsp+700h+var_6B8], r13d
0x180044dcf  call    memcpy_0
0x180044dd4  mov     rdx, qword ptr [rsp+700h+var_6B4+4]
0x180044dd9  lea     eax, [r14-1]
0x180044ddd  cmp     [rsp+700h+var_6BC], eax
0x180044de1  mov     eax, [rbp+600h+var_680]
0x180044de4  sbb     cx, cx
0x180044de7  and     cx, 7Ch
0x180044deb  mov     [rdx+rax*2], cx
0x180044def  lea     rdx, [rdx+r13*2]
0x180044df3  mov     r13d, [rsp+700h+var_6C0]
0x180044df8  mov     qword ptr [rsp+700h+var_6B4+4], rdx
0x180044dfd  mov     rcx, gs:60h
0x180044e06  xor     edx, edx; Flags
0x180044e08  mov     r8, [rsp+700h+NtPathName.Buffer]; P
0x180044e0d  mov     rcx, [rcx+30h]; HeapHandle
0x180044e11  call    cs:__imp_RtlFreeHeap
0x180044e18  nop     dword ptr [rax+rax+00h]
0x180044e1d  xor     ecx, ecx
0x180044e1f  test    r13d, r13d
0x180044e22  jz      short loc_180044E7B
0x180044e24  mov     eax, [rsp+700h+var_6BC]
0x180044e28  add     r12, 2
0x180044e2c  inc     eax
0x180044e2e  jmp     loc_180044C61
0x180044e33  cmp     [rbp+600h+arg_20], ecx
0x180044e39  jz      short loc_180044E5A
0x180044e3b  and     ebx, 3
0x180044e3e  sub     ebx, 1
0x180044e41  jz      short loc_180044E75
0x180044e43  sub     ebx, 1
0x180044e46  jnz     loc_180044F01
0x180044e4c  and     dil, 2
0x180044e50  neg     dil
0x180044e53  sbb     eax, eax
0x180044e55  test    r13d, eax
0x180044e58  jz      short loc_180044E7B
0x180044e5a  mov     rax, [rsp+700h+var_6A8]
0x180044e5f  mov     ecx, [rsp+700h+var_6B8]
0x180044e63  mov     [rax], ecx
0x180044e65  mov     rax, [rsp+700h+var_6A0]
0x180044e6a  mov     [rax], r14d
0x180044e6d  mov     eax, dword ptr [rsp+700h+var_6B4]
0x180044e71  or      [rsi], eax
0x180044e73  jmp     short loc_180044EB4
0x180044e75  test    dil, 2
0x180044e79  jz      short loc_180044E5A
0x180044e7b  xor     r13d, r13d
0x180044e7e  mov     rax, [rsp+700h+var_6A8]
0x180044e83  mov     [rax], r13d
0x180044e86  mov     rax, [rsp+700h+var_6A0]
0x180044e8b  mov     [rax], r13d
0x180044e8e  test    r15, r15
0x180044e91  jz      short loc_180044EB4
0x180044e93  mov     rcx, gs:60h
0x180044e9c  mov     r8, r15; P
0x180044e9f  xor     edx, edx; Flags
0x180044ea1  mov     rcx, [rcx+30h]; HeapHandle
0x180044ea5  call    cs:__imp_RtlFreeHeap
0x180044eac  nop     dword ptr [rax+rax+00h]
0x180044eb1  mov     r15, r13
0x180044eb4  mov     rax, r15
0x180044eb7  mov     rcx, [rbp+600h+var_40]
0x180044ebe  xor     rcx, rsp; StackCookie
0x180044ec1  call    __security_check_cookie
0x180044ec6  mov     rbx, [rsp+700h+arg_0]
0x180044ece  add     rsp, 6D0h
0x180044ed5  pop     r15
0x180044ed7  pop     r14
0x180044ed9  pop     r13
0x180044edb  pop     r12
0x180044edd  pop     rdi
0x180044ede  pop     rsi
0x180044edf  pop     rbp
0x180044ee0  retn
0x180044ee2  xor     r13d, r13d
0x180044ee5  mov     [rsp+700h+var_6C0], r13d
0x180044eea  jmp     loc_180044DFD
0x180044eef  mov     ebx, r13d
0x180044ef2  jmp     loc_180044BEC
0x180044ef7  mov     [rsp+700h+var_6C0], r13d
0x180044efc  jmp     loc_180044E1D
0x180044f01  cmp     ebx, 1
0x180044f04  jz      loc_180044E7B
0x180044f0a  mov     eax, [rsi]
0x180044f0c  test    dil, 2
0x180044f10  jnz     short loc_180044F24
0x180044f12  or      eax, 1
0x180044f15  mov     [rsi], eax
0x180044f17  jmp     loc_180044E5A
0x180044f1c  or      edi, 2
0x180044f1f  jmp     loc_180044D70
0x180044f24  or      eax, 2
0x180044f27  jmp     short loc_180044F15
```
