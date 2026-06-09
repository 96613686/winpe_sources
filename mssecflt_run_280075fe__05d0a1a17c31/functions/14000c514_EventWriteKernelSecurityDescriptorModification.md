# EventWriteKernelSecurityDescriptorModification

- ea: `0x14000c514`
- end: `0x14000c944`
- name: `EventWriteKernelSecurityDescriptorModification`
- size: `1072`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a4f0`

## callees

- `0x140008714`
- `0x14000876c`
- `0x140009b80`
- `0x14000c514`
- `0x14000c944`
- `0x14001008c`
- `0x140011650`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000c89c`
- `ntoskrnl!EtwWrite` at `0x14000c89c`

## pseudocode

```c
__int64 EventWriteKernelSecurityDescriptorModification(__int64 a1, int a2, ...)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  PSLIST_ENTRY EtwDescriptorBuffer; // rax
  struct _SLIST_ENTRY *v5; // r12
  PSLIST_ENTRY v6; // rbx
  struct _SLIST_ENTRY *v8; // rdi
  wchar_t *v9; // r14
  int v10; // r13d
  int v11; // ecx
  const WCHAR *v12; // rax
  WCHAR *v13; // rsi
  int v14; // ecx
  __int64 v15; // rcx
  const WCHAR *v16; // rax
  struct _SLIST_ENTRY *v17; // r15
  WCHAR *v18; // rdi
  bool v19; // zf
  int v20; // eax
  const WCHAR *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // r13d
  PVOID P; // [rsp+38h] [rbp-71h] BYREF
  struct _SLIST_ENTRY *v25; // [rsp+40h] [rbp-69h] BYREF
  struct _SLIST_ENTRY *v26; // [rsp+48h] [rbp-61h] BYREF
  __int64 v27; // [rsp+50h] [rbp-59h]
  wchar_t *Str[2]; // [rsp+58h] [rbp-51h] BYREF
  PVOID v29[2]; // [rsp+68h] [rbp-41h] BYREF
  PVOID v30[2]; // [rsp+78h] [rbp-31h] BYREF
  int v31; // [rsp+88h] [rbp-21h] BYREF
  int v32; // [rsp+8Ch] [rbp-1Dh] BYREF
  unsigned int v33; // [rsp+90h] [rbp-19h] BYREF
  BOOL v34; // [rsp+94h] [rbp-15h] BYREF
  BOOL v35; // [rsp+98h] [rbp-11h] BYREF
  BOOL v36; // [rsp+9Ch] [rbp-Dh] BYREF
  __int64 v37; // [rsp+F8h] [rbp+4Fh] BYREF
  int v38; // [rsp+100h] [rbp+57h] BYREF
  __int64 v39; // [rsp+108h] [rbp+5Fh] BYREF
  va_list va; // [rsp+108h] [rbp+5Fh]
  __int64 v41; // [rsp+110h] [rbp+67h] BYREF
  va_list va1; // [rsp+110h] [rbp+67h]
  __int64 v43; // [rsp+118h] [rbp+6Fh] BYREF
  va_list va2; // [rsp+118h] [rbp+6Fh]
  __int64 v45; // [rsp+120h] [rbp+77h]
  __int64 v46; // [rsp+128h] [rbp+7Fh]
  __int64 v47; // [rsp+130h] [rbp+87h]
  va_list va3; // [rsp+138h] [rbp+8Fh] BYREF

  va_start(va3, a2);
  va_start(va2, a2);
  va_start(va1, a2);
  va_start(va, a2);
  v39 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v41 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v43 = va_arg(va3, _QWORD);
  v45 = va_arg(va3, _QWORD);
  v46 = va_arg(va3, _QWORD);
  v47 = va_arg(va3, _QWORD);
  v38 = a2;
  v37 = a1;
  v2 = v45;
  v3 = v46;
  v27 = v47;
  EtwDescriptorBuffer = SecGetEtwDescriptorBuffer(0x17u);
  v5 = 0;
  P = 0;
  v6 = EtwDescriptorBuffer;
  v31 = 0;
  v25 = 0;
  v32 = 0;
  v26 = 0;
  v33 = 0;
  *(_OWORD *)Str = 0;
  *(_OWORD *)v29 = 0;
  *(_OWORD *)v30 = 0;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  *((_QWORD *)&EtwDescriptorBuffer->Next + 1) = 8;
  EtwDescriptorBuffer->Next = (struct _SLIST_ENTRY *)&v37;
  *((_QWORD *)&EtwDescriptorBuffer[1].Next + 1) = 4;
  EtwDescriptorBuffer[1].Next = (struct _SLIST_ENTRY *)&v38;
  *((_QWORD *)&EtwDescriptorBuffer[2].Next + 1) = 8;
  EtwDescriptorBuffer[2].Next = (struct _SLIST_ENTRY *)va;
  *((_QWORD *)&EtwDescriptorBuffer[3].Next + 1) = 8;
  EtwDescriptorBuffer[3].Next = (struct _SLIST_ENTRY *)va1;
  *((_QWORD *)&EtwDescriptorBuffer[4].Next + 1) = 4;
  EtwDescriptorBuffer[4].Next = (struct _SLIST_ENTRY *)va2;
  v34 = *(_QWORD *)(v2 + 16) != 0;
  EtwDescriptorBuffer[6].Next = (struct _SLIST_ENTRY *)&v34;
  EtwDescriptorBuffer[7].Next = (struct _SLIST_ENTRY *)(v2 + 8);
  EtwDescriptorBuffer[5].Next = (struct _SLIST_ENTRY *)v2;
  *((_QWORD *)&EtwDescriptorBuffer[5].Next + 1) = 8;
  *((_QWORD *)&EtwDescriptorBuffer[6].Next + 1) = 4;
  *((_QWORD *)&EtwDescriptorBuffer[7].Next + 1) = 4;
  if ( (int)PrepareAceDataForEvent(v2, &P, &v31, (__int64)Str) >= 0 )
  {
    v8 = (struct _SLIST_ENTRY *)P;
  }
  else
  {
    v8 = 0;
    P = 0;
    v31 = 0;
  }
  v9 = Str[1];
  v10 = 2;
  if ( Str[1] )
    v11 = 2 * wcslen_0(Str[1]) + 2;
  else
    v11 = 2;
  *((_DWORD *)&v6[8].Next + 2) = v11;
  *((_DWORD *)&v6[8].Next + 3) = 0;
  *((_QWORD *)&v6[9].Next + 1) = 4;
  v12 = &SourceString;
  if ( v9 )
    v12 = v9;
  v6[8].Next = (struct _SLIST_ENTRY *)v12;
  v6[9].Next = (struct _SLIST_ENTRY *)&v31;
  *((_DWORD *)&v6[10].Next + 2) = v31;
  v6[10].Next = v8;
  *((_DWORD *)&v6[10].Next + 3) = 0;
  v35 = *(_QWORD *)(v3 + 16) != 0;
  v6[12].Next = (struct _SLIST_ENTRY *)&v35;
  v6[13].Next = (struct _SLIST_ENTRY *)(v3 + 8);
  v6[11].Next = (struct _SLIST_ENTRY *)v3;
  *((_QWORD *)&v6[11].Next + 1) = 8;
  *((_QWORD *)&v6[12].Next + 1) = 4;
  *((_QWORD *)&v6[13].Next + 1) = 4;
  if ( (int)PrepareAceDataForEvent(v3, (PVOID *)&v25, &v32, (__int64)v29) >= 0 )
    v5 = v25;
  else
    v32 = 0;
  v13 = (WCHAR *)v29[1];
  if ( v29[1] )
    v14 = 2 * wcslen_0((const wchar_t *)v29[1]) + 2;
  else
    v14 = 2;
  *((_DWORD *)&v6[14].Next + 2) = v14;
  v15 = v27;
  *((_DWORD *)&v6[14].Next + 3) = 0;
  *((_QWORD *)&v6[15].Next + 1) = 4;
  v16 = &SourceString;
  if ( v13 )
    v16 = v13;
  v6[14].Next = (struct _SLIST_ENTRY *)v16;
  v6[15].Next = (struct _SLIST_ENTRY *)&v32;
  *((_DWORD *)&v6[16].Next + 2) = v32;
  v6[16].Next = v5;
  *((_DWORD *)&v6[16].Next + 3) = 0;
  v36 = *(_QWORD *)(v15 + 16) != 0;
  v6[18].Next = (struct _SLIST_ENTRY *)&v36;
  v6[19].Next = (struct _SLIST_ENTRY *)(v15 + 8);
  v6[17].Next = (struct _SLIST_ENTRY *)v15;
  *((_QWORD *)&v6[17].Next + 1) = 8;
  *((_QWORD *)&v6[18].Next + 1) = 4;
  *((_QWORD *)&v6[19].Next + 1) = 4;
  if ( (int)PrepareAceDataForEvent(v15, (PVOID *)&v26, &v33, (__int64)v30) >= 0 )
  {
    v17 = v26;
  }
  else
  {
    v17 = 0;
    v33 = 0;
  }
  v18 = (WCHAR *)v30[1];
  v19 = v30[1] == 0;
  if ( v30[1] )
  {
    v20 = wcslen_0((const wchar_t *)v30[1]);
    v19 = v18 == 0;
    v10 = 2 * v20 + 2;
  }
  *((_DWORD *)&v6[20].Next + 2) = v10;
  v21 = &SourceString;
  if ( !v19 )
    v21 = v18;
  *((_DWORD *)&v6[20].Next + 3) = 0;
  v6[20].Next = (struct _SLIST_ENTRY *)v21;
  *((_QWORD *)&v6[21].Next + 1) = 4;
  v6[21].Next = (struct _SLIST_ENTRY *)&v33;
  v22 = v33;
  v6[22].Next = v17;
  *((_QWORD *)&v6[22].Next + 1) = v22;
  v23 = EtwWrite(Microsoft_Windows_SECHandle, &Event27, 0, 0x17u, (PEVENT_DATA_DESCRIPTOR)v6);
  if ( P )
    SecFreePool(P, 0x64446353u);
  if ( v9 )
    SecFreePool(v9, 0x74736353u);
  if ( v5 )
    SecFreePool(v5, 0x64446353u);
  if ( v13 )
    SecFreePool(v13, 0x74736353u);
  if ( v17 )
    SecFreePool(v17, 0x64446353u);
  if ( v18 )
    SecFreePool(v18, 0x74736353u);
  SecReleaseEtwDescriptorBuffer(v6);
  return v23;
}

```

