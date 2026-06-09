# PopulateMetadata<TASK_ENTRY>(std::vector<std::unique_ptr<TASK_ENTRY,std::default_delete<TASK_ENTRY>>,std::allocator<std::unique_ptr<TASK_ENTRY,std::default_delete<TASK_ENTRY>>>> &,_EVENT_FIELD_TYPE,TDH_MOF_INFO *)

- ea: `0x1800251a8`
- end: `0x180025365`
- name: `??$PopulateMetadata@VTASK_ENTRY@@@@YAKAEAV?$vector@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@V?$allocator@V?$unique_ptr@VTASK_ENTRY@@U?$default_delete@VTASK_ENTRY@@@std@@@std@@@2@@std@@W4_EVENT_FIELD_TYPE@@PEAUTDH_MOF_INFO@@@Z`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180025b8c`

## callees

- `0x18000b9d0`
- `0x180012f34`
- `0x1800137e8`
- `0x180018350`
- `0x1800251a8`
- `0x180037138`
- `0x180037160`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025206`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025286`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800252f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025206`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025286`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800252f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800251f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800251f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252df`

## pseudocode

```c
__int64 __fastcall PopulateMetadata<TASK_ENTRY>(wchar_t ***a1, __int64 a2, __int64 a3)
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

  v4 = (struct FIELD_INFOLIST *)(a3 + 6240);
  v5 = (unsigned int *)(a3 + 6248);
  *(_DWORD *)(a3 + 6248) = 0;
  *(_QWORD *)(a3 + 6240) = 0;
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
      if ( *((_QWORD *)*i + 16) )
      {
        *(_DWORD *)(v13 + 40 * v10 + 24) = 0;
        v18 = 2 * STRING_ENTRY::FirstTranslationValueLength(*((STRING_ENTRY **)*i + 16)) + 2;
        *(_DWORD *)(v13 + 40 * v10 + 20) = v18;
        v19 = GetProcessHeap();
        v20 = HeapAlloc(v19, 8u, v18);
        *(_QWORD *)(v13 + 40 * v10 + 8) = v20;
        if ( !v20 )
          goto LABEL_16;
        TranslationValue = (wchar_t *)STRING_ENTRY::FirstTranslationValue(*((STRING_ENTRY **)*i + 16));
        StringCbCopyW(v22, *(unsigned int *)(v13 + 40 * v10 + 20), TranslationValue);
      }
      v23 = *i;
      v5 = (unsigned int *)((char *)v4 + 8);
      ++v10;
      *(_QWORD *)(v13 + 8 * v12 + 32) = v23[16];
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800251a8  push    rbx
0x1800251aa  push    rbp
0x1800251ab  push    rsi
0x1800251ac  push    rdi
0x1800251ad  push    r12
0x1800251af  push    r13
0x1800251b1  push    r14
0x1800251b3  push    r15
0x1800251b5  sub     rsp, 28h
0x1800251b9  mov     r12, rcx
0x1800251bc  lea     r13, [r8+1860h]
0x1800251c3  xor     ebx, ebx
0x1800251c5  lea     rdi, [r13+8]
0x1800251c9  mov     [rdi], ebx
0x1800251cb  lea     r8, [rsp+68h+dwBytes]; unsigned __int64 *
0x1800251d0  mov     [r13+0], rbx
0x1800251d4  mov     rcx, [rcx+8]
0x1800251d8  sub     rcx, [r12]
0x1800251dc  lea     edx, [rbx+28h]; unsigned __int64
0x1800251df  sar     rcx, 3; unsigned __int64
0x1800251e3  mov     [rsp+68h+dwBytes], rbx
0x1800251e8  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800251ed  test    eax, eax
0x1800251ef  js      loc_18002534F
0x1800251f5  call    cs:__imp_GetProcessHeap
0x1800251fb  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x180025200  lea     edx, [rbx+8]; dwFlags
0x180025203  mov     rcx, rax; hHeap
0x180025206  call    cs:__imp_HeapAlloc
0x18002520c  mov     [r13+0], rax
0x180025210  test    rax, rax
0x180025213  jz      loc_18002534F
0x180025219  mov     rcx, [r12+8]
0x18002521e  mov     rdx, rdi; unsigned int *
0x180025221  sub     rcx, [r12]
0x180025225  sar     rcx, 3; unsigned __int64
0x180025229  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002522e  test    eax, eax
0x180025230  js      loc_18002533E
0x180025236  mov     esi, ebx
0x180025238  mov     r14d, ebx
0x18002523b  mov     rbx, [r12]
0x18002523f  mov     eax, [rdi]
0x180025241  cmp     r14, rax
0x180025244  jnb     loc_18002534B
0x18002524a  cmp     rbx, [r12+8]
0x18002524f  jz      loc_18002534B
0x180025255  mov     rax, [rbx]
0x180025258  lea     rbp, [r14+r14*4]
0x18002525c  mov     r15, [r13+0]
0x180025260  cmp     [rax+10h], rsi
0x180025264  jz      short loc_1800252B3
0x180025266  mov     eax, [rax+10h]
0x180025269  lea     edi, ds:2[rax*2]
0x180025270  mov     [r15+rbp*8+10h], edi
0x180025275  call    cs:__imp_GetProcessHeap
0x18002527b  mov     r8d, edi; dwBytes
0x18002527e  mov     edx, 8; dwFlags
0x180025283  mov     rcx, rax; hHeap
0x180025286  call    cs:__imp_HeapAlloc
0x18002528c  mov     [r15+rbp*8], rax
0x180025290  test    rax, rax
0x180025293  jz      loc_18002533E
0x180025299  mov     r8, [rbx]
0x18002529c  cmp     qword ptr [r8+18h], 7
0x1800252a1  jbe     short loc_1800252A6
0x1800252a3  mov     r8, [r8]; wchar_t *
0x1800252a6  mov     edx, [r15+rbp*8+10h]; unsigned __int64
0x1800252ab  mov     rcx, rax; wchar_t *
0x1800252ae  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800252b3  mov     rax, [rbx]
0x1800252b6  cmp     [rax+80h], rsi
0x1800252bd  jz      short loc_180025322
0x1800252bf  mov     [r15+rbp*8+18h], esi
0x1800252c4  mov     rcx, [rbx]
0x1800252c7  mov     rcx, [rcx+80h]; this
0x1800252ce  call    ?FirstTranslationValueLength@STRING_ENTRY@@QEBA_KXZ; STRING_ENTRY::FirstTranslationValueLength(void)
0x1800252d3  lea     edi, ds:2[rax*2]
0x1800252da  mov     [r15+rbp*8+14h], edi
0x1800252df  call    cs:__imp_GetProcessHeap
0x1800252e5  mov     r8d, edi; dwBytes
0x1800252e8  mov     edx, 8; dwFlags
0x1800252ed  mov     rcx, rax; hHeap
0x1800252f0  call    cs:__imp_HeapAlloc
0x1800252f6  mov     [r15+rbp*8+8], rax
0x1800252fb  mov     r9, rax
0x1800252fe  test    rax, rax
0x180025301  jz      short loc_18002533E
0x180025303  mov     rcx, [rbx]
0x180025306  mov     rcx, [rcx+80h]; this
0x18002530d  call    ?FirstTranslationValue@STRING_ENTRY@@QEBAPEB_WXZ; STRING_ENTRY::FirstTranslationValue(void)
0x180025312  mov     edx, [r15+rbp*8+14h]; unsigned __int64
0x180025317  mov     r8, rax; wchar_t *
0x18002531a  mov     rcx, r9; wchar_t *
0x18002531d  call    ?StringCbCopyW@@YAJPEA_W_KPEB_W@Z; StringCbCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180025322  mov     rax, [rbx]
0x180025325  lea     rdi, [r13+8]
0x180025329  inc     r14
0x18002532c  add     rbx, 8
0x180025330  movzx   ecx, word ptr [rax+20h]
0x180025334  mov     [r15+rbp*8+20h], rcx
0x180025339  jmp     loc_18002523F
0x18002533e  mov     esi, 8
0x180025343  mov     rcx, r13; struct FIELD_INFOLIST *
0x180025346  call    ?TdhpClearFieldInfoList@@YAXPEAUFIELD_INFOLIST@@@Z; TdhpClearFieldInfoList(FIELD_INFOLIST *)
0x18002534b  mov     eax, esi
0x18002534d  jmp     short loc_180025354
0x18002534f  mov     eax, 8
0x180025354  add     rsp, 28h
0x180025358  pop     r15
0x18002535a  pop     r14
0x18002535c  pop     r13
0x18002535e  pop     r12
0x180025360  pop     rdi
0x180025361  pop     rsi
0x180025362  pop     rbp
0x180025363  pop     rbx
0x180025364  retn
```
