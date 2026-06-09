# CMSMQTriggerSet::GetQueueFormatName(wchar_t const *,wchar_t * *)

- ea: `0x1800119a8`
- end: `0x180011a8e`
- name: `?GetQueueFormatName@CMSMQTriggerSet@@AEAAJPEB_WPEAPEA_W@Z`
- size: `230`
- prototype: `__int64 __fastcall(CMSMQTriggerSet *this, const wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012d10`

## callees

- `0x1800119a8`
- `0x180013b2c`
- `0x180014ae8`

## import_xrefs

- `msvcrt!free` at `0x180011a23`
- `msvcrt!free` at `0x180011a4d`
- `msvcrt!free` at `0x180011a5d`
- `msvcrt!free` at `0x180011a6d`
- `msvcrt!free` at `0x180011a23`
- `msvcrt!free` at `0x180011a4d`
- `msvcrt!free` at `0x180011a5d`
- `msvcrt!free` at `0x180011a6d`
- `mqrt!MQPathNameToFormatName` at `0x180011a37`
- `mqrt!MQPathNameToFormatName` at `0x180011a37`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQTriggerSet::GetQueueFormatName(CMSMQTriggerSet *this, const wchar_t *a2, wchar_t **a3)
{
  unsigned __int64 v5; // rax
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  HRESULT v8; // eax
  unsigned int v9; // esi
  CMSMQTriggerSet *dwFormatNameLength; // [rsp+40h] [rbp+8h] BYREF
  void *Block; // [rsp+48h] [rbp+10h] BYREF

  dwFormatNameLength = this;
  if ( !a2 || !a3 )
    return 3222142982LL;
  *a3 = 0;
  LODWORD(dwFormatNameLength) = 256;
  Block = 0;
  do
  {
    AP<wchar_t>::free(&Block);
    v5 = 2LL * (unsigned int)dwFormatNameLength;
    if ( !is_mul_ok((unsigned int)dwFormatNameLength, 2u) )
      v5 = -1;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v6 = (wchar_t *)MmAllocate(v5);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180011A68);
        free(Block);
        return 3222143015LL;
      }
    }
    v7 = v6;
    Block = v6;
    if ( !v6 )
    {
      free(0);
      return 3222143015LL;
    }
    v8 = MQPathNameToFormatName(a2, v6, (LPDWORD)&dwFormatNameLength);
    v9 = v8;
  }
  while ( v8 == -1072824289 );
  if ( v8 >= 0 )
  {
    *a3 = v7;
    free(0);
    return 0;
  }
  else
  {
    free(v7);
    return v9;
  }
}

```

## disassembly

```asm
0x1800119a8  mov     rax, rsp
0x1800119ab  mov     [rax+18h], rbx
0x1800119af  mov     [rax+8], rcx
0x1800119b3  push    rsi
0x1800119b4  push    rdi
0x1800119b5  push    r14
0x1800119b7  sub     rsp, 20h
0x1800119bb  mov     rdi, r8
0x1800119be  mov     r14, rdx
0x1800119c1  test    rdx, rdx
0x1800119c4  jz      loc_180011A7B
0x1800119ca  test    r8, r8
0x1800119cd  jz      loc_180011A7B
0x1800119d3  mov     qword ptr [r8], 0
0x1800119da  mov     dword ptr [rax+8], 100h
0x1800119e1  mov     qword ptr [rax+10h], 0
0x1800119e9  lea     rcx, [rsp+38h+Block]
0x1800119ee  call    ?free@?$AP@_W@@QEAAXXZ; AP<wchar_t>::free(void)
0x1800119f3  nop
0x1800119f4  mov     ecx, dword ptr [rsp+38h+dwFormatNameLength]
0x1800119f8  mov     eax, 2
0x1800119fd  mul     rcx
0x180011a00  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180011a07  cmovb   rax, rcx
0x180011a0b  mov     rcx, rax; unsigned __int64
0x180011a0e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011a13  mov     rbx, rax
0x180011a16  mov     [rsp+38h+Block], rax
0x180011a1b  test    rbx, rbx
0x180011a1e  jnz     short loc_180011A2C
0x180011a20  mov     rcx, rbx; Block
0x180011a23  call    cs:__imp_free
0x180011a29  nop
0x180011a2a  jmp     short loc_180011A74
0x180011a2c  lea     r8, [rsp+38h+dwFormatNameLength]; lpdwFormatNameLength
0x180011a31  mov     rdx, rbx; lpwcsFormatName
0x180011a34  mov     rcx, r14; lpwcsPathName
0x180011a37  call    cs:__imp_MQPathNameToFormatName
0x180011a3d  mov     esi, eax
0x180011a3f  cmp     eax, 0C00E001Fh
0x180011a44  jz      short loc_1800119E9
0x180011a46  test    eax, eax
0x180011a48  jns     short loc_180011A58
0x180011a4a  mov     rcx, rbx; Block
0x180011a4d  call    cs:__imp_free
0x180011a53  nop
0x180011a54  mov     eax, esi
0x180011a56  jmp     short loc_180011A80
0x180011a58  mov     [rdi], rbx
0x180011a5b  xor     ecx, ecx; Block
0x180011a5d  call    cs:__imp_free
0x180011a63  nop
0x180011a64  xor     eax, eax
0x180011a66  jmp     short loc_180011A80
0x180011a68  mov     rcx, [rsp+38h+Block]; Block
0x180011a6d  call    cs:__imp_free
0x180011a73  nop
0x180011a74  mov     eax, 0C00E0027h
0x180011a79  jmp     short loc_180011A80
0x180011a7b  mov     eax, 0C00E0006h
0x180011a80  mov     rbx, [rsp+38h+arg_10]
0x180011a85  add     rsp, 20h
0x180011a89  pop     r14
0x180011a8b  pop     rdi
0x180011a8c  pop     rsi
0x180011a8d  retn
```