## disassembly

```asm
0x14000c514  mov     rax, rsp
0x14000c517  mov     [rax+20h], r9
0x14000c51b  mov     [rax+18h], r8
0x14000c51f  mov     [rax+10h], edx
0x14000c522  mov     [rax+8], rcx
0x14000c526  push    rbp
0x14000c527  push    rbx
0x14000c528  push    rsi
0x14000c529  push    rdi
0x14000c52a  push    r12
0x14000c52c  push    r13
0x14000c52e  push    r14
0x14000c530  push    r15
0x14000c532  lea     rbp, [rax-47h]
0x14000c536  sub     rsp, 0A8h
0x14000c53d  mov     rax, cs:__security_cookie
0x14000c544  xor     rax, rsp
0x14000c547  mov     [rbp+3Fh+var_48], rax
0x14000c54b  mov     rax, [rbp+3Fh+arg_38]
0x14000c552  mov     ecx, 17h
0x14000c557  mov     rdi, [rbp+3Fh+arg_28]
0x14000c55b  mov     rsi, [rbp+3Fh+arg_30]
0x14000c55f  mov     [rbp+3Fh+var_98], rax
0x14000c563  call    SecGetEtwDescriptorBuffer
0x14000c568  xor     r12d, r12d
0x14000c56b  xorps   xmm0, xmm0
0x14000c56e  mov     [rbp+3Fh+P], r12
0x14000c572  mov     rbx, rax
0x14000c575  mov     [rbp+3Fh+var_60], r12d
0x14000c579  mov     [rbp+3Fh+var_A8], r12
0x14000c57d  mov     [rbp+3Fh+var_5C], r12d
0x14000c581  mov     [rbp+3Fh+var_A0], r12
0x14000c585  mov     [rbp+3Fh+var_58], r12d
0x14000c589  movups  xmmword ptr [rbp+3Fh+Str], xmm0
0x14000c58d  movups  xmmword ptr [rbp+3Fh+var_80], xmm0
0x14000c591  movups  xmmword ptr [rbp+3Fh+var_70], xmm0
0x14000c595  test    rax, rax
0x14000c598  jnz     short loc_14000C5A4
0x14000c59a  mov     eax, 0C000009Ah
0x14000c59f  jmp     loc_14000C923
0x14000c5a4  mov     qword ptr [rbx+8], 8
0x14000c5ac  lea     rax, [rbp+3Fh+arg_0]
0x14000c5b0  mov     [rbx], rax
0x14000c5b3  lea     r9, [rbp+3Fh+Str]
0x14000c5b7  mov     qword ptr [rbx+18h], 4
0x14000c5bf  lea     rax, [rbp+3Fh+arg_8]
0x14000c5c3  mov     [rbx+10h], rax
0x14000c5c7  lea     r8, [rbp+3Fh+var_60]
0x14000c5cb  mov     qword ptr [rbx+28h], 8
0x14000c5d3  lea     rax, [rbp+3Fh+arg_10]
0x14000c5d7  mov     [rbx+20h], rax
0x14000c5db  lea     rdx, [rbp+3Fh+P]
0x14000c5df  mov     qword ptr [rbx+38h], 8
0x14000c5e7  lea     rax, [rbp+3Fh+arg_18]
0x14000c5eb  mov     [rbx+30h], rax
0x14000c5ef  mov     rcx, rdi
0x14000c5f2  mov     qword ptr [rbx+48h], 4
0x14000c5fa  lea     rax, [rbp+3Fh+arg_20]
0x14000c5fe  mov     [rbx+40h], rax
0x14000c602  mov     eax, r12d
0x14000c605  cmp     [rdi+10h], r12
0x14000c609  setnz   al
0x14000c60c  mov     [rbp+3Fh+var_54], eax
0x14000c60f  lea     rax, [rbp+3Fh+var_54]
0x14000c613  mov     [rbx+60h], rax
0x14000c617  lea     rax, [rdi+8]
0x14000c61b  mov     [rbx+70h], rax
0x14000c61f  mov     [rbx+50h], rdi
0x14000c623  mov     qword ptr [rbx+58h], 8
0x14000c62b  mov     qword ptr [rbx+68h], 4
0x14000c633  mov     qword ptr [rbx+78h], 4
0x14000c63b  call    PrepareAceDataForEvent
0x14000c640  test    eax, eax
0x14000c642  jns     short loc_14000C651
0x14000c644  mov     rdi, r12
0x14000c647  mov     [rbp+3Fh+P], r12
0x14000c64b  mov     [rbp+3Fh+var_60], r12d
0x14000c64f  jmp     short loc_14000C659
0x14000c651  mov     rdi, [rbp+3Fh+P]
0x14000c655  mov     [rbp+3Fh+P], rdi
0x14000c659  mov     r14, [rbp+3Fh+Str+8]
0x14000c65d  mov     r13d, 2
0x14000c663  test    r14, r14
0x14000c666  jz      short loc_14000C679
0x14000c668  mov     rcx, r14; Str
0x14000c66b  call    wcslen_0
0x14000c670  lea     ecx, ds:2[rax*2]
0x14000c677  jmp     short loc_14000C67C
0x14000c679  mov     ecx, r13d
0x14000c67c  mov     [rbx+88h], ecx
0x14000c682  lea     r15, SourceString
0x14000c689  mov     [rbx+8Ch], r12d
0x14000c690  lea     r9, [rbp+3Fh+var_80]
0x14000c694  mov     qword ptr [rbx+98h], 4
0x14000c69f  lea     r8, [rbp+3Fh+var_5C]
0x14000c6a3  test    r14, r14
0x14000c6a6  lea     rdx, [rbp+3Fh+var_A8]
0x14000c6aa  mov     rax, r15
0x14000c6ad  mov     rcx, rsi
0x14000c6b0  cmovnz  rax, r14
0x14000c6b4  mov     [rbx+80h], rax
0x14000c6bb  lea     rax, [rbp+3Fh+var_60]
0x14000c6bf  mov     [rbx+90h], rax
0x14000c6c6  mov     eax, [rbp+3Fh+var_60]
0x14000c6c9  mov     [rbx+0A8h], eax
0x14000c6cf  mov     eax, r12d
0x14000c6d2  mov     [rbx+0A0h], rdi
0x14000c6d9  mov     [rbx+0ACh], r12d
0x14000c6e0  cmp     [rsi+10h], r12
0x14000c6e4  setnz   al
0x14000c6e7  mov     [rbp+3Fh+var_50], eax
0x14000c6ea  lea     rax, [rbp+3Fh+var_50]
0x14000c6ee  mov     [rbx+0C0h], rax
0x14000c6f5  lea     rax, [rsi+8]
0x14000c6f9  mov     [rbx+0D0h], rax
0x14000c700  mov     [rbx+0B0h], rsi
0x14000c707  mov     qword ptr [rbx+0B8h], 8
0x14000c712  mov     qword ptr [rbx+0C8h], 4
0x14000c71d  mov     qword ptr [rbx+0D8h], 4
0x14000c728  call    PrepareAceDataForEvent
0x14000c72d  xor     edi, edi
0x14000c72f  test    eax, eax
0x14000c731  jns     short loc_14000C738
0x14000c733  mov     [rbp+3Fh+var_5C], edi
0x14000c736  jmp     short loc_14000C73C
0x14000c738  mov     r12, [rbp+3Fh+var_A8]
0x14000c73c  mov     rsi, [rbp+3Fh+var_80+8]
0x14000c740  test    rsi, rsi
0x14000c743  jz      short loc_14000C756
0x14000c745  mov     rcx, rsi; Str
0x14000c748  call    wcslen_0
0x14000c74d  lea     ecx, ds:2[rax*2]
0x14000c754  jmp     short loc_14000C759
0x14000c756  mov     ecx, r13d
0x14000c759  mov     [rbx+0E8h], ecx
0x14000c75f  lea     r9, [rbp+3Fh+var_70]
0x14000c763  mov     rcx, [rbp+3Fh+var_98]
0x14000c767  lea     r8, [rbp+3Fh+var_58]
0x14000c76b  mov     [rbx+0ECh], edi
0x14000c771  lea     rdx, [rbp+3Fh+var_A0]
0x14000c775  mov     qword ptr [rbx+0F8h], 4
0x14000c780  test    rsi, rsi
0x14000c783  mov     rax, r15
0x14000c786  cmovnz  rax, rsi
0x14000c78a  mov     [rbx+0E0h], rax
0x14000c791  lea     rax, [rbp+3Fh+var_5C]
0x14000c795  mov     [rbx+0F0h], rax
0x14000c79c  mov     eax, [rbp+3Fh+var_5C]
0x14000c79f  mov     [rbx+108h], eax
0x14000c7a5  mov     eax, edi
0x14000c7a7  mov     [rbx+100h], r12
0x14000c7ae  mov     [rbx+10Ch], edi
0x14000c7b4  cmp     [rcx+10h], rdi
0x14000c7b8  setnz   al
0x14000c7bb  mov     [rbp+3Fh+var_4C], eax
0x14000c7be  lea     rax, [rbp+3Fh+var_4C]
0x14000c7c2  mov     [rbx+120h], rax
0x14000c7c9  lea     rax, [rcx+8]
0x14000c7cd  mov     [rbx+130h], rax
0x14000c7d4  mov     [rbx+110h], rcx
0x14000c7db  mov     qword ptr [rbx+118h], 8
0x14000c7e6  mov     qword ptr [rbx+128h], 4
0x14000c7f1  mov     qword ptr [rbx+138h], 4
0x14000c7fc  call    PrepareAceDataForEvent
0x14000c801  test    eax, eax
0x14000c803  jns     short loc_14000C80D
0x14000c805  mov     r15, rdi
0x14000c808  mov     [rbp+3Fh+var_58], edi
0x14000c80b  jmp     short loc_14000C811
0x14000c80d  mov     r15, [rbp+3Fh+var_A0]
0x14000c811  mov     rdi, [rbp+3Fh+var_70+8]
0x14000c815  test    rdi, rdi
0x14000c818  jz      short loc_14000C82D
0x14000c81a  mov     rcx, rdi; Str
0x14000c81d  call    wcslen_0
0x14000c822  test    rdi, rdi
0x14000c825  lea     r13d, ds:2[rax*2]
0x14000c82d  mov     [rbx+148h], r13d
0x14000c834  lea     rax, SourceString
0x14000c83b  cmovnz  rax, rdi
0x14000c83f  mov     dword ptr [rbx+14Ch], 0
0x14000c849  mov     [rbx+140h], rax
0x14000c850  lea     rdx, Event27; EventDescriptor
0x14000c857  lea     rax, [rbp+3Fh+var_58]
0x14000c85b  mov     qword ptr [rbx+158h], 4
0x14000c866  mov     [rbx+150h], rax
0x14000c86d  mov     r9d, 17h; UserDataCount
0x14000c873  mov     eax, [rbp+3Fh+var_58]
0x14000c876  xor     r8d, r8d; ActivityId
0x14000c879  mov     [rbx+160h], r15
0x14000c880  mov     [rbx+168h], eax
0x14000c886  mov     dword ptr [rbx+16Ch], 0
0x14000c890  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x14000c897  mov     [rsp+20h], rbx; UserData
0x14000c89c  call    cs:__imp_EtwWrite
0x14000c8a3  nop     dword ptr [rax+rax+00h]
0x14000c8a8  mov     rcx, [rbp+3Fh+P]; P
0x14000c8ac  mov     r13d, eax
0x14000c8af  test    rcx, rcx
0x14000c8b2  jz      short loc_14000C8BE
0x14000c8b4  mov     edx, 64446353h; Tag
0x14000c8b9  call    SecFreePool
0x14000c8be  test    r14, r14
0x14000c8c1  jz      short loc_14000C8D0
0x14000c8c3  mov     edx, 74736353h; Tag
0x14000c8c8  mov     rcx, r14; P
0x14000c8cb  call    SecFreePool
0x14000c8d0  test    r12, r12
0x14000c8d3  jz      short loc_14000C8E2
0x14000c8d5  mov     edx, 64446353h; Tag
0x14000c8da  mov     rcx, r12; P
0x14000c8dd  call    SecFreePool
0x14000c8e2  test    rsi, rsi
0x14000c8e5  jz      short loc_14000C8F4
0x14000c8e7  mov     edx, 74736353h; Tag
0x14000c8ec  mov     rcx, rsi; P
0x14000c8ef  call    SecFreePool
0x14000c8f4  test    r15, r15
0x14000c8f7  jz      short loc_14000C906
0x14000c8f9  mov     edx, 64446353h; Tag
0x14000c8fe  mov     rcx, r15; P
0x14000c901  call    SecFreePool
0x14000c906  test    rdi, rdi
0x14000c909  jz      short loc_14000C918
0x14000c90b  mov     edx, 74736353h; Tag
0x14000c910  mov     rcx, rdi; P
0x14000c913  call    SecFreePool
0x14000c918  mov     rcx, rbx; ListEntry
0x14000c91b  call    SecReleaseEtwDescriptorBuffer
0x14000c920  mov     eax, r13d
0x14000c923  mov     rcx, [rbp+3Fh+var_48]
0x14000c927  xor     rcx, rsp; StackCookie
0x14000c92a  call    __security_check_cookie
0x14000c92f  add     rsp, 0A8h
0x14000c936  pop     r15
0x14000c938  pop     r14
0x14000c93a  pop     r13
0x14000c93c  pop     r12
0x14000c93e  pop     rdi
0x14000c93f  pop     rsi
0x14000c940  pop     rbx
0x14000c941  pop     rbp
0x14000c942  retn
```
