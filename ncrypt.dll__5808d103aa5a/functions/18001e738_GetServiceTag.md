# GetServiceTag

- ea: `0x18001e738`
- end: `0x18001e89b`
- name: `GetServiceTag`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001e50c`

## callees

- `0x1800198c4`
- `0x18001e32c`
- `0x18001e738`
- `0x18001ea10`
- `0x18001ead4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e880`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e880`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18001e767`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x18001e767`

## pseudocode

```c
__int64 __fastcall GetServiceTag(int a1, STRSAFE_LPWSTR *a2, size_t a3)
{
  _QWORD *v4; // rsi
  size_t v5; // rdx
  unsigned int v6; // ebx
  ULONGLONG v7; // rdi
  __int64 i; // r11
  __int64 v9; // rax
  const wchar_t *v10; // rcx
  HRESULT v11; // eax
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  int j; // edx
  __int64 v16; // rax
  const wchar_t *v17; // rbp
  __int128 v19; // [rsp+20h] [rbp-28h] BYREF
  size_t pcchLength; // [rsp+60h] [rbp+18h] BYREF

  pcchLength = a3;
  v19 = 0;
  LODWORD(v19) = a1;
  v4 = 0;
  v6 = I_QueryTagInformation(0, 3, &v19);
  if ( !v6 )
  {
    v4 = (_QWORD *)*((_QWORD *)&v19 + 1);
    if ( !*((_QWORD *)&v19 + 1) )
    {
      v6 = 1168;
      goto LABEL_26;
    }
    v7 = 0;
    for ( i = 0; (unsigned int)i < *(_DWORD *)v4; i = (unsigned int)(i + 1) )
    {
      v9 = v4[1];
      if ( *(_DWORD *)(v9 + 24 * i) == 1 )
      {
        v10 = *(const wchar_t **)(v9 + 24 * i + 8);
        if ( v10 )
        {
          pcchLength = 0;
          v11 = StringCchLengthW(v10, v5, &pcchLength);
          if ( v11 < 0 )
          {
            v6 = v11;
            goto LABEL_26;
          }
          v12 = v7 + pcchLength;
          if ( v7 + pcchLength < v7 )
            goto LABEL_12;
          v7 = v12 + 1;
          if ( v12 + 1 < v12 )
            goto LABEL_12;
        }
      }
    }
    if ( !v7 )
    {
LABEL_25:
      v6 = 0;
      goto LABEL_26;
    }
    pcchLength = 0;
    if ( ULongLongMult(v7, v5, &pcchLength) < 0 )
    {
LABEL_12:
      v6 = 534;
      goto LABEL_26;
    }
    v13 = CertInUseZeroAlloc(pcchLength);
    *a2 = (STRSAFE_LPWSTR)v13;
    if ( v13 )
    {
      v14 = 0;
      for ( j = 1; (unsigned int)v14 < *(_DWORD *)v4; v14 = (unsigned int)(v14 + 1) )
      {
        v16 = v4[1];
        if ( *(_DWORD *)(v16 + 24 * v14) == 1 )
        {
          v17 = *(const wchar_t **)(v16 + 24 * v14 + 8);
          if ( v17 )
          {
            if ( !j )
              StringCchCatW(*a2, v7, L",");
            StringCchCatW(*a2, v7, v17);
            j = 0;
          }
        }
      }
      g_stServiceNameLen = v7;
      goto LABEL_25;
    }
  }
LABEL_26:
  LocalFree(v4);
  return v6;
}

```

## disassembly

