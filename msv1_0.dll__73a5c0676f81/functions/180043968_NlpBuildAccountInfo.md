# NlpBuildAccountInfo

- ea: `0x180043968`
- end: `0x180043e5d`
- name: `NlpBuildAccountInfo`
- size: `1269`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800428a8`
- `0x18004417c`
- `0x1800444e4`
- `0x1800448cc`

## callees

- `0x180030844`
- `0x180041744`
- `0x180043124`
- `0x180043968`
- `0x18006bd74`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043dbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043dbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043a87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180043a87`
- `ntdll!RtlLengthSid` at `0x180043c70`
- `ntdll!RtlLengthSid` at `0x180043c70`
- `ntdll!RtlCopySid` at `0x180043c80`
- `ntdll!RtlCopySid` at `0x180043cef`
- `ntdll!RtlCopySid` at `0x180043c80`
- `ntdll!RtlCopySid` at `0x180043cef`

## pseudocode

```c
__int64 __fastcall NlpBuildAccountInfo(unsigned __int16 *a1, _QWORD *a2)
{
  unsigned int v3; // r13d
  unsigned int v4; // edx
  unsigned int v5; // eax
  SIZE_T v6; // rbx
  char *v7; // rax
  char *v8; // r15
  __int64 v10; // rcx
  unsigned __int8 *v11; // rsi
  void *v12; // rbx
  unsigned __int8 *v13; // rcx
  size_t v14; // rdi
  unsigned __int16 v15; // cx
  __int64 v16; // rax
  _DWORD *v17; // r8
  unsigned __int64 v18; // rdx
  void *v19; // r12
  void *v20; // rsi
  __int64 v21; // r13
  ULONG v22; // eax
  __int64 v23; // rbx
  __int64 v24; // rbx
  unsigned __int16 v25; // r13
  int v26; // r8d
  int v27; // eax
  unsigned __int64 v28; // [rsp+20h] [rbp-28h]
  PWSTR Buffer; // [rsp+28h] [rbp-20h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-18h] BYREF
  __int16 v31; // [rsp+90h] [rbp+48h]
  __int64 v32; // [rsp+90h] [rbp+48h]
  void *Src; // [rsp+A0h] [rbp+58h] BYREF
  unsigned __int8 *v35; // [rsp+A8h] [rbp+60h] BYREF

  v3 = *((_DWORD *)a1 + 36);
  v31 = v3;
  if ( v3 )
  {
    Buffer = 0;
  }
  else
  {
    v3 = NlpComputerName.Length >> 1;
    v31 = v3;
    Buffer = NlpComputerName.Buffer;
  }
  v4 = 16 * *((_DWORD *)a1 + 11)
     + 8
     + ((a1[3] + 3) & 0xFFFFFFFC)
     + ((a1[7] + 3) & 0xFFFFFFFC)
     + ((a1[31] + 3) & 0xFFFFFFFC)
     + ((a1[4] + 3) & 0xFFFFFFFC)
     + ((a1[14] + 3) & 0xFFFFFFFC)
     + ((a1[5] + 3) & 0xFFFFFFFC)
     + ((a1[30] + 3) & 0xFFFFFFFC)
     + ((a1[2] + 3) & 0xFFFFFFFC)
     + ((a1[6] + 3) & 0xFFFFFFFC)
     + 8 * *((_DWORD *)a1 + 6)
     + ((*((_DWORD *)a1 + 13) + 3) & 0xFFFFFFFC);
  if ( v4 > 0xFA00 )
    return 3221225485LL;
  if ( v3 > 0x100 )
    return 3221225485LL;
  v5 = a1[15];
  if ( v5 > 0x44 )
    return 3221225485LL;
  v6 = v4 + 480 + v5 + 2 * v3;
  v7 = (char *)LocalAlloc(0x40u, v6);
  v8 = v7;
  if ( !v7 )
    return 3221225495LL;
  memset_0(v7, 0, v6);
  v10 = *a1;
  v35 = (unsigned __int8 *)(v8 + 480);
  Src = (char *)a1 + ((a1[1] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + ((v10 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 168;
  NlpCopyAndUpdateAccountInfo(a1[30], (struct _UNICODE_STRING *)v8 + 18, (unsigned __int8 **)&Src, &v35);
  NlpCopyAndUpdateAccountInfo(a1[31], (struct _UNICODE_STRING *)v8 + 19, (unsigned __int8 **)&Src, &v35);
  NlpCopyAndUpdateAccountInfo(a1[2], (struct _UNICODE_STRING *)v8 + 3, (unsigned __int8 **)&Src, &v35);
  NlpCopyAndUpdateAccountInfo(a1[3], (struct _UNICODE_STRING *)v8 + 4, (unsigned __int8 **)&Src, &v35);
  NlpCopyAndUpdateAccountInfo(a1[4], (struct _UNICODE_STRING *)v8 + 5, (unsigned __int8 **)&Src, &v35);
  NlpCopyAndUpdateAccountInfo(a1[5], (struct _UNICODE_STRING *)v8 + 6, (unsigned __int8 **)&Src, &v35);
  NlpCopyAndUpdateAccountInfo(a1[6], (struct _UNICODE_STRING *)v8 + 7, (unsigned __int8 **)&Src, &v35);
  NlpCopyAndUpdateAccountInfo(a1[7], (struct _UNICODE_STRING *)v8 + 8, (unsigned __int8 **)&Src, &v35);
  v11 = v35;
  v12 = Src;
  v13 = v35;
  *((_QWORD *)v8 + 20) = v35;
  v14 = (unsigned int)(8 * *((_DWORD *)a1 + 6));
  memcpy_0(v13, v12, v14);
  v15 = a1[14];
  v35 = (unsigned __int8 *)((unsigned __int64)&v11[v14 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
  Src = (void *)(((unsigned __int64)v12 + v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
  NlpCopyAndUpdateAccountInfo(v15, (struct _UNICODE_STRING *)v8 + 13, (unsigned __int8 **)&Src, &v35);
  *((_DWORD *)v8 + 68) = *((_DWORD *)a1 + 11);
  if ( *((_DWORD *)a1 + 11) )
  {
    v16 = *((unsigned int *)a1 + 11);
    v17 = Src;
    v18 = (unsigned __int64)(v35 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    *((_QWORD *)v8 + 35) = v18;
    v19 = (void *)(v18 + 16LL * *((unsigned int *)a1 + 11));
    v20 = (void *)(((unsigned __int64)&v17[v16] + 3) & 0xFFFFFFFFFFFFFFFCuLL);
    if ( *((_DWORD *)a1 + 11) )
    {
      v21 = 0;
      v35 = (unsigned __int8 *)(v18 + 16LL * *((unsigned int *)a1 + 11));
      v28 = ((unsigned __int64)&v17[v16] + 3) & 0xFFFFFFFFFFFFFFFCuLL;
      do
      {
        *(_DWORD *)(*((_QWORD *)v8 + 35) + 16LL * (unsigned int)v21 + 8) = v17[v21];
        v22 = RtlLengthSid(v20);
        v23 = v22;
        RtlCopySid(v22, v19, v20);
        v17 = Src;
        v20 = (void *)((v23 + v28 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
        v28 = (unsigned __int64)v20;
        *(_QWORD *)(*((_QWORD *)v8 + 35) + 16LL * (unsigned int)v21) = v19;
        v21 = (unsigned int)(v21 + 1);
        v19 = (void *)((unsigned __int64)&v35[v23 + 3] & 0xFFFFFFFFFFFFFFFCuLL);
        v35 = (unsigned __int8 *)v19;
      }
      while ( (unsigned int)v21 < *((_DWORD *)a1 + 11) );
      LOWORD(v3) = v31;
    }
  }
  else
  {
    v20 = Src;
    v19 = v35;
    *((_QWORD *)v8 + 35) = 0;
  }
  v24 = a1[15];
  RtlCopySid(a1[15], v19, v20);
  *((_QWORD *)v8 + 28) = v19;
  v35 = (unsigned __int8 *)(((unsigned __int64)v19 + v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
  Src = (void *)(((unsigned __int64)v20 + v24 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
  if ( Buffer )
  {
    Src = Buffer;
    v25 = 2 * v3;
  }
  else
  {
    v25 = a1[72];
  }
  NlpCopyAndUpdateAccountInfo(v25, (struct _UNICODE_STRING *)v8 + 12, (unsigned __int8 **)&Src, &v35);
  *((_DWORD *)v8 + 37) = *((_DWORD *)a1 + 4);
  *((_DWORD *)v8 + 38) = *((_DWORD *)a1 + 5);
  *((_DWORD *)v8 + 39) = *((_DWORD *)a1 + 6);
  NlpSetTimeField(v8, 2);
  NlpSetTimeField(v8 + 8, 1);
  NlpSetTimeField(v8 + 16, 1);
  NlpSetTimeField(v8 + 24, 0);
  NlpSetTimeField(v8 + 32, 1);
  NlpSetTimeField(v8 + 40, 1);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v26 = 32;
  v32 = *(_QWORD *)(a1 + 74);
  if ( v32 && v32 <= *(_QWORD *)&SystemTimeAsFileTime + 6000000000LL )
    *((_DWORD *)a1 + 35) |= 0x20u;
  *((_DWORD *)v8 + 42) = 32;
  *((_DWORD *)v8 + 36) = 0;
  if ( (a1[70] & 0x20) != 0 )
  {
    v26 = 131104;
    *((_DWORD *)v8 + 42) = 131104;
  }
  v27 = *((_DWORD *)a1 + 14);
  if ( v27 )
    *((_DWORD *)v8 + 42) = v26 | (v27 << 24);
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x180043968  mov     [rsp-40h+arg_8], rdx
0x18004396d  push    rbp
0x18004396e  push    rbx
0x18004396f  push    rsi
0x180043970  push    rdi
0x180043971  push    r12
0x180043973  push    r13
0x180043975  push    r14
0x180043977  push    r15
0x180043979  mov     rbp, rsp
0x18004397c  sub     rsp, 48h
0x180043980  movzx   r8d, word ptr [rcx+0Ch]
0x180043985  mov     r14, rcx
0x180043988  mov     edi, 3
0x18004398d  mov     ecx, 0FFFFFFFCh
0x180043992  add     r8d, edi
0x180043995  and     r8d, ecx
0x180043998  movzx   eax, word ptr [r14+4]
0x18004399d  mov     r13d, [r14+90h]
0x1800439a4  add     eax, edi
0x1800439a6  and     eax, ecx
0x1800439a8  mov     dword ptr [rbp+arg_0], r13d
0x1800439ac  add     r8d, eax
0x1800439af  movzx   eax, word ptr [r14+3Ch]
0x1800439b4  add     eax, edi
0x1800439b6  and     eax, ecx
0x1800439b8  add     r8d, eax
0x1800439bb  movzx   eax, word ptr [r14+0Ah]
0x1800439c0  add     eax, edi
0x1800439c2  and     eax, ecx
0x1800439c4  add     r8d, eax
0x1800439c7  movzx   eax, word ptr [r14+1Ch]
0x1800439cc  add     eax, edi
0x1800439ce  and     eax, ecx
0x1800439d0  add     r8d, eax
0x1800439d3  movzx   eax, word ptr [r14+8]
0x1800439d8  add     eax, edi
0x1800439da  and     eax, ecx
0x1800439dc  add     r8d, eax
0x1800439df  movzx   eax, word ptr [r14+3Eh]
0x1800439e4  add     eax, edi
0x1800439e6  and     eax, ecx
0x1800439e8  add     r8d, eax
0x1800439eb  movzx   eax, word ptr [r14+0Eh]
0x1800439f0  add     eax, edi
0x1800439f2  and     eax, ecx
0x1800439f4  add     r8d, eax
0x1800439f7  movzx   eax, word ptr [r14+6]
0x1800439fc  add     eax, edi
0x1800439fe  and     eax, ecx
0x180043a00  add     r8d, eax
0x180043a03  mov     eax, [r14+18h]
0x180043a07  lea     r9d, [r8+rax*8]
0x180043a0b  test    r13d, r13d
0x180043a0e  jnz     short loc_180043A2C
0x180043a10  movzx   r13d, cs:NlpComputerName.Length
0x180043a18  mov     rdx, cs:NlpComputerName.Buffer
0x180043a1f  shr     r13d, 1
0x180043a22  mov     dword ptr [rbp+arg_0], r13d
0x180043a26  mov     [rbp+var_20], rdx
0x180043a2a  jmp     short loc_180043A34
0x180043a2c  mov     [rbp+var_20], 0
0x180043a34  mov     edx, [r14+34h]
0x180043a38  add     edx, edi
0x180043a3a  and     edx, ecx
0x180043a3c  mov     ecx, [r14+2Ch]
0x180043a40  shl     ecx, 4
0x180043a43  add     edx, r9d
0x180043a46  add     ecx, 8
0x180043a49  add     edx, ecx
0x180043a4b  cmp     edx, 0FA00h
0x180043a51  ja      loc_180043E47
0x180043a57  cmp     r13d, 100h
0x180043a5e  ja      loc_180043E47
0x180043a64  movzx   eax, word ptr [r14+1Eh]
0x180043a69  cmp     eax, 44h ; 'D'
0x180043a6c  ja      loc_180043E47
0x180043a72  add     edx, 1E0h
0x180043a78  lea     eax, [rax+r13*2]
0x180043a7c  add     eax, edx
0x180043a7e  mov     ecx, 40h ; '@'; uFlags
0x180043a83  mov     edx, eax; uBytes
0x180043a85  mov     ebx, eax
0x180043a87  call    cs:__imp_LocalAlloc
0x180043a8d  mov     r15, rax
0x180043a90  test    rax, rax
0x180043a93  jnz     short loc_180043A9F
0x180043a95  mov     eax, 0C0000017h
0x180043a9a  jmp     loc_180043E4C
0x180043a9f  mov     r8, rbx; Size
0x180043aa2  xor     edx, edx; Val
0x180043aa4  mov     rcx, r15; void *
0x180043aa7  call    memset_0
0x180043aac  movzx   ecx, word ptr [r14]
0x180043ab0  lea     rax, [r15+1E0h]
0x180043ab7  mov     [rbp+arg_18], rax
0x180043abb  lea     rdx, [r15+120h]; struct _UNICODE_STRING *
0x180043ac2  movzx   eax, word ptr [r14+2]
0x180043ac7  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043acb  add     rcx, rdi
0x180043ace  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043ad2  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180043ad6  add     rax, rdi
0x180043ad9  add     rcx, 0A8h
0x180043ae0  and     rax, 0FFFFFFFFFFFFFFFCh
0x180043ae4  add     rax, r14
0x180043ae7  add     rcx, rax
0x180043aea  mov     [rbp+Src], rcx
0x180043aee  movzx   ecx, word ptr [r14+3Ch]; unsigned __int16
0x180043af3  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043af8  movzx   ecx, word ptr [r14+3Eh]; unsigned __int16
0x180043afd  lea     rdx, [r15+130h]; struct _UNICODE_STRING *
0x180043b04  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043b08  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043b0c  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043b11  movzx   ecx, word ptr [r14+4]; unsigned __int16
0x180043b16  lea     rdx, [r15+30h]; struct _UNICODE_STRING *
0x180043b1a  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043b1e  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043b22  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043b27  movzx   ecx, word ptr [r14+6]; unsigned __int16
0x180043b2c  lea     rdx, [r15+40h]; struct _UNICODE_STRING *
0x180043b30  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043b34  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043b38  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043b3d  movzx   ecx, word ptr [r14+8]; unsigned __int16
0x180043b42  lea     rdx, [r15+50h]; struct _UNICODE_STRING *
0x180043b46  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043b4a  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043b4e  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043b53  movzx   ecx, word ptr [r14+0Ah]; unsigned __int16
0x180043b58  lea     rdx, [r15+60h]; struct _UNICODE_STRING *
0x180043b5c  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043b60  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043b64  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043b69  movzx   ecx, word ptr [r14+0Ch]; unsigned __int16
0x180043b6e  lea     rdx, [r15+70h]; struct _UNICODE_STRING *
0x180043b72  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043b76  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043b7a  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043b7f  movzx   ecx, word ptr [r14+0Eh]; unsigned __int16
0x180043b84  lea     rdx, [r15+80h]; struct _UNICODE_STRING *
0x180043b8b  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043b8f  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043b93  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043b98  mov     rsi, [rbp+arg_18]
0x180043b9c  mov     rbx, [rbp+Src]
0x180043ba0  mov     rcx, rsi; void *
0x180043ba3  mov     [r15+0A0h], rsi
0x180043baa  mov     rdx, rbx; Src
0x180043bad  mov     eax, [r14+18h]
0x180043bb1  shl     eax, 3
0x180043bb4  mov     r8d, eax; Size
0x180043bb7  mov     edi, eax
0x180043bb9  call    memcpy_0
0x180043bbe  movzx   ecx, word ptr [r14+1Ch]; unsigned __int16
0x180043bc3  lea     rax, [rsi+3]
0x180043bc7  add     rax, rdi
0x180043bca  lea     rdx, [r15+0D0h]; struct _UNICODE_STRING *
0x180043bd1  and     rax, 0FFFFFFFFFFFFFFFCh
0x180043bd5  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043bd9  mov     [rbp+arg_18], rax
0x180043bdd  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043be1  lea     rax, [rbx+3]
0x180043be5  add     rax, rdi
0x180043be8  and     rax, 0FFFFFFFFFFFFFFFCh
0x180043bec  mov     [rbp+Src], rax
0x180043bf0  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043bf5  mov     eax, [r14+2Ch]
0x180043bf9  mov     [r15+110h], eax
0x180043c00  cmp     dword ptr [r14+2Ch], 0
0x180043c05  mov     edi, 1
0x180043c0a  jz      loc_180043CCF
0x180043c10  mov     eax, [r14+2Ch]
0x180043c14  mov     rdx, [rbp+arg_18]
0x180043c18  mov     r8, [rbp+Src]
0x180043c1c  add     rdx, 7
0x180043c20  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180043c24  mov     [r15+118h], rdx
0x180043c2b  mov     ecx, [r14+2Ch]
0x180043c2f  mov     r12d, ecx
0x180043c32  lea     rsi, [r8+3]
0x180043c36  shl     r12, 4
0x180043c3a  lea     rsi, [rsi+rax*4]
0x180043c3e  add     r12, rdx
0x180043c41  and     rsi, 0FFFFFFFFFFFFFFFCh
0x180043c45  test    ecx, ecx
0x180043c47  jz      loc_180043CE2
0x180043c4d  xor     r13d, r13d
0x180043c50  mov     [rbp+arg_18], r12
0x180043c54  mov     [rbp+var_28], rsi
0x180043c58  mov     rcx, [r15+118h]
0x180043c5f  mov     eax, [r8+r13*4]
0x180043c63  mov     edi, r13d
0x180043c66  add     rdi, rdi
0x180043c69  mov     [rcx+rdi*8+8], eax
0x180043c6d  mov     rcx, rsi; Sid
0x180043c70  call    cs:__imp_RtlLengthSid
0x180043c76  mov     r8, rsi; SourceSid
0x180043c79  mov     rdx, r12; DestinationSid
0x180043c7c  mov     ecx, eax; DestinationSidLength
0x180043c7e  mov     ebx, eax
0x180043c80  call    cs:__imp_RtlCopySid
0x180043c86  mov     rsi, [rbp+var_28]
0x180043c8a  mov     rcx, [r15+118h]
0x180043c91  add     rsi, 3
0x180043c95  mov     r8, [rbp+Src]
0x180043c99  add     rsi, rbx
0x180043c9c  and     rsi, 0FFFFFFFFFFFFFFFCh
0x180043ca0  mov     [rbp+var_28], rsi
0x180043ca4  mov     [rcx+rdi*8], r12
0x180043ca8  mov     edi, 1
0x180043cad  mov     r12, [rbp+arg_18]
0x180043cb1  add     r13d, edi
0x180043cb4  add     r12, 3
0x180043cb8  add     r12, rbx
0x180043cbb  and     r12, 0FFFFFFFFFFFFFFFCh
0x180043cbf  mov     [rbp+arg_18], r12
0x180043cc3  cmp     r13d, [r14+2Ch]
0x180043cc7  jb      short loc_180043C58
0x180043cc9  mov     r13d, dword ptr [rbp+arg_0]
0x180043ccd  jmp     short loc_180043CE2
0x180043ccf  mov     rsi, [rbp+Src]
0x180043cd3  mov     r12, [rbp+arg_18]
0x180043cd7  mov     qword ptr [r15+118h], 0
0x180043ce2  movzx   ebx, word ptr [r14+1Eh]
0x180043ce7  mov     r8, rsi; SourceSid
0x180043cea  mov     ecx, ebx; DestinationSidLength
0x180043cec  mov     rdx, r12; DestinationSid
0x180043cef  call    cs:__imp_RtlCopySid
0x180043cf5  lea     rax, [rbx+3]
0x180043cf9  mov     [r15+0E0h], r12
0x180043d00  add     rax, r12
0x180043d03  lea     rdx, [r15+0C0h]; struct _UNICODE_STRING *
0x180043d0a  and     rax, 0FFFFFFFFFFFFFFFCh
0x180043d0e  mov     [rbp+arg_18], rax
0x180043d12  lea     rax, [rbx+3]
0x180043d16  add     rax, rsi
0x180043d19  and     rax, 0FFFFFFFFFFFFFFFCh
0x180043d1d  mov     [rbp+Src], rax
0x180043d21  mov     rax, [rbp+var_20]
0x180043d25  test    rax, rax
0x180043d28  jz      short loc_180043D34
0x180043d2a  mov     [rbp+Src], rax
0x180043d2e  add     r13w, r13w
0x180043d32  jmp     short loc_180043D3C
0x180043d34  movzx   r13d, word ptr [r14+90h]
0x180043d3c  lea     r9, [rbp+arg_18]; unsigned __int8 **
0x180043d40  movzx   ecx, r13w; unsigned __int16
0x180043d44  lea     r8, [rbp+Src]; unsigned __int8 **
0x180043d48  call    ?NlpCopyAndUpdateAccountInfo@@YAXGPEAU_UNICODE_STRING@@PEAPEAE1@Z; NlpCopyAndUpdateAccountInfo(ushort,_UNICODE_STRING *,uchar * *,uchar * *)
0x180043d4d  mov     eax, [r14+10h]
0x180043d51  mov     edx, 2
0x180043d56  mov     [r15+94h], eax
0x180043d5d  mov     rcx, r15
0x180043d60  mov     eax, [r14+14h]
0x180043d64  mov     [r15+98h], eax
0x180043d6b  mov     eax, [r14+18h]
0x180043d6f  mov     [r15+9Ch], eax
0x180043d76  call    ?NlpSetTimeField@@YAXPEAU_OLD_LARGE_INTEGER@@W4_NLP_SET_TIME_HINT@@@Z; NlpSetTimeField(_OLD_LARGE_INTEGER *,_NLP_SET_TIME_HINT)
0x180043d7b  lea     rcx, [r15+8]
0x180043d7f  mov     edx, edi
0x180043d81  call    ?NlpSetTimeField@@YAXPEAU_OLD_LARGE_INTEGER@@W4_NLP_SET_TIME_HINT@@@Z; NlpSetTimeField(_OLD_LARGE_INTEGER *,_NLP_SET_TIME_HINT)
0x180043d86  lea     rcx, [r15+10h]
0x180043d8a  mov     edx, edi
0x180043d8c  call    ?NlpSetTimeField@@YAXPEAU_OLD_LARGE_INTEGER@@W4_NLP_SET_TIME_HINT@@@Z; NlpSetTimeField(_OLD_LARGE_INTEGER *,_NLP_SET_TIME_HINT)
0x180043d91  lea     rcx, [r15+18h]
0x180043d95  xor     edx, edx
0x180043d97  call    ?NlpSetTimeField@@YAXPEAU_OLD_LARGE_INTEGER@@W4_NLP_SET_TIME_HINT@@@Z; NlpSetTimeField(_OLD_LARGE_INTEGER *,_NLP_SET_TIME_HINT)
0x180043d9c  lea     rcx, [r15+20h]
0x180043da0  mov     edx, edi
0x180043da2  call    ?NlpSetTimeField@@YAXPEAU_OLD_LARGE_INTEGER@@W4_NLP_SET_TIME_HINT@@@Z; NlpSetTimeField(_OLD_LARGE_INTEGER *,_NLP_SET_TIME_HINT)
0x180043da7  lea     rcx, [r15+28h]
0x180043dab  mov     edx, edi
0x180043dad  call    ?NlpSetTimeField@@YAXPEAU_OLD_LARGE_INTEGER@@W4_NLP_SET_TIME_HINT@@@Z; NlpSetTimeField(_OLD_LARGE_INTEGER *,_NLP_SET_TIME_HINT)
0x180043db2  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180043db6  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180043dbe  call    cs:__imp_GetSystemTimeAsFileTime
0x180043dc4  mov     eax, [r14+94h]
0x180043dcb  mov     r8d, 20h ; ' '
0x180043dd1  mov     dword ptr [rbp+arg_0], eax
0x180043dd4  mov     eax, [r14+98h]
0x180043ddb  mov     dword ptr [rbp+arg_0+4], eax
0x180043dde  mov     rax, [rbp+arg_0]
0x180043de2  test    rax, rax
0x180043de5  jz      short loc_180043E01
0x180043de7  mov     rdx, 165A0BC00h
0x180043df1  add     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180043df5  cmp     rax, rdx
0x180043df8  jg      short loc_180043E01
0x180043dfa  or      [r14+8Ch], r8d
0x180043e01  xor     eax, eax
0x180043e03  mov     [r15+0A8h], r8d
0x180043e0a  mov     [r15+90h], eax
0x180043e11  test    [r14+8Ch], r8b
0x180043e18  jz      short loc_180043E27
0x180043e1a  mov     r8d, 20020h
0x180043e20  mov     [r15+0A8h], r8d
0x180043e27  mov     eax, [r14+38h]
0x180043e2b  test    eax, eax
  ... truncated ...
```
