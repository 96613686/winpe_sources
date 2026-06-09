# ExecutionContext_DuplicateCurrentContext

- ea: `0x180009590`
- end: `0x180009661`
- name: `ExecutionContext_DuplicateCurrentContext`
- size: `209`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009590`
- `0x180009c44`

## import_xrefs

- `msvcrt!malloc` at `0x1800095b6`
- `msvcrt!malloc` at `0x1800095b6`
- `msvcrt!free` at `0x18000963d`
- `msvcrt!free` at `0x180009646`
- `msvcrt!free` at `0x18000963d`
- `msvcrt!free` at `0x180009646`
- `msvcrt!_wcsdup` at `0x1800095ec`
- `msvcrt!_wcsdup` at `0x1800095ec`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180009620`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180009620`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009617`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180009617`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009611`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009611`

## pseudocode

```c
__int64 __fastcall ExecutionContext_DuplicateCurrentContext(_QWORD *a1)
{
  __int64 result; // rax
  wchar_t *v3; // rdi
  _OWORD *TLSContext; // rbp
  _OWORD *v5; // rax
  void *v6; // rbx
  const wchar_t *v7; // rcx
  wchar_t *v8; // rax

  if ( !a1 )
    return 4;
  v3 = 0;
  TLSContext = (_OWORD *)GetTLSContext();
  v5 = malloc(0x40u);
  v6 = v5;
  if ( v5 )
  {
    *v5 = *TLSContext;
    v5[1] = TLSContext[1];
    v5[2] = TLSContext[2];
    v5[3] = TLSContext[3];
    v7 = (const wchar_t *)*((_QWORD *)TLSContext + 6);
    if ( !v7 )
    {
LABEL_7:
      _InterlockedAdd64(*((volatile signed __int64 **)v6 + 1), 1u);
      EventActivityIdControl(1u, (LPGUID)v6 + 1);
      *((_DWORD *)v6 + 8) = GetThreadLocale();
      *((_DWORD *)v6 + 9) = GetThreadUILanguage();
      result = 0;
      *((_BYTE *)v6 + 56) = 1;
      *(_QWORD *)v6 = 1;
      *a1 = v6;
      return result;
    }
    v8 = _wcsdup(v7);
    v3 = v8;
    if ( v8 )
    {
      *((_QWORD *)v6 + 6) = v8;
      goto LABEL_7;
    }
  }
  free(v6);
  free(v3);
  result = 27;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180009590  push    rbx
0x180009592  push    rbp
0x180009593  push    rsi
0x180009594  push    rdi
0x180009595  sub     rsp, 28h
0x180009599  mov     rsi, rcx
0x18000959c  test    rcx, rcx
0x18000959f  jnz     short loc_1800095A9
0x1800095a1  lea     eax, [rcx+4]
0x1800095a4  jmp     loc_180009658
0x1800095a9  xor     edi, edi
0x1800095ab  call    GetTLSContext
0x1800095b0  lea     ecx, [rdi+40h]; Size
0x1800095b3  mov     rbp, rax
0x1800095b6  call    cs:__imp_malloc
0x1800095bc  mov     rbx, rax
0x1800095bf  test    rax, rax
0x1800095c2  jz      short loc_18000963A
0x1800095c4  movups  xmm0, xmmword ptr [rbp+0]
0x1800095c8  movups  xmmword ptr [rax], xmm0
0x1800095cb  movups  xmm1, xmmword ptr [rbp+10h]
0x1800095cf  movups  xmmword ptr [rax+10h], xmm1
0x1800095d3  movups  xmm0, xmmword ptr [rbp+20h]
0x1800095d7  movups  xmmword ptr [rax+20h], xmm0
0x1800095db  movups  xmm1, xmmword ptr [rbp+30h]
0x1800095df  movups  xmmword ptr [rax+30h], xmm1
0x1800095e3  mov     rcx, [rbp+30h]; String
0x1800095e7  test    rcx, rcx
0x1800095ea  jz      short loc_1800095FE
0x1800095ec  call    cs:__imp__wcsdup
0x1800095f2  mov     rdi, rax
0x1800095f5  test    rax, rax
0x1800095f8  jz      short loc_18000963A
0x1800095fa  mov     [rbx+30h], rax
0x1800095fe  mov     rax, [rbx+8]
0x180009602  mov     edi, 1
0x180009607  lock add [rax], rdi
0x18000960b  lea     rdx, [rbx+10h]; ActivityId
0x18000960f  mov     ecx, edi; ControlCode
0x180009611  call    cs:__imp_EventActivityIdControl
0x180009617  call    cs:__imp_GetThreadLocale
0x18000961d  mov     [rbx+20h], eax
0x180009620  call    cs:__imp_GetThreadUILanguage
0x180009626  movzx   eax, ax
0x180009629  mov     [rbx+24h], eax
0x18000962c  xor     eax, eax
0x18000962e  mov     [rbx+38h], dil
0x180009632  mov     [rbx], rdi
0x180009635  mov     [rsi], rbx
0x180009638  jmp     short loc_180009658
0x18000963a  mov     rcx, rbx; Block
0x18000963d  call    cs:__imp_free
0x180009643  mov     rcx, rdi; Block
0x180009646  call    cs:__imp_free
0x18000964c  mov     eax, 1Bh
0x180009651  mov     qword ptr [rsi], 0
0x180009658  add     rsp, 28h
0x18000965c  pop     rdi
0x18000965d  pop     rsi
0x18000965e  pop     rbp
0x18000965f  pop     rbx
0x180009660  retn
```
