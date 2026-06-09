# NlpMakeTokenInformationV3

- ea: `0x1800405e8`
- end: `0x180040a04`
- name: `NlpMakeTokenInformationV3`
- size: `1052`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a470`

## callees

- `0x180030844`
- `0x18003f96c`
- `0x1800405e8`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180040645`
- `ntdll!RtlLengthSid` at `0x18004067b`
- `ntdll!RtlLengthSid` at `0x1800406c2`
- `ntdll!RtlLengthSid` at `0x1800406f7`
- `ntdll!RtlLengthSid` at `0x180040720`
- `ntdll!RtlLengthSid` at `0x1800408b2`
- `ntdll!RtlLengthSid` at `0x180040917`
- `ntdll!RtlLengthSid` at `0x180040645`
- `ntdll!RtlLengthSid` at `0x18004067b`
- `ntdll!RtlLengthSid` at `0x1800406c2`
- `ntdll!RtlLengthSid` at `0x1800406f7`
- `ntdll!RtlLengthSid` at `0x180040720`
- `ntdll!RtlLengthSid` at `0x1800408b2`
- `ntdll!RtlLengthSid` at `0x180040917`
- `ntdll!RtlCopySid` at `0x1800408c9`
- `ntdll!RtlCopySid` at `0x18004092f`
- `ntdll!RtlCopySid` at `0x1800408c9`
- `ntdll!RtlCopySid` at `0x18004092f`

## pseudocode

