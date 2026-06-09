# PopulateMetadata<CHANNEL_ENTRY>(std::vector<std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>,std::allocator<std::unique_ptr<CHANNEL_ENTRY,std::default_delete<CHANNEL_ENTRY>>>> &,_EVENT_FIELD_TYPE,TDH_MOF_INFO *)

- ea: `0x180024a8c`
- end: `0x180024c49`
- name: `??$PopulateMetadata@VCHANNEL_ENTRY@@@@YAKAEAV?$vector@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VCHANNEL_ENTRY@@U?$default_delete@VCHANNEL_ENTRY@@@std@@@std@@@2@@std@@W4_EVENT_FIELD_TYPE@@PEAUTDH_MOF_INFO@@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025b8c`

## callees

- `0x18000b9d0`
- `0x180012f34`
- `0x1800137e8`
- `0x180018350`
- `0x180024a8c`
- `0x180037138`
- `0x180037160`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024aea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024b6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024bd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024aea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024b6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024bd4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ad9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024bc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ad9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024bc3`

## pseudocode

```c
__int64 __fastcall PopulateMetadata<CHANNEL_ENTRY>(wchar_t ***a1, __int64 a2, __int64 a3)
{
  struct FIELD_INFOLIST *v4; // r13
  unsigned int *v5; // rdi
  unsigned __int64 v6; // rcx
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  unsigned int v9; // esi
  unsigned __int64 v10; // r14
  wchar_t **i; // rbx
  __int64 v12; // rbp
  __int64 v13; // r15
  unsigned int v14; // edi
  HANDLE v15; // rax
  wchar_t *v16; // rax
  wchar_t *v17; // r8
  unsigned int v18; // edi
  HANDLE v19; // rax
  LPVOID v20; // rax
  wchar_t *TranslationValue; // rax
  wchar_t *v22; // r9
  wchar_t *v23; // rax
  SIZE_T dwBytes; // [rsp+70h] [rbp+8h] BYREF

  v4 = (struct FIELD_INFOLIST *)(a3 + 6224);
  v5 = (unsigned int *)(a3 + 6232);
  *(_DWORD *)(a3 + 6232) = 0;
  *(_QWORD *)(a3 + 6224) = 0;
  v6 = a1[1] - *a1;
  dwBytes = 0;
  if ( (int)ULongLongMult(v6, 0x28u, &dwBytes) < 0 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, dwBytes);
  *(_QWORD *)v4 = v8;
  if ( !v8 )
    return 8;
  if ( (int)ULongLongToULong(a1[1] - *a1, v5) < 0 )
  {
LABEL_16:
    v9 = 8;
    TdhpClearFieldInfoList(v4);
  }
  else
  {
    v9 = 0;
    v10 = 0;
    for ( i = *a1; v10 < *v5 && i != a1[1]; ++i )
    {
      v12 = 5 * v10;
      v13 = *(_QWORD *)v4;
      if ( *((_QWORD *)*i + 2) )
      {
        v14 = 2 * *((_DWORD *)*i + 4) + 2;
        *(_DWORD *)(v13 + 40 * v10 + 16) = v14;
        v15 = GetProcessHeap();
        v16 = (wchar_t *)HeapAlloc(v15, 8u, v14);
        *(_QWORD *)(v13 + 40 * v10) = v16;
        if ( !v16 )
          goto LABEL_16;
        v17 = *i;
        if ( *((_QWORD *)*i + 3) > 7u )
          v17 = *(wchar_t **)v17;
        StringCbCopyW(v16, *(unsigned int *)(v13 + 40 * v10 + 16), v17);
      }
      if ( *((_QWORD *)*i + 23) )
      {
        *(_DWORD *)(v13 + 40 * v10 + 24) = 0;
        v18 = 2 * STRING_ENTRY::FirstTranslationValueLength(*((STRING_ENTRY **)*i + 23)) + 2;
        *(_DWORD *)(v13 + 40 * v10 + 20) = v18;
        v19 = GetProcessHeap();
        v20 = HeapAlloc(v19, 8u, v18);
        *(_QWORD *)(v13 + 40 * v10 + 8) = v20;
        if ( !v20 )
          goto LABEL_16;
        TranslationValue = (wchar_t *)STRING_ENTRY::FirstTranslationValue(*((STRING_ENTRY **)*i + 23));
        StringCbCopyW(v22, *(unsigned int *)(v13 + 40 * v10 + 20), TranslationValue);
      }
      v23 = *i;
      v5 = (unsigned int *)((char *)v4 + 8);
      ++v10;
      *(_QWORD *)(v13 + 8 * v12 + 32) = v23[52];
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180024a8c  push    rbx
0x180024a8e  push    rbp
0x180024a8f  push    rsi
0x180024a90  push    rdi
0x180024a91  push    r12
0x180024a93  push    r13
0x180024a95  push    r14
0x180024a97  push    r15
0x180024a99  sub     rsp, 28h
0x180024a9d  mov     r12, rcx
0x180024aa0  lea     r13, [r8+1850h]
0x180024aa7  xor     ebx, ebx
0x180024aa9  lea     rdi, [r13+8]
0x180024aad  mov     [rdi], ebx
0x180024aaf  lea     r8, [rsp+68h+dwBytes]; unsigned __int64 *
0x180024ab4  mov     [r13+0], rbx
0x180024ab8  mov     rcx, [rcx+8]
0x180024abc  sub     rcx, [r12]
0x180024ac0  lea     edx, [rbx+28h]; unsigned __int64
0x180024ac3  sar     rcx, 3; unsigned __int64
0x180024ac7  mov     [rsp+68h+dwBytes], rbx
0x180024acc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180024ad1  test    eax, eax
0x180024ad3  js      loc_180024C33
0x180024ad9  call    cs:__imp_GetProcessHeap
0x180024adf  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x180024ae4  lea     edx, [rbx+8]; dwFlags
0x180024ae7  mov     rcx, rax; hHeap
0x180024aea  call    cs:__imp_HeapAlloc
0x180024af0  mov     [r13+0], rax
0x180024af4  test    rax, rax
0x180024af7  jz      loc_180024C33
0x180024afd  mov     rcx, [r12+8]
0x180024b02  mov     rdx, rdi; unsigned int *
0x180024b05  sub     rcx, [r12]
0x180024b09  sar     rcx, 3; unsigned __int64
0x180024b0d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180024b12  test    eax, eax
0x180024b14  js      loc_180024C22
0x180024b1a  mov     esi, ebx
0x180024b1c  mov     r14d, ebx
0x180024b1f  mov     rbx, [r12]
0x180024b23  mov     eax, [rdi]
0x180024b25  cmp     r14, rax
0x180024b28  jnb     loc_180024C2F
0x180024b2e  cmp     rbx, [r12+8]
0x180024b33  jz      loc_180024C2F
0x180024b39  mov     rax, [rbx]
0x180024b3c  lea     rbp, [r14+r14*4]
0x180024b40  mov     r15, [r13+0]
0x180024b44  cmp     [rax+10h], rsi
0x180024b48  jz      short loc_180024B97
0x180024b4a  mov     eax, [rax+10h]
0x180024b4d  lea     edi, ds:2[rax*2]
0x180024b54  mov     [r15+rbp*8+10h], edi
0x180024b59  call    cs:__imp_GetProcessHeap
0x180024b5f  mov     r8d, edi; dwBytes
0x180024b62  mov     edx, 8; dwFlags
0x180024b67  mov     rcx, rax; hHeap
0x180024b6a  call    cs:__imp_HeapAlloc
0x180024b70  mov     [r15+rbp*8], rax
0x180024b74  test    rax, rax
0x180024b77  jz      loc_180024C22
0x180024b7d  mov     r8, [rbx]
0x180024b80  cmp     qword ptr [r8+18h], 7
0x180024b85  jbe     short loc_180024B8A
0x180024b87  mov     r8, [r8]; wchar_t *
0x180024b8a  mov     edx, [r15+rbp*8+10h]; unsigned __int64
0x180024b8f  mov     rcx, rax; wchar_t *
0x180024b92  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024b97  mov     rax, [rbx]
0x180024b9a  cmp     [rax+0B8h], rsi
0x180024ba1  jz      short loc_180024C06
0x180024ba3  mov     [r15+rbp*8+18h], esi
0x180024ba8  mov     rcx, [rbx]
0x180024bab  mov     rcx, [rcx+0B8h]; this
0x180024bb2  call    ?FirstTranslationValueLength@STRING_ENTRY@@QEBA_KXZ; STRING_ENTRY::FirstTranslationValueLength(void)
0x180024bb7  lea     edi, ds:2[rax*2]
0x180024bbe  mov     [r15+rbp*8+14h], edi
0x180024bc3  call    cs:__imp_GetProcessHeap
0x180024bc9  mov     r8d, edi; dwBytes
0x180024bcc  mov     edx, 8; dwFlags
0x180024bd1  mov     rcx, rax; hHeap
0x180024bd4  call    cs:__imp_HeapAlloc
0x180024bda  mov     [r15+rbp*8+8], rax
0x180024bdf  mov     r9, rax
0x180024be2  test    rax, rax
0x180024be5  jz      short loc_180024C22
0x180024be7  mov     rcx, [rbx]
0x180024bea  mov     rcx, [rcx+0B8h]; this
0x180024bf1  call    ?FirstTranslationValue@STRING_ENTRY@@QEBAPEB_WXZ; STRING_ENTRY::FirstTranslationValue(void)
0x180024bf6  mov     edx, [r15+rbp*8+14h]; unsigned __int64
0x180024bfb  mov     r8, rax; wchar_t *
0x180024bfe  mov     rcx, r9; wchar_t *
0x180024c01  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024c06  mov     rax, [rbx]
0x180024c09  lea     rdi, [r13+8]
0x180024c0d  inc     r14
0x180024c10  add     rbx, 8
0x180024c14  movzx   ecx, word ptr [rax+68h]
0x180024c18  mov     [r15+rbp*8+20h], rcx
0x180024c1d  jmp     loc_180024B23
0x180024c22  mov     esi, 8
0x180024c27  mov     rcx, r13; struct FIELD_INFOLIST *
0x180024c2a  call    ?TdhpClearFieldInfoList@@YAXPEAUFIELD_INFOLIST@@@Z; TdhpClearFieldInfoList(FIELD_INFOLIST *)
0x180024c2f  mov     eax, esi
0x180024c31  jmp     short loc_180024C38
0x180024c33  mov     eax, 8
0x180024c38  add     rsp, 28h
0x180024c3c  pop     r15
0x180024c3e  pop     r14
0x180024c40  pop     r13
0x180024c42  pop     r12
0x180024c44  pop     rdi
0x180024c45  pop     rsi
0x180024c46  pop     rbp
0x180024c47  pop     rbx
0x180024c48  retn
```