```asm
0x18001e738  mov     rax, rsp
0x18001e73b  mov     [rax+8], rbx
0x18001e73f  mov     [rax+10h], rbp
0x18001e743  mov     [rax+18h], r8
0x18001e747  push    rsi
0x18001e748  push    rdi
0x18001e749  push    r14
0x18001e74b  sub     rsp, 30h
0x18001e74f  xorps   xmm0, xmm0
0x18001e752  lea     r8, [rax-28h]
0x18001e756  movups  xmmword ptr [rax-28h], xmm0
0x18001e75a  mov     r14, rdx
0x18001e75d  mov     [rax-28h], ecx
0x18001e760  xor     esi, esi
0x18001e762  xor     ecx, ecx
0x18001e764  lea     edx, [rsi+3]
0x18001e767  call    cs:__imp_I_QueryTagInformation
0x18001e76d  mov     ebx, eax
0x18001e76f  test    eax, eax
0x18001e771  jnz     loc_18001E87D
0x18001e777  mov     rsi, [rsp+48h+var_20]
0x18001e77c  test    rsi, rsi
0x18001e77f  jnz     short loc_18001E78B
0x18001e781  mov     ebx, 490h
0x18001e786  jmp     loc_18001E87D
0x18001e78b  xor     edi, edi
0x18001e78d  xor     r11d, r11d
0x18001e790  cmp     r11d, [rsi]
0x18001e793  jnb     short loc_18001E7F0
0x18001e795  mov     rax, [rsi+8]
0x18001e799  lea     rcx, [r11+r11*2]
0x18001e79d  cmp     dword ptr [rax+rcx*8], 1
0x18001e7a1  jnz     short loc_18001E7DA
0x18001e7a3  mov     rcx, [rax+rcx*8+8]; psz
0x18001e7a8  test    rcx, rcx
0x18001e7ab  jz      short loc_18001E7DA
0x18001e7ad  lea     r8, [rsp+48h+pcchLength]; pcchLength
0x18001e7b2  mov     [rsp+48h+pcchLength], 0
0x18001e7bb  call    StringCchLengthW
0x18001e7c0  test    eax, eax
0x18001e7c2  js      short loc_18001E7E9
0x18001e7c4  mov     rcx, [rsp+48h+pcchLength]
0x18001e7c9  add     rcx, rdi
0x18001e7cc  cmp     rcx, rdi
0x18001e7cf  jb      short loc_18001E7DF
0x18001e7d1  lea     rdi, [rcx+1]
0x18001e7d5  cmp     rdi, rcx
0x18001e7d8  jb      short loc_18001E7DF
0x18001e7da  inc     r11d
0x18001e7dd  jmp     short loc_18001E790
0x18001e7df  mov     ebx, 216h
0x18001e7e4  jmp     loc_18001E87D
0x18001e7e9  mov     ebx, eax
0x18001e7eb  jmp     loc_18001E87D
0x18001e7f0  test    rdi, rdi
0x18001e7f3  jz      loc_18001E87B
0x18001e7f9  lea     r8, [rsp+48h+pcchLength]; pullResult
0x18001e7fe  mov     [rsp+48h+pcchLength], 0
0x18001e807  mov     rcx, rdi; ullMultiplicand
0x18001e80a  call    ULongLongMult
0x18001e80f  test    eax, eax
0x18001e811  js      short loc_18001E7DF
0x18001e813  mov     rcx, [rsp+48h+pcchLength]
0x18001e818  call    CertInUseZeroAlloc
0x18001e81d  mov     [r14], rax
0x18001e820  test    rax, rax
0x18001e823  jz      short loc_18001E87D
0x18001e825  xor     ebx, ebx
0x18001e827  mov     edx, 1
0x18001e82c  cmp     [rsi], ebx
0x18001e82e  jbe     short loc_18001E874
0x18001e830  mov     rax, [rsi+8]
0x18001e834  lea     rcx, [rbx+rbx*2]
0x18001e838  cmp     dword ptr [rax+rcx*8], 1
0x18001e83c  jnz     short loc_18001E86E
0x18001e83e  mov     rbp, [rax+rcx*8+8]
0x18001e843  test    rbp, rbp
0x18001e846  jz      short loc_18001E86E
0x18001e848  test    edx, edx
0x18001e84a  jnz     short loc_18001E85E
0x18001e84c  mov     rcx, [r14]; pszDest
0x18001e84f  lea     r8, asc_1800237B4; ","
0x18001e856  mov     rdx, rdi; cchDest
0x18001e859  call    StringCchCatW
0x18001e85e  mov     rcx, [r14]; pszDest
0x18001e861  mov     r8, rbp; pszSrc
0x18001e864  mov     rdx, rdi; cchDest
0x18001e867  call    StringCchCatW
0x18001e86c  xor     edx, edx
0x18001e86e  inc     ebx
0x18001e870  cmp     ebx, [rsi]
0x18001e872  jb      short loc_18001E830
0x18001e874  mov     cs:g_stServiceNameLen, rdi
0x18001e87b  xor     ebx, ebx
0x18001e87d  mov     rcx, rsi; hMem
0x18001e880  call    cs:__imp_LocalFree
0x18001e886  mov     rbp, [rsp+48h+arg_8]
0x18001e88b  mov     eax, ebx
0x18001e88d  mov     rbx, [rsp+48h+arg_0]
0x18001e892  add     rsp, 30h
0x18001e896  pop     r14
0x18001e898  pop     rdi
0x18001e899  pop     rsi
0x18001e89a  retn
```
