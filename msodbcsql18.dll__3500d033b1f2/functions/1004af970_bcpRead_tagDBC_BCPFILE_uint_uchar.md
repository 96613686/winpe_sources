# bcpRead(tagDBC *,BCPFILE *,uint,uchar *)

- ea: `0x1004af970`
- end: `0x1004afcc4`
- name: `?bcpRead@@YAFPEAUtagDBC@@PEAUBCPFILE@@IPEAE@Z`
- size: `852`
- prototype: `__int16(struct tagDBC *, struct BCPFILE *, unsigned int, unsigned __int8 *)`
- caller_count: `19`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100496940`
- `0x100497780`
- `0x100497980`
- `0x100497bd0`
- `0x100499300`
- `0x100499e40`
- `0x10049b4a0`
- `0x1004a8bd0`
- `0x1004a8e90`
- `0x1004a9870`
- `0x1004abebc`
- `0x1004aeae4`
- `0x1004afccc`
- `0x1004afda4`
- `0x1004b02c8`
- `0x1004b07e0`
- `0x1004b1670`
- `0x1004b2260`
- `0x1004b4cd0`

## callees

- `0x1004af970`
- `0x1004b02c8`
- `0x1005212b4`
- `0x100546a24`
- `0x100546a7c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004afa52`
- `KERNEL32!GetLastError` at `0x1004afa52`
- `KERNEL32!ReadFile` at `0x1004afa00`
- `KERNEL32!ReadFile` at `0x1004afa72`
- `KERNEL32!ReadFile` at `0x1004afab2`
- `KERNEL32!ReadFile` at `0x1004afba5`
- `KERNEL32!ReadFile` at `0x1004afa00`
- `KERNEL32!ReadFile` at `0x1004afa72`
- `KERNEL32!ReadFile` at `0x1004afab2`
- `KERNEL32!ReadFile` at `0x1004afba5`
- `KERNEL32!SetFilePointer` at `0x1004afa47`
- `KERNEL32!SetFilePointer` at `0x1004afa47`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004af9c3`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004afc7a`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004af9c3`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004afc7a`

## pseudocode

```c
__int64 __fastcall bcpRead(struct tagDBC *a1, struct BCPFILE *a2, DWORD a3, unsigned __int8 *a4)
{
  rsize_t v5; // r14
  unsigned __int16 v8; // di
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  void *v11; // rdx
  BOOL File; // eax
  LONG v13; // edx
  BOOL v14; // eax
  BOOL v15; // eax
  DWORD v16; // r8d
  __int64 v17; // rcx
  unsigned __int64 *v18; // rdx
  unsigned __int64 *v19; // r8
  unsigned __int64 v20; // r9
  unsigned __int64 v21; // r12
  BOOL v22; // eax
  DWORD v23; // r8d
  LONG DistanceToMoveHigh; // [rsp+30h] [rbp-28h] BYREF
  DWORD v26; // [rsp+34h] [rbp-24h] BYREF
  DWORD v27; // [rsp+38h] [rbp-20h] BYREF
  DWORD v28; // [rsp+3Ch] [rbp-1Ch] BYREF
  __int64 NumberOfBytesRead; // [rsp+68h] [rbp+10h] BYREF

  v5 = a3;
  v8 = 0;
  if ( *((_DWORD *)a2 + 16) )
  {
    v9 = *((_QWORD *)a2 + 7);
    if ( a3 + v9 >= v9 && a3 + v9 <= *((_QWORD *)a2 + 4) )
    {
      _mm_lfence();
      memcpy_s(a4, a3, (const void *const)(*((_QWORD *)a2 + 7) + *((_QWORD *)a2 + 2)), a3);
      *((_QWORD *)a2 + 7) += v5;
      goto LABEL_34;
    }
    goto LABEL_7;
  }
  v10 = *((_QWORD *)a1 + 15);
  v11 = *(void **)(v10 + 1880);
  if ( !v11 )
  {
    File = ReadFile(*(HANDLE *)a2, a4, a3, (LPDWORD)&NumberOfBytesRead, 0);
    if ( (File ? NumberOfBytesRead : 0) != 0 )
      goto LABEL_34;
    goto LABEL_7;
  }
  if ( a3 >= 0x3800 )
  {
    v13 = *(_DWORD *)(v10 + 1616);
    DistanceToMoveHigh = HIDWORD(*(_QWORD *)(v10 + 1616));
    if ( SetFilePointer(*(HANDLE *)a2, v13, &DistanceToMoveHigh, 0) != -1 || !GetLastError() )
    {
      _mm_lfence();
      v14 = ReadFile(*(HANDLE *)a2, a4, v5, &v26, 0);
      if ( (v14 ? v26 : 0) != 0 )
      {
        *(_QWORD *)(*((_QWORD *)a1 + 15) + 1616LL) += v5;
        goto LABEL_34;
      }
    }
LABEL_7:
    v8 = 100;
    goto LABEL_34;
  }
  if ( *(_QWORD *)(v10 + 1632) == -1 )
  {
    v15 = ReadFile(*(HANDLE *)a2, v11, 0x4000u, &v27, 0);
    v16 = v15 ? v27 : 0;
    if ( !v16 )
      goto LABEL_7;
    *(_DWORD *)(*((_QWORD *)a1 + 15) + 52LL) = *(_DWORD *)(*((_QWORD *)a1 + 15) + 52LL) & 0xFFFFFFF7
                                             | (v16 != 0x4000 ? 8 : 0);
    *(_QWORD *)(*((_QWORD *)a1 + 15) + 1632LL) = (int)(v16 - 1);
  }
  v17 = *((_QWORD *)a1 + 15);
  v18 = (unsigned __int64 *)(v17 + 1616);
  v19 = (unsigned __int64 *)(v17 + 1632);
  if ( (*(_BYTE *)(v17 + 52) & 8) != 0 && *v18 > *v19 )
    goto LABEL_7;
  v20 = *v18;
  if ( *v18 < *(_QWORD *)(v17 + 1624) || v20 + (int)v5 > *v19 )
  {
    v21 = 0;
    if ( v20 >= 0x800 )
      v21 = v20 - 2048;
    NumberOfBytesRead = *(_QWORD *)(v17 + 1880);
    *(_QWORD *)(v17 + 1880) = 0;
    if ( *((_DWORD *)a2 + 16) )
      *((_QWORD *)a2 + 7) = v21;
    else
      bcpSeek64(a1, a2, v21);
    *(_QWORD *)(*((_QWORD *)a1 + 15) + 1880LL) = NumberOfBytesRead;
    v22 = ReadFile(*(HANDLE *)a2, *(LPVOID *)(*((_QWORD *)a1 + 15) + 1880LL), 0x4000u, &v28, 0);
    v23 = v22 ? v28 : 0;
    if ( !v23 )
      goto LABEL_7;
    *(_DWORD *)(*((_QWORD *)a1 + 15) + 52LL) = *(_DWORD *)(*((_QWORD *)a1 + 15) + 52LL) & 0xFFFFFFF7
                                             | (v23 != 0x4000 ? 8 : 0);
    *(_QWORD *)(*((_QWORD *)a1 + 15) + 1624LL) = v21;
    *(_QWORD *)(*((_QWORD *)a1 + 15) + 1632LL) = *(_QWORD *)(*((_QWORD *)a1 + 15) + 1624LL) - 1LL + v23;
  }
  if ( !a4 )
  {
LABEL_34:
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x7F1409u, v8);
    return v8;
  }
  if ( *(_QWORD *)(*((_QWORD *)a1 + 15) + 1616LL) >= *(_QWORD *)(*((_QWORD *)a1 + 15) + 1624LL) )
  {
    _mm_lfence();
    memcpy_s(
      a4,
      v5,
      (const void *const)(*(_QWORD *)(*((_QWORD *)a1 + 15) + 1616LL)
                        + *(_QWORD *)(*((_QWORD *)a1 + 15) + 1880LL)
                        - *(_QWORD *)(*((_QWORD *)a1 + 15) + 1624LL)),
      v5);
    *(_QWORD *)(*((_QWORD *)a1 + 15) + 1616LL) += v5;
    goto LABEL_34;
  }
  if ( (bidGblFlags & 2) != 0 )
    bidTraceHR(0, 8314889, 2147942934LL, v20);
  v8 = -1;
  if ( (bidGblFlags & 2) != 0 )
  {
    bidTraceMark(0, 8315913);
    goto LABEL_34;
  }
  return v8;
}

