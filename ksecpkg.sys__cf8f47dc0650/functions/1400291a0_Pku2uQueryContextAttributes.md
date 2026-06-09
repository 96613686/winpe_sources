# Pku2uQueryContextAttributes

- ea: `0x1400291a0`
- end: `0x14002967c`
- name: `Pku2uQueryContextAttributes`
- size: `1244`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007008`
- `0x14000d9b0`
- `0x14000da94`
- `0x14000dd40`
- `0x1400102c0`
- `0x1400291a0`
- `0x140029d94`
- `0x140029f3c`
- `0x14002a470`
- `0x14002c874`

## import_xrefs

- `ntoskrnl!wcschr` at `0x1400293d9`
- `ntoskrnl!wcschr` at `0x1400293d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029468`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029604`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029468`
- `ntoskrnl!RtlInitUnicodeString` at `0x140029604`
- `ksecdd!FreeContextBuffer` at `0x1400293b1`
- `ksecdd!FreeContextBuffer` at `0x140029649`
- `ksecdd!FreeContextBuffer` at `0x1400293b1`
- `ksecdd!FreeContextBuffer` at `0x140029649`
- `ksecdd!QuerySecurityPackageInfoW` at `0x14002947c`
- `ksecdd!QuerySecurityPackageInfoW` at `0x140029618`
- `ksecdd!QuerySecurityPackageInfoW` at `0x14002947c`
- `ksecdd!QuerySecurityPackageInfoW` at `0x140029618`
- `ksecdd!KSecAllocateContextBuffer` at `0x140029264`
- `ksecdd!KSecAllocateContextBuffer` at `0x140029293`
- `ksecdd!KSecAllocateContextBuffer` at `0x1400292c2`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002933f`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002937a`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002941a`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002952c`
- `ksecdd!KSecAllocateContextBuffer` at `0x140029264`
- `ksecdd!KSecAllocateContextBuffer` at `0x140029293`
- `ksecdd!KSecAllocateContextBuffer` at `0x1400292c2`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002933f`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002937a`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002941a`
- `ksecdd!KSecAllocateContextBuffer` at `0x14002952c`

## string_xrefs

- `0x14002920a`: `Invalid handle supplied for GetContextToken(0x%x)\n`
- `0x1400295c1`: `PKU2U Security Package`

## pseudocode

