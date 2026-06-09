# CategoryResolver::GetPaths(ushort *)

- ea: `0x18003fc9c`
- end: `0x18003fdc0`
- name: `?GetPaths@CategoryResolver@@QEAA?AV?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@PEAG@Z`
- size: `292`
- prototype: `__int64 __fastcall(__int64, __int64, const BYTE *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180012eb4`
- `0x180018f74`

## callees

- `0x180021cf4`
- `0x180021d14`
- `0x18003fc9c`
- `0x18003fdc8`
- `0x180047010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18003fd43`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18003fd43`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CategoryResolver::GetPaths(__int64 a1, __int64 a2, const BYTE *a3)
{
  __int64 v4; // rcx
  const BYTE *v5; // rax
  __int64 v6; // r9
  unsigned __int64 v7; // rax
  IStream *v8; // rax
  const char *v9; // r9
  IStream *v10; // rbx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a3 )
  {
    v4 = 0x3FFFFFFF;
    v5 = a3;
    do
    {
      if ( !*(_WORD *)v5 )
        break;
      v5 += 2;
      --v4;
    }
    while ( v4 );
    v6 = v4 == 0 ? 0x80070057 : 0;
    if ( v4 )
    {
      v7 = (2 * (0x3FFFFFFF - v4)) & -(__int64)(v4 != 0);
      goto LABEL_9;
    }
  }
  else
  {
    v6 = 2147942487LL;
  }
  v7 = 0;
LABEL_9:
  if ( (int)v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      (const char *)v6,
      v12);
  if ( v7 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      v7 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      v12);
  v8 = SHCreateMemStream(a3, v7);
  v10 = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x44,
      (int)"onecoreuap\\admin\\prov\\lib\\categoryresolver.cpp",
      v9);
  CategoryResolver::GetPaths(retaddr, a2, v8);
  (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 16LL))(v10);
  return a2;
}

```

## disassembly

```asm
0x18003fc9c  mov     rax, rsp
0x18003fc9f  mov     [rax+10h], rbx
0x18003fca3  mov     [rax+18h], rsi
0x18003fca7  mov     [rax+8], rcx
0x18003fcab  push    rdi
0x18003fcac  sub     rsp, 30h
0x18003fcb0  mov     rdi, rdx
0x18003fcb3  xor     esi, esi
0x18003fcb5  mov     [rax+8], rsi
0x18003fcb9  test    r8, r8
0x18003fcbc  jz      short loc_18003FD02
0x18003fcbe  mov     r10d, 3FFFFFFFh
0x18003fcc4  mov     ecx, r10d
0x18003fcc7  mov     rax, r8
0x18003fcca  cmp     [rax], si
0x18003fccd  jz      short loc_18003FCD9
0x18003fccf  add     rax, 2
0x18003fcd3  sub     rcx, 1
0x18003fcd7  jnz     short loc_18003FCCA
0x18003fcd9  mov     rax, rcx
0x18003fcdc  neg     rax
0x18003fcdf  sbb     r9d, r9d
0x18003fce2  not     r9d
0x18003fce5  and     r9d, 80070057h
0x18003fcec  test    rcx, rcx
0x18003fcef  jz      short loc_18003FD08
0x18003fcf1  sub     r10, rcx
0x18003fcf4  add     r10, r10
0x18003fcf7  neg     rcx
0x18003fcfa  sbb     rax, rax
0x18003fcfd  and     rax, r10
0x18003fd00  jmp     short loc_18003FD0B
0x18003fd02  mov     r9d, 80070057h; char *
0x18003fd08  mov     rax, rsi
0x18003fd0b  mov     rcx, [rsp+38h]; this
0x18003fd10  test    r9d, r9d
0x18003fd13  js      loc_18003FD9C
0x18003fd19  mov     r10d, 0FFFFFFFFh
0x18003fd1f  cmp     rax, r10
0x18003fd22  mov     edx, eax
0x18003fd24  jbe     short loc_18003FD29
0x18003fd26  mov     edx, r10d; cbInit
0x18003fd29  cmp     r10, rax
0x18003fd2c  sbb     r9d, r9d
0x18003fd2f  and     r9d, 80070216h; char *
0x18003fd36  mov     rcx, [rsp+38h]; this
0x18003fd3b  cmp     rax, r10
0x18003fd3e  ja      short loc_18003FDAE
0x18003fd40  mov     rcx, r8; pInit
0x18003fd43  call    cs:__imp_SHCreateMemStream
0x18003fd49  mov     rbx, rax
0x18003fd4c  mov     [rsp+38h+arg_0], rax
0x18003fd51  mov     rcx, [rsp+38h]; this
0x18003fd56  test    rax, rax
0x18003fd59  jz      short loc_18003FD8A
0x18003fd5b  mov     r8, rax
0x18003fd5e  mov     rdx, rdi
0x18003fd61  call    ?GetPaths@CategoryResolver@@QEAA?AV?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@PEAUIStream@@@Z; CategoryResolver::GetPaths(IStream *)
0x18003fd66  nop
0x18003fd67  mov     rax, [rbx]
0x18003fd6a  mov     rcx, rbx
0x18003fd6d  mov     rax, [rax+10h]
0x18003fd71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd76  nop
0x18003fd77  mov     rax, rdi
0x18003fd7a  mov     rbx, [rsp+38h+arg_8]
0x18003fd7f  mov     rsi, [rsp+38h+arg_10]
0x18003fd84  add     rsp, 30h
0x18003fd88  pop     rdi
0x18003fd89  retn
0x18003fd8a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003fd91  mov     edx, 44h ; 'D'; void *
0x18003fd96  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18003fd9c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003fda3  mov     edx, 40h ; '@'; void *
0x18003fda8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fdae  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\categoryr"...
0x18003fdb5  mov     edx, 41h ; 'A'; void *
0x18003fdba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