```c
__int64 __fastcall NlpMakeTokenInformationV3(__int64 a1, const void *a2, unsigned int a3, _QWORD *a4)
{
  unsigned int v4; // ebp
  unsigned int v7; // ebx
  _QWORD *v8; // r14
  ULONG v9; // edi
  int v10; // eax
  unsigned int v11; // ebp
  int v12; // r15d
  unsigned int v13; // ebx
  PSID *v14; // r12
  unsigned int *v15; // r13
  ULONG v16; // ecx
  ULONG v17; // ecx
  ULONG v18; // edi
  unsigned int v19; // edi
  PSID *v20; // rbp
  _QWORD *v21; // rax
  char *v22; // r15
  unsigned int v23; // ebx
  char *i; // r15
  unsigned int v25; // eax
  unsigned int v26; // ebp
  ULONG v27; // eax
  __int64 v28; // rbx
  ULONG v29; // eax
  __int64 v30; // rbx
  unsigned int j; // ebx
  unsigned int v32; // eax

  v4 = a3;
  if ( (*(_DWORD *)(a1 + 168) & 0x200) != 0 )
    return 3221225485LL;
  v7 = *(_DWORD *)(a1 + 156);
  v8 = 0;
  v9 = 112;
  if ( v7 )
    v9 = v7 * (RtlLengthSid(*(PSID *)(a1 + 224)) + 4) + 112;
  if ( (*(_BYTE *)(a1 + 168) & 0x20) != 0 )
  {
    v10 = *(_DWORD *)(a1 + 272);
    v11 = 0;
    v7 += v10;
    if ( v10 )
    {
      do
        v9 += RtlLengthSid(*(PSID *)(*(_QWORD *)(a1 + 280) + 16LL * v11++));
      while ( v11 < *(_DWORD *)(a1 + 272) );
    }
    v4 = a3;
  }
  if ( (*(_DWORD *)(a1 + 168) & 0x200) != 0 )
  {
    v12 = *(_DWORD *)(a1 + 296);
    if ( v12 )
    {
      if ( !*(_QWORD *)(a1 + 304) || !*(_QWORD *)(a1 + 288) )
      {
        v13 = -1073741811;
LABEL_44:
        ((void (__fastcall *)(_QWORD *))qword_180088240)(v8);
        return v13;
      }
      v7 += v12;
      v9 += v12 * (RtlLengthSid(*(PSID *)(a1 + 288)) + 4);
    }
  }
  if ( *(_DWORD *)(a1 + 148) )
  {
    v14 = (PSID *)(a1 + 224);
    v15 = (unsigned int *)(a1 + 148);
    v16 = v9 + 2 * (RtlLengthSid(*(PSID *)(a1 + 224)) + 4);
  }
  else
  {
    if ( !*(_DWORD *)(a1 + 272) )
    {
LABEL_43:
      v13 = -1073741232;
      goto LABEL_44;
    }
    v14 = (PSID *)(a1 + 224);
    v15 = (unsigned int *)(a1 + 148);
    v16 = v9 + RtlLengthSid(*(PSID *)(a1 + 224)) + 4;
  }
  v17 = 16 * v7 + v16;
  v18 = v17 - 16;
  if ( a2 )
  {
    if ( v4 )
    {
      v19 = (v4 + 3) & 0xFFFFFFFC;
      v20 = (PSID *)(a1 + 224);
      v18 = v17 + v19;
      goto LABEL_24;
    }
  }
  else
  {
    v15 = (unsigned int *)(a1 + 148);
  }
  v20 = v14;
LABEL_24:
  v21 = (_QWORD *)((__int64 (__fastcall *)(_QWORD))qword_180088238)(v18);
  v8 = v21;
  if ( !v21 )
    return 3221225495LL;
  memset_0(v21, 0, v18);
  v8[3] = v8 + 11;
  v22 = (char *)&v8[2 * v7 + 12];
  *((_DWORD *)v8 + 22) = 0;
  *(_DWORD *)v8 = *(_DWORD *)(a1 + 16);
  *((_DWORD *)v8 + 1) = *(_DWORD *)(a1 + 20);
  if ( a2 )
  {
    if ( a3 )
    {
      v8[8] = v22;
      *((_QWORD *)v22 + 1) = v22 + 16;
      *(_DWORD *)v22 = a3;
      memcpy_0(v22 + 16, a2, a3);
      v22 += ((a3 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + 16;
    }
  }
  else
  {
    v20 = v14;
  }
  if ( *v15 )
  {
    v8[1] = v22;
    v22 += NlpCopyDomainRelativeSid(v22, *v20, *v15);
  }
  v8[4] = v22;
  v23 = 0;
  for ( i = &v22[NlpCopyDomainRelativeSid(v22, *v20, *(_DWORD *)(a1 + 152))];
        v23 < *(_DWORD *)(a1 + 156);
        ++*(_DWORD *)v8[3] )
  {
    *(_DWORD *)(v8[3] + 16 * (*(unsigned int *)v8[3] + 1LL)) = *(_DWORD *)(*(_QWORD *)(a1 + 160) + 8LL * v23 + 4);
    *(_QWORD *)(v8[3] + 16LL * *(unsigned int *)v8[3] + 8) = i;
    v25 = NlpCopyDomainRelativeSid(i, *v20, *(_DWORD *)(*(_QWORD *)(a1 + 160) + 8LL * v23++));
    i += v25;
  }
  if ( (*(_BYTE *)(a1 + 168) & 0x20) != 0 )
  {
    v26 = 0;
    if ( !v8[1] )
    {
      v8[1] = i;
      v27 = RtlLengthSid(**(PSID **)(a1 + 280));
      v28 = v27;
      RtlCopySid(v27, i, **(PSID **)(a1 + 280));
      i += v28;
      v26 = 1;
    }
    for ( ; v26 < *(_DWORD *)(a1 + 272); ++*(_DWORD *)v8[3] )
    {
      *(_DWORD *)(v8[3] + 16 * (*(unsigned int *)v8[3] + 1LL)) = *(_DWORD *)(*(_QWORD *)(a1 + 280) + 16LL * v26 + 8);
      *(_QWORD *)(v8[3] + 16LL * *(unsigned int *)v8[3] + 8) = i;
      v29 = RtlLengthSid(*(PSID *)(*(_QWORD *)(a1 + 280) + 16LL * v26));
      v30 = v29;
      RtlCopySid(v29, i, *(PSID *)(*(_QWORD *)(a1 + 280) + 16LL * v26));
      i += v30;
      ++v26;
    }
  }
  if ( (*(_DWORD *)(a1 + 168) & 0x200) != 0 )
  {
    for ( j = 0; j < *(_DWORD *)(a1 + 296); ++*(_DWORD *)v8[3] )
    {
      *(_DWORD *)(v8[3] + 16 * (*(unsigned int *)v8[3] + 1LL)) = *(_DWORD *)(*(_QWORD *)(a1 + 304) + 8LL * j + 4);
      *(_QWORD *)(v8[3] + 16LL * *(unsigned int *)v8[3] + 8) = i;
      v32 = NlpCopyDomainRelativeSid(i, *(PSID *)(a1 + 288), *(_DWORD *)(*(_QWORD *)(a1 + 304) + 8LL * j++));
      i += v32;
    }
  }
  if ( !v8[1] )
    goto LABEL_43;
  v8[5] = 0;
  v8[6] = 0;
  v8[7] = 0;
  *a4 = v8;
  return 0;
}

```

