# SSI_ELEMENT_LIST::AppendCommand(SSI_COMMANDS,SSI_TAGS,char *)

- ea: `0x180002cb0`
- end: `0x180002db7`
- name: `?AppendCommand@SSI_ELEMENT_LIST@@AEAAHW4SSI_COMMANDS@@W4SSI_TAGS@@PEAD@Z`
- size: `263`
- prototype: `__int64 __fastcall(__int64, int, int, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002dc0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002da4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002da4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002d87`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180002d87`
- `iisutil!?Escape@STRA@@QEAAJ_N0@Z` at `0x180002d3e`
- `iisutil!?Escape@STRA@@QEAAJ_N0@Z` at `0x180002d3e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002d1f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180002d1f`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002d0a`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180002d0a`

## pseudocode

```c
__int64 __fastcall SSI_ELEMENT_LIST::AppendCommand(__int64 a1, int a2, int a3, const char *a4)
{
  char *v8; // rax
  char *v9; // rbx
  STRA *v10; // rax
  _QWORD *v11; // rdx
  STRA *v13; // rdi

  v8 = (char *)operator new(0x30u);
  v9 = v8;
  if ( !v8 )
  {
    SetLastError(8u);
    return 0;
  }
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 4) = 0;
  *(_DWORD *)v8 = 541672787;
  *((_DWORD *)v8 + 1) = a2;
  *((_DWORD *)v8 + 2) = a3;
  v10 = (STRA *)operator new(0x38u);
  if ( v10 )
    v10 = STRA::STRA(v10);
  *((_QWORD *)v9 + 2) = v10;
  if ( !v10
    || (int)STRA::Copy(v10, a4) < 0
    || *((_DWORD *)v9 + 1) == 5 && *((_DWORD *)v9 + 2) != 3 && (int)STRA::Escape(*((STRA **)v9 + 2), 0, 1) < 0 )
  {
    v13 = (STRA *)*((_QWORD *)v9 + 2);
    *(_DWORD *)v9 = 1716077907;
    if ( v13 )
    {
      STRA::~STRA(v13);
      operator delete(v13);
    }
    operator delete(v9);
    return 0;
  }
  v11 = *(_QWORD **)(a1 + 16);
  if ( *v11 != a1 + 8 )
    __fastfail(3u);
  *((_QWORD *)v9 + 4) = a1 + 8;
  *((_QWORD *)v9 + 5) = v11;
  *v11 = v9 + 32;
  *(_QWORD *)(a1 + 16) = v9 + 32;
  return 1;
}

```

## disassembly

```asm
0x180002cb0  push    rbx
0x180002cb2  push    rbp
0x180002cb3  push    rsi
0x180002cb4  push    rdi
0x180002cb5  push    r14
0x180002cb7  sub     rsp, 20h
0x180002cbb  mov     rbp, rcx
0x180002cbe  mov     r14, r9
0x180002cc1  mov     ecx, 30h ; '0'; Size
0x180002cc6  mov     edi, r8d
0x180002cc9  mov     esi, edx
0x180002ccb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002cd0  mov     rbx, rax
0x180002cd3  test    rax, rax
0x180002cd6  jz      loc_180002D9F
0x180002cdc  mov     qword ptr [rax+10h], 0
0x180002ce4  mov     ecx, 38h ; '8'; Size
0x180002ce9  mov     qword ptr [rax+20h], 0
0x180002cf1  mov     dword ptr [rax], 20494553h
0x180002cf7  mov     [rax+4], esi
0x180002cfa  mov     [rax+8], edi
0x180002cfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d02  test    rax, rax
0x180002d05  jz      short loc_180002D10
0x180002d07  mov     rcx, rax
0x180002d0a  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180002d10  mov     [rbx+10h], rax
0x180002d14  test    rax, rax
0x180002d17  jz      short loc_180002D75
0x180002d19  mov     rdx, r14
0x180002d1c  mov     rcx, rax
0x180002d1f  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180002d25  test    eax, eax
0x180002d27  js      short loc_180002D75
0x180002d29  cmp     dword ptr [rbx+4], 5
0x180002d2d  jnz     short loc_180002D48
0x180002d2f  cmp     dword ptr [rbx+8], 3
0x180002d33  jz      short loc_180002D48
0x180002d35  mov     rcx, [rbx+10h]
0x180002d39  mov     r8b, 1
0x180002d3c  xor     edx, edx
0x180002d3e  call    cs:__imp_?Escape@STRA@@QEAAJ_N0@Z; STRA::Escape(bool,bool)
0x180002d44  test    eax, eax
0x180002d46  js      short loc_180002D75
0x180002d48  lea     rax, [rbp+8]
0x180002d4c  mov     rdx, [rax+8]
0x180002d50  cmp     [rdx], rax
0x180002d53  jz      short loc_180002D5C
0x180002d55  mov     ecx, 3
0x180002d5a  int     29h; Win8: RtlFailFast(ecx)
0x180002d5c  lea     rcx, [rbx+20h]
0x180002d60  mov     [rcx], rax
0x180002d63  mov     [rcx+8], rdx
0x180002d67  mov     [rdx], rcx
0x180002d6a  mov     [rax+8], rcx
0x180002d6e  mov     eax, 1
0x180002d73  jmp     short loc_180002DAC
0x180002d75  mov     rdi, [rbx+10h]
0x180002d79  mov     dword ptr [rbx], 66494553h
0x180002d7f  test    rdi, rdi
0x180002d82  jz      short loc_180002D95
0x180002d84  mov     rcx, rdi
0x180002d87  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002d8d  mov     rcx, rdi; Block
0x180002d90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d95  mov     rcx, rbx; Block
0x180002d98  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d9d  jmp     short loc_180002DAA
0x180002d9f  mov     ecx, 8; dwErrCode
0x180002da4  call    cs:__imp_SetLastError
0x180002daa  xor     eax, eax
0x180002dac  add     rsp, 20h
0x180002db0  pop     r14
0x180002db2  pop     rdi
0x180002db3  pop     rsi
0x180002db4  pop     rbp
0x180002db5  pop     rbx
0x180002db6  retn
```