```

## disassembly

```asm
0x1004af970  mov     [rsp+arg_0], rbx
0x1004af975  mov     [rsp+arg_10], rsi
0x1004af97a  mov     [rsp+arg_18], rdi
0x1004af97f  push    r12
0x1004af981  push    r14
0x1004af983  push    r15
0x1004af985  sub     rsp, 40h
0x1004af989  mov     r15, r9
0x1004af98c  mov     r14d, r8d
0x1004af98f  mov     rbx, rdx
0x1004af992  mov     rsi, rcx
0x1004af995  xor     edi, edi
0x1004af997  cmp     [rdx+40h], edi
0x1004af99a  jz      short loc_1004AF9DD
0x1004af99c  mov     rax, [rdx+38h]
0x1004af9a0  lea     rcx, [r14+rax]
0x1004af9a4  cmp     rcx, rax
0x1004af9a7  jb      short loc_1004AFA14
0x1004af9a9  cmp     rcx, [rdx+20h]
0x1004af9ad  ja      short loc_1004AFA14
0x1004af9af  lfence
0x1004af9b2  mov     r8, [rdx+10h]
0x1004af9b6  add     r8, [rdx+38h]; Source
0x1004af9ba  mov     r9d, r14d; SourceSize
0x1004af9bd  mov     edx, r14d; DestinationSize
0x1004af9c0  mov     rcx, r15; Destination
0x1004af9c3  call    cs:__imp_memcpy_s
0x1004af9c9  nop
0x1004af9ca  add     [rbx+38h], r14
0x1004af9ce  jmp     loc_1004AFC8B
0x1004af9d3  mov     edi, 64h ; 'd'
0x1004af9d8  jmp     loc_1004AFC8B
0x1004af9dd  mov     rax, [rcx+78h]
0x1004af9e1  mov     rdx, [rax+758h]; lpBuffer
0x1004af9e8  test    rdx, rdx
0x1004af9eb  jnz     short loc_1004AFA1E
0x1004af9ed  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x1004af9f2  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1004af9f7  mov     r8d, r14d; nNumberOfBytesToRead
0x1004af9fa  mov     rdx, r15; lpBuffer
0x1004af9fd  mov     rcx, [rbx]; hFile
0x1004afa00  call    cs:__imp_ReadFile
0x1004afa06  neg     eax
0x1004afa08  sbb     ecx, ecx
0x1004afa0a  and     ecx, dword ptr [rsp+58h+NumberOfBytesRead]
0x1004afa0e  jnz     loc_1004AFC8B
0x1004afa14  mov     edi, 64h ; 'd'
0x1004afa19  jmp     loc_1004AFC8B
0x1004afa1e  cmp     r14d, 3800h
0x1004afa25  jb      short loc_1004AFA92
0x1004afa27  mov     edx, [rax+650h]; lDistanceToMove
0x1004afa2d  mov     rax, [rax+650h]
0x1004afa34  shr     rax, 20h
0x1004afa38  mov     [rsp+58h+DistanceToMoveHigh], eax
0x1004afa3c  xor     r9d, r9d; dwMoveMethod
0x1004afa3f  lea     r8, [rsp+58h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1004afa44  mov     rcx, [rbx]; hFile
0x1004afa47  call    cs:__imp_SetFilePointer
0x1004afa4d  cmp     eax, 0FFFFFFFFh
0x1004afa50  jnz     short loc_1004AFA5C
0x1004afa52  call    cs:__imp_GetLastError
0x1004afa58  test    eax, eax
0x1004afa5a  jnz     short loc_1004AFA14
0x1004afa5c  lfence
0x1004afa5f  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x1004afa64  lea     r9, [rsp+58h+var_24]; lpNumberOfBytesRead
0x1004afa69  mov     r8d, r14d; nNumberOfBytesToRead
0x1004afa6c  mov     rdx, r15; lpBuffer
0x1004afa6f  mov     rcx, [rbx]; hFile
0x1004afa72  call    cs:__imp_ReadFile
0x1004afa78  neg     eax
0x1004afa7a  sbb     ecx, ecx
0x1004afa7c  and     ecx, [rsp+58h+var_24]
0x1004afa80  jz      short loc_1004AFA14
0x1004afa82  mov     rcx, [rsi+78h]
0x1004afa86  add     [rcx+650h], r14
0x1004afa8d  jmp     loc_1004AFC8B
0x1004afa92  or      r12, 0FFFFFFFFFFFFFFFFh
0x1004afa96  cmp     [rax+660h], r12
0x1004afa9d  jnz     short loc_1004AFAF7
0x1004afa9f  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x1004afaa4  lea     r9, [rsp+58h+var_20]; lpNumberOfBytesRead
0x1004afaa9  mov     r8d, 4000h; nNumberOfBytesToRead
0x1004afaaf  mov     rcx, [rbx]; hFile
0x1004afab2  call    cs:__imp_ReadFile
0x1004afab8  neg     eax
0x1004afaba  sbb     r8d, r8d
0x1004afabd  and     r8d, [rsp+58h+var_20]
0x1004afac2  jz      loc_1004AFA14
0x1004afac8  mov     rdx, [rsi+78h]
0x1004afacc  lea     eax, [r8-4000h]
0x1004afad3  neg     eax
0x1004afad5  sbb     ecx, ecx
0x1004afad7  and     ecx, 8
0x1004afada  mov     eax, [rdx+34h]
0x1004afadd  and     eax, 0FFFFFFF7h
0x1004afae0  or      ecx, eax
0x1004afae2  mov     [rdx+34h], ecx
0x1004afae5  lea     eax, [r8-1]
0x1004afae9  movsxd  rcx, eax
0x1004afaec  mov     rax, [rsi+78h]
0x1004afaf0  mov     [rax+660h], rcx
0x1004afaf7  mov     rcx, [rsi+78h]
0x1004afafb  lea     rdx, [rcx+650h]
0x1004afb02  lea     r8, [rcx+660h]
0x1004afb09  test    byte ptr [rcx+34h], 8
0x1004afb0d  jz      short loc_1004AFB1B
0x1004afb0f  mov     rax, [r8]
0x1004afb12  cmp     [rdx], rax
0x1004afb15  ja      loc_1004AFA14
0x1004afb1b  mov     r9, [rdx]
0x1004afb1e  cmp     r9, [rcx+658h]
0x1004afb25  jb      short loc_1004AFB36
0x1004afb27  movsxd  rax, r14d
0x1004afb2a  add     rax, r9
0x1004afb2d  cmp     rax, [r8]
0x1004afb30  jbe     loc_1004AFC02
0x1004afb36  lea     rax, [r9-800h]
0x1004afb3d  mov     r12, rdi
0x1004afb40  cmp     r9, 800h
0x1004afb47  cmovnb  r12, rax
0x1004afb4b  mov     rax, [rcx+758h]
0x1004afb52  mov     [rsp+58h+NumberOfBytesRead], rax
0x1004afb57  mov     [rcx+758h], rdi
0x1004afb5e  cmp     [rbx+40h], edi
0x1004afb61  jz      short loc_1004AFB69
0x1004afb63  mov     [rbx+38h], r12
0x1004afb67  jmp     short loc_1004AFB77
0x1004afb69  mov     r8, r12; unsigned __int64
0x1004afb6c  mov     rdx, rbx; struct BCPFILE *
0x1004afb6f  mov     rcx, rsi; struct tagDBC *
0x1004afb72  call    ?bcpSeek64@@YAFPEAUtagDBC@@PEAUBCPFILE@@_K@Z; bcpSeek64(tagDBC *,BCPFILE *,unsigned __int64)
0x1004afb77  mov     rax, [rsi+78h]
0x1004afb7b  mov     rcx, [rsp+58h+NumberOfBytesRead]
0x1004afb80  mov     [rax+758h], rcx
0x1004afb87  mov     rax, [rsi+78h]
0x1004afb8b  mov     [rsp+58h+lpOverlapped], rdi; lpOverlapped
0x1004afb90  lea     r9, [rsp+58h+var_1C]; lpNumberOfBytesRead
0x1004afb95  mov     r8d, 4000h; nNumberOfBytesToRead
0x1004afb9b  mov     rdx, [rax+758h]; lpBuffer
0x1004afba2  mov     rcx, [rbx]; hFile
0x1004afba5  call    cs:__imp_ReadFile
0x1004afbab  neg     eax
0x1004afbad  sbb     r8d, r8d
0x1004afbb0  and     r8d, [rsp+58h+var_1C]
0x1004afbb5  jz      loc_1004AFA14
0x1004afbbb  mov     rdx, [rsi+78h]
0x1004afbbf  lea     eax, [r8-4000h]
0x1004afbc6  neg     eax
0x1004afbc8  sbb     ecx, ecx
0x1004afbca  and     ecx, 8
0x1004afbcd  mov     eax, [rdx+34h]
0x1004afbd0  and     eax, 0FFFFFFF7h
0x1004afbd3  or      ecx, eax
0x1004afbd5  mov     [rdx+34h], ecx
0x1004afbd8  mov     rax, [rsi+78h]
0x1004afbdc  mov     [rax+658h], r12
0x1004afbe3  mov     rdx, [rsi+78h]
0x1004afbe7  mov     ecx, r8d
0x1004afbea  mov     rax, [rdx+658h]
0x1004afbf1  dec     rax
0x1004afbf4  add     rcx, rax
0x1004afbf7  mov     [rdx+660h], rcx
0x1004afbfe  or      r12, 0FFFFFFFFFFFFFFFFh
0x1004afc02  test    r15, r15
0x1004afc05  jz      loc_1004AFC8B
0x1004afc0b  mov     rcx, [rsi+78h]
0x1004afc0f  mov     rax, [rcx+658h]
0x1004afc16  cmp     [rcx+650h], rax
0x1004afc1d  jnb     short loc_1004AFC55
0x1004afc1f  test    byte ptr cs:_bidGblFlags, 2
0x1004afc26  jz      short loc_1004AFC3A
0x1004afc28  mov     edx, 7EE009h
0x1004afc2d  xor     ecx, ecx
0x1004afc2f  mov     r8d, 80070216h
0x1004afc35  call    _bidTraceHR
0x1004afc3a  movzx   edi, r12w
0x1004afc3e  test    byte ptr cs:_bidGblFlags, 2
0x1004afc45  jz      short loc_1004AFCA7
0x1004afc47  mov     edx, 7EE409h
0x1004afc4c  xor     ecx, ecx
0x1004afc4e  call    _bidTraceMark
0x1004afc53  jmp     short loc_1004AFC8B
0x1004afc55  lfence
0x1004afc58  mov     rax, [rsi+78h]
0x1004afc5c  mov     r8, [rax+758h]
0x1004afc63  sub     r8, [rax+658h]
0x1004afc6a  add     r8, [rax+650h]; Source
0x1004afc71  mov     r9, r14; SourceSize
0x1004afc74  mov     rdx, r14; DestinationSize
0x1004afc77  mov     rcx, r15; Destination
0x1004afc7a  call    cs:__imp_memcpy_s
0x1004afc80  mov     rax, [rsi+78h]
0x1004afc84  add     [rax+650h], r14
0x1004afc8b  test    byte ptr cs:_bidGblFlags, 2
0x1004afc92  jz      short loc_1004AFCA7
0x1004afc94  movzx   r8d, di; __int16
0x1004afc98  mov     edx, 7F1409h; unsigned __int64
0x1004afc9d  xor     ecx, ecx; unsigned __int64
0x1004afc9f  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x1004afca4  movzx   edi, ax
0x1004afca7  movzx   eax, di
0x1004afcaa  mov     rbx, [rsp+58h+arg_0]
0x1004afcaf  mov     rsi, [rsp+58h+arg_10]
0x1004afcb4  mov     rdi, [rsp+58h+arg_18]
0x1004afcb9  add     rsp, 40h
0x1004afcbd  pop     r15
0x1004afcbf  pop     r14
0x1004afcc1  pop     r12
0x1004afcc3  retn
```
