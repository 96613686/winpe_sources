# IsCombinableGenericTextOut(HDC__ *,void * *,int)

- ea: `0x1800260b8`
- end: `0x1800261c0`
- name: `?IsCombinableGenericTextOut@@YAHPEAUHDC__@@PEAPEAXH@Z`
- size: `264`
- prototype: `__int64 __fastcall(HDC, void **, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024c40`

## callees

- `0x180009760`
- `0x1800260b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002613c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002613c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002611a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002611a`
- `TextShaping!ShapingGetCombiningOptions` at `0x180026189`
- `TextShaping!ShapingGetCombiningOptions` at `0x180026189`

## pseudocode

```c
__int64 __fastcall IsCombinableGenericTextOut(HDC a1, void **a2, int a3)
{
  __int64 v3; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  int updated; // ebx
  __int64 v9; // r9
  int v10; // eax

  v3 = a3;
  if ( !a2 )
    goto LABEL_12;
  if ( *a2 )
  {
    v6 = *((_QWORD *)*a2 + 10);
    if ( v6 )
    {
      if ( a3 < 0 )
        goto LABEL_9;
      if ( a3 >= 225 || (v7 = *(_QWORD *)(v6 + 8LL * a3 + 344)) == 0 )
      {
LABEL_12:
        v9 = v3;
LABEL_13:
        if ( (char *)funcs_180021072[3 * v9] != (char *)ShlTextOut )
          return 0;
        goto LABEL_10;
      }
      if ( v7 != -1 )
        goto LABEL_9;
    }
  }
  EnterCriticalSection(&csCache);
  updated = UpdateCache(a2, v3, a1);
  LeaveCriticalSection(&csCache);
  if ( updated < 0 )
    goto LABEL_12;
LABEL_9:
  v9 = v3;
  v10 = *(_DWORD *)(*((_QWORD *)*a2 + 10) + 4 * (v3 >> 5) + 248);
  if ( !_bittest(&v10, (int)v3 % 32) )
    goto LABEL_13;
LABEL_10:
  if ( (_DWORD)v3 != 19 )
    return ((unsigned int)ShapingGetCombiningOptions(*((unsigned __int16 *)&ShlScriptSupport + 4 * v9), 1) >> 1) & 1;
  return 0;
}

```

## disassembly

```asm
0x1800260b8  push    rbx
0x1800260ba  push    rbp
0x1800260bb  push    rsi
0x1800260bc  push    rdi
0x1800260bd  sub     rsp, 28h
0x1800260c1  movsxd  rdi, r8d
0x1800260c4  mov     rsi, rdx
0x1800260c7  lea     rbp, __ImageBase
0x1800260ce  mov     rbx, rcx
0x1800260d1  test    rdx, rdx
0x1800260d4  jz      loc_1800261A4
0x1800260da  mov     rax, [rdx]
0x1800260dd  test    rax, rax
0x1800260e0  jz      short loc_180026113
0x1800260e2  mov     rcx, [rax+50h]
0x1800260e6  test    rcx, rcx
0x1800260e9  jz      short loc_180026113
0x1800260eb  test    r8d, r8d
0x1800260ee  js      short loc_18002614C
0x1800260f0  cmp     edi, 0E1h
0x1800260f6  jge     loc_1800261A4
0x1800260fc  mov     rcx, [rcx+rdi*8+158h]
0x180026104  test    rcx, rcx
0x180026107  jz      loc_1800261A4
0x18002610d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180026111  jnz     short loc_18002614C
0x180026113  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002611a  call    cs:__imp_EnterCriticalSection
0x180026121  nop     dword ptr [rax+rax+00h]
0x180026126  mov     r8, rbx; HDC
0x180026129  mov     edx, edi; int
0x18002612b  mov     rcx, rsi; void **
0x18002612e  call    ?UpdateCache@@YAJPEAPEAXHPEAUHDC__@@@Z; UpdateCache(void * *,int,HDC__ *)
0x180026133  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002613a  mov     ebx, eax
0x18002613c  call    cs:__imp_LeaveCriticalSection
0x180026143  nop     dword ptr [rax+rax+00h]
0x180026148  test    ebx, ebx
0x18002614a  js      short loc_1800261A4
0x18002614c  mov     rax, [rsi]
0x18002614f  mov     r10d, 20h ; ' '
0x180026155  mov     r8, rdi
0x180026158  mov     r9, rdi
0x18002615b  sar     r8, 5
0x18002615f  mov     rcx, [rax+50h]
0x180026163  mov     eax, edi
0x180026165  cdq
0x180026166  idiv    r10d
0x180026169  mov     eax, [rcx+r8*4+0F8h]
0x180026171  bt      eax, edx
0x180026174  jnb     short loc_1800261A7
0x180026176  cmp     edi, 13h
0x180026179  jz      short loc_1800261BC
0x18002617b  movzx   ecx, ss:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[rbp+r9*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180026184  mov     edx, 1
0x180026189  call    cs:__imp_ShapingGetCombiningOptions
0x180026190  nop     dword ptr [rax+rax+00h]
0x180026195  shr     eax, 1
0x180026197  and     eax, 1
0x18002619a  add     rsp, 28h
0x18002619e  pop     rdi
0x18002619f  pop     rsi
0x1800261a0  pop     rbp
0x1800261a1  pop     rbx
0x1800261a2  retn
0x1800261a4  mov     r9, rdi
0x1800261a7  lea     rax, [r9+r9*2]
0x1800261ab  lea     rcx, ?ShlTextOut@@YAJPEAUHDC__@@PEAPEAXHHIPEBUtagRECT@@PEBUtag_SCRIPT_ANALYSIS@@PEBGHPEBH5PEBUtagGOFFSET@@@Z; ShlTextOut(HDC__ *,void * *,int,int,uint,tagRECT const *,tag_SCRIPT_ANALYSIS const *,ushort const *,int,int const *,int const *,tagGOFFSET const *)
0x1800261b2  cmp     ss:rva funcs_180021072[rbp+rax*8], rcx
0x1800261ba  jz      short loc_180026176
0x1800261bc  xor     eax, eax
0x1800261be  jmp     short loc_18002619A
```
