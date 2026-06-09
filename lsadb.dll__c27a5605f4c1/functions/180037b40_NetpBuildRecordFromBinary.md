# NetpBuildRecordFromBinary

- ea: `0x180037b40`
- end: `0x180037e08`
- name: `NetpBuildRecordFromBinary`
- size: `712`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003759c`
- `0x180037768`

## callees

- `0x180001fb8`
- `0x180037b40`
- `0x18003a4f4`
- `0x18003a624`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037cc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037cc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037dd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037de0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037de8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037dd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037de0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037de8`
- `ntdll!RtlLengthSid` at `0x180037c0d`
- `ntdll!RtlLengthSid` at `0x180037d35`
- `ntdll!RtlLengthSid` at `0x180037c0d`
- `ntdll!RtlLengthSid` at `0x180037d35`

## pseudocode

```c
__int64 __fastcall NetpBuildRecordFromBinary(int a1, __int64 *a2, _BYTE *a3, unsigned int a4, _QWORD *a5)
{
  size_t v5; // r13
  PSID v7; // r14
  int v8; // ebx
  unsigned __int8 v9; // r9
  unsigned int v10; // edi
  unsigned __int16 v11; // r12
  unsigned __int16 v12; // r15
  int v13; // eax
  ULONG v14; // eax
  SIZE_T v15; // rbx
  char *v16; // rax
  char *v17; // rdi
  __int64 v18; // rax
  char *v19; // rsi
  ULONG v20; // eax
  __int64 v21; // rbx
  HLOCAL v22; // rdx
  HLOCAL v23; // rdx
  int v25; // [rsp+30h] [rbp-40h] BYREF
  _BYTE *v26; // [rsp+38h] [rbp-38h] BYREF
  PSID Sid; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL v29[2]; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 v32; // [rsp+C8h] [rbp+58h]

  v5 = a4;
  Sid = 0;
  v7 = 0;
  *a5 = 0;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v29 = 0;
  if ( a4 <= 4 || (v9 = a3[4], v32 = v9, v26 = a3 + 5, v25 = v5 - 5, v9 <= 3u) )
  {
    v8 = -2147483643;
    goto LABEL_31;
  }
  if ( v9 != 4 )
  {
    v10 = v5 + 56;
    if ( (unsigned int)v5 < 0xFFFFFFC8 )
    {
      v11 = (unsigned __int16)hMem[0];
      v12 = (unsigned __int16)v29[0];
      goto LABEL_18;
    }
LABEL_30:
    v8 = -1073741675;
    goto LABEL_31;
  }
  v13 = NetpUnmarshalSid((int)a3 + 5, (int)v5 - 5, (unsigned int)&v26, (unsigned int)&v25, (__int64)&Sid);
  v7 = Sid;
  v8 = v13;
  if ( v13 < 0 )
    goto LABEL_31;
  v10 = 56;
  if ( Sid )
  {
    v14 = RtlLengthSid(Sid);
    v10 = v14 + 56;
    if ( v14 >= 0xFFFFFFC8 )
      goto LABEL_30;
  }
  v8 = NetpUnmarshalString((_DWORD)v26, v25, (unsigned int)&v26, (unsigned int)&v25, (__int64)hMem);
  if ( v8 < 0 )
    goto LABEL_31;
  v11 = (unsigned __int16)hMem[0];
  if ( LOWORD(hMem[0]) )
  {
    if ( v10 + LOWORD(hMem[0]) + 2 < v10 )
      goto LABEL_30;
    v10 += LOWORD(hMem[0]) + 2;
  }
  v8 = NetpUnmarshalString((_DWORD)v26, v25, (unsigned int)&v26, (unsigned int)&v25, (__int64)v29);
  if ( v8 < 0 )
    goto LABEL_31;
  v12 = (unsigned __int16)v29[0];
  if ( LOWORD(v29[0]) )
  {
    if ( v10 + LOWORD(v29[0]) + 2 < v10 )
      goto LABEL_30;
    v10 += LOWORD(v29[0]) + 2;
  }
LABEL_18:
  if ( v10 + 8 < v10 )
    goto LABEL_30;
  v15 = (v10 + 7) & 0xFFFFFFF8;
  v16 = (char *)LocalAlloc(0x40u, v15);
  v17 = v16;
  if ( v16 )
  {
    memset_0(v16, 0, v15);
    *(_DWORD *)v17 = a1;
    v18 = *a2;
    v19 = v17 + 56;
    *((_QWORD *)v17 + 1) = v18;
    if ( v32 == 4 )
    {
      *((_DWORD *)v17 + 1) = 4;
      if ( v7 )
      {
        v20 = RtlLengthSid(v7);
        *((_QWORD *)v17 + 2) = v19;
        v21 = v20;
        memcpy_0(v17 + 56, v7, v20);
        v19 += v21;
      }
      if ( v11 )
      {
        v22 = hMem[1];
        *((_QWORD *)v17 + 4) = v19;
        *((_WORD *)v17 + 13) = v11 + 2;
        *((_WORD *)v17 + 12) = v11;
        memcpy_0(v19, v22, v11);
        *(_WORD *)&v19[v11] = 0;
        v19 += v11 + 2;
      }
      if ( v12 )
      {
        v23 = v29[1];
        *((_QWORD *)v17 + 6) = v19;
        *((_WORD *)v17 + 21) = v12 + 2;
        *((_WORD *)v17 + 20) = v12;
        memcpy_0(v19, v23, v12);
        *(_WORD *)&v19[v12] = 0;
      }
    }
    else
    {
      *((_DWORD *)v17 + 1) = 3;
      *((_QWORD *)v17 + 3) = v19;
      *((_DWORD *)v17 + 4) = v5;
      memcpy_0(v17 + 56, a3, v5);
    }
    v8 = 0;
    *a5 = v17;
  }
  else
  {
    v8 = -1073741670;
  }
LABEL_31:
  LocalFree(v7);
  LocalFree(hMem[1]);
  LocalFree(v29[1]);
  LocalFree(0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180037b40  mov     [rsp-38h+arg_8], rbx
0x180037b45  mov     [rsp-38h+Src], r8
0x180037b4a  mov     [rsp-38h+arg_0], ecx
0x180037b4e  push    rbp
0x180037b4f  push    rsi
0x180037b50  push    rdi
0x180037b51  push    r12
0x180037b53  push    r13
0x180037b55  push    r14
0x180037b57  push    r15
0x180037b59  mov     rbp, rsp
0x180037b5c  sub     rsp, 70h
0x180037b60  mov     rax, [rbp+arg_20]
0x180037b64  xor     r15d, r15d
0x180037b67  mov     r13d, r9d
0x180037b6a  xorps   xmm0, xmm0
0x180037b6d  mov     [rbp+Sid], r15
0x180037b71  xorps   xmm1, xmm1
0x180037b74  mov     rsi, rdx
0x180037b77  mov     r14d, r15d
0x180037b7a  mov     [rax], r15
0x180037b7d  movups  xmmword ptr [rbp+hMem], xmm0
0x180037b81  movups  xmmword ptr [rbp+var_18], xmm1
0x180037b85  cmp     r9d, 4
0x180037b89  jnb     short loc_180037B95
0x180037b8b  mov     ebx, 80000005h
0x180037b90  jmp     loc_180037DC9
0x180037b95  lea     eax, [r13-4]
0x180037b99  cmp     eax, 1
0x180037b9c  jb      short loc_180037B8B
0x180037b9e  mov     r9b, [r8+4]
0x180037ba2  lea     rcx, [r8+5]
0x180037ba6  mov     [rbp+arg_18], r9b
0x180037baa  lea     edx, [rax-1]
0x180037bad  mov     [rbp+var_38], rcx
0x180037bb1  mov     [rbp+var_40], edx
0x180037bb4  cmp     r9b, 3
0x180037bb8  jbe     short loc_180037B8B
0x180037bba  cmp     r9b, 4
0x180037bbe  jz      short loc_180037BDC
0x180037bc0  lea     edi, [r13+38h]
0x180037bc4  cmp     edi, 38h ; '8'
0x180037bc7  jb      loc_180037DC4
0x180037bcd  movzx   r12d, word ptr [rbp+hMem]
0x180037bd2  movzx   r15d, word ptr [rbp+var_18]
0x180037bd7  jmp     loc_180037CA4
0x180037bdc  lea     rax, [rbp+Sid]
0x180037be0  lea     r9, [rbp+var_40]
0x180037be4  mov     [rsp+70h+var_50], rax
0x180037be9  lea     r8, [rbp+var_38]
0x180037bed  call    NetpUnmarshalSid
0x180037bf2  mov     r14, [rbp+Sid]
0x180037bf6  mov     ebx, eax
0x180037bf8  test    eax, eax
0x180037bfa  js      loc_180037DC9
0x180037c00  mov     edi, 38h ; '8'
0x180037c05  test    r14, r14
0x180037c08  jz      short loc_180037C1F
0x180037c0a  mov     rcx, r14; Sid
0x180037c0d  call    cs:__imp_RtlLengthSid
0x180037c13  lea     edi, [rax+38h]
0x180037c16  cmp     edi, 38h ; '8'
0x180037c19  jb      loc_180037DC4
0x180037c1f  mov     edx, [rbp+var_40]
0x180037c22  lea     rax, [rbp+hMem]
0x180037c26  mov     rcx, [rbp+var_38]
0x180037c2a  lea     r9, [rbp+var_40]
0x180037c2e  lea     r8, [rbp+var_38]
0x180037c32  mov     [rsp+70h+var_50], rax
0x180037c37  call    NetpUnmarshalString
0x180037c3c  mov     ebx, eax
0x180037c3e  test    eax, eax
0x180037c40  js      loc_180037DC9
0x180037c46  movzx   r12d, word ptr [rbp+hMem]
0x180037c4b  test    r12w, r12w
0x180037c4f  jz      short loc_180037C62
0x180037c51  lea     ecx, [r12+2]
0x180037c56  add     ecx, edi
0x180037c58  cmp     ecx, edi
0x180037c5a  jb      loc_180037DC4
0x180037c60  mov     edi, ecx
0x180037c62  mov     edx, [rbp+var_40]
0x180037c65  lea     rax, [rbp+var_18]
0x180037c69  mov     rcx, [rbp+var_38]
0x180037c6d  lea     r9, [rbp+var_40]
0x180037c71  lea     r8, [rbp+var_38]
0x180037c75  mov     [rsp+70h+var_50], rax
0x180037c7a  call    NetpUnmarshalString
0x180037c7f  mov     ebx, eax
0x180037c81  test    eax, eax
0x180037c83  js      loc_180037DC9
0x180037c89  movzx   r15d, word ptr [rbp+var_18]
0x180037c8e  test    r15w, r15w
0x180037c92  jz      short loc_180037CA4
0x180037c94  lea     ecx, [r15+2]
0x180037c98  add     ecx, edi
0x180037c9a  cmp     ecx, edi
0x180037c9c  jb      loc_180037DC4
0x180037ca2  mov     edi, ecx
0x180037ca4  lea     eax, [rdi+8]
0x180037ca7  cmp     eax, edi
0x180037ca9  jbe     loc_180037DC4
0x180037caf  mov     eax, 0FFFFFFF8h
0x180037cb4  lea     ebx, [rdi+7]
0x180037cb7  and     rbx, rax
0x180037cba  mov     ecx, 40h ; '@'; uFlags
0x180037cbf  mov     rdx, rbx; uBytes
0x180037cc2  call    cs:__imp_LocalAlloc
0x180037cc8  mov     rdi, rax
0x180037ccb  test    rax, rax
0x180037cce  jnz     short loc_180037CDA
0x180037cd0  mov     ebx, 0C000009Ah
0x180037cd5  jmp     loc_180037DC9
0x180037cda  mov     r8, rbx; Size
0x180037cdd  xor     edx, edx; Val
0x180037cdf  mov     rcx, rdi; void *
0x180037ce2  call    memset_0
0x180037ce7  cmp     [rbp+arg_18], 4
0x180037ceb  mov     eax, [rbp+arg_0]
0x180037cee  mov     [rdi], eax
0x180037cf0  mov     rax, [rsi]
0x180037cf3  lea     rsi, [rdi+38h]
0x180037cf7  mov     [rdi+8], rax
0x180037cfb  jz      short loc_180037D23
0x180037cfd  mov     rdx, [rbp+Src]; Src
0x180037d01  mov     r8, r13; Size
0x180037d04  mov     rcx, rsi; void *
0x180037d07  mov     dword ptr [rdi+4], 3
0x180037d0e  mov     [rdi+18h], rsi
0x180037d12  mov     [rdi+10h], r13d
0x180037d16  call    memcpy_0
0x180037d1b  xor     r13d, r13d
0x180037d1e  jmp     loc_180037DB8
0x180037d23  xor     r13d, r13d
0x180037d26  mov     dword ptr [rdi+4], 4
0x180037d2d  test    r14, r14
0x180037d30  jz      short loc_180037D52
0x180037d32  mov     rcx, r14; Sid
0x180037d35  call    cs:__imp_RtlLengthSid
0x180037d3b  mov     rdx, r14; Src
0x180037d3e  mov     [rdi+10h], rsi
0x180037d42  mov     r8d, eax; Size
0x180037d45  mov     rcx, rsi; void *
0x180037d48  mov     ebx, eax
0x180037d4a  call    memcpy_0
0x180037d4f  add     rsi, rbx
0x180037d52  test    r12w, r12w
0x180037d56  jz      short loc_180037D89
0x180037d58  mov     rdx, [rbp+hMem+8]; Src
0x180037d5c  lea     eax, [r12+2]
0x180037d61  movzx   ebx, r12w
0x180037d65  mov     rcx, rsi; void *
0x180037d68  mov     r8d, ebx; Size
0x180037d6b  mov     [rdi+20h], rsi
0x180037d6f  mov     [rdi+1Ah], ax
0x180037d73  mov     [rdi+18h], r12w
0x180037d78  call    memcpy_0
0x180037d7d  lea     rcx, [rbx+rsi]
0x180037d81  mov     [rcx], r13w
0x180037d85  lea     rsi, [rcx+2]
0x180037d89  test    r15w, r15w
0x180037d8d  jz      short loc_180037DB8
0x180037d8f  mov     rdx, [rbp+var_18+8]; Src
0x180037d93  lea     eax, [r15+2]
0x180037d97  movzx   ebx, r15w
0x180037d9b  mov     rcx, rsi; void *
0x180037d9e  mov     r8d, ebx; Size
0x180037da1  mov     [rdi+30h], rsi
0x180037da5  mov     [rdi+2Ah], ax
0x180037da9  mov     [rdi+28h], r15w
0x180037dae  call    memcpy_0
0x180037db3  mov     [rbx+rsi], r13w
0x180037db8  mov     rax, [rbp+arg_20]
0x180037dbc  mov     ebx, r13d
0x180037dbf  mov     [rax], rdi
0x180037dc2  jmp     short loc_180037DC9
0x180037dc4  mov     ebx, 0C0000095h
0x180037dc9  mov     rcx, r14; hMem
0x180037dcc  call    cs:__imp_LocalFree
0x180037dd2  mov     rcx, [rbp+hMem+8]; hMem
0x180037dd6  call    cs:__imp_LocalFree
0x180037ddc  mov     rcx, [rbp+var_18+8]; hMem
0x180037de0  call    cs:__imp_LocalFree
0x180037de6  xor     ecx, ecx; hMem
0x180037de8  call    cs:__imp_LocalFree
0x180037dee  mov     eax, ebx
0x180037df0  mov     rbx, [rsp+70h+arg_8]
0x180037df8  add     rsp, 70h
0x180037dfc  pop     r15
0x180037dfe  pop     r14
0x180037e00  pop     r13
0x180037e02  pop     r12
0x180037e04  pop     rdi
0x180037e05  pop     rsi
0x180037e06  pop     rbp
0x180037e07  retn
```