## disassembly

```asm
0x1800405e8  mov     rax, rsp
0x1800405eb  mov     [rax+8], rbx
0x1800405ef  mov     [rax+20h], r9
0x1800405f3  mov     [rax+18h], r8d
0x1800405f7  mov     [rax+10h], rdx
0x1800405fb  push    rbp
0x1800405fc  push    rsi
0x1800405fd  push    rdi
0x1800405fe  push    r12
0x180040600  push    r13
0x180040602  push    r14
0x180040604  push    r15
0x180040606  sub     rsp, 20h
0x18004060a  mov     r15d, 200h
0x180040610  mov     ebp, r8d
0x180040613  mov     rsi, rcx
0x180040616  test    [rcx+0A8h], r15d
0x18004061d  jz      short loc_180040629
0x18004061f  mov     eax, 0C000000Dh
0x180040624  jmp     loc_1800409EF
0x180040629  mov     ebx, [rcx+9Ch]
0x18004062f  xor     r12d, r12d
0x180040632  mov     r14d, r12d
0x180040635  lea     edi, [r12+70h]
0x18004063a  test    ebx, ebx
0x18004063c  jz      short loc_180040653
0x18004063e  mov     rcx, [rcx+0E0h]; Sid
0x180040645  call    cs:__imp_RtlLengthSid
0x18004064b  add     eax, 4
0x18004064e  imul    eax, ebx
0x180040651  add     edi, eax
0x180040653  test    byte ptr [rsi+0A8h], 20h
0x18004065a  jz      short loc_180040691
0x18004065c  mov     eax, [rsi+110h]
0x180040662  mov     ebp, r12d
0x180040665  add     ebx, eax
0x180040667  test    eax, eax
0x180040669  jz      short loc_18004068D
0x18004066b  mov     rcx, [rsi+118h]
0x180040672  mov     eax, ebp
0x180040674  add     rax, rax
0x180040677  mov     rcx, [rcx+rax*8]; Sid
0x18004067b  call    cs:__imp_RtlLengthSid
0x180040681  add     edi, eax
0x180040683  inc     ebp
0x180040685  cmp     ebp, [rsi+110h]
0x18004068b  jb      short loc_18004066B
0x18004068d  mov     ebp, dword ptr [rsp+58h+Size]
0x180040691  test    [rsi+0A8h], r15d
0x180040698  jz      short loc_1800406E0
0x18004069a  mov     r15d, [rsi+128h]
0x1800406a1  test    r15d, r15d
0x1800406a4  jz      short loc_1800406DD
0x1800406a6  cmp     [rsi+130h], r12
0x1800406ad  jz      short loc_1800406D3
0x1800406af  cmp     [rsi+120h], r12
0x1800406b6  jz      short loc_1800406D3
0x1800406b8  mov     rcx, [rsi+120h]; Sid
0x1800406bf  add     ebx, r15d
0x1800406c2  call    cs:__imp_RtlLengthSid
0x1800406c8  add     eax, 4
0x1800406cb  imul    eax, r15d
0x1800406cf  add     edi, eax
0x1800406d1  jmp     short loc_1800406E0
0x1800406d3  mov     ebx, 0C000000Dh
0x1800406d8  jmp     loc_1800409C6
0x1800406dd  add     ebx, r15d
0x1800406e0  lea     r15, [rsi+94h]
0x1800406e7  cmp     [r15], r12d
0x1800406ea  jz      short loc_180040708
0x1800406ec  lea     r12, [rsi+0E0h]
0x1800406f3  mov     rcx, [r12]; Sid
0x1800406f7  call    cs:__imp_RtlLengthSid
0x1800406fd  mov     r13, r15
0x180040700  lea     ecx, [rax+4]
0x180040703  lea     ecx, [rdi+rcx*2]
0x180040706  jmp     short loc_180040732
0x180040708  cmp     [rsi+110h], r12d
0x18004070f  jbe     loc_1800409C1
0x180040715  lea     r12, [rsi+0E0h]
0x18004071c  mov     rcx, [r12]; Sid
0x180040720  call    cs:__imp_RtlLengthSid
0x180040726  lea     r13, [rsi+94h]
0x18004072d  lea     ecx, [rax+4]
0x180040730  add     ecx, edi
0x180040732  mov     eax, ebx
0x180040734  shl     eax, 4
0x180040737  add     ecx, eax
0x180040739  lea     edi, [rcx-10h]
0x18004073c  cmp     [rsp+58h+Src], r14
0x180040741  jz      short loc_180040758
0x180040743  test    ebp, ebp
0x180040745  jz      short loc_18004075B
0x180040747  lea     edi, [rbp+3]
0x18004074a  and     edi, 0FFFFFFFCh
0x18004074d  lea     rbp, [rsi+0E0h]
0x180040754  add     edi, ecx
0x180040756  jmp     short loc_18004075E
0x180040758  mov     r13, r15
0x18004075b  mov     rbp, r12
0x18004075e  mov     rax, cs:qword_180088238
0x180040765  mov     ecx, edi
0x180040767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004076c  mov     r14, rax
0x18004076f  test    rax, rax
0x180040772  jnz     short loc_18004077E
0x180040774  mov     eax, 0C0000017h
0x180040779  jmp     loc_1800409EF
0x18004077e  mov     r8d, edi; Size
0x180040781  xor     edx, edx; Val
0x180040783  mov     rcx, r14; void *
0x180040786  call    memset_0
0x18004078b  lea     rcx, [r14+58h]
0x18004078f  mov     eax, ebx
0x180040791  shl     rax, 4
0x180040795  lea     r15, [rcx+8]
0x180040799  mov     [r14+18h], rcx
0x18004079d  add     r15, rax
0x1800407a0  xor     edi, edi
0x1800407a2  mov     [rcx], edi
0x1800407a4  mov     eax, [rsi+10h]
0x1800407a7  mov     rcx, [rsp+58h+Src]
0x1800407ac  mov     [r14], eax
0x1800407af  mov     eax, [rsi+14h]
0x1800407b2  mov     [r14+4], eax
0x1800407b6  test    rcx, rcx
0x1800407b9  jz      short loc_1800407EF
0x1800407bb  mov     eax, dword ptr [rsp+58h+Size]
0x1800407bf  test    eax, eax
0x1800407c1  jz      short loc_1800407F2
0x1800407c3  mov     [r14+40h], r15
0x1800407c7  lea     rdi, [r15+10h]
0x1800407cb  mov     rdx, rcx; Src
0x1800407ce  mov     [r15+8], rdi
0x1800407d2  mov     [r15], eax
0x1800407d5  mov     rcx, rdi; void *
0x1800407d8  mov     r8d, eax; Size
0x1800407db  lea     r15, [rax+3]
0x1800407df  call    memcpy_0
0x1800407e4  and     r15, 0FFFFFFFFFFFFFFFCh
0x1800407e8  add     r15, rdi
0x1800407eb  xor     edi, edi
0x1800407ed  jmp     short loc_1800407F2
0x1800407ef  mov     rbp, r12
0x1800407f2  cmp     [r13+0], edi
0x1800407f6  jz      short loc_180040811
0x1800407f8  mov     [r14+8], r15
0x1800407fc  mov     rcx, r15; Sid
0x1800407ff  mov     r8d, [r13+0]; unsigned int
0x180040803  mov     rdx, [rbp+0]; SourceSid
0x180040807  call    ?NlpCopyDomainRelativeSid@@YAKPEAX0K@Z; NlpCopyDomainRelativeSid(void *,void *,ulong)
0x18004080c  mov     eax, eax
0x18004080e  add     r15, rax
0x180040811  mov     [r14+20h], r15
0x180040815  mov     rcx, r15; Sid
0x180040818  mov     r8d, [rsi+98h]; unsigned int
0x18004081f  mov     rdx, [rbp+0]; SourceSid
0x180040823  call    ?NlpCopyDomainRelativeSid@@YAKPEAX0K@Z; NlpCopyDomainRelativeSid(void *,void *,ulong)
0x180040828  mov     eax, eax
0x18004082a  mov     ebx, edi
0x18004082c  add     r15, rax
0x18004082f  cmp     [rsi+9Ch], edi
0x180040835  jbe     short loc_18004088F
0x180040837  mov     rdx, [r14+18h]
0x18004083b  mov     rax, [rsi+0A0h]
0x180040842  mov     r9d, ebx
0x180040845  mov     ecx, [rdx]
0x180040847  inc     rcx
0x18004084a  mov     eax, [rax+r9*8+4]
0x18004084f  add     rcx, rcx
0x180040852  mov     [rdx+rcx*8], eax
0x180040855  mov     rcx, [r14+18h]
0x180040859  mov     eax, [rcx]
0x18004085b  add     rax, rax
0x18004085e  mov     [rcx+rax*8+8], r15
0x180040863  mov     rcx, r15; Sid
0x180040866  mov     r8, [rsi+0A0h]
0x18004086d  mov     rdx, [rbp+0]; SourceSid
0x180040871  mov     r8d, [r8+r9*8]; unsigned int
0x180040875  call    ?NlpCopyDomainRelativeSid@@YAKPEAX0K@Z; NlpCopyDomainRelativeSid(void *,void *,ulong)
0x18004087a  mov     eax, eax
0x18004087c  inc     ebx
0x18004087e  add     r15, rax
0x180040881  mov     rax, [r14+18h]
0x180040885  inc     dword ptr [rax]
0x180040887  cmp     ebx, [rsi+9Ch]
0x18004088d  jb      short loc_180040837
0x18004088f  test    byte ptr [rsi+0A8h], 20h
0x180040896  jz      loc_18004094A
0x18004089c  mov     ebp, edi
0x18004089e  cmp     [r14+8], rdi
0x1800408a2  jnz     short loc_1800408D7
0x1800408a4  mov     [r14+8], r15
0x1800408a8  mov     rcx, [rsi+118h]
0x1800408af  mov     rcx, [rcx]; Sid
0x1800408b2  call    cs:__imp_RtlLengthSid
0x1800408b8  mov     r8, [rsi+118h]
0x1800408bf  mov     rdx, r15; DestinationSid
0x1800408c2  mov     ecx, eax; DestinationSidLength
0x1800408c4  mov     ebx, eax
0x1800408c6  mov     r8, [r8]; SourceSid
0x1800408c9  call    cs:__imp_RtlCopySid
0x1800408cf  add     r15, rbx
0x1800408d2  mov     ebp, 1
0x1800408d7  cmp     ebp, [rsi+110h]
0x1800408dd  jnb     short loc_18004094A
0x1800408df  mov     rax, [rsi+118h]
0x1800408e6  mov     rdx, [r14+18h]
0x1800408ea  mov     edi, ebp
0x1800408ec  add     rdi, rdi
0x1800408ef  mov     ecx, [rdx]
0x1800408f1  inc     rcx
0x1800408f4  mov     eax, [rax+rdi*8+8]
0x1800408f8  add     rcx, rcx
0x1800408fb  mov     [rdx+rcx*8], eax
0x1800408fe  mov     rcx, [r14+18h]
0x180040902  mov     eax, [rcx]
0x180040904  add     rax, rax
0x180040907  mov     [rcx+rax*8+8], r15
0x18004090c  mov     rcx, [rsi+118h]
0x180040913  mov     rcx, [rcx+rdi*8]; Sid
0x180040917  call    cs:__imp_RtlLengthSid
0x18004091d  mov     r8, [rsi+118h]
0x180040924  mov     rdx, r15; DestinationSid
0x180040927  mov     ecx, eax; DestinationSidLength
0x180040929  mov     ebx, eax
0x18004092b  mov     r8, [r8+rdi*8]; SourceSid
0x18004092f  call    cs:__imp_RtlCopySid
0x180040935  mov     rax, [r14+18h]
0x180040939  add     r15, rbx
0x18004093c  inc     ebp
0x18004093e  inc     dword ptr [rax]
0x180040940  cmp     ebp, [rsi+110h]
0x180040946  jb      short loc_1800408DF
0x180040948  xor     edi, edi
0x18004094a  test    dword ptr [rsi+0A8h], 200h
0x180040954  jz      short loc_1800409BB
0x180040956  mov     ebx, edi
0x180040958  cmp     [rsi+128h], edi
0x18004095e  jbe     short loc_1800409BB
0x180040960  mov     rdx, [r14+18h]
0x180040964  mov     rax, [rsi+130h]
0x18004096b  mov     r9d, ebx
0x18004096e  mov     ecx, [rdx]
0x180040970  inc     rcx
0x180040973  mov     eax, [rax+r9*8+4]
0x180040978  add     rcx, rcx
0x18004097b  mov     [rdx+rcx*8], eax
0x18004097e  mov     rcx, [r14+18h]
0x180040982  mov     eax, [rcx]
0x180040984  add     rax, rax
0x180040987  mov     [rcx+rax*8+8], r15
0x18004098c  mov     rcx, r15; Sid
0x18004098f  mov     r8, [rsi+130h]
0x180040996  mov     rdx, [rsi+120h]; SourceSid
0x18004099d  mov     r8d, [r8+r9*8]; unsigned int
0x1800409a1  call    ?NlpCopyDomainRelativeSid@@YAKPEAX0K@Z; NlpCopyDomainRelativeSid(void *,void *,ulong)
0x1800409a6  mov     eax, eax
0x1800409a8  inc     ebx
0x1800409aa  add     r15, rax
0x1800409ad  mov     rax, [r14+18h]
0x1800409b1  inc     dword ptr [rax]
0x1800409b3  cmp     ebx, [rsi+128h]
0x1800409b9  jb      short loc_180040960
0x1800409bb  cmp     [r14+8], rdi
0x1800409bf  jnz     short loc_1800409D9
0x1800409c1  mov     ebx, 0C0000250h
0x1800409c6  mov     rax, cs:qword_180088240
0x1800409cd  mov     rcx, r14
0x1800409d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800409d5  mov     eax, ebx
0x1800409d7  jmp     short loc_1800409EF
0x1800409d9  mov     rax, [rsp+58h+arg_18]
0x1800409de  mov     [r14+28h], rdi
0x1800409e2  mov     [r14+30h], rdi
0x1800409e6  mov     [r14+38h], rdi
0x1800409ea  mov     [rax], r14
0x1800409ed  xor     eax, eax
0x1800409ef  mov     rbx, [rsp+58h+arg_0]
0x1800409f4  add     rsp, 20h
0x1800409f8  pop     r15
0x1800409fa  pop     r14
0x1800409fc  pop     r13
0x1800409fe  pop     r12
0x180040a00  pop     rdi
0x180040a01  pop     rsi
0x180040a02  pop     rbp
0x180040a03  retn
```
