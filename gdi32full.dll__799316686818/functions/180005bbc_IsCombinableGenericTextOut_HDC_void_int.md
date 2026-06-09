# IsCombinableGenericTextOut(HDC__ *,void * *,int)

- ea: `0x180005bbc`
- end: `0x180005cb1`
- name: `?IsCombinableGenericTextOut@@YAHPEAUHDC__@@PEAPEAXH@Z`
- size: `245`
- prototype: `__int64 __fastcall(HDC, void **, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011fc0`

## callees

- `0x180005bbc`
- `0x180005fac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005c3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c1e`
- `TextShaping!ShapingGetCombiningOptions` at `0x180005c81`
- `TextShaping!ShapingGetCombiningOptions` at `0x180005c81`

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
        if ( (char *)funcs_180014CAF[3 * v9] != (char *)ShlTextOut )
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
0x180005bbc  push    rbx
0x180005bbe  push    rbp
0x180005bbf  push    rsi
0x180005bc0  push    rdi
0x180005bc1  sub     rsp, 28h
0x180005bc5  movsxd  rdi, r8d
0x180005bc8  mov     rsi, rdx
0x180005bcb  lea     rbp, __ImageBase
0x180005bd2  mov     rbx, rcx
0x180005bd5  test    rdx, rdx
0x180005bd8  jz      loc_180005C95
0x180005bde  mov     rax, [rdx]
0x180005be1  test    rax, rax
0x180005be4  jz      short loc_180005C17
0x180005be6  mov     rcx, [rax+50h]
0x180005bea  test    rcx, rcx
0x180005bed  jz      short loc_180005C17
0x180005bef  test    r8d, r8d
0x180005bf2  js      short loc_180005C44
0x180005bf4  cmp     edi, 0E1h
0x180005bfa  jge     loc_180005C95
0x180005c00  mov     rcx, [rcx+rdi*8+158h]
0x180005c08  test    rcx, rcx
0x180005c0b  jz      loc_180005C95
0x180005c11  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005c15  jnz     short loc_180005C44
0x180005c17  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005c1e  call    cs:__imp_EnterCriticalSection
0x180005c24  mov     r8, rbx; HDC
0x180005c27  mov     edx, edi; int
0x180005c29  mov     rcx, rsi; void **
0x180005c2c  call    ?UpdateCache@@YAJPEAPEAXHPEAUHDC__@@@Z; UpdateCache(void * *,int,HDC__ *)
0x180005c31  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005c38  mov     ebx, eax
0x180005c3a  call    cs:__imp_LeaveCriticalSection
0x180005c40  test    ebx, ebx
0x180005c42  js      short loc_180005C95
0x180005c44  mov     rax, [rsi]
0x180005c47  mov     r10d, 20h ; ' '
0x180005c4d  mov     r8, rdi
0x180005c50  mov     r9, rdi
0x180005c53  sar     r8, 5
0x180005c57  mov     rcx, [rax+50h]
0x180005c5b  mov     eax, edi
0x180005c5d  cdq
0x180005c5e  idiv    r10d
0x180005c61  mov     eax, [rcx+r8*4+0F8h]
0x180005c69  bt      eax, edx
0x180005c6c  jnb     short loc_180005C98
0x180005c6e  cmp     edi, 13h
0x180005c71  jz      short loc_180005CAD
0x180005c73  movzx   ecx, ss:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[rbp+r9*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180005c7c  mov     edx, 1
0x180005c81  call    cs:__imp_ShapingGetCombiningOptions
0x180005c87  shr     eax, 1
0x180005c89  and     eax, 1
0x180005c8c  add     rsp, 28h
0x180005c90  pop     rdi
0x180005c91  pop     rsi
0x180005c92  pop     rbp
0x180005c93  pop     rbx
0x180005c94  retn
0x180005c95  mov     r9, rdi
0x180005c98  lea     rax, [r9+r9*2]
0x180005c9c  lea     rcx, ?ShlTextOut@@YAJPEAUHDC__@@PEAPEAXHHIPEBUtagRECT@@PEBUtag_SCRIPT_ANALYSIS@@PEBGHPEBH5PEBUtagGOFFSET@@@Z; ShlTextOut(HDC__ *,void * *,int,int,uint,tagRECT const *,tag_SCRIPT_ANALYSIS const *,ushort const *,int,int const *,int const *,tagGOFFSET const *)
0x180005ca3  cmp     ss:rva funcs_180014CAF[rbp+rax*8], rcx
0x180005cab  jz      short loc_180005C6E
0x180005cad  xor     eax, eax
0x180005caf  jmp     short loc_180005C8C
```
