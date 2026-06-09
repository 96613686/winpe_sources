# PoolKeyList::p_Add(ushort const *,_PregenParms const *)

- ea: `0x18001c9a8`
- end: `0x18001ca8f`
- name: `?p_Add@PoolKeyList@@AEAAJPEBGPEBU_PregenParms@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(PoolKeyList *this, NgcUtils *, const struct _PregenParms *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ca98`

## callees

- `0x18000b0fc`
- `0x180015288`
- `0x18001c9a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c9d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c9d3`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001c9e1`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18001c9e1`

## string_xrefs

- `0x18001c9f4`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`
- `0x18001ca62`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
__int64 __fastcall PoolKeyList::p_Add(PoolKeyList *this, NgcUtils *a2, const struct _PregenParms *a3)
{
  void *v5; // rcx
  SIZE_T v7; // rdx
  _QWORD *v8; // rax
  unsigned __int16 **v9; // r8
  _QWORD *v10; // rdx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // edi
  int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = *(void **)this;
  v7 = (unsigned int)(24 * (*((_DWORD *)this + 2) + 1));
  if ( v5 )
    v8 = LocalReAlloc(v5, v7, 2u);
  else
    v8 = LocalAlloc(0, v7);
  v10 = v8;
  if ( v8 )
  {
    v12 = *((unsigned int *)this + 2);
    *(_QWORD *)this = v10;
    v10[3 * v12] = 0;
    *(_QWORD *)(*(_QWORD *)this + 24LL * *((unsigned int *)this + 2) + 8) = a3;
    *(_BYTE *)(*(_QWORD *)this + 24LL * *((unsigned int *)this + 2) + 16) = 0;
    v13 = NgcUtils::DuplicateString(
            a2,
            (const unsigned __int16 *)(*(_QWORD *)this + 24LL * *((unsigned int *)this + 2)),
            v9);
    v14 = v13;
    if ( v13 >= 0 )
    {
      ++*((_DWORD *)this + 2);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B6,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
        (const char *)(unsigned int)v13,
        v15);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6AD,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
      (const char *)0x8007000ELL,
      v15);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001c9a8  mov     [rsp+arg_0], rbx
0x18001c9ad  mov     [rsp+arg_8], rsi
0x18001c9b2  push    rdi; int
0x18001c9b3  sub     rsp, 20h
0x18001c9b7  mov     rbx, rcx
0x18001c9ba  mov     rsi, rdx
0x18001c9bd  mov     rcx, [rcx]; hMem
0x18001c9c0  mov     rdi, r8
0x18001c9c3  mov     eax, [rbx+8]
0x18001c9c6  inc     eax
0x18001c9c8  lea     edx, [rax+rax*2]
0x18001c9cb  shl     edx, 3; uBytes
0x18001c9ce  test    rcx, rcx
0x18001c9d1  jnz     short loc_18001C9DB
0x18001c9d3  call    cs:__imp_LocalAlloc
0x18001c9d9  jmp     short loc_18001C9E7
0x18001c9db  mov     r8d, 2; uFlags
0x18001c9e1  call    cs:__imp_LocalReAlloc
0x18001c9e7  mov     rdx, rax
0x18001c9ea  test    rax, rax
0x18001c9ed  jnz     short loc_18001CA11
0x18001c9ef  mov     rcx, [rsp+28h]; this
0x18001c9f4  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001c9fb  mov     ebx, 8007000Eh
0x18001ca00  mov     edx, 6ADh; void *
0x18001ca05  mov     r9d, ebx; char *
0x18001ca08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca0d  mov     eax, ebx
0x18001ca0f  jmp     short loc_18001CA7F
0x18001ca11  mov     eax, [rbx+8]
0x18001ca14  mov     [rbx], rdx
0x18001ca17  lea     rcx, [rax+rax*2]
0x18001ca1b  mov     qword ptr [rdx+rcx*8], 0
0x18001ca23  mov     eax, [rbx+8]
0x18001ca26  lea     rcx, [rax+rax*2]
0x18001ca2a  mov     rax, [rbx]
0x18001ca2d  mov     [rax+rcx*8+8], rdi
0x18001ca32  mov     eax, [rbx+8]
0x18001ca35  lea     rcx, [rax+rax*2]
0x18001ca39  mov     rax, [rbx]
0x18001ca3c  mov     byte ptr [rax+rcx*8+10h], 0
0x18001ca41  mov     eax, [rbx+8]
0x18001ca44  lea     rcx, [rax+rax*2]
0x18001ca48  mov     rax, [rbx]
0x18001ca4b  lea     rdx, [rax+rcx*8]; unsigned __int16 *
0x18001ca4f  mov     rcx, rsi; this
0x18001ca52  call    ?DuplicateString@NgcUtils@@YAJPEBGPEAPEAG@Z; NgcUtils::DuplicateString(ushort const *,ushort * *)
0x18001ca57  mov     edi, eax
0x18001ca59  test    eax, eax
0x18001ca5b  jns     short loc_18001CA7A
0x18001ca5d  mov     rcx, [rsp+28h]; this
0x18001ca62  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001ca69  mov     r9d, eax; char *
0x18001ca6c  mov     edx, 6B6h; void *
0x18001ca71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca76  mov     eax, edi
0x18001ca78  jmp     short loc_18001CA7F
0x18001ca7a  inc     dword ptr [rbx+8]
0x18001ca7d  xor     eax, eax
0x18001ca7f  mov     rbx, [rsp+28h+arg_0]
0x18001ca84  mov     rsi, [rsp+28h+arg_8]
0x18001ca89  add     rsp, 20h
0x18001ca8d  pop     rdi
0x18001ca8e  retn
```