```c
__int64 __fastcall Pku2uQueryContextAttributes(__int64 a1, unsigned int a2, unsigned int *a3)
{
  __int64 v6; // r14
  SECURITY_STATUS v7; // edi
  __int64 v8; // rax
  __int64 v9; // rcx
  void *v10; // rax
  _BYTE *v11; // rax
  __int64 v12; // rcx
  bool v13; // zf
  _QWORD *v14; // r15
  __int64 v15; // rbx
  __int64 v16; // rcx
  void *v17; // rax
  _WORD *v18; // rdx
  _OWORD *v19; // rax
  const wchar_t *v20; // rcx
  wchar_t *v21; // rax
  __int64 v22; // rdx
  int v23; // eax
  unsigned __int64 v24; // rbx
  void *v25; // rax
  __int64 v26; // rax
  void *ContextBuffer; // rax
  __int64 v28; // rcx
  __int64 v29; // rcx
  _OWORD *v30; // rcx
  void *Src[2]; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  PSecPkgInfoW ppPackageInfo; // [rsp+88h] [rbp+48h] BYREF

  ppPackageInfo = 0;
  DestinationString = 0;
  if ( KsecInfoLevel )
    KsecDebugOut(4, "SpQueryContextAttributes Called\n");
  v6 = Pku2uReferenceContext(a1, 0);
  if ( !v6 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Invalid handle supplied for GetContextToken(0x%x)\n", a1);
    v7 = -1073741816;
    goto LABEL_62;
  }
  v7 = 0;
  if ( a2 > 0xB )
  {
    if ( a2 == 12 )
      goto LABEL_14;
    if ( a2 == 14 )
    {
      v28 = *(unsigned int *)(v6 + 108);
      if ( (*(_DWORD *)(v6 + 104) & 4) != 0 )
        LODWORD(v28) = WSTMapContextAttributes(v28);
      *a3 = v28;
      goto LABEL_62;
    }
    if ( a2 != 17 )
    {
      if ( a2 == 18 )
      {
        v26 = *(_QWORD *)(v6 + 56);
        if ( !v26 )
        {
          v7 = -2146893045;
          goto LABEL_62;
        }
      }
      else
      {
        if ( a2 != 21 )
          goto LABEL_46;
        v26 = *(_QWORD *)(v6 + 112);
      }
      *(_QWORD *)a3 = v26;
      goto LABEL_62;
    }
    if ( !a3 )
    {
      v7 = -1073741811;
      goto LABEL_62;
    }
    *((_QWORD *)a3 + 1) = 0;
    if ( *(_QWORD *)(v6 + 160) )
    {
      ContextBuffer = (void *)KSecAllocateContextBuffer(*(unsigned int *)(v6 + 168));
      *((_QWORD *)a3 + 1) = ContextBuffer;
      if ( ContextBuffer )
      {
        memmove(ContextBuffer, *(const void **)(v6 + 160), *(unsigned int *)(v6 + 168));
        *a3 = *(_DWORD *)(v6 + 168);
        goto LABEL_62;
      }
      goto LABEL_15;
    }
LABEL_40:
    *a3 = 0;
    goto LABEL_62;
  }
  switch ( a2 )
  {
    case 0xBu:
      goto LABEL_40;
    case 0u:
      RtlInitUnicodeString(&DestinationString, L"pku2u");
      v7 = QuerySecurityPackageInfoW(&DestinationString, &ppPackageInfo);
      if ( v7 >= 0 )
      {
        *a3 = ppPackageInfo->cbMaxToken;
        a3[1] = 28;
        a3[2] = 1;
        a3[3] = 76;
      }
      goto LABEL_62;
    case 1u:
      v20 = *(const wchar_t **)(v6 + 128);
      *(_OWORD *)Src = 0;
      v21 = wcschr(v20, 0x40u);
      v22 = v6 + 120;
      if ( v21 )
        v23 = Pku2uDuplicateString(Src, v22);
      else
        v23 = Pku2uBuildFullServiceName(v6 + 136, v22, Src);
      v7 = v23;
      if ( v23 >= 0 )
      {
        v24 = LOWORD(Src[0]);
        v25 = (void *)KSecAllocateContextBuffer((unsigned int)LOWORD(Src[0]) + 2);
        *(_QWORD *)a3 = v25;
        if ( v25 )
        {
          memmove(v25, Src[1], (unsigned int)v24);
          *(_WORD *)(*(_QWORD *)a3 + 2 * (v24 >> 1)) = 0;
        }
        else
        {
          v7 = -1073741670;
        }
        Pku2uFreeString(Src);
      }
      goto LABEL_62;
    case 5u:
      v12 = *(unsigned int *)(v6 + 64);
      a3[6] = v12;
      v13 = *(_DWORD *)(v6 + 64) == 17;
      Src[0] = 0;
      a3[5] = !v13 + 15;
      *(_QWORD *)a3 = 0;
      *((_QWORD *)a3 + 1) = 0;
      v7 = CDLocateCSystem(v12, Src);
      if ( v7 < 0 )
        goto LABEL_62;
      v14 = Src[0];
      a3[4] = 8 * *((_DWORD *)Src[0] + 3);
      v15 = -1;
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)(v14[4] + 2 * v16) );
      v17 = (void *)KSecAllocateContextBuffer((unsigned int)(2 * v16 + 2));
      *((_QWORD *)a3 + 1) = v17;
      if ( v17 )
      {
        v18 = (_WORD *)v14[4];
        do
          ++v15;
        while ( v18[v15] );
        memmove(v17, v18, 2LL * (unsigned int)(v15 + 1));
        v19 = (_OWORD *)KSecAllocateContextBuffer(26);
        *(_QWORD *)a3 = v19;
        if ( v19 )
        {
          *v19 = *(_OWORD *)L"HMAC-SHA1-96";
          *(_OWORD *)((char *)v19 + 10) = *(_OWORD *)L"SHA1-96";
        }
        else
        {
          v7 = -1073741670;
          FreeContextBuffer(*((PVOID *)a3 + 1));
          *((_QWORD *)a3 + 1) = 0;
        }
        goto LABEL_62;
      }
LABEL_15:
      v7 = -1073741670;
      goto LABEL_62;
    case 9u:
      v9 = *(unsigned int *)(v6 + 72);
      *a3 = v9;
      if ( (_DWORD)v9 )
      {
        v10 = (void *)KSecAllocateContextBuffer(v9);
        *((_QWORD *)a3 + 1) = v10;
        if ( v10 )
        {
          memmove(v10, *(const void **)(v6 + 80), *(unsigned int *)(v6 + 72));
          goto LABEL_62;
        }
      }
      else
      {
        v11 = (_BYTE *)KSecAllocateContextBuffer(1);
        *((_QWORD *)a3 + 1) = v11;
        if ( v11 )
        {
          *v11 = 0;
          goto LABEL_62;
        }
      }
      goto LABEL_15;
  }
  if ( a2 != 10 )
  {
LABEL_46:
    v7 = -1073741637;
    goto LABEL_62;
  }
LABEL_14:
  v8 = KSecAllocateContextBuffer(90);
  *(_QWORD *)a3 = v8;
  if ( !v8 )
    goto LABEL_15;
  *(_QWORD *)(v8 + 16) = v8 + 32;
  *(_QWORD *)(*(_QWORD *)a3 + 24LL) = *(_QWORD *)(*(_QWORD *)a3 + 16LL) + 12LL;
  v29 = *(_QWORD *)(*(_QWORD *)a3 + 16LL);
  *(_QWORD *)v29 = *(_QWORD *)L"pku2u";
  *(_DWORD *)(v29 + 8) = *(_DWORD *)L"u";
  v30 = *(_OWORD **)(*(_QWORD *)a3 + 24LL);
  *v30 = *(_OWORD *)L"PKU2U Security Package";
  v30[1] = *(_OWORD *)L"curity Package";
  *(_OWORD *)((char *)v30 + 30) = *(_OWORD *)L"Package";
  *(_WORD *)(*(_QWORD *)a3 + 4LL) = 1;
  *(_WORD *)(*(_QWORD *)a3 + 6LL) = 31;
  **(_DWORD **)a3 = 10555667;
  RtlInitUnicodeString(&DestinationString, L"pku2u");
  v7 = QuerySecurityPackageInfoW(&DestinationString, &ppPackageInfo);
  if ( v7 >= 0 )
  {
    *(_DWORD *)(*(_QWORD *)a3 + 8LL) = ppPackageInfo->cbMaxToken;
    if ( a2 == 12 )
      a3[2] = 0;
  }
LABEL_62:
  if ( ppPackageInfo )
    FreeContextBuffer(ppPackageInfo);
  if ( v6 )
    Pku2uDereferenceContext((PVOID)v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400291a0  mov     [rsp-28h+arg_0], rbx
0x1400291a5  mov     [rsp-28h+arg_8], rsi
0x1400291aa  push    rbp
0x1400291ab  push    rdi
0x1400291ac  push    r12
0x1400291ae  push    r14
0x1400291b0  push    r15
0x1400291b2  mov     rbp, rsp
0x1400291b5  sub     rsp, 40h
0x1400291b9  xor     r12d, r12d
0x1400291bc  xorps   xmm0, xmm0
0x1400291bf  cmp     cs:KsecInfoLevel, r12d
0x1400291c6  mov     rsi, r8
0x1400291c9  mov     ebx, edx
0x1400291cb  mov     [rbp+ppPackageInfo], r12
0x1400291cf  mov     rdi, rcx
0x1400291d2  lea     r15d, [r12+4]
0x1400291d7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400291db  jz      short loc_1400291EC
0x1400291dd  lea     rdx, aSpquerycontext; "SpQueryContextAttributes Called\n"
0x1400291e4  mov     ecx, r15d
0x1400291e7  call    KsecDebugOut
0x1400291ec  xor     edx, edx
0x1400291ee  mov     rcx, rdi
0x1400291f1  call    Pku2uReferenceContext
0x1400291f6  mov     r14, rax
0x1400291f9  test    rax, rax
0x1400291fc  jnz     short loc_140029223
0x1400291fe  cmp     cs:KsecInfoLevel, r12d
0x140029205  jz      short loc_140029219
0x140029207  mov     r8, rdi
0x14002920a  lea     rdx, aInvalidHandleS_0; "Invalid handle supplied for GetContextT"...
0x140029211  lea     ecx, [rax+1]
0x140029214  call    KsecDebugOut
0x140029219  mov     edi, 0C0000008h
0x14002921e  jmp     loc_140029640
0x140029223  mov     edi, r12d
0x140029226  cmp     ebx, 0Bh
0x140029229  ja      loc_1400294BD
0x14002922f  jz      loc_1400294B5
0x140029235  mov     eax, ebx
0x140029237  test    ebx, ebx
0x140029239  jz      loc_14002945D
0x14002923f  sub     eax, 1
0x140029242  jz      loc_1400293C6
0x140029248  sub     eax, r15d
0x14002924b  jz      loc_1400292DF
0x140029251  sub     eax, r15d
0x140029254  jz      short loc_140029289
0x140029256  cmp     eax, 1
0x140029259  jnz     loc_1400294E0
0x14002925f  mov     ecx, 5Ah ; 'Z'
0x140029264  call    cs:__imp_KSecAllocateContextBuffer
0x14002926b  nop     dword ptr [rax+rax+00h]
0x140029270  mov     [rsi], rax
0x140029273  mov     rcx, rax
0x140029276  test    rax, rax
0x140029279  jnz     loc_140029584
0x14002927f  mov     edi, 0C000009Ah
0x140029284  jmp     loc_140029640
0x140029289  mov     ecx, [r14+48h]
0x14002928d  mov     [rsi], ecx
0x14002928f  test    ecx, ecx
0x140029291  jz      short loc_1400292BD
0x140029293  call    cs:__imp_KSecAllocateContextBuffer
0x14002929a  nop     dword ptr [rax+rax+00h]
0x14002929f  mov     [rsi+8], rax
0x1400292a3  test    rax, rax
0x1400292a6  jz      short loc_14002927F
0x1400292a8  mov     r8d, [r14+48h]; Size
0x1400292ac  mov     rcx, rax; void *
0x1400292af  mov     rdx, [r14+50h]; Src
0x1400292b3  call    memmove
0x1400292b8  jmp     loc_140029640
0x1400292bd  mov     ecx, 1
0x1400292c2  call    cs:__imp_KSecAllocateContextBuffer
0x1400292c9  nop     dword ptr [rax+rax+00h]
0x1400292ce  mov     [rsi+8], rax
0x1400292d2  test    rax, rax
0x1400292d5  jz      short loc_14002927F
0x1400292d7  mov     [rax], r12b
0x1400292da  jmp     loc_140029640
0x1400292df  mov     ecx, [r14+40h]
0x1400292e3  lea     rdx, [rbp+Src]
0x1400292e7  mov     [rsi+18h], ecx
0x1400292ea  mov     eax, r12d
0x1400292ed  cmp     dword ptr [r14+40h], 11h
0x1400292f2  mov     [rbp+Src], r12
0x1400292f6  setnz   al
0x1400292f9  add     eax, 0Fh
0x1400292fc  mov     [rsi+14h], eax
0x1400292ff  mov     [rsi], r12
0x140029302  mov     [rsi+8], r12
0x140029306  call    CDLocateCSystem
0x14002930b  mov     edi, eax
0x14002930d  test    eax, eax
0x14002930f  js      loc_140029640
0x140029315  mov     r15, [rbp+Src]
0x140029319  mov     ecx, [r15+0Ch]
0x14002931d  shl     ecx, 3
0x140029320  mov     [rsi+10h], ecx
0x140029323  mov     rax, [r15+20h]
0x140029327  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002932b  mov     rcx, rbx
0x14002932e  inc     rcx
0x140029331  cmp     [rax+rcx*2], r12w
0x140029336  jnz     short loc_14002932E
0x140029338  lea     ecx, ds:2[rcx*2]
0x14002933f  call    cs:__imp_KSecAllocateContextBuffer
0x140029346  nop     dword ptr [rax+rax+00h]
0x14002934b  mov     [rsi+8], rax
0x14002934f  mov     rcx, rax; void *
0x140029352  test    rax, rax
0x140029355  jz      loc_14002927F
0x14002935b  mov     rdx, [r15+20h]; Src
0x14002935f  inc     rbx
0x140029362  cmp     [rdx+rbx*2], r12w
0x140029367  jnz     short loc_14002935F
0x140029369  lea     r8d, [rbx+1]
0x14002936d  add     r8, r8; Size
0x140029370  call    memmove
0x140029375  mov     ecx, 1Ah
0x14002937a  call    cs:__imp_KSecAllocateContextBuffer
0x140029381  nop     dword ptr [rax+rax+00h]
0x140029386  mov     [rsi], rax
0x140029389  test    rax, rax
0x14002938c  jz      short loc_1400293A8
0x14002938e  movups  xmm0, xmmword ptr cs:aHmacSha196; "HMAC-SHA1-96"
0x140029395  movups  xmmword ptr [rax], xmm0
0x140029398  movups  xmm1, xmmword ptr cs:aHmacSha196+0Ah; "SHA1-96"
0x14002939f  movups  xmmword ptr [rax+0Ah], xmm1
0x1400293a3  jmp     loc_140029640
0x1400293a8  mov     edi, 0C000009Ah
0x1400293ad  mov     rcx, [rsi+8]; pvContextBuffer
0x1400293b1  call    cs:__imp_FreeContextBuffer
0x1400293b8  nop     dword ptr [rax+rax+00h]
0x1400293bd  mov     [rsi+8], r12
0x1400293c1  jmp     loc_140029640
0x1400293c6  mov     rcx, [r14+80h]; Str
0x1400293cd  xorps   xmm0, xmm0
0x1400293d0  mov     edx, 40h ; '@'; Ch
0x1400293d5  movups  xmmword ptr [rbp+Src], xmm0
0x1400293d9  call    cs:__imp_wcschr
0x1400293e0  nop     dword ptr [rax+rax+00h]
0x1400293e5  lea     rdx, [r14+78h]
0x1400293e9  test    rax, rax
0x1400293ec  jz      short loc_1400293F9
0x1400293ee  lea     rcx, [rbp+Src]
0x1400293f2  call    Pku2uDuplicateString
0x1400293f7  jmp     short loc_140029409
0x1400293f9  lea     rcx, [r14+88h]
0x140029400  lea     r8, [rbp+Src]
0x140029404  call    Pku2uBuildFullServiceName
0x140029409  mov     edi, eax
0x14002940b  test    eax, eax
0x14002940d  js      loc_140029640
0x140029413  movzx   ebx, word ptr [rbp+Src]
0x140029417  lea     ecx, [rbx+2]
0x14002941a  call    cs:__imp_KSecAllocateContextBuffer
0x140029421  nop     dword ptr [rax+rax+00h]
0x140029426  mov     [rsi], rax
0x140029429  test    rax, rax
0x14002942c  jz      short loc_14002944A
0x14002942e  mov     rdx, [rbp+Src+8]; Src
0x140029432  mov     r8d, ebx; Size
0x140029435  mov     rcx, rax; void *
0x140029438  call    memmove
0x14002943d  mov     rcx, [rsi]
0x140029440  shr     rbx, 1
0x140029443  mov     [rcx+rbx*2], r12w
0x140029448  jmp     short loc_14002944F
0x14002944a  mov     edi, 0C000009Ah
0x14002944f  lea     rcx, [rbp+Src]
0x140029453  call    Pku2uFreeString
0x140029458  jmp     loc_140029640
0x14002945d  lea     rdx, aPku2u; "pku2u"
0x140029464  lea     rcx, [rbp+DestinationString]; DestinationString
0x140029468  call    cs:__imp_RtlInitUnicodeString
0x14002946f  nop     dword ptr [rax+rax+00h]
0x140029474  lea     rdx, [rbp+ppPackageInfo]; ppPackageInfo
0x140029478  lea     rcx, [rbp+DestinationString]; pPackageName
0x14002947c  call    cs:__imp_QuerySecurityPackageInfoW
0x140029483  nop     dword ptr [rax+rax+00h]
0x140029488  mov     edi, eax
0x14002948a  test    eax, eax
0x14002948c  js      loc_140029640
0x140029492  mov     rax, [rbp+ppPackageInfo]
0x140029496  mov     ecx, [rax+8]
0x140029499  mov     [rsi], ecx
0x14002949b  mov     dword ptr [rsi+4], 1Ch
0x1400294a2  mov     dword ptr [rsi+8], 1
0x1400294a9  mov     dword ptr [rsi+0Ch], 4Ch ; 'L'
0x1400294b0  jmp     loc_140029640
0x1400294b5  mov     [rsi], r12d
0x1400294b8  jmp     loc_140029640
0x1400294bd  mov     eax, ebx
0x1400294bf  sub     eax, 0Ch
0x1400294c2  jz      loc_14002925F
0x1400294c8  sub     eax, 2
0x1400294cb  jz      loc_140029569
0x1400294d1  sub     eax, 3
0x1400294d4  jz      short loc_140029509
0x1400294d6  sub     eax, 1
0x1400294d9  jz      short loc_1400294F6
0x1400294db  cmp     eax, 3
0x1400294de  jz      short loc_1400294EA
0x1400294e0  mov     edi, 0C00000BBh
0x1400294e5  jmp     loc_140029640
0x1400294ea  mov     rax, [r14+70h]
0x1400294ee  mov     [rsi], rax
0x1400294f1  jmp     loc_140029640
0x1400294f6  mov     rax, [r14+38h]
0x1400294fa  test    rax, rax
0x1400294fd  jnz     short loc_1400294EE
0x1400294ff  mov     edi, 8009030Bh
0x140029504  jmp     loc_140029640
0x140029509  test    rsi, rsi
0x14002950c  jnz     short loc_140029518
0x14002950e  mov     edi, 0C000000Dh
0x140029513  jmp     loc_140029640
0x140029518  mov     [rsi+8], r12
0x14002951c  cmp     [r14+0A0h], r12
0x140029523  jz      short loc_1400294B5
0x140029525  mov     ecx, [r14+0A8h]
0x14002952c  call    cs:__imp_KSecAllocateContextBuffer
0x140029533  nop     dword ptr [rax+rax+00h]
0x140029538  mov     [rsi+8], rax
0x14002953c  test    rax, rax
0x14002953f  jz      loc_14002927F
0x140029545  mov     r8d, [r14+0A8h]; Size
0x14002954c  mov     rcx, rax; void *
0x14002954f  mov     rdx, [r14+0A0h]; Src
0x140029556  call    memmove
0x14002955b  mov     eax, [r14+0A8h]
0x140029562  mov     [rsi], eax
0x140029564  jmp     loc_140029640
0x140029569  mov     eax, [r14+68h]
0x14002956d  mov     ecx, [r14+6Ch]
0x140029571  test    r15b, al
0x140029574  jz      short loc_14002957D
0x140029576  call    WSTMapContextAttributes
0x14002957b  mov     ecx, eax
0x14002957d  mov     [rsi], ecx
0x14002957f  jmp     loc_140029640
0x140029584  add     rax, 20h ; ' '
0x140029588  lea     rdx, aPku2u; "pku2u"
0x14002958f  mov     [rcx+10h], rax
0x140029593  mov     rcx, [rsi]
0x140029596  mov     rax, [rcx+10h]
0x14002959a  add     rax, 0Ch
0x14002959e  mov     [rcx+18h], rax
0x1400295a2  mov     rax, [rsi]
0x1400295a5  movsd   xmm0, qword ptr cs:aPku2u; "pku2u"
0x1400295ad  mov     rcx, [rax+10h]
0x1400295b1  movsd   qword ptr [rcx], xmm0
0x1400295b5  mov     eax, dword ptr cs:aPku2u+8; "u"
0x1400295bb  mov     [rcx+8], eax
0x1400295be  mov     rax, [rsi]
0x1400295c1  movups  xmm0, xmmword ptr cs:aPku2uSecurityP; "PKU2U Security Package"
0x1400295c8  mov     rcx, [rax+18h]
0x1400295cc  movups  xmmword ptr [rcx], xmm0
0x1400295cf  movups  xmm1, xmmword ptr cs:aPku2uSecurityP+10h; "curity Package"
0x1400295d6  movups  xmmword ptr [rcx+10h], xmm1
0x1400295da  movups  xmm0, xmmword ptr cs:aPku2uSecurityP+1Eh; "Package"
0x1400295e1  movups  xmmword ptr [rcx+1Eh], xmm0
0x1400295e5  mov     rax, [rsi]
0x1400295e8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400295ec  mov     word ptr [rax+4], 1
0x1400295f2  mov     rax, [rsi]
0x1400295f5  mov     word ptr [rax+6], 1Fh
0x1400295fb  mov     rax, [rsi]
0x1400295fe  mov     dword ptr [rax], 0A11113h
0x140029604  call    cs:__imp_RtlInitUnicodeString
0x14002960b  nop     dword ptr [rax+rax+00h]
0x140029610  lea     rdx, [rbp+ppPackageInfo]; ppPackageInfo
0x140029614  lea     rcx, [rbp+DestinationString]; pPackageName
0x140029618  call    cs:__imp_QuerySecurityPackageInfoW
0x14002961f  nop     dword ptr [rax+rax+00h]
0x140029624  mov     edi, eax
0x140029626  test    eax, eax
0x140029628  js      short loc_140029640
0x14002962a  mov     rax, [rbp+ppPackageInfo]
0x14002962e  mov     rdx, [rsi]
0x140029631  mov     ecx, [rax+8]
0x140029634  mov     [rdx+8], ecx
0x140029637  cmp     ebx, 0Ch
0x14002963a  jnz     short loc_140029640
0x14002963c  mov     [rsi+8], r12d
0x140029640  mov     rcx, [rbp+ppPackageInfo]; pvContextBuffer
0x140029644  test    rcx, rcx
0x140029647  jz      short loc_140029655
0x140029649  call    cs:__imp_FreeContextBuffer
0x140029650  nop     dword ptr [rax+rax+00h]
0x140029655  test    r14, r14
0x140029658  jz      short loc_140029662
0x14002965a  mov     rcx, r14; P
0x14002965d  call    Pku2uDereferenceContext
0x140029662  mov     rbx, [rsp+40h+arg_0]
0x140029667  mov     eax, edi
0x140029669  mov     rsi, [rsp+40h+arg_8]
  ... truncated ...
```
