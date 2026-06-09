# std::_Future_error_category2::message(int)

- ea: `0x180027490`
- end: `0x180027540`
- name: `?message@_Future_error_category2@std@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@H@Z`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180006d1c`
- `0x180027490`

## import_xrefs

- `msvcp_win!?_Syserror_map@std@@YAPEBDH@Z` at `0x1800274b3`
- `msvcp_win!?_Syserror_map@std@@YAPEBDH@Z` at `0x1800274b3`

## string_xrefs

- `0x1800274fa`: `future already retrieved`
- `0x1800274f1`: `promise already satisfied`

## pseudocode

```c
__int64 __fastcall std::_Future_error_category2::message(__int64 a1, __int64 a2, int a3)
{
  const char *v4; // rax
  __int64 v5; // r8
  const char *v6; // rdx

  switch ( a3 )
  {
    case 1:
      v6 = "broken promise";
      break;
    case 2:
      v6 = "future already retrieved";
      break;
    case 3:
      v6 = "promise already satisfied";
      break;
    case 4:
      v6 = "no state";
      break;
    default:
      v4 = std::_Syserror_map(a3);
      v5 = -1;
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 24) = 0;
      do
        ++v5;
      while ( v4[v5] );
      v6 = v4;
      goto LABEL_14;
  }
  v5 = -1;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 0;
  do
    ++v5;
  while ( v6[v5] );
LABEL_14:
  std::string::_Construct<1,char const *>(a2, v6, v5);
  return a2;
}

```

## disassembly

```asm
0x180027490  push    rbx
0x180027492  sub     rsp, 30h
0x180027496  mov     ecx, r8d
0x180027499  mov     rbx, rdx
0x18002749c  sub     ecx, 1
0x18002749f  jz      short loc_180027503
0x1800274a1  sub     ecx, 1
0x1800274a4  jz      short loc_1800274FA
0x1800274a6  sub     ecx, 1
0x1800274a9  jz      short loc_1800274F1
0x1800274ab  cmp     ecx, 1
0x1800274ae  jz      short loc_1800274E8
0x1800274b0  mov     ecx, r8d
0x1800274b3  call    cs:__imp_?_Syserror_map@std@@YAPEBDH@Z; std::_Syserror_map(int)
0x1800274ba  nop     dword ptr [rax+rax+00h]
0x1800274bf  xorps   xmm0, xmm0
0x1800274c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800274c6  movups  xmmword ptr [rbx], xmm0
0x1800274c9  mov     qword ptr [rbx+10h], 0
0x1800274d1  mov     qword ptr [rbx+18h], 0
0x1800274d9  inc     r8
0x1800274dc  cmp     byte ptr [rax+r8], 0
0x1800274e1  jnz     short loc_1800274D9
0x1800274e3  mov     rdx, rax
0x1800274e6  jmp     short loc_18002752E
0x1800274e8  lea     rdx, aNoState; "no state"
0x1800274ef  jmp     short loc_18002750A
0x1800274f1  lea     rdx, aPromiseAlready; "promise already satisfied"
0x1800274f8  jmp     short loc_18002750A
0x1800274fa  lea     rdx, aFutureAlreadyR; "future already retrieved"
0x180027501  jmp     short loc_18002750A
0x180027503  lea     rdx, aBrokenPromise; "broken promise"
0x18002750a  xorps   xmm0, xmm0
0x18002750d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027511  movups  xmmword ptr [rbx], xmm0
0x180027514  mov     qword ptr [rbx+10h], 0
0x18002751c  mov     qword ptr [rbx+18h], 0
0x180027524  inc     r8
0x180027527  cmp     byte ptr [rdx+r8], 0
0x18002752c  jnz     short loc_180027524
0x18002752e  mov     rcx, rbx
0x180027531  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180027536  mov     rax, rbx
0x180027539  add     rsp, 30h
0x18002753d  pop     rbx
0x18002753e  retn
```
